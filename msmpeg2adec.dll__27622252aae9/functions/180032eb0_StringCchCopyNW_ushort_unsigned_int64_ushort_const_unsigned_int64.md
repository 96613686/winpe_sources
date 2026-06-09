# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180032eb0`
- end: `0x180032ef8`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `72`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180032f00`

## callees

- `0x180032eb0`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3)
{
  const wchar_t *v3; // rax
  __int64 v4; // r8
  unsigned __int16 *v5; // rcx
  __int64 result; // rax
  unsigned __int16 *v7; // rdx

  v3 = L"Software\\Microsoft\\Scrunch\\CodecPack\\MSDVD";
  v4 = 63;
  v5 = &xmmword_1800ADB00;
  do
  {
    if ( !*v3 )
      break;
    *v5++ = *v3++;
    --v4;
  }
  while ( v4 );
  result = 2147942522LL;
  if ( v4 )
    result = 0;
  v7 = v5 - 1;
  if ( v4 )
    v7 = v5;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x180032eb0  lea     rax, aSoftwareMicros_2; "Software\\Microsoft\\Scrunch\\CodecPack"...
0x180032eb7  mov     r8d, 3Fh ; '?'
0x180032ebd  lea     rcx, xmmword_1800ADB00
0x180032ec4  movzx   edx, word ptr [rax]
0x180032ec7  test    dx, dx
0x180032eca  jz      short loc_180032EDD
0x180032ecc  mov     [rcx], dx
0x180032ecf  add     rax, 2
0x180032ed3  add     rcx, 2
0x180032ed7  sub     r8, 1
0x180032edb  jnz     short loc_180032EC4
0x180032edd  xor     edx, edx
0x180032edf  mov     eax, 8007007Ah
0x180032ee4  test    r8, r8
0x180032ee7  cmovnz  eax, edx
0x180032eea  lea     rdx, [rcx-2]
0x180032eee  cmovnz  rdx, rcx
0x180032ef2  xor     ecx, ecx
0x180032ef4  mov     [rdx], cx
0x180032ef7  retn
```
