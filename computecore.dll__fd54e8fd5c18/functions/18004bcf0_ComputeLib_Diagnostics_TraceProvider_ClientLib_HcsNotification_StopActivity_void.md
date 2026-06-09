# ComputeLib::Diagnostics::TraceProvider::ClientLib_HcsNotification::StopActivity(void)

- ea: `0x18004bcf0`
- end: `0x18004bfd0`
- name: `?StopActivity@ClientLib_HcsNotification@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ClientLib_HcsNotification *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x180014de4`
- `0x18001558c`
- `0x18004bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004bd57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004bf25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004bd57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004bf25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bf57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bf57`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::ClientLib_HcsNotification::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::ClientLib_HcsNotification *this)
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
    v5 = ComputeLib::Diagnostics::TraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x10000LL) != 0 && (v7 & 0x10000) == v7 )
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
          (int)&byte_1800C7C95,
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
    v8 = ComputeLib::Diagnostics::TraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x10000LL) != 0 && (v10 & 0x10000) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)&unk_1800C8428,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::ClientLib_HcsNotification *)((char *)this + 288));
}

```

## disassembly

```asm
0x18004bcf0  mov     [rsp-8+arg_8], rbx
0x18004bcf5  mov     [rsp-8+arg_10], rdi
0x18004bcfa  push    rbp
0x18004bcfb  mov     rbp, rsp
0x18004bcfe  sub     rsp, 140h
0x18004bd05  mov     rbx, rcx
0x18004bd08  mov     rdi, [rcx+110h]
0x18004bd0f  mov     eax, [rdi+48h]
0x18004bd12  test    eax, eax
0x18004bd14  jns     loc_18004BEFE
0x18004bd1a  add     rdi, 50h ; 'P'
0x18004bd1e  cmp     eax, [rdi+8]
0x18004bd21  jnz     loc_18004BEFE
0x18004bd27  test    rdi, rdi
0x18004bd2a  jz      loc_18004BEFE
0x18004bd30  mov     [rbp+SRWLock], 0
0x18004bd38  lea     rdx, [rbp+SRWLock]
0x18004bd3c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004bd41  mov     rax, [rbx+110h]
0x18004bd48  mov     dword ptr [rax], 2
0x18004bd4e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004bd52  test    rcx, rcx
0x18004bd55  jz      short loc_18004BD5D
0x18004bd57  call    cs:__imp_ReleaseSRWLockExclusive
0x18004bd5d  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004bd62  mov     r9, rax
0x18004bd65  mov     ecx, [rax]
0x18004bd67  cmp     ecx, 4
0x18004bd6a  jbe     loc_18004BFA8
0x18004bd70  mov     rax, [rax+18h]
0x18004bd74  mov     rcx, [r9+10h]
0x18004bd78  mov     edx, 10000h
0x18004bd7d  test    rdx, rcx
0x18004bd80  jz      loc_18004BFA8
0x18004bd86  mov     rcx, rax
0x18004bd89  and     rcx, rdx
0x18004bd8c  cmp     rcx, rax
0x18004bd8f  jnz     loc_18004BFA8
0x18004bd95  mov     rax, [rdi+30h]
0x18004bd99  mov     [rbp+var_50], rax
0x18004bd9d  mov     eax, [rdi+44h]
0x18004bda0  mov     dword ptr [rbp+var_78+4], eax
0x18004bda3  mov     eax, [rdi+10h]
0x18004bda6  mov     dword ptr [rbp+var_70], eax
0x18004bda9  mov     rax, [rdi+78h]
0x18004bdad  mov     [rbp+var_48], rax
0x18004bdb1  mov     rax, [rdi+70h]
0x18004bdb5  mov     [rbp+var_40], rax
0x18004bdb9  mov     eax, [rdi+68h]
0x18004bdbc  mov     dword ptr [rbp+var_70+4], eax
0x18004bdbf  mov     rax, [rdi+60h]
0x18004bdc3  mov     [rbp+var_38], rax
0x18004bdc7  mov     rax, [rdi+58h]
0x18004bdcb  mov     [rbp+var_30], rax
0x18004bdcf  mov     eax, [rdi+50h]
0x18004bdd2  mov     dword ptr [rbp+var_68], eax
0x18004bdd5  mov     rax, [rdi+48h]
0x18004bdd9  mov     [rbp+var_28], rax
0x18004bddd  mov     eax, [rdi+20h]
0x18004bde0  mov     dword ptr [rbp+var_68+4], eax
0x18004bde3  mov     rax, [rdi+18h]
0x18004bde7  mov     [rbp+var_20], rax
0x18004bdeb  mov     eax, [rdi]
0x18004bded  mov     [rbp+var_60], eax
0x18004bdf0  mov     rax, [rdi+80h]
0x18004bdf7  mov     [rbp+var_18], rax
0x18004bdfb  mov     eax, [rdi+40h]
0x18004bdfe  mov     dword ptr [rbp+var_78], eax
0x18004be01  mov     rax, [rdi+38h]
0x18004be05  mov     [rbp+var_10], rax
0x18004be09  mov     eax, [rdi+8]
0x18004be0c  mov     dword ptr [rbp+SRWLock], eax
0x18004be0f  mov     [rbp+var_8], 1000000h
0x18004be17  mov     [rbp+var_58], 0
0x18004be1f  mov     r8, [rbx+110h]
0x18004be26  add     r8, 8; int
0x18004be2a  lea     rax, [rbp+var_50]
0x18004be2e  mov     [rsp+140h+var_90], rax; __int64
0x18004be36  lea     rax, [rbp+var_78+4]
0x18004be3a  mov     [rsp+140h+var_98], rax; __int64
0x18004be42  lea     rax, [rbp+var_70]
0x18004be46  mov     [rsp+140h+var_A0], rax; __int64
0x18004be4e  lea     rax, [rbp+var_48]
0x18004be52  mov     [rsp+140h+var_A8], rax; __int64
0x18004be5a  lea     rax, [rbp+var_40]
0x18004be5e  mov     [rsp+140h+var_B0], rax; __int64
0x18004be66  lea     rax, [rbp+var_70+4]
0x18004be6a  mov     [rsp+140h+var_B8], rax; __int64
0x18004be72  lea     rax, [rbp+var_38]
0x18004be76  mov     [rsp+140h+var_C0], rax; __int64
0x18004be7e  lea     rax, [rbp+var_30]
0x18004be82  mov     [rsp+140h+var_C8], rax; __int64
0x18004be87  lea     rax, [rbp+var_68]
0x18004be8b  mov     [rsp+140h+var_D0], rax; __int64
0x18004be90  lea     rax, [rbp+var_28]
0x18004be94  mov     [rsp+140h+var_D8], rax; __int64
0x18004be99  lea     rax, [rbp+var_68+4]
0x18004be9d  mov     [rsp+140h+var_E0], rax; __int64
0x18004bea2  lea     rax, [rbp+var_20]
0x18004bea6  mov     [rsp+140h+var_E8], rax; __int64
0x18004beab  lea     rax, [rbp+var_60]
0x18004beaf  mov     [rsp+140h+var_F0], rax; __int64
0x18004beb4  lea     rax, [rbp+var_18]
0x18004beb8  mov     [rsp+140h+var_F8], rax; __int64
0x18004bebd  lea     rax, [rbp+var_78]
0x18004bec1  mov     [rsp+140h+var_100], rax; __int64
0x18004bec6  lea     rax, [rbp+var_10]
0x18004beca  mov     [rsp+140h+var_108], rax; __int64
0x18004becf  lea     rax, [rbp+SRWLock]
0x18004bed3  mov     [rsp+140h+var_110], rax; __int64
0x18004bed8  lea     rax, [rbp+var_8]
0x18004bedc  mov     [rsp+140h+var_118], rax; __int64
0x18004bee1  lea     rax, [rbp+var_58]
0x18004bee5  mov     [rsp+140h+var_120], rax; __int64
0x18004beea  lea     rdx, byte_1800C7C95; int
0x18004bef1  mov     rcx, r9; int
0x18004bef4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004bef9  jmp     loc_18004BFA8
0x18004befe  mov     [rbp+SRWLock], 0
0x18004bf06  lea     rdx, [rbp+SRWLock]
0x18004bf0a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004bf0f  mov     rax, [rbx+110h]
0x18004bf16  mov     dword ptr [rax], 2
0x18004bf1c  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004bf20  test    rcx, rcx
0x18004bf23  jz      short loc_18004BF2B
0x18004bf25  call    cs:__imp_ReleaseSRWLockExclusive
0x18004bf2b  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004bf30  mov     rdi, rax
0x18004bf33  mov     ecx, [rax]
0x18004bf35  cmp     ecx, 4
0x18004bf38  jbe     short loc_18004BFA8
0x18004bf3a  mov     rax, [rax+18h]
0x18004bf3e  mov     rcx, [rdi+10h]
0x18004bf42  mov     edx, 10000h
0x18004bf47  test    rdx, rcx
0x18004bf4a  jz      short loc_18004BFA8
0x18004bf4c  mov     rcx, rax
0x18004bf4f  and     rcx, rdx
0x18004bf52  cmp     rcx, rax
0x18004bf55  jnz     short loc_18004BFA8
0x18004bf57  call    cs:__imp_GetCurrentThreadId
0x18004bf5d  mov     dword ptr [rbp+SRWLock], eax
0x18004bf60  mov     r8, [rbx+110h]
0x18004bf67  mov     eax, [r8+48h]
0x18004bf6b  mov     dword ptr [rbp+var_78], eax
0x18004bf6e  mov     [rbp+var_58], 0
0x18004bf76  add     r8, 8
0x18004bf7a  lea     rax, [rbp+SRWLock]
0x18004bf7e  mov     [rsp+140h+var_110], rax
0x18004bf83  lea     rax, [rbp+var_78]
0x18004bf87  mov     [rsp+140h+var_118], rax
0x18004bf8c  lea     rax, [rbp+var_58]
0x18004bf90  mov     [rsp+140h+var_120], rax
0x18004bf95  xor     r9d, r9d
0x18004bf98  lea     rdx, unk_1800C8428
0x18004bf9f  mov     rcx, rdi
0x18004bfa2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004bfa7  nop
0x18004bfa8  lea     rcx, [rbx+120h]; this
0x18004bfaf  cmp     dword ptr [rcx+18h], 0
0x18004bfb3  jz      short loc_18004BFBB
0x18004bfb5  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18004bfba  nop
0x18004bfbb  lea     r11, [rsp+140h+var_s0]
0x18004bfc3  mov     rbx, [r11+18h]
0x18004bfc7  mov     rdi, [r11+20h]
0x18004bfcb  mov     rsp, r11
0x18004bfce  pop     rbp
0x18004bfcf  retn
```
