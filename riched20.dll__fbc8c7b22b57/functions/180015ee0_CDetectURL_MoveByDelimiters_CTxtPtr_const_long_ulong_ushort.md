# CDetectURL::MoveByDelimiters(CTxtPtr const &,long,ulong,ushort *)

- ea: `0x180015ee0`
- end: `0x180016468`
- name: `?MoveByDelimiters@CDetectURL@@AEAAJAEBVCTxtPtr@@JKPEAG@Z`
- size: `1416`
- prototype: `__int64 __fastcall(CDetectURL *__hidden this, const struct CTxtPtr *, int, unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800159d8`
- `0x180021c30`

## callees

- `0x180015ee0`
- `0x18001e3e0`
- `0x18001f230`
- `0x18008f3bc`
- `0x1800903d4`
- `0x180093c00`

## import_xrefs

- `KERNEL32!GetStringTypeExW` at `0x1800161a6`
- `KERNEL32!GetStringTypeExW` at `0x1800161a6`
- `KERNEL32!GetStringTypeExA` at `0x180016440`
- `KERNEL32!GetStringTypeExA` at `0x180016440`

## pseudocode

```c
__int64 __fastcall CDetectURL::MoveByDelimiters(
        CDetectURL *this,
        const struct CTxtPtr *a2,
        int a3,
        char a4,
        unsigned __int16 *a5)
{
  __int128 v5; // xmm0
  unsigned int v6; // r13d
  __int128 v7; // xmm1
  int v8; // r15d
  int v9; // r10d
  int v10; // r11d
  unsigned __int16 v11; // r14
  int v12; // ebp
  int v13; // ebx
  int v14; // eax
  void *v15; // rdx
  int v16; // esi
  int v17; // r9d
  __int64 v18; // rdi
  int v19; // ecx
  int v20; // eax
  int *v21; // r8
  int v22; // esi
  int v23; // r9d
  int v24; // r13d
  int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // ecx
  int v28; // ecx
  bool v29; // zf
  unsigned int v30; // r9d
  unsigned int v31; // eax
  bool v32; // zf
  int v33; // ecx
  __int64 result; // rax
  int *v35; // rax
  WCHAR SrcStr; // [rsp+30h] [rbp-2B8h] BYREF
  WORD CharType[2]; // [rsp+38h] [rbp-2B0h] BYREF
  int v38; // [rsp+3Ch] [rbp-2ACh]
  int v39; // [rsp+40h] [rbp-2A8h]
  int v40; // [rsp+44h] [rbp-2A4h]
  int v41; // [rsp+48h] [rbp-2A0h]
  int v42; // [rsp+4Ch] [rbp-29Ch]
  int v43; // [rsp+50h] [rbp-298h]
  int v44; // [rsp+54h] [rbp-294h]
  CArrayBase *v45[2]; // [rsp+58h] [rbp-290h] BYREF
  __int128 v46; // [rsp+68h] [rbp-280h]
  LPCSTR lpSrcStr[66]; // [rsp+80h] [rbp-268h] BYREF
  int cchSrc; // [rsp+290h] [rbp-58h]

  v5 = *(_OWORD *)a2;
  v6 = 0;
  v7 = *((_OWORD *)a2 + 1);
  v38 = a3;
  v40 = 0;
  v8 = 0x3FFFFFFF;
  if ( (a4 & 0x20) == 0 )
    v8 = 512;
  v9 = a3;
  v10 = a4 & 0x10;
  v39 = v10;
  v42 = a4 & 1;
  v11 = 32;
  v41 = a4 & 2;
  v44 = a4 & 4;
  v43 = a4 & 8;
  v12 = 0;
  *(_OWORD *)v45 = v5;
  v46 = v7;
  while ( 2 )
  {
    if ( v9 != 1 )
    {
      v13 = -1;
      if ( v45[0] && *((_DWORD *)v45[0] + 2) )
      {
        v20 = *((_DWORD *)v45[0] + 2);
        if ( v20 > 0 && SLODWORD(v45[1]) < v20 && *(_QWORD *)v45[0] && SLODWORD(v45[1]) >= 0 )
          v21 = (int *)(*(_QWORD *)v45[0] + *((_DWORD *)v45[0] + 4) * LODWORD(v45[1]));
        else
          v21 = 0;
        v22 = 0;
        if ( v21 )
        {
          v23 = HIDWORD(v45[1]);
          if ( HIDWORD(v45[1]) )
            goto LABEL_27;
          if ( LODWORD(v45[1]) )
          {
            v35 = (int *)CArrayBase::Elem(v45[0], LODWORD(v45[1]) - 1);
            v21 = v35;
            if ( v35 )
            {
              v23 = *v35;
LABEL_27:
              v18 = *((_QWORD *)v21 + 1) + 2LL * v23;
              v22 = v23 - v21[4] / 2;
              if ( v22 > 0 )
                v18 += 2LL * (v21[5] / 2 - *v21);
              else
                v22 = v23;
              goto LABEL_29;
            }
          }
        }
      }
      else
      {
        v22 = 0;
      }
      v18 = 0;
LABEL_29:
      v16 = v22 + 1;
      goto LABEL_30;
    }
    v13 = 0;
    if ( !v45[0] || !*((_DWORD *)v45[0] + 2) )
    {
      v16 = 0;
LABEL_69:
      v18 = 0;
      goto LABEL_30;
    }
    v14 = *((_DWORD *)v45[0] + 2);
    if ( v14 > 0 && SLODWORD(v45[1]) < v14 && *(_QWORD *)v45[0] && SLODWORD(v45[1]) >= 0 )
      v15 = (void *)(*(_QWORD *)v45[0] + *((_DWORD *)v45[0] + 4) * LODWORD(v45[1]));
    else
      v15 = 0;
    v16 = 0;
    if ( !v15 )
      goto LABEL_69;
    v17 = HIDWORD(v45[1]);
    if ( HIDWORD(v45[1]) != *(_DWORD *)v15 )
      goto LABEL_14;
    if ( SLODWORD(v45[1]) >= *((_DWORD *)v45[0] + 2) - 1 )
      goto LABEL_69;
    v15 = CArrayBase::Elem(v45[0], LODWORD(v45[1]) + 1);
    if ( v15 )
    {
      v17 = 0;
LABEL_14:
      v18 = *((_QWORD *)v15 + 1) + 2LL * v17;
      v19 = *((_DWORD *)v15 + 4);
      if ( 2 * v17 >= v19 )
      {
        v16 = *(_DWORD *)v15 - v17;
        v18 += 2LL * (*((_DWORD *)v15 + 5) / 2 - *(_DWORD *)v15);
        if ( !v16 )
          v18 = 0;
      }
      else
      {
        v16 = v19 / 2 - v17;
        if ( v19 / 2 == v17 )
          v18 = 0;
      }
      goto LABEL_30;
    }
    v18 = 0;
LABEL_30:
    if ( !v18 )
      break;
    v24 = v41;
    while ( 1 )
    {
      v25 = -v13;
      if ( v13 > 0 )
        v25 = v13;
      if ( v25 >= v16 || v12 >= v8 )
        break;
      v26 = *(unsigned __int16 *)(v18 + 2LL * v13);
      if ( v26 == 32 || v26 - 9 <= 4 || (v26 | 1) == 0x2029 )
      {
LABEL_67:
        v29 = v42 == 0;
        goto LABEL_47;
      }
      v27 = v26 - 44032;
      if ( (unsigned __int16)v26 >= 0x3000u )
      {
        if ( v27 > 0x2BFF )
          goto LABEL_67;
        SrcStr = *(_WORD *)(v18 + 2LL * v13);
      }
      else
      {
        SrcStr = *(_WORD *)(v18 + 2LL * v13);
        if ( v27 > 0x2BFF )
        {
          if ( v26 - 55296 <= 0x7FF )
          {
            v28 = (v26 - 56320 <= 0x3FF) + 1;
          }
          else
          {
            v28 = *((char *)qword_1800A6FB0
                  + 64 * (unsigned __int64)*((unsigned __int8 *)qword_1800A6FB8 + ((unsigned __int64)v26 >> 6))
                  + (v26 & 0x3F));
            if ( v28 < 0 )
            {
              CharType[0] = 0;
              if ( CW32System::_dwPlatformId == 1 )
              {
                CStrIn::CStrIn((CStrIn *)lpSrcStr, &SrcStr, 1, 0);
                GetStringTypeExA(0, 4u, lpSrcStr[0], cchSrc, CharType);
                CConvertStr::Free((CConvertStr *)lpSrcStr);
              }
              else
              {
                GetStringTypeExW(0, 4u, &SrcStr, 1, CharType);
              }
              v10 = v39;
              v9 = v38;
              goto LABEL_46;
            }
          }
          if ( ((v28 - 10) & 0xFFFFFFFB) == 0 )
            goto LABEL_67;
        }
      }
LABEL_46:
      v29 = v24 == 0;
LABEL_47:
      if ( !v29 )
        break;
      if ( (v30 = *(unsigned __int16 *)(v18 + 2LL * v13), v30 - 44032 > 0x2BFF)
        && (v31 = *((char *)qword_1800A6FB0
                  + 64 * (unsigned __int64)*((unsigned __int8 *)qword_1800A6FB8 + ((unsigned __int64)v30 >> 6))
                  + (v30 & 0x3F)),
            v31 > 2)
        && (v31 - 4 > 2 || v30 == 47)
        && (((_WORD)v30 - 60) & 0xFFFD) != 0 )
      {
        v32 = v43 == 0;
      }
      else
      {
        v32 = v44 == 0;
      }
      if ( !v32 || v10 && v11 != 32 && *a5 == v11 || (v11 == 13 || v11 == 10) && !v24 )
        break;
      v13 += v9;
      v11 = v30;
      ++v12;
    }
    if ( v9 == -1 )
    {
      ++v13;
      --v16;
    }
    v6 = v13 + v40;
    v33 = -v13;
    v40 += v13;
    if ( v13 > 0 )
      v33 = v13;
    if ( v33 >= v16 )
    {
      CTxtPtr::AdvanceCp((CTxtPtr *)v45, v13);
      v9 = v38;
      v10 = v39;
      if ( v12 < v8 )
        continue;
    }
    break;
  }
  result = v6;
  if ( a5 )
    *a5 = v11;
  return result;
}

```

