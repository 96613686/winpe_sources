# ShellExtensionTelemetry::RightClickToPrint::StopActivity(void)

- ea: `0x180009070`
- end: `0x1800093b0`
- name: `?StopActivity@RightClickToPrint@ShellExtensionTelemetry@@MEAAXXZ`
- size: `832`
- prototype: `void __fastcall(ShellExtensionTelemetry::RightClickToPrint *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180001008`
- `0x1800018dc`
- `0x180001ef0`
- `0x18000705c`
- `0x180007c04`
- `0x180009070`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800092b1`
- `KERNEL32!GetCurrentThreadId` at `0x180009338`
- `KERNEL32!GetCurrentThreadId` at `0x1800092b1`
- `KERNEL32!GetCurrentThreadId` at `0x180009338`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800090df`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180009272`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800090df`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180009272`

## string_xrefs

- `0x180009353`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ShellExtensionTelemetry::RightClickToPrint::StopActivity(
        ShellExtensionTelemetry::RightClickToPrint *this)
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
  char *v12; // rbx
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // [rsp+A0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  PSRWLOCK v17; // [rsp+B0h] [rbp-70h] BYREF
  int v18; // [rsp+B8h] [rbp-68h] BYREF
  int v19; // [rsp+BCh] [rbp-64h] BYREF
  int v20; // [rsp+C0h] [rbp-60h] BYREF
  int v21; // [rsp+C4h] [rbp-5Ch] BYREF
  __int64 v22; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v26; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v27; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v29; // [rsp+100h] [rbp-20h] BYREF
  __int64 v30; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v31[32]; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v32; // [rsp+130h] [rbp+10h]
  __int64 v33; // [rsp+138h] [rbp+18h]
  int *v34; // [rsp+140h] [rbp+20h]
  __int64 v35; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v37; // [rsp+158h] [rbp+38h]
  void *retaddr; // [rsp+178h] [rbp+58h]

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = MS3DPrintShellExtension::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
      {
        v22 = *((_QWORD *)v4 + 15);
        v23 = *((_QWORD *)v4 + 14);
        v18 = v4[26];
        v24 = *((_QWORD *)v4 + 12);
        v25 = *((_QWORD *)v4 + 11);
        v19 = v4[20];
        v26 = *((_QWORD *)v4 + 9);
        v20 = v4[8];
        v27 = *((_QWORD *)v4 + 3);
        v21 = *v4;
        v28 = *((_QWORD *)v4 + 16);
        v15 = v4[16];
        v29 = *((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v30 = 0x1000000;
        v17 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v6,
          (unsigned int)byte_18000D9A9,
          *((_QWORD *)this + 34) + 8,
          (_DWORD)v6,
          (__int64)&v17,
          (__int64)&v30,
          (__int64)&SRWLock,
          (__int64)&v29,
          (__int64)&v15,
          (__int64)&v28,
          (__int64)&v21,
          (__int64)&v27,
          (__int64)&v20,
          (__int64)&v26,
          (__int64)&v19,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v18,
          (__int64)&v23,
          (__int64)&v22);
      }
    }
  }
  else
  {
    wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v17);
    **((_DWORD **)this + 34) = 2;
    if ( v17 )
      ReleaseSRWLockExclusive(v17);
    v8 = MS3DPrintShellExtension::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v15 = *(_DWORD *)(v11 + 72);
        v17 = 0;
        p_SRWLock = &SRWLock;
        v37 = 4;
        v34 = &v15;
        v35 = 4;
        v32 = &v17;
        v33 = 8;
        tlgWriteTransfer_EventWriteTransfer(v9, &unk_18000DE40, v11 + 8, 0, 5, v31);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v12 = (char *)this + 288;
    if ( *((_DWORD *)v12 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v12 + 6) = 0;
    v13 = *(__int64 **)v12;
    while ( 1 )
    {
      v14 = *v13;
      if ( !*v13 )
        break;
      if ( (char *)v14 == v12 )
      {
        *v13 = *((_QWORD *)v12 + 2);
        break;
      }
      v13 = (__int64 *)(v14 + 16);
      *(_QWORD *)v12 = v14 + 16;
    }
    *(_QWORD *)v12 = 0;
  }
}

```

## disassembly

