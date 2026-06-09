# std::vector<container::RegistryProvider::_VR_NSN_INFO,std::allocator<container::RegistryProvider::_VR_NSN_INFO>>::_Emplace_reallocate<container::RegistryProvider::_VR_NSN_INFO const &>(container::RegistryProvider::_VR_NSN_INFO * const,container::RegistryProvider::_VR_NSN_INFO const &)

- ea: `0x18000cac4`
- end: `0x18000cd47`
- name: `??$_Emplace_reallocate@AEBU_VR_NSN_INFO@RegistryProvider@container@@@?$vector@U_VR_NSN_INFO@RegistryProvider@container@@V?$allocator@U_VR_NSN_INFO@RegistryProvider@container@@@std@@@std@@AEAAPEAU_VR_NSN_INFO@RegistryProvider@container@@QEAU234@AEBU234@@Z`
- size: `643`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x18000d710`

## callees

- `0x180002af4`
- `0x180002ee4`
- `0x180004c40`
- `0x1800051b0`
- `0x18000be08`
- `0x18000cac4`
- `0x18000ce4c`
- `0x18000d5a8`
- `0x1800120b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char *__fastcall std::vector<container::RegistryProvider::_VR_NSN_INFO>::_Emplace_reallocate<container::RegistryProvider::_VR_NSN_INFO const &>(
        _QWORD *a1,
        __int64 a2,
        _DWORD *a3)
{
  void *v5; // rbx
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // r12
  unsigned __int64 v10; // r15
  unsigned __int64 v11; // r14
  _QWORD *v12; // rdi
  void *v13; // rax
  __int64 v14; // r13
  _DWORD *v15; // rbx
  __int64 v16; // rdx
  _DWORD *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rbp
  __int64 v21; // rcx
  void *v22; // rax
  _QWORD *v24; // [rsp+20h] [rbp-68h] BYREF
  _QWORD *v25; // [rsp+28h] [rbp-60h]
  unsigned __int64 v26; // [rsp+30h] [rbp-58h]
  _DWORD *v27; // [rsp+38h] [rbp-50h]
  _DWORD *v28; // [rsp+40h] [rbp-48h]

  v5 = (void *)*a1;
  v6 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a1[1] - *a1) >> 4);
  if ( v6 == 0x333333333333333LL )
    std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength();
  v7 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a1[2] - (_QWORD)v5) >> 4);
  v8 = v7 >> 1;
  if ( v7 > 0x333333333333333LL - (v7 >> 1) )
    goto LABEL_27;
  v9 = v6 + 1;
  v10 = v6 + 1;
  if ( v7 + v8 >= v6 + 1 )
    v10 = v7 + v8;
  if ( v10 > 0x333333333333333LL )
    goto LABEL_27;
  v11 = 80 * v10;
  if ( !(80 * v10) )
  {
    v12 = 0;
    goto LABEL_14;
  }
  if ( v11 < 0x1000 )
  {
    v12 = operator new(80 * v10);
    goto LABEL_14;
  }
  if ( v11 + 39 < v11 )
LABEL_27:
    __scrt_throw_std_bad_array_new_length();
  v13 = operator new(v11 + 39);
  if ( !v13 )
    __fastfail(5u);
  v12 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v12 - 1) = v13;
