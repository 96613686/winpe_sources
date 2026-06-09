# NakCheck

- ea: `0x18001f06c`
- end: `0x18001f7d6`
- name: `NakCheck`
- size: `1898`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, _DWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001dd10`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180017ea4`
- `0x180017fec`
- `0x18001f06c`
- `0x18001f7dc`
- `0x18002a138`
- `0x180032460`
- `0x180033010`

## string_xrefs

- `0x18001f1c9`: `IPCP: Naking IP compression`
- `0x18001f44c`: `IPCP: RasSrvrAcquireAddress(%08x)...`
- `0x18001f4d7`: `IPCP: RasSrvrAcquireAddress done(%d)`
- `0x18001f71f`: `IPCP: RasSrvrAcquireAddress done(%d)`
- `0x18001f58b`: `IPCP: 3rd party DLL changed IP`
- `0x18001f6ce`: `IPCP: RasSrvrAcquireAddress(0)...`

## pseudocode

```c
__int64 __fastcall NakCheck(__int64 a1, unsigned __int8 *a2, __int64 a3, __int64 a4, _DWORD *a5, unsigned int a6)
{
  __int16 v6; // r14
  _DWORD *v7; // rdi
  _DWORD *v8; // r12
  unsigned __int8 *v9; // r15
  __int16 v11; // cx
  unsigned int v12; // r13d
  int v13; // r14d
  __int64 v14; // rbx
  unsigned __int16 v15; // r9
  unsigned __int8 v16; // cl
  int v17; // eax
  unsigned __int8 v18; // cl
  int v19; // eax
  int v20; // eax
  unsigned int *v21; // r12
  unsigned int v22; // edx
  unsigned int v23; // eax
  unsigned int v24; // r14d
  const wchar_t *v25; // r8
  __int64 v26; // rax
  unsigned int v28; // eax
  unsigned int v29; // ebx
  int v30; // eax
  _BYTE *v31; // rcx
  __int16 v32; // di
  int v33; // [rsp+30h] [rbp-D0h]
  _DWORD *v34; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v35; // [rsp+48h] [rbp-B8h]
  int v36; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v37[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v6 = a2[3];
  v7 = (_DWORD *)(a3 + 4);
  v8 = a5;
  v9 = a2 + 4;
  v35 = (_BYTE *)a3;
  v11 = a2[2] << 8;
  v34 = (_DWORD *)(a3 + 4);
  v36 = 0;
  v12 = 0;
  v13 = (unsigned __int16)(v11 + v6 - 4);
  v33 = v13;
  memset_0(v37, 0, sizeof(v37));
  v14 = *((_QWORD *)&xmmword_18004C860 + 1);
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      L"IPCP: NakCheck");
    v14 = *((_QWORD *)&xmmword_18004C860 + 1);
  }
  *a5 = 0;
  while ( (unsigned __int16)v13 >= 2u )
  {
    v15 = v9[1];
    if ( (unsigned __int16)v13 < v15 )
      return 722;
    if ( *v9 == 2 )
    {
      if ( (v9[2] << 8) + v9[3] != 45 )
        goto LABEL_18;
      if ( (_BYTE)v15 != 6 )
        return 722;
      v16 = v9[4];
      if ( v16 > *(_BYTE *)(a1 + 174) )
      {
        v17 = 1;
      }
      else
      {
        v17 = 0;
        *(_BYTE *)(a1 + 174) = v16;
      }
      v18 = v9[5];
      if ( *(_BYTE *)(a1 + 175) )
      {
        *(_BYTE *)(a1 + 175) = v18;
      }
      else if ( v18 )
      {
        v17 = 1;
      }
      if ( v17 )
      {
LABEL_18:
        if ( v14 )
        {
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            v14,
            L"IPCP: Naking IP compression");
          v14 = *((_QWORD *)&xmmword_18004C860 + 1);
        }
        *v8 = 1;
        if ( a6 )
        {
          memcpy_0(v7, v9, v9[1]);
        }
        else
        {
          *v7 = 754976258;
          *((_BYTE *)v7 + 4) = *(_BYTE *)(a1 + 174);
          *((_BYTE *)v7 + 5) = *(_BYTE *)(a1 + 175);
          v7 = (_DWORD *)((char *)v7 + *((unsigned __int8 *)v7 + 1));
          v34 = v7;
        }
        v19 = 0;
      }
      else
      {
        v19 = 1;
      }
      *(_DWORD *)(a1 + 180) = v19;
    }
    else if ( *(_DWORD *)a1 || *(_DWORD *)(a1 + 2088) == 2 )
    {
      if ( *v9 == 3 )
      {
        if ( (_BYTE)v15 != 6 )
          return 722;
        v12 = *(_DWORD *)(v9 + 2);
        v21 = (unsigned int *)(a1 + 148);
        if ( !*(_DWORD *)(a1 + 148) )
        {
          if ( v12 )
            goto LABEL_49;
          goto LABEL_54;
        }
        if ( v12 != *v21 )
        {
          if ( !v12 )
          {
            v12 = *v21;
            *a5 = 1;
            memcpy_0(v7, v9, v9[1]);
            if ( !a6 )
            {
              if ( v14 )
              {
                ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
                  gRasIpcpEtwContext,
                  v14,
                  L"IPCP: Naking IP");
                v14 = *((_QWORD *)&xmmword_18004C860 + 1);
              }
              *(_DWORD *)((char *)v7 + 2) = *v21;
            }
            goto LABEL_78;
          }
          if ( v14 )
            ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
              gRasIpcpEtwContext,
              v14,
              L"IPCP: RasSrvrReleaseAddress...");
          RasPPPSrvrReleaseAddress(*v21, a1 + 1264, a1 + 1778, a1 + 2120, 0);
          v14 = *((_QWORD *)&xmmword_18004C860 + 1);
          if ( *((_QWORD *)&xmmword_18004C860 + 1) )
          {
            ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
              gRasIpcpEtwContext,
              *((_QWORD *)&xmmword_18004C860 + 1),
              L"IPCP: RasSrvrReleaseAddress done");
            v14 = *((_QWORD *)&xmmword_18004C860 + 1);
          }
          *v21 = 0;
LABEL_49:
          if ( *(_DWORD *)(a1 + 2088) != 2 && *(_DWORD *)(a1 + 152) == -16777217 )
          {
            if ( v14 )
            {
              ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
                gRasIpcpEtwContext,
                v14,
                L"IPCP: Clients not allowed to request IPaddr");
              v14 = *((_QWORD *)&xmmword_18004C860 + 1);
            }
            v12 = 0;
          }
LABEL_54:
          if ( v14 )
          {
            LOWORD(v36) = 0;
            FormatRRASErrorString(&v36, L"IPCP: RasSrvrAcquireAddress(%08x)...", v12);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
              gRasIpcpEtwContext,
              *((_QWORD *)&xmmword_18004C860 + 1),
              &v36);
          }
          v22 = v12;
          if ( ((*(_DWORD *)(a1 + 152) + 16777217) & 0xFEFFFFFF) != 0 )
            v22 = *(_DWORD *)(a1 + 152);
          v23 = RasPPPSrvrAcquireAddress(*(_QWORD *)(a1 + 8), v22, (int)a1 + 148, (int)a1 + 1264, a1 + 1778, a1 + 2120);
          v14 = *((_QWORD *)&xmmword_18004C860 + 1);
          v24 = v23;
          if ( *((_QWORD *)&xmmword_18004C860 + 1) )
          {
            LOWORD(v36) = 0;
            FormatRRASErrorString(&v36, L"IPCP: RasSrvrAcquireAddress done(%d)", v23);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
              gRasIpcpEtwContext,
              *((_QWORD *)&xmmword_18004C860 + 1),
              &v36);
            v14 = *((_QWORD *)&xmmword_18004C860 + 1);
          }
          if ( v24 )
            return v24;
          if ( v12 )
          {
            if ( v14 )
            {
              ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
                gRasIpcpEtwContext,
                v14,
                L"IPCP: Hard IP requested");
              v14 = *((_QWORD *)&xmmword_18004C860 + 1);
            }
            if ( v12 == *v21 )
            {
              if ( v14 )
              {
                ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
                  gRasIpcpEtwContext,
                  v14,
                  L"IPCP: Accepting IP");
                v14 = *((_QWORD *)&xmmword_18004C860 + 1);
              }
              v13 = v33;
              goto LABEL_79;
            }
            if ( v14 )
            {
              v25 = L"IPCP: 3rd party DLL changed IP";
              goto LABEL_72;
            }
          }
          else if ( v14 )
          {
            v25 = L"IPCP: Server IP requested";
LABEL_72:
            ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(gRasIpcpEtwContext, v14, v25);
            v14 = *((_QWORD *)&xmmword_18004C860 + 1);
          }
          v12 = *v21;
          *a5 = 1;
          memcpy_0(v7, v9, v9[1]);
          if ( !a6 )
          {
            if ( v14 )
            {
              ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
                gRasIpcpEtwContext,
                v14,
                L"IPCP: Naking IP");
              v14 = *((_QWORD *)&xmmword_18004C860 + 1);
            }
            *(_DWORD *)((char *)v7 + 2) = *v21;
          }
          v13 = v33;
LABEL_78:
          v7 = (_DWORD *)((char *)v7 + v9[1]);
          v34 = v7;
        }
LABEL_79:
        v8 = a5;
        goto LABEL_80;
      }
      if ( *v9 == 129 || *v9 == 130 || (unsigned int)*v9 - 131 < 2 )
      {
        v20 = NakCheckNameServerOption(a1, a6, v9, &v34);
        v7 = v34;
        v14 = *((_QWORD *)&xmmword_18004C860 + 1);
        if ( v20 )
          *v8 = 1;
      }
      else if ( (_QWORD)xmmword_18004C860 )
      {
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          xmmword_18004C860,
          L"IPCP: Unknown option?");
        v14 = *((_QWORD *)&xmmword_18004C860 + 1);
      }
    }
LABEL_80:
    v26 = v9[1];
    if ( (_BYTE)v26 && (unsigned __int16)v26 < (unsigned __int16)v13 )
      LOWORD(v13) = v13 - v26;
    else
      v13 = 0;
    v33 = v13;
    v9 += v26;
  }
  if ( *(_DWORD *)a1 && *(_DWORD *)(a1 + 2088) != 2 && !v12 )
  {
    if ( v14 )
    {
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        v14,
        L"IPCP: No IP option");
      v14 = *((_QWORD *)&xmmword_18004C860 + 1);
    }
    if ( !*(_DWORD *)(a1 + 148) )
    {
      if ( v14 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          v14,
          L"IPCP: RasSrvrAcquireAddress(0)...");
      v28 = RasPPPSrvrAcquireAddress(*(_QWORD *)(a1 + 8), 0, (int)a1 + 148, (int)a1 + 1264, a1 + 1778, a1 + 2120);
      v29 = v28;
      if ( *((_QWORD *)&xmmword_18004C860 + 1) )
      {
        LOWORD(v36) = 0;
        FormatRRASErrorString(&v36, L"IPCP: RasSrvrAcquireAddress done(%d)", v28);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004C860 + 1),
          &v36);
      }
      if ( v29 )
        return v29;
    }
    if ( !a6 )
    {
      v30 = *(_DWORD *)(a1 + 148);
      *(_WORD *)v7 = 1539;
      *(_DWORD *)((char *)v7 + 2) = v30;
      LOWORD(v7) = (_WORD)v7 + 6;
      *v8 = 1;
    }
  }
  if ( *v8 )
  {
    v31 = v35;
    v32 = (_WORD)v7 - (_WORD)v35;
    *v35 = (a6 != 0) + 3;
    v31[2] = HIBYTE(v32);
    v31[3] = v32;
  }
  return 0;
}

```

