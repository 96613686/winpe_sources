# Windows::UI::Composition::Compositor::Api::CreateExpressionAnimationWithExpression(HSTRING__ *,Windows::UI::Composition::IExpressionAnimation * *)

- ea: `0x180037da0`
- end: `0x180037f77`
- name: `?CreateExpressionAnimationWithExpression@Api@Compositor@Composition@UI@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIExpressionAnimation@345@@Z`
- size: `471`
- prototype: `int(Windows::UI::Composition::Compositor::Api *__hidden this, HSTRING, struct Windows::UI::Composition::IExpressionAnimation **)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x18000d8cc`
- `0x18000f810`
- `0x180012da0`
- `0x180013528`
- `0x18001358c`
- `0x180030db8`
- `0x1800348d0`
- `0x180036f90`
- `0x180037da0`
- `0x180038c10`
- `0x180039138`
- `0x180039638`
- `0x1800f7a80`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180037ea3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180037ea3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037e90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037e90`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180037ed9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180037ed9`

## string_xrefs

- `0x180037f0a`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositor.cpp`
- `0x180037ece`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180037ee6`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtexpressionanimation.cpp`
- `0x180037f56`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtexpressionanimation.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::Compositor::Api::CreateExpressionAnimationWithExpression(
        Windows::UI::Composition::Compositor::Api *this,
        HSTRING a2,
        struct Windows::UI::Composition::IExpressionAnimation **a3)
{
  struct Windows::UI::Composition::Compositor *v3; // rbp
  void *v6; // rax
  Windows::UI::Composition::ExpressionAnimation *v7; // rax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  HSTRING v11; // rcx
  HRESULT v12; // eax
  __int64 v13; // rdx
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v16; // [rsp+40h] [rbp+8h] BYREF
  __int64 v17; // [rsp+50h] [rbp+18h] BYREF

  v3 = (Windows::UI::Composition::Compositor::Api *)((char *)this - 1064);
  *a3 = 0;
  Microsoft::WRL2::ContextSession::BeginApiEntry((Windows::UI::Composition::Compositor::Api *)((char *)this - 1064));
  if ( (*((_BYTE *)v3 + 48) & 2) == 0 )
  {
    v9 = -2147483629;
    RoOriginateErrorW(
      2147483667LL,
      0,
      L"The given object has already been closed / disposed and may no longer be used.");
    goto LABEL_8;
  }
  v17 = 0;
  v16 = 0;
  v6 = DefaultHeap::Alloc(0x3D8u);
  if ( !v6 )
  {
    v9 = -2147024882;
    goto LABEL_16;
  }
  v7 = (Windows::UI::Composition::ExpressionAnimation *)memset_0(v6, 0, 0x3D8u);
  if ( v7 )
    v8 = Windows::UI::Composition::ExpressionAnimation::ExpressionAnimation(v7);
  else
    v8 = 0;
  *(_QWORD *)(v8 + 8) = &Windows::UI::Composition::ExpressionAnimation::s_InterfaceType;
  v9 = Windows::UI::Composition::CompositionAnimation::RuntimeClassInitialize(
         (Windows::UI::Composition::CompositionAnimation *)v8,
         v3);
  if ( (v9 & 0x80000000) != 0 )
  {
    v13 = 54;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtexpressionanimation.cpp",
      (const char *)v9,
      v14);
    Microsoft::WRL2::NestableRuntimeClass::InternalRelease((Microsoft::WRL2::NestableRuntimeClass *)v8);
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5CD,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositor.cpp",
      (const char *)v9,
      v14);
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(&v16);
    DoStackCaptureDirect(v9, 0x49Au);
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(&v17);
    goto LABEL_8;
  }
  *(_DWORD *)(v8 + 316) = 0;
  if ( a2 )
  {
    v11 = *(HSTRING *)(v8 + 952);
    if ( v11 )
    {
      WindowsDeleteString(v11);
      *(_QWORD *)(v8 + 952) = 0;
    }
    v12 = WindowsDuplicateString(a2, (HSTRING *)(v8 + 952));
    v9 = v12;
    if ( v12 >= 0 )
    {
      Windows::UI::Composition::ExpressionAnimationBuilder::Reset((Windows::UI::Composition::ExpressionAnimationBuilder *)(v8 + 376));
      Windows::UI::Composition::CompositionAnimation::InvalidateCache((Windows::UI::Composition::CompositionAnimation *)v8);
      goto LABEL_7;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtexpressionanimation.cpp",
      (const char *)(unsigned int)v12,
      v14);
    v13 = 61;
    goto LABEL_15;
  }
LABEL_7:
  *a3 = (struct Windows::UI::Composition::IExpressionAnimation *)((v8 + 360) & -(__int64)(v8 != 0));
  v9 = 0;
LABEL_8:
  Microsoft::WRL2::ContextSession::EndApiEntry(v3);
  return v9;
}

```

## disassembly

