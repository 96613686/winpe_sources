# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008fb0`
- end: `0x1800091b7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180008fb0`
- `0x180009750`
- `0x180009834`
- `0x18000a2b8`
- `0x18000bba4`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008fda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000909c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008fda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000909c`

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
0x180008fb0  push    rbx
0x180008fb2  push    rbp
0x180008fb3  push    rsi
0x180008fb4  push    rdi
0x180008fb5  push    r14
0x180008fb7  sub     rsp, 20h
0x180008fbb  mov     r14, r8
0x180008fbe  mov     rsi, rdx
0x180008fc1  mov     rdi, rcx
0x180008fc4  mov     byte ptr [rdx], 0
0x180008fc7  xor     bpl, bpl
0x180008fca  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008fd1  test    rbx, rbx
0x180008fd4  jz      loc_180009070
0x180008fda  call    cs:__imp_GetCurrentThreadId
0x180008fe0  mov     r9d, eax
0x180008fe3  mov     r8d, eax
0x180008fe6  shr     r8, 2
0x180008fea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008ff4  mul     r8
0x180008ff7  shr     rdx, 3
0x180008ffb  lea     rcx, [rdx+rdx*4]
0x180008fff  add     rcx, rcx
0x180009002  sub     r8, rcx
0x180009005  mov     rbx, [rbx+r8*8]
0x180009009  jmp     short loc_180009014
0x18000900b  cmp     [rbx], r9d
0x18000900e  jz      short loc_18000908B
0x180009010  mov     rbx, [rbx+8]
0x180009014  test    rbx, rbx
0x180009017  jnz     short loc_18000900B
0x180009019  test    rbx, rbx
0x18000901c  jz      short loc_180009070
0x18000901e  cmp     qword ptr [rbx], 0
0x180009022  jz      short loc_180009070
0x180009024  mov     [rsi], bpl
0x180009027  mov     r9, r14; unsigned __int64
0x18000902a  mov     r8, rsi; char *
0x18000902d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180009030  mov     rcx, rdi; struct wil::FailureInfo *
0x180009033  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180009038  test    al, al
0x18000903a  jz      short loc_180009040
0x18000903c  mov     [rdi+48h], rsi
0x180009040  mov     rbx, [rbx]
0x180009043  mov     al, [rbx+28h]
0x180009046  mov     byte ptr [rbx+28h], 1
0x18000904a  test    al, al
0x18000904c  jnz     short loc_180009067
0x18000904e  mov     rcx, [rbx+8]
0x180009052  mov     rax, [rcx]
0x180009055  mov     rdx, rdi
0x180009058  mov     rax, [rax]
0x18000905b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009060  or      bpl, al
0x180009063  mov     byte ptr [rbx+28h], 0
0x180009067  mov     rbx, [rbx+10h]
0x18000906b  test    rbx, rbx
0x18000906e  jnz     short loc_180009043
0x180009070  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180009077  test    rax, rax
0x18000907a  jz      short loc_18000909C
0x18000907c  test    bpl, bpl
0x18000907f  jnz     short loc_180009091
0x180009081  test    byte ptr [rdi+4], 2
0x180009085  jnz     short loc_180009091
0x180009087  xor     ecx, ecx
0x180009089  jmp     short loc_180009093
0x18000908b  add     rbx, 10h
0x18000908f  jmp     short loc_180009019
0x180009091  mov     cl, 1
0x180009093  mov     rdx, rdi
0x180009096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000909b  nop
0x18000909c  call    cs:__imp_GetCurrentThreadId
0x1800090a2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800090a8  cmp     ecx, eax
0x1800090aa  jz      loc_1800091AC
0x1800090b0  mov     ecx, 1
0x1800090b5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800090bd  inc     ecx; this
0x1800090bf  cmp     ecx, 4
0x1800090c2  jge     loc_1800091A5
0x1800090c8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800090ce  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800090d3  mov     rbx, rax
0x1800090d6  test    rax, rax
0x1800090d9  jz      loc_18000919B
0x1800090df  mov     esi, [rax+10h]
0x1800090e2  mov     ebp, 50h ; 'P'
0x1800090e7  cmp     qword ptr [rax+18h], 0
0x1800090ec  jnz     short loc_180009123
0x1800090ee  test    esi, esi
0x1800090f0  jz      short loc_180009123
0x1800090f2  mov     edx, 190h; dwBytes
0x1800090f7  lea     ecx, [rbp-48h]; dwFlags
0x1800090fa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800090ff  mov     [rbx+18h], rax
0x180009103  test    rax, rax
0x180009106  jz      short loc_180009123
0x180009108  mov     dword ptr [rbx+20h], 5
0x18000910f  lea     rcx, [rax+190h]
0x180009116  jmp     short loc_18000911E
0x180009118  mov     [rax], bp
0x18000911b  add     rax, rbp
0x18000911e  cmp     rax, rcx
0x180009121  jnz     short loc_180009118
0x180009123  mov     r9, [rbx+18h]
0x180009127  test    r9, r9
0x18000912a  jz      short loc_18000919B
0x18000912c  test    esi, esi
0x18000912e  jz      short loc_180009161
0x180009130  mov     rcx, r9
0x180009133  movzx   eax, word ptr [rbx+20h]
0x180009137  lea     rdx, [rax+rax*4]
0x18000913b  shl     rdx, 4
0x18000913f  add     rdx, r9
0x180009142  cmp     r9, rdx
0x180009145  jz      short loc_180009161
0x180009147  mov     r8d, [rbx+10h]
0x18000914b  cmp     [rcx+4], r8d
0x18000914f  jbe     short loc_180009159
0x180009151  mov     eax, [rdi+8]
0x180009154  cmp     [rcx+8], eax
0x180009157  jz      short loc_18000919B
0x180009159  add     rcx, rbp
0x18000915c  cmp     rcx, rdx
0x18000915f  jnz     short loc_18000914B
0x180009161  movzx   eax, word ptr [rbx+22h]
0x180009165  inc     eax
0x180009167  movzx   ecx, word ptr [rbx+20h]
0x18000916b  xor     edx, edx
0x18000916d  div     ecx
0x18000916f  mov     [rbx+22h], dx
0x180009173  mov     rax, [rbx+8]
0x180009177  mov     r8d, 1
0x18000917d  lock xadd [rax], r8d
0x180009182  inc     r8d; unsigned int
0x180009185  movzx   eax, dx
0x180009188  lea     rcx, [rax+rax*4]
0x18000918c  shl     rcx, 4
0x180009190  add     rcx, r9; this
0x180009193  mov     rdx, rdi; struct wil::FailureInfo *
0x180009196  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000919b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800091a5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800091ac  add     rsp, 20h
0x1800091b0  pop     r14
0x1800091b2  pop     rdi
0x1800091b3  pop     rsi
0x1800091b4  pop     rbp
0x1800091b5  pop     rbx
0x1800091b6  retn
```
