# Windows::UI::Composition::ProxyObject::RuntimeClassInitialize(Windows::UI::Composition::Compositor *,uint,bool)

- ea: `0x180015490`
- end: `0x180015a62`
- name: `?RuntimeClassInitialize@ProxyObject@Composition@UI@Windows@@IEAAJPEAVCompositor@234@I_N@Z`
- size: `1490`
- prototype: `__int64 __fastcall(Windows::UI::Composition::ProxyObject *__hidden this, struct Windows::UI::Composition::Compositor *, unsigned int, bool)`
- caller_count: `69`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000dff0`
- `0x18000e4b0`
- `0x18002a700`
- `0x18002fa28`
- `0x1800340b0`
- `0x180034190`
- `0x180038610`
- `0x1800452a4`
- `0x180045714`
- `0x180045d68`
- `0x180046160`
- `0x1800462d8`
- `0x1800463e8`
- `0x180046e0c`
- `0x180048ec8`
- `0x1800490a0`
- `0x1800493a8`
- `0x180049a3c`
- `0x180049d40`
- `0x18004a8c4`
- `0x180050b5c`
- `0x180051144`
- `0x18005210c`
- `0x18005245c`
- `0x18005293c`
- `0x1800564ac`
- `0x18005faa4`
- `0x180072170`
- `0x18007beb4`
- `0x18007c528`
- `0x18008e2e0`
- `0x1800a3854`
- `0x1800a3f5c`
- `0x1800a5d00`
- `0x1800adcf0`
- `0x1800ae720`
- `0x1800b3da8`
- `0x1800b72f8`
- `0x1800b8984`
- `0x1800bee0c`
- `0x1800c2880`
- `0x1800ceeb4`
- `0x1800dbe58`
- `0x1800df1fc`
- `0x1800e6960`
- `0x1800e9854`
- `0x1800ea0a8`
- `0x1800eb2b4`
- `0x1800f24ac`
- `0x1800f4828`

## callees

- `0x18000b53c`
- `0x180012da0`
- `0x180013528`
- `0x18001358c`
- `0x180015490`
- `0x180015ed0`
- `0x180017f4c`
- `0x18001ff20`
- `0x180021140`
- `0x180036f90`
- `0x18003ced8`
- `0x18006c5b0`
- `0x180095e10`
- `0x1800aaf34`
- `0x1800e8210`
- `0x1800ea11c`
- `0x1800f6f10`
- `0x180107230`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800154fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800154fb`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x180015a0a`
- `api-ms-win-core-errorhandling-l1-1-3!TerminateProcessOnMemoryExhaustion` at `0x180015a0a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180015543`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180015543`

## string_xrefs

