# HyperVStorage::SetVariantValue(ushort const *,tagVARIANT const &)

- ea: `0x1800784ac`
- end: `0x180078803`
- name: `?SetVariantValue@HyperVStorage@@QEAAJPEBGAEBUtagVARIANT@@@Z`
- size: `855`
- prototype: `int(HyperVStorage *__hidden this, const unsigned __int16 *, const struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180096980`

## callees

- `0x1800067c0`
- `0x180077ecc`
- `0x1800784ac`
- `0x180082244`
- `0x1800a3010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800784f0`
- `OLEAUT32!__imp_VariantInit` at `0x1800784f0`
- `OLEAUT32!__imp_VariantClear` at `0x18007877a`
- `OLEAUT32!__imp_VariantClear` at `0x18007877a`
- `OLEAUT32!__imp_VariantChangeType` at `0x180078554`
- `OLEAUT32!__imp_VariantChangeType` at `0x18007863a`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800786f1`
- `OLEAUT32!__imp_VariantChangeType` at `0x18007871d`
- `OLEAUT32!__imp_VariantChangeType` at `0x180078554`
- `OLEAUT32!__imp_VariantChangeType` at `0x18007863a`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800786f1`
- `OLEAUT32!__imp_VariantChangeType` at `0x18007871d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800785c2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800785c2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18007859c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18007859c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180078570`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180078570`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18007876f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18007876f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18007868f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18007868f`

## pseudocode

