# wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x14000a400`
- end: `0x14000a76c`
- name: `?NotifyFailure@?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `876`
- prototype: `char __fastcall(_QWORD *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140001590`
- `0x140001834`
- `0x140009e44`
- `0x14000a400`
- `0x14000a9b4`
- `0x14000cd28`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a759`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a759`

## pseudocode

```c
char __fastcall wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r9
  __int64 v6; // rax
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // r8
  _DWORD *v12; // rax
  int v13; // edx
  int v15; // [rsp+B0h] [rbp-80h] BYREF
  int v16; // [rsp+B4h] [rbp-7Ch] BYREF
  const unsigned __int16 *v17; // [rsp+B8h] [rbp-78h] BYREF
  __int64 *v18; // [rsp+C0h] [rbp-70h] BYREF
  __int64 *v19; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v21; // [rsp+D8h] [rbp-58h] BYREF
  __int64 *v22; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+E8h] [rbp-48h] BYREF
  __int64 *v24; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v26; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v27; // [rsp+108h] [rbp-28h] BYREF
  __int64 v28[4]; // [rsp+110h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+140h] [rbp+10h] BYREF
  int v30; // [rsp+148h] [rbp+18h] BYREF
  int v31; // [rsp+150h] [rbp+20h] BYREF
  int v32; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v8 = DXGIAdapterCacheLogging::Provider();
      v9 = (__int64)v8;
      if ( *(_DWORD *)v8 > 2u )
      {
        v10 = *((_QWORD *)v8 + 3);
        if ( (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
        {
          v25 = *((_QWORD *)a2 + 6);
          LODWORD(SRWLock) = a2[17];
          v30 = a2[4];
          v24 = (__int64 *)*((_QWORD *)a2 + 15);
          v11 = a1[34];
          v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
          v31 = a2[26];
          v22 = (__int64 *)*((_QWORD *)a2 + 12);
          v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
          v32 = a2[20];
          v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
          v16 = a2[8];
          v19 = (__int64 *)*((_QWORD *)a2 + 3);
          v15 = *a2;
          v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
          LODWORD(v17) = a2[16];
          v27 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
          LODWORD(v18) = a2[2];
          v28[0] = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v9,
            (__int64)byte_1400155A5,
            v11 + 8,
            v9,
            (__int64)v28,
            (__int64)&v18,
            &v27,
            (__int64)&v17,
            &v26,
            (__int64)&v15,
            &v19,
            (__int64)&v16,
            &v20,
            (__int64)&v32,
            &v21,
            &v22,
            (__int64)&v31,
            &v23,
            &v24,
            (__int64)&v30,
            (__int64)&SRWLock,
            (const unsigned __int16 **)&v25);
        }
      }
    }
    else
    {
      v4 = DXGIAdapterCacheLogging::Provider();
      v5 = (__int64)v4;
      if ( *(_DWORD *)v4 > 2u )
      {
        v6 = *((_QWORD *)v4 + 3);
        if ( (*(_QWORD *)(v5 + 16) & 0x600000000000LL) != 0 && (v6 & 0x600000000000LL) == v6 )
        {
          v7 = a1[34];
          v18 = (__int64 *)*((_QWORD *)a2 + 15);
          v17 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
          LODWORD(SRWLock) = a2[26];
          v19 = (__int64 *)*((_QWORD *)a2 + 12);
          v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
          v30 = a2[20];
          v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
          v31 = a2[8];
          v22 = (__int64 *)*((_QWORD *)a2 + 3);
          v32 = *a2;
          v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
          v15 = a2[16];
          v24 = (__int64 *)*((_QWORD *)a2 + 7);
          v16 = a2[2];
          v25 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v5,
            (__int64)word_14001519A,
            v7 + 8,
            v5,
            (__int64)&v25,
            (__int64)&v16,
            (const unsigned __int16 **)&v24,
            (__int64)&v15,
            &v23,
            (__int64)&v32,
            &v22,
            (__int64)&v31,
            &v21,
            (__int64)&v30,
            &v20,
            &v19,
            (__int64)&SRWLock,
            &v17,
            &v18);
        }
      }
    }
  }
  wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &SRWLock);
  v12 = (_DWORD *)a1[34];
  v13 = a2[2];
  if ( v13 != v12[22] && (v13 != v12[18] || (int)v12[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v12 + 20), (const struct wil::FailureInfo *)a2);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return 1;
}

