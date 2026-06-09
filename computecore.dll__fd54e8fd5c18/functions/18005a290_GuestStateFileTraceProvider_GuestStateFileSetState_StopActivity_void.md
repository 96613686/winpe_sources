# GuestStateFileTraceProvider::GuestStateFileSetState::StopActivity(void)

- ea: `0x18005a290`
- end: `0x18005a570`
- name: `?StopActivity@GuestStateFileSetState@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileSetState *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x18005a290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a2f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a4c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a2f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a4c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a4f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a4f7`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileSetState::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileSetState *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v13; // [rsp+C8h] [rbp-78h] BYREF
  int v14; // [rsp+CCh] [rbp-74h] BYREF
  int v15; // [rsp+D0h] [rbp-70h] BYREF
  int v16; // [rsp+D4h] [rbp-6Ch] BYREF
  int v17; // [rsp+D8h] [rbp-68h] BYREF
  int v18; // [rsp+DCh] [rbp-64h] BYREF
  int v19; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+100h] [rbp-40h] BYREF
  __int64 v24; // [rsp+108h] [rbp-38h] BYREF
  __int64 v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  __int64 v27; // [rsp+120h] [rbp-20h] BYREF
  __int64 v28; // [rsp+128h] [rbp-18h] BYREF
  __int64 v29; // [rsp+130h] [rbp-10h] BYREF
  __int64 v30; // [rsp+138h] [rbp-8h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = GuestStateFileTraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x1000LL) != 0 && (v7 & 0x1000) == v7 )
      {
        v21 = *((_QWORD *)v4 + 6);
        v14 = v4[17];
        v15 = v4[4];
        v22 = *((_QWORD *)v4 + 15);
        v23 = *((_QWORD *)v4 + 14);
        v16 = v4[26];
        v24 = *((_QWORD *)v4 + 12);
        v25 = *((_QWORD *)v4 + 11);
        v17 = v4[20];
        v26 = *((_QWORD *)v4 + 9);
        v18 = v4[8];
        v27 = *((_QWORD *)v4 + 3);
        v19 = *v4;
        v28 = *((_QWORD *)v4 + 16);
        v13 = v4[16];
        v29 = *((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v30 = 0x1000000;
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (int)v6,
          (int)&byte_1800C8E9F,
          *((_QWORD *)this + 34) + 8,
          (__int64)&v20,
          (__int64)&v30,
          (__int64)&SRWLock,
          (__int64)&v29,
          (__int64)&v13,
          (__int64)&v28,
          (__int64)&v19,
          (__int64)&v27,
          (__int64)&v18,
          (__int64)&v26,
          (__int64)&v17,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v16,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&v21);
      }
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v8 = GuestStateFileTraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x1000LL) != 0 && (v10 & 0x1000) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)&dword_1800C8D8C,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileSetState *)((char *)this + 288));
}

