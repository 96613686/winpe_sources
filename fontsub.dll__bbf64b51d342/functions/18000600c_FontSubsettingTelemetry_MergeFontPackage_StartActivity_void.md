# FontSubsettingTelemetry::MergeFontPackage::StartActivity(void)

- ea: `0x18000600c`
- end: `0x1800060a2`
- name: `?StartActivity@MergeFontPackage@FontSubsettingTelemetry@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(FontSubsettingTelemetry::MergeFontPackage *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002c80`

## callees

- `0x180001908`
- `0x180004004`
- `0x1800055ac`
- `0x18000600c`
- `0x180007378`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000602d`
- `KERNEL32!GetCurrentThreadId` at `0x18000602d`

## pseudocode

```c
void __fastcall FontSubsettingTelemetry::MergeFontPackage::StartActivity(
        FontSubsettingTelemetry::MergeFontPackage *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  int v6; // r9d
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = FontSubsettingTelemetryProvider::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u )
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
      (unsigned int)&dword_18001E6F4,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&v7);
  }
  wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x18000600c  mov     [rsp+arg_10], rbx
0x180006011  push    rdi
0x180006012  sub     rsp, 30h
0x180006016  mov     rbx, rcx
0x180006019  call    ?zInternalStart@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000601e  call    ?Provider@FontSubsettingTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; FontSubsettingTelemetryProvider::Provider(void)
0x180006023  mov     rdi, rax
0x180006026  mov     edx, [rax]
0x180006028  cmp     edx, 5
0x18000602b  jbe     short loc_180006090
0x18000602d  call    cs:__imp_GetCurrentThreadId
0x180006033  mov     r8, [rbx+110h]
0x18000603a  mov     [rsp+38h+arg_0], eax
0x18000603e  xor     eax, eax
0x180006040  mov     [rsp+38h+arg_8], rax
0x180006045  cmp     [r8+4], al
0x180006049  jz      short loc_180006066
0x18000604b  lea     r9, [r8+18h]
0x18000604f  cmp     [r9], eax
0x180006052  jnz     short loc_180006069
0x180006054  cmp     [r9+4], eax
0x180006058  jnz     short loc_180006069
0x18000605a  cmp     [r9+8], eax
0x18000605e  jnz     short loc_180006069
0x180006060  cmp     [r9+0Ch], eax
0x180006064  jnz     short loc_180006069
0x180006066  mov     r9, rax
0x180006069  lea     rax, [rsp+38h+arg_0]
0x18000606e  add     r8, 8
0x180006072  mov     [rsp+38h+var_10], rax
0x180006077  lea     rdx, dword_18001E6F4
0x18000607e  lea     rax, [rsp+38h+arg_8]
0x180006083  mov     rcx, rdi
0x180006086  mov     [rsp+38h+var_18], rax
0x18000608b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180006090  mov     rcx, rbx
0x180006093  mov     rbx, [rsp+38h+arg_10]
0x180006098  add     rsp, 30h
0x18000609c  pop     rdi
0x18000609d  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