- `0x180015535`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180015672`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionobject.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::ProxyObject::RuntimeClassInitialize(
        Windows::UI::Composition::ProxyObject *this,
        struct Windows::UI::Composition::Compositor *a2,
        int a3,
        char a4)
{
  Microsoft::WRL2::ContextSession *v7; // rbx
  int v8; // esi
  struct Windows::UI::Composition::Compositor **v9; // rdx
  char v10; // cl
  int v11; // eax
  int v12; // esi
  char v13; // al
  bool v14; // zf
  int v15; // eax
  __int64 v16; // r15
  unsigned int v17; // eax
  __int64 *v18; // rbx
  unsigned int v19; // ecx
  __int64 v20; // r14
  __int64 v21; // rax
  _DWORD *v22; // rdx
  int v23; // r8d
  unsigned int v24; // edx
  int v26; // r14d
  _DWORD *v27; // rax
  int v28; // r12d
  __int64 v29; // rcx
  __int64 v30; // rdx
  void *v31; // rcx
  __int64 v32; // rcx
  unsigned __int64 v33; // rcx
  __int64 v34; // rax
  int v35; // r14d
  __int64 v36; // rax
  int v37; // ebx
  DirectComposition::CDevice *v38; // rsi
  _DWORD *v39; // rax
  __int64 v40; // rcx
  _DWORD *v41; // r8
  int v42; // [rsp+20h] [rbp-B9h]
  _BYTE v43[8]; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v44; // [rsp+38h] [rbp-A1h] BYREF
  void *v45; // [rsp+40h] [rbp-99h] BYREF
  int v46; // [rsp+48h] [rbp-91h] BYREF
  int v47; // [rsp+50h] [rbp-89h] BYREF
  int v48; // [rsp+58h] [rbp-81h] BYREF
  unsigned __int64 v49; // [rsp+60h] [rbp-79h] BYREF
  _QWORD v50[17]; // [rsp+68h] [rbp-71h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v43[0] = a4;
  v46 = a3;
  *((_QWORD *)this + 3) = a2;
  if ( a2 != this )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)a2 + 4) == 1 )
      (*(void (__fastcall **)(struct Windows::UI::Composition::Compositor *))(*(_QWORD *)a2 + 80LL))(a2);
    v7 = 0;
    v8 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 56LL) + 40LL);
    if ( v8 == GetCurrentThreadId()
      || (Microsoft::WRL2::ContextSession::BeginApiEntry(*((Microsoft::WRL2::ContextSession **)a2 + 3)),
          v7 = (Microsoft::WRL2::ContextSession *)*((_QWORD *)a2 + 3),
          (*((_BYTE *)a2 + 48) & 2) != 0) )
    {
      v9 = (struct Windows::UI::Composition::Compositor **)*((_QWORD *)a2 + 5);
      if ( *v9 != (struct Windows::UI::Composition::Compositor *)((char *)a2 + 32) )
        __fastfail(3u);
      *((_QWORD *)this + 4) = (char *)a2 + 32;
      *((_QWORD *)this + 5) = v9;
      *v9 = (Windows::UI::Composition::ProxyObject *)((char *)this + 32);
      *((_QWORD *)a2 + 5) = (char *)this + 32;
      if ( v7 )
        Microsoft::WRL2::ContextSession::EndApiEntry(v7);
    }
    else
    {
      Microsoft::WRL2::ContextSession::EndApiEntry(*((Microsoft::WRL2::ContextSession **)a2 + 3));
      RoOriginateErrorW(
        2147483667LL,
        0,
        L"The given object has already been closed / disposed and may no longer be used.");
    }
  }
  v10 = *((_BYTE *)this + 49);
  *((_BYTE *)this + 48) = 31;
  *((_BYTE *)this + 49) ^= (*((_BYTE *)a2 + 49) ^ v10) & 1;
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, Windows::UI::Composition::ProxyObject *, char *))(**(_QWORD **)(*((_QWORD *)a2 + 51) + 32LL) + 24LL))(
          *(_QWORD *)(*((_QWORD *)a2 + 51) + 32LL),
          *(unsigned int *)(*((_QWORD *)a2 + 51) + 64LL),
          this,
          (char *)this + 136);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionobject.cpp",
      (const char *)(unsigned int)v11,
      v42);
    v24 = 55;
LABEL_22:
    DoStackCaptureDirect(v12, v24);
    Microsoft::WRL2::ContextRuntimeClass::Dispose(this);
    return (unsigned int)v12;
  }
  v13 = *((_BYTE *)a2 + 436);
  if ( (v13 & 1) == 0 )
  {
    v14 = *((_DWORD *)a2 + 108) == 0;
    *((_BYTE *)a2 + 436) = v13 | 1;
    if ( v14 )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a2 + 52) + 48LL))(*((_QWORD *)a2 + 52), 1);
      if ( v15 < 0 )
        Microsoft::WRL2::FailFast::ForHR(v15, retaddr);
    }
  }
  *((_DWORD *)this + 35) |= 1u;
  v16 = *(_QWORD *)(*((_QWORD *)this + 3) + 440LL);
  v17 = *(_DWORD *)(v16 + 368);
  v18 = (__int64 *)(v16 + 208);
  if ( v17 == -1 )
  {
    v12 = -2147024882;
    goto LABEL_45;
  }
  v19 = *(_DWORD *)(v16 + 232);
  if ( v17 >> 5 >= v19 )
  {
    LODWORD(v20) = *(_DWORD *)(v16 + 232);
    v44 = 0;
    v12 = DynArray<unsigned int,1>::AddMultipleAndSet(v16 + 208, &v44);
    if ( v12 >= 0 )
      goto LABEL_19;
LABEL_45:
    v24 = 64;
    goto LABEL_22;
  }
  v20 = *(unsigned int *)(v16 + 372);
  if ( *(_DWORD *)(*v18 + 4 * v20) == -1 )
  {
    do
      LODWORD(v20) = ((int)v20 + 1) % v19;
    while ( *(_DWORD *)(*v18 + 4LL * (unsigned int)v20) == -1 );
  }
  *(_DWORD *)(v16 + 372) = v20;
LABEL_19:
  v21 = *v18;
  LODWORD(v45) = 0;
  v22 = (_DWORD *)(v21 + 4LL * (unsigned int)v20);
  v14 = !_BitScanForward((unsigned int *)&v23, ~*v22);
  if ( v14 )
    Microsoft::WRL2::FailFast::Do();
  *v22 |= *v22 + 1;
  v26 = v23 + 32 * v20 + 1;
  ++*(_DWORD *)(v16 + 368);
  v45 = 0;
  DirectComposition::CDevice::BeginKernelCommand((DirectComposition::CDevice *)v16, 0x10u, &v45, 0);
  v27 = v45;
  *(_DWORD *)v45 = 2;
  v27[1] = v26;
  v27[2] = a3;
  v28 = v43[0];
  v27[3] = v43[0];
  if ( !*(_QWORD *)(v16 + 88) )
  {
    DirectComposition::CDeviceLock::AssertIsOwned((DirectComposition::CDeviceLock *)(v16 + 104));
    v29 = *(_QWORD *)(v16 + 168);
    v30 = (unsigned int)(*(_DWORD *)(v16 + 184) - *(_DWORD *)(v16 + 188));
    v44 = 0;
    v43[0] = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, _BYTE *))(*(_QWORD *)v29 + 16LL))(
            v29,
            v30,
            &v44,
            v43);
    if ( v44 != *(_DWORD *)(v16 + 192) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SeparateOOMDCompKBatchFailures>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SeparateOOMDCompKBatchFailures>::GetImpl'::`2'::impl)
        && IsOOM(v12) )
      {
        TerminateProcessOnMemoryExhaustion(0);
      }
      DirectComposition::CDevice::FailFastForKernelBatchFailure((DirectComposition::CDevice *)v16, v44);
    }
    v31 = *(void **)(v16 + 200);
    if ( v31 )
    {
      operator delete(v31);
      *(_QWORD *)(v16 + 200) = 0;
    }
    v14 = v43[0] == 0;
    *(_QWORD *)(v16 + 188) = *(unsigned int *)(v16 + 184);
    if ( !v14 )
      DirectComposition::CDevice::CheckForDelayedDestructionObjects((DirectComposition::CDevice *)v16);
    if ( v12 < 0 )
    {
      v41 = (_DWORD *)(*v18 + 4 * ((unsigned __int64)(unsigned int)(v26 - 1) >> 5));
      *v41 &= ~(1 << (v26 - 1));
      --*(_DWORD *)(v16 + 368);
      goto LABEL_45;
    }
  }
  *((_DWORD *)this + 36) = v26;
  if ( (Microsoft_Windows_DirectCompositionEnableBits & 1) != 0 )
  {
    v32 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 440LL) + 168LL);
    v33 = ((unsigned __int64)(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32) << 32)
        | *((unsigned int *)this + 36);
    v47 = *((_DWORD *)this + 36);
    v34 = *((_QWORD *)this + 3);
    v49 = v33 | 0x8000000000000000uLL;
    v44 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v34 + 440) + 168LL) + 8LL))(*(_QWORD *)(*(_QWORD *)(v34 + 440) + 168LL));
    v50[0] = this;
    v50[3] = &v44;
    v50[5] = &v47;
    v50[7] = &v49;
    v50[9] = &v46;
    v50[11] = &v48;
    v50[13] = &v45;
    v50[15] = v50;
    LODWORD(v45) = 0;
    v48 = v28;
    v50[4] = 4;
    v50[6] = 4;
    v50[8] = 8;
    v50[10] = 4;
    v50[12] = 4;
    v50[14] = 4;
    v50[16] = 8;
    McGenEventWrite_EventWriteTransfer(0, DCOMPEVENT_RESOURCE_CREATION);
  }
  if ( (*(unsigned __int8 (__fastcall **)(Windows::UI::Composition::ProxyObject *))(*(_QWORD *)this + 104LL))(this) )
  {
    v35 = *((_DWORD *)this + 36);
    if ( v35 )
    {
      v36 = *((_QWORD *)this + 3);
      v37 = *((_DWORD *)this + 34);
      v45 = 0;
      v38 = *(DirectComposition::CDevice **)(v36 + 440);
      DirectComposition::CDevice::BeginKernelCommand(v38, 0xCu, &v45, 0);
      v39 = v45;
      *(_DWORD *)v45 = 10;
      v39[1] = v35;
      v39[2] = v37;
      v40 = *((_QWORD *)v38 + 11);
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 24LL))(v40);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180015490  push    rbp
0x180015492  push    rbx
0x180015493  push    rsi
0x180015494  push    rdi
0x180015495  push    r12
0x180015497  push    r13
0x180015499  push    r14
0x18001549b  lea     rbp, [rsp-27h]
0x1800154a0  sub     rsp, 100h
0x1800154a7  mov     rax, cs:__security_cookie
0x1800154ae  xor     rax, rsp
0x1800154b1  mov     [rbp+57h+var_40], rax
0x1800154b5  mov     [rsp+130h+var_100], r9b
0x1800154ba  mov     r12d, r8d
0x1800154bd  mov     [rsp+130h+var_E8], r8d
0x1800154c2  mov     r14, rdx
0x1800154c5  mov     [rcx+18h], rdx
0x1800154c9  mov     rdi, rcx
0x1800154cc  mov     r13d, 1
0x1800154d2  cmp     rdx, rcx
0x1800154d5  jz      loc_180015567
0x1800154db  mov     eax, r13d
0x1800154de  lock xadd [rdx+10h], eax
0x1800154e3  inc     eax
0x1800154e5  cmp     eax, r13d
0x1800154e8  jz      loc_1800159A9
0x1800154ee  mov     rax, [r14+18h]
0x1800154f2  xor     ebx, ebx
0x1800154f4  mov     rcx, [rax+38h]
0x1800154f8  mov     esi, [rcx+28h]
0x1800154fb  call    cs:__imp_GetCurrentThreadId
0x180015501  cmp     esi, eax
0x180015503  jnz     short loc_180015519
0x180015505  mov     rdx, [r14+28h]
0x180015509  lea     rcx, [r14+20h]
0x18001550d  cmp     [rdx], rcx
0x180015510  jz      short loc_18001554B
0x180015512  mov     ecx, 3
0x180015517  int     29h; Win8: RtlFailFast(ecx)
0x180015519  mov     rcx, [r14+18h]; this
0x18001551d  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x180015522  test    byte ptr [r14+30h], 2
0x180015527  mov     rbx, [r14+18h]
0x18001552b  jnz     short loc_180015505
0x18001552d  mov     rcx, rbx; this
0x180015530  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x180015535  lea     r8, aTheGivenObject; "The given object has already been close"...
0x18001553c  xor     edx, edx
0x18001553e  mov     ecx, 80000013h
0x180015543  call    cs:__imp_RoOriginateErrorW
0x180015549  jmp     short loc_180015567
0x18001554b  mov     [rdi+20h], rcx
0x18001554f  lea     rax, [rdi+20h]
0x180015553  mov     [rax+8], rdx
0x180015557  mov     [rdx], rax
0x18001555a  mov     [rcx+8], rax
0x18001555e  test    rbx, rbx
0x180015561  jnz     loc_1800159BD
0x180015567  movzx   ecx, byte ptr [rdi+31h]
0x18001556b  lea     r9, [rdi+88h]
0x180015572  mov     byte ptr [rdi+30h], 1Fh
0x180015576  mov     r8, rdi
0x180015579  xor     cl, [r14+31h]
0x18001557d  and     cl, r13b
0x180015580  mov     [rsp+130h+arg_10], r15
0x180015588  xor     [rdi+31h], cl
0x18001558b  mov     rdx, [r14+198h]
0x180015592  mov     rcx, [rdx+20h]
0x180015596  mov     edx, [rdx+40h]
0x180015599  mov     rax, [rcx]
0x18001559c  mov     rax, [rax+18h]
0x1800155a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155a5  mov     esi, eax
0x1800155a7  test    eax, eax
0x1800155a9  js      loc_18001566E
0x1800155af  movzx   eax, byte ptr [r14+1B4h]
0x1800155b7  test    r13b, al
0x1800155ba  jnz     short loc_1800155EF
0x1800155bc  or      al, r13b
0x1800155bf  cmp     dword ptr [r14+1B0h], 0
0x1800155c7  mov     [r14+1B4h], al
0x1800155ce  jnz     short loc_1800155EF
0x1800155d0  mov     rcx, [r14+1A0h]
0x1800155d7  movzx   edx, r13b
0x1800155db  mov     rax, [rcx]
0x1800155de  mov     rax, [rax+30h]
0x1800155e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155e7  test    eax, eax
0x1800155e9  js      loc_1800159CA
0x1800155ef  or      [rdi+8Ch], r13d
0x1800155f6  mov     rax, [rdi+18h]
0x1800155fa  mov     r15, [rax+1B8h]
0x180015601  mov     eax, [r15+170h]
0x180015608  lea     rbx, [r15+0D0h]
0x18001560f  cmp     eax, 0FFFFFFFFh
0x180015612  jz      loc_1800159D6
0x180015618  mov     ecx, [rbx+18h]
0x18001561b  shr     eax, 5
0x18001561e  cmp     eax, ecx
0x180015620  jnb     loc_180015983
0x180015626  mov     r14d, [rbx+0A4h]
0x18001562d  xor     r9d, r9d
0x180015630  mov     r8, [rbx]
0x180015633  mov     esi, r9d
0x180015636  cmp     dword ptr [r8+r14*4], 0FFFFFFFFh
0x18001563b  jz      loc_1800156E0
0x180015641  mov     [rbx+0A4h], r14d
0x180015648  mov     rax, [rbx]
0x18001564b  mov     ecx, r14d
0x18001564e  mov     dword ptr [rsp+130h+var_F0], r9d
0x180015653  lea     rdx, [rax+rcx*4]
0x180015657  mov     ecx, [rax+rcx*4]
0x18001565a  mov     eax, ecx
0x18001565c  not     eax
0x18001565e  bsf     r8d, eax
0x180015662  jnz     loc_1800156F7
0x180015668  call    ?Do@FailFast@WRL2@Microsoft@@SAXXZ; Microsoft::WRL2::FailFast::Do(void)
0x18001566e  mov     rcx, [rbp+5Fh]; this
0x180015672  lea     r8, aOnecoreuapWind_78; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180015679  mov     r9d, esi; char *
0x18001567c  mov     edx, 55h ; 'U'; void *
0x180015681  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015686  mov     edx, 37h ; '7'; unsigned int
0x18001568b  mov     ecx, esi; int
0x18001568d  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180015692  mov     rcx, rdi; this
0x180015695  call    ?Dispose@ContextRuntimeClass@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextRuntimeClass::Dispose(void)
0x18001569a  jmp     short loc_1800156AA
0x18001569c  mov     rax, [rcx]
0x18001569f  mov     rax, [rax+18h]
0x1800156a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156a8  xor     esi, esi
0x1800156aa  mov     r15, [rsp+130h+arg_10]
0x1800156b2  mov     eax, esi
0x1800156b4  mov     rcx, [rbp+57h+var_40]
0x1800156b8  xor     rcx, rsp; StackCookie
0x1800156bb  call    __security_check_cookie
0x1800156c0  add     rsp, 100h
0x1800156c7  pop     r14
0x1800156c9  pop     r13
0x1800156cb  pop     r12
0x1800156cd  pop     rdi
0x1800156ce  pop     rsi
0x1800156cf  pop     rbx
0x1800156d0  pop     rbp
0x1800156d1  retn
0x1800156e0  lea     eax, [r14+1]
0x1800156e4  xor     edx, edx
0x1800156e6  div     ecx
0x1800156e8  mov     r14d, edx
0x1800156eb  cmp     dword ptr [r8+rdx*4], 0FFFFFFFFh
0x1800156f0  jz      short loc_1800156E0
0x1800156f2  jmp     loc_180015641
0x1800156f7  shl     r14d, 5
0x1800156fb  lea     eax, [rcx+1]
0x1800156fe  or      eax, ecx
0x180015700  inc     r14d
0x180015703  mov     [rdx], eax
0x180015705  add     r14d, r8d
0x180015708  inc     dword ptr [rbx+0A0h]
0x18001570e  test    esi, esi
0x180015710  js      loc_1800159DB
0x180015716  mov     [rsp+130h+var_F0], r9
0x18001571b  lea     r8, [rsp+130h+var_F0]; void **
0x180015720  xor     r9d, r9d; bool
0x180015723  mov     edx, 10h; unsigned int
0x180015728  mov     rcx, r15; this
0x18001572b  call    ?BeginKernelCommand@CDevice@DirectComposition@@AEAAXIPEAPEAX_N@Z; DirectComposition::CDevice::BeginKernelCommand(uint,void * *,bool)
0x180015730  mov     rax, [rsp+130h+var_F0]
0x180015735  mov     dword ptr [rax], 2
0x18001573b  mov     [rax+4], r14d
0x18001573f  mov     [rax+8], r12d
0x180015743  movzx   r12d, [rsp+130h+var_100]
0x180015749  mov     [rax+0Ch], r12d
0x18001574d  cmp     qword ptr [r15+58h], 0
0x180015752  jnz     loc_1800157E8
0x180015758  lea     rcx, [r15+68h]; this
0x18001575c  call    ?AssertIsOwned@CDeviceLock@DirectComposition@@QEBAXXZ; DirectComposition::CDeviceLock::AssertIsOwned(void)
0x180015761  mov     rcx, [r15+0A8h]
0x180015768  lea     r9, [rsp+130h+var_100]
0x18001576d  mov     edx, [r15+0B8h]
0x180015774  lea     r8, [rsp+130h+var_F8]
0x180015779  sub     edx, [r15+0BCh]
0x180015780  mov     [rsp+130h+var_F8], 0
0x180015788  mov     [rsp+130h+var_100], 0
0x18001578d  mov     rax, [rcx]
0x180015790  mov     rax, [rax+10h]
0x180015794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015799  mov     esi, eax
0x18001579b  mov     eax, [r15+0C0h]
0x1800157a2  cmp     [rsp+130h+var_F8], eax
0x1800157a6  jnz     loc_1800159E5
0x1800157ac  mov     rcx, [r15+0C8h]; lpMem
0x1800157b3  test    rcx, rcx
0x1800157b6  jnz     loc_180015A16
0x1800157bc  cmp     [rsp+130h+var_100], 0
0x1800157c1  mov     eax, [r15+0B8h]
0x1800157c8  mov     [r15+0BCh], eax
0x1800157cf  mov     dword ptr [r15+0C0h], 0
0x1800157da  jnz     loc_180015A2B
0x1800157e0  test    esi, esi
0x1800157e2  js      loc_180015A38
0x1800157e8  mov     [rdi+90h], r14d
0x1800157ef  test    byte ptr cs:Microsoft_Windows_DirectCompositionEnableBits, r13b
0x1800157f6  jz      loc_180015909
0x1800157fc  mov     rax, [rdi+18h]
0x180015800  mov     rcx, [rax+1B8h]
0x180015807  mov     rcx, [rcx+0A8h]
0x18001580e  mov     rax, [rcx]
0x180015811  mov     rax, [rax+8]
0x180015815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001581a  mov     edx, [rdi+90h]
0x180015820  mov     eax, eax
0x180015822  mov     ecx, edx
0x180015824  shl     rax, 20h
0x180015828  or      rcx, rax
0x18001582b  mov     [rsp+130h+var_E0], edx
0x18001582f  mov     rax, 8000000000000000h
0x180015839  or      rcx, rax
0x18001583c  mov     rax, [rdi+18h]
0x180015840  mov     [rbp+57h+var_D0], rcx
0x180015844  mov     rcx, [rax+1B8h]
0x18001584b  mov     rcx, [rcx+0A8h]
0x180015852  mov     rax, [rcx]
0x180015855  mov     rax, [rax+8]
0x180015859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001585e  mov     [rsp+130h+var_F8], eax
0x180015862  lea     rdx, DCOMPEVENT_RESOURCE_CREATION
0x180015869  mov     eax, [rsp+130h+var_E8]
0x18001586d  xor     ecx, ecx
0x18001586f  mov     [rsp+130h+var_E8], eax
0x180015873  mov     r9d, 8
0x180015879  lea     rax, [rsp+130h+var_F8]
0x18001587e  mov     [rbp+57h+var_C8], rdi
0x180015882  mov     [rbp+57h+var_B0], rax
0x180015886  lea     rax, [rsp+130h+var_E0]
0x18001588b  mov     [rbp+57h+var_A0], rax
0x18001588f  lea     rax, [rbp+57h+var_D0]
0x180015893  mov     [rbp+57h+var_90], rax
0x180015897  lea     rax, [rsp+130h+var_E8]
0x18001589c  mov     [rbp+57h+var_80], rax
0x1800158a0  lea     rax, [rsp+130h+var_D8]
0x1800158a5  mov     [rbp+57h+var_70], rax
0x1800158a9  lea     rax, [rsp+130h+var_F0]
0x1800158ae  mov     [rbp+57h+var_60], rax
0x1800158b2  lea     rax, [rbp+57h+var_C8]
0x1800158b6  mov     [rbp+57h+var_50], rax
0x1800158ba  lea     rax, [rbp+57h+var_C0]
0x1800158be  mov     qword ptr [rsp+130h+var_110], rax
0x1800158c3  mov     dword ptr [rsp+130h+var_F0], ecx
0x1800158c7  mov     [rsp+130h+var_D8], r12d
0x1800158cc  mov     [rbp+57h+var_A8], 4
0x1800158d4  mov     [rbp+57h+var_98], 4
0x1800158dc  mov     [rbp+57h+var_88], 8
0x1800158e4  mov     [rbp+57h+var_78], 4
0x1800158ec  mov     [rbp+57h+var_68], 4
0x1800158f4  mov     [rbp+57h+var_58], 4
0x1800158fc  mov     [rbp+57h+var_48], 8
0x180015904  call    McGenEventWrite_EventWriteTransfer
0x180015909  mov     rax, [rdi]
0x18001590c  mov     rcx, rdi
0x18001590f  mov     rax, [rax+68h]
0x180015913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015918  test    al, al
0x18001591a  jz      loc_1800156A8
0x180015920  mov     r14d, [rdi+90h]
0x180015927  test    r14d, r14d
0x18001592a  jz      loc_1800156A8
0x180015930  mov     rax, [rdi+18h]
0x180015934  lea     r8, [rsp+130h+var_F0]; void **
0x180015939  mov     ebx, [rdi+88h]
0x18001593f  xor     r9d, r9d; bool
0x180015942  mov     edx, 0Ch; unsigned int
0x180015947  mov     [rsp+130h+var_F0], 0
0x180015950  mov     rsi, [rax+1B8h]
0x180015957  mov     rcx, rsi; this
0x18001595a  call    ?BeginKernelCommand@CDevice@DirectComposition@@AEAAXIPEAPEAX_N@Z; DirectComposition::CDevice::BeginKernelCommand(uint,void * *,bool)
0x18001595f  mov     rax, [rsp+130h+var_F0]
0x180015964  mov     dword ptr [rax], 0Ah
0x18001596a  mov     [rax+4], r14d
0x18001596e  mov     [rax+8], ebx
0x180015971  mov     rcx, [rsi+58h]
0x180015975  test    rcx, rcx
0x180015978  jz      loc_1800156A8
0x18001597e  jmp     loc_18001569C
0x180015983  mov     r14d, ecx
0x180015986  mov     [rsp+130h+var_F8], 0
0x18001598e  mov     rcx, rbx
0x180015991  lea     rdx, [rsp+130h+var_F8]
0x180015996  call    ?AddMultipleAndSet@?$DynArray@I$00@@QEAAJPEFBII@Z; DynArray<uint,1>::AddMultipleAndSet(uint const *,uint)
0x18001599b  mov     esi, eax
0x18001599d  test    eax, eax
0x18001599f  js      short loc_1800159DB
0x1800159a1  xor     r9d, r9d
0x1800159a4  jmp     loc_180015648
0x1800159a9  mov     rax, [rdx]
0x1800159ac  mov     rcx, r14
0x1800159af  mov     rax, [rax+50h]
0x1800159b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159b8  jmp     loc_1800154EE
  ... truncated ...
```
