# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004dd0`
- end: `0x140004fd6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140004dd0`
- `0x140005ba0`
- `0x140005c84`
- `0x14000756c`
- `0x140007de0`
- `0x140010010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004dfa`
- `KERNEL32!GetCurrentThreadId` at `0x140004ebb`
- `KERNEL32!GetCurrentThreadId` at `0x140004dfa`
- `KERNEL32!GetCurrentThreadId` at `0x140004ebb`

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
0x140004dd0  push    rbx
0x140004dd2  push    rbp
0x140004dd3  push    rsi
0x140004dd4  push    rdi
0x140004dd5  push    r14
0x140004dd7  sub     rsp, 20h
0x140004ddb  mov     byte ptr [rdx], 0
0x140004dde  xor     bpl, bpl
0x140004de1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004de8  mov     r14, r8
0x140004deb  mov     rsi, rdx
0x140004dee  mov     rdi, rcx
0x140004df1  test    rbx, rbx
0x140004df4  jz      loc_140004E90
0x140004dfa  call    cs:__imp_GetCurrentThreadId
0x140004e00  mov     r8d, eax
0x140004e03  mov     r9d, eax
0x140004e06  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004e10  shr     r8, 2
0x140004e14  mul     r8
0x140004e17  shr     rdx, 3
0x140004e1b  lea     rcx, [rdx+rdx*4]
0x140004e1f  add     rcx, rcx
0x140004e22  sub     r8, rcx
0x140004e25  mov     rbx, [rbx+r8*8]
0x140004e29  jmp     short loc_140004E34
0x140004e2b  cmp     [rbx], r9d
0x140004e2e  jz      short loc_140004EAB
0x140004e30  mov     rbx, [rbx+8]
0x140004e34  test    rbx, rbx
0x140004e37  jnz     short loc_140004E2B
0x140004e39  test    rbx, rbx
0x140004e3c  jz      short loc_140004E90
0x140004e3e  cmp     qword ptr [rbx], 0
0x140004e42  jz      short loc_140004E90
0x140004e44  mov     [rsi], bpl
0x140004e47  mov     r9, r14; unsigned __int64
0x140004e4a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140004e4d  mov     r8, rsi; char *
0x140004e50  mov     rcx, rdi; struct wil::FailureInfo *
0x140004e53  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004e58  test    al, al
0x140004e5a  jz      short loc_140004E60
0x140004e5c  mov     [rdi+48h], rsi
0x140004e60  mov     rbx, [rbx]
0x140004e63  mov     al, [rbx+28h]
0x140004e66  mov     byte ptr [rbx+28h], 1
0x140004e6a  test    al, al
0x140004e6c  jnz     short loc_140004E87
0x140004e6e  mov     rcx, [rbx+8]
0x140004e72  mov     rdx, rdi
0x140004e75  mov     rax, [rcx]
0x140004e78  mov     rax, [rax]
0x140004e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e80  or      bpl, al
0x140004e83  mov     byte ptr [rbx+28h], 0
0x140004e87  mov     rbx, [rbx+10h]
0x140004e8b  test    rbx, rbx
0x140004e8e  jnz     short loc_140004E63
0x140004e90  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140004e97  test    rax, rax
0x140004e9a  jz      short loc_140004EBB
0x140004e9c  test    bpl, bpl
0x140004e9f  jnz     short loc_140004EB1
0x140004ea1  test    byte ptr [rdi+4], 2
0x140004ea5  jnz     short loc_140004EB1
0x140004ea7  xor     ecx, ecx
0x140004ea9  jmp     short loc_140004EB3
0x140004eab  add     rbx, 10h
0x140004eaf  jmp     short loc_140004E39
0x140004eb1  mov     cl, 1
0x140004eb3  mov     rdx, rdi
0x140004eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ebb  call    cs:__imp_GetCurrentThreadId
0x140004ec1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004ec7  cmp     ecx, eax
0x140004ec9  jz      loc_140004FCB
0x140004ecf  mov     ecx, 1
0x140004ed4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004edc  inc     ecx; this
0x140004ede  cmp     ecx, 4
0x140004ee1  jge     loc_140004FC4
0x140004ee7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004eed  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140004ef2  mov     rbx, rax
0x140004ef5  test    rax, rax
0x140004ef8  jz      loc_140004FBA
0x140004efe  cmp     qword ptr [rax+18h], 0
0x140004f03  mov     ebp, 50h ; 'P'
0x140004f08  mov     esi, [rax+10h]
0x140004f0b  jnz     short loc_140004F42
0x140004f0d  test    esi, esi
0x140004f0f  jz      short loc_140004F42
0x140004f11  mov     edx, 190h; dwBytes
0x140004f16  lea     ecx, [rbp-48h]; dwFlags
0x140004f19  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004f1e  mov     [rbx+18h], rax
0x140004f22  test    rax, rax
0x140004f25  jz      short loc_140004F42
0x140004f27  mov     dword ptr [rbx+20h], 5
0x140004f2e  lea     rcx, [rax+190h]
0x140004f35  jmp     short loc_140004F3D
0x140004f37  mov     [rax], bp
0x140004f3a  add     rax, rbp
0x140004f3d  cmp     rax, rcx
0x140004f40  jnz     short loc_140004F37
0x140004f42  mov     r9, [rbx+18h]
0x140004f46  test    r9, r9
0x140004f49  jz      short loc_140004FBA
0x140004f4b  test    esi, esi
0x140004f4d  jz      short loc_140004F80
0x140004f4f  movzx   eax, word ptr [rbx+20h]
0x140004f53  mov     rcx, r9
0x140004f56  lea     rdx, [rax+rax*4]
0x140004f5a  shl     rdx, 4
0x140004f5e  add     rdx, r9
0x140004f61  cmp     r9, rdx
0x140004f64  jz      short loc_140004F80
0x140004f66  mov     r8d, [rbx+10h]
0x140004f6a  cmp     [rcx+4], r8d
0x140004f6e  jbe     short loc_140004F78
0x140004f70  mov     eax, [rdi+8]
0x140004f73  cmp     [rcx+8], eax
0x140004f76  jz      short loc_140004FBA
0x140004f78  add     rcx, rbp
0x140004f7b  cmp     rcx, rdx
0x140004f7e  jnz     short loc_140004F6A
0x140004f80  movzx   eax, word ptr [rbx+22h]
0x140004f84  xor     edx, edx
0x140004f86  movzx   ecx, word ptr [rbx+20h]
0x140004f8a  inc     eax
0x140004f8c  div     ecx
0x140004f8e  mov     rax, [rbx+8]
0x140004f92  mov     r8d, 1
0x140004f98  mov     [rbx+22h], dx
0x140004f9c  lock xadd [rax], r8d
0x140004fa1  movzx   eax, dx
0x140004fa4  inc     r8d; unsigned int
0x140004fa7  mov     rdx, rdi; struct wil::FailureInfo *
0x140004faa  lea     rcx, [rax+rax*4]
0x140004fae  shl     rcx, 4
0x140004fb2  add     rcx, r9; this
0x140004fb5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140004fba  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004fc4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004fcb  add     rsp, 20h
0x140004fcf  pop     r14
0x140004fd1  pop     rdi
0x140004fd2  pop     rsi
0x140004fd3  pop     rbp
0x140004fd4  pop     rbx
0x140004fd5  retn
```
