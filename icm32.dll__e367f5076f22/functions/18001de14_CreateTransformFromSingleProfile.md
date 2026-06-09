# CreateTransformFromSingleProfile

- ea: `0x18001de14`
- end: `0x18001e1e5`
- name: `CreateTransformFromSingleProfile`
- size: `977`
- prototype: `__int64 __fastcall(HPROFILE hProfile, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x180005974`

## callees

- `0x1800042e0`
- `0x180006008`
- `0x18000604c`
- `0x1800060f0`
- `0x180006f00`
- `0x180007130`
- `0x180018abc`
- `0x180018b68`
- `0x18001de14`
- `0x180021060`
- `0x1800211ec`
- `0x18002145c`
- `0x180021554`
- `0x18002167c`
- `0x180021b38`
- `0x18003d00e`
- `0x18003d040`

## import_xrefs

- `mscms!IsColorProfileTagPresent` at `0x18001dec9`
- `mscms!IsColorProfileTagPresent` at `0x18001dec9`

## pseudocode

```c
__int64 __fastcall CreateTransformFromSingleProfile(HPROFILE hProfile, __int64 a2)
{
  char *v4; // rsi
  unsigned int MatrixFromProfile; // ebx
  int v6; // eax
  char *v7; // rax
  __int64 v8; // rdx
  unsigned int v9; // r10d
  __int64 v10; // rdx
  unsigned int v11; // r8d
  int v12; // edx
  bool v14; // zf
  unsigned int ElutFromLut16; // eax
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int16 v24[2]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcbElement; // [rsp+34h] [rbp-CCh] BYREF
  WINBOOL pbPresent; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v27; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD v28[4]; // [rsp+40h] [rbp-C0h] BYREF
  HPROFILE v29; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+78h] [rbp-88h]
  __int16 v32; // [rsp+80h] [rbp-80h]
  char v33; // [rsp+82h] [rbp-7Eh]
  char v34; // [rsp+84h] [rbp-7Ch]
  _OWORD v35[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v36; // [rsp+D0h] [rbp-30h]
  __int128 v37; // [rsp+E0h] [rbp-20h]
  __int128 v38; // [rsp+F0h] [rbp-10h]
  __int128 v39; // [rsp+100h] [rbp+0h]
  __int128 v40; // [rsp+110h] [rbp+10h]
  __int128 v41; // [rsp+120h] [rbp+20h]
  __int64 v42; // [rsp+130h] [rbp+30h] BYREF
  char v43[8]; // [rsp+140h] [rbp+40h] BYREF
  int v44; // [rsp+148h] [rbp+48h]
  int v45; // [rsp+150h] [rbp+50h]
  int v46; // [rsp+154h] [rbp+54h]

  memset_0(v35, 0, 0x90u);
  memset_0(&v29, 0, 0x50u);
  v24[0] = 0;
  v28[0] = 0;
  v4 = 0;
  v27 = 0;
  memset_0(v43, 0, 0x80u);
  v42 = 0;
  pcbElement = 0;
  MatrixFromProfile = CMGetProfileHeader(hProfile, v43);
  if ( !MatrixFromProfile )
  {
    pbPresent = 0;
    IsColorProfileTagPresent(hProfile, 0x41324230u, &pbPresent);
    if ( !(_BYTE)pbPresent )
      goto LABEL_3;
    v6 = v44;
    v30 = v44;
    *(_DWORD *)(a2 + 308) = v44;
    *(_DWORD *)(a2 + 312) = v6;
    *(_DWORD *)(a2 + 292) = v45;
    *(_DWORD *)(a2 + 296) = v46;
    v29 = hProfile;
    pcbElement = 8;
    MatrixFromProfile = CMGetPartialProfileElement(hProfile, 0x41324230u, 0, &pcbElement, &v42);
    if ( MatrixFromProfile )
      goto LABEL_15;
    if ( pcbElement != 8 )
      goto LABEL_3;
    LODWORD(v42) = BYTE3(v42) | ((BYTE2(v42) | ((BYTE1(v42) | ((unsigned __int8)v42 << 8)) << 8)) << 8);
    if ( (_DWORD)v42 == 1832993312 )
    {
LABEL_14:
      MatrixFromProfile = 1;
      goto LABEL_15;
    }
    if ( (unsigned int)(v42 - 1835430961) > 1 )
    {
LABEL_3:
      MatrixFromProfile = 2011;
      goto LABEL_15;
    }
    MatrixFromProfile = CMGetPartialProfileElement(hProfile, 0x41324230u, 0, v28, 0);
    if ( !MatrixFromProfile )
    {
      v27 = 52;
      v7 = (char *)SmartNewPtr(52, v24);
      MatrixFromProfile = v24[0];
      v4 = v7;
      if ( !v24[0] )
      {
        MatrixFromProfile = CMGetPartialProfileElement(hProfile, 0x41324230u, 0, &v27, v7);
        if ( !MatrixFromProfile )
        {
          SwapLongOffset(v4, 0, 4);
          SwapShortOffset(v4 + 48, v8, 2);
          SwapShortOffset(v4 + 50, v10, v9);
          v11 = (unsigned __int8)v4[8];
          v12 = (unsigned __int8)v4[10];
          *(_QWORD *)&v36 = __PAIR64__((unsigned __int8)v4[9], v11);
          DWORD2(v36) = v12;
          if ( v11 == 3 )
          {
            if ( ((v12 - 16) & 0xFFFFFFEF) != 0 )
              goto LABEL_14;
            if ( v46 == 1482250784 )
            {
              MatrixFromProfile = GetMatrixFromProfile(v35, &v29, 1093812784);
              if ( MatrixFromProfile )
                goto LABEL_15;
              if ( (_QWORD)v38 && !(unsigned __int8)MatrixIsCloseToIdentity() )
                goto LABEL_14;
            }
          }
          else if ( v11 == 4 && ((v12 - 8) & 0xFFFFFFF7) != 0 )
          {
            goto LABEL_14;
          }
          v14 = *(_DWORD *)v4 == 1835430962;
          v31 = 0;
          v33 = 0;
          if ( v14 )
          {
            v32 = 256;
            v34 = 1;
            MatrixFromProfile = ExtractAlutFromLut16(v35, (__int64)&v29, (__int64)(v4 + 8), 0x41324230u);
            if ( MatrixFromProfile )
              goto LABEL_15;
            MatrixFromProfile = ExtractXlutFromLut16((__int64)v35, (__int64)&v29, (__int64)(v4 + 8), 0x41324230u);
            if ( MatrixFromProfile )
              goto LABEL_15;
            ElutFromLut16 = ExtractElutFromLut16(v35, (__int64)&v29, (__int64)(v4 + 8), 0x41324230u);
          }
          else
          {
            v34 = 0;
            v32 = 0;
            MatrixFromProfile = ExtractAlutFromLut8(v35, &v29, 1093812784);
            if ( MatrixFromProfile )
              goto LABEL_15;
            MatrixFromProfile = ExtractXlutFromLut8(v35, &v29, 1093812784);
            if ( MatrixFromProfile )
              goto LABEL_15;
            ElutFromLut16 = ExtractElutFromLut8(v35, &v29, 1093812784);
          }
          MatrixFromProfile = ElutFromLut16;
          if ( !ElutFromLut16 )
          {
            v16 = v35[1];
            *(_OWORD *)a2 = v35[0];
            v17 = v35[2];
            *(_OWORD *)(a2 + 16) = v16;
            v18 = v36;
            *(_OWORD *)(a2 + 32) = v17;
            v19 = v37;
            *(_OWORD *)(a2 + 48) = v18;
            v20 = v38;
            *(_OWORD *)(a2 + 64) = v19;
            v21 = v39;
            *(_OWORD *)(a2 + 80) = v20;
            v22 = v40;
            *(_OWORD *)(a2 + 96) = v21;
            v23 = v41;
            *(_OWORD *)(a2 + 112) = v22;
            *(_OWORD *)(a2 + 128) = v23;
          }
        }
      }
    }
  }
LABEL_15:
  DisposeIfPtr(v4);
  return MatrixFromProfile;
}

```

