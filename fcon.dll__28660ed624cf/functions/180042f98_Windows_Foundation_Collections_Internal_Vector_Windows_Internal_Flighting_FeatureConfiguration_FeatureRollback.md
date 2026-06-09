# Windows::Foundation::Collections::Internal::Vector<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy,FeatureRollbackPolicyEquality,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy>>::IndexOfInternal(Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy *,uint,Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy,uint *,uchar *)

- ea: `0x180042f98`
- end: `0x180043059`
- name: `?IndexOfInternal@?$Vector@UFeatureRollbackPolicy@FeatureConfiguration@Flighting@Internal@Windows@@UFeatureRollbackPolicyEquality@@UPodLifetimeTraits@XWinRT@@U?$DefaultVectorOptions@UFeatureRollbackPolicy@FeatureConfiguration@Flighting@Internal@Windows@@@4Collections@Foundation@5@@Internal@Collections@Foundation@Windows@@AEAAJPEAUFeatureRollbackPolicy@FeatureConfiguration@Flighting@25@IU67825@PEAIPEAE@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180042ca0`

## callees

- `0x18000949c`
- `0x180042f98`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180042fdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180042fdf`

## string_xrefs

- `0x180042ff0`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy,FeatureRollbackPolicyEquality,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy>>::IndexOfInternal(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int *a5,
        _BYTE *a6)
{
  unsigned int v6; // ebx
  unsigned int v10; // edi
  HSTRING v11; // rcx
  __int64 v12; // rsi
  HRESULT v13; // eax
  bool v14; // al
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  INT32 result; // [rsp+70h] [rbp+18h] BYREF

  v6 = 0;
  if ( a3 )
  {
    v10 = 0;
    while ( (v6 & 0x80000000) == 0 )
    {
      v11 = *(HSTRING *)(a4 + 16);
      v12 = 32LL * v10;
      result = 0;
      v13 = WindowsCompareStringOrdinal(v11, *(HSTRING *)(v12 + a2 + 16), &result);
      v6 = v13;
      if ( v13 >= 0 )
      {
        v14 = !result && *(_DWORD *)a4 == *(_DWORD *)(v12 + a2) && *(_DWORD *)(a4 + 4) == *(_DWORD *)(v12 + a2 + 4);
        v6 = 0;
        if ( v14 )
        {
          *a6 = 1;
          *a5 = v10;
          return v6;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x68,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
          (const char *)(unsigned int)v13,
          v16);
      }
      if ( ++v10 >= a3 )
        return v6;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180042f98  push    rbx
0x180042f9a  push    rbp
0x180042f9b  push    rsi
0x180042f9c  push    rdi
0x180042f9d  push    r14
0x180042f9f  push    r15
0x180042fa1  sub     rsp, 28h
0x180042fa5  xor     ebx, ebx
0x180042fa7  mov     rbp, r9
0x180042faa  mov     r15d, r8d
0x180042fad  mov     r14, rdx
0x180042fb0  test    r8d, r8d
0x180042fb3  jz      loc_18004304A
0x180042fb9  xor     edi, edi
0x180042fbb  test    ebx, ebx
0x180042fbd  js      loc_18004304A
0x180042fc3  mov     rcx, [rbp+10h]; string1
0x180042fc7  lea     r8, [rsp+58h+result]; result
0x180042fcc  mov     esi, edi
0x180042fce  shl     rsi, 5
0x180042fd2  mov     [rsp+58h+result], 0
0x180042fda  mov     rdx, [rsi+r14+10h]; string2
0x180042fdf  call    cs:__imp_WindowsCompareStringOrdinal
0x180042fe5  mov     ebx, eax
0x180042fe7  test    eax, eax
0x180042fe9  jns     short loc_180043006
0x180042feb  mov     rcx, [rsp+58h]; this
0x180042ff0  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x180042ff7  mov     r9d, eax; char *
0x180042ffa  mov     edx, 68h ; 'h'; void *
0x180042fff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043004  jmp     short loc_18004302C
0x180043006  cmp     [rsp+58h+result], 0
0x18004300b  jnz     short loc_180043024
0x18004300d  mov     eax, [rsi+r14]
0x180043011  cmp     [rbp+0], eax
0x180043014  jnz     short loc_180043024
0x180043016  mov     eax, [rsi+r14+4]
0x18004301b  cmp     [rbp+4], eax
0x18004301e  jnz     short loc_180043024
0x180043020  mov     al, 1
0x180043022  jmp     short loc_180043026
0x180043024  xor     al, al
0x180043026  xor     ebx, ebx
0x180043028  test    al, al
0x18004302a  jnz     short loc_180043035
0x18004302c  inc     edi
0x18004302e  cmp     edi, r15d
0x180043031  jb      short loc_180042FBB
0x180043033  jmp     short loc_18004304A
0x180043035  mov     rax, [rsp+58h+arg_28]
0x18004303d  mov     byte ptr [rax], 1
0x180043040  mov     rax, [rsp+58h+arg_20]
0x180043048  mov     [rax], edi
0x18004304a  mov     eax, ebx
0x18004304c  add     rsp, 28h
0x180043050  pop     r15
0x180043052  pop     r14
0x180043054  pop     rdi
0x180043055  pop     rsi
0x180043056  pop     rbp
0x180043057  pop     rbx
0x180043058  retn
```
