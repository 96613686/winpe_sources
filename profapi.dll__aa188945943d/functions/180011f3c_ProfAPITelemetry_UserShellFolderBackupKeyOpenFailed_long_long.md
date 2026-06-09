# ProfAPITelemetry::UserShellFolderBackupKeyOpenFailed<long>(long &&)

- ea: `0x180011f3c`
- end: `0x180011fa2`
- name: `??$UserShellFolderBackupKeyOpenFailed@J@ProfAPITelemetry@@SAX$$QEAJ@Z`
- size: `102`
- prototype: `const struct _tlgProvider_t *__fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009488`

## callees

- `0x18000adc4`
- `0x18000b3f0`
- `0x18000c25c`
- `0x180011f3c`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall ProfAPITelemetry::UserShellFolderBackupKeyOpenFailed<long>(int *a1)
{
  const struct _tlgProvider_t *result; // rax
  __int64 v3; // r9
  int v4; // r8d
  int v5; // r9d
  int v6; // [rsp+48h] [rbp+10h] BYREF
  __int64 v7; // [rsp+50h] [rbp+18h] BYREF

  result = ProfileLogging::Provider();
  if ( *(_DWORD *)result > 5u )
  {
    result = (const struct _tlgProvider_t *)tlgKeywordOn(result, 0x400000000000LL, result, v3);
    if ( (_BYTE)result )
    {
      v6 = *a1;
      v7 = 0x1000000;
      return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                                              v4,
                                              (unsigned int)&unk_18001D4F8,
                                              v4,
                                              v5,
                                              (__int64)&v6,
                                              (__int64)&v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180011f3c  push    rbx
0x180011f3e  sub     rsp, 30h
0x180011f42  mov     rbx, rcx
0x180011f45  call    ?Provider@ProfileLogging@@SAPEBU_tlgProvider_t@@XZ; ProfileLogging::Provider(void)
0x180011f4a  mov     r8, rax
0x180011f4d  mov     edx, [rax]
0x180011f4f  cmp     edx, 5
0x180011f52  jbe     short loc_180011F9C
0x180011f54  mov     rdx, 400000000000h
0x180011f5e  mov     rcx, rax
0x180011f61  call    _tlgKeywordOn
0x180011f66  test    al, al
0x180011f68  jz      short loc_180011F9C
0x180011f6a  mov     ecx, [rbx]
0x180011f6c  lea     rax, [rsp+38h+arg_10]
0x180011f71  mov     [rsp+38h+var_10], rax
0x180011f76  lea     rdx, unk_18001D4F8
0x180011f7d  lea     rax, [rsp+38h+arg_8]
0x180011f82  mov     [rsp+38h+arg_8], ecx
0x180011f86  mov     rcx, r8
0x180011f89  mov     [rsp+38h+var_18], rax
0x180011f8e  mov     [rsp+38h+arg_10], 1000000h
0x180011f97  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180011f9c  add     rsp, 30h
0x180011fa0  pop     rbx
0x180011fa1  retn
```
