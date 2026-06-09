# Microsoft::IoT::ShellExtension::CTelemetryProvider::Excess_CBT_Failures<ushort *,ushort *,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,ulong &,ulong &,ulong &>(ushort * &&,ushort * &&,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,ulong &,ulong &,ulong &)

- ea: `0x18000f208`
- end: `0x18000f2fd`
- name: `??$Excess_CBT_Failures@PEAGPEAGAEA_KAEA_KAEA_KAEAKAEAKAEAK@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAX$$QEAPEAG0AEA_K11AEAK22@Z`
- size: `245`
- prototype: `const struct _tlgProvider_t *__fastcall(_QWORD *, __int64 *, __int64 *, __int64 *, __int64 *, int *, int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011068`

## callees

- `0x1800019bc`
- `0x180002398`
- `0x180008ca0`
- `0x18000f208`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
const struct _tlgProvider_t *__fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::Excess_CBT_Failures<unsigned short *,unsigned short *,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &,unsigned long &,unsigned long &,unsigned long &>(
        _QWORD *a1,
        __int64 *a2,
        __int64 *a3,
        __int64 *a4,
        __int64 *a5,
        int *a6,
        int *a7,
        int *a8)
{
  const struct _tlgProvider_t *result; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // r8d
  int v16; // r9d
  int v17; // r11d
  int v18; // edx
  __int64 v19; // rcx
  int v20; // [rsp+60h] [rbp-29h] BYREF
  int v21; // [rsp+64h] [rbp-25h] BYREF
  int v22; // [rsp+68h] [rbp-21h] BYREF
  __int64 v23; // [rsp+70h] [rbp-19h] BYREF
  __int64 v24; // [rsp+78h] [rbp-11h] BYREF
  __int64 v25; // [rsp+80h] [rbp-9h] BYREF
  __int64 v26; // [rsp+88h] [rbp-1h] BYREF
  _QWORD v27[6]; // [rsp+90h] [rbp+7h] BYREF

  result = Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider();
  if ( *(_DWORD *)result > 5u )
  {
    result = (const struct _tlgProvider_t *)tlgKeywordOn(result, 0x200000000000LL, v13, v14);
    if ( (_BYTE)result )
    {
      v18 = *a8;
      v21 = *a7;
      v20 = v18;
      v22 = *a6;
      v19 = *a5;
      v24 = *a4;
      v25 = *a3;
      v26 = *a2;
      v27[0] = *a1;
      v23 = v19;
      return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                                              v17,
                                              (unsigned int)&unk_1800201D8,
                                              v15,
                                              v16,
                                              (__int64)v27,
                                              (__int64)&v26,
                                              (__int64)&v25,
                                              (__int64)&v24,
                                              (__int64)&v23,
                                              (__int64)&v22,
                                              (__int64)&v21,
                                              (__int64)&v20);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f208  push    rbp
0x18000f20a  push    rbx
0x18000f20b  push    rsi
0x18000f20c  push    rdi
0x18000f20d  push    r14
0x18000f20f  lea     rbp, [rsp-17h]
0x18000f214  sub     rsp, 0A0h
0x18000f21b  mov     rbx, r9
0x18000f21e  mov     rdi, r8
0x18000f221  mov     rsi, rdx
0x18000f224  mov     r14, rcx
0x18000f227  call    ?Provider@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::Provider(void)
0x18000f22c  mov     r11, rax
0x18000f22f  mov     r10d, [rax]
0x18000f232  cmp     r10d, 5
0x18000f236  jbe     loc_18000F2EF
0x18000f23c  mov     rdx, 200000000000h
0x18000f246  mov     rcx, rax
0x18000f249  call    _tlgKeywordOn
0x18000f24e  test    al, al
0x18000f250  jz      loc_18000F2EF
0x18000f256  mov     rcx, [rbp+37h+arg_38]
0x18000f25a  mov     rax, [rbp+37h+arg_30]
0x18000f25e  mov     edx, [rcx]
0x18000f260  mov     ecx, [rax]
0x18000f262  mov     rax, [rbp+37h+arg_28]
0x18000f266  mov     [rbp+37h+var_5C], ecx
0x18000f269  mov     [rbp+37h+var_60], edx
0x18000f26c  lea     rdx, unk_1800201D8
0x18000f273  mov     ecx, [rax]
0x18000f275  mov     rax, [rbp+37h+arg_20]
0x18000f279  mov     [rbp+37h+var_58], ecx
0x18000f27c  mov     rcx, [rax]
0x18000f27f  mov     rax, [rbx]
0x18000f282  mov     [rbp+37h+var_48], rax
0x18000f286  mov     rax, [rdi]
0x18000f289  mov     [rbp+37h+var_40], rax
0x18000f28d  mov     rax, [rsi]
0x18000f290  mov     [rbp+37h+var_38], rax
0x18000f294  mov     rax, [r14]
0x18000f297  mov     [rbp+37h+var_30], rax
0x18000f29b  lea     rax, [rbp+37h+var_60]
0x18000f29f  mov     [rsp+0C0h+var_68], rax
0x18000f2a4  lea     rax, [rbp+37h+var_5C]
0x18000f2a8  mov     [rsp+0C0h+var_70], rax
0x18000f2ad  lea     rax, [rbp+37h+var_58]
0x18000f2b1  mov     [rsp+0C0h+var_78], rax
0x18000f2b6  lea     rax, [rbp+37h+var_50]
0x18000f2ba  mov     [rsp+0C0h+var_80], rax
0x18000f2bf  lea     rax, [rbp+37h+var_48]
0x18000f2c3  mov     [rsp+0C0h+var_88], rax
0x18000f2c8  lea     rax, [rbp+37h+var_40]
0x18000f2cc  mov     [rsp+0C0h+var_90], rax
0x18000f2d1  lea     rax, [rbp+37h+var_38]
0x18000f2d5  mov     [rsp+0C0h+var_98], rax
0x18000f2da  lea     rax, [rbp+37h+var_30]
0x18000f2de  mov     [rbp+37h+var_50], rcx
0x18000f2e2  mov     rcx, r11
0x18000f2e5  mov     [rsp+0C0h+var_A0], rax
0x18000f2ea  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapperByVal@$03@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000f2ef  add     rsp, 0A0h
0x18000f2f6  pop     r14
0x18000f2f8  pop     rdi
0x18000f2f9  pop     rsi
0x18000f2fa  pop     rbx
0x18000f2fb  pop     rbp
0x18000f2fc  retn
```
