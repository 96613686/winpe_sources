# DWMIndirect::UpdatePresentStats(void)

- ea: `0x18000687c`
- end: `0x18000693d`
- name: `?UpdatePresentStats@DWMIndirect@@IEAAXXZ`
- size: `193`
- prototype: `void __fastcall(DWMIndirect *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006240`
- `0x180006a40`

## callees

- `0x180001b3c`
- `0x18000687c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800068a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800068a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800068c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800068c5`

## string_xrefs

- `0x1800068fd`: `Updated present stats: CompletedUpdateCount=%d, CompletedSyncCount=%d, CompletedQPCTime=%I64d`

## pseudocode

```c
void __fastcall DWMIndirect::UpdatePresentStats(DWMIndirect *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // [rsp+60h] [rbp+8h] BYREF
  int v7; // [rsp+68h] [rbp+10h] BYREF
  __int64 v8; // [rsp+70h] [rbp+18h] BYREF
  const char *v9; // [rsp+78h] [rbp+20h] BYREF

  ++*((_DWORD *)this + 44);
  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  *((_DWORD *)this + 45) = *((_DWORD *)this + 44);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  *((_DWORD *)this + 50) = *((_DWORD *)this + 46);
  *((_QWORD *)this + 26) = *((_QWORD *)this + 24);
  LeaveCriticalSection(v1);
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v8 = *((_QWORD *)this + 26);
    v6 = *((_DWORD *)this + 50);
    v7 = *((_DWORD *)this + 45);
    v9 = "Updated present stats: CompletedUpdateCount=%d, CompletedSyncCount=%d, CompletedQPCTime=%I64d";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v3,
      (__int64)byte_180037209,
      v4,
      v5,
      (const unsigned __int16 **)&v9,
      (__int64)&v7,
      (__int64)&v6,
      (__int64)&v8);
  }
}

```

## disassembly

```asm
0x18000687c  push    rbx
0x18000687e  push    rdi
0x18000687f  sub     rsp, 48h
0x180006883  inc     dword ptr [rcx+0B0h]
0x180006889  lea     rbx, [rcx+88h]
0x180006890  mov     eax, [rcx+0B0h]
0x180006896  mov     rdi, rcx
0x180006899  mov     [rcx+0B4h], eax
0x18000689f  mov     rcx, rbx; lpCriticalSection
0x1800068a2  call    cs:__imp_EnterCriticalSection
0x1800068a8  mov     eax, [rdi+0B8h]
0x1800068ae  mov     rcx, rbx; lpCriticalSection
0x1800068b1  mov     [rdi+0C8h], eax
0x1800068b7  mov     rax, [rdi+0C0h]
0x1800068be  mov     [rdi+0D0h], rax
0x1800068c5  call    cs:__imp_LeaveCriticalSection
0x1800068cb  mov     eax, cs:dword_180044008
0x1800068d1  cmp     eax, 5
0x1800068d4  jbe     short loc_180006936
0x1800068d6  mov     rax, [rdi+0D0h]
0x1800068dd  lea     rdx, byte_180037209
0x1800068e4  mov     [rsp+58h+arg_10], rax
0x1800068e9  mov     eax, [rdi+0C8h]
0x1800068ef  mov     [rsp+58h+arg_0], eax
0x1800068f3  mov     eax, [rdi+0B4h]
0x1800068f9  mov     [rsp+58h+arg_8], eax
0x1800068fd  lea     rax, aUpdatedPresent; "Updated present stats: CompletedUpdateC"...
0x180006904  mov     [rsp+58h+arg_18], rax
0x180006909  lea     rax, [rsp+58h+arg_10]
0x18000690e  mov     [rsp+58h+var_20], rax
0x180006913  lea     rax, [rsp+58h+arg_0]
0x180006918  mov     [rsp+58h+var_28], rax
0x18000691d  lea     rax, [rsp+58h+arg_8]
0x180006922  mov     [rsp+58h+var_30], rax
0x180006927  lea     rax, [rsp+58h+arg_18]
0x18000692c  mov     [rsp+58h+var_38], rax
0x180006931  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180006936  add     rsp, 48h
0x18000693a  pop     rdi
0x18000693b  pop     rbx
0x18000693c  retn
```
