# winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::factory_implementation::EapMethodRunnerOptions,winrt::Windows::Internal::Eap::Utility::IEapMethodRunnerOptionsFactory>::CreateInstance(uint,uchar,uint,uint,uint,uint,__int64,void *,void *,void * *)

- ea: `0x1800119e0`
- end: `0x180011a93`
- name: `?CreateInstance@?$produce@UEapMethodRunnerOptions@factory_implementation@Utility@Eap@Internal@Windows@winrt@@UIEapMethodRunnerOptionsFactory@34567@@impl@winrt@@UEAAHIEIIII_JPEAX1PEAPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(__int64, int, char, int, int, int, int, __int64, int, int, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800112ec`
- `0x1800119e0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::Eap::Utility::factory_implementation::EapMethodRunnerOptions,winrt::Windows::Internal::Eap::Utility::IEapMethodRunnerOptionsFactory>::CreateInstance(
        __int64 a1,
        int a2,
        char a3,
        int a4,
        int a5,
        int a6,
        int a7,
        __int64 a8,
        int a9,
        int a10,
        _QWORD *a11)
{
  _QWORD *v11; // rbx
  __int64 result; // rax
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF
  int v14; // [rsp+68h] [rbp+10h] BYREF
  int v15; // [rsp+70h] [rbp+18h] BYREF
  int v16; // [rsp+78h] [rbp+20h] BYREF

  v14 = a2;
  v11 = a11;
  *a11 = 0;
  v13 = a8;
  v16 = a4;
  LOBYTE(v15) = a3;
  try
  {
    winrt::make<winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerOptions,enum winrt::Windows::Internal::Eap::Utility::EapMethodFlags const &,unsigned char &,unsigned int &,unsigned int &,unsigned int &,unsigned int &,__int64 &,winrt::Windows::Storage::Streams::IBuffer const &,winrt::Windows::Storage::Streams::IBuffer const &>(
      (unsigned int)&a11,
      (unsigned int)&v14,
      (unsigned int)&v15,
      (unsigned int)&v16,
      (__int64)&a5,
      (__int64)&a6,
      (__int64)&a7,
      (__int64)&v13,
      (__int64)&a9,
      (__int64)&a10);
    *v11 = a11;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v15);
  }
  return result;
}

```

## disassembly

```asm
0x1800119e0  mov     [rsp+arg_8], edx
0x1800119e4  mov     r11, rsp
0x1800119e7  mov     [r11+8], rcx
0x1800119eb  push    rbx
0x1800119ec  sub     rsp, 50h
0x1800119f0  mov     rbx, [rsp+58h+arg_50]
0x1800119f8  mov     qword ptr [rbx], 0
0x1800119ff  mov     rax, [rsp+58h+arg_38]
0x180011a07  mov     [r11+8], rax
0x180011a0b  mov     eax, [rsp+58h+arg_30]
0x180011a12  mov     [r11+38h], eax
0x180011a16  mov     eax, [rsp+58h+arg_28]
0x180011a1d  mov     [r11+30h], eax
0x180011a21  mov     eax, [rsp+58h+arg_20]
0x180011a28  mov     [r11+28h], eax
0x180011a2c  mov     [r11+20h], r9d
0x180011a30  mov     [r11+18h], r8b
0x180011a34  lea     rax, [r11+50h]
0x180011a38  mov     [r11-10h], rax
0x180011a3c  lea     rax, [r11+48h]
0x180011a40  mov     [r11-18h], rax
0x180011a44  lea     rax, [r11+8]
0x180011a48  mov     [r11-20h], rax
0x180011a4c  lea     rax, [r11+38h]
0x180011a50  mov     [r11-28h], rax
0x180011a54  lea     rax, [r11+30h]
0x180011a58  mov     [r11-30h], rax
0x180011a5c  lea     rax, [r11+28h]
0x180011a60  mov     [r11-38h], rax
0x180011a64  lea     r9, [r11+20h]
0x180011a68  lea     r8, [r11+18h]
0x180011a6c  lea     rdx, [r11+10h]
0x180011a70  lea     rcx, [r11+58h]
0x180011a74  call    ??$make@UEapMethodRunnerOptions@implementation@Utility@Eap@Internal@Windows@winrt@@AEBW4EapMethodFlags@34567@AEAEAEAIAEAIAEAIAEAIAEA_JAEBUIBuffer@Streams@Storage@67@AEBU9Streams@Storage@67@@winrt@@YA?A_PAEBW4EapMethodFlags@Utility@Eap@Internal@Windows@0@AEAEAEAI222AEA_JAEBUIBuffer@Streams@Storage@50@4@Z
0x180011a79  mov     rax, [rsp+58h+arg_50]
0x180011a81  mov     [rbx], rax
0x180011a84  xor     eax, eax
0x180011a86  jmp     short loc_180011A8C
0x180011a88  mov     eax, [rsp+58h+arg_10]
0x180011a8c  add     rsp, 50h
0x180011a90  pop     rbx
0x180011a91  retn
```
