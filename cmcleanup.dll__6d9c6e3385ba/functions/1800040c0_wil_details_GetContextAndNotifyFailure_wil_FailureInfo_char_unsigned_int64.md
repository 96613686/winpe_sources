# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800040c0`
- end: `0x1800042c7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800040c0`
- `0x180004810`
- `0x1800048f4`
- `0x18000529c`
- `0x180006960`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800041ac`

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
0x1800040c0  push    rbx
0x1800040c2  push    rbp
0x1800040c3  push    rsi
0x1800040c4  push    rdi
0x1800040c5  push    r14
0x1800040c7  sub     rsp, 20h
0x1800040cb  mov     r14, r8
0x1800040ce  mov     rsi, rdx
0x1800040d1  mov     rdi, rcx
0x1800040d4  mov     byte ptr [rdx], 0
0x1800040d7  xor     bpl, bpl
0x1800040da  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800040e1  test    rbx, rbx
0x1800040e4  jz      loc_180004180
0x1800040ea  call    cs:__imp_GetCurrentThreadId
0x1800040f0  mov     r9d, eax
0x1800040f3  mov     r8d, eax
0x1800040f6  shr     r8, 2
0x1800040fa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004104  mul     r8
0x180004107  shr     rdx, 3
0x18000410b  lea     rcx, [rdx+rdx*4]
0x18000410f  add     rcx, rcx
0x180004112  sub     r8, rcx
0x180004115  mov     rbx, [rbx+r8*8]
0x180004119  jmp     short loc_180004124
0x18000411b  cmp     [rbx], r9d
0x18000411e  jz      short loc_18000419B
0x180004120  mov     rbx, [rbx+8]
0x180004124  test    rbx, rbx
0x180004127  jnz     short loc_18000411B
0x180004129  test    rbx, rbx
0x18000412c  jz      short loc_180004180
0x18000412e  cmp     qword ptr [rbx], 0
0x180004132  jz      short loc_180004180
0x180004134  mov     [rsi], bpl
0x180004137  mov     r9, r14; unsigned __int64
0x18000413a  mov     r8, rsi; char *
0x18000413d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004140  mov     rcx, rdi; struct wil::FailureInfo *
0x180004143  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004148  test    al, al
0x18000414a  jz      short loc_180004150
0x18000414c  mov     [rdi+48h], rsi
0x180004150  mov     rbx, [rbx]
0x180004153  mov     al, [rbx+28h]
0x180004156  mov     byte ptr [rbx+28h], 1
0x18000415a  test    al, al
0x18000415c  jnz     short loc_180004177
0x18000415e  mov     rcx, [rbx+8]
0x180004162  mov     rax, [rcx]
0x180004165  mov     rdx, rdi
0x180004168  mov     rax, [rax]
0x18000416b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004170  or      bpl, al
0x180004173  mov     byte ptr [rbx+28h], 0
0x180004177  mov     rbx, [rbx+10h]
0x18000417b  test    rbx, rbx
0x18000417e  jnz     short loc_180004153
0x180004180  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004187  test    rax, rax
0x18000418a  jz      short loc_1800041AC
0x18000418c  test    bpl, bpl
0x18000418f  jnz     short loc_1800041A1
0x180004191  test    byte ptr [rdi+4], 2
0x180004195  jnz     short loc_1800041A1
0x180004197  xor     ecx, ecx
0x180004199  jmp     short loc_1800041A3
0x18000419b  add     rbx, 10h
0x18000419f  jmp     short loc_180004129
0x1800041a1  mov     cl, 1
0x1800041a3  mov     rdx, rdi
0x1800041a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041ab  nop
0x1800041ac  call    cs:__imp_GetCurrentThreadId
0x1800041b2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800041b8  cmp     ecx, eax
0x1800041ba  jz      loc_1800042BC
0x1800041c0  mov     ecx, 1
0x1800041c5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800041cd  inc     ecx; this
0x1800041cf  cmp     ecx, 4
0x1800041d2  jge     loc_1800042B5
0x1800041d8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800041de  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800041e3  mov     rbx, rax
0x1800041e6  test    rax, rax
0x1800041e9  jz      loc_1800042AB
0x1800041ef  mov     esi, [rax+10h]
0x1800041f2  mov     ebp, 50h ; 'P'
0x1800041f7  cmp     qword ptr [rax+18h], 0
0x1800041fc  jnz     short loc_180004233
0x1800041fe  test    esi, esi
0x180004200  jz      short loc_180004233
0x180004202  mov     edx, 190h; dwBytes
0x180004207  lea     ecx, [rbp-48h]; dwFlags
0x18000420a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000420f  mov     [rbx+18h], rax
0x180004213  test    rax, rax
0x180004216  jz      short loc_180004233
0x180004218  mov     dword ptr [rbx+20h], 5
0x18000421f  lea     rcx, [rax+190h]
0x180004226  jmp     short loc_18000422E
0x180004228  mov     [rax], bp
0x18000422b  add     rax, rbp
0x18000422e  cmp     rax, rcx
0x180004231  jnz     short loc_180004228
0x180004233  mov     r9, [rbx+18h]
0x180004237  test    r9, r9
0x18000423a  jz      short loc_1800042AB
0x18000423c  test    esi, esi
0x18000423e  jz      short loc_180004271
0x180004240  mov     rcx, r9
0x180004243  movzx   eax, word ptr [rbx+20h]
0x180004247  lea     rdx, [rax+rax*4]
0x18000424b  shl     rdx, 4
0x18000424f  add     rdx, r9
0x180004252  cmp     r9, rdx
0x180004255  jz      short loc_180004271
0x180004257  mov     r8d, [rbx+10h]
0x18000425b  cmp     [rcx+4], r8d
0x18000425f  jbe     short loc_180004269
0x180004261  mov     eax, [rdi+8]
0x180004264  cmp     [rcx+8], eax
0x180004267  jz      short loc_1800042AB
0x180004269  add     rcx, rbp
0x18000426c  cmp     rcx, rdx
0x18000426f  jnz     short loc_18000425B
0x180004271  movzx   eax, word ptr [rbx+22h]
0x180004275  inc     eax
0x180004277  movzx   ecx, word ptr [rbx+20h]
0x18000427b  xor     edx, edx
0x18000427d  div     ecx
0x18000427f  mov     [rbx+22h], dx
0x180004283  mov     rax, [rbx+8]
0x180004287  mov     r8d, 1
0x18000428d  lock xadd [rax], r8d
0x180004292  inc     r8d; unsigned int
0x180004295  movzx   eax, dx
0x180004298  lea     rcx, [rax+rax*4]
0x18000429c  shl     rcx, 4
0x1800042a0  add     rcx, r9; this
0x1800042a3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800042a6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800042ab  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800042b5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800042bc  add     rsp, 20h
0x1800042c0  pop     r14
0x1800042c2  pop     rdi
0x1800042c3  pop     rsi
0x1800042c4  pop     rbp
0x1800042c5  pop     rbx
0x1800042c6  retn
```
