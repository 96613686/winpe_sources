# WorkerEtwProvider::ApplyAdjustments::StartActivity(ushort const *,ushort const *)

- ea: `0x140007798`
- end: `0x1400078de`
- name: `?StartActivity@ApplyAdjustments@WorkerEtwProvider@@QEAAXPEBG0@Z`
- size: `326`
- prototype: `void __fastcall(WorkerEtwProvider::ApplyAdjustments *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140005fbc`

## callees

- `0x1400018e8`
- `0x140004ed0`
- `0x140006894`
- `0x140007798`
- `0x14000939c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400077fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400078b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400077fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400078b8`

## pseudocode

```c
void __fastcall WorkerEtwProvider::ApplyAdjustments::StartActivity(
        WorkerEtwProvider::ApplyAdjustments *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // r9d
  char *v14; // rbx
  _QWORD *Local; // rax
  const unsigned __int16 *v16; // [rsp+40h] [rbp-28h] BYREF
  __int64 v17[4]; // [rsp+48h] [rbp-20h] BYREF
  DWORD v18; // [rsp+70h] [rbp+8h] BYREF
  const unsigned __int16 *v19; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v6 = WorkerEtwProvider::Provider();
  v9 = v6;
  if ( *(_DWORD *)v6 > 5u )
  {
    v10 = *((_QWORD *)v6 + 3);
    v7 = 0x400000000000LL;
    if ( (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0 )
    {
      v8 = v10 & 0x400000000000LL;
      if ( (v10 & 0x400000000000LL) == v10 )
      {
        v19 = a3;
        v16 = a2;
        CurrentThreadId = GetCurrentThreadId();
        v12 = *((_QWORD *)this + 34);
        v18 = CurrentThreadId;
        v17[0] = 0x1000000;
        if ( !*(_BYTE *)(v12 + 4)
          || (v13 = v12 + 24, !*(_DWORD *)(v12 + 24))
          && !*(_DWORD *)(v12 + 28)
          && !*(_DWORD *)(v12 + 32)
          && !*(_DWORD *)(v12 + 36) )
        {
          v13 = 0;
        }
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v9,
          (unsigned int)&word_140038BCE,
          v12 + 8,
          v13,
          (__int64)v17,
          (__int64)&v18,
          (__int64)&v16,
          (__int64)&v19);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v14 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v7) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v8,
                          v7);
      *(_QWORD *)v14 = Local;
      if ( Local )
      {
        *((_QWORD *)v14 + 2) = *Local;
        *Local = v14;
        *((_DWORD *)v14 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v14 = 0;
    }
  }
}

```

## disassembly

```asm
0x140007798  mov     [rsp+arg_8], rbx
0x14000779d  push    rbp
0x14000779e  push    rsi
0x14000779f  push    rdi
0x1400077a0  sub     rsp, 50h
0x1400077a4  mov     rsi, r8
0x1400077a7  mov     rbp, rdx
0x1400077aa  mov     rbx, rcx
0x1400077ad  call    ?zInternalStart@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1400077b2  call    ?Provider@WorkerEtwProvider@@SAPEBU_tlgProvider_t@@XZ; WorkerEtwProvider::Provider(void)
0x1400077b7  mov     rdi, rax
0x1400077ba  mov     r9d, [rax]
0x1400077bd  cmp     r9d, 5
0x1400077c1  jbe     loc_140007885
0x1400077c7  mov     rax, [rax+18h]
0x1400077cb  mov     rdx, 400000000000h
0x1400077d5  mov     r9, [rdi+10h]
0x1400077d9  test    rdx, r9
0x1400077dc  jz      loc_140007885
0x1400077e2  mov     rcx, rax
0x1400077e5  and     rcx, rdx
0x1400077e8  cmp     rcx, rax
0x1400077eb  jnz     loc_140007885
0x1400077f1  mov     [rsp+68h+arg_18], rsi
0x1400077f9  mov     [rsp+68h+var_28], rbp
0x1400077fe  call    cs:__imp_GetCurrentThreadId
0x140007805  nop     dword ptr [rax+rax+00h]
0x14000780a  mov     r8, [rbx+110h]
0x140007811  mov     [rsp+68h+arg_0], eax
0x140007815  mov     [rsp+68h+var_20], 1000000h
0x14000781e  cmp     byte ptr [r8+4], 0
0x140007823  jz      short loc_140007844
0x140007825  lea     r9, [r8+18h]
0x140007829  cmp     dword ptr [r9], 0
0x14000782d  jnz     short loc_140007847
0x14000782f  cmp     dword ptr [r9+4], 0
0x140007834  jnz     short loc_140007847
0x140007836  cmp     dword ptr [r9+8], 0
0x14000783b  jnz     short loc_140007847
0x14000783d  cmp     dword ptr [r9+0Ch], 0
0x140007842  jnz     short loc_140007847
0x140007844  xor     r9d, r9d
0x140007847  lea     rax, [rsp+68h+arg_18]
0x14000784f  add     r8, 8
0x140007853  mov     [rsp+68h+var_30], rax
0x140007858  lea     rdx, word_140038BCE
0x14000785f  lea     rax, [rsp+68h+var_28]
0x140007864  mov     rcx, rdi
0x140007867  mov     [rsp+68h+var_38], rax
0x14000786c  lea     rax, [rsp+68h+arg_0]
0x140007871  mov     [rsp+68h+var_40], rax
0x140007876  lea     rax, [rsp+68h+var_20]
0x14000787b  mov     [rsp+68h+var_48], rax
0x140007880  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140007885  cmp     dword ptr [rbx+138h], 0
0x14000788c  jnz     short loc_1400078D0
0x14000788e  add     rbx, 120h
0x140007895  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000789d  jz      short loc_1400078C9
0x14000789f  mov     dl, 1
0x1400078a1  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1400078a6  mov     [rbx], rax
0x1400078a9  test    rax, rax
0x1400078ac  jz      short loc_1400078D0
0x1400078ae  mov     rcx, [rax]
0x1400078b1  mov     [rbx+10h], rcx
0x1400078b5  mov     [rax], rbx
0x1400078b8  call    cs:__imp_GetCurrentThreadId
0x1400078bf  nop     dword ptr [rax+rax+00h]
0x1400078c4  mov     [rbx+18h], eax
0x1400078c7  jmp     short loc_1400078D0
0x1400078c9  mov     qword ptr [rbx], 0
0x1400078d0  mov     rbx, [rsp+68h+arg_8]
0x1400078d5  add     rsp, 50h
0x1400078d9  pop     rdi
0x1400078da  pop     rsi
0x1400078db  pop     rbp
0x1400078dc  retn
```
