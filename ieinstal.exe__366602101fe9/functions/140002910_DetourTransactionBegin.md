# DetourTransactionBegin

- ea: `0x140002910`
- end: `0x1400029c8`
- name: `DetourTransactionBegin`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d36c`
- `0x14000d4f0`

## callees

- `0x140002910`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002921`
- `KERNEL32!GetCurrentThreadId` at `0x140002921`
- `KERNEL32!VirtualProtect` at `0x140002983`
- `KERNEL32!VirtualProtect` at `0x140002983`
- `KERNEL32!GetLastError` at `0x1400029a8`
- `KERNEL32!GetLastError` at `0x1400029a8`

## pseudocode

```c
DWORD DetourTransactionBegin()
{
  _QWORD *v0; // rbx
  DWORD result; // eax
  DWORD flOldProtect; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_140017728 || _InterlockedCompareExchange(&dword_140017728, GetCurrentThreadId(), 0) )
    return 4317;
  v0 = lpBaseAddress;
  qword_140017740 = 0;
  qword_140017738 = 0;
  qword_140017730 = 0;
  if ( lpBaseAddress )
  {
    while ( VirtualProtect(v0, 0x10000u, 0x40u, &flOldProtect) )
    {
      v0 = (_QWORD *)v0[1];
      if ( !v0 )
        goto LABEL_6;
    }
    result = GetLastError();
    dword_14001772C = result;
  }
  else
  {
LABEL_6:
    result = 0;
    dword_14001772C = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140002910  sub     rsp, 28h
0x140002914  cmp     cs:dword_140017728, 0
0x14000291b  jnz     loc_1400029BE
0x140002921  call    cs:__imp_GetCurrentThreadId
0x140002927  mov     ecx, eax
0x140002929  xor     eax, eax
0x14000292b  lock cmpxchg cs:dword_140017728, ecx
0x140002933  jnz     loc_1400029BE
0x140002939  mov     [rsp+28h+var_8], rbx
0x14000293e  mov     rbx, cs:lpBaseAddress
0x140002945  mov     cs:qword_140017740, 0
0x140002950  mov     cs:qword_140017738, 0
0x14000295b  mov     cs:qword_140017730, 0
0x140002966  test    rbx, rbx
0x140002969  jz      short loc_140002996
0x14000296b  nop     dword ptr [rax+rax+00h]
0x140002970  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x140002975  mov     edx, 10000h; dwSize
0x14000297a  mov     r8d, 40h ; '@'; flNewProtect
0x140002980  mov     rcx, rbx; lpAddress
0x140002983  call    cs:__imp_VirtualProtect
0x140002989  test    eax, eax
0x14000298b  jz      short loc_1400029A8
0x14000298d  mov     rbx, [rbx+8]
0x140002991  test    rbx, rbx
0x140002994  jnz     short loc_140002970
0x140002996  mov     rbx, [rsp+28h+var_8]
0x14000299b  xor     eax, eax
0x14000299d  mov     cs:dword_14001772C, eax
0x1400029a3  add     rsp, 28h
0x1400029a7  retn
0x1400029a8  call    cs:__imp_GetLastError
0x1400029ae  mov     rbx, [rsp+28h+var_8]
0x1400029b3  mov     cs:dword_14001772C, eax
0x1400029b9  add     rsp, 28h
0x1400029bd  retn
0x1400029be  mov     eax, 10DDh
0x1400029c3  add     rsp, 28h
0x1400029c7  retn
```
