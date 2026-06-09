# CWwanTranslator::_ProcessReadyState(_GUID const &,uchar *,uint)

- ea: `0x180042b60`
- end: `0x180042f43`
- name: `?_ProcessReadyState@CWwanTranslator@@AEAAJAEBU_GUID@@PEAEI@Z`
- size: `995`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, const struct _GUID *, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180037d04`
- `0x18003e4f4`
- `0x180043834`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800172bc`
- `0x18001dd10`
- `0x180034964`
- `0x18003994c`
- `0x180042b60`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180042d27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180042d40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180042d27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180042d40`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180042cd7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180042cd7`

## string_xrefs

- `0x180042de4`: `UICC binding for the adapter does not exist. Ignore the slot state update for state %d.`
- `0x180042bf9`: `CWwanTranslator::_ProcessReadyState`
- `0x180042e0f`: `CWwanTranslator::_ProcessReadyState`
- `0x180042eca`: `CWwanTranslator::_ProcessReadyState`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWwanTranslator::_ProcessReadyState(RTL_SRWLOCK *this, const struct _GUID *a2, unsigned __int8 *a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  bool v10; // si
  SlotBindingMap *Ptr; // rcx
  int HasUiccBinding; // eax
  unsigned int v13; // esi
  _QWORD *v14; // rdx
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21[2]; // [rsp+20h] [rbp-59h]
  bool v22; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-45h] BYREF
  int v24[2]; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int16 *v25[2]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v26; // [rsp+50h] [rbp-29h]
  unsigned __int16 *v27[2]; // [rsp+58h] [rbp-21h] BYREF
  __int64 v28; // [rsp+68h] [rbp-11h]
  _QWORD v29[7]; // [rsp+70h] [rbp-9h] BYREF
  _QWORD *v30; // [rsp+A8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(_OWORD *)v27 = 0;
  v28 = 0;
  *(_OWORD *)v25 = 0;
  v26 = 0;
  std::vector<unsigned short>::resize(v27);
  std::vector<unsigned short>::resize(v25);
  StringCchPrintfW(v27[0], v27[1] - v27[0], L"Enter");
  v21[0] = 1748;
  StringCchPrintfW(v25[0], v25[1] - v25[0], L"%S(%d):%s", "CWwanTranslator::_ProcessReadyState");
  v6 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    *(unsigned __int16 **)v24 = v25[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)&dword_180076F3C,
      v7,
      v8,
      (const unsigned __int16 **)v24);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v25);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v27);
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D5,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
      (const char *)0x80070057LL,
      v21[0]);
    return 2147942487LL;
  }
  v23 = -1;
  if ( *(_DWORD *)a3 )
  {
    switch ( *(_DWORD *)a3 )
    {
      case 1:
LABEL_11:
        v23 = 5;
        break;
      case 2:
        v23 = 3;
        break;
      case 3:
      case 4:
        v23 = 6;
        break;
      default:
        if ( (unsigned int)(*(_DWORD *)a3 - 5) > 1 )
          goto LABEL_30;
        goto LABEL_11;
    }
  }
  else
  {
    v23 = 2;
  }
  v10 = 0;
  v22 = 0;
  AcquireSRWLockShared(this + 19);
  *(_QWORD *)v24 = this + 19;
  if ( this[4].Ptr )
  {
    Ptr = (SlotBindingMap *)this[17].Ptr;
    if ( Ptr )
    {
      HasUiccBinding = SlotBindingMap::GetAdapterHasUiccBinding(Ptr, a2, &v22);
      v13 = HasUiccBinding;
      if ( HasUiccBinding < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6FF,
          (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
          (const char *)(unsigned int)HasUiccBinding,
          v21[0]);
        if ( this != (RTL_SRWLOCK *)-152LL )
          ReleaseSRWLockShared(this + 19);
        return v13;
      }
      v10 = v22;
    }
  }
  if ( this != (RTL_SRWLOCK *)-152LL )
    ReleaseSRWLockShared(this + 19);
  if ( v10 )
  {
    v29[0] = off_18005EF78;
    v29[1] = this;
    v29[2] = a2;
    v29[3] = &v23;
    v30 = v29;
    CWwanTranslator::SafelyNotify(this, v29);
    if ( v30 )
    {
      v14 = v29;
      LOBYTE(v14) = v30 != v29;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v30 + 32LL))(v30, v14);
    }
  }
  else
  {
    *(_OWORD *)v25 = 0;
    v26 = 0;
    *(_OWORD *)v27 = 0;
    v28 = 0;
    std::vector<unsigned short>::resize(v25);
    std::vector<unsigned short>::resize(v27);
    StringCchPrintfW(
      v25[0],
      v25[1] - v25[0],
      L"UICC binding for the adapter does not exist. Ignore the slot state update for state %d.",
      v23);
    v21[0] = 1803;
    StringCchPrintfW(
      v27[0],
      v27[1] - v27[0],
      L"%S(%d):%s",
      "CWwanTranslator::_ProcessReadyState",
      *(_QWORD *)v21,
      v25[0]);
    v15 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v15 > 4u )
    {
      *(unsigned __int16 **)v24 = v27[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v15,
        (__int64)&byte_180076F5F,
        v16,
        v17,
        (const unsigned __int16 **)v24);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v27);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v25);
  }
