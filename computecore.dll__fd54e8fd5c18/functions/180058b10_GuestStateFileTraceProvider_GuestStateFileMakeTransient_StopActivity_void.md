# GuestStateFileTraceProvider::GuestStateFileMakeTransient::StopActivity(void)

- ea: `0x180058b10`
- end: `0x180058df0`
- name: `?StopActivity@GuestStateFileMakeTransient@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileMakeTransient *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x180058b10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058b77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058d45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058b77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058d45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058d77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058d77`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileMakeTransient::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileMakeTransient *this)
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
          (int)&unk_1800C94B0,
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
          (unsigned int)&unk_1800C93F8,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileMakeTransient *)((char *)this + 288));
}

```

## disassembly

```asm
0x180058b10  mov     [rsp-8+arg_8], rbx
0x180058b15  mov     [rsp-8+arg_10], rdi
0x180058b1a  push    rbp
0x180058b1b  mov     rbp, rsp
0x180058b1e  sub     rsp, 140h
0x180058b25  mov     rbx, rcx
0x180058b28  mov     rdi, [rcx+110h]
0x180058b2f  mov     eax, [rdi+48h]
0x180058b32  test    eax, eax
0x180058b34  jns     loc_180058D1E
0x180058b3a  add     rdi, 50h ; 'P'
0x180058b3e  cmp     eax, [rdi+8]
0x180058b41  jnz     loc_180058D1E
0x180058b47  test    rdi, rdi
0x180058b4a  jz      loc_180058D1E
0x180058b50  mov     [rbp+SRWLock], 0
0x180058b58  lea     rdx, [rbp+SRWLock]
0x180058b5c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180058b61  mov     rax, [rbx+110h]
0x180058b68  mov     dword ptr [rax], 2
0x180058b6e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180058b72  test    rcx, rcx
0x180058b75  jz      short loc_180058B7D
0x180058b77  call    cs:__imp_ReleaseSRWLockExclusive
0x180058b7d  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180058b82  mov     r9, rax
0x180058b85  mov     ecx, [rax]
0x180058b87  cmp     ecx, 4
0x180058b8a  jbe     loc_180058DC8
0x180058b90  mov     rax, [rax+18h]
0x180058b94  mov     rcx, [r9+10h]
0x180058b98  mov     edx, 1000h
0x180058b9d  test    rdx, rcx
0x180058ba0  jz      loc_180058DC8
0x180058ba6  mov     rcx, rax
0x180058ba9  and     rcx, rdx
0x180058bac  cmp     rcx, rax
0x180058baf  jnz     loc_180058DC8
0x180058bb5  mov     rax, [rdi+30h]
0x180058bb9  mov     [rbp+var_50], rax
0x180058bbd  mov     eax, [rdi+44h]
0x180058bc0  mov     dword ptr [rbp+var_78+4], eax
0x180058bc3  mov     eax, [rdi+10h]
0x180058bc6  mov     dword ptr [rbp+var_70], eax
0x180058bc9  mov     rax, [rdi+78h]
0x180058bcd  mov     [rbp+var_48], rax
0x180058bd1  mov     rax, [rdi+70h]
0x180058bd5  mov     [rbp+var_40], rax
0x180058bd9  mov     eax, [rdi+68h]
0x180058bdc  mov     dword ptr [rbp+var_70+4], eax
0x180058bdf  mov     rax, [rdi+60h]
0x180058be3  mov     [rbp+var_38], rax
0x180058be7  mov     rax, [rdi+58h]
0x180058beb  mov     [rbp+var_30], rax
0x180058bef  mov     eax, [rdi+50h]
0x180058bf2  mov     dword ptr [rbp+var_68], eax
0x180058bf5  mov     rax, [rdi+48h]
0x180058bf9  mov     [rbp+var_28], rax
0x180058bfd  mov     eax, [rdi+20h]
0x180058c00  mov     dword ptr [rbp+var_68+4], eax
0x180058c03  mov     rax, [rdi+18h]
0x180058c07  mov     [rbp+var_20], rax
0x180058c0b  mov     eax, [rdi]
0x180058c0d  mov     [rbp+var_60], eax
0x180058c10  mov     rax, [rdi+80h]
0x180058c17  mov     [rbp+var_18], rax
0x180058c1b  mov     eax, [rdi+40h]
0x180058c1e  mov     dword ptr [rbp+var_78], eax
0x180058c21  mov     rax, [rdi+38h]
0x180058c25  mov     [rbp+var_10], rax
0x180058c29  mov     eax, [rdi+8]
0x180058c2c  mov     dword ptr [rbp+SRWLock], eax
0x180058c2f  mov     [rbp+var_8], 1000000h
0x180058c37  mov     [rbp+var_58], 0
0x180058c3f  mov     r8, [rbx+110h]
0x180058c46  add     r8, 8; int
0x180058c4a  lea     rax, [rbp+var_50]
0x180058c4e  mov     [rsp+140h+var_90], rax; __int64
0x180058c56  lea     rax, [rbp+var_78+4]
0x180058c5a  mov     [rsp+140h+var_98], rax; __int64
0x180058c62  lea     rax, [rbp+var_70]
0x180058c66  mov     [rsp+140h+var_A0], rax; __int64
0x180058c6e  lea     rax, [rbp+var_48]
0x180058c72  mov     [rsp+140h+var_A8], rax; __int64
0x180058c7a  lea     rax, [rbp+var_40]
0x180058c7e  mov     [rsp+140h+var_B0], rax; __int64
0x180058c86  lea     rax, [rbp+var_70+4]
0x180058c8a  mov     [rsp+140h+var_B8], rax; __int64
0x180058c92  lea     rax, [rbp+var_38]
0x180058c96  mov     [rsp+140h+var_C0], rax; __int64
0x180058c9e  lea     rax, [rbp+var_30]
0x180058ca2  mov     [rsp+140h+var_C8], rax; __int64
0x180058ca7  lea     rax, [rbp+var_68]
0x180058cab  mov     [rsp+140h+var_D0], rax; __int64
0x180058cb0  lea     rax, [rbp+var_28]
0x180058cb4  mov     [rsp+140h+var_D8], rax; __int64
0x180058cb9  lea     rax, [rbp+var_68+4]
0x180058cbd  mov     [rsp+140h+var_E0], rax; __int64
0x180058cc2  lea     rax, [rbp+var_20]
0x180058cc6  mov     [rsp+140h+var_E8], rax; __int64
0x180058ccb  lea     rax, [rbp+var_60]
0x180058ccf  mov     [rsp+140h+var_F0], rax; __int64
0x180058cd4  lea     rax, [rbp+var_18]
0x180058cd8  mov     [rsp+140h+var_F8], rax; __int64
0x180058cdd  lea     rax, [rbp+var_78]
0x180058ce1  mov     [rsp+140h+var_100], rax; __int64
0x180058ce6  lea     rax, [rbp+var_10]
0x180058cea  mov     [rsp+140h+var_108], rax; __int64
0x180058cef  lea     rax, [rbp+SRWLock]
0x180058cf3  mov     [rsp+140h+var_110], rax; __int64
0x180058cf8  lea     rax, [rbp+var_8]
0x180058cfc  mov     [rsp+140h+var_118], rax; __int64
0x180058d01  lea     rax, [rbp+var_58]
0x180058d05  mov     [rsp+140h+var_120], rax; __int64
0x180058d0a  lea     rdx, unk_1800C94B0; int
0x180058d11  mov     rcx, r9; int
0x180058d14  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180058d19  jmp     loc_180058DC8
0x180058d1e  mov     [rbp+SRWLock], 0
0x180058d26  lea     rdx, [rbp+SRWLock]
0x180058d2a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180058d2f  mov     rax, [rbx+110h]
0x180058d36  mov     dword ptr [rax], 2
0x180058d3c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180058d40  test    rcx, rcx
0x180058d43  jz      short loc_180058D4B
0x180058d45  call    cs:__imp_ReleaseSRWLockExclusive
0x180058d4b  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180058d50  mov     rdi, rax
0x180058d53  mov     ecx, [rax]
0x180058d55  cmp     ecx, 4
0x180058d58  jbe     short loc_180058DC8
0x180058d5a  mov     rax, [rax+18h]
0x180058d5e  mov     rcx, [rdi+10h]
0x180058d62  mov     edx, 1000h
0x180058d67  test    rdx, rcx
0x180058d6a  jz      short loc_180058DC8
0x180058d6c  mov     rcx, rax
0x180058d6f  and     rcx, rdx
0x180058d72  cmp     rcx, rax
0x180058d75  jnz     short loc_180058DC8
0x180058d77  call    cs:__imp_GetCurrentThreadId
0x180058d7d  mov     dword ptr [rbp+SRWLock], eax
0x180058d80  mov     r8, [rbx+110h]
0x180058d87  mov     eax, [r8+48h]
0x180058d8b  mov     dword ptr [rbp+var_78], eax
0x180058d8e  mov     [rbp+var_58], 0
0x180058d96  add     r8, 8
0x180058d9a  lea     rax, [rbp+SRWLock]
0x180058d9e  mov     [rsp+140h+var_110], rax
0x180058da3  lea     rax, [rbp+var_78]
0x180058da7  mov     [rsp+140h+var_118], rax
0x180058dac  lea     rax, [rbp+var_58]
0x180058db0  mov     [rsp+140h+var_120], rax
0x180058db5  xor     r9d, r9d
0x180058db8  lea     rdx, unk_1800C93F8
0x180058dbf  mov     rcx, rdi
0x180058dc2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180058dc7  nop
0x180058dc8  lea     rcx, [rbx+120h]; this
0x180058dcf  cmp     dword ptr [rcx+18h], 0
0x180058dd3  jz      short loc_180058DDB
0x180058dd5  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180058dda  nop
0x180058ddb  lea     r11, [rsp+140h+var_s0]
0x180058de3  mov     rbx, [r11+18h]
0x180058de7  mov     rdi, [r11+20h]
0x180058deb  mov     rsp, r11
0x180058dee  pop     rbp
0x180058def  retn
```
