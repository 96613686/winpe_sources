# CImmersiveWindowFactoryBase::v_MarshalAdditionalData(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x1401c7e10`
- end: `0x1401c7fab`
- name: `?v_MarshalAdditionalData@CImmersiveWindowFactoryBase@@EEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `411`
- prototype: `int(CImmersiveWindowFactoryBase *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1401c7a14`
- `0x1401c7e10`

## import_xrefs

- `SHCORE!IStream_Write` at `0x1401c7e35`
- `SHCORE!IStream_Write` at `0x1401c7e58`
- `SHCORE!IStream_Write` at `0x1401c7e7e`
- `SHCORE!IStream_Write` at `0x1401c7ea4`
- `SHCORE!IStream_Write` at `0x1401c7eca`
- `SHCORE!IStream_Write` at `0x1401c7ef0`
- `SHCORE!IStream_Write` at `0x1401c7f12`
- `SHCORE!IStream_Write` at `0x1401c7f3a`
- `SHCORE!IStream_Write` at `0x1401c7f68`
- `SHCORE!IStream_Write` at `0x1401c7f87`
- `SHCORE!IStream_Write` at `0x1401c7e35`
- `SHCORE!IStream_Write` at `0x1401c7e58`
- `SHCORE!IStream_Write` at `0x1401c7e7e`
- `SHCORE!IStream_Write` at `0x1401c7ea4`
- `SHCORE!IStream_Write` at `0x1401c7eca`
- `SHCORE!IStream_Write` at `0x1401c7ef0`
- `SHCORE!IStream_Write` at `0x1401c7f12`
- `SHCORE!IStream_Write` at `0x1401c7f3a`
- `SHCORE!IStream_Write` at `0x1401c7f68`
- `SHCORE!IStream_Write` at `0x1401c7f87`

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
0x1401c7e10  mov     [rsp+arg_8], rbx
0x1401c7e15  mov     [rsp+arg_10], rbp
0x1401c7e1a  push    rsi
0x1401c7e1b  push    rdi
0x1401c7e1c  push    r15
0x1401c7e1e  sub     rsp, 20h
0x1401c7e22  mov     rdi, rdx
0x1401c7e25  mov     rsi, rcx
0x1401c7e28  lea     rdx, [rcx+6Ch]; pv
0x1401c7e2c  mov     r8d, 10h; cb
0x1401c7e32  mov     rcx, rdi; pstm
0x1401c7e35  call    cs:__imp_IStream_Write
0x1401c7e3c  nop     dword ptr [rax+rax+00h]
0x1401c7e41  mov     ebx, eax
0x1401c7e43  test    eax, eax
0x1401c7e45  js      loc_1401C7F95
0x1401c7e4b  lea     rdx, [rsi+7Ch]; pv
0x1401c7e4f  mov     r8d, 4; cb
0x1401c7e55  mov     rcx, rdi; pstm
0x1401c7e58  call    cs:__imp_IStream_Write
0x1401c7e5f  nop     dword ptr [rax+rax+00h]
0x1401c7e64  mov     ebx, eax
0x1401c7e66  test    eax, eax
0x1401c7e68  js      loc_1401C7F95
0x1401c7e6e  mov     r15d, 1
0x1401c7e74  lea     rdx, [rsi+61h]; pv
0x1401c7e78  mov     r8d, r15d; cb
0x1401c7e7b  mov     rcx, rdi; pstm
0x1401c7e7e  call    cs:__imp_IStream_Write
0x1401c7e85  nop     dword ptr [rax+rax+00h]
0x1401c7e8a  mov     ebx, eax
0x1401c7e8c  test    eax, eax
0x1401c7e8e  js      loc_1401C7F95
0x1401c7e94  mov     r8d, r15d; cb
0x1401c7e97  mov     [rsp+38h+pv], 0
0x1401c7e9c  lea     rdx, [rsp+38h+pv]; pv
0x1401c7ea1  mov     rcx, rdi; pstm
0x1401c7ea4  call    cs:__imp_IStream_Write
0x1401c7eab  nop     dword ptr [rax+rax+00h]
0x1401c7eb0  mov     ebx, eax
0x1401c7eb2  test    eax, eax
0x1401c7eb4  js      loc_1401C7F48
0x1401c7eba  lea     rbp, [rsi+88h]
0x1401c7ec1  mov     r8d, r15d; cb
0x1401c7ec4  mov     rdx, rbp; pv
0x1401c7ec7  mov     rcx, rdi; pstm
0x1401c7eca  call    cs:__imp_IStream_Write
0x1401c7ed1  nop     dword ptr [rax+rax+00h]
0x1401c7ed6  mov     ebx, eax
0x1401c7ed8  test    eax, eax
0x1401c7eda  js      short loc_1401C7F48
0x1401c7edc  cmp     byte ptr [rbp+0], 0
0x1401c7ee0  jz      short loc_1401C7F02
0x1401c7ee2  lea     rdx, [rsi+8Ch]; pv
0x1401c7ee9  mov     rcx, rdi; pstm
0x1401c7eec  lea     r8d, [r15+3]; cb
0x1401c7ef0  call    cs:__imp_IStream_Write
0x1401c7ef7  nop     dword ptr [rax+rax+00h]
0x1401c7efc  mov     ebx, eax
0x1401c7efe  test    eax, eax
0x1401c7f00  js      short loc_1401C7F48
0x1401c7f02  lea     rbp, [rsi+90h]
0x1401c7f09  mov     r8d, r15d; cb
0x1401c7f0c  mov     rdx, rbp; pv
0x1401c7f0f  mov     rcx, rdi; pstm
0x1401c7f12  call    cs:__imp_IStream_Write
0x1401c7f19  nop     dword ptr [rax+rax+00h]
0x1401c7f1e  mov     ebx, eax
0x1401c7f20  test    eax, eax
0x1401c7f22  js      short loc_1401C7F48
0x1401c7f24  cmp     byte ptr [rbp+0], 0
0x1401c7f28  jz      short loc_1401C7F48
0x1401c7f2a  lea     rdx, [rsi+94h]; pv
0x1401c7f31  mov     r8d, 4; cb
0x1401c7f37  mov     rcx, rdi; pstm
0x1401c7f3a  call    cs:__imp_IStream_Write
0x1401c7f41  nop     dword ptr [rax+rax+00h]
0x1401c7f46  mov     ebx, eax
0x1401c7f48  mov     dl, r15b
0x1401c7f4b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient> `wil::Feature<__WilFeatureTraits_Feature_LIACoreNavigationClient>::GetImpl(void)'::`2'::impl
0x1401c7f52  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_LIACoreNavigationClient@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LIACoreNavigationClient>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1401c7f57  test    ebx, ebx
0x1401c7f59  js      short loc_1401C7F95
0x1401c7f5b  lea     rdx, [rsi+68h]; pv
0x1401c7f5f  mov     r8d, 4; cb
0x1401c7f65  mov     rcx, rdi; pstm
0x1401c7f68  call    cs:__imp_IStream_Write
0x1401c7f6f  nop     dword ptr [rax+rax+00h]
0x1401c7f74  mov     ebx, eax
0x1401c7f76  test    eax, eax
0x1401c7f78  js      short loc_1401C7F95
0x1401c7f7a  lea     rdx, [rsi+0A0h]; pv
0x1401c7f81  mov     r8d, r15d; cb
0x1401c7f84  mov     rcx, rdi; pstm
0x1401c7f87  call    cs:__imp_IStream_Write
0x1401c7f8e  nop     dword ptr [rax+rax+00h]
0x1401c7f93  mov     ebx, eax
0x1401c7f95  mov     rbp, [rsp+38h+arg_10]
0x1401c7f9a  mov     eax, ebx
0x1401c7f9c  mov     rbx, [rsp+38h+arg_8]
0x1401c7fa1  add     rsp, 20h
0x1401c7fa5  pop     r15
0x1401c7fa7  pop     rdi
0x1401c7fa8  pop     rsi
0x1401c7fa9  retn
```
