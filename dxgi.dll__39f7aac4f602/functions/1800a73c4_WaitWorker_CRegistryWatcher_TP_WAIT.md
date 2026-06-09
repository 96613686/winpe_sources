# WaitWorker(CRegistryWatcher *,_TP_WAIT *)

- ea: `0x1800a73c4`
- end: `0x1800a747a`
- name: `?WaitWorker@@YAXPEAVCRegistryWatcher@@PEAU_TP_WAIT@@@Z`
- size: `182`
- prototype: `void(struct CRegistryWatcher *, struct _TP_WAIT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800301dc`
- `0x1800a73a0`

## callees

- `0x1800a73c4`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800a73d8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800a73d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800a73e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800a73e8`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800a7407`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800a7407`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800a7449`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800a7449`

## pseudocode

```c
void __fastcall WaitWorker(struct CRegistryWatcher *a1, struct _TP_WAIT *a2)
{
  char v4; // bl
  HKEY v5; // rcx
  __int64 v6; // rcx
  DWORD Type; // [rsp+40h] [rbp+8h] BYREF
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF

  ResetEvent(*((HANDLE *)a1 + 4));
  SetThreadpoolWait(a2, *((HANDLE *)a1 + 4), 0);
  v4 = 1;
  RegNotifyChangeKeyValue(*((HKEY *)a1 + 3), 1, 0x10000004u, *((HANDLE *)a1 + 4), 1);
  v5 = (HKEY)*((_QWORD *)a1 + 3);
  Type = 0;
  Data = 0;
  cbData = 4;
  if ( RegQueryValueExA(v5, (LPCSTR)a1 + 40, 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
    v4 = 0;
  LOBYTE(v6) = v4;
  (*((void (__fastcall **)(__int64, _QWORD, _QWORD))a1 + 1))(v6, Data, *((_QWORD *)a1 + 2));
}

```

## disassembly

```asm
0x1800a73c4  mov     [rsp+arg_8], rbx
0x1800a73c9  push    rdi
0x1800a73ca  sub     rsp, 30h
0x1800a73ce  mov     rdi, rcx
0x1800a73d1  mov     rbx, rdx
0x1800a73d4  mov     rcx, [rcx+20h]; hEvent
0x1800a73d8  call    cs:__imp_ResetEvent
0x1800a73de  mov     rdx, [rdi+20h]; h
0x1800a73e2  xor     r8d, r8d; pftTimeout
0x1800a73e5  mov     rcx, rbx; pwa
0x1800a73e8  call    cs:__imp_SetThreadpoolWait
0x1800a73ee  mov     r9, [rdi+20h]; hEvent
0x1800a73f2  mov     ebx, 1
0x1800a73f7  mov     rcx, [rdi+18h]; hKey
0x1800a73fb  mov     edx, ebx; bWatchSubtree
0x1800a73fd  mov     r8d, 10000004h; dwNotifyFilter
0x1800a7403  mov     [rsp+38h+fAsynchronous], ebx; fAsynchronous
0x1800a7407  call    cs:__imp_RegNotifyChangeKeyValue
0x1800a740d  mov     rcx, [rdi+18h]; hKey
0x1800a7411  lea     rax, [rsp+38h+cbData]
0x1800a7416  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800a741b  lea     rdx, [rdi+28h]; lpValueName
0x1800a741f  lea     rax, [rsp+38h+Data]
0x1800a7424  mov     [rsp+38h+Type], 0
0x1800a742c  lea     r9, [rsp+38h+Type]; lpType
0x1800a7431  mov     qword ptr [rsp+38h+fAsynchronous], rax; lpData
0x1800a7436  xor     r8d, r8d; lpReserved
0x1800a7439  mov     [rsp+38h+Data], 0
0x1800a7441  mov     [rsp+38h+cbData], 4
0x1800a7449  call    cs:__imp_RegQueryValueExA
0x1800a744f  test    eax, eax
0x1800a7451  jnz     short loc_1800A745A
0x1800a7453  cmp     [rsp+38h+Type], 4
0x1800a7458  jz      short loc_1800A745C
0x1800a745a  xor     bl, bl
0x1800a745c  mov     r8, [rdi+10h]
0x1800a7460  mov     cl, bl
0x1800a7462  mov     edx, [rsp+38h+Data]
0x1800a7466  mov     rax, [rdi+8]
0x1800a746a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a746f  mov     rbx, [rsp+38h+arg_8]
0x1800a7474  add     rsp, 30h
0x1800a7478  pop     rdi
0x1800a7479  retn
```
