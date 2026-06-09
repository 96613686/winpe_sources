# VstorlibTraceProvider::VstorCreateDeviceVHD::StopActivity(void)

- ea: `0x180098a30`
- end: `0x180098d10`
- name: `?StopActivity@VstorCreateDeviceVHD@VstorlibTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(VstorlibTraceProvider::VstorCreateDeviceVHD *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180097be4`
- `0x180098a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098a97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098c65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098a97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098c65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098c97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098c97`

## pseudocode

```c
void __fastcall VstorlibTraceProvider::VstorCreateDeviceVHD::StopActivity(
        VstorlibTraceProvider::VstorCreateDeviceVHD *this)
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
    v5 = VstorlibTraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x200LL) != 0 && (v7 & 0x200) == v7 )
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
          (int)&byte_1800CE49B,
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
    v8 = VstorlibTraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x200LL) != 0 && (v10 & 0x200) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)byte_1800CE77D,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((VstorlibTraceProvider::VstorCreateDeviceVHD *)((char *)this + 288));
}

```

## disassembly

```asm
0x180098a30  mov     [rsp-8+arg_8], rbx
0x180098a35  mov     [rsp-8+arg_10], rdi
0x180098a3a  push    rbp
0x180098a3b  mov     rbp, rsp
0x180098a3e  sub     rsp, 140h
0x180098a45  mov     rbx, rcx
0x180098a48  mov     rdi, [rcx+110h]
0x180098a4f  mov     eax, [rdi+48h]
0x180098a52  test    eax, eax
0x180098a54  jns     loc_180098C3E
0x180098a5a  add     rdi, 50h ; 'P'
0x180098a5e  cmp     eax, [rdi+8]
0x180098a61  jnz     loc_180098C3E
0x180098a67  test    rdi, rdi
0x180098a6a  jz      loc_180098C3E
0x180098a70  mov     [rbp+SRWLock], 0
0x180098a78  lea     rdx, [rbp+SRWLock]
0x180098a7c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180098a81  mov     rax, [rbx+110h]
0x180098a88  mov     dword ptr [rax], 2
0x180098a8e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180098a92  test    rcx, rcx
0x180098a95  jz      short loc_180098A9D
0x180098a97  call    cs:__imp_ReleaseSRWLockExclusive
0x180098a9d  call    ?Provider@VstorlibTraceProvider@@SAPEBU_tlgProvider_t@@XZ; VstorlibTraceProvider::Provider(void)
0x180098aa2  mov     r9, rax
0x180098aa5  mov     ecx, [rax]
0x180098aa7  cmp     ecx, 4
0x180098aaa  jbe     loc_180098CE8
0x180098ab0  mov     rax, [rax+18h]
0x180098ab4  mov     rcx, [r9+10h]
0x180098ab8  mov     edx, 200h
0x180098abd  test    rdx, rcx
0x180098ac0  jz      loc_180098CE8
0x180098ac6  mov     rcx, rax
0x180098ac9  and     rcx, rdx
0x180098acc  cmp     rcx, rax
0x180098acf  jnz     loc_180098CE8
0x180098ad5  mov     rax, [rdi+30h]
0x180098ad9  mov     [rbp+var_50], rax
0x180098add  mov     eax, [rdi+44h]
0x180098ae0  mov     dword ptr [rbp+var_78+4], eax
0x180098ae3  mov     eax, [rdi+10h]
0x180098ae6  mov     dword ptr [rbp+var_70], eax
0x180098ae9  mov     rax, [rdi+78h]
0x180098aed  mov     [rbp+var_48], rax
0x180098af1  mov     rax, [rdi+70h]
0x180098af5  mov     [rbp+var_40], rax
0x180098af9  mov     eax, [rdi+68h]
0x180098afc  mov     dword ptr [rbp+var_70+4], eax
0x180098aff  mov     rax, [rdi+60h]
0x180098b03  mov     [rbp+var_38], rax
0x180098b07  mov     rax, [rdi+58h]
0x180098b0b  mov     [rbp+var_30], rax
0x180098b0f  mov     eax, [rdi+50h]
0x180098b12  mov     dword ptr [rbp+var_68], eax
0x180098b15  mov     rax, [rdi+48h]
0x180098b19  mov     [rbp+var_28], rax
0x180098b1d  mov     eax, [rdi+20h]
0x180098b20  mov     dword ptr [rbp+var_68+4], eax
0x180098b23  mov     rax, [rdi+18h]
0x180098b27  mov     [rbp+var_20], rax
0x180098b2b  mov     eax, [rdi]
0x180098b2d  mov     [rbp+var_60], eax
0x180098b30  mov     rax, [rdi+80h]
0x180098b37  mov     [rbp+var_18], rax
0x180098b3b  mov     eax, [rdi+40h]
0x180098b3e  mov     dword ptr [rbp+var_78], eax
0x180098b41  mov     rax, [rdi+38h]
0x180098b45  mov     [rbp+var_10], rax
0x180098b49  mov     eax, [rdi+8]
0x180098b4c  mov     dword ptr [rbp+SRWLock], eax
0x180098b4f  mov     [rbp+var_8], 1000000h
0x180098b57  mov     [rbp+var_58], 0
0x180098b5f  mov     r8, [rbx+110h]
0x180098b66  add     r8, 8; int
0x180098b6a  lea     rax, [rbp+var_50]
0x180098b6e  mov     [rsp+140h+var_90], rax; __int64
0x180098b76  lea     rax, [rbp+var_78+4]
0x180098b7a  mov     [rsp+140h+var_98], rax; __int64
0x180098b82  lea     rax, [rbp+var_70]
0x180098b86  mov     [rsp+140h+var_A0], rax; __int64
0x180098b8e  lea     rax, [rbp+var_48]
0x180098b92  mov     [rsp+140h+var_A8], rax; __int64
0x180098b9a  lea     rax, [rbp+var_40]
0x180098b9e  mov     [rsp+140h+var_B0], rax; __int64
0x180098ba6  lea     rax, [rbp+var_70+4]
0x180098baa  mov     [rsp+140h+var_B8], rax; __int64
0x180098bb2  lea     rax, [rbp+var_38]
0x180098bb6  mov     [rsp+140h+var_C0], rax; __int64
0x180098bbe  lea     rax, [rbp+var_30]
0x180098bc2  mov     [rsp+140h+var_C8], rax; __int64
0x180098bc7  lea     rax, [rbp+var_68]
0x180098bcb  mov     [rsp+140h+var_D0], rax; __int64
0x180098bd0  lea     rax, [rbp+var_28]
0x180098bd4  mov     [rsp+140h+var_D8], rax; __int64
0x180098bd9  lea     rax, [rbp+var_68+4]
0x180098bdd  mov     [rsp+140h+var_E0], rax; __int64
0x180098be2  lea     rax, [rbp+var_20]
0x180098be6  mov     [rsp+140h+var_E8], rax; __int64
0x180098beb  lea     rax, [rbp+var_60]
0x180098bef  mov     [rsp+140h+var_F0], rax; __int64
0x180098bf4  lea     rax, [rbp+var_18]
0x180098bf8  mov     [rsp+140h+var_F8], rax; __int64
0x180098bfd  lea     rax, [rbp+var_78]
0x180098c01  mov     [rsp+140h+var_100], rax; __int64
0x180098c06  lea     rax, [rbp+var_10]
0x180098c0a  mov     [rsp+140h+var_108], rax; __int64
0x180098c0f  lea     rax, [rbp+SRWLock]
0x180098c13  mov     [rsp+140h+var_110], rax; __int64
0x180098c18  lea     rax, [rbp+var_8]
0x180098c1c  mov     [rsp+140h+var_118], rax; __int64
0x180098c21  lea     rax, [rbp+var_58]
0x180098c25  mov     [rsp+140h+var_120], rax; __int64
0x180098c2a  lea     rdx, byte_1800CE49B; int
0x180098c31  mov     rcx, r9; int
0x180098c34  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180098c39  jmp     loc_180098CE8
0x180098c3e  mov     [rbp+SRWLock], 0
0x180098c46  lea     rdx, [rbp+SRWLock]
0x180098c4a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180098c4f  mov     rax, [rbx+110h]
0x180098c56  mov     dword ptr [rax], 2
0x180098c5c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180098c60  test    rcx, rcx
0x180098c63  jz      short loc_180098C6B
0x180098c65  call    cs:__imp_ReleaseSRWLockExclusive
0x180098c6b  call    ?Provider@VstorlibTraceProvider@@SAPEBU_tlgProvider_t@@XZ; VstorlibTraceProvider::Provider(void)
0x180098c70  mov     rdi, rax
0x180098c73  mov     ecx, [rax]
0x180098c75  cmp     ecx, 4
0x180098c78  jbe     short loc_180098CE8
0x180098c7a  mov     rax, [rax+18h]
0x180098c7e  mov     rcx, [rdi+10h]
0x180098c82  mov     edx, 200h
0x180098c87  test    rdx, rcx
0x180098c8a  jz      short loc_180098CE8
0x180098c8c  mov     rcx, rax
0x180098c8f  and     rcx, rdx
0x180098c92  cmp     rcx, rax
0x180098c95  jnz     short loc_180098CE8
0x180098c97  call    cs:__imp_GetCurrentThreadId
0x180098c9d  mov     dword ptr [rbp+SRWLock], eax
0x180098ca0  mov     r8, [rbx+110h]
0x180098ca7  mov     eax, [r8+48h]
0x180098cab  mov     dword ptr [rbp+var_78], eax
0x180098cae  mov     [rbp+var_58], 0
0x180098cb6  add     r8, 8
0x180098cba  lea     rax, [rbp+SRWLock]
0x180098cbe  mov     [rsp+140h+var_110], rax
0x180098cc3  lea     rax, [rbp+var_78]
0x180098cc7  mov     [rsp+140h+var_118], rax
0x180098ccc  lea     rax, [rbp+var_58]
0x180098cd0  mov     [rsp+140h+var_120], rax
0x180098cd5  xor     r9d, r9d
0x180098cd8  lea     rdx, byte_1800CE77D
0x180098cdf  mov     rcx, rdi
0x180098ce2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180098ce7  nop
0x180098ce8  lea     rcx, [rbx+120h]; this
0x180098cef  cmp     dword ptr [rcx+18h], 0
0x180098cf3  jz      short loc_180098CFB
0x180098cf5  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180098cfa  nop
0x180098cfb  lea     r11, [rsp+140h+var_s0]
0x180098d03  mov     rbx, [r11+18h]
0x180098d07  mov     rdi, [r11+20h]
0x180098d0b  mov     rsp, r11
0x180098d0e  pop     rbp
0x180098d0f  retn
```
