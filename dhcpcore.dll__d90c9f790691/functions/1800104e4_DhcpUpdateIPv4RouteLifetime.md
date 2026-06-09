# DhcpUpdateIPv4RouteLifetime

- ea: `0x1800104e4`
- end: `0x180010674`
- name: `DhcpUpdateIPv4RouteLifetime`
- size: `400`
- prototype: `__int64 __fastcall(unsigned int, __int64, _QWORD *, int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180017e68`

## callees

- `0x1800104e4`
- `0x18001cef0`
- `0x1800492fc`
- `0x18004d1a0`
- `0x18004dbc4`

## import_xrefs

- `NSI!NsiSetParameterEx` at `0x1800105f8`
- `NSI!NsiSetParameterEx` at `0x1800105f8`

## pseudocode

```c
__int64 __fastcall DhcpUpdateIPv4RouteLifetime(unsigned int a1, __int64 a2, _QWORD *a3, int a4, unsigned int a5)
{
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rcx
  __m128i si128; // xmm0
  unsigned int v10; // ebx
  char v11; // al
  __int64 v13; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+48h] [rbp-C0h]
  const NPI_MODULEID *v15; // [rsp+50h] [rbp-B8h]
  __int64 v16; // [rsp+58h] [rbp-B0h]
  __int64 v17; // [rsp+60h] [rbp-A8h]
  __int128 *v18; // [rsp+68h] [rbp-A0h]
  __int64 v19; // [rsp+70h] [rbp-98h]
  __int64 v20; // [rsp+78h] [rbp-90h]
  __int8 *v21; // [rsp+80h] [rbp-88h]
  __int64 v22; // [rsp+88h] [rbp-80h]
  __int128 v23; // [rsp+90h] [rbp-78h] BYREF
  __int128 v24; // [rsp+A0h] [rbp-68h]
  __int128 v25; // [rsp+B0h] [rbp-58h]
  __m128i v26; // [rsp+C0h] [rbp-48h] BYREF
  __m128i v27; // [rsp+D0h] [rbp-38h]

  v14 = 0;
  v23 = 0;
  v16 = 16;
  v24 = 0;
  v6 = a1;
  v19 = 48;
  v25 = 0;
  v7 = *a3;
  v8 = 0xFFFFFFFFLL;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *((_QWORD *)&v24 + 1) = *a3;
  if ( a5 != -1 )
    v8 = a5;
  *(_QWORD *)&v25 = v7;
  v15 = &NPI_MS_IPV4_MODULEID;
  v18 = &v23;
  v20 = 0;
  v13 = 0;
  v17 = 1;
  v26 = si128;
  v21 = &v26.m128i_i8[4];
  v22 = 0x400000004LL;
  v27 = si128;
  DWORD1(v23) = v6;
  BYTE8(v23) = a2;
  HIDWORD(v23) = 0;
  LOBYTE(v24) = 0;
  DWORD2(v25) = a4;
  v26.m128i_i32[2] = v8;
  v26.m128i_i32[1] = v8;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_JDdDD(
      v8,
      a2,
      v6,
      *a3,
      v6,
      (unsigned __int8)a2,
      a4,
      v8,
      v13,
      v14,
      v15,
      v16,
      v17,
      v18,
      v19,
      v20,
      v21,
      v22,
      v23,
      *((_QWORD *)&v23 + 1),
      v24,
      *((_QWORD *)&v24 + 1),
      v25,
      *((_QWORD *)&v25 + 1),
      v26.m128i_i64[0],
      v26.m128i_i64[1],
      v27.m128i_i64[0],
      v27.m128i_i64[1]);
  v10 = NsiSetParameterEx(&v13);
  v11 = xmmword_1800616A0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    WPP_SF_D(1028, 69, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, v10);
    v11 = xmmword_1800616A0;
  }
  if ( !v10 )
    return 0;
  if ( (v11 & 2) != 0 )
    WPP_SF_dJ(1025, 70, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, v10, *a3);
  return v10;
}

```

## disassembly

