# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000ad10`
- end: `0x18000af17`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000ad10`
- `0x18000be3c`
- `0x18000bf20`
- `0x18000d178`
- `0x18000ed44`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000adfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000adfc`

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
0x18000ad10  push    rbx
0x18000ad12  push    rbp
0x18000ad13  push    rsi
0x18000ad14  push    rdi
0x18000ad15  push    r14
0x18000ad17  sub     rsp, 20h
0x18000ad1b  mov     r14, r8
0x18000ad1e  mov     rsi, rdx
0x18000ad21  mov     rdi, rcx
0x18000ad24  mov     byte ptr [rdx], 0
0x18000ad27  xor     bpl, bpl
0x18000ad2a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ad31  test    rbx, rbx
0x18000ad34  jz      loc_18000ADD0
0x18000ad3a  call    cs:__imp_GetCurrentThreadId
0x18000ad40  mov     r9d, eax
0x18000ad43  mov     r8d, eax
0x18000ad46  shr     r8, 2
0x18000ad4a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ad54  mul     r8
0x18000ad57  shr     rdx, 3
0x18000ad5b  lea     rcx, [rdx+rdx*4]
0x18000ad5f  add     rcx, rcx
0x18000ad62  sub     r8, rcx
0x18000ad65  mov     rbx, [rbx+r8*8]
0x18000ad69  jmp     short loc_18000AD74
0x18000ad6b  cmp     [rbx], r9d
0x18000ad6e  jz      short loc_18000ADEB
0x18000ad70  mov     rbx, [rbx+8]
0x18000ad74  test    rbx, rbx
0x18000ad77  jnz     short loc_18000AD6B
0x18000ad79  test    rbx, rbx
0x18000ad7c  jz      short loc_18000ADD0
0x18000ad7e  cmp     qword ptr [rbx], 0
0x18000ad82  jz      short loc_18000ADD0
0x18000ad84  mov     [rsi], bpl
0x18000ad87  mov     r9, r14; unsigned __int64
0x18000ad8a  mov     r8, rsi; char *
0x18000ad8d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000ad90  mov     rcx, rdi; struct wil::FailureInfo *
0x18000ad93  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000ad98  test    al, al
0x18000ad9a  jz      short loc_18000ADA0
0x18000ad9c  mov     [rdi+48h], rsi
0x18000ada0  mov     rbx, [rbx]
0x18000ada3  mov     al, [rbx+28h]
0x18000ada6  mov     byte ptr [rbx+28h], 1
0x18000adaa  test    al, al
0x18000adac  jnz     short loc_18000ADC7
0x18000adae  mov     rcx, [rbx+8]
0x18000adb2  mov     rax, [rcx]
0x18000adb5  mov     rdx, rdi
0x18000adb8  mov     rax, [rax]
0x18000adbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adc0  or      bpl, al
0x18000adc3  mov     byte ptr [rbx+28h], 0
0x18000adc7  mov     rbx, [rbx+10h]
0x18000adcb  test    rbx, rbx
0x18000adce  jnz     short loc_18000ADA3
0x18000add0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000add7  test    rax, rax
0x18000adda  jz      short loc_18000ADFC
0x18000addc  test    bpl, bpl
0x18000addf  jnz     short loc_18000ADF1
0x18000ade1  test    byte ptr [rdi+4], 2
0x18000ade5  jnz     short loc_18000ADF1
0x18000ade7  xor     ecx, ecx
0x18000ade9  jmp     short loc_18000ADF3
0x18000adeb  add     rbx, 10h
0x18000adef  jmp     short loc_18000AD79
0x18000adf1  mov     cl, 1
0x18000adf3  mov     rdx, rdi
0x18000adf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adfb  nop
0x18000adfc  call    cs:__imp_GetCurrentThreadId
0x18000ae02  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000ae08  cmp     ecx, eax
0x18000ae0a  jz      loc_18000AF0C
0x18000ae10  mov     ecx, 1
0x18000ae15  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000ae1d  inc     ecx; this
0x18000ae1f  cmp     ecx, 4
0x18000ae22  jge     loc_18000AF05
0x18000ae28  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000ae2e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000ae33  mov     rbx, rax
0x18000ae36  test    rax, rax
0x18000ae39  jz      loc_18000AEFB
0x18000ae3f  mov     esi, [rax+10h]
0x18000ae42  mov     ebp, 50h ; 'P'
0x18000ae47  cmp     qword ptr [rax+18h], 0
0x18000ae4c  jnz     short loc_18000AE83
0x18000ae4e  test    esi, esi
0x18000ae50  jz      short loc_18000AE83
0x18000ae52  mov     edx, 190h; dwBytes
0x18000ae57  lea     ecx, [rbp-48h]; dwFlags
0x18000ae5a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ae5f  mov     [rbx+18h], rax
0x18000ae63  test    rax, rax
0x18000ae66  jz      short loc_18000AE83
0x18000ae68  mov     dword ptr [rbx+20h], 5
0x18000ae6f  lea     rcx, [rax+190h]
0x18000ae76  jmp     short loc_18000AE7E
0x18000ae78  mov     [rax], bp
0x18000ae7b  add     rax, rbp
0x18000ae7e  cmp     rax, rcx
0x18000ae81  jnz     short loc_18000AE78
0x18000ae83  mov     r9, [rbx+18h]
0x18000ae87  test    r9, r9
0x18000ae8a  jz      short loc_18000AEFB
0x18000ae8c  test    esi, esi
0x18000ae8e  jz      short loc_18000AEC1
0x18000ae90  mov     rcx, r9
0x18000ae93  movzx   eax, word ptr [rbx+20h]
0x18000ae97  lea     rdx, [rax+rax*4]
0x18000ae9b  shl     rdx, 4
0x18000ae9f  add     rdx, r9
0x18000aea2  cmp     r9, rdx
0x18000aea5  jz      short loc_18000AEC1
0x18000aea7  mov     r8d, [rbx+10h]
0x18000aeab  cmp     [rcx+4], r8d
0x18000aeaf  jbe     short loc_18000AEB9
0x18000aeb1  mov     eax, [rdi+8]
0x18000aeb4  cmp     [rcx+8], eax
0x18000aeb7  jz      short loc_18000AEFB
0x18000aeb9  add     rcx, rbp
0x18000aebc  cmp     rcx, rdx
0x18000aebf  jnz     short loc_18000AEAB
0x18000aec1  movzx   eax, word ptr [rbx+22h]
0x18000aec5  inc     eax
0x18000aec7  movzx   ecx, word ptr [rbx+20h]
0x18000aecb  xor     edx, edx
0x18000aecd  div     ecx
0x18000aecf  mov     [rbx+22h], dx
0x18000aed3  mov     rax, [rbx+8]
0x18000aed7  mov     r8d, 1
0x18000aedd  lock xadd [rax], r8d
0x18000aee2  inc     r8d; unsigned int
0x18000aee5  movzx   eax, dx
0x18000aee8  lea     rcx, [rax+rax*4]
0x18000aeec  shl     rcx, 4
0x18000aef0  add     rcx, r9; this
0x18000aef3  mov     rdx, rdi; struct wil::FailureInfo *
0x18000aef6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000aefb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000af05  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000af0c  add     rsp, 20h
0x18000af10  pop     r14
0x18000af12  pop     rdi
0x18000af13  pop     rsi
0x18000af14  pop     rbp
0x18000af15  pop     rbx
0x18000af16  retn
```