LABEL_30:
  *(_OWORD *)v25 = 0;
  v26 = 0;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  std::vector<unsigned short>::resize(v25);
  std::vector<unsigned short>::resize(v27);
  StringCchPrintfW(v25[0], v25[1] - v25[0], L"Exit");
  v21[0] = 1807;
  StringCchPrintfW(v27[0], v27[1] - v27[0], L"%S(%d):%s", "CWwanTranslator::_ProcessReadyState", *(_QWORD *)v21, v25[0]);
  v18 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v18 > 5u )
  {
    *(unsigned __int16 **)v24 = v27[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v18,
      (__int64)&word_180076EF6,
      v19,
      v20,
      (const unsigned __int16 **)v24);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v27);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v25);
  return 0;
}

```

## disassembly

```asm
0x180042b60  mov     [rsp-8+arg_10], rbx
0x180042b65  mov     [rsp-8+arg_18], rsi
0x180042b6a  push    rbp
0x180042b6b  push    rdi
0x180042b6c  push    r14
0x180042b6e  lea     rbp, [rsp-47h]
0x180042b73  sub     rsp, 0C0h
0x180042b7a  mov     rax, cs:__security_cookie
0x180042b81  xor     rax, rsp
0x180042b84  mov     [rbp+57h+var_20], rax
0x180042b88  mov     rbx, r8
0x180042b8b  mov     r14, rdx
0x180042b8e  mov     rdi, rcx
0x180042b91  xorps   xmm0, xmm0
0x180042b94  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x180042b99  mov     [rbp+57h+var_68], 0
0x180042ba1  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180042ba6  mov     [rbp+57h+var_80], 0
0x180042bae  lea     rcx, [rbp+57h+var_78]
0x180042bb2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180042bb7  lea     rcx, [rbp+57h+var_90]
0x180042bbb  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180042bc0  mov     rdx, [rbp+57h+var_78+8]
0x180042bc4  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x180042bc8  sub     rdx, rcx
0x180042bcb  sar     rdx, 1; unsigned __int64
0x180042bce  lea     r8, aEnter; "Enter"
0x180042bd5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042bda  mov     rdx, [rbp+57h+var_90+8]
0x180042bde  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x180042be2  sub     rdx, rcx
0x180042be5  sar     rdx, 1; unsigned __int64
0x180042be8  mov     rax, [rbp+57h+var_78]
0x180042bec  mov     [rsp+0D0h+var_A8], rax
0x180042bf1  mov     [rsp+0D0h+var_B0], 6D4h
0x180042bf9  lea     r9, aCwwantranslato_43; "CWwanTranslator::_ProcessReadyState"
0x180042c00  lea     r8, aSDS; "%S(%d):%s"
0x180042c07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042c0c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180042c11  mov     ecx, [rax]
0x180042c13  cmp     ecx, 5
0x180042c16  jbe     short loc_180042C39
0x180042c18  mov     rcx, [rbp+57h+var_90]
0x180042c1c  mov     qword ptr [rbp+57h+var_98], rcx
0x180042c20  lea     rcx, [rbp+57h+var_98]
0x180042c24  mov     qword ptr [rsp+0D0h+var_B0], rcx; int
0x180042c29  lea     rdx, dword_180076F3C
0x180042c30  mov     rcx, rax
0x180042c33  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180042c38  nop
0x180042c39  lea     rcx, [rbp+57h+var_90]
0x180042c3d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180042c42  nop
0x180042c43  lea     rcx, [rbp+57h+var_78]
0x180042c47  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180042c4c  test    rbx, rbx
0x180042c4f  jnz     short loc_180042C75
0x180042c51  mov     rcx, [rbp+5Fh]; this
0x180042c55  mov     ebx, 80070057h
0x180042c5a  mov     r9d, ebx; char *
0x180042c5d  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180042c64  mov     edx, 6D5h; void *
0x180042c69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042c6e  mov     eax, ebx
0x180042c70  jmp     loc_180042F1F
0x180042c75  mov     [rbp+57h+var_9C], 0FFFFFFFFh
0x180042c7c  mov     ecx, [rbx]
0x180042c7e  test    ecx, ecx
0x180042c80  jz      short loc_180042CBF
0x180042c82  sub     ecx, 1
0x180042c85  jz      short loc_180042CA4
0x180042c87  sub     ecx, 1
0x180042c8a  jz      short loc_180042CB6
0x180042c8c  sub     ecx, 1
0x180042c8f  jz      short loc_180042CAD
0x180042c91  sub     ecx, 1
0x180042c94  jz      short loc_180042CAD
0x180042c96  sub     ecx, 1
0x180042c99  jz      short loc_180042CA4
0x180042c9b  cmp     ecx, 1
0x180042c9e  jnz     loc_180042E62
0x180042ca4  mov     [rbp+57h+var_9C], 5
0x180042cab  jmp     short loc_180042CC6
0x180042cad  mov     [rbp+57h+var_9C], 6
0x180042cb4  jmp     short loc_180042CC6
0x180042cb6  mov     [rbp+57h+var_9C], 3
0x180042cbd  jmp     short loc_180042CC6
0x180042cbf  mov     [rbp+57h+var_9C], 2
0x180042cc6  xor     sil, sil
0x180042cc9  mov     [rbp+57h+var_A0], sil
0x180042ccd  lea     rbx, [rdi+98h]
0x180042cd4  mov     rcx, rbx; SRWLock
0x180042cd7  call    cs:__imp_AcquireSRWLockShared
0x180042cdd  mov     qword ptr [rbp+57h+var_98], rbx
0x180042ce1  cmp     qword ptr [rdi+20h], 0
0x180042ce6  jz      short loc_180042D38
0x180042ce8  mov     rcx, [rdi+88h]; this
0x180042cef  test    rcx, rcx
0x180042cf2  jz      short loc_180042D38
0x180042cf4  lea     r8, [rbp+57h+var_A0]; bool *
0x180042cf8  mov     rdx, r14; struct _GUID *
0x180042cfb  call    ?GetAdapterHasUiccBinding@SlotBindingMap@@QEAAJAEBU_GUID@@AEA_N@Z; SlotBindingMap::GetAdapterHasUiccBinding(_GUID const &,bool &)
0x180042d00  mov     esi, eax
0x180042d02  test    eax, eax
0x180042d04  jns     short loc_180042D34
0x180042d06  mov     rcx, [rbp+5Fh]; this
0x180042d0a  mov     r9d, eax; char *
0x180042d0d  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180042d14  mov     edx, 6FFh; void *
0x180042d19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042d1e  nop
0x180042d1f  test    rbx, rbx
0x180042d22  jz      short loc_180042D2D
0x180042d24  mov     rcx, rbx; SRWLock
0x180042d27  call    cs:__imp_ReleaseSRWLockShared
0x180042d2d  mov     eax, esi
0x180042d2f  jmp     loc_180042F1F
0x180042d34  mov     sil, [rbp+57h+var_A0]
0x180042d38  test    rbx, rbx
0x180042d3b  jz      short loc_180042D46
0x180042d3d  mov     rcx, rbx; SRWLock
0x180042d40  call    cs:__imp_ReleaseSRWLockShared
0x180042d46  test    sil, sil
0x180042d49  jz      short loc_180042DA3
0x180042d4b  lea     rax, off_18005EF78
0x180042d52  mov     [rbp+57h+var_60], rax
0x180042d56  mov     [rbp+57h+var_58], rdi
0x180042d5a  mov     [rbp+57h+var_50], r14
0x180042d5e  lea     rax, [rbp+57h+var_9C]
0x180042d62  mov     [rbp+57h+var_48], rax
0x180042d66  lea     rax, [rbp+57h+var_60]
0x180042d6a  mov     [rbp+57h+var_28], rax
0x180042d6e  lea     rdx, [rbp+57h+var_60]
0x180042d72  mov     rcx, rdi
0x180042d75  call    ?SafelyNotify@CWwanTranslator@@AEAAJ$$QEAV?$function@$$A6AXXZ@std@@@Z; CWwanTranslator::SafelyNotify(std::function<void (void)> &&)
0x180042d7a  nop
0x180042d7b  mov     rcx, [rbp+57h+var_28]
0x180042d7f  test    rcx, rcx
0x180042d82  jz      loc_180042E62
0x180042d88  mov     rax, [rcx]
0x180042d8b  lea     rdx, [rbp+57h+var_60]
0x180042d8f  cmp     rcx, rdx
0x180042d92  setnz   dl
0x180042d95  mov     rax, [rax+20h]
0x180042d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d9e  jmp     loc_180042E62
0x180042da3  xorps   xmm0, xmm0
0x180042da6  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180042dab  mov     [rbp+57h+var_80], 0
0x180042db3  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x180042db8  mov     [rbp+57h+var_68], 0
0x180042dc0  lea     rcx, [rbp+57h+var_90]
0x180042dc4  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180042dc9  lea     rcx, [rbp+57h+var_78]
0x180042dcd  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180042dd2  mov     rdx, [rbp+57h+var_90+8]
0x180042dd6  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x180042dda  sub     rdx, rcx
0x180042ddd  sar     rdx, 1; unsigned __int64
0x180042de0  mov     r9d, [rbp+57h+var_9C]
0x180042de4  lea     r8, aUiccBindingFor; "UICC binding for the adapter does not e"...
0x180042deb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042df0  mov     rdx, [rbp+57h+var_78+8]
0x180042df4  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x180042df8  sub     rdx, rcx
0x180042dfb  sar     rdx, 1; unsigned __int64
0x180042dfe  mov     rax, [rbp+57h+var_90]
0x180042e02  mov     [rsp+0D0h+var_A8], rax
0x180042e07  mov     [rsp+0D0h+var_B0], 70Bh
0x180042e0f  lea     r9, aCwwantranslato_43; "CWwanTranslator::_ProcessReadyState"
0x180042e16  lea     r8, aSDS; "%S(%d):%s"
0x180042e1d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042e22  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180042e27  mov     ecx, [rax]
0x180042e29  cmp     ecx, 4
0x180042e2c  jbe     short loc_180042E4F
0x180042e2e  mov     rcx, [rbp+57h+var_78]
0x180042e32  mov     qword ptr [rbp+57h+var_98], rcx
0x180042e36  lea     rcx, [rbp+57h+var_98]
0x180042e3a  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x180042e3f  lea     rdx, byte_180076F5F
0x180042e46  mov     rcx, rax
0x180042e49  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180042e4e  nop
0x180042e4f  lea     rcx, [rbp+57h+var_78]
0x180042e53  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180042e58  nop
0x180042e59  lea     rcx, [rbp+57h+var_90]
0x180042e5d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180042e62  xorps   xmm0, xmm0
0x180042e65  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180042e6a  mov     [rbp+57h+var_80], 0
0x180042e72  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x180042e77  mov     [rbp+57h+var_68], 0
0x180042e7f  lea     rcx, [rbp+57h+var_90]
0x180042e83  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180042e88  lea     rcx, [rbp+57h+var_78]
0x180042e8c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180042e91  mov     rdx, [rbp+57h+var_90+8]
0x180042e95  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x180042e99  sub     rdx, rcx
0x180042e9c  sar     rdx, 1; unsigned __int64
0x180042e9f  lea     r8, aExit; "Exit"
0x180042ea6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042eab  mov     rdx, [rbp+57h+var_78+8]
0x180042eaf  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x180042eb3  sub     rdx, rcx
0x180042eb6  sar     rdx, 1; unsigned __int64
0x180042eb9  mov     rax, [rbp+57h+var_90]
0x180042ebd  mov     [rsp+0D0h+var_A8], rax
0x180042ec2  mov     [rsp+0D0h+var_B0], 70Fh
0x180042eca  lea     r9, aCwwantranslato_43; "CWwanTranslator::_ProcessReadyState"
0x180042ed1  lea     r8, aSDS; "%S(%d):%s"
0x180042ed8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042edd  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180042ee2  mov     ecx, [rax]
0x180042ee4  cmp     ecx, 5
0x180042ee7  jbe     short loc_180042F0A
0x180042ee9  mov     rcx, [rbp+57h+var_78]
0x180042eed  mov     qword ptr [rbp+57h+var_98], rcx
0x180042ef1  lea     rcx, [rbp+57h+var_98]
0x180042ef5  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x180042efa  lea     rdx, word_180076EF6
0x180042f01  mov     rcx, rax
0x180042f04  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180042f09  nop
0x180042f0a  lea     rcx, [rbp+57h+var_78]
0x180042f0e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180042f13  nop
0x180042f14  lea     rcx, [rbp+57h+var_90]
0x180042f18  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180042f1d  xor     eax, eax
0x180042f1f  mov     rcx, [rbp+57h+var_20]
0x180042f23  xor     rcx, rsp; StackCookie
0x180042f26  call    __security_check_cookie
0x180042f2b  lea     r11, [rsp+0D0h+var_10]
0x180042f33  mov     rbx, [r11+30h]
0x180042f37  mov     rsi, [r11+38h]
0x180042f3b  mov     rsp, r11
0x180042f3e  pop     r14
0x180042f40  pop     rdi
0x180042f41  pop     rbp
0x180042f42  retn
```
