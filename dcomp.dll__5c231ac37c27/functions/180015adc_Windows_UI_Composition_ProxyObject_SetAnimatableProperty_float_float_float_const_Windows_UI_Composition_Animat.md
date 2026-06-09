# Windows::UI::Composition::ProxyObject::SetAnimatableProperty<float>(float *,float const &,Windows::UI::Composition::AnimationHelper::AnimatedProperty const &)

- ea: `0x180015adc`
- end: `0x180015ebf`
- name: `??$SetAnimatableProperty@M@ProxyObject@Composition@UI@Windows@@IEAAJPEAMAEBMAEBUAnimatedProperty@AnimationHelper@123@@Z`
- size: `995`
- prototype: ``
- caller_count: `69`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034ed0`
- `0x180035500`
- `0x180035860`
- `0x1800359a0`
- `0x180037b30`
- `0x180037c50`
- `0x180046e0c`
- `0x18004bb60`
- `0x18004bc60`
- `0x18004bd60`
- `0x18004be60`
- `0x18004bf60`
- `0x18004c060`
- `0x18004c160`
- `0x18004c260`
- `0x1800a9300`
- `0x1800a9d60`
- `0x1800a9ef0`
- `0x1800aa2a0`
- `0x1800aa360`
- `0x1800aa400`
- `0x1800aab70`
- `0x1800aac10`
- `0x1800b3534`
- `0x1800b8374`
- `0x1800b86c4`
- `0x1800c3530`
- `0x1800c4714`
- `0x1800c4d84`
- `0x1800c7340`
- `0x1800c9ad4`
- `0x1800d3208`
- `0x1800d9180`
- `0x1800eb448`
- `0x1800eb49c`
- `0x1800eb51c`
- `0x1800ecf60`
- `0x1800ef7e0`
- `0x180132cb0`
- `0x180132ee0`
- `0x180139064`
- `0x180142998`
- `0x180150270`
- `0x180150f00`
- `0x180151d00`
- `0x180153d70`
- `0x180153df8`
- `0x180154618`
- `0x180154720`
- `0x180154774`

## callees

- `0x180007484`
- `0x18001358c`
- `0x180015adc`
- `0x180015ed0`
- `0x18001603c`
- `0x180016a08`
- `0x1800171b0`
- `0x1800311c8`
- `0x18004a0b8`
- `0x1800f6f10`
- `0x1800f7a80`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015c35`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015c6f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015dc4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015e1d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015c35`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015c6f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015dc4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015e1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015d83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015dde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015d83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015dde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015c1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015dae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015e07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015c1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015dae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015e07`
- `ntdll!RtlLookupElementGenericTable` at `0x180015b88`
- `ntdll!RtlLookupElementGenericTable` at `0x180015b88`

## string_xrefs

