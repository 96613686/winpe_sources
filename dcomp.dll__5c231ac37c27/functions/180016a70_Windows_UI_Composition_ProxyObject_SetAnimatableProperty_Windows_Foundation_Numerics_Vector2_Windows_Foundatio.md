# Windows::UI::Composition::ProxyObject::SetAnimatableProperty<Windows::Foundation::Numerics::Vector2>(Windows::Foundation::Numerics::Vector2 *,Windows::Foundation::Numerics::Vector2 const &,Windows::UI::Composition::AnimationHelper::AnimatedProperty const &)

- ea: `0x180016a70`
- end: `0x180016db2`
- name: `??$SetAnimatableProperty@UVector2@Numerics@Foundation@Windows@@@ProxyObject@Composition@UI@Windows@@IEAAJPEAUVector2@Numerics@Foundation@3@AEBU4563@AEBUAnimatedProperty@AnimationHelper@123@@Z`
- size: `834`
- prototype: ``
- caller_count: `37`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180056098`
- `0x18007ab14`
- `0x18007ac30`
- `0x18007ad60`
- `0x18007c350`
- `0x18007c484`
- `0x18007c6a0`
- `0x1800ad090`
- `0x1800b39a0`
- `0x1800b42a0`
- `0x1800b6750`
- `0x1800bcda0`
- `0x1800c1390`
- `0x1800c43c0`
- `0x1800c82e0`
- `0x1800c8b30`
- `0x1800cb3d0`
- `0x1800cd6f0`
- `0x1800cdfb0`
- `0x1800cf110`
- `0x1800d1408`
- `0x1800d3500`
- `0x180142784`
- `0x18014281c`
- `0x180151a60`
- `0x180153140`
- `0x180153350`
- `0x180153400`
- `0x1801540d0`
- `0x180154180`
- `0x18015dcc8`
- `0x18015de20`
- `0x18015df48`
- `0x18015e148`
- `0x18015ee8c`
- `0x18015ef24`
- `0x18015f2e8`

## callees

- `0x180007484`
- `0x18001358c`
- `0x180015ed0`
- `0x18001603c`
- `0x180016a08`
- `0x180016a70`
- `0x1800171b0`
- `0x1800311c8`
- `0x18004a0b8`
- `0x18008c56c`
- `0x18008c610`
- `0x1800e77ac`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016bf2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016c08`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016bf2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016c08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016bd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016bd8`
- `ntdll!RtlLookupElementGenericTable` at `0x180016b2c`
- `ntdll!RtlLookupElementGenericTable` at `0x180016b2c`

## string_xrefs

- `0x180016d87`: `onecoreuap\windows\dwm\dcomp\winrtnested\WrtProxyObject.inl`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::ProxyObject::SetAnimatableProperty<Windows::Foundation::Numerics::Vector2>(
        __int64 a1,
        float *a2,
        float *a3,
        __int64 a4)
{
  bool v4; // zf
  __int64 v5; // rdi
  char v8; // si
  __int64 v9; // rax
  int v10; // ebx
  struct _RTL_GENERIC_TABLE *BindingManager; // rax
  _QWORD *v12; // rax
  Windows::UI::Composition::AnimationBindingManager *v13; // rcx
  _QWORD *v14; // rsi
  unsigned int v15; // ebx
  char v17; // al
  __int64 v18; // rdx
  const WCHAR *v19; // rdi
  unsigned __int64 v20; // rbx
  unsigned int v21; // eax
  UINT32 v22; // edx
  HRESULT v23; // eax
  __int64 i; // rdx
  __int64 j; // rdi
  __int64 v26; // rax
  int v27; // r12d
  __int64 v28; // rax
  DirectComposition::CDevice *v29; // rbx
  _DWORD *v30; // rax
  _QWORD *v31; // rbx
  _QWORD *v32; // r13
  _QWORD *v33; // rdi
  _QWORD *v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 (__fastcall *v37)(__int64, _BYTE *, int *); // rax
  int v38; // eax
  int v39; // [rsp+20h] [rbp-E0h] BYREF
  void *v40; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v41; // [rsp+30h] [rbp-D0h]
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING_HEADER Buffer; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v45[32]; // [rsp+80h] [rbp-80h] BYREF
  float v46; // [rsp+A0h] [rbp-60h]
  int v47; // [rsp+A4h] [rbp-5Ch]
  int v48; // [rsp+E0h] [rbp-20h]
  char v49; // [rsp+E4h] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v4 = *a2 == *a3;
  v5 = a4;
  v41 = a4;
  if ( v4 && a2[1] == a3[1] )
  {
    v8 = 0;
  }
  else
  {
    v8 = 1;
    *(_QWORD *)a2 = *(_QWORD *)a3;
  }
  v9 = *(_QWORD *)a1;
  BYTE1(v39) = v8;
  LOBYTE(v39) = 0;
  if ( (*(__int64 (__fastcall **)(__int64))(v9 + 232))(a1) )
  {
    v19 = *(const WCHAR **)v5;
    v20 = -1;
    string = 0;
    do
      ++v20;
    while ( v19[v20] );
    if ( v20 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    v21 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v20);
    v22 = v21 - 1;
    if ( (unsigned int)v20 < v21 )
      v22 = v20;
    v23 = WindowsCreateStringReference(v19, v22, &Buffer, &string);
    if ( v23 < 0 )
    {
      RaiseException(v23, 1u, 0, 0);
      __debugbreak();
    }
    v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const struct Microsoft::WRL::Wrappers::HStringReference *)&Buffer);
    Windows::UI::Composition::AnimationValueData::AnimationValueData(v45, v35);
    v36 = *(_QWORD *)a1;
    v49 = v8;
    v48 = 35;
    v37 = *(__int64 (__fastcall **)(__int64, _BYTE *, int *))(v36 + 224);
    v46 = *a3;
    v47 = *((_DWORD *)a3 + 1);
    v38 = v37(a1, v45, &v39);
    v15 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\WrtProxyObject.inl",
        (const char *)(unsigned int)v38,
        v39);
      return v15;
    }
    v5 = v41;
  }
  if ( !(_BYTE)v39 )
  {
    v10 = *(_DWORD *)(v5 + 8) & 0x7FFFFFFF;
    BindingManager = (struct _RTL_GENERIC_TABLE *)Windows::UI::Composition::CompositorCommon::GetBindingManager(*(Windows::UI::Composition::CompositorCommon **)(a1 + 24));
    LODWORD(Buffer.Reserved.Reserved1) = *(_DWORD *)(a1 + 144);
    *(_DWORD *)&Buffer.Reserved.Reserved2[4] = v10;
    *(_OWORD *)&Buffer.Reserved.Reserved2[8] = 0;
    v12 = RtlLookupElementGenericTable(BindingManager, &Buffer);
    v14 = v12;
    if ( v12 )
    {
      for ( i = v12[1]; i; i = *(_QWORD *)(i + 24) )
      {
        *(_WORD *)(i + 16) = 0;
        *(_BYTE *)(i + 18) = 0;
      }
      for ( j = v12[2]; j; j = *(_QWORD *)(j + 24) )
      {
        v26 = *(_QWORD *)(j + 8);
        *(_WORD *)(j + 16) = 0;
        *(_BYTE *)(j + 18) = 0;
        v27 = *(_DWORD *)(v26 + 144);
        if ( v27 )
        {
          v28 = *(_QWORD *)(v26 + 24);
          v40 = 0;
          v29 = *(DirectComposition::CDevice **)(v28 + 440);
          DirectComposition::CDevice::BeginKernelCommand(v29, 0x18u, &v40, 0);
          v30 = v40;
          *(_DWORD *)v40 = 11;
          v30[1] = v27;
          v30[2] = 7;
          *((_QWORD *)v30 + 2) = 0;
          v13 = (Windows::UI::Composition::AnimationBindingManager *)*((_QWORD *)v29 + 11);
          if ( v13 )
            (*(void (__fastcall **)(Windows::UI::Composition::AnimationBindingManager *))(*(_QWORD *)v13 + 24LL))(v13);
        }
      }
      v31 = (_QWORD *)v14[1];
      v32 = v31;
      while ( v31 )
      {
        v33 = v31 + 3;
        if ( Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(
               v13,
               (struct SubchannelMaskInfo *)*v31) )
        {
          Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(v31[1], 6, 1);
          v34 = (_QWORD *)*v33;
          if ( v31 == (_QWORD *)v14[1] )
            v14[1] = v34;
          else
            v32[3] = v34;
          v13 = (Windows::UI::Composition::AnimationBindingManager *)v31;
          v31 = (_QWORD *)*v33;
          *v33 = v14[2];
          v14[2] = v13;
        }
        else
        {
          v32 = v31;
          v31 = (_QWORD *)*v33;
        }
      }
      v5 = v41;
    }
    if ( BYTE1(v39) || v14 )
    {
      v18 = *(unsigned int *)(v5 + 8);
      v17 = *(_BYTE *)(v5 + 16);
      LODWORD(v18) = v18 & 0x7FFFFFFF;
      if ( v17 )
      {
        if ( v17 != 1 )
          Microsoft::WRL2::FailFast::Unexpected(0);
        Windows::UI::Composition::ProxyObject::SetBufferProperty(a1, v18, a3, 8u);
      }
      else
      {
        Windows::UI::Composition::ProxyObject::SetScalarFloatProperty(a1, v18);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016a70  push    rbp
0x180016a72  push    rbx
0x180016a73  push    rsi
0x180016a74  push    rdi
0x180016a75  push    r12
0x180016a77  push    r13
0x180016a79  push    r14
0x180016a7b  push    r15
0x180016a7d  lea     rbp, [rsp-8]
0x180016a82  sub     rsp, 108h
0x180016a89  mov     rax, cs:__security_cookie
0x180016a90  xor     rax, rsp
0x180016a93  mov     [rbp+40h+var_50], rax
0x180016a97  movss   xmm0, dword ptr [rdx]
0x180016a9b  xor     r13d, r13d
0x180016a9e  ucomiss xmm0, dword ptr [r8]
0x180016aa2  mov     rdi, r9
0x180016aa5  mov     [rsp+140h+var_110], r9
0x180016aaa  mov     r14, r8
0x180016aad  mov     r15, rcx
0x180016ab0  jp      short loc_180016AC7
0x180016ab2  jnz     short loc_180016AC7
0x180016ab4  movss   xmm0, dword ptr [rdx+4]
0x180016ab9  ucomiss xmm0, dword ptr [r8+4]
0x180016abe  jp      short loc_180016AC7
0x180016ac0  jnz     short loc_180016AC7
0x180016ac2  mov     sil, r13b
0x180016ac5  jmp     short loc_180016AD3
0x180016ac7  movsd   xmm0, qword ptr [r8]
0x180016acc  mov     sil, 1
0x180016acf  movsd   qword ptr [rdx], xmm0
0x180016ad3  mov     rax, [rcx]
0x180016ad6  mov     byte ptr [rsp+140h+var_120+1], sil
0x180016adb  mov     byte ptr [rsp+140h+var_120], r13b; int
0x180016ae0  mov     rax, [rax+0E8h]
0x180016ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aec  test    rax, rax
0x180016aef  jnz     loc_180016B9C
0x180016af5  cmp     byte ptr [rsp+140h+var_120], r13b
0x180016afa  jnz     short loc_180016B4A
0x180016afc  mov     ebx, [rdi+8]
0x180016aff  mov     rcx, [r15+18h]; this
0x180016b03  btr     ebx, 1Fh
0x180016b07  call    ?GetBindingManager@CompositorCommon@Composition@UI@Windows@@QEAAPEAVAnimationBindingManager@234@XZ; Windows::UI::Composition::CompositorCommon::GetBindingManager(void)
0x180016b0c  mov     ecx, [r15+90h]
0x180016b13  lea     rdx, [rsp+140h+Buffer]; Buffer
0x180016b18  mov     [rsp+140h+Buffer], ecx
0x180016b1c  xorps   xmm0, xmm0
0x180016b1f  mov     rcx, rax; Table
0x180016b22  mov     [rsp+140h+var_E4], ebx
0x180016b26  movdqu  [rsp+140h+var_E0], xmm0
0x180016b2c  call    cs:__imp_RtlLookupElementGenericTable
0x180016b32  mov     rsi, rax
0x180016b35  test    rax, rax
0x180016b38  jnz     loc_180016C0F
0x180016b3e  cmp     byte ptr [rsp+140h+var_120+1], r13b
0x180016b43  jnz     short loc_180016B6F
0x180016b45  test    rsi, rsi
0x180016b48  jnz     short loc_180016B6F
0x180016b4a  mov     ebx, r13d
0x180016b4d  mov     eax, ebx
0x180016b4f  mov     rcx, [rbp+40h+var_50]
0x180016b53  xor     rcx, rsp; StackCookie
0x180016b56  call    __security_check_cookie
0x180016b5b  add     rsp, 108h
0x180016b62  pop     r15
0x180016b64  pop     r14
0x180016b66  pop     r13
0x180016b68  pop     r12
0x180016b6a  pop     rdi
0x180016b6b  pop     rsi
0x180016b6c  pop     rbx
0x180016b6d  pop     rbp
0x180016b6e  retn
0x180016b6f  mov     edx, [rdi+8]
0x180016b72  mov     al, [rdi+10h]
0x180016b75  btr     edx, 1Fh
0x180016b79  test    al, al
0x180016b7b  jz      loc_180016DA0
0x180016b81  cmp     al, 1
0x180016b83  jnz     loc_180016D7B
0x180016b89  mov     r9d, 8
0x180016b8f  mov     r8, r14
0x180016b92  mov     rcx, r15
0x180016b95  call    ?SetBufferProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@PEBX_K@Z; Windows::UI::Composition::ProxyObject::SetBufferProperty(DCOMPOSITION_PROPERTY_ID,void const *,unsigned __int64)
0x180016b9a  jmp     short loc_180016B4A
0x180016b9c  mov     rdi, [rdi]
0x180016b9f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016ba3  mov     [rsp+140h+string], r13
0x180016ba8  inc     rbx
0x180016bab  cmp     [rdi+rbx*2], r13w
0x180016bb0  jnz     short loc_180016BA8
0x180016bb2  mov     eax, 0FFFFFFFFh
0x180016bb7  cmp     rbx, rax
0x180016bba  ja      short loc_180016BF9
0x180016bbc  mov     ecx, ebx; unsigned int
0x180016bbe  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180016bc3  cmp     ebx, eax
0x180016bc5  lea     r9, [rsp+140h+string]; string
0x180016bca  lea     r8, [rsp+140h+Buffer]; hstringHeader
0x180016bcf  mov     rcx, rdi; sourceString
0x180016bd2  lea     edx, [rax-1]
0x180016bd5  cmovb   edx, ebx; length
0x180016bd8  call    cs:__imp_WindowsCreateStringReference
0x180016bde  test    eax, eax
0x180016be0  jns     loc_180016D0C
0x180016be6  xor     r9d, r9d; lpArguments
0x180016be9  xor     r8d, r8d; nNumberOfArguments
0x180016bec  mov     ecx, eax; dwExceptionCode
0x180016bee  lea     edx, [r9+1]; dwExceptionFlags
0x180016bf2  call    cs:__imp_RaiseException
0x180016bf8  int     3; Trap to Debugger
0x180016bf9  xor     r9d, r9d; lpArguments
0x180016bfc  xor     r8d, r8d; nNumberOfArguments
0x180016bff  mov     ecx, 80070216h; dwExceptionCode
0x180016c04  lea     edx, [r9+1]; dwExceptionFlags
0x180016c08  call    cs:__imp_RaiseException
0x180016c0e  int     3; Trap to Debugger
0x180016c0f  mov     rdx, [rax+8]
0x180016c13  jmp     short loc_180016C22
0x180016c15  mov     [rdx+10h], r13w
0x180016c1a  mov     [rdx+12h], r13b
0x180016c1e  mov     rdx, [rdx+18h]
0x180016c22  test    rdx, rdx
0x180016c25  jnz     short loc_180016C15
0x180016c27  mov     rdi, [rax+10h]
0x180016c2b  jmp     short loc_180016C3D
0x180016c2d  mov     rax, [rcx]
0x180016c30  mov     rax, [rax+18h]
0x180016c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c39  mov     rdi, [rdi+18h]
0x180016c3d  test    rdi, rdi
0x180016c40  jz      short loc_180016CA4
0x180016c42  mov     rax, [rdi+8]
0x180016c46  mov     [rdi+10h], r13w
0x180016c4b  mov     [rdi+12h], r13b
0x180016c4f  mov     r12d, [rax+90h]
0x180016c56  test    r12d, r12d
0x180016c59  jz      short loc_180016C39
0x180016c5b  mov     rax, [rax+18h]
0x180016c5f  lea     r8, [rsp+140h+var_118]; void **
0x180016c64  xor     r9d, r9d; bool
0x180016c67  mov     [rsp+140h+var_118], r13
0x180016c6c  mov     rbx, [rax+1B8h]
0x180016c73  mov     rcx, rbx; this
0x180016c76  lea     edx, [r9+18h]; unsigned int
0x180016c7a  call    ?BeginKernelCommand@CDevice@DirectComposition@@AEAAXIPEAPEAX_N@Z; DirectComposition::CDevice::BeginKernelCommand(uint,void * *,bool)
0x180016c7f  mov     rax, [rsp+140h+var_118]
0x180016c84  mov     dword ptr [rax], 0Bh
0x180016c8a  mov     [rax+4], r12d
0x180016c8e  mov     dword ptr [rax+8], 7
0x180016c95  mov     [rax+10h], r13
0x180016c99  mov     rcx, [rbx+58h]
0x180016c9d  test    rcx, rcx
0x180016ca0  jz      short loc_180016C39
0x180016ca2  jmp     short loc_180016C2D
0x180016ca4  mov     rbx, [rsi+8]
0x180016ca8  mov     r13, rbx
0x180016cab  test    rbx, rbx
0x180016cae  jnz     short loc_180016CBD
0x180016cb0  mov     rdi, [rsp+140h+var_110]
0x180016cb5  xor     r13d, r13d
0x180016cb8  jmp     loc_180016B3E
0x180016cbd  mov     rdx, [rbx]; struct SubchannelMaskInfo *
0x180016cc0  lea     rdi, [rbx+18h]
0x180016cc4  call    ?GetSubchannelsFromMask@AnimationBindingManager@Composition@UI@Windows@@AEAAGPEAVSubchannelMaskInfo@@@Z; Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(SubchannelMaskInfo *)
0x180016cc9  test    ax, ax
0x180016ccc  jz      short loc_180016D04
0x180016cce  mov     rcx, [rbx+8]
0x180016cd2  mov     edx, 6
0x180016cd7  lea     r8d, [rdx-5]
0x180016cdb  call    ?SetScalarIntegerProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@_J@Z; Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(DCOMPOSITION_PROPERTY_ID,__int64)
0x180016ce0  mov     rax, [rdi]
0x180016ce3  cmp     rbx, [rsi+8]
0x180016ce7  jnz     loc_180016D72
0x180016ced  mov     [rsi+8], rax
0x180016cf1  mov     rax, [rsi+10h]
0x180016cf5  mov     rcx, rbx
0x180016cf8  mov     rbx, [rdi]
0x180016cfb  mov     [rdi], rax
0x180016cfe  mov     [rsi+10h], rcx
0x180016d02  jmp     short loc_180016CAB
0x180016d04  mov     r13, rbx
0x180016d07  mov     rbx, [rdi]
0x180016d0a  jmp     short loc_180016CAB
0x180016d0c  lea     rdx, [rsp+140h+Buffer]; struct Microsoft::WRL::Wrappers::HStringReference *
0x180016d11  lea     rcx, [rsp+140h+hstringHeader]; hstringHeader
0x180016d16  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV0123@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Microsoft::WRL::Wrappers::HStringReference const &)
0x180016d1b  mov     rdx, rax
0x180016d1e  lea     rcx, [rbp+40h+var_C0]
0x180016d22  call    ??0AnimationValueData@Composition@UI@Windows@@QEAA@VHStringReference@Wrappers@WRL@Microsoft@@@Z; Windows::UI::Composition::AnimationValueData::AnimationValueData(Microsoft::WRL::Wrappers::HStringReference)
0x180016d27  mov     rax, [r15]
0x180016d2a  lea     r8, [rsp+140h+var_120]
0x180016d2f  mov     [rbp+40h+var_5C], sil
0x180016d33  lea     rdx, [rbp+40h+var_C0]
0x180016d37  mov     [rbp+40h+var_60], 23h ; '#'
0x180016d3e  mov     rcx, r15
0x180016d41  movss   xmm0, dword ptr [r14]
0x180016d46  mov     rax, [rax+0E0h]
0x180016d4d  movss   [rbp+40h+var_A0], xmm0
0x180016d52  movss   xmm1, dword ptr [r14+4]
0x180016d58  movss   [rbp+40h+var_9C], xmm1
0x180016d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d62  mov     ebx, eax
0x180016d64  test    eax, eax
0x180016d66  js      short loc_180016D83
0x180016d68  mov     rdi, [rsp+140h+var_110]
0x180016d6d  jmp     loc_180016AF5
0x180016d72  mov     [r13+18h], rax
0x180016d76  jmp     loc_180016CF1
0x180016d7b  xor     ecx, ecx; char *
0x180016d7d  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x180016d83  mov     rcx, [rbp+48h]; this
0x180016d87  lea     r8, aOnecoreuapWind_195; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180016d8e  mov     r9d, eax; char *
0x180016d91  mov     edx, 104h; void *
0x180016d96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016d9b  jmp     loc_180016B4D
0x180016da0  movss   xmm2, dword ptr [r14]
0x180016da5  mov     rcx, r15
0x180016da8  call    ?SetScalarFloatProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@M@Z; Windows::UI::Composition::ProxyObject::SetScalarFloatProperty(DCOMPOSITION_PROPERTY_ID,float)
0x180016dad  jmp     loc_180016B4A
```
