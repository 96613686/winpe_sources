# COleScript::ParseScriptTextCore(ushort const *,ushort const *,IUnknown *,ushort const *,unsigned __int64,ulong,ulong,tagVARIANT *,tagEXCEPINFO *)

- ea: `0x180017b00`
- end: `0x180017ff9`
- name: `?ParseScriptTextCore@COleScript@@QEAAJPEBG0PEAUIUnknown@@0_KKKPEAUtagVARIANT@@PEAUtagEXCEPINFO@@@Z`
- size: `1273`
- prototype: `__int64 __fastcall(COleScript *this, const unsigned __int16 *, unsigned __int16 *, struct IUnknown *, wchar_t *, unsigned __int64, unsigned int, __int16, struct tagVARIANT *pvarg, struct tagEXCEPINFO *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180017a90`

## callees

- `0x180007e68`
- `0x180016e94`
- `0x180017b00`
- `0x180018000`
- `0x180018350`
- `0x180030770`
- `0x1800326c0`
- `0x18003557c`
- `0x180047240`
- `0x18007e04c`
- `0x18008a40c`
- `0x180096692`
- `0x1800966e0`

## import_xrefs

- `msvcrt!free` at `0x180017e1c`
- `msvcrt!free` at `0x180017e1c`
- `msvcrt!_wcsdup` at `0x180017e05`
- `msvcrt!_wcsdup` at `0x180017e05`
- `OLEAUT32!__imp_SysFreeString` at `0x180017fe8`
- `OLEAUT32!__imp_SysFreeString` at `0x180017fe8`
- `OLEAUT32!__imp_VariantInit` at `0x180017edb`
- `OLEAUT32!__imp_VariantInit` at `0x180017edb`
- `KERNEL32!GetCurrentThreadId` at `0x180017b5a`
- `KERNEL32!GetCurrentThreadId` at `0x180017b5a`

## pseudocode

