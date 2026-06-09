# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180009690`
- end: `0x180009896`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180009690`
- `0x180009d88`
- `0x180009e6c`
- `0x18000a7f8`
- `0x18000bb88`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800096ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000977b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800096ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000977b`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
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
  volatile signed __int32 *v25; // rax

  *(_BYTE *)a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (wil::details *)this;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
             v7,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v7 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v3 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v3 || (*((_BYTE *)v7 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v7);
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
            v25 = (volatile signed __int32 *)*((_QWORD *)v17 + 1);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v7,
              _InterlockedIncrement(v25));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v7 + 2) )
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
0x180009690  push    rbx
0x180009692  push    rbp
0x180009693  push    rsi
0x180009694  push    rdi
0x180009695  push    r14
0x180009697  sub     rsp, 20h
0x18000969b  mov     byte ptr [rdx], 0
0x18000969e  xor     bpl, bpl
0x1800096a1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800096a8  mov     r14, r8
0x1800096ab  mov     rsi, rdx
0x1800096ae  mov     rdi, rcx
0x1800096b1  test    rbx, rbx
0x1800096b4  jz      loc_180009750
0x1800096ba  call    cs:__imp_GetCurrentThreadId
0x1800096c0  mov     r8d, eax
0x1800096c3  mov     r9d, eax
0x1800096c6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800096d0  shr     r8, 2
0x1800096d4  mul     r8
0x1800096d7  shr     rdx, 3
0x1800096db  lea     rcx, [rdx+rdx*4]
0x1800096df  add     rcx, rcx
0x1800096e2  sub     r8, rcx
0x1800096e5  mov     rbx, [rbx+r8*8]
0x1800096e9  jmp     short loc_1800096F4
0x1800096eb  cmp     [rbx], r9d
0x1800096ee  jz      short loc_18000976B
0x1800096f0  mov     rbx, [rbx+8]
0x1800096f4  test    rbx, rbx
0x1800096f7  jnz     short loc_1800096EB
0x1800096f9  test    rbx, rbx
0x1800096fc  jz      short loc_180009750
0x1800096fe  cmp     qword ptr [rbx], 0
0x180009702  jz      short loc_180009750
0x180009704  mov     [rsi], bpl
0x180009707  mov     r9, r14; unsigned __int64
0x18000970a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000970d  mov     r8, rsi; char *
0x180009710  mov     rcx, rdi; struct wil::FailureInfo *
0x180009713  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180009718  test    al, al
0x18000971a  jz      short loc_180009720
0x18000971c  mov     [rdi+48h], rsi
0x180009720  mov     rbx, [rbx]
0x180009723  mov     al, [rbx+28h]
0x180009726  mov     byte ptr [rbx+28h], 1
0x18000972a  test    al, al
0x18000972c  jnz     short loc_180009747
0x18000972e  mov     rcx, [rbx+8]
0x180009732  mov     rdx, rdi
0x180009735  mov     rax, [rcx]
0x180009738  mov     rax, [rax]
0x18000973b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009740  or      bpl, al
0x180009743  mov     byte ptr [rbx+28h], 0
0x180009747  mov     rbx, [rbx+10h]
0x18000974b  test    rbx, rbx
0x18000974e  jnz     short loc_180009723
0x180009750  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180009757  test    rax, rax
0x18000975a  jz      short loc_18000977B
0x18000975c  test    bpl, bpl
0x18000975f  jnz     short loc_180009771
0x180009761  test    byte ptr [rdi+4], 2
0x180009765  jnz     short loc_180009771
0x180009767  xor     ecx, ecx
0x180009769  jmp     short loc_180009773
0x18000976b  add     rbx, 10h
0x18000976f  jmp     short loc_1800096F9
0x180009771  mov     cl, 1
0x180009773  mov     rdx, rdi
0x180009776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000977b  call    cs:__imp_GetCurrentThreadId
0x180009781  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009787  cmp     ecx, eax
0x180009789  jz      loc_18000988B
0x18000978f  mov     ecx, 1
0x180009794  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000979c  inc     ecx; this
0x18000979e  cmp     ecx, 4
0x1800097a1  jge     loc_180009884
0x1800097a7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800097ad  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800097b2  mov     rbx, rax
0x1800097b5  test    rax, rax
0x1800097b8  jz      loc_18000987A
0x1800097be  cmp     qword ptr [rax+18h], 0
0x1800097c3  mov     ebp, 50h ; 'P'
0x1800097c8  mov     esi, [rax+10h]
0x1800097cb  jnz     short loc_180009802
0x1800097cd  test    esi, esi
0x1800097cf  jz      short loc_180009802
0x1800097d1  mov     edx, 190h; dwBytes
0x1800097d6  lea     ecx, [rbp-48h]; dwFlags
0x1800097d9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800097de  mov     [rbx+18h], rax
0x1800097e2  test    rax, rax
0x1800097e5  jz      short loc_180009802
0x1800097e7  mov     dword ptr [rbx+20h], 5
0x1800097ee  lea     rcx, [rax+190h]
0x1800097f5  jmp     short loc_1800097FD
0x1800097f7  mov     [rax], bp
0x1800097fa  add     rax, rbp
0x1800097fd  cmp     rax, rcx
0x180009800  jnz     short loc_1800097F7
0x180009802  mov     r9, [rbx+18h]
0x180009806  test    r9, r9
0x180009809  jz      short loc_18000987A
0x18000980b  test    esi, esi
0x18000980d  jz      short loc_180009840
0x18000980f  movzx   eax, word ptr [rbx+20h]
0x180009813  mov     rcx, r9
0x180009816  lea     rdx, [rax+rax*4]
0x18000981a  shl     rdx, 4
0x18000981e  add     rdx, r9
0x180009821  cmp     r9, rdx
0x180009824  jz      short loc_180009840
0x180009826  mov     r8d, [rbx+10h]
0x18000982a  cmp     [rcx+4], r8d
0x18000982e  jbe     short loc_180009838
0x180009830  mov     eax, [rdi+8]
0x180009833  cmp     [rcx+8], eax
0x180009836  jz      short loc_18000987A
0x180009838  add     rcx, rbp
0x18000983b  cmp     rcx, rdx
0x18000983e  jnz     short loc_18000982A
0x180009840  movzx   eax, word ptr [rbx+22h]
0x180009844  xor     edx, edx
0x180009846  movzx   ecx, word ptr [rbx+20h]
0x18000984a  inc     eax
0x18000984c  div     ecx
0x18000984e  mov     rax, [rbx+8]
0x180009852  mov     r8d, 1
0x180009858  mov     [rbx+22h], dx
0x18000985c  lock xadd [rax], r8d
0x180009861  movzx   eax, dx
0x180009864  inc     r8d; unsigned int
0x180009867  mov     rdx, rdi; struct wil::FailureInfo *
0x18000986a  lea     rcx, [rax+rax*4]
0x18000986e  shl     rcx, 4
0x180009872  add     rcx, r9; this
0x180009875  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000987a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009884  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000988b  add     rsp, 20h
0x18000988f  pop     r14
0x180009891  pop     rdi
0x180009892  pop     rsi
0x180009893  pop     rbp
0x180009894  pop     rbx
0x180009895  retn
```
