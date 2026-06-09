# CWwanHelper::GetSignalStrength(std::list<tagSIGNALSTRENGTHDATA *,std::allocator<tagSIGNALSTRENGTHDATA *>> *)

- ea: `0x180017dc0`
- end: `0x180018105`
- name: `?GetSignalStrength@CWwanHelper@@QEAAJPEAV?$list@PEAUtagSIGNALSTRENGTHDATA@@V?$allocator@PEAUtagSIGNALSTRENGTHDATA@@@std@@@std@@@Z`
- size: `837`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180008b7c`
- `0x18000a010`
- `0x18000f550`
- `0x18000f9ec`

## callees

- `0x180002270`
- `0x18000400c`
- `0x1800075a8`
- `0x180007ffc`
- `0x180010f44`
- `0x180014274`
- `0x180017dc0`
- `0x180018708`
- `0x18001e500`
- `0x180023010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001801d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001801d`

## string_xrefs

- `0x180017e94`: `net\ux\netcenter\dll\wwanhelper.cpp`
- `0x180017f8a`: `net\ux\netcenter\dll\wwanhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWwanHelper::GetSignalStrength(__int64 a1, __int64 *a2)
{
  __int64 *v3; // r13
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // esi
  PVOID *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int i; // r12d
  __int64 v14; // rdi
  int (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdx
  unsigned __int64 v18; // rdx
  _DWORD *v19; // rax
  _DWORD *v20; // rbx
  __int64 v21; // rdi
  _QWORD *v22; // rax
  _QWORD *v23; // rcx
  int v25; // [rsp+20h] [rbp-98h] BYREF
  unsigned int v26; // [rsp+24h] [rbp-94h] BYREF
  __int64 v27; // [rsp+28h] [rbp-90h] BYREF
  __int64 v28; // [rsp+30h] [rbp-88h] BYREF
  unsigned int v29; // [rsp+38h] [rbp-80h]
  __int64 *v30; // [rsp+40h] [rbp-78h]
  void *v31; // [rsp+48h] [rbp-70h]
  __int64 *v32; // [rsp+50h] [rbp-68h]
  __int64 *v33; // [rsp+60h] [rbp-58h] BYREF
  __int64 v34; // [rsp+68h] [rbp-50h]
  __int128 v35; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v30 = a2;
  v3 = a2;
  v32 = a2;
  ClearSignalStrengthDataList(a2);
  v28 = 0;
  v4 = *(_QWORD *)(a1 + 32);
  v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v4 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(&v28);
  v6 = v5(v4, 2, &v28);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v25 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 56LL))(v28, &v25);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          &WPP_a11cf809049534719b1b19f33c80d524_Traceguids,
          (unsigned int)v25);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      for ( i = 0; ; ++i )
      {
        v29 = i;
        if ( i >= v25 )
          break;
        v27 = 0;
        v35 = 0;
        v26 = 0;
        v14 = v28;
        v15 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v28 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(&v27);
        if ( v15(v14, i, &v27) >= 0 )
        {
          v16 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v27 + 64LL))(v27, &v35);
          v7 = v16;
          if ( v16 < 0 )
          {
            v17 = 194;
LABEL_17:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v17,
              (unsigned int)"net\\ux\\netcenter\\dll\\wwanhelper.cpp",
              (const char *)(unsigned int)v16,
              v25);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(&v27);
            goto LABEL_31;
          }
          v16 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v27 + 80LL))(v27, &v26);
          v7 = v16;
          if ( v16 < 0 )
          {
            v17 = 195;
            goto LABEL_17;
          }
          v19 = DirectUI::HAllocAndZero((DirectUI *)0x14, v18);
          v20 = v19;
          if ( v19 )
          {
            v7 = 0;
            v31 = v19;
            *(_OWORD *)v19 = v35;
            v19[4] = v26;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_a11cf809049534719b1b19f33c80d524_Traceguids, v26);
            try
            {
              if ( v3[1] == 0xAAAAAAAAAAAAAAALL )
                std::_Xlength_error("list too long");
              v21 = *v30;
              v33 = v3;
              v34 = 0;
              v22 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(24);
              v22[2] = v20;
              ++v3[1];
              v23 = *(_QWORD **)(v21 + 8);
              *v22 = v21;
              v22[1] = v23;
              v34 = 0;
              *(_QWORD *)(v21 + 8) = v22;
              *v23 = v22;
              std::_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>(&v33);
            }
            catch ( ... )
            {
              operator delete(v31, 0x14u);
              v7 = -2147024882;
              i = v29;
              v3 = v32;
              v30 = v32;
            }
          }
          else
          {
            v7 = -2147024882;
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(&v27);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
      {
        v9 = 14;
        v10 = v7;
        goto LABEL_30;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB7,
        (unsigned int)"net\\ux\\netcenter\\dll\\wwanhelper.cpp",
        (const char *)(unsigned int)v11,
        v25);
      v7 = v12;
    }
  }
  else
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 10;
      v10 = (unsigned int)v6;
