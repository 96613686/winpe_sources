# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006fd0`
- end: `0x1800071e0`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `528`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006fd0`
- `0x180007d0c`
- `0x180007df0`
- `0x180008b94`
- `0x18000a4e8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007003`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800070c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007003`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800070c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180006fd0  push    rbx
0x180006fd2  push    rbp
0x180006fd3  push    rsi
0x180006fd4  push    rdi
0x180006fd5  push    r14
0x180006fd7  sub     rsp, 30h
0x180006fdb  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180006fe4  mov     r14, r8
0x180006fe7  mov     rsi, rdx
0x180006fea  mov     rdi, rcx
0x180006fed  mov     byte ptr [rdx], 0
0x180006ff0  xor     bpl, bpl
0x180006ff3  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006ffa  test    rbx, rbx
0x180006ffd  jz      loc_180007099
0x180007003  call    cs:__imp_GetCurrentThreadId
0x180007009  mov     r9d, eax
0x18000700c  mov     r8d, eax
0x18000700f  shr     r8, 2
0x180007013  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000701d  mul     r8
0x180007020  shr     rdx, 3
0x180007024  lea     rcx, [rdx+rdx*4]
0x180007028  add     rcx, rcx
0x18000702b  sub     r8, rcx
0x18000702e  mov     rbx, [rbx+r8*8]
0x180007032  jmp     short loc_18000703D
0x180007034  cmp     [rbx], r9d
0x180007037  jz      short loc_1800070B4
0x180007039  mov     rbx, [rbx+8]
0x18000703d  test    rbx, rbx
0x180007040  jnz     short loc_180007034
0x180007042  test    rbx, rbx
0x180007045  jz      short loc_180007099
0x180007047  cmp     qword ptr [rbx], 0
0x18000704b  jz      short loc_180007099
0x18000704d  mov     [rsi], bpl
0x180007050  mov     r9, r14; unsigned __int64
0x180007053  mov     r8, rsi; char *
0x180007056  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180007059  mov     rcx, rdi; struct wil::FailureInfo *
0x18000705c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007061  test    al, al
0x180007063  jz      short loc_180007069
0x180007065  mov     [rdi+48h], rsi
0x180007069  mov     rbx, [rbx]
0x18000706c  mov     al, [rbx+28h]
0x18000706f  mov     byte ptr [rbx+28h], 1
0x180007073  test    al, al
0x180007075  jnz     short loc_180007090
0x180007077  mov     rcx, [rbx+8]
0x18000707b  mov     rax, [rcx]
0x18000707e  mov     rdx, rdi
0x180007081  mov     rax, [rax]
0x180007084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007089  or      bpl, al
0x18000708c  mov     byte ptr [rbx+28h], 0
0x180007090  mov     rbx, [rbx+10h]
0x180007094  test    rbx, rbx
0x180007097  jnz     short loc_18000706C
0x180007099  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800070a0  test    rax, rax
0x1800070a3  jz      short loc_1800070C5
0x1800070a5  test    bpl, bpl
0x1800070a8  jnz     short loc_1800070BA
0x1800070aa  test    byte ptr [rdi+4], 2
0x1800070ae  jnz     short loc_1800070BA
0x1800070b0  xor     ecx, ecx
0x1800070b2  jmp     short loc_1800070BC
0x1800070b4  add     rbx, 10h
0x1800070b8  jmp     short loc_180007042
0x1800070ba  mov     cl, 1
0x1800070bc  mov     rdx, rdi
0x1800070bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070c4  nop
0x1800070c5  call    cs:__imp_GetCurrentThreadId
0x1800070cb  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800070d1  cmp     ecx, eax
0x1800070d3  jz      loc_1800071D5
0x1800070d9  mov     ecx, 1
0x1800070de  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800070e6  inc     ecx; this
0x1800070e8  cmp     ecx, 4
0x1800070eb  jge     loc_1800071CE
0x1800070f1  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800070f7  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800070fc  mov     rbx, rax
0x1800070ff  test    rax, rax
0x180007102  jz      loc_1800071C4
0x180007108  mov     esi, [rax+10h]
0x18000710b  mov     ebp, 50h ; 'P'
0x180007110  cmp     qword ptr [rax+18h], 0
0x180007115  jnz     short loc_18000714C
0x180007117  test    esi, esi
0x180007119  jz      short loc_18000714C
0x18000711b  mov     edx, 190h; dwBytes
0x180007120  lea     ecx, [rbp-48h]; dwFlags
0x180007123  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007128  mov     [rbx+18h], rax
0x18000712c  test    rax, rax
0x18000712f  jz      short loc_18000714C
0x180007131  mov     dword ptr [rbx+20h], 5
0x180007138  lea     rcx, [rax+190h]
0x18000713f  jmp     short loc_180007147
0x180007141  mov     [rax], bp
0x180007144  add     rax, rbp
0x180007147  cmp     rax, rcx
0x18000714a  jnz     short loc_180007141
0x18000714c  mov     r9, [rbx+18h]
0x180007150  test    r9, r9
0x180007153  jz      short loc_1800071C4
0x180007155  test    esi, esi
0x180007157  jz      short loc_18000718A
0x180007159  mov     rcx, r9
0x18000715c  movzx   eax, word ptr [rbx+20h]
0x180007160  lea     rdx, [rax+rax*4]
0x180007164  shl     rdx, 4
0x180007168  add     rdx, r9
0x18000716b  cmp     r9, rdx
0x18000716e  jz      short loc_18000718A
0x180007170  mov     r8d, [rbx+10h]
0x180007174  cmp     [rcx+4], r8d
0x180007178  jbe     short loc_180007182
0x18000717a  mov     eax, [rdi+8]
0x18000717d  cmp     [rcx+8], eax
0x180007180  jz      short loc_1800071C4
0x180007182  add     rcx, rbp
0x180007185  cmp     rcx, rdx
0x180007188  jnz     short loc_180007174
0x18000718a  movzx   eax, word ptr [rbx+22h]
0x18000718e  inc     eax
0x180007190  movzx   ecx, word ptr [rbx+20h]
0x180007194  xor     edx, edx
0x180007196  div     ecx
0x180007198  mov     [rbx+22h], dx
0x18000719c  mov     rax, [rbx+8]
0x1800071a0  mov     r8d, 1
0x1800071a6  lock xadd [rax], r8d
0x1800071ab  inc     r8d; unsigned int
0x1800071ae  movzx   eax, dx
0x1800071b1  lea     rcx, [rax+rax*4]
0x1800071b5  shl     rcx, 4
0x1800071b9  add     rcx, r9; this
0x1800071bc  mov     rdx, rdi; struct wil::FailureInfo *
0x1800071bf  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800071c4  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800071ce  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800071d5  add     rsp, 30h
0x1800071d9  pop     r14
0x1800071db  pop     rdi
0x1800071dc  pop     rsi
0x1800071dd  pop     rbp
0x1800071de  pop     rbx
0x1800071df  retn
```
