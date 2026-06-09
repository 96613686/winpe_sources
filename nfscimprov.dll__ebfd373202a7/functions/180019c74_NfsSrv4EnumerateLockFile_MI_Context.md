# NfsSrv4EnumerateLockFile(_MI_Context *)

- ea: `0x180019c74`
- end: `0x180019ed6`
- name: `?NfsSrv4EnumerateLockFile@@YAKPEAU_MI_Context@@@Z`
- size: `610`
- prototype: `unsigned int __fastcall(struct _MI_Context *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009360`

## callees

- `0x1800098c4`
- `0x18000bde0`
- `0x18000cd6c`
- `0x18000eae4`
- `0x180018188`
- `0x180018250`
- `0x180018960`
- `0x180019010`
- `0x180019504`
- `0x180019c74`
- `0x18001a3dc`
- `0x180035b40`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180019e7c`
- `KERNEL32!HeapFree` at `0x180019e7c`
- `KERNEL32!GetLastError` at `0x180019d37`
- `KERNEL32!GetLastError` at `0x180019dad`
- `KERNEL32!GetLastError` at `0x180019d37`
- `KERNEL32!GetLastError` at `0x180019dad`
- `KERNEL32!CloseHandle` at `0x180019e63`
- `KERNEL32!CloseHandle` at `0x180019e63`
- `KERNEL32!HeapAlloc` at `0x180019d62`
- `KERNEL32!HeapAlloc` at `0x180019d62`
- `KERNEL32!GetProcessHeap` at `0x180019d47`
- `KERNEL32!GetProcessHeap` at `0x180019e6e`
- `KERNEL32!GetProcessHeap` at `0x180019d47`
- `KERNEL32!GetProcessHeap` at `0x180019e6e`
- `KERNEL32!CreateFileW` at `0x180019d28`
- `KERNEL32!CreateFileW` at `0x180019d28`
- `KERNEL32!DeviceIoControl` at `0x180019da3`
- `KERNEL32!DeviceIoControl` at `0x180019da3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NfsSrv4EnumerateLockFile(struct _MI_Context *a1)
{
  DWORD LastError; // ebx
  enum _MI_Result v2; // r12d
  HANDLE FileW; // rsi
  HANDLE ProcessHeap; // rax
  unsigned int *v5; // rdi
  DWORD v6; // eax
  char *v7; // r15
  __int64 i; // r14
  HANDLE v9; // rax
  __int64 v10; // rdx
  DWORD BytesReturned; // [rsp+40h] [rbp-89h] BYREF
  _QWORD v13[2]; // [rsp+48h] [rbp-81h] BYREF
  __int16 v14; // [rsp+58h] [rbp-71h]
  struct _MI_Context *v15; // [rsp+60h] [rbp-69h]
  int v16; // [rsp+68h] [rbp-61h]
  __int64 v17; // [rsp+6Ch] [rbp-5Dh]
  _BYTE v18[16]; // [rsp+78h] [rbp-51h] BYREF
  _BYTE v19[24]; // [rsp+88h] [rbp-41h] BYREF
  __int128 v20; // [rsp+A0h] [rbp-29h]
  __int64 v21; // [rsp+B0h] [rbp-19h] BYREF
  _WORD v22[8]; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v23; // [rsp+C8h] [rbp-1h]
  __int64 v24; // [rsp+D0h] [rbp+7h]
  char v25; // [rsp+EAh] [rbp+21h]

  LastError = 0;
  BytesReturned = 0;
  v24 = 7;
  v23 = 0;
  v22[0] = 0;
  v13[0] = &CWMIContext::`vftable';
  v15 = a1;
  v13[1] = 0;
  v14 = 0;
  v17 = 0;
  v16 = 0;
  v21 = (__int64)v13;
  v25 = 1;
  v2 = (unsigned int)IdentifyLocksToEnumerate(a1, &v21);
  if ( v2 )
    goto LABEL_21;
  if ( !v25 )
    goto LABEL_21;
  FileW = CreateFileW(L"\\\\.\\NfsSvr", 0x80000000, 0, 0, 3u, 0x1000080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_21;
  }
  ProcessHeap = GetProcessHeap();
  v5 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, 0x1000u);
  if ( v5 )
  {
    if ( !DeviceIoControl(FileW, 0x1000059Cu, 0, 0, v5, 0x1000u, &BytesReturned, 0) )
    {
      v6 = GetLastError();
      LastError = v6;
      if ( v6 == 50 )
      {
        NfsPostNfsv4DisabledError(50, v13);
        goto LABEL_17;
      }
      if ( v6 )
        goto LABEL_17;
    }
    std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v18);
    std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v19);
    NfsMapVolPathToMntPointWithSharePrefix(v18);
    v7 = (char *)v5 + v5[2];
    for ( i = 0; (unsigned int)i < *v5; i = (unsigned int)(i + 1) )
    {
      v20 = *(_OWORD *)&v7[20 * i + 4];
      LastError = NfsSrv4EnumeratePerVsLockFile(FileW, (__int64)&v21);
      if ( CWMIContext::IsCanceled((CWMIContext *)v13) )
      {
        LastError = 1223;
        break;
      }
    }
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v19);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v18);
    goto LABEL_17;
  }
  LastError = 8;
LABEL_17:
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  if ( v5 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v5);
  }
LABEL_21:
  LODWORD(v17) = LastError;
  CWMIContext::PostResult((CWMIContext *)v13, v2);
  CWMIContext::~CWMIContext((CWMIContext *)v13);
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(v22, v10, 0);
  return LastError;
}

```

## disassembly

```asm
0x180019c74  mov     [rsp-8+arg_8], rbx
0x180019c79  mov     [rsp-8+arg_10], rsi
0x180019c7e  push    rbp
0x180019c7f  push    rdi
0x180019c80  push    r12
0x180019c82  push    r14
0x180019c84  push    r15
0x180019c86  lea     rbp, [rsp-37h]
0x180019c8b  sub     rsp, 100h
0x180019c92  mov     rax, cs:__security_cookie
0x180019c99  xor     rax, rsp
0x180019c9c  mov     [rbp+57h+var_30], rax
0x180019ca0  xor     ebx, ebx
0x180019ca2  mov     [rsp+120h+BytesReturned], ebx
0x180019ca6  mov     [rbp+57h+var_50], 7
0x180019cae  mov     [rbp+57h+var_58], rbx
0x180019cb2  xor     eax, eax
0x180019cb4  mov     [rbp+57h+var_68], ax
0x180019cb8  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180019cbf  mov     [rsp+120h+var_D8], rax
0x180019cc4  mov     [rbp+57h+var_C0], rcx
0x180019cc8  mov     [rbp+57h+var_D0], rbx
0x180019ccc  mov     [rbp+57h+var_C8], bx
0x180019cd0  mov     [rbp+57h+var_B4], rbx
0x180019cd4  mov     [rbp+57h+var_B8], ebx
0x180019cd7  lea     rax, [rsp+120h+var_D8]
0x180019cdc  mov     [rbp+57h+var_70], rax
0x180019ce0  mov     [rbp+57h+var_36], 1
0x180019ce4  lea     rdx, [rbp+57h+var_70]
0x180019ce8  call    IdentifyLocksToEnumerate
0x180019ced  mov     r12d, eax
0x180019cf0  test    eax, eax
0x180019cf2  jnz     loc_180019E82
0x180019cf8  cmp     [rbp+57h+var_36], al
0x180019cfb  jz      loc_180019E82
0x180019d01  mov     [rsp+120h+hTemplateFile], rbx; hTemplateFile
0x180019d06  mov     [rsp+120h+dwFlagsAndAttributes], 1000080h; dwFlagsAndAttributes
0x180019d0e  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x180019d16  xor     r9d, r9d; lpSecurityAttributes
0x180019d19  xor     r8d, r8d; dwShareMode
0x180019d1c  mov     edx, 80000000h; dwDesiredAccess
0x180019d21  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x180019d28  call    cs:__imp_CreateFileW
0x180019d2e  mov     rsi, rax
0x180019d31  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019d35  jnz     short loc_180019D47
0x180019d37  call    cs:__imp_GetLastError
0x180019d3d  mov     ebx, eax
0x180019d3f  test    eax, eax
0x180019d41  jnz     loc_180019E82
0x180019d47  call    cs:__imp_GetProcessHeap
0x180019d4d  mov     rcx, rax; hHeap
0x180019d50  mov     r15d, 1000h
0x180019d56  mov     r8d, r15d; dwBytes
0x180019d59  mov     r14d, 8
0x180019d5f  mov     edx, r14d; dwFlags
0x180019d62  call    cs:__imp_HeapAlloc
0x180019d68  mov     rdi, rax
0x180019d6b  test    rax, rax
0x180019d6e  jnz     short loc_180019D78
0x180019d70  mov     ebx, r14d
0x180019d73  jmp     loc_180019E5A
0x180019d78  mov     [rsp+120h+lpOverlapped], 0; lpOverlapped
0x180019d81  lea     rax, [rsp+120h+BytesReturned]
0x180019d86  mov     [rsp+120h+hTemplateFile], rax; lpBytesReturned
0x180019d8b  mov     [rsp+120h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x180019d90  mov     qword ptr [rsp+120h+dwCreationDisposition], rdi; lpOutBuffer
0x180019d95  xor     r9d, r9d; nInBufferSize
0x180019d98  xor     r8d, r8d; lpInBuffer
0x180019d9b  mov     edx, 1000059Ch; dwIoControlCode
0x180019da0  mov     rcx, rsi; hDevice
0x180019da3  call    cs:__imp_DeviceIoControl
0x180019da9  test    eax, eax
0x180019dab  jnz     short loc_180019DD5
0x180019dad  call    cs:__imp_GetLastError
0x180019db3  mov     ebx, eax
0x180019db5  mov     ecx, 32h ; '2'
0x180019dba  cmp     eax, ecx
0x180019dbc  jnz     short loc_180019DCD
0x180019dbe  lea     rdx, [rsp+120h+var_D8]
0x180019dc3  call    NfsPostNfsv4DisabledError
0x180019dc8  jmp     loc_180019E5A
0x180019dcd  test    eax, eax
0x180019dcf  jnz     loc_180019E5A
0x180019dd5  lea     rcx, [rbp+57h+var_A8]
0x180019dd9  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x180019dde  nop
0x180019ddf  lea     rcx, [rbp+57h+var_98]
0x180019de3  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x180019de8  nop
0x180019de9  lea     rcx, [rbp+57h+var_A8]
0x180019ded  call    NfsMapVolPathToMntPointWithSharePrefix
0x180019df2  mov     r15d, [rdi+8]
0x180019df6  add     r15, rdi
0x180019df9  xor     r14d, r14d
0x180019dfc  cmp     r14d, [rdi]
0x180019dff  jnb     short loc_180019E47
0x180019e01  lea     rcx, [r14+r14*4]
0x180019e05  movups  xmm0, xmmword ptr [r15+rcx*4+4]
0x180019e0b  movdqu  [rbp+57h+var_80], xmm0
0x180019e10  lea     rax, [rbp+57h+var_70]
0x180019e14  mov     qword ptr [rsp+120h+dwCreationDisposition], rax; __int64
0x180019e19  lea     r9, [rbp+57h+var_98]
0x180019e1d  lea     r8, [rbp+57h+var_A8]
0x180019e21  lea     rdx, [rbp+57h+var_80]
0x180019e25  mov     rcx, rsi; hDevice
0x180019e28  call    NfsSrv4EnumeratePerVsLockFile
0x180019e2d  mov     ebx, eax
0x180019e2f  lea     rcx, [rsp+120h+var_D8]; this
0x180019e34  call    ?IsCanceled@CWMIContext@@UEAA_NXZ; CWMIContext::IsCanceled(void)
0x180019e39  test    al, al
0x180019e3b  jnz     short loc_180019E42
0x180019e3d  inc     r14d
0x180019e40  jmp     short loc_180019DFC
0x180019e42  mov     ebx, 4C7h
0x180019e47  lea     rcx, [rbp+57h+var_98]
0x180019e4b  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180019e50  nop
0x180019e51  lea     rcx, [rbp+57h+var_A8]
0x180019e55  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180019e5a  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180019e5e  jz      short loc_180019E69
0x180019e60  mov     rcx, rsi; hObject
0x180019e63  call    cs:__imp_CloseHandle
0x180019e69  test    rdi, rdi
0x180019e6c  jz      short loc_180019E82
0x180019e6e  call    cs:__imp_GetProcessHeap
0x180019e74  mov     rcx, rax; hHeap
0x180019e77  mov     r8, rdi; lpMem
0x180019e7a  xor     edx, edx; dwFlags
0x180019e7c  call    cs:__imp_HeapFree
0x180019e82  mov     dword ptr [rbp+57h+var_B4], ebx
0x180019e85  mov     edx, r12d; enum _MI_Result
0x180019e88  lea     rcx, [rsp+120h+var_D8]; this
0x180019e8d  call    ?PostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::PostResult(_MI_Result)
0x180019e92  nop
0x180019e93  lea     rcx, [rsp+120h+var_D8]; this
0x180019e98  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x180019e9d  nop
0x180019e9e  xor     r8d, r8d
0x180019ea1  mov     dl, 1
0x180019ea3  lea     rcx, [rbp+57h+var_68]
0x180019ea7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180019eac  mov     eax, ebx
0x180019eae  mov     rcx, [rbp+57h+var_30]
0x180019eb2  xor     rcx, rsp; StackCookie
0x180019eb5  call    __security_check_cookie
0x180019eba  lea     r11, [rsp+120h+var_20]
0x180019ec2  mov     rbx, [r11+38h]
0x180019ec6  mov     rsi, [r11+40h]
0x180019eca  mov     rsp, r11
0x180019ecd  pop     r15
0x180019ecf  pop     r14
0x180019ed1  pop     r12
0x180019ed3  pop     rdi
0x180019ed4  pop     rbp
0x180019ed5  retn
```
