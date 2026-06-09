# GetAttributeXmlLength(ushort const *,ushort const * &)

- ea: `0x18000c844`
- end: `0x18000c885`
- name: `?GetAttributeXmlLength@@YA_KPEBGAEAPEBG@Z`
- size: `65`
- prototype: `unsigned __int64 __fastcall(const unsigned __int16 *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000bfcc`

## callees

- `0x18000c844`

## pseudocode

```c
__int64 __fastcall GetAttributeXmlLength(const unsigned __int16 *a1, const unsigned __int16 **a2)
{
  __int64 result; // rax
  __int64 v3; // r8
  __int64 v4; // rax

  result = 0;
  if ( a1 )
  {
    v3 = -1;
    v4 = -1;
    do
      ++v4;
    while ( a1[v4] );
    result = v4 + 4;
    if ( *a2 )
    {
      do
        ++v3;
      while ( (*a2)[v3] );
      result += v3;
    }
    else
    {
      *a2 = &String;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c844  xor     r9d, r9d
0x18000c847  mov     eax, r9d
0x18000c84a  test    rcx, rcx
0x18000c84d  jz      short locret_18000C884
0x18000c84f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c853  mov     rax, r8
0x18000c856  inc     rax
0x18000c859  cmp     [rcx+rax*2], r9w
0x18000c85e  jnz     short loc_18000C856
0x18000c860  mov     rcx, [rdx]
0x18000c863  add     rax, 4
0x18000c867  test    rcx, rcx
0x18000c86a  jz      short loc_18000C87A
0x18000c86c  inc     r8
0x18000c86f  cmp     [rcx+r8*2], r9w
0x18000c874  jnz     short loc_18000C86C
0x18000c876  add     rax, r8
0x18000c879  retn
0x18000c87a  lea     rcx, String
0x18000c881  mov     [rdx], rcx
0x18000c884  retn
```
