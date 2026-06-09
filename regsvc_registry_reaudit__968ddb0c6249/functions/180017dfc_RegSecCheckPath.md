# RegSecCheckPath

- ea: `0x180017dfc`
- end: `0x180017f64`
- name: `RegSecCheckPath`
- size: `360`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019290`
- `0x1800199a0`

## callees

- `0x18001782c`
- `0x180017dfc`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180017f3f`
- `ntdll!RtlReleaseResource` at `0x180017f3f`
- `ntdll!RtlAcquireResourceShared` at `0x180017e5f`
- `ntdll!RtlAcquireResourceShared` at `0x180017e5f`
- `ntdll!RtlCompareUnicodeString` at `0x180017ef1`
- `ntdll!RtlCompareUnicodeString` at `0x180017ef1`

## pseudocode

```c
__int64 __fastcall RegSecCheckPath(__int64 a1, __m128i *a2, _DWORD *a3)
{
  unsigned int v5; // ebp
  char v6; // si
  __m128i *v7; // r15
  unsigned int i; // ebx
  __int64 v9; // r8
  USHORT v10; // cx
  bool v11; // zf
  USHORT v12; // dx
  unsigned int v13; // ebx
  UNICODE_STRING String1; // [rsp+20h] [rbp-48h] BYREF
  UNICODE_STRING String2; // [rsp+30h] [rbp-38h] BYREF

  String2 = 0;
  String1 = 0;
  if ( RegSecCheckAllowedPaths() < 0 || !a2->m128i_i64[1] || !a2->m128i_i16[0] || !a2->m128i_i16[1] )
    return 0;
  RtlAcquireResourceShared(RegSecReloadLock, 1u);
  v5 = MachineAllowedPathsCount;
  v6 = 0;
  v7 = (__m128i *)MachineAllowedPaths;
LABEL_6:
  for ( i = 0; ; ++i )
  {
    if ( i >= v5 )
    {
      v13 = 0;
      if ( v6 )
        goto LABEL_24;
      v5 = MachineAllowedExactPathsCount;
      v6 = 1;
      v7 = (__m128i *)MachineAllowedExactPaths;
      goto LABEL_6;
    }
    v9 = a2->m128i_i64[1];
    v10 = _mm_cvtsi128_si32(*a2);
    String1 = (UNICODE_STRING)*a2;
    if ( v10 )
    {
      do
      {
        if ( *(_WORD *)(v9 + 2 * ((unsigned __int64)v10 >> 1) - 2) )
          break;
        v11 = v10 == 2;
        v10 -= 2;
        String1.Length = v10;
      }
      while ( !v11 );
    }
    v12 = _mm_cvtsi128_si32(v7[i]);
    String2 = (UNICODE_STRING)v7[i];
    if ( v10 > v12 )
    {
      if ( v6 )
        continue;
      if ( *(_WORD *)(v9 + 2 * ((unsigned __int64)v12 >> 1)) == 92 )
        v10 = v12;
      String1.Length = v10;
    }
    if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
      break;
  }
  if ( a3 )
  {
    *a3 = 0;
    if ( v6 )
      *a3 = 1;
  }
  v13 = 1;
LABEL_24:
  RtlReleaseResource(RegSecReloadLock);
  return v13;
}

```

## disassembly

