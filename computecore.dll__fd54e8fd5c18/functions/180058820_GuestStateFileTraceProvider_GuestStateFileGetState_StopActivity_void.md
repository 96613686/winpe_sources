# GuestStateFileTraceProvider::GuestStateFileGetState::StopActivity(void)

- ea: `0x180058820`
- end: `0x180058b00`
- name: `?StopActivity@GuestStateFileGetState@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileGetState *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x180058820`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058887`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058a55`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058887`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058a55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058a87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058a87`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileGetState::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileGetState *this)
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
          (int)&byte_1800C9047,
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
          (unsigned int)&unk_1800C8FF0,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileGetState *)((char *)this + 288));
}

```

## disassembly

```asm
0x180058820  mov     [rsp-8+arg_8], rbx
0x180058825  mov     [rsp-8+arg_10], rdi
0x18005882a  push    rbp
0x18005882b  mov     rbp, rsp
0x18005882e  sub     rsp, 140h
0x180058835  mov     rbx, rcx
0x180058838  mov     rdi, [rcx+110h]
0x18005883f  mov     eax, [rdi+48h]
0x180058842  test    eax, eax
0x180058844  jns     loc_180058A2E
0x18005884a  add     rdi, 50h ; 'P'
0x18005884e  cmp     eax, [rdi+8]
0x180058851  jnz     loc_180058A2E
0x180058857  test    rdi, rdi
0x18005885a  jz      loc_180058A2E
0x180058860  mov     [rbp+SRWLock], 0
0x180058868  lea     rdx, [rbp+SRWLock]
0x18005886c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180058871  mov     rax, [rbx+110h]
0x180058878  mov     dword ptr [rax], 2
0x18005887e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180058882  test    rcx, rcx
0x180058885  jz      short loc_18005888D
0x180058887  call    cs:__imp_ReleaseSRWLockExclusive
0x18005888d  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180058892  mov     r9, rax
0x180058895  mov     ecx, [rax]
0x180058897  cmp     ecx, 4
0x18005889a  jbe     loc_180058AD8
0x1800588a0  mov     rax, [rax+18h]
0x1800588a4  mov     rcx, [r9+10h]
0x1800588a8  mov     edx, 1000h
0x1800588ad  test    rdx, rcx
0x1800588b0  jz      loc_180058AD8
0x1800588b6  mov     rcx, rax
0x1800588b9  and     rcx, rdx
0x1800588bc  cmp     rcx, rax
0x1800588bf  jnz     loc_180058AD8
0x1800588c5  mov     rax, [rdi+30h]
0x1800588c9  mov     [rbp+var_50], rax
0x1800588cd  mov     eax, [rdi+44h]
0x1800588d0  mov     dword ptr [rbp+var_78+4], eax
0x1800588d3  mov     eax, [rdi+10h]
0x1800588d6  mov     dword ptr [rbp+var_70], eax
0x1800588d9  mov     rax, [rdi+78h]
0x1800588dd  mov     [rbp+var_48], rax
0x1800588e1  mov     rax, [rdi+70h]
0x1800588e5  mov     [rbp+var_40], rax
0x1800588e9  mov     eax, [rdi+68h]
0x1800588ec  mov     dword ptr [rbp+var_70+4], eax
0x1800588ef  mov     rax, [rdi+60h]
0x1800588f3  mov     [rbp+var_38], rax
0x1800588f7  mov     rax, [rdi+58h]
0x1800588fb  mov     [rbp+var_30], rax
0x1800588ff  mov     eax, [rdi+50h]
0x180058902  mov     dword ptr [rbp+var_68], eax
0x180058905  mov     rax, [rdi+48h]
0x180058909  mov     [rbp+var_28], rax
0x18005890d  mov     eax, [rdi+20h]
0x180058910  mov     dword ptr [rbp+var_68+4], eax
0x180058913  mov     rax, [rdi+18h]
0x180058917  mov     [rbp+var_20], rax
0x18005891b  mov     eax, [rdi]
0x18005891d  mov     [rbp+var_60], eax
0x180058920  mov     rax, [rdi+80h]
0x180058927  mov     [rbp+var_18], rax
0x18005892b  mov     eax, [rdi+40h]
0x18005892e  mov     dword ptr [rbp+var_78], eax
0x180058931  mov     rax, [rdi+38h]
0x180058935  mov     [rbp+var_10], rax
0x180058939  mov     eax, [rdi+8]
0x18005893c  mov     dword ptr [rbp+SRWLock], eax
0x18005893f  mov     [rbp+var_8], 1000000h
0x180058947  mov     [rbp+var_58], 0
0x18005894f  mov     r8, [rbx+110h]
0x180058956  add     r8, 8; int
0x18005895a  lea     rax, [rbp+var_50]
0x18005895e  mov     [rsp+140h+var_90], rax; __int64
0x180058966  lea     rax, [rbp+var_78+4]
0x18005896a  mov     [rsp+140h+var_98], rax; __int64
0x180058972  lea     rax, [rbp+var_70]
0x180058976  mov     [rsp+140h+var_A0], rax; __int64
0x18005897e  lea     rax, [rbp+var_48]
0x180058982  mov     [rsp+140h+var_A8], rax; __int64
0x18005898a  lea     rax, [rbp+var_40]
0x18005898e  mov     [rsp+140h+var_B0], rax; __int64
0x180058996  lea     rax, [rbp+var_70+4]
0x18005899a  mov     [rsp+140h+var_B8], rax; __int64
0x1800589a2  lea     rax, [rbp+var_38]
0x1800589a6  mov     [rsp+140h+var_C0], rax; __int64
0x1800589ae  lea     rax, [rbp+var_30]
0x1800589b2  mov     [rsp+140h+var_C8], rax; __int64
0x1800589b7  lea     rax, [rbp+var_68]
0x1800589bb  mov     [rsp+140h+var_D0], rax; __int64
0x1800589c0  lea     rax, [rbp+var_28]
0x1800589c4  mov     [rsp+140h+var_D8], rax; __int64
0x1800589c9  lea     rax, [rbp+var_68+4]
0x1800589cd  mov     [rsp+140h+var_E0], rax; __int64
0x1800589d2  lea     rax, [rbp+var_20]
0x1800589d6  mov     [rsp+140h+var_E8], rax; __int64
0x1800589db  lea     rax, [rbp+var_60]
0x1800589df  mov     [rsp+140h+var_F0], rax; __int64
0x1800589e4  lea     rax, [rbp+var_18]
0x1800589e8  mov     [rsp+140h+var_F8], rax; __int64
0x1800589ed  lea     rax, [rbp+var_78]
0x1800589f1  mov     [rsp+140h+var_100], rax; __int64
0x1800589f6  lea     rax, [rbp+var_10]
0x1800589fa  mov     [rsp+140h+var_108], rax; __int64
0x1800589ff  lea     rax, [rbp+SRWLock]
0x180058a03  mov     [rsp+140h+var_110], rax; __int64
0x180058a08  lea     rax, [rbp+var_8]
0x180058a0c  mov     [rsp+140h+var_118], rax; __int64
0x180058a11  lea     rax, [rbp+var_58]
0x180058a15  mov     [rsp+140h+var_120], rax; __int64
0x180058a1a  lea     rdx, byte_1800C9047; int
0x180058a21  mov     rcx, r9; int
0x180058a24  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180058a29  jmp     loc_180058AD8
0x180058a2e  mov     [rbp+SRWLock], 0
0x180058a36  lea     rdx, [rbp+SRWLock]
0x180058a3a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180058a3f  mov     rax, [rbx+110h]
0x180058a46  mov     dword ptr [rax], 2
0x180058a4c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180058a50  test    rcx, rcx
0x180058a53  jz      short loc_180058A5B
0x180058a55  call    cs:__imp_ReleaseSRWLockExclusive
0x180058a5b  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180058a60  mov     rdi, rax
0x180058a63  mov     ecx, [rax]
0x180058a65  cmp     ecx, 4
0x180058a68  jbe     short loc_180058AD8
0x180058a6a  mov     rax, [rax+18h]
0x180058a6e  mov     rcx, [rdi+10h]
0x180058a72  mov     edx, 1000h
0x180058a77  test    rdx, rcx
0x180058a7a  jz      short loc_180058AD8
0x180058a7c  mov     rcx, rax
0x180058a7f  and     rcx, rdx
0x180058a82  cmp     rcx, rax
0x180058a85  jnz     short loc_180058AD8
0x180058a87  call    cs:__imp_GetCurrentThreadId
0x180058a8d  mov     dword ptr [rbp+SRWLock], eax
0x180058a90  mov     r8, [rbx+110h]
0x180058a97  mov     eax, [r8+48h]
0x180058a9b  mov     dword ptr [rbp+var_78], eax
0x180058a9e  mov     [rbp+var_58], 0
0x180058aa6  add     r8, 8
0x180058aaa  lea     rax, [rbp+SRWLock]
0x180058aae  mov     [rsp+140h+var_110], rax
0x180058ab3  lea     rax, [rbp+var_78]
0x180058ab7  mov     [rsp+140h+var_118], rax
0x180058abc  lea     rax, [rbp+var_58]
0x180058ac0  mov     [rsp+140h+var_120], rax
0x180058ac5  xor     r9d, r9d
0x180058ac8  lea     rdx, unk_1800C8FF0
0x180058acf  mov     rcx, rdi
0x180058ad2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180058ad7  nop
0x180058ad8  lea     rcx, [rbx+120h]; this
0x180058adf  cmp     dword ptr [rcx+18h], 0
0x180058ae3  jz      short loc_180058AEB
0x180058ae5  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180058aea  nop
0x180058aeb  lea     r11, [rsp+140h+var_s0]
0x180058af3  mov     rbx, [r11+18h]
0x180058af7  mov     rdi, [r11+20h]
0x180058afb  mov     rsp, r11
0x180058afe  pop     rbp
0x180058aff  retn
```
