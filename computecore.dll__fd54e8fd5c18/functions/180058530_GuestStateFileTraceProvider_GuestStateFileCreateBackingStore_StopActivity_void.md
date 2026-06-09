# GuestStateFileTraceProvider::GuestStateFileCreateBackingStore::StopActivity(void)

- ea: `0x180058530`
- end: `0x180058810`
- name: `?StopActivity@GuestStateFileCreateBackingStore@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileCreateBackingStore *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x180058530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058597`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058765`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058597`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058765`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058797`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058797`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileCreateBackingStore::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileCreateBackingStore *this)
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
          (int)&unk_1800CA5C0,
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
          (unsigned int)byte_1800CA4F9,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileCreateBackingStore *)((char *)this + 288));
}

```

## disassembly

```asm
0x180058530  mov     [rsp-8+arg_8], rbx
0x180058535  mov     [rsp-8+arg_10], rdi
0x18005853a  push    rbp
0x18005853b  mov     rbp, rsp
0x18005853e  sub     rsp, 140h
0x180058545  mov     rbx, rcx
0x180058548  mov     rdi, [rcx+110h]
0x18005854f  mov     eax, [rdi+48h]
0x180058552  test    eax, eax
0x180058554  jns     loc_18005873E
0x18005855a  add     rdi, 50h ; 'P'
0x18005855e  cmp     eax, [rdi+8]
0x180058561  jnz     loc_18005873E
0x180058567  test    rdi, rdi
0x18005856a  jz      loc_18005873E
0x180058570  mov     [rbp+SRWLock], 0
0x180058578  lea     rdx, [rbp+SRWLock]
0x18005857c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180058581  mov     rax, [rbx+110h]
0x180058588  mov     dword ptr [rax], 2
0x18005858e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180058592  test    rcx, rcx
0x180058595  jz      short loc_18005859D
0x180058597  call    cs:__imp_ReleaseSRWLockExclusive
0x18005859d  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x1800585a2  mov     r9, rax
0x1800585a5  mov     ecx, [rax]
0x1800585a7  cmp     ecx, 4
0x1800585aa  jbe     loc_1800587E8
0x1800585b0  mov     rax, [rax+18h]
0x1800585b4  mov     rcx, [r9+10h]
0x1800585b8  mov     edx, 1000h
0x1800585bd  test    rdx, rcx
0x1800585c0  jz      loc_1800587E8
0x1800585c6  mov     rcx, rax
0x1800585c9  and     rcx, rdx
0x1800585cc  cmp     rcx, rax
0x1800585cf  jnz     loc_1800587E8
0x1800585d5  mov     rax, [rdi+30h]
0x1800585d9  mov     [rbp+var_50], rax
0x1800585dd  mov     eax, [rdi+44h]
0x1800585e0  mov     dword ptr [rbp+var_78+4], eax
0x1800585e3  mov     eax, [rdi+10h]
0x1800585e6  mov     dword ptr [rbp+var_70], eax
0x1800585e9  mov     rax, [rdi+78h]
0x1800585ed  mov     [rbp+var_48], rax
0x1800585f1  mov     rax, [rdi+70h]
0x1800585f5  mov     [rbp+var_40], rax
0x1800585f9  mov     eax, [rdi+68h]
0x1800585fc  mov     dword ptr [rbp+var_70+4], eax
0x1800585ff  mov     rax, [rdi+60h]
0x180058603  mov     [rbp+var_38], rax
0x180058607  mov     rax, [rdi+58h]
0x18005860b  mov     [rbp+var_30], rax
0x18005860f  mov     eax, [rdi+50h]
0x180058612  mov     dword ptr [rbp+var_68], eax
0x180058615  mov     rax, [rdi+48h]
0x180058619  mov     [rbp+var_28], rax
0x18005861d  mov     eax, [rdi+20h]
0x180058620  mov     dword ptr [rbp+var_68+4], eax
0x180058623  mov     rax, [rdi+18h]
0x180058627  mov     [rbp+var_20], rax
0x18005862b  mov     eax, [rdi]
0x18005862d  mov     [rbp+var_60], eax
0x180058630  mov     rax, [rdi+80h]
0x180058637  mov     [rbp+var_18], rax
0x18005863b  mov     eax, [rdi+40h]
0x18005863e  mov     dword ptr [rbp+var_78], eax
0x180058641  mov     rax, [rdi+38h]
0x180058645  mov     [rbp+var_10], rax
0x180058649  mov     eax, [rdi+8]
0x18005864c  mov     dword ptr [rbp+SRWLock], eax
0x18005864f  mov     [rbp+var_8], 1000000h
0x180058657  mov     [rbp+var_58], 0
0x18005865f  mov     r8, [rbx+110h]
0x180058666  add     r8, 8; int
0x18005866a  lea     rax, [rbp+var_50]
0x18005866e  mov     [rsp+140h+var_90], rax; __int64
0x180058676  lea     rax, [rbp+var_78+4]
0x18005867a  mov     [rsp+140h+var_98], rax; __int64
0x180058682  lea     rax, [rbp+var_70]
0x180058686  mov     [rsp+140h+var_A0], rax; __int64
0x18005868e  lea     rax, [rbp+var_48]
0x180058692  mov     [rsp+140h+var_A8], rax; __int64
0x18005869a  lea     rax, [rbp+var_40]
0x18005869e  mov     [rsp+140h+var_B0], rax; __int64
0x1800586a6  lea     rax, [rbp+var_70+4]
0x1800586aa  mov     [rsp+140h+var_B8], rax; __int64
0x1800586b2  lea     rax, [rbp+var_38]
0x1800586b6  mov     [rsp+140h+var_C0], rax; __int64
0x1800586be  lea     rax, [rbp+var_30]
0x1800586c2  mov     [rsp+140h+var_C8], rax; __int64
0x1800586c7  lea     rax, [rbp+var_68]
0x1800586cb  mov     [rsp+140h+var_D0], rax; __int64
0x1800586d0  lea     rax, [rbp+var_28]
0x1800586d4  mov     [rsp+140h+var_D8], rax; __int64
0x1800586d9  lea     rax, [rbp+var_68+4]
0x1800586dd  mov     [rsp+140h+var_E0], rax; __int64
0x1800586e2  lea     rax, [rbp+var_20]
0x1800586e6  mov     [rsp+140h+var_E8], rax; __int64
0x1800586eb  lea     rax, [rbp+var_60]
0x1800586ef  mov     [rsp+140h+var_F0], rax; __int64
0x1800586f4  lea     rax, [rbp+var_18]
0x1800586f8  mov     [rsp+140h+var_F8], rax; __int64
0x1800586fd  lea     rax, [rbp+var_78]
0x180058701  mov     [rsp+140h+var_100], rax; __int64
0x180058706  lea     rax, [rbp+var_10]
0x18005870a  mov     [rsp+140h+var_108], rax; __int64
0x18005870f  lea     rax, [rbp+SRWLock]
0x180058713  mov     [rsp+140h+var_110], rax; __int64
0x180058718  lea     rax, [rbp+var_8]
0x18005871c  mov     [rsp+140h+var_118], rax; __int64
0x180058721  lea     rax, [rbp+var_58]
0x180058725  mov     [rsp+140h+var_120], rax; __int64
0x18005872a  lea     rdx, unk_1800CA5C0; int
0x180058731  mov     rcx, r9; int
0x180058734  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180058739  jmp     loc_1800587E8
0x18005873e  mov     [rbp+SRWLock], 0
0x180058746  lea     rdx, [rbp+SRWLock]
0x18005874a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005874f  mov     rax, [rbx+110h]
0x180058756  mov     dword ptr [rax], 2
0x18005875c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180058760  test    rcx, rcx
0x180058763  jz      short loc_18005876B
0x180058765  call    cs:__imp_ReleaseSRWLockExclusive
0x18005876b  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180058770  mov     rdi, rax
0x180058773  mov     ecx, [rax]
0x180058775  cmp     ecx, 4
0x180058778  jbe     short loc_1800587E8
0x18005877a  mov     rax, [rax+18h]
0x18005877e  mov     rcx, [rdi+10h]
0x180058782  mov     edx, 1000h
0x180058787  test    rdx, rcx
0x18005878a  jz      short loc_1800587E8
0x18005878c  mov     rcx, rax
0x18005878f  and     rcx, rdx
0x180058792  cmp     rcx, rax
0x180058795  jnz     short loc_1800587E8
0x180058797  call    cs:__imp_GetCurrentThreadId
0x18005879d  mov     dword ptr [rbp+SRWLock], eax
0x1800587a0  mov     r8, [rbx+110h]
0x1800587a7  mov     eax, [r8+48h]
0x1800587ab  mov     dword ptr [rbp+var_78], eax
0x1800587ae  mov     [rbp+var_58], 0
0x1800587b6  add     r8, 8
0x1800587ba  lea     rax, [rbp+SRWLock]
0x1800587be  mov     [rsp+140h+var_110], rax
0x1800587c3  lea     rax, [rbp+var_78]
0x1800587c7  mov     [rsp+140h+var_118], rax
0x1800587cc  lea     rax, [rbp+var_58]
0x1800587d0  mov     [rsp+140h+var_120], rax
0x1800587d5  xor     r9d, r9d
0x1800587d8  lea     rdx, byte_1800CA4F9
0x1800587df  mov     rcx, rdi
0x1800587e2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800587e7  nop
0x1800587e8  lea     rcx, [rbx+120h]; this
0x1800587ef  cmp     dword ptr [rcx+18h], 0
0x1800587f3  jz      short loc_1800587FB
0x1800587f5  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800587fa  nop
0x1800587fb  lea     r11, [rsp+140h+var_s0]
0x180058803  mov     rbx, [r11+18h]
0x180058807  mov     rdi, [r11+20h]
0x18005880b  mov     rsp, r11
0x18005880e  pop     rbp
0x18005880f  retn
```