```

## disassembly

```asm
0x14000a400  push    rbp
0x14000a402  push    rbx
0x14000a403  push    rdi
0x14000a404  lea     rbp, [rsp+10h]
0x14000a409  sub     rsp, 120h
0x14000a410  test    byte ptr [rdx+4], 2
0x14000a414  mov     rbx, rdx
0x14000a417  mov     rdi, rcx
0x14000a41a  jnz     loc_14000A71E
0x14000a420  mov     rax, [rcx]
0x14000a423  mov     edx, [rdx+10h]
0x14000a426  mov     rax, [rax+10h]
0x14000a42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a42f  test    al, al
0x14000a431  jnz     loc_14000A591
0x14000a437  call    ?Provider@DXGIAdapterCacheLogging@@SAPEBU_tlgProvider_t@@XZ; DXGIAdapterCacheLogging::Provider(void)
0x14000a43c  mov     r9, rax
0x14000a43f  mov     ecx, [rax]
0x14000a441  cmp     ecx, 2
0x14000a444  jbe     loc_14000A71E
0x14000a44a  mov     rax, [rax+18h]
0x14000a44e  mov     rdx, 600000000000h
0x14000a458  mov     rcx, [r9+10h]
0x14000a45c  test    rdx, rcx
0x14000a45f  jz      loc_14000A71E
0x14000a465  mov     rcx, rax
0x14000a468  and     rcx, rdx
0x14000a46b  cmp     rcx, rax
0x14000a46e  jnz     loc_14000A71E
0x14000a474  mov     rax, [rbx+78h]
0x14000a478  lea     rdx, word_14001519A
0x14000a47f  mov     r8, [rdi+110h]
0x14000a486  mov     rcx, r9
0x14000a489  mov     [rbp+var_70], rax
0x14000a48d  add     r8, 8
0x14000a491  mov     rax, [rbx+70h]
0x14000a495  mov     [rbp+var_78], rax
0x14000a499  mov     eax, [rbx+68h]
0x14000a49c  mov     dword ptr [rbp+SRWLock], eax
0x14000a49f  mov     rax, [rbx+60h]
0x14000a4a3  mov     [rbp+var_68], rax
0x14000a4a7  mov     rax, [rbx+58h]
0x14000a4ab  mov     [rbp+var_60], rax
0x14000a4af  mov     eax, [rbx+50h]
0x14000a4b2  mov     [rbp+arg_8], eax
0x14000a4b5  mov     rax, [rbx+48h]
0x14000a4b9  mov     [rbp+var_58], rax
0x14000a4bd  mov     eax, [rbx+20h]
0x14000a4c0  mov     [rbp+arg_10], eax
0x14000a4c3  mov     rax, [rbx+18h]
0x14000a4c7  mov     [rbp+var_50], rax
0x14000a4cb  mov     eax, [rbx]
0x14000a4cd  mov     [rbp+arg_18], eax
0x14000a4d0  mov     rax, [rbx+80h]
0x14000a4d7  mov     [rbp+var_48], rax
0x14000a4db  mov     eax, [rbx+40h]
0x14000a4de  mov     [rbp+var_80], eax
0x14000a4e1  mov     rax, [rbx+38h]
0x14000a4e5  mov     [rbp+var_40], rax
0x14000a4e9  mov     eax, [rbx+8]
0x14000a4ec  mov     [rbp+var_7C], eax
0x14000a4ef  lea     rax, [rbp+var_70]
0x14000a4f3  mov     [rsp+130h+var_A0], rax
0x14000a4fb  lea     rax, [rbp+var_78]
0x14000a4ff  mov     [rsp+130h+var_A8], rax
0x14000a507  lea     rax, [rbp+SRWLock]
0x14000a50b  mov     [rsp+130h+var_B0], rax
0x14000a513  lea     rax, [rbp+var_68]
0x14000a517  mov     [rsp+130h+var_B8], rax
0x14000a51c  lea     rax, [rbp+var_60]
0x14000a520  mov     [rsp+130h+var_C0], rax
0x14000a525  lea     rax, [rbp+arg_8]
0x14000a529  mov     [rsp+130h+var_C8], rax
0x14000a52e  lea     rax, [rbp+var_58]
0x14000a532  mov     [rsp+130h+var_D0], rax
0x14000a537  lea     rax, [rbp+arg_10]
0x14000a53b  mov     [rsp+130h+var_D8], rax
0x14000a540  lea     rax, [rbp+var_50]
0x14000a544  mov     [rsp+130h+var_E0], rax
0x14000a549  lea     rax, [rbp+arg_18]
0x14000a54d  mov     [rsp+130h+var_E8], rax
0x14000a552  lea     rax, [rbp+var_48]
0x14000a556  mov     [rsp+130h+var_F0], rax
0x14000a55b  lea     rax, [rbp+var_80]
0x14000a55f  mov     [rsp+130h+var_F8], rax
0x14000a564  lea     rax, [rbp+var_40]
0x14000a568  mov     [rsp+130h+var_100], rax
0x14000a56d  lea     rax, [rbp+var_7C]
0x14000a571  mov     [rsp+130h+var_108], rax
0x14000a576  lea     rax, [rbp+var_38]
0x14000a57a  mov     [rsp+130h+var_110], rax
0x14000a57f  mov     [rbp+var_38], 1000000h
0x14000a587  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000a58c  jmp     loc_14000A71E
0x14000a591  call    ?Provider@DXGIAdapterCacheLogging@@SAPEBU_tlgProvider_t@@XZ; DXGIAdapterCacheLogging::Provider(void)
0x14000a596  mov     r9, rax
0x14000a599  mov     ecx, [rax]
0x14000a59b  cmp     ecx, 2
0x14000a59e  jbe     loc_14000A71E
0x14000a5a4  mov     rax, [rax+18h]
0x14000a5a8  mov     rdx, 400000000000h
0x14000a5b2  mov     rcx, [r9+10h]
0x14000a5b6  test    rdx, rcx
0x14000a5b9  jz      loc_14000A71E
0x14000a5bf  mov     rcx, rax
0x14000a5c2  and     rcx, rdx
0x14000a5c5  cmp     rcx, rax
0x14000a5c8  jnz     loc_14000A71E
0x14000a5ce  mov     rax, [rbx+30h]
0x14000a5d2  lea     rdx, byte_1400155A5
0x14000a5d9  mov     [rbp+var_38], rax
0x14000a5dd  mov     rcx, r9
0x14000a5e0  mov     eax, [rbx+44h]
0x14000a5e3  mov     dword ptr [rbp+SRWLock], eax
0x14000a5e6  mov     eax, [rbx+10h]
0x14000a5e9  mov     [rbp+arg_8], eax
0x14000a5ec  mov     rax, [rbx+78h]
0x14000a5f0  mov     [rbp+var_40], rax
0x14000a5f4  mov     rax, [rbx+70h]
0x14000a5f8  mov     r8, [rdi+110h]
0x14000a5ff  mov     [rbp+var_48], rax
0x14000a603  add     r8, 8
0x14000a607  mov     eax, [rbx+68h]
0x14000a60a  mov     [rbp+arg_10], eax
0x14000a60d  mov     rax, [rbx+60h]
0x14000a611  mov     [rbp+var_50], rax
0x14000a615  mov     rax, [rbx+58h]
0x14000a619  mov     [rbp+var_58], rax
0x14000a61d  mov     eax, [rbx+50h]
0x14000a620  mov     [rbp+arg_18], eax
0x14000a623  mov     rax, [rbx+48h]
0x14000a627  mov     [rbp+var_60], rax
0x14000a62b  mov     eax, [rbx+20h]
0x14000a62e  mov     [rbp+var_7C], eax
0x14000a631  mov     rax, [rbx+18h]
0x14000a635  mov     [rbp+var_68], rax
0x14000a639  mov     eax, [rbx]
0x14000a63b  mov     [rbp+var_80], eax
0x14000a63e  mov     rax, [rbx+80h]
0x14000a645  mov     [rbp+var_30], rax
0x14000a649  mov     eax, [rbx+40h]
0x14000a64c  mov     dword ptr [rbp+var_78], eax
0x14000a64f  mov     rax, [rbx+38h]
0x14000a653  mov     [rbp+var_28], rax
0x14000a657  mov     eax, [rbx+8]
0x14000a65a  mov     dword ptr [rbp+var_70], eax
0x14000a65d  lea     rax, [rbp+var_38]
0x14000a661  mov     [rsp+130h+var_88], rax
0x14000a669  lea     rax, [rbp+SRWLock]
0x14000a66d  mov     [rsp+130h+var_90], rax
0x14000a675  lea     rax, [rbp+arg_8]
0x14000a679  mov     [rsp+130h+var_98], rax
0x14000a681  lea     rax, [rbp+var_40]
0x14000a685  mov     [rsp+130h+var_A0], rax
0x14000a68d  lea     rax, [rbp+var_48]
0x14000a691  mov     [rsp+130h+var_A8], rax
0x14000a699  lea     rax, [rbp+arg_10]
0x14000a69d  mov     [rsp+130h+var_B0], rax
0x14000a6a5  lea     rax, [rbp+var_50]
0x14000a6a9  mov     [rsp+130h+var_B8], rax
0x14000a6ae  lea     rax, [rbp+var_58]
0x14000a6b2  mov     [rsp+130h+var_C0], rax
0x14000a6b7  lea     rax, [rbp+arg_18]
0x14000a6bb  mov     [rsp+130h+var_C8], rax
0x14000a6c0  lea     rax, [rbp+var_60]
0x14000a6c4  mov     [rsp+130h+var_D0], rax
0x14000a6c9  lea     rax, [rbp+var_7C]
0x14000a6cd  mov     [rsp+130h+var_D8], rax
0x14000a6d2  lea     rax, [rbp+var_68]
0x14000a6d6  mov     [rsp+130h+var_E0], rax
0x14000a6db  lea     rax, [rbp+var_80]
0x14000a6df  mov     [rsp+130h+var_E8], rax
0x14000a6e4  lea     rax, [rbp+var_30]
0x14000a6e8  mov     [rsp+130h+var_F0], rax
0x14000a6ed  lea     rax, [rbp+var_78]
0x14000a6f1  mov     [rsp+130h+var_F8], rax
0x14000a6f6  lea     rax, [rbp+var_28]
0x14000a6fa  mov     [rsp+130h+var_100], rax
0x14000a6ff  lea     rax, [rbp+var_70]
0x14000a703  mov     [rsp+130h+var_108], rax
0x14000a708  lea     rax, [rbp+var_20]
0x14000a70c  mov     [rsp+130h+var_110], rax
0x14000a711  mov     [rbp+var_20], 1000000h
0x14000a719  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14000a71e  lea     rdx, [rbp+SRWLock]
0x14000a722  mov     rcx, rdi
0x14000a725  call    ?LockExclusive@?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000a72a  mov     rax, [rdi+110h]
0x14000a731  mov     edx, [rbx+8]
0x14000a734  lea     rcx, [rax+50h]; this
0x14000a738  cmp     edx, [rcx+8]
0x14000a73b  jz      short loc_14000A750
0x14000a73d  cmp     edx, [rax+48h]
0x14000a740  jnz     short loc_14000A748
0x14000a742  cmp     dword ptr [rax+48h], 0
0x14000a746  jl      short loc_14000A750
0x14000a748  mov     rdx, rbx; struct wil::FailureInfo *
0x14000a74b  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x14000a750  mov     rcx, [rbp+SRWLock]; SRWLock
0x14000a754  test    rcx, rcx
0x14000a757  jz      short loc_14000A75F
0x14000a759  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a75f  mov     al, 1
0x14000a761  add     rsp, 120h
0x14000a768  pop     rdi
0x14000a769  pop     rbx
0x14000a76a  pop     rbp
0x14000a76b  retn
```
