# FileExplorerTelemetry::CabViewCopy::StopActivity(void)

- ea: `0x1800115e0`
- end: `0x180011804`
- name: `?StopActivity@CabViewCopy@FileExplorerTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(FileExplorerTelemetry::CabViewCopy *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001010`
- `0x1800017ac`
- `0x180001f3c`
- `0x180010410`
- `0x180010b7c`
- `0x1800115e0`
- `0x180011d9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800117a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800117a5`

## pseudocode

```c
void __fastcall FileExplorerTelemetry::CabViewCopy::StopActivity(FileExplorerTelemetry::CabViewCopy *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // r9d
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v18; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v19; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v20; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v24; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = FileExplorerLogging::Provider();
    v8 = v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL) )
    {
      v9 = *((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v19 = *((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v9;
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v8,
        (unsigned int)word_18001644A,
        v10 + 8,
        (_DWORD)v8,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        (__int64)&v25,
        (__int64)&v16,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v23,
        (__int64)&v30,
        (__int64)&v22,
        (__int64)&v29,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v28,
        (__int64)&v19,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = FileExplorerLogging::Provider();
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&word_1800163FE,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x1800115e0  push    rbp
0x1800115e2  push    rbx
0x1800115e3  push    rdi
0x1800115e4  lea     rbp, [rsp-47h]
0x1800115e9  sub     rsp, 100h
0x1800115f0  mov     rdi, [rcx+110h]
0x1800115f7  mov     rbx, rcx
0x1800115fa  mov     eax, [rdi+48h]
0x1800115fd  test    eax, eax
0x1800115ff  jns     loc_18001177B
0x180011605  add     rdi, 50h ; 'P'
0x180011609  cmp     eax, [rdi+8]
0x18001160c  jnz     loc_18001177B
0x180011612  test    rdi, rdi
0x180011615  jz      loc_18001177B
0x18001161b  call    ?zInternalStop@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180011620  call    ?Provider@FileExplorerLogging@@SAPEBU_tlgProvider_t@@XZ; FileExplorerLogging::Provider(void)
0x180011625  mov     r9, rax
0x180011628  mov     ecx, [rax]
0x18001162a  cmp     ecx, 5
0x18001162d  jbe     loc_1800117F2
0x180011633  mov     rdx, 200000000000h
0x18001163d  mov     rcx, rax
0x180011640  call    _tlgKeywordOn
0x180011645  test    al, al
0x180011647  jz      loc_1800117F2
0x18001164d  mov     rax, [rdi+70h]
0x180011651  lea     rdx, word_18001644A
0x180011658  mov     rcx, [rdi+78h]
0x18001165c  mov     r8, [rbx+110h]
0x180011663  mov     [rbp+57h+var_60], rax
0x180011667  add     r8, 8
0x18001166b  mov     eax, [rdi+68h]
0x18001166e  mov     [rbp+57h+arg_0], eax
0x180011671  mov     rax, [rdi+60h]
0x180011675  mov     [rbp+57h+var_58], rax
0x180011679  mov     rax, [rdi+58h]
0x18001167d  mov     [rbp+57h+var_50], rax
0x180011681  mov     eax, [rdi+50h]
0x180011684  mov     [rbp+57h+arg_8], eax
0x180011687  mov     rax, [rdi+48h]
0x18001168b  mov     [rbp+57h+var_48], rax
0x18001168f  mov     eax, [rdi+20h]
0x180011692  mov     dword ptr [rbp+57h+arg_10], eax
0x180011695  mov     rax, [rdi+18h]
0x180011699  mov     [rbp+57h+var_40], rax
0x18001169d  mov     eax, [rdi]
0x18001169f  mov     [rbp+57h+arg_18], eax
0x1800116a2  mov     rax, [rdi+80h]
0x1800116a9  mov     [rbp+57h+var_38], rax
0x1800116ad  mov     eax, [rdi+40h]
0x1800116b0  mov     [rbp+57h+var_70], eax
0x1800116b3  mov     rax, [rdi+38h]
0x1800116b7  mov     [rbp+57h+var_30], rax
0x1800116bb  mov     eax, [rdi+8]
0x1800116be  mov     [rbp+57h+var_6C], eax
0x1800116c1  lea     rax, [rbp+57h+var_68]
0x1800116c5  mov     [rsp+110h+var_78], rax
0x1800116cd  lea     rax, [rbp+57h+var_60]
0x1800116d1  mov     [rsp+110h+var_80], rax
0x1800116d9  lea     rax, [rbp+57h+arg_0]
0x1800116dd  mov     [rsp+110h+var_88], rax
0x1800116e5  lea     rax, [rbp+57h+var_58]
0x1800116e9  mov     [rsp+110h+var_90], rax
0x1800116f1  lea     rax, [rbp+57h+var_50]
0x1800116f5  mov     [rsp+110h+var_98], rax
0x1800116fa  lea     rax, [rbp+57h+arg_8]
0x1800116fe  mov     [rsp+110h+var_A0], rax
0x180011703  lea     rax, [rbp+57h+var_48]
0x180011707  mov     [rsp+110h+var_A8], rax
0x18001170c  lea     rax, [rbp+57h+arg_10]
0x180011710  mov     [rsp+110h+var_B0], rax
0x180011715  lea     rax, [rbp+57h+var_40]
0x180011719  mov     [rsp+110h+var_B8], rax
0x18001171e  lea     rax, [rbp+57h+arg_18]
0x180011722  mov     [rsp+110h+var_C0], rax
0x180011727  lea     rax, [rbp+57h+var_38]
0x18001172b  mov     [rsp+110h+var_C8], rax
0x180011730  lea     rax, [rbp+57h+var_70]
0x180011734  mov     [rsp+110h+var_D0], rax
0x180011739  lea     rax, [rbp+57h+var_30]
0x18001173d  mov     [rsp+110h+var_D8], rax
0x180011742  lea     rax, [rbp+57h+var_6C]
0x180011746  mov     [rsp+110h+var_E0], rax
0x18001174b  lea     rax, [rbp+57h+var_28]
0x18001174f  mov     [rsp+110h+var_E8], rax
0x180011754  lea     rax, [rbp+57h+var_20]
0x180011758  mov     [rbp+57h+var_68], rcx
0x18001175c  mov     rcx, r9
0x18001175f  mov     [rsp+110h+var_F0], rax
0x180011764  mov     [rbp+57h+var_28], 1000000h
0x18001176c  mov     [rbp+57h+var_20], 0
0x180011774  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180011779  jmp     short loc_1800117F2
0x18001177b  call    ?zInternalStop@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180011780  call    ?Provider@FileExplorerLogging@@SAPEBU_tlgProvider_t@@XZ; FileExplorerLogging::Provider(void)
0x180011785  mov     rdi, rax
0x180011788  mov     ecx, [rax]
0x18001178a  cmp     ecx, 5
0x18001178d  jbe     short loc_1800117F2
0x18001178f  mov     rdx, 200000000000h
0x180011799  mov     rcx, rax
0x18001179c  call    _tlgKeywordOn
0x1800117a1  test    al, al
0x1800117a3  jz      short loc_1800117F2
0x1800117a5  call    cs:__imp_GetCurrentThreadId
0x1800117ab  mov     r8, [rbx+110h]
0x1800117b2  lea     rdx, word_1800163FE
0x1800117b9  mov     [rbp+57h+arg_0], eax
0x1800117bc  mov     rcx, rdi
0x1800117bf  mov     eax, [r8+48h]
0x1800117c3  add     r8, 8
0x1800117c7  mov     [rbp+57h+arg_8], eax
0x1800117ca  lea     rax, [rbp+57h+arg_0]
0x1800117ce  mov     [rsp+110h+var_E0], rax
0x1800117d3  lea     rax, [rbp+57h+arg_8]
0x1800117d7  mov     [rsp+110h+var_E8], rax
0x1800117dc  lea     rax, [rbp+57h+arg_10]
0x1800117e0  mov     [rsp+110h+var_F0], rax
0x1800117e5  mov     [rbp+57h+arg_10], 0
0x1800117ed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800117f2  mov     rcx, rbx
0x1800117f5  add     rsp, 100h
0x1800117fc  pop     rdi
0x1800117fd  pop     rbx
0x1800117fe  pop     rbp
0x1800117ff  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
