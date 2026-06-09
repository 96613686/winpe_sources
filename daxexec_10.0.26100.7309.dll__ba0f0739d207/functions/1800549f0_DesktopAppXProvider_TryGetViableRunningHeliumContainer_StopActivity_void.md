# DesktopAppXProvider::TryGetViableRunningHeliumContainer::StopActivity(void)

- ea: `0x1800549f0`
- end: `0x180054cda`
- name: `?StopActivity@TryGetViableRunningHeliumContainer@DesktopAppXProvider@@MEAAXXZ`
- size: `746`
- prototype: `void __fastcall(DesktopAppXProvider::TryGetViableRunningHeliumContainer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x180001a84`
- `0x18001031c`
- `0x18001bd34`
- `0x18001be00`
- `0x1800549f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054a4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054bd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054a4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054bd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054c10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054c77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054c10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054c77`

## string_xrefs

- `0x180054c8c`: `onecore\internal\sdk\inc\wil\opensource/wil/result.h`

## pseudocode

```c
void __fastcall DesktopAppXProvider::TryGetViableRunningHeliumContainer::StopActivity(
        DesktopAppXProvider::TryGetViableRunningHeliumContainer *this)
{
  _DWORD **v1; // rdi
  int *v3; // rax
  int v4; // ecx
  int *v5; // rsi
  RTL_SRWLOCK *v6; // rcx
  __int64 v7; // r9
  _DWORD *v8; // r8
  RTL_SRWLOCK *v9; // rcx
  __int64 v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  char *v13; // rbx
  __int64 *v14; // rcx
  __int64 v15; // rax
  int v16; // [rsp+20h] [rbp-100h]
  int v17; // [rsp+A0h] [rbp-80h] BYREF
  int v18; // [rsp+A4h] [rbp-7Ch] BYREF
  __int64 v19; // [rsp+A8h] [rbp-78h] BYREF
  __int64 v20; // [rsp+B0h] [rbp-70h] BYREF
  __int64 v21; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v22; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v23; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v24; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v28[6]; // [rsp+F0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+8h]
  PSRWLOCK SRWLock; // [rsp+130h] [rbp+10h] BYREF
  int v31; // [rsp+138h] [rbp+18h] BYREF
  __int64 v32; // [rsp+140h] [rbp+20h] BYREF
  int v33; // [rsp+148h] [rbp+28h] BYREF

  v1 = (_DWORD **)((char *)this + 272);
  v3 = (int *)*((_QWORD *)this + 34);
  v4 = v3[18];
  if ( v4 >= 0 || v4 != v3[22] || (v5 = v3 + 20, v3 == (int *)-80LL) )
  {
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v9 = SRWLock;
    **v1 = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = *((_QWORD *)DesktopAppXProvider::Instance() + 1);
    if ( *(_DWORD *)v10 > 5u
      && (*(_QWORD *)(v10 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v10 + 24) & 0x200000000000LL) == *(_QWORD *)(v10 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v31 = *(_DWORD *)(v12 + 72);
      v32 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)&unk_1800E6764,
        v12 + 8,
        0,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&SRWLock);
    }
  }
  else
  {
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v6 = SRWLock;
    **v1 = 2;
    if ( v6 )
      ReleaseSRWLockExclusive(v6);
    v7 = *((_QWORD *)DesktopAppXProvider::Instance() + 1);
    if ( *(_DWORD *)v7 > 5u
      && (*(_QWORD *)(v7 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v7 + 24) & 0x200000000000LL) == *(_QWORD *)(v7 + 24) )
    {
      v8 = *v1;
      v19 = *((_QWORD *)v5 + 15);
      v20 = *((_QWORD *)v5 + 14);
      LODWORD(SRWLock) = v5[26];
      v21 = *((_QWORD *)v5 + 12);
      v22 = *((_QWORD *)v5 + 11);
      v31 = v5[20];
      v23 = *((_QWORD *)v5 + 9);
      LODWORD(v32) = v5[8];
      v24 = *((_QWORD *)v5 + 3);
      v33 = *v5;
      v25 = *((_QWORD *)v5 + 16);
      v17 = v5[16];
      v26 = *((_QWORD *)v5 + 7);
      v18 = v5[2];
      v27 = 0x1000000;
      v28[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (unsigned int)&unk_1800E67C7,
        (_DWORD)v8 + 8,
        v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v18,
        (__int64)&v26,
        (__int64)&v17,
        (__int64)&v25,
        (__int64)&v33,
        (__int64)&v24,
        (__int64)&v32,
        (__int64)&v23,
        (__int64)&v31,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&SRWLock,
        (__int64)&v20,
        (__int64)&v19);
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v13 = (char *)this + 288;
    if ( *((_DWORD *)v13 + 6) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x3BE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result.h",
        (const char *)0x8007029CLL,
        v16);
    *((_DWORD *)v13 + 6) = 0;
    v14 = *(__int64 **)v13;
    while ( 1 )
    {
      v15 = *v14;
      if ( !*v14 )
        break;
      if ( (char *)v15 == v13 )
      {
        *v14 = *((_QWORD *)v13 + 2);
        break;
      }
      v14 = (__int64 *)(v15 + 16);
      *(_QWORD *)v13 = v15 + 16;
    }
    *(_QWORD *)v13 = 0;
  }
}

```

