# Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivated<ushort *,ushort *,_GUID &,ushort const * &>(ushort * &&,ushort * &&,_GUID &,ushort const * &)

- ea: `0x18000ec88`
- end: `0x18000ed53`
- name: `??$BackgroundTaskActivated@PEAGPEAGAEAU_GUID@@AEAPEBG@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAX$$QEAPEAG0AEAU_GUID@@AEAPEBG@Z`
- size: `203`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64 *, __int64 *, __int128 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012790`

## callees

- `0x1800019bc`
- `0x180002180`
- `0x180002b10`
- `0x180008ca0`
- `0x18000ec88`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
const struct _tlgProvider_t *__fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskActivated<unsigned short *,unsigned short *,_GUID &,unsigned short const * &>(
        __int64 *a1,
        __int64 *a2,
        __int128 *a3,
        __int64 *a4)
{
  const struct _tlgProvider_t *result; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // r8d
  int v12; // r9d
  int v13; // r11d
  __int64 v14; // rcx
  __int128 v15; // xmm0
  __int64 v16; // [rsp+40h] [rbp-68h] BYREF
  __int128 *v17; // [rsp+48h] [rbp-60h] BYREF
  __int64 v18; // [rsp+50h] [rbp-58h] BYREF
  __int64 v19; // [rsp+58h] [rbp-50h] BYREF
  __int128 v20; // [rsp+60h] [rbp-48h] BYREF

  result = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider();
  if ( *(_DWORD *)result > 5u )
  {
    result = (const struct _tlgProvider_t *)tlgKeywordOn(result, 0x200000000000LL, v9, v10);
    if ( (_BYTE)result )
    {
      v14 = *a4;
      v15 = *a3;
      v17 = &v20;
      v18 = *a2;
      v19 = *a1;
      v16 = v14;
      v20 = v15;
      return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
                                              v13,
                                              (unsigned int)&dword_180020184,
                                              v11,
                                              v12,
                                              (__int64)&v19,
                                              (__int64)&v18,
                                              (__int64)&v17,
                                              (__int64)&v16);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ec88  push    rbx
0x18000ec8a  push    rsi
0x18000ec8b  push    rdi
0x18000ec8c  push    r14
0x18000ec8e  sub     rsp, 88h
0x18000ec95  mov     rax, cs:__security_cookie
0x18000ec9c  xor     rax, rsp
0x18000ec9f  mov     [rsp+0A8h+var_38], rax
0x18000eca4  mov     rbx, r9
0x18000eca7  mov     rdi, r8
0x18000ecaa  mov     rsi, rdx
0x18000ecad  mov     r14, rcx
0x18000ecb0  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x18000ecb5  mov     r11, rax
0x18000ecb8  mov     r10d, [rax]
0x18000ecbb  cmp     r10d, 5
0x18000ecbf  jbe     short loc_18000ED39
0x18000ecc1  mov     rdx, 200000000000h
0x18000eccb  mov     rcx, rax
0x18000ecce  call    _tlgKeywordOn
0x18000ecd3  test    al, al
0x18000ecd5  jz      short loc_18000ED39
0x18000ecd7  mov     rcx, [rbx]
0x18000ecda  lea     rax, [rsp+0A8h+var_48]
0x18000ecdf  movups  xmm0, xmmword ptr [rdi]
0x18000ece2  mov     [rsp+0A8h+var_60], rax
0x18000ece7  lea     rdx, dword_180020184
0x18000ecee  mov     rax, [rsi]
0x18000ecf1  mov     [rsp+0A8h+var_58], rax
0x18000ecf6  mov     rax, [r14]
0x18000ecf9  mov     [rsp+0A8h+var_50], rax
0x18000ecfe  lea     rax, [rsp+0A8h+var_68]
0x18000ed03  mov     [rsp+0A8h+var_70], rax
0x18000ed08  lea     rax, [rsp+0A8h+var_60]
0x18000ed0d  mov     [rsp+0A8h+var_78], rax
0x18000ed12  lea     rax, [rsp+0A8h+var_58]
0x18000ed17  mov     [rsp+0A8h+var_80], rax
0x18000ed1c  lea     rax, [rsp+0A8h+var_50]
0x18000ed21  mov     [rsp+0A8h+var_68], rcx
0x18000ed26  mov     rcx, r11
0x18000ed29  mov     [rsp+0A8h+var_88], rax
0x18000ed2e  movdqu  [rsp+0A8h+var_48], xmm0
0x18000ed34  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &)
0x18000ed39  mov     rcx, [rsp+0A8h+var_38]
0x18000ed3e  xor     rcx, rsp; StackCookie
0x18000ed41  call    __security_check_cookie
0x18000ed46  add     rsp, 88h
0x18000ed4d  pop     r14
0x18000ed4f  pop     rdi
0x18000ed50  pop     rsi
0x18000ed51  pop     rbx
0x18000ed52  retn
```
