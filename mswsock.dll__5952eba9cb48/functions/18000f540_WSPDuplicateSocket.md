# WSPDuplicateSocket

- ea: `0x18000f540`
- end: `0x18000f83d`
- name: `WSPDuplicateSocket`
- size: `765`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle, DWORD dwProcessId)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008190`
- `0x180008250`
- `0x18000c130`
- `0x18000f540`
- `0x18000f844`
- `0x18003ac78`
- `0x18003ad20`
- `0x18003aefc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f611`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f611`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000f5a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000f5a4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f643`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f6a4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f77d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f643`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f6a4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f77d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f6b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f6db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f78c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f6b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f6db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f78c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f5f4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f5f4`

## pseudocode

```c
__int64 __fastcall WSPDuplicateSocket(HANDLE hSourceHandle, DWORD dwProcessId, __int64 a3, int *a4)
{
  volatile signed __int32 *v8; // rax
  __int64 v9; // rcx
  volatile signed __int32 *v10; // rsi
  HANDLE v11; // r14
  HANDLE CurrentProcess; // rax
  int v13; // ebx
  int v15; // eax
  BOOL bInheritHandle[2]; // [rsp+28h] [rbp-60h]
  DWORD dwOptions[2]; // [rsp+30h] [rbp-58h]
  HANDLE TargetHandle; // [rsp+40h] [rbp-48h] BYREF
  HANDLE hSourceProcessHandle[8]; // [rsp+48h] [rbp-40h] BYREF

  hSourceProcessHandle[0] = 0;
  TargetHandle = 0;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_sqqqq(
      (_DWORD)hSourceHandle,
      12,
      (unsigned int)WPP_16902e14e6ca314a5ddfbf127ca5d75b_Traceguids,
      (unsigned int)"WSPDuplicateSocket",
      (char)hSourceHandle,
      dwProcessId,
      a3,
      (char)a4);
  if ( SockProcessTerminating || !SockWspStartupCount || (hSourceProcessHandle[0] = TlsGetValue(MSAFD_SockTlsSlot)) == 0 )
  {
    v15 = SockEnterApiSlow(hSourceProcessHandle);
    if ( v15 )
    {
      *a4 = v15;
      return 0xFFFFFFFFLL;
    }
  }
  v8 = (volatile signed __int32 *)SockFindAndReferenceSocket(hSourceHandle);
  v10 = v8;
  hSourceProcessHandle[1] = (HANDLE)v8;
  if ( !v8 || (*((_BYTE *)v8 + 69) & 0x20) != 0 )
  {
    v13 = 10038;
    goto LABEL_28;
  }
  if ( !a3 )
  {
    v13 = 10014;
    goto LABEL_28;
  }
  v11 = OpenProcess(0x40u, 0, dwProcessId);
  hSourceProcessHandle[0] = v11;
  if ( !v11 )
  {
    v13 = 10022;
LABEL_28:
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      bInheritHandle[0] = v13;
      WPP_SF_iql(
        v9,
        13,
        WPP_16902e14e6ca314a5ddfbf127ca5d75b_Traceguids,
        hSourceHandle,
        v10,
        *(_QWORD *)bInheritHandle,
        *(_QWORD *)dwOptions);
    }
    goto LABEL_16;
  }
  CurrentProcess = GetCurrentProcess();
  if ( DuplicateHandle(CurrentProcess, hSourceHandle, v11, &TargetHandle, 0, 1, 2u) )
  {
    v13 = SockBuildProtocolInfoForSocket(v10, a3);
    if ( !v13 )
    {
      *(_DWORD *)(a3 + 112) = (_DWORD)TargetHandle;
      CloseHandle(v11);
      v13 = 0;
      goto LABEL_13;
    }
    DuplicateHandle(v11, TargetHandle, 0, 0, 0, 0, 1u);
  }
  else
  {
    v13 = 10024;
  }
  CloseHandle(v11);
LABEL_13:
  if ( v13 )
    goto LABEL_28;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_qq(
      1025,
      14,
      WPP_16902e14e6ca314a5ddfbf127ca5d75b_Traceguids,
      hSourceHandle,
      v10,
      *(_QWORD *)bInheritHandle,
      *(_QWORD *)dwOptions);
