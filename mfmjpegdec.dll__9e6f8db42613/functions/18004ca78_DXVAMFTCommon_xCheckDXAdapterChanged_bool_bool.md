# DXVAMFTCommon::xCheckDXAdapterChanged(bool *,bool *)

- ea: `0x18004ca78`
- end: `0x18004ccae`
- name: `?xCheckDXAdapterChanged@DXVAMFTCommon@@AEAAJPEA_N0@Z`
- size: `566`
- prototype: `__int64 __fastcall(DXVAMFTCommon *__hidden this, bool *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004ccc0`

## callees

- `0x180024220`
- `0x180024bf4`
- `0x18004a11c`
- `0x18004ca78`
- `0x18004d8ac`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DXVAMFTCommon::xCheckDXAdapterChanged(DXVAMFTCommon *this, bool *a2, bool *a3)
{
  __int64 v6; // rcx
  unsigned int v7; // r14d
  __int64 v8; // rcx
  bool v9; // al
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, _QWORD, GUID *, __int64 *); // rbx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, GUID *, __int64 *); // rbx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 *); // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // eax
  int v19; // ecx
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[296]; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+188h] [rbp+88h]
  int v26; // [rsp+18Ch] [rbp+8Ch]

  *a2 = 0;
  *a3 = 0;
  v23[0] = 0;
  v6 = *((_QWORD *)this + 50);
  if ( v6 && *((_QWORD *)this + 52) )
  {
    v7 = 0;
    v9 = 1;
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v6 + 64LL))(v6) )
    {
      v8 = *((_QWORD *)this + 1);
      if ( !v8
        || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8)
        && !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) )
      {
        v9 = 0;
      }
    }
    *a2 = v9;
    v10 = *((_QWORD *)this + 50);
    v11 = *(int (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v10 + 32LL);
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(v23);
    if ( v11(v10, 0, &IID_ID3D11Device, v23) >= 0 )
    {
      v22 = 0;
      v21 = 0;
      memset_0(v24, 0, 0x130u);
      v12 = v23[0];
      v13 = **(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v23[0];
      Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v22);
      v7 = v13(v12, &GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c, &v22);
      if ( !v7 )
      {
        v14 = v22;
        v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 56LL);
        Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v21);
        v7 = v15(v14, &v21);
        if ( !v7 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v21 + 64LL))(v21, v24);
          if ( !v7 )
          {
            v18 = v25;
            v19 = v26;
            if ( v26 != *((_DWORD *)this + 81) || v25 != *((_DWORD *)this + 80) )
            {
              *a3 = 1;
              if ( g_wppLevels >= 4u )
                WPP_SF_DDDDq(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v16,
                  v17,
                  *((unsigned int *)this + 81),
                  *((_DWORD *)this + 80),
                  v19,
                  v18,
                  this);
            }
          }
        }
      }
      Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v21);
      Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v22);
    }
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(v23);
    return v7;
  }
  else
  {
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(v23);
    return 0;
  }
}

