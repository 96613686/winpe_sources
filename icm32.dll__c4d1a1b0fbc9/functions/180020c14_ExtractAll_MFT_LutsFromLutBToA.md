# ExtractAll_MFT_LutsFromLutBToA

- ea: `0x180020c14`
- end: `0x180021059`
- name: `ExtractAll_MFT_LutsFromLutBToA`
- size: `1093`
- prototype: `__int64 __fastcall(__int64, __int64, TAGTYPE)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180005838`

## callees

- `0x18000604c`
- `0x180007418`
- `0x180018af8`
- `0x180019b00`
- `0x18001a7d0`
- `0x180020984`
- `0x180020c14`
- `0x18003d040`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180020e94`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180020e94`

## pseudocode

```c
__int64 __fastcall ExtractAll_MFT_LutsFromLutBToA(__int64 a1, __int64 a2, TAGTYPE a3)
{
  HPROFILE v6; // rcx
  __int64 result; // rax
  unsigned int v8; // ecx
  unsigned int v9; // eax
  int v10; // r14d
  int v11; // r15d
  int v12; // r9d
  int v13; // r10d
  int v14; // r11d
  __int64 v15; // rax
  int v16; // r9d
  unsigned __int8 v17; // r14
  int v18; // r9d
  DWORD v19; // ecx
  DWORD v20; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbElement; // [rsp+54h] [rbp-ACh] BYREF
  BOOL v22; // [rsp+58h] [rbp-A8h] BYREF
  BOOL v23; // [rsp+5Ch] [rbp-A4h] BYREF
  BOOL v24; // [rsp+60h] [rbp-A0h] BYREF
  BOOL v25; // [rsp+64h] [rbp-9Ch] BYREF
  BOOL v26; // [rsp+68h] [rbp-98h] BYREF
  DWORD v27[4]; // [rsp+70h] [rbp-90h] BYREF
  DWORD v28[2]; // [rsp+80h] [rbp-80h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-70h] BYREF
  BOOL *v30; // [rsp+A0h] [rbp-60h]
  __int64 v31; // [rsp+A8h] [rbp-58h]
  BOOL *v32; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  BOOL *v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C8h] [rbp-38h]
  BOOL *v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  BOOL *v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+E8h] [rbp-18h]
  _WORD v40[8]; // [rsp+F0h] [rbp-10h] BYREF

  pcbElement = 24;
  v22 = 0;
  v23 = 0;
  *(_QWORD *)v28 = 0;
  v24 = 0;
  v6 = *(HPROFILE *)a2;
  v25 = 0;
  v26 = 0;
  v20 = 0;
  *(_OWORD *)v27 = 0;
  result = CMGetPartialProfileElement(v6, a3, 8u, &pcbElement, v27);
  if ( (_DWORD)result )
    return result;
  if ( pcbElement != 24 )
    return 2011;
  v8 = LOBYTE(v27[0]);
  v9 = BYTE1(v27[0]);
  *(_DWORD *)(a1 + 48) = LOBYTE(v27[0]);
  *(_DWORD *)(a1 + 52) = v9;
  if ( !v8 || !v9 || v8 > 8 || v9 > 8 )
    return 2011;
  v27[1] = HIBYTE(v27[1]) | ((BYTE2(v27[1]) | ((BYTE1(v27[1]) | (LOBYTE(v27[1]) << 8)) << 8)) << 8);
  v27[2] = HIBYTE(v27[2]) | ((BYTE2(v27[2]) | ((BYTE1(v27[2]) | (LOBYTE(v27[2]) << 8)) << 8)) << 8);
  v27[3] = HIBYTE(v27[3]) | ((BYTE2(v27[3]) | ((BYTE1(v27[3]) | (LOBYTE(v27[3]) << 8)) << 8)) << 8);
  v10 = HIBYTE(v28[0]) | ((BYTE2(v28[0]) | ((BYTE1(v28[0]) | (LOBYTE(v28[0]) << 8)) << 8)) << 8);
  v28[0] = v10;
  v11 = HIBYTE(v28[1]) | ((BYTE2(v28[1]) | ((BYTE1(v28[1]) | (LOBYTE(v28[1]) << 8)) << 8)) << 8);
  v28[1] = v11;
  ConvertDwordToString(a3, v40);
  v15 = -1;
  do
    ++v15;
  while ( v40[v15] );
  UserData.Reserved = 0;
  UserData.Size = 2 * v15 + 2;
  UserData.Ptr = (ULONGLONG)v40;
  v31 = 4;
  v33 = 4;
  v22 = v12 != 0;
  v35 = 4;
  v30 = &v22;
  v37 = 4;
  v39 = 4;
  v23 = v13 != 0;
  v32 = &v23;
  v24 = v14 != 0;
  v34 = &v24;
  v25 = v10 != 0;
  v36 = &v25;
  v26 = v11 != 0;
  v38 = &v26;
  EventWrite(g_etwHandle, &V4_LUT_ELEMENTS, 6u, &UserData);
  result = CMGetPartialProfileElement(*(HPROFILE *)a2, a3, 0, &v20, 0);
  if ( (_DWORD)result )
    return result;
  if ( !v27[1] )
    return 2011;
  if ( *(_BYTE *)(a2 + 48) || (v17 = 10, *(_BYTE *)(a2 + 52)) )
    v17 = 16;
  LOBYTE(v16) = v27[0];
  result = ExtractNestedCurves(*(_QWORD *)a2, a3, v20, v16, v27[1], 8, v17, a1 + 16);
  if ( (_DWORD)result )
    return result;
  *(_DWORD *)(a1 + 4) = 256;
  *(_DWORD *)(a1 + 8) = v17;
  v19 = v27[2];
  if ( v27[2] )
  {
    if ( !v27[3] || LOBYTE(v27[0]) != 3 )
      return 2011;
    result = ExtractMatrixWithOffsets(*(HPROFILE *)a2, a3, a1 + 120);
    if ( (_DWORD)result )
      return result;
    v19 = v27[2];
  }
  if ( !v27[3] )
    goto LABEL_24;
  if ( !v19 )
    return 2011;
  LOBYTE(v18) = v27[0];
  result = ExtractNestedCurves(*(_QWORD *)a2, a3, v20, v18, v27[3], 8, 16, a1 + 88);
  if ( (_DWORD)result )
    return result;
  *(_DWORD *)(a1 + 112) = 256;
  *(_DWORD *)(a1 + 116) = 16;
LABEL_24:
  if ( !v28[0] )
  {
    if ( BYTE1(v27[0]) != LOBYTE(v27[0]) )
      return 2011;
    goto LABEL_30;
  }
  if ( !v28[1] )
    return 2011;
  result = ExtractAtoBStyleClut(
             *(HPROFILE *)a2,
             a3,
             v20,
             v27[0],
             BYTE1(v27[0]),
             v28[0],
             a1 + 96,
             (_DWORD *)(a1 + 56),
             (_QWORD *)(a1 + 64),
             a1 + 60);
  if ( !(_DWORD)result )
  {
LABEL_30:
    result = ExtractACurvesFromLutBToA(a1, a2, v27, a3, v20);
    if ( !(_DWORD)result )
      *(_DWORD *)a1 = 4;
  }
  return result;
}

```