```c
__int64 __fastcall HyperVStorage::SetVariantValue(
        HyperVStorage *this,
        const unsigned __int16 *a2,
        const struct tagVARIANT *p_pvarg)
{
  SAFEARRAY *parray; // rsi
  unsigned int vt; // eax
  HRESULT v8; // eax
  HRESULT v9; // eax
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  __int64 v12; // r9
  __int64 v13; // r8
  HRESULT v14; // eax
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rdi
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *v16; // rax
  HRESULT v17; // eax
  HRESULT v18; // eax
  void *ppvData; // [rsp+40h] [rbp-68h] BYREF
  LONG plLbound; // [rsp+48h] [rbp-60h] BYREF
  LONG plUbound; // [rsp+4Ch] [rbp-5Ch] BYREF
  BOOL v23; // [rsp+50h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-50h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  parray = 0;
  VariantInit(&pvarg);
  try
  {
    if ( !(*(unsigned int (**)(void))(*(_QWORD *)this + 288LL))() )
      HvsThrowHResultError(-2147467259);
    if ( !a2 )
      HvsThrowHResultError(-2147024809);
    ppvData = 0;
    v23 = 0;
    vt = p_pvarg->vt;
    if ( (vt & 0x2000) != 0 )
    {
      if ( (vt & 0xFFF) != 0x11 )
      {
        v8 = VariantChangeType(&pvarg, p_pvarg, 0, 0x2011u);
        if ( v8 < 0 )
          HvsThrowHResultError(v8);
        p_pvarg = &pvarg;
      }
      v9 = SafeArrayAccessData(p_pvarg->parray, &ppvData);
      if ( v9 < 0 )
        HvsThrowHResultError(v9);
      parray = p_pvarg->parray;
      plUbound = 0;
      plLbound = 0;
      LBound = SafeArrayGetLBound(parray, 1u, &plLbound);
      if ( LBound < 0 )
        HvsThrowHResultError(LBound);
      if ( plLbound )
        HvsThrowHResultError(-2147024809);
      UBound = SafeArrayGetUBound(p_pvarg->parray, 1u, &plUbound);
      if ( UBound < 0 )
        HvsThrowHResultError(UBound);
      v12 = (unsigned int)(plUbound + 1);
      v13 = 7;
      goto LABEL_44;
    }
    if ( vt <= 0x10 )
    {
      if ( vt != 16 && vt != 2 && vt != 3 )
      {
        switch ( vt )
        {
          case 4u:
LABEL_22:
            v14 = VariantChangeType(&pvarg, p_pvarg, 0, 5u);
            if ( v14 < 0 )
              HvsThrowHResultError(v14);
            p_pvarg = &pvarg;
            goto LABEL_24;
          case 5u:
LABEL_24:
            p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&p_pvarg->llVal;
            if ( p_llVal->dblVal > 1.797693134862314e308 )
              HvsThrowHResultError(-2147352566);
            ppvData = p_llVal;
            v12 = 8;
            v13 = 5;
            goto LABEL_44;
          case 8u:
            ppvData = p_pvarg->bstrVal;
            v12 = SysStringByteLen((BSTR)ppvData);
            v13 = 6;
LABEL_44:
            HyperVStorage::SetValueInternal(this, a2, v13, v12, ppvData);
            goto LABEL_62;
        }
        if ( vt != 11 )
        {
          if ( vt == 14 )
            goto LABEL_22;
LABEL_57:
          HvsThrowHResultError(-2147352571);
        }
        v23 = p_pvarg->iVal != 0;
        v16 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&v23;
        v12 = 4;
        v13 = 8;
LABEL_43:
        ppvData = v16;
        goto LABEL_44;
      }
      goto LABEL_36;
    }
    if ( vt != 17 && vt != 18 && vt != 19 )
    {
      switch ( vt )
      {
        case 0x14u:
LABEL_38:
          v13 = 3;
LABEL_42:
          v12 = 8;
          v16 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&p_pvarg->llVal;
          goto LABEL_43;
        case 0x15u:
LABEL_41:
          v13 = 4;
          goto LABEL_42;
        case 0x16u:
LABEL_36:
          v17 = VariantChangeType(&pvarg, p_pvarg, 0, 0x14u);
          if ( v17 < 0 )
            HvsThrowHResultError(v17);
          p_pvarg = &pvarg;
          goto LABEL_38;
      }
      if ( vt != 23 )
        goto LABEL_57;
    }
    v18 = VariantChangeType(&pvarg, p_pvarg, 0, 0x15u);
    if ( v18 < 0 )
      HvsThrowHResultError(v18);
    p_pvarg = &pvarg;
    goto LABEL_41;
  }
  catch ( ... )
  {
    HvsGetHResultForThrownException();
  }
LABEL_62:
  if ( parray )
    SafeArrayUnaccessData(parray);
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x1800784ac  push    rbx
0x1800784ae  push    rsi
0x1800784af  push    rdi
0x1800784b0  push    r14
0x1800784b2  push    r15
0x1800784b4  sub     rsp, 80h
0x1800784bb  mov     rax, cs:__security_cookie
0x1800784c2  xor     rax, rsp
0x1800784c5  mov     [rsp+0A8h+var_38], rax
0x1800784ca  mov     rdi, r8
0x1800784cd  mov     r14, rdx
0x1800784d0  mov     r15, rcx
0x1800784d3  xorps   xmm0, xmm0
0x1800784d6  xor     eax, eax
0x1800784d8  movups  xmmword ptr [rsp+0A8h+pvarg], xmm0
0x1800784dd  mov     qword ptr [rsp+0A8h+pvarg+10h], rax
0x1800784e2  xor     ebx, ebx
0x1800784e4  mov     esi, ebx
0x1800784e6  mov     [rsp+0A8h+var_70], rbx
0x1800784eb  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1800784f0  call    cs:__imp_VariantInit
0x1800784f6  nop
0x1800784f7  mov     rax, [r15]
0x1800784fa  mov     rcx, r15
0x1800784fd  mov     rax, [rax+120h]
0x180078504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078509  test    eax, eax
0x18007850b  jz      loc_18007879E
0x180078511  test    r14, r14
0x180078514  jz      loc_1800787A8
0x18007851a  mov     [rsp+0A8h+ppvData], rbx
0x18007851f  mov     [rsp+0A8h+var_58], ebx
0x180078523  movzx   eax, word ptr [rdi]
0x180078526  bt      ax, 0Dh
0x18007852b  jnb     loc_1800785E3
0x180078531  mov     ecx, 0FFFh
0x180078536  and     ax, cx
0x180078539  mov     edx, 11h
0x18007853e  cmp     ax, dx
0x180078541  jz      short loc_180078567
0x180078543  mov     r9d, 2011h; vt
0x180078549  xor     r8d, r8d; wFlags
0x18007854c  mov     rdx, rdi; pvarSrc
0x18007854f  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x180078554  call    cs:__imp_VariantChangeType
0x18007855a  test    eax, eax
0x18007855c  js      loc_1800787BC
0x180078562  lea     rdi, [rsp+0A8h+pvarg]
0x180078567  lea     rdx, [rsp+0A8h+ppvData]; ppvData
0x18007856c  mov     rcx, [rdi+8]; psa
0x180078570  call    cs:__imp_SafeArrayAccessData
0x180078576  test    eax, eax
0x180078578  js      loc_1800787D1
0x18007857e  mov     rsi, [rdi+8]
0x180078582  mov     [rsp+0A8h+var_70], rsi
0x180078587  mov     [rsp+0A8h+plUbound], ebx
0x18007858b  mov     [rsp+0A8h+plLbound], ebx
0x18007858f  lea     r8, [rsp+0A8h+plLbound]; plLbound
0x180078594  mov     edx, 1; nDim
0x180078599  mov     rcx, rsi; psa
0x18007859c  call    cs:__imp_SafeArrayGetLBound
0x1800785a2  test    eax, eax
0x1800785a4  js      loc_1800787CA
0x1800785aa  cmp     [rsp+0A8h+plLbound], ebx
0x1800785ae  jnz     loc_1800787B2
0x1800785b4  lea     r8, [rsp+0A8h+plUbound]; plUbound
0x1800785b9  mov     edx, 1; nDim
0x1800785be  mov     rcx, [rdi+8]; psa
0x1800785c2  call    cs:__imp_SafeArrayGetUBound
0x1800785c8  test    eax, eax
0x1800785ca  js      loc_1800787C3
0x1800785d0  mov     r9d, [rsp+0A8h+plUbound]
0x1800785d5  inc     r9d
0x1800785d8  mov     r8d, 7
0x1800785de  jmp     loc_180078745
0x1800785e3  mov     ecx, eax
0x1800785e5  cmp     eax, 10h
0x1800785e8  ja      loc_1800786B7
0x1800785ee  jz      loc_1800786E0
0x1800785f4  sub     ecx, 2
0x1800785f7  jz      loc_1800786E0
0x1800785fd  sub     ecx, 1
0x180078600  jz      loc_1800786E0
0x180078606  sub     ecx, 1
0x180078609  jz      short loc_180078629
0x18007860b  sub     ecx, 1
0x18007860e  jz      short loc_18007864D
0x180078610  mov     r8d, 3
0x180078616  sub     ecx, r8d
0x180078619  jz      short loc_180078686
0x18007861b  sub     ecx, r8d
0x18007861e  jz      short loc_180078665
0x180078620  cmp     ecx, r8d
0x180078623  jnz     loc_1800787E9
0x180078629  mov     r9d, 5; vt
0x18007862f  xor     r8d, r8d; wFlags
0x180078632  mov     rdx, rdi; pvarSrc
0x180078635  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x18007863a  call    cs:__imp_VariantChangeType
0x180078640  test    eax, eax
0x180078642  js      loc_1800787E2
0x180078648  lea     rdi, [rsp+0A8h+pvarg]
0x18007864d  add     rdi, 8
0x180078651  movsd   xmm0, qword ptr [rdi]
0x180078655  comisd  xmm0, cs:__real@7feffffffffffff6
0x18007865d  ja      loc_1800787D8
0x180078663  jmp     short loc_1800786A3
0x180078665  mov     eax, ebx
0x180078667  cmp     [rdi+8], bx
0x18007866b  setnz   al
0x18007866e  mov     [rsp+0A8h+var_58], eax
0x180078672  lea     rax, [rsp+0A8h+var_58]
0x180078677  mov     r9d, 4
0x18007867d  lea     r8d, [r9+4]
0x180078681  jmp     loc_180078740
0x180078686  mov     rcx, [rdi+8]; bstr
0x18007868a  mov     [rsp+0A8h+ppvData], rcx
0x18007868f  call    cs:__imp_SysStringByteLen
0x180078695  mov     r9d, eax
0x180078698  mov     r8d, 6
0x18007869e  jmp     loc_180078745
0x1800786a3  mov     [rsp+0A8h+ppvData], rdi
0x1800786a8  mov     r9d, 8
0x1800786ae  lea     r8d, [r9-3]
0x1800786b2  jmp     loc_180078745
0x1800786b7  sub     ecx, 11h
0x1800786ba  jz      short loc_18007870C
0x1800786bc  sub     ecx, 1
0x1800786bf  jz      short loc_18007870C
0x1800786c1  sub     ecx, 1
0x1800786c4  jz      short loc_18007870C
0x1800786c6  sub     ecx, 1
0x1800786c9  jz      short loc_180078704
0x1800786cb  sub     ecx, 1
0x1800786ce  jz      short loc_180078730
0x1800786d0  sub     ecx, 1
0x1800786d3  jz      short loc_1800786E0
0x1800786d5  cmp     ecx, 1
0x1800786d8  jnz     loc_1800787E9
0x1800786de  jmp     short loc_18007870C
0x1800786e0  mov     r9d, 14h; vt
0x1800786e6  xor     r8d, r8d; wFlags
0x1800786e9  mov     rdx, rdi; pvarSrc
0x1800786ec  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x1800786f1  call    cs:__imp_VariantChangeType
0x1800786f7  test    eax, eax
0x1800786f9  js      loc_1800787F3
0x1800786ff  lea     rdi, [rsp+0A8h+pvarg]
0x180078704  mov     r8d, 3
0x18007870a  jmp     short loc_180078736
0x18007870c  mov     r9d, 15h; vt
0x180078712  xor     r8d, r8d; wFlags
0x180078715  mov     rdx, rdi; pvarSrc
0x180078718  lea     rcx, [rsp+0A8h+pvarg]; pvargDest
0x18007871d  call    cs:__imp_VariantChangeType
0x180078723  test    eax, eax
0x180078725  js      loc_1800787FA
0x18007872b  lea     rdi, [rsp+0A8h+pvarg]
0x180078730  mov     r8d, 4
0x180078736  mov     r9d, 8
0x18007873c  lea     rax, [rdi+8]
0x180078740  mov     [rsp+0A8h+ppvData], rax
0x180078745  mov     rax, [rsp+0A8h+ppvData]
0x18007874a  mov     [rsp+0A8h+var_88], rax
0x18007874f  mov     rdx, r14
0x180078752  mov     rcx, r15
0x180078755  call    ?SetValueInternal@HyperVStorage@@IEAAXPEBGW4HyperVStorageKeyType@@IPEBE@Z; HyperVStorage::SetValueInternal(ushort const *,HyperVStorageKeyType,uint,uchar const *)
0x18007875a  mov     edi, ebx
0x18007875c  jmp     short loc_180078767
0x18007875e  mov     edi, [rsp+0A8h+var_78]
0x180078762  mov     rsi, [rsp+0A8h+var_70]
0x180078767  test    rsi, rsi
0x18007876a  jz      short loc_180078775
0x18007876c  mov     rcx, rsi; psa
0x18007876f  call    cs:__imp_SafeArrayUnaccessData
0x180078775  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18007877a  call    cs:__imp_VariantClear
0x180078780  mov     eax, edi
0x180078782  mov     rcx, [rsp+0A8h+var_38]
0x180078787  xor     rcx, rsp; StackCookie
0x18007878a  call    __security_check_cookie
0x18007878f  add     rsp, 80h
0x180078796  pop     r15
0x180078798  pop     r14
0x18007879a  pop     rdi
0x18007879b  pop     rsi
0x18007879c  pop     rbx
0x18007879d  retn
0x18007879e  mov     ecx, 80004005h; int
0x1800787a3  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1800787a8  mov     ecx, 80070057h; int
0x1800787ad  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1800787b2  mov     ecx, 80070057h; int
0x1800787b7  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1800787bc  mov     ecx, eax; int
0x1800787be  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1800787c3  mov     ecx, eax; int
0x1800787c5  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1800787ca  mov     ecx, eax; int
0x1800787cc  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1800787d1  mov     ecx, eax; int
0x1800787d3  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1800787d8  mov     ecx, 8002000Ah; int
0x1800787dd  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1800787e2  mov     ecx, eax; int
0x1800787e4  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1800787e9  mov     ecx, 80020005h; int
0x1800787ee  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1800787f3  mov     ecx, eax; int
0x1800787f5  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x1800787fa  mov     ecx, eax; int
0x1800787fc  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
```