```

## disassembly

```asm
0x18005a290  mov     [rsp-8+arg_8], rbx
0x18005a295  mov     [rsp-8+arg_10], rdi
0x18005a29a  push    rbp
0x18005a29b  mov     rbp, rsp
0x18005a29e  sub     rsp, 140h
0x18005a2a5  mov     rbx, rcx
0x18005a2a8  mov     rdi, [rcx+110h]
0x18005a2af  mov     eax, [rdi+48h]
0x18005a2b2  test    eax, eax
0x18005a2b4  jns     loc_18005A49E
0x18005a2ba  add     rdi, 50h ; 'P'
0x18005a2be  cmp     eax, [rdi+8]
0x18005a2c1  jnz     loc_18005A49E
0x18005a2c7  test    rdi, rdi
0x18005a2ca  jz      loc_18005A49E
0x18005a2d0  mov     [rbp+SRWLock], 0
0x18005a2d8  lea     rdx, [rbp+SRWLock]
0x18005a2dc  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005a2e1  mov     rax, [rbx+110h]
0x18005a2e8  mov     dword ptr [rax], 2
0x18005a2ee  mov     rcx, [rbp+SRWLock]; SRWLock
0x18005a2f2  test    rcx, rcx
0x18005a2f5  jz      short loc_18005A2FD
0x18005a2f7  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a2fd  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x18005a302  mov     r9, rax
0x18005a305  mov     ecx, [rax]
0x18005a307  cmp     ecx, 4
0x18005a30a  jbe     loc_18005A548
0x18005a310  mov     rax, [rax+18h]
0x18005a314  mov     rcx, [r9+10h]
0x18005a318  mov     edx, 1000h
0x18005a31d  test    rdx, rcx
0x18005a320  jz      loc_18005A548
0x18005a326  mov     rcx, rax
0x18005a329  and     rcx, rdx
0x18005a32c  cmp     rcx, rax
0x18005a32f  jnz     loc_18005A548
0x18005a335  mov     rax, [rdi+30h]
0x18005a339  mov     [rbp+var_50], rax
0x18005a33d  mov     eax, [rdi+44h]
0x18005a340  mov     dword ptr [rbp+var_78+4], eax
0x18005a343  mov     eax, [rdi+10h]
0x18005a346  mov     dword ptr [rbp+var_70], eax
0x18005a349  mov     rax, [rdi+78h]
0x18005a34d  mov     [rbp+var_48], rax
0x18005a351  mov     rax, [rdi+70h]
0x18005a355  mov     [rbp+var_40], rax
0x18005a359  mov     eax, [rdi+68h]
0x18005a35c  mov     dword ptr [rbp+var_70+4], eax
0x18005a35f  mov     rax, [rdi+60h]
0x18005a363  mov     [rbp+var_38], rax
0x18005a367  mov     rax, [rdi+58h]
0x18005a36b  mov     [rbp+var_30], rax
0x18005a36f  mov     eax, [rdi+50h]
0x18005a372  mov     dword ptr [rbp+var_68], eax
0x18005a375  mov     rax, [rdi+48h]
0x18005a379  mov     [rbp+var_28], rax
0x18005a37d  mov     eax, [rdi+20h]
0x18005a380  mov     dword ptr [rbp+var_68+4], eax
0x18005a383  mov     rax, [rdi+18h]
0x18005a387  mov     [rbp+var_20], rax
0x18005a38b  mov     eax, [rdi]
0x18005a38d  mov     [rbp+var_60], eax
0x18005a390  mov     rax, [rdi+80h]
0x18005a397  mov     [rbp+var_18], rax
0x18005a39b  mov     eax, [rdi+40h]
0x18005a39e  mov     dword ptr [rbp+var_78], eax
0x18005a3a1  mov     rax, [rdi+38h]
0x18005a3a5  mov     [rbp+var_10], rax
0x18005a3a9  mov     eax, [rdi+8]
0x18005a3ac  mov     dword ptr [rbp+SRWLock], eax
0x18005a3af  mov     [rbp+var_8], 1000000h
0x18005a3b7  mov     [rbp+var_58], 0
0x18005a3bf  mov     r8, [rbx+110h]
0x18005a3c6  add     r8, 8; int
0x18005a3ca  lea     rax, [rbp+var_50]
0x18005a3ce  mov     [rsp+140h+var_90], rax; __int64
0x18005a3d6  lea     rax, [rbp+var_78+4]
0x18005a3da  mov     [rsp+140h+var_98], rax; __int64
0x18005a3e2  lea     rax, [rbp+var_70]
0x18005a3e6  mov     [rsp+140h+var_A0], rax; __int64
0x18005a3ee  lea     rax, [rbp+var_48]
0x18005a3f2  mov     [rsp+140h+var_A8], rax; __int64
0x18005a3fa  lea     rax, [rbp+var_40]
0x18005a3fe  mov     [rsp+140h+var_B0], rax; __int64
0x18005a406  lea     rax, [rbp+var_70+4]
0x18005a40a  mov     [rsp+140h+var_B8], rax; __int64
0x18005a412  lea     rax, [rbp+var_38]
0x18005a416  mov     [rsp+140h+var_C0], rax; __int64
0x18005a41e  lea     rax, [rbp+var_30]
0x18005a422  mov     [rsp+140h+var_C8], rax; __int64
0x18005a427  lea     rax, [rbp+var_68]
0x18005a42b  mov     [rsp+140h+var_D0], rax; __int64
0x18005a430  lea     rax, [rbp+var_28]
0x18005a434  mov     [rsp+140h+var_D8], rax; __int64
0x18005a439  lea     rax, [rbp+var_68+4]
0x18005a43d  mov     [rsp+140h+var_E0], rax; __int64
0x18005a442  lea     rax, [rbp+var_20]
0x18005a446  mov     [rsp+140h+var_E8], rax; __int64
0x18005a44b  lea     rax, [rbp+var_60]
0x18005a44f  mov     [rsp+140h+var_F0], rax; __int64
0x18005a454  lea     rax, [rbp+var_18]
0x18005a458  mov     [rsp+140h+var_F8], rax; __int64
0x18005a45d  lea     rax, [rbp+var_78]
0x18005a461  mov     [rsp+140h+var_100], rax; __int64
0x18005a466  lea     rax, [rbp+var_10]
0x18005a46a  mov     [rsp+140h+var_108], rax; __int64
0x18005a46f  lea     rax, [rbp+SRWLock]
0x18005a473  mov     [rsp+140h+var_110], rax; __int64
0x18005a478  lea     rax, [rbp+var_8]
0x18005a47c  mov     [rsp+140h+var_118], rax; __int64
0x18005a481  lea     rax, [rbp+var_58]
0x18005a485  mov     [rsp+140h+var_120], rax; __int64
0x18005a48a  lea     rdx, byte_1800C8E9F; int
0x18005a491  mov     rcx, r9; int
0x18005a494  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005a499  jmp     loc_18005A548
0x18005a49e  mov     [rbp+SRWLock], 0
0x18005a4a6  lea     rdx, [rbp+SRWLock]
0x18005a4aa  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005a4af  mov     rax, [rbx+110h]
0x18005a4b6  mov     dword ptr [rax], 2
0x18005a4bc  mov     rcx, [rbp+SRWLock]; SRWLock
0x18005a4c0  test    rcx, rcx
0x18005a4c3  jz      short loc_18005A4CB
0x18005a4c5  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a4cb  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x18005a4d0  mov     rdi, rax
0x18005a4d3  mov     ecx, [rax]
0x18005a4d5  cmp     ecx, 4
0x18005a4d8  jbe     short loc_18005A548
0x18005a4da  mov     rax, [rax+18h]
0x18005a4de  mov     rcx, [rdi+10h]
0x18005a4e2  mov     edx, 1000h
0x18005a4e7  test    rdx, rcx
0x18005a4ea  jz      short loc_18005A548
0x18005a4ec  mov     rcx, rax
0x18005a4ef  and     rcx, rdx
0x18005a4f2  cmp     rcx, rax
0x18005a4f5  jnz     short loc_18005A548
0x18005a4f7  call    cs:__imp_GetCurrentThreadId
0x18005a4fd  mov     dword ptr [rbp+SRWLock], eax
0x18005a500  mov     r8, [rbx+110h]
0x18005a507  mov     eax, [r8+48h]
0x18005a50b  mov     dword ptr [rbp+var_78], eax
0x18005a50e  mov     [rbp+var_58], 0
0x18005a516  add     r8, 8
0x18005a51a  lea     rax, [rbp+SRWLock]
0x18005a51e  mov     [rsp+140h+var_110], rax
0x18005a523  lea     rax, [rbp+var_78]
0x18005a527  mov     [rsp+140h+var_118], rax
0x18005a52c  lea     rax, [rbp+var_58]
0x18005a530  mov     [rsp+140h+var_120], rax
0x18005a535  xor     r9d, r9d
0x18005a538  lea     rdx, dword_1800C8D8C
0x18005a53f  mov     rcx, rdi
0x18005a542  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005a547  nop
0x18005a548  lea     rcx, [rbx+120h]; this
0x18005a54f  cmp     dword ptr [rcx+18h], 0
0x18005a553  jz      short loc_18005A55B
0x18005a555  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18005a55a  nop
0x18005a55b  lea     r11, [rsp+140h+var_s0]
0x18005a563  mov     rbx, [r11+18h]
0x18005a567  mov     rdi, [r11+20h]
0x18005a56b  mov     rsp, r11
0x18005a56e  pop     rbp
0x18005a56f  retn
```