- `0x180015e6d`: `onecoreuap\windows\dwm\dcomp\winrtnested\WrtProxyObject.inl`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::ProxyObject::SetAnimatableProperty<float>(
        __int64 a1,
        float *a2,
        float *a3,
        __int64 a4)
{
  float v4; // xmm1_4
  float v5; // xmm0_4
  __int64 v6; // rdi
  char v9; // si
  __int64 v10; // rax
  int v11; // ebx
  struct _RTL_GENERIC_TABLE *BindingManager; // rax
  _QWORD *v13; // rax
  Windows::UI::Composition::AnimationBindingManager *v14; // rcx
  _QWORD *v15; // rsi
  unsigned int v16; // ebx
  const WCHAR *v18; // rdi
  unsigned __int64 v19; // rbx
  unsigned int v20; // eax
  UINT32 v21; // edx
  HRESULT v22; // eax
  char v23; // al
  __int64 v24; // rdx
  __int64 i; // rdx
  __int64 j; // rdi
  __int64 v27; // rax
  int v28; // r12d
  __int64 v29; // rax
  DirectComposition::CDevice *v30; // rbx
  __int64 v31; // rax
  _QWORD *v32; // rbx
  _QWORD *v33; // r13
  _QWORD *v34; // rdi
  _QWORD *v35; // rax
  const WCHAR *StringRawBuffer; // rbx
  unsigned int v37; // eax
  UINT32 v38; // edx
  HRESULT v39; // eax
  const WCHAR *v40; // rbx
  unsigned int v41; // eax
  UINT32 v42; // edx
  HRESULT v43; // eax
  __int64 v44; // rax
  __int64 (__fastcall *v45)(__int64, HSTRING_HEADER *, int *); // rax
  int v46; // eax
  int v47; // [rsp+20h] [rbp-E0h] BYREF
  UINT32 length[2]; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v49; // [rsp+30h] [rbp-D0h]
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v51; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER Buffer; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  HSTRING_HEADER v54; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v55; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v56[17]; // [rsp+A0h] [rbp-60h] BYREF
  char v57; // [rsp+E4h] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v4 = *a3;
  v5 = *a2;
  v6 = a4;
  v49 = a4;
  if ( v5 == v4 )
  {
    v9 = 0;
  }
  else
  {
    *a2 = v4;
    v9 = 1;
  }
  v10 = *(_QWORD *)a1;
  BYTE1(v47) = v9;
  LOBYTE(v47) = 0;
  if ( (*(__int64 (__fastcall **)(__int64))(v10 + 232))(a1) )
  {
    v18 = *(const WCHAR **)v6;
    v19 = -1;
    string = 0;
    do
      ++v19;
    while ( v18[v19] );
    if ( v19 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    v20 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v19);
    v21 = v20 - 1;
    if ( (unsigned int)v19 < v20 )
      v21 = v19;
    v22 = WindowsCreateStringReference(v18, v21, &Buffer, &string);
    if ( v22 < 0 )
    {
      RaiseException(v22, 1u, 0, 0);
      __debugbreak();
    }
    v51 = 0;
    length[0] = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, length);
    v37 = Microsoft::WRL::Wrappers::HStringReference::AddOne(length[0]);
    v38 = v37 - 1;
    if ( length[0] < v37 )
      v38 = length[0];
    v39 = WindowsCreateStringReference(StringRawBuffer, v38, &hstringHeader, &v51);
    if ( v39 < 0 )
    {
      RaiseException(v39, 1u, 0, 0);
      __debugbreak();
    }
    v55 = 0;
    length[0] = 0;
    v40 = WindowsGetStringRawBuffer(v51, length);
    v41 = Microsoft::WRL::Wrappers::HStringReference::AddOne(length[0]);
    v42 = v41 - 1;
    if ( length[0] < v41 )
      v42 = length[0];
    v43 = WindowsCreateStringReference(v40, v42, &v54, &v55);
    if ( v43 < 0 )
    {
      RaiseException(v43, 1u, 0, 0);
      __debugbreak();
    }
    memset_0(v56, 0, 0x40u);
    v44 = *(_QWORD *)a1;
    v57 = v9;
    v56[16] = 18;
    v45 = *(__int64 (__fastcall **)(__int64, HSTRING_HEADER *, int *))(v44 + 224);
    *(float *)v56 = *a3;
    v46 = v45(a1, &v54, &v47);
    v16 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\WrtProxyObject.inl",
        (const char *)(unsigned int)v46,
        v47);
      return v16;
    }
    v6 = v49;
  }
  if ( !(_BYTE)v47 )
  {
    v11 = *(_DWORD *)(v6 + 8) & 0x7FFFFFFF;
    BindingManager = (struct _RTL_GENERIC_TABLE *)Windows::UI::Composition::CompositorCommon::GetBindingManager(*(Windows::UI::Composition::CompositorCommon **)(a1 + 24));
    LODWORD(Buffer.Reserved.Reserved1) = *(_DWORD *)(a1 + 144);
    *(_DWORD *)&Buffer.Reserved.Reserved2[4] = v11;
    *(_OWORD *)&Buffer.Reserved.Reserved2[8] = 0;
    v13 = RtlLookupElementGenericTable(BindingManager, &Buffer);
    v15 = v13;
    if ( v13 )
    {
      for ( i = v13[1]; i; i = *(_QWORD *)(i + 24) )
      {
        *(_WORD *)(i + 16) = 0;
        *(_BYTE *)(i + 18) = 0;
      }
      for ( j = v13[2]; j; j = *(_QWORD *)(j + 24) )
      {
        v27 = *(_QWORD *)(j + 8);
        *(_WORD *)(j + 16) = 0;
        *(_BYTE *)(j + 18) = 0;
        v28 = *(_DWORD *)(v27 + 144);
        if ( v28 )
        {
          v29 = *(_QWORD *)(v27 + 24);
          *(_QWORD *)length = 0;
          v30 = *(DirectComposition::CDevice **)(v29 + 440);
          DirectComposition::CDevice::BeginKernelCommand(v30, 0x18u, (void **)length, 0);
          v31 = *(_QWORD *)length;
          **(_DWORD **)length = 11;
          *(_DWORD *)(v31 + 4) = v28;
          *(_DWORD *)(v31 + 8) = 7;
          *(_QWORD *)(v31 + 16) = 0;
          v14 = (Windows::UI::Composition::AnimationBindingManager *)*((_QWORD *)v30 + 11);
          if ( v14 )
            (*(void (__fastcall **)(Windows::UI::Composition::AnimationBindingManager *))(*(_QWORD *)v14 + 24LL))(v14);
        }
      }
      v32 = (_QWORD *)v15[1];
      v33 = v32;
      while ( v32 )
      {
        v34 = v32 + 3;
        if ( Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(
               v14,
               (struct SubchannelMaskInfo *)*v32) )
        {
          Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(v32[1], 6, 1);
          v35 = (_QWORD *)*v34;
          if ( v32 == (_QWORD *)v15[1] )
            v15[1] = v35;
          else
            v33[3] = v35;
          v14 = (Windows::UI::Composition::AnimationBindingManager *)v32;
          v32 = (_QWORD *)*v34;
          *v34 = v15[2];
          v15[2] = v14;
        }
        else
        {
          v33 = v32;
          v32 = (_QWORD *)*v34;
        }
      }
      v6 = v49;
    }
    if ( BYTE1(v47) || v15 )
    {
      v24 = *(unsigned int *)(v6 + 8);
      v23 = *(_BYTE *)(v6 + 16);
      LODWORD(v24) = v24 & 0x7FFFFFFF;
      if ( v23 )
      {
        if ( v23 == 1 )
          Windows::UI::Composition::ProxyObject::SetBufferProperty(a1, v24, a3, 4u);
        else
          Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(a1, v24, *(int *)a3);
      }
      else
      {
        Windows::UI::Composition::ProxyObject::SetScalarFloatProperty(a1, v24);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180015adc  push    rbp
0x180015ade  push    rbx
0x180015adf  push    rsi
0x180015ae0  push    rdi
0x180015ae1  push    r12
0x180015ae3  push    r13
0x180015ae5  push    r14
0x180015ae7  push    r15
0x180015ae9  lea     rbp, [rsp-8]
0x180015aee  sub     rsp, 108h
0x180015af5  mov     rax, cs:__security_cookie
0x180015afc  xor     rax, rsp
0x180015aff  mov     [rbp+40h+var_50], rax
0x180015b03  movss   xmm1, dword ptr [r8]
0x180015b08  xor     r13d, r13d
0x180015b0b  movss   xmm0, dword ptr [rdx]
0x180015b0f  mov     rdi, r9
0x180015b12  ucomiss xmm0, xmm1
0x180015b15  mov     [rsp+140h+var_110], r9
0x180015b1a  mov     r15, r8
0x180015b1d  mov     r14, rcx
0x180015b20  jp      loc_180015BD3
0x180015b26  jnz     loc_180015BD3
0x180015b2c  mov     sil, r13b
0x180015b2f  mov     rax, [rcx]
0x180015b32  mov     byte ptr [rsp+140h+var_120+1], sil
0x180015b37  mov     byte ptr [rsp+140h+var_120], r13b; int
0x180015b3c  mov     rax, [rax+0E8h]
0x180015b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b48  test    rax, rax
0x180015b4b  jnz     loc_180015BDF
0x180015b51  cmp     byte ptr [rsp+140h+var_120], r13b
0x180015b56  jnz     short loc_180015BAE
0x180015b58  mov     ebx, [rdi+8]
0x180015b5b  mov     rcx, [r14+18h]; this
0x180015b5f  btr     ebx, 1Fh
0x180015b63  call    ?GetBindingManager@CompositorCommon@Composition@UI@Windows@@QEAAPEAVAnimationBindingManager@234@XZ; Windows::UI::Composition::CompositorCommon::GetBindingManager(void)
0x180015b68  mov     ecx, [r14+90h]
0x180015b6f  lea     rdx, [rsp+140h+Buffer]; Buffer
0x180015b74  mov     [rsp+140h+Buffer], ecx
0x180015b78  xorps   xmm0, xmm0
0x180015b7b  mov     rcx, rax; Table
0x180015b7e  mov     [rsp+140h+var_E4], ebx
0x180015b82  movdqu  [rsp+140h+var_E0], xmm0
0x180015b88  call    cs:__imp_RtlLookupElementGenericTable
0x180015b8e  mov     rsi, rax
0x180015b91  test    rax, rax
0x180015b94  jnz     loc_180015C76
0x180015b9a  cmp     byte ptr [rsp+140h+var_120+1], r13b
0x180015b9f  jnz     loc_180015C3C
0x180015ba5  test    rsi, rsi
0x180015ba8  jnz     loc_180015C3C
0x180015bae  mov     ebx, r13d
0x180015bb1  mov     eax, ebx
0x180015bb3  mov     rcx, [rbp+40h+var_50]
0x180015bb7  xor     rcx, rsp; StackCookie
0x180015bba  call    __security_check_cookie
0x180015bbf  add     rsp, 108h
0x180015bc6  pop     r15
0x180015bc8  pop     r14
0x180015bca  pop     r13
0x180015bcc  pop     r12
0x180015bce  pop     rdi
0x180015bcf  pop     rsi
0x180015bd0  pop     rbx
0x180015bd1  pop     rbp
0x180015bd2  retn
0x180015bd3  movss   dword ptr [rdx], xmm1
0x180015bd7  mov     sil, 1
0x180015bda  jmp     loc_180015B2F
0x180015bdf  mov     rdi, [rdi]
0x180015be2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015be6  mov     [rsp+140h+string], r13
0x180015beb  inc     rbx
0x180015bee  cmp     [rdi+rbx*2], r13w
0x180015bf3  jnz     short loc_180015BEB
0x180015bf5  mov     eax, 0FFFFFFFFh
0x180015bfa  cmp     rbx, rax
0x180015bfd  ja      short loc_180015C60
0x180015bff  mov     ecx, ebx; unsigned int
0x180015c01  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180015c06  cmp     ebx, eax
0x180015c08  lea     r9, [rsp+140h+string]; string
0x180015c0d  lea     r8, [rsp+140h+Buffer]; hstringHeader
0x180015c12  mov     rcx, rdi; sourceString
0x180015c15  lea     edx, [rax-1]
0x180015c18  cmovb   edx, ebx; length
0x180015c1b  call    cs:__imp_WindowsCreateStringReference
0x180015c21  test    eax, eax
0x180015c23  jns     loc_180015D6F
0x180015c29  xor     r9d, r9d; lpArguments
0x180015c2c  xor     r8d, r8d; nNumberOfArguments
0x180015c2f  mov     ecx, eax; dwExceptionCode
0x180015c31  lea     edx, [r9+1]; dwExceptionFlags
0x180015c35  call    cs:__imp_RaiseException
0x180015c3b  int     3; Trap to Debugger
0x180015c3c  mov     edx, [rdi+8]
0x180015c3f  mov     rcx, r14
0x180015c42  mov     al, [rdi+10h]
0x180015c45  btr     edx, 1Fh
0x180015c49  test    al, al
0x180015c4b  jnz     loc_180015EA4
0x180015c51  movss   xmm2, dword ptr [r15]
0x180015c56  call    ?SetScalarFloatProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@M@Z; Windows::UI::Composition::ProxyObject::SetScalarFloatProperty(DCOMPOSITION_PROPERTY_ID,float)
0x180015c5b  jmp     loc_180015BAE
0x180015c60  xor     r9d, r9d; lpArguments
0x180015c63  xor     r8d, r8d; nNumberOfArguments
0x180015c66  mov     ecx, 80070216h; dwExceptionCode
0x180015c6b  lea     edx, [r9+1]; dwExceptionFlags
0x180015c6f  call    cs:__imp_RaiseException
0x180015c75  int     3; Trap to Debugger
0x180015c76  mov     rdx, [rax+8]
0x180015c7a  jmp     short loc_180015C89
0x180015c7c  mov     [rdx+10h], r13w
0x180015c81  mov     [rdx+12h], r13b
0x180015c85  mov     rdx, [rdx+18h]
0x180015c89  test    rdx, rdx
0x180015c8c  jnz     short loc_180015C7C
0x180015c8e  mov     rdi, [rax+10h]
0x180015c92  jmp     short loc_180015CA4
0x180015c94  mov     rax, [rcx]
0x180015c97  mov     rax, [rax+18h]
0x180015c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ca0  mov     rdi, [rdi+18h]
0x180015ca4  test    rdi, rdi
0x180015ca7  jz      short loc_180015D0B
0x180015ca9  mov     rax, [rdi+8]
0x180015cad  mov     [rdi+10h], r13w
0x180015cb2  mov     [rdi+12h], r13b
0x180015cb6  mov     r12d, [rax+90h]
0x180015cbd  test    r12d, r12d
0x180015cc0  jz      short loc_180015CA0
0x180015cc2  mov     rax, [rax+18h]
0x180015cc6  lea     r8, [rsp+140h+length]; void **
0x180015ccb  xor     r9d, r9d; bool
0x180015cce  mov     qword ptr [rsp+140h+length], r13
0x180015cd3  mov     rbx, [rax+1B8h]
0x180015cda  mov     rcx, rbx; this
0x180015cdd  lea     edx, [r9+18h]; unsigned int
0x180015ce1  call    ?BeginKernelCommand@CDevice@DirectComposition@@AEAAXIPEAPEAX_N@Z; DirectComposition::CDevice::BeginKernelCommand(uint,void * *,bool)
0x180015ce6  mov     rax, qword ptr [rsp+140h+length]
0x180015ceb  mov     dword ptr [rax], 0Bh
0x180015cf1  mov     [rax+4], r12d
0x180015cf5  mov     dword ptr [rax+8], 7
0x180015cfc  mov     [rax+10h], r13
0x180015d00  mov     rcx, [rbx+58h]
0x180015d04  test    rcx, rcx
0x180015d07  jnz     short loc_180015C94
0x180015d09  jmp     short loc_180015CA0
0x180015d0b  mov     rbx, [rsi+8]
0x180015d0f  mov     r13, rbx
0x180015d12  test    rbx, rbx
0x180015d15  jnz     short loc_180015D24
0x180015d17  mov     rdi, [rsp+140h+var_110]
0x180015d1c  xor     r13d, r13d
0x180015d1f  jmp     loc_180015B9A
0x180015d24  mov     rdx, [rbx]; struct SubchannelMaskInfo *
0x180015d27  lea     rdi, [rbx+18h]
0x180015d2b  call    ?GetSubchannelsFromMask@AnimationBindingManager@Composition@UI@Windows@@AEAAGPEAVSubchannelMaskInfo@@@Z; Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(SubchannelMaskInfo *)
0x180015d30  test    ax, ax
0x180015d33  jz      loc_180015E86
0x180015d39  mov     rcx, [rbx+8]
0x180015d3d  mov     edx, 6
0x180015d42  lea     r8d, [rdx-5]
0x180015d46  call    ?SetScalarIntegerProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@_J@Z; Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(DCOMPOSITION_PROPERTY_ID,__int64)
0x180015d4b  mov     rax, [rdi]
0x180015d4e  cmp     rbx, [rsi+8]
0x180015d52  jnz     loc_180015E91
0x180015d58  mov     [rsi+8], rax
0x180015d5c  mov     rax, [rsi+10h]
0x180015d60  mov     rcx, rbx
0x180015d63  mov     rbx, [rdi]
0x180015d66  mov     [rdi], rax
0x180015d69  mov     [rsi+10h], rcx
0x180015d6d  jmp     short loc_180015D12
0x180015d6f  mov     rcx, [rsp+140h+string]; string
0x180015d74  lea     rdx, [rsp+140h+length]; length
0x180015d79  mov     [rsp+140h+var_F0], r13
0x180015d7e  mov     [rsp+140h+length], r13d
0x180015d83  call    cs:__imp_WindowsGetStringRawBuffer
0x180015d89  mov     ecx, [rsp+140h+length]; unsigned int
0x180015d8d  mov     rbx, rax
0x180015d90  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180015d95  cmp     [rsp+140h+length], eax
0x180015d99  lea     r9, [rsp+140h+var_F0]; string
0x180015d9e  lea     r8, [rsp+140h+hstringHeader]; hstringHeader
0x180015da3  mov     rcx, rbx; sourceString
0x180015da6  lea     edx, [rax-1]
0x180015da9  cmovb   edx, [rsp+140h+length]; length
0x180015dae  call    cs:__imp_WindowsCreateStringReference
0x180015db4  test    eax, eax
0x180015db6  jns     short loc_180015DCB
0x180015db8  xor     r9d, r9d; lpArguments
0x180015dbb  xor     r8d, r8d; nNumberOfArguments
0x180015dbe  mov     ecx, eax; dwExceptionCode
0x180015dc0  lea     edx, [r9+1]; dwExceptionFlags
0x180015dc4  call    cs:__imp_RaiseException
0x180015dca  int     3; Trap to Debugger
0x180015dcb  mov     rcx, [rsp+140h+var_F0]; string
0x180015dd0  lea     rdx, [rsp+140h+length]; length
0x180015dd5  mov     [rbp+40h+var_A8], r13
0x180015dd9  mov     [rsp+140h+length], r13d
0x180015dde  call    cs:__imp_WindowsGetStringRawBuffer
0x180015de4  mov     ecx, [rsp+140h+length]; unsigned int
0x180015de8  mov     rbx, rax
0x180015deb  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180015df0  cmp     [rsp+140h+length], eax
0x180015df4  lea     r9, [rbp+40h+var_A8]; string
0x180015df8  lea     r8, [rbp+40h+var_C0]; hstringHeader
0x180015dfc  mov     rcx, rbx; sourceString
0x180015dff  lea     edx, [rax-1]
0x180015e02  cmovb   edx, [rsp+140h+length]; length
0x180015e07  call    cs:__imp_WindowsCreateStringReference
0x180015e0d  test    eax, eax
0x180015e0f  jns     short loc_180015E24
0x180015e11  xor     r9d, r9d; lpArguments
0x180015e14  xor     r8d, r8d; nNumberOfArguments
0x180015e17  mov     ecx, eax; dwExceptionCode
0x180015e19  lea     edx, [r9+1]; dwExceptionFlags
0x180015e1d  call    cs:__imp_RaiseException
0x180015e23  int     3; Trap to Debugger
0x180015e24  xor     edx, edx; Val
0x180015e26  lea     rcx, [rbp+40h+var_A0]; void *
0x180015e2a  lea     r8d, [rdx+40h]; Size
0x180015e2e  call    memset_0
0x180015e33  mov     rax, [r14]
0x180015e36  lea     r8, [rsp+140h+var_120]
0x180015e3b  mov     [rbp+40h+var_5C], sil
0x180015e3f  lea     rdx, [rbp+40h+var_C0]
0x180015e43  mov     [rbp+40h+var_60], 12h
0x180015e4a  mov     rcx, r14
0x180015e4d  movss   xmm0, dword ptr [r15]
0x180015e52  mov     rax, [rax+0E0h]
0x180015e59  movss   [rbp+40h+var_A0], xmm0
0x180015e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e63  mov     ebx, eax
0x180015e65  test    eax, eax
0x180015e67  jns     short loc_180015E9A
0x180015e69  mov     rcx, [rbp+48h]; this
0x180015e6d  lea     r8, aOnecoreuapWind_195; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180015e74  mov     r9d, eax; char *
0x180015e77  mov     edx, 104h; void *
0x180015e7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015e81  jmp     loc_180015BB1
0x180015e86  mov     r13, rbx
0x180015e89  mov     rbx, [rdi]
0x180015e8c  jmp     loc_180015D12
0x180015e91  mov     [r13+18h], rax
0x180015e95  jmp     loc_180015D5C
0x180015e9a  mov     rdi, [rsp+140h+var_110]
0x180015e9f  jmp     loc_180015B51
0x180015ea4  cmp     al, 1
0x180015ea6  jnz     loc_18017D2E6
0x180015eac  mov     r9d, 4
0x180015eb2  mov     r8, r15
0x180015eb5  call    ?SetBufferProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@PEBX_K@Z; Windows::UI::Composition::ProxyObject::SetBufferProperty(DCOMPOSITION_PROPERTY_ID,void const *,unsigned __int64)
0x180015eba  jmp     loc_180015BAE
0x18017d2e6  movsxd  r8, dword ptr [r15]
0x18017d2e9  call    ?SetScalarIntegerProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@_J@Z; Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(DCOMPOSITION_PROPERTY_ID,__int64)
0x18017d2ee  nop
0x18017d2ef  jmp     loc_180015BAE
```
