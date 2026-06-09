# DataSharingServiceTelemetry::RemoveExpiredTokens::StopActivity(void)

- ea: `0x18000ed70`
- end: `0x18000eff2`
- name: `?StopActivity@RemoveExpiredTokens@DataSharingServiceTelemetry@@MEAAXXZ`
- size: `642`
- prototype: `void __fastcall(DataSharingServiceTelemetry::RemoveExpiredTokens *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180001818`
- `0x1800018b8`
- `0x180005c54`
- `0x18000dd94`
- `0x18000ed70`
- `0x18000f6fc`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ef52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ef52`

## pseudocode

```c
void __fastcall DataSharingServiceTelemetry::RemoveExpiredTokens::StopActivity(
        DataSharingServiceTelemetry::RemoveExpiredTokens *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const unsigned __int16 *v6; // rcx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  int v11; // ecx
  int v12; // [rsp+C0h] [rbp-80h] BYREF
  DWORD v13; // [rsp+C4h] [rbp-7Ch] BYREF
  int v14; // [rsp+C8h] [rbp-78h] BYREF
  int v15; // [rsp+CCh] [rbp-74h] BYREF
  int v16; // [rsp+D0h] [rbp-70h] BYREF
  int v17; // [rsp+D4h] [rbp-6Ch] BYREF
  int v18; // [rsp+D8h] [rbp-68h] BYREF
  int v19; // [rsp+DCh] [rbp-64h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-60h] BYREF
  const unsigned __int16 *v21; // [rsp+E8h] [rbp-58h] BYREF
  const WCHAR *v22; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+F8h] [rbp-48h] BYREF
  const WCHAR *v24; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v25; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v26; // [rsp+110h] [rbp-30h] BYREF
  const WCHAR *v27; // [rsp+118h] [rbp-28h] BYREF
  const unsigned __int16 *v28; // [rsp+120h] [rbp-20h] BYREF
  const unsigned __int16 *v29; // [rsp+128h] [rbp-18h] BYREF
  __int64 v30; // [rsp+130h] [rbp-10h] BYREF
  char v31[32]; // [rsp+140h] [rbp+0h] BYREF
  __int64 *v32; // [rsp+160h] [rbp+20h]
  __int64 v33; // [rsp+168h] [rbp+28h]
  int *v34; // [rsp+170h] [rbp+30h]
  __int64 v35; // [rsp+178h] [rbp+38h]
  DWORD *v36; // [rsp+180h] [rbp+40h]
  __int64 v37; // [rsp+188h] [rbp+48h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = DataSharingServiceProvider::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v6 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v16 = v4[26];
      v7 = *((_QWORD *)this + 34);
      v24 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v17 = v4[20];
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v18 = v4[8];
      v27 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v19 = *v4;
      v28 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v12 = v4[16];
      v29 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v13 = v4[2];
      v30 = 0x1000000;
      v20 = 0x1000000;
      v21 = v6;
      v14 = v4[17];
      v15 = v4[4];
      v22 = (const WCHAR *)*((_QWORD *)v4 + 15);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)&unk_180025D38,
        v7 + 8,
        (__int64)v5,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v13,
        &v29,
        (__int64)&v12,
        &v28,
        (__int64)&v19,
        &v27,
        (__int64)&v18,
        &v26,
        (__int64)&v17,
        &v25,
        &v24,
        (__int64)&v16,
        &v23,
        &v22,
        (__int64)&v15,
        (__int64)&v14,
        &v21);
    }
  }
  else
  {
    wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = DataSharingServiceProvider::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 34);
      v13 = CurrentThreadId;
      v37 = 4;
      v35 = 4;
      v11 = *(_DWORD *)(v10 + 72);
      v20 = 0x1000000;
      v36 = &v13;
      v34 = &v12;
      v32 = &v20;
      v12 = v11;
      v33 = 8;
      tlgWriteTransfer_EventWriteTransfer(v8, &dword_180025CE4, v10 + 8, 0, 5, v31);
    }
  }
  wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000ed70  mov     [rsp-8+arg_8], rbx
