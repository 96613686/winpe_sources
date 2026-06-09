# PrimeCache

- ea: `0x14004d4b0`
- end: `0x14004d738`
- name: `PrimeCache`
- size: `648`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x14004d390`

## callees

- `0x140025c84`
- `0x14002bb80`
- `0x140030f40`
- `0x140040294`
- `0x1400445a8`
- `0x1400447ac`
- `0x14004b704`
- `0x14004d4b0`
- `0x14004dc90`
- `0x14004de44`
- `0x14004e380`
- `0x14004e40c`
- `0x14004e60c`
- `0x14004ea48`

## pseudocode

```c
__int64 __fastcall PrimeCache(__int64 a1, __int64 a2, char a3)
{
  int v3; // r13d
  int v4; // esi
  __int64 result; // rax
  KSPIN_LOCK *v7; // r15
  unsigned int v8; // r14d
  int v9; // ebx
  int v10; // edi
  int v11; // edi
  int v12; // edi
  void *v13; // rax
  int Tokens; // ebx
  int v15; // edi
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // r9
  unsigned int v19; // [rsp+34h] [rbp-35h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-31h] BYREF
  int v21; // [rsp+3Ch] [rbp-2Dh] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-29h] BYREF
  _OWORD v23[2]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v24; // [rsp+70h] [rbp+7h]
  _BYTE v25[24]; // [rsp+78h] [rbp+Fh] BYREF

  v4 = 0;
  result = 0;
  LOBYTE(v3) = a3;
  v21 = 0;
  v24 = 0;
  memset(v23, 0, sizeof(v23));
  v19 = 0;
  v20 = 0;
  if ( byte_140039679 )
  {
    v22[1] = v22;
    v22[0] = v22;
    if ( (unsigned __int8)LmpBreakRecursion(a1, word_140033C3A, 1) == 1 )
      return 0xFFFFFFFFLL;
    v7 = LmOpenFile(a1);
    if ( !v7 )
      return 0xFFFFFFFFLL;
    v8 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        v13 = (void *)LmFgets(v7, &v21);
        if ( !v13 || dword_14003968C - v8 < 3 )
        {
          LmCloseFile(v7);
          MakeNewListCurrent(v22);
          return v8;
        }
        Tokens = LmpGetTokens(v13, v23);
        v15 = Tokens << 28 >> 28;
        if ( v15 != 6 )
          break;
        if ( SBYTE1(xmmword_140038420) < 0 )
        {
          v16 = 37;
          goto LABEL_20;
        }
      }
      if ( *((_QWORD *)&v23[0] + 1) || (unsigned int)(v15 - 4) <= 1 )
      {
        v9 = -__CFSHR__(Tokens, 5);
        if ( v9
          && (int)ConvertDottedDecimalToUlong(*(_QWORD *)&v23[0], &v19) >= 0
          && (int)PreloadEntry(*((_QWORD *)&v23[0] + 1), v19) >= 0 )
        {
          ++v8;
        }
        v10 = v15 - 2;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( v12 )
            {
              if ( v12 == 1 )
                v4 = 0;
            }
            else
            {
              v4 = 1;
            }
          }
          else if ( (_BYTE)v3 )
          {
            if ( v4 != 2 )
            {
              v17 = LmInclude(DWORD2(v23[0]), (unsigned int)PrimeCache, 0, v3 - 1, 0);
              if ( v17 != -1 )
              {
                if ( v4 == 1 )
                  v4 = 2;
                v8 += v17;
              }
            }
          }
        }
        else
        {
          LmExpandName(v25);
          if ( (int)ConvertDottedDecimalToUlong(*(_QWORD *)&v23[0], &v20) >= 0 )
          {
            LOBYTE(v18) = v9;
            AddToDomainList(v25, v20, v22, v18);
          }
        }
      }
      else if ( SBYTE1(xmmword_140038420) < 0 )
      {
        v16 = 38;
LABEL_20:
        WPP_SF_(1039, v16, WPP_e595452688c43ce128ab41f39d85d938_Traceguids);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14004d4b0  mov     [rsp-8+arg_8], rbx
0x14004d4b5  mov     [rsp-8+arg_18], rsi
0x14004d4ba  push    rbp
0x14004d4bb  push    rdi
0x14004d4bc  push    r13
0x14004d4be  push    r14
0x14004d4c0  push    r15
0x14004d4c2  lea     rbp, [rsp-37h]
0x14004d4c7  sub     rsp, 0A0h
0x14004d4ce  mov     rax, cs:__security_cookie
0x14004d4d5  xor     rax, rsp
0x14004d4d8  mov     [rbp+57h+var_30], rax
0x14004d4dc  xor     esi, esi
0x14004d4de  xor     eax, eax
0x14004d4e0  cmp     cs:byte_140039679, sil
0x14004d4e7  xorps   xmm0, xmm0
0x14004d4ea  mov     r13b, r8b
0x14004d4ed  mov     [rbp+57h+var_84], esi
0x14004d4f0  mov     rbx, rcx
0x14004d4f3  mov     [rbp+57h+var_50], rax
0x14004d4f7  movups  [rbp+57h+var_70], xmm0
0x14004d4fb  mov     [rbp+57h+var_8C], esi
0x14004d4fe  movups  [rbp+57h+var_60], xmm0
0x14004d502  mov     [rbp+57h+var_88], esi
0x14004d505  jz      short loc_14004D53E
0x14004d507  lea     rax, [rbp+57h+var_80]
0x14004d50b  mov     [rbp+57h+var_78], rax
0x14004d50f  lea     r8d, [rsi+1]
0x14004d513  lea     rax, [rbp+57h+var_80]
0x14004d517  lea     rdx, word_140033C3A
0x14004d51e  mov     [rbp+57h+var_80], rax
0x14004d522  call    LmpBreakRecursion
0x14004d527  cmp     al, 1
0x14004d529  jz      short loc_14004D53B
0x14004d52b  mov     rcx, rbx
0x14004d52e  call    LmOpenFile
0x14004d533  mov     r15, rax
0x14004d536  test    rax, rax
0x14004d539  jnz     short loc_14004D567
0x14004d53b  or      eax, 0FFFFFFFFh
0x14004d53e  mov     rcx, [rbp+57h+var_30]
0x14004d542  xor     rcx, rsp; StackCookie
0x14004d545  call    __security_check_cookie
0x14004d54a  lea     r11, [rsp+0C0h+var_20]
0x14004d552  mov     rbx, [r11+38h]
0x14004d556  mov     rsi, [r11+48h]
0x14004d55a  mov     rsp, r11
0x14004d55d  pop     r15
0x14004d55f  pop     r14
0x14004d561  pop     r13
0x14004d563  pop     rdi
0x14004d564  pop     rbp
0x14004d565  retn
0x14004d567  mov     r14d, esi
0x14004d56a  jmp     short loc_14004D5AF
0x14004d56c  cmp     qword ptr [rbp+57h+var_70+8], 0
0x14004d571  lea     eax, [rdi-4]
0x14004d574  jz      loc_14004D63A
0x14004d57a  shr     ebx, 5
0x14004d57d  sbb     ebx, ebx
0x14004d57f  test    ebx, ebx
0x14004d581  jnz     loc_14004D652
0x14004d587  mov     ecx, 2
0x14004d58c  sub     edi, ecx
0x14004d58e  jz      loc_14004D6EA
0x14004d594  sub     edi, 1
0x14004d597  jz      loc_14004D694
0x14004d59d  sub     edi, 1
0x14004d5a0  jz      loc_14004D68A
0x14004d5a6  cmp     edi, 1
0x14004d5a9  jz      loc_14004D683
0x14004d5af  lea     rdx, [rbp+57h+var_84]
0x14004d5b3  mov     rcx, r15
0x14004d5b6  call    LmFgets
0x14004d5bb  test    rax, rax
0x14004d5be  jnz     short loc_14004D5D9
0x14004d5c0  mov     rcx, r15; P
0x14004d5c3  call    LmCloseFile
0x14004d5c8  lea     rcx, [rbp+57h+var_80]
0x14004d5cc  call    MakeNewListCurrent
0x14004d5d1  mov     eax, r14d
0x14004d5d4  jmp     loc_14004D53E
0x14004d5d9  mov     ecx, cs:dword_14003968C
0x14004d5df  sub     ecx, r14d
0x14004d5e2  cmp     ecx, 3
0x14004d5e5  jb      short loc_14004D5C0
0x14004d5e7  lea     r8, [rbp+57h+var_90]
0x14004d5eb  mov     [rbp+57h+var_90], 5
0x14004d5f2  lea     rdx, [rbp+57h+var_70]; void *
0x14004d5f6  mov     rcx, rax; Buf1
0x14004d5f9  call    LmpGetTokens
0x14004d5fe  mov     edi, eax
0x14004d600  mov     ebx, eax
0x14004d602  shl     edi, 1Ch
0x14004d605  sar     edi, 1Ch
0x14004d608  cmp     edi, 6
0x14004d60b  jnz     loc_14004D56C
0x14004d611  cmp     byte ptr cs:xmmword_140038420+1, 0
0x14004d618  jge     short loc_14004D5AF
0x14004d61a  lea     edx, [rdi+1Fh]
0x14004d61d  jmp     short loc_14004D624
0x14004d61f  mov     edx, 26h ; '&'
0x14004d624  mov     ecx, 40Fh
0x14004d629  lea     r8, WPP_e595452688c43ce128ab41f39d85d938_Traceguids
0x14004d630  call    WPP_SF_
0x14004d635  jmp     loc_14004D5AF
0x14004d63a  cmp     eax, 1
0x14004d63d  jbe     loc_14004D57A
0x14004d643  cmp     byte ptr cs:xmmword_140038420+1, 0
0x14004d64a  jge     loc_14004D5AF
0x14004d650  jmp     short loc_14004D61F
0x14004d652  mov     rcx, qword ptr [rbp+57h+var_70]
0x14004d656  lea     rdx, [rbp+57h+var_8C]
0x14004d65a  call    ConvertDottedDecimalToUlong
0x14004d65f  test    eax, eax
0x14004d661  js      loc_14004D587
0x14004d667  mov     edx, [rbp+57h+var_8C]
0x14004d66a  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x14004d66e  call    PreloadEntry
0x14004d673  test    eax, eax
0x14004d675  js      loc_14004D587
0x14004d67b  inc     r14d
0x14004d67e  jmp     loc_14004D587
0x14004d683  xor     esi, esi
0x14004d685  jmp     loc_14004D5AF
0x14004d68a  mov     esi, 1
0x14004d68f  jmp     loc_14004D5AF
0x14004d694  test    r13b, r13b
0x14004d697  jz      loc_14004D5AF
0x14004d69d  cmp     esi, ecx
0x14004d69f  jz      loc_14004D5AF
0x14004d6a5  cmp     [rbp+57h+var_90], ecx
0x14004d6a8  jl      loc_14004D5AF
0x14004d6ae  mov     rcx, qword ptr [rbp+57h+var_70+8]
0x14004d6b2  lea     r9d, [r13-1]
0x14004d6b6  xor     r8d, r8d
0x14004d6b9  mov     [rsp+0C0h+var_A0], 0
0x14004d6c2  lea     rdx, PrimeCache
0x14004d6c9  call    LmInclude
0x14004d6ce  cmp     eax, 0FFFFFFFFh
0x14004d6d1  jz      loc_14004D5AF
0x14004d6d7  cmp     esi, 1
0x14004d6da  mov     ecx, 2
0x14004d6df  cmovz   esi, ecx
0x14004d6e2  add     r14d, eax
0x14004d6e5  jmp     loc_14004D5AF
0x14004d6ea  mov     eax, [rbp+57h+var_90]
0x14004d6ed  dec     eax
0x14004d6ef  cmp     eax, ecx
0x14004d6f1  jl      loc_14004D5AF
0x14004d6f7  mov     rdx, qword ptr [rbp+57h+var_60]
0x14004d6fb  lea     rcx, [rbp+57h+var_48]; void *
0x14004d6ff  add     rdx, 5
0x14004d703  mov     r8b, 1Ch
0x14004d706  call    LmExpandName
0x14004d70b  mov     rcx, qword ptr [rbp+57h+var_70]
0x14004d70f  lea     rdx, [rbp+57h+var_88]
0x14004d713  call    ConvertDottedDecimalToUlong
0x14004d718  test    eax, eax
0x14004d71a  js      loc_14004D5AF
0x14004d720  mov     edx, [rbp+57h+var_88]
0x14004d723  lea     r8, [rbp+57h+var_80]
0x14004d727  mov     r9b, bl
0x14004d72a  lea     rcx, [rbp+57h+var_48]
0x14004d72e  call    AddToDomainList
0x14004d733  jmp     loc_14004D5AF
```
