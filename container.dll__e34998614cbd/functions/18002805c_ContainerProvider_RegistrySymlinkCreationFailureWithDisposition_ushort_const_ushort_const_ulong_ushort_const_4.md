# ContainerProvider::RegistrySymlinkCreationFailureWithDisposition<ushort const *,ushort const *,ulong &,ushort const (&)[41]>(ushort const * &&,ushort const * &&,ulong &,ushort const (&)[41])

- ea: `0x18002805c`
- end: `0x1800280f9`
- name: `??$RegistrySymlinkCreationFailureWithDisposition@PEBGPEBGAEAKAEAY0CJ@$$CBG@ContainerProvider@@SAX$$QEAPEBG0AEAKAEAY0CJ@$$CBG@Z`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config`

## callers

- `0x18002abc0`

## callees

- `0x18000202c`
- `0x18000895c`
- `0x18002805c`

## string_xrefs

- `0x18002808a`: `Symlink creation failed after 2 attempts`

## pseudocode

```c
const struct _tlgProvider_t *ContainerProvider::RegistrySymlinkCreationFailureWithDisposition<unsigned short const *,unsigned short const *,unsigned long &,unsigned short const (&)[41]>(
        _QWORD *a1,
        __int64 *a2,
        int *a3,
        ...)
{
  const struct _tlgProvider_t *result; // rax
  int v7; // r9d
  __int64 v8; // rdx
  int v9; // r8d
  const wchar_t *v10; // [rsp+40h] [rbp-28h] BYREF
  __int64 v11; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v12[3]; // [rsp+50h] [rbp-18h] BYREF
  __int64 v13; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  va_list va1; // [rsp+90h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v13 = va_arg(va1, _QWORD);
  result = ContainerProvider::Provider();
  v7 = *(_DWORD *)result;
  if ( *(_DWORD *)result > 2u )
  {
    v8 = *a2;
    v9 = *a3;
    v10 = L"Symlink creation failed after 2 attempts";
    v12[0] = *a1;
    v11 = v8;
    LODWORD(v13) = v9;
    return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                                            (_DWORD)result,
                                            (unsigned int)byte_18003CDB5,
                                            v9,
                                            v7,
                                            (__int64)v12,
                                            (__int64)&v11,
                                            (__int64)va,
                                            (__int64)&v10);
  }
  return result;
}

```

## disassembly

```asm
0x18002805c  mov     [rsp+arg_0], rbx
0x180028061  mov     [rsp+arg_8], rsi
0x180028066  mov     [rsp+arg_18], r9
0x18002806b  push    rdi
0x18002806c  sub     rsp, 60h
0x180028070  mov     rbx, r8
0x180028073  mov     rdi, rdx
0x180028076  mov     rsi, rcx
0x180028079  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18002807e  mov     r9d, [rax]
0x180028081  cmp     r9d, 2
0x180028085  jbe     short loc_1800280E8
0x180028087  mov     rdx, [rdi]
0x18002808a  lea     rcx, aSymlinkCreatio; "Symlink creation failed after 2 attempt"...
0x180028091  mov     r8d, [rbx]
0x180028094  mov     [rsp+68h+var_28], rcx
0x180028099  mov     rcx, [rsi]
0x18002809c  mov     [rsp+68h+var_18], rcx
0x1800280a1  lea     rcx, [rsp+68h+var_28]
0x1800280a6  mov     [rsp+68h+var_30], rcx
0x1800280ab  lea     rcx, [rsp+68h+arg_18]
0x1800280b3  mov     [rsp+68h+var_38], rcx
0x1800280b8  lea     rcx, [rsp+68h+var_20]
0x1800280bd  mov     [rsp+68h+var_40], rcx
0x1800280c2  lea     rcx, [rsp+68h+var_18]
0x1800280c7  mov     [rsp+68h+var_48], rcx
0x1800280cc  mov     rcx, rax
0x1800280cf  mov     [rsp+68h+var_20], rdx
0x1800280d4  lea     rdx, byte_18003CDB5
0x1800280db  mov     dword ptr [rsp+68h+arg_18], r8d
0x1800280e3  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800280e8  mov     rbx, [rsp+68h+arg_0]
0x1800280ed  mov     rsi, [rsp+68h+arg_8]
0x1800280f2  add     rsp, 60h
0x1800280f6  pop     rdi
0x1800280f7  retn
```
