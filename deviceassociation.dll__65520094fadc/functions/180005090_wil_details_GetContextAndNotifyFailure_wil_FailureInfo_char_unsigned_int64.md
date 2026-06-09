# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005090`
- end: `0x180005296`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005090`
- `0x180005788`
- `0x18000586c`
- `0x1800061f8`
- `0x180007588`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000517b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000517b`

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
0x180005090  push    rbx
0x180005092  push    rbp
0x180005093  push    rsi
0x180005094  push    rdi
0x180005095  push    r14
0x180005097  sub     rsp, 20h
0x18000509b  mov     byte ptr [rdx], 0
0x18000509e  xor     bpl, bpl
0x1800050a1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800050a8  mov     r14, r8
0x1800050ab  mov     rsi, rdx
0x1800050ae  mov     rdi, rcx
0x1800050b1  test    rbx, rbx
0x1800050b4  jz      loc_180005150
0x1800050ba  call    cs:__imp_GetCurrentThreadId
0x1800050c0  mov     r8d, eax
0x1800050c3  mov     r9d, eax
0x1800050c6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800050d0  shr     r8, 2
0x1800050d4  mul     r8
0x1800050d7  shr     rdx, 3
0x1800050db  lea     rcx, [rdx+rdx*4]
0x1800050df  add     rcx, rcx
0x1800050e2  sub     r8, rcx
0x1800050e5  mov     rbx, [rbx+r8*8]
0x1800050e9  jmp     short loc_1800050F4
0x1800050eb  cmp     [rbx], r9d
0x1800050ee  jz      short loc_18000516B
0x1800050f0  mov     rbx, [rbx+8]
0x1800050f4  test    rbx, rbx
0x1800050f7  jnz     short loc_1800050EB
0x1800050f9  test    rbx, rbx
0x1800050fc  jz      short loc_180005150
0x1800050fe  cmp     qword ptr [rbx], 0
0x180005102  jz      short loc_180005150
0x180005104  mov     [rsi], bpl
0x180005107  mov     r9, r14; unsigned __int64
0x18000510a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000510d  mov     r8, rsi; char *
0x180005110  mov     rcx, rdi; struct wil::FailureInfo *
0x180005113  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005118  test    al, al
0x18000511a  jz      short loc_180005120
0x18000511c  mov     [rdi+48h], rsi
0x180005120  mov     rbx, [rbx]
0x180005123  mov     al, [rbx+28h]
0x180005126  mov     byte ptr [rbx+28h], 1
0x18000512a  test    al, al
0x18000512c  jnz     short loc_180005147
0x18000512e  mov     rcx, [rbx+8]
0x180005132  mov     rdx, rdi
0x180005135  mov     rax, [rcx]
0x180005138  mov     rax, [rax]
0x18000513b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005140  or      bpl, al
0x180005143  mov     byte ptr [rbx+28h], 0
0x180005147  mov     rbx, [rbx+10h]
0x18000514b  test    rbx, rbx
0x18000514e  jnz     short loc_180005123
0x180005150  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005157  test    rax, rax
0x18000515a  jz      short loc_18000517B
0x18000515c  test    bpl, bpl
0x18000515f  jnz     short loc_180005171
0x180005161  test    byte ptr [rdi+4], 2
0x180005165  jnz     short loc_180005171
0x180005167  xor     ecx, ecx
0x180005169  jmp     short loc_180005173
0x18000516b  add     rbx, 10h
0x18000516f  jmp     short loc_1800050F9
0x180005171  mov     cl, 1
0x180005173  mov     rdx, rdi
0x180005176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000517b  call    cs:__imp_GetCurrentThreadId
0x180005181  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005187  cmp     ecx, eax
0x180005189  jz      loc_18000528B
0x18000518f  mov     ecx, 1
0x180005194  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000519c  inc     ecx; this
0x18000519e  cmp     ecx, 4
0x1800051a1  jge     loc_180005284
0x1800051a7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800051ad  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800051b2  mov     rbx, rax
0x1800051b5  test    rax, rax
0x1800051b8  jz      loc_18000527A
0x1800051be  cmp     qword ptr [rax+18h], 0
0x1800051c3  mov     ebp, 50h ; 'P'
0x1800051c8  mov     esi, [rax+10h]
0x1800051cb  jnz     short loc_180005202
0x1800051cd  test    esi, esi
0x1800051cf  jz      short loc_180005202
0x1800051d1  mov     edx, 190h; dwBytes
0x1800051d6  lea     ecx, [rbp-48h]; dwFlags
0x1800051d9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800051de  mov     [rbx+18h], rax
0x1800051e2  test    rax, rax
0x1800051e5  jz      short loc_180005202
0x1800051e7  mov     dword ptr [rbx+20h], 5
0x1800051ee  lea     rcx, [rax+190h]
0x1800051f5  jmp     short loc_1800051FD
0x1800051f7  mov     [rax], bp
0x1800051fa  add     rax, rbp
0x1800051fd  cmp     rax, rcx
0x180005200  jnz     short loc_1800051F7
0x180005202  mov     r9, [rbx+18h]
0x180005206  test    r9, r9
0x180005209  jz      short loc_18000527A
0x18000520b  test    esi, esi
0x18000520d  jz      short loc_180005240
0x18000520f  movzx   eax, word ptr [rbx+20h]
0x180005213  mov     rcx, r9
0x180005216  lea     rdx, [rax+rax*4]
0x18000521a  shl     rdx, 4
0x18000521e  add     rdx, r9
0x180005221  cmp     r9, rdx
0x180005224  jz      short loc_180005240
0x180005226  mov     r8d, [rbx+10h]
0x18000522a  cmp     [rcx+4], r8d
0x18000522e  jbe     short loc_180005238
0x180005230  mov     eax, [rdi+8]
0x180005233  cmp     [rcx+8], eax
0x180005236  jz      short loc_18000527A
0x180005238  add     rcx, rbp
0x18000523b  cmp     rcx, rdx
0x18000523e  jnz     short loc_18000522A
0x180005240  movzx   eax, word ptr [rbx+22h]
0x180005244  xor     edx, edx
0x180005246  movzx   ecx, word ptr [rbx+20h]
0x18000524a  inc     eax
0x18000524c  div     ecx
0x18000524e  mov     rax, [rbx+8]
0x180005252  mov     r8d, 1
0x180005258  mov     [rbx+22h], dx
0x18000525c  lock xadd [rax], r8d
0x180005261  movzx   eax, dx
0x180005264  inc     r8d; unsigned int
0x180005267  mov     rdx, rdi; struct wil::FailureInfo *
0x18000526a  lea     rcx, [rax+rax*4]
0x18000526e  shl     rcx, 4
0x180005272  add     rcx, r9; this
0x180005275  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000527a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005284  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000528b  add     rsp, 20h
0x18000528f  pop     r14
0x180005291  pop     rdi
0x180005292  pop     rsi
0x180005293  pop     rbp
0x180005294  pop     rbx
0x180005295  retn
```
