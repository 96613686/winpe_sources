# COleScript::ParseScriptTextCore(ushort const *,ushort const *,IUnknown *,ushort const *,unsigned __int64,ulong,ulong,tagVARIANT *,tagEXCEPINFO *)

- ea: `0x18001aa80`
- end: `0x18001af5d`
- name: `?ParseScriptTextCore@COleScript@@QEAAJPEBG0PEAUIUnknown@@0_KKKPEAUtagVARIANT@@PEAUtagEXCEPINFO@@@Z`
- size: `1245`
- prototype: `__int64 __fastcall(COleScript *this, const unsigned __int16 *, unsigned __int16 *, struct IUnknown *, wchar_t *, unsigned __int64, unsigned int, __int16, struct tagVARIANT *pvarg, struct tagEXCEPINFO *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18001aa10`

## callees

- `0x180004470`
- `0x18000895c`
- `0x18000ad40`
- `0x180019e50`
- `0x18001aa80`
- `0x18001af64`
- `0x18001b2a8`
- `0x180046510`
- `0x18004ab4c`
- `0x18007c7d8`
- `0x180088584`
- `0x180094282`
- `0x1800942d0`

## import_xrefs

- `msvcrt!free` at `0x18001ad92`
- `msvcrt!free` at `0x18001ad92`
- `msvcrt!_wcsdup` at `0x18001ad81`
- `msvcrt!_wcsdup` at `0x18001ad81`
- `OLEAUT32!__imp_SysFreeString` at `0x18001af52`
- `OLEAUT32!__imp_SysFreeString` at `0x18001af52`
- `OLEAUT32!__imp_VariantInit` at `0x18001ae4b`
- `OLEAUT32!__imp_VariantInit` at `0x18001ae4b`
- `KERNEL32!GetCurrentThreadId` at `0x18001aada`
- `KERNEL32!GetCurrentThreadId` at `0x18001aada`

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
      *a10 = (struct tagEXCEPINFO)zmmword_1800A0280;
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
        *((_WORD *)v25 + 2) = asc_1800A02E0[2];
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
0x18001aa80  push    rbp
0x18001aa82  push    rbx
0x18001aa83  push    rsi
0x18001aa84  push    rdi
0x18001aa85  push    r12
0x18001aa87  push    r14
0x18001aa89  push    r15
0x18001aa8b  lea     rbp, [rsp-7]
0x18001aa90  sub     rsp, 0C0h
0x18001aa97  mov     rax, cs:__security_cookie
0x18001aa9e  xor     rax, rsp
0x18001aaa1  mov     [rbp+37h+var_38], rax
0x18001aaa5  mov     rax, [rbp+37h+arg_20]
0x18001aaa9  mov     rdi, r8
0x18001aaac  mov     r12, [rbp+37h+pvarg]
0x18001aab3  mov     rsi, rdx
0x18001aab6  mov     r14, [rbp+37h+arg_48]
0x18001aabd  mov     r15, rcx
0x18001aac0  mov     ebx, [rcx+104h]
0x18001aac6  mov     [rbp+37h+var_68], rax
0x18001aaca  mov     [rbp+37h+var_60], r12
0x18001aace  mov     [rbp+37h+var_70], r14
0x18001aad2  mov     [rbp+37h+var_88], r8
0x18001aad6  mov     [rbp+37h+var_90], rcx
0x18001aada  call    cs:__imp_GetCurrentThreadId
0x18001aae0  cmp     eax, ebx
0x18001aae2  jnz     loc_18001AE58
0x18001aae8  xor     ecx, ecx
0x18001aaea  mov     [rsp+0F0h+arg_18], r13
0x18001aaf2  mov     [rbp+37h+bstrString], rcx
0x18001aaf6  test    r12, r12
0x18001aaf9  jnz     loc_18001AE48
0x18001aaff  test    r14, r14
0x18001ab02  jz      short loc_18001AB33
0x18001ab04  movaps  xmm0, xmmword ptr cs:zmmword_1800A0280
0x18001ab0b  movaps  xmm1, xmmword ptr cs:zmmword_1800A0280+10h
0x18001ab12  movups  xmmword ptr [r14], xmm0
0x18001ab16  movaps  xmm0, xmmword ptr cs:zmmword_1800A0280+20h
0x18001ab1d  movups  xmmword ptr [r14+10h], xmm1
0x18001ab22  movaps  xmm1, xmmword ptr cs:zmmword_1800A0280+30h
0x18001ab29  movups  xmmword ptr [r14+20h], xmm0
0x18001ab2e  movups  xmmword ptr [r14+30h], xmm1
0x18001ab33  mov     r13d, dword ptr [rbp+37h+arg_38]
0x18001ab37  and     r13d, 3E3h
0x18001ab3e  test    r12, r12
0x18001ab41  jz      loc_18001AD9A
0x18001ab47  bts     r13d, 1Fh
0x18001ab4c  cmp     dword ptr [r15+2B0h], 0
0x18001ab54  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001ab5b  jnz     loc_18001AE62
0x18001ab61  test    rsi, rsi
0x18001ab64  jz      loc_18001AF48
0x18001ab6a  cmp     cx, [rsi]
0x18001ab6d  jz      loc_18001AF48
0x18001ab73  mov     [rbp+37h+var_B0], ecx
0x18001ab76  mov     [rbp+37h+var_80], rcx
0x18001ab7a  test    rdi, rdi
0x18001ab7d  jnz     loc_18001AE15
0x18001ab83  mov     r14, [rbp+37h+var_90]
0x18001ab87  mov     r12, rcx
0x18001ab8a  mov     [rbp+37h+Block], rcx
0x18001ab8e  mov     r15d, ecx
0x18001ab91  mov     [rbp+37h+var_A0], 0
0x18001ab99  mov     [rbp+37h+var_98], ecx
0x18001ab9c  mov     r14, [r14+0B8h]
0x18001aba3  test    r14, r14
0x18001aba6  jz      loc_18001AEDA
0x18001abac  mov     rdi, rbx
0x18001abaf  nop
0x18001abb0  inc     rdi
0x18001abb3  cmp     word ptr [r14+rdi*2], 0
0x18001abb9  jnz     short loc_18001ABB0
0x18001abbb  test    edi, edi
0x18001abbd  js      loc_18001AEE5
0x18001abc3  mov     edx, edi; int
0x18001abc5  lea     rcx, [rbp+37h+Block]; this
0x18001abc9  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x18001abce  mov     r12, [rbp+37h+Block]
0x18001abd2  test    eax, eax
0x18001abd4  jz      loc_18001AEE1
0x18001abda  movsxd  r15, dword ptr [rbp+37h+var_A0+4]
0x18001abde  mov     rdx, r14; Src
0x18001abe1  mov     r8d, edi
0x18001abe4  add     r8, r8; Size
0x18001abe7  lea     rcx, [r12+r15*2]; void *
0x18001abeb  call    memcpy_0
0x18001abf0  add     r15d, edi
0x18001abf3  xor     r14d, r14d
0x18001abf6  mov     dword ptr [rbp+37h+var_A0+4], r15d
0x18001abfa  test    r12, r12
0x18001abfd  jz      short loc_18001AC07
0x18001abff  movsxd  rcx, r15d
0x18001ac02  mov     [r12+rcx*2], r14w
0x18001ac07  lea     edx, [r15+3]; int
0x18001ac0b  cmp     edx, r15d
0x18001ac0e  jl      short loc_18001AC49
0x18001ac10  cmp     edx, dword ptr [rbp+37h+var_A0]
0x18001ac13  jge     loc_18001ADBB
0x18001ac19  movsxd  rax, r15d
0x18001ac1c  add     r15d, 3
0x18001ac20  mov     dword ptr [rbp+37h+var_A0+4], r15d
0x18001ac24  lea     rcx, [r12+rax*2]
0x18001ac28  mov     rax, qword ptr cs:asc_1800A02E0; " - "
0x18001ac2f  mov     [rcx], eax
0x18001ac31  movzx   eax, word ptr cs:asc_1800A02E0+4; " "
0x18001ac38  mov     [rcx+4], ax
0x18001ac3c  test    r12, r12
0x18001ac3f  jz      short loc_18001AC49
0x18001ac41  movsxd  rcx, r15d
0x18001ac44  mov     [r12+rcx*2], r14w
0x18001ac49  mov     rdx, [rbp+37h+var_88]; unsigned __int16 *
0x18001ac4d  test    rdx, rdx
0x18001ac50  jnz     loc_18001AEED
0x18001ac56  lea     edx, [r15+0Ch]; int
0x18001ac5a  cmp     edx, r15d
0x18001ac5d  jl      short loc_18001AC9B
0x18001ac5f  cmp     edx, dword ptr [rbp+37h+var_A0]
0x18001ac62  jge     loc_18001ADD9
0x18001ac68  movups  xmm0, xmmword ptr cs:aScriptBlock; "script block"
0x18001ac6f  movsxd  rax, r15d
0x18001ac72  add     r15d, 0Ch
0x18001ac76  mov     dword ptr [rbp+37h+var_A0+4], r15d
0x18001ac7a  movups  xmmword ptr [r12+rax*2], xmm0
0x18001ac7f  movsd   xmm1, qword ptr cs:aScriptBlock+10h; "lock"
0x18001ac87  movsd   qword ptr [r12+rax*2+10h], xmm1
0x18001ac8e  test    r12, r12
0x18001ac91  jz      short loc_18001AC9B
0x18001ac93  movsxd  rcx, r15d
0x18001ac96  mov     [r12+rcx*2], r14w
0x18001ac9b  cmp     [rbp+37h+var_98], 0
0x18001ac9f  jnz     loc_18001AF35
0x18001aca5  test    r12, r12
0x18001aca8  jz      loc_18001AD7A
0x18001acae  mov     [rbp+37h+Block], r14
0x18001acb2  mov     [rbp+37h+var_A0], 0
0x18001acba  mov     [rbp+37h+var_98], r14d
0x18001acbe  test    r12, r12
0x18001acc1  jz      loc_18001AF35
0x18001acc7  mov     rdx, [rbp+37h+var_80]; struct NamedItem *
0x18001accb  mov     r15, [rbp+37h+var_90]
0x18001accf  test    rdx, rdx
0x18001acd2  jnz     loc_18001AF14
0x18001acd8  mov     rax, [rbp+37h+arg_28]
0x18001acdc  mov     [rbp+37h+var_58], rax
0x18001ace0  mov     eax, [rbp+37h+arg_30]
0x18001ace3  mov     [rbp+37h+var_50], eax
0x18001ace6  mov     [rbp+37h+var_4C], 0
0x18001acee  xchg    ax, ax
0x18001acf0  inc     rbx
0x18001acf3  cmp     word ptr [rsi+rbx*2], 0
0x18001acf8  jnz     short loc_18001ACF0
0x18001acfa  mov     eax, [rbp+37h+var_B0]
0x18001acfd  lea     r9, [rbp+37h+var_58]; struct SRCINFO *
0x18001ad01  mov     [rsp+0F0h+var_B8], r14; struct CScriptBody **
0x18001ad06  mov     r8d, r13d; unsigned int
0x18001ad09  mov     [rbp+37h+var_3C], r14d
0x18001ad0d  mov     rdx, rsi; unsigned __int16 *
0x18001ad10  mov     r14, [rbp+37h+var_70]
0x18001ad14  mov     rcx, r15; this
0x18001ad17  mov     [rbp+37h+var_40], eax
0x18001ad1a  mov     rax, [rbp+37h+var_68]
0x18001ad1e  mov     [rsp+0F0h+var_C0], r14; struct tagEXCEPINFO *
0x18001ad23  mov     [rsp+0F0h+var_C8], r12; unsigned __int16 *
0x18001ad28  mov     [rsp+0F0h+String2], rax; String2
0x18001ad2d  mov     [rbp+37h+var_44], ebx
0x18001ad30  call    ?CreateScriptBody@COleScript@@QEAAJPEBGKPEAVSRCINFO@@00PEAUtagEXCEPINFO@@PEAPEAVCScriptBody@@@Z; COleScript::CreateScriptBody(ushort const *,ulong,SRCINFO *,ushort const *,ushort const *,tagEXCEPINFO *,CScriptBody * *)
0x18001ad35  mov     edi, eax
0x18001ad37  test    r13d, r13d
0x18001ad3a  js      loc_18001ADF7
0x18001ad40  test    r12, r12
0x18001ad43  jnz     short loc_18001AD8F
0x18001ad45  mov     rcx, [rbp+37h+bstrString]; bstrString
0x18001ad49  test    rcx, rcx
0x18001ad4c  jnz     loc_18001AF52
0x18001ad52  mov     r13, [rsp+0F0h+arg_18]
0x18001ad5a  mov     eax, edi
0x18001ad5c  mov     rcx, [rbp+37h+var_38]
0x18001ad60  xor     rcx, rsp; StackCookie
0x18001ad63  call    __security_check_cookie
0x18001ad68  add     rsp, 0C0h
0x18001ad6f  pop     r15
0x18001ad71  pop     r14
0x18001ad73  pop     r12
0x18001ad75  pop     rdi
0x18001ad76  pop     rsi
0x18001ad77  pop     rbx
0x18001ad78  pop     rbp
0x18001ad79  retn
0x18001ad7a  lea     rcx, String; String
0x18001ad81  call    cs:__imp__wcsdup
0x18001ad87  mov     r12, rax
0x18001ad8a  jmp     loc_18001ACAE
0x18001ad8f  mov     rcx, r12; Block
0x18001ad92  call    cs:__imp_free
0x18001ad98  jmp     short loc_18001AD45
0x18001ad9a  test    r13b, 1
0x18001ad9e  jnz     loc_18001AB4C
0x18001ada4  mov     eax, [r15+0A8h]
0x18001adab  dec     eax
0x18001adad  cmp     eax, 2
0x18001adb0  ja      loc_18001AB4C
0x18001adb6  jmp     loc_18001AB47
0x18001adbb  lea     rcx, [rbp+37h+Block]; this
0x18001adbf  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x18001adc4  mov     r15d, dword ptr [rbp+37h+var_A0+4]
0x18001adc8  mov     r12, [rbp+37h+Block]
0x18001adcc  test    eax, eax
0x18001adce  jnz     loc_18001AC19
0x18001add4  jmp     loc_18001AC49
0x18001add9  lea     rcx, [rbp+37h+Block]; this
0x18001addd  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x18001ade2  mov     r12, [rbp+37h+Block]
0x18001ade6  test    eax, eax
0x18001ade8  jz      loc_18001AC9B
0x18001adee  mov     r15d, dword ptr [rbp+37h+var_A0+4]
0x18001adf2  jmp     loc_18001AC68
0x18001adf7  test    edi, edi
0x18001adf9  js      loc_18001AD40
0x18001adff  mov     rdx, [rbp+37h+var_60]; struct tagVARIANT *
0x18001ae03  mov     r8, r14; struct tagEXCEPINFO *
0x18001ae06  mov     rcx, r15; this
0x18001ae09  call    ?ExecutePendingScripts@COleScript@@AEAAJPEAUtagVARIANT@@PEAUtagEXCEPINFO@@@Z; COleScript::ExecutePendingScripts(tagVARIANT *,tagEXCEPINFO *)
0x18001ae0e  mov     edi, eax
0x18001ae10  jmp     loc_18001AD40
0x18001ae15  cmp     word ptr [rdi], 0
0x18001ae19  jz      loc_18001AB83
0x18001ae1f  lea     rcx, [r15+138h]; this
0x18001ae26  mov     rdx, rdi; unsigned __int16 *
0x18001ae29  call    ?Find@NamedItemList@@QEAAPEAUNamedItem@@PEBG@Z; NamedItemList::Find(ushort const *)
0x18001ae2e  mov     [rbp+37h+var_80], rax
0x18001ae32  test    rax, rax
0x18001ae35  jz      loc_18001AED0
0x18001ae3b  mov     eax, [rax+34h]
0x18001ae3e  xor     ecx, ecx
0x18001ae40  mov     [rbp+37h+var_B0], eax
0x18001ae43  jmp     loc_18001AB83
0x18001ae48  mov     rcx, r12; pvarg
0x18001ae4b  call    cs:__imp_VariantInit
0x18001ae51  xor     ecx, ecx
0x18001ae53  jmp     loc_18001AAFF
0x18001ae58  mov     eax, 8000FFFFh
0x18001ae5d  jmp     loc_18001AD5C
0x18001ae62  mov     rdi, rbx
0x18001ae65  inc     rdi
0x18001ae68  cmp     word ptr [rsi+rdi*2], 0
0x18001ae6d  jnz     short loc_18001AE65
0x18001ae6f  mov     edx, edi; unsigned int
0x18001ae71  mov     [rbp+37h+var_B0], edi
0x18001ae74  xor     ecx, ecx; unsigned __int16 *
0x18001ae76  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18001ae7b  mov     [rbp+37h+bstrString], rax
0x18001ae7f  mov     r12, rax
0x18001ae82  test    edi, edi
0x18001ae84  jz      short loc_18001AE95
0x18001ae86  test    rax, rax
0x18001ae89  jnz     short loc_18001AE95
0x18001ae8b  mov     edi, 8007000Eh
0x18001ae90  jmp     loc_18001AD52
0x18001ae95  lea     rax, [rbp+37h+var_B0]
0x18001ae99  mov     r9d, edi; unsigned int
0x18001ae9c  mov     r8, r12; unsigned __int16 *
0x18001ae9f  mov     [rsp+0F0h+String2], rax; unsigned int *
0x18001aea4  mov     edx, edi; unsigned int
0x18001aea6  mov     rcx, rsi; unsigned __int16 *
0x18001aea9  call    ?DecodeScriptCore@@YAJPEBGKPEAGKPEAK@Z; DecodeScriptCore(ushort const *,ulong,ushort *,ulong,ulong *)
0x18001aeae  mov     edi, eax
0x18001aeb0  test    eax, eax
0x18001aeb2  js      loc_18001AD45
0x18001aeb8  mov     ecx, [rbp+37h+var_B0]
0x18001aebb  xor     eax, eax
0x18001aebd  mov     rdi, [rbp+37h+var_88]
0x18001aec1  mov     rsi, r12
0x18001aec4  mov     [r12+rcx*2], ax
0x18001aec9  xor     ecx, ecx
0x18001aecb  jmp     loc_18001AB61
0x18001aed0  mov     edi, 80070057h
0x18001aed5  jmp     loc_18001AD45
0x18001aeda  mov     edi, ecx
0x18001aedc  jmp     loc_18001ABC3
0x18001aee1  mov     r15d, dword ptr [rbp+37h+var_A0+4]
0x18001aee5  xor     r14d, r14d
0x18001aee8  jmp     loc_18001AC07
0x18001aeed  mov     r8d, ebx; int
0x18001aef0  lea     rcx, [rbp+37h+Block]; this
0x18001aef4  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18001aef9  mov     edx, 20h ; ' '; unsigned __int16
0x18001aefe  lea     rcx, [rbp+37h+Block]; this
0x18001af02  call    ?AppendCh@BuildString@@QEAAJG@Z; BuildString::AppendCh(ushort)
0x18001af07  mov     r15d, dword ptr [rbp+37h+var_A0+4]
0x18001af0b  mov     r12, [rbp+37h+Block]
0x18001af0f  jmp     loc_18001AC56
0x18001af14  test    byte ptr [rdx+38h], 2
0x18001af18  jnz     loc_18001ACD8
0x18001af1e  mov     rcx, r15; this
0x18001af21  call    ?RegisterNamedItemHasCode@COleScript@@AEAAJPEAUNamedItem@@@Z; COleScript::RegisterNamedItemHasCode(NamedItem *)
0x18001af26  mov     edi, eax
0x18001af28  test    eax, eax
0x18001af2a  js      loc_18001AD8F
0x18001af30  jmp     loc_18001ACD8
0x18001af35  lea     rcx, [rbp+37h+Block]; this
  ... truncated ...
```
