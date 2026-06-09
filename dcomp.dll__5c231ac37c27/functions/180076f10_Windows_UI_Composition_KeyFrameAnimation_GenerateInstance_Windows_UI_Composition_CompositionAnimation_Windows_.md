# Windows::UI::Composition::KeyFrameAnimation::GenerateInstance(Windows::UI::Composition::CompositionAnimation *,Windows::UI::Composition::CompositionObject *,HSTRING__ *,SubchannelMaskInfo *,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Windows::UI::Composition::ParameterOverrideEntry,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Windows::UI::Composition::ParameterOverrideEntry>>> *,Windows::UI::Composition::CompositionPropertyAnimator * *)

- ea: `0x180076f10`
- end: `0x180077251`
- name: `?GenerateInstance@KeyFrameAnimation@Composition@UI@Windows@@UEAAJPEAVCompositionAnimation@234@PEAVCompositionObject@234@PEAUHSTRING__@@PEAVSubchannelMaskInfo@@PEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@PEAPEAVCompositionPropertyAnimator@234@@Z`
- size: `833`
- prototype: `__int64 __usercall@<rax>(Windows::UI::Composition::CompositionAnimation *this@<rcx>, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180006590`
- `0x18000bc00`
- `0x18000e278`
- `0x18000f810`
- `0x1800171b0`
- `0x180033bb4`
- `0x1800348d0`
- `0x1800464c4`
- `0x180076f10`
- `0x180077258`
- `0x18007727c`
- `0x1800772f4`
- `0x1800779c4`
- `0x1800f6f10`
- `0x1800f7a80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800770f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180077152`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800771c9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800771df`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800770f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180077152`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800771c9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800771df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800770d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007713c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800770d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007713c`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::KeyFrameAnimation::GenerateInstance(
        Windows::UI::Composition::CompositionAnimation *this,
        struct Windows::UI::Composition::CompositionObject *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        struct Windows::UI::Composition::ProxyObject **a7)
{
  HSTRING v8; // rdx
  unsigned __int64 v9; // r14
  char v13; // r13
  __int64 v14; // rcx
  float *v15; // rax
  char v16; // r15
  void *v17; // rax
  Windows::UI::Composition::KeyFrameAnimator *v18; // rax
  struct Windows::UI::Composition::ProxyObject *v19; // rbp
  int v20; // esi
  unsigned int v22; // eax
  UINT32 v23; // edx
  HRESULT v24; // eax
  unsigned __int64 v25; // rbx
  unsigned int v26; // eax
  UINT32 v27; // edx
  HRESULT v28; // eax
  int v29; // eax
  __int64 v30; // [rsp+38h] [rbp-70h] BYREF
  struct Windows::UI::Composition::ProxyObject **v31; // [rsp+40h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-60h] BYREF
  HSTRING string; // [rsp+60h] [rbp-48h] BYREF

  v8 = 0;
  v9 = -1;
  v31 = a7;
  v13 = 0;
  *a7 = 0;
  if ( (*((_BYTE *)this + 496) & 1) != 0
    || Windows::UI::Composition::CompositionAnimation::HasInitialValueExpressions(this)
    || (v15 = *(float **)(v14 + 440)) == 0
    || *v15 > 0.0 )
  {
    v25 = -1;
    string = v8;
    do
      ++v25;
    while ( Windows::UI::Composition::CompositionAnimation::c_thisParameterName[v25] != (_WORD)v8 );
    if ( v25 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    v26 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v25);
    v27 = v26 - 1;
    if ( (unsigned int)v25 < v26 )
      v27 = v25;
    v28 = WindowsCreateStringReference(
            Windows::UI::Composition::CompositionAnimation::c_thisParameterName,
            v27,
            &hstringHeader,
            &string);
    if ( v28 < 0 )
    {
      RaiseException(v28, 1u, 0, 0);
      __debugbreak();
    }
    v29 = Windows::UI::Composition::CompositionAnimation::SetReferenceParameter(this, string, a2, 1);
    v20 = v29;
    if ( v29 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1801B45C0, 3u, v29, 0xC2u, 0);
      goto LABEL_13;
    }
    v13 = 1;
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionObject>::operator=((char *)this + 288, a3);
    *((_QWORD *)this + 38) = a5;
    *((_QWORD *)this + 37) = a4;
  }
  if ( (*((_BYTE *)this + 496) & 2) != 0 || (v16 = 0, (*(_BYTE *)(*((_QWORD *)this + 3) + 1016LL) & 4) != 0) )
    v16 = 1;
  v17 = DefaultHeap::Alloc(0x190u);
  if ( v17 )
  {
    v18 = (Windows::UI::Composition::KeyFrameAnimator *)memset_0(v17, 0, 0x190u);
    if ( v18 )
      v19 = (struct Windows::UI::Composition::ProxyObject *)Windows::UI::Composition::KeyFrameAnimator::KeyFrameAnimator(v18);
    else
      v19 = 0;
    *((_QWORD *)v19 + 1) = &Windows::UI::Composition::CompositionPropertyAnimator::s_InterfaceType;
    v30 = 0;
    v20 = Windows::UI::Composition::KeyFrameAnimator::RuntimeClassInitialize(v19, a6, v16);
    if ( v20 >= 0 )
    {
      v20 = 0;
      *v31 = v19;
      goto LABEL_13;
    }
    Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>>::~MakeAllocator<Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>>(&v30);
    Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v19);
  }
  else
  {
    v20 = -2147024882;
  }
  MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_1801B45C0, 3u, v20, 0xDFu, 0);
LABEL_13:
  Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock((char *)this + 288);
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  if ( v13 )
  {
    string = 0;
    do
      ++v9;
    while ( Windows::UI::Composition::CompositionAnimation::c_thisParameterName[v9] );
    if ( v9 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    v22 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v9);
    v23 = v22 - 1;
    if ( (unsigned int)v9 < v22 )
      v23 = v9;
    v24 = WindowsCreateStringReference(
            Windows::UI::Composition::CompositionAnimation::c_thisParameterName,
            v23,
            &hstringHeader,
            &string);
    if ( v24 < 0 )
    {
      RaiseException(v24, 1u, 0, 0);
      __debugbreak();
    }
    Windows::UI::Composition::CompositionAnimation::ClearParameter(this, string);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180076f10  mov     [rsp+arg_18], rbx
0x180076f15  push    rbp
0x180076f16  push    rsi
0x180076f17  push    rdi
0x180076f18  push    r12
0x180076f1a  push    r13
0x180076f1c  push    r14
0x180076f1e  push    r15
0x180076f20  sub     rsp, 70h
0x180076f24  mov     rax, cs:__security_cookie
0x180076f2b  xor     rax, rsp
0x180076f2e  mov     [rsp+0A8h+var_40], rax
0x180076f33  mov     rax, [rsp+0A8h+arg_28]
0x180076f3b  mov     r12, rdx
0x180076f3e  xor     edx, edx
0x180076f40  mov     [rsp+0A8h+var_78], rax
0x180076f45  mov     rax, [rsp+0A8h+arg_30]
0x180076f4d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180076f51  mov     [rsp+0A8h+var_68], rax
0x180076f56  mov     rbp, r9
0x180076f59  mov     r15, r8
0x180076f5c  mov     rdi, rcx
0x180076f5f  mov     r13b, dl
0x180076f62  mov     [rax], rdx
0x180076f65  mov     eax, 0FFFFFFFFh
0x180076f6a  test    byte ptr [rcx+1F0h], 1
0x180076f71  jnz     loc_1800770FF
0x180076f77  call    ?HasInitialValueExpressions@CompositionAnimation@Composition@UI@Windows@@QEBA_NXZ; Windows::UI::Composition::CompositionAnimation::HasInitialValueExpressions(void)
0x180076f7c  test    al, al
0x180076f7e  jnz     loc_1800770FA
0x180076f84  mov     rax, [rcx+1B8h]
0x180076f8b  test    rax, rax
0x180076f8e  jz      loc_1800770FA
0x180076f94  movss   xmm0, dword ptr [rax]
0x180076f98  comiss  xmm0, cs:__real@00000000
0x180076f9f  ja      loc_1800770FA
0x180076fa5  xor     r12d, r12d
0x180076fa8  test    byte ptr [rdi+1F0h], 2
0x180076faf  mov     rsi, [rdi+18h]
0x180076fb3  jnz     short loc_180076FC1
0x180076fb5  test    byte ptr [rsi+3F8h], 4
0x180076fbc  mov     r15b, r12b
0x180076fbf  jz      short loc_180076FC4
0x180076fc1  mov     r15b, 1
0x180076fc4  mov     ebp, 190h
0x180076fc9  mov     rbx, r12
0x180076fcc  mov     ecx, ebp; unsigned __int64
0x180076fce  call    ?Alloc@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::Alloc(unsigned __int64)
0x180076fd3  test    rax, rax
0x180076fd6  jz      loc_180077159
0x180076fdc  mov     r8d, ebp; Size
0x180076fdf  xor     edx, edx; Val
0x180076fe1  mov     rcx, rax; void *
0x180076fe4  call    memset_0
0x180076fe9  test    rax, rax
0x180076fec  jz      loc_180077225
0x180076ff2  mov     rcx, rax; this
0x180076ff5  call    ??0KeyFrameAnimator@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::KeyFrameAnimator::KeyFrameAnimator(void)
0x180076ffa  mov     rbp, rax
0x180076ffd  lea     rax, ?s_InterfaceType@CompositionPropertyAnimator@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; Microsoft::WRL2::NestableRuntimeClass::InterfaceType const Windows::UI::Composition::CompositionPropertyAnimator::s_InterfaceType
0x180077004  mov     byte ptr [rsp+0A8h+var_80], r15b; char
0x180077009  mov     [rbp+8], rax
0x18007700d  mov     r9, rdi
0x180077010  mov     rax, [rsp+0A8h+var_78]
0x180077015  mov     rdx, rsi
0x180077018  mov     r8d, [rdi+1B0h]
0x18007701f  mov     rcx, rbp; struct Windows::UI::Composition::ProxyObject *
0x180077022  mov     qword ptr [rsp+0A8h+var_88], rax; __int64
0x180077027  mov     [rsp+0A8h+var_70], r12
0x18007702c  call    ?RuntimeClassInitialize@KeyFrameAnimator@Composition@UI@Windows@@QEAAJPEAVCompositor@234@W4DCOMPOSITION_EXPRESSION_TYPE@@PEAVKeyFrameAnimation@234@PEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UParameterOverrideEntry@Composition@UI@Windows@@@std@@@2@@std@@_N@Z; Windows::UI::Composition::KeyFrameAnimator::RuntimeClassInitialize(Windows::UI::Composition::Compositor *,DCOMPOSITION_EXPRESSION_TYPE,Windows::UI::Composition::KeyFrameAnimation *,std::unordered_map<std::wstring,Windows::UI::Composition::ParameterOverrideEntry> *,bool)
0x180077031  mov     esi, eax
0x180077033  test    eax, eax
0x180077035  js      loc_18007722D
0x18007703b  mov     rax, [rsp+0A8h+var_68]
0x180077040  mov     esi, r12d
0x180077043  mov     [rax], rbp
0x180077046  lea     rcx, [rdi+120h]; void *
0x18007704d  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180077052  mov     [rdi+128h], r12
0x180077059  mov     [rdi+130h], r12
0x180077060  test    r13b, r13b
0x180077063  jnz     short loc_180077095
0x180077065  test    rbx, rbx
0x180077068  jnz     loc_180077244
0x18007706e  mov     eax, esi
0x180077070  mov     rcx, [rsp+0A8h+var_40]
0x180077075  xor     rcx, rsp; StackCookie
0x180077078  call    __security_check_cookie
0x18007707d  mov     rbx, [rsp+0A8h+arg_18]
0x180077085  add     rsp, 70h
0x180077089  pop     r15
0x18007708b  pop     r14
0x18007708d  pop     r13
0x18007708f  pop     r12
0x180077091  pop     rdi
0x180077092  pop     rsi
0x180077093  pop     rbp
0x180077094  retn
0x180077095  mov     rbp, cs:?c_thisParameterName@CompositionAnimation@Composition@UI@Windows@@2QEBGEB; ushort const * const Windows::UI::Composition::CompositionAnimation::c_thisParameterName
0x18007709c  mov     [rsp+0A8h+string], r12
0x1800770a1  inc     r14
0x1800770a4  cmp     [rbp+r14*2+0], r12w
0x1800770aa  jnz     short loc_1800770A1
0x1800770ac  mov     eax, 0FFFFFFFFh
0x1800770b1  cmp     r14, rax
0x1800770b4  ja      loc_1800771BA
0x1800770ba  mov     ecx, r14d; unsigned int
0x1800770bd  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800770c2  cmp     r14d, eax
0x1800770c5  lea     r9, [rsp+0A8h+string]; string
0x1800770ca  lea     r8, [rsp+0A8h+hstringHeader]; hstringHeader
0x1800770cf  mov     rcx, rbp; sourceString
0x1800770d2  lea     edx, [rax-1]
0x1800770d5  cmovb   edx, r14d; length
0x1800770d9  call    cs:__imp_WindowsCreateStringReference
0x1800770df  test    eax, eax
0x1800770e1  jns     loc_180077213
0x1800770e7  xor     r9d, r9d; lpArguments
0x1800770ea  xor     r8d, r8d; nNumberOfArguments
0x1800770ed  mov     ecx, eax; dwExceptionCode
0x1800770ef  lea     edx, [r9+1]; dwExceptionFlags
0x1800770f3  call    cs:__imp_RaiseException
0x1800770f9  int     3; Trap to Debugger
0x1800770fa  mov     eax, 0FFFFFFFFh
0x1800770ff  mov     rsi, cs:?c_thisParameterName@CompositionAnimation@Composition@UI@Windows@@2QEBGEB; ushort const * const Windows::UI::Composition::CompositionAnimation::c_thisParameterName
0x180077106  mov     rbx, r14
0x180077109  mov     [rsp+0A8h+string], rdx
0x18007710e  inc     rbx
0x180077111  cmp     [rsi+rbx*2], dx
0x180077115  jnz     short loc_18007710E
0x180077117  cmp     rbx, rax
0x18007711a  ja      loc_1800771D0
0x180077120  mov     ecx, ebx; unsigned int
0x180077122  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180077127  cmp     ebx, eax
0x180077129  lea     r9, [rsp+0A8h+string]; string
0x18007712e  lea     r8, [rsp+0A8h+hstringHeader]; hstringHeader
0x180077133  mov     rcx, rsi; sourceString
0x180077136  lea     edx, [rax-1]
0x180077139  cmovb   edx, ebx; length
0x18007713c  call    cs:__imp_WindowsCreateStringReference
0x180077142  test    eax, eax
0x180077144  jns     short loc_180077170
0x180077146  xor     r9d, r9d; lpArguments
0x180077149  xor     r8d, r8d; nNumberOfArguments
0x18007714c  mov     ecx, eax; dwExceptionCode
0x18007714e  lea     edx, [r9+1]; dwExceptionFlags
0x180077152  call    cs:__imp_RaiseException
0x180077158  int     3; Trap to Debugger
0x180077159  mov     esi, 8007000Eh
0x18007715e  mov     [rsp+0A8h+var_80], r12
0x180077163  mov     r9d, esi
0x180077166  mov     [rsp+0A8h+var_88], 0DFh
0x18007716e  jmp     short loc_18007719F
0x180077170  mov     rdx, [rsp+0A8h+string]; string
0x180077175  mov     r9b, 1; bool
0x180077178  mov     r8, r12; struct Windows::UI::Composition::CompositionObject *
0x18007717b  mov     rcx, rdi; this
0x18007717e  call    ?SetReferenceParameter@CompositionAnimation@Composition@UI@Windows@@QEAAJPEAUHSTRING__@@PEAVCompositionObject@234@_N@Z; Windows::UI::Composition::CompositionAnimation::SetReferenceParameter(HSTRING__ *,Windows::UI::Composition::CompositionObject *,bool)
0x180077183  xor     r12d, r12d
0x180077186  mov     esi, eax
0x180077188  test    eax, eax
0x18007718a  jns     short loc_1800771E6
0x18007718c  mov     [rsp+0A8h+var_80], r12; void *
0x180077191  mov     ebx, r12d
0x180077194  mov     [rsp+0A8h+var_88], 0C2h; unsigned int
0x18007719c  mov     r9d, eax; int
0x18007719f  mov     r8d, 3; unsigned int
0x1800771a5  lea     rdx, qword_1801B45C0; int *
0x1800771ac  lea     ecx, [r8+1]; unsigned int
0x1800771b0  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800771b5  jmp     loc_180077046
0x1800771ba  xor     r9d, r9d; lpArguments
0x1800771bd  xor     r8d, r8d; nNumberOfArguments
0x1800771c0  mov     ecx, 80070216h; dwExceptionCode
0x1800771c5  lea     edx, [r9+1]; dwExceptionFlags
0x1800771c9  call    cs:__imp_RaiseException
0x1800771cf  int     3; Trap to Debugger
0x1800771d0  xor     r9d, r9d; lpArguments
0x1800771d3  xor     r8d, r8d; nNumberOfArguments
0x1800771d6  mov     ecx, 80070216h; dwExceptionCode
0x1800771db  lea     edx, [r9+1]; dwExceptionFlags
0x1800771df  call    cs:__imp_RaiseException
0x1800771e5  int     3; Trap to Debugger
0x1800771e6  lea     rcx, [rdi+120h]
0x1800771ed  mov     rdx, r15
0x1800771f0  mov     r13b, 1
0x1800771f3  call    ??4?$RefPtr@VCompositionObject@Composition@UI@Windows@@@WRL2@Microsoft@@QEAAAEAV012@PEAVCompositionObject@Composition@UI@Windows@@@Z; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionObject>::operator=(Windows::UI::Composition::CompositionObject *)
0x1800771f8  mov     rax, [rsp+0A8h+arg_20]
0x180077200  mov     [rdi+130h], rax
0x180077207  mov     [rdi+128h], rbp
0x18007720e  jmp     loc_180076FA8
0x180077213  mov     rdx, [rsp+0A8h+string]; HSTRING
0x180077218  mov     rcx, rdi; this
0x18007721b  call    ?ClearParameter@CompositionAnimation@Composition@UI@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::UI::Composition::CompositionAnimation::ClearParameter(HSTRING__ *)
0x180077220  jmp     loc_180077065
0x180077225  mov     rbp, r12
0x180077228  jmp     loc_180076FFD
0x18007722d  lea     rcx, [rsp+0A8h+var_70]
0x180077232  call    ??1?$MakeAllocator@V?$NaiveSplitView@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@7895@U?$DefaultLifetimeTraits@PEAUICompositionAnimationBase@Composition@UI@Windows@@@7895@U?$HashMapOptions@PEAUHSTRING__@@PEAUICompositionAnimationBase@Composition@UI@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@5@$0A@$00$0A@@7895@@Internal@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>>::~MakeAllocator<Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Composition::ICompositionAnimationBase *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::UI::Composition::ICompositionAnimationBase *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>>(void)
0x180077237  mov     rcx, rbp; this
0x18007723a  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x18007723f  jmp     loc_18007715E
0x180077244  mov     rcx, rbx; this
0x180077247  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x18007724c  jmp     loc_18007706E
```
