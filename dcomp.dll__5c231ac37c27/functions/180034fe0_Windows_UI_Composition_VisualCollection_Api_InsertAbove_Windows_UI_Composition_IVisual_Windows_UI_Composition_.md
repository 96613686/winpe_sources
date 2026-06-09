# Windows::UI::Composition::VisualCollection::Api::InsertAbove(Windows::UI::Composition::IVisual *,Windows::UI::Composition::IVisual *)

- ea: `0x180034fe0`
- end: `0x1800354ef`
- name: `?InsertAbove@Api@VisualCollection@Composition@UI@Windows@@UEAAJPEAUIVisual@345@0@Z`
- size: `1295`
- prototype: `__int64 __fastcall(Windows::UI::Composition::VisualCollection::Api *__hidden this, struct Windows::UI::Composition::IVisual *, struct Windows::UI::Composition::IVisual *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000bc00`
- `0x180012da0`
- `0x180013528`
- `0x18001358c`
- `0x180015ed0`
- `0x180034fe0`
- `0x1800e77ac`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003501b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003501b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800353f9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180035452`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180035473`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800353f9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180035452`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180035473`

## string_xrefs

- `0x1800353ee`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180035442`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180035463`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180035076`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtvisualcollection.cpp`
- `0x18003540d`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtvisual.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::VisualCollection::Api::InsertAbove(
        Windows::UI::Composition::VisualCollection::Api *this,
        __int64 (__fastcall ***a2)(struct Windows::UI::Composition::IVisual *, GUID *, __int64 **),
        __int64 (__fastcall ***a3)(struct Windows::UI::Composition::IVisual *, GUID *, __int64 **))
{
  __int64 v3; // r15
  int v7; // ecx
  int v8; // eax
  int v9; // ebx
  unsigned int v10; // edx
  int v11; // ecx
  __int64 (__fastcall **v13)(struct Windows::UI::Composition::IVisual *, GUID *, __int64 **); // rax
  volatile signed __int32 *v14; // rdi
  void **i; // rax
  __int64 (__fastcall **v16)(struct Windows::UI::Composition::IVisual *, GUID *, __int64 **); // rax
  __int64 v17; // r9
  __int64 *v18; // rsi
  void **j; // rax
  __int64 v20; // r14
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // r12d
  int v24; // r13d
  __int64 v25; // rax
  DirectComposition::CDevice *v26; // rbx
  _DWORD *v27; // rax
  int v28; // ecx
  __int64 v29; // rcx
  __int64 v30; // rdx
  unsigned int v31; // edx
  int v32; // ecx
  __int64 *v33; // rcx
  __int64 v34; // rax
  __int64 *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rdx
  const wchar_t *v38; // r8
  const wchar_t *v39; // r8
  int v40; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  __int64 *v42; // [rsp+70h] [rbp+40h] BYREF
  void *v43; // [rsp+88h] [rbp+58h] BYREF

  v3 = *((_QWORD *)this - 16);
  if ( *(_DWORD *)(v3 + 92) )
    Microsoft::WRL2::FailFast::Unexpected("ContextSession RIP");
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v3 + 56) + 24LL));
  v7 = *(_DWORD *)(v3 + 64);
  if ( v7 != *(_DWORD *)(v3 + 68) + *(_DWORD *)(v3 + 72) )
    Microsoft::WRL2::FailFast::Unexpected("ContextSession begin counts");
  *(_DWORD *)(v3 + 64) = v7 + 1;
  if ( (*((_BYTE *)this - 104) & 2) == 0 )
  {
    v9 = -2147483629;
    RoOriginateErrorW(
      2147483667LL,
      0,
      L"The given object has already been closed / disposed and may no longer be used.");
    goto LABEL_10;
  }
  if ( !a2 )
  {
    v10 = 90;
    goto LABEL_71;
  }
  if ( !a3 )
  {
    v10 = 91;
LABEL_71:
    v9 = -2147024809;
    v11 = -2147024809;
    goto LABEL_9;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 248LL))(*((_QWORD *)this + 2));
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtvisualcollection.cpp",
      (const char *)(unsigned int)v8,
      v40);
    v10 = 93;
LABEL_8:
    v11 = v9;
