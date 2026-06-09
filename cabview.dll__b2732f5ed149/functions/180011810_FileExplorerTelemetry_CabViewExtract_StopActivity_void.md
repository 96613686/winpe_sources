# FileExplorerTelemetry::CabViewExtract::StopActivity(void)

- ea: `0x180011810`
- end: `0x180011a34`
- name: `?StopActivity@CabViewExtract@FileExplorerTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(FileExplorerTelemetry::CabViewExtract *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001010`
- `0x1800017ac`
- `0x180001f3c`
- `0x180010410`
- `0x180010b7c`
- `0x180011810`
- `0x180011d9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800119d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800119d5`

## pseudocode

```c
void __fastcall FileExplorerTelemetry::CabViewExtract::StopActivity(FileExplorerTelemetry::CabViewExtract *this)
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
        (unsigned int)word_180016602,
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
        (unsigned int)byte_1800165B3,
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
0x180011810  push    rbp
0x180011812  push    rbx
0x180011813  push    rdi
0x180011814  lea     rbp, [rsp-47h]
0x180011819  sub     rsp, 100h
0x180011820  mov     rdi, [rcx+110h]
0x180011827  mov     rbx, rcx
0x18001182a  mov     eax, [rdi+48h]
0x18001182d  test    eax, eax
0x18001182f  jns     loc_1800119AB
0x180011835  add     rdi, 50h ; 'P'
0x180011839  cmp     eax, [rdi+8]
0x18001183c  jnz     loc_1800119AB
0x180011842  test    rdi, rdi
0x180011845  jz      loc_1800119AB
0x18001184b  call    ?zInternalStop@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180011850  call    ?Provider@FileExplorerLogging@@SAPEBU_tlgProvider_t@@XZ; FileExplorerLogging::Provider(void)
0x180011855  mov     r9, rax
0x180011858  mov     ecx, [rax]
0x18001185a  cmp     ecx, 5
0x18001185d  jbe     loc_180011A22
0x180011863  mov     rdx, 200000000000h
0x18001186d  mov     rcx, rax
0x180011870  call    _tlgKeywordOn
0x180011875  test    al, al
0x180011877  jz      loc_180011A22
0x18001187d  mov     rax, [rdi+70h]
0x180011881  lea     rdx, word_180016602
0x180011888  mov     rcx, [rdi+78h]
0x18001188c  mov     r8, [rbx+110h]
0x180011893  mov     [rbp+57h+var_60], rax
0x180011897  add     r8, 8
0x18001189b  mov     eax, [rdi+68h]
0x18001189e  mov     [rbp+57h+arg_0], eax
0x1800118a1  mov     rax, [rdi+60h]
0x1800118a5  mov     [rbp+57h+var_58], rax
0x1800118a9  mov     rax, [rdi+58h]
0x1800118ad  mov     [rbp+57h+var_50], rax
0x1800118b1  mov     eax, [rdi+50h]
0x1800118b4  mov     [rbp+57h+arg_8], eax
0x1800118b7  mov     rax, [rdi+48h]
0x1800118bb  mov     [rbp+57h+var_48], rax
0x1800118bf  mov     eax, [rdi+20h]
0x1800118c2  mov     dword ptr [rbp+57h+arg_10], eax
0x1800118c5  mov     rax, [rdi+18h]
0x1800118c9  mov     [rbp+57h+var_40], rax
0x1800118cd  mov     eax, [rdi]
0x1800118cf  mov     [rbp+57h+arg_18], eax
0x1800118d2  mov     rax, [rdi+80h]
0x1800118d9  mov     [rbp+57h+var_38], rax
0x1800118dd  mov     eax, [rdi+40h]
0x1800118e0  mov     [rbp+57h+var_70], eax
0x1800118e3  mov     rax, [rdi+38h]
0x1800118e7  mov     [rbp+57h+var_30], rax
0x1800118eb  mov     eax, [rdi+8]
0x1800118ee  mov     [rbp+57h+var_6C], eax
0x1800118f1  lea     rax, [rbp+57h+var_68]
0x1800118f5  mov     [rsp+110h+var_78], rax
0x1800118fd  lea     rax, [rbp+57h+var_60]
0x180011901  mov     [rsp+110h+var_80], rax
0x180011909  lea     rax, [rbp+57h+arg_0]
0x18001190d  mov     [rsp+110h+var_88], rax
0x180011915  lea     rax, [rbp+57h+var_58]
0x180011919  mov     [rsp+110h+var_90], rax
0x180011921  lea     rax, [rbp+57h+var_50]
0x180011925  mov     [rsp+110h+var_98], rax
0x18001192a  lea     rax, [rbp+57h+arg_8]
0x18001192e  mov     [rsp+110h+var_A0], rax
0x180011933  lea     rax, [rbp+57h+var_48]
0x180011937  mov     [rsp+110h+var_A8], rax
0x18001193c  lea     rax, [rbp+57h+arg_10]
0x180011940  mov     [rsp+110h+var_B0], rax
0x180011945  lea     rax, [rbp+57h+var_40]
0x180011949  mov     [rsp+110h+var_B8], rax
0x18001194e  lea     rax, [rbp+57h+arg_18]
0x180011952  mov     [rsp+110h+var_C0], rax
0x180011957  lea     rax, [rbp+57h+var_38]
0x18001195b  mov     [rsp+110h+var_C8], rax
0x180011960  lea     rax, [rbp+57h+var_70]
0x180011964  mov     [rsp+110h+var_D0], rax
0x180011969  lea     rax, [rbp+57h+var_30]
0x18001196d  mov     [rsp+110h+var_D8], rax
0x180011972  lea     rax, [rbp+57h+var_6C]
0x180011976  mov     [rsp+110h+var_E0], rax
0x18001197b  lea     rax, [rbp+57h+var_28]
0x18001197f  mov     [rsp+110h+var_E8], rax
0x180011984  lea     rax, [rbp+57h+var_20]
0x180011988  mov     [rbp+57h+var_68], rcx
0x18001198c  mov     rcx, r9
0x18001198f  mov     [rsp+110h+var_F0], rax
0x180011994  mov     [rbp+57h+var_28], 1000000h
0x18001199c  mov     [rbp+57h+var_20], 0
0x1800119a4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800119a9  jmp     short loc_180011A22
0x1800119ab  call    ?zInternalStop@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800119b0  call    ?Provider@FileExplorerLogging@@SAPEBU_tlgProvider_t@@XZ; FileExplorerLogging::Provider(void)
0x1800119b5  mov     rdi, rax
0x1800119b8  mov     ecx, [rax]
0x1800119ba  cmp     ecx, 5
0x1800119bd  jbe     short loc_180011A22
0x1800119bf  mov     rdx, 200000000000h
0x1800119c9  mov     rcx, rax
0x1800119cc  call    _tlgKeywordOn
0x1800119d1  test    al, al
0x1800119d3  jz      short loc_180011A22
0x1800119d5  call    cs:__imp_GetCurrentThreadId
0x1800119db  mov     r8, [rbx+110h]
0x1800119e2  lea     rdx, byte_1800165B3
0x1800119e9  mov     [rbp+57h+arg_0], eax
0x1800119ec  mov     rcx, rdi
0x1800119ef  mov     eax, [r8+48h]
0x1800119f3  add     r8, 8
0x1800119f7  mov     [rbp+57h+arg_8], eax
0x1800119fa  lea     rax, [rbp+57h+arg_0]
0x1800119fe  mov     [rsp+110h+var_E0], rax
0x180011a03  lea     rax, [rbp+57h+arg_8]
0x180011a07  mov     [rsp+110h+var_E8], rax
0x180011a0c  lea     rax, [rbp+57h+arg_10]
0x180011a10  mov     [rsp+110h+var_F0], rax
0x180011a15  mov     [rbp+57h+arg_10], 0
0x180011a1d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011a22  mov     rcx, rbx
0x180011a25  add     rsp, 100h
0x180011a2c  pop     rdi
0x180011a2d  pop     rbx
0x180011a2e  pop     rbp
0x180011a2f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
