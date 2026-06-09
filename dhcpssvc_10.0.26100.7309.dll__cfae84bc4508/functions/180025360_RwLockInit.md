# RwLockInit

- ea: `0x180025360`
- end: `0x18002541b`
- name: `RwLockInit`
- size: `187`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a00`
- `0x180055758`
- `0x180069f98`

## callees

- `0x180025360`

## import_xrefs

- `KERNEL32!TlsFree` at `0x1800253e2`
- `KERNEL32!TlsFree` at `0x1800253e2`
- `KERNEL32!CreateEventW` at `0x1800253bc`
- `KERNEL32!CreateEventW` at `0x1800253bc`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800253a2`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800253a2`
- `KERNEL32!TlsAlloc` at `0x180025377`
- `KERNEL32!TlsAlloc` at `0x180025377`
- `KERNEL32!DeleteCriticalSection` at `0x1800253f2`
- `KERNEL32!DeleteCriticalSection` at `0x1800253f2`
- `KERNEL32!GetLastError` at `0x18002538b`
- `KERNEL32!GetLastError` at `0x1800253d1`
- `KERNEL32!GetLastError` at `0x18002538b`
- `KERNEL32!GetLastError` at `0x1800253d1`

## pseudocode

```c
DWORD __fastcall RwLockInit(__int64 a1)
{
  DWORD v2; // eax
  HANDLE EventW; // rax
  DWORD LastError; // ebx

  *(_QWORD *)a1 = 0;
  v2 = TlsAlloc();
  *(_DWORD *)(a1 + 8) = v2;
  if ( v2 == -1 )
    return GetLastError();
  *(_DWORD *)(a1 + 12) = 0;
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(a1 + 16), 0) )
    return GetLastError();
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 56) = EventW;
  if ( EventW )
  {
    *(_DWORD *)a1 = 1;
    return 0;
  }
  else
  {
    LastError = GetLastError();
    TlsFree(*(_DWORD *)(a1 + 8));
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    return LastError;
  }
}

```

## disassembly

```asm
0x180025360  mov     [rsp+arg_0], rbx
0x180025365  mov     [rsp+arg_8], rsi
0x18002536a  push    rdi
0x18002536b  sub     rsp, 20h
0x18002536f  xor     ebx, ebx
0x180025371  mov     rdi, rcx
0x180025374  mov     [rcx], rbx
0x180025377  call    cs:__imp_TlsAlloc
0x18002537e  nop     dword ptr [rax+rax+00h]
0x180025383  mov     [rdi+8], eax
0x180025386  cmp     eax, 0FFFFFFFFh
0x180025389  jnz     short loc_180025399
0x18002538b  call    cs:__imp_GetLastError
0x180025392  nop     dword ptr [rax+rax+00h]
0x180025397  jmp     short loc_18002540A
0x180025399  xor     edx, edx; dwSpinCount
0x18002539b  mov     [rdi+0Ch], ebx
0x18002539e  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800253a2  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800253a9  nop     dword ptr [rax+rax+00h]
0x1800253ae  test    eax, eax
0x1800253b0  jz      short loc_18002538B
0x1800253b2  xor     r9d, r9d; lpName
0x1800253b5  xor     r8d, r8d; bInitialState
0x1800253b8  xor     edx, edx; bManualReset
0x1800253ba  xor     ecx, ecx; lpEventAttributes
0x1800253bc  call    cs:__imp_CreateEventW
0x1800253c3  nop     dword ptr [rax+rax+00h]
0x1800253c8  mov     [rdi+38h], rax
0x1800253cc  test    rax, rax
0x1800253cf  jnz     short loc_180025402
0x1800253d1  call    cs:__imp_GetLastError
0x1800253d8  nop     dword ptr [rax+rax+00h]
0x1800253dd  mov     ecx, [rdi+8]; dwTlsIndex
0x1800253e0  mov     ebx, eax
0x1800253e2  call    cs:__imp_TlsFree
0x1800253e9  nop     dword ptr [rax+rax+00h]
0x1800253ee  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800253f2  call    cs:__imp_DeleteCriticalSection
0x1800253f9  nop     dword ptr [rax+rax+00h]
0x1800253fe  mov     eax, ebx
0x180025400  jmp     short loc_18002540A
0x180025402  mov     dword ptr [rdi], 1
0x180025408  xor     eax, eax
0x18002540a  mov     rbx, [rsp+28h+arg_0]
0x18002540f  mov     rsi, [rsp+28h+arg_8]
0x180025414  add     rsp, 20h
0x180025418  pop     rdi
0x180025419  retn
```
