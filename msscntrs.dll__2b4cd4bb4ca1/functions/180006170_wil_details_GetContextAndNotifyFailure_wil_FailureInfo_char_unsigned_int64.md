# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006170`
- end: `0x180006377`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006170`
- `0x18000686c`
- `0x180006950`
- `0x1800073c8`
- `0x180008c84`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000619a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000625c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000619a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000625c`

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
0x180006170  push    rbx
0x180006172  push    rbp
0x180006173  push    rsi
0x180006174  push    rdi
0x180006175  push    r14
0x180006177  sub     rsp, 20h
0x18000617b  mov     r14, r8
0x18000617e  mov     rsi, rdx
0x180006181  mov     rdi, rcx
0x180006184  mov     byte ptr [rdx], 0
0x180006187  xor     bpl, bpl
0x18000618a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006191  test    rbx, rbx
0x180006194  jz      loc_180006230
0x18000619a  call    cs:__imp_GetCurrentThreadId
0x1800061a0  mov     r9d, eax
0x1800061a3  mov     r8d, eax
0x1800061a6  shr     r8, 2
0x1800061aa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800061b4  mul     r8
0x1800061b7  shr     rdx, 3
0x1800061bb  lea     rcx, [rdx+rdx*4]
0x1800061bf  add     rcx, rcx
0x1800061c2  sub     r8, rcx
0x1800061c5  mov     rbx, [rbx+r8*8]
0x1800061c9  jmp     short loc_1800061D4
0x1800061cb  cmp     [rbx], r9d
0x1800061ce  jz      short loc_18000624B
0x1800061d0  mov     rbx, [rbx+8]
0x1800061d4  test    rbx, rbx
0x1800061d7  jnz     short loc_1800061CB
0x1800061d9  test    rbx, rbx
0x1800061dc  jz      short loc_180006230
0x1800061de  cmp     qword ptr [rbx], 0
0x1800061e2  jz      short loc_180006230
0x1800061e4  mov     [rsi], bpl
0x1800061e7  mov     r9, r14; unsigned __int64
0x1800061ea  mov     r8, rsi; char *
0x1800061ed  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800061f0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800061f3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800061f8  test    al, al
0x1800061fa  jz      short loc_180006200
0x1800061fc  mov     [rdi+48h], rsi
0x180006200  mov     rbx, [rbx]
0x180006203  mov     al, [rbx+28h]
0x180006206  mov     byte ptr [rbx+28h], 1
0x18000620a  test    al, al
0x18000620c  jnz     short loc_180006227
0x18000620e  mov     rcx, [rbx+8]
0x180006212  mov     rax, [rcx]
0x180006215  mov     rdx, rdi
0x180006218  mov     rax, [rax]
0x18000621b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006220  or      bpl, al
0x180006223  mov     byte ptr [rbx+28h], 0
0x180006227  mov     rbx, [rbx+10h]
0x18000622b  test    rbx, rbx
0x18000622e  jnz     short loc_180006203
0x180006230  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006237  test    rax, rax
0x18000623a  jz      short loc_18000625C
0x18000623c  test    bpl, bpl
0x18000623f  jnz     short loc_180006251
0x180006241  test    byte ptr [rdi+4], 2
0x180006245  jnz     short loc_180006251
0x180006247  xor     ecx, ecx
0x180006249  jmp     short loc_180006253
0x18000624b  add     rbx, 10h
0x18000624f  jmp     short loc_1800061D9
0x180006251  mov     cl, 1
0x180006253  mov     rdx, rdi
0x180006256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000625b  nop
0x18000625c  call    cs:__imp_GetCurrentThreadId
0x180006262  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006268  cmp     ecx, eax
0x18000626a  jz      loc_18000636C
0x180006270  mov     ecx, 1
0x180006275  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000627d  inc     ecx; this
0x18000627f  cmp     ecx, 4
0x180006282  jge     loc_180006365
0x180006288  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000628e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180006293  mov     rbx, rax
0x180006296  test    rax, rax
0x180006299  jz      loc_18000635B
0x18000629f  mov     esi, [rax+10h]
0x1800062a2  mov     ebp, 50h ; 'P'
0x1800062a7  cmp     qword ptr [rax+18h], 0
0x1800062ac  jnz     short loc_1800062E3
0x1800062ae  test    esi, esi
0x1800062b0  jz      short loc_1800062E3
0x1800062b2  mov     edx, 190h; dwBytes
0x1800062b7  lea     ecx, [rbp-48h]; dwFlags
0x1800062ba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800062bf  mov     [rbx+18h], rax
0x1800062c3  test    rax, rax
0x1800062c6  jz      short loc_1800062E3
0x1800062c8  mov     dword ptr [rbx+20h], 5
0x1800062cf  lea     rcx, [rax+190h]
0x1800062d6  jmp     short loc_1800062DE
0x1800062d8  mov     [rax], bp
0x1800062db  add     rax, rbp
0x1800062de  cmp     rax, rcx
0x1800062e1  jnz     short loc_1800062D8
0x1800062e3  mov     r9, [rbx+18h]
0x1800062e7  test    r9, r9
0x1800062ea  jz      short loc_18000635B
0x1800062ec  test    esi, esi
0x1800062ee  jz      short loc_180006321
0x1800062f0  mov     rcx, r9
0x1800062f3  movzx   eax, word ptr [rbx+20h]
0x1800062f7  lea     rdx, [rax+rax*4]
0x1800062fb  shl     rdx, 4
0x1800062ff  add     rdx, r9
0x180006302  cmp     r9, rdx
0x180006305  jz      short loc_180006321
0x180006307  mov     r8d, [rbx+10h]
0x18000630b  cmp     [rcx+4], r8d
0x18000630f  jbe     short loc_180006319
0x180006311  mov     eax, [rdi+8]
0x180006314  cmp     [rcx+8], eax
0x180006317  jz      short loc_18000635B
0x180006319  add     rcx, rbp
0x18000631c  cmp     rcx, rdx
0x18000631f  jnz     short loc_18000630B
0x180006321  movzx   eax, word ptr [rbx+22h]
0x180006325  inc     eax
0x180006327  movzx   ecx, word ptr [rbx+20h]
0x18000632b  xor     edx, edx
0x18000632d  div     ecx
0x18000632f  mov     [rbx+22h], dx
0x180006333  mov     rax, [rbx+8]
0x180006337  mov     r8d, 1
0x18000633d  lock xadd [rax], r8d
0x180006342  inc     r8d; unsigned int
0x180006345  movzx   eax, dx
0x180006348  lea     rcx, [rax+rax*4]
0x18000634c  shl     rcx, 4
0x180006350  add     rcx, r9; this
0x180006353  mov     rdx, rdi; struct wil::FailureInfo *
0x180006356  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000635b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006365  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000636c  add     rsp, 20h
0x180006370  pop     r14
0x180006372  pop     rdi
0x180006373  pop     rsi
0x180006374  pop     rbp
0x180006375  pop     rbx
0x180006376  retn
```
