# ServiceIsTrustedByDefault

- ea: `0x18001422c`
- end: `0x1800142a4`
- name: `ServiceIsTrustedByDefault`
- size: `120`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800136b0`

## callees

- `0x18001422c`
- `0x18001e419`

## pseudocode

```c
__int64 __fastcall ServiceIsTrustedByDefault(__int64 a1)
{
  unsigned int v2; // edi
  unsigned int v3; // edx
  int v4; // ecx

  v2 = 0;
  if ( a1 )
  {
    v3 = 0;
    while ( *(_WORD *)(a1 + 2LL * v3) )
    {
      if ( ++v3 >= 6 )
      {
        if ( v3 == 6 && !wcsncmp_0((const wchar_t *)a1, L"Perf", 8u) )
        {
          v4 = 0;
          while ( *(_DWORD *)(a1 + 8) != *(_DWORD *)&aOsneprdi[2 * v4] )
          {
            if ( (unsigned int)++v4 >= 4 )
              return v2;
          }
          return 1;
        }
        return v2;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001422c  mov     [rsp+arg_0], rbx
0x180014231  mov     [rsp+arg_8], rsi
0x180014236  push    rdi
0x180014237  sub     rsp, 20h
0x18001423b  xor     esi, esi
0x18001423d  mov     rbx, rcx
0x180014240  mov     edi, esi
0x180014242  test    rcx, rcx
0x180014245  jz      short loc_180014292
0x180014247  mov     edx, esi
0x180014249  mov     eax, edx
0x18001424b  cmp     [rcx+rax*2], si
0x18001424f  jbe     short loc_180014292
0x180014251  inc     edx
0x180014253  cmp     edx, 6
0x180014256  jb      short loc_180014249
0x180014258  jnz     short loc_180014292
0x18001425a  mov     r8d, 8; MaxCount
0x180014260  lea     rdx, aPerf; "Perf"
0x180014267  call    wcsncmp_0
0x18001426c  test    eax, eax
0x18001426e  jnz     short loc_180014292
0x180014270  mov     edx, [rbx+8]
0x180014273  mov     ecx, esi
0x180014275  mov     eax, ecx
0x180014277  lea     r8, aOsneprdi; "OSNePrDi"
0x18001427e  cmp     edx, [r8+rax*4]
0x180014282  jz      short loc_18001428D
0x180014284  inc     ecx
0x180014286  cmp     ecx, 4
0x180014289  jb      short loc_180014275
0x18001428b  jmp     short loc_180014292
0x18001428d  mov     edi, 1
0x180014292  mov     rbx, [rsp+28h+arg_0]
0x180014297  mov     eax, edi
0x180014299  mov     rsi, [rsp+28h+arg_8]
0x18001429e  add     rsp, 20h
0x1800142a2  pop     rdi
0x1800142a3  retn
```
