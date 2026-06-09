# TextLogContainsPendingRenameTag

- ea: `0x1800045ec`
- end: `0x18000464f`
- name: `TextLogContainsPendingRenameTag`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800063bc`

## callees

- `0x1800045ec`
- `0x180004e0c`

## pseudocode

```c
__int64 __fastcall TextLogContainsPendingRenameTag(__int64 a1)
{
  unsigned int v1; // ebx
  unsigned int v2; // edi
  unsigned int v3; // edx
  __int64 v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  int v7; // [rsp+30h] [rbp-18h]

  v1 = 0;
  v2 = 0;
  v7 = 0;
  v3 = 0;
  v6 = 0;
  v4 = a1;
  while ( (unsigned int)TextLogEnumerateOpenSections(a1, v3, (__int64)&v6) )
  {
    if ( !DWORD1(v6) && (v7 & 0x10000) != 0 )
      return 1;
    ++v2;
    a1 = v4;
    v3 = v2;
  }
  return v1;
}

```

## disassembly

```asm
0x1800045ec  mov     [rsp+arg_0], rbx
0x1800045f1  mov     [rsp+arg_8], rsi
0x1800045f6  push    rdi
0x1800045f7  sub     rsp, 40h
0x1800045fb  xor     eax, eax
0x1800045fd  xor     ebx, ebx
0x1800045ff  xor     edi, edi
0x180004601  mov     [rsp+48h+var_18], eax
0x180004605  xorps   xmm0, xmm0
0x180004608  xor     edx, edx
0x18000460a  movups  [rsp+48h+var_28], xmm0
0x18000460f  mov     rsi, rcx
0x180004612  jmp     short loc_180004628
0x180004614  cmp     dword ptr [rsp+48h+var_28+4], ebx
0x180004618  jnz     short loc_180004621
0x18000461a  test    byte ptr [rsp+48h+var_18+2], 1
0x18000461f  jnz     short loc_180004638
0x180004621  inc     edi
0x180004623  mov     rcx, rsi
0x180004626  mov     edx, edi
0x180004628  lea     r8, [rsp+48h+var_28]
0x18000462d  call    TextLogEnumerateOpenSections
0x180004632  test    eax, eax
0x180004634  jnz     short loc_180004614
0x180004636  jmp     short loc_18000463D
0x180004638  mov     ebx, 1
0x18000463d  mov     rsi, [rsp+48h+arg_8]
0x180004642  mov     eax, ebx
0x180004644  mov     rbx, [rsp+48h+arg_0]
0x180004649  add     rsp, 40h
0x18000464d  pop     rdi
0x18000464e  retn
```
