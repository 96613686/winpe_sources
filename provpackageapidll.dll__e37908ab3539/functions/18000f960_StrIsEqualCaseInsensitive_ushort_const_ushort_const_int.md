# StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)

- ea: `0x18000f960`
- end: `0x18000f9b2`
- name: `?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z`
- size: `82`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f040`
- `0x18000f81c`
- `0x18000f8b4`
- `0x18000ff24`

## callees

- `0x18000f960`

## pseudocode

```c
bool __fastcall StrIsEqualCaseInsensitive(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  int v5; // r9d
  int v6; // edx
  int v7; // r10d
  int v8; // ecx

  do
  {
    v5 = *a1;
    v6 = *a2;
    v7 = v5 + 32;
    if ( (unsigned int)(v5 - 65) > 0x19 )
      v7 = *a1;
    v8 = v6 + 32;
    if ( (unsigned int)(v6 - 65) > 0x19 )
      v8 = *a2;
    if ( !--a3 )
      break;
    if ( !v7 )
      break;
    ++a1;
    ++a2;
  }
  while ( v7 == v8 );
  return v7 == v8;
}

```

## disassembly

```asm
0x18000f960  mov     [rsp+arg_0], rbx
0x18000f965  mov     r11, rdx
0x18000f968  mov     rbx, rcx
0x18000f96b  movzx   r9d, word ptr [rbx]
0x18000f96f  movzx   edx, word ptr [r11]
0x18000f973  lea     eax, [r9-41h]
0x18000f977  cmp     eax, 19h
0x18000f97a  lea     r10d, [r9+20h]
0x18000f97e  lea     eax, [rdx-41h]
0x18000f981  cmova   r10d, r9d
0x18000f985  lea     ecx, [rdx+20h]
0x18000f988  cmp     eax, 19h
0x18000f98b  cmova   ecx, edx
0x18000f98e  sub     r8d, 1
0x18000f992  jz      short loc_18000F9A6
0x18000f994  test    r10d, r10d
0x18000f997  jz      short loc_18000F9A6
0x18000f999  add     rbx, 2
0x18000f99d  add     r11, 2
0x18000f9a1  cmp     r10d, ecx
0x18000f9a4  jz      short loc_18000F96B
0x18000f9a6  mov     rbx, [rsp+arg_0]
0x18000f9ab  cmp     r10d, ecx
0x18000f9ae  setz    al
0x18000f9b1  retn
```