```asm
0x180037da0  mov     [rsp+arg_8], rbx
0x180037da5  mov     [rsp+arg_18], rbp
0x180037daa  push    rsi
0x180037dab  push    rdi
0x180037dac  push    r14; int
0x180037dae  sub     rsp, 20h
0x180037db2  lea     rbp, [rcx-428h]
0x180037db9  mov     qword ptr [r8], 0
0x180037dc0  mov     rcx, rbp; this
0x180037dc3  mov     r14, r8
0x180037dc6  mov     rsi, rdx
0x180037dc9  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x180037dce  test    byte ptr [rbp+30h], 2
0x180037dd2  jz      loc_180037EC9
0x180037dd8  mov     ebx, 3D8h
0x180037ddd  mov     [rsp+38h+arg_10], 0
0x180037de6  mov     ecx, ebx; unsigned __int64
0x180037de8  mov     [rsp+38h+arg_0], 0
0x180037df1  call    ?Alloc@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::Alloc(unsigned __int64)
0x180037df6  test    rax, rax
0x180037df9  jz      loc_180037F43
0x180037dff  mov     r8d, ebx; Size
0x180037e02  xor     edx, edx; Val
0x180037e04  mov     rcx, rax; void *
0x180037e07  call    memset_0
0x180037e0c  test    rax, rax
0x180037e0f  jz      loc_180037F4A
0x180037e15  mov     rcx, rax; this
0x180037e18  call    ??0ExpressionAnimation@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::ExpressionAnimation::ExpressionAnimation(void)
0x180037e1d  mov     rdi, rax
0x180037e20  lea     rax, ?s_InterfaceType@ExpressionAnimation@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; Microsoft::WRL2::NestableRuntimeClass::InterfaceType const Windows::UI::Composition::ExpressionAnimation::s_InterfaceType
0x180037e27  mov     rdx, rbp; struct Windows::UI::Composition::Compositor *
0x180037e2a  mov     rcx, rdi; this
0x180037e2d  mov     [rdi+8], rax
0x180037e31  call    ?RuntimeClassInitialize@CompositionAnimation@Composition@UI@Windows@@QEAAJPEAVCompositor@234@@Z; Windows::UI::Composition::CompositionAnimation::RuntimeClassInitialize(Windows::UI::Composition::Compositor *)
0x180037e36  mov     ebx, eax
0x180037e38  test    eax, eax
0x180037e3a  js      loc_180037EE1
0x180037e40  mov     dword ptr [rdi+13Ch], 0
0x180037e4a  test    rsi, rsi
0x180037e4d  jnz     short loc_180037E81
0x180037e4f  lea     rdx, [rdi+168h]
0x180037e56  neg     rdi
0x180037e59  sbb     rax, rax
0x180037e5c  and     rax, rdx
0x180037e5f  mov     [r14], rax
0x180037e62  xor     ebx, ebx
0x180037e64  mov     rcx, rbp; this
0x180037e67  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x180037e6c  mov     rbp, [rsp+38h+arg_18]
0x180037e71  mov     eax, ebx
0x180037e73  mov     rbx, [rsp+38h+arg_8]
0x180037e78  add     rsp, 20h
0x180037e7c  pop     r14
0x180037e7e  pop     rdi
0x180037e7f  pop     rsi
0x180037e80  retn
0x180037e81  lea     rbx, [rdi+3B8h]
0x180037e88  mov     rcx, [rbx]; string
0x180037e8b  test    rcx, rcx
0x180037e8e  jz      short loc_180037E9D
0x180037e90  call    cs:__imp_WindowsDeleteString
0x180037e96  mov     qword ptr [rbx], 0
0x180037e9d  mov     rdx, rbx; newString
0x180037ea0  mov     rcx, rsi; string
0x180037ea3  call    cs:__imp_WindowsDuplicateString
0x180037ea9  mov     ebx, eax
0x180037eab  test    eax, eax
0x180037ead  js      loc_180037F51
0x180037eb3  lea     rcx, [rdi+178h]; this
0x180037eba  call    ?Reset@ExpressionAnimationBuilder@Composition@UI@Windows@@QEAAJXZ; Windows::UI::Composition::ExpressionAnimationBuilder::Reset(void)
0x180037ebf  mov     rcx, rdi; this
0x180037ec2  call    ?InvalidateCache@CompositionAnimation@Composition@UI@Windows@@IEAAXXZ; Windows::UI::Composition::CompositionAnimation::InvalidateCache(void)
0x180037ec7  jmp     short loc_180037E4F
0x180037ec9  mov     ebx, 80000013h
0x180037ece  lea     r8, aTheGivenObject; "The given object has already been close"...
0x180037ed5  mov     ecx, ebx
0x180037ed7  xor     edx, edx
0x180037ed9  call    cs:__imp_RoOriginateErrorW
0x180037edf  jmp     short loc_180037E64
0x180037ee1  mov     edx, 36h ; '6'; void *
0x180037ee6  lea     rsi, aOnecoreuapWind_19; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180037eed  mov     rcx, [rsp+38h]; this
0x180037ef2  mov     r9d, ebx; char *
0x180037ef5  mov     r8, rsi; unsigned int
0x180037ef8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037efd  mov     rcx, rdi; this
0x180037f00  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x180037f05  mov     rcx, [rsp+38h]; this
0x180037f0a  lea     r8, aOnecoreuapWind_158; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180037f11  mov     r9d, ebx; char *
0x180037f14  mov     edx, 5CDh; void *
0x180037f19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037f1e  lea     rcx, [rsp+38h+arg_0]
0x180037f23  call    ?InternalUnlock@?$RefPtr@VNaturalMotionAnimation@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(void)
0x180037f28  mov     edx, 49Ah; unsigned int
0x180037f2d  mov     ecx, ebx; int
0x180037f2f  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180037f34  lea     rcx, [rsp+38h+arg_10]
0x180037f39  call    ?InternalUnlock@?$RefPtr@VNaturalMotionAnimation@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(void)
0x180037f3e  jmp     loc_180037E64
0x180037f43  mov     ebx, 8007000Eh
0x180037f48  jmp     short loc_180037F05
0x180037f4a  xor     edi, edi
0x180037f4c  jmp     loc_180037E20
0x180037f51  mov     rcx, [rsp+38h]; this
0x180037f56  lea     rsi, aOnecoreuapWind_19; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180037f5d  mov     r8, rsi; unsigned int
0x180037f60  mov     r9d, ebx; char *
0x180037f63  mov     edx, 1A1h; void *
0x180037f68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037f6d  mov     edx, 3Dh ; '='
0x180037f72  jmp     loc_180037EED
```
