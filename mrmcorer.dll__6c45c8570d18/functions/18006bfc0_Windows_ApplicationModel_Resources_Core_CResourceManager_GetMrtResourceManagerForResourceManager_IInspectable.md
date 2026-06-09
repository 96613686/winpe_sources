# Windows::ApplicationModel::Resources::Core::CResourceManager::GetMrtResourceManagerForResourceManager(IInspectable * *)

- ea: `0x18006bfc0`
- end: `0x18006c1bf`
- name: `?GetMrtResourceManagerForResourceManager@CResourceManager@Core@Resources@ApplicationModel@Windows@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `511`
- prototype: `int(Windows::ApplicationModel::Resources::Core::CResourceManager *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000a0d0`
- `0x18002c8d0`
- `0x18006bfc0`
- `0x18006c1c8`
- `0x18006c46c`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006c023`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006c16a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006c023`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006c16a`

## string_xrefs

- `0x18006c031`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x18006c08a`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x18006c0f3`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x18006c12c`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x18006c178`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x18006c193`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceManager::GetMrtResourceManagerForResourceManager(
        struct IInspectable *this,
        struct IInspectable **a2)
{
  char MrtSharedObjectState; // di
  CMrtResourceManager *v5; // rbx
  unsigned int v6; // edi
  int v8; // eax
  int v9; // eax
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  CMrtResourceManager *v14; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  MrtSharedObjectState = Windows::ApplicationModel::Resources::Core::CResourceManager::GetMrtSharedObjectState(&this[-7]);
  if ( (MrtSharedObjectState & 8) == 0 )
  {
    v11 = -2147009751;
    RoOriginateError(2147957545LL);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
      (const char *)0x80073B29LL,
      v12);
    return v11;
  }
  Microsoft::WRL::Details::Make<CMrtResourceManager,>(&v14);
  v5 = v14;
  if ( !v14 )
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x141,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
      (const char *)0x8007000ELL,
      v12);
    return v11;
  }
  if ( (MrtSharedObjectState & 1) != 0 )
  {
    v9 = CMrtResourceManager::InitializeForSystemProfile(v14, this - 7, this[4].lpVtbl);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
        (const char *)(unsigned int)v9,
        v12);
      if ( v5 )
        (*(void (__fastcall **)(CMrtResourceManager *))(*(_QWORD *)v5 + 16LL))(v5);
      return v6;
    }
  }
  else
  {
    if ( (MrtSharedObjectState & 2) == 0 )
    {
      v6 = -2147009752;
      RoOriginateError(2147957544LL);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x150,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
        (const char *)0x80073B28LL,
        v12);
      if ( v5 )
        (*(void (__fastcall **)(CMrtResourceManager *))(*(_QWORD *)v5 + 16LL))(v5);
      return v6;
    }
    v8 = (*(__int64 (__fastcall **)(CMrtResourceManager *))(*(_QWORD *)v14 + 32LL))(v14);
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x149,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
        (const char *)(unsigned int)v8,
        v12);
      if ( v5 )
        (*(void (__fastcall **)(CMrtResourceManager *))(*(_QWORD *)v5 + 16LL))(v5);
      return v6;
    }
  }
  v10 = (**(__int64 (__fastcall ***)(CMrtResourceManager *, GUID *, struct IInspectable **))v5)(
          v5,
          &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
          a2);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
      (const char *)(unsigned int)v10,
      v12);
    if ( v5 )
      (*(void (__fastcall **)(CMrtResourceManager *))(*(_QWORD *)v5 + 16LL))(v5);
    return v6;
  }
  if ( v5 )
    (*(void (__fastcall **)(CMrtResourceManager *))(*(_QWORD *)v5 + 16LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x18006bfc0  mov     [rsp+arg_8], rbx
0x18006bfc5  mov     [rsp+arg_10], rbp
0x18006bfca  push    rsi
0x18006bfcb  push    rdi
0x18006bfcc  push    r14; int
0x18006bfce  sub     rsp, 20h
0x18006bfd2  mov     r14, rdx
0x18006bfd5  mov     rsi, rcx
0x18006bfd8  mov     qword ptr [rdx], 0
0x18006bfdf  add     rcx, 0FFFFFFFFFFFFFFC8h
0x18006bfe3  call    ?GetMrtSharedObjectState@CResourceManager@Core@Resources@ApplicationModel@Windows@@QEAA?AW4_MrtSharedObjectState@3Microsoft@@XZ; Windows::ApplicationModel::Resources::Core::CResourceManager::GetMrtSharedObjectState(void)
0x18006bfe8  mov     edi, eax
0x18006bfea  test    al, 8
0x18006bfec  jz      loc_18006C161
0x18006bff2  lea     rcx, [rsp+38h+arg_0]
0x18006bff7  call    ??$Make@VCMrtResourceManager@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCMrtResourceManager@@@12@XZ; Microsoft::WRL::Details::Make<CMrtResourceManager,>(void)
0x18006bffc  mov     rbx, [rsp+38h+arg_0]
0x18006c001  test    rbx, rbx
0x18006c004  jz      loc_18006C11F
0x18006c00a  test    dil, 1
0x18006c00e  jnz     loc_18006C0B3
0x18006c014  test    dil, 2
0x18006c018  jnz     short loc_18006C06D
0x18006c01a  xor     edx, edx
0x18006c01c  mov     edi, 80073B28h
0x18006c021  mov     ecx, edi
0x18006c023  call    cs:__imp_RoOriginateError
0x18006c029  mov     rcx, [rsp+38h]; this
0x18006c02e  mov     r9d, edi; char *
0x18006c031  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18006c038  mov     edx, 150h; void *
0x18006c03d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c042  nop
0x18006c043  test    rbx, rbx
0x18006c046  jz      short loc_18006C058
0x18006c048  mov     rdx, [rbx]
0x18006c04b  mov     rcx, rbx
0x18006c04e  mov     rax, [rdx+10h]
0x18006c052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c057  nop
0x18006c058  mov     eax, edi
0x18006c05a  mov     rbx, [rsp+38h+arg_8]
0x18006c05f  mov     rbp, [rsp+38h+arg_10]
0x18006c064  add     rsp, 20h
0x18006c068  pop     r14
0x18006c06a  pop     rdi
0x18006c06b  pop     rsi
0x18006c06c  retn
0x18006c06d  mov     rax, [rbx]
0x18006c070  mov     rcx, rbx
0x18006c073  mov     rax, [rax+20h]
0x18006c077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c07c  mov     edi, eax
0x18006c07e  test    eax, eax
0x18006c080  jns     short loc_18006C0CD
0x18006c082  mov     rcx, [rsp+38h]; this
0x18006c087  mov     r9d, eax; char *
0x18006c08a  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18006c091  mov     edx, 149h; void *
0x18006c096  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c09b  nop
0x18006c09c  test    rbx, rbx
0x18006c09f  jz      short loc_18006C0B1
0x18006c0a1  mov     rax, [rbx]
0x18006c0a4  mov     rcx, rbx
0x18006c0a7  mov     rax, [rax+10h]
0x18006c0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c0b0  nop
0x18006c0b1  jmp     short loc_18006C058
0x18006c0b3  mov     r8, [rsi+20h]; void *
0x18006c0b7  lea     rdx, [rsi-38h]; struct IInspectable *
0x18006c0bb  mov     rcx, rbx; this
0x18006c0be  call    ?InitializeForSystemProfile@CMrtResourceManager@@QEAAJPEAUIInspectable@@PEAX@Z; CMrtResourceManager::InitializeForSystemProfile(IInspectable *,void *)
0x18006c0c3  mov     edi, eax
0x18006c0c5  test    eax, eax
0x18006c0c7  js      loc_18006C18B
0x18006c0cd  mov     rax, [rbx]
0x18006c0d0  mov     r8, r14
0x18006c0d3  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18006c0da  mov     rcx, rbx
0x18006c0dd  mov     rax, [rax]
0x18006c0e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c0e5  mov     edi, eax
0x18006c0e7  test    eax, eax
0x18006c0e9  jns     short loc_18006C145
0x18006c0eb  mov     rcx, [rsp+38h]; this
0x18006c0f0  mov     r9d, eax; char *
0x18006c0f3  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18006c0fa  mov     edx, 153h; void *
0x18006c0ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c104  nop
0x18006c105  test    rbx, rbx
0x18006c108  jz      short loc_18006C11A
0x18006c10a  mov     rax, [rbx]
0x18006c10d  mov     rcx, rbx
0x18006c110  mov     rax, [rax+10h]
0x18006c114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c119  nop
0x18006c11a  jmp     loc_18006C058
0x18006c11f  mov     rcx, [rsp+38h]; this
0x18006c124  mov     ebx, 8007000Eh
0x18006c129  mov     r9d, ebx; char *
0x18006c12c  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18006c133  mov     edx, 141h; void *
0x18006c138  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c13d  nop
0x18006c13e  mov     eax, ebx
0x18006c140  jmp     loc_18006C05A
0x18006c145  test    rbx, rbx
0x18006c148  jz      short loc_18006C15A
0x18006c14a  mov     rax, [rbx]
0x18006c14d  mov     rcx, rbx
0x18006c150  mov     rax, [rax+10h]
0x18006c154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c159  nop
0x18006c15a  xor     eax, eax
0x18006c15c  jmp     loc_18006C05A
0x18006c161  xor     edx, edx
0x18006c163  mov     ebx, 80073B29h
0x18006c168  mov     ecx, ebx
0x18006c16a  call    cs:__imp_RoOriginateError
0x18006c170  mov     rcx, [rsp+38h]; this
0x18006c175  mov     r9d, ebx; char *
0x18006c178  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18006c17f  mov     edx, 159h; void *
0x18006c184  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c189  jmp     short loc_18006C13E
0x18006c18b  mov     rcx, [rsp+38h]; this
0x18006c190  mov     r9d, edi; char *
0x18006c193  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18006c19a  mov     edx, 145h; void *
0x18006c19f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c1a4  nop
0x18006c1a5  test    rbx, rbx
0x18006c1a8  jz      short loc_18006C1BA
0x18006c1aa  mov     rax, [rbx]
0x18006c1ad  mov     rcx, rbx
0x18006c1b0  mov     rax, [rax+10h]
0x18006c1b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c1b9  nop
0x18006c1ba  jmp     loc_18006C058
```