## disassembly

```asm
0x18001f06c  mov     [rsp-8+arg_18], rbx
0x18001f071  push    rbp
0x18001f072  push    rsi
0x18001f073  push    rdi
0x18001f074  push    r12
0x18001f076  push    r13
0x18001f078  push    r14
0x18001f07a  push    r15
0x18001f07c  lea     rbp, [rsp-760h]
0x18001f084  sub     rsp, 860h
0x18001f08b  mov     rax, cs:__security_cookie
0x18001f092  xor     rax, rsp
0x18001f095  mov     [rbp+790h+var_40], rax
0x18001f09c  movzx   r14d, byte ptr [rdx+3]
0x18001f0a1  lea     rdi, [r8+4]
0x18001f0a5  mov     r12, [rbp+790h+arg_20]
0x18001f0ac  lea     r15, [rdx+4]
0x18001f0b0  mov     rsi, rcx
0x18001f0b3  mov     [rsp+890h+var_848], r8
0x18001f0b8  movzx   ecx, byte ptr [rdx+2]
0x18001f0bc  mov     eax, 100h
0x18001f0c1  imul    ecx, eax
0x18001f0c4  sub     r14w, 4
0x18001f0c9  xor     eax, eax
0x18001f0cb  mov     [rsp+890h+var_858], r12
0x18001f0d0  xor     edx, edx; Val
0x18001f0d2  mov     [rsp+890h+var_850], rdi
0x18001f0d7  mov     r8d, 7FCh; Size
0x18001f0dd  mov     [rsp+890h+var_840], eax
0x18001f0e1  xor     r13d, r13d
0x18001f0e4  add     r14w, cx
0x18001f0e8  lea     rcx, [rsp+890h+var_83C]; void *
0x18001f0ed  mov     [rsp+890h+var_860], r14d
0x18001f0f2  call    memset_0
0x18001f0f7  mov     rbx, qword ptr cs:xmmword_18004C860+8
0x18001f0fe  test    rbx, rbx
0x18001f101  jz      short loc_18001F127
0x18001f103  mov     rcx, cs:gRasIpcpEtwContext
0x18001f10a  lea     r8, aIpcpNakcheck; "IPCP: NakCheck"
0x18001f111  mov     rax, cs:gRasIpcpTemplateFunc
0x18001f118  mov     rdx, rbx
0x18001f11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f120  mov     rbx, qword ptr cs:xmmword_18004C860+8
0x18001f127  mov     [r12], r13d
0x18001f12b  mov     r10d, 1
0x18001f131  mov     r11d, 2
0x18001f137  cmp     r14w, r11w
0x18001f13b  jb      loc_18001F669
0x18001f141  movzx   r9d, byte ptr [r15+1]
0x18001f146  cmp     r14w, r9w
0x18001f14a  jb      loc_18001F65F
0x18001f150  cmp     [r15], r11b
0x18001f153  jnz     loc_18001F242
0x18001f159  movzx   edx, byte ptr [r15+2]
0x18001f15e  mov     ecx, 100h
0x18001f163  movzx   r8d, byte ptr [r15+3]
0x18001f168  imul    edx, ecx
0x18001f16b  add     r8w, dx
0x18001f16f  cmp     r8w, 2Dh ; '-'
0x18001f174  jnz     short loc_18001F1BD
0x18001f176  cmp     r9b, 6
0x18001f17a  jnz     loc_18001F65F
0x18001f180  mov     cl, [r15+4]
0x18001f184  cmp     cl, [rsi+0AEh]
0x18001f18a  ja      short loc_18001F196
0x18001f18c  xor     eax, eax
0x18001f18e  mov     [rsi+0AEh], cl
0x18001f194  jmp     short loc_18001F199
0x18001f196  mov     eax, r10d
0x18001f199  cmp     byte ptr [rsi+0AFh], 0
0x18001f1a0  mov     cl, [r15+5]
0x18001f1a4  jz      short loc_18001F1AE
0x18001f1a6  mov     [rsi+0AFh], cl
0x18001f1ac  jmp     short loc_18001F1B4
0x18001f1ae  test    cl, cl
0x18001f1b0  cmovnz  eax, r10d
0x18001f1b4  test    eax, eax
0x18001f1b6  jnz     short loc_18001F1BD
0x18001f1b8  mov     eax, r10d
0x18001f1bb  jmp     short loc_18001F237
0x18001f1bd  test    rbx, rbx
0x18001f1c0  jz      short loc_18001F1EC
0x18001f1c2  mov     rcx, cs:gRasIpcpEtwContext
0x18001f1c9  lea     r8, aIpcpNakingIpCo; "IPCP: Naking IP compression"
0x18001f1d0  mov     rax, cs:gRasIpcpTemplateFunc
0x18001f1d7  mov     rdx, rbx
0x18001f1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1df  mov     rbx, qword ptr cs:xmmword_18004C860+8
0x18001f1e6  mov     r10d, 1
0x18001f1ec  cmp     [rbp+790h+arg_28], 0
0x18001f1f3  mov     [r12], r10d
0x18001f1f7  jz      short loc_18001F211
0x18001f1f9  movzx   r8d, byte ptr [r15+1]; Size
0x18001f1fe  mov     rdx, r15; Src
0x18001f201  mov     rcx, rdi; void *
0x18001f204  call    memcpy_0
0x18001f209  mov     r10d, 1
0x18001f20f  jmp     short loc_18001F235
0x18001f211  mov     dword ptr [rdi], 2D000602h
0x18001f217  mov     al, [rsi+0AEh]
0x18001f21d  mov     [rdi+4], al
0x18001f220  mov     al, [rsi+0AFh]
0x18001f226  mov     [rdi+5], al
0x18001f229  movzx   eax, byte ptr [rdi+1]
0x18001f22d  add     rdi, rax
0x18001f230  mov     [rsp+890h+var_850], rdi
0x18001f235  xor     eax, eax
0x18001f237  mov     [rsi+0B4h], eax
0x18001f23d  jmp     loc_18001F632
0x18001f242  cmp     dword ptr [rsi], 0
0x18001f245  jnz     short loc_18001F254
0x18001f247  cmp     [rsi+828h], r11d
0x18001f24e  jnz     loc_18001F632
0x18001f254  movzx   ecx, byte ptr [r15]
0x18001f258  sub     ecx, 3
0x18001f25b  jz      loc_18001F2EA
0x18001f261  sub     ecx, 7Eh ; '~'
0x18001f264  jz      short loc_18001F2B1
0x18001f266  sub     ecx, 1
0x18001f269  jz      short loc_18001F2B1
0x18001f26b  sub     ecx, 1
0x18001f26e  jz      short loc_18001F2B1
0x18001f270  cmp     ecx, 1
0x18001f273  jz      short loc_18001F2B1
0x18001f275  mov     rdx, qword ptr cs:xmmword_18004C860
0x18001f27c  test    rdx, rdx
0x18001f27f  jz      loc_18001F632
0x18001f285  mov     rcx, cs:gRasIpcpEtwContext
0x18001f28c  lea     r8, aIpcpUnknownOpt; "IPCP: Unknown option?"
0x18001f293  mov     rax, cs:gRasIpcpTemplateFunc
0x18001f29a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f29f  mov     rbx, qword ptr cs:xmmword_18004C860+8
0x18001f2a6  mov     r10d, 1
0x18001f2ac  jmp     loc_18001F632
0x18001f2b1  mov     edx, [rbp+790h+arg_28]
0x18001f2b7  lea     r9, [rsp+890h+var_850]
0x18001f2bc  mov     r8, r15
0x18001f2bf  mov     rcx, rsi
0x18001f2c2  call    NakCheckNameServerOption
0x18001f2c7  mov     rdi, [rsp+890h+var_850]
0x18001f2cc  mov     r10d, 1
0x18001f2d2  mov     rbx, qword ptr cs:xmmword_18004C860+8
0x18001f2d9  test    eax, eax
0x18001f2db  jz      loc_18001F632
0x18001f2e1  mov     [r12], r10d
0x18001f2e5  jmp     loc_18001F632
0x18001f2ea  cmp     r9b, 6
0x18001f2ee  jnz     loc_18001F65F
0x18001f2f4  mov     r13d, [r15+2]
0x18001f2f8  lea     r12, [rsi+94h]
0x18001f2ff  cmp     dword ptr [r12], 0
0x18001f304  jz      loc_18001F3FF
0x18001f30a  cmp     r13d, [r12]
0x18001f30e  jz      loc_18001F62D
0x18001f314  test    r13d, r13d
0x18001f317  jnz     short loc_18001F377
0x18001f319  mov     rax, [rsp+890h+var_858]
0x18001f31e  mov     rdx, r15; Src
0x18001f321  mov     r13d, [r12]
0x18001f325  mov     rcx, rdi; void *
0x18001f328  mov     [rax], r10d
0x18001f32b  movzx   r8d, byte ptr [r15+1]; Size
0x18001f330  call    memcpy_0
0x18001f335  cmp     [rbp+790h+arg_28], 0
0x18001f33c  jnz     loc_18001F61A
0x18001f342  test    rbx, rbx
0x18001f345  jz      short loc_18001F36B
0x18001f347  mov     rcx, cs:gRasIpcpEtwContext
0x18001f34e  lea     r8, aIpcpNakingIp; "IPCP: Naking IP"
0x18001f355  mov     rax, cs:gRasIpcpTemplateFunc
0x18001f35c  mov     rdx, rbx
0x18001f35f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f364  mov     rbx, qword ptr cs:xmmword_18004C860+8
0x18001f36b  mov     eax, [r12]
0x18001f36f  mov     [rdi+2], eax
0x18001f372  jmp     loc_18001F61A
0x18001f377  test    rbx, rbx
0x18001f37a  jz      short loc_18001F399
0x18001f37c  mov     rcx, cs:gRasIpcpEtwContext
0x18001f383  lea     r8, aIpcpRassrvrrel_0; "IPCP: RasSrvrReleaseAddress..."
0x18001f38a  mov     rax, cs:gRasIpcpTemplateFunc
0x18001f391  mov     rdx, rbx
0x18001f394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f399  mov     ecx, [r12]
0x18001f39d  lea     r9, [rsi+848h]
0x18001f3a4  lea     r8, [rsi+6F2h]
0x18001f3ab  mov     dword ptr [rsp+890h+var_870], 0
0x18001f3b3  lea     rdx, [rsi+4F0h]
0x18001f3ba  call    RasPPPSrvrReleaseAddress
0x18001f3bf  mov     rbx, qword ptr cs:xmmword_18004C860+8
0x18001f3c6  test    rbx, rbx
0x18001f3c9  jz      short loc_18001F3EF
0x18001f3cb  mov     rcx, cs:gRasIpcpEtwContext
0x18001f3d2  lea     r8, aIpcpRassrvrrel_1; "IPCP: RasSrvrReleaseAddress done"
0x18001f3d9  mov     rax, cs:gRasIpcpTemplateFunc
0x18001f3e0  mov     rdx, rbx
0x18001f3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3e8  mov     rbx, qword ptr cs:xmmword_18004C860+8
0x18001f3ef  mov     dword ptr [r12], 0
0x18001f3f7  mov     r11d, 2
0x18001f3fd  jmp     short loc_18001F404
0x18001f3ff  test    r13d, r13d
0x18001f402  jz      short loc_18001F445
0x18001f404  cmp     [rsi+828h], r11d
0x18001f40b  jz      short loc_18001F445
0x18001f40d  cmp     dword ptr [rsi+98h], 0FEFFFFFFh
0x18001f417  jnz     short loc_18001F445
0x18001f419  test    rbx, rbx
0x18001f41c  jz      short loc_18001F442
0x18001f41e  mov     rcx, cs:gRasIpcpEtwContext
0x18001f425  lea     r8, aIpcpClientsNot; "IPCP: Clients not allowed to request IP"...
0x18001f42c  mov     rax, cs:gRasIpcpTemplateFunc
0x18001f433  mov     rdx, rbx
0x18001f436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f43b  mov     rbx, qword ptr cs:xmmword_18004C860+8
0x18001f442  xor     r13d, r13d
0x18001f445  test    rbx, rbx
0x18001f448  jz      short loc_18001F484
0x18001f44a  xor     eax, eax
0x18001f44c  lea     rdx, aIpcpRassrvracq_1; "IPCP: RasSrvrAcquireAddress(%08x)..."
0x18001f453  mov     r8d, r13d
0x18001f456  mov     word ptr [rsp+890h+var_840], ax
0x18001f45b  lea     rcx, [rsp+890h+var_840]
0x18001f460  call    FormatRRASErrorString
0x18001f465  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001f46c  lea     r8, [rsp+890h+var_840]
0x18001f471  mov     rcx, cs:gRasIpcpEtwContext
0x18001f478  mov     rax, cs:gRasIpcpTemplateFunc
0x18001f47f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f484  mov     ecx, [rsi+98h]
0x18001f48a  lea     r9, [rsi+4F0h]
0x18001f491  mov     edx, r13d
0x18001f494  mov     r8, r12
0x18001f497  lea     eax, [rcx+1000001h]
0x18001f49d  test    eax, 0FEFFFFFFh
0x18001f4a2  lea     rax, [rsi+848h]
0x18001f4a9  mov     [rsp+890h+var_868], rax
0x18001f4ae  cmovnz  edx, ecx
0x18001f4b1  lea     rcx, [rsi+6F2h]
0x18001f4b8  mov     [rsp+890h+var_870], rcx
0x18001f4bd  mov     rcx, [rsi+8]
0x18001f4c1  call    RasPPPSrvrAcquireAddress
0x18001f4c6  mov     rbx, qword ptr cs:xmmword_18004C860+8
0x18001f4cd  mov     r14d, eax
0x18001f4d0  test    rbx, rbx
0x18001f4d3  jz      short loc_18001F516
0x18001f4d5  xor     ecx, ecx
0x18001f4d7  lea     rdx, aIpcpRassrvracq_0; "IPCP: RasSrvrAcquireAddress done(%d)"
0x18001f4de  mov     word ptr [rsp+890h+var_840], cx
0x18001f4e3  mov     r8d, eax
0x18001f4e6  lea     rcx, [rsp+890h+var_840]
0x18001f4eb  call    FormatRRASErrorString
0x18001f4f0  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001f4f7  lea     r8, [rsp+890h+var_840]
0x18001f4fc  mov     rcx, cs:gRasIpcpEtwContext
0x18001f503  mov     rax, cs:gRasIpcpTemplateFunc
0x18001f50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f50f  mov     rbx, qword ptr cs:xmmword_18004C860+8
0x18001f516  test    r14d, r14d
0x18001f519  jnz     loc_18001F657
0x18001f51f  test    r13d, r13d
0x18001f522  jz      short loc_18001F594
0x18001f524  test    rbx, rbx
0x18001f527  jz      short loc_18001F54D
0x18001f529  mov     rcx, cs:gRasIpcpEtwContext
0x18001f530  lea     r8, aIpcpHardIpRequ; "IPCP: Hard IP requested"
0x18001f537  mov     rax, cs:gRasIpcpTemplateFunc
0x18001f53e  mov     rdx, rbx
0x18001f541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f546  mov     rbx, qword ptr cs:xmmword_18004C860+8
0x18001f54d  cmp     r13d, [r12]
0x18001f551  jnz     short loc_18001F586
0x18001f553  test    rbx, rbx
0x18001f556  jz      short loc_18001F57C
0x18001f558  mov     rcx, cs:gRasIpcpEtwContext
0x18001f55f  lea     r8, aIpcpAcceptingI; "IPCP: Accepting IP"
0x18001f566  mov     rax, cs:gRasIpcpTemplateFunc
0x18001f56d  mov     rdx, rbx
0x18001f570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f575  mov     rbx, qword ptr cs:xmmword_18004C860+8
0x18001f57c  mov     r14d, [rsp+890h+var_860]
0x18001f581  jmp     loc_18001F627
0x18001f586  test    rbx, rbx
0x18001f589  jz      short loc_18001F5BD
0x18001f58b  lea     r8, aIpcp3rdPartyDl; "IPCP: 3rd party DLL changed IP"
0x18001f592  jmp     short loc_18001F5A0
0x18001f594  test    rbx, rbx
0x18001f597  jz      short loc_18001F5BD
0x18001f599  lea     r8, aIpcpServerIpRe; "IPCP: Server IP requested"
0x18001f5a0  mov     rcx, cs:gRasIpcpEtwContext
0x18001f5a7  mov     rdx, rbx
0x18001f5aa  mov     rax, cs:gRasIpcpTemplateFunc
0x18001f5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5b6  mov     rbx, qword ptr cs:xmmword_18004C860+8
0x18001f5bd  mov     rax, [rsp+890h+var_858]
0x18001f5c2  mov     rdx, r15; Src
0x18001f5c5  mov     r13d, [r12]
0x18001f5c9  mov     rcx, rdi; void *
0x18001f5cc  mov     dword ptr [rax], 1
0x18001f5d2  movzx   r8d, byte ptr [r15+1]; Size
  ... truncated ...
```
