# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004160`
- end: `0x180004370`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `528`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004160`
- `0x18000488c`
- `0x180004970`
- `0x18000524c`
- `0x180005650`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004193`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004255`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004193`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004255`

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
0x180004160  push    rbx
0x180004162  push    rbp
0x180004163  push    rsi
0x180004164  push    rdi
0x180004165  push    r14
0x180004167  sub     rsp, 30h
0x18000416b  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180004174  mov     r14, r8
0x180004177  mov     rsi, rdx
0x18000417a  mov     rdi, rcx
0x18000417d  mov     byte ptr [rdx], 0
0x180004180  xor     bpl, bpl
0x180004183  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000418a  test    rbx, rbx
0x18000418d  jz      loc_180004229
0x180004193  call    cs:__imp_GetCurrentThreadId
0x180004199  mov     r9d, eax
0x18000419c  mov     r8d, eax
0x18000419f  shr     r8, 2
0x1800041a3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800041ad  mul     r8
0x1800041b0  shr     rdx, 3
0x1800041b4  lea     rcx, [rdx+rdx*4]
0x1800041b8  add     rcx, rcx
0x1800041bb  sub     r8, rcx
0x1800041be  mov     rbx, [rbx+r8*8]
0x1800041c2  jmp     short loc_1800041CD
0x1800041c4  cmp     [rbx], r9d
0x1800041c7  jz      short loc_180004244
0x1800041c9  mov     rbx, [rbx+8]
0x1800041cd  test    rbx, rbx
0x1800041d0  jnz     short loc_1800041C4
0x1800041d2  test    rbx, rbx
0x1800041d5  jz      short loc_180004229
0x1800041d7  cmp     qword ptr [rbx], 0
0x1800041db  jz      short loc_180004229
0x1800041dd  mov     [rsi], bpl
0x1800041e0  mov     r9, r14; unsigned __int64
0x1800041e3  mov     r8, rsi; char *
0x1800041e6  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800041e9  mov     rcx, rdi; struct wil::FailureInfo *
0x1800041ec  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800041f1  test    al, al
0x1800041f3  jz      short loc_1800041F9
0x1800041f5  mov     [rdi+48h], rsi
0x1800041f9  mov     rbx, [rbx]
0x1800041fc  mov     al, [rbx+28h]
0x1800041ff  mov     byte ptr [rbx+28h], 1
0x180004203  test    al, al
0x180004205  jnz     short loc_180004220
0x180004207  mov     rcx, [rbx+8]
0x18000420b  mov     rax, [rcx]
0x18000420e  mov     rdx, rdi
0x180004211  mov     rax, [rax]
0x180004214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004219  or      bpl, al
0x18000421c  mov     byte ptr [rbx+28h], 0
0x180004220  mov     rbx, [rbx+10h]
0x180004224  test    rbx, rbx
0x180004227  jnz     short loc_1800041FC
0x180004229  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004230  test    rax, rax
0x180004233  jz      short loc_180004255
0x180004235  test    bpl, bpl
0x180004238  jnz     short loc_18000424A
0x18000423a  test    byte ptr [rdi+4], 2
0x18000423e  jnz     short loc_18000424A
0x180004240  xor     ecx, ecx
0x180004242  jmp     short loc_18000424C
0x180004244  add     rbx, 10h
0x180004248  jmp     short loc_1800041D2
0x18000424a  mov     cl, 1
0x18000424c  mov     rdx, rdi
0x18000424f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004254  nop
0x180004255  call    cs:__imp_GetCurrentThreadId
0x18000425b  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004261  cmp     ecx, eax
0x180004263  jz      loc_180004365
0x180004269  mov     ecx, 1
0x18000426e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004276  inc     ecx; this
0x180004278  cmp     ecx, 4
0x18000427b  jge     loc_18000435E
0x180004281  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004287  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000428c  mov     rbx, rax
0x18000428f  test    rax, rax
0x180004292  jz      loc_180004354
0x180004298  mov     esi, [rax+10h]
0x18000429b  mov     ebp, 50h ; 'P'
0x1800042a0  cmp     qword ptr [rax+18h], 0
0x1800042a5  jnz     short loc_1800042DC
0x1800042a7  test    esi, esi
0x1800042a9  jz      short loc_1800042DC
0x1800042ab  mov     edx, 190h; dwBytes
0x1800042b0  lea     ecx, [rbp-48h]; dwFlags
0x1800042b3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800042b8  mov     [rbx+18h], rax
0x1800042bc  test    rax, rax
0x1800042bf  jz      short loc_1800042DC
0x1800042c1  mov     dword ptr [rbx+20h], 5
0x1800042c8  lea     rcx, [rax+190h]
0x1800042cf  jmp     short loc_1800042D7
0x1800042d1  mov     [rax], bp
0x1800042d4  add     rax, rbp
0x1800042d7  cmp     rax, rcx
0x1800042da  jnz     short loc_1800042D1
0x1800042dc  mov     r9, [rbx+18h]
0x1800042e0  test    r9, r9
0x1800042e3  jz      short loc_180004354
0x1800042e5  test    esi, esi
0x1800042e7  jz      short loc_18000431A
0x1800042e9  mov     rcx, r9
0x1800042ec  movzx   eax, word ptr [rbx+20h]
0x1800042f0  lea     rdx, [rax+rax*4]
0x1800042f4  shl     rdx, 4
0x1800042f8  add     rdx, r9
0x1800042fb  cmp     r9, rdx
0x1800042fe  jz      short loc_18000431A
0x180004300  mov     r8d, [rbx+10h]
0x180004304  cmp     [rcx+4], r8d
0x180004308  jbe     short loc_180004312
0x18000430a  mov     eax, [rdi+8]
0x18000430d  cmp     [rcx+8], eax
0x180004310  jz      short loc_180004354
0x180004312  add     rcx, rbp
0x180004315  cmp     rcx, rdx
0x180004318  jnz     short loc_180004304
0x18000431a  movzx   eax, word ptr [rbx+22h]
0x18000431e  inc     eax
0x180004320  movzx   ecx, word ptr [rbx+20h]
0x180004324  xor     edx, edx
0x180004326  div     ecx
0x180004328  mov     [rbx+22h], dx
0x18000432c  mov     rax, [rbx+8]
0x180004330  mov     r8d, 1
0x180004336  lock xadd [rax], r8d
0x18000433b  inc     r8d; unsigned int
0x18000433e  movzx   eax, dx
0x180004341  lea     rcx, [rax+rax*4]
0x180004345  shl     rcx, 4
0x180004349  add     rcx, r9; this
0x18000434c  mov     rdx, rdi; struct wil::FailureInfo *
0x18000434f  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004354  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000435e  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004365  add     rsp, 30h
0x180004369  pop     r14
0x18000436b  pop     rdi
0x18000436c  pop     rsi
0x18000436d  pop     rbp
0x18000436e  pop     rbx
0x18000436f  retn
```