LABEL_9:
    DoStackCaptureDirect(v11, v10);
    goto LABEL_10;
  }
  v13 = *a2;
  v42 = 0;
  v9 = (*v13)((struct Windows::UI::Composition::IVisual *)a2, &GUID_7d099463_1e1d_4495_828a_d36bd8ebeeb7, &v42);
  if ( v9 < 0 )
  {
    v33 = v42;
    if ( !v42 )
    {
LABEL_53:
      v10 = 96;
      goto LABEL_8;
    }
    v42 = 0;
    v34 = *v33;
LABEL_63:
    (*(void (**)(void))(v34 + 16))();
    goto LABEL_53;
  }
  v14 = (volatile signed __int32 *)v42;
  for ( i = (void **)v42[1]; ; i = (void **)*i )
  {
    if ( !i )
    {
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 16LL))(v14);
      }
      v9 = -2147467262;
      goto LABEL_53;
    }
    if ( &Windows::UI::Composition::Visual::s_InterfaceType == (_UNKNOWN *)i )
      break;
  }
  v42 = 0;
  if ( (v14[12] & 2) == 0 )
  {
    v38 = L"The given object has already been closed / disposed and may no longer be used.";
    v9 = -2147483629;
LABEL_73:
    RoOriginateErrorW((unsigned int)v9, 0, v38);
    v34 = *(_QWORD *)v14;
    goto LABEL_63;
  }
  if ( !*((_QWORD *)v14 + 3) )
    goto LABEL_79;
  if ( *((_QWORD *)v14 + 3) != v3 )
  {
    v38 = L"The caller is not allowed to perform this operation on this object.";
    v9 = -2147024891;
    goto LABEL_73;
  }
  v16 = *a3;
  v43 = (void *)v14;
  v42 = 0;
  v9 = (*v16)((struct Windows::UI::Composition::IVisual *)a3, &GUID_7d099463_1e1d_4495_828a_d36bd8ebeeb7, &v42);
  if ( v9 < 0 )
  {
    v35 = v42;
    if ( !v42 )
    {
LABEL_57:
      v42 = 0;
      v31 = 99;
      v32 = v9;
LABEL_58:
      DoStackCaptureDirect(v32, v31);
      Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v42);
      Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(&v43);
      goto LABEL_10;
    }
    v42 = 0;
    v36 = *v35;
LABEL_66:
    (*(void (**)(void))(v36 + 16))();
    goto LABEL_57;
  }
  v18 = v42;
  for ( j = (void **)v42[1]; ; j = (void **)*j )
  {
    if ( !j )
    {
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
      }
      v9 = -2147467262;
      goto LABEL_57;
    }
    if ( &Windows::UI::Composition::Visual::s_InterfaceType == (_UNKNOWN *)j )
      break;
  }
  v42 = 0;
  if ( (v18[6] & 2) == 0 )
  {
    v39 = L"The given object has already been closed / disposed and may no longer be used.";
    v9 = -2147483629;
LABEL_75:
    RoOriginateErrorW((unsigned int)v9, 0, v39);
    v36 = *v18;
    goto LABEL_66;
  }
  if ( !v18[3] )
LABEL_79:
    Microsoft::WRL2::FailFast::Unexpected("No session");
  if ( v18[3] != v3 )
  {
    v39 = L"The caller is not allowed to perform this operation on this object.";
    v9 = -2147024891;
    goto LABEL_75;
  }
  v42 = v18;
  if ( *((_QWORD *)v14 + 19) )
  {
    v37 = 1305;
LABEL_69:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v37,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtvisual.cpp",
      (const char *)0x80070057LL,
      v40);
    v31 = 101;
    v32 = -2147024809;
    v9 = -2147024809;
    goto LABEL_58;
  }
  v20 = *((_QWORD *)this + 2);
  if ( v18 && v18[19] != v20 )
  {
    v37 = 1310;
    goto LABEL_69;
  }
  *((_QWORD *)v14 + 19) = v20;
  v21 = *(_QWORD *)(v20 + 160);
  if ( !v21 )
  {
LABEL_49:
    *(_QWORD *)(v20 + 160) = v14;
    goto LABEL_35;
  }
  if ( !v18 )
  {
    *((_QWORD *)v14 + 21) = v21;
    *((_QWORD *)v14 + 22) = *(_QWORD *)(v21 + 176);
    *(_QWORD *)(v21 + 176) = v14;
    goto LABEL_49;
  }
  v22 = v18[21];
  if ( v22 )
  {
    *(_QWORD *)(v22 + 176) = v14;
    *((_QWORD *)v14 + 21) = v18[21];
  }
  else
  {
    *(_QWORD *)(v21 + 176) = v14;
  }
  *((_QWORD *)v14 + 22) = v18;
  v18[21] = (__int64)v14;
