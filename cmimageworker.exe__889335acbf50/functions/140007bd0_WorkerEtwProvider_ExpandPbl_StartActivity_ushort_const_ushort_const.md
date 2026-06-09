# WorkerEtwProvider::ExpandPbl::StartActivity(ushort const *,ushort const *)

- ea: `0x140007bd0`
- end: `0x140007d16`
- name: `?StartActivity@ExpandPbl@WorkerEtwProvider@@QEAAXPEBG0@Z`
- size: `326`
- prototype: `void __fastcall(WorkerEtwProvider::ExpandPbl *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400066e0`

## callees

- `0x1400018e8`
- `0x140004ed0`
- `0x140006894`
- `0x140007bd0`
- `0x14000939c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007c36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007cf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007c36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007cf0`

## pseudocode

```c
void __fastcall WorkerEtwProvider::ExpandPbl::StartActivity(
        WorkerEtwProvider::ExpandPbl *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rax
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  char *v13; // rbx
  _QWORD *Local; // rax
  int *v15; // [rsp+40h] [rbp-28h] BYREF
  __int64 v16[4]; // [rsp+48h] [rbp-20h] BYREF
  DWORD v17; // [rsp+70h] [rbp+8h] BYREF
  int *v18; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v6 = WorkerEtwProvider::Provider();
  v8 = (__int64)v6;
  if ( *(_DWORD *)v6 > 5u )
  {
    v9 = *((_QWORD *)v6 + 3);
    if ( (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0 )
    {
      v7 = v9 & 0x400000000000LL;
      if ( (v9 & 0x400000000000LL) == v9 )
      {
        v18 = (int *)a3;
        v15 = (int *)a2;
        CurrentThreadId = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v17 = CurrentThreadId;
        v16[0] = 0x1000000;
        if ( !*(_BYTE *)(v11 + 4)
          || (v12 = v11 + 24, !*(_DWORD *)(v11 + 24))
          && !*(_DWORD *)(v11 + 28)
          && !*(_DWORD *)(v11 + 32)
          && !*(_DWORD *)(v11 + 36) )
        {
          v12 = 0;
        }
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v8,
          (__int64)byte_14003925B,
          v11 + 8,
          v12,
          (__int64)v16,
          (__int64)&v17,
          &v15,
          &v18);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v13 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v7,
                          1);
      *(_QWORD *)v13 = Local;
      if ( Local )
      {
        *((_QWORD *)v13 + 2) = *Local;
        *Local = v13;
        *((_DWORD *)v13 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v13 = 0;
    }
  }
}

```

## disassembly

```asm
0x140007bd0  mov     [rsp+arg_8], rbx
0x140007bd5  push    rbp
0x140007bd6  push    rsi
0x140007bd7  push    rdi
0x140007bd8  sub     rsp, 50h
0x140007bdc  mov     rsi, r8
0x140007bdf  mov     rbp, rdx
0x140007be2  mov     rbx, rcx
0x140007be5  call    ?zInternalStart@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x140007bea  call    ?Provider@WorkerEtwProvider@@SAPEBU_tlgProvider_t@@XZ; WorkerEtwProvider::Provider(void)
0x140007bef  mov     rdi, rax
0x140007bf2  mov     r9d, [rax]
0x140007bf5  cmp     r9d, 5
0x140007bf9  jbe     loc_140007CBD
0x140007bff  mov     rax, [rax+18h]
0x140007c03  mov     rdx, 400000000000h
0x140007c0d  mov     r9, [rdi+10h]
0x140007c11  test    rdx, r9
0x140007c14  jz      loc_140007CBD
0x140007c1a  mov     rcx, rax
0x140007c1d  and     rcx, rdx
0x140007c20  cmp     rcx, rax
0x140007c23  jnz     loc_140007CBD
0x140007c29  mov     [rsp+68h+arg_18], rsi
0x140007c31  mov     [rsp+68h+var_28], rbp
0x140007c36  call    cs:__imp_GetCurrentThreadId
0x140007c3d  nop     dword ptr [rax+rax+00h]
0x140007c42  mov     r8, [rbx+110h]
0x140007c49  mov     [rsp+68h+arg_0], eax
0x140007c4d  mov     [rsp+68h+var_20], 1000000h
0x140007c56  cmp     byte ptr [r8+4], 0
0x140007c5b  jz      short loc_140007C7C
0x140007c5d  lea     r9, [r8+18h]
0x140007c61  cmp     dword ptr [r9], 0
0x140007c65  jnz     short loc_140007C7F
0x140007c67  cmp     dword ptr [r9+4], 0
0x140007c6c  jnz     short loc_140007C7F
0x140007c6e  cmp     dword ptr [r9+8], 0
0x140007c73  jnz     short loc_140007C7F
0x140007c75  cmp     dword ptr [r9+0Ch], 0
0x140007c7a  jnz     short loc_140007C7F
0x140007c7c  xor     r9d, r9d
0x140007c7f  lea     rax, [rsp+68h+arg_18]
0x140007c87  add     r8, 8
0x140007c8b  mov     [rsp+68h+var_30], rax
0x140007c90  lea     rdx, byte_14003925B
0x140007c97  lea     rax, [rsp+68h+var_28]
0x140007c9c  mov     rcx, rdi
0x140007c9f  mov     [rsp+68h+var_38], rax
0x140007ca4  lea     rax, [rsp+68h+arg_0]
0x140007ca9  mov     [rsp+68h+var_40], rax
0x140007cae  lea     rax, [rsp+68h+var_20]
0x140007cb3  mov     [rsp+68h+var_48], rax
0x140007cb8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140007cbd  cmp     dword ptr [rbx+138h], 0
0x140007cc4  jnz     short loc_140007D08
0x140007cc6  add     rbx, 120h
0x140007ccd  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140007cd5  jz      short loc_140007D01
0x140007cd7  mov     dl, 1
0x140007cd9  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140007cde  mov     [rbx], rax
0x140007ce1  test    rax, rax
0x140007ce4  jz      short loc_140007D08
0x140007ce6  mov     rcx, [rax]
0x140007ce9  mov     [rbx+10h], rcx
0x140007ced  mov     [rax], rbx
0x140007cf0  call    cs:__imp_GetCurrentThreadId
0x140007cf7  nop     dword ptr [rax+rax+00h]
0x140007cfc  mov     [rbx+18h], eax
0x140007cff  jmp     short loc_140007D08
0x140007d01  mov     qword ptr [rbx], 0
0x140007d08  mov     rbx, [rsp+68h+arg_8]
0x140007d0d  add     rsp, 50h
0x140007d11  pop     rdi
0x140007d12  pop     rsi
0x140007d13  pop     rbp
0x140007d14  retn
```
