# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000bc80`
- end: `0x18000be86`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000bc80`
- `0x18000c378`
- `0x18000c45c`
- `0x18000ccc8`
- `0x18000d010`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000bcaa`
- `KERNEL32!GetCurrentThreadId` at `0x18000bd6b`
- `KERNEL32!GetCurrentThreadId` at `0x18000bcaa`
- `KERNEL32!GetCurrentThreadId` at `0x18000bd6b`

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
0x18000bc80  push    rbx
0x18000bc82  push    rbp
0x18000bc83  push    rsi
0x18000bc84  push    rdi
0x18000bc85  push    r14
0x18000bc87  sub     rsp, 20h
0x18000bc8b  mov     byte ptr [rdx], 0
0x18000bc8e  xor     bpl, bpl
0x18000bc91  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000bc98  mov     r14, r8
0x18000bc9b  mov     rsi, rdx
0x18000bc9e  mov     rdi, rcx
0x18000bca1  test    rbx, rbx
0x18000bca4  jz      loc_18000BD40
0x18000bcaa  call    cs:__imp_GetCurrentThreadId
0x18000bcb0  mov     r8d, eax
0x18000bcb3  mov     r9d, eax
0x18000bcb6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000bcc0  shr     r8, 2
0x18000bcc4  mul     r8
0x18000bcc7  shr     rdx, 3
0x18000bccb  lea     rcx, [rdx+rdx*4]
0x18000bccf  add     rcx, rcx
0x18000bcd2  sub     r8, rcx
0x18000bcd5  mov     rbx, [rbx+r8*8]
0x18000bcd9  jmp     short loc_18000BCE4
0x18000bcdb  cmp     [rbx], r9d
0x18000bcde  jz      short loc_18000BD5B
0x18000bce0  mov     rbx, [rbx+8]
0x18000bce4  test    rbx, rbx
0x18000bce7  jnz     short loc_18000BCDB
0x18000bce9  test    rbx, rbx
0x18000bcec  jz      short loc_18000BD40
0x18000bcee  cmp     qword ptr [rbx], 0
0x18000bcf2  jz      short loc_18000BD40
0x18000bcf4  mov     [rsi], bpl
0x18000bcf7  mov     r9, r14; unsigned __int64
0x18000bcfa  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000bcfd  mov     r8, rsi; char *
0x18000bd00  mov     rcx, rdi; struct wil::FailureInfo *
0x18000bd03  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000bd08  test    al, al
0x18000bd0a  jz      short loc_18000BD10
0x18000bd0c  mov     [rdi+48h], rsi
0x18000bd10  mov     rbx, [rbx]
0x18000bd13  mov     al, [rbx+28h]
0x18000bd16  mov     byte ptr [rbx+28h], 1
0x18000bd1a  test    al, al
0x18000bd1c  jnz     short loc_18000BD37
0x18000bd1e  mov     rcx, [rbx+8]
0x18000bd22  mov     rdx, rdi
0x18000bd25  mov     rax, [rcx]
0x18000bd28  mov     rax, [rax]
0x18000bd2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd30  or      bpl, al
0x18000bd33  mov     byte ptr [rbx+28h], 0
0x18000bd37  mov     rbx, [rbx+10h]
0x18000bd3b  test    rbx, rbx
0x18000bd3e  jnz     short loc_18000BD13
0x18000bd40  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000bd47  test    rax, rax
0x18000bd4a  jz      short loc_18000BD6B
0x18000bd4c  test    bpl, bpl
0x18000bd4f  jnz     short loc_18000BD61
0x18000bd51  test    byte ptr [rdi+4], 2
0x18000bd55  jnz     short loc_18000BD61
0x18000bd57  xor     ecx, ecx
0x18000bd59  jmp     short loc_18000BD63
0x18000bd5b  add     rbx, 10h
0x18000bd5f  jmp     short loc_18000BCE9
0x18000bd61  mov     cl, 1
0x18000bd63  mov     rdx, rdi
0x18000bd66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd6b  call    cs:__imp_GetCurrentThreadId
0x18000bd71  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000bd77  cmp     ecx, eax
0x18000bd79  jz      loc_18000BE7B
0x18000bd7f  mov     ecx, 1
0x18000bd84  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000bd8c  inc     ecx; this
0x18000bd8e  cmp     ecx, 4
0x18000bd91  jge     loc_18000BE74
0x18000bd97  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000bd9d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000bda2  mov     rbx, rax
0x18000bda5  test    rax, rax
0x18000bda8  jz      loc_18000BE6A
0x18000bdae  cmp     qword ptr [rax+18h], 0
0x18000bdb3  mov     ebp, 50h ; 'P'
0x18000bdb8  mov     esi, [rax+10h]
0x18000bdbb  jnz     short loc_18000BDF2
0x18000bdbd  test    esi, esi
0x18000bdbf  jz      short loc_18000BDF2
0x18000bdc1  mov     edx, 190h; dwBytes
0x18000bdc6  lea     ecx, [rbp-48h]; dwFlags
0x18000bdc9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000bdce  mov     [rbx+18h], rax
0x18000bdd2  test    rax, rax
0x18000bdd5  jz      short loc_18000BDF2
0x18000bdd7  mov     dword ptr [rbx+20h], 5
0x18000bdde  lea     rcx, [rax+190h]
0x18000bde5  jmp     short loc_18000BDED
0x18000bde7  mov     [rax], bp
0x18000bdea  add     rax, rbp
0x18000bded  cmp     rax, rcx
0x18000bdf0  jnz     short loc_18000BDE7
0x18000bdf2  mov     r9, [rbx+18h]
0x18000bdf6  test    r9, r9
0x18000bdf9  jz      short loc_18000BE6A
0x18000bdfb  test    esi, esi
0x18000bdfd  jz      short loc_18000BE30
0x18000bdff  movzx   eax, word ptr [rbx+20h]
0x18000be03  mov     rcx, r9
0x18000be06  lea     rdx, [rax+rax*4]
0x18000be0a  shl     rdx, 4
0x18000be0e  add     rdx, r9
0x18000be11  cmp     r9, rdx
0x18000be14  jz      short loc_18000BE30
0x18000be16  mov     r8d, [rbx+10h]
0x18000be1a  cmp     [rcx+4], r8d
0x18000be1e  jbe     short loc_18000BE28
0x18000be20  mov     eax, [rdi+8]
0x18000be23  cmp     [rcx+8], eax
0x18000be26  jz      short loc_18000BE6A
0x18000be28  add     rcx, rbp
0x18000be2b  cmp     rcx, rdx
0x18000be2e  jnz     short loc_18000BE1A
0x18000be30  movzx   eax, word ptr [rbx+22h]
0x18000be34  xor     edx, edx
0x18000be36  movzx   ecx, word ptr [rbx+20h]
0x18000be3a  inc     eax
0x18000be3c  div     ecx
0x18000be3e  mov     rax, [rbx+8]
0x18000be42  mov     r8d, 1
0x18000be48  mov     [rbx+22h], dx
0x18000be4c  lock xadd [rax], r8d
0x18000be51  movzx   eax, dx
0x18000be54  inc     r8d; unsigned int
0x18000be57  mov     rdx, rdi; struct wil::FailureInfo *
0x18000be5a  lea     rcx, [rax+rax*4]
0x18000be5e  shl     rcx, 4
0x18000be62  add     rcx, r9; this
0x18000be65  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000be6a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000be74  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000be7b  add     rsp, 20h
0x18000be7f  pop     r14
0x18000be81  pop     rdi
0x18000be82  pop     rsi
0x18000be83  pop     rbp
0x18000be84  pop     rbx
0x18000be85  retn
```
