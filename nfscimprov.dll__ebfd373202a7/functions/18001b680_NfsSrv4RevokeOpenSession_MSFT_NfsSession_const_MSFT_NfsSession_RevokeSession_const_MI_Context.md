# NfsSrv4RevokeOpenSession(_MSFT_NfsSession const *,_MSFT_NfsSession_RevokeSession const *,_MI_Context *)

- ea: `0x18001b680`
- end: `0x18001b902`
- name: `?NfsSrv4RevokeOpenSession@@YAKPEBU_MSFT_NfsSession@@PEBU_MSFT_NfsSession_RevokeSession@@PEAU_MI_Context@@@Z`
- size: `642`
- prototype: `unsigned int(const struct _MSFT_NfsSession *, const struct _MSFT_NfsSession_RevokeSession *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800092c0`

## callees

- `0x1800098c4`
- `0x18000b2ac`
- `0x18000b620`
- `0x18000be78`
- `0x18000ce30`
- `0x180019504`
- `0x18001b680`
- `0x180029c30`
- `0x18002a4dc`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001b754`
- `ntdll!RtlInitUnicodeString` at `0x18001b754`
- `ntdll!RtlGUIDFromString` at `0x18001b7b6`
- `ntdll!RtlGUIDFromString` at `0x18001b7b6`
- `KERNEL32!GetLastError` at `0x18001b83e`
- `KERNEL32!GetLastError` at `0x18001b864`
- `KERNEL32!GetLastError` at `0x18001b83e`
- `KERNEL32!GetLastError` at `0x18001b864`
- `KERNEL32!CloseHandle` at `0x18001b85c`
- `KERNEL32!CloseHandle` at `0x18001b85c`
- `KERNEL32!CreateFileW` at `0x18001b7fa`
- `KERNEL32!CreateFileW` at `0x18001b7fa`
- `KERNEL32!DeviceIoControl` at `0x18001b834`
- `KERNEL32!DeviceIoControl` at `0x18001b834`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NfsSrv4RevokeOpenSession(
        const struct _MSFT_NfsSession *a1,
        const struct _MSFT_NfsSession_RevokeSession *a2,
        MI_Instance *a3)
{
  DWORD IsClusterNode; // ebx
  __int64 v6; // rcx
  DWORD ResourceIdForNetworkName; // eax
  HANDLE FileW; // rdi
  enum _MI_Result v9; // eax
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-BCh] BYREF
  _QWORD v13[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v14; // [rsp+58h] [rbp-A8h]
  MI_Instance *v15; // [rsp+60h] [rbp-A0h]
  int v16; // [rsp+68h] [rbp-98h]
  __int64 v17; // [rsp+6Ch] [rbp-94h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  MI_Instance self; // [rsp+90h] [rbp-70h] BYREF
  int ReturnValue; // [rsp+D0h] [rbp-30h]
  char v21; // [rsp+D4h] [rbp-2Ch]
  __int128 v22; // [rsp+E0h] [rbp-20h] BYREF
  GUID Guid; // [rsp+F0h] [rbp-10h] BYREF
  GUID InBuffer; // [rsp+100h] [rbp+0h] BYREF
  char v25; // [rsp+110h] [rbp+10h]
  __int128 v26; // [rsp+114h] [rbp+14h]

  IsClusterNode = 0;
  BytesReturned = 0;
  v22 = 0;
  Guid = 0;
  memset_0(&InBuffer, 0, 0x40u);
  DestinationString = 0;
  v11 = 0;
  self.ft = 0;
  memset_0(&self.classDecl, 0, sizeof(MI_Instance));
  v13[0] = &CWMIContext::`vftable';
  v15 = a3;
  v13[1] = 0;
  v14 = 0;
  v17 = 0;
  v16 = 0;
  if ( !*((_BYTE *)a1 + 72) || !*((_BYTE *)a1 + 88) )
    goto LABEL_23;
  if ( !CWMIContext::PromptUser((CWMIContext *)v13, 0x40001030u, *((_QWORD *)a1 + 8)) )
    goto LABEL_19;
  RtlInitUnicodeString(&DestinationString, *((PCWSTR *)a1 + 8));
  v25 = 1;
  IsClusterNode = NfsClusterIsClusterNode(v6, &v11);
  if ( !IsClusterNode )
  {
    if ( !v11 )
      goto LABEL_10;
    ResourceIdForNetworkName = NfsClusGetResourceIdForNetworkName(*((LPCWSTR *)a1 + 10), (__int64)&v22);
    IsClusterNode = ResourceIdForNetworkName;
    if ( !ResourceIdForNetworkName )
    {
      v26 = v22;
      v25 = 0;
      goto LABEL_10;
    }
    if ( ResourceIdForNetworkName == 1168 )
    {
      IsClusterNode = 0;
      v25 = 1;
LABEL_10:
      if ( RtlGUIDFromString(&DestinationString, &Guid) >= 0 )
      {
        InBuffer = Guid;
        FileW = CreateFileW(L"\\\\.\\NfsSvr", 0x40000000u, 0, 0, 3u, 0x1000080u, 0);
        if ( FileW == (HANDLE)-1LL )
        {
          IsClusterNode = GetLastError();
        }
        else
        {
          if ( !DeviceIoControl(FileW, 0x10008598u, &InBuffer, 0x40u, 0, 0, &BytesReturned, 0) )
          {
            IsClusterNode = GetLastError();
            if ( IsClusterNode == 50 )
              NfsPostNfsv4DisabledError(50, v13);
          }
          CloseHandle(FileW);
        }
      }
      else
      {
        IsClusterNode = 13;
      }
    }
  }
  LODWORD(v17) = IsClusterNode;