0x18000ed75  mov     [rsp-8+arg_10], rdi
0x18000ed7a  push    rbp
0x18000ed7b  lea     rbp, [rsp-60h]
0x18000ed80  sub     rsp, 1A0h
0x18000ed87  mov     rax, cs:__security_cookie
0x18000ed8e  xor     rax, rsp
0x18000ed91  mov     [rbp+60h+var_10], rax
0x18000ed95  mov     rdi, [rcx+110h]
0x18000ed9c  mov     rbx, rcx
0x18000ed9f  mov     eax, [rdi+48h]
0x18000eda2  test    eax, eax
0x18000eda4  jns     loc_18000EF3E
0x18000edaa  add     rdi, 50h ; 'P'
0x18000edae  cmp     eax, [rdi+8]
0x18000edb1  jnz     loc_18000EF3E
0x18000edb7  test    rdi, rdi
0x18000edba  jz      loc_18000EF3E
0x18000edc0  call    ?zInternalStop@?$ActivityBase@VDataSharingServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000edc5  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x18000edca  mov     r9, rax
0x18000edcd  mov     ecx, [rax]
0x18000edcf  cmp     ecx, 5
0x18000edd2  jbe     loc_18000EFC9
0x18000edd8  mov     rax, [rdi+70h]
0x18000eddc  lea     rdx, unk_180025D38
0x18000ede3  mov     rcx, [rdi+30h]
0x18000ede7  mov     [rbp+60h+var_A8], rax
0x18000edeb  mov     eax, [rdi+68h]
0x18000edee  mov     [rbp+60h+var_D0], eax
0x18000edf1  mov     rax, [rdi+60h]
0x18000edf5  mov     r8, [rbx+110h]
0x18000edfc  mov     [rbp+60h+var_A0], rax
0x18000ee00  add     r8, 8
0x18000ee04  mov     rax, [rdi+58h]
0x18000ee08  mov     [rbp+60h+var_98], rax
0x18000ee0c  mov     eax, [rdi+50h]
0x18000ee0f  mov     [rbp+60h+var_CC], eax
0x18000ee12  mov     rax, [rdi+48h]
0x18000ee16  mov     [rbp+60h+var_90], rax
0x18000ee1a  mov     eax, [rdi+20h]
0x18000ee1d  mov     [rbp+60h+var_C8], eax
0x18000ee20  mov     rax, [rdi+18h]
0x18000ee24  mov     [rbp+60h+var_88], rax
0x18000ee28  mov     eax, [rdi]
0x18000ee2a  mov     [rbp+60h+var_C4], eax
0x18000ee2d  mov     rax, [rdi+80h]
0x18000ee34  mov     [rbp+60h+var_80], rax
0x18000ee38  mov     eax, [rdi+40h]
0x18000ee3b  mov     [rbp+60h+var_E0], eax
0x18000ee3e  mov     rax, [rdi+38h]
0x18000ee42  mov     [rbp+60h+var_78], rax
0x18000ee46  mov     eax, [rdi+8]
0x18000ee49  mov     [rbp+60h+var_DC], eax
0x18000ee4c  mov     eax, 1000000h
0x18000ee51  mov     [rbp+60h+var_70], rax
0x18000ee55  mov     [rbp+60h+var_C0], rax
0x18000ee59  lea     rax, [rbp+60h+var_B8]
0x18000ee5d  mov     [rsp+1A0h+var_F0], rax
0x18000ee65  lea     rax, [rbp+60h+var_D8]
0x18000ee69  mov     [rsp+1A0h+var_F8], rax
0x18000ee71  lea     rax, [rbp+60h+var_D4]
0x18000ee75  mov     [rsp+1A0h+var_100], rax
0x18000ee7d  lea     rax, [rbp+60h+var_B0]
0x18000ee81  mov     [rsp+1A0h+var_108], rax
0x18000ee89  lea     rax, [rbp+60h+var_A8]
0x18000ee8d  mov     [rsp+1A0h+var_110], rax
0x18000ee95  lea     rax, [rbp+60h+var_D0]
0x18000ee99  mov     [rsp+1A0h+var_118], rax
0x18000eea1  lea     rax, [rbp+60h+var_A0]
0x18000eea5  mov     [rsp+1A0h+var_120], rax
0x18000eead  lea     rax, [rbp+60h+var_98]
0x18000eeb1  mov     [rsp+1A0h+var_128], rax
0x18000eeb6  lea     rax, [rbp+60h+var_CC]
0x18000eeba  mov     [rsp+1A0h+var_130], rax
0x18000eebf  lea     rax, [rbp+60h+var_90]
0x18000eec3  mov     [rsp+1A0h+var_138], rax
0x18000eec8  lea     rax, [rbp+60h+var_C8]
0x18000eecc  mov     [rsp+1A0h+var_140], rax
0x18000eed1  lea     rax, [rbp+60h+var_88]
0x18000eed5  mov     [rsp+1A0h+var_148], rax
0x18000eeda  lea     rax, [rbp+60h+var_C4]
0x18000eede  mov     [rsp+1A0h+var_150], rax
0x18000eee3  lea     rax, [rbp+60h+var_80]
0x18000eee7  mov     [rsp+1A0h+var_158], rax
0x18000eeec  lea     rax, [rbp+60h+var_E0]
0x18000eef0  mov     [rsp+1A0h+var_160], rax
0x18000eef5  lea     rax, [rbp+60h+var_78]
0x18000eef9  mov     [rsp+1A0h+var_168], rax
0x18000eefe  lea     rax, [rbp+60h+var_DC]
0x18000ef02  mov     [rbp+60h+var_B8], rcx
0x18000ef06  mov     ecx, [rdi+44h]
0x18000ef09  mov     [rsp+1A0h+var_170], rax
0x18000ef0e  lea     rax, [rbp+60h+var_70]
0x18000ef12  mov     [rbp+60h+var_D8], ecx
0x18000ef15  mov     ecx, [rdi+10h]
0x18000ef18  mov     [rbp+60h+var_D4], ecx
0x18000ef1b  mov     rcx, [rdi+78h]
0x18000ef1f  mov     [rsp+1A0h+var_178], rax
0x18000ef24  lea     rax, [rbp+60h+var_C0]
0x18000ef28  mov     [rbp+60h+var_B0], rcx
0x18000ef2c  mov     rcx, r9
0x18000ef2f  mov     [rsp+1A0h+var_180], rax
0x18000ef34  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000ef39  jmp     loc_18000EFC9
0x18000ef3e  call    ?zInternalStop@?$ActivityBase@VDataSharingServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000ef43  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x18000ef48  mov     rdi, rax
0x18000ef4b  mov     ecx, [rax]
0x18000ef4d  cmp     ecx, 5
0x18000ef50  jbe     short loc_18000EFC9
0x18000ef52  call    cs:__imp_GetCurrentThreadId
0x18000ef58  mov     r8, [rbx+110h]
0x18000ef5f  lea     rdx, dword_180025CE4
0x18000ef66  mov     [rbp+60h+var_DC], eax
0x18000ef69  xor     r9d, r9d
0x18000ef6c  mov     eax, 1000000h
0x18000ef71  mov     [rbp+60h+var_18], 4
0x18000ef79  mov     [rbp+60h+var_28], 4
0x18000ef81  mov     ecx, [r8+48h]
0x18000ef85  add     r8, 8
0x18000ef89  mov     [rbp+60h+var_C0], rax
0x18000ef8d  lea     rax, [rbp+60h+var_DC]
0x18000ef91  mov     [rbp+60h+var_20], rax
0x18000ef95  lea     rax, [rbp+60h+var_E0]
0x18000ef99  mov     [rbp+60h+var_30], rax
0x18000ef9d  lea     rax, [rbp+60h+var_C0]
0x18000efa1  mov     [rbp+60h+var_40], rax
0x18000efa5  lea     rax, [rbp+60h+var_60]
0x18000efa9  mov     [rbp+60h+var_E0], ecx
0x18000efac  mov     rcx, rdi
0x18000efaf  mov     [rsp+1A0h+var_178], rax
0x18000efb4  mov     dword ptr [rsp+1A0h+var_180], 5
0x18000efbc  mov     [rbp+60h+var_38], 8
0x18000efc4  call    _tlgWriteTransfer_EventWriteTransfer
0x18000efc9  mov     rcx, rbx
0x18000efcc  call    ?IgnoreCurrentThread@?$ActivityBase@VDataSharingServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000efd1  mov     rcx, [rbp+60h+var_10]
0x18000efd5  xor     rcx, rsp; StackCookie
0x18000efd8  call    __security_check_cookie
0x18000efdd  lea     r11, [rsp+1A0h+var_s0]
0x18000efe5  mov     rbx, [r11+18h]
0x18000efe9  mov     rdi, [r11+20h]
0x18000efed  mov     rsp, r11
0x18000eff0  pop     rbp
0x18000eff1  retn
```
