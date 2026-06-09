# RtlStringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x14000ef60`
- end: `0x14000efaf`
- name: `?RtlStringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `79`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e904`
- `0x14000efb8`
- `0x14000f7f8`
- `0x1400100ac`
- `0x140010380`

## callees

- `0x14000ef60`

## pseudocode

```c
__int64 __fastcall RtlStringCbCopyW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  unsigned __int16 *v5; // rdx
  __int64 result; // rax

  v3 = 2147483646;
  v4 = 36;
  do
  {
    if ( !v3 )
      break;
    if ( !*a3 )
      break;
    *a1++ = *a3++;
    --v3;
    --v4;
  }
  while ( v4 );
  v5 = a1 - 1;
  result = v4 == 0 ? 0x80000005 : 0;
  if ( v4 )
    v5 = a1;
  *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x14000ef60  mov     eax, 7FFFFFFEh
0x14000ef65  mov     r9d, 24h ; '$'
0x14000ef6b  xor     r10d, r10d
0x14000ef6e  test    rax, rax
0x14000ef71  jz      short loc_14000EF90
0x14000ef73  movzx   edx, word ptr [r8]
0x14000ef77  test    dx, dx
0x14000ef7a  jz      short loc_14000EF90
0x14000ef7c  mov     [rcx], dx
0x14000ef7f  add     r8, 2
0x14000ef83  add     rcx, 2
0x14000ef87  dec     rax
0x14000ef8a  sub     r9, 1
0x14000ef8e  jnz     short loc_14000EF6E
0x14000ef90  mov     rax, r9
0x14000ef93  lea     rdx, [rcx-2]
0x14000ef97  neg     rax
0x14000ef9a  sbb     eax, eax
0x14000ef9c  not     eax
0x14000ef9e  and     eax, 80000005h
0x14000efa3  test    r9, r9
0x14000efa6  cmovnz  rdx, rcx
0x14000efaa  mov     [rdx], r10w
0x14000efae  retn
```
