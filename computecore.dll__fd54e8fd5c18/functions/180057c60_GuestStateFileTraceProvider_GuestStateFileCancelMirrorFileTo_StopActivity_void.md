# GuestStateFileTraceProvider::GuestStateFileCancelMirrorFileTo::StopActivity(void)

- ea: `0x180057c60`
- end: `0x180057f40`
- name: `?StopActivity@GuestStateFileCancelMirrorFileTo@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileCancelMirrorFileTo *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x180057c60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057cc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057e95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057cc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057e95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057ec7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057ec7`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileCancelMirrorFileTo::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileCancelMirrorFileTo *this)
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
          (int)&byte_1800C9A7D,
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
          (unsigned int)&dword_1800C9A1C,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileCancelMirrorFileTo *)((char *)this + 288));
}

```

## disassembly

```asm
0x180057c60  mov     [rsp-8+arg_8], rbx
0x180057c65  mov     [rsp-8+arg_10], rdi
0x180057c6a  push    rbp
0x180057c6b  mov     rbp, rsp
0x180057c6e  sub     rsp, 140h
0x180057c75  mov     rbx, rcx
0x180057c78  mov     rdi, [rcx+110h]
0x180057c7f  mov     eax, [rdi+48h]
0x180057c82  test    eax, eax
0x180057c84  jns     loc_180057E6E
0x180057c8a  add     rdi, 50h ; 'P'
0x180057c8e  cmp     eax, [rdi+8]
0x180057c91  jnz     loc_180057E6E
0x180057c97  test    rdi, rdi
0x180057c9a  jz      loc_180057E6E
0x180057ca0  mov     [rbp+SRWLock], 0
0x180057ca8  lea     rdx, [rbp+SRWLock]
0x180057cac  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180057cb1  mov     rax, [rbx+110h]
0x180057cb8  mov     dword ptr [rax], 2
0x180057cbe  mov     rcx, [rbp+SRWLock]; SRWLock
0x180057cc2  test    rcx, rcx
0x180057cc5  jz      short loc_180057CCD
0x180057cc7  call    cs:__imp_ReleaseSRWLockExclusive
0x180057ccd  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180057cd2  mov     r9, rax
0x180057cd5  mov     ecx, [rax]
0x180057cd7  cmp     ecx, 4
0x180057cda  jbe     loc_180057F18
0x180057ce0  mov     rax, [rax+18h]
0x180057ce4  mov     rcx, [r9+10h]
0x180057ce8  mov     edx, 1000h
0x180057ced  test    rdx, rcx
0x180057cf0  jz      loc_180057F18
0x180057cf6  mov     rcx, rax
0x180057cf9  and     rcx, rdx
0x180057cfc  cmp     rcx, rax
0x180057cff  jnz     loc_180057F18
0x180057d05  mov     rax, [rdi+30h]
0x180057d09  mov     [rbp+var_50], rax
0x180057d0d  mov     eax, [rdi+44h]
0x180057d10  mov     dword ptr [rbp+var_78+4], eax
0x180057d13  mov     eax, [rdi+10h]
0x180057d16  mov     dword ptr [rbp+var_70], eax
0x180057d19  mov     rax, [rdi+78h]
0x180057d1d  mov     [rbp+var_48], rax
0x180057d21  mov     rax, [rdi+70h]
0x180057d25  mov     [rbp+var_40], rax
0x180057d29  mov     eax, [rdi+68h]
0x180057d2c  mov     dword ptr [rbp+var_70+4], eax
0x180057d2f  mov     rax, [rdi+60h]
0x180057d33  mov     [rbp+var_38], rax
0x180057d37  mov     rax, [rdi+58h]
0x180057d3b  mov     [rbp+var_30], rax
0x180057d3f  mov     eax, [rdi+50h]
0x180057d42  mov     dword ptr [rbp+var_68], eax
0x180057d45  mov     rax, [rdi+48h]
0x180057d49  mov     [rbp+var_28], rax
0x180057d4d  mov     eax, [rdi+20h]
0x180057d50  mov     dword ptr [rbp+var_68+4], eax
0x180057d53  mov     rax, [rdi+18h]
0x180057d57  mov     [rbp+var_20], rax
0x180057d5b  mov     eax, [rdi]
0x180057d5d  mov     [rbp+var_60], eax
0x180057d60  mov     rax, [rdi+80h]
0x180057d67  mov     [rbp+var_18], rax
0x180057d6b  mov     eax, [rdi+40h]
0x180057d6e  mov     dword ptr [rbp+var_78], eax
0x180057d71  mov     rax, [rdi+38h]
0x180057d75  mov     [rbp+var_10], rax
0x180057d79  mov     eax, [rdi+8]
0x180057d7c  mov     dword ptr [rbp+SRWLock], eax
0x180057d7f  mov     [rbp+var_8], 1000000h
0x180057d87  mov     [rbp+var_58], 0
0x180057d8f  mov     r8, [rbx+110h]
0x180057d96  add     r8, 8; int
0x180057d9a  lea     rax, [rbp+var_50]
0x180057d9e  mov     [rsp+140h+var_90], rax; __int64
0x180057da6  lea     rax, [rbp+var_78+4]
0x180057daa  mov     [rsp+140h+var_98], rax; __int64
0x180057db2  lea     rax, [rbp+var_70]
0x180057db6  mov     [rsp+140h+var_A0], rax; __int64
0x180057dbe  lea     rax, [rbp+var_48]
0x180057dc2  mov     [rsp+140h+var_A8], rax; __int64
0x180057dca  lea     rax, [rbp+var_40]
0x180057dce  mov     [rsp+140h+var_B0], rax; __int64
0x180057dd6  lea     rax, [rbp+var_70+4]
0x180057dda  mov     [rsp+140h+var_B8], rax; __int64
0x180057de2  lea     rax, [rbp+var_38]
0x180057de6  mov     [rsp+140h+var_C0], rax; __int64
0x180057dee  lea     rax, [rbp+var_30]
0x180057df2  mov     [rsp+140h+var_C8], rax; __int64
0x180057df7  lea     rax, [rbp+var_68]
0x180057dfb  mov     [rsp+140h+var_D0], rax; __int64
0x180057e00  lea     rax, [rbp+var_28]
0x180057e04  mov     [rsp+140h+var_D8], rax; __int64
0x180057e09  lea     rax, [rbp+var_68+4]
0x180057e0d  mov     [rsp+140h+var_E0], rax; __int64
0x180057e12  lea     rax, [rbp+var_20]
0x180057e16  mov     [rsp+140h+var_E8], rax; __int64
0x180057e1b  lea     rax, [rbp+var_60]
0x180057e1f  mov     [rsp+140h+var_F0], rax; __int64
0x180057e24  lea     rax, [rbp+var_18]
0x180057e28  mov     [rsp+140h+var_F8], rax; __int64
0x180057e2d  lea     rax, [rbp+var_78]
0x180057e31  mov     [rsp+140h+var_100], rax; __int64
0x180057e36  lea     rax, [rbp+var_10]
0x180057e3a  mov     [rsp+140h+var_108], rax; __int64
0x180057e3f  lea     rax, [rbp+SRWLock]
0x180057e43  mov     [rsp+140h+var_110], rax; __int64
0x180057e48  lea     rax, [rbp+var_8]
0x180057e4c  mov     [rsp+140h+var_118], rax; __int64
0x180057e51  lea     rax, [rbp+var_58]
0x180057e55  mov     [rsp+140h+var_120], rax; __int64
0x180057e5a  lea     rdx, byte_1800C9A7D; int
0x180057e61  mov     rcx, r9; int
0x180057e64  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180057e69  jmp     loc_180057F18
0x180057e6e  mov     [rbp+SRWLock], 0
0x180057e76  lea     rdx, [rbp+SRWLock]
0x180057e7a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180057e7f  mov     rax, [rbx+110h]
0x180057e86  mov     dword ptr [rax], 2
0x180057e8c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180057e90  test    rcx, rcx
0x180057e93  jz      short loc_180057E9B
0x180057e95  call    cs:__imp_ReleaseSRWLockExclusive
0x180057e9b  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180057ea0  mov     rdi, rax
0x180057ea3  mov     ecx, [rax]
0x180057ea5  cmp     ecx, 4
0x180057ea8  jbe     short loc_180057F18
0x180057eaa  mov     rax, [rax+18h]
0x180057eae  mov     rcx, [rdi+10h]
0x180057eb2  mov     edx, 1000h
0x180057eb7  test    rdx, rcx
0x180057eba  jz      short loc_180057F18
0x180057ebc  mov     rcx, rax
0x180057ebf  and     rcx, rdx
0x180057ec2  cmp     rcx, rax
0x180057ec5  jnz     short loc_180057F18
0x180057ec7  call    cs:__imp_GetCurrentThreadId
0x180057ecd  mov     dword ptr [rbp+SRWLock], eax
0x180057ed0  mov     r8, [rbx+110h]
0x180057ed7  mov     eax, [r8+48h]
0x180057edb  mov     dword ptr [rbp+var_78], eax
0x180057ede  mov     [rbp+var_58], 0
0x180057ee6  add     r8, 8
0x180057eea  lea     rax, [rbp+SRWLock]
0x180057eee  mov     [rsp+140h+var_110], rax
0x180057ef3  lea     rax, [rbp+var_78]
0x180057ef7  mov     [rsp+140h+var_118], rax
0x180057efc  lea     rax, [rbp+var_58]
0x180057f00  mov     [rsp+140h+var_120], rax
0x180057f05  xor     r9d, r9d
0x180057f08  lea     rdx, dword_1800C9A1C
0x180057f0f  mov     rcx, rdi
0x180057f12  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180057f17  nop
0x180057f18  lea     rcx, [rbx+120h]; this
0x180057f1f  cmp     dword ptr [rcx+18h], 0
0x180057f23  jz      short loc_180057F2B
0x180057f25  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180057f2a  nop
0x180057f2b  lea     r11, [rsp+140h+var_s0]
0x180057f33  mov     rbx, [r11+18h]
0x180057f37  mov     rdi, [r11+20h]
0x180057f3b  mov     rsp, r11
0x180057f3e  pop     rbp
0x180057f3f  retn
```
