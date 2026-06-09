# DesktopAppXProvider::TryActivateDesktopAppXApplication::StopActivity(void)

- ea: `0x180093070`
- end: `0x18009335c`
- name: `?StopActivity@TryActivateDesktopAppXApplication@DesktopAppXProvider@@MEAAXXZ`
- size: `748`
- prototype: `void __fastcall(DesktopAppXProvider::TryActivateDesktopAppXApplication *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x180001a84`
- `0x18001031c`
- `0x18001bd34`
- `0x18001be00`
- `0x180093070`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800930cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009325c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800930cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009325c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093293`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800932f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180093293`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800932f9`

## string_xrefs

- `0x18009330e`: `onecore\internal\sdk\inc\wil\opensource/wil/result.h`

## pseudocode

```c
void __fastcall DesktopAppXProvider::TryActivateDesktopAppXApplication::StopActivity(
        DesktopAppXProvider::TryActivateDesktopAppXApplication *this)
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
      && (*(_QWORD *)(v10 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v10 + 24) & 0x400000000000LL) == *(_QWORD *)(v10 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v31 = *(_DWORD *)(v12 + 72);
      v32 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)&unk_1800EA8EB,
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
      && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
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
      v28[0] = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (unsigned int)&unk_1800EA7B2,
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
0x180093070  push    rbp
0x180093072  push    rbx
0x180093073  push    rsi
0x180093074  push    rdi
0x180093075  lea     rbp, [rsp+18h]
0x18009307a  sub     rsp, 108h
0x180093081  lea     rdi, [rcx+110h]
0x180093088  mov     rbx, rcx
0x18009308b  mov     rax, [rdi]
0x18009308e  mov     ecx, [rax+48h]
0x180093091  test    ecx, ecx
0x180093093  jns     loc_18009323E
0x180093099  cmp     ecx, [rax+58h]
0x18009309c  jnz     loc_18009323E
0x1800930a2  lea     rsi, [rax+50h]
0x1800930a6  test    rsi, rsi
0x1800930a9  jz      loc_18009323E
0x1800930af  lea     rdx, [rbp+SRWLock]
0x1800930b3  mov     rcx, rbx
0x1800930b6  call    ?LockExclusive@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800930bb  mov     rax, [rdi]
0x1800930be  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800930c2  mov     dword ptr [rax], 2
0x1800930c8  test    rcx, rcx
0x1800930cb  jz      short loc_1800930D9
0x1800930cd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800930d4  nop     dword ptr [rax+rax+00h]
0x1800930d9  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x1800930de  mov     r9, [rax+8]
0x1800930e2  cmp     dword ptr [r9], 5
0x1800930e6  jbe     loc_1800932E9
0x1800930ec  mov     rcx, 400000000000h
0x1800930f6  test    [r9+10h], rcx
0x1800930fa  jz      loc_1800932E9
0x180093100  mov     rax, [r9+18h]
0x180093104  and     rax, rcx
0x180093107  cmp     rax, [r9+18h]
0x18009310b  jnz     loc_1800932E9
0x180093111  mov     rax, [rsi+78h]
0x180093115  lea     rdx, unk_1800EA7B2
0x18009311c  mov     r8, [rdi]
0x18009311f  mov     rcx, r9
0x180093122  mov     [rbp+var_78], rax
0x180093126  add     r8, 8
0x18009312a  mov     rax, [rsi+70h]
0x18009312e  mov     [rbp+var_70], rax
0x180093132  mov     eax, [rsi+68h]
0x180093135  mov     dword ptr [rbp+SRWLock], eax
0x180093138  mov     rax, [rsi+60h]
0x18009313c  mov     [rbp+var_68], rax
0x180093140  mov     rax, [rsi+58h]
0x180093144  mov     [rbp+var_60], rax
0x180093148  mov     eax, [rsi+50h]
0x18009314b  mov     [rbp+arg_8], eax
0x18009314e  mov     rax, [rsi+48h]
0x180093152  mov     [rbp+var_58], rax
0x180093156  mov     eax, [rsi+20h]
0x180093159  mov     dword ptr [rbp+arg_10], eax
0x18009315c  mov     rax, [rsi+18h]
0x180093160  mov     [rbp+var_50], rax
0x180093164  mov     eax, [rsi]
0x180093166  mov     [rbp+arg_18], eax
0x180093169  mov     rax, [rsi+80h]
0x180093170  mov     [rbp+var_48], rax
0x180093174  mov     eax, [rsi+40h]
0x180093177  mov     [rbp+var_80], eax
0x18009317a  mov     rax, [rsi+38h]
0x18009317e  mov     [rbp+var_40], rax
0x180093182  mov     eax, [rsi+8]
0x180093185  mov     [rbp+var_7C], eax
0x180093188  lea     rax, [rbp+var_78]
0x18009318c  mov     [rsp+120h+var_88], rax
0x180093194  lea     rax, [rbp+var_70]
0x180093198  mov     [rsp+120h+var_90], rax
0x1800931a0  lea     rax, [rbp+SRWLock]
0x1800931a4  mov     [rsp+120h+var_98], rax
0x1800931ac  lea     rax, [rbp+var_68]
0x1800931b0  mov     [rsp+120h+var_A0], rax
0x1800931b8  lea     rax, [rbp+var_60]
0x1800931bc  mov     [rsp+120h+var_A8], rax
0x1800931c1  lea     rax, [rbp+arg_8]
0x1800931c5  mov     [rsp+120h+var_B0], rax
0x1800931ca  lea     rax, [rbp+var_58]
0x1800931ce  mov     [rsp+120h+var_B8], rax
0x1800931d3  lea     rax, [rbp+arg_10]
0x1800931d7  mov     [rsp+120h+var_C0], rax
0x1800931dc  lea     rax, [rbp+var_50]
0x1800931e0  mov     [rsp+120h+var_C8], rax
0x1800931e5  lea     rax, [rbp+arg_18]
0x1800931e9  mov     [rsp+120h+var_D0], rax
0x1800931ee  lea     rax, [rbp+var_48]
0x1800931f2  mov     [rsp+120h+var_D8], rax
0x1800931f7  lea     rax, [rbp+var_80]
0x1800931fb  mov     [rsp+120h+var_E0], rax
0x180093200  lea     rax, [rbp+var_40]
0x180093204  mov     [rsp+120h+var_E8], rax
0x180093209  lea     rax, [rbp+var_7C]
0x18009320d  mov     [rsp+120h+var_F0], rax
0x180093212  lea     rax, [rbp+var_38]
0x180093216  mov     [rsp+120h+var_F8], rax
0x18009321b  lea     rax, [rbp+var_30]
0x18009321f  mov     qword ptr [rsp+120h+var_100], rax
0x180093224  mov     [rbp+var_38], 1000000h
0x18009322c  mov     [rbp+var_30], 3000000h
0x180093234  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180093239  jmp     loc_1800932E9
0x18009323e  lea     rdx, [rbp+SRWLock]
0x180093242  mov     rcx, rbx
0x180093245  call    ?LockExclusive@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18009324a  mov     rax, [rdi]
0x18009324d  mov     rcx, [rbp+SRWLock]; SRWLock
0x180093251  mov     dword ptr [rax], 2
0x180093257  test    rcx, rcx
0x18009325a  jz      short loc_180093268
0x18009325c  call    cs:__imp_ReleaseSRWLockExclusive
0x180093263  nop     dword ptr [rax+rax+00h]
0x180093268  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x18009326d  mov     rdi, [rax+8]
0x180093271  cmp     dword ptr [rdi], 5
0x180093274  jbe     short loc_1800932E9
0x180093276  mov     rcx, 400000000000h
0x180093280  test    [rdi+10h], rcx
0x180093284  jz      short loc_1800932E9
0x180093286  mov     rax, [rdi+18h]
0x18009328a  and     rax, rcx
0x18009328d  cmp     rax, [rdi+18h]
0x180093291  jnz     short loc_1800932E9
0x180093293  call    cs:__imp_GetCurrentThreadId
0x18009329a  nop     dword ptr [rax+rax+00h]
0x18009329f  mov     r8, [rbx+110h]
0x1800932a6  lea     rdx, unk_1800EA8EB
0x1800932ad  mov     dword ptr [rbp+SRWLock], eax
0x1800932b0  xor     r9d, r9d
0x1800932b3  mov     rcx, rdi
0x1800932b6  mov     eax, [r8+48h]
0x1800932ba  add     r8, 8
0x1800932be  mov     [rbp+arg_8], eax
0x1800932c1  lea     rax, [rbp+SRWLock]
0x1800932c5  mov     [rsp+120h+var_F0], rax
0x1800932ca  lea     rax, [rbp+arg_8]
0x1800932ce  mov     [rsp+120h+var_F8], rax
0x1800932d3  lea     rax, [rbp+arg_10]
0x1800932d7  mov     qword ptr [rsp+120h+var_100], rax; int
0x1800932dc  mov     [rbp+arg_10], 3000000h
0x1800932e4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800932e9  cmp     dword ptr [rbx+138h], 0
0x1800932f0  jz      short loc_18009334F
0x1800932f2  add     rbx, 120h
0x1800932f9  call    cs:__imp_GetCurrentThreadId
0x180093300  nop     dword ptr [rax+rax+00h]
0x180093305  cmp     [rbx+18h], eax
0x180093308  jz      short loc_180093325
0x18009330a  mov     rcx, [rbp+8]; this
0x18009330e  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180093315  mov     r9d, 8007029Ch; char *
0x18009331b  mov     edx, 3BEh; void *
0x180093320  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180093325  and     dword ptr [rbx+18h], 0
0x180093329  mov     rcx, [rbx]
0x18009332c  jmp     short loc_18009333A
0x18009332e  cmp     rax, rbx
0x180093331  jz      short loc_180093344
0x180093333  lea     rcx, [rax+10h]
0x180093337  mov     [rbx], rcx
0x18009333a  mov     rax, [rcx]
0x18009333d  test    rax, rax
0x180093340  jnz     short loc_18009332E
0x180093342  jmp     short loc_18009334B
0x180093344  mov     rax, [rbx+10h]
0x180093348  mov     [rcx], rax
0x18009334b  and     qword ptr [rbx], 0
0x18009334f  add     rsp, 108h
0x180093356  pop     rdi
0x180093357  pop     rsi
0x180093358  pop     rbx
0x180093359  pop     rbp
0x18009335a  retn
```
