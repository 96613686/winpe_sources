# HyperVStorageTrace::HyperVAsyncIo::StopActivity(void)

- ea: `0x180091b20`
- end: `0x180091df7`
- name: `?StopActivity@HyperVAsyncIo@HyperVStorageTrace@@MEAAXXZ`
- size: `727`
- prototype: `void __fastcall(HyperVStorageTrace::HyperVAsyncIo *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180066284`
- `0x180091b20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180091b87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180091d4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180091b87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180091d4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180091d7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180091d7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HyperVStorageTrace::HyperVAsyncIo::StopActivity(HyperVStorageTrace::HyperVAsyncIo *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // r8
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v9; // [rsp+C8h] [rbp-78h] BYREF
  int v10; // [rsp+CCh] [rbp-74h] BYREF
  int v11; // [rsp+D0h] [rbp-70h] BYREF
  int v12; // [rsp+D4h] [rbp-6Ch] BYREF
  int v13; // [rsp+D8h] [rbp-68h] BYREF
  int v14; // [rsp+DCh] [rbp-64h] BYREF
  int v15; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v16; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v17; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v18; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v19; // [rsp+100h] [rbp-40h] BYREF
  __int64 v20; // [rsp+108h] [rbp-38h] BYREF
  __int64 v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  __int64 v23; // [rsp+120h] [rbp-20h] BYREF
  __int64 v24; // [rsp+128h] [rbp-18h] BYREF
  __int64 v25; // [rsp+130h] [rbp-10h] BYREF
  __int64 v26; // [rsp+138h] [rbp-8h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)HyperVStorageTrace::Instance() + 1);
    if ( *(_DWORD *)v5 > 5u
      && (*(_QWORD *)(v5 + 16) & 0xA0) != 0
      && (*(_QWORD *)(v5 + 24) & 0xA0LL) == *(_QWORD *)(v5 + 24) )
    {
      v17 = *((_QWORD *)v4 + 6);
      v10 = v4[17];
      v11 = v4[4];
      v18 = *((_QWORD *)v4 + 15);
      v19 = *((_QWORD *)v4 + 14);
      v12 = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v13 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v9 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      LODWORD(SRWLock) = v4[2];
      v26 = 0x1000000;
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (int)&byte_1800CD6DF,
        *((_QWORD *)this + 34) + 8,
        (__int64)&v16,
        (__int64)&v26,
        (__int64)&SRWLock,
        (__int64)&v25,
        (__int64)&v9,
        (__int64)&v24,
        (__int64)&v15,
        (__int64)&v23,
        (__int64)&v14,
        (__int64)&v22,
        (__int64)&v13,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v12,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v11,
        (__int64)&v10,
        (__int64)&v17);
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = *((_QWORD *)HyperVStorageTrace::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0xA0) != 0
      && (*(_QWORD *)(v6 + 24) & 0xA0LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&byte_1800CD827,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((HyperVStorageTrace::HyperVAsyncIo *)((char *)this + 288));
}

```

## disassembly

