# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,uint)

- ea: `0x1000a6c0`
- end: `0x1000a8e9`
- name: `?GetContextAndNotifyFailure@details@wil@@YGXPAUFailureInfo@2@PADI@Z`
- size: `553`
- prototype: `void(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x10008950`
- `0x1000a370`
- `0x1000a550`
- `0x1000a5f0`
- `0x1000a6c0`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000a70a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000a7d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000a70a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000a7d0`

## pseudocode

```c
void __userpurge wil::details::GetContextAndNotifyFailure(
        unsigned int a1@<eax>,
        wil::details *this,
        struct wil::FailureInfo *a3,
        struct wil::details::ThreadFailureCallbackHolder *a4,
        unsigned int a5)
{
  char v5; // dl
  int v6; // ebx
  DWORD CurrentThreadId; // esi
  _DWORD *v8; // ecx
  int *v9; // ebx
  wil::details *v10; // ecx
  int v11; // ebx
  char v12; // al
  DWORD v13; // eax
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // eax
  struct wil::details_abi::ThreadLocalData *v15; // esi
  bool v16; // zf
  int v17; // eax
  _WORD *v18; // eax
  _WORD *v19; // ecx
  int v20; // edi
  int v21; // ecx
  int v22; // edx
  unsigned int v23; // eax
  char *v24; // [esp+0h] [ebp-24h]
  wil::details *v25; // [esp+0h] [ebp-24h]
  unsigned int v26; // [esp+4h] [ebp-20h]
  unsigned int v27; // [esp+4h] [ebp-20h]
  unsigned int v28; // [esp+8h] [ebp-1Ch]
  int v29; // [esp+10h] [ebp-14h]
  char v30; // [esp+17h] [ebp-Dh]

  v5 = 0;
  v30 = 0;
  *(_BYTE *)a3 = 0;
  v6 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    a1 = (CurrentThreadId >> 2) / 0xA;
    v8 = *(_DWORD **)(v6 + 4 * ((CurrentThreadId >> 2) % 0xA));
    if ( v8 )
    {
      while ( *v8 != CurrentThreadId )
      {
        v8 = (_DWORD *)v8[1];
        if ( !v8 )
          goto LABEL_5;
      }
      v9 = v8 + 2;
    }
    else
    {
LABEL_5:
      v9 = 0;
    }
    if ( v9 && *v9 )
    {
      *(_BYTE *)a3 = 0;
      LOBYTE(a1) = wil::details::ThreadFailureCallbackHolder::GetThreadContext(a3, a4, v24, v26);
      v10 = this;
      if ( (_BYTE)a1 )
        *((_DWORD *)this + 12) = a3;
      v11 = *v9;
      do
      {
        v12 = *(_BYTE *)(v11 + 20);
        *(_BYTE *)(v11 + 20) = 1;
        if ( v12 )
        {
          v5 = v30;
        }
        else
        {
          LOWORD(a1) = (***(int (__thiscall ****)(_DWORD, wil::details *))(v11 + 4))(*(_DWORD *)(v11 + 4), v10);
          v5 = a1 | v30;
          *(_BYTE *)(v11 + 20) = 0;
          v30 |= a1;
        }
        v11 = *(_DWORD *)(v11 + 8);
        v10 = this;
      }
      while ( v11 );
    }
    else
    {
      v5 = 0;
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v5 || (*((_BYTE *)this + 4) & 2) != 0 )
      LOWORD(a1) = 1;
    else
      LOBYTE(a1) = 0;
    wil::details::g_pfnTelemetryCallback(wil::details::g_pfnTelemetryCallback, (_WORD)a1, this);
  }
  v13 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v13 )
  {
    if ( _InterlockedIncrement(&`wil::SetLastError'::`5'::depth) < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v13;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache((wil::details_abi *)v24, v26);
      v15 = ThreadLocalDataCache;
      if ( ThreadLocalDataCache )
      {
        v16 = *((_DWORD *)ThreadLocalDataCache + 4) == 0;
        v17 = *((_DWORD *)ThreadLocalDataCache + 3);
        v29 = *((_DWORD *)v15 + 3);
        if ( v16 && v17 )
        {
          v18 = wil::details::ProcessHeapAlloc(v25, v27, v28);
          *((_DWORD *)v15 + 4) = v18;
          if ( v18 )
          {
            v19 = v18 + 110;
            *((_DWORD *)v15 + 5) = 5;
            do
            {
              *v18 = 44;
              v18 += 22;
            }
            while ( v18 != v19 );
          }
          v17 = v29;
        }
        v20 = *((_DWORD *)v15 + 4);
        if ( v20 )
        {
          if ( !v17 || (v21 = *((_DWORD *)v15 + 4), v22 = v20 + 44 * *((unsigned __int16 *)v15 + 10), v20 == v22) )
          {
LABEL_40:
            v23 = ((unsigned int)*((unsigned __int16 *)v15 + 11) + 1) % *((unsigned __int16 *)v15 + 10);
            *((_WORD *)v15 + 11) = v23;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v20 + 44 * v23),
              this,
              _InterlockedIncrement(*((volatile signed __int32 **)v15 + 2)));
          }
          else
          {
            while ( *(_DWORD *)(v21 + 4) <= *((_DWORD *)v15 + 3) || *(_DWORD *)(v21 + 8) != *((_DWORD *)this + 2) )
            {
              v21 += 44;
              if ( v21 == v22 )
              {
                v20 = *((_DWORD *)v15 + 4);
                goto LABEL_40;
              }
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
0x1000a6c0  mov     edi, edi
0x1000a6c2  push    ebp
0x1000a6c3  mov     ebp, esp
0x1000a6c5  push    0FFFFFFFFh
0x1000a6c7  push    offset ?GetContextAndNotifyFailure@details@wil@@YGXPAUFailureInfo@2@PADI@Z_SEH
0x1000a6cc  mov     eax, large fs:0
0x1000a6d2  push    eax
0x1000a6d3  sub     esp, 8
0x1000a6d6  push    ebx
0x1000a6d7  push    esi; unsigned int
0x1000a6d8  push    edi; unsigned int
0x1000a6d9  mov     eax, ___security_cookie
0x1000a6de  xor     eax, ebp
0x1000a6e0  push    eax; this
0x1000a6e1  lea     eax, [ebp+var_C]
0x1000a6e4  mov     large fs:0, eax
0x1000a6ea  mov     edi, [ebp+arg_4]
0x1000a6ed  xor     dl, dl
0x1000a6ef  mov     [ebp+var_4], 0
0x1000a6f6  mov     [ebp+var_D], dl
0x1000a6f9  mov     byte ptr [edi], 0
0x1000a6fc  mov     ebx, ?g_pThreadFailureCallbacks@details@wil@@3PAV?$ThreadLocalStorage@PAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1000a702  test    ebx, ebx
0x1000a704  jz      loc_1000A7A4
0x1000a70a  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1000a710  mov     esi, eax
0x1000a712  xor     edx, edx
0x1000a714  shr     eax, 2
0x1000a717  mov     ecx, 0Ah
0x1000a71c  div     ecx
0x1000a71e  mov     ecx, [ebx+edx*4]
0x1000a721  test    ecx, ecx
0x1000a723  jz      short loc_1000A730
0x1000a725  cmp     [ecx], esi
0x1000a727  jz      short loc_1000A78D
0x1000a729  mov     ecx, [ecx+4]
0x1000a72c  test    ecx, ecx
0x1000a72e  jnz     short loc_1000A725
0x1000a730  xor     ebx, ebx
0x1000a732  test    ebx, ebx
0x1000a734  jz      short loc_1000A7A1
0x1000a736  cmp     dword ptr [ebx], 0
0x1000a739  jz      short loc_1000A7A1
0x1000a73b  push    [ebp+arg_8]; struct wil::details::ThreadFailureCallbackHolder *
0x1000a73e  mov     ecx, [ebp+this]
0x1000a741  mov     byte ptr [edi], 0
0x1000a744  mov     edx, [ebx]
0x1000a746  push    edi; struct wil::FailureInfo *
0x1000a747  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SG_NPAUFailureInfo@3@PAV123@PADI@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,uint)
0x1000a74c  mov     ecx, [ebp+this]
0x1000a74f  test    al, al
0x1000a751  jz      short loc_1000A756
0x1000a753  mov     [ecx+30h], edi
0x1000a756  mov     ebx, [ebx]
0x1000a758  nop     dword ptr [eax+eax+00000000h]
0x1000a760  mov     al, [ebx+14h]
0x1000a763  mov     byte ptr [ebx+14h], 1
0x1000a767  test    al, al
0x1000a769  jnz     short loc_1000A792
0x1000a76b  mov     edi, [ebx+4]
0x1000a76e  push    ecx; void *
0x1000a76f  mov     eax, [edi]
0x1000a771  mov     esi, [eax]
0x1000a773  mov     ecx, esi
0x1000a775  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000a77b  mov     ecx, edi
0x1000a77d  call    esi
0x1000a77f  mov     dl, [ebp+var_D]
0x1000a782  or      dl, al
0x1000a784  mov     byte ptr [ebx+14h], 0
0x1000a788  mov     [ebp+var_D], dl
0x1000a78b  jmp     short loc_1000A795
0x1000a78d  lea     ebx, [ecx+8]
0x1000a790  jmp     short loc_1000A732
0x1000a792  mov     dl, [ebp+var_D]
0x1000a795  mov     ebx, [ebx+8]
0x1000a798  mov     ecx, [ebp+this]
0x1000a79b  test    ebx, ebx
0x1000a79d  jnz     short loc_1000A760
0x1000a79f  jmp     short loc_1000A7A4
0x1000a7a1  mov     dl, [ebp+var_D]
0x1000a7a4  mov     esi, ?g_pfnTelemetryCallback@details@wil@@3P6GX_NABUFailureInfo@2@@_EA
0x1000a7aa  mov     ebx, [ebp+this]
0x1000a7ad  test    esi, esi
0x1000a7af  jz      short loc_1000A7D0
0x1000a7b1  test    dl, dl
0x1000a7b3  jnz     short loc_1000A7BF
0x1000a7b5  test    byte ptr [ebx+4], 2
0x1000a7b9  jnz     short loc_1000A7BF
0x1000a7bb  xor     al, al
0x1000a7bd  jmp     short loc_1000A7C4
0x1000a7bf  mov     eax, 1
0x1000a7c4  push    ebx; unsigned int
0x1000a7c5  push    eax; void *
0x1000a7c6  mov     ecx, esi
0x1000a7c8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000a7ce  call    esi ; ?g_pfnTelemetryCallback@details@wil@@3P6GX_NABUFailureInfo@2@@_EA
0x1000a7d0  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1000a7d6  cmp     ?lastThread@?1??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1000a7dc  jz      loc_1000A8D5
0x1000a7e2  mov     ecx, 1
0x1000a7e7  lock xadd ?depth@?4??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1000a7ef  inc     ecx
0x1000a7f0  cmp     ecx, 4
0x1000a7f3  jge     loc_1000A8CE
0x1000a7f9  mov     ?lastThread@?1??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1000a7fe  call    ?GetThreadLocalDataCache@details_abi@wil@@YGPAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1000a803  mov     esi, eax
0x1000a805  test    esi, esi
0x1000a807  jz      loc_1000A8C4
0x1000a80d  cmp     dword ptr [esi+10h], 0
0x1000a811  mov     eax, [esi+0Ch]
0x1000a814  mov     [ebp+var_14], eax
0x1000a817  jnz     short loc_1000A85D
0x1000a819  test    eax, eax
0x1000a81b  jz      short loc_1000A85D
0x1000a81d  mov     edx, 0DCh
0x1000a822  mov     ecx, 8
0x1000a827  call    ?ProcessHeapAlloc@details@wil@@YGPAXKI@Z; wil::details::ProcessHeapAlloc(ulong,uint)
0x1000a82c  mov     [esi+10h], eax
0x1000a82f  test    eax, eax
0x1000a831  jz      short loc_1000A85A
0x1000a833  lea     ecx, [eax+0DCh]
0x1000a839  mov     dword ptr [esi+14h], 5
0x1000a840  cmp     eax, ecx
0x1000a842  jz      short loc_1000A85A
0x1000a844  mov     edx, 2Ch ; ','
0x1000a849  nop     dword ptr [eax+00000000h]
0x1000a850  mov     [eax], dx
0x1000a853  add     eax, 2Ch ; ','
0x1000a856  cmp     eax, ecx
0x1000a858  jnz     short loc_1000A850
0x1000a85a  mov     eax, [ebp+var_14]
0x1000a85d  mov     edi, [esi+10h]
0x1000a860  test    edi, edi
0x1000a862  jz      short loc_1000A8C4
0x1000a864  test    eax, eax
0x1000a866  jz      short loc_1000A897
0x1000a868  movzx   eax, word ptr [esi+14h]
0x1000a86c  mov     ecx, edi
0x1000a86e  imul    edx, eax, 2Ch ; ','
0x1000a871  add     edx, edi
0x1000a873  cmp     edi, edx
0x1000a875  jz      short loc_1000A897
0x1000a877  mov     edi, [esi+0Ch]
0x1000a87a  nop     word ptr [eax+eax+00h]
0x1000a880  cmp     [ecx+4], edi
0x1000a883  jbe     short loc_1000A88D
0x1000a885  mov     eax, [ecx+8]
0x1000a888  cmp     eax, [ebx+8]
0x1000a88b  jz      short loc_1000A8C4
0x1000a88d  add     ecx, 2Ch ; ','
0x1000a890  cmp     ecx, edx
0x1000a892  jnz     short loc_1000A880
0x1000a894  mov     edi, [esi+10h]
0x1000a897  movzx   eax, word ptr [esi+16h]
0x1000a89b  xor     edx, edx
0x1000a89d  movzx   ecx, word ptr [esi+14h]
0x1000a8a1  inc     eax
0x1000a8a2  div     ecx
0x1000a8a4  movzx   eax, dx
0x1000a8a7  mov     edx, 1
0x1000a8ac  imul    ecx, eax, 2Ch ; ','
0x1000a8af  mov     [esi+16h], ax
0x1000a8b3  mov     eax, [esi+8]
0x1000a8b6  add     ecx, edi; this
0x1000a8b8  lock xadd [eax], edx
0x1000a8bc  inc     edx
0x1000a8bd  push    edx; unsigned int
0x1000a8be  push    ebx; struct wil::FailureInfo *
0x1000a8bf  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QAEXABUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1000a8c4  mov     ?lastThread@?1??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1000a8ce  lock dec ?depth@?4??SetLastError@wil@@YGXABUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1000a8d5  mov     ecx, [ebp+var_C]
0x1000a8d8  mov     large fs:0, ecx
0x1000a8df  pop     ecx
0x1000a8e0  pop     edi
0x1000a8e1  pop     esi
0x1000a8e2  pop     ebx
0x1000a8e3  mov     esp, ebp
0x1000a8e5  pop     ebp
0x1000a8e6  retn    0Ch
0x1005f070  jmp     ds:__imp____std_terminate
0x1005f690  nop
0x1005f691  nop
0x1005f692  mov     edx, [esp-4+arg_4]
0x1005f696  lea     eax, [edx+0Ch]
0x1005f699  mov     ecx, [edx-18h]
0x1005f69c  xor     ecx, eax; StackCookie
0x1005f69e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f6a3  mov     eax, offset stru_10062AD4
0x1005f6a8  jmp     ___CxxFrameHandler3
```
