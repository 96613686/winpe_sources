# CipInstrumentVbsPolicyFailure

- ea: `0x18006c77c`
- end: `0x18006caf2`
- name: `CipInstrumentVbsPolicyFailure`
- size: `886`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18006c2fc`
- `0x18006c350`

## callees

- `0x18000a2f4`
- `0x18000fb30`
- `0x18002bf20`
- `0x18006c77c`
- `0x1800e3e70`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18006ca9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006cabb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006ca9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006cabb`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18006ca21`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18006ca21`

## pseudocode

```c
void __fastcall CipInstrumentVbsPolicyFailure(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5)
{
  unsigned __int16 *v5; // rdi
  void *v6; // r13
  unsigned __int16 *v7; // r14
  char v8; // bl
  __int64 v9; // rcx
  __int64 v10; // r12
  unsigned __int16 v11; // r15
  __int64 v12; // rax
  int v13; // eax
  PVOID v14; // rsi
  int v15; // r9d
  int v16; // eax
  __int64 v17; // r8
  PVOID v18; // rdi
  char v19; // al
  char IsCurrentThreadInServerSilo; // al
  __int64 v21; // r8
  char v22; // [rsp+30h] [rbp-D0h] BYREF
  char v23; // [rsp+31h] [rbp-CFh] BYREF
  char v24; // [rsp+32h] [rbp-CEh] BYREF
  char v25; // [rsp+33h] [rbp-CDh] BYREF
  char v26; // [rsp+34h] [rbp-CCh] BYREF
  char v27; // [rsp+35h] [rbp-CBh] BYREF
  unsigned __int16 v28; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-B0h] BYREF
  PVOID v32[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+70h] [rbp-90h] BYREF
  __int128 v34; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  _DWORD *v38; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  PVOID v40; // [rsp+D0h] [rbp-30h]
  _DWORD v41[2]; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD *v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  PVOID v44; // [rsp+F0h] [rbp-10h]
  _DWORD v45[2]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 **v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]
  char *v48; // [rsp+110h] [rbp+10h]
  __int64 v49; // [rsp+118h] [rbp+18h]
  __int64 *v50; // [rsp+120h] [rbp+20h]
  __int64 v51; // [rsp+128h] [rbp+28h]
  char *v52; // [rsp+130h] [rbp+30h]
  __int64 v53; // [rsp+138h] [rbp+38h]
  _DWORD *v54; // [rsp+140h] [rbp+40h]
  __int64 v55; // [rsp+148h] [rbp+48h]
  __int64 v56; // [rsp+150h] [rbp+50h]
  _DWORD v57[2]; // [rsp+158h] [rbp+58h] BYREF
  PVOID *v58; // [rsp+160h] [rbp+60h]
  __int64 v59; // [rsp+168h] [rbp+68h]
  __int16 *v60; // [rsp+170h] [rbp+70h]
  __int64 v61; // [rsp+178h] [rbp+78h]
  __int64 v62; // [rsp+180h] [rbp+80h]
  int v63; // [rsp+188h] [rbp+88h]
  int v64; // [rsp+18Ch] [rbp+8Ch]
  char *v65; // [rsp+190h] [rbp+90h]
  __int64 v66; // [rsp+198h] [rbp+98h]
  char *v67; // [rsp+1A0h] [rbp+A0h]
  __int64 v68; // [rsp+1A8h] [rbp+A8h]
  PVOID *v69; // [rsp+1B0h] [rbp+B0h]
  __int64 v70; // [rsp+1B8h] [rbp+B8h]

  v29 = a4;
  v30 = a1;
  v24 = 0;
  v23 = 0;
  v5 = a4;
  v34 = 0;
  *(_OWORD *)v32 = 0;
  *(_OWORD *)P = 0;
  if ( a2 )
  {
    v6 = *(void **)(a2 + 840);
    v7 = (unsigned __int16 *)(a2 + 744);
    v8 = 0;
    v9 = 160LL * (((unsigned __int8)*(_DWORD *)(a2 + 32) - 1) & 3 & (unsigned int)-(*(_DWORD *)(a2 + 32) != 0));
    v10 = v9 + a2 + 128;
    v11 = *(_WORD *)(v9 + a2 + 124);
    v12 = *(_QWORD *)(a2 + 984);
    v22 = *(_BYTE *)(v9 + a2 + 92);
    v5 = v29;
    if ( v12 )
      v8 = BYTE1(*(_DWORD *)(*(_QWORD *)(v12 + 8) + 48LL)) & 1;
  }
  else
  {
    v10 = 0;
    v22 = 0;
    v11 = 0;
    v7 = (unsigned __int16 *)&v34;
    v6 = 0;
    v8 = 1;
  }
  v13 = CiSanitizeFileName(a3, (struct _UNICODE_STRING *)v32, &v24);
  v14 = v32[1];
  LOBYTE(v15) = 0;
  if ( v13 >= 0 )
  {
    v16 = CiSanitizeFileName(v5, (struct _UNICODE_STRING *)P, &v23);
    v18 = P[1];
    LOBYTE(v15) = 0;
    if ( v16 >= 0
      && (unsigned int)dword_180049128 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_180049128, 0x800000000000LL, v17, 0) )
    {
      v33 = (unsigned int)(v15 + 1);
      v36 = &v33;
      v38 = v41;
      v41[0] = LOWORD(v32[0]);
      v42 = v45;
      v45[0] = LOWORD(P[0]);
      LODWORD(v29) = a5;
      v46 = &v29;
      v19 = (v15 + 1) & *(_BYTE *)(v30 + 46);
      v37 = 8;
      v25 = v19;
      v48 = &v25;
      v30 = *(_QWORD *)(v30 + 32);
      v50 = &v30;
      v52 = &v22;
      v54 = v57;
      v56 = *((_QWORD *)v7 + 1);
      v57[0] = *v7;
      v58 = P;
      v60 = (__int16 *)&v28;
      v63 = v11;
      v65 = &v26;
      v39 = 2;
      v40 = v14;
      v41[1] = v15;
      v43 = 2;
      v44 = v18;
      v45[1] = v15;
      v47 = 4;
      v49 = v33;
      v51 = 8;
      v53 = v33;
      v55 = 2;
      v57[1] = v15;
      P[0] = v6;
      v59 = 8;
      v28 = v11;
      v61 = 2;
      v62 = v10;
      v64 = v15;
      v26 = v8;
      v66 = v33;
      IsCurrentThreadInServerSilo = PsIsCurrentThreadInServerSilo();
      v68 = 1;
      v27 = IsCurrentThreadInServerSilo;
      v70 = 8;
      v67 = &v27;
      v32[0] = (PVOID)0x80000000LL;
      v69 = v32;
      tlgWriteAgg((__int64)&dword_180049128, (unsigned __int8 *)&byte_18003DBA1, v21, 0x13u, &v35);
      LOBYTE(v15) = 0;
    }
    if ( v23 != (_BYTE)v15 )
    {
      ExFreePoolWithTag(v18, 0x63734943u);
      LOBYTE(v15) = 0;
    }
  }
  if ( v24 != (_BYTE)v15 )
    ExFreePoolWithTag(v14, 0x63734943u);
}

```

