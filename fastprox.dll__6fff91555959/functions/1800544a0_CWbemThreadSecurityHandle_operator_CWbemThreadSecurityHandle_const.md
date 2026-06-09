# CWbemThreadSecurityHandle::operator=(CWbemThreadSecurityHandle const &)

- ea: `0x1800544a0`
- end: `0x18005461e`
- name: `??4CWbemThreadSecurityHandle@@QEAAAEAV0@AEBV0@@Z`
- size: `382`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054450`

## callees

- `0x18004f9a0`
- `0x1800544a0`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800544cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800544d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800544cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800544d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800545e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800545e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800545c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005460f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800545c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005460f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180054500`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180054500`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800545b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800545b6`

## pseudocode

```c
__int64 __fastcall CWbemThreadSecurityHandle::operator=(__int64 a1, __int64 a2)
{
  HANDLE *v2; // r14
  void *v4; // rcx
  HANDLE CurrentProcess; // rax
  void *v7; // rdi
  void *v8; // rbx
  HANDLE v9; // rax
  void *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rbx
  void *v13; // rcx
  __int64 v14; // rax
  void (__fastcall ***v15)(_QWORD, __int64); // rcx
  unsigned __int64 v17; // rbx
  unsigned __int16 *v18; // rax
  __int64 v19; // rax
  unsigned __int64 v20; // rdi
  unsigned __int16 *v21; // rax

  v2 = (HANDLE *)(a1 + 16);
  v4 = *(void **)(a1 + 16);
  if ( v4 )
  {
    CloseHandle(v4);
    *v2 = 0;
  }
  if ( *(_QWORD *)(a2 + 16) )
  {
    CurrentProcess = GetCurrentProcess();
    v7 = *(void **)(a2 + 16);
    v8 = CurrentProcess;
    v9 = GetCurrentProcess();
    DuplicateHandle(v9, v7, v8, v2, 0, 1, 2u);
  }
  v10 = *(void **)(a1 + 40);
  *(_DWORD *)(a1 + 56) = *(_DWORD *)(a2 + 56);
  *(_DWORD *)(a1 + 24) = *(_DWORD *)(a2 + 24);
  *(_DWORD *)(a1 + 28) = *(_DWORD *)(a2 + 28);
  *(_DWORD *)(a1 + 32) = *(_DWORD *)(a2 + 32);
  *(_DWORD *)(a1 + 36) = *(_DWORD *)(a2 + 36);
  if ( v10 )
  {
    CoTaskMemFree(v10);
    *(_QWORD *)(a1 + 40) = 0;
  }
  v11 = *(_QWORD *)(a2 + 40);
  v12 = -1;
  if ( v11 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)(v11 + 2 * v19) );
    v20 = v19 + 1;
    v21 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v19 + 1));
    *(_QWORD *)(a1 + 40) = v21;
    if ( v21 )
      StringCchCopyW(v21, v20, *(const unsigned __int16 **)(a2 + 40));
  }
  v13 = *(void **)(a1 + 48);
  if ( v13 )
  {
    CoTaskMemFree(v13);
    *(_QWORD *)(a1 + 48) = 0;
  }
  v14 = *(_QWORD *)(a2 + 48);
  if ( v14 )
  {
    do
      ++v12;
    while ( *(_WORD *)(v14 + 2 * v12) );
    v17 = v12 + 1;
    v18 = (unsigned __int16 *)CoTaskMemAlloc(2 * v17);
    *(_QWORD *)(a1 + 48) = v18;
    if ( v18 )
      StringCchCopyW(v18, v17, *(const unsigned __int16 **)(a2 + 48));
  }
  v15 = *(void (__fastcall ****)(_QWORD, __int64))(a2 + 64);
  if ( v15 )
  {
    *(_QWORD *)(a1 + 64) = v15;
    (**v15)(v15, a1);
  }
  return a1;
}

```

## disassembly