## disassembly

```asm
0x18001de14  mov     [rsp-8+arg_10], rbx
0x18001de19  mov     [rsp-8+arg_18], rsi
0x18001de1e  push    rbp
0x18001de1f  push    rdi
0x18001de20  push    r12
0x18001de22  push    r14
0x18001de24  push    r15
0x18001de26  lea     rbp, [rsp-0D0h]
0x18001de2e  sub     rsp, 1D0h
0x18001de35  mov     rax, cs:__security_cookie
0x18001de3c  xor     rax, rsp
0x18001de3f  mov     [rbp+0F0h+var_30], rax
0x18001de46  mov     rdi, rdx
0x18001de49  mov     r14, rcx
0x18001de4c  xor     edx, edx; Val
0x18001de4e  lea     rcx, [rbp+0F0h+var_150]; void *
0x18001de52  mov     r8d, 90h; Size
0x18001de58  call    memset_0
0x18001de5d  xor     edx, edx; Val
0x18001de5f  lea     rcx, [rsp+1F0h+var_1A0]; void *
0x18001de64  lea     r8d, [rdx+50h]; Size
0x18001de68  call    memset_0
0x18001de6d  xor     r15d, r15d
0x18001de70  lea     rcx, [rbp+0F0h+var_B0]; void *
0x18001de74  xor     edx, edx; Val
0x18001de76  mov     [rsp+1F0h+var_1C0], r15w
0x18001de7c  mov     r8d, 80h; Size
0x18001de82  mov     [rsp+1F0h+var_1B0], r15d
0x18001de87  mov     esi, r15d
0x18001de8a  mov     [rsp+1F0h+var_1B4], r15d
0x18001de8f  call    memset_0
0x18001de94  lea     rdx, [rbp+0F0h+var_B0]
0x18001de98  mov     [rbp+0F0h+var_C0], r15
0x18001de9c  mov     rcx, r14
0x18001de9f  mov     [rsp+1F0h+pcbElement], r15d
0x18001dea4  call    CMGetProfileHeader
0x18001dea9  mov     ebx, eax
0x18001deab  test    eax, eax
0x18001dead  jnz     loc_18001E04F
0x18001deb3  mov     r12d, 41324230h
0x18001deb9  mov     [rsp+1F0h+pbPresent], r15d
0x18001debe  mov     edx, r12d; tag
0x18001dec1  lea     r8, [rsp+1F0h+pbPresent]; pbPresent
0x18001dec6  mov     rcx, r14; hProfile
0x18001dec9  call    cs:__imp_IsColorProfileTagPresent
0x18001decf  cmp     byte ptr [rsp+1F0h+pbPresent], r15b
0x18001ded4  jnz     short loc_18001DEE0
0x18001ded6  mov     ebx, 7DBh
0x18001dedb  jmp     loc_18001E04F
0x18001dee0  mov     eax, [rbp+0F0h+var_A8]
0x18001dee3  lea     r9, [rsp+1F0h+pcbElement]; pcbElement
0x18001dee8  mov     [rsp+1F0h+var_198], eax
0x18001deec  xor     r8d, r8d; dwOffset
0x18001deef  mov     [rdi+134h], eax
0x18001def5  mov     edx, r12d; tag
0x18001def8  mov     [rdi+138h], eax
0x18001defe  mov     rcx, r14; hProfile
0x18001df01  mov     eax, [rbp+0F0h+var_A0]
0x18001df04  mov     [rdi+124h], eax
0x18001df0a  mov     eax, [rbp+0F0h+var_9C]
0x18001df0d  mov     [rdi+128h], eax
0x18001df13  lea     rax, [rbp+0F0h+var_C0]
0x18001df17  mov     [rsp+1F0h+var_1D0], rax; PVOID
0x18001df1c  mov     [rsp+1F0h+var_1A0], r14
0x18001df21  mov     [rsp+1F0h+pcbElement], 8
0x18001df29  call    CMGetPartialProfileElement
0x18001df2e  mov     ebx, eax
0x18001df30  test    eax, eax
0x18001df32  jnz     loc_18001E04F
0x18001df38  cmp     [rsp+1F0h+pcbElement], 8
0x18001df3d  jnz     short loc_18001DED6
0x18001df3f  movzx   eax, byte ptr [rbp+0F0h+var_C0+1]
0x18001df43  movzx   ecx, byte ptr [rbp+0F0h+var_C0]
0x18001df47  shl     ecx, 8
0x18001df4a  or      ecx, eax
0x18001df4c  movzx   eax, byte ptr [rbp+0F0h+var_C0+2]
0x18001df50  shl     ecx, 8
0x18001df53  or      ecx, eax
0x18001df55  movzx   eax, byte ptr [rbp+0F0h+var_C0+3]
0x18001df59  shl     ecx, 8
0x18001df5c  or      ecx, eax
0x18001df5e  mov     dword ptr [rbp+0F0h+var_C0], ecx
0x18001df61  sub     ecx, 6D414220h
0x18001df67  jz      loc_18001E04A
0x18001df6d  sub     ecx, 253211h
0x18001df73  jz      short loc_18001DF7E
0x18001df75  cmp     ecx, 1
0x18001df78  jnz     loc_18001DED6
0x18001df7e  lea     r9, [rsp+1F0h+var_1B0]; pcbElement
0x18001df83  mov     [rsp+1F0h+var_1D0], r15; PVOID
0x18001df88  xor     r8d, r8d; dwOffset
0x18001df8b  mov     edx, r12d; tag
0x18001df8e  mov     rcx, r14; hProfile
0x18001df91  call    CMGetPartialProfileElement
0x18001df96  mov     ebx, eax
0x18001df98  test    eax, eax
0x18001df9a  jnz     loc_18001E04F
0x18001dfa0  lea     ecx, [rax+34h]
0x18001dfa3  lea     rdx, [rsp+1F0h+var_1C0]
0x18001dfa8  mov     [rsp+1F0h+var_1B4], ecx
0x18001dfac  call    SmartNewPtr
0x18001dfb1  movsx   ebx, [rsp+1F0h+var_1C0]
0x18001dfb6  mov     rsi, rax
0x18001dfb9  test    ebx, ebx
0x18001dfbb  jnz     loc_18001E04F
0x18001dfc1  lea     r9, [rsp+1F0h+var_1B4]; pcbElement
0x18001dfc6  mov     [rsp+1F0h+var_1D0], rax; PVOID
0x18001dfcb  xor     r8d, r8d; dwOffset
0x18001dfce  mov     edx, r12d; tag
0x18001dfd1  mov     rcx, r14; hProfile
0x18001dfd4  call    CMGetPartialProfileElement
0x18001dfd9  mov     ebx, eax
0x18001dfdb  test    eax, eax
0x18001dfdd  jnz     short loc_18001E04F
0x18001dfdf  xor     edx, edx
0x18001dfe1  lea     r8d, [rax+4]
0x18001dfe5  mov     rcx, rsi
0x18001dfe8  call    SwapLongOffset
0x18001dfed  lea     r10d, [rbx+2]
0x18001dff1  mov     r8d, r10d
0x18001dff4  lea     rcx, [rsi+30h]
0x18001dff8  call    SwapShortOffset
0x18001dffd  lea     rcx, [rsi+32h]
0x18001e001  mov     r8d, r10d
0x18001e004  call    SwapShortOffset
0x18001e009  movzx   eax, byte ptr [rsi+9]
0x18001e00d  lea     r14, [rsi+8]
0x18001e011  movzx   r8d, byte ptr [r14]
0x18001e015  movzx   edx, byte ptr [rsi+0Ah]
0x18001e019  mov     ecx, r8d
0x18001e01c  mov     dword ptr [rbp+0F0h+var_120], r8d
0x18001e020  mov     dword ptr [rbp+0F0h+var_120+4], eax
0x18001e023  mov     dword ptr [rbp+0F0h+var_120+8], edx
0x18001e026  sub     ecx, 3
0x18001e029  jz      short loc_18001E084
0x18001e02b  cmp     ecx, 1
0x18001e02e  jz      short loc_18001E03C
0x18001e030  cmp     r8d, 3
0x18001e034  jnz     loc_18001E0D4
0x18001e03a  jmp     short loc_18001E08E
0x18001e03c  lea     eax, [rdx-8]
0x18001e03f  test    eax, 0FFFFFFF7h
0x18001e044  jz      loc_18001E0D4
0x18001e04a  mov     ebx, 1
0x18001e04f  mov     rcx, rsi
0x18001e052  call    DisposeIfPtr
0x18001e057  mov     eax, ebx
0x18001e059  mov     rcx, [rbp+0F0h+var_30]
0x18001e060  xor     rcx, rsp; StackCookie
0x18001e063  call    __security_check_cookie
0x18001e068  lea     r11, [rsp+1F0h+var_20]
0x18001e070  mov     rbx, [r11+40h]
0x18001e074  mov     rsi, [r11+48h]
0x18001e078  mov     rsp, r11
0x18001e07b  pop     r15
0x18001e07d  pop     r14
0x18001e07f  pop     r12
0x18001e081  pop     rdi
0x18001e082  pop     rbp
0x18001e083  retn
0x18001e084  lea     eax, [rdx-10h]
0x18001e087  test    eax, 0FFFFFFEFh
0x18001e08c  jnz     short loc_18001E04A
0x18001e08e  cmp     [rbp+0F0h+var_9C], 58595A20h
0x18001e095  jnz     short loc_18001E0D4
0x18001e097  movsd   xmm3, cs:__real@3ff0000000000000
0x18001e09f  lea     rdx, [rsp+1F0h+var_1A0]
0x18001e0a4  mov     r8d, r12d
0x18001e0a7  lea     rcx, [rbp+0F0h+var_150]
0x18001e0ab  call    GetMatrixFromProfile
0x18001e0b0  mov     ebx, eax
0x18001e0b2  test    eax, eax
0x18001e0b4  jnz     short loc_18001E04F
0x18001e0b6  mov     rcx, qword ptr [rbp+0F0h+var_100]
0x18001e0ba  test    rcx, rcx
0x18001e0bd  jz      short loc_18001E0D4
0x18001e0bf  movss   xmm1, cs:__real@358637bd
0x18001e0c7  call    MatrixIsCloseToIdentity
0x18001e0cc  test    al, al
0x18001e0ce  jz      loc_18001E04A
0x18001e0d4  cmp     dword ptr [rsi], 6D667432h
0x18001e0da  lea     rdx, [rsp+1F0h+var_1A0]
0x18001e0df  mov     [rsp+1F0h+var_178], r15d
0x18001e0e4  lea     rcx, [rbp+0F0h+var_150]
0x18001e0e8  mov     [rbp+0F0h+var_16E], r15b
0x18001e0ec  jnz     short loc_18001E145
0x18001e0ee  mov     ebx, 1
0x18001e0f3  mov     [rbp+0F0h+var_170], 100h
0x18001e0f9  mov     r9d, r12d
0x18001e0fc  mov     [rbp+0F0h+var_16C], bl
0x18001e0ff  mov     r8, r14
0x18001e102  call    ExtractAlutFromLut16
0x18001e107  mov     ebx, eax
0x18001e109  test    eax, eax
0x18001e10b  jnz     loc_18001E04F
0x18001e111  mov     r9d, r12d
0x18001e114  lea     rdx, [rsp+1F0h+var_1A0]
0x18001e119  mov     r8, r14
0x18001e11c  lea     rcx, [rbp+0F0h+var_150]
0x18001e120  call    ExtractXlutFromLut16
0x18001e125  mov     ebx, eax
0x18001e127  test    eax, eax
0x18001e129  jnz     loc_18001E04F
0x18001e12f  mov     r9d, r12d
0x18001e132  lea     rdx, [rsp+1F0h+var_1A0]
0x18001e137  mov     r8, r14
0x18001e13a  lea     rcx, [rbp+0F0h+var_150]
0x18001e13e  call    ExtractElutFromLut16
0x18001e143  jmp     short loc_18001E18C
0x18001e145  mov     r8d, r12d
0x18001e148  mov     [rbp+0F0h+var_16C], r15b
0x18001e14c  mov     [rbp+0F0h+var_170], r15w
0x18001e151  call    ExtractAlutFromLut8
0x18001e156  mov     ebx, eax
0x18001e158  test    eax, eax
0x18001e15a  jnz     loc_18001E04F
0x18001e160  mov     r8d, r12d
0x18001e163  lea     rdx, [rsp+1F0h+var_1A0]
0x18001e168  lea     rcx, [rbp+0F0h+var_150]
0x18001e16c  call    ExtractXlutFromLut8
0x18001e171  mov     ebx, eax
0x18001e173  test    eax, eax
0x18001e175  jnz     loc_18001E04F
0x18001e17b  mov     r8d, r12d
0x18001e17e  lea     rdx, [rsp+1F0h+var_1A0]
0x18001e183  lea     rcx, [rbp+0F0h+var_150]
0x18001e187  call    ExtractElutFromLut8
0x18001e18c  mov     ebx, eax
0x18001e18e  test    eax, eax
0x18001e190  jnz     loc_18001E04F
0x18001e196  movaps  xmm0, [rbp+0F0h+var_150]
0x18001e19a  movaps  xmm1, [rbp+0F0h+var_140]
0x18001e19e  movups  xmmword ptr [rdi], xmm0
0x18001e1a1  movaps  xmm0, [rbp+0F0h+var_130]
0x18001e1a5  movups  xmmword ptr [rdi+10h], xmm1
0x18001e1a9  movaps  xmm1, [rbp+0F0h+var_120]
0x18001e1ad  movups  xmmword ptr [rdi+20h], xmm0
0x18001e1b1  movaps  xmm0, [rbp+0F0h+var_110]
0x18001e1b5  movups  xmmword ptr [rdi+30h], xmm1
0x18001e1b9  movaps  xmm1, [rbp+0F0h+var_100]
0x18001e1bd  movups  xmmword ptr [rdi+40h], xmm0
0x18001e1c1  movaps  xmm0, [rbp+0F0h+var_F0]
0x18001e1c5  movups  xmmword ptr [rdi+50h], xmm1
0x18001e1c9  movaps  xmm1, [rbp+0F0h+var_E0]
0x18001e1cd  movups  xmmword ptr [rdi+60h], xmm0
0x18001e1d1  movaps  xmm0, [rbp+0F0h+var_D0]
0x18001e1d5  movups  xmmword ptr [rdi+70h], xmm1
0x18001e1d9  movups  xmmword ptr [rdi+80h], xmm0
0x18001e1e0  jmp     loc_18001E04F
```
