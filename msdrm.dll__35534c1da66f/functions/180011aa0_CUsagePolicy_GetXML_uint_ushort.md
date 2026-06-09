# CUsagePolicy::GetXML(uint *,ushort * *)

- ea: `0x180011aa0`
- end: `0x180011fee`
- name: `?GetXML@CUsagePolicy@@QEAAJPEAIPEAPEAG@Z`
- size: `1358`
- prototype: `__int64 __fastcall(CUsagePolicy *__hidden this, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18000c414`

## callees

- `0x180001284`
- `0x180001290`
- `0x180011aa0`
- `0x180017358`
- `0x18001ef6c`
- `0x18001f020`
- `0x180020080`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011fbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011fbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011af6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011af6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUsagePolicy::GetXML(CUsagePolicy *this, unsigned int *a2, unsigned __int16 **a3)
{
  __int64 v5; // rsi
  unsigned __int16 *v6; // r15
  int v7; // eax
  __int64 v8; // rax
  int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r12
  void *v14; // rax
  int v15; // eax
  unsigned __int16 *v16; // r8
  unsigned __int16 *v17; // rax
  wchar_t *v18; // rcx
  __int64 v19; // rdx
  CDRMCBase *v20; // rcx
  unsigned int v21; // r13d
  unsigned int v22; // ecx
  __int64 v23; // rbx
  void *v24; // rax
  unsigned __int8 *v25; // rdx
  unsigned int v26; // ecx
  CDRMCBase *v27; // rcx
  __int64 v28; // r13
  void *v29; // rax
  unsigned int v31[2]; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int16 **v32; // [rsp+40h] [rbp-C8h]
  unsigned __int16 *v33; // [rsp+48h] [rbp-C0h] BYREF
  void *Block; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int *v35; // [rsp+58h] [rbp-B0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-A8h]
  __int64 v37; // [rsp+68h] [rbp-A0h]
  _OWORD v38[13]; // [rsp+78h] [rbp-90h] BYREF
  wchar_t v39; // [rsp+148h] [rbp+40h]
  _OWORD v40[10]; // [rsp+158h] [rbp+50h] BYREF
  _OWORD v41[2]; // [rsp+1F8h] [rbp+F0h]
  unsigned __int16 v42[240]; // [rsp+218h] [rbp+110h] BYREF

  v37 = -2;
  v32 = a3;
  v35 = a2;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v5 = 0;
  v6 = 0;
  v33 = 0;
  Block = 0;
  if ( !a2 )
    goto LABEL_41;
  *a2 = 0;
  v7 = *((_DWORD *)this + 38);
  if ( !v7 )
  {
    v8 = *((_QWORD *)this + 16);
    if ( v8 )
    {
      v9 = 0;
      v40[0] = *(_OWORD *)L"<POLICY><OBJECT><ID type=\"filename\">%s</ID><VERSIONSPAN min=\"%s\" max=\"%s\" /></OBJECT></POLICY>";
      v40[1] = *(_OWORD *)L"<OBJECT><ID type=\"filename\">%s</ID><VERSIONSPAN min=\"%s\" max=\"%s\" /></OBJECT></POLICY>";
      v40[2] = *(_OWORD *)L"<ID type=\"filename\">%s</ID><VERSIONSPAN min=\"%s\" max=\"%s\" /></OBJECT></POLICY>";
      v40[3] = *(_OWORD *)L"=\"filename\">%s</ID><VERSIONSPAN min=\"%s\" max=\"%s\" /></OBJECT></POLICY>";
      v40[4] = *(_OWORD *)L"me\">%s</ID><VERSIONSPAN min=\"%s\" max=\"%s\" /></OBJECT></POLICY>";
      v40[5] = *(_OWORD *)L"ID><VERSIONSPAN min=\"%s\" max=\"%s\" /></OBJECT></POLICY>";
      v40[6] = *(_OWORD *)L"IONSPAN min=\"%s\" max=\"%s\" /></OBJECT></POLICY>";
      v40[7] = *(_OWORD *)L"min=\"%s\" max=\"%s\" /></OBJECT></POLICY>";
      v40[8] = *(_OWORD *)L" max=\"%s\" /></OBJECT></POLICY>";
      v40[9] = *(_OWORD *)L"\" /></OBJECT></POLICY>";
      v41[0] = *(_OWORD *)L"JECT></POLICY>";
      *(_OWORD *)((char *)v41 + 14) = *(_OWORD *)L"POLICY>";
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)(v8 + 2 * v10) );
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(*((_QWORD *)this + 17) + 2 * v11) );
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(*((_QWORD *)this + 18) + 2 * v12) );
      v13 = (unsigned int)(v10 + v11 + v12 + 89);
      if ( !v32 )
        goto LABEL_40;
      v14 = operator new[](saturated_mul((unsigned int)v13, 2u));
      v5 = (__int64)v14;
      if ( !v14 )
      {
LABEL_12:
        v9 = -2147024882;
        goto LABEL_42;
      }
      memset_0(v14, 0, 2 * v13);
      v15 = StringCchPrintfW(
              (unsigned __int16 *)v5,
              (unsigned int)v13,
              (const unsigned __int16 *)v40,
              *((_QWORD *)this + 16),
              *((_QWORD *)this + 17),
              *((_QWORD *)this + 18));
      goto LABEL_38;
    }
    goto LABEL_41;
  }
  if ( v7 != 1 )
  {
    if ( v7 == 2 )
    {
      if ( *((_QWORD *)this + 16) )
      {
        v25 = (unsigned __int8 *)*((_QWORD *)this + 17);
        if ( v25 )
        {
          v26 = *((_DWORD *)this + 36);
          if ( v26 )
          {
            v38[0] = *(_OWORD *)L"<POLICY><DIGEST><ALGORITHM>%s</ALGORITHM><VALUE encoding=\"base64\" size=\"%d\">%s</VALU"
                                 "E></DIGEST></POLICY>";
            v38[1] = *(_OWORD *)L"<DIGEST><ALGORITHM>%s</ALGORITHM><VALUE encoding=\"base64\" size=\"%d\">%s</VALUE></DIGEST></POLICY>";
            v38[2] = *(_OWORD *)L"<ALGORITHM>%s</ALGORITHM><VALUE encoding=\"base64\" size=\"%d\">%s</VALUE></DIGEST></POLICY>";
            v38[3] = *(_OWORD *)L"HM>%s</ALGORITHM><VALUE encoding=\"base64\" size=\"%d\">%s</VALUE></DIGEST></POLICY>";
            v38[4] = *(_OWORD *)L"LGORITHM><VALUE encoding=\"base64\" size=\"%d\">%s</VALUE></DIGEST></POLICY>";
            v38[5] = *(_OWORD *)L"><VALUE encoding=\"base64\" size=\"%d\">%s</VALUE></DIGEST></POLICY>";
            v38[6] = *(_OWORD *)L"encoding=\"base64\" size=\"%d\">%s</VALUE></DIGEST></POLICY>";
            v38[7] = *(_OWORD *)L"=\"base64\" size=\"%d\">%s</VALUE></DIGEST></POLICY>";
            v38[8] = *(_OWORD *)L"\" size=\"%d\">%s</VALUE></DIGEST></POLICY>";
            v38[9] = *(_OWORD *)L"%d\">%s</VALUE></DIGEST></POLICY>";
            v38[10] = *(_OWORD *)L"VALUE></DIGEST></POLICY>";
            v38[11] = *(_OWORD *)L"DIGEST></POLICY>";
            v38[12] = *(_OWORD *)L"/POLICY>";
            v39 = aPolicyDigestAl[104];
            v9 = CDRMCBase::Base64EncodeData(v26, v25, v31, &v33);
            v6 = v33;
            if ( v9 < 0 )
              goto LABEL_42;
            if ( v33 && *v33 )
            {
              v5 = -1;
              do
                ++v5;
              while ( v33[v5] );
            }
            v13 = -1;
            do
              ++v13;
            while ( *(_WORD *)(*((_QWORD *)this + 16) + 2 * v13) );
            v28 = (unsigned int)v5 + (_DWORD)v13 + CDRMCBase::UINT2STRLength(v27, *((_DWORD *)this + 36)) + 99;
            LODWORD(v13) = v28;
            if ( !v32 )
            {
LABEL_40:
              *v35 = v13;
              v5 = 0;
              goto LABEL_42;
            }
            v29 = operator new[](saturated_mul((unsigned int)v28, 2u));
            v5 = (__int64)v29;
            if ( !v29 )
              goto LABEL_12;
            memset_0(v29, 0, 2 * v28);
            v15 = StringCchPrintfW(
                    (unsigned __int16 *)v5,
                    (unsigned int)v28,
                    (const unsigned __int16 *)v38,
                    *((_QWORD *)this + 16),
                    *((_DWORD *)this + 36),
                    v6);
LABEL_38:
            v9 = v15;
            if ( v15 < 0 )
              goto LABEL_42;
            *v32 = (unsigned __int16 *)v5;
            goto LABEL_40;
          }
        }
      }
    }
LABEL_41:
    v9 = -2147024809;
    goto LABEL_42;
  }
  v16 = (unsigned __int16 *)*((_QWORD *)this + 16);
  if ( !v16 )
    goto LABEL_41;
  v17 = v42;
  v18 = L"<POLICY><PUBLICKEY><ALGORITHM>RSA</ALGORITHM><PARAMETER name=\"public-exponent\"><VALUE encoding=\"integer32\">6"
         "5537</VALUE></PARAMETER><PARAMETER name=\"modulus\"><VALUE encoding=\"base64\" size=\"%d\">%s</VALUE></PARAMETE"
         "R></PUBLICKEY></POLICY>";
  v19 = 3;
  do
  {
    *(_OWORD *)v17 = *(_OWORD *)v18;
    *((_OWORD *)v17 + 1) = *((_OWORD *)v18 + 1);
    *((_OWORD *)v17 + 2) = *((_OWORD *)v18 + 2);
    *((_OWORD *)v17 + 3) = *((_OWORD *)v18 + 3);
    *((_OWORD *)v17 + 4) = *((_OWORD *)v18 + 4);
    *((_OWORD *)v17 + 5) = *((_OWORD *)v18 + 5);
    *((_OWORD *)v17 + 6) = *((_OWORD *)v18 + 6);
    *((_OWORD *)v17 + 7) = *((_OWORD *)v18 + 7);
    v17 += 64;
    v18 += 64;
    --v19;
  }
  while ( v19 );
  *(_OWORD *)v17 = *(_OWORD *)v18;
  *((_OWORD *)v17 + 1) = *((_OWORD *)v18 + 1);
  *((_OWORD *)v17 + 2) = *((_OWORD *)v18 + 2);
  *((_OWORD *)v17 + 3) = *((_OWORD *)v18 + 3);
  *((_OWORD *)v17 + 4) = *((_OWORD *)v18 + 4);
  *(_OWORD *)(v17 + 37) = *(_OWORD *)(v18 + 37);
  v13 = -1;
  do
    ++v13;
  while ( v16[v13] );
  v31[0] = 0;
  v9 = CDRMCBase::Base64DecodeData((CDRMCBase *)v18, v13, v16, v31, (unsigned __int8 **)&Block);
  if ( v9 >= 0 )
  {
    v21 = 8 * v31[0];
    v22 = v13 + CDRMCBase::UINT2STRLength(v20, 8 * v31[0]) + 237;
    LODWORD(v13) = v22;
    if ( !v32 )
      goto LABEL_40;
    v23 = v22;
    v24 = operator new[](saturated_mul(v22, 2u));
    v5 = (__int64)v24;
    if ( !v24 )
      goto LABEL_12;
    memset_0(v24, 0, 2 * v23);
    v15 = StringCchPrintfW((unsigned __int16 *)v5, (unsigned int)v23, v42, v21, *((_QWORD *)this + 16));
    goto LABEL_38;
  }
