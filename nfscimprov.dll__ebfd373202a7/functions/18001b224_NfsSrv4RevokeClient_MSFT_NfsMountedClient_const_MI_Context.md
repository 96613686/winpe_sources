# NfsSrv4RevokeClient(_MSFT_NfsMountedClient const *,_MI_Context *)

- ea: `0x18001b224`
- end: `0x18001b496`
- name: `?NfsSrv4RevokeClient@@YAKPEBU_MSFT_NfsMountedClient@@PEAU_MI_Context@@@Z`
- size: `626`
- prototype: `unsigned int(const struct _MSFT_NfsMountedClient *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009320`

## callees

- `0x1800098c4`
- `0x18000b2ac`
- `0x18000b620`
- `0x18000be78`
- `0x18000ce30`
- `0x180019504`
- `0x18001b224`
- `0x18001bacc`
- `0x180029c30`
- `0x18002a4dc`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001b3cf`
- `KERNEL32!GetLastError` at `0x18001b3f5`
- `KERNEL32!GetLastError` at `0x18001b3cf`
- `KERNEL32!GetLastError` at `0x18001b3f5`
- `KERNEL32!CloseHandle` at `0x18001b3ed`
- `KERNEL32!CloseHandle` at `0x18001b3ed`
- `KERNEL32!CreateFileW` at `0x18001b38b`
- `KERNEL32!CreateFileW` at `0x18001b38b`
- `KERNEL32!DeviceIoControl` at `0x18001b3c5`
- `KERNEL32!DeviceIoControl` at `0x18001b3c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NfsSrv4RevokeClient(const struct _MSFT_NfsMountedClient *a1, MI_Instance *a2)
{
  DWORD IsClusterNode; // edi
  enum _MI_Result v5; // ebx
  __int64 v6; // rcx
  DWORD ResourceIdForNetworkName; // eax
  HANDLE FileW; // rsi
  MI_Result v9; // eax
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-BCh] BYREF
  _QWORD v13[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v14; // [rsp+58h] [rbp-A8h]
  MI_Instance *v15; // [rsp+60h] [rbp-A0h]
  int v16; // [rsp+68h] [rbp-98h]
  __int64 v17; // [rsp+6Ch] [rbp-94h]
  MI_Instance self; // [rsp+80h] [rbp-80h] BYREF
  int ReturnValue; // [rsp+C0h] [rbp-40h]
  char v20; // [rsp+C4h] [rbp-3Ch]
  _OWORD InBuffer[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v22; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v23[256]; // [rsp+100h] [rbp+0h] BYREF

  IsClusterNode = 0;
  BytesReturned = 0;
  v11 = 0;
  v22 = 0;
  memset(InBuffer, 0, sizeof(InBuffer));
  self.ft = 0;
  memset_0(&self.classDecl, 0, sizeof(MI_Instance));
  v13[0] = &CWMIContext::`vftable';
  v15 = a2;
  v13[1] = 0;
  v14 = 0;
  v17 = 0;
  v16 = 0;
  if ( !*((_BYTE *)a1 + 72) || !*((_BYTE *)a1 + 88) )
    goto LABEL_24;
  if ( StringCbPrintfW(v23, 0x200u, L"%I64d", *((_QWORD *)a1 + 8)) < 0 )
  {
    v5 = MI_RESULT_FAILED;
    goto LABEL_25;
  }
  if ( !CWMIContext::PromptUser((CWMIContext *)v13, 0x40001031u, v23) )
    goto LABEL_19;
  *(_QWORD *)&InBuffer[0] = *((_QWORD *)a1 + 8);
  BYTE8(InBuffer[0]) = 1;
  IsClusterNode = NfsClusterIsClusterNode(v6, &v11);
  if ( !IsClusterNode )
  {
    if ( !v11 )
      goto LABEL_12;
    ResourceIdForNetworkName = NfsClusGetResourceIdForNetworkName(*((LPCWSTR *)a1 + 10), (__int64)&v22);
    IsClusterNode = ResourceIdForNetworkName;
    if ( !ResourceIdForNetworkName )
    {
      *(_OWORD *)((char *)InBuffer + 12) = v22;
      BYTE8(InBuffer[0]) = 0;
      goto LABEL_12;
    }
    if ( ResourceIdForNetworkName == 1168 )
    {
      IsClusterNode = 0;
      BYTE8(InBuffer[0]) = 1;
LABEL_12:
      FileW = CreateFileW(L"\\\\.\\NfsSvr", 0x40000000u, 0, 0, 3u, 0x1000080u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        IsClusterNode = GetLastError();
      }
      else
      {
        if ( !DeviceIoControl(FileW, 0x100085A0u, InBuffer, 0x20u, 0, 0, &BytesReturned, 0) )
        {
          IsClusterNode = GetLastError();
          if ( IsClusterNode == 50 )
            NfsPostNfsv4DisabledError(50, v13);
        }
        CloseHandle(FileW);
      }
    }
  }
  LODWORD(v17) = IsClusterNode;
LABEL_19:
  if ( !a2 || !a2->ft )
  {
LABEL_24:
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_25;
  }
  v9 = ((unsigned int (__fastcall *)(MI_Instance *, void *, MI_Instance *))a2->ft->GetClassNameA)(
         a2,
         &MSFT_NfsMountedClient_Revoke_rtti,
         &self);
  if ( v9 == MI_RESULT_OK )
  {
    ReturnValue = CWMIContext::GetReturnValue((CWMIContext *)v13);
    v20 = 1;
    MI_Instance_Destruct(a2);
    v9 = MI_Instance_Destruct(&self);
  }
  v5 = v9;
LABEL_25:
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v13, v5);
  CWMIContext::~CWMIContext((CWMIContext *)v13);
  return IsClusterNode;
}

```

## disassembly

```asm
0x18001b224  mov     [rsp-8+arg_10], rbx
0x18001b229  push    rbp
0x18001b22a  push    rsi
0x18001b22b  push    rdi
0x18001b22c  push    r14
0x18001b22e  push    r15
0x18001b230  lea     rbp, [rsp-210h]
0x18001b238  sub     rsp, 310h
0x18001b23f  mov     rax, cs:__security_cookie
0x18001b246  xor     rax, rsp
0x18001b249  mov     [rbp+230h+var_30], rax
0x18001b250  mov     r14, rdx
0x18001b253  mov     rsi, rcx
0x18001b256  xor     r15d, r15d
0x18001b259  mov     edi, r15d
0x18001b25c  mov     [rsp+330h+BytesReturned], r15d
0x18001b261  mov     [rsp+330h+var_2F0], r15d
0x18001b266  xorps   xmm0, xmm0
0x18001b269  movups  [rbp+230h+var_240], xmm0
0x18001b26d  xorps   xmm1, xmm1
0x18001b270  movups  [rbp+230h+InBuffer], xmm1
0x18001b274  movups  [rbp+230h+var_250], xmm1
0x18001b278  mov     [rbp+230h+self.ft], r15
0x18001b27c  xor     edx, edx; Val
0x18001b27e  lea     r8d, [r15+40h]; Size
0x18001b282  lea     rcx, [rbp+230h+self.classDecl]; void *
0x18001b286  call    memset_0
0x18001b28b  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18001b292  mov     [rsp+330h+var_2E8], rax
0x18001b297  mov     [rsp+330h+var_2D0], r14
0x18001b29c  mov     [rsp+330h+var_2E0], r15
0x18001b2a1  mov     [rsp+330h+var_2D8], r15w
0x18001b2a7  mov     [rsp+330h+var_2C4], r15
0x18001b2ac  mov     [rsp+330h+var_2C8], r15d
0x18001b2b1  cmp     [rsi+48h], r15b
0x18001b2b5  jz      loc_18001B452
0x18001b2bb  cmp     [rsi+58h], r15b
0x18001b2bf  jz      loc_18001B452
0x18001b2c5  mov     r9, [rsi+40h]
0x18001b2c9  lea     r8, aI64d; "%I64d"
0x18001b2d0  mov     edx, 200h; unsigned __int64
0x18001b2d5  lea     rcx, [rbp+230h+var_230]; unsigned __int16 *
0x18001b2d9  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b2de  test    eax, eax
0x18001b2e0  jns     short loc_18001B2EB
0x18001b2e2  lea     ebx, [r15+1]
0x18001b2e6  jmp     loc_18001B457
0x18001b2eb  lea     r8, [rbp+230h+var_230]
0x18001b2ef  mov     edx, 40001031h; unsigned int
0x18001b2f4  lea     rcx, [rsp+330h+var_2E8]; this
0x18001b2f9  call    ?PromptUser@CWMIContext@@UEAAEKZZ; CWMIContext::PromptUser(ulong,...)
0x18001b2fe  mov     ebx, 1
0x18001b303  test    al, al
0x18001b305  jz      loc_18001B401
0x18001b30b  mov     rax, [rsi+40h]
0x18001b30f  mov     qword ptr [rbp+230h+InBuffer], rax
0x18001b313  mov     byte ptr [rbp+230h+InBuffer+8], bl
0x18001b316  lea     rdx, [rsp+330h+var_2F0]
0x18001b31b  call    NfsClusterIsClusterNode
0x18001b320  mov     edi, eax
0x18001b322  test    eax, eax
0x18001b324  jnz     loc_18001B3FD
0x18001b32a  cmp     [rsp+330h+var_2F0], r15d
0x18001b32f  jz      short loc_18001B364
0x18001b331  lea     rdx, [rbp+230h+var_240]
0x18001b335  mov     rcx, [rsi+50h]; lpszResourceName
0x18001b339  call    NfsClusGetResourceIdForNetworkName
0x18001b33e  mov     edi, eax
0x18001b340  test    eax, eax
0x18001b342  jnz     short loc_18001B353
0x18001b344  movups  xmm0, [rbp+230h+var_240]
0x18001b348  movdqu  [rbp+230h+InBuffer+0Ch], xmm0
0x18001b34d  mov     byte ptr [rbp+230h+InBuffer+8], r15b
0x18001b351  jmp     short loc_18001B364
0x18001b353  cmp     eax, 490h
0x18001b358  jnz     loc_18001B3FD
0x18001b35e  mov     edi, r15d
0x18001b361  mov     byte ptr [rbp+230h+InBuffer+8], bl
0x18001b364  mov     [rsp+330h+hTemplateFile], r15; hTemplateFile
0x18001b369  mov     [rsp+330h+dwFlagsAndAttributes], 1000080h; dwFlagsAndAttributes
0x18001b371  mov     [rsp+330h+dwCreationDisposition], 3; dwCreationDisposition
0x18001b379  xor     r9d, r9d; lpSecurityAttributes
0x18001b37c  xor     r8d, r8d; dwShareMode
0x18001b37f  mov     edx, 40000000h; dwDesiredAccess
0x18001b384  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x18001b38b  call    cs:__imp_CreateFileW
0x18001b391  mov     rsi, rax
0x18001b394  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b398  jz      short loc_18001B3F5
0x18001b39a  mov     [rsp+330h+lpOverlapped], r15; lpOverlapped
0x18001b39f  lea     rax, [rsp+330h+BytesReturned]
0x18001b3a4  mov     [rsp+330h+hTemplateFile], rax; lpBytesReturned
0x18001b3a9  mov     [rsp+330h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x18001b3ae  mov     qword ptr [rsp+330h+dwCreationDisposition], r15; lpOutBuffer
0x18001b3b3  mov     r9d, 20h ; ' '; nInBufferSize
0x18001b3b9  lea     r8, [rbp+230h+InBuffer]; lpInBuffer
0x18001b3bd  mov     edx, 100085A0h; dwIoControlCode
0x18001b3c2  mov     rcx, rsi; hDevice
0x18001b3c5  call    cs:__imp_DeviceIoControl
0x18001b3cb  test    eax, eax
0x18001b3cd  jnz     short loc_18001B3EA
0x18001b3cf  call    cs:__imp_GetLastError
0x18001b3d5  mov     edi, eax
0x18001b3d7  mov     ecx, 32h ; '2'
0x18001b3dc  cmp     eax, ecx
0x18001b3de  jnz     short loc_18001B3EA
0x18001b3e0  lea     rdx, [rsp+330h+var_2E8]
0x18001b3e5  call    NfsPostNfsv4DisabledError
0x18001b3ea  mov     rcx, rsi; hObject
0x18001b3ed  call    cs:__imp_CloseHandle
0x18001b3f3  jmp     short loc_18001B3FD
0x18001b3f5  call    cs:__imp_GetLastError
0x18001b3fb  mov     edi, eax
0x18001b3fd  mov     dword ptr [rsp+330h+var_2C4], edi
0x18001b401  test    r14, r14
0x18001b404  jz      short loc_18001B452
0x18001b406  mov     rax, [r14]
0x18001b409  test    rax, rax
0x18001b40c  jz      short loc_18001B452
0x18001b40e  lea     r8, [rbp+230h+self]
0x18001b412  lea     rdx, MSFT_NfsMountedClient_Revoke_rtti
0x18001b419  mov     rcx, r14
0x18001b41c  mov     rax, [rax+20h]
0x18001b420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b425  test    eax, eax
0x18001b427  jnz     short loc_18001B44E
0x18001b429  lea     rcx, [rsp+330h+var_2E8]; this
0x18001b42e  call    ?GetReturnValue@CWMIContext@@QEAAJXZ; CWMIContext::GetReturnValue(void)
0x18001b433  mov     [rbp+230h+var_270], eax
0x18001b436  mov     [rbp+230h+var_26C], bl
0x18001b439  lea     rdx, [rbp+230h+self]
0x18001b43d  mov     rcx, r14; self
0x18001b440  call    MI_Instance_Destruct
0x18001b445  lea     rcx, [rbp+230h+self]; self
0x18001b449  call    MI_Instance_Destruct
0x18001b44e  mov     ebx, eax
0x18001b450  jmp     short loc_18001B457
0x18001b452  mov     ebx, 4
0x18001b457  mov     edx, ebx; enum _MI_Result
0x18001b459  lea     rcx, [rsp+330h+var_2E8]; this
0x18001b45e  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18001b463  nop
0x18001b464  lea     rcx, [rsp+330h+var_2E8]; this
0x18001b469  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x18001b46e  mov     eax, edi
0x18001b470  mov     rcx, [rbp+230h+var_30]
0x18001b477  xor     rcx, rsp; StackCookie
0x18001b47a  call    __security_check_cookie
0x18001b47f  mov     rbx, [rsp+330h+arg_10]
0x18001b487  add     rsp, 310h
0x18001b48e  pop     r15
0x18001b490  pop     r14
0x18001b492  pop     rdi
0x18001b493  pop     rsi
0x18001b494  pop     rbp
0x18001b495  retn
```
