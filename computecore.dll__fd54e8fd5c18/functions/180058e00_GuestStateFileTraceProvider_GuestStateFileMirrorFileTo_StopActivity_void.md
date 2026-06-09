# GuestStateFileTraceProvider::GuestStateFileMirrorFileTo::StopActivity(void)

- ea: `0x180058e00`
- end: `0x1800590e0`
- name: `?StopActivity@GuestStateFileMirrorFileTo@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileMirrorFileTo *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x180058e00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058e67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059035`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058e67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059035`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059067`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059067`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileMirrorFileTo::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileMirrorFileTo *this)
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
          (int)&byte_1800CA133,
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
          (unsigned int)&unk_1800CA0D8,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileMirrorFileTo *)((char *)this + 288));
}

```

## disassembly

```asm
0x180058e00  mov     [rsp-8+arg_8], rbx
0x180058e05  mov     [rsp-8+arg_10], rdi
0x180058e0a  push    rbp
0x180058e0b  mov     rbp, rsp
0x180058e0e  sub     rsp, 140h
0x180058e15  mov     rbx, rcx
0x180058e18  mov     rdi, [rcx+110h]
0x180058e1f  mov     eax, [rdi+48h]
0x180058e22  test    eax, eax
0x180058e24  jns     loc_18005900E
0x180058e2a  add     rdi, 50h ; 'P'
0x180058e2e  cmp     eax, [rdi+8]
0x180058e31  jnz     loc_18005900E
0x180058e37  test    rdi, rdi
0x180058e3a  jz      loc_18005900E
0x180058e40  mov     [rbp+SRWLock], 0
0x180058e48  lea     rdx, [rbp+SRWLock]
0x180058e4c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180058e51  mov     rax, [rbx+110h]
0x180058e58  mov     dword ptr [rax], 2
0x180058e5e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180058e62  test    rcx, rcx
0x180058e65  jz      short loc_180058E6D
0x180058e67  call    cs:__imp_ReleaseSRWLockExclusive
0x180058e6d  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180058e72  mov     r9, rax
0x180058e75  mov     ecx, [rax]
0x180058e77  cmp     ecx, 4
0x180058e7a  jbe     loc_1800590B8
0x180058e80  mov     rax, [rax+18h]
0x180058e84  mov     rcx, [r9+10h]
0x180058e88  mov     edx, 1000h
0x180058e8d  test    rdx, rcx
0x180058e90  jz      loc_1800590B8
0x180058e96  mov     rcx, rax
0x180058e99  and     rcx, rdx
0x180058e9c  cmp     rcx, rax
0x180058e9f  jnz     loc_1800590B8
0x180058ea5  mov     rax, [rdi+30h]
0x180058ea9  mov     [rbp+var_50], rax
0x180058ead  mov     eax, [rdi+44h]
0x180058eb0  mov     dword ptr [rbp+var_78+4], eax
0x180058eb3  mov     eax, [rdi+10h]
0x180058eb6  mov     dword ptr [rbp+var_70], eax
0x180058eb9  mov     rax, [rdi+78h]
0x180058ebd  mov     [rbp+var_48], rax
0x180058ec1  mov     rax, [rdi+70h]
0x180058ec5  mov     [rbp+var_40], rax
0x180058ec9  mov     eax, [rdi+68h]
0x180058ecc  mov     dword ptr [rbp+var_70+4], eax
0x180058ecf  mov     rax, [rdi+60h]
0x180058ed3  mov     [rbp+var_38], rax
0x180058ed7  mov     rax, [rdi+58h]
0x180058edb  mov     [rbp+var_30], rax
0x180058edf  mov     eax, [rdi+50h]
0x180058ee2  mov     dword ptr [rbp+var_68], eax
0x180058ee5  mov     rax, [rdi+48h]
0x180058ee9  mov     [rbp+var_28], rax
0x180058eed  mov     eax, [rdi+20h]
0x180058ef0  mov     dword ptr [rbp+var_68+4], eax
0x180058ef3  mov     rax, [rdi+18h]
0x180058ef7  mov     [rbp+var_20], rax
0x180058efb  mov     eax, [rdi]
0x180058efd  mov     [rbp+var_60], eax
0x180058f00  mov     rax, [rdi+80h]
0x180058f07  mov     [rbp+var_18], rax
0x180058f0b  mov     eax, [rdi+40h]
0x180058f0e  mov     dword ptr [rbp+var_78], eax
0x180058f11  mov     rax, [rdi+38h]
0x180058f15  mov     [rbp+var_10], rax
0x180058f19  mov     eax, [rdi+8]
0x180058f1c  mov     dword ptr [rbp+SRWLock], eax
0x180058f1f  mov     [rbp+var_8], 1000000h
0x180058f27  mov     [rbp+var_58], 0
0x180058f2f  mov     r8, [rbx+110h]
0x180058f36  add     r8, 8; int
0x180058f3a  lea     rax, [rbp+var_50]
0x180058f3e  mov     [rsp+140h+var_90], rax; __int64
0x180058f46  lea     rax, [rbp+var_78+4]
0x180058f4a  mov     [rsp+140h+var_98], rax; __int64
0x180058f52  lea     rax, [rbp+var_70]
0x180058f56  mov     [rsp+140h+var_A0], rax; __int64
0x180058f5e  lea     rax, [rbp+var_48]
0x180058f62  mov     [rsp+140h+var_A8], rax; __int64
0x180058f6a  lea     rax, [rbp+var_40]
0x180058f6e  mov     [rsp+140h+var_B0], rax; __int64
0x180058f76  lea     rax, [rbp+var_70+4]
0x180058f7a  mov     [rsp+140h+var_B8], rax; __int64
0x180058f82  lea     rax, [rbp+var_38]
0x180058f86  mov     [rsp+140h+var_C0], rax; __int64
0x180058f8e  lea     rax, [rbp+var_30]
0x180058f92  mov     [rsp+140h+var_C8], rax; __int64
0x180058f97  lea     rax, [rbp+var_68]
0x180058f9b  mov     [rsp+140h+var_D0], rax; __int64
0x180058fa0  lea     rax, [rbp+var_28]
0x180058fa4  mov     [rsp+140h+var_D8], rax; __int64
0x180058fa9  lea     rax, [rbp+var_68+4]
0x180058fad  mov     [rsp+140h+var_E0], rax; __int64
0x180058fb2  lea     rax, [rbp+var_20]
0x180058fb6  mov     [rsp+140h+var_E8], rax; __int64
0x180058fbb  lea     rax, [rbp+var_60]
0x180058fbf  mov     [rsp+140h+var_F0], rax; __int64
0x180058fc4  lea     rax, [rbp+var_18]
0x180058fc8  mov     [rsp+140h+var_F8], rax; __int64
0x180058fcd  lea     rax, [rbp+var_78]
0x180058fd1  mov     [rsp+140h+var_100], rax; __int64
0x180058fd6  lea     rax, [rbp+var_10]
0x180058fda  mov     [rsp+140h+var_108], rax; __int64
0x180058fdf  lea     rax, [rbp+SRWLock]
0x180058fe3  mov     [rsp+140h+var_110], rax; __int64
0x180058fe8  lea     rax, [rbp+var_8]
0x180058fec  mov     [rsp+140h+var_118], rax; __int64
0x180058ff1  lea     rax, [rbp+var_58]
0x180058ff5  mov     [rsp+140h+var_120], rax; __int64
0x180058ffa  lea     rdx, byte_1800CA133; int
0x180059001  mov     rcx, r9; int
0x180059004  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180059009  jmp     loc_1800590B8
0x18005900e  mov     [rbp+SRWLock], 0
0x180059016  lea     rdx, [rbp+SRWLock]
0x18005901a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005901f  mov     rax, [rbx+110h]
0x180059026  mov     dword ptr [rax], 2
0x18005902c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180059030  test    rcx, rcx
0x180059033  jz      short loc_18005903B
0x180059035  call    cs:__imp_ReleaseSRWLockExclusive
0x18005903b  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180059040  mov     rdi, rax
0x180059043  mov     ecx, [rax]
0x180059045  cmp     ecx, 4
0x180059048  jbe     short loc_1800590B8
0x18005904a  mov     rax, [rax+18h]
0x18005904e  mov     rcx, [rdi+10h]
0x180059052  mov     edx, 1000h
0x180059057  test    rdx, rcx
0x18005905a  jz      short loc_1800590B8
0x18005905c  mov     rcx, rax
0x18005905f  and     rcx, rdx
0x180059062  cmp     rcx, rax
0x180059065  jnz     short loc_1800590B8
0x180059067  call    cs:__imp_GetCurrentThreadId
0x18005906d  mov     dword ptr [rbp+SRWLock], eax
0x180059070  mov     r8, [rbx+110h]
0x180059077  mov     eax, [r8+48h]
0x18005907b  mov     dword ptr [rbp+var_78], eax
0x18005907e  mov     [rbp+var_58], 0
0x180059086  add     r8, 8
0x18005908a  lea     rax, [rbp+SRWLock]
0x18005908e  mov     [rsp+140h+var_110], rax
0x180059093  lea     rax, [rbp+var_78]
0x180059097  mov     [rsp+140h+var_118], rax
0x18005909c  lea     rax, [rbp+var_58]
0x1800590a0  mov     [rsp+140h+var_120], rax
0x1800590a5  xor     r9d, r9d
0x1800590a8  lea     rdx, unk_1800CA0D8
0x1800590af  mov     rcx, rdi
0x1800590b2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800590b7  nop
0x1800590b8  lea     rcx, [rbx+120h]; this
0x1800590bf  cmp     dword ptr [rcx+18h], 0
0x1800590c3  jz      short loc_1800590CB
0x1800590c5  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800590ca  nop
0x1800590cb  lea     r11, [rsp+140h+var_s0]
0x1800590d3  mov     rbx, [r11+18h]
0x1800590d7  mov     rdi, [r11+20h]
0x1800590db  mov     rsp, r11
0x1800590de  pop     rbp
0x1800590df  retn
```
