# MRxDAVIsValidDirectory

- ea: `0x140021470`
- end: `0x1400214be`
- name: `MRxDAVIsValidDirectory`
- size: `78`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140006782`
- `0x140021470`

## pseudocode

```c
__int64 __fastcall MRxDAVIsValidDirectory(__int64 a1)
{
  unsigned int v1; // ebx
  const char *i; // rdi
  __int64 v3; // rax

  v1 = -1073741823;
  if ( *(_DWORD *)(a1 + 712) )
  {
    for ( i = *(const char **)(a1 + 696); strcmp_0(i + 8, "mrxdav"); i += v3 )
    {
      v3 = *(unsigned int *)i;
      if ( !(_DWORD)v3 )
        return v1;
    }
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x140021470  mov     [rsp+arg_0], rbx
0x140021475  push    rdi
0x140021476  sub     rsp, 20h
0x14002147a  cmp     dword ptr [rcx+2C8h], 0
0x140021481  mov     ebx, 0C0000001h
0x140021486  jz      short loc_1400214B0
0x140021488  mov     rdi, [rcx+2B8h]
0x14002148f  jmp     short loc_14002149A
0x140021491  mov     eax, [rdi]
0x140021493  test    eax, eax
0x140021495  jz      short loc_1400214B0
0x140021497  add     rdi, rax
0x14002149a  lea     rdx, aMrxdav; "mrxdav"
0x1400214a1  lea     rcx, [rdi+8]; Str1
0x1400214a5  call    strcmp_0
0x1400214aa  test    eax, eax
0x1400214ac  jnz     short loc_140021491
0x1400214ae  xor     ebx, ebx
0x1400214b0  mov     eax, ebx
0x1400214b2  mov     rbx, [rsp+28h+arg_0]
0x1400214b7  add     rsp, 20h
0x1400214bb  pop     rdi
0x1400214bc  retn
```