LABEL_35:
  if ( _InterlockedIncrement(v14 + 4) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 80LL))(v14);
  if ( v18 )
    v23 = *((_DWORD *)v18 + 36);
  else
    v23 = 0;
  v24 = *(_DWORD *)(v20 + 144);
  if ( v24 )
  {
    LODWORD(v42) = *((_DWORD *)v14 + 36);
    if ( (_DWORD)v42 )
    {
      v25 = *(_QWORD *)(v20 + 24);
      v43 = 0;
      v26 = *(DirectComposition::CDevice **)(v25 + 440);
      DirectComposition::CDevice::BeginKernelCommand(v26, 0x14u, &v43, 0);
      v27 = v43;
      v28 = (int)v42;
      *(_DWORD *)v43 = 20;
      v27[1] = v24;
      v27[2] = v28;
      v27[3] = 1;
      v27[4] = v23;
      v29 = *((_QWORD *)v26 + 11);
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 24LL))(v29);
    }
  }
  LOBYTE(v17) = 1;
  (*(void (__fastcall **)(__int64, volatile signed __int32 *, __int64 *, __int64))(*(_QWORD *)v20 + 280LL))(
    v20,
    v14,
    v18,
    v17);
  v9 = 0;
  if ( v18 && _InterlockedExchangeAdd((volatile signed __int32 *)v18 + 4, 0xFFFFFFFF) == 1 )
  {
    LOBYTE(v30) = 1;
    (*(void (__fastcall **)(__int64 *, __int64))(*v18 + 64))(v18, v30);
  }
  if ( _InterlockedExchangeAdd(v14 + 4, 0xFFFFFFFF) == 1 )
  {
    LOBYTE(v30) = 1;
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v14 + 64LL))(v14, v30);
  }