## disassembly

```asm
0x180020c14  mov     [rsp-8+arg_18], rbx
0x180020c19  push    rbp
0x180020c1a  push    rsi
0x180020c1b  push    rdi
0x180020c1c  push    r12
0x180020c1e  push    r13
0x180020c20  push    r14
0x180020c22  push    r15
0x180020c24  lea     rbp, [rsp-10h]
0x180020c29  sub     rsp, 110h
0x180020c30  mov     rax, cs:__security_cookie
0x180020c37  xor     rax, rsp
0x180020c3a  mov     [rbp+40h+var_40], rax
0x180020c3e  xor     r12d, r12d
0x180020c41  mov     [rsp+140h+pcbElement], 18h
0x180020c49  mov     rdi, rdx
0x180020c4c  mov     [rsp+140h+var_E8], r12d
0x180020c51  xor     eax, eax
0x180020c53  mov     [rsp+140h+var_E4], r12d
0x180020c58  mov     esi, r8d
0x180020c5b  mov     qword ptr [rbp+40h+var_C0], rax
0x180020c5f  mov     rbx, rcx
0x180020c62  mov     [rsp+140h+var_E0], r12d
0x180020c67  mov     rcx, [rdi]; hProfile
0x180020c6a  lea     rax, [rsp+140h+var_D0]
0x180020c6f  xorps   xmm0, xmm0
0x180020c72  mov     [rsp+140h+var_DC], r12d
0x180020c77  lea     r8d, [r12+8]; dwOffset
0x180020c7c  mov     [rsp+140h+var_D8], r12d
0x180020c81  lea     r9, [rsp+140h+pcbElement]; pcbElement
0x180020c86  mov     [rsp+140h+var_F0], r12d
0x180020c8b  mov     edx, esi; tag
0x180020c8d  mov     [rsp+140h+var_120], rax; PVOID
0x180020c92  movups  xmmword ptr [rsp+140h+var_D0], xmm0
0x180020c97  call    CMGetPartialProfileElement
0x180020c9c  test    eax, eax
0x180020c9e  jnz     loc_180020FB8
0x180020ca4  cmp     [rsp+140h+pcbElement], 18h
0x180020ca9  jnz     loc_180020FB3
0x180020caf  movzx   ecx, byte ptr [rsp+140h+var_D0]
0x180020cb4  movzx   eax, byte ptr [rsp+140h+var_D0+1]
0x180020cb9  mov     [rbx+30h], ecx
0x180020cbc  mov     [rbx+34h], eax
0x180020cbf  test    ecx, ecx
0x180020cc1  jz      loc_180020FB3
0x180020cc7  test    eax, eax
0x180020cc9  jz      loc_180020FB3
0x180020ccf  cmp     ecx, 8
0x180020cd2  ja      loc_180020FB3
0x180020cd8  cmp     eax, 8
0x180020cdb  ja      loc_180020FB3
0x180020ce1  movzx   eax, byte ptr [rsp+140h+var_D0+5]
0x180020ce6  lea     rdx, [rbp+40h+var_50]
0x180020cea  movzx   r9d, byte ptr [rsp+140h+var_D0+4]
0x180020cf0  mov     ecx, esi
0x180020cf2  movzx   r10d, byte ptr [rsp+140h+var_D0+8]
0x180020cf8  movzx   r11d, byte ptr [rsp+140h+var_D0+0Ch]
0x180020cfe  movzx   r14d, byte ptr [rbp+40h+var_C0]
0x180020d03  movzx   r15d, byte ptr [rbp+40h+var_C0+4]
0x180020d08  shl     r9d, 8
0x180020d0c  or      r9d, eax
0x180020d0f  shl     r10d, 8
0x180020d13  movzx   eax, byte ptr [rsp+140h+var_D0+6]
0x180020d18  shl     r11d, 8
0x180020d1c  shl     r14d, 8
0x180020d20  shl     r15d, 8
0x180020d24  shl     r9d, 8
0x180020d28  or      r9d, eax
0x180020d2b  movzx   eax, byte ptr [rsp+140h+var_D0+7]
0x180020d30  shl     r9d, 8
0x180020d34  or      r9d, eax
0x180020d37  movzx   eax, byte ptr [rsp+140h+var_D0+9]
0x180020d3c  or      r10d, eax
0x180020d3f  mov     [rsp+140h+var_D0+4], r9d
0x180020d44  movzx   eax, byte ptr [rsp+140h+var_D0+0Ah]
0x180020d49  shl     r10d, 8
0x180020d4d  or      r10d, eax
0x180020d50  movzx   eax, byte ptr [rsp+140h+var_D0+0Bh]
0x180020d55  shl     r10d, 8
0x180020d59  or      r10d, eax
0x180020d5c  movzx   eax, byte ptr [rsp+140h+var_D0+0Dh]
0x180020d61  or      r11d, eax
0x180020d64  mov     [rsp+140h+var_D0+8], r10d
0x180020d69  movzx   eax, byte ptr [rsp+140h+var_D0+0Eh]
0x180020d6e  shl     r11d, 8
0x180020d72  or      r11d, eax
0x180020d75  movzx   eax, byte ptr [rsp+140h+var_D0+0Fh]
0x180020d7a  shl     r11d, 8
0x180020d7e  or      r11d, eax
0x180020d81  movzx   eax, byte ptr [rbp+40h+var_C0+1]
0x180020d85  or      r14d, eax
0x180020d88  mov     [rsp+140h+var_D0+0Ch], r11d
0x180020d8d  movzx   eax, byte ptr [rbp+40h+var_C0+2]
0x180020d91  shl     r14d, 8
0x180020d95  or      r14d, eax
0x180020d98  movzx   eax, byte ptr [rbp+40h+var_C0+3]
0x180020d9c  shl     r14d, 8
0x180020da0  or      r14d, eax
0x180020da3  movzx   eax, byte ptr [rbp+40h+var_C0+5]
0x180020da7  or      r15d, eax
0x180020daa  mov     [rbp+40h+var_C0], r14d
0x180020dae  movzx   eax, byte ptr [rbp+40h+var_C0+6]
0x180020db2  shl     r15d, 8
0x180020db6  or      r15d, eax
0x180020db9  movzx   eax, byte ptr [rbp+40h+var_C0+7]
0x180020dbd  shl     r15d, 8
0x180020dc1  or      r15d, eax
0x180020dc4  mov     [rbp+40h+var_C0+4], r15d
0x180020dc8  call    ConvertDwordToString
0x180020dcd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020dd1  lea     rdx, [rbp+40h+var_50]
0x180020dd5  inc     rax
0x180020dd8  cmp     [rdx+rax*2], r12w
0x180020ddd  jnz     short loc_180020DD5
0x180020ddf  lea     rax, ds:2[rax*2]
0x180020de7  mov     dword ptr [rbp+40h+UserData.0Ch], r12d
0x180020deb  mov     [rbp+40h+UserData.Size], eax
0x180020dee  lea     rcx, [rbp+40h+var_50]
0x180020df2  test    r9d, r9d
0x180020df5  mov     [rbp+40h+UserData.Ptr], rcx
0x180020df9  mov     rcx, cs:g_etwHandle; RegHandle
0x180020e00  lea     r9, [rbp+40h+UserData]; UserData
0x180020e04  mov     r13d, 4
0x180020e0a  lea     rdx, V4_LUT_ELEMENTS; EventDescriptor
0x180020e11  mov     eax, r12d
0x180020e14  mov     [rbp+40h+var_98], r13
0x180020e18  setnz   al
0x180020e1b  mov     [rbp+40h+var_88], r13
0x180020e1f  mov     [rsp+140h+var_E8], eax
0x180020e23  test    r10d, r10d
0x180020e26  lea     rax, [rsp+140h+var_E8]
0x180020e2b  mov     [rbp+40h+var_78], r13
0x180020e2f  mov     [rbp+40h+var_A0], rax
0x180020e33  lea     r8d, [r13+2]; UserDataCount
0x180020e37  mov     eax, r12d
0x180020e3a  mov     [rbp+40h+var_68], r13
0x180020e3e  setnz   al
0x180020e41  mov     [rbp+40h+var_58], r13
0x180020e45  mov     [rsp+140h+var_E4], eax
0x180020e49  test    r11d, r11d
0x180020e4c  lea     rax, [rsp+140h+var_E4]
0x180020e51  mov     [rbp+40h+var_90], rax
0x180020e55  mov     eax, r12d
0x180020e58  setnz   al
0x180020e5b  test    r14d, r14d
0x180020e5e  mov     [rsp+140h+var_E0], eax
0x180020e62  lea     rax, [rsp+140h+var_E0]
0x180020e67  mov     [rbp+40h+var_80], rax
0x180020e6b  mov     eax, r12d
0x180020e6e  setnz   al
0x180020e71  test    r15d, r15d
0x180020e74  mov     [rsp+140h+var_DC], eax
0x180020e78  lea     rax, [rsp+140h+var_DC]
0x180020e7d  mov     [rbp+40h+var_70], rax
0x180020e81  mov     eax, r12d
0x180020e84  setnz   al
0x180020e87  mov     [rsp+140h+var_D8], eax
0x180020e8b  lea     rax, [rsp+140h+var_D8]
0x180020e90  mov     [rbp+40h+var_60], rax
0x180020e94  call    cs:__imp_EventWrite
0x180020e9a  mov     rcx, [rdi]; hProfile
0x180020e9d  lea     r9, [rsp+140h+var_F0]; pcbElement
0x180020ea2  xor     r8d, r8d; dwOffset
0x180020ea5  mov     [rsp+140h+var_120], r12; PVOID
0x180020eaa  mov     edx, esi; tag
0x180020eac  call    CMGetPartialProfileElement
0x180020eb1  test    eax, eax
0x180020eb3  jnz     loc_180020FB8
0x180020eb9  mov     ecx, [rsp+140h+var_D0+4]
0x180020ebd  test    ecx, ecx
0x180020ebf  jz      loc_180020FB3
0x180020ec5  cmp     [rdi+30h], r12b
0x180020ec9  jnz     short loc_180020ED4
0x180020ecb  mov     r14b, 0Ah
0x180020ece  cmp     [rdi+34h], r12b
0x180020ed2  jz      short loc_180020ED7
0x180020ed4  mov     r14b, 10h
0x180020ed7  mov     r9b, byte ptr [rsp+140h+var_D0]; int
0x180020edc  lea     rax, [rbx+10h]
0x180020ee0  mov     r8d, [rsp+140h+var_F0]; int
0x180020ee5  mov     edx, esi; int
0x180020ee7  mov     [rsp+140h+var_108], rax; __int64
0x180020eec  mov     [rsp+140h+var_110], r14b; char
0x180020ef1  mov     byte ptr [rsp+140h+dwOffset], 8; char
0x180020ef6  mov     [rsp+140h+var_120], rcx; dwOffset
0x180020efb  mov     rcx, [rdi]; int
0x180020efe  call    ExtractNestedCurves
0x180020f03  test    eax, eax
0x180020f05  jnz     loc_180020FB8
0x180020f0b  mov     r15d, 100h
0x180020f11  movzx   eax, r14b
0x180020f15  mov     [rbx+4], r15d
0x180020f19  mov     [rbx+8], eax
0x180020f1c  mov     ecx, [rsp+140h+var_D0+8]
0x180020f20  test    ecx, ecx
0x180020f22  jz      short loc_180020F59
0x180020f24  cmp     [rsp+140h+var_D0+0Ch], r12d
0x180020f29  jz      loc_180020FB3
0x180020f2f  cmp     byte ptr [rsp+140h+var_D0], 3
0x180020f34  jnz     short loc_180020FB3
0x180020f36  mov     r8d, [rsp+140h+var_F0]
0x180020f3b  lea     rax, [rbx+78h]
0x180020f3f  mov     r9d, ecx
0x180020f42  mov     [rsp+140h+var_120], rax; __int64
0x180020f47  mov     rcx, [rdi]; hProfile
0x180020f4a  mov     edx, esi; tag
0x180020f4c  call    ExtractMatrixWithOffsets
0x180020f51  test    eax, eax
0x180020f53  jnz     short loc_180020FB8
0x180020f55  mov     ecx, [rsp+140h+var_D0+8]
0x180020f59  mov     edx, [rsp+140h+var_D0+0Ch]
0x180020f5d  test    edx, edx
0x180020f5f  jz      short loc_180020FA0
0x180020f61  test    ecx, ecx
0x180020f63  jz      short loc_180020FB3
0x180020f65  mov     r9b, byte ptr [rsp+140h+var_D0]; int
0x180020f6a  lea     rax, [rbx+58h]
0x180020f6e  mov     r8d, [rsp+140h+var_F0]; int
0x180020f73  mov     rcx, [rdi]; int
0x180020f76  mov     [rsp+140h+var_108], rax; __int64
0x180020f7b  mov     [rsp+140h+var_110], 10h; char
0x180020f80  mov     byte ptr [rsp+140h+dwOffset], 8; char
0x180020f85  mov     [rsp+140h+var_120], rdx; dwOffset
0x180020f8a  mov     edx, esi; int
0x180020f8c  call    ExtractNestedCurves
0x180020f91  test    eax, eax
0x180020f93  jnz     short loc_180020FB8
0x180020f95  mov     [rbx+70h], r15d
0x180020f99  mov     dword ptr [rbx+74h], 10h
0x180020fa0  mov     r8d, [rbp+40h+var_C0]
0x180020fa4  test    r8d, r8d
0x180020fa7  jnz     short loc_180020FDF
0x180020fa9  mov     al, byte ptr [rsp+140h+var_D0]
0x180020fad  cmp     byte ptr [rsp+140h+var_D0+1], al
0x180020fb1  jz      short loc_18002102E
0x180020fb3  mov     eax, 7DBh
0x180020fb8  mov     rcx, [rbp+40h+var_40]
0x180020fbc  xor     rcx, rsp; StackCookie
0x180020fbf  call    __security_check_cookie
0x180020fc4  mov     rbx, [rsp+140h+arg_18]
0x180020fcc  add     rsp, 110h
0x180020fd3  pop     r15
0x180020fd5  pop     r14
0x180020fd7  pop     r13
0x180020fd9  pop     r12
0x180020fdb  pop     rdi
0x180020fdc  pop     rsi
0x180020fdd  pop     rbp
0x180020fde  retn
0x180020fdf  cmp     [rbp+40h+var_C0+4], r12d
0x180020fe3  jz      short loc_180020FB3
0x180020fe5  lea     rax, [rbx+3Ch]
0x180020fe9  mov     [rsp+140h+var_F8], rax; __int64
0x180020fee  lea     rdx, [rbx+38h]
0x180020ff2  mov     al, byte ptr [rsp+140h+var_D0+1]
0x180020ff6  lea     r9, [rbx+60h]
0x180020ffa  lea     rcx, [rbx+40h]
0x180020ffe  mov     [rsp+140h+var_100], rcx; __int64
0x180021003  mov     rcx, [rdi]; hProfile
0x180021006  mov     [rsp+140h+var_108], rdx; __int64
0x18002100b  mov     edx, esi; tag
0x18002100d  mov     qword ptr [rsp+140h+var_110], r9; __int64
0x180021012  mov     r9b, byte ptr [rsp+140h+var_D0]
0x180021017  mov     qword ptr [rsp+140h+dwOffset], r8; dwOffset
0x18002101c  mov     r8d, [rsp+140h+var_F0]
0x180021021  mov     byte ptr [rsp+140h+var_120], al; char
0x180021025  call    ExtractAtoBStyleClut
0x18002102a  test    eax, eax
0x18002102c  jnz     short loc_180020FB8
0x18002102e  mov     eax, [rsp+140h+var_F0]
0x180021032  lea     r8, [rsp+140h+var_D0]
0x180021037  mov     r9d, esi
0x18002103a  mov     dword ptr [rsp+140h+var_120], eax
0x18002103e  mov     rdx, rdi
0x180021041  mov     rcx, rbx
0x180021044  call    ExtractACurvesFromLutBToA
0x180021049  test    eax, eax
0x18002104b  jnz     loc_180020FB8
0x180021051  mov     [rbx], r13d
0x180021054  jmp     loc_180020FB8
```
