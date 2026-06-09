# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800067b0`
- end: `0x1800069b7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800067b0`
- `0x180006eac`
- `0x180006f90`
- `0x180007828`
- `0x180007b90`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800067da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000689c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800067da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000689c`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // rdi
  char v6; // bp
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al
  DWORD v12; // eax
  bool v13; // dl
  wil::details_abi *v14; // rcx
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  unsigned __int64 v16; // r8
  struct wil::details_abi::ThreadLocalData *v17; // rbx
  int v18; // esi
  _WORD *v19; // rax
  _WORD *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned __int16 v24; // dx

  v5 = (wil::details *)this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        i += 16;
        break;
      }
    }
    if ( i && *(_QWORD *)i )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v5,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v5 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v5);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (*((_BYTE *)v5 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v5);
  }
  v12 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v12 )
  {
    v14 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v14 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v12;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v14, v13);
      v17 = ThreadLocalDataCache;
      if ( ThreadLocalDataCache )
      {
        v18 = *((_DWORD *)ThreadLocalDataCache + 4);
        if ( !*((_QWORD *)ThreadLocalDataCache + 3) )
        {
          if ( v18 )
          {
            v19 = wil::details::ProcessHeapAlloc(8u, 0x190u, v16);
            *((_QWORD *)v17 + 3) = v19;
            if ( v19 )
            {
              *((_DWORD *)v17 + 8) = 5;
              v20 = v19 + 200;
              while ( v19 != v20 )
              {
                *v19 = 80;
                v19 += 40;
              }
            }
          }
        }
        v21 = *((_QWORD *)v17 + 3);
        if ( v21 )
        {
          if ( !v18 || (v22 = *((_QWORD *)v17 + 3), v23 = v21 + 80LL * *((unsigned __int16 *)v17 + 16), v21 == v23) )
          {
LABEL_36:
            v24 = ((unsigned int)*((unsigned __int16 *)v17 + 17) + 1) % *((unsigned __int16 *)v17 + 16);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v5,
              _InterlockedIncrement(*((volatile signed __int32 **)v17 + 1)));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v5 + 2) )
            {
              v22 += 80;
              if ( v22 == v23 )
                goto LABEL_36;
            }
          }
        }
      }
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x1800067b0  push    rbx
0x1800067b2  push    rbp
0x1800067b3  push    rsi
0x1800067b4  push    rdi
0x1800067b5  push    r14
0x1800067b7  sub     rsp, 20h
0x1800067bb  mov     r14, r8
0x1800067be  mov     rsi, rdx
0x1800067c1  mov     rdi, rcx
0x1800067c4  mov     byte ptr [rdx], 0
0x1800067c7  xor     bpl, bpl
0x1800067ca  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800067d1  test    rbx, rbx
0x1800067d4  jz      loc_180006870
0x1800067da  call    cs:__imp_GetCurrentThreadId
0x1800067e0  mov     r9d, eax
0x1800067e3  mov     r8d, eax
0x1800067e6  shr     r8, 2
0x1800067ea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800067f4  mul     r8
0x1800067f7  shr     rdx, 3
0x1800067fb  lea     rcx, [rdx+rdx*4]
0x1800067ff  add     rcx, rcx
0x180006802  sub     r8, rcx
0x180006805  mov     rbx, [rbx+r8*8]
0x180006809  jmp     short loc_180006814
0x18000680b  cmp     [rbx], r9d
0x18000680e  jz      short loc_18000688B
0x180006810  mov     rbx, [rbx+8]
0x180006814  test    rbx, rbx
0x180006817  jnz     short loc_18000680B
0x180006819  test    rbx, rbx
0x18000681c  jz      short loc_180006870
0x18000681e  cmp     qword ptr [rbx], 0
0x180006822  jz      short loc_180006870
0x180006824  mov     [rsi], bpl
0x180006827  mov     r9, r14; unsigned __int64
0x18000682a  mov     r8, rsi; char *
0x18000682d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180006830  mov     rcx, rdi; struct wil::FailureInfo *
0x180006833  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006838  test    al, al
0x18000683a  jz      short loc_180006840
0x18000683c  mov     [rdi+48h], rsi
0x180006840  mov     rbx, [rbx]
0x180006843  mov     al, [rbx+28h]
0x180006846  mov     byte ptr [rbx+28h], 1
0x18000684a  test    al, al
0x18000684c  jnz     short loc_180006867
0x18000684e  mov     rcx, [rbx+8]
0x180006852  mov     rax, [rcx]
0x180006855  mov     rdx, rdi
0x180006858  mov     rax, [rax]
0x18000685b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006860  or      bpl, al
0x180006863  mov     byte ptr [rbx+28h], 0
0x180006867  mov     rbx, [rbx+10h]
0x18000686b  test    rbx, rbx
0x18000686e  jnz     short loc_180006843
0x180006870  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006877  test    rax, rax
0x18000687a  jz      short loc_18000689C
0x18000687c  test    bpl, bpl
0x18000687f  jnz     short loc_180006891
0x180006881  test    byte ptr [rdi+4], 2
0x180006885  jnz     short loc_180006891
0x180006887  xor     ecx, ecx
0x180006889  jmp     short loc_180006893
0x18000688b  add     rbx, 10h
0x18000688f  jmp     short loc_180006819
0x180006891  mov     cl, 1
0x180006893  mov     rdx, rdi
0x180006896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000689b  nop
0x18000689c  call    cs:__imp_GetCurrentThreadId
0x1800068a2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800068a8  cmp     ecx, eax
0x1800068aa  jz      loc_1800069AC
0x1800068b0  mov     ecx, 1
0x1800068b5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800068bd  inc     ecx; this
0x1800068bf  cmp     ecx, 4
0x1800068c2  jge     loc_1800069A5
0x1800068c8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800068ce  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800068d3  mov     rbx, rax
0x1800068d6  test    rax, rax
0x1800068d9  jz      loc_18000699B
0x1800068df  mov     esi, [rax+10h]
0x1800068e2  mov     ebp, 50h ; 'P'
0x1800068e7  cmp     qword ptr [rax+18h], 0
0x1800068ec  jnz     short loc_180006923
0x1800068ee  test    esi, esi
0x1800068f0  jz      short loc_180006923
0x1800068f2  mov     edx, 190h; dwBytes
0x1800068f7  lea     ecx, [rbp-48h]; dwFlags
0x1800068fa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800068ff  mov     [rbx+18h], rax
0x180006903  test    rax, rax
0x180006906  jz      short loc_180006923
0x180006908  mov     dword ptr [rbx+20h], 5
0x18000690f  lea     rcx, [rax+190h]
0x180006916  jmp     short loc_18000691E
0x180006918  mov     [rax], bp
0x18000691b  add     rax, rbp
0x18000691e  cmp     rax, rcx
0x180006921  jnz     short loc_180006918
0x180006923  mov     r9, [rbx+18h]
0x180006927  test    r9, r9
0x18000692a  jz      short loc_18000699B
0x18000692c  test    esi, esi
0x18000692e  jz      short loc_180006961
0x180006930  mov     rcx, r9
0x180006933  movzx   eax, word ptr [rbx+20h]
0x180006937  lea     rdx, [rax+rax*4]
0x18000693b  shl     rdx, 4
0x18000693f  add     rdx, r9
0x180006942  cmp     r9, rdx
0x180006945  jz      short loc_180006961
0x180006947  mov     r8d, [rbx+10h]
0x18000694b  cmp     [rcx+4], r8d
0x18000694f  jbe     short loc_180006959
0x180006951  mov     eax, [rdi+8]
0x180006954  cmp     [rcx+8], eax
0x180006957  jz      short loc_18000699B
0x180006959  add     rcx, rbp
0x18000695c  cmp     rcx, rdx
0x18000695f  jnz     short loc_18000694B
0x180006961  movzx   eax, word ptr [rbx+22h]
0x180006965  inc     eax
0x180006967  movzx   ecx, word ptr [rbx+20h]
0x18000696b  xor     edx, edx
0x18000696d  div     ecx
0x18000696f  mov     [rbx+22h], dx
0x180006973  mov     rax, [rbx+8]
0x180006977  mov     r8d, 1
0x18000697d  lock xadd [rax], r8d
0x180006982  inc     r8d; unsigned int
0x180006985  movzx   eax, dx
0x180006988  lea     rcx, [rax+rax*4]
0x18000698c  shl     rcx, 4
0x180006990  add     rcx, r9; this
0x180006993  mov     rdx, rdi; struct wil::FailureInfo *
0x180006996  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000699b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800069a5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800069ac  add     rsp, 20h
0x1800069b0  pop     r14
0x1800069b2  pop     rdi
0x1800069b3  pop     rsi
0x1800069b4  pop     rbp
0x1800069b5  pop     rbx
0x1800069b6  retn
```