## disassembly

```asm
0x18006c77c  mov     [rsp-8+arg_0], rbx
0x18006c781  push    rbp
0x18006c782  push    rsi
0x18006c783  push    rdi
0x18006c784  push    r12
0x18006c786  push    r13
0x18006c788  push    r14
0x18006c78a  push    r15
0x18006c78c  lea     rbp, [rsp-0D0h]
0x18006c794  sub     rsp, 1D0h
0x18006c79b  mov     rax, cs:__security_cookie
0x18006c7a2  xor     rax, rsp
0x18006c7a5  mov     [rbp+100h+var_40], rax
0x18006c7ac  xor     r11d, r11d
0x18006c7af  mov     [rsp+200h+var_1C0], r9
0x18006c7b4  mov     [rsp+200h+var_1B8], rcx
0x18006c7b9  xorps   xmm0, xmm0
0x18006c7bc  mov     [rsp+200h+var_1CE], r11b
0x18006c7c1  xorps   xmm1, xmm1
0x18006c7c4  mov     [rsp+200h+var_1CF], r11b
0x18006c7c9  mov     rdi, r9
0x18006c7cc  mov     r10, r8
0x18006c7cf  mov     r9, rdx
0x18006c7d2  movups  [rsp+200h+var_188], xmm0
0x18006c7d7  movups  xmmword ptr [rsp+200h+var_1A0], xmm1
0x18006c7dc  movups  xmmword ptr [rsp+200h+P], xmm0
0x18006c7e1  test    rdx, rdx
0x18006c7e4  jz      short loc_18006C85C
0x18006c7e6  mov     edx, [rdx+20h]
0x18006c7e9  lea     r12, [r9+80h]
0x18006c7f0  mov     r13, [r9+348h]
0x18006c7f7  lea     r14, [r9+2E8h]
0x18006c7fe  mov     eax, edx
0x18006c800  mov     bl, r11b
0x18006c803  lea     r8d, [rdx-1]
0x18006c807  and     r8d, 3
0x18006c80b  neg     eax
0x18006c80d  sbb     ecx, ecx
0x18006c80f  and     ecx, r8d
0x18006c812  lea     rcx, [rcx+rcx*4]
0x18006c816  shl     rcx, 5
0x18006c81a  add     r12, rcx
0x18006c81d  neg     edx
0x18006c81f  movzx   r15d, word ptr [rcx+r9+7Ch]
0x18006c825  sbb     eax, eax
0x18006c827  and     eax, r8d
0x18006c82a  lea     rcx, [rax+rax*4]
0x18006c82e  mov     rax, [r9+3D8h]
0x18006c835  shl     rcx, 5
0x18006c839  mov     dil, [rcx+r9+5Ch]
0x18006c83e  mov     [rsp+200h+var_1D0], dil
0x18006c843  mov     rdi, [rsp+200h+var_1C0]
0x18006c848  test    rax, rax
0x18006c84b  jz      short loc_18006C871
0x18006c84d  mov     rax, [rax+8]
0x18006c851  mov     ebx, [rax+30h]
0x18006c854  shr     ebx, 8
0x18006c857  and     bl, 1
0x18006c85a  jmp     short loc_18006C871
0x18006c85c  mov     r12, r11
0x18006c85f  mov     [rsp+200h+var_1D0], r11b
0x18006c864  mov     r15d, r11d
0x18006c867  lea     r14, [rsp+200h+var_188]
0x18006c86c  mov     r13, r11
0x18006c86f  mov     bl, 1
0x18006c871  lea     r8, [rsp+200h+var_1CE]
0x18006c876  mov     rcx, r10
0x18006c879  lea     rdx, [rsp+200h+var_1A0]
0x18006c87e  call    CiSanitizeFileName
0x18006c883  mov     rsi, [rsp+200h+var_1A0+8]
0x18006c888  xor     r9d, r9d
0x18006c88b  test    eax, eax
0x18006c88d  js      loc_18006CAAC
0x18006c893  lea     r8, [rsp+200h+var_1CF]
0x18006c898  mov     rcx, rdi
0x18006c89b  lea     rdx, [rsp+200h+P]
0x18006c8a0  call    CiSanitizeFileName
0x18006c8a5  mov     rdi, [rsp+200h+P+8]
0x18006c8aa  xor     r9d, r9d
0x18006c8ad  test    eax, eax
0x18006c8af  js      loc_18006CA8E
0x18006c8b5  mov     eax, cs:dword_180049128
0x18006c8bb  cmp     eax, 5
0x18006c8be  jbe     loc_18006CA8E
0x18006c8c4  mov     rdx, 800000000000h
0x18006c8ce  lea     rcx, dword_180049128
0x18006c8d5  call    _tlgKeywordOn
0x18006c8da  test    al, al
0x18006c8dc  jz      loc_18006CA8E
0x18006c8e2  mov     rcx, [rsp+200h+var_1B8]
0x18006c8e7  lea     r10d, [r9+1]
0x18006c8eb  lea     rax, [rsp+200h+var_190]
0x18006c8f0  mov     [rsp+200h+var_190], r10
0x18006c8f5  mov     [rbp+100h+var_150], rax
0x18006c8f9  lea     rax, [rbp+100h+var_128]
0x18006c8fd  mov     [rbp+100h+var_140], rax
0x18006c901  movzx   eax, word ptr [rsp+200h+var_1A0]
0x18006c906  mov     [rbp+100h+var_128], eax
0x18006c909  lea     rax, [rbp+100h+var_108]
0x18006c90d  mov     [rbp+100h+var_120], rax
0x18006c911  movzx   eax, word ptr [rsp+200h+P]
0x18006c916  mov     [rbp+100h+var_108], eax
0x18006c919  mov     eax, [rbp+100h+arg_20]
0x18006c91f  mov     dword ptr [rsp+200h+var_1C0], eax
0x18006c923  lea     rax, [rsp+200h+var_1C0]
0x18006c928  mov     [rbp+100h+var_100], rax
0x18006c92c  mov     al, [rcx+2Eh]
0x18006c92f  and     al, r10b
0x18006c932  mov     [rbp+100h+var_148], 8
0x18006c93a  mov     [rsp+200h+var_1CD], al
0x18006c93e  lea     rax, [rsp+200h+var_1CD]
0x18006c943  mov     [rbp+100h+var_F0], rax
0x18006c947  mov     rax, [rcx+20h]
0x18006c94b  mov     [rsp+200h+var_1B8], rax
0x18006c950  lea     rax, [rsp+200h+var_1B8]
0x18006c955  mov     [rbp+100h+var_E0], rax
0x18006c959  mov     al, [rsp+200h+var_1D0]
0x18006c95d  mov     [rsp+200h+var_1D0], al
0x18006c961  lea     rax, [rsp+200h+var_1D0]
0x18006c966  mov     [rbp+100h+var_D0], rax
0x18006c96a  lea     rax, [rbp+100h+var_A8]
0x18006c96e  mov     [rbp+100h+var_C0], rax
0x18006c972  mov     rax, [r14+8]
0x18006c976  mov     [rbp+100h+var_B0], rax
0x18006c97a  movzx   eax, word ptr [r14]
0x18006c97e  mov     [rbp+100h+var_A8], eax
0x18006c981  lea     rax, [rsp+200h+P]
0x18006c986  mov     [rbp+100h+var_A0], rax
0x18006c98a  lea     rax, [rsp+200h+var_1C8]
0x18006c98f  mov     [rbp+100h+var_90], rax
0x18006c993  movzx   eax, r15w
0x18006c997  mov     [rbp+100h+var_78], eax
0x18006c99d  lea     rax, [rsp+200h+var_1CC]
0x18006c9a2  mov     [rbp+100h+var_70], rax
0x18006c9a9  mov     [rbp+100h+var_138], 2
0x18006c9b1  mov     [rbp+100h+var_130], rsi
0x18006c9b5  mov     [rbp+100h+var_124], r9d
0x18006c9b9  mov     [rbp+100h+var_118], 2
0x18006c9c1  mov     [rbp+100h+var_110], rdi
0x18006c9c5  mov     [rbp+100h+var_104], r9d
0x18006c9c9  mov     [rbp+100h+var_F8], 4
0x18006c9d1  mov     [rbp+100h+var_E8], r10
0x18006c9d5  mov     [rbp+100h+var_D8], 8
0x18006c9dd  mov     [rbp+100h+var_C8], r10
0x18006c9e1  mov     [rbp+100h+var_B8], 2
0x18006c9e9  mov     [rbp+100h+var_A4], r9d
0x18006c9ed  mov     [rsp+200h+P], r13
0x18006c9f2  mov     [rbp+100h+var_98], 8
0x18006c9fa  mov     [rsp+200h+var_1C8], r15w
0x18006ca00  mov     [rbp+100h+var_88], 2
0x18006ca08  mov     [rbp+100h+var_80], r12
0x18006ca0f  mov     [rbp+100h+var_74], r9d
0x18006ca16  mov     [rsp+200h+var_1CC], bl
0x18006ca1a  mov     [rbp+100h+var_68], r10
0x18006ca21  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x18006ca28  nop     dword ptr [rax+rax+00h]
0x18006ca2d  mov     r9d, 13h; int
0x18006ca33  mov     [rbp+100h+var_58], 1
0x18006ca3e  mov     [rsp+200h+var_1CB], al
0x18006ca42  lea     rdx, byte_18003DBA1; int
0x18006ca49  lea     rax, [rsp+200h+var_1CB]
0x18006ca4e  mov     [rbp+100h+var_48], 8
0x18006ca59  mov     [rbp+100h+var_60], rax
0x18006ca60  lea     rcx, dword_180049128; int
0x18006ca67  mov     eax, 80000000h
0x18006ca6c  mov     [rsp+200h+var_1A0], rax
0x18006ca71  lea     rax, [rsp+200h+var_1A0]
0x18006ca76  mov     [rbp+100h+var_50], rax
0x18006ca7d  lea     rax, [rbp+100h+var_170]
0x18006ca81  mov     [rsp+200h+var_1E0], rax; PEVENT_DATA_DESCRIPTOR
0x18006ca86  call    _tlgWriteAgg
0x18006ca8b  xor     r9d, r9d
0x18006ca8e  cmp     [rsp+200h+var_1CF], r9b
0x18006ca93  jz      short loc_18006CAAC
0x18006ca95  mov     edx, 63734943h; Tag
0x18006ca9a  mov     rcx, rdi; P
0x18006ca9d  call    cs:__imp_ExFreePoolWithTag
0x18006caa4  nop     dword ptr [rax+rax+00h]
0x18006caa9  xor     r9d, r9d
0x18006caac  cmp     [rsp+200h+var_1CE], r9b
0x18006cab1  jz      short loc_18006CAC7
0x18006cab3  mov     edx, 63734943h; Tag
0x18006cab8  mov     rcx, rsi; P
0x18006cabb  call    cs:__imp_ExFreePoolWithTag
0x18006cac2  nop     dword ptr [rax+rax+00h]
0x18006cac7  mov     rcx, [rbp+100h+var_40]
0x18006cace  xor     rcx, rsp; StackCookie
0x18006cad1  call    __security_check_cookie
0x18006cad6  mov     rbx, [rsp+200h+arg_0]
0x18006cade  add     rsp, 1D0h
0x18006cae5  pop     r15
0x18006cae7  pop     r14
0x18006cae9  pop     r13
0x18006caeb  pop     r12
0x18006caed  pop     rdi
0x18006caee  pop     rsi
0x18006caef  pop     rbp
0x18006caf0  retn
```
