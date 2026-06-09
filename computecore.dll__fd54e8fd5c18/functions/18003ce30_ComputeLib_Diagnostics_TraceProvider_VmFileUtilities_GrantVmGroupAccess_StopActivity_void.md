# ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmGroupAccess::StopActivity(void)

- ea: `0x18003ce30`
- end: `0x18003d106`
- name: `?StopActivity@VmFileUtilities_GrantVmGroupAccess@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `726`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmGroupAccess *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x180014de4`
- `0x18001558c`
- `0x18003ce30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ce97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d060`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ce97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d060`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d08d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d08d`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmGroupAccess::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmGroupAccess *this)
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
      if ( (*((_QWORD *)v6 + 2) & 0x40) != 0 && (v7 & 0x40) == v7 )
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
          (int)&byte_1800C6F75,
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
      if ( (*((_QWORD *)v9 + 2) & 0x40) != 0 && (v10 & 0x40) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)&word_1800C6C26,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_GrantVmGroupAccess *)((char *)this + 288));
}

```

## disassembly

```asm
0x18003ce30  mov     [rsp-8+arg_8], rbx
0x18003ce35  mov     [rsp-8+arg_10], rdi
0x18003ce3a  push    rbp
0x18003ce3b  mov     rbp, rsp
0x18003ce3e  sub     rsp, 140h
0x18003ce45  mov     rbx, rcx
0x18003ce48  mov     rdi, [rcx+110h]
0x18003ce4f  mov     eax, [rdi+48h]
0x18003ce52  test    eax, eax
0x18003ce54  jns     loc_18003D039
0x18003ce5a  add     rdi, 50h ; 'P'
0x18003ce5e  cmp     eax, [rdi+8]
0x18003ce61  jnz     loc_18003D039
0x18003ce67  test    rdi, rdi
0x18003ce6a  jz      loc_18003D039
0x18003ce70  mov     [rbp+SRWLock], 0
0x18003ce78  lea     rdx, [rbp+SRWLock]
0x18003ce7c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003ce81  mov     rax, [rbx+110h]
0x18003ce88  mov     dword ptr [rax], 2
0x18003ce8e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003ce92  test    rcx, rcx
0x18003ce95  jz      short loc_18003CE9D
0x18003ce97  call    cs:__imp_ReleaseSRWLockExclusive
0x18003ce9d  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003cea2  mov     r9, rax
0x18003cea5  mov     ecx, [rax]
0x18003cea7  cmp     ecx, 4
0x18003ceaa  jbe     loc_18003D0DE
0x18003ceb0  mov     rax, [rax+18h]
0x18003ceb4  mov     rcx, [r9+10h]
0x18003ceb8  test    cl, 40h
0x18003cebb  jz      loc_18003D0DE
0x18003cec1  mov     rcx, rax
0x18003cec4  and     ecx, 40h
0x18003cec7  cmp     rcx, rax
0x18003ceca  jnz     loc_18003D0DE
0x18003ced0  mov     rax, [rdi+30h]
0x18003ced4  mov     [rbp+var_50], rax
0x18003ced8  mov     eax, [rdi+44h]
0x18003cedb  mov     dword ptr [rbp+var_78+4], eax
0x18003cede  mov     eax, [rdi+10h]
0x18003cee1  mov     dword ptr [rbp+var_70], eax
0x18003cee4  mov     rax, [rdi+78h]
0x18003cee8  mov     [rbp+var_48], rax
0x18003ceec  mov     rax, [rdi+70h]
0x18003cef0  mov     [rbp+var_40], rax
0x18003cef4  mov     eax, [rdi+68h]
0x18003cef7  mov     dword ptr [rbp+var_70+4], eax
0x18003cefa  mov     rax, [rdi+60h]
0x18003cefe  mov     [rbp+var_38], rax
0x18003cf02  mov     rax, [rdi+58h]
0x18003cf06  mov     [rbp+var_30], rax
0x18003cf0a  mov     eax, [rdi+50h]
0x18003cf0d  mov     dword ptr [rbp+var_68], eax
0x18003cf10  mov     rax, [rdi+48h]
0x18003cf14  mov     [rbp+var_28], rax
0x18003cf18  mov     eax, [rdi+20h]
0x18003cf1b  mov     dword ptr [rbp+var_68+4], eax
0x18003cf1e  mov     rax, [rdi+18h]
0x18003cf22  mov     [rbp+var_20], rax
0x18003cf26  mov     eax, [rdi]
0x18003cf28  mov     [rbp+var_60], eax
0x18003cf2b  mov     rax, [rdi+80h]
0x18003cf32  mov     [rbp+var_18], rax
0x18003cf36  mov     eax, [rdi+40h]
0x18003cf39  mov     dword ptr [rbp+var_78], eax
0x18003cf3c  mov     rax, [rdi+38h]
0x18003cf40  mov     [rbp+var_10], rax
0x18003cf44  mov     eax, [rdi+8]
0x18003cf47  mov     dword ptr [rbp+SRWLock], eax
0x18003cf4a  mov     [rbp+var_8], 1000000h
0x18003cf52  mov     [rbp+var_58], 0
0x18003cf5a  mov     r8, [rbx+110h]
0x18003cf61  add     r8, 8; int
0x18003cf65  lea     rax, [rbp+var_50]
0x18003cf69  mov     [rsp+140h+var_90], rax; __int64
0x18003cf71  lea     rax, [rbp+var_78+4]
0x18003cf75  mov     [rsp+140h+var_98], rax; __int64
0x18003cf7d  lea     rax, [rbp+var_70]
0x18003cf81  mov     [rsp+140h+var_A0], rax; __int64
0x18003cf89  lea     rax, [rbp+var_48]
0x18003cf8d  mov     [rsp+140h+var_A8], rax; __int64
0x18003cf95  lea     rax, [rbp+var_40]
0x18003cf99  mov     [rsp+140h+var_B0], rax; __int64
0x18003cfa1  lea     rax, [rbp+var_70+4]
0x18003cfa5  mov     [rsp+140h+var_B8], rax; __int64
0x18003cfad  lea     rax, [rbp+var_38]
0x18003cfb1  mov     [rsp+140h+var_C0], rax; __int64
0x18003cfb9  lea     rax, [rbp+var_30]
0x18003cfbd  mov     [rsp+140h+var_C8], rax; __int64
0x18003cfc2  lea     rax, [rbp+var_68]
0x18003cfc6  mov     [rsp+140h+var_D0], rax; __int64
0x18003cfcb  lea     rax, [rbp+var_28]
0x18003cfcf  mov     [rsp+140h+var_D8], rax; __int64
0x18003cfd4  lea     rax, [rbp+var_68+4]
0x18003cfd8  mov     [rsp+140h+var_E0], rax; __int64
0x18003cfdd  lea     rax, [rbp+var_20]
0x18003cfe1  mov     [rsp+140h+var_E8], rax; __int64
0x18003cfe6  lea     rax, [rbp+var_60]
0x18003cfea  mov     [rsp+140h+var_F0], rax; __int64
0x18003cfef  lea     rax, [rbp+var_18]
0x18003cff3  mov     [rsp+140h+var_F8], rax; __int64
0x18003cff8  lea     rax, [rbp+var_78]
0x18003cffc  mov     [rsp+140h+var_100], rax; __int64
0x18003d001  lea     rax, [rbp+var_10]
0x18003d005  mov     [rsp+140h+var_108], rax; __int64
0x18003d00a  lea     rax, [rbp+SRWLock]
0x18003d00e  mov     [rsp+140h+var_110], rax; __int64
0x18003d013  lea     rax, [rbp+var_8]
0x18003d017  mov     [rsp+140h+var_118], rax; __int64
0x18003d01c  lea     rax, [rbp+var_58]
0x18003d020  mov     [rsp+140h+var_120], rax; __int64
0x18003d025  lea     rdx, byte_1800C6F75; int
0x18003d02c  mov     rcx, r9; int
0x18003d02f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003d034  jmp     loc_18003D0DE
0x18003d039  mov     [rbp+SRWLock], 0
0x18003d041  lea     rdx, [rbp+SRWLock]
0x18003d045  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003d04a  mov     rax, [rbx+110h]
0x18003d051  mov     dword ptr [rax], 2
0x18003d057  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003d05b  test    rcx, rcx
0x18003d05e  jz      short loc_18003D066
0x18003d060  call    cs:__imp_ReleaseSRWLockExclusive
0x18003d066  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003d06b  mov     rdi, rax
0x18003d06e  mov     ecx, [rax]
0x18003d070  cmp     ecx, 4
0x18003d073  jbe     short loc_18003D0DE
0x18003d075  mov     rax, [rax+18h]
0x18003d079  mov     rcx, [rdi+10h]
0x18003d07d  test    cl, 40h
0x18003d080  jz      short loc_18003D0DE
0x18003d082  mov     rcx, rax
0x18003d085  and     ecx, 40h
0x18003d088  cmp     rcx, rax
0x18003d08b  jnz     short loc_18003D0DE
0x18003d08d  call    cs:__imp_GetCurrentThreadId
0x18003d093  mov     dword ptr [rbp+SRWLock], eax
0x18003d096  mov     r8, [rbx+110h]
0x18003d09d  mov     eax, [r8+48h]
0x18003d0a1  mov     dword ptr [rbp+var_78], eax
0x18003d0a4  mov     [rbp+var_58], 0
0x18003d0ac  add     r8, 8
0x18003d0b0  lea     rax, [rbp+SRWLock]
0x18003d0b4  mov     [rsp+140h+var_110], rax
0x18003d0b9  lea     rax, [rbp+var_78]
0x18003d0bd  mov     [rsp+140h+var_118], rax
0x18003d0c2  lea     rax, [rbp+var_58]
0x18003d0c6  mov     [rsp+140h+var_120], rax
0x18003d0cb  xor     r9d, r9d
0x18003d0ce  lea     rdx, word_1800C6C26
0x18003d0d5  mov     rcx, rdi
0x18003d0d8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003d0dd  nop
0x18003d0de  lea     rcx, [rbx+120h]; this
0x18003d0e5  cmp     dword ptr [rcx+18h], 0
0x18003d0e9  jz      short loc_18003D0F1
0x18003d0eb  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003d0f0  nop
0x18003d0f1  lea     r11, [rsp+140h+var_s0]
0x18003d0f9  mov     rbx, [r11+18h]
0x18003d0fd  mov     rdi, [r11+20h]
0x18003d101  mov     rsp, r11
0x18003d104  pop     rbp
0x18003d105  retn
```