## disassembly

```asm
0x1800549f0  push    rbp
0x1800549f2  push    rbx
0x1800549f3  push    rsi
0x1800549f4  push    rdi
0x1800549f5  lea     rbp, [rsp+18h]
0x1800549fa  sub     rsp, 108h
0x180054a01  lea     rdi, [rcx+110h]
0x180054a08  mov     rbx, rcx
0x180054a0b  mov     rax, [rdi]
0x180054a0e  mov     ecx, [rax+48h]
0x180054a11  test    ecx, ecx
0x180054a13  jns     loc_180054BBB
0x180054a19  cmp     ecx, [rax+58h]
0x180054a1c  jnz     loc_180054BBB
0x180054a22  lea     rsi, [rax+50h]
0x180054a26  test    rsi, rsi
0x180054a29  jz      loc_180054BBB
0x180054a2f  lea     rdx, [rbp+SRWLock]
0x180054a33  mov     rcx, rbx
0x180054a36  call    ?LockExclusive@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180054a3b  mov     rax, [rdi]
0x180054a3e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180054a42  mov     dword ptr [rax], 2
0x180054a48  test    rcx, rcx
0x180054a4b  jz      short loc_180054A59
0x180054a4d  call    cs:__imp_ReleaseSRWLockExclusive
0x180054a54  nop     dword ptr [rax+rax+00h]
0x180054a59  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x180054a5e  mov     r9, [rax+8]
0x180054a62  cmp     dword ptr [r9], 5
0x180054a66  jbe     loc_180054C67
0x180054a6c  mov     rcx, 200000000000h
0x180054a76  test    [r9+10h], rcx
0x180054a7a  jz      loc_180054C67
0x180054a80  mov     rax, [r9+18h]
0x180054a84  and     rax, rcx
0x180054a87  cmp     rax, [r9+18h]
0x180054a8b  jnz     loc_180054C67
0x180054a91  mov     rax, [rsi+78h]
0x180054a95  lea     rdx, unk_1800E67C7
0x180054a9c  mov     r8, [rdi]
0x180054a9f  mov     rcx, r9
0x180054aa2  mov     [rbp+var_78], rax
0x180054aa6  add     r8, 8
0x180054aaa  mov     rax, [rsi+70h]
0x180054aae  mov     [rbp+var_70], rax
0x180054ab2  mov     eax, [rsi+68h]
0x180054ab5  mov     dword ptr [rbp+SRWLock], eax
0x180054ab8  mov     rax, [rsi+60h]
0x180054abc  mov     [rbp+var_68], rax
0x180054ac0  mov     rax, [rsi+58h]
0x180054ac4  mov     [rbp+var_60], rax
0x180054ac8  mov     eax, [rsi+50h]
0x180054acb  mov     [rbp+arg_8], eax
0x180054ace  mov     rax, [rsi+48h]
0x180054ad2  mov     [rbp+var_58], rax
0x180054ad6  mov     eax, [rsi+20h]
0x180054ad9  mov     dword ptr [rbp+arg_10], eax
0x180054adc  mov     rax, [rsi+18h]
0x180054ae0  mov     [rbp+var_50], rax
0x180054ae4  mov     eax, [rsi]
0x180054ae6  mov     [rbp+arg_18], eax
0x180054ae9  mov     rax, [rsi+80h]
0x180054af0  mov     [rbp+var_48], rax
0x180054af4  mov     eax, [rsi+40h]
0x180054af7  mov     [rbp+var_80], eax
0x180054afa  mov     rax, [rsi+38h]
0x180054afe  mov     [rbp+var_40], rax
0x180054b02  mov     eax, [rsi+8]
0x180054b05  mov     [rbp+var_7C], eax
0x180054b08  mov     eax, 1000000h
0x180054b0d  mov     [rbp+var_38], rax
0x180054b11  mov     [rbp+var_30], rax
0x180054b15  lea     rax, [rbp+var_78]
0x180054b19  mov     [rsp+120h+var_88], rax
0x180054b21  lea     rax, [rbp+var_70]
0x180054b25  mov     [rsp+120h+var_90], rax
0x180054b2d  lea     rax, [rbp+SRWLock]
0x180054b31  mov     [rsp+120h+var_98], rax
0x180054b39  lea     rax, [rbp+var_68]
0x180054b3d  mov     [rsp+120h+var_A0], rax
0x180054b45  lea     rax, [rbp+var_60]
0x180054b49  mov     [rsp+120h+var_A8], rax
0x180054b4e  lea     rax, [rbp+arg_8]
0x180054b52  mov     [rsp+120h+var_B0], rax
0x180054b57  lea     rax, [rbp+var_58]
0x180054b5b  mov     [rsp+120h+var_B8], rax
0x180054b60  lea     rax, [rbp+arg_10]
0x180054b64  mov     [rsp+120h+var_C0], rax
0x180054b69  lea     rax, [rbp+var_50]
0x180054b6d  mov     [rsp+120h+var_C8], rax
0x180054b72  lea     rax, [rbp+arg_18]
0x180054b76  mov     [rsp+120h+var_D0], rax
0x180054b7b  lea     rax, [rbp+var_48]
0x180054b7f  mov     [rsp+120h+var_D8], rax
0x180054b84  lea     rax, [rbp+var_80]
0x180054b88  mov     [rsp+120h+var_E0], rax
0x180054b8d  lea     rax, [rbp+var_40]
0x180054b91  mov     [rsp+120h+var_E8], rax
0x180054b96  lea     rax, [rbp+var_7C]
0x180054b9a  mov     [rsp+120h+var_F0], rax
0x180054b9f  lea     rax, [rbp+var_38]
0x180054ba3  mov     [rsp+120h+var_F8], rax
0x180054ba8  lea     rax, [rbp+var_30]
0x180054bac  mov     qword ptr [rsp+120h+var_100], rax
0x180054bb1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180054bb6  jmp     loc_180054C67
0x180054bbb  lea     rdx, [rbp+SRWLock]
0x180054bbf  mov     rcx, rbx
0x180054bc2  call    ?LockExclusive@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180054bc7  mov     rax, [rdi]
0x180054bca  mov     rcx, [rbp+SRWLock]; SRWLock
0x180054bce  mov     dword ptr [rax], 2
0x180054bd4  test    rcx, rcx
0x180054bd7  jz      short loc_180054BE5
0x180054bd9  call    cs:__imp_ReleaseSRWLockExclusive
0x180054be0  nop     dword ptr [rax+rax+00h]
0x180054be5  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x180054bea  mov     rdi, [rax+8]
0x180054bee  cmp     dword ptr [rdi], 5
0x180054bf1  jbe     short loc_180054C67
0x180054bf3  mov     rcx, 200000000000h
0x180054bfd  test    [rdi+10h], rcx
0x180054c01  jz      short loc_180054C67
0x180054c03  mov     rax, [rdi+18h]
0x180054c07  and     rax, rcx
0x180054c0a  cmp     rax, [rdi+18h]
0x180054c0e  jnz     short loc_180054C67
0x180054c10  call    cs:__imp_GetCurrentThreadId
0x180054c17  nop     dword ptr [rax+rax+00h]
0x180054c1c  mov     r8, [rbx+110h]
0x180054c23  lea     rdx, unk_1800E6764
0x180054c2a  mov     dword ptr [rbp+SRWLock], eax
0x180054c2d  xor     r9d, r9d
0x180054c30  mov     rcx, rdi
0x180054c33  mov     eax, [r8+48h]
0x180054c37  add     r8, 8
0x180054c3b  mov     [rbp+arg_8], eax
0x180054c3e  mov     eax, 1000000h
0x180054c43  mov     [rbp+arg_10], rax
0x180054c47  lea     rax, [rbp+SRWLock]
0x180054c4b  mov     [rsp+120h+var_F0], rax
0x180054c50  lea     rax, [rbp+arg_8]
0x180054c54  mov     [rsp+120h+var_F8], rax
0x180054c59  lea     rax, [rbp+arg_10]
0x180054c5d  mov     qword ptr [rsp+120h+var_100], rax; int
0x180054c62  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180054c67  cmp     dword ptr [rbx+138h], 0
0x180054c6e  jz      short loc_180054CCD
0x180054c70  add     rbx, 120h
0x180054c77  call    cs:__imp_GetCurrentThreadId
0x180054c7e  nop     dword ptr [rax+rax+00h]
0x180054c83  cmp     [rbx+18h], eax
0x180054c86  jz      short loc_180054CA3
0x180054c88  mov     rcx, [rbp+8]; this
0x180054c8c  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180054c93  mov     r9d, 8007029Ch; char *
0x180054c99  mov     edx, 3BEh; void *
0x180054c9e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180054ca3  and     dword ptr [rbx+18h], 0
0x180054ca7  mov     rcx, [rbx]
0x180054caa  jmp     short loc_180054CB8
0x180054cac  cmp     rax, rbx
0x180054caf  jz      short loc_180054CC2
0x180054cb1  lea     rcx, [rax+10h]
0x180054cb5  mov     [rbx], rcx
0x180054cb8  mov     rax, [rcx]
0x180054cbb  test    rax, rax
0x180054cbe  jnz     short loc_180054CAC
0x180054cc0  jmp     short loc_180054CC9
0x180054cc2  mov     rax, [rbx+10h]
0x180054cc6  mov     [rcx], rax
0x180054cc9  and     qword ptr [rbx], 0
0x180054ccd  add     rsp, 108h
0x180054cd4  pop     rdi
0x180054cd5  pop     rsi
0x180054cd6  pop     rbx
0x180054cd7  pop     rbp
0x180054cd8  retn
```
