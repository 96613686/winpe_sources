# ExtractAll_MFT_LutsFromLutAToB

- ea: `0x180019f50`
- end: `0x18001a308`
- name: `ExtractAll_MFT_LutsFromLutAToB`
- size: `952`
- prototype: `__int64 __fastcall(_DWORD *, HPROFILE *, TAGTYPE)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005838`

## callees

- `0x180019f50`
- `0x18001a358`
- `0x18001a490`
- `0x18001a7d0`
- `0x180021348`
- `0x1800213cc`
- `0x18003d040`

## import_xrefs

- `mscms!GetColorProfileElement` at `0x180019fe2`
- `mscms!GetColorProfileElement` at `0x18001a20a`
- `mscms!GetColorProfileElement` at `0x180019fe2`
- `mscms!GetColorProfileElement` at `0x18001a20a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019fbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a1e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019fbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a1e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a214`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001a1d3`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001a1d3`

## pseudocode

```c
__int64 __fastcall ExtractAll_MFT_LutsFromLutAToB(_DWORD *a1, HPROFILE *a2, TAGTYPE a3)
{
  HPROFILE v3; // rbx
  __int64 result; // rax
  unsigned int v8; // ecx
  unsigned int v9; // eax
  signed int v10; // edx
  int v11; // r8d
  int v12; // r9d
  int v13; // r10d
  int v14; // r11d
  int v15; // ebx
  __int64 v16; // rcx
  char *v17; // rax
  __int64 v18; // rax
  HPROFILE v19; // rbx
  DWORD v20; // [rsp+30h] [rbp-99h] BYREF
  WINBOOL pbReference; // [rsp+38h] [rbp-91h] BYREF
  DWORD pcbElement; // [rsp+40h] [rbp-89h] BYREF
  BOOL v23; // [rsp+44h] [rbp-85h] BYREF
  BOOL v24; // [rsp+48h] [rbp-81h] BYREF
  BOOL v25; // [rsp+4Ch] [rbp-7Dh] BYREF
  BOOL v26; // [rsp+50h] [rbp-79h] BYREF
  BOOL v27; // [rsp+54h] [rbp-75h] BYREF
  __int128 pElement; // [rsp+58h] [rbp-71h] BYREF
  __int64 v29; // [rsp+68h] [rbp-61h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-59h] BYREF
  BOOL *v31; // [rsp+80h] [rbp-49h]
  __int64 v32; // [rsp+88h] [rbp-41h]
  BOOL *v33; // [rsp+90h] [rbp-39h]
  __int64 v34; // [rsp+98h] [rbp-31h]
  BOOL *v35; // [rsp+A0h] [rbp-29h]
  __int64 v36; // [rsp+A8h] [rbp-21h]
  BOOL *v37; // [rsp+B0h] [rbp-19h]
  __int64 v38; // [rsp+B8h] [rbp-11h]
  BOOL *v39; // [rsp+C0h] [rbp-9h]
  __int64 v40; // [rsp+C8h] [rbp-1h]
  _WORD v41[8]; // [rsp+D0h] [rbp+7h] BYREF

  v3 = *a2;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  pElement = 0;
  v29 = 0;
  v20 = 0;
  pbReference = 0;
  pcbElement = 24;
  SetLastError(0);
  if ( !GetColorProfileElement(v3, a3, 8u, &pcbElement, &pElement, &pbReference) )
    return 2012;
  if ( pcbElement != 24 )
    return 2011;
  v8 = (unsigned __int8)pElement;
  v9 = BYTE1(pElement);
  a1[12] = (unsigned __int8)pElement;
  a1[13] = v9;
  if ( !v8 || !v9 || v8 > 8 || v9 > 8 )
    return 2011;
  v10 = 0;
  v11 = BYTE7(pElement) | ((BYTE6(pElement) | ((BYTE5(pElement) | (BYTE4(pElement) << 8)) << 8)) << 8);
  pbReference = a3;
  DWORD1(pElement) = v11;
  v12 = BYTE11(pElement) | ((BYTE10(pElement) | ((BYTE9(pElement) | (BYTE8(pElement) << 8)) << 8)) << 8);
  DWORD2(pElement) = v12;
  v13 = HIBYTE(pElement) | ((BYTE14(pElement) | ((BYTE13(pElement) | (BYTE12(pElement) << 8)) << 8)) << 8);
  HIDWORD(pElement) = v13;
  v14 = BYTE3(v29) | ((BYTE2(v29) | ((BYTE1(v29) | ((unsigned __int8)v29 << 8)) << 8)) << 8);
  LODWORD(v29) = v14;
  v15 = HIBYTE(v29) | ((BYTE6(v29) | ((BYTE5(v29) | (BYTE4(v29) << 8)) << 8)) << 8);
  HIDWORD(v29) = v15;
  do
  {
    v16 = v10;
    v17 = (char *)&pbReference - v10++ + 3;
    v41[v16] = *v17;
  }
  while ( (unsigned int)v10 < 4 );
  v41[4] = 0;
  v18 = -1;
  do
    ++v18;
  while ( v41[v18] );
  UserData.Reserved = 0;
  UserData.Size = 2 * v18 + 2;
  UserData.Ptr = (ULONGLONG)v41;
  v32 = 4;
  v34 = 4;
  v23 = v11 != 0;
  v36 = 4;
  v31 = &v23;
  v38 = 4;
  v40 = 4;
  v24 = v12 != 0;
  v33 = &v24;
  v25 = v13 != 0;
  v35 = &v25;
  v26 = v14 != 0;
  v37 = &v26;
  v27 = v15 != 0;
  v39 = &v27;
  EventWrite(g_etwHandle, &V4_LUT_ELEMENTS, 6u, &UserData);
  v19 = *a2;
  pbReference = 0;
  SetLastError(0);
  v20 = 0;
  if ( !GetColorProfileElement(v19, a3, 0, &v20, 0, &pbReference) && GetLastError() != 122 )
    return 2012;
  result = ExtractClutFromLutAToB(a1, a2, &pElement, a3, v20);
  if ( (_DWORD)result )
    return result;
  result = ExtractBCurvesFromLutAToB(a1, a2, &pElement, a3, v20);
  if ( (_DWORD)result )
    return result;
  if ( DWORD2(pElement) )
  {
    if ( HIDWORD(pElement) && BYTE1(pElement) == 3 )
    {
      result = ExtractMatrixWithOffsets(*a2, a3, (__int64)(a1 + 30));
      if ( (_DWORD)result )
        return result;
      goto LABEL_20;
    }
    return 2011;
  }
LABEL_20:
  result = ExtractMCurvesFromLutAToB(a1, a2, &pElement, a3, v20);
  if ( !(_DWORD)result )
  {
    result = ExtractACurvesFromLutAToB(a1, a2, &pElement, a3, v20);
    if ( !(_DWORD)result )
      *a1 = 3;
  }
  return result;
}

```