LABEL_16:
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10, 0xFFFFFFFF) == 1 )
      SockDestroySocket(v10);
  }
  if ( !v13 )
    return 0;
  *a4 = v13;
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18000f540  mov     rax, rsp
0x18000f543  mov     [rax+10h], rbx
0x18000f547  mov     [rax+20h], r9
0x18000f54b  mov     [rax+8], rcx
0x18000f54f  push    rsi
0x18000f550  push    r12
0x18000f552  push    r13
0x18000f554  push    r14
0x18000f556  push    r15
0x18000f558  sub     rsp, 60h
0x18000f55c  mov     r12, r9
0x18000f55f  mov     r13, r8
0x18000f562  mov     ebx, edx
0x18000f564  mov     r15, rcx
0x18000f567  mov     qword ptr [rax-40h], 0
0x18000f56f  mov     qword ptr [rax-48h], 0
0x18000f577  test    byte ptr cs:xmmword_180063D60, 2
0x18000f57e  jnz     loc_18000F79D
0x18000f584  cmp     cs:SockProcessTerminating, 0
0x18000f58b  jnz     loc_18000F720
0x18000f591  cmp     cs:SockWspStartupCount, 0
0x18000f598  jbe     loc_18000F720
0x18000f59e  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18000f5a4  call    cs:__imp_TlsGetValue
0x18000f5ab  nop     dword ptr [rax+rax+00h]
0x18000f5b0  mov     [rsp+88h+hSourceProcessHandle], rax
0x18000f5b5  test    rax, rax
0x18000f5b8  jz      loc_18000F720
0x18000f5be  mov     dl, 1
0x18000f5c0  mov     rcx, r15
0x18000f5c3  call    SockFindAndReferenceSocket
0x18000f5c8  mov     rsi, rax
0x18000f5cb  mov     [rsp+88h+var_38], rax
0x18000f5d0  test    rax, rax
0x18000f5d3  jz      loc_18000F7CE
0x18000f5d9  test    byte ptr [rax+45h], 20h
0x18000f5dd  jnz     loc_18000F7CE
0x18000f5e3  test    r13, r13
0x18000f5e6  jz      loc_18000F802
0x18000f5ec  mov     r8d, ebx; dwProcessId
0x18000f5ef  xor     edx, edx; bInheritHandle
0x18000f5f1  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18000f5f4  call    cs:__imp_OpenProcess
0x18000f5fb  nop     dword ptr [rax+rax+00h]
0x18000f600  mov     r14, rax
0x18000f603  mov     [rsp+88h+hSourceProcessHandle], rax
0x18000f608  test    rax, rax
0x18000f60b  jz      loc_18000F809
0x18000f611  call    cs:__imp_GetCurrentProcess
0x18000f618  nop     dword ptr [rax+rax+00h]
0x18000f61d  mov     rcx, rax; hSourceProcessHandle
0x18000f620  mov     [rsp+88h+dwOptions], 2; dwOptions
0x18000f628  mov     [rsp+88h+bInheritHandle], 1; bInheritHandle
0x18000f630  mov     [rsp+88h+dwDesiredAccess], 0; dwDesiredAccess
0x18000f638  lea     r9, [rsp+88h+TargetHandle]; lpTargetHandle
0x18000f63d  mov     r8, r14; hTargetProcessHandle
0x18000f640  mov     rdx, r15; hSourceHandle
0x18000f643  call    cs:__imp_DuplicateHandle
0x18000f64a  nop     dword ptr [rax+rax+00h]
0x18000f64f  test    eax, eax
0x18000f651  jz      loc_18000F810
0x18000f657  mov     rdx, r13
0x18000f65a  mov     rcx, rsi
0x18000f65d  call    SockBuildProtocolInfoForSocket
0x18000f662  mov     ebx, eax
0x18000f664  test    eax, eax
0x18000f666  jnz     loc_18000F757
0x18000f66c  mov     rax, [rsp+88h+TargetHandle]
0x18000f671  mov     [r13+70h], eax
0x18000f675  jmp     short loc_18000F6D8
0x18000f677  mov     ebx, 271Eh
0x18000f67c  mov     [rsp+88h+dwOptions], 1; dwOptions
0x18000f684  mov     [rsp+88h+bInheritHandle], 0; bInheritHandle
0x18000f68c  mov     [rsp+88h+dwDesiredAccess], 0; dwDesiredAccess
0x18000f694  xor     r9d, r9d; lpTargetHandle
0x18000f697  xor     r8d, r8d; hTargetProcessHandle
0x18000f69a  mov     rdx, [rsp+88h+TargetHandle]; hSourceHandle
0x18000f69f  mov     rcx, [rsp+88h+hSourceProcessHandle]; hSourceProcessHandle
0x18000f6a4  call    cs:__imp_DuplicateHandle
0x18000f6ab  nop     dword ptr [rax+rax+00h]
0x18000f6b0  mov     rcx, [rsp+88h+hSourceProcessHandle]; hObject
0x18000f6b5  call    cs:__imp_CloseHandle
0x18000f6bc  nop     dword ptr [rax+rax+00h]
0x18000f6c1  mov     r12, [rsp+88h+arg_18]
0x18000f6c9  mov     r15, [rsp+88h+arg_0]
0x18000f6d1  mov     rsi, [rsp+88h+var_38]
0x18000f6d6  jmp     short loc_18000F6E9
0x18000f6d8  mov     rcx, r14; hObject
0x18000f6db  call    cs:__imp_CloseHandle
0x18000f6e2  nop     dword ptr [rax+rax+00h]
0x18000f6e7  xor     ebx, ebx
0x18000f6e9  test    ebx, ebx
0x18000f6eb  jnz     loc_18000F7D3
0x18000f6f1  test    byte ptr cs:xmmword_180063D60, 2
0x18000f6f8  jnz     loc_18000F81A
0x18000f6fe  test    rsi, rsi
0x18000f701  jnz     short loc_18000F738
0x18000f703  test    ebx, ebx
0x18000f705  jnz     short loc_18000F74E
0x18000f707  xor     eax, eax
0x18000f709  mov     rbx, [rsp+88h+arg_8]
0x18000f711  add     rsp, 60h
0x18000f715  pop     r15
0x18000f717  pop     r14
0x18000f719  pop     r13
0x18000f71b  pop     r12
0x18000f71d  pop     rsi
0x18000f71e  retn
0x18000f720  lea     rcx, [rsp+88h+hSourceProcessHandle]
0x18000f725  call    SockEnterApiSlow
0x18000f72a  test    eax, eax
0x18000f72c  jz      loc_18000F5BE
0x18000f732  mov     [r12], eax
0x18000f736  jmp     short loc_18000F752
0x18000f738  or      eax, 0FFFFFFFFh
0x18000f73b  lock xadd [rsi], eax
0x18000f73f  cmp     eax, 1
0x18000f742  jnz     short loc_18000F703
0x18000f744  mov     rcx, rsi
0x18000f747  call    SockDestroySocket
0x18000f74c  jmp     short loc_18000F703
0x18000f74e  mov     [r12], ebx
0x18000f752  or      eax, 0FFFFFFFFh
0x18000f755  jmp     short loc_18000F709
0x18000f757  mov     [rsp+88h+dwOptions], 1; dwOptions
0x18000f75f  mov     [rsp+88h+bInheritHandle], 0; bInheritHandle
0x18000f767  mov     [rsp+88h+dwDesiredAccess], 0; dwDesiredAccess
0x18000f76f  xor     r9d, r9d; lpTargetHandle
0x18000f772  xor     r8d, r8d; hTargetProcessHandle
0x18000f775  mov     rdx, [rsp+88h+TargetHandle]; hSourceHandle
0x18000f77a  mov     rcx, r14; hSourceProcessHandle
0x18000f77d  call    cs:__imp_DuplicateHandle
0x18000f784  nop     dword ptr [rax+rax+00h]
0x18000f789  mov     rcx, r14; hObject
0x18000f78c  call    cs:__imp_CloseHandle
0x18000f793  nop     dword ptr [rax+rax+00h]
0x18000f798  jmp     loc_18000F6E9
0x18000f79d  mov     edx, 0Ch
0x18000f7a2  mov     [rsp+88h+var_50], r12
0x18000f7a7  mov     qword ptr [rsp+88h+dwOptions], r13
0x18000f7ac  mov     qword ptr [rsp+88h+bInheritHandle], rbx
0x18000f7b1  mov     qword ptr [rsp+88h+dwDesiredAccess], r15
0x18000f7b6  lea     r9, aWspduplicateso; "WSPDuplicateSocket"
0x18000f7bd  lea     r8, WPP_16902e14e6ca314a5ddfbf127ca5d75b_Traceguids
0x18000f7c4  call    WPP_SF_sqqqq
0x18000f7c9  jmp     loc_18000F584
0x18000f7ce  mov     ebx, 2736h
0x18000f7d3  test    byte ptr cs:xmmword_180063D60, 2
0x18000f7da  jz      loc_18000F6FE
0x18000f7e0  mov     edx, 0Dh
0x18000f7e5  mov     [rsp+88h+bInheritHandle], ebx
0x18000f7e9  mov     qword ptr [rsp+88h+dwDesiredAccess], rsi
0x18000f7ee  mov     r9, r15
0x18000f7f1  lea     r8, WPP_16902e14e6ca314a5ddfbf127ca5d75b_Traceguids
0x18000f7f8  call    WPP_SF_iql
0x18000f7fd  jmp     loc_18000F6FE
0x18000f802  mov     ebx, 271Eh
0x18000f807  jmp     short loc_18000F7D3
0x18000f809  mov     ebx, 2726h
0x18000f80e  jmp     short loc_18000F7D3
0x18000f810  mov     ebx, 2728h
0x18000f815  jmp     loc_18000F789
0x18000f81a  mov     edx, 0Eh
0x18000f81f  mov     ecx, 401h
0x18000f824  mov     qword ptr [rsp+88h+dwDesiredAccess], rsi
0x18000f829  mov     r9, r15
0x18000f82c  lea     r8, WPP_16902e14e6ca314a5ddfbf127ca5d75b_Traceguids
0x18000f833  call    WPP_SF_qq
0x18000f838  jmp     loc_18000F6FE
```