```c
__int64 __fastcall COleScript::ParseScriptTextCore(
        COleScript *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IUnknown *a4,
        wchar_t *a5,
        unsigned __int64 a6,
        unsigned int a7,
        __int16 a8,
        struct tagVARIANT *pvarg,
        struct tagEXCEPINFO *a10)
{
  unsigned __int16 *v10; // rdi
  struct tagEXCEPINFO *v12; // r14
  COleScript *v13; // r15
  int v14; // ebx
  signed int v15; // r13d
  __int64 v16; // rbx
  _WORD *v17; // r12
  int v18; // r15d
  _WORD *v19; // r14
  __int64 v20; // rdi
  int v21; // eax
  int v22; // r15d
  int v23; // edx
  __int64 v24; // rax
  char *v25; // rcx
  int v26; // edx
  __int64 v27; // rax
  int v28; // r15d
  int HasCode; // edi
  int v31; // eax
  int v32; // eax
  unsigned int *v33; // rax
  __int64 v34; // rdi
  OLECHAR *v35; // rax
  const unsigned __int16 *v36; // r12
  unsigned int v37; // [rsp+40h] [rbp-79h] BYREF
  void *Block; // [rsp+48h] [rbp-71h] BYREF
  __int64 v39; // [rsp+50h] [rbp-69h]
  int v40; // [rsp+58h] [rbp-61h]
  COleScript *v41; // [rsp+60h] [rbp-59h]
  unsigned __int16 *v42; // [rsp+68h] [rbp-51h]
  struct NamedItem *v43; // [rsp+70h] [rbp-49h]
  BSTR bstrString; // [rsp+78h] [rbp-41h]
  struct tagEXCEPINFO *v45; // [rsp+80h] [rbp-39h]
  wchar_t *String2; // [rsp+88h] [rbp-31h]
  struct tagVARIANT *v47; // [rsp+90h] [rbp-29h]
  unsigned __int64 v48; // [rsp+98h] [rbp-21h] BYREF
  unsigned int v49; // [rsp+A0h] [rbp-19h]
  __int64 v50; // [rsp+A4h] [rbp-15h]
  int v51; // [rsp+ACh] [rbp-Dh]
  unsigned int v52; // [rsp+B0h] [rbp-9h]
  int v53; // [rsp+B4h] [rbp-5h]

  v10 = a3;
  v12 = a10;
  v13 = this;
  v14 = *((_DWORD *)this + 65);
  String2 = a5;
  v47 = pvarg;
  v45 = a10;
  v42 = a3;
  v41 = this;
  if ( GetCurrentThreadId() == v14 )
  {
    bstrString = 0;
    if ( pvarg )
      VariantInit(pvarg);
    if ( a10 )
      *(__m512 *)a10 = zmmword_1800A21D0;
    v15 = a8 & 0x3E3;
    if ( pvarg || (a8 & 1) == 0 && (unsigned int)(*((_DWORD *)v13 + 42) - 1) <= 2 )
      v15 |= 0x80000000;
    v16 = -1;
    if ( *((_DWORD *)v13 + 172) )
    {
      v34 = -1;
      do
        ++v34;
      while ( a2[v34] );
      v37 = v34;
      v35 = _SysAllocStringLen(0, v34);
      bstrString = v35;
      v36 = v35;
      if ( (_DWORD)v34 && !v35 )
        return (unsigned int)-2147024882;
      HasCode = DecodeScriptCore(a2, v34, v35, v34, &v37);
      if ( HasCode < 0 )
        goto LABEL_39;
      v10 = v42;
      a2 = v36;
      v36[v37] = 0;
    }
    if ( !a2 || !*a2 )
    {
      v17 = 0;
      HasCode = 0;
      goto LABEL_37;
    }
    v37 = 0;
    v43 = 0;
    if ( v10 && *v10 )
    {
      v33 = (unsigned int *)NamedItemList::Find((COleScript *)((char *)v13 + 312), v10);
      v43 = (struct NamedItem *)v33;
      if ( !v33 )
      {
        HasCode = -2147024809;
        goto LABEL_39;
      }
      v37 = v33[13];
    }
    v17 = 0;
    Block = 0;
    v18 = 0;
    v39 = 0;
    v40 = 0;
    v19 = (_WORD *)*((_QWORD *)v41 + 23);
    if ( v19 )
    {
      v20 = -1;
      do
        ++v20;
      while ( v19[v20] );
      if ( (int)v20 < 0 )
        goto LABEL_19;
    }
    else
    {
      LODWORD(v20) = 0;
    }
    v21 = BuildString::FEnsureSpace((BuildString *)&Block, v20);
    v17 = Block;
    if ( v21 )
    {
      v22 = HIDWORD(v39);
      memcpy_0((char *)Block + 2 * SHIDWORD(v39), v19, 2LL * (unsigned int)v20);
      v18 = v20 + v22;
      HIDWORD(v39) = v18;
      if ( v17 )
        v17[v18] = 0;
    }
    else
    {
      v18 = HIDWORD(v39);
    }
LABEL_19:
    v23 = v18 + 3;
    if ( v18 + 3 > v18 )
    {
      if ( v23 < (int)v39
        || (v31 = BuildString::FEnsureSpace((BuildString *)&Block, v23), v18 = HIDWORD(v39), v17 = Block, v31) )
      {
        v24 = v18;
        v18 += 3;
        HIDWORD(v39) = v18;
        v25 = (char *)&v17[v24];
        *(_DWORD *)v25 = *(_DWORD *)L" - ";
        *((_WORD *)v25 + 2) = asc_1800A2230[2];
        if ( v17 )
          v17[v18] = 0;
      }
    }
    if ( v42 )
    {
      BuildString::AppendSz((BuildString *)&Block, v42, -1);
      BuildString::AppendCh((BuildString *)&Block, 0x20u);
      v18 = HIDWORD(v39);
      v17 = Block;
    }
    v26 = v18 + 12;
    if ( v18 + 12 <= v18 )
      goto LABEL_29;
    if ( v26 >= (int)v39 )
    {
      v32 = BuildString::FEnsureSpace((BuildString *)&Block, v26);
      v17 = Block;
      if ( !v32 )
      {
LABEL_29:
        if ( !v40 )
        {
          if ( !v17 )
            v17 = _wcsdup(&String);
          Block = 0;
          v39 = 0;
          v40 = 0;
          if ( v17 )
          {
            v13 = v41;
            if ( v43 )
            {
              if ( (*((_BYTE *)v43 + 56) & 2) == 0 )
              {
                HasCode = COleScript::RegisterNamedItemHasCode(v41, v43);
                if ( HasCode < 0 )
                {
LABEL_42:
                  free(v17);
                  goto LABEL_39;
                }
              }
            }
            v48 = a6;
            v49 = a7;
            v50 = 0;
            do
              ++v16;
            while ( a2[v16] );
            v53 = 0;
            v12 = v45;
            v52 = v37;
            v51 = v16;
            HasCode = COleScript::CreateScriptBody(v13, a2, v15, (struct SRCINFO *)&v48, String2, v17, v45, 0);
LABEL_37:
            if ( v15 < 0 && HasCode >= 0 )
              HasCode = COleScript::ExecutePendingScripts(v13, v47, v12);
            if ( !v17 )
              goto LABEL_39;
            goto LABEL_42;
          }
        }
        HasCode = -2147024882;
        BuildString::Reset((BuildString *)&Block);
LABEL_39:
        if ( bstrString )
          SysFreeString(bstrString);
        return (unsigned int)HasCode;
      }
      v18 = HIDWORD(v39);
    }
    v27 = v18;
    v28 = v18 + 12;
    HIDWORD(v39) = v28;
    *(_OWORD *)&v17[v27] = *(_OWORD *)L"script block";
    *(_QWORD *)&v17[v27 + 8] = *(_QWORD *)L"lock";
    if ( v17 )
      v17[v28] = 0;
    goto LABEL_29;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180017b00  push    rbp
0x180017b02  push    rbx
0x180017b03  push    rsi
0x180017b04  push    rdi
0x180017b05  push    r12
0x180017b07  push    r14
0x180017b09  push    r15
0x180017b0b  lea     rbp, [rsp-7]
0x180017b10  sub     rsp, 0C0h
0x180017b17  mov     rax, cs:__security_cookie
0x180017b1e  xor     rax, rsp
0x180017b21  mov     [rbp+37h+var_38], rax
0x180017b25  mov     rax, [rbp+37h+arg_20]
0x180017b29  mov     rdi, r8
0x180017b2c  mov     r12, [rbp+37h+pvarg]
0x180017b33  mov     rsi, rdx
0x180017b36  mov     r14, [rbp+37h+arg_48]
0x180017b3d  mov     r15, rcx
0x180017b40  mov     ebx, [rcx+104h]
0x180017b46  mov     [rbp+37h+var_68], rax
0x180017b4a  mov     [rbp+37h+var_60], r12
0x180017b4e  mov     [rbp+37h+var_70], r14
0x180017b52  mov     [rbp+37h+var_88], r8
0x180017b56  mov     [rbp+37h+var_90], rcx
0x180017b5a  call    cs:__imp_GetCurrentThreadId
0x180017b61  nop     dword ptr [rax+rax+00h]
0x180017b66  cmp     eax, ebx
0x180017b68  jnz     loc_180017EEE
0x180017b6e  xor     ecx, ecx
0x180017b70  mov     [rsp+0F0h+arg_18], r13
0x180017b78  mov     [rbp+37h+bstrString], rcx
0x180017b7c  test    r12, r12
0x180017b7f  jnz     loc_180017ED8
0x180017b85  test    r14, r14
0x180017b88  jz      short loc_180017BB9
0x180017b8a  movaps  xmm0, xmmword ptr cs:zmmword_1800A21D0
0x180017b91  movaps  xmm1, xmmword ptr cs:zmmword_1800A21D0+10h
0x180017b98  movups  xmmword ptr [r14], xmm0
0x180017b9c  movaps  xmm0, xmmword ptr cs:zmmword_1800A21D0+20h
0x180017ba3  movups  xmmword ptr [r14+10h], xmm1
0x180017ba8  movaps  xmm1, xmmword ptr cs:zmmword_1800A21D0+30h
0x180017baf  movups  xmmword ptr [r14+20h], xmm0
0x180017bb4  movups  xmmword ptr [r14+30h], xmm1
0x180017bb9  mov     r13d, dword ptr [rbp+37h+arg_38]
0x180017bbd  and     r13d, 3E3h
0x180017bc4  test    r12, r12
0x180017bc7  jz      loc_180017E2A
0x180017bcd  bts     r13d, 1Fh
0x180017bd2  cmp     dword ptr [r15+2B0h], 0
0x180017bda  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180017be1  jnz     loc_180017EF8
0x180017be7  test    rsi, rsi
0x180017bea  jz      loc_180017FDE
0x180017bf0  cmp     cx, [rsi]
0x180017bf3  jz      loc_180017FDE
0x180017bf9  mov     [rbp+37h+var_B0], ecx
0x180017bfc  mov     [rbp+37h+var_80], rcx
0x180017c00  test    rdi, rdi
0x180017c03  jnz     loc_180017EA5
0x180017c09  mov     r14, [rbp+37h+var_90]
0x180017c0d  mov     r12, rcx
0x180017c10  mov     [rbp+37h+Block], rcx
0x180017c14  mov     r15d, ecx
0x180017c17  mov     [rbp+37h+var_A0], 0
0x180017c1f  mov     [rbp+37h+var_98], ecx
0x180017c22  mov     r14, [r14+0B8h]
0x180017c29  test    r14, r14
0x180017c2c  jz      loc_180017F70
0x180017c32  mov     rdi, rbx
0x180017c35  inc     rdi
0x180017c38  cmp     word ptr [r14+rdi*2], 0
0x180017c3e  jnz     short loc_180017C35
0x180017c40  test    edi, edi
0x180017c42  js      loc_180017F7B
0x180017c48  mov     edx, edi; int
0x180017c4a  lea     rcx, [rbp+37h+Block]; this
0x180017c4e  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x180017c53  mov     r12, [rbp+37h+Block]
0x180017c57  test    eax, eax
0x180017c59  jz      loc_180017F77
0x180017c5f  movsxd  r15, dword ptr [rbp+37h+var_A0+4]
0x180017c63  mov     rdx, r14; Src
0x180017c66  mov     r8d, edi
0x180017c69  add     r8, r8; Size
0x180017c6c  lea     rcx, [r12+r15*2]; void *
0x180017c70  call    memcpy_0
0x180017c75  add     r15d, edi
0x180017c78  xor     r14d, r14d
0x180017c7b  mov     dword ptr [rbp+37h+var_A0+4], r15d
0x180017c7f  test    r12, r12
0x180017c82  jz      short loc_180017C8C
0x180017c84  movsxd  rcx, r15d
0x180017c87  mov     [r12+rcx*2], r14w
0x180017c8c  lea     edx, [r15+3]; int
0x180017c90  cmp     edx, r15d
0x180017c93  jl      short loc_180017CCE
0x180017c95  cmp     edx, dword ptr [rbp+37h+var_A0]
0x180017c98  jge     loc_180017E4B
0x180017c9e  movsxd  rax, r15d
0x180017ca1  add     r15d, 3
0x180017ca5  mov     dword ptr [rbp+37h+var_A0+4], r15d
0x180017ca9  lea     rcx, [r12+rax*2]
0x180017cad  mov     rax, qword ptr cs:asc_1800A2230; " - "
0x180017cb4  mov     [rcx], eax
0x180017cb6  movzx   eax, word ptr cs:asc_1800A2230+4; " "
0x180017cbd  mov     [rcx+4], ax
0x180017cc1  test    r12, r12
0x180017cc4  jz      short loc_180017CCE
0x180017cc6  movsxd  rcx, r15d
0x180017cc9  mov     [r12+rcx*2], r14w
0x180017cce  mov     rdx, [rbp+37h+var_88]; unsigned __int16 *
0x180017cd2  test    rdx, rdx
0x180017cd5  jnz     loc_180017F83
0x180017cdb  lea     edx, [r15+0Ch]; int
0x180017cdf  cmp     edx, r15d
0x180017ce2  jl      short loc_180017D20
0x180017ce4  cmp     edx, dword ptr [rbp+37h+var_A0]
0x180017ce7  jge     loc_180017E69
0x180017ced  movups  xmm0, xmmword ptr cs:aScriptBlock; "script block"
0x180017cf4  movsxd  rax, r15d
0x180017cf7  add     r15d, 0Ch
0x180017cfb  mov     dword ptr [rbp+37h+var_A0+4], r15d
0x180017cff  movups  xmmword ptr [r12+rax*2], xmm0
0x180017d04  movsd   xmm1, qword ptr cs:aScriptBlock+10h; "lock"
0x180017d0c  movsd   qword ptr [r12+rax*2+10h], xmm1
0x180017d13  test    r12, r12
0x180017d16  jz      short loc_180017D20
0x180017d18  movsxd  rcx, r15d
0x180017d1b  mov     [r12+rcx*2], r14w
0x180017d20  cmp     [rbp+37h+var_98], 0
0x180017d24  jnz     loc_180017FCB
0x180017d2a  test    r12, r12
0x180017d2d  jz      loc_180017DFE
0x180017d33  mov     [rbp+37h+Block], r14
0x180017d37  mov     [rbp+37h+var_A0], 0
0x180017d3f  mov     [rbp+37h+var_98], r14d
0x180017d43  test    r12, r12
0x180017d46  jz      loc_180017FCB
0x180017d4c  mov     rdx, [rbp+37h+var_80]; struct NamedItem *
0x180017d50  mov     r15, [rbp+37h+var_90]
0x180017d54  test    rdx, rdx
0x180017d57  jnz     loc_180017FAA
0x180017d5d  mov     rax, [rbp+37h+arg_28]
0x180017d61  mov     [rbp+37h+var_58], rax
0x180017d65  mov     eax, [rbp+37h+arg_30]
0x180017d68  mov     [rbp+37h+var_50], eax
0x180017d6b  mov     [rbp+37h+var_4C], 0
0x180017d73  inc     rbx
0x180017d76  cmp     word ptr [rsi+rbx*2], 0
0x180017d7b  jnz     short loc_180017D73
0x180017d7d  mov     eax, [rbp+37h+var_B0]
0x180017d80  lea     r9, [rbp+37h+var_58]; struct SRCINFO *
0x180017d84  mov     [rsp+0F0h+var_B8], r14; struct CScriptBody **
0x180017d89  mov     r8d, r13d; unsigned int
0x180017d8c  mov     [rbp+37h+var_3C], r14d
0x180017d90  mov     rdx, rsi; unsigned __int16 *
0x180017d93  mov     r14, [rbp+37h+var_70]
0x180017d97  mov     rcx, r15; this
0x180017d9a  mov     [rbp+37h+var_40], eax
0x180017d9d  mov     rax, [rbp+37h+var_68]
0x180017da1  mov     [rsp+0F0h+var_C0], r14; struct tagEXCEPINFO *
0x180017da6  mov     [rsp+0F0h+var_C8], r12; unsigned __int16 *
0x180017dab  mov     [rsp+0F0h+String2], rax; String2
0x180017db0  mov     [rbp+37h+var_44], ebx
0x180017db3  call    ?CreateScriptBody@COleScript@@QEAAJPEBGKPEAVSRCINFO@@00PEAUtagEXCEPINFO@@PEAPEAVCScriptBody@@@Z; COleScript::CreateScriptBody(ushort const *,ulong,SRCINFO *,ushort const *,ushort const *,tagEXCEPINFO *,CScriptBody * *)
0x180017db8  mov     edi, eax
0x180017dba  test    r13d, r13d
0x180017dbd  js      loc_180017E87
0x180017dc3  test    r12, r12
0x180017dc6  jnz     short loc_180017E19
0x180017dc8  mov     rcx, [rbp+37h+bstrString]; bstrString
0x180017dcc  test    rcx, rcx
0x180017dcf  jnz     loc_180017FE8
0x180017dd5  mov     r13, [rsp+0F0h+arg_18]
0x180017ddd  mov     eax, edi
0x180017ddf  mov     rcx, [rbp+37h+var_38]
0x180017de3  xor     rcx, rsp; StackCookie
0x180017de6  call    __security_check_cookie
0x180017deb  add     rsp, 0C0h
0x180017df2  pop     r15
0x180017df4  pop     r14
0x180017df6  pop     r12
0x180017df8  pop     rdi
0x180017df9  pop     rsi
0x180017dfa  pop     rbx
0x180017dfb  pop     rbp
0x180017dfc  retn
0x180017dfe  lea     rcx, String; String
0x180017e05  call    cs:__imp__wcsdup
0x180017e0c  nop     dword ptr [rax+rax+00h]
0x180017e11  mov     r12, rax
0x180017e14  jmp     loc_180017D33
0x180017e19  mov     rcx, r12; Block
0x180017e1c  call    cs:__imp_free
0x180017e23  nop     dword ptr [rax+rax+00h]
0x180017e28  jmp     short loc_180017DC8
0x180017e2a  test    r13b, 1
0x180017e2e  jnz     loc_180017BD2
0x180017e34  mov     eax, [r15+0A8h]
0x180017e3b  dec     eax
0x180017e3d  cmp     eax, 2
0x180017e40  ja      loc_180017BD2
0x180017e46  jmp     loc_180017BCD
0x180017e4b  lea     rcx, [rbp+37h+Block]; this
0x180017e4f  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x180017e54  mov     r15d, dword ptr [rbp+37h+var_A0+4]
0x180017e58  mov     r12, [rbp+37h+Block]
0x180017e5c  test    eax, eax
0x180017e5e  jnz     loc_180017C9E
0x180017e64  jmp     loc_180017CCE
0x180017e69  lea     rcx, [rbp+37h+Block]; this
0x180017e6d  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x180017e72  mov     r12, [rbp+37h+Block]
0x180017e76  test    eax, eax
0x180017e78  jz      loc_180017D20
0x180017e7e  mov     r15d, dword ptr [rbp+37h+var_A0+4]
0x180017e82  jmp     loc_180017CED
0x180017e87  test    edi, edi
0x180017e89  js      loc_180017DC3
0x180017e8f  mov     rdx, [rbp+37h+var_60]; struct tagVARIANT *
0x180017e93  mov     r8, r14; struct tagEXCEPINFO *
0x180017e96  mov     rcx, r15; this
0x180017e99  call    ?ExecutePendingScripts@COleScript@@AEAAJPEAUtagVARIANT@@PEAUtagEXCEPINFO@@@Z; COleScript::ExecutePendingScripts(tagVARIANT *,tagEXCEPINFO *)
0x180017e9e  mov     edi, eax
0x180017ea0  jmp     loc_180017DC3
0x180017ea5  cmp     word ptr [rdi], 0
0x180017ea9  jz      loc_180017C09
0x180017eaf  lea     rcx, [r15+138h]; this
0x180017eb6  mov     rdx, rdi; unsigned __int16 *
0x180017eb9  call    ?Find@NamedItemList@@QEAAPEAUNamedItem@@PEBG@Z; NamedItemList::Find(ushort const *)
0x180017ebe  mov     [rbp+37h+var_80], rax
0x180017ec2  test    rax, rax
0x180017ec5  jz      loc_180017F66
0x180017ecb  mov     eax, [rax+34h]
0x180017ece  xor     ecx, ecx
0x180017ed0  mov     [rbp+37h+var_B0], eax
0x180017ed3  jmp     loc_180017C09
0x180017ed8  mov     rcx, r12; pvarg
0x180017edb  call    cs:__imp_VariantInit
0x180017ee2  nop     dword ptr [rax+rax+00h]
0x180017ee7  xor     ecx, ecx
0x180017ee9  jmp     loc_180017B85
0x180017eee  mov     eax, 8000FFFFh
0x180017ef3  jmp     loc_180017DDF
0x180017ef8  mov     rdi, rbx
0x180017efb  inc     rdi
0x180017efe  cmp     word ptr [rsi+rdi*2], 0
0x180017f03  jnz     short loc_180017EFB
0x180017f05  mov     edx, edi; unsigned int
0x180017f07  mov     [rbp+37h+var_B0], edi
0x180017f0a  xor     ecx, ecx; unsigned __int16 *
0x180017f0c  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x180017f11  mov     [rbp+37h+bstrString], rax
0x180017f15  mov     r12, rax
0x180017f18  test    edi, edi
0x180017f1a  jz      short loc_180017F2B
0x180017f1c  test    rax, rax
0x180017f1f  jnz     short loc_180017F2B
0x180017f21  mov     edi, 8007000Eh
0x180017f26  jmp     loc_180017DD5
0x180017f2b  lea     rax, [rbp+37h+var_B0]
0x180017f2f  mov     r9d, edi; unsigned int
0x180017f32  mov     r8, r12; unsigned __int16 *
0x180017f35  mov     [rsp+0F0h+String2], rax; unsigned int *
0x180017f3a  mov     edx, edi; unsigned int
0x180017f3c  mov     rcx, rsi; unsigned __int16 *
0x180017f3f  call    ?DecodeScriptCore@@YAJPEBGKPEAGKPEAK@Z; DecodeScriptCore(ushort const *,ulong,ushort *,ulong,ulong *)
0x180017f44  mov     edi, eax
0x180017f46  test    eax, eax
0x180017f48  js      loc_180017DC8
0x180017f4e  mov     ecx, [rbp+37h+var_B0]
0x180017f51  xor     eax, eax
0x180017f53  mov     rdi, [rbp+37h+var_88]
0x180017f57  mov     rsi, r12
0x180017f5a  mov     [r12+rcx*2], ax
0x180017f5f  xor     ecx, ecx
0x180017f61  jmp     loc_180017BE7
0x180017f66  mov     edi, 80070057h
0x180017f6b  jmp     loc_180017DC8
0x180017f70  mov     edi, ecx
0x180017f72  jmp     loc_180017C48
0x180017f77  mov     r15d, dword ptr [rbp+37h+var_A0+4]
0x180017f7b  xor     r14d, r14d
0x180017f7e  jmp     loc_180017C8C
0x180017f83  mov     r8d, ebx; int
0x180017f86  lea     rcx, [rbp+37h+Block]; this
0x180017f8a  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180017f8f  mov     edx, 20h ; ' '; unsigned __int16
0x180017f94  lea     rcx, [rbp+37h+Block]; this
0x180017f98  call    ?AppendCh@BuildString@@QEAAJG@Z; BuildString::AppendCh(ushort)
0x180017f9d  mov     r15d, dword ptr [rbp+37h+var_A0+4]
0x180017fa1  mov     r12, [rbp+37h+Block]
0x180017fa5  jmp     loc_180017CDB
0x180017faa  test    byte ptr [rdx+38h], 2
0x180017fae  jnz     loc_180017D5D
0x180017fb4  mov     rcx, r15; this
0x180017fb7  call    ?RegisterNamedItemHasCode@COleScript@@AEAAJPEAUNamedItem@@@Z; COleScript::RegisterNamedItemHasCode(NamedItem *)
0x180017fbc  mov     edi, eax
0x180017fbe  test    eax, eax
0x180017fc0  js      loc_180017E19
  ... truncated ...
```