```asm
0x180009070  mov     [rsp-8+arg_8], rbx
0x180009075  mov     [rsp-8+arg_10], rdi
0x18000907a  push    rbp
0x18000907b  lea     rbp, [rsp-50h]
0x180009080  sub     rsp, 170h
0x180009087  mov     rax, cs:__security_cookie
0x18000908e  xor     rax, rsp
0x180009091  mov     [rbp+50h+var_10], rax
0x180009095  mov     rbx, rcx
0x180009098  mov     rdi, [rcx+110h]
0x18000909f  mov     eax, [rdi+48h]
0x1800090a2  test    eax, eax
0x1800090a4  jns     loc_180009253
0x1800090aa  add     rdi, 50h ; 'P'
0x1800090ae  cmp     eax, [rdi+8]
0x1800090b1  jnz     loc_180009253
0x1800090b7  test    rdi, rdi
0x1800090ba  jz      loc_180009253
0x1800090c0  lea     rdx, [rbp+50h+SRWLock]
0x1800090c4  call    ?LockExclusive@?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800090c9  mov     rax, [rbx+110h]
0x1800090d0  mov     dword ptr [rax], 2
0x1800090d6  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x1800090da  test    rcx, rcx
0x1800090dd  jz      short loc_1800090E5
0x1800090df  call    cs:__imp_ReleaseSRWLockExclusive
0x1800090e5  call    ?Provider@MS3DPrintShellExtension@@SAPEBU_tlgProvider_t@@XZ; MS3DPrintShellExtension::Provider(void)
0x1800090ea  mov     r9, rax
0x1800090ed  mov     ecx, [rax]
0x1800090ef  cmp     ecx, 5
0x1800090f2  jbe     loc_180009328
0x1800090f8  mov     rax, [rax+18h]
0x1800090fc  mov     rcx, [r9+10h]
0x180009100  mov     rdx, 400000000000h
0x18000910a  test    rdx, rcx
0x18000910d  jz      loc_180009328
0x180009113  mov     rcx, rax
0x180009116  and     rcx, rdx
0x180009119  cmp     rcx, rax
0x18000911c  jnz     loc_180009328
0x180009122  mov     rax, [rdi+78h]
0x180009126  mov     [rbp+50h+var_A8], rax
0x18000912a  mov     rax, [rdi+70h]
0x18000912e  mov     [rbp+50h+var_A0], rax
0x180009132  mov     eax, [rdi+68h]
0x180009135  mov     [rbp+50h+var_B8], eax
0x180009138  mov     rax, [rdi+60h]
0x18000913c  mov     [rbp+50h+var_98], rax
0x180009140  mov     rax, [rdi+58h]
0x180009144  mov     [rbp+50h+var_90], rax
0x180009148  mov     eax, [rdi+50h]
0x18000914b  mov     [rbp+50h+var_B4], eax
0x18000914e  mov     rax, [rdi+48h]
0x180009152  mov     [rbp+50h+var_88], rax
0x180009156  mov     eax, [rdi+20h]
0x180009159  mov     [rbp+50h+var_B0], eax
0x18000915c  mov     rax, [rdi+18h]
0x180009160  mov     [rbp+50h+var_80], rax
0x180009164  mov     eax, [rdi]
0x180009166  mov     [rbp+50h+var_AC], eax
0x180009169  mov     rax, [rdi+80h]
0x180009170  mov     [rbp+50h+var_78], rax
0x180009174  mov     eax, [rdi+40h]
0x180009177  mov     [rbp+50h+var_D0], eax
0x18000917a  mov     rax, [rdi+38h]
0x18000917e  mov     [rbp+50h+var_70], rax
0x180009182  mov     eax, [rdi+8]
0x180009185  mov     dword ptr [rbp+50h+SRWLock], eax
0x180009188  mov     [rbp+50h+var_68], 1000000h
0x180009190  mov     [rbp+50h+var_C0], 0
0x180009198  mov     r8, [rbx+110h]
0x18000919f  add     r8, 8
0x1800091a3  lea     rax, [rbp+50h+var_A8]
0x1800091a7  mov     [rsp+170h+var_D8], rax
0x1800091af  lea     rax, [rbp+50h+var_A0]
0x1800091b3  mov     [rsp+170h+var_E0], rax
0x1800091bb  lea     rax, [rbp+50h+var_B8]
0x1800091bf  mov     [rsp+170h+var_E8], rax
0x1800091c7  lea     rax, [rbp+50h+var_98]
0x1800091cb  mov     [rsp+170h+var_F0], rax
0x1800091d3  lea     rax, [rbp+50h+var_90]
0x1800091d7  mov     [rsp+170h+var_F8], rax
0x1800091dc  lea     rax, [rbp+50h+var_B4]
0x1800091e0  mov     [rsp+170h+var_100], rax
0x1800091e5  lea     rax, [rbp+50h+var_88]
0x1800091e9  mov     [rsp+170h+var_108], rax
0x1800091ee  lea     rax, [rbp+50h+var_B0]
0x1800091f2  mov     [rsp+170h+var_110], rax
0x1800091f7  lea     rax, [rbp+50h+var_80]
0x1800091fb  mov     [rsp+170h+var_118], rax
0x180009200  lea     rax, [rbp+50h+var_AC]
0x180009204  mov     [rsp+170h+var_120], rax
0x180009209  lea     rax, [rbp+50h+var_78]
0x18000920d  mov     [rsp+170h+var_128], rax
0x180009212  lea     rax, [rbp+50h+var_D0]
0x180009216  mov     [rsp+170h+var_130], rax
0x18000921b  lea     rax, [rbp+50h+var_70]
0x18000921f  mov     [rsp+170h+var_138], rax
0x180009224  lea     rax, [rbp+50h+SRWLock]
0x180009228  mov     [rsp+170h+var_140], rax
0x18000922d  lea     rax, [rbp+50h+var_68]
0x180009231  mov     [rsp+170h+var_148], rax
0x180009236  lea     rax, [rbp+50h+var_C0]
0x18000923a  mov     [rsp+170h+var_150], rax
0x18000923f  lea     rdx, byte_18000D9A9
0x180009246  mov     rcx, r9
0x180009249  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000924e  jmp     loc_180009328
0x180009253  lea     rdx, [rbp+50h+var_C0]
0x180009257  call    ?LockExclusive@?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000925c  mov     rax, [rbx+110h]
0x180009263  mov     dword ptr [rax], 2
0x180009269  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x18000926d  test    rcx, rcx
0x180009270  jz      short loc_180009278
0x180009272  call    cs:__imp_ReleaseSRWLockExclusive
0x180009278  call    ?Provider@MS3DPrintShellExtension@@SAPEBU_tlgProvider_t@@XZ; MS3DPrintShellExtension::Provider(void)
0x18000927d  mov     rdi, rax
0x180009280  mov     ecx, [rax]
0x180009282  cmp     ecx, 5
0x180009285  jbe     loc_180009328
0x18000928b  mov     rax, [rax+18h]
0x18000928f  mov     rcx, [rdi+10h]
0x180009293  mov     rdx, 400000000000h
0x18000929d  test    rdx, rcx
0x1800092a0  jz      loc_180009328
0x1800092a6  mov     rcx, rax
0x1800092a9  and     rcx, rdx
0x1800092ac  cmp     rcx, rax
0x1800092af  jnz     short loc_180009328
0x1800092b1  call    cs:__imp_GetCurrentThreadId
0x1800092b7  mov     dword ptr [rbp+50h+SRWLock], eax
0x1800092ba  mov     r8, [rbx+110h]
0x1800092c1  mov     eax, [r8+48h]
0x1800092c5  mov     [rbp+50h+var_D0], eax
0x1800092c8  mov     [rbp+50h+var_C0], 0
0x1800092d0  lea     rax, [rbp+50h+SRWLock]
0x1800092d4  mov     [rbp+50h+var_20], rax
0x1800092d8  mov     [rbp+50h+var_18], 4
0x1800092e0  lea     rax, [rbp+50h+var_D0]
0x1800092e4  mov     [rbp+50h+var_30], rax
0x1800092e8  mov     [rbp+50h+var_28], 4
0x1800092f0  lea     rax, [rbp+50h+var_C0]
0x1800092f4  mov     [rbp+50h+var_40], rax
0x1800092f8  mov     [rbp+50h+var_38], 8
0x180009300  add     r8, 8
0x180009304  lea     rax, [rbp+50h+var_60]
0x180009308  mov     [rsp+170h+var_148], rax
0x18000930d  mov     dword ptr [rsp+170h+var_150], 5
0x180009315  xor     r9d, r9d
0x180009318  lea     rdx, unk_18000DE40
0x18000931f  mov     rcx, rdi
0x180009322  call    _tlgWriteTransfer_EventWriteTransfer
0x180009327  nop
0x180009328  cmp     dword ptr [rbx+138h], 0
0x18000932f  jz      short loc_18000938F
0x180009331  add     rbx, 120h
0x180009338  call    cs:__imp_GetCurrentThreadId
0x18000933e  cmp     [rbx+18h], eax
0x180009341  jz      short loc_18000935F
0x180009343  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000934a  test    rax, rax
0x18000934d  jz      short loc_18000935F
0x18000934f  mov     rdx, [rbp+58h]
0x180009353  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000935a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000935f  mov     dword ptr [rbx+18h], 0
0x180009366  mov     rcx, [rbx]
0x180009369  jmp     short loc_180009377
0x18000936b  cmp     rax, rbx
0x18000936e  jz      short loc_180009381
0x180009370  lea     rcx, [rax+10h]
0x180009374  mov     [rbx], rcx
0x180009377  mov     rax, [rcx]
0x18000937a  test    rax, rax
0x18000937d  jnz     short loc_18000936B
0x18000937f  jmp     short loc_180009388
0x180009381  mov     rax, [rbx+10h]
0x180009385  mov     [rcx], rax
0x180009388  mov     qword ptr [rbx], 0
0x18000938f  mov     rcx, [rbp+50h+var_10]
0x180009393  xor     rcx, rsp; StackCookie
0x180009396  call    __security_check_cookie
0x18000939b  lea     r11, [rsp+170h+var_s0]
0x1800093a3  mov     rbx, [r11+18h]
0x1800093a7  mov     rdi, [r11+20h]
0x1800093ab  mov     rsp, r11
0x1800093ae  pop     rbp
0x1800093af  retn
```
