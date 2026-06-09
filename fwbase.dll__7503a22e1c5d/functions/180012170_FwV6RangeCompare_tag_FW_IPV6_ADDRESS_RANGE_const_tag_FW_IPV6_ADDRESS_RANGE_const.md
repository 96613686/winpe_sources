# FwV6RangeCompare(_tag_FW_IPV6_ADDRESS_RANGE const *,_tag_FW_IPV6_ADDRESS_RANGE const *)

- ea: `0x180012170`
- end: `0x1800121af`
- name: `?FwV6RangeCompare@@YAHPEBU_tag_FW_IPV6_ADDRESS_RANGE@@0@Z`
- size: `63`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180012170`
- `0x18002f668`

## pseudocode

```c
int __fastcall FwV6RangeCompare(char *a1, char *a2)
{
  int result; // eax

  result = memcmp_0(a1, a2, 0x10u);
  if ( !result )
    return memcmp_0(a1 + 16, a2 + 16, 0x10u);
  return result;
}

```

## disassembly

```asm
0x180012170  mov     [rsp+arg_0], rbx
0x180012175  push    rdi
0x180012176  sub     rsp, 20h
0x18001217a  mov     r8d, 10h; Size
0x180012180  mov     rbx, rdx
0x180012183  mov     rdi, rcx
0x180012186  call    memcmp_0
0x18001218b  test    eax, eax
0x18001218d  jz      short loc_18001219A
0x18001218f  mov     rbx, [rsp+28h+arg_0]
0x180012194  add     rsp, 20h
0x180012198  pop     rdi
0x180012199  retn
0x18001219a  lea     rdx, [rbx+10h]; Buf2
0x18001219e  mov     r8d, 10h; Size
0x1800121a4  lea     rcx, [rdi+10h]; Buf1
0x1800121a8  call    memcmp_0
0x1800121ad  jmp     short loc_18001218F
```
