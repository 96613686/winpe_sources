# FileExplorerTelemetry::CabViewCopy::StartActivity(void)

- ea: `0x180011308`
- end: `0x1800113bf`
- name: `?StartActivity@CabViewCopy@FileExplorerTelemetry@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(FileExplorerTelemetry::CabViewCopy *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180010440`

## callees

- `0x18000173c`
- `0x180001f3c`
- `0x18000ff98`
- `0x180010b7c`
- `0x180011308`
- `0x180011d2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011343`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011343`

## pseudocode

```c
void __fastcall FileExplorerTelemetry::CabViewCopy::StartActivity(FileExplorerTelemetry::CabViewCopy *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  int v6; // r9d
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = FileExplorerLogging::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x200000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v5 = *((_QWORD *)this + 34);
    v7 = CurrentThreadId;
    v8 = 0;
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = v5 + 24, !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)byte_1800163BB,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&v7);
  }
  wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180011308  mov     [rsp+arg_10], rbx
0x18001130d  push    rdi
0x18001130e  sub     rsp, 30h
0x180011312  mov     rbx, rcx
0x180011315  call    ?zInternalStart@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001131a  call    ?Provider@FileExplorerLogging@@SAPEBU_tlgProvider_t@@XZ; FileExplorerLogging::Provider(void)
0x18001131f  mov     rdi, rax
0x180011322  mov     edx, [rax]
0x180011324  cmp     edx, 5
0x180011327  jbe     loc_1800113AD
0x18001132d  mov     rdx, 200000000000h
0x180011337  mov     rcx, rax
0x18001133a  call    _tlgKeywordOn
0x18001133f  test    al, al
0x180011341  jz      short loc_1800113AD
0x180011343  call    cs:__imp_GetCurrentThreadId
0x180011349  mov     r8, [rbx+110h]
0x180011350  mov     [rsp+38h+arg_0], eax
0x180011354  mov     [rsp+38h+arg_8], 0
0x18001135d  cmp     byte ptr [r8+4], 0
0x180011362  jz      short loc_180011383
0x180011364  lea     r9, [r8+18h]
0x180011368  cmp     dword ptr [r9], 0
0x18001136c  jnz     short loc_180011386
0x18001136e  cmp     dword ptr [r9+4], 0
0x180011373  jnz     short loc_180011386
0x180011375  cmp     dword ptr [r9+8], 0
0x18001137a  jnz     short loc_180011386
0x18001137c  cmp     dword ptr [r9+0Ch], 0
0x180011381  jnz     short loc_180011386
0x180011383  xor     r9d, r9d
0x180011386  lea     rax, [rsp+38h+arg_0]
0x18001138b  add     r8, 8
0x18001138f  mov     [rsp+38h+var_10], rax
0x180011394  lea     rdx, byte_1800163BB
0x18001139b  lea     rax, [rsp+38h+arg_8]
0x1800113a0  mov     rcx, rdi
0x1800113a3  mov     [rsp+38h+var_18], rax
0x1800113a8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800113ad  mov     rcx, rbx
0x1800113b0  mov     rbx, [rsp+38h+arg_10]
0x1800113b5  add     rsp, 30h
0x1800113b9  pop     rdi
0x1800113ba  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