```asm
0x1800544a0  push    rbx
0x1800544a2  push    rbp
0x1800544a3  push    rsi
0x1800544a4  push    rdi
0x1800544a5  push    r14
0x1800544a7  push    r15
0x1800544a9  sub     rsp, 48h
0x1800544ad  lea     r14, [rcx+10h]
0x1800544b1  mov     rsi, rcx
0x1800544b4  mov     rcx, [r14]; hObject
0x1800544b7  xor     r15d, r15d
0x1800544ba  mov     rbp, rdx
0x1800544bd  test    rcx, rcx
0x1800544c0  jnz     loc_1800545B6
0x1800544c6  cmp     [rbp+10h], r15
0x1800544ca  jz      short loc_180054506
0x1800544cc  call    cs:__imp_GetCurrentProcess
0x1800544d2  mov     rdi, [rbp+10h]
0x1800544d6  mov     rbx, rax
0x1800544d9  call    cs:__imp_GetCurrentProcess
0x1800544df  mov     [rsp+78h+dwOptions], 2; dwOptions
0x1800544e7  mov     r9, r14; lpTargetHandle
0x1800544ea  mov     rcx, rax; hSourceProcessHandle
0x1800544ed  mov     [rsp+78h+bInheritHandle], 1; bInheritHandle
0x1800544f5  mov     r8, rbx; hTargetProcessHandle
0x1800544f8  mov     [rsp+78h+dwDesiredAccess], r15d; dwDesiredAccess
0x1800544fd  mov     rdx, rdi; hSourceHandle
0x180054500  call    cs:__imp_DuplicateHandle
0x180054506  mov     eax, [rbp+38h]
0x180054509  mov     rcx, [rsi+28h]; pv
0x18005450d  mov     [rsi+38h], eax
0x180054510  mov     eax, [rbp+18h]
0x180054513  mov     [rsi+18h], eax
0x180054516  mov     eax, [rbp+1Ch]
0x180054519  mov     [rsi+1Ch], eax
0x18005451c  mov     eax, [rbp+20h]
0x18005451f  mov     [rsi+20h], eax
0x180054522  mov     eax, [rbp+24h]
0x180054525  mov     [rsi+24h], eax
0x180054528  test    rcx, rcx
0x18005452b  jnz     loc_1800545C4
0x180054531  mov     rcx, [rbp+28h]
0x180054535  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180054539  test    rcx, rcx
0x18005453c  jnz     loc_1800545D3
0x180054542  mov     rcx, [rsi+30h]; pv
0x180054546  test    rcx, rcx
0x180054549  jnz     loc_18005460F
0x18005454f  mov     rax, [rbp+30h]
0x180054553  test    rax, rax
0x180054556  jnz     short loc_180054571
0x180054558  mov     rcx, [rbp+40h]
0x18005455c  test    rcx, rcx
0x18005455f  jnz     short loc_1800545A2
0x180054561  mov     rax, rsi
0x180054564  add     rsp, 48h
0x180054568  pop     r15
0x18005456a  pop     r14
0x18005456c  pop     rdi
0x18005456d  pop     rsi
0x18005456e  pop     rbp
0x18005456f  pop     rbx
0x180054570  retn
0x180054571  inc     rbx
0x180054574  cmp     [rax+rbx*2], r15w
0x180054579  jnz     short loc_180054571
0x18005457b  inc     rbx
0x18005457e  lea     rcx, [rbx+rbx]; cb
0x180054582  call    cs:__imp_CoTaskMemAlloc
0x180054588  mov     [rsi+30h], rax
0x18005458c  test    rax, rax
0x18005458f  jz      short loc_180054558
0x180054591  mov     r8, [rbp+30h]; unsigned __int16 *
0x180054595  mov     rdx, rbx; unsigned __int64
0x180054598  mov     rcx, rax; unsigned __int16 *
0x18005459b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800545a0  jmp     short loc_180054558
0x1800545a2  mov     [rsi+40h], rcx
0x1800545a6  mov     rdx, rsi
0x1800545a9  mov     rax, [rcx]
0x1800545ac  mov     rax, [rax]
0x1800545af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545b4  jmp     short loc_180054561
0x1800545b6  call    cs:__imp_CloseHandle
0x1800545bc  mov     [r14], r15
0x1800545bf  jmp     loc_1800544C6
0x1800545c4  call    cs:__imp_CoTaskMemFree
0x1800545ca  mov     [rsi+28h], r15
0x1800545ce  jmp     loc_180054531
0x1800545d3  mov     rax, rbx
0x1800545d6  inc     rax
0x1800545d9  cmp     [rcx+rax*2], r15w
0x1800545de  jnz     short loc_1800545D6
0x1800545e0  lea     rdi, [rax+1]
0x1800545e4  lea     rcx, [rdi+rdi]; cb
0x1800545e8  call    cs:__imp_CoTaskMemAlloc
0x1800545ee  mov     [rsi+28h], rax
0x1800545f2  test    rax, rax
0x1800545f5  jz      loc_180054542
0x1800545fb  mov     r8, [rbp+28h]; unsigned __int16 *
0x1800545ff  mov     rdx, rdi; unsigned __int64
0x180054602  mov     rcx, rax; unsigned __int16 *
0x180054605  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005460a  jmp     loc_180054542
0x18005460f  call    cs:__imp_CoTaskMemFree
0x180054615  mov     [rsi+30h], r15
0x180054619  jmp     loc_18005454F
```
