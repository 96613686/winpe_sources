# NakCheck

- ea: `0x18001fc1c`
- end: `0x180020387`
- name: `NakCheck`
- size: `1899`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, __int64, __int64, _DWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e830`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001870c`
- `0x180018854`
- `0x18001fc1c`
- `0x180020390`
- `0x18002b0dc`
- `0x180033a80`
- `0x180034010`

## string_xrefs

- `0x18001fd79`: `IPCP: Naking IP compression`
- `0x18001fffc`: `IPCP: RasSrvrAcquireAddress(%08x)...`
- `0x180020087`: `IPCP: RasSrvrAcquireAddress done(%d)`
- `0x1800202cf`: `IPCP: RasSrvrAcquireAddress done(%d)`
- `0x18002013b`: `IPCP: 3rd party DLL changed IP`
- `0x18002027e`: `IPCP: RasSrvrAcquireAddress(0)...`

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
  v14 = *((_QWORD *)&xmmword_18004D860 + 1);
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      L"IPCP: NakCheck");
    v14 = *((_QWORD *)&xmmword_18004D860 + 1);
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
          v14 = *((_QWORD *)&xmmword_18004D860 + 1);
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
                v14 = *((_QWORD *)&xmmword_18004D860 + 1);
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
          RasPPPSrvrReleaseAddress(*v21, a1 + 1264, a1 + 1778, (__int128 *)(a1 + 2120), 0);
          v14 = *((_QWORD *)&xmmword_18004D860 + 1);
          if ( *((_QWORD *)&xmmword_18004D860 + 1) )
          {
            ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
              gRasIpcpEtwContext,
              *((_QWORD *)&xmmword_18004D860 + 1),
              L"IPCP: RasSrvrReleaseAddress done");
            v14 = *((_QWORD *)&xmmword_18004D860 + 1);
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
              v14 = *((_QWORD *)&xmmword_18004D860 + 1);
            }
            v12 = 0;
          }
