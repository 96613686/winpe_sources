# Windows::UI::Composition::VisualCommon::SetOpacity(float)

- ea: `0x18001626c`
- end: `0x180016571`
- name: `?SetOpacity@VisualCommon@Composition@UI@Windows@@QEAAJM@Z`
- size: `773`
- prototype: `__int64 __fastcall(Windows::UI::Composition::VisualCommon *__hidden this, float)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800d3c50`

## callees

- `0x180007484`
- `0x18001358c`
- `0x180015ed0`
- `0x18001603c`
- `0x18001626c`
- `0x180016a08`
- `0x1800171b0`
- `0x180017890`
- `0x18004a0b8`
- `0x180053170`
- `0x18008c56c`
- `0x18008c610`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800164e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800164fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800164e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800164fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800164cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800164cb`
- `ntdll!RtlLookupElementGenericTable` at `0x180016323`
- `ntdll!RtlLookupElementGenericTable` at `0x180016323`

## string_xrefs

- `0x180016558`: `onecoreuap\windows\dwm\dcomp\winrtnested\WrtProxyObject.inl`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::VisualCommon::SetOpacity(
        Windows::UI::Composition::CompositorCommon **this,
        float a2)
{
  float v3; // xmm6_4
  char v4; // si
  Windows::UI::Composition::CompositorCommon *v5; // rax
  struct _RTL_GENERIC_TABLE *BindingManager; // rax
  _QWORD *v7; // rax
  Windows::UI::Composition::AnimationBindingManager *v8; // rcx
  _QWORD *v9; // r14
  unsigned int v10; // ebx
  __int64 i; // rdx
  __int64 j; // rsi
  __int64 v14; // rax
  int v15; // r12d
  __int64 v16; // rax
  DirectComposition::CDevice *v17; // rdi
  _DWORD *v18; // rax
  _QWORD *v19; // rdi
  _QWORD *v20; // r13
  _QWORD *v21; // rsi
  _QWORD *v22; // rax
  unsigned __int64 v23; // rbx
  unsigned int v24; // eax
  UINT32 v25; // edx
  HRESULT v26; // eax
  __int64 v27; // rax
  Windows::UI::Composition::CompositorCommon *v28; // rax
  int v29; // eax
  int v30[2]; // [rsp+28h] [rbp-E0h] BYREF
  void *v31; // [rsp+30h] [rbp-D8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-C8h] BYREF
  HSTRING_HEADER Buffer; // [rsp+60h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v35[32]; // [rsp+88h] [rbp-80h] BYREF
  float v36; // [rsp+A8h] [rbp-60h]
  int v37; // [rsp+E8h] [rbp-20h]
  char v38; // [rsp+ECh] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v3 = fminf(1.0, fmaxf(a2, 0.0));
  if ( Windows::UI::Composition::VisualCommon::GetSparse_Opacity((Windows::UI::Composition::VisualCommon *)this) == v3 )
  {
    v4 = 0;
  }
  else
  {
    Windows::UI::Composition::VisualCommon::SetSparse_Opacity((Windows::UI::Composition::VisualCommon *)this, v3);
    v4 = 1;
  }
  v5 = *this;
  BYTE1(v30[0]) = v4;
  LOBYTE(v30[0]) = 0;
  if ( !(*((__int64 (__fastcall **)(Windows::UI::Composition::CompositorCommon **))v5 + 29))(this) )
    goto LABEL_4;
  v23 = -1;
  string = 0;
  do
    ++v23;
  while ( Windows::UI::Composition::VisualCommon::sc_Opacity[v23] );
  if ( v23 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v24 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v23);
  v25 = v24 - 1;
  if ( (unsigned int)v23 < v24 )
    v25 = v23;
  v26 = WindowsCreateStringReference(Windows::UI::Composition::VisualCommon::sc_Opacity, v25, &Buffer, &string);
  if ( v26 < 0 )
  {
    RaiseException(v26, 1u, 0, 0);
    __debugbreak();
  }
  v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          &hstringHeader,
          (const struct Microsoft::WRL::Wrappers::HStringReference *)&Buffer);
  Windows::UI::Composition::AnimationValueData::AnimationValueData(v35, v27);
  v28 = *this;
  v36 = v3;
  v38 = v4;
  v37 = 18;
  v29 = (*((__int64 (__fastcall **)(Windows::UI::Composition::CompositorCommon **, _BYTE *, int *))v28 + 28))(
          this,
          v35,
          v30);
  v10 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\WrtProxyObject.inl",
      (const char *)(unsigned int)v29,
      v30[0]);
  }
  else
  {
LABEL_4:
    if ( !LOBYTE(v30[0]) )
    {
      BindingManager = (struct _RTL_GENERIC_TABLE *)Windows::UI::Composition::CompositorCommon::GetBindingManager(this[3]);
      LODWORD(Buffer.Reserved.Reserved1) = *((_DWORD *)this + 36);
      *(_OWORD *)&Buffer.Reserved.Reserved2[8] = 0;
      *(_DWORD *)&Buffer.Reserved.Reserved2[4] = 26;
      v7 = RtlLookupElementGenericTable(BindingManager, &Buffer);
      v9 = v7;
      if ( v7 )
      {
        for ( i = v7[1]; i; i = *(_QWORD *)(i + 24) )
        {
          *(_WORD *)(i + 16) = 0;
          *(_BYTE *)(i + 18) = 0;
        }
        for ( j = v7[2]; j; j = *(_QWORD *)(j + 24) )
        {
          v14 = *(_QWORD *)(j + 8);
          *(_WORD *)(j + 16) = 0;
          *(_BYTE *)(j + 18) = 0;
          v15 = *(_DWORD *)(v14 + 144);
          if ( v15 )
          {
            v16 = *(_QWORD *)(v14 + 24);
            v31 = 0;
            v17 = *(DirectComposition::CDevice **)(v16 + 440);
            DirectComposition::CDevice::BeginKernelCommand(v17, 0x18u, &v31, 0);
            v18 = v31;
            *(_DWORD *)v31 = 11;
            v18[1] = v15;
            v18[2] = 7;
            *((_QWORD *)v18 + 2) = 0;
            v8 = (Windows::UI::Composition::AnimationBindingManager *)*((_QWORD *)v17 + 11);
            if ( v8 )
              (*(void (__fastcall **)(Windows::UI::Composition::AnimationBindingManager *))(*(_QWORD *)v8 + 24LL))(v8);
          }
        }
        v19 = (_QWORD *)v9[1];
        v20 = v19;
        while ( v19 )
        {
          v21 = v19 + 3;
          if ( Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(
                 v8,
                 (struct SubchannelMaskInfo *)*v19) )
          {
            Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(v19[1], 6, 1);
            v22 = (_QWORD *)*v21;
            if ( v19 == (_QWORD *)v9[1] )
              v9[1] = v22;
            else
              v20[3] = v22;
            v8 = (Windows::UI::Composition::AnimationBindingManager *)v19;
            v19 = (_QWORD *)*v21;
            *v21 = v9[2];
            v9[2] = v8;
          }
          else
          {
            v20 = v19;
            v19 = (_QWORD *)*v21;
          }
        }
      }
      if ( BYTE1(v30[0]) || v9 )
        Windows::UI::Composition::ProxyObject::SetScalarFloatProperty(this, 26);
    }
    return 0;
  }
  return v10;
}

```

