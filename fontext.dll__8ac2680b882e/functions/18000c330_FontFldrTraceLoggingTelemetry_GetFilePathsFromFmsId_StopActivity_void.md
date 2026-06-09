# FontFldrTraceLoggingTelemetry::_GetFilePathsFromFmsId::StopActivity(void)

- ea: `0x18000c330`
- end: `0x18000c55c`
- name: `?StopActivity@_GetFilePathsFromFmsId@FontFldrTraceLoggingTelemetry@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(FontFldrTraceLoggingTelemetry::_GetFilePathsFromFmsId *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180001314`
- `0x180001698`
- `0x180009328`
- `0x180009930`
- `0x18000c330`
- `0x180010420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c4fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c4fd`

## pseudocode

```c
void __fastcall FontFldrTraceLoggingTelemetry::_GetFilePathsFromFmsId::StopActivity(
        FontFldrTraceLoggingTelemetry::_GetFilePathsFromFmsId *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // r9d
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  int v16; // [rsp+C4h] [rbp-7Ch] BYREF
  int v17; // [rsp+C8h] [rbp-78h] BYREF
  int v18; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v19; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+100h] [rbp-40h] BYREF
  __int64 v26; // [rsp+108h] [rbp-38h] BYREF
  __int64 v27; // [rsp+110h] [rbp-30h] BYREF
  __int64 v28; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v29[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v30; // [rsp+150h] [rbp+10h] BYREF
  int v31; // [rsp+158h] [rbp+18h] BYREF
  __int64 v32; // [rsp+160h] [rbp+20h] BYREF
  int v33; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = FontFldrTraceLogging::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      v8 = *((_QWORD *)v4 + 6);
      v21 = *((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v32) = v4[26];
      v22 = *((_QWORD *)v4 + 12);
      v23 = *((_QWORD *)v4 + 11);
      v33 = v4[20];
      v24 = *((_QWORD *)v4 + 9);
      v15 = v4[8];
      v25 = *((_QWORD *)v4 + 3);
      v16 = *v4;
      v26 = *((_QWORD *)v4 + 16);
      v17 = v4[16];
      v27 = *((_QWORD *)v4 + 7);
      v18 = v4[2];
      v19 = v8;
      v30 = v4[17];
      v31 = v4[4];
      v20 = *((_QWORD *)v4 + 15);
      v28 = 0x1000000;
      v29[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v7,
        (unsigned int)&unk_18003B320,
        v9 + 8,
        (_DWORD)v7,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v33,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v32,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v19);
    }
  }
  else
  {
    wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = FontFldrTraceLogging::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v30 = CurrentThreadId;
      v31 = *(_DWORD *)(v13 + 72);
      v32 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)byte_18003B2C9,
        v13 + 8,
        v14,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v5,
    v6,
    v7);
}

```

## disassembly

