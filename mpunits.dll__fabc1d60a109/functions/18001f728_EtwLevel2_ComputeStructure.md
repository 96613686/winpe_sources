# EtwLevel2_ComputeStructure

- ea: `0x18001f728`
- end: `0x18001fb31`
- name: `EtwLevel2_ComputeStructure`
- size: `1033`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001f3a4`
- `0x18001f728`

## callees

- `0x18001f728`
- `0x180020778`
- `0x180044880`

## import_xrefs

- `miutils!RCClass_New` at `0x18001f858`
- `miutils!RCClass_New` at `0x18001f858`
- `miutils!RCClass_AddElement` at `0x18001fad2`
- `miutils!RCClass_AddElement` at `0x18001fad2`

## pseudocode

```c
__int64 __fastcall EtwLevel2_ComputeStructure(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall **a3)(),
        _QWORD *a4,
        __int64 (__fastcall ***a5)(),
        __int64 (__fastcall **a6)(),
        __int64 *a7,
        __int64 a8,
        __int64 a9,
        unsigned __int64 a10,
        __int64 a11)
{
  __int64 v11; // r15
  int v12; // r10d
  int v13; // r11d
  int v14; // ebx
  int v15; // edi
  int v16; // esi
  int v17; // r14d
  int v18; // ecx
  int v19; // edx
  int v20; // r8d
  __int64 result; // rax
  unsigned __int64 v22; // rdi
  __int64 v23; // xmm6_8
  __int64 v24; // r15
  __int64 (__fastcall **v25)(); // r12
  _QWORD *v26; // r9
  __int64 (__fastcall **v27)(); // rbx
  __int64 v28; // rcx
  _QWORD *v29; // rdx
  _WORD *v30; // rcx
  char *v31; // rax
  __int64 v32; // r8
  __int64 (__fastcall ***v33)(); // r10
  __int64 (__fastcall **v34)(); // r11
  __int64 (__fastcall *v35)(); // rax
  __int64 (__fastcall *v36)(); // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  int v39; // [rsp+38h] [rbp-D0h]
  __int64 v40; // [rsp+58h] [rbp-B0h]
  int v41; // [rsp+78h] [rbp-90h]
  __int64 v42; // [rsp+88h] [rbp-80h] BYREF
  int v43; // [rsp+90h] [rbp-78h] BYREF
  _QWORD *v44; // [rsp+98h] [rbp-70h]
  __int64 (__fastcall **v45)(); // [rsp+A0h] [rbp-68h]
  __int64 (__fastcall ***v46)(); // [rsp+A8h] [rbp-60h]
  __int64 (__fastcall **v47)(); // [rsp+B0h] [rbp-58h]
  __int64 *v48; // [rsp+B8h] [rbp-50h]
  __int64 v49; // [rsp+C0h] [rbp-48h]
  __int64 v50; // [rsp+C8h] [rbp-40h]
  _OWORD v51[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v52; // [rsp+F8h] [rbp-10h]
  wchar_t pszDest[104]; // [rsp+108h] [rbp+0h] BYREF

  v11 = *(_QWORD *)(a1 + 224);
  v12 = *(unsigned __int8 *)(v11 + 36);
  v13 = *(unsigned __int8 *)(v11 + 35);
  v14 = *(unsigned __int8 *)(v11 + 34);
  v15 = *(unsigned __int8 *)(v11 + 33);
  v16 = *(unsigned __int8 *)(v11 + 32);
  v17 = *(unsigned __int16 *)(v11 + 30);
  v46 = a5;
  v45 = a6;
  v49 = a1;
  v18 = *(unsigned __int8 *)(v11 + 39);
  v42 = a2;
  v19 = *(unsigned __int8 *)(v11 + 38);
  v47 = a3;
  v20 = *(unsigned __int8 *)(v11 + 37);
  v48 = a7;
  v41 = *(unsigned __int16 *)(v11 + 40);
  v44 = a4;
  StringCchPrintfW(
    pszDest,
    0x64u,
    L"Provider%08x_%04x_%04x_%02x%02x_%02x%02x%02x%02x%02x%02x_Event%d",
    *(unsigned int *)(v11 + 24),
    *(unsigned __int16 *)(v11 + 28),
    v17,
    v16,
    v15,
    v14,
    v13,
    v12,
    v20,
    v19,
    v18,
    v41);
  v52 = 0;
  result = RCClass_New(a9, 0, 0, pszDest, 0, a11, 0, a7);
  if ( !(_DWORD)result )
  {
    v22 = a10;
    if ( a10 < a10 + a11 )
    {
      v23 = v52;
      v24 = v42;
      v25 = v47;
      v50 = 1;
      while ( 1 )
      {
        v26 = v44;
        v27 = (__int64 (__fastcall **)())(v24 + 80 * v22);
        v43 = 0;
        v27[5] = (__int64 (__fastcall *)())*v44;
        v28 = *(unsigned __int16 *)(a8 + 24 * v22 + 120);
        if ( (*(_BYTE *)(a8 + 24 * v22 + 112) & 1) != 0 )
        {
          v40 = *(unsigned __int16 *)(a8 + 24 * v22 + 122);
          v42 = 0;
          result = EtwLevel2_ComputeStructure(
                     v49,
                     v24,
                     (_DWORD)v25,
                     (_DWORD)v26,
                     (__int64)v46,
                     (__int64)v45,
                     (__int64)&v42,
                     a8,
                     0,
                     v28,
                     v40);
          if ( (_DWORD)result )
            return result;
          v29 = &unk_1800494F0;
          v26 = v44;
          v27[6] = (__int64 (__fastcall *)())*(unsigned __int16 *)(a8 + 24 * v22 + 120);
          v27[9] = *(__int64 (__fastcall **)())(v42 + 8);
          v30 = (_WORD *)(a8 + 130 + 24 * v22);
        }
        else
        {
          if ( (unsigned __int16)(v28 - 1) > 0x14u )
            return 7;
          if ( (_DWORD)v28 == 8 && *(_WORD *)(a8 + 24 * v22 + 122) == 23 )
          {
            v29 = &unk_180049B40;
          }
          else
          {
            v29 = (_QWORD *)((char *)&unk_1800494F0 + 64 * v28);
            if ( (_DWORD)v28 == 14 )
            {
              v31 = (char *)&unk_180049A70;
              if ( *(_WORD *)(a8 + 24 * v22 + 122) != 24 )
                v31 = (char *)&unk_1800494F0 + 64 * v28;
              v29 = v31;
            }
          }
          v30 = (_WORD *)(a8 + 130 + 24 * v22);
          v27[6] = (__int64 (__fastcall *)())(unsigned __int16)*v30;
          v27[9] = 0;
          *v26 += (unsigned __int16)*v30;
        }
        v32 = *(unsigned int *)v29;
        v33 = v46;
        v34 = v45;
        *v27 = *v45;
        v27[2] = (__int64 (__fastcall *)())*v33;
        v27[8] = *v25;
        v27[3] = 0;
        v27[4] = 0;
        *v25 = (__int64 (__fastcall *)())((char *)*v25 + v29[1]);
        v27[1] = *(__int64 (__fastcall **)())((char *)v29 + (*v33 != 0 ? 0x10 : 0) + 24);
        if ( (*(_BYTE *)(a8 + 24 * v22 + 112) & 2) != 0 )
          break;
        v35 = (__int64 (__fastcall *)())v29[2];
        if ( v35 )
        {
          v25 = v47;
          if ( !*v30 )
            goto LABEL_18;
        }
LABEL_21:
        v36 = (__int64 (__fastcall *)())*(unsigned __int16 *)(a8 + 24 * v22 + 128);
        if ( (*(_BYTE *)(a8 + 24 * v22 + 112) & 4) != 0 )
        {
          v27[4] = (__int64 (__fastcall *)())(v24 + 80LL * (_QWORD)v36);
          v27[7] = 0;
        }
        else
        {
          if ( (_WORD)v36 == (_WORD)v50 )
            goto LABEL_26;
          v27[7] = v36;
        }
        v32 = (unsigned int)v32 | 0x10;
        v27[1] = (__int64 (__fastcall *)())v29[6];
        *v34 = (__int64 (__fastcall *)())v29[7];
        *v33 = v27;
        *v26 = 0;
LABEL_26:
        v37 = a8 + *(unsigned int *)(a8 + 24 * v22 + 116);
        LOBYTE(v39) = 0;
        v38 = *v48;
        memset(v51, 0, sizeof(v51));
        v52 = v23;
        result = RCClass_AddElement(v38, v37, v32, v51, 0x20000000, 0, v39, 0, 0, &v43);
        if ( !(_DWORD)result && ++v22 < a10 + a11 )
          continue;
        return result;
      }
      v35 = Locator_DependentLength;
      v27[3] = (__int64 (__fastcall *)())(v24 + 80LL * (unsigned __int16)*v30);
      v27[6] = 0;
LABEL_18:
      *v34 = v35;
      *v33 = v27;
      *v26 = 0;
      goto LABEL_21;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001f728  mov     rax, rsp
0x18001f72b  push    rbp
0x18001f72c  push    rbx
0x18001f72d  push    rsi
0x18001f72e  push    rdi
0x18001f72f  push    r12
0x18001f731  push    r13
0x18001f733  push    r14
0x18001f735  push    r15
0x18001f737  lea     rbp, [rax-148h]
0x18001f73e  sub     rsp, 208h
0x18001f745  movaps  xmmword ptr [rax-58h], xmm6
0x18001f749  movaps  xmmword ptr [rax-68h], xmm7
0x18001f74d  mov     rax, cs:__security_cookie
0x18001f754  xor     rax, rsp
0x18001f757  mov     [rbp+140h+var_70], rax
0x18001f75e  mov     r15, [rcx+0E0h]
0x18001f765  mov     rax, [rbp+140h+arg_20]
0x18001f76c  mov     r13, [rbp+140h+arg_38]
0x18001f773  mov     r12, [rbp+140h+arg_40]
0x18001f77a  movzx   r10d, byte ptr [r15+24h]
0x18001f77f  movzx   r11d, byte ptr [r15+23h]
0x18001f784  movzx   ebx, byte ptr [r15+22h]
0x18001f789  movzx   edi, byte ptr [r15+21h]
0x18001f78e  movzx   esi, byte ptr [r15+20h]
0x18001f793  movzx   r14d, word ptr [r15+1Eh]
0x18001f798  mov     [rbp+140h+var_1A0], rax
0x18001f79c  mov     rax, [rbp+140h+arg_28]
0x18001f7a3  mov     [rbp+140h+var_1A8], rax
0x18001f7a7  mov     rax, [rbp+140h+arg_30]
0x18001f7ae  mov     [rbp+140h+var_188], rcx
0x18001f7b2  movzx   ecx, byte ptr [r15+27h]
0x18001f7b7  mov     [rbp+140h+var_1C0], rdx
0x18001f7bb  movzx   edx, byte ptr [r15+26h]
0x18001f7c0  mov     [rbp+140h+var_198], r8
0x18001f7c4  movzx   r8d, byte ptr [r15+25h]
0x18001f7c9  mov     [rbp+140h+var_190], rax
0x18001f7cd  movzx   eax, word ptr [r15+28h]
0x18001f7d2  mov     [rsp+240h+var_1D0], eax
0x18001f7d6  mov     [rsp+240h+var_1D8], ecx
0x18001f7da  lea     rcx, [rbp+140h+pszDest]; pszDest
0x18001f7de  mov     [rsp+240h+var_1E0], edx
0x18001f7e2  mov     edx, 64h ; 'd'; cchDest
0x18001f7e7  mov     [rsp+240h+var_1E8], r8d
0x18001f7ec  lea     r8, aProvider08x04x; "Provider%08x_%04x_%04x_%02x%02x_%02x%02"...
0x18001f7f3  mov     dword ptr [rsp+240h+var_1F0], r10d
0x18001f7f8  mov     dword ptr [rsp+240h+var_1F8], r11d
0x18001f7fd  mov     dword ptr [rsp+240h+var_200], ebx
0x18001f801  mov     dword ptr [rsp+240h+var_208], edi
0x18001f805  mov     [rbp+140h+var_1B0], r9
0x18001f809  mov     r9d, [r15+18h]
0x18001f80d  movzx   r15d, word ptr [r15+1Ch]
0x18001f812  mov     dword ptr [rsp+240h+var_210], esi
0x18001f816  mov     dword ptr [rsp+240h+var_218], r14d
0x18001f81b  mov     dword ptr [rsp+240h+var_220], r15d
0x18001f820  call    StringCchPrintfW
0x18001f825  mov     rbx, [rbp+140h+arg_50]
0x18001f82c  lea     r9, [rbp+140h+pszDest]
0x18001f830  xor     eax, eax
0x18001f832  xor     r8d, r8d
0x18001f835  mov     [rbp+140h+var_150], rax
0x18001f839  xor     edx, edx
0x18001f83b  mov     rax, [rbp+140h+var_190]
0x18001f83f  mov     rcx, r12
0x18001f842  mov     [rsp+240h+var_208], rax
0x18001f847  xorps   xmm7, xmm7
0x18001f84a  xor     eax, eax
0x18001f84c  mov     dword ptr [rsp+240h+var_210], eax
0x18001f850  mov     dword ptr [rsp+240h+var_218], ebx
0x18001f854  mov     dword ptr [rsp+240h+var_220], eax
0x18001f858  call    cs:__imp_RCClass_New
0x18001f85e  xor     r8d, r8d
0x18001f861  test    eax, eax
0x18001f863  jnz     loc_18001FB00
0x18001f869  mov     rdi, [rbp+140h+arg_48]
0x18001f870  lea     r14, [rdi+rbx]
0x18001f874  cmp     rdi, r14
0x18001f877  jnb     loc_18001FB00
0x18001f87d  movsd   xmm6, [rbp+140h+var_150]
0x18001f882  lea     edx, [rax+1]
0x18001f885  mov     r15, [rbp+140h+var_1C0]
0x18001f889  lea     r10, unk_1800494F0
0x18001f890  mov     r12, [rbp+140h+var_198]
0x18001f894  lea     r11d, [r8+18h]
0x18001f898  mov     [rbp+140h+var_180], rdx
0x18001f89c  mov     r9, [rbp+140h+var_1B0]
0x18001f8a0  lea     rbx, [rdi+rdi*4]
0x18001f8a4  shl     rbx, 4
0x18001f8a8  lea     rsi, [rdi+rdi*2]
0x18001f8ac  add     rbx, r15
0x18001f8af  mov     [rbp+140h+var_1B8], r8d
0x18001f8b3  lea     rcx, [rdi+rdi*2]
0x18001f8b7  mov     rax, [r9]
0x18001f8ba  mov     [rbx+28h], rax
0x18001f8be  movzx   ecx, word ptr [r13+rcx*8+78h]
0x18001f8c4  test    [r13+rsi*8+70h], dl
0x18001f8c9  jz      short loc_18001F949
0x18001f8cb  movzx   eax, word ptr [r13+rsi*8+7Ah]
0x18001f8d1  mov     rdx, r15
0x18001f8d4  mov     [rsp+240h+var_1F0], rax
0x18001f8d9  lea     rax, [rbp+140h+var_1C0]
0x18001f8dd  mov     [rsp+240h+var_1F8], rcx
0x18001f8e2  mov     rcx, [rbp+140h+var_188]
0x18001f8e6  mov     [rsp+240h+var_200], r8
0x18001f8eb  mov     [rsp+240h+var_208], r13
0x18001f8f0  mov     [rsp+240h+var_210], rax
0x18001f8f5  mov     rax, [rbp+140h+var_1A8]
0x18001f8f9  mov     [rsp+240h+var_218], rax
0x18001f8fe  mov     rax, [rbp+140h+var_1A0]
0x18001f902  mov     [rbp+140h+var_1C0], r8
0x18001f906  mov     r8, r12
0x18001f909  mov     [rsp+240h+var_220], rax
0x18001f90e  call    EtwLevel2_ComputeStructure
0x18001f913  test    eax, eax
0x18001f915  jnz     loc_18001FB00
0x18001f91b  movzx   eax, word ptr [r13+rsi*8+78h]
0x18001f921  lea     rdx, unk_1800494F0
0x18001f928  mov     r9, [rbp+140h+var_1B0]
0x18001f92c  mov     [rbx+30h], rax
0x18001f930  mov     rax, [rbp+140h+var_1C0]
0x18001f934  mov     rcx, [rax+8]
0x18001f938  mov     [rbx+48h], rcx
0x18001f93c  lea     rcx, [r13+82h]
0x18001f943  lea     rcx, [rcx+rsi*8]
0x18001f947  jmp     short loc_18001F9AF
0x18001f949  movzx   eax, cx
0x18001f94c  sub     ax, dx
0x18001f94f  cmp     ax, 14h
0x18001f953  ja      loc_18001FAFB
0x18001f959  cmp     ecx, 8
0x18001f95c  jnz     short loc_18001F970
0x18001f95e  cmp     word ptr [r13+rsi*8+7Ah], 17h
0x18001f965  jnz     short loc_18001F970
0x18001f967  lea     rdx, unk_180049B40
0x18001f96e  jmp     short loc_18001F993
0x18001f970  mov     rdx, rcx
0x18001f973  shl     rdx, 6
0x18001f977  add     rdx, r10
0x18001f97a  cmp     ecx, 0Eh
0x18001f97d  jnz     short loc_18001F993
0x18001f97f  cmp     [r13+rsi*8+7Ah], r11w
0x18001f985  lea     rax, unk_180049A70
0x18001f98c  cmovnz  rax, rdx
0x18001f990  mov     rdx, rax
0x18001f993  lea     rcx, [r13+82h]
0x18001f99a  lea     rcx, [rcx+rsi*8]
0x18001f99e  movzx   eax, word ptr [rcx]
0x18001f9a1  mov     [rbx+30h], rax
0x18001f9a5  mov     [rbx+48h], r8
0x18001f9a9  movzx   eax, word ptr [rcx]
0x18001f9ac  add     [r9], rax
0x18001f9af  mov     r8d, [rdx]
0x18001f9b2  mov     r10, [rbp+140h+var_1A0]
0x18001f9b6  mov     r11, [rbp+140h+var_1A8]
0x18001f9ba  mov     rax, [r11]
0x18001f9bd  mov     [rbx], rax
0x18001f9c0  mov     rax, [r10]
0x18001f9c3  mov     [rbx+10h], rax
0x18001f9c7  mov     rax, [r12]
0x18001f9cb  mov     [rbx+40h], rax
0x18001f9cf  xor     eax, eax
0x18001f9d1  mov     [rbx+18h], rax
0x18001f9d5  mov     [rbx+20h], rax
0x18001f9d9  mov     rax, [rdx+8]
0x18001f9dd  add     [r12], rax
0x18001f9e1  mov     rax, [r10]
0x18001f9e4  neg     rax
0x18001f9e7  sbb     rax, rax
0x18001f9ea  and     eax, 10h
0x18001f9ed  mov     rax, [rax+rdx+18h]
0x18001f9f2  mov     [rbx+8], rax
0x18001f9f6  test    byte ptr [r13+rsi*8+70h], 2
0x18001f9fc  jz      short loc_18001FA28
0x18001f9fe  movzx   eax, word ptr [rcx]
0x18001fa01  lea     rcx, [rax+rax*4]
0x18001fa05  shl     rcx, 4
0x18001fa09  lea     rax, Locator_DependentLength
0x18001fa10  add     rcx, r15
0x18001fa13  mov     [rbx+18h], rcx
0x18001fa17  xor     ecx, ecx
0x18001fa19  mov     [rbx+30h], rcx
0x18001fa1d  mov     [r11], rax
0x18001fa20  mov     [r10], rbx
0x18001fa23  mov     [r9], rcx
0x18001fa26  jmp     short loc_18001FA44
0x18001fa28  mov     rax, [rdx+10h]
0x18001fa2c  test    rax, rax
0x18001fa2f  jz      short loc_18001FA42
0x18001fa31  xor     r12d, r12d
0x18001fa34  cmp     [rcx], r12w
0x18001fa38  mov     r12, [rbp+140h+var_198]
0x18001fa3c  jnz     short loc_18001FA42
0x18001fa3e  xor     ecx, ecx
0x18001fa40  jmp     short loc_18001FA1D
0x18001fa42  xor     ecx, ecx
0x18001fa44  test    byte ptr [r13+rsi*8+70h], 4
0x18001fa4a  movzx   eax, word ptr [r13+rsi*8+80h]
0x18001fa53  jz      short loc_18001FA6C
0x18001fa55  lea     rcx, [rax+rax*4]
0x18001fa59  shl     rcx, 4
0x18001fa5d  add     rcx, r15
0x18001fa60  mov     [rbx+20h], rcx
0x18001fa64  xor     ecx, ecx
0x18001fa66  mov     [rbx+38h], rcx
0x18001fa6a  jmp     short loc_18001FA76
0x18001fa6c  cmp     ax, word ptr [rbp+140h+var_180]
0x18001fa70  jz      short loc_18001FA8F
0x18001fa72  mov     [rbx+38h], rax
0x18001fa76  mov     rax, [rdx+30h]
0x18001fa7a  or      r8d, 10h
0x18001fa7e  mov     [rbx+8], rax
0x18001fa82  mov     rax, [rdx+38h]
0x18001fa86  mov     [r11], rax
0x18001fa89  mov     [r10], rbx
0x18001fa8c  mov     [r9], rcx
0x18001fa8f  mov     edx, [r13+rsi*8+74h]
0x18001fa94  lea     rax, [rbp+140h+var_1B8]
0x18001fa98  mov     [rsp+240h+var_1F8], rax
0x18001fa9d  lea     r9, [rbp+140h+var_170]
0x18001faa1  mov     rax, [rbp+140h+var_190]
0x18001faa5  add     rdx, r13
0x18001faa8  mov     dword ptr [rsp+240h+var_200], ecx
0x18001faac  mov     [rsp+240h+var_208], rcx
0x18001fab1  mov     byte ptr [rsp+240h+var_210], cl
0x18001fab5  mov     [rsp+240h+var_218], rcx
0x18001faba  mov     rcx, [rax]
0x18001fabd  movaps  [rbp+140h+var_170], xmm7
0x18001fac1  movaps  [rbp+140h+var_160], xmm7
0x18001fac5  movsd   [rbp+140h+var_150], xmm6
0x18001faca  mov     dword ptr [rsp+240h+var_220], 20000000h
0x18001fad2  call    cs:__imp_RCClass_AddElement
0x18001fad8  xor     r8d, r8d
0x18001fadb  test    eax, eax
0x18001fadd  jnz     short loc_18001FB00
0x18001fadf  lea     edx, [rax+1]
0x18001fae2  add     rdi, rdx
0x18001fae5  lea     r10, unk_1800494F0
0x18001faec  lea     r11d, [r8+18h]
0x18001faf0  cmp     rdi, r14
0x18001faf3  jb      loc_18001F89C
0x18001faf9  jmp     short loc_18001FB00
0x18001fafb  mov     eax, 7
0x18001fb00  mov     rcx, [rbp+140h+var_70]
0x18001fb07  xor     rcx, rsp; StackCookie
0x18001fb0a  call    __security_check_cookie
0x18001fb0f  lea     r11, [rsp+240h+var_38]
0x18001fb17  movaps  xmm6, xmmword ptr [r11-18h]
0x18001fb1c  movaps  xmm7, xmmword ptr [r11-28h]
0x18001fb21  mov     rsp, r11
0x18001fb24  pop     r15
0x18001fb26  pop     r14
0x18001fb28  pop     r13
0x18001fb2a  pop     r12
0x18001fb2c  pop     rdi
0x18001fb2d  pop     rsi
0x18001fb2e  pop     rbx
0x18001fb2f  pop     rbp
0x18001fb30  retn
```
