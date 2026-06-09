# DWMIndirect::GetUpdateStatistics(_DWMIndirectUpdateStatistics *)

- ea: `0x180004bd0`
- end: `0x180004cb5`
- name: `?GetUpdateStatistics@DWMIndirect@@UEAAJPEAU_DWMIndirectUpdateStatistics@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(DWMIndirect *__hidden this, struct _DWMIndirectUpdateStatistics *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180001368`
- `0x180004bd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004c03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004c03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c21`

## string_xrefs

- `0x180004c5d`: `Returning update stats for %s:UpdateCount=%d, UpdateRefreshCount=%d, m_uiSyncCount=%d, m_SyncQPCTime=%I64d`

## pseudocode

```c
__int64 __fastcall DWMIndirect::GetUpdateStatistics(DWMIndirect *this, struct _DWMIndirectUpdateStatistics *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v8; // [rsp+50h] [rbp-20h] BYREF
  char *v9; // [rsp+58h] [rbp-18h] BYREF
  const char *v10; // [rsp+60h] [rbp-10h] BYREF
  int v11; // [rsp+98h] [rbp+28h] BYREF
  int v12; // [rsp+A0h] [rbp+30h] BYREF
  int v13; // [rsp+A8h] [rbp+38h] BYREF

  if ( a2 )
  {
    *(_DWORD *)a2 = *((_DWORD *)this + 33);
    *((_DWORD *)a2 + 1) = *((_DWORD *)this + 38);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    *((_DWORD *)a2 + 2) = *((_DWORD *)this + 34);
    *((_QWORD *)a2 + 2) = *((_QWORD *)this + 18);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    if ( (unsigned int)dword_180044008 > 5 )
    {
      v8 = *((_QWORD *)a2 + 2);
      v11 = *((_DWORD *)a2 + 2);
      v12 = *((_DWORD *)a2 + 1);
      v13 = *(_DWORD *)a2;
      v9 = (char *)this + 788;
      v10 = "Returning update stats for %s:UpdateCount=%d, UpdateRefreshCount=%d, m_uiSyncCount=%d, m_SyncQPCTime=%I64d";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v4,
        (__int64)qword_180037270,
        v5,
        v6,
        (const unsigned __int16 **)&v10,
        &v9,
        (__int64)&v13,
        (__int64)&v12,
        (__int64)&v11,
        (__int64)&v8);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004bd0  mov     [rsp-18h+arg_0], rbx
0x180004bd5  push    rbp
0x180004bd6  push    rsi
0x180004bd7  push    rdi
0x180004bd8  mov     rbp, rsp
0x180004bdb  sub     rsp, 70h
0x180004bdf  mov     rdi, rdx
0x180004be2  mov     rsi, rcx
0x180004be5  test    rdx, rdx
0x180004be8  jz      loc_180004CA3
0x180004bee  mov     eax, [rcx+84h]
0x180004bf4  mov     [rdx], eax
0x180004bf6  mov     eax, [rcx+98h]
0x180004bfc  add     rcx, 58h ; 'X'; lpCriticalSection
0x180004c00  mov     [rdx+4], eax
0x180004c03  call    cs:__imp_EnterCriticalSection
0x180004c09  mov     eax, [rsi+88h]
0x180004c0f  lea     rcx, [rsi+58h]; lpCriticalSection
0x180004c13  mov     [rdi+8], eax
0x180004c16  mov     rax, [rsi+90h]
0x180004c1d  mov     [rdi+10h], rax
0x180004c21  call    cs:__imp_LeaveCriticalSection
0x180004c27  mov     eax, cs:dword_180044008
0x180004c2d  cmp     eax, 5
0x180004c30  jbe     short loc_180004CA3
0x180004c32  mov     rax, [rdi+10h]
0x180004c36  lea     rdx, qword_180037270
0x180004c3d  mov     [rbp+var_20], rax
0x180004c41  mov     eax, [rdi+8]
0x180004c44  mov     [rbp+arg_8], eax
0x180004c47  mov     eax, [rdi+4]
0x180004c4a  mov     [rbp+arg_10], eax
0x180004c4d  mov     eax, [rdi]
0x180004c4f  mov     [rbp+arg_18], eax
0x180004c52  lea     rax, [rsi+314h]
0x180004c59  mov     [rbp+var_18], rax
0x180004c5d  lea     rax, aReturningUpdat; "Returning update stats for %s:UpdateCou"...
0x180004c64  mov     [rbp+var_10], rax
0x180004c68  lea     rax, [rbp+var_20]
0x180004c6c  mov     [rsp+70h+var_28], rax
0x180004c71  lea     rax, [rbp+arg_8]
0x180004c75  mov     [rsp+70h+var_30], rax
0x180004c7a  lea     rax, [rbp+arg_10]
0x180004c7e  mov     [rsp+70h+var_38], rax
0x180004c83  lea     rax, [rbp+arg_18]
0x180004c87  mov     [rsp+70h+var_40], rax
0x180004c8c  lea     rax, [rbp+var_18]
0x180004c90  mov     [rsp+70h+var_48], rax
0x180004c95  lea     rax, [rbp+var_10]
0x180004c99  mov     [rsp+70h+var_50], rax
0x180004c9e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180004ca3  mov     rbx, [rsp+70h+arg_0]
0x180004cab  xor     eax, eax
0x180004cad  add     rsp, 70h
0x180004cb1  pop     rdi
0x180004cb2  pop     rsi
0x180004cb3  pop     rbp
0x180004cb4  retn
```