LABEL_19:
  if ( !a3 || !a3->ft )
  {
LABEL_23:
    v9 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_24;
  }
  v9 = ((unsigned int (__fastcall *)(MI_Instance *, void *, MI_Instance *))a3->ft->GetClassNameA)(
         a3,
         &MSFT_NfsSession_RevokeSession_rtti,
         &self);
  if ( v9 == MI_RESULT_OK )
  {
    ReturnValue = CWMIContext::GetReturnValue((CWMIContext *)v13);
    v21 = 1;
    MI_Instance_Destruct(a3);
    v9 = MI_Instance_Destruct(&self);
  }
LABEL_24:
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v13, v9);
  CWMIContext::~CWMIContext((CWMIContext *)v13);
  return IsClusterNode;
}

```

## disassembly

```asm
0x18001b680  mov     [rsp-8+arg_8], rbx
0x18001b685  mov     [rsp-8+arg_18], rsi
0x18001b68a  push    rbp
0x18001b68b  push    rdi
0x18001b68c  push    r14
0x18001b68e  lea     rbp, [rsp-50h]
0x18001b693  sub     rsp, 150h
0x18001b69a  mov     rax, cs:__security_cookie
0x18001b6a1  xor     rax, rsp
0x18001b6a4  mov     [rbp+60h+var_20], rax
0x18001b6a8  mov     rsi, r8
0x18001b6ab  mov     rdi, rcx
0x18001b6ae  xor     r14d, r14d
0x18001b6b1  mov     ebx, r14d
0x18001b6b4  mov     [rsp+160h+BytesReturned], r14d
0x18001b6b9  xorps   xmm0, xmm0
0x18001b6bc  movups  [rbp+60h+var_80], xmm0
0x18001b6c0  xorps   xmm1, xmm1
0x18001b6c3  movups  xmmword ptr [rbp+60h+Guid.Data1], xmm1
0x18001b6c7  xor     edx, edx; Val
0x18001b6c9  lea     r8d, [r14+40h]; Size
0x18001b6cd  lea     rcx, [rbp+60h+InBuffer]; void *
0x18001b6d1  call    memset_0
0x18001b6d6  xorps   xmm0, xmm0
0x18001b6d9  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x18001b6de  mov     [rsp+160h+var_120], r14d
0x18001b6e3  mov     [rbp+60h+self.ft], r14
0x18001b6e7  xor     edx, edx; Val
0x18001b6e9  lea     r8d, [r14+40h]; Size
0x18001b6ed  lea     rcx, [rbp+60h+self.classDecl]; void *
0x18001b6f1  call    memset_0
0x18001b6f6  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18001b6fd  mov     [rsp+160h+var_118], rax
0x18001b702  mov     [rsp+160h+var_100], rsi
0x18001b707  mov     [rsp+160h+var_110], r14
0x18001b70c  mov     [rsp+160h+var_108], r14w
0x18001b712  mov     [rsp+160h+var_F4], r14
0x18001b717  mov     [rsp+160h+var_F8], r14d
0x18001b71c  cmp     [rdi+48h], r14b
0x18001b720  jz      loc_18001B8C0
0x18001b726  cmp     [rdi+58h], r14b
0x18001b72a  jz      loc_18001B8C0
0x18001b730  mov     r8, [rdi+40h]
0x18001b734  mov     edx, 40001030h; unsigned int
0x18001b739  lea     rcx, [rsp+160h+var_118]; this
0x18001b73e  call    ?PromptUser@CWMIContext@@UEAAEKZZ; CWMIContext::PromptUser(ulong,...)
0x18001b743  test    al, al
0x18001b745  jz      loc_18001B870
0x18001b74b  mov     rdx, [rdi+40h]; SourceString
0x18001b74f  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x18001b754  call    cs:__imp_RtlInitUnicodeString
0x18001b75a  mov     [rbp+60h+var_50], 1
0x18001b75e  lea     rdx, [rsp+160h+var_120]
0x18001b763  call    NfsClusterIsClusterNode
0x18001b768  mov     ebx, eax
0x18001b76a  test    eax, eax
0x18001b76c  jnz     loc_18001B86C
0x18001b772  cmp     [rsp+160h+var_120], r14d
0x18001b777  jz      short loc_18001B7AD
0x18001b779  lea     rdx, [rbp+60h+var_80]
0x18001b77d  mov     rcx, [rdi+50h]; lpszResourceName
0x18001b781  call    NfsClusGetResourceIdForNetworkName
0x18001b786  mov     ebx, eax
0x18001b788  test    eax, eax
0x18001b78a  jnz     short loc_18001B79B
0x18001b78c  movups  xmm0, [rbp+60h+var_80]
0x18001b790  movdqu  [rbp+60h+var_4C], xmm0
0x18001b795  mov     [rbp+60h+var_50], r14b
0x18001b799  jmp     short loc_18001B7AD
0x18001b79b  cmp     eax, 490h
0x18001b7a0  jnz     loc_18001B86C
0x18001b7a6  mov     ebx, r14d
0x18001b7a9  mov     [rbp+60h+var_50], 1
0x18001b7ad  lea     rdx, [rbp+60h+Guid]; Guid
0x18001b7b1  lea     rcx, [rsp+160h+DestinationString]; GuidString
0x18001b7b6  call    cs:__imp_RtlGUIDFromString
0x18001b7bc  test    eax, eax
0x18001b7be  jns     short loc_18001B7CA
0x18001b7c0  mov     ebx, 0Dh
0x18001b7c5  jmp     loc_18001B86C
0x18001b7ca  movups  xmm0, xmmword ptr [rbp+60h+Guid.Data1]
0x18001b7ce  movdqu  [rbp+60h+InBuffer], xmm0
0x18001b7d3  mov     [rsp+160h+hTemplateFile], r14; hTemplateFile
0x18001b7d8  mov     [rsp+160h+dwFlagsAndAttributes], 1000080h; dwFlagsAndAttributes
0x18001b7e0  mov     [rsp+160h+dwCreationDisposition], 3; dwCreationDisposition
0x18001b7e8  xor     r9d, r9d; lpSecurityAttributes
0x18001b7eb  xor     r8d, r8d; dwShareMode
0x18001b7ee  mov     edx, 40000000h; dwDesiredAccess
0x18001b7f3  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x18001b7fa  call    cs:__imp_CreateFileW
0x18001b800  mov     rdi, rax
0x18001b803  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b807  jz      short loc_18001B864
0x18001b809  mov     [rsp+160h+lpOverlapped], r14; lpOverlapped
0x18001b80e  lea     rax, [rsp+160h+BytesReturned]
0x18001b813  mov     [rsp+160h+hTemplateFile], rax; lpBytesReturned
0x18001b818  mov     [rsp+160h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x18001b81d  mov     qword ptr [rsp+160h+dwCreationDisposition], r14; lpOutBuffer
0x18001b822  mov     r9d, 40h ; '@'; nInBufferSize
0x18001b828  lea     r8, [rbp+60h+InBuffer]; lpInBuffer
0x18001b82c  mov     edx, 10008598h; dwIoControlCode
0x18001b831  mov     rcx, rdi; hDevice
0x18001b834  call    cs:__imp_DeviceIoControl
0x18001b83a  test    eax, eax
0x18001b83c  jnz     short loc_18001B859
0x18001b83e  call    cs:__imp_GetLastError
0x18001b844  mov     ebx, eax
0x18001b846  mov     ecx, 32h ; '2'
0x18001b84b  cmp     eax, ecx
0x18001b84d  jnz     short loc_18001B859
0x18001b84f  lea     rdx, [rsp+160h+var_118]
0x18001b854  call    NfsPostNfsv4DisabledError
0x18001b859  mov     rcx, rdi; hObject
0x18001b85c  call    cs:__imp_CloseHandle
0x18001b862  jmp     short loc_18001B86C
0x18001b864  call    cs:__imp_GetLastError
0x18001b86a  mov     ebx, eax
0x18001b86c  mov     dword ptr [rsp+160h+var_F4], ebx
0x18001b870  test    rsi, rsi
0x18001b873  jz      short loc_18001B8C0
0x18001b875  mov     rax, [rsi]
0x18001b878  test    rax, rax
0x18001b87b  jz      short loc_18001B8C0
0x18001b87d  lea     r8, [rbp+60h+self]
0x18001b881  lea     rdx, MSFT_NfsSession_RevokeSession_rtti
0x18001b888  mov     rcx, rsi
0x18001b88b  mov     rax, [rax+20h]
0x18001b88f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b894  test    eax, eax
0x18001b896  jnz     short loc_18001B8C5
0x18001b898  lea     rcx, [rsp+160h+var_118]; this
0x18001b89d  call    ?GetReturnValue@CWMIContext@@QEAAJXZ; CWMIContext::GetReturnValue(void)
0x18001b8a2  mov     [rbp+60h+var_90], eax
0x18001b8a5  mov     [rbp+60h+var_8C], 1
0x18001b8a9  lea     rdx, [rbp+60h+self]
0x18001b8ad  mov     rcx, rsi; self
0x18001b8b0  call    MI_Instance_Destruct
0x18001b8b5  lea     rcx, [rbp+60h+self]; self
0x18001b8b9  call    MI_Instance_Destruct
0x18001b8be  jmp     short loc_18001B8C5
0x18001b8c0  mov     eax, 4
0x18001b8c5  mov     edx, eax; enum _MI_Result
0x18001b8c7  lea     rcx, [rsp+160h+var_118]; this
0x18001b8cc  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18001b8d1  nop
0x18001b8d2  lea     rcx, [rsp+160h+var_118]; this
0x18001b8d7  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x18001b8dc  mov     eax, ebx
0x18001b8de  mov     rcx, [rbp+60h+var_20]
0x18001b8e2  xor     rcx, rsp; StackCookie
0x18001b8e5  call    __security_check_cookie
0x18001b8ea  lea     r11, [rsp+160h+var_10]
0x18001b8f2  mov     rbx, [r11+28h]
0x18001b8f6  mov     rsi, [r11+38h]
0x18001b8fa  mov     rsp, r11
0x18001b8fd  pop     r14
0x18001b8ff  pop     rdi
0x18001b900  pop     rbp
0x18001b901  retn
```