LABEL_14:
  v14 = (a2 - (__int64)v5) / 80;
  v15 = &v12[10 * v14];
  v24 = a1;
  v25 = v12;
  v26 = v10;
  v27 = v15 + 20;
  v28 = v15 + 20;
  std::wstring::wstring(v15, a3);
  std::wstring::wstring(v15 + 8, a3 + 8);
  v15[16] = a3[16];
  v15[17] = a3[17];
  v15[18] = a3[18];
  v27 = v15;
  v16 = a1[1];
  v17 = v12;
  v18 = *a1;
  if ( a2 != v16 )
  {
    std::_Uninitialized_move<container::RegistryProvider::_VR_NSN_INFO *>(v18, a2, v12);
    v27 = v12;
    v17 = v15 + 20;
    v16 = a1[1];
    v18 = a2;
  }
  std::_Uninitialized_move<container::RegistryProvider::_VR_NSN_INFO *>(v18, v16, v17);
  v25 = 0;
  v19 = *a1;
  if ( *a1 )
  {
    v20 = a1[1];
    while ( v19 != v20 )
    {
      std::wstring::~wstring(v19 + 32);
      std::wstring::~wstring(v19);
      v19 += 80;
    }
    v21 = *a1;
    if ( (unsigned __int64)(16 * ((__int64)(a1[2] - *a1) >> 4)) < 0x1000 )
    {
      v22 = (void *)*a1;
    }
    else
    {
      v22 = *(void **)(v21 - 8);
      if ( (unsigned __int64)(v21 - (_QWORD)v22 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v22);
  }
  *a1 = v12;
  a1[1] = &v12[10 * v9];
  a1[2] = &v12[v11 / 8];
  std::vector<container::RegistryProvider::_VR_NSN_INFO>::_Reallocation_guard::~_Reallocation_guard(&v24);
  return (char *)&v12[10 * v14];
}

```

## disassembly

```asm
0x18000cac4  mov     [rsp+arg_8], rbx
0x18000cac9  mov     [rsp+arg_10], r8
0x18000cace  push    rbp
0x18000cacf  push    rsi
0x18000cad0  push    rdi
0x18000cad1  push    r12
0x18000cad3  push    r13
0x18000cad5  push    r14
0x18000cad7  push    r15
0x18000cad9  sub     rsp, 50h
0x18000cadd  mov     rbp, rdx
0x18000cae0  mov     rsi, rcx
0x18000cae3  mov     rbx, [rcx]
0x18000cae6  mov     r9, [rcx+8]
0x18000caea  sub     r9, rbx
0x18000caed  sar     r9, 4
0x18000caf1  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000cafb  imul    r9, rax
0x18000caff  mov     r8, 333333333333333h
0x18000cb09  cmp     r9, r8
0x18000cb0c  jz      loc_18000CD3B
0x18000cb12  mov     rcx, [rcx+10h]
0x18000cb16  sub     rcx, rbx
0x18000cb19  sar     rcx, 4
0x18000cb1d  imul    rcx, rax
0x18000cb21  mov     rdx, rcx
0x18000cb24  shr     rdx, 1
0x18000cb27  mov     rax, r8
0x18000cb2a  sub     rax, rdx
0x18000cb2d  cmp     rcx, rax
0x18000cb30  ja      loc_18000CD41
0x18000cb36  lea     r12, [r9+1]
0x18000cb3a  lea     rax, [rcx+rdx]
0x18000cb3e  mov     r15, r12
0x18000cb41  cmp     rax, r12
0x18000cb44  cmovnb  r15, rax
0x18000cb48  cmp     r15, r8
0x18000cb4b  ja      loc_18000CD41
0x18000cb51  lea     r14, [r15+r15*4]
0x18000cb55  shl     r14, 4
0x18000cb59  test    r14, r14
0x18000cb5c  jnz     short loc_18000CB62
0x18000cb5e  xor     edi, edi
0x18000cb60  jmp     short loc_18000CBA0
0x18000cb62  cmp     r14, 1000h
0x18000cb69  jb      short loc_18000CB95
0x18000cb6b  lea     rcx, [r14+27h]; Size
0x18000cb6f  cmp     rcx, r14
0x18000cb72  jbe     loc_18000CD41
0x18000cb78  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cb7d  test    rax, rax
0x18000cb80  jnz     short loc_18000CB87
0x18000cb82  lea     ecx, [rax+5]
0x18000cb85  int     29h; Win8: RtlFailFast(ecx)
0x18000cb87  lea     rdi, [rax+27h]
0x18000cb8b  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18000cb8f  mov     [rdi-8], rax
0x18000cb93  jmp     short loc_18000CBA0
0x18000cb95  mov     rcx, r14; Size
0x18000cb98  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cb9d  mov     rdi, rax
0x18000cba0  mov     rcx, rbp
0x18000cba3  sub     rcx, rbx
0x18000cba6  mov     rax, 6666666666666667h
0x18000cbb0  imul    rcx
0x18000cbb3  mov     r13, rdx
0x18000cbb6  sar     r13, 5
0x18000cbba  mov     rcx, r13
0x18000cbbd  shr     rcx, 3Fh
0x18000cbc1  add     r13, rcx
0x18000cbc4  lea     rbx, ds:0[r13*4]
0x18000cbcc  add     rbx, r13
0x18000cbcf  shl     rbx, 4
0x18000cbd3  add     rbx, rdi
0x18000cbd6  lea     rax, [rbx+50h]
0x18000cbda  mov     [rsp+88h+var_68], rsi
0x18000cbdf  mov     [rsp+88h+var_60], rdi
0x18000cbe4  mov     [rsp+88h+var_58], r15
0x18000cbe9  mov     [rsp+88h+var_50], rax
0x18000cbee  mov     [rsp+88h+var_48], rax
0x18000cbf3  mov     [rsp+88h+arg_0], rbx
0x18000cbfb  mov     r15, [rsp+88h+arg_10]
0x18000cc03  mov     rdx, r15
0x18000cc06  mov     rcx, rbx
0x18000cc09  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000cc0e  nop
0x18000cc0f  lea     rdx, [r15+20h]
0x18000cc13  lea     rcx, [rbx+20h]
0x18000cc17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000cc1c  mov     eax, [r15+40h]
0x18000cc20  mov     [rbx+40h], eax
0x18000cc23  mov     eax, [r15+44h]
0x18000cc27  mov     [rbx+44h], eax
0x18000cc2a  mov     eax, [r15+48h]
0x18000cc2e  mov     [rbx+48h], eax
0x18000cc31  mov     [rsp+88h+var_50], rbx
0x18000cc36  mov     rdx, [rsi+8]
0x18000cc3a  mov     r8, rdi
0x18000cc3d  mov     rcx, [rsi]
0x18000cc40  cmp     rbp, rdx
0x18000cc43  jz      short loc_18000CC5D
0x18000cc45  mov     rdx, rbp
0x18000cc48  call    ??$_Uninitialized_move@PEAU_VR_NSN_INFO@RegistryProvider@container@@V?$allocator@U_VR_NSN_INFO@RegistryProvider@container@@@std@@@std@@YAPEAU_VR_NSN_INFO@RegistryProvider@container@@QEAU123@0PEAU123@AEAV?$allocator@U_VR_NSN_INFO@RegistryProvider@container@@@0@@Z; std::_Uninitialized_move<container::RegistryProvider::_VR_NSN_INFO *>(container::RegistryProvider::_VR_NSN_INFO * const,container::RegistryProvider::_VR_NSN_INFO * const,container::RegistryProvider::_VR_NSN_INFO *,std::allocator<container::RegistryProvider::_VR_NSN_INFO> &)
0x18000cc4d  mov     [rsp+88h+var_50], rdi
0x18000cc52  lea     r8, [rbx+50h]
0x18000cc56  mov     rdx, [rsi+8]
0x18000cc5a  mov     rcx, rbp
0x18000cc5d  call    ??$_Uninitialized_move@PEAU_VR_NSN_INFO@RegistryProvider@container@@V?$allocator@U_VR_NSN_INFO@RegistryProvider@container@@@std@@@std@@YAPEAU_VR_NSN_INFO@RegistryProvider@container@@QEAU123@0PEAU123@AEAV?$allocator@U_VR_NSN_INFO@RegistryProvider@container@@@0@@Z; std::_Uninitialized_move<container::RegistryProvider::_VR_NSN_INFO *>(container::RegistryProvider::_VR_NSN_INFO * const,container::RegistryProvider::_VR_NSN_INFO * const,container::RegistryProvider::_VR_NSN_INFO *,std::allocator<container::RegistryProvider::_VR_NSN_INFO> &)
0x18000cc62  mov     [rsp+88h+var_60], 0
0x18000cc6b  mov     rbx, [rsi]
0x18000cc6e  test    rbx, rbx
0x18000cc71  jz      short loc_18000CCE9
0x18000cc73  mov     rbp, [rsi+8]
0x18000cc77  jmp     short loc_18000CC8E
0x18000cc79  lea     rcx, [rbx+20h]
0x18000cc7d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc82  mov     rcx, rbx
0x18000cc85  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc8a  add     rbx, 50h ; 'P'
0x18000cc8e  cmp     rbx, rbp
0x18000cc91  jnz     short loc_18000CC79
0x18000cc93  mov     rcx, [rsi]
0x18000cc96  mov     rax, [rsi+10h]
0x18000cc9a  sub     rax, rcx
0x18000cc9d  sar     rax, 4
0x18000cca1  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18000ccab  imul    rax, rdx
0x18000ccaf  lea     rdx, [rax+rax*4]
0x18000ccb3  shl     rdx, 4; unsigned __int64
0x18000ccb7  cmp     rdx, 1000h
0x18000ccbe  jb      short loc_18000CCDE
0x18000ccc0  mov     rax, [rcx-8]
0x18000ccc4  sub     rcx, rax
0x18000ccc7  sub     rcx, 8
0x18000cccb  cmp     rcx, 1Fh
0x18000cccf  ja      short loc_18000CCD7
0x18000ccd1  add     rdx, 27h ; '''
0x18000ccd5  jmp     short loc_18000CCE1
0x18000ccd7  mov     ecx, 5
0x18000ccdc  int     29h; Win8: RtlFailFast(ecx)
0x18000ccde  mov     rax, rcx
0x18000cce1  mov     rcx, rax; void *
0x18000cce4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cce9  mov     [rsi], rdi
0x18000ccec  lea     rax, [r12+r12*4]
0x18000ccf0  shl     rax, 4
0x18000ccf4  add     rax, rdi
0x18000ccf7  mov     [rsi+8], rax
0x18000ccfb  lea     rax, [r14+rdi]
0x18000ccff  mov     [rsi+10h], rax
0x18000cd03  lea     rbx, ds:0[r13*4]
0x18000cd0b  add     rbx, r13
0x18000cd0e  shl     rbx, 4
0x18000cd12  add     rbx, rdi
0x18000cd15  lea     rcx, [rsp+88h+var_68]
0x18000cd1a  call    ??1_Reallocation_guard@?$vector@U_VR_NSN_INFO@RegistryProvider@container@@V?$allocator@U_VR_NSN_INFO@RegistryProvider@container@@@std@@@std@@QEAA@XZ; std::vector<container::RegistryProvider::_VR_NSN_INFO>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000cd1f  mov     rax, rbx
0x18000cd22  mov     rbx, [rsp+88h+arg_8]
0x18000cd2a  add     rsp, 50h
0x18000cd2e  pop     r15
0x18000cd30  pop     r14
0x18000cd32  pop     r13
0x18000cd34  pop     r12
0x18000cd36  pop     rdi
0x18000cd37  pop     rsi
0x18000cd38  pop     rbp
0x18000cd39  retn
0x18000cd3b  call    ?_Xlength@?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@CAXXZ; std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength(void)
0x18000cd41  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