LABEL_54:
          if ( v14 )
          {
            LOWORD(v36) = 0;
            FormatRRASErrorString((wchar_t *)&v36, L"IPCP: RasSrvrAcquireAddress(%08x)...", v12);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
              gRasIpcpEtwContext,
              *((_QWORD *)&xmmword_18004D860 + 1),
              &v36);
          }
          v22 = v12;
          if ( ((*(_DWORD *)(a1 + 152) + 16777217) & 0xFEFFFFFF) != 0 )
            v22 = *(_DWORD *)(a1 + 152);
          v23 = RasPPPSrvrAcquireAddress(
                  *(_QWORD *)(a1 + 8),
                  v22,
                  a1 + 148,
                  a1 + 1264,
                  a1 + 1778,
                  (__int128 *)(a1 + 2120));
          v14 = *((_QWORD *)&xmmword_18004D860 + 1);
          v24 = v23;
          if ( *((_QWORD *)&xmmword_18004D860 + 1) )
          {
            LOWORD(v36) = 0;
            FormatRRASErrorString((wchar_t *)&v36, L"IPCP: RasSrvrAcquireAddress done(%d)", v23);
            ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
              gRasIpcpEtwContext,
              *((_QWORD *)&xmmword_18004D860 + 1),
              &v36);
            v14 = *((_QWORD *)&xmmword_18004D860 + 1);
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
              v14 = *((_QWORD *)&xmmword_18004D860 + 1);
            }
            if ( v12 == *v21 )
            {
              if ( v14 )
              {
                ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
                  gRasIpcpEtwContext,
                  v14,
                  L"IPCP: Accepting IP");
                v14 = *((_QWORD *)&xmmword_18004D860 + 1);
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
            v14 = *((_QWORD *)&xmmword_18004D860 + 1);
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
              v14 = *((_QWORD *)&xmmword_18004D860 + 1);
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
        v14 = *((_QWORD *)&xmmword_18004D860 + 1);
        if ( v20 )
          *v8 = 1;
      }
      else if ( (_QWORD)xmmword_18004D860 )
      {
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          xmmword_18004D860,
          L"IPCP: Unknown option?");
        v14 = *((_QWORD *)&xmmword_18004D860 + 1);
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
      v14 = *((_QWORD *)&xmmword_18004D860 + 1);
    }
    if ( !*(_DWORD *)(a1 + 148) )
    {
      if ( v14 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          v14,
          L"IPCP: RasSrvrAcquireAddress(0)...");
      v28 = RasPPPSrvrAcquireAddress(*(_QWORD *)(a1 + 8), 0, a1 + 148, a1 + 1264, a1 + 1778, (__int128 *)(a1 + 2120));
      v29 = v28;
      if ( *((_QWORD *)&xmmword_18004D860 + 1) )
      {
        LOWORD(v36) = 0;
        FormatRRASErrorString((wchar_t *)&v36, L"IPCP: RasSrvrAcquireAddress done(%d)", v28);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004D860 + 1),
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
0x18001fc1c  mov     [rsp-8+arg_18], rbx
0x18001fc21  push    rbp
0x18001fc22  push    rsi
0x18001fc23  push    rdi
0x18001fc24  push    r12
0x18001fc26  push    r13
0x18001fc28  push    r14
0x18001fc2a  push    r15
0x18001fc2c  lea     rbp, [rsp-760h]
0x18001fc34  sub     rsp, 860h
0x18001fc3b  mov     rax, cs:__security_cookie
0x18001fc42  xor     rax, rsp
0x18001fc45  mov     [rbp+790h+var_40], rax
0x18001fc4c  movzx   r14d, byte ptr [rdx+3]
0x18001fc51  lea     rdi, [r8+4]
0x18001fc55  mov     r12, [rbp+790h+arg_20]
0x18001fc5c  lea     r15, [rdx+4]
0x18001fc60  mov     rsi, rcx
0x18001fc63  mov     [rsp+890h+var_848], r8
0x18001fc68  movzx   ecx, byte ptr [rdx+2]
0x18001fc6c  mov     eax, 100h
0x18001fc71  imul    ecx, eax
0x18001fc74  sub     r14w, 4
0x18001fc79  xor     eax, eax
0x18001fc7b  mov     [rsp+890h+var_858], r12
0x18001fc80  xor     edx, edx; Val
0x18001fc82  mov     [rsp+890h+var_850], rdi
0x18001fc87  mov     r8d, 7FCh; Size
0x18001fc8d  mov     [rsp+890h+var_840], eax
0x18001fc91  xor     r13d, r13d
0x18001fc94  add     r14w, cx
0x18001fc98  lea     rcx, [rsp+890h+var_83C]; void *
0x18001fc9d  mov     [rsp+890h+var_860], r14d
0x18001fca2  call    memset_0
0x18001fca7  mov     rbx, qword ptr cs:xmmword_18004D860+8
0x18001fcae  test    rbx, rbx
0x18001fcb1  jz      short loc_18001FCD7
0x18001fcb3  mov     rcx, cs:gRasIpcpEtwContext
0x18001fcba  lea     r8, aIpcpNakcheck; "IPCP: NakCheck"
0x18001fcc1  mov     rax, cs:gRasIpcpTemplateFunc
0x18001fcc8  mov     rdx, rbx
0x18001fccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcd0  mov     rbx, qword ptr cs:xmmword_18004D860+8
0x18001fcd7  mov     [r12], r13d
0x18001fcdb  mov     r10d, 1
0x18001fce1  mov     r11d, 2
0x18001fce7  cmp     r14w, r11w
0x18001fceb  jb      loc_180020219
0x18001fcf1  movzx   r9d, byte ptr [r15+1]
0x18001fcf6  cmp     r14w, r9w
0x18001fcfa  jb      loc_18002020F
0x18001fd00  cmp     [r15], r11b
0x18001fd03  jnz     loc_18001FDF2
0x18001fd09  movzx   edx, byte ptr [r15+2]
0x18001fd0e  mov     ecx, 100h
0x18001fd13  movzx   r8d, byte ptr [r15+3]
0x18001fd18  imul    edx, ecx
0x18001fd1b  add     r8w, dx
0x18001fd1f  cmp     r8w, 2Dh ; '-'
0x18001fd24  jnz     short loc_18001FD6D
0x18001fd26  cmp     r9b, 6
0x18001fd2a  jnz     loc_18002020F
0x18001fd30  mov     cl, [r15+4]
0x18001fd34  cmp     cl, [rsi+0AEh]
0x18001fd3a  ja      short loc_18001FD46
0x18001fd3c  xor     eax, eax
0x18001fd3e  mov     [rsi+0AEh], cl
0x18001fd44  jmp     short loc_18001FD49
0x18001fd46  mov     eax, r10d
0x18001fd49  cmp     byte ptr [rsi+0AFh], 0
0x18001fd50  mov     cl, [r15+5]
0x18001fd54  jz      short loc_18001FD5E
0x18001fd56  mov     [rsi+0AFh], cl
0x18001fd5c  jmp     short loc_18001FD64
0x18001fd5e  test    cl, cl
0x18001fd60  cmovnz  eax, r10d
0x18001fd64  test    eax, eax
0x18001fd66  jnz     short loc_18001FD6D
0x18001fd68  mov     eax, r10d
0x18001fd6b  jmp     short loc_18001FDE7
0x18001fd6d  test    rbx, rbx
0x18001fd70  jz      short loc_18001FD9C
0x18001fd72  mov     rcx, cs:gRasIpcpEtwContext
0x18001fd79  lea     r8, aIpcpNakingIpCo; "IPCP: Naking IP compression"
0x18001fd80  mov     rax, cs:gRasIpcpTemplateFunc
0x18001fd87  mov     rdx, rbx
0x18001fd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd8f  mov     rbx, qword ptr cs:xmmword_18004D860+8
0x18001fd96  mov     r10d, 1
0x18001fd9c  cmp     [rbp+790h+arg_28], 0
0x18001fda3  mov     [r12], r10d
0x18001fda7  jz      short loc_18001FDC1
0x18001fda9  movzx   r8d, byte ptr [r15+1]; Size
0x18001fdae  mov     rdx, r15; Src
0x18001fdb1  mov     rcx, rdi; void *
0x18001fdb4  call    memcpy_0
0x18001fdb9  mov     r10d, 1
0x18001fdbf  jmp     short loc_18001FDE5
0x18001fdc1  mov     dword ptr [rdi], 2D000602h
0x18001fdc7  mov     al, [rsi+0AEh]
0x18001fdcd  mov     [rdi+4], al
0x18001fdd0  mov     al, [rsi+0AFh]
0x18001fdd6  mov     [rdi+5], al
0x18001fdd9  movzx   eax, byte ptr [rdi+1]
0x18001fddd  add     rdi, rax
0x18001fde0  mov     [rsp+890h+var_850], rdi
0x18001fde5  xor     eax, eax
0x18001fde7  mov     [rsi+0B4h], eax
0x18001fded  jmp     loc_1800201E2
0x18001fdf2  cmp     dword ptr [rsi], 0
0x18001fdf5  jnz     short loc_18001FE04
0x18001fdf7  cmp     [rsi+828h], r11d
0x18001fdfe  jnz     loc_1800201E2
0x18001fe04  movzx   ecx, byte ptr [r15]
0x18001fe08  sub     ecx, 3
0x18001fe0b  jz      loc_18001FE9A
0x18001fe11  sub     ecx, 7Eh ; '~'
0x18001fe14  jz      short loc_18001FE61
0x18001fe16  sub     ecx, 1
0x18001fe19  jz      short loc_18001FE61
0x18001fe1b  sub     ecx, 1
0x18001fe1e  jz      short loc_18001FE61
0x18001fe20  cmp     ecx, 1
0x18001fe23  jz      short loc_18001FE61
0x18001fe25  mov     rdx, qword ptr cs:xmmword_18004D860
0x18001fe2c  test    rdx, rdx
0x18001fe2f  jz      loc_1800201E2
0x18001fe35  mov     rcx, cs:gRasIpcpEtwContext
0x18001fe3c  lea     r8, aIpcpUnknownOpt; "IPCP: Unknown option?"
0x18001fe43  mov     rax, cs:gRasIpcpTemplateFunc
0x18001fe4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe4f  mov     rbx, qword ptr cs:xmmword_18004D860+8
0x18001fe56  mov     r10d, 1
0x18001fe5c  jmp     loc_1800201E2
0x18001fe61  mov     edx, [rbp+790h+arg_28]
0x18001fe67  lea     r9, [rsp+890h+var_850]
0x18001fe6c  mov     r8, r15
0x18001fe6f  mov     rcx, rsi
0x18001fe72  call    NakCheckNameServerOption
0x18001fe77  mov     rdi, [rsp+890h+var_850]
0x18001fe7c  mov     r10d, 1
0x18001fe82  mov     rbx, qword ptr cs:xmmword_18004D860+8
0x18001fe89  test    eax, eax
0x18001fe8b  jz      loc_1800201E2
0x18001fe91  mov     [r12], r10d
0x18001fe95  jmp     loc_1800201E2
0x18001fe9a  cmp     r9b, 6
0x18001fe9e  jnz     loc_18002020F
0x18001fea4  mov     r13d, [r15+2]
0x18001fea8  lea     r12, [rsi+94h]
0x18001feaf  cmp     dword ptr [r12], 0
0x18001feb4  jz      loc_18001FFAF
0x18001feba  cmp     r13d, [r12]
0x18001febe  jz      loc_1800201DD
0x18001fec4  test    r13d, r13d
0x18001fec7  jnz     short loc_18001FF27
0x18001fec9  mov     rax, [rsp+890h+var_858]
0x18001fece  mov     rdx, r15; Src
0x18001fed1  mov     r13d, [r12]
0x18001fed5  mov     rcx, rdi; void *
0x18001fed8  mov     [rax], r10d
0x18001fedb  movzx   r8d, byte ptr [r15+1]; Size
0x18001fee0  call    memcpy_0
0x18001fee5  cmp     [rbp+790h+arg_28], 0
0x18001feec  jnz     loc_1800201CA
0x18001fef2  test    rbx, rbx
0x18001fef5  jz      short loc_18001FF1B
0x18001fef7  mov     rcx, cs:gRasIpcpEtwContext
0x18001fefe  lea     r8, aIpcpNakingIp; "IPCP: Naking IP"
0x18001ff05  mov     rax, cs:gRasIpcpTemplateFunc
0x18001ff0c  mov     rdx, rbx
0x18001ff0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff14  mov     rbx, qword ptr cs:xmmword_18004D860+8
0x18001ff1b  mov     eax, [r12]
0x18001ff1f  mov     [rdi+2], eax
0x18001ff22  jmp     loc_1800201CA
0x18001ff27  test    rbx, rbx
0x18001ff2a  jz      short loc_18001FF49
0x18001ff2c  mov     rcx, cs:gRasIpcpEtwContext
0x18001ff33  lea     r8, aIpcpRassrvrrel_0; "IPCP: RasSrvrReleaseAddress..."
0x18001ff3a  mov     rax, cs:gRasIpcpTemplateFunc
0x18001ff41  mov     rdx, rbx
0x18001ff44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff49  mov     ecx, [r12]
0x18001ff4d  lea     r9, [rsi+848h]
0x18001ff54  lea     r8, [rsi+6F2h]
0x18001ff5b  mov     dword ptr [rsp+890h+var_870], 0
0x18001ff63  lea     rdx, [rsi+4F0h]
0x18001ff6a  call    RasPPPSrvrReleaseAddress
0x18001ff6f  mov     rbx, qword ptr cs:xmmword_18004D860+8
0x18001ff76  test    rbx, rbx
0x18001ff79  jz      short loc_18001FF9F
0x18001ff7b  mov     rcx, cs:gRasIpcpEtwContext
0x18001ff82  lea     r8, aIpcpRassrvrrel_1; "IPCP: RasSrvrReleaseAddress done"
0x18001ff89  mov     rax, cs:gRasIpcpTemplateFunc
0x18001ff90  mov     rdx, rbx
0x18001ff93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff98  mov     rbx, qword ptr cs:xmmword_18004D860+8
0x18001ff9f  mov     dword ptr [r12], 0
0x18001ffa7  mov     r11d, 2
0x18001ffad  jmp     short loc_18001FFB4
0x18001ffaf  test    r13d, r13d
0x18001ffb2  jz      short loc_18001FFF5
0x18001ffb4  cmp     [rsi+828h], r11d
0x18001ffbb  jz      short loc_18001FFF5
0x18001ffbd  cmp     dword ptr [rsi+98h], 0FEFFFFFFh
0x18001ffc7  jnz     short loc_18001FFF5
0x18001ffc9  test    rbx, rbx
0x18001ffcc  jz      short loc_18001FFF2
0x18001ffce  mov     rcx, cs:gRasIpcpEtwContext
0x18001ffd5  lea     r8, aIpcpClientsNot; "IPCP: Clients not allowed to request IP"...
0x18001ffdc  mov     rax, cs:gRasIpcpTemplateFunc
0x18001ffe3  mov     rdx, rbx
0x18001ffe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffeb  mov     rbx, qword ptr cs:xmmword_18004D860+8
0x18001fff2  xor     r13d, r13d
0x18001fff5  test    rbx, rbx
0x18001fff8  jz      short loc_180020034
0x18001fffa  xor     eax, eax
0x18001fffc  lea     rdx, aIpcpRassrvracq_1; "IPCP: RasSrvrAcquireAddress(%08x)..."
0x180020003  mov     r8d, r13d
0x180020006  mov     word ptr [rsp+890h+var_840], ax
0x18002000b  lea     rcx, [rsp+890h+var_840]
0x180020010  call    FormatRRASErrorString
0x180020015  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18002001c  lea     r8, [rsp+890h+var_840]
0x180020021  mov     rcx, cs:gRasIpcpEtwContext
0x180020028  mov     rax, cs:gRasIpcpTemplateFunc
0x18002002f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020034  mov     ecx, [rsi+98h]
0x18002003a  lea     r9, [rsi+4F0h]
0x180020041  mov     edx, r13d
0x180020044  mov     r8, r12
0x180020047  lea     eax, [rcx+1000001h]
0x18002004d  test    eax, 0FEFFFFFFh
0x180020052  lea     rax, [rsi+848h]
0x180020059  mov     [rsp+890h+var_868], rax
0x18002005e  cmovnz  edx, ecx
0x180020061  lea     rcx, [rsi+6F2h]
0x180020068  mov     [rsp+890h+var_870], rcx
0x18002006d  mov     rcx, [rsi+8]
0x180020071  call    RasPPPSrvrAcquireAddress
0x180020076  mov     rbx, qword ptr cs:xmmword_18004D860+8
0x18002007d  mov     r14d, eax
0x180020080  test    rbx, rbx
0x180020083  jz      short loc_1800200C6
0x180020085  xor     ecx, ecx
0x180020087  lea     rdx, aIpcpRassrvracq_0; "IPCP: RasSrvrAcquireAddress done(%d)"
0x18002008e  mov     word ptr [rsp+890h+var_840], cx
0x180020093  mov     r8d, eax
0x180020096  lea     rcx, [rsp+890h+var_840]
0x18002009b  call    FormatRRASErrorString
0x1800200a0  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x1800200a7  lea     r8, [rsp+890h+var_840]
0x1800200ac  mov     rcx, cs:gRasIpcpEtwContext
0x1800200b3  mov     rax, cs:gRasIpcpTemplateFunc
0x1800200ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200bf  mov     rbx, qword ptr cs:xmmword_18004D860+8
0x1800200c6  test    r14d, r14d
0x1800200c9  jnz     loc_180020207
0x1800200cf  test    r13d, r13d
0x1800200d2  jz      short loc_180020144
0x1800200d4  test    rbx, rbx
0x1800200d7  jz      short loc_1800200FD
0x1800200d9  mov     rcx, cs:gRasIpcpEtwContext
0x1800200e0  lea     r8, aIpcpHardIpRequ; "IPCP: Hard IP requested"
0x1800200e7  mov     rax, cs:gRasIpcpTemplateFunc
0x1800200ee  mov     rdx, rbx
0x1800200f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200f6  mov     rbx, qword ptr cs:xmmword_18004D860+8
0x1800200fd  cmp     r13d, [r12]
0x180020101  jnz     short loc_180020136
0x180020103  test    rbx, rbx
0x180020106  jz      short loc_18002012C
0x180020108  mov     rcx, cs:gRasIpcpEtwContext
0x18002010f  lea     r8, aIpcpAcceptingI; "IPCP: Accepting IP"
0x180020116  mov     rax, cs:gRasIpcpTemplateFunc
0x18002011d  mov     rdx, rbx
0x180020120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020125  mov     rbx, qword ptr cs:xmmword_18004D860+8
0x18002012c  mov     r14d, [rsp+890h+var_860]
0x180020131  jmp     loc_1800201D7
0x180020136  test    rbx, rbx
0x180020139  jz      short loc_18002016D
0x18002013b  lea     r8, aIpcp3rdPartyDl; "IPCP: 3rd party DLL changed IP"
0x180020142  jmp     short loc_180020150
0x180020144  test    rbx, rbx
0x180020147  jz      short loc_18002016D
0x180020149  lea     r8, aIpcpServerIpRe; "IPCP: Server IP requested"
0x180020150  mov     rcx, cs:gRasIpcpEtwContext
0x180020157  mov     rdx, rbx
0x18002015a  mov     rax, cs:gRasIpcpTemplateFunc
0x180020161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020166  mov     rbx, qword ptr cs:xmmword_18004D860+8
0x18002016d  mov     rax, [rsp+890h+var_858]
0x180020172  mov     rdx, r15; Src
0x180020175  mov     r13d, [r12]
0x180020179  mov     rcx, rdi; void *
0x18002017c  mov     dword ptr [rax], 1
0x180020182  movzx   r8d, byte ptr [r15+1]; Size
  ... truncated ...
```