## disassembly

```asm
0x180019f50  push    rbp
0x180019f52  push    rbx
0x180019f53  push    rsi
0x180019f54  push    rdi
0x180019f55  push    r12
0x180019f57  push    r14
0x180019f59  push    r15
0x180019f5b  lea     rbp, [rsp-27h]
0x180019f60  sub     rsp, 0F0h
0x180019f67  mov     rax, cs:__security_cookie
0x180019f6e  xor     rax, rsp
0x180019f71  mov     [rbp+57h+var_40], rax
0x180019f75  mov     rbx, [rdx]
0x180019f78  xor     r15d, r15d
0x180019f7b  mov     rdi, rcx
0x180019f7e  mov     [rsp+120h+var_DC], r15d
0x180019f83  xorps   xmm0, xmm0
0x180019f86  mov     [rsp+120h+var_D8], r15d
0x180019f8b  xor     eax, eax
0x180019f8d  mov     [rbp+57h+var_D4], r15d
0x180019f91  xor     ecx, ecx; dwErrCode
0x180019f93  mov     [rbp+57h+var_D0], r15d
0x180019f97  mov     [rbp+57h+var_CC], r15d
0x180019f9b  mov     esi, r8d
0x180019f9e  movups  [rbp+57h+var_C8], xmm0
0x180019fa2  mov     [rbp+57h+var_B8], rax
0x180019fa6  mov     r14, rdx
0x180019fa9  mov     [rsp+120h+var_F0], r15d
0x180019fae  mov     [rsp+120h+var_E8], r15d
0x180019fb3  mov     [rsp+120h+pcbElement], 18h
0x180019fbb  call    cs:__imp_SetLastError
0x180019fc1  lea     rax, [rsp+120h+var_E8]
0x180019fc6  mov     edx, esi; tag
0x180019fc8  mov     [rsp+120h+pbReference], rax; pbReference
0x180019fcd  lea     r9, [rsp+120h+pcbElement]; pcbElement
0x180019fd2  lea     rax, [rbp+57h+var_C8]
0x180019fd6  mov     rcx, rbx; hProfile
0x180019fd9  lea     r8d, [r15+8]; dwOffset
0x180019fdd  mov     [rsp+120h+pElement], rax; pElement
0x180019fe2  call    cs:__imp_GetColorProfileElement
0x180019fe8  test    eax, eax
0x180019fea  jz      loc_18001A2E5
0x180019ff0  cmp     [rsp+120h+pcbElement], 18h
0x180019ff5  jz      short loc_18001A001
0x180019ff7  mov     eax, 7DBh
0x180019ffc  jmp     loc_18001A2EA
0x18001a001  movzx   ecx, byte ptr [rbp+57h+var_C8]
0x18001a005  movzx   eax, byte ptr [rbp+57h+var_C8+1]
0x18001a009  mov     [rdi+30h], ecx
0x18001a00c  mov     [rdi+34h], eax
0x18001a00f  test    ecx, ecx
0x18001a011  jz      short loc_180019FF7
0x18001a013  test    eax, eax
0x18001a015  jz      short loc_180019FF7
0x18001a017  cmp     ecx, 8
0x18001a01a  ja      short loc_180019FF7
0x18001a01c  cmp     eax, 8
0x18001a01f  ja      short loc_180019FF7
0x18001a021  movzx   eax, byte ptr [rbp+57h+var_C8+5]
0x18001a025  mov     edx, r15d
0x18001a028  movzx   r8d, byte ptr [rbp+57h+var_C8+4]
0x18001a02d  mov     r12d, 4
0x18001a033  movzx   r9d, byte ptr [rbp+57h+var_C8+8]
0x18001a038  movzx   r10d, byte ptr [rbp+57h+var_C8+0Ch]
0x18001a03d  movzx   r11d, byte ptr [rbp+57h+var_B8]
0x18001a042  movzx   ebx, byte ptr [rbp+57h+var_B8+4]
0x18001a046  shl     r8d, 8
0x18001a04a  or      r8d, eax
0x18001a04d  shl     r9d, 8
0x18001a051  movzx   eax, byte ptr [rbp+57h+var_C8+6]
0x18001a055  shl     r10d, 8
0x18001a059  shl     r11d, 8
0x18001a05d  shl     r8d, 8
0x18001a061  or      r8d, eax
0x18001a064  shl     ebx, 8
0x18001a067  movzx   eax, byte ptr [rbp+57h+var_C8+7]
0x18001a06b  shl     r8d, 8
0x18001a06f  or      r8d, eax
0x18001a072  mov     [rsp+120h+var_E8], esi
0x18001a076  movzx   eax, byte ptr [rbp+57h+var_C8+9]
0x18001a07a  or      r9d, eax
0x18001a07d  mov     dword ptr [rbp+57h+var_C8+4], r8d
0x18001a081  movzx   eax, byte ptr [rbp+57h+var_C8+0Ah]
0x18001a085  shl     r9d, 8
0x18001a089  or      r9d, eax
0x18001a08c  movzx   eax, byte ptr [rbp+57h+var_C8+0Bh]
0x18001a090  shl     r9d, 8
0x18001a094  or      r9d, eax
0x18001a097  movzx   eax, byte ptr [rbp+57h+var_C8+0Dh]
0x18001a09b  or      r10d, eax
0x18001a09e  mov     dword ptr [rbp+57h+var_C8+8], r9d
0x18001a0a2  movzx   eax, byte ptr [rbp+57h+var_C8+0Eh]
0x18001a0a6  shl     r10d, 8
0x18001a0aa  or      r10d, eax
0x18001a0ad  movzx   eax, byte ptr [rbp+57h+var_C8+0Fh]
0x18001a0b1  shl     r10d, 8
0x18001a0b5  or      r10d, eax
0x18001a0b8  movzx   eax, byte ptr [rbp+57h+var_B8+1]
0x18001a0bc  or      r11d, eax
0x18001a0bf  mov     dword ptr [rbp+57h+var_C8+0Ch], r10d
0x18001a0c3  movzx   eax, byte ptr [rbp+57h+var_B8+2]
0x18001a0c7  shl     r11d, 8
0x18001a0cb  or      r11d, eax
0x18001a0ce  movzx   eax, byte ptr [rbp+57h+var_B8+3]
0x18001a0d2  shl     r11d, 8
0x18001a0d6  or      r11d, eax
0x18001a0d9  movzx   eax, byte ptr [rbp+57h+var_B8+5]
0x18001a0dd  or      ebx, eax
0x18001a0df  mov     dword ptr [rbp+57h+var_B8], r11d
0x18001a0e3  movzx   eax, byte ptr [rbp+57h+var_B8+6]
0x18001a0e7  shl     ebx, 8
0x18001a0ea  or      ebx, eax
0x18001a0ec  movzx   eax, byte ptr [rbp+57h+var_B8+7]
0x18001a0f0  shl     ebx, 8
0x18001a0f3  or      ebx, eax
0x18001a0f5  mov     dword ptr [rbp+57h+var_B8+4], ebx
0x18001a0f8  movsxd  rcx, edx
0x18001a0fb  lea     rax, [rsp+120h+var_E8+3]
0x18001a100  sub     rax, rcx
0x18001a103  inc     edx
0x18001a105  movsx   eax, byte ptr [rax]
0x18001a108  mov     [rbp+rcx*2+57h+var_50], ax
0x18001a10d  cmp     edx, r12d
0x18001a110  jb      short loc_18001A0F8
0x18001a112  mov     [rbp+57h+var_48], r15w
0x18001a117  lea     rcx, [rbp+57h+var_50]
0x18001a11b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a11f  inc     rax
0x18001a122  cmp     [rcx+rax*2], r15w
0x18001a127  jnz     short loc_18001A11F
0x18001a129  lea     rax, ds:2[rax*2]
0x18001a131  mov     dword ptr [rbp+57h+UserData.0Ch], r15d
0x18001a135  mov     [rbp+57h+UserData.Size], eax
0x18001a138  lea     rcx, [rbp+57h+var_50]
0x18001a13c  test    r8d, r8d
0x18001a13f  mov     [rbp+57h+UserData.Ptr], rcx
0x18001a143  mov     rcx, cs:g_etwHandle; RegHandle
0x18001a14a  lea     rdx, V4_LUT_ELEMENTS; EventDescriptor
0x18001a151  mov     eax, r15d
0x18001a154  mov     [rbp+57h+var_98], r12
0x18001a158  setnz   al
0x18001a15b  mov     [rbp+57h+var_88], r12
0x18001a15f  mov     [rsp+120h+var_DC], eax
0x18001a163  test    r9d, r9d
0x18001a166  lea     rax, [rsp+120h+var_DC]
0x18001a16b  mov     [rbp+57h+var_78], r12
0x18001a16f  mov     [rbp+57h+var_A0], rax
0x18001a173  lea     r9, [rbp+57h+UserData]; UserData
0x18001a177  mov     eax, r15d
0x18001a17a  mov     [rbp+57h+var_68], r12
0x18001a17e  setnz   al
0x18001a181  mov     [rbp+57h+var_58], r12
0x18001a185  mov     [rsp+120h+var_D8], eax
0x18001a189  test    r10d, r10d
0x18001a18c  lea     rax, [rsp+120h+var_D8]
0x18001a191  mov     r8d, 6; UserDataCount
0x18001a197  mov     [rbp+57h+var_90], rax
0x18001a19b  mov     eax, r15d
0x18001a19e  setnz   al
0x18001a1a1  test    r11d, r11d
0x18001a1a4  mov     [rbp+57h+var_D4], eax
0x18001a1a7  lea     rax, [rbp+57h+var_D4]
0x18001a1ab  mov     [rbp+57h+var_80], rax
0x18001a1af  mov     eax, r15d
0x18001a1b2  setnz   al
0x18001a1b5  test    ebx, ebx
0x18001a1b7  mov     [rbp+57h+var_D0], eax
0x18001a1ba  lea     rax, [rbp+57h+var_D0]
0x18001a1be  mov     [rbp+57h+var_70], rax
0x18001a1c2  mov     eax, r15d
0x18001a1c5  setnz   al
0x18001a1c8  mov     [rbp+57h+var_CC], eax
0x18001a1cb  lea     rax, [rbp+57h+var_CC]
0x18001a1cf  mov     [rbp+57h+var_60], rax
0x18001a1d3  call    cs:__imp_EventWrite
0x18001a1d9  mov     rbx, [r14]
0x18001a1dc  xor     ecx, ecx; dwErrCode
0x18001a1de  mov     [rsp+120h+var_E8], r15d
0x18001a1e3  call    cs:__imp_SetLastError
0x18001a1e9  lea     rax, [rsp+120h+var_E8]
0x18001a1ee  mov     [rsp+120h+var_F0], r15d
0x18001a1f3  mov     [rsp+120h+pbReference], rax; pbReference
0x18001a1f8  lea     r9, [rsp+120h+var_F0]; pcbElement
0x18001a1fd  xor     r8d, r8d; dwOffset
0x18001a200  mov     [rsp+120h+pElement], r15; pElement
0x18001a205  mov     edx, esi; tag
0x18001a207  mov     rcx, rbx; hProfile
0x18001a20a  call    cs:__imp_GetColorProfileElement
0x18001a210  test    eax, eax
0x18001a212  jnz     short loc_18001A223
0x18001a214  call    cs:__imp_GetLastError
0x18001a21a  cmp     eax, 7Ah ; 'z'
0x18001a21d  jnz     loc_18001A2E5
0x18001a223  mov     eax, [rsp+120h+var_F0]
0x18001a227  lea     r8, [rbp+57h+var_C8]
0x18001a22b  mov     r9d, esi
0x18001a22e  mov     dword ptr [rsp+120h+pElement], eax
0x18001a232  mov     rdx, r14
0x18001a235  mov     rcx, rdi
0x18001a238  call    ExtractClutFromLutAToB
0x18001a23d  test    eax, eax
0x18001a23f  jnz     loc_18001A2EA
0x18001a245  mov     eax, [rsp+120h+var_F0]
0x18001a249  lea     r8, [rbp+57h+var_C8]
0x18001a24d  mov     r9d, esi
0x18001a250  mov     dword ptr [rsp+120h+pElement], eax
0x18001a254  mov     rdx, r14
0x18001a257  mov     rcx, rdi
0x18001a25a  call    ExtractBCurvesFromLutAToB
0x18001a25f  test    eax, eax
0x18001a261  jnz     loc_18001A2EA
0x18001a267  mov     ecx, dword ptr [rbp+57h+var_C8+8]
0x18001a26a  test    ecx, ecx
0x18001a26c  jz      short loc_18001A2A1
0x18001a26e  cmp     dword ptr [rbp+57h+var_C8+0Ch], r15d
0x18001a272  jz      loc_180019FF7
0x18001a278  cmp     byte ptr [rbp+57h+var_C8+1], 3
0x18001a27c  jnz     loc_180019FF7
0x18001a282  mov     r8d, [rsp+120h+var_F0]
0x18001a287  lea     rax, [rdi+78h]
0x18001a28b  mov     r9d, ecx
0x18001a28e  mov     [rsp+120h+pElement], rax; __int64
0x18001a293  mov     rcx, [r14]; hProfile
0x18001a296  mov     edx, esi; tag
0x18001a298  call    ExtractMatrixWithOffsets
0x18001a29d  test    eax, eax
0x18001a29f  jnz     short loc_18001A2EA
0x18001a2a1  mov     eax, [rsp+120h+var_F0]
0x18001a2a5  lea     r8, [rbp+57h+var_C8]
0x18001a2a9  mov     r9d, esi
0x18001a2ac  mov     dword ptr [rsp+120h+pElement], eax
0x18001a2b0  mov     rdx, r14
0x18001a2b3  mov     rcx, rdi
0x18001a2b6  call    ExtractMCurvesFromLutAToB
0x18001a2bb  test    eax, eax
0x18001a2bd  jnz     short loc_18001A2EA
0x18001a2bf  mov     eax, [rsp+120h+var_F0]
0x18001a2c3  lea     r8, [rbp+57h+var_C8]
0x18001a2c7  mov     r9d, esi
0x18001a2ca  mov     dword ptr [rsp+120h+pElement], eax
0x18001a2ce  mov     rdx, r14
0x18001a2d1  mov     rcx, rdi
0x18001a2d4  call    ExtractACurvesFromLutAToB
0x18001a2d9  test    eax, eax
0x18001a2db  jnz     short loc_18001A2EA
0x18001a2dd  mov     dword ptr [rdi], 3
0x18001a2e3  jmp     short loc_18001A2EA
0x18001a2e5  mov     eax, 7DCh
0x18001a2ea  mov     rcx, [rbp+57h+var_40]
0x18001a2ee  xor     rcx, rsp; StackCookie
0x18001a2f1  call    __security_check_cookie
0x18001a2f6  add     rsp, 0F0h
0x18001a2fd  pop     r15
0x18001a2ff  pop     r14
0x18001a301  pop     r12
0x18001a303  pop     rdi
0x18001a304  pop     rsi
0x18001a305  pop     rbx
0x18001a306  pop     rbp
0x18001a307  retn
```