## disassembly

```asm
0x180015ee0  mov     [rsp+arg_0], rbx
0x180015ee5  push    rbp
0x180015ee6  push    rsi
0x180015ee7  push    rdi
0x180015ee8  push    r12
0x180015eea  push    r13
0x180015eec  push    r14
0x180015eee  push    r15
0x180015ef0  sub     rsp, 2B0h
0x180015ef7  mov     rax, cs:__security_cookie
0x180015efe  xor     rax, rsp
0x180015f01  mov     [rsp+2E8h+var_48], rax
0x180015f09  movups  xmm0, xmmword ptr [rdx]
0x180015f0c  mov     r12, [rsp+2E8h+arg_20]
0x180015f14  xor     r13d, r13d
0x180015f17  movups  xmm1, xmmword ptr [rdx+10h]
0x180015f1b  test    r9b, 20h
0x180015f1f  mov     [rsp+2E8h+var_2AC], r8d
0x180015f24  mov     eax, 200h
0x180015f29  mov     [rsp+2E8h+var_2A4], r13d
0x180015f2e  mov     r15d, 3FFFFFFFh
0x180015f34  mov     r11d, r9d
0x180015f37  cmovz   r15d, eax
0x180015f3b  mov     r10d, r8d
0x180015f3e  and     r11d, 10h
0x180015f42  mov     eax, r9d
0x180015f45  and     eax, 1
0x180015f48  mov     [rsp+2E8h+var_2A8], r11d
0x180015f4d  mov     [rsp+2E8h+var_29C], eax
0x180015f51  mov     r14d, 20h ; ' '
0x180015f57  mov     eax, r9d
0x180015f5a  and     eax, 2
0x180015f5d  mov     [rsp+2E8h+var_2A0], eax
0x180015f61  mov     eax, r9d
0x180015f64  and     eax, 4
0x180015f67  mov     [rsp+2E8h+var_294], eax
0x180015f6b  mov     eax, r9d
0x180015f6e  and     eax, 8
0x180015f71  mov     [rsp+2E8h+var_298], eax
0x180015f75  xor     ebp, ebp
0x180015f77  movups  xmmword ptr [rsp+2E8h+var_290], xmm0
0x180015f7c  movups  [rsp+2E8h+var_280], xmm1
0x180015f81  mov     rcx, [rsp+2E8h+var_290]; this
0x180015f86  cmp     r10d, 1
0x180015f8a  jnz     loc_18001602B
0x180015f90  xor     ebx, ebx
0x180015f92  test    rcx, rcx
0x180015f95  jz      loc_1800162D5
0x180015f9b  cmp     [rcx+8], ebx
0x180015f9e  jz      loc_1800162D5
0x180015fa4  mov     eax, [rcx+8]
0x180015fa7  mov     r8d, dword ptr [rsp+2E8h+var_290+8]
0x180015fac  test    eax, eax
0x180015fae  jle     loc_1800163D7
0x180015fb4  cmp     r8d, eax
0x180015fb7  jge     loc_1800163D7
0x180015fbd  mov     r9, [rcx]
0x180015fc0  test    r9, r9
0x180015fc3  jz      loc_1800163D7
0x180015fc9  test    r8d, r8d
0x180015fcc  js      loc_1800163D7
0x180015fd2  mov     eax, r8d
0x180015fd5  imul    eax, [rcx+10h]
0x180015fd9  movsxd  rdx, eax
0x180015fdc  add     rdx, r9
0x180015fdf  xor     esi, esi
0x180015fe1  test    rdx, rdx
0x180015fe4  jz      loc_1800162D7
0x180015fea  mov     r9d, dword ptr [rsp+2E8h+var_290+0Ch]
0x180015fef  cmp     r9d, [rdx]
0x180015ff2  jz      loc_180016353
0x180015ff8  mov     rax, [rdx+8]
0x180015ffc  movsxd  rcx, r9d
0x180015fff  lea     rdi, [rax+rcx*2]
0x180016003  mov     ecx, [rdx+10h]
0x180016006  lea     eax, [r9+r9]
0x18001600a  cmp     eax, ecx
0x18001600c  jge     loc_180016308
0x180016012  mov     eax, ecx
0x180016014  cdq
0x180016015  sub     eax, edx
0x180016017  sar     eax, 1
0x180016019  mov     esi, eax
0x18001601b  xor     eax, eax
0x18001601d  sub     esi, r9d
0x180016020  test    esi, esi
0x180016022  cmovz   rdi, rax
0x180016026  jmp     loc_1800160B9
0x18001602b  mov     ebx, 0FFFFFFFFh
0x180016030  test    rcx, rcx
0x180016033  jz      loc_1800162DE
0x180016039  cmp     dword ptr [rcx+8], 0
0x18001603d  jz      loc_1800162DE
0x180016043  mov     eax, [rcx+8]
0x180016046  mov     edx, dword ptr [rsp+2E8h+var_290+8]
0x18001604a  test    eax, eax
0x18001604c  jle     loc_1800163DE
0x180016052  cmp     edx, eax
0x180016054  jge     loc_1800163DE
0x18001605a  mov     r9, [rcx]
0x18001605d  test    r9, r9
0x180016060  jz      loc_1800163DE
0x180016066  test    edx, edx
0x180016068  js      loc_1800163DE
0x18001606e  mov     eax, edx
0x180016070  imul    eax, [rcx+10h]
0x180016074  movsxd  r8, eax
0x180016077  add     r8, r9
0x18001607a  xor     esi, esi
0x18001607c  test    r8, r8
0x18001607f  jz      loc_1800162E0
0x180016085  mov     r9d, dword ptr [rsp+2E8h+var_290+0Ch]
0x18001608a  test    r9d, r9d
0x18001608d  jz      loc_1800163B4
0x180016093  mov     rax, [r8+8]
0x180016097  mov     esi, r9d
0x18001609a  movsxd  rcx, r9d
0x18001609d  lea     rdi, [rax+rcx*2]
0x1800160a1  mov     eax, [r8+10h]
0x1800160a5  cdq
0x1800160a6  sub     eax, edx
0x1800160a8  sar     eax, 1
0x1800160aa  sub     esi, eax
0x1800160ac  test    esi, esi
0x1800160ae  jg      loc_18001639D
0x1800160b4  mov     esi, r9d
0x1800160b7  inc     esi
0x1800160b9  test    rdi, rdi
0x1800160bc  jz      loc_180016284
0x1800160c2  mov     r13d, [rsp+2E8h+var_2A0]
0x1800160c7  mov     eax, ebx
0x1800160c9  neg     eax
0x1800160cb  cmovs   eax, ebx
0x1800160ce  cmp     eax, esi
0x1800160d0  jge     loc_18001625E
0x1800160d6  cmp     ebp, r15d
0x1800160d9  jge     loc_18001625E
0x1800160df  movsxd  rax, ebx
0x1800160e2  movzx   eax, word ptr [rdi+rax*2]
0x1800160e6  cmp     eax, 20h ; ' '
0x1800160e9  jz      loc_1800162CB
0x1800160ef  lea     ecx, [rax-9]
0x1800160f2  cmp     ecx, 4
0x1800160f5  jbe     loc_1800162CB
0x1800160fb  mov     ecx, eax
0x1800160fd  or      ecx, 1
0x180016100  cmp     ecx, 2029h
0x180016106  jz      loc_1800162CB
0x18001610c  mov     ecx, 3000h
0x180016111  cmp     ax, cx
0x180016114  lea     ecx, [rax-0AC00h]
0x18001611a  jnb     loc_1800162E7
0x180016120  mov     [rsp+2E8h+SrcStr], ax
0x180016125  cmp     ecx, 2BFFh
0x18001612b  jbe     loc_1800161BC
0x180016131  lea     ecx, [rax-0D800h]
0x180016137  cmp     ecx, 7FFh
0x18001613d  jbe     loc_1800163EE
0x180016143  mov     r8d, eax
0x180016146  mov     ecx, eax
0x180016148  mov     rax, cs:qword_1800A6FB8
0x18001614f  and     r8d, 3Fh
0x180016153  shr     rcx, 6
0x180016157  movzx   edx, byte ptr [rcx+rax]
0x18001615b  mov     rcx, cs:qword_1800A6FB0
0x180016162  shl     rdx, 6
0x180016166  add     rcx, rdx
0x180016169  movsx   ecx, byte ptr [r8+rcx]
0x18001616e  test    ecx, ecx
0x180016170  jns     loc_1800162BD
0x180016176  xor     eax, eax
0x180016178  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18001617f  mov     [rsp+2E8h+CharType], ax
0x180016184  jz      loc_180016404
0x18001618a  lea     rax, [rsp+2E8h+CharType]
0x18001618f  mov     r9d, 1; cchSrc
0x180016195  lea     r8, [rsp+2E8h+SrcStr]; lpSrcStr
0x18001619a  mov     [rsp+2E8h+lpCharType], rax; lpCharType
0x18001619f  mov     edx, 4; dwInfoType
0x1800161a4  xor     ecx, ecx; Locale
0x1800161a6  call    cs:__imp_GetStringTypeExW
0x1800161ad  nop     dword ptr [rax+rax+00h]
0x1800161b2  mov     r11d, [rsp+2E8h+var_2A8]
0x1800161b7  mov     r10d, [rsp+2E8h+var_2AC]
0x1800161bc  test    r13d, r13d
0x1800161bf  jnz     loc_18001625E
0x1800161c5  movsxd  rax, ebx
0x1800161c8  movzx   r9d, word ptr [rdi+rax*2]
0x1800161cd  lea     eax, [r9-0AC00h]
0x1800161d4  cmp     eax, 2BFFh
0x1800161d9  jbe     short loc_18001622A
0x1800161db  mov     rax, cs:qword_1800A6FB8
0x1800161e2  mov     r8d, r9d
0x1800161e5  and     r8d, 3Fh
0x1800161e9  mov     ecx, r9d
0x1800161ec  shr     rcx, 6
0x1800161f0  movzx   edx, byte ptr [rcx+rax]
0x1800161f4  mov     rcx, cs:qword_1800A6FB0
0x1800161fb  shl     rdx, 6
0x1800161ff  add     rcx, rdx
0x180016202  movsx   eax, byte ptr [r8+rcx]
0x180016207  cmp     eax, 2
0x18001620a  jbe     short loc_18001622A
0x18001620c  add     eax, 0FFFFFFFCh
0x18001620f  cmp     eax, 2
0x180016212  jbe     loc_1800162F9
0x180016218  lea     eax, [r9-3Ch]
0x18001621c  mov     ecx, 0FFFDh
0x180016221  test    cx, ax
0x180016224  jnz     loc_18001645E
0x18001622a  cmp     [rsp+2E8h+var_294], 0
0x18001622f  jnz     short loc_18001625E
0x180016231  test    r11d, r11d
0x180016234  jnz     loc_180016338
0x18001623a  cmp     r14w, 0Dh
0x18001623f  jz      loc_18001632A
0x180016245  cmp     r14w, 0Ah
0x18001624a  jz      loc_18001632A
0x180016250  add     ebx, r10d
0x180016253  movzx   r14d, r9w
0x180016257  inc     ebp
0x180016259  jmp     loc_1800160C7
0x18001625e  mov     r13d, [rsp+2E8h+var_2A4]
0x180016263  cmp     r10d, 0FFFFFFFFh
0x180016267  jnz     short loc_18001626D
0x180016269  inc     ebx
0x18001626b  dec     esi
0x18001626d  add     r13d, ebx
0x180016270  mov     ecx, ebx
0x180016272  neg     ecx
0x180016274  mov     [rsp+2E8h+var_2A4], r13d
0x180016279  cmovs   ecx, ebx
0x18001627c  cmp     ecx, esi
0x18001627e  jge     loc_180016379
0x180016284  mov     eax, r13d
0x180016287  test    r12, r12
0x18001628a  jz      short loc_180016291
0x18001628c  mov     [r12], r14w
0x180016291  mov     rcx, [rsp+2E8h+var_48]
0x180016299  xor     rcx, rsp; StackCookie
0x18001629c  call    __security_check_cookie
0x1800162a1  mov     rbx, [rsp+2E8h+arg_0]
0x1800162a9  add     rsp, 2B0h
0x1800162b0  pop     r15
0x1800162b2  pop     r14
0x1800162b4  pop     r13
0x1800162b6  pop     r12
0x1800162b8  pop     rdi
0x1800162b9  pop     rsi
0x1800162ba  pop     rbp
0x1800162bb  retn
0x1800162bd  lea     eax, [rcx-0Ah]
0x1800162c0  test    eax, 0FFFFFFFBh
0x1800162c5  jnz     loc_1800161BC
0x1800162cb  cmp     [rsp+2E8h+var_29C], 0
0x1800162d0  jmp     loc_1800161BF
0x1800162d5  xor     esi, esi
0x1800162d7  xor     edi, edi
0x1800162d9  jmp     loc_1800160B9
0x1800162de  xor     esi, esi
0x1800162e0  xor     edi, edi
0x1800162e2  jmp     loc_1800160B7
0x1800162e7  cmp     ecx, 2BFFh
0x1800162ed  ja      short loc_1800162CB
0x1800162ef  mov     [rsp+2E8h+SrcStr], ax
0x1800162f4  jmp     loc_1800161BC
0x1800162f9  cmp     r9d, 2Fh ; '/'
0x1800162fd  jnz     loc_18001622A
0x180016303  jmp     loc_180016218
0x180016308  mov     esi, [rdx]
0x18001630a  mov     eax, [rdx+14h]
0x18001630d  cdq
0x18001630e  sub     eax, edx
0x180016310  sar     eax, 1
0x180016312  sub     eax, esi
0x180016314  sub     esi, r9d
0x180016317  cdqe
0x180016319  lea     rdi, [rdi+rax*2]
0x18001631d  xor     eax, eax
0x18001631f  test    esi, esi
0x180016321  cmovz   rdi, rax
0x180016325  jmp     loc_1800160B9
0x18001632a  test    r13d, r13d
0x18001632d  jnz     loc_180016250
0x180016333  jmp     loc_18001625E
0x180016338  cmp     r14w, 20h ; ' '
0x18001633d  jz      loc_18001623A
0x180016343  cmp     [r12], r14w
0x180016348  jnz     loc_18001623A
0x18001634e  jmp     loc_18001625E
0x180016353  mov     eax, [rcx+8]
0x180016356  dec     eax
0x180016358  cmp     r8d, eax
0x18001635b  jge     loc_1800162D7
0x180016361  lea     edx, [r8+1]; int
0x180016365  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18001636a  mov     rdx, rax
0x18001636d  test    rax, rax
0x180016370  jnz     short loc_1800163E6
0x180016372  xor     edi, edi
  ... truncated ...
```
