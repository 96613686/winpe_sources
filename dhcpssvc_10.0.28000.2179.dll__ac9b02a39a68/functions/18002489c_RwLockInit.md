# RwLockInit

- ea: `0x18002489c`
- end: `0x180024957`
- name: `RwLockInit`
- size: `187`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029d8`
- `0x18005546c`
- `0x180069d98`

## callees

- `0x18002489c`

## import_xrefs

- `KERNEL32!TlsFree` at `0x18002491e`
- `KERNEL32!TlsFree` at `0x18002491e`
- `KERNEL32!CreateEventW` at `0x1800248f8`
- `KERNEL32!CreateEventW` at `0x1800248f8`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800248de`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800248de`
- `KERNEL32!TlsAlloc` at `0x1800248b3`
- `KERNEL32!TlsAlloc` at `0x1800248b3`
- `KERNEL32!DeleteCriticalSection` at `0x18002492e`
- `KERNEL32!DeleteCriticalSection` at `0x18002492e`
- `KERNEL32!GetLastError` at `0x1800248c7`
- `KERNEL32!GetLastError` at `0x18002490d`
- `KERNEL32!GetLastError` at `0x1800248c7`
- `KERNEL32!GetLastError` at `0x18002490d`

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
0x18002489c  mov     [rsp+arg_0], rbx
0x1800248a1  mov     [rsp+arg_8], rsi
0x1800248a6  push    rdi
0x1800248a7  sub     rsp, 20h
0x1800248ab  xor     ebx, ebx
0x1800248ad  mov     rdi, rcx
0x1800248b0  mov     [rcx], rbx
0x1800248b3  call    cs:__imp_TlsAlloc
0x1800248ba  nop     dword ptr [rax+rax+00h]
0x1800248bf  mov     [rdi+8], eax
0x1800248c2  cmp     eax, 0FFFFFFFFh
0x1800248c5  jnz     short loc_1800248D5
0x1800248c7  call    cs:__imp_GetLastError
0x1800248ce  nop     dword ptr [rax+rax+00h]
0x1800248d3  jmp     short loc_180024946
0x1800248d5  xor     edx, edx; dwSpinCount
0x1800248d7  mov     [rdi+0Ch], ebx
0x1800248da  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800248de  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800248e5  nop     dword ptr [rax+rax+00h]
0x1800248ea  test    eax, eax
0x1800248ec  jz      short loc_1800248C7
0x1800248ee  xor     r9d, r9d; lpName
0x1800248f1  xor     r8d, r8d; bInitialState
0x1800248f4  xor     edx, edx; bManualReset
0x1800248f6  xor     ecx, ecx; lpEventAttributes
0x1800248f8  call    cs:__imp_CreateEventW
0x1800248ff  nop     dword ptr [rax+rax+00h]
0x180024904  mov     [rdi+38h], rax
0x180024908  test    rax, rax
0x18002490b  jnz     short loc_18002493E
0x18002490d  call    cs:__imp_GetLastError
0x180024914  nop     dword ptr [rax+rax+00h]
0x180024919  mov     ecx, [rdi+8]; dwTlsIndex
0x18002491c  mov     ebx, eax
0x18002491e  call    cs:__imp_TlsFree
0x180024925  nop     dword ptr [rax+rax+00h]
0x18002492a  lea     rcx, [rdi+10h]; lpCriticalSection
0x18002492e  call    cs:__imp_DeleteCriticalSection
0x180024935  nop     dword ptr [rax+rax+00h]
0x18002493a  mov     eax, ebx
0x18002493c  jmp     short loc_180024946
0x18002493e  mov     dword ptr [rdi], 1
0x180024944  xor     eax, eax
0x180024946  mov     rbx, [rsp+28h+arg_0]
0x18002494b  mov     rsi, [rsp+28h+arg_8]
0x180024950  add     rsp, 20h
0x180024954  pop     rdi
0x180024955  retn
```
