# GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::StopActivity(void)

- ea: `0x180059cb0`
- end: `0x180059f90`
- name: `?StopActivity@GuestStateFileOpenVirtualDisk@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x180059cb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059d17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059ee5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059d17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059ee5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059f17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059f17`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk *this)
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
          (int)&word_1800C8BD6,
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
          (unsigned int)&word_1800C8D2E,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileOpenVirtualDisk *)((char *)this + 288));
}

```

## disassembly

```asm
0x180059cb0  mov     [rsp-8+arg_8], rbx
0x180059cb5  mov     [rsp-8+arg_10], rdi
0x180059cba  push    rbp
0x180059cbb  mov     rbp, rsp
0x180059cbe  sub     rsp, 140h
0x180059cc5  mov     rbx, rcx
0x180059cc8  mov     rdi, [rcx+110h]
0x180059ccf  mov     eax, [rdi+48h]
0x180059cd2  test    eax, eax
0x180059cd4  jns     loc_180059EBE
0x180059cda  add     rdi, 50h ; 'P'
0x180059cde  cmp     eax, [rdi+8]
0x180059ce1  jnz     loc_180059EBE
0x180059ce7  test    rdi, rdi
0x180059cea  jz      loc_180059EBE
0x180059cf0  mov     [rbp+SRWLock], 0
0x180059cf8  lea     rdx, [rbp+SRWLock]
0x180059cfc  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180059d01  mov     rax, [rbx+110h]
0x180059d08  mov     dword ptr [rax], 2
0x180059d0e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180059d12  test    rcx, rcx
0x180059d15  jz      short loc_180059D1D
0x180059d17  call    cs:__imp_ReleaseSRWLockExclusive
0x180059d1d  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180059d22  mov     r9, rax
0x180059d25  mov     ecx, [rax]
0x180059d27  cmp     ecx, 4
0x180059d2a  jbe     loc_180059F68
0x180059d30  mov     rax, [rax+18h]
0x180059d34  mov     rcx, [r9+10h]
0x180059d38  mov     edx, 1000h
0x180059d3d  test    rdx, rcx
0x180059d40  jz      loc_180059F68
0x180059d46  mov     rcx, rax
0x180059d49  and     rcx, rdx
0x180059d4c  cmp     rcx, rax
0x180059d4f  jnz     loc_180059F68
0x180059d55  mov     rax, [rdi+30h]
0x180059d59  mov     [rbp+var_50], rax
0x180059d5d  mov     eax, [rdi+44h]
0x180059d60  mov     dword ptr [rbp+var_78+4], eax
0x180059d63  mov     eax, [rdi+10h]
0x180059d66  mov     dword ptr [rbp+var_70], eax
0x180059d69  mov     rax, [rdi+78h]
0x180059d6d  mov     [rbp+var_48], rax
0x180059d71  mov     rax, [rdi+70h]
0x180059d75  mov     [rbp+var_40], rax
0x180059d79  mov     eax, [rdi+68h]
0x180059d7c  mov     dword ptr [rbp+var_70+4], eax
0x180059d7f  mov     rax, [rdi+60h]
0x180059d83  mov     [rbp+var_38], rax
0x180059d87  mov     rax, [rdi+58h]
0x180059d8b  mov     [rbp+var_30], rax
0x180059d8f  mov     eax, [rdi+50h]
0x180059d92  mov     dword ptr [rbp+var_68], eax
0x180059d95  mov     rax, [rdi+48h]
0x180059d99  mov     [rbp+var_28], rax
0x180059d9d  mov     eax, [rdi+20h]
0x180059da0  mov     dword ptr [rbp+var_68+4], eax
0x180059da3  mov     rax, [rdi+18h]
0x180059da7  mov     [rbp+var_20], rax
0x180059dab  mov     eax, [rdi]
0x180059dad  mov     [rbp+var_60], eax
0x180059db0  mov     rax, [rdi+80h]
0x180059db7  mov     [rbp+var_18], rax
0x180059dbb  mov     eax, [rdi+40h]
0x180059dbe  mov     dword ptr [rbp+var_78], eax
0x180059dc1  mov     rax, [rdi+38h]
0x180059dc5  mov     [rbp+var_10], rax
0x180059dc9  mov     eax, [rdi+8]
0x180059dcc  mov     dword ptr [rbp+SRWLock], eax
0x180059dcf  mov     [rbp+var_8], 1000000h
0x180059dd7  mov     [rbp+var_58], 0
0x180059ddf  mov     r8, [rbx+110h]
0x180059de6  add     r8, 8; int
0x180059dea  lea     rax, [rbp+var_50]
0x180059dee  mov     [rsp+140h+var_90], rax; __int64
0x180059df6  lea     rax, [rbp+var_78+4]
0x180059dfa  mov     [rsp+140h+var_98], rax; __int64
0x180059e02  lea     rax, [rbp+var_70]
0x180059e06  mov     [rsp+140h+var_A0], rax; __int64
0x180059e0e  lea     rax, [rbp+var_48]
0x180059e12  mov     [rsp+140h+var_A8], rax; __int64
0x180059e1a  lea     rax, [rbp+var_40]
0x180059e1e  mov     [rsp+140h+var_B0], rax; __int64
0x180059e26  lea     rax, [rbp+var_70+4]
0x180059e2a  mov     [rsp+140h+var_B8], rax; __int64
0x180059e32  lea     rax, [rbp+var_38]
0x180059e36  mov     [rsp+140h+var_C0], rax; __int64
0x180059e3e  lea     rax, [rbp+var_30]
0x180059e42  mov     [rsp+140h+var_C8], rax; __int64
0x180059e47  lea     rax, [rbp+var_68]
0x180059e4b  mov     [rsp+140h+var_D0], rax; __int64
0x180059e50  lea     rax, [rbp+var_28]
0x180059e54  mov     [rsp+140h+var_D8], rax; __int64
0x180059e59  lea     rax, [rbp+var_68+4]
0x180059e5d  mov     [rsp+140h+var_E0], rax; __int64
0x180059e62  lea     rax, [rbp+var_20]
0x180059e66  mov     [rsp+140h+var_E8], rax; __int64
0x180059e6b  lea     rax, [rbp+var_60]
0x180059e6f  mov     [rsp+140h+var_F0], rax; __int64
0x180059e74  lea     rax, [rbp+var_18]
0x180059e78  mov     [rsp+140h+var_F8], rax; __int64
0x180059e7d  lea     rax, [rbp+var_78]
0x180059e81  mov     [rsp+140h+var_100], rax; __int64
0x180059e86  lea     rax, [rbp+var_10]
0x180059e8a  mov     [rsp+140h+var_108], rax; __int64
0x180059e8f  lea     rax, [rbp+SRWLock]
0x180059e93  mov     [rsp+140h+var_110], rax; __int64
0x180059e98  lea     rax, [rbp+var_8]
0x180059e9c  mov     [rsp+140h+var_118], rax; __int64
0x180059ea1  lea     rax, [rbp+var_58]
0x180059ea5  mov     [rsp+140h+var_120], rax; __int64
0x180059eaa  lea     rdx, word_1800C8BD6; int
0x180059eb1  mov     rcx, r9; int
0x180059eb4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180059eb9  jmp     loc_180059F68
0x180059ebe  mov     [rbp+SRWLock], 0
0x180059ec6  lea     rdx, [rbp+SRWLock]
0x180059eca  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180059ecf  mov     rax, [rbx+110h]
0x180059ed6  mov     dword ptr [rax], 2
0x180059edc  mov     rcx, [rbp+SRWLock]; SRWLock
0x180059ee0  test    rcx, rcx
0x180059ee3  jz      short loc_180059EEB
0x180059ee5  call    cs:__imp_ReleaseSRWLockExclusive
0x180059eeb  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180059ef0  mov     rdi, rax
0x180059ef3  mov     ecx, [rax]
0x180059ef5  cmp     ecx, 4
0x180059ef8  jbe     short loc_180059F68
0x180059efa  mov     rax, [rax+18h]
0x180059efe  mov     rcx, [rdi+10h]
0x180059f02  mov     edx, 1000h
0x180059f07  test    rdx, rcx
0x180059f0a  jz      short loc_180059F68
0x180059f0c  mov     rcx, rax
0x180059f0f  and     rcx, rdx
0x180059f12  cmp     rcx, rax
0x180059f15  jnz     short loc_180059F68
0x180059f17  call    cs:__imp_GetCurrentThreadId
0x180059f1d  mov     dword ptr [rbp+SRWLock], eax
0x180059f20  mov     r8, [rbx+110h]
0x180059f27  mov     eax, [r8+48h]
0x180059f2b  mov     dword ptr [rbp+var_78], eax
0x180059f2e  mov     [rbp+var_58], 0
0x180059f36  add     r8, 8
0x180059f3a  lea     rax, [rbp+SRWLock]
0x180059f3e  mov     [rsp+140h+var_110], rax
0x180059f43  lea     rax, [rbp+var_78]
0x180059f47  mov     [rsp+140h+var_118], rax
0x180059f4c  lea     rax, [rbp+var_58]
0x180059f50  mov     [rsp+140h+var_120], rax
0x180059f55  xor     r9d, r9d
0x180059f58  lea     rdx, word_1800C8D2E
0x180059f5f  mov     rcx, rdi
0x180059f62  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180059f67  nop
0x180059f68  lea     rcx, [rbx+120h]; this
0x180059f6f  cmp     dword ptr [rcx+18h], 0
0x180059f73  jz      short loc_180059F7B
0x180059f75  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180059f7a  nop
0x180059f7b  lea     r11, [rsp+140h+var_s0]
0x180059f83  mov     rbx, [r11+18h]
0x180059f87  mov     rdi, [r11+20h]
0x180059f8b  mov     rsp, r11
0x180059f8e  pop     rbp
0x180059f8f  retn
```
