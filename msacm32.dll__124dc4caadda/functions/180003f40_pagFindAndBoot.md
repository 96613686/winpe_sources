# pagFindAndBoot

- ea: `0x180003f40`
- end: `0x180003fb9`
- name: `pagFindAndBoot`
- size: `121`
- prototype: `__int64(void)`
- caller_count: `18`
- callee_count: `3`
- tags: ``

## callers

- `0x180002470`
- `0x180002540`
- `0x180002900`
- `0x180002b00`
- `0x180002e70`
- `0x180005990`
- `0x180007ef0`
- `0x180008160`
- `0x1800089c0`
- `0x180008c00`
- `0x180008d00`
- `0x18000b8d0`
- `0x18000bca0`
- `0x18000c130`
- `0x18000cfe0`
- `0x18000d7b0`
- `0x18000da50`
- `0x1800119c0`

## callees

- `0x1800012a0`
- `0x180003f40`
- `0x180005e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003f62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003f62`

## pseudocode

```c
__int64 pagFindAndBoot()
{
  __int64 v0; // rbx
  int v1; // esi

  v0 = gplag;
  if ( !gplag )
    return 0;
  v1 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(gplag + 24));
  if ( !*(_DWORD *)(v0 + 16) )
  {
    v1 = acmBootDrivers(v0);
    if ( !v1 )
      v1 = acmBootPnpDrivers(v0);
    *(_DWORD *)(v0 + 16) = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v0 + 24));
  if ( v1 )
    return 0;
  else
    return gplag;
}

```

## disassembly

```asm
0x180003f40  push    rbx
0x180003f42  sub     rsp, 20h
0x180003f46  mov     rbx, cs:gplag
0x180003f4d  test    rbx, rbx
0x180003f50  jz      short loc_180003F92
0x180003f52  mov     [rsp+28h+arg_0], rsi
0x180003f57  lea     rcx, [rbx+18h]; lpCriticalSection
0x180003f5b  mov     [rsp+28h+arg_8], rdi
0x180003f60  xor     esi, esi
0x180003f62  call    cs:__imp_EnterCriticalSection
0x180003f68  cmp     [rbx+10h], esi
0x180003f6b  jz      short loc_180003F96
0x180003f6d  lea     rcx, [rbx+18h]; lpCriticalSection
0x180003f71  call    cs:__imp_LeaveCriticalSection
0x180003f77  mov     rdi, [rsp+28h+arg_8]
0x180003f7c  test    esi, esi
0x180003f7e  mov     rsi, [rsp+28h+arg_0]
0x180003f83  jnz     short loc_180003F92
0x180003f85  mov     rax, cs:gplag
0x180003f8c  add     rsp, 20h
0x180003f90  pop     rbx
0x180003f91  retn
0x180003f92  xor     eax, eax
0x180003f94  jmp     short loc_180003F8C
0x180003f96  mov     rcx, rbx
0x180003f99  call    acmBootDrivers
0x180003f9e  mov     esi, eax
0x180003fa0  test    eax, eax
0x180003fa2  jz      short loc_180003FAD
0x180003fa4  mov     dword ptr [rbx+10h], 1
0x180003fab  jmp     short loc_180003F6D
0x180003fad  mov     rcx, rbx
0x180003fb0  call    acmBootPnpDrivers
0x180003fb5  mov     esi, eax
0x180003fb7  jmp     short loc_180003FA4
```