LABEL_30:
      WPP_SF_d(v8[2], v9, &WPP_a11cf809049534719b1b19f33c80d524_Traceguids, v10);
    }
  }
LABEL_31:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(&v28);
  return v7;
}

```

## disassembly

```asm
0x180017dc0  mov     [rsp+arg_10], rbx
0x180017dc5  push    rsi
0x180017dc6  push    rdi
0x180017dc7  push    r12
0x180017dc9  push    r13
0x180017dcb  push    r15
0x180017dcd  sub     rsp, 90h
0x180017dd4  mov     rax, cs:__security_cookie
0x180017ddb  xor     rax, rsp
0x180017dde  mov     [rsp+0B8h+var_38], rax
0x180017de6  mov     [rsp+0B8h+var_78], rdx
0x180017deb  mov     rdi, rcx
0x180017dee  mov     r13, rdx
0x180017df1  mov     [rsp+0B8h+var_68], rdx
0x180017df6  mov     rcx, rdx
0x180017df9  call    ?ClearSignalStrengthDataList@@YAXPEAV?$list@PEAUtagSIGNALSTRENGTHDATA@@V?$allocator@PEAUtagSIGNALSTRENGTHDATA@@@std@@@std@@@Z; ClearSignalStrengthDataList(std::list<tagSIGNALSTRENGTHDATA *> *)
0x180017dfe  mov     [rsp+0B8h+var_88], 0
0x180017e07  mov     rdi, [rdi+20h]
0x180017e0b  mov     rax, [rdi]
0x180017e0e  mov     rbx, [rax+48h]
0x180017e12  lea     rcx, [rsp+0B8h+var_88]
0x180017e17  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIUXCategory@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(void)
0x180017e1c  lea     r8, [rsp+0B8h+var_88]
0x180017e21  mov     edx, 2
0x180017e26  mov     rcx, rdi
0x180017e29  mov     rax, rbx
0x180017e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e31  mov     esi, eax
0x180017e33  test    eax, eax
0x180017e35  jns     short loc_180017E65
0x180017e37  lea     r15, WPP_GLOBAL_Control
0x180017e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e45  cmp     rcx, r15
0x180017e48  jz      loc_1800180D1
0x180017e4e  test    byte ptr [rcx+1Ch], 1
0x180017e52  jz      loc_1800180D1
0x180017e58  mov     edx, 0Ah
0x180017e5d  mov     r9d, eax
0x180017e60  jmp     loc_1800180C0
0x180017e65  mov     [rsp+0B8h+var_98], 0; int
0x180017e6d  mov     rcx, [rsp+0B8h+var_88]
0x180017e72  mov     rax, [rcx]
0x180017e75  lea     rdx, [rsp+0B8h+var_98]
0x180017e7a  mov     rax, [rax+38h]
0x180017e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e83  mov     ebx, eax
0x180017e85  test    eax, eax
0x180017e87  jns     short loc_180017EAC
0x180017e89  mov     rcx, [rsp+0B8h]; this
0x180017e91  mov     r9d, eax; char *
0x180017e94  lea     r8, aNetUxNetcenter; "net\\ux\\netcenter\\dll\\wwanhelper.cpp"
0x180017e9b  mov     edx, 0B7h; void *
0x180017ea0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ea5  mov     esi, ebx
0x180017ea7  jmp     loc_1800180D1
0x180017eac  lea     r15, WPP_GLOBAL_Control
0x180017eb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180017eba  cmp     rcx, r15
0x180017ebd  jz      short loc_180017EE6
0x180017ebf  test    byte ptr [rcx+1Ch], 8
0x180017ec3  jz      short loc_180017EE6
0x180017ec5  mov     edx, 0Bh
0x180017eca  mov     r9d, [rsp+0B8h+var_98]
0x180017ecf  lea     r8, WPP_a11cf809049534719b1b19f33c80d524_Traceguids
0x180017ed6  mov     rcx, [rcx+10h]
0x180017eda  call    WPP_SF_d
0x180017edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ee6  xor     r12d, r12d
0x180017ee9  mov     [rsp+0B8h+var_80], r12d
0x180017eee  cmp     r12d, [rsp+0B8h+var_98]
0x180017ef3  jnb     loc_1800180AD
0x180017ef9  mov     [rsp+0B8h+var_90], 0
0x180017f02  xorps   xmm0, xmm0
0x180017f05  movups  [rsp+0B8h+var_48], xmm0
0x180017f0a  mov     [rsp+0B8h+var_94], 0
0x180017f12  mov     rdi, [rsp+0B8h+var_88]
0x180017f17  mov     rax, [rdi]
0x180017f1a  mov     rbx, [rax+30h]
0x180017f1e  lea     rcx, [rsp+0B8h+var_90]
0x180017f23  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIUXCategory@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(void)
0x180017f28  lea     r8, [rsp+0B8h+var_90]
0x180017f2d  mov     edx, r12d
0x180017f30  mov     rcx, rdi
0x180017f33  mov     rax, rbx
0x180017f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f3b  test    eax, eax
0x180017f3d  js      loc_180018094
0x180017f43  mov     rcx, [rsp+0B8h+var_90]
0x180017f48  mov     rax, [rcx]
0x180017f4b  lea     rdx, [rsp+0B8h+var_48]
0x180017f50  mov     rax, [rax+40h]
0x180017f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f59  mov     esi, eax
0x180017f5b  test    eax, eax
0x180017f5d  jns     short loc_180017F66
0x180017f5f  mov     edx, 0C2h
0x180017f64  jmp     short loc_180017F87
0x180017f66  mov     rcx, [rsp+0B8h+var_90]
0x180017f6b  mov     rax, [rcx]
0x180017f6e  lea     rdx, [rsp+0B8h+var_94]
0x180017f73  mov     rax, [rax+50h]
0x180017f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f7c  mov     esi, eax
0x180017f7e  test    eax, eax
0x180017f80  jns     short loc_180017FAE
0x180017f82  mov     edx, 0C3h; void *
0x180017f87  mov     r9d, eax; char *
0x180017f8a  lea     r8, aNetUxNetcenter; "net\\ux\\netcenter\\dll\\wwanhelper.cpp"
0x180017f91  mov     rcx, [rsp+0B8h]; this
0x180017f99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017f9e  nop
0x180017f9f  lea     rcx, [rsp+0B8h+var_90]
0x180017fa4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIUXCategory@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(void)
0x180017fa9  jmp     loc_1800180D1
0x180017fae  mov     ecx, 14h; this
0x180017fb3  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180017fb8  mov     rbx, rax
0x180017fbb  test    rax, rax
0x180017fbe  jz      loc_18001808F
0x180017fc4  xor     esi, esi
0x180017fc6  mov     [rsp+0B8h+var_70], rax
0x180017fcb  movups  xmm0, [rsp+0B8h+var_48]
0x180017fd0  movdqu  xmmword ptr [rax], xmm0
0x180017fd4  mov     ecx, [rsp+0B8h+var_94]
0x180017fd8  mov     [rax+10h], ecx
0x180017fdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180017fe2  cmp     rcx, r15
0x180017fe5  jz      short loc_180018006
0x180017fe7  test    byte ptr [rcx+1Ch], 4
0x180017feb  jz      short loc_180018006
0x180017fed  lea     edx, [rsi+0Dh]
0x180017ff0  mov     r9d, [rsp+0B8h+var_94]
0x180017ff5  lea     r8, WPP_a11cf809049534719b1b19f33c80d524_Traceguids
0x180017ffc  mov     rcx, [rcx+10h]
0x180018000  call    WPP_SF_d
0x180018005  nop
0x180018006  mov     rax, 0AAAAAAAAAAAAAAAh
0x180018010  cmp     [r13+8], rax
0x180018014  jnz     short loc_180018023
0x180018016  lea     rcx, aListTooLong; "list too long"
0x18001801d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180018023  mov     rax, [rsp+0B8h+var_78]
0x180018028  mov     rdi, [rax]
0x18001802b  mov     [rsp+0B8h+var_58], r13
0x180018030  mov     [rsp+0B8h+var_50], 0
0x180018039  mov     ecx, 18h
0x18001803e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180018043  mov     [rax+10h], rbx
0x180018047  inc     qword ptr [r13+8]
0x18001804b  mov     rcx, [rdi+8]
0x18001804f  mov     [rax], rdi
0x180018052  mov     [rax+8], rcx
0x180018056  mov     [rsp+0B8h+var_50], 0
0x18001805f  mov     [rdi+8], rax
0x180018063  mov     [rcx], rax
0x180018066  lea     rcx, [rsp+0B8h+var_58]
0x18001806b  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAUtagNSC_INSTANCE_DATA@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>(void)
0x180018070  nop
0x180018071  jmp     short loc_180018094
0x180018073  lea     r15, WPP_GLOBAL_Control
0x18001807a  mov     esi, dword ptr [rsp+0B8h+var_78]
0x18001807e  mov     r12d, [rsp+0B8h+var_80]
0x180018083  mov     r13, [rsp+0B8h+var_68]
0x180018088  mov     [rsp+0B8h+var_78], r13
0x18001808d  jmp     short loc_180018094
0x18001808f  mov     esi, 8007000Eh
0x180018094  lea     rcx, [rsp+0B8h+var_90]
0x180018099  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIUXCategory@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(void)
0x18001809e  inc     r12d
0x1800180a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180a8  jmp     loc_180017EE9
0x1800180ad  cmp     rcx, r15
0x1800180b0  jz      short loc_1800180D1
0x1800180b2  test    byte ptr [rcx+1Ch], 8
0x1800180b6  jz      short loc_1800180D1
0x1800180b8  mov     edx, 0Eh
0x1800180bd  mov     r9d, esi
0x1800180c0  lea     r8, WPP_a11cf809049534719b1b19f33c80d524_Traceguids
0x1800180c7  mov     rcx, [rcx+10h]
0x1800180cb  call    WPP_SF_d
0x1800180d0  nop
0x1800180d1  lea     rcx, [rsp+0B8h+var_88]
0x1800180d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIUXCategory@UX@Networking@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Networking::UX::IUXCategory *>>::InternalRelease(void)
0x1800180db  mov     eax, esi
0x1800180dd  mov     rcx, [rsp+0B8h+var_38]
0x1800180e5  xor     rcx, rsp; StackCookie
0x1800180e8  call    __security_check_cookie
0x1800180ed  mov     rbx, [rsp+0B8h+arg_10]
0x1800180f5  add     rsp, 90h
0x1800180fc  pop     r15
0x1800180fe  pop     r13
0x180018100  pop     r12
0x180018102  pop     rdi
0x180018103  pop     rsi
0x180018104  retn
```
