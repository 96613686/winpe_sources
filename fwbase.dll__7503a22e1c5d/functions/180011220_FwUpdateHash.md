# FwUpdateHash

- ea: `0x180011220`
- end: `0x18001124c`
- name: `FwUpdateHash`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180011220`

## pseudocode

```c
__int64 __fastcall FwUpdateHash(__int64 a1, unsigned int a2, __int64 *a3)
{
  __int64 result; // rax
  __int64 v5; // r10
  __int64 v6; // r8

  result = 0;
  if ( a2 )
  {
    v5 = *a3;
    do
    {
      v6 = *(unsigned __int8 *)(result + a1);
      result = (unsigned int)(result + 1);
      v5 = v6 + 37 * v5;
      *a3 = v5;
    }
    while ( (unsigned int)result < a2 );
  }
  return result;
}

```

## disassembly

```asm
0x180011220  mov     [rsp+arg_0], rbx
0x180011225  xor     eax, eax
0x180011227  mov     r11, r8
0x18001122a  test    edx, edx
0x18001122c  jz      short loc_180011246
0x18001122e  mov     r10, [r8]
0x180011231  movzx   r8d, byte ptr [rax+rcx]
0x180011236  inc     eax
0x180011238  imul    r10, 25h ; '%'
0x18001123c  add     r10, r8
0x18001123f  mov     [r11], r10
0x180011242  cmp     eax, edx
0x180011244  jb      short loc_180011231
0x180011246  mov     rbx, [rsp+arg_0]
0x18001124b  retn
```
