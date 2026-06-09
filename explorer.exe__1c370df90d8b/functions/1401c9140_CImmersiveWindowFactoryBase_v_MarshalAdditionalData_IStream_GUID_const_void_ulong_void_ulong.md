# CImmersiveWindowFactoryBase::v_MarshalAdditionalData(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x1401c9140`
- end: `0x1401c929a`
- name: `?v_MarshalAdditionalData@CImmersiveWindowFactoryBase@@EEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `346`
- prototype: `int(CImmersiveWindowFactoryBase *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1401c8d64`
- `0x1401c9140`

## import_xrefs

- `SHCORE!IStream_Write` at `0x1401c9165`
- `SHCORE!IStream_Write` at `0x1401c9182`
- `SHCORE!IStream_Write` at `0x1401c91a2`
- `SHCORE!IStream_Write` at `0x1401c91c2`
- `SHCORE!IStream_Write` at `0x1401c91de`
- `SHCORE!IStream_Write` at `0x1401c91fe`
- `SHCORE!IStream_Write` at `0x1401c921a`
- `SHCORE!IStream_Write` at `0x1401c923c`
- `SHCORE!IStream_Write` at `0x1401c9264`
- `SHCORE!IStream_Write` at `0x1401c927d`
- `SHCORE!IStream_Write` at `0x1401c9165`
- `SHCORE!IStream_Write` at `0x1401c9182`
- `SHCORE!IStream_Write` at `0x1401c91a2`
- `SHCORE!IStream_Write` at `0x1401c91c2`
- `SHCORE!IStream_Write` at `0x1401c91de`
- `SHCORE!IStream_Write` at `0x1401c91fe`
- `SHCORE!IStream_Write` at `0x1401c921a`
- `SHCORE!IStream_Write` at `0x1401c923c`
- `SHCORE!IStream_Write` at `0x1401c9264`
- `SHCORE!IStream_Write` at `0x1401c927d`

## pseudocode

```c
__int64 __fastcall CImmersiveWindowFactoryBase::v_MarshalAdditionalData(
        CImmersiveWindowFactoryBase *this,
        struct IStream *a2,
        const struct _GUID *a3,
        void *a4)
{
  HRESULT v6; // ebx
  __int64 v7; // rdx
  char pv; // [rsp+40h] [rbp+8h] BYREF

  v6 = IStream_Write(a2, (char *)this + 108, 0x10u);
  if ( v6 >= 0 )
  {
    v6 = IStream_Write(a2, (char *)this + 124, 4u);
    if ( v6 >= 0 )
    {
      v6 = IStream_Write(a2, (char *)this + 97, 1u);
      if ( v6 >= 0 )
      {
        pv = 0;
        v6 = IStream_Write(a2, &pv, 1u);
        if ( v6 >= 0 )
        {
          v6 = IStream_Write(a2, (char *)this + 136, 1u);
          if ( v6 >= 0 )
          {
            if ( !*((_BYTE *)this + 136) || (v6 = IStream_Write(a2, (char *)this + 140, 4u), v6 >= 0) )
            {
              v6 = IStream_Write(a2, (char *)this + 144, 1u);
              if ( v6 >= 0 )
              {
                if ( *((_BYTE *)this + 144) )
                  v6 = IStream_Write(a2, (char *)this + 148, 4u);
              }
            }
          }
        }
        LOBYTE(v7) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_LIACoreNavigationClient>::GetImpl'::`2'::impl,
          v7);
        if ( v6 >= 0 )
        {
          v6 = IStream_Write(a2, (char *)this + 104, 4u);
          if ( v6 >= 0 )
            return (unsigned int)IStream_Write(a2, (char *)this + 160, 1u);
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1401c9140  mov     [rsp+arg_8], rbx
0x1401c9145  mov     [rsp+arg_10], rbp
0x1401c914a  push    rsi
0x1401c914b  push    rdi
0x1401c914c  push    r15
0x1401c914e  sub     rsp, 20h
0x1401c9152  mov     rdi, rdx
0x1401c9155  mov     rsi, rcx
0x1401c9158  lea     rdx, [rcx+6Ch]; pv
0x1401c915c  mov     r8d, 10h; cb
0x1401c9162  mov     rcx, rdi; pstm
0x1401c9165  call    cs:__imp_IStream_Write
0x1401c916b  mov     ebx, eax
0x1401c916d  test    eax, eax
0x1401c916f  js      loc_1401C9285
0x1401c9175  lea     rdx, [rsi+7Ch]; pv
0x1401c9179  mov     r8d, 4; cb
0x1401c917f  mov     rcx, rdi; pstm
0x1401c9182  call    cs:__imp_IStream_Write
0x1401c9188  mov     ebx, eax
0x1401c918a  test    eax, eax
0x1401c918c  js      loc_1401C9285
0x1401c9192  mov     r15d, 1
0x1401c9198  lea     rdx, [rsi+61h]; pv
0x1401c919c  mov     r8d, r15d; cb
0x1401c919f  mov     rcx, rdi; pstm
0x1401c91a2  call    cs:__imp_IStream_Write
0x1401c91a8  mov     ebx, eax
0x1401c91aa  test    eax, eax
0x1401c91ac  js      loc_1401C9285
0x1401c91b2  mov     r8d, r15d; cb
0x1401c91b5  mov     [rsp+38h+pv], 0
0x1401c91ba  lea     rdx, [rsp+38h+pv]; pv
0x1401c91bf  mov     rcx, rdi; pstm
0x1401c91c2  call    cs:__imp_IStream_Write
0x1401c91c8  mov     ebx, eax
0x1401c91ca  test    eax, eax
0x1401c91cc  js      short loc_1401C9244
0x1401c91ce  lea     rbp, [rsi+88h]
0x1401c91d5  mov     r8d, r15d; cb
0x1401c91d8  mov     rdx, rbp; pv
0x1401c91db  mov     rcx, rdi; pstm
0x1401c91de  call    cs:__imp_IStream_Write
0x1401c91e4  mov     ebx, eax
0x1401c91e6  test    eax, eax
0x1401c91e8  js      short loc_1401C9244
0x1401c91ea  cmp     byte ptr [rbp+0], 0
0x1401c91ee  jz      short loc_1401C920A
0x1401c91f0  lea     rdx, [rsi+8Ch]; pv
0x1401c91f7  mov     rcx, rdi; pstm
0x1401c91fa  lea     r8d, [r15+3]; cb
0x1401c91fe  call    cs:__imp_IStream_Write
0x1401c9204  mov     ebx, eax
0x1401c9206  test    eax, eax
0x1401c9208  js      short loc_1401C9244
0x1401c920a  lea     rbp, [rsi+90h]
0x1401c9211  mov     r8d, r15d; cb
0x1401c9214  mov     rdx, rbp; pv
0x1401c9217  mov     rcx, rdi; pstm
0x1401c921a  call    cs:__imp_IStream_Write
0x1401c9220  mov     ebx, eax
0x1401c9222  test    eax, eax
0x1401c9224  js      short loc_1401C9244
0x1401c9226  cmp     byte ptr [rbp+0], 0
0x1401c922a  jz      short loc_1401C9244
0x1401c922c  lea     rdx, [rsi+94h]; pv
0x1401c9233  mov     r8d, 4; cb
0x1401c9239  mov     rcx, rdi; pstm
0x1401c923c  call    cs:__imp_IStream_Write
0x1401c9242  mov     ebx, eax
0x1401c9244  mov     dl, r15b
0x1401c9247  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient> `wil::Feature<__WilFeatureTraits_Feature_LIACoreNavigationClient>::GetImpl(void)'::`2'::impl
0x1401c924e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1401c9253  test    ebx, ebx
0x1401c9255  js      short loc_1401C9285
0x1401c9257  lea     rdx, [rsi+68h]; pv
0x1401c925b  mov     r8d, 4; cb
0x1401c9261  mov     rcx, rdi; pstm
0x1401c9264  call    cs:__imp_IStream_Write
0x1401c926a  mov     ebx, eax
0x1401c926c  test    eax, eax
0x1401c926e  js      short loc_1401C9285
0x1401c9270  lea     rdx, [rsi+0A0h]; pv
0x1401c9277  mov     r8d, r15d; cb
0x1401c927a  mov     rcx, rdi; pstm
0x1401c927d  call    cs:__imp_IStream_Write
0x1401c9283  mov     ebx, eax
0x1401c9285  mov     rbp, [rsp+38h+arg_10]
0x1401c928a  mov     eax, ebx
0x1401c928c  mov     rbx, [rsp+38h+arg_8]
0x1401c9291  add     rsp, 20h
0x1401c9295  pop     r15
0x1401c9297  pop     rdi
0x1401c9298  pop     rsi
0x1401c9299  retn
```
