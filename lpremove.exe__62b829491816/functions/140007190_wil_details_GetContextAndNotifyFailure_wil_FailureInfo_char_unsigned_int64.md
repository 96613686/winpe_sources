# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140007190`
- end: `0x140007397`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140007190`
- `0x1400079dc`
- `0x140007ac0`
- `0x140009080`
- `0x14000aa04`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400071ba`
- `KERNEL32!GetCurrentThreadId` at `0x14000727c`
- `KERNEL32!GetCurrentThreadId` at `0x1400071ba`
- `KERNEL32!GetCurrentThreadId` at `0x14000727c`

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
0x140007190  push    rbx
0x140007192  push    rbp
0x140007193  push    rsi
0x140007194  push    rdi
0x140007195  push    r14
0x140007197  sub     rsp, 20h
0x14000719b  mov     r14, r8
0x14000719e  mov     rsi, rdx
0x1400071a1  mov     rdi, rcx
0x1400071a4  mov     byte ptr [rdx], 0
0x1400071a7  xor     bpl, bpl
0x1400071aa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400071b1  test    rbx, rbx
0x1400071b4  jz      loc_140007250
0x1400071ba  call    cs:__imp_GetCurrentThreadId
0x1400071c0  mov     r9d, eax
0x1400071c3  mov     r8d, eax
0x1400071c6  shr     r8, 2
0x1400071ca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400071d4  mul     r8
0x1400071d7  shr     rdx, 3
0x1400071db  lea     rcx, [rdx+rdx*4]
0x1400071df  add     rcx, rcx
0x1400071e2  sub     r8, rcx
0x1400071e5  mov     rbx, [rbx+r8*8]
0x1400071e9  jmp     short loc_1400071F4
0x1400071eb  cmp     [rbx], r9d
0x1400071ee  jz      short loc_14000726B
0x1400071f0  mov     rbx, [rbx+8]
0x1400071f4  test    rbx, rbx
0x1400071f7  jnz     short loc_1400071EB
0x1400071f9  test    rbx, rbx
0x1400071fc  jz      short loc_140007250
0x1400071fe  cmp     qword ptr [rbx], 0
0x140007202  jz      short loc_140007250
0x140007204  mov     [rsi], bpl
0x140007207  mov     r9, r14; unsigned __int64
0x14000720a  mov     r8, rsi; char *
0x14000720d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140007210  mov     rcx, rdi; struct wil::FailureInfo *
0x140007213  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140007218  test    al, al
0x14000721a  jz      short loc_140007220
0x14000721c  mov     [rdi+48h], rsi
0x140007220  mov     rbx, [rbx]
0x140007223  mov     al, [rbx+28h]
0x140007226  mov     byte ptr [rbx+28h], 1
0x14000722a  test    al, al
0x14000722c  jnz     short loc_140007247
0x14000722e  mov     rcx, [rbx+8]
0x140007232  mov     rax, [rcx]
0x140007235  mov     rdx, rdi
0x140007238  mov     rax, [rax]
0x14000723b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007240  or      bpl, al
0x140007243  mov     byte ptr [rbx+28h], 0
0x140007247  mov     rbx, [rbx+10h]
0x14000724b  test    rbx, rbx
0x14000724e  jnz     short loc_140007223
0x140007250  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140007257  test    rax, rax
0x14000725a  jz      short loc_14000727C
0x14000725c  test    bpl, bpl
0x14000725f  jnz     short loc_140007271
0x140007261  test    byte ptr [rdi+4], 2
0x140007265  jnz     short loc_140007271
0x140007267  xor     ecx, ecx
0x140007269  jmp     short loc_140007273
0x14000726b  add     rbx, 10h
0x14000726f  jmp     short loc_1400071F9
0x140007271  mov     cl, 1
0x140007273  mov     rdx, rdi
0x140007276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000727b  nop
0x14000727c  call    cs:__imp_GetCurrentThreadId
0x140007282  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140007288  cmp     ecx, eax
0x14000728a  jz      loc_14000738C
0x140007290  mov     ecx, 1
0x140007295  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000729d  inc     ecx; this
0x14000729f  cmp     ecx, 4
0x1400072a2  jge     loc_140007385
0x1400072a8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400072ae  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1400072b3  mov     rbx, rax
0x1400072b6  test    rax, rax
0x1400072b9  jz      loc_14000737B
0x1400072bf  mov     esi, [rax+10h]
0x1400072c2  mov     ebp, 50h ; 'P'
0x1400072c7  cmp     qword ptr [rax+18h], 0
0x1400072cc  jnz     short loc_140007303
0x1400072ce  test    esi, esi
0x1400072d0  jz      short loc_140007303
0x1400072d2  mov     edx, 190h; dwBytes
0x1400072d7  lea     ecx, [rbp-48h]; dwFlags
0x1400072da  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400072df  mov     [rbx+18h], rax
0x1400072e3  test    rax, rax
0x1400072e6  jz      short loc_140007303
0x1400072e8  mov     dword ptr [rbx+20h], 5
0x1400072ef  lea     rcx, [rax+190h]
0x1400072f6  jmp     short loc_1400072FE
0x1400072f8  mov     [rax], bp
0x1400072fb  add     rax, rbp
0x1400072fe  cmp     rax, rcx
0x140007301  jnz     short loc_1400072F8
0x140007303  mov     r9, [rbx+18h]
0x140007307  test    r9, r9
0x14000730a  jz      short loc_14000737B
0x14000730c  test    esi, esi
0x14000730e  jz      short loc_140007341
0x140007310  mov     rcx, r9
0x140007313  movzx   eax, word ptr [rbx+20h]
0x140007317  lea     rdx, [rax+rax*4]
0x14000731b  shl     rdx, 4
0x14000731f  add     rdx, r9
0x140007322  cmp     r9, rdx
0x140007325  jz      short loc_140007341
0x140007327  mov     r8d, [rbx+10h]
0x14000732b  cmp     [rcx+4], r8d
0x14000732f  jbe     short loc_140007339
0x140007331  mov     eax, [rdi+8]
0x140007334  cmp     [rcx+8], eax
0x140007337  jz      short loc_14000737B
0x140007339  add     rcx, rbp
0x14000733c  cmp     rcx, rdx
0x14000733f  jnz     short loc_14000732B
0x140007341  movzx   eax, word ptr [rbx+22h]
0x140007345  inc     eax
0x140007347  movzx   ecx, word ptr [rbx+20h]
0x14000734b  xor     edx, edx
0x14000734d  div     ecx
0x14000734f  mov     [rbx+22h], dx
0x140007353  mov     rax, [rbx+8]
0x140007357  mov     r8d, 1
0x14000735d  lock xadd [rax], r8d
0x140007362  inc     r8d; unsigned int
0x140007365  movzx   eax, dx
0x140007368  lea     rcx, [rax+rax*4]
0x14000736c  shl     rcx, 4
0x140007370  add     rcx, r9; this
0x140007373  mov     rdx, rdi; struct wil::FailureInfo *
0x140007376  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000737b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140007385  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000738c  add     rsp, 20h
0x140007390  pop     r14
0x140007392  pop     rdi
0x140007393  pop     rsi
0x140007394  pop     rbp
0x140007395  pop     rbx
0x140007396  retn
```
