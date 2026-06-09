# FontSubsettingTelemetry::CreateFontPackage::StartActivity(void)

- ea: `0x180005f70`
- end: `0x180006006`
- name: `?StartActivity@CreateFontPackage@FontSubsettingTelemetry@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(FontSubsettingTelemetry::CreateFontPackage *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002a70`

## callees

- `0x180001908`
- `0x180004004`
- `0x1800055ac`
- `0x180005f70`
- `0x180007378`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180005f91`
- `KERNEL32!GetCurrentThreadId` at `0x180005f91`

## pseudocode

```c
void __fastcall FontSubsettingTelemetry::CreateFontPackage::StartActivity(
        FontSubsettingTelemetry::CreateFontPackage *this)
{
  const struct _tlgProvider_t *v2; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v4; // r8
  int v5; // r9d
  DWORD v6; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = FontSubsettingTelemetryProvider::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = *((_QWORD *)this + 34);
    v6 = CurrentThreadId;
    v7 = 0;
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = v4 + 24, !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (_DWORD)v2,
      (unsigned int)byte_18001E4FD,
      v4 + 8,
      v5,
      (__int64)&v7,
      (__int64)&v6);
  }
  wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180005f70  mov     [rsp+arg_10], rbx
0x180005f75  push    rdi
0x180005f76  sub     rsp, 30h
0x180005f7a  mov     rbx, rcx
0x180005f7d  call    ?zInternalStart@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180005f82  call    ?Provider@FontSubsettingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontSubsettingTelemetryProvider::Provider(void)
0x180005f87  mov     rdi, rax
0x180005f8a  mov     edx, [rax]
0x180005f8c  cmp     edx, 5
0x180005f8f  jbe     short loc_180005FF4
0x180005f91  call    cs:__imp_GetCurrentThreadId
0x180005f97  mov     r8, [rbx+110h]
0x180005f9e  mov     [rsp+38h+arg_0], eax
0x180005fa2  xor     eax, eax
0x180005fa4  mov     [rsp+38h+arg_8], rax
0x180005fa9  cmp     [r8+4], al
0x180005fad  jz      short loc_180005FCA
0x180005faf  lea     r9, [r8+18h]
0x180005fb3  cmp     [r9], eax
0x180005fb6  jnz     short loc_180005FCD
0x180005fb8  cmp     [r9+4], eax
0x180005fbc  jnz     short loc_180005FCD
0x180005fbe  cmp     [r9+8], eax
0x180005fc2  jnz     short loc_180005FCD
0x180005fc4  cmp     [r9+0Ch], eax
0x180005fc8  jnz     short loc_180005FCD
0x180005fca  mov     r9, rax
0x180005fcd  lea     rax, [rsp+38h+arg_0]
0x180005fd2  add     r8, 8
0x180005fd6  mov     [rsp+38h+var_10], rax
0x180005fdb  lea     rdx, byte_18001E4FD
0x180005fe2  lea     rax, [rsp+38h+arg_8]
0x180005fe7  mov     rcx, rdi
0x180005fea  mov     [rsp+38h+var_18], rax
0x180005fef  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180005ff4  mov     rcx, rbx
0x180005ff7  mov     rbx, [rsp+38h+arg_10]
0x180005ffc  add     rsp, 30h
0x180006000  pop     rdi
0x180006001  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