LABEL_42:
  operator delete((void *)v5);
  operator delete(v6);
  operator delete(Block);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180011aa0  mov     rax, rsp
0x180011aa3  push    rbp
0x180011aa4  push    rsi
0x180011aa5  push    rdi
0x180011aa6  push    r12
0x180011aa8  push    r13
0x180011aaa  push    r14
0x180011aac  push    r15
0x180011aae  lea     rbp, [rax-338h]
0x180011ab5  sub     rsp, 400h
0x180011abc  mov     [rsp+430h+var_3D0], 0FFFFFFFFFFFFFFFEh
0x180011ac5  mov     [rax+20h], rbx
0x180011ac9  mov     rax, cs:__security_cookie
0x180011ad0  xor     rax, rsp
0x180011ad3  mov     [rbp+330h+var_40], rax
0x180011ada  mov     [rsp+430h+var_3F8], r8
0x180011adf  mov     rbx, rdx
0x180011ae2  mov     [rsp+430h+var_3E0], rdx
0x180011ae7  mov     rdi, rcx
0x180011aea  lea     rax, [rcx+58h]
0x180011aee  mov     [rsp+430h+lpCriticalSection], rax
0x180011af3  mov     rcx, rax; lpCriticalSection
0x180011af6  call    cs:__imp_EnterCriticalSection
0x180011afc  nop
0x180011afd  xor     r13d, r13d
0x180011b00  mov     esi, r13d
0x180011b03  mov     r15d, r13d
0x180011b06  mov     [rsp+430h+var_3F0], r13
0x180011b0b  mov     [rsp+430h+Block], r13
0x180011b10  test    rbx, rbx
0x180011b13  jz      loc_180011F97
0x180011b19  mov     [rbx], r13d
0x180011b1c  mov     eax, [rdi+98h]
0x180011b22  test    eax, eax
0x180011b24  jnz     loc_180011C86
0x180011b2a  mov     rax, [rdi+80h]
0x180011b31  test    rax, rax
0x180011b34  jz      loc_180011F97
0x180011b3a  mov     ebx, r13d
0x180011b3d  movaps  xmm0, xmmword ptr cs:aPolicyObjectId; "<POLICY><OBJECT><ID type=\"filename\">%"...
0x180011b44  movups  [rbp+330h+var_2E0], xmm0
0x180011b48  movaps  xmm1, xmmword ptr cs:aPolicyObjectId+10h; "<OBJECT><ID type=\"filename\">%s</ID><V"...
0x180011b4f  movups  [rbp+330h+var_2D0], xmm1
0x180011b53  movaps  xmm0, xmmword ptr cs:aPolicyObjectId+20h; "<ID type=\"filename\">%s</ID><VERSIONSP"...
0x180011b5a  movups  [rbp+330h+var_2C0], xmm0
0x180011b5e  movaps  xmm1, xmmword ptr cs:aPolicyObjectId+30h; "=\"filename\">%s</ID><VERSIONSPAN min="...
0x180011b65  movups  [rbp+330h+var_2B0], xmm1
0x180011b6c  movaps  xmm0, xmmword ptr cs:aPolicyObjectId+40h; "me\">%s</ID><VERSIONSPAN min=\"%s\" max"...
0x180011b73  movups  [rbp+330h+var_2A0], xmm0
0x180011b7a  movaps  xmm1, xmmword ptr cs:aPolicyObjectId+50h; "ID><VERSIONSPAN min=\"%s\" max=\"%s\" /"...
0x180011b81  movups  [rbp+330h+var_290], xmm1
0x180011b88  movaps  xmm0, xmmword ptr cs:aPolicyObjectId+60h; "IONSPAN min=\"%s\" max=\"%s\" /></OBJEC"...
0x180011b8f  movups  [rbp+330h+var_280], xmm0
0x180011b96  movaps  xmm1, xmmword ptr cs:aPolicyObjectId+70h; "min=\"%s\" max=\"%s\" /></OBJECT></POLI"...
0x180011b9d  movups  [rbp+330h+var_270], xmm1
0x180011ba4  movaps  xmm0, xmmword ptr cs:aPolicyObjectId+80h; " max=\"%s\" /></OBJECT></POLICY>"
0x180011bab  movups  [rbp+330h+var_260], xmm0
0x180011bb2  movaps  xmm1, xmmword ptr cs:aPolicyObjectId+90h; "\" /></OBJECT></POLICY>"
0x180011bb9  movups  [rbp+330h+var_250], xmm1
0x180011bc0  movaps  xmm0, xmmword ptr cs:aPolicyObjectId+0A0h; "JECT></POLICY>"
0x180011bc7  movups  xmmword ptr [rbp+330h+var_240], xmm0
0x180011bce  movups  xmm1, xmmword ptr cs:aPolicyObjectId+0AEh; "POLICY>"
0x180011bd5  movups  xmmword ptr [rbp+330h+var_240+0Eh], xmm1
0x180011bdc  or      r14, 0FFFFFFFFFFFFFFFFh
0x180011be0  mov     rdx, r14
0x180011be3  inc     rdx
0x180011be6  cmp     [rax+rdx*2], r13w
0x180011beb  jnz     short loc_180011BE3
0x180011bed  mov     rax, [rdi+88h]
0x180011bf4  mov     rcx, r14
0x180011bf7  inc     rcx
0x180011bfa  cmp     [rax+rcx*2], r13w
0x180011bff  jnz     short loc_180011BF7
0x180011c01  mov     r8, [rdi+90h]
0x180011c08  mov     rax, r14
0x180011c0b  inc     rax
0x180011c0e  cmp     [r8+rax*2], r13w
0x180011c13  jnz     short loc_180011C0B
0x180011c15  lea     r12d, [rcx+rax]
0x180011c19  add     r12d, 59h ; 'Y'
0x180011c1d  add     r12d, edx
0x180011c20  cmp     [rsp+430h+var_3F8], r13
0x180011c25  jz      loc_180011F8B
0x180011c2b  mov     ecx, r12d
0x180011c2e  mov     eax, 2
0x180011c33  mul     rcx
0x180011c36  cmovb   rax, r14
0x180011c3a  mov     rcx, rax; unsigned __int64
0x180011c3d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011c42  mov     rsi, rax
0x180011c45  test    rax, rax
0x180011c48  jnz     short loc_180011C54
0x180011c4a  mov     ebx, 8007000Eh
0x180011c4f  jmp     loc_180011F9C
0x180011c54  lea     r8, [r12+r12]; Size
0x180011c58  xor     edx, edx; Val
0x180011c5a  mov     rcx, rsi; void *
0x180011c5d  call    memset_0
0x180011c62  mov     rax, [rdi+90h]
0x180011c69  mov     qword ptr [rsp+430h+var_408], rax
0x180011c6e  mov     rax, [rdi+88h]
0x180011c75  mov     [rsp+430h+var_410], rax
0x180011c7a  lea     r8, [rbp+330h+var_2E0]
0x180011c7e  mov     edx, r12d
0x180011c81  jmp     loc_180011F6E
0x180011c86  cmp     eax, 1
0x180011c89  jnz     loc_180011DE5
0x180011c8f  mov     r8, [rdi+80h]; unsigned __int16 *
0x180011c96  test    r8, r8
0x180011c99  jz      loc_180011F97
0x180011c9f  lea     rax, [rbp+330h+var_220]
0x180011ca6  lea     rcx, aPolicyPublicke; "<POLICY><PUBLICKEY><ALGORITHM>RSA</ALGO"...
0x180011cad  mov     edx, 3
0x180011cb2  lea     r9d, [rdx+7Dh]
0x180011cb6  movups  xmm0, xmmword ptr [rcx]
0x180011cb9  movups  xmmword ptr [rax], xmm0
0x180011cbc  movups  xmm1, xmmword ptr [rcx+10h]
0x180011cc0  movups  xmmword ptr [rax+10h], xmm1
0x180011cc4  movups  xmm0, xmmword ptr [rcx+20h]
0x180011cc8  movups  xmmword ptr [rax+20h], xmm0
0x180011ccc  movups  xmm1, xmmword ptr [rcx+30h]
0x180011cd0  movups  xmmword ptr [rax+30h], xmm1
0x180011cd4  movups  xmm0, xmmword ptr [rcx+40h]
0x180011cd8  movups  xmmword ptr [rax+40h], xmm0
0x180011cdc  movups  xmm1, xmmword ptr [rcx+50h]
0x180011ce0  movups  xmmword ptr [rax+50h], xmm1
0x180011ce4  movups  xmm0, xmmword ptr [rcx+60h]
0x180011ce8  movups  xmmword ptr [rax+60h], xmm0
0x180011cec  movups  xmm1, xmmword ptr [rcx+70h]
0x180011cf0  movups  xmmword ptr [rax+70h], xmm1
0x180011cf4  add     rax, r9
0x180011cf7  add     rcx, r9; this
0x180011cfa  sub     rdx, 1
0x180011cfe  jnz     short loc_180011CB6
0x180011d00  movups  xmm0, xmmword ptr [rcx]
0x180011d03  movups  xmmword ptr [rax], xmm0
0x180011d06  movups  xmm1, xmmword ptr [rcx+10h]
0x180011d0a  movups  xmmword ptr [rax+10h], xmm1
0x180011d0e  movups  xmm0, xmmword ptr [rcx+20h]
0x180011d12  movups  xmmword ptr [rax+20h], xmm0
0x180011d16  movups  xmm1, xmmword ptr [rcx+30h]
0x180011d1a  movups  xmmword ptr [rax+30h], xmm1
0x180011d1e  movups  xmm0, xmmword ptr [rcx+40h]
0x180011d22  movups  xmmword ptr [rax+40h], xmm0
0x180011d26  movups  xmm1, xmmword ptr [rcx+4Ah]
0x180011d2a  movups  xmmword ptr [rax+4Ah], xmm1
0x180011d2e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180011d32  mov     r12, r14
0x180011d35  inc     r12
0x180011d38  cmp     [r8+r12*2], r13w
0x180011d3d  jnz     short loc_180011D35
0x180011d3f  mov     [rsp+430h+var_400], r13d
0x180011d44  lea     rax, [rsp+430h+Block]
0x180011d49  mov     [rsp+430h+var_410], rax; unsigned __int8 **
0x180011d4e  lea     r9, [rsp+430h+var_400]; unsigned int *
0x180011d53  mov     edx, r12d; unsigned int
0x180011d56  call    ?Base64DecodeData@CDRMCBase@@QEAAJIPEAGPEAIPEAPEAE@Z; CDRMCBase::Base64DecodeData(uint,ushort *,uint *,uchar * *)
0x180011d5b  mov     ebx, eax
0x180011d5d  test    eax, eax
0x180011d5f  js      loc_180011F9C
0x180011d65  mov     eax, [rsp+430h+var_400]
0x180011d69  lea     r13d, ds:0[rax*8]
0x180011d71  mov     edx, r13d; unsigned int
0x180011d74  call    ?UINT2STRLength@CDRMCBase@@QEAAII@Z; CDRMCBase::UINT2STRLength(uint)
0x180011d79  lea     ecx, [rax+0EDh]
0x180011d7f  add     ecx, r12d
0x180011d82  mov     r12d, ecx
0x180011d85  cmp     [rsp+430h+var_3F8], rsi
0x180011d8a  jz      loc_180011F8B
0x180011d90  mov     ebx, ecx
0x180011d92  mov     eax, 2
0x180011d97  mul     rbx
0x180011d9a  cmovb   rax, r14
0x180011d9e  mov     rcx, rax; unsigned __int64
0x180011da1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011da6  mov     rsi, rax
0x180011da9  test    rax, rax
0x180011dac  jz      loc_180011C4A
0x180011db2  lea     r8, [rbx+rbx]; Size
0x180011db6  xor     edx, edx; Val
0x180011db8  mov     rcx, rax; void *
0x180011dbb  call    memset_0
0x180011dc0  mov     rax, [rdi+80h]
0x180011dc7  mov     [rsp+430h+var_410], rax
0x180011dcc  mov     r9d, r13d
0x180011dcf  lea     r8, [rbp+330h+var_220]; unsigned __int16 *
0x180011dd6  mov     edx, ebx; unsigned __int64
0x180011dd8  mov     rcx, rsi; unsigned __int16 *
0x180011ddb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011de0  jmp     loc_180011F7D
0x180011de5  cmp     eax, 2
0x180011de8  jnz     loc_180011F97
0x180011dee  cmp     [rdi+80h], r13
0x180011df5  jz      loc_180011F97
0x180011dfb  mov     rdx, [rdi+88h]; unsigned __int8 *
0x180011e02  test    rdx, rdx
0x180011e05  jz      loc_180011F97
0x180011e0b  mov     ecx, [rdi+90h]; unsigned int
0x180011e11  test    ecx, ecx
0x180011e13  jz      loc_180011F97
0x180011e19  movaps  xmm0, xmmword ptr cs:aPolicyDigestAl; "<POLICY><DIGEST><ALGORITHM>%s</ALGORITH"...
0x180011e20  movups  xmmword ptr [rsp+430h+var_3C8+8], xmm0
0x180011e25  movaps  xmm1, xmmword ptr cs:aPolicyDigestAl+10h; "<DIGEST><ALGORITHM>%s</ALGORITHM><VALUE"...
0x180011e2c  movups  [rbp+330h+var_3B0], xmm1
0x180011e30  movaps  xmm0, xmmword ptr cs:aPolicyDigestAl+20h; "<ALGORITHM>%s</ALGORITHM><VALUE encodin"...
0x180011e37  movups  [rbp+330h+var_3A0], xmm0
0x180011e3b  movaps  xmm1, xmmword ptr cs:aPolicyDigestAl+30h; "HM>%s</ALGORITHM><VALUE encoding=\"base"...
0x180011e42  movups  [rbp+330h+var_390], xmm1
0x180011e46  movaps  xmm0, xmmword ptr cs:aPolicyDigestAl+40h; "LGORITHM><VALUE encoding=\"base64\" siz"...
0x180011e4d  movups  [rbp+330h+var_380], xmm0
0x180011e51  movaps  xmm1, xmmword ptr cs:aPolicyDigestAl+50h; "><VALUE encoding=\"base64\" size=\"%d\""...
0x180011e58  movups  [rbp+330h+var_370], xmm1
0x180011e5c  movaps  xmm0, xmmword ptr cs:aPolicyDigestAl+60h; "encoding=\"base64\" size=\"%d\">%s</VAL"...
0x180011e63  movups  [rbp+330h+var_360], xmm0
0x180011e67  movaps  xmm1, xmmword ptr cs:aPolicyDigestAl+70h; "=\"base64\" size=\"%d\">%s</VALUE></DIG"...
0x180011e6e  movups  [rbp+330h+var_350], xmm1
0x180011e72  movaps  xmm0, xmmword ptr cs:aPolicyDigestAl+80h; "\" size=\"%d\">%s</VALUE></DIGEST></POL"...
0x180011e79  movups  [rbp+330h+var_340], xmm0
0x180011e7d  movaps  xmm1, xmmword ptr cs:aPolicyDigestAl+90h; "%d\">%s</VALUE></DIGEST></POLICY>"
0x180011e84  movups  [rbp+330h+var_330], xmm1
0x180011e88  movaps  xmm0, xmmword ptr cs:aPolicyDigestAl+0A0h; "VALUE></DIGEST></POLICY>"
0x180011e8f  movups  [rbp+330h+var_320], xmm0
0x180011e93  movaps  xmm1, xmmword ptr cs:aPolicyDigestAl+0B0h; "DIGEST></POLICY>"
0x180011e9a  movups  [rbp+330h+var_310], xmm1
0x180011e9e  movaps  xmm0, xmmword ptr cs:aPolicyDigestAl+0C0h; "/POLICY>"
0x180011ea5  movups  [rbp+330h+var_300], xmm0
0x180011ea9  movzx   eax, word ptr cs:aPolicyDigestAl+0D0h; ""
0x180011eb0  mov     [rbp+330h+var_2F0], ax
0x180011eb4  lea     r9, [rsp+430h+var_3F0]; unsigned __int16 **
0x180011eb9  lea     r8, [rsp+430h+var_400]; unsigned int *
0x180011ebe  call    ?Base64EncodeData@CDRMCBase@@SAJIPEAEPEAIPEAPEAG@Z; CDRMCBase::Base64EncodeData(uint,uchar *,uint *,ushort * *)
0x180011ec3  mov     ebx, eax
0x180011ec5  mov     r15, [rsp+430h+var_3F0]
0x180011eca  test    eax, eax
0x180011ecc  js      loc_180011F9C
0x180011ed2  or      r14, 0FFFFFFFFFFFFFFFFh
0x180011ed6  test    r15, r15
0x180011ed9  jz      short loc_180011EEE
0x180011edb  cmp     [r15], r13w
0x180011edf  jz      short loc_180011EEE
0x180011ee1  mov     rsi, r14
0x180011ee4  inc     rsi
0x180011ee7  cmp     [r15+rsi*2], r13w
0x180011eec  jnz     short loc_180011EE4
0x180011eee  mov     rax, [rdi+80h]
0x180011ef5  mov     r12, r14
0x180011ef8  inc     r12
0x180011efb  cmp     [rax+r12*2], r13w
0x180011f00  jnz     short loc_180011EF8
0x180011f02  mov     edx, [rdi+90h]; unsigned int
0x180011f08  call    ?UINT2STRLength@CDRMCBase@@QEAAII@Z; CDRMCBase::UINT2STRLength(uint)
0x180011f0d  lea     r13d, [rax+63h]
0x180011f11  add     r13d, r12d
0x180011f14  add     r13d, esi
0x180011f17  mov     r12d, r13d
0x180011f1a  cmp     [rsp+430h+var_3F8], 0
0x180011f20  jz      short loc_180011F8B
0x180011f22  mov     ecx, r13d
0x180011f25  mov     eax, 2
0x180011f2a  mul     rcx
0x180011f2d  cmovb   rax, r14
0x180011f31  mov     rcx, rax; unsigned __int64
0x180011f34  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011f39  mov     rsi, rax
0x180011f3c  test    rax, rax
0x180011f3f  jz      loc_180011C4A
0x180011f45  lea     r8, ds:0[r13*2]; Size
0x180011f4d  xor     edx, edx; Val
0x180011f4f  mov     rcx, rax; void *
0x180011f52  call    memset_0
0x180011f57  mov     qword ptr [rsp+430h+var_408], r15
0x180011f5c  mov     eax, [rdi+90h]
0x180011f62  mov     dword ptr [rsp+430h+var_410], eax
0x180011f66  lea     r8, [rsp+430h+var_3C8+8]; unsigned __int16 *
0x180011f6b  mov     edx, r13d; unsigned __int64
0x180011f6e  mov     r9, [rdi+80h]
0x180011f75  mov     rcx, rsi; unsigned __int16 *
0x180011f78  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011f7d  mov     ebx, eax
0x180011f7f  test    eax, eax
0x180011f81  js      short loc_180011F9C
0x180011f83  mov     rax, [rsp+430h+var_3F8]
0x180011f88  mov     [rax], rsi
0x180011f8b  mov     rax, [rsp+430h+var_3E0]
0x180011f90  mov     [rax], r12d
0x180011f93  xor     esi, esi
0x180011f95  jmp     short loc_180011F9C
0x180011f97  mov     ebx, 80070057h
0x180011f9c  mov     rcx, rsi; Block
0x180011f9f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011fa4  mov     rcx, r15; Block
0x180011fa7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011fac  mov     rcx, [rsp+430h+Block]; Block
0x180011fb1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011fb6  nop
0x180011fb7  mov     rcx, [rsp+430h+lpCriticalSection]; lpCriticalSection
0x180011fbc  call    cs:__imp_LeaveCriticalSection
0x180011fc2  mov     eax, ebx
0x180011fc4  mov     rcx, [rbp+330h+var_40]
0x180011fcb  xor     rcx, rsp; StackCookie
  ... truncated ...
```
