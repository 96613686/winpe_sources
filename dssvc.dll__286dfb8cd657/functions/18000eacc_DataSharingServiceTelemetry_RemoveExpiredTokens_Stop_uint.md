# DataSharingServiceTelemetry::RemoveExpiredTokens::Stop(uint)

- ea: `0x18000eacc`
- end: `0x18000ed67`
- name: `?Stop@RemoveExpiredTokens@DataSharingServiceTelemetry@@QEAAXI@Z`
- size: `667`
- prototype: `void __fastcall(DataSharingServiceTelemetry::RemoveExpiredTokens *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000d68c`

## callees

- `0x180001818`
- `0x180001bcc`
- `0x180005c54`
- `0x18000dd94`
- `0x18000eacc`
- `0x18000f6fc`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ecc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ecc0`

## pseudocode

```c
void __fastcall DataSharingServiceTelemetry::RemoveExpiredTokens::Stop(
        DataSharingServiceTelemetry::RemoveExpiredTokens *this,
        int a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // r9
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rcx
  const struct _tlgProvider_t *v13; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // ecx
  int v17; // [rsp+C0h] [rbp-80h] BYREF
  DWORD v18; // [rsp+C4h] [rbp-7Ch] BYREF
  int v19; // [rsp+C8h] [rbp-78h] BYREF
  int v20; // [rsp+CCh] [rbp-74h] BYREF
  int v21; // [rsp+D0h] [rbp-70h] BYREF
  int v22; // [rsp+D4h] [rbp-6Ch] BYREF
  int v23; // [rsp+D8h] [rbp-68h] BYREF
  int v24; // [rsp+DCh] [rbp-64h] BYREF
  int v25; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v27; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v29; // [rsp+100h] [rbp-40h] BYREF
  __int64 v30; // [rsp+108h] [rbp-38h] BYREF
  __int64 v31; // [rsp+110h] [rbp-30h] BYREF
  __int64 v32; // [rsp+118h] [rbp-28h] BYREF
  __int64 v33; // [rsp+120h] [rbp-20h] BYREF
  __int64 v34; // [rsp+128h] [rbp-18h] BYREF
  __int64 v35; // [rsp+130h] [rbp-10h] BYREF
  __int64 v36; // [rsp+138h] [rbp-8h] BYREF
  char v37[32]; // [rsp+140h] [rbp+0h] BYREF
  __int64 *v38; // [rsp+160h] [rbp+20h]
  __int64 v39; // [rsp+168h] [rbp+28h]
  int *v40; // [rsp+170h] [rbp+30h]
  __int64 v41; // [rsp+178h] [rbp+38h]
  DWORD *v42; // [rsp+180h] [rbp+40h]
  __int64 v43; // [rsp+188h] [rbp+48h]
  int *v44; // [rsp+190h] [rbp+50h]
  __int64 v45; // [rsp+198h] [rbp+58h]

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = DataSharingServiceProvider::Provider();
    if ( *(_DWORD *)v9 > 5u )
    {
      v29 = *((_QWORD *)v6 + 14);
      v10 = *((_QWORD *)v6 + 6);
      v23 = v6[26];
      v30 = *((_QWORD *)v6 + 12);
      v11 = *((_QWORD *)this + 34);
      v31 = *((_QWORD *)v6 + 11);
      v24 = v6[20];
      v32 = *((_QWORD *)v6 + 9);
      v25 = v6[8];
      v33 = *((_QWORD *)v6 + 3);
      v17 = *v6;
      v34 = *((_QWORD *)v6 + 16);
      v18 = v6[16];
      v35 = *((_QWORD *)v6 + 7);
      v19 = v6[2];
      v36 = 0x1000000;
      v26 = 0x1000000;
      v27 = v10;
      v21 = v6[17];
      v22 = v6[4];
      v12 = *((_QWORD *)v6 + 15);
      v20 = a2;
      v28 = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (unsigned int)&dword_180025B3C,
        v11 + 8,
        (_DWORD)v9,
        (__int64)&v26,
        (__int64)&v36,
        (__int64)&v19,
        (__int64)&v35,
        (__int64)&v18,
        (__int64)&v34,
        (__int64)&v17,
        (__int64)&v33,
        (__int64)&v25,
        (__int64)&v32,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v23,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v27,
        (__int64)&v20);
    }
  }
  else
  {
    wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v13 = DataSharingServiceProvider::Provider();
    if ( *(_DWORD *)v13 > 5u )
    {
      v19 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v18 = CurrentThreadId;
      v45 = 4;
      v43 = 4;
      v16 = *(_DWORD *)(v15 + 72);
      v26 = 0x1000000;
      v44 = &v19;
      v42 = &v18;
      v40 = &v17;
      v38 = &v26;
      v17 = v16;
      v41 = 4;
      v39 = 8;
      tlgWriteTransfer_EventWriteTransfer(v13, byte_180025AD9, v15 + 8, 0, 6, v37);
    }
  }
  wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v7,
    v8,
    v9);
}

