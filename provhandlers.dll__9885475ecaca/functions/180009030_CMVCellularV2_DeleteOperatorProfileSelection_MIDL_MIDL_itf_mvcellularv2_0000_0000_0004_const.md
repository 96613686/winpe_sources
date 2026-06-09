# CMVCellularV2::DeleteOperatorProfileSelection(__MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 const *)

- ea: `0x180009030`
- end: `0x1800090c6`
- name: `?DeleteOperatorProfileSelection@CMVCellularV2@@UEAAJPEBU__MIDL___MIDL_itf_mvcellularv2_0000_0000_0004@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(CMVCellularV2 *this, const struct __MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800011bc`
- `0x180009030`
- `0x18000ae44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000904c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000904c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800090ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800090ae`

## string_xrefs

- `0x180009077`: `CMVCellularV2::DeleteOperatorProfileSelection`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMVCellularV2::DeleteOperatorProfileSelection(
        CMVCellularV2 *this,
        const struct __MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v5; // r8
  __int64 v6; // r9
  WwanController *v7; // rcx
  unsigned int v8; // ebx
  int v10; // [rsp+40h] [rbp+8h] BYREF
  const char *v11; // [rsp+50h] [rbp+18h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v7 = (WwanController *)*((_QWORD *)this + 7);
  if ( v7 )
  {
    v8 = WwanController::DeleteOperatorProfileSelection(v7, a2);
  }
  else
  {
    v8 = -2147467259;
    if ( (unsigned int)dword_180052170 > 2 )
    {
      v10 = -2147467259;
      v11 = "CMVCellularV2::DeleteOperatorProfileSelection";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        0,
        (__int64)byte_180047AE5,
        v5,
        v6,
        (const unsigned __int16 **)&v11,
        (__int64)&v10);
    }
  }
  LeaveCriticalSection(v2);
  return v8;
}

```

## disassembly

```asm
0x180009030  mov     [rsp+arg_8], rbx
0x180009035  mov     [rsp+arg_18], rsi
0x18000903a  push    rdi
0x18000903b  sub     rsp, 30h
0x18000903f  lea     rdi, [rcx+10h]
0x180009043  mov     rbx, rcx
0x180009046  mov     rcx, rdi; lpCriticalSection
0x180009049  mov     rsi, rdx
0x18000904c  call    cs:__imp_EnterCriticalSection
0x180009052  mov     rcx, [rbx+38h]; this
0x180009056  test    rcx, rcx
0x180009059  jz      short loc_180009067
0x18000905b  mov     rdx, rsi; struct __MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 *
0x18000905e  call    ?DeleteOperatorProfileSelection@WwanController@@QEAAJPEBU__MIDL___MIDL_itf_mvcellularv2_0000_0000_0004@@@Z; WwanController::DeleteOperatorProfileSelection(__MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 const *)
0x180009063  mov     ebx, eax
0x180009065  jmp     short loc_1800090AB
0x180009067  mov     eax, cs:dword_180052170
0x18000906d  mov     ebx, 80004005h
0x180009072  cmp     eax, 2
0x180009075  jbe     short loc_1800090AB
0x180009077  lea     rax, aCmvcellularv2D; "CMVCellularV2::DeleteOperatorProfileSel"...
0x18000907e  mov     [rsp+38h+arg_0], 80004005h
0x180009086  mov     [rsp+38h+arg_10], rax
0x18000908b  lea     rdx, byte_180047AE5
0x180009092  lea     rax, [rsp+38h+arg_0]
0x180009097  mov     [rsp+38h+var_10], rax
0x18000909c  lea     rax, [rsp+38h+arg_10]
0x1800090a1  mov     [rsp+38h+var_18], rax
0x1800090a6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800090ab  mov     rcx, rdi; lpCriticalSection
0x1800090ae  call    cs:__imp_LeaveCriticalSection
0x1800090b4  mov     rsi, [rsp+38h+arg_18]
0x1800090b9  mov     eax, ebx
0x1800090bb  mov     rbx, [rsp+38h+arg_8]
0x1800090c0  add     rsp, 30h
0x1800090c4  pop     rdi
0x1800090c5  retn
```