LABEL_10:
  Microsoft::WRL2::ContextSession::EndApiEntry((Microsoft::WRL2::ContextSession *)v3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180034fe0  mov     [rsp-38h+arg_8], rbx
0x180034fe5  push    rbp
0x180034fe6  push    rsi
0x180034fe7  push    rdi
0x180034fe8  push    r12
0x180034fea  push    r13
0x180034fec  push    r14
0x180034fee  push    r15
0x180034ff0  mov     rbp, rsp
0x180034ff3  sub     rsp, 30h
0x180034ff7  mov     r15, [rcx-80h]
0x180034ffb  xor     r13d, r13d
0x180034ffe  mov     rsi, r8
0x180035001  mov     rdi, rdx
0x180035004  mov     r14, rcx
0x180035007  mov     eax, [r15+5Ch]
0x18003500b  test    eax, eax
0x18003500d  jnz     loc_1800354D8
0x180035013  mov     rcx, [r15+38h]
0x180035017  add     rcx, 18h; lpCriticalSection
0x18003501b  call    cs:__imp_EnterCriticalSection
0x180035021  mov     eax, [r15+48h]
0x180035025  add     eax, [r15+44h]
0x180035029  mov     ecx, [r15+40h]
0x18003502d  cmp     ecx, eax
0x18003502f  jnz     loc_1800354CB
0x180035035  lea     eax, [rcx+1]
0x180035038  mov     [r15+40h], eax
0x18003503c  test    byte ptr [r14-68h], 2
0x180035041  jz      loc_1800353E9
0x180035047  test    rdi, rdi
0x18003504a  jz      loc_1800354E5
0x180035050  test    rsi, rsi
0x180035053  jz      loc_18003542F
0x180035059  mov     rcx, [r14+10h]
0x18003505d  mov     rax, [rcx]
0x180035060  mov     rax, [rax+0F8h]
0x180035067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003506c  mov     ebx, eax
0x18003506e  test    eax, eax
0x180035070  jns     short loc_1800350B3
0x180035072  mov     rcx, [rbp+38h]; this
0x180035076  lea     r8, aOnecoreuapWind_133; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18003507d  mov     r9d, eax; char *
0x180035080  lea     edx, [r13+45h]; void *
0x180035084  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035089  lea     edx, [r13+5Dh]; unsigned int
0x18003508d  mov     ecx, ebx; int
0x18003508f  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180035094  mov     rcx, r15; this
0x180035097  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x18003509c  mov     eax, ebx
0x18003509e  mov     rbx, [rsp+30h+arg_8]
0x1800350a3  add     rsp, 30h
0x1800350a7  pop     r15
0x1800350a9  pop     r14
0x1800350ab  pop     r13
0x1800350ad  pop     r12
0x1800350af  pop     rdi
0x1800350b0  pop     rsi
0x1800350b1  pop     rbp
0x1800350b2  retn
0x1800350b3  mov     rax, [rdi]
0x1800350b6  lea     r8, [rbp+arg_0]
0x1800350ba  lea     rdx, _GUID_7d099463_1e1d_4495_828a_d36bd8ebeeb7
0x1800350c1  mov     [rbp+arg_0], r13
0x1800350c5  mov     rcx, rdi
0x1800350c8  mov     rax, [rax]
0x1800350cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350d0  mov     ebx, eax
0x1800350d2  test    eax, eax
0x1800350d4  js      loc_1800353B3
0x1800350da  mov     rdi, [rbp+arg_0]
0x1800350de  lea     rcx, ?s_InterfaceType@Visual@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; Microsoft::WRL2::NestableRuntimeClass::InterfaceType const Windows::UI::Composition::Visual::s_InterfaceType
0x1800350e5  mov     rax, [rdi+8]
0x1800350e9  test    rax, rax
0x1800350ec  jz      loc_180035334
0x1800350f2  cmp     rcx, rax
0x1800350f5  jz      short loc_1800350FC
0x1800350f7  mov     rax, [rax]
0x1800350fa  jmp     short loc_1800350E9
0x1800350fc  mov     [rbp+arg_0], r13
0x180035100  test    byte ptr [rdi+30h], 2
0x180035104  jz      loc_180035442
0x18003510a  cmp     [rdi+18h], r13
0x18003510e  jz      loc_1800354AA
0x180035114  cmp     [rdi+18h], r15
0x180035118  jnz     loc_180035484
0x18003511e  mov     rax, [rsi]
0x180035121  lea     r8, [rbp+arg_0]
0x180035125  lea     rdx, _GUID_7d099463_1e1d_4495_828a_d36bd8ebeeb7
0x18003512c  mov     [rbp+arg_18], rdi
0x180035130  mov     rcx, rsi
0x180035133  mov     [rbp+arg_0], r13
0x180035137  mov     rax, [rax]
0x18003513a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003513f  mov     ebx, eax
0x180035141  test    eax, eax
0x180035143  js      loc_1800353CE
0x180035149  mov     rsi, [rbp+arg_0]
0x18003514d  lea     rcx, ?s_InterfaceType@Visual@Composition@UI@Windows@@2UInterfaceType@NestableRuntimeClass@WRL2@Microsoft@@B; Microsoft::WRL2::NestableRuntimeClass::InterfaceType const Windows::UI::Composition::Visual::s_InterfaceType
0x180035154  mov     rax, [rsi+8]
0x180035158  test    rax, rax
0x18003515b  jz      loc_18003535B
0x180035161  cmp     rcx, rax
0x180035164  jz      short loc_18003516B
0x180035166  mov     rax, [rax]
0x180035169  jmp     short loc_180035158
0x18003516b  mov     [rbp+arg_0], r13
0x18003516f  test    byte ptr [rsi+30h], 2
0x180035173  jz      loc_180035463
0x180035179  cmp     [rsi+18h], r13
0x18003517d  jz      loc_1800354AA
0x180035183  cmp     [rsi+18h], r15
0x180035187  jnz     loc_180035492
0x18003518d  mov     [rbp+arg_0], rsi
0x180035191  cmp     [rdi+98h], r13
0x180035198  jnz     loc_180035404
0x18003519e  mov     r14, [r14+10h]
0x1800351a2  test    rsi, rsi
0x1800351a5  jz      short loc_1800351B4
0x1800351a7  cmp     [rsi+98h], r14
0x1800351ae  jnz     loc_1800354A0
0x1800351b4  mov     [rdi+98h], r14
0x1800351bb  mov     rcx, [r14+0A0h]
0x1800351c2  test    rcx, rcx
0x1800351c5  jz      loc_180035328
0x1800351cb  test    rsi, rsi
0x1800351ce  jz      loc_18003530C
0x1800351d4  mov     rax, [rsi+0A8h]
0x1800351db  test    rax, rax
0x1800351de  jz      loc_1800353A7
0x1800351e4  mov     [rax+0B0h], rdi
0x1800351eb  mov     rax, [rsi+0A8h]
0x1800351f2  mov     [rdi+0A8h], rax
0x1800351f9  mov     [rdi+0B0h], rsi
0x180035200  mov     [rsi+0A8h], rdi
0x180035207  mov     eax, 1
0x18003520c  lock xadd [rdi+10h], eax
0x180035211  inc     eax
0x180035213  cmp     eax, 1
0x180035216  jz      loc_1800354B7
0x18003521c  test    rsi, rsi
0x18003521f  jz      loc_18003539F
0x180035225  mov     r12d, [rsi+90h]
0x18003522c  mov     r13d, [r14+90h]
0x180035233  test    r13d, r13d
0x180035236  jz      short loc_180035293
0x180035238  mov     eax, [rdi+90h]
0x18003523e  mov     dword ptr [rbp+arg_0], eax
0x180035241  test    eax, eax
0x180035243  jz      short loc_180035293
0x180035245  mov     rax, [r14+18h]
0x180035249  lea     r8, [rbp+arg_18]; void **
0x18003524d  xor     r9d, r9d; bool
0x180035250  mov     [rbp+arg_18], 0
0x180035258  mov     rbx, [rax+1B8h]
0x18003525f  mov     rcx, rbx; this
0x180035262  lea     edx, [r9+14h]; unsigned int
0x180035266  call    ?BeginKernelCommand@CDevice@DirectComposition@@AEAAXIPEAPEAX_N@Z; DirectComposition::CDevice::BeginKernelCommand(uint,void * *,bool)
0x18003526b  mov     rax, [rbp+arg_18]
0x18003526f  mov     ecx, dword ptr [rbp+arg_0]
0x180035272  mov     dword ptr [rax], 14h
0x180035278  mov     [rax+4], r13d
0x18003527c  mov     [rax+8], ecx
0x18003527f  mov     dword ptr [rax+0Ch], 1
0x180035286  mov     [rax+10h], r12d
0x18003528a  mov     rcx, [rbx+58h]
0x18003528e  test    rcx, rcx
0x180035291  jnz     short loc_1800352FE
0x180035293  mov     rax, [r14]
0x180035296  mov     r9b, 1
0x180035299  mov     r8, rsi
0x18003529c  mov     rdx, rdi
0x18003529f  mov     rcx, r14
0x1800352a2  mov     rax, [rax+118h]
0x1800352a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800352ae  xor     ebx, ebx
0x1800352b0  or      r14d, 0FFFFFFFFh
0x1800352b4  test    rsi, rsi
0x1800352b7  jz      short loc_1800352D7
0x1800352b9  mov     eax, r14d
0x1800352bc  lock xadd [rsi+10h], eax
0x1800352c1  add     eax, r14d
0x1800352c4  jnz     short loc_1800352D7
0x1800352c6  mov     rax, [rsi]
0x1800352c9  mov     dl, 1
0x1800352cb  mov     rcx, rsi
0x1800352ce  mov     rax, [rax+40h]
0x1800352d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800352d7  mov     eax, r14d
0x1800352da  lock xadd [rdi+10h], eax
0x1800352df  add     eax, r14d
0x1800352e2  jnz     loc_180035094
0x1800352e8  mov     rax, [rdi]
0x1800352eb  mov     dl, 1
0x1800352ed  mov     rcx, rdi
0x1800352f0  mov     rax, [rax+40h]
0x1800352f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800352f9  jmp     loc_180035094
0x1800352fe  mov     rax, [rcx]
0x180035301  mov     rax, [rax+18h]
0x180035305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003530a  jmp     short loc_180035293
0x18003530c  mov     [rdi+0A8h], rcx
0x180035313  mov     rax, [rcx+0B0h]
0x18003531a  mov     [rdi+0B0h], rax
0x180035321  mov     [rcx+0B0h], rdi
0x180035328  mov     [r14+0A0h], rdi
0x18003532f  jmp     loc_180035207
0x180035334  test    rdi, rdi
0x180035337  jz      short loc_18003534C
0x180035339  mov     [rbp+arg_0], r13
0x18003533d  mov     rcx, rdi
0x180035340  mov     rax, [rdi]
0x180035343  mov     rax, [rax+10h]
0x180035347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003534c  mov     ebx, 80004002h
0x180035351  mov     edx, 60h ; '`'
0x180035356  jmp     loc_18003508D
0x18003535b  test    rsi, rsi
0x18003535e  jz      short loc_180035373
0x180035360  mov     [rbp+arg_0], r13
0x180035364  mov     rcx, rsi
0x180035367  mov     rax, [rsi]
0x18003536a  mov     rax, [rax+10h]
0x18003536e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035373  mov     ebx, 80004002h
0x180035378  mov     [rbp+arg_0], r13
0x18003537c  mov     edx, 63h ; 'c'; unsigned int
0x180035381  mov     ecx, ebx; int
0x180035383  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180035388  lea     rcx, [rbp+arg_0]; void *
0x18003538c  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x180035391  lea     rcx, [rbp+arg_18]; void *
0x180035395  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18003539a  jmp     loc_180035094
0x18003539f  mov     r12d, r13d
0x1800353a2  jmp     loc_18003522C
0x1800353a7  mov     [rcx+0B0h], rdi
0x1800353ae  jmp     loc_1800351F9
0x1800353b3  mov     rcx, [rbp+arg_0]
0x1800353b7  test    rcx, rcx
0x1800353ba  jz      short loc_180035351
0x1800353bc  mov     [rbp+arg_0], r13
0x1800353c0  mov     rax, [rcx]
0x1800353c3  mov     rax, [rax+10h]
0x1800353c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800353cc  jmp     short loc_180035351
0x1800353ce  mov     rcx, [rbp+arg_0]
0x1800353d2  test    rcx, rcx
0x1800353d5  jz      short loc_180035378
0x1800353d7  mov     [rbp+arg_0], r13
0x1800353db  mov     rax, [rcx]
0x1800353de  mov     rax, [rax+10h]
0x1800353e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800353e7  jmp     short loc_180035378
0x1800353e9  mov     ebx, 80000013h
0x1800353ee  lea     r8, aTheGivenObject; "The given object has already been close"...
0x1800353f5  mov     ecx, ebx
0x1800353f7  xor     edx, edx
0x1800353f9  call    cs:__imp_RoOriginateErrorW
0x1800353ff  jmp     loc_180035094
0x180035404  mov     edx, 519h; void *
0x180035409  mov     rcx, [rbp+38h]; this
0x18003540d  lea     r8, aOnecoreuapWind_187; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180035414  mov     edi, 80070057h
0x180035419  mov     r9d, edi; char *
0x18003541c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035421  mov     edx, 65h ; 'e'
0x180035426  mov     ecx, edi
0x180035428  mov     ebx, edi
0x18003542a  jmp     loc_180035383
0x18003542f  mov     edx, 5Bh ; '['
0x180035434  mov     edi, 80070057h
0x180035439  mov     ebx, edi
0x18003543b  mov     ecx, edi
0x18003543d  jmp     loc_18003508F
0x180035442  lea     r8, aTheGivenObject; "The given object has already been close"...
0x180035449  mov     ebx, 80000013h
0x18003544e  xor     edx, edx
0x180035450  mov     ecx, ebx
0x180035452  call    cs:__imp_RoOriginateErrorW
0x180035458  mov     rax, [rdi]
0x18003545b  mov     rcx, rdi
0x18003545e  jmp     loc_1800353C3
0x180035463  lea     r8, aTheGivenObject; "The given object has already been close"...
0x18003546a  mov     ebx, 80000013h
0x18003546f  xor     edx, edx
0x180035471  mov     ecx, ebx
0x180035473  call    cs:__imp_RoOriginateErrorW
0x180035479  mov     rax, [rsi]
0x18003547c  mov     rcx, rsi
0x18003547f  jmp     loc_1800353DE
0x180035484  lea     r8, aTheCallerIsNot; "The caller is not allowed to perform th"...
0x18003548b  mov     ebx, 80070005h
0x180035490  jmp     short loc_18003544E
0x180035492  lea     r8, aTheCallerIsNot; "The caller is not allowed to perform th"...
0x180035499  mov     ebx, 80070005h
0x18003549e  jmp     short loc_18003546F
  ... truncated ...
```