```asm
0x180091b20  mov     [rsp-8+arg_8], rbx
0x180091b25  mov     [rsp-8+arg_10], rdi
0x180091b2a  push    rbp
0x180091b2b  mov     rbp, rsp
0x180091b2e  sub     rsp, 140h
0x180091b35  mov     rbx, rcx
0x180091b38  mov     rdi, [rcx+110h]
0x180091b3f  mov     eax, [rdi+48h]
0x180091b42  test    eax, eax
0x180091b44  jns     loc_180091D28
0x180091b4a  add     rdi, 50h ; 'P'
0x180091b4e  cmp     eax, [rdi+8]
0x180091b51  jnz     loc_180091D28
0x180091b57  test    rdi, rdi
0x180091b5a  jz      loc_180091D28
0x180091b60  mov     [rbp+SRWLock], 0
0x180091b68  lea     rdx, [rbp+SRWLock]
0x180091b6c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180091b71  mov     rax, [rbx+110h]
0x180091b78  mov     dword ptr [rax], 2
0x180091b7e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180091b82  test    rcx, rcx
0x180091b85  jz      short loc_180091B8D
0x180091b87  call    cs:__imp_ReleaseSRWLockExclusive
0x180091b8d  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180091b92  mov     rcx, [rax+8]; int
0x180091b96  mov     eax, [rcx]
0x180091b98  cmp     eax, 5
0x180091b9b  jbe     loc_180091DCF
0x180091ba1  mov     rdx, [rcx+18h]
0x180091ba5  mov     rax, [rcx+10h]
0x180091ba9  test    al, 0A0h
0x180091bab  jz      loc_180091DCF
0x180091bb1  mov     rax, rdx
0x180091bb4  and     eax, 0A0h
0x180091bb9  cmp     rax, rdx
0x180091bbc  jnz     loc_180091DCF
0x180091bc2  mov     rax, [rdi+30h]
0x180091bc6  mov     [rbp+var_50], rax
0x180091bca  mov     eax, [rdi+44h]
0x180091bcd  mov     dword ptr [rbp+var_78+4], eax
0x180091bd0  mov     eax, [rdi+10h]
0x180091bd3  mov     dword ptr [rbp+var_70], eax
0x180091bd6  mov     rax, [rdi+78h]
0x180091bda  mov     [rbp+var_48], rax
0x180091bde  mov     rax, [rdi+70h]
0x180091be2  mov     [rbp+var_40], rax
0x180091be6  mov     eax, [rdi+68h]
0x180091be9  mov     dword ptr [rbp+var_70+4], eax
0x180091bec  mov     rax, [rdi+60h]
0x180091bf0  mov     [rbp+var_38], rax
0x180091bf4  mov     rax, [rdi+58h]
0x180091bf8  mov     [rbp+var_30], rax
0x180091bfc  mov     eax, [rdi+50h]
0x180091bff  mov     dword ptr [rbp+var_68], eax
0x180091c02  mov     rax, [rdi+48h]
0x180091c06  mov     [rbp+var_28], rax
0x180091c0a  mov     eax, [rdi+20h]
0x180091c0d  mov     dword ptr [rbp+var_68+4], eax
0x180091c10  mov     rax, [rdi+18h]
0x180091c14  mov     [rbp+var_20], rax
0x180091c18  mov     eax, [rdi]
0x180091c1a  mov     [rbp+var_60], eax
0x180091c1d  mov     rax, [rdi+80h]
0x180091c24  mov     [rbp+var_18], rax
0x180091c28  mov     eax, [rdi+40h]
0x180091c2b  mov     dword ptr [rbp+var_78], eax
0x180091c2e  mov     rax, [rdi+38h]
0x180091c32  mov     [rbp+var_10], rax
0x180091c36  mov     eax, [rdi+8]
0x180091c39  mov     dword ptr [rbp+SRWLock], eax
0x180091c3c  mov     [rbp+var_8], 1000000h
0x180091c44  mov     [rbp+var_58], 0
0x180091c4c  mov     r8, [rbx+110h]
0x180091c53  add     r8, 8; int
0x180091c57  lea     rax, [rbp+var_50]
0x180091c5b  mov     [rsp+140h+var_90], rax; __int64
0x180091c63  lea     rax, [rbp+var_78+4]
0x180091c67  mov     [rsp+140h+var_98], rax; __int64
0x180091c6f  lea     rax, [rbp+var_70]
0x180091c73  mov     [rsp+140h+var_A0], rax; __int64
0x180091c7b  lea     rax, [rbp+var_48]
0x180091c7f  mov     [rsp+140h+var_A8], rax; __int64
0x180091c87  lea     rax, [rbp+var_40]
0x180091c8b  mov     [rsp+140h+var_B0], rax; __int64
0x180091c93  lea     rax, [rbp+var_70+4]
0x180091c97  mov     [rsp+140h+var_B8], rax; __int64
0x180091c9f  lea     rax, [rbp+var_38]
0x180091ca3  mov     [rsp+140h+var_C0], rax; __int64
0x180091cab  lea     rax, [rbp+var_30]
0x180091caf  mov     [rsp+140h+var_C8], rax; __int64
0x180091cb4  lea     rax, [rbp+var_68]
0x180091cb8  mov     [rsp+140h+var_D0], rax; __int64
0x180091cbd  lea     rax, [rbp+var_28]
0x180091cc1  mov     [rsp+140h+var_D8], rax; __int64
0x180091cc6  lea     rax, [rbp+var_68+4]
0x180091cca  mov     [rsp+140h+var_E0], rax; __int64
0x180091ccf  lea     rax, [rbp+var_20]
0x180091cd3  mov     [rsp+140h+var_E8], rax; __int64
0x180091cd8  lea     rax, [rbp+var_60]
0x180091cdc  mov     [rsp+140h+var_F0], rax; __int64
0x180091ce1  lea     rax, [rbp+var_18]
0x180091ce5  mov     [rsp+140h+var_F8], rax; __int64
0x180091cea  lea     rax, [rbp+var_78]
0x180091cee  mov     [rsp+140h+var_100], rax; __int64
0x180091cf3  lea     rax, [rbp+var_10]
0x180091cf7  mov     [rsp+140h+var_108], rax; __int64
0x180091cfc  lea     rax, [rbp+SRWLock]
0x180091d00  mov     [rsp+140h+var_110], rax; __int64
0x180091d05  lea     rax, [rbp+var_8]
0x180091d09  mov     [rsp+140h+var_118], rax; __int64
0x180091d0e  lea     rax, [rbp+var_58]
0x180091d12  mov     [rsp+140h+var_120], rax; __int64
0x180091d17  lea     rdx, byte_1800CD6DF; int
0x180091d1e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180091d23  jmp     loc_180091DCF
0x180091d28  mov     [rbp+SRWLock], 0
0x180091d30  lea     rdx, [rbp+SRWLock]
0x180091d34  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180091d39  mov     rax, [rbx+110h]
0x180091d40  mov     dword ptr [rax], 2
0x180091d46  mov     rcx, [rbp+SRWLock]; SRWLock
0x180091d4a  test    rcx, rcx
0x180091d4d  jz      short loc_180091D55
0x180091d4f  call    cs:__imp_ReleaseSRWLockExclusive
0x180091d55  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180091d5a  mov     rdi, [rax+8]
0x180091d5e  mov     eax, [rdi]
0x180091d60  cmp     eax, 5
0x180091d63  jbe     short loc_180091DCF
0x180091d65  mov     rcx, [rdi+18h]
0x180091d69  mov     rax, [rdi+10h]
0x180091d6d  test    al, 0A0h
0x180091d6f  jz      short loc_180091DCF
0x180091d71  mov     rax, rcx
0x180091d74  and     eax, 0A0h
0x180091d79  cmp     rax, rcx
0x180091d7c  jnz     short loc_180091DCF
0x180091d7e  call    cs:__imp_GetCurrentThreadId
0x180091d84  mov     dword ptr [rbp+SRWLock], eax
0x180091d87  mov     r8, [rbx+110h]
0x180091d8e  mov     eax, [r8+48h]
0x180091d92  mov     dword ptr [rbp+var_78], eax
0x180091d95  mov     [rbp+var_58], 0
0x180091d9d  add     r8, 8
0x180091da1  lea     rax, [rbp+SRWLock]
0x180091da5  mov     [rsp+140h+var_110], rax
0x180091daa  lea     rax, [rbp+var_78]
0x180091dae  mov     [rsp+140h+var_118], rax
0x180091db3  lea     rax, [rbp+var_58]
0x180091db7  mov     [rsp+140h+var_120], rax
0x180091dbc  xor     r9d, r9d
0x180091dbf  lea     rdx, byte_1800CD827
0x180091dc6  mov     rcx, rdi
0x180091dc9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180091dce  nop
0x180091dcf  lea     rcx, [rbx+120h]; this
0x180091dd6  cmp     dword ptr [rcx+18h], 0
0x180091dda  jz      short loc_180091DE2
0x180091ddc  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180091de1  nop
0x180091de2  lea     r11, [rsp+140h+var_s0]
0x180091dea  mov     rbx, [r11+18h]
0x180091dee  mov     rdi, [r11+20h]
0x180091df2  mov     rsp, r11
0x180091df5  pop     rbp
0x180091df6  retn
```
