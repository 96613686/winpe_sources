# VstorlibTraceProvider::VstorMountDevice::StopActivity(void)

- ea: `0x180099010`
- end: `0x1800992f0`
- name: `?StopActivity@VstorMountDevice@VstorlibTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(VstorlibTraceProvider::VstorMountDevice *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180097be4`
- `0x180099010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180099077`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180099245`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180099077`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180099245`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180099277`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180099277`

## pseudocode

```c
void __fastcall VstorlibTraceProvider::VstorMountDevice::StopActivity(VstorlibTraceProvider::VstorMountDevice *this)
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
          (int)&byte_1800CE929,
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
          (unsigned int)qword_1800CEAD8,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((VstorlibTraceProvider::VstorMountDevice *)((char *)this + 288));
}

```

## disassembly

```asm
0x180099010  mov     [rsp-8+arg_8], rbx
0x180099015  mov     [rsp-8+arg_10], rdi
0x18009901a  push    rbp
0x18009901b  mov     rbp, rsp
0x18009901e  sub     rsp, 140h
0x180099025  mov     rbx, rcx
0x180099028  mov     rdi, [rcx+110h]
0x18009902f  mov     eax, [rdi+48h]
0x180099032  test    eax, eax
0x180099034  jns     loc_18009921E
0x18009903a  add     rdi, 50h ; 'P'
0x18009903e  cmp     eax, [rdi+8]
0x180099041  jnz     loc_18009921E
0x180099047  test    rdi, rdi
0x18009904a  jz      loc_18009921E
0x180099050  mov     [rbp+SRWLock], 0
0x180099058  lea     rdx, [rbp+SRWLock]
0x18009905c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180099061  mov     rax, [rbx+110h]
0x180099068  mov     dword ptr [rax], 2
0x18009906e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180099072  test    rcx, rcx
0x180099075  jz      short loc_18009907D
0x180099077  call    cs:__imp_ReleaseSRWLockExclusive
0x18009907d  call    ?Provider@VstorlibTraceProvider@@SAPEBU_tlgProvider_t@@XZ; VstorlibTraceProvider::Provider(void)
0x180099082  mov     r9, rax
0x180099085  mov     ecx, [rax]
0x180099087  cmp     ecx, 4
0x18009908a  jbe     loc_1800992C8
0x180099090  mov     rax, [rax+18h]
0x180099094  mov     rcx, [r9+10h]
0x180099098  mov     edx, 200h
0x18009909d  test    rdx, rcx
0x1800990a0  jz      loc_1800992C8
0x1800990a6  mov     rcx, rax
0x1800990a9  and     rcx, rdx
0x1800990ac  cmp     rcx, rax
0x1800990af  jnz     loc_1800992C8
0x1800990b5  mov     rax, [rdi+30h]
0x1800990b9  mov     [rbp+var_50], rax
0x1800990bd  mov     eax, [rdi+44h]
0x1800990c0  mov     dword ptr [rbp+var_78+4], eax
0x1800990c3  mov     eax, [rdi+10h]
0x1800990c6  mov     dword ptr [rbp+var_70], eax
0x1800990c9  mov     rax, [rdi+78h]
0x1800990cd  mov     [rbp+var_48], rax
0x1800990d1  mov     rax, [rdi+70h]
0x1800990d5  mov     [rbp+var_40], rax
0x1800990d9  mov     eax, [rdi+68h]
0x1800990dc  mov     dword ptr [rbp+var_70+4], eax
0x1800990df  mov     rax, [rdi+60h]
0x1800990e3  mov     [rbp+var_38], rax
0x1800990e7  mov     rax, [rdi+58h]
0x1800990eb  mov     [rbp+var_30], rax
0x1800990ef  mov     eax, [rdi+50h]
0x1800990f2  mov     dword ptr [rbp+var_68], eax
0x1800990f5  mov     rax, [rdi+48h]
0x1800990f9  mov     [rbp+var_28], rax
0x1800990fd  mov     eax, [rdi+20h]
0x180099100  mov     dword ptr [rbp+var_68+4], eax
0x180099103  mov     rax, [rdi+18h]
0x180099107  mov     [rbp+var_20], rax
0x18009910b  mov     eax, [rdi]
0x18009910d  mov     [rbp+var_60], eax
0x180099110  mov     rax, [rdi+80h]
0x180099117  mov     [rbp+var_18], rax
0x18009911b  mov     eax, [rdi+40h]
0x18009911e  mov     dword ptr [rbp+var_78], eax
0x180099121  mov     rax, [rdi+38h]
0x180099125  mov     [rbp+var_10], rax
0x180099129  mov     eax, [rdi+8]
0x18009912c  mov     dword ptr [rbp+SRWLock], eax
0x18009912f  mov     [rbp+var_8], 1000000h
0x180099137  mov     [rbp+var_58], 0
0x18009913f  mov     r8, [rbx+110h]
0x180099146  add     r8, 8; int
0x18009914a  lea     rax, [rbp+var_50]
0x18009914e  mov     [rsp+140h+var_90], rax; __int64
0x180099156  lea     rax, [rbp+var_78+4]
0x18009915a  mov     [rsp+140h+var_98], rax; __int64
0x180099162  lea     rax, [rbp+var_70]
0x180099166  mov     [rsp+140h+var_A0], rax; __int64
0x18009916e  lea     rax, [rbp+var_48]
0x180099172  mov     [rsp+140h+var_A8], rax; __int64
0x18009917a  lea     rax, [rbp+var_40]
0x18009917e  mov     [rsp+140h+var_B0], rax; __int64
0x180099186  lea     rax, [rbp+var_70+4]
0x18009918a  mov     [rsp+140h+var_B8], rax; __int64
0x180099192  lea     rax, [rbp+var_38]
0x180099196  mov     [rsp+140h+var_C0], rax; __int64
0x18009919e  lea     rax, [rbp+var_30]
0x1800991a2  mov     [rsp+140h+var_C8], rax; __int64
0x1800991a7  lea     rax, [rbp+var_68]
0x1800991ab  mov     [rsp+140h+var_D0], rax; __int64
0x1800991b0  lea     rax, [rbp+var_28]
0x1800991b4  mov     [rsp+140h+var_D8], rax; __int64
0x1800991b9  lea     rax, [rbp+var_68+4]
0x1800991bd  mov     [rsp+140h+var_E0], rax; __int64
0x1800991c2  lea     rax, [rbp+var_20]
0x1800991c6  mov     [rsp+140h+var_E8], rax; __int64
0x1800991cb  lea     rax, [rbp+var_60]
0x1800991cf  mov     [rsp+140h+var_F0], rax; __int64
0x1800991d4  lea     rax, [rbp+var_18]
0x1800991d8  mov     [rsp+140h+var_F8], rax; __int64
0x1800991dd  lea     rax, [rbp+var_78]
0x1800991e1  mov     [rsp+140h+var_100], rax; __int64
0x1800991e6  lea     rax, [rbp+var_10]
0x1800991ea  mov     [rsp+140h+var_108], rax; __int64
0x1800991ef  lea     rax, [rbp+SRWLock]
0x1800991f3  mov     [rsp+140h+var_110], rax; __int64
0x1800991f8  lea     rax, [rbp+var_8]
0x1800991fc  mov     [rsp+140h+var_118], rax; __int64
0x180099201  lea     rax, [rbp+var_58]
0x180099205  mov     [rsp+140h+var_120], rax; __int64
0x18009920a  lea     rdx, byte_1800CE929; int
0x180099211  mov     rcx, r9; int
0x180099214  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180099219  jmp     loc_1800992C8
0x18009921e  mov     [rbp+SRWLock], 0
0x180099226  lea     rdx, [rbp+SRWLock]
0x18009922a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18009922f  mov     rax, [rbx+110h]
0x180099236  mov     dword ptr [rax], 2
0x18009923c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180099240  test    rcx, rcx
0x180099243  jz      short loc_18009924B
0x180099245  call    cs:__imp_ReleaseSRWLockExclusive
0x18009924b  call    ?Provider@VstorlibTraceProvider@@SAPEBU_tlgProvider_t@@XZ; VstorlibTraceProvider::Provider(void)
0x180099250  mov     rdi, rax
0x180099253  mov     ecx, [rax]
0x180099255  cmp     ecx, 4
0x180099258  jbe     short loc_1800992C8
0x18009925a  mov     rax, [rax+18h]
0x18009925e  mov     rcx, [rdi+10h]
0x180099262  mov     edx, 200h
0x180099267  test    rdx, rcx
0x18009926a  jz      short loc_1800992C8
0x18009926c  mov     rcx, rax
0x18009926f  and     rcx, rdx
0x180099272  cmp     rcx, rax
0x180099275  jnz     short loc_1800992C8
0x180099277  call    cs:__imp_GetCurrentThreadId
0x18009927d  mov     dword ptr [rbp+SRWLock], eax
0x180099280  mov     r8, [rbx+110h]
0x180099287  mov     eax, [r8+48h]
0x18009928b  mov     dword ptr [rbp+var_78], eax
0x18009928e  mov     [rbp+var_58], 0
0x180099296  add     r8, 8
0x18009929a  lea     rax, [rbp+SRWLock]
0x18009929e  mov     [rsp+140h+var_110], rax
0x1800992a3  lea     rax, [rbp+var_78]
0x1800992a7  mov     [rsp+140h+var_118], rax
0x1800992ac  lea     rax, [rbp+var_58]
0x1800992b0  mov     [rsp+140h+var_120], rax
0x1800992b5  xor     r9d, r9d
0x1800992b8  lea     rdx, qword_1800CEAD8
0x1800992bf  mov     rcx, rdi
0x1800992c2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800992c7  nop
0x1800992c8  lea     rcx, [rbx+120h]; this
0x1800992cf  cmp     dword ptr [rcx+18h], 0
0x1800992d3  jz      short loc_1800992DB
0x1800992d5  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800992da  nop
0x1800992db  lea     r11, [rsp+140h+var_s0]
0x1800992e3  mov     rbx, [r11+18h]
0x1800992e7  mov     rdi, [r11+20h]
0x1800992eb  mov     rsp, r11
0x1800992ee  pop     rbp
0x1800992ef  retn
```