```asm
0x180017dfc  mov     rax, rsp
0x180017dff  mov     [rax+10h], rbx
0x180017e03  mov     [rax+18h], rbp
0x180017e07  push    rsi
0x180017e08  push    rdi
0x180017e09  push    r12
0x180017e0b  push    r14
0x180017e0d  push    r15
0x180017e0f  sub     rsp, 40h
0x180017e13  xorps   xmm0, xmm0
0x180017e16  xorps   xmm1, xmm1
0x180017e19  movups  xmmword ptr [rax-38h], xmm0
0x180017e1d  mov     r14, r8
0x180017e20  mov     rdi, rdx
0x180017e23  movups  xmmword ptr [rax-48h], xmm1
0x180017e27  call    RegSecCheckAllowedPaths
0x180017e2c  xor     r12d, r12d
0x180017e2f  test    eax, eax
0x180017e31  js      loc_180017F49
0x180017e37  cmp     [rdi+8], r12
0x180017e3b  jz      loc_180017F49
0x180017e41  cmp     [rdi], r12w
0x180017e45  jz      loc_180017F49
0x180017e4b  cmp     [rdi+2], r12w
0x180017e50  jz      loc_180017F49
0x180017e56  mov     rcx, cs:RegSecReloadLock; Resource
0x180017e5d  mov     dl, 1; Wait
0x180017e5f  call    cs:__imp_RtlAcquireResourceShared
0x180017e65  mov     ebp, cs:MachineAllowedPathsCount
0x180017e6b  mov     sil, r12b
0x180017e6e  mov     r15, cs:MachineAllowedPaths
0x180017e75  mov     ebx, r12d
0x180017e78  cmp     ebx, ebp
0x180017e7a  jnb     loc_180017F02
0x180017e80  movups  xmm1, xmmword ptr [rdi]
0x180017e83  mov     r8, [rdi+8]
0x180017e87  movd    ecx, xmm1
0x180017e8b  movups  xmmword ptr [rsp+68h+String1.Length], xmm1
0x180017e90  test    cx, cx
0x180017e93  jz      short loc_180017EB2
0x180017e95  movzx   eax, cx
0x180017e98  shr     rax, 1
0x180017e9b  cmp     [r8+rax*2-2], r12w
0x180017ea1  jnz     short loc_180017EB2
0x180017ea3  mov     eax, 0FFFEh
0x180017ea8  add     cx, ax
0x180017eab  mov     [rsp+68h+String1.Length], cx
0x180017eb0  jnz     short loc_180017E95
0x180017eb2  mov     eax, ebx
0x180017eb4  add     rax, rax
0x180017eb7  movups  xmm0, xmmword ptr [r15+rax*8]
0x180017ebc  movd    edx, xmm0
0x180017ec0  movups  xmmword ptr [rsp+68h+String2.Length], xmm0
0x180017ec5  cmp     cx, dx
0x180017ec8  jbe     short loc_180017EE4
0x180017eca  test    sil, sil
0x180017ecd  jnz     short loc_180017EFB
0x180017ecf  movzx   eax, dx
0x180017ed2  shr     rax, 1
0x180017ed5  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x180017edb  cmovz   cx, dx
0x180017edf  mov     [rsp+68h+String1.Length], cx
0x180017ee4  mov     r8b, 1; CaseInsensitive
0x180017ee7  lea     rdx, [rsp+68h+String2]; String2
0x180017eec  lea     rcx, [rsp+68h+String1]; String1
0x180017ef1  call    cs:__imp_RtlCompareUnicodeString
0x180017ef7  test    eax, eax
0x180017ef9  jz      short loc_180017F1F
0x180017efb  inc     ebx
0x180017efd  jmp     loc_180017E78
0x180017f02  mov     ebx, r12d
0x180017f05  test    sil, sil
0x180017f08  jnz     short loc_180017F38
0x180017f0a  mov     ebp, cs:MachineAllowedExactPathsCount
0x180017f10  mov     sil, 1
0x180017f13  mov     r15, cs:MachineAllowedExactPaths
0x180017f1a  jmp     loc_180017E75
0x180017f1f  test    r14, r14
0x180017f22  jz      short loc_180017F33
0x180017f24  mov     [r14], r12d
0x180017f27  test    sil, sil
0x180017f2a  jz      short loc_180017F33
0x180017f2c  mov     dword ptr [r14], 1
0x180017f33  mov     ebx, 1
0x180017f38  mov     rcx, cs:RegSecReloadLock; Resource
0x180017f3f  call    cs:__imp_RtlReleaseResource
0x180017f45  mov     eax, ebx
0x180017f47  jmp     short loc_180017F4B
0x180017f49  xor     eax, eax
0x180017f4b  lea     r11, [rsp+68h+var_28]
0x180017f50  mov     rbx, [r11+38h]
0x180017f54  mov     rbp, [r11+40h]
0x180017f58  mov     rsp, r11
0x180017f5b  pop     r15
0x180017f5d  pop     r14
0x180017f5f  pop     r12
0x180017f61  pop     rdi
0x180017f62  pop     rsi
0x180017f63  retn
```