```asm
0x1800104e4  mov     r11, rsp
0x1800104e7  push    rbx
0x1800104e8  push    rdi
0x1800104e9  sub     rsp, 0F8h
0x1800104f0  mov     rax, cs:__security_cookie
0x1800104f7  xor     rax, rsp
0x1800104fa  mov     [rsp+108h+var_28], rax
0x180010502  xorps   xmm0, xmm0
0x180010505  mov     [rsp+108h+var_C0], 0
0x18001050e  movups  xmmword ptr [r11-78h], xmm0
0x180010513  mov     [rsp+108h+var_B0], 10h
0x18001051c  mov     rdi, r8
0x18001051f  movups  xmmword ptr [r11-68h], xmm0
0x180010524  mov     r8d, ecx
0x180010527  mov     [rsp+108h+var_98], 30h ; '0'
0x180010530  movups  xmmword ptr [r11-58h], xmm0
0x180010535  mov     rax, [rdi]
0x180010538  or      ecx, 0FFFFFFFFh
0x18001053b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180010543  cmp     [rsp+108h+arg_20], ecx
0x18001054a  mov     [r11-60h], rax
0x18001054e  cmovnz  ecx, [rsp+108h+arg_20]
0x180010556  mov     [r11-58h], rax
0x18001055a  lea     rax, NPI_MS_IPV4_MODULEID
0x180010561  mov     [rsp+108h+var_B8], rax
0x180010566  lea     rax, [r11-78h]
0x18001056a  mov     [rsp+108h+var_A0], rax
0x18001056f  lea     rax, [r11-44h]
0x180010573  mov     [rsp+108h+var_90], 0
0x18001057c  mov     [rsp+108h+var_C8], 0
0x180010585  mov     [rsp+108h+var_A8], 1
0x18001058e  movups  xmmword ptr [r11-48h], xmm0
0x180010593  mov     [r11-88h], rax
0x18001059a  mov     eax, 4
0x18001059f  mov     [r11-80h], eax
0x1800105a3  mov     [r11-7Ch], eax
0x1800105a7  movups  xmmword ptr [r11-38h], xmm0
0x1800105ac  mov     [r11-74h], r8d
0x1800105b0  mov     [r11-70h], dl
0x1800105b4  mov     dword ptr [r11-6Ch], 0
0x1800105bc  mov     byte ptr [r11-68h], 0
0x1800105c1  mov     [r11-50h], r9d
0x1800105c5  mov     [r11-40h], ecx
0x1800105c9  mov     [r11-44h], ecx
0x1800105cd  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800105d4  jz      short loc_1800105F3
0x1800105d6  mov     [rsp+108h+var_D0], ecx
0x1800105da  mov     [rsp+108h+var_D8], r9d
0x1800105df  mov     r9, [rdi]
0x1800105e2  movzx   eax, dl
0x1800105e5  mov     [rsp+108h+var_E0], eax
0x1800105e9  mov     dword ptr [rsp+108h+var_E8], r8d
0x1800105ee  call    WPP_SF_JDdDD
0x1800105f3  lea     rcx, [rsp+108h+var_C8]
0x1800105f8  call    cs:__imp_NsiSetParameterEx
0x1800105fe  mov     ebx, eax
0x180010600  mov     al, byte ptr cs:xmmword_1800616A0
0x180010606  test    al, 10h
0x180010608  jnz     short loc_18001064F
0x18001060a  test    ebx, ebx
0x18001060c  jz      short loc_180010670
0x18001060e  test    al, 2
0x180010610  jz      short loc_180010633
0x180010612  mov     rax, [rdi]
0x180010615  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x18001061c  mov     edx, 46h ; 'F'
0x180010621  mov     [rsp+108h+var_E8], rax
0x180010626  mov     ecx, 401h
0x18001062b  mov     r9d, ebx
0x18001062e  call    WPP_SF_dJ
0x180010633  mov     eax, ebx
0x180010635  mov     rcx, [rsp+108h+var_28]
0x18001063d  xor     rcx, rsp; StackCookie
0x180010640  call    __security_check_cookie
0x180010645  add     rsp, 0F8h
0x18001064c  pop     rdi
0x18001064d  pop     rbx
0x18001064e  retn
0x18001064f  mov     edx, 45h ; 'E'
0x180010654  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x18001065b  mov     ecx, 404h
0x180010660  mov     r9d, ebx
0x180010663  call    WPP_SF_D
0x180010668  mov     al, byte ptr cs:xmmword_1800616A0
0x18001066e  jmp     short loc_18001060A
0x180010670  xor     eax, eax
0x180010672  jmp     short loc_180010635
```