```

## disassembly

```asm
0x18004ca78  mov     [rsp-8+arg_18], rbx
0x18004ca7d  push    rbp
0x18004ca7e  push    rsi
0x18004ca7f  push    rdi
0x18004ca80  push    r14
0x18004ca82  push    r15
0x18004ca84  lea     rbp, [rsp-0A0h]
0x18004ca8c  sub     rsp, 1A0h
0x18004ca93  mov     rax, cs:__security_cookie
0x18004ca9a  xor     rax, rsp
0x18004ca9d  mov     [rbp+0C0h+var_30], rax
0x18004caa4  mov     r15, r8
0x18004caa7  mov     rbx, rdx
0x18004caaa  mov     rsi, rcx
0x18004caad  mov     byte ptr [rdx], 0
0x18004cab0  mov     byte ptr [r8], 0
0x18004cab4  mov     [rsp+1C0h+var_170], 0
0x18004cabd  mov     rcx, [rcx+190h]
0x18004cac4  test    rcx, rcx
0x18004cac7  jz      loc_18004CC7C
0x18004cacd  mov     rdx, [rsi+1A0h]
0x18004cad4  test    rdx, rdx
0x18004cad7  jz      loc_18004CC7C
0x18004cadd  xor     r14d, r14d
0x18004cae0  mov     rax, [rcx]
0x18004cae3  mov     rax, [rax+40h]
0x18004cae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004caec  test    eax, eax
0x18004caee  jnz     short loc_18004CB21
0x18004caf0  mov     rcx, [rsi+8]
0x18004caf4  test    rcx, rcx
0x18004caf7  jz      short loc_18004CB1D
0x18004caf9  mov     rax, [rcx]
0x18004cafc  mov     rax, [rax+18h]
0x18004cb00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb05  test    eax, eax
0x18004cb07  jnz     short loc_18004CB21
0x18004cb09  mov     rcx, [rsi+8]
0x18004cb0d  mov     rax, [rcx]
0x18004cb10  mov     rax, [rax+10h]
0x18004cb14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb19  test    eax, eax
0x18004cb1b  jnz     short loc_18004CB21
0x18004cb1d  xor     al, al
0x18004cb1f  jmp     short loc_18004CB23
0x18004cb21  mov     al, 1
0x18004cb23  mov     [rbx], al
0x18004cb25  mov     rdi, [rsi+190h]
0x18004cb2c  mov     rax, [rdi]
0x18004cb2f  mov     rbx, [rax+20h]
0x18004cb33  lea     rcx, [rsp+1C0h+var_170]
0x18004cb38  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004cb3d  lea     r9, [rsp+1C0h+var_170]
0x18004cb42  lea     r8, IID_ID3D11Device
0x18004cb49  xor     edx, edx
0x18004cb4b  mov     rcx, rdi
0x18004cb4e  mov     rax, rbx
0x18004cb51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb56  test    eax, eax
0x18004cb58  js      loc_18004CC6D
0x18004cb5e  mov     [rsp+1C0h+var_178], r14
0x18004cb63  mov     [rsp+1C0h+var_180], 0
0x18004cb6c  xor     edx, edx; Val
0x18004cb6e  mov     r8d, 130h; Size
0x18004cb74  lea     rcx, [rsp+1C0h+var_160]; void *
0x18004cb79  call    memset_0
0x18004cb7e  mov     rdi, [rsp+1C0h+var_170]
0x18004cb83  mov     rax, [rdi]
0x18004cb86  mov     rbx, [rax]
0x18004cb89  lea     rcx, [rsp+1C0h+var_178]
0x18004cb8e  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004cb93  lea     r8, [rsp+1C0h+var_178]
0x18004cb98  lea     rdx, _GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c
0x18004cb9f  mov     rcx, rdi
0x18004cba2  mov     rax, rbx
0x18004cba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbaa  mov     r14d, eax
0x18004cbad  test    eax, eax
0x18004cbaf  jnz     loc_18004CC57
0x18004cbb5  mov     rdi, [rsp+1C0h+var_178]
0x18004cbba  mov     rax, [rdi]
0x18004cbbd  mov     rbx, [rax+38h]
0x18004cbc1  lea     rcx, [rsp+1C0h+var_180]
0x18004cbc6  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004cbcb  lea     rdx, [rsp+1C0h+var_180]
0x18004cbd0  mov     rcx, rdi
0x18004cbd3  mov     rax, rbx
0x18004cbd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbdb  mov     r14d, eax
0x18004cbde  test    eax, eax
0x18004cbe0  jnz     short loc_18004CC57
0x18004cbe2  mov     rcx, [rsp+1C0h+var_180]
0x18004cbe7  mov     rax, [rcx]
0x18004cbea  lea     rdx, [rsp+1C0h+var_160]
0x18004cbef  mov     rax, [rax+40h]
0x18004cbf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbf8  mov     r14d, eax
0x18004cbfb  test    eax, eax
0x18004cbfd  jnz     short loc_18004CC57
0x18004cbff  mov     eax, [rbp+0C0h+var_38]
0x18004cc05  mov     ecx, [rbp+0C0h+var_34]
0x18004cc0b  cmp     ecx, [rsi+144h]
0x18004cc11  jnz     short loc_18004CC1B
0x18004cc13  cmp     eax, [rsi+140h]
0x18004cc19  jz      short loc_18004CC57
0x18004cc1b  mov     byte ptr [r15], 1
0x18004cc1f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x18004cc26  jb      short loc_18004CC57
0x18004cc28  mov     [rsp+1C0h+var_188], rsi
0x18004cc2d  mov     [rsp+1C0h+var_190], eax
0x18004cc31  mov     [rsp+1C0h+var_198], ecx
0x18004cc35  mov     eax, [rsi+140h]
0x18004cc3b  mov     [rsp+1C0h+var_1A0], eax
0x18004cc3f  mov     r9d, [rsi+144h]
0x18004cc46  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cc4d  mov     rcx, [rcx+10h]
0x18004cc51  call    WPP_SF_DDDDq
0x18004cc56  nop
0x18004cc57  lea     rcx, [rsp+1C0h+var_180]
0x18004cc5c  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004cc61  nop
0x18004cc62  lea     rcx, [rsp+1C0h+var_178]
0x18004cc67  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004cc6c  nop
0x18004cc6d  lea     rcx, [rsp+1C0h+var_170]
0x18004cc72  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004cc77  mov     eax, r14d
0x18004cc7a  jmp     short loc_18004CC88
0x18004cc7c  lea     rcx, [rsp+1C0h+var_170]
0x18004cc81  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004cc86  xor     eax, eax
0x18004cc88  mov     rcx, [rbp+0C0h+var_30]
0x18004cc8f  xor     rcx, rsp; StackCookie
0x18004cc92  call    __security_check_cookie
0x18004cc97  mov     rbx, [rsp+1C0h+arg_18]
0x18004cc9f  add     rsp, 1A0h
0x18004cca6  pop     r15
0x18004cca8  pop     r14
0x18004ccaa  pop     rdi
0x18004ccab  pop     rsi
0x18004ccac  pop     rbp
0x18004ccad  retn
```
