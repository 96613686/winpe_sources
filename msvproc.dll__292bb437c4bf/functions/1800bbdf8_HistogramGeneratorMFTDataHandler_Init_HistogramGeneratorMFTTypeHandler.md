# HistogramGeneratorMFTDataHandler::Init(HistogramGeneratorMFTTypeHandler *)

- ea: `0x1800bbdf8`
- end: `0x1800bbf14`
- name: `?Init@HistogramGeneratorMFTDataHandler@@QEAAJPEAVHistogramGeneratorMFTTypeHandler@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(HistogramGeneratorMFTDataHandler *__hidden this, struct HistogramGeneratorMFTTypeHandler *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800bc058`

## callees

- `0x18000a09c`
- `0x18001f5e0`
- `0x180048f0c`
- `0x18004bdd0`
- `0x1800bbdf8`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x1800bbe28`
- `MFPlat!MFCreateAttributes` at `0x1800bbe42`
- `MFPlat!MFCreateAttributes` at `0x1800bbe28`
- `MFPlat!MFCreateAttributes` at `0x1800bbe42`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall HistogramGeneratorMFTDataHandler::Init(
        HistogramGeneratorMFTDataHandler *this,
        struct HistogramGeneratorMFTTypeHandler *a2)
{
  IMFAttributes **v3; // rbx
  __int64 (__fastcall **v5)(); // [rsp+20h] [rbp-40h] BYREF
  HistogramGeneratorMFTDataHandler *v6; // [rsp+28h] [rbp-38h]
  __int64 (__fastcall ***v7)(); // [rsp+58h] [rbp-8h]

  *((_QWORD *)this + 1) = a2;
  v3 = (IMFAttributes **)((char *)this + 248);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 248);
  if ( MFCreateAttributes(v3, 1u) >= 0 )
  {
    if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, __int64))(*v3)->lpVtbl->SetUINT32)(*v3, MF_SA_D3D11_AWARE, 1) >= 0 )
    {
      v5 = off_1800D5A48;
      v6 = this;
      v7 = &v5;
      std::function<void (void)>::operator=((char *)this + 112, &v5);
      std::_Func_class<void,>::_Tidy(&v5);
      v5 = off_1800D59E0;
      v6 = this;
      v7 = &v5;
      std::function<long (void)>::operator=((char *)this + 176, &v5);
      std::_Func_class<void,>::_Tidy(&v5);
      return 0;
    }
    else
    {
      return ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))(*v3)->lpVtbl->SetUINT32)(
               *v3,
               MF_SA_D3D11_AWARE,
               1);
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v3);
    return MFCreateAttributes(v3, 1u);
  }
}

```

## disassembly

```asm
0x1800bbdf8  mov     [rsp-8+arg_8], rbx
0x1800bbdfd  mov     [rsp-8+arg_10], rdi
0x1800bbe02  push    rbp
0x1800bbe03  mov     rbp, rsp
0x1800bbe06  sub     rsp, 60h
0x1800bbe0a  mov     rdi, rcx
0x1800bbe0d  mov     [rcx+8], rdx
0x1800bbe11  lea     rbx, [rcx+0F8h]
0x1800bbe18  mov     rcx, rbx
0x1800bbe1b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bbe20  mov     edx, 1; cInitialSize
0x1800bbe25  mov     rcx, rbx; ppMFAttributes
0x1800bbe28  call    cs:__imp_MFCreateAttributes
0x1800bbe2e  test    eax, eax
0x1800bbe30  jns     short loc_1800BBE4D
0x1800bbe32  mov     rcx, rbx
0x1800bbe35  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bbe3a  mov     edx, 1; cInitialSize
0x1800bbe3f  mov     rcx, rbx; ppMFAttributes
0x1800bbe42  call    cs:__imp_MFCreateAttributes
0x1800bbe48  jmp     loc_1800BBF02
0x1800bbe4d  mov     rcx, [rbx]
0x1800bbe50  mov     rax, [rcx]
0x1800bbe53  mov     r8d, 1
0x1800bbe59  lea     rdx, MF_SA_D3D11_AWARE
0x1800bbe60  mov     rax, [rax+0A8h]
0x1800bbe67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbe6c  test    eax, eax
0x1800bbe6e  jns     short loc_1800BBE91
0x1800bbe70  mov     rcx, [rbx]
0x1800bbe73  mov     rax, [rcx]
0x1800bbe76  mov     r8d, 1
0x1800bbe7c  lea     rdx, MF_SA_D3D11_AWARE
0x1800bbe83  mov     rax, [rax+0A8h]
0x1800bbe8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbe8f  jmp     short loc_1800BBF02
0x1800bbe91  lea     rax, off_1800D5A48
0x1800bbe98  mov     [rbp+var_40], rax
0x1800bbe9c  mov     [rbp+var_38], rdi
0x1800bbea0  lea     rax, [rbp+var_40]
0x1800bbea4  mov     [rbp+var_8], rax
0x1800bbea8  lea     rax, [rbp+var_40]
0x1800bbeac  mov     [rbp+arg_0], rax
0x1800bbeb0  lea     rcx, [rdi+70h]
0x1800bbeb4  lea     rdx, [rbp+var_40]
0x1800bbeb8  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> const &)
0x1800bbebd  nop
0x1800bbebe  lea     rcx, [rbp+var_40]
0x1800bbec2  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x1800bbec7  lea     rax, off_1800D59E0
0x1800bbece  mov     [rbp+var_40], rax
0x1800bbed2  mov     [rbp+var_38], rdi
0x1800bbed6  lea     rax, [rbp+var_40]
0x1800bbeda  mov     [rbp+var_8], rax
0x1800bbede  lea     rax, [rbp+var_40]
0x1800bbee2  mov     [rbp+arg_0], rax
0x1800bbee6  lea     rcx, [rdi+0B0h]
0x1800bbeed  lea     rdx, [rbp+var_40]
0x1800bbef1  call    ??4?$function@$$A6AJXZ@std@@QEAAAEAV01@AEBV01@@Z; std::function<long (void)>::operator=(std::function<long (void)> const &)
0x1800bbef6  nop
0x1800bbef7  lea     rcx, [rbp+var_40]
0x1800bbefb  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x1800bbf00  xor     eax, eax
0x1800bbf02  lea     r11, [rsp+60h+var_s0]
0x1800bbf07  mov     rbx, [r11+18h]
0x1800bbf0b  mov     rdi, [r11+20h]
0x1800bbf0f  mov     rsp, r11
0x1800bbf12  pop     rbp
0x1800bbf13  retn
```