```

## disassembly

```asm
0x18000eacc  push    rbp
0x18000eace  push    rbx
0x18000eacf  push    rsi
0x18000ead0  push    rdi
0x18000ead1  lea     rbp, [rsp-78h]
0x18000ead6  sub     rsp, 1B8h
0x18000eadd  mov     rax, cs:__security_cookie
0x18000eae4  xor     rax, rsp
0x18000eae7  mov     [rbp+90h+var_30], rax
0x18000eaeb  mov     rdi, [rcx+110h]
0x18000eaf2  mov     esi, edx
0x18000eaf4  mov     rbx, rcx
0x18000eaf7  mov     eax, [rdi+48h]
0x18000eafa  test    eax, eax
0x18000eafc  jns     loc_18000ECA5
0x18000eb02  add     rdi, 50h ; 'P'
0x18000eb06  cmp     eax, [rdi+8]
0x18000eb09  jnz     loc_18000ECA5
0x18000eb0f  test    rdi, rdi
0x18000eb12  jz      loc_18000ECA5
0x18000eb18  call    ?zInternalStop@?$ActivityBase@VDataSharingServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000eb1d  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x18000eb22  mov     r9, rax
0x18000eb25  mov     ecx, [rax]
0x18000eb27  cmp     ecx, 5
0x18000eb2a  jbe     loc_18000ED47
0x18000eb30  mov     rax, [rdi+70h]
0x18000eb34  lea     rdx, dword_180025B3C
0x18000eb3b  mov     [rbp+90h+var_D0], rax
0x18000eb3f  mov     eax, [rdi+68h]
0x18000eb42  mov     rcx, [rdi+30h]
0x18000eb46  mov     [rbp+90h+var_F8], eax
0x18000eb49  mov     rax, [rdi+60h]
0x18000eb4d  mov     [rbp+90h+var_C8], rax
0x18000eb51  mov     rax, [rdi+58h]
0x18000eb55  mov     r8, [rbx+110h]
0x18000eb5c  mov     [rbp+90h+var_C0], rax
0x18000eb60  add     r8, 8
0x18000eb64  mov     eax, [rdi+50h]
0x18000eb67  mov     [rbp+90h+var_F4], eax
0x18000eb6a  mov     rax, [rdi+48h]
0x18000eb6e  mov     [rbp+90h+var_B8], rax
0x18000eb72  mov     eax, [rdi+20h]
0x18000eb75  mov     [rbp+90h+var_F0], eax
0x18000eb78  mov     rax, [rdi+18h]
0x18000eb7c  mov     [rbp+90h+var_B0], rax
0x18000eb80  mov     eax, [rdi]
0x18000eb82  mov     [rbp+90h+var_110], eax
0x18000eb85  mov     rax, [rdi+80h]
0x18000eb8c  mov     [rbp+90h+var_A8], rax
0x18000eb90  mov     eax, [rdi+40h]
0x18000eb93  mov     [rbp+90h+var_10C], eax
0x18000eb96  mov     rax, [rdi+38h]
0x18000eb9a  mov     [rbp+90h+var_A0], rax
0x18000eb9e  mov     eax, [rdi+8]
0x18000eba1  mov     [rbp+90h+var_108], eax
0x18000eba4  mov     eax, 1000000h
0x18000eba9  mov     [rbp+90h+var_98], rax
0x18000ebad  mov     [rbp+90h+var_E8], rax
0x18000ebb1  lea     rax, [rbp+90h+var_104]
0x18000ebb5  mov     [rsp+1D0h+var_118], rax
0x18000ebbd  lea     rax, [rbp+90h+var_E0]
0x18000ebc1  mov     [rsp+1D0h+var_120], rax
0x18000ebc9  lea     rax, [rbp+90h+var_100]
0x18000ebcd  mov     [rsp+1D0h+var_128], rax
0x18000ebd5  lea     rax, [rbp+90h+var_FC]
0x18000ebd9  mov     [rsp+1D0h+var_130], rax
0x18000ebe1  lea     rax, [rbp+90h+var_D8]
0x18000ebe5  mov     [rsp+1D0h+var_138], rax
0x18000ebed  lea     rax, [rbp+90h+var_D0]
0x18000ebf1  mov     [rsp+1D0h+var_140], rax
0x18000ebf9  lea     rax, [rbp+90h+var_F8]
0x18000ebfd  mov     [rsp+1D0h+var_148], rax
0x18000ec05  lea     rax, [rbp+90h+var_C8]
0x18000ec09  mov     [rsp+1D0h+var_150], rax
0x18000ec11  lea     rax, [rbp+90h+var_C0]
0x18000ec15  mov     [rsp+1D0h+var_158], rax
0x18000ec1a  lea     rax, [rbp+90h+var_F4]
0x18000ec1e  mov     [rsp+1D0h+var_160], rax
0x18000ec23  lea     rax, [rbp+90h+var_B8]
0x18000ec27  mov     [rsp+1D0h+var_168], rax
0x18000ec2c  lea     rax, [rbp+90h+var_F0]
0x18000ec30  mov     [rsp+1D0h+var_170], rax
0x18000ec35  lea     rax, [rbp+90h+var_B0]
0x18000ec39  mov     [rsp+1D0h+var_178], rax
0x18000ec3e  lea     rax, [rbp+90h+var_110]
0x18000ec42  mov     [rsp+1D0h+var_180], rax
0x18000ec47  lea     rax, [rbp+90h+var_A8]
0x18000ec4b  mov     [rsp+1D0h+var_188], rax
0x18000ec50  lea     rax, [rbp+90h+var_10C]
0x18000ec54  mov     [rsp+1D0h+var_190], rax
0x18000ec59  lea     rax, [rbp+90h+var_A0]
0x18000ec5d  mov     [rsp+1D0h+var_198], rax
0x18000ec62  lea     rax, [rbp+90h+var_108]
0x18000ec66  mov     [rsp+1D0h+var_1A0], rax
0x18000ec6b  lea     rax, [rbp+90h+var_98]
0x18000ec6f  mov     [rbp+90h+var_E0], rcx
0x18000ec73  mov     ecx, [rdi+44h]
0x18000ec76  mov     [rbp+90h+var_100], ecx
0x18000ec79  mov     ecx, [rdi+10h]
0x18000ec7c  mov     [rsp+1D0h+var_1A8], rax
0x18000ec81  lea     rax, [rbp+90h+var_E8]
0x18000ec85  mov     [rbp+90h+var_FC], ecx
0x18000ec88  mov     rcx, [rdi+78h]
0x18000ec8c  mov     [rsp+1D0h+var_1B0], rax
0x18000ec91  mov     [rbp+90h+var_104], esi
0x18000ec94  mov     [rbp+90h+var_D8], rcx
0x18000ec98  mov     rcx, r9
0x18000ec9b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564454@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000eca0  jmp     loc_18000ED47
0x18000eca5  call    ?zInternalStop@?$ActivityBase@VDataSharingServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000ecaa  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x18000ecaf  mov     rdi, rax
0x18000ecb2  mov     ecx, [rax]
0x18000ecb4  cmp     ecx, 5
0x18000ecb7  jbe     loc_18000ED47
0x18000ecbd  mov     [rbp+90h+var_108], esi
0x18000ecc0  call    cs:__imp_GetCurrentThreadId
0x18000ecc6  mov     r8, [rbx+110h]
0x18000eccd  lea     rdx, byte_180025AD9
0x18000ecd4  mov     [rbp+90h+var_10C], eax
0x18000ecd7  xor     r9d, r9d
0x18000ecda  mov     eax, 1000000h
0x18000ecdf  mov     [rbp+90h+var_38], 4
0x18000ece7  mov     [rbp+90h+var_48], 4
0x18000ecef  mov     ecx, [r8+48h]
0x18000ecf3  add     r8, 8
0x18000ecf7  mov     [rbp+90h+var_E8], rax
0x18000ecfb  lea     rax, [rbp+90h+var_108]
0x18000ecff  mov     [rbp+90h+var_40], rax
0x18000ed03  lea     rax, [rbp+90h+var_10C]
0x18000ed07  mov     [rbp+90h+var_50], rax
0x18000ed0b  lea     rax, [rbp+90h+var_110]
0x18000ed0f  mov     [rbp+90h+var_60], rax
0x18000ed13  lea     rax, [rbp+90h+var_E8]
0x18000ed17  mov     [rbp+90h+var_70], rax
0x18000ed1b  lea     rax, [rbp+90h+var_90]
0x18000ed1f  mov     [rbp+90h+var_110], ecx
0x18000ed22  mov     rcx, rdi
0x18000ed25  mov     [rsp+1D0h+var_1A8], rax
0x18000ed2a  mov     dword ptr [rsp+1D0h+var_1B0], 6
0x18000ed32  mov     [rbp+90h+var_58], 4
0x18000ed3a  mov     [rbp+90h+var_68], 8
0x18000ed42  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ed47  mov     rcx, rbx
0x18000ed4a  call    ?IgnoreCurrentThread@?$ActivityBase@VDataSharingServiceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DataSharingServiceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000ed4f  mov     rcx, [rbp+90h+var_30]
0x18000ed53  xor     rcx, rsp; StackCookie
0x18000ed56  call    __security_check_cookie
0x18000ed5b  add     rsp, 1B8h
0x18000ed62  pop     rdi
0x18000ed63  pop     rsi
0x18000ed64  pop     rbx
0x18000ed65  pop     rbp
0x18000ed66  retn
```
