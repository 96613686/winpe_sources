# ContainerProvider::RegistrySymlinkValueFailure<ushort const *,ushort const *,long,ushort const (&)[44]>(ushort const * &&,ushort const * &&,long &&,ushort const (&)[44])

- ea: `0x1800281e8`
- end: `0x180028285`
- name: `??$RegistrySymlinkValueFailure@PEBGPEBGJAEAY0CM@$$CBG@ContainerProvider@@SAX$$QEAPEBG0$$QEAJAEAY0CM@$$CBG@Z`
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
- `0x1800281e8`

## string_xrefs

- `0x180028216`: `NtSetValueKey failed setting symlink target`

## pseudocode

```c
const struct _tlgProvider_t *ContainerProvider::RegistrySymlinkValueFailure<unsigned short const *,unsigned short const *,long,unsigned short const (&)[44]>(
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
    v10 = L"NtSetValueKey failed setting symlink target";
    v12[0] = *a1;
    v11 = v8;
    LODWORD(v13) = v9;
    return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                                            (_DWORD)result,
                                            (unsigned int)&word_18003CC6E,
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
0x1800281e8  mov     [rsp+arg_0], rbx
0x1800281ed  mov     [rsp+arg_8], rsi
0x1800281f2  mov     [rsp+arg_18], r9
0x1800281f7  push    rdi
0x1800281f8  sub     rsp, 60h
0x1800281fc  mov     rbx, r8
0x1800281ff  mov     rdi, rdx
0x180028202  mov     rsi, rcx
0x180028205  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18002820a  mov     r9d, [rax]
0x18002820d  cmp     r9d, 2
0x180028211  jbe     short loc_180028274
0x180028213  mov     rdx, [rdi]
0x180028216  lea     rcx, aNtsetvaluekeyF; "NtSetValueKey failed setting symlink ta"...
0x18002821d  mov     r8d, [rbx]
0x180028220  mov     [rsp+68h+var_28], rcx
0x180028225  mov     rcx, [rsi]
0x180028228  mov     [rsp+68h+var_18], rcx
0x18002822d  lea     rcx, [rsp+68h+var_28]
0x180028232  mov     [rsp+68h+var_30], rcx
0x180028237  lea     rcx, [rsp+68h+arg_18]
0x18002823f  mov     [rsp+68h+var_38], rcx
0x180028244  lea     rcx, [rsp+68h+var_20]
0x180028249  mov     [rsp+68h+var_40], rcx
0x18002824e  lea     rcx, [rsp+68h+var_18]
0x180028253  mov     [rsp+68h+var_48], rcx
0x180028258  mov     rcx, rax
0x18002825b  mov     [rsp+68h+var_20], rdx
0x180028260  lea     rdx, word_18003CC6E
0x180028267  mov     dword ptr [rsp+68h+arg_18], r8d
0x18002826f  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180028274  mov     rbx, [rsp+68h+arg_0]
0x180028279  mov     rsi, [rsp+68h+arg_8]
0x18002827e  add     rsp, 60h
0x180028282  pop     rdi
0x180028283  retn
```
