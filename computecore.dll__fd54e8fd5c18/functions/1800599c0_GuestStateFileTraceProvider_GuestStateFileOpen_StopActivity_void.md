# GuestStateFileTraceProvider::GuestStateFileOpen::StopActivity(void)

- ea: `0x1800599c0`
- end: `0x180059ca0`
- name: `?StopActivity@GuestStateFileOpen@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileOpen *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x1800599c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059a27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059bf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059a27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059bf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059c27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059c27`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileOpen::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileOpen *this)
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
          (int)&dword_1800CA3AC,
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
          (unsigned int)byte_1800CA359,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileOpen *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800599c0  mov     [rsp-8+arg_8], rbx
0x1800599c5  mov     [rsp-8+arg_10], rdi
0x1800599ca  push    rbp
0x1800599cb  mov     rbp, rsp
0x1800599ce  sub     rsp, 140h
0x1800599d5  mov     rbx, rcx
0x1800599d8  mov     rdi, [rcx+110h]
0x1800599df  mov     eax, [rdi+48h]
0x1800599e2  test    eax, eax
0x1800599e4  jns     loc_180059BCE
0x1800599ea  add     rdi, 50h ; 'P'
0x1800599ee  cmp     eax, [rdi+8]
0x1800599f1  jnz     loc_180059BCE
0x1800599f7  test    rdi, rdi
0x1800599fa  jz      loc_180059BCE
0x180059a00  mov     [rbp+SRWLock], 0
0x180059a08  lea     rdx, [rbp+SRWLock]
0x180059a0c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180059a11  mov     rax, [rbx+110h]
0x180059a18  mov     dword ptr [rax], 2
0x180059a1e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180059a22  test    rcx, rcx
0x180059a25  jz      short loc_180059A2D
0x180059a27  call    cs:__imp_ReleaseSRWLockExclusive
0x180059a2d  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180059a32  mov     r9, rax
0x180059a35  mov     ecx, [rax]
0x180059a37  cmp     ecx, 4
0x180059a3a  jbe     loc_180059C78
0x180059a40  mov     rax, [rax+18h]
0x180059a44  mov     rcx, [r9+10h]
0x180059a48  mov     edx, 1000h
0x180059a4d  test    rdx, rcx
0x180059a50  jz      loc_180059C78
0x180059a56  mov     rcx, rax
0x180059a59  and     rcx, rdx
0x180059a5c  cmp     rcx, rax
0x180059a5f  jnz     loc_180059C78
0x180059a65  mov     rax, [rdi+30h]
0x180059a69  mov     [rbp+var_50], rax
0x180059a6d  mov     eax, [rdi+44h]
0x180059a70  mov     dword ptr [rbp+var_78+4], eax
0x180059a73  mov     eax, [rdi+10h]
0x180059a76  mov     dword ptr [rbp+var_70], eax
0x180059a79  mov     rax, [rdi+78h]
0x180059a7d  mov     [rbp+var_48], rax
0x180059a81  mov     rax, [rdi+70h]
0x180059a85  mov     [rbp+var_40], rax
0x180059a89  mov     eax, [rdi+68h]
0x180059a8c  mov     dword ptr [rbp+var_70+4], eax
0x180059a8f  mov     rax, [rdi+60h]
0x180059a93  mov     [rbp+var_38], rax
0x180059a97  mov     rax, [rdi+58h]
0x180059a9b  mov     [rbp+var_30], rax
0x180059a9f  mov     eax, [rdi+50h]
0x180059aa2  mov     dword ptr [rbp+var_68], eax
0x180059aa5  mov     rax, [rdi+48h]
0x180059aa9  mov     [rbp+var_28], rax
0x180059aad  mov     eax, [rdi+20h]
0x180059ab0  mov     dword ptr [rbp+var_68+4], eax
0x180059ab3  mov     rax, [rdi+18h]
0x180059ab7  mov     [rbp+var_20], rax
0x180059abb  mov     eax, [rdi]
0x180059abd  mov     [rbp+var_60], eax
0x180059ac0  mov     rax, [rdi+80h]
0x180059ac7  mov     [rbp+var_18], rax
0x180059acb  mov     eax, [rdi+40h]
0x180059ace  mov     dword ptr [rbp+var_78], eax
0x180059ad1  mov     rax, [rdi+38h]
0x180059ad5  mov     [rbp+var_10], rax
0x180059ad9  mov     eax, [rdi+8]
0x180059adc  mov     dword ptr [rbp+SRWLock], eax
0x180059adf  mov     [rbp+var_8], 1000000h
0x180059ae7  mov     [rbp+var_58], 0
0x180059aef  mov     r8, [rbx+110h]
0x180059af6  add     r8, 8; int
0x180059afa  lea     rax, [rbp+var_50]
0x180059afe  mov     [rsp+140h+var_90], rax; __int64
0x180059b06  lea     rax, [rbp+var_78+4]
0x180059b0a  mov     [rsp+140h+var_98], rax; __int64
0x180059b12  lea     rax, [rbp+var_70]
0x180059b16  mov     [rsp+140h+var_A0], rax; __int64
0x180059b1e  lea     rax, [rbp+var_48]
0x180059b22  mov     [rsp+140h+var_A8], rax; __int64
0x180059b2a  lea     rax, [rbp+var_40]
0x180059b2e  mov     [rsp+140h+var_B0], rax; __int64
0x180059b36  lea     rax, [rbp+var_70+4]
0x180059b3a  mov     [rsp+140h+var_B8], rax; __int64
0x180059b42  lea     rax, [rbp+var_38]
0x180059b46  mov     [rsp+140h+var_C0], rax; __int64
0x180059b4e  lea     rax, [rbp+var_30]
0x180059b52  mov     [rsp+140h+var_C8], rax; __int64
0x180059b57  lea     rax, [rbp+var_68]
0x180059b5b  mov     [rsp+140h+var_D0], rax; __int64
0x180059b60  lea     rax, [rbp+var_28]
0x180059b64  mov     [rsp+140h+var_D8], rax; __int64
0x180059b69  lea     rax, [rbp+var_68+4]
0x180059b6d  mov     [rsp+140h+var_E0], rax; __int64
0x180059b72  lea     rax, [rbp+var_20]
0x180059b76  mov     [rsp+140h+var_E8], rax; __int64
0x180059b7b  lea     rax, [rbp+var_60]
0x180059b7f  mov     [rsp+140h+var_F0], rax; __int64
0x180059b84  lea     rax, [rbp+var_18]
0x180059b88  mov     [rsp+140h+var_F8], rax; __int64
0x180059b8d  lea     rax, [rbp+var_78]
0x180059b91  mov     [rsp+140h+var_100], rax; __int64
0x180059b96  lea     rax, [rbp+var_10]
0x180059b9a  mov     [rsp+140h+var_108], rax; __int64
0x180059b9f  lea     rax, [rbp+SRWLock]
0x180059ba3  mov     [rsp+140h+var_110], rax; __int64
0x180059ba8  lea     rax, [rbp+var_8]
0x180059bac  mov     [rsp+140h+var_118], rax; __int64
0x180059bb1  lea     rax, [rbp+var_58]
0x180059bb5  mov     [rsp+140h+var_120], rax; __int64
0x180059bba  lea     rdx, dword_1800CA3AC; int
0x180059bc1  mov     rcx, r9; int
0x180059bc4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180059bc9  jmp     loc_180059C78
0x180059bce  mov     [rbp+SRWLock], 0
0x180059bd6  lea     rdx, [rbp+SRWLock]
0x180059bda  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180059bdf  mov     rax, [rbx+110h]
0x180059be6  mov     dword ptr [rax], 2
0x180059bec  mov     rcx, [rbp+SRWLock]; SRWLock
0x180059bf0  test    rcx, rcx
0x180059bf3  jz      short loc_180059BFB
0x180059bf5  call    cs:__imp_ReleaseSRWLockExclusive
0x180059bfb  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180059c00  mov     rdi, rax
0x180059c03  mov     ecx, [rax]
0x180059c05  cmp     ecx, 4
0x180059c08  jbe     short loc_180059C78
0x180059c0a  mov     rax, [rax+18h]
0x180059c0e  mov     rcx, [rdi+10h]
0x180059c12  mov     edx, 1000h
0x180059c17  test    rdx, rcx
0x180059c1a  jz      short loc_180059C78
0x180059c1c  mov     rcx, rax
0x180059c1f  and     rcx, rdx
0x180059c22  cmp     rcx, rax
0x180059c25  jnz     short loc_180059C78
0x180059c27  call    cs:__imp_GetCurrentThreadId
0x180059c2d  mov     dword ptr [rbp+SRWLock], eax
0x180059c30  mov     r8, [rbx+110h]
0x180059c37  mov     eax, [r8+48h]
0x180059c3b  mov     dword ptr [rbp+var_78], eax
0x180059c3e  mov     [rbp+var_58], 0
0x180059c46  add     r8, 8
0x180059c4a  lea     rax, [rbp+SRWLock]
0x180059c4e  mov     [rsp+140h+var_110], rax
0x180059c53  lea     rax, [rbp+var_78]
0x180059c57  mov     [rsp+140h+var_118], rax
0x180059c5c  lea     rax, [rbp+var_58]
0x180059c60  mov     [rsp+140h+var_120], rax
0x180059c65  xor     r9d, r9d
0x180059c68  lea     rdx, byte_1800CA359
0x180059c6f  mov     rcx, rdi
0x180059c72  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180059c77  nop
0x180059c78  lea     rcx, [rbx+120h]; this
0x180059c7f  cmp     dword ptr [rcx+18h], 0
0x180059c83  jz      short loc_180059C8B
0x180059c85  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180059c8a  nop
0x180059c8b  lea     r11, [rsp+140h+var_s0]
0x180059c93  mov     rbx, [r11+18h]
0x180059c97  mov     rdi, [r11+20h]
0x180059c9b  mov     rsp, r11
0x180059c9e  pop     rbp
0x180059c9f  retn
```