## disassembly

```asm
0x18001626c  mov     rax, rsp
0x18001626f  push    rbp
0x180016270  push    rbx
0x180016271  push    rsi
0x180016272  push    rdi
0x180016273  push    r12
0x180016275  push    r13
0x180016277  push    r14
0x180016279  push    r15
0x18001627b  lea     rbp, [rax-58h]
0x18001627f  sub     rsp, 118h
0x180016286  movaps  xmmword ptr [rax-58h], xmm6
0x18001628a  mov     rax, cs:__security_cookie
0x180016291  xor     rax, rsp
0x180016294  mov     [rbp+50h+var_60], rax
0x180016298  maxss   xmm1, cs:__real@00000000
0x1800162a0  movss   xmm6, cs:__real@3f800000
0x1800162a8  mov     r15, rcx
0x1800162ab  minss   xmm6, xmm1
0x1800162af  call    ?GetSparse_Opacity@VisualCommon@Composition@UI@Windows@@AEBAMXZ; Windows::UI::Composition::VisualCommon::GetSparse_Opacity(void)
0x1800162b4  xor     r13d, r13d
0x1800162b7  ucomiss xmm0, xmm6
0x1800162ba  jp      loc_180016372
0x1800162c0  jnz     loc_180016372
0x1800162c6  mov     sil, r13b
0x1800162c9  mov     rax, [r15]
0x1800162cc  mov     rcx, r15
0x1800162cf  mov     byte ptr [rsp+150h+var_130+1], sil
0x1800162d4  mov     byte ptr [rsp+150h+var_130], r13b; int
0x1800162d9  mov     rax, [rax+0E8h]
0x1800162e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162e5  test    rax, rax
0x1800162e8  jnz     loc_18001648B
0x1800162ee  cmp     byte ptr [rsp+150h+var_130], r13b
0x1800162f3  jnz     short loc_180016345
0x1800162f5  mov     rcx, [r15+18h]; this
0x1800162f9  call    ?GetBindingManager@CompositorCommon@Composition@UI@Windows@@QEAAPEAVAnimationBindingManager@234@XZ; Windows::UI::Composition::CompositorCommon::GetBindingManager(void)
0x1800162fe  mov     ecx, [r15+90h]
0x180016305  lea     rdx, [rsp+150h+Buffer]; Buffer
0x18001630a  mov     dword ptr [rsp+150h+Buffer], ecx
0x18001630e  xorps   xmm0, xmm0
0x180016311  mov     ebx, 1Ah
0x180016316  mov     rcx, rax; Table
0x180016319  movdqu  [rsp+150h+Buffer+8], xmm0
0x18001631f  mov     dword ptr [rsp+150h+Buffer+4], ebx
0x180016323  call    cs:__imp_RtlLookupElementGenericTable
0x180016329  mov     r14, rax
0x18001632c  test    rax, rax
0x18001632f  jnz     short loc_180016385
0x180016331  cmp     byte ptr [rsp+150h+var_130+1], r13b
0x180016336  jnz     loc_18001642E
0x18001633c  test    r14, r14
0x18001633f  jnz     loc_18001642E
0x180016345  mov     ebx, r13d
0x180016348  mov     eax, ebx
0x18001634a  mov     rcx, [rbp+50h+var_60]
0x18001634e  xor     rcx, rsp; StackCookie
0x180016351  call    __security_check_cookie
0x180016356  movaps  xmm6, [rsp+150h+var_58+8]
0x18001635e  add     rsp, 118h
0x180016365  pop     r15
0x180016367  pop     r14
0x180016369  pop     r13
0x18001636b  pop     r12
0x18001636d  pop     rdi
0x18001636e  pop     rsi
0x18001636f  pop     rbx
0x180016370  pop     rbp
0x180016371  retn
0x180016372  movaps  xmm1, xmm6; float
0x180016375  mov     rcx, r15; this
0x180016378  call    ?SetSparse_Opacity@VisualCommon@Composition@UI@Windows@@AEAAXM@Z; Windows::UI::Composition::VisualCommon::SetSparse_Opacity(float)
0x18001637d  mov     sil, 1
0x180016380  jmp     loc_1800162C9
0x180016385  mov     rdx, [rax+8]
0x180016389  jmp     short loc_180016398
0x18001638b  mov     [rdx+10h], r13w
0x180016390  mov     [rdx+12h], r13b
0x180016394  mov     rdx, [rdx+18h]
0x180016398  test    rdx, rdx
0x18001639b  jnz     short loc_18001638B
0x18001639d  mov     rsi, [rax+10h]
0x1800163a1  jmp     short loc_1800163B3
0x1800163a3  mov     rax, [rcx]
0x1800163a6  mov     rax, [rax+18h]
0x1800163aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163af  mov     rsi, [rsi+18h]
0x1800163b3  test    rsi, rsi
0x1800163b6  jz      short loc_18001641A
0x1800163b8  mov     rax, [rsi+8]
0x1800163bc  mov     [rsi+10h], r13w
0x1800163c1  mov     [rsi+12h], r13b
0x1800163c5  mov     r12d, [rax+90h]
0x1800163cc  test    r12d, r12d
0x1800163cf  jz      short loc_1800163AF
0x1800163d1  mov     rax, [rax+18h]
0x1800163d5  lea     r8, [rsp+150h+var_128]; void **
0x1800163da  xor     r9d, r9d; bool
0x1800163dd  mov     [rsp+150h+var_128], r13
0x1800163e2  mov     rdi, [rax+1B8h]
0x1800163e9  mov     rcx, rdi; this
0x1800163ec  lea     edx, [r9+18h]; unsigned int
0x1800163f0  call    ?BeginKernelCommand@CDevice@DirectComposition@@AEAAXIPEAPEAX_N@Z; DirectComposition::CDevice::BeginKernelCommand(uint,void * *,bool)
0x1800163f5  mov     rax, [rsp+150h+var_128]
0x1800163fa  mov     dword ptr [rax], 0Bh
0x180016400  mov     [rax+4], r12d
0x180016404  mov     dword ptr [rax+8], 7
0x18001640b  mov     [rax+10h], r13
0x18001640f  mov     rcx, [rdi+58h]
0x180016413  test    rcx, rcx
0x180016416  jnz     short loc_1800163A3
0x180016418  jmp     short loc_1800163AF
0x18001641a  mov     rdi, [r14+8]
0x18001641e  mov     r13, rdi
0x180016421  test    rdi, rdi
0x180016424  jnz     short loc_180016440
0x180016426  xor     r13d, r13d
0x180016429  jmp     loc_180016331
0x18001642e  movaps  xmm2, xmm6
0x180016431  mov     edx, ebx
0x180016433  mov     rcx, r15
0x180016436  call    ?SetScalarFloatProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@M@Z; Windows::UI::Composition::ProxyObject::SetScalarFloatProperty(DCOMPOSITION_PROPERTY_ID,float)
0x18001643b  jmp     loc_180016345
0x180016440  mov     rdx, [rdi]; struct SubchannelMaskInfo *
0x180016443  lea     rsi, [rdi+18h]
0x180016447  call    ?GetSubchannelsFromMask@AnimationBindingManager@Composition@UI@Windows@@AEAAGPEAVSubchannelMaskInfo@@@Z; Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(SubchannelMaskInfo *)
0x18001644c  test    ax, ax
0x18001644f  jz      short loc_180016483
0x180016451  mov     rcx, [rdi+8]
0x180016455  mov     edx, 6
0x18001645a  lea     r8d, [rdx-5]
0x18001645e  call    ?SetScalarIntegerProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@_J@Z; Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(DCOMPOSITION_PROPERTY_ID,__int64)
0x180016463  mov     rax, [rsi]
0x180016466  cmp     rdi, [r14+8]
0x18001646a  jnz     short loc_1800164E8
0x18001646c  mov     [r14+8], rax
0x180016470  mov     rax, [r14+10h]
0x180016474  mov     rcx, rdi
0x180016477  mov     rdi, [rsi]
0x18001647a  mov     [rsi], rax
0x18001647d  mov     [r14+10h], rcx
0x180016481  jmp     short loc_180016421
0x180016483  mov     r13, rdi
0x180016486  mov     rdi, [rsi]
0x180016489  jmp     short loc_180016421
0x18001648b  mov     rdi, cs:?sc_Opacity@VisualCommon@Composition@UI@Windows@@0UAnimatedProperty@AnimationHelper@234@B; Windows::UI::Composition::AnimationHelper::AnimatedProperty const Windows::UI::Composition::VisualCommon::sc_Opacity
0x180016492  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016496  mov     [rsp+150h+string], r13
0x18001649b  inc     rbx
0x18001649e  cmp     [rdi+rbx*2], r13w
0x1800164a3  jnz     short loc_18001649B
0x1800164a5  mov     eax, 0FFFFFFFFh
0x1800164aa  cmp     rbx, rax
0x1800164ad  ja      short loc_1800164EE
0x1800164af  mov     ecx, ebx; unsigned int
0x1800164b1  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800164b6  cmp     ebx, eax
0x1800164b8  lea     r9, [rsp+150h+string]; string
0x1800164bd  lea     r8, [rsp+150h+Buffer]; hstringHeader
0x1800164c2  mov     rcx, rdi; sourceString
0x1800164c5  lea     edx, [rax-1]
0x1800164c8  cmovb   edx, ebx; length
0x1800164cb  call    cs:__imp_WindowsCreateStringReference
0x1800164d1  test    eax, eax
0x1800164d3  jns     short loc_180016504
0x1800164d5  xor     r9d, r9d; lpArguments
0x1800164d8  xor     r8d, r8d; nNumberOfArguments
0x1800164db  mov     ecx, eax; dwExceptionCode
0x1800164dd  lea     edx, [r9+1]; dwExceptionFlags
0x1800164e1  call    cs:__imp_RaiseException
0x1800164e7  int     3; Trap to Debugger
0x1800164e8  mov     [r13+18h], rax
0x1800164ec  jmp     short loc_180016470
0x1800164ee  xor     r9d, r9d; lpArguments
0x1800164f1  xor     r8d, r8d; nNumberOfArguments
0x1800164f4  mov     ecx, 80070216h; dwExceptionCode
0x1800164f9  lea     edx, [r9+1]; dwExceptionFlags
0x1800164fd  call    cs:__imp_RaiseException
0x180016503  int     3; Trap to Debugger
0x180016504  lea     rdx, [rsp+150h+Buffer]; struct Microsoft::WRL::Wrappers::HStringReference *
0x180016509  lea     rcx, [rsp+150h+hstringHeader]; hstringHeader
0x18001650e  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV0123@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Microsoft::WRL::Wrappers::HStringReference const &)
0x180016513  mov     rdx, rax
0x180016516  lea     rcx, [rbp+50h+var_D0]
0x18001651a  call    ??0AnimationValueData@Composition@UI@Windows@@QEAA@VHStringReference@Wrappers@WRL@Microsoft@@@Z; Windows::UI::Composition::AnimationValueData::AnimationValueData(Microsoft::WRL::Wrappers::HStringReference)
0x18001651f  mov     rax, [r15]
0x180016522  lea     r8, [rsp+150h+var_130]
0x180016527  lea     rdx, [rbp+50h+var_D0]
0x18001652b  movss   [rbp+50h+var_B0], xmm6
0x180016530  mov     rcx, r15
0x180016533  mov     [rbp+50h+var_6C], sil
0x180016537  mov     [rbp+50h+var_70], 12h
0x18001653e  mov     rax, [rax+0E0h]
0x180016545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001654a  mov     ebx, eax
0x18001654c  test    eax, eax
0x18001654e  jns     loc_1800162EE
0x180016554  mov     rcx, [rbp+58h]; this
0x180016558  lea     r8, aOnecoreuapWind_195; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18001655f  mov     r9d, eax; char *
0x180016562  mov     edx, 104h; void *
0x180016567  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001656c  jmp     loc_180016348
```