```asm
0x18000c330  push    rbp
0x18000c332  push    rbx
0x18000c333  push    rdi
0x18000c334  lea     rbp, [rsp+10h]
0x18000c339  sub     rsp, 130h
0x18000c340  mov     rdi, [rcx+110h]
0x18000c347  mov     rbx, rcx
0x18000c34a  mov     eax, [rdi+48h]
0x18000c34d  test    eax, eax
0x18000c34f  jns     loc_18000C4E9
0x18000c355  add     rdi, 50h ; 'P'
0x18000c359  cmp     eax, [rdi+8]
0x18000c35c  jnz     loc_18000C4E9
0x18000c362  test    rdi, rdi
0x18000c365  jz      loc_18000C4E9
0x18000c36b  call    ?zInternalStop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000c370  call    ?Provider@FontFldrTraceLogging@@SAPEBU_tlgProvider_t@@XZ; FontFldrTraceLogging::Provider(void)
0x18000c375  mov     r9, rax
0x18000c378  mov     ecx, [rax]
0x18000c37a  cmp     ecx, 5
0x18000c37d  jbe     loc_18000C54A
0x18000c383  mov     rax, [rdi+70h]
0x18000c387  lea     rdx, unk_18003B320
0x18000c38e  mov     rcx, [rdi+30h]
0x18000c392  mov     [rbp+var_60], rax
0x18000c396  mov     eax, [rdi+68h]
0x18000c399  mov     r8, [rbx+110h]
0x18000c3a0  mov     dword ptr [rbp+arg_10], eax
0x18000c3a3  add     r8, 8
0x18000c3a7  mov     rax, [rdi+60h]
0x18000c3ab  mov     [rbp+var_58], rax
0x18000c3af  mov     rax, [rdi+58h]
0x18000c3b3  mov     [rbp+var_50], rax
0x18000c3b7  mov     eax, [rdi+50h]
0x18000c3ba  mov     [rbp+arg_18], eax
0x18000c3bd  mov     rax, [rdi+48h]
0x18000c3c1  mov     [rbp+var_48], rax
0x18000c3c5  mov     eax, [rdi+20h]
0x18000c3c8  mov     [rbp+var_80], eax
0x18000c3cb  mov     rax, [rdi+18h]
0x18000c3cf  mov     [rbp+var_40], rax
0x18000c3d3  mov     eax, [rdi]
0x18000c3d5  mov     [rbp+var_7C], eax
0x18000c3d8  mov     rax, [rdi+80h]
0x18000c3df  mov     [rbp+var_38], rax
0x18000c3e3  mov     eax, [rdi+40h]
0x18000c3e6  mov     [rbp+var_78], eax
0x18000c3e9  mov     rax, [rdi+38h]
0x18000c3ed  mov     [rbp+var_30], rax
0x18000c3f1  mov     eax, [rdi+8]
0x18000c3f4  mov     [rbp+var_74], eax
0x18000c3f7  lea     rax, [rbp+var_70]
0x18000c3fb  mov     [rsp+140h+var_90], rax
0x18000c403  lea     rax, [rbp+arg_0]
0x18000c407  mov     [rsp+140h+var_98], rax
0x18000c40f  lea     rax, [rbp+arg_8]
0x18000c413  mov     [rsp+140h+var_A0], rax
0x18000c41b  lea     rax, [rbp+var_68]
0x18000c41f  mov     [rsp+140h+var_A8], rax
0x18000c427  lea     rax, [rbp+var_60]
0x18000c42b  mov     [rsp+140h+var_B0], rax
0x18000c433  lea     rax, [rbp+arg_10]
0x18000c437  mov     [rsp+140h+var_B8], rax
0x18000c43f  lea     rax, [rbp+var_58]
0x18000c443  mov     [rsp+140h+var_C0], rax
0x18000c44b  lea     rax, [rbp+var_50]
0x18000c44f  mov     [rsp+140h+var_C8], rax
0x18000c454  lea     rax, [rbp+arg_18]
0x18000c458  mov     [rsp+140h+var_D0], rax
0x18000c45d  lea     rax, [rbp+var_48]
0x18000c461  mov     [rsp+140h+var_D8], rax
0x18000c466  lea     rax, [rbp+var_80]
0x18000c46a  mov     [rsp+140h+var_E0], rax
0x18000c46f  lea     rax, [rbp+var_40]
0x18000c473  mov     [rsp+140h+var_E8], rax
0x18000c478  lea     rax, [rbp+var_7C]
0x18000c47c  mov     [rsp+140h+var_F0], rax
0x18000c481  lea     rax, [rbp+var_38]
0x18000c485  mov     [rsp+140h+var_F8], rax
0x18000c48a  lea     rax, [rbp+var_78]
0x18000c48e  mov     [rsp+140h+var_100], rax
0x18000c493  lea     rax, [rbp+var_30]
0x18000c497  mov     [rsp+140h+var_108], rax
0x18000c49c  lea     rax, [rbp+var_74]
0x18000c4a0  mov     [rbp+var_70], rcx
0x18000c4a4  mov     ecx, [rdi+44h]
0x18000c4a7  mov     [rsp+140h+var_110], rax
0x18000c4ac  lea     rax, [rbp+var_28]
0x18000c4b0  mov     [rbp+arg_0], ecx
0x18000c4b3  mov     ecx, [rdi+10h]
0x18000c4b6  mov     [rbp+arg_8], ecx
0x18000c4b9  mov     rcx, [rdi+78h]
0x18000c4bd  mov     [rsp+140h+var_118], rax
0x18000c4c2  lea     rax, [rbp+var_20]
0x18000c4c6  mov     [rbp+var_68], rcx
0x18000c4ca  mov     rcx, r9
0x18000c4cd  mov     [rsp+140h+var_120], rax
0x18000c4d2  mov     [rbp+var_28], 1000000h
0x18000c4da  mov     [rbp+var_20], 0
0x18000c4e2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000c4e7  jmp     short loc_18000C54A
0x18000c4e9  call    ?zInternalStop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000c4ee  call    ?Provider@FontFldrTraceLogging@@SAPEBU_tlgProvider_t@@XZ; FontFldrTraceLogging::Provider(void)
0x18000c4f3  mov     rdi, rax
0x18000c4f6  mov     ecx, [rax]
0x18000c4f8  cmp     ecx, 5
0x18000c4fb  jbe     short loc_18000C54A
0x18000c4fd  call    cs:__imp_GetCurrentThreadId
0x18000c503  mov     r8, [rbx+110h]
0x18000c50a  lea     rdx, byte_18003B2C9
0x18000c511  mov     [rbp+arg_0], eax
0x18000c514  lea     rax, [rbp+arg_0]
0x18000c518  mov     [rsp+140h+var_110], rax
0x18000c51d  lea     rax, [rbp+arg_8]
0x18000c521  mov     [rsp+140h+var_118], rax
0x18000c526  lea     rax, [rbp+arg_10]
0x18000c52a  mov     ecx, [r8+48h]
0x18000c52e  add     r8, 8
0x18000c532  mov     [rbp+arg_8], ecx
0x18000c535  mov     rcx, rdi
0x18000c538  mov     [rsp+140h+var_120], rax
0x18000c53d  mov     [rbp+arg_10], 0
0x18000c545  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c54a  mov     rcx, rbx
0x18000c54d  add     rsp, 130h
0x18000c554  pop     rdi
0x18000c555  pop     rbx
0x18000c556  pop     rbp
0x18000c557  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
