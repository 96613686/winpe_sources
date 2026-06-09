# PsmSrvOpenManagementChannel

- ea: `0x180019550`
- end: `0x18001966a`
- name: `PsmSrvOpenManagementChannel`
- size: `282`
- prototype: `__int64 __fastcall(int, int, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000102c`
- `0x1800039a8`
- `0x1800192fc`
- `0x180019550`
- `0x180019bfc`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x1800195d7`
- `ntdll!NtDuplicateObject` at `0x1800195d7`
- `ntdll!NtClose` at `0x180019611`
- `ntdll!NtClose` at `0x180019611`

## pseudocode

```c
__int64 __fastcall PsmSrvOpenManagementChannel(int a1, int a2, _QWORD *a3, _QWORD *a4)
{
  int ClientContext; // eax
  __int64 v7; // r8
  _DWORD *v8; // rbx
  NTSTATUS v9; // edi
  void *v10; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  __int64 v15; // [rsp+40h] [rbp-10h] BYREF
  void *TargetHandle; // [rsp+48h] [rbp-8h] BYREF
  int v17; // [rsp+78h] [rbp+28h] BYREF

  v17 = a2;
  v15 = 0;
  TargetHandle = 0;
  ClientContext = PsmpAllocateClientContext(a1, 1, (unsigned int)&v17, (unsigned int)&v15, 0, 0);
  v8 = (_DWORD *)v15;
  v9 = ClientContext;
  if ( ClientContext >= 0 )
  {
    v9 = NtDuplicateObject(
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           *(HANDLE *)(*(_QWORD *)(v15 + 56) + 56LL),
           *(HANDLE *)(v15 + 16),
           &TargetHandle,
           0x100000u,
           0,
           0);
    if ( v9 >= 0 )
    {
      v10 = TargetHandle;
      *a3 = v8;
      v8 = 0;
      TargetHandle = 0;
      v9 = 0;
      *a4 = v10;
    }
  }
  if ( v8 )
  {
    *v8 = 0;
    PsmpDereferenceClientContext(v8);
  }
  if ( TargetHandle )
    NtClose(TargetHandle);
  if ( v9 < 0 && (unsigned int)dword_18003F080 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003F080, 3, v7) )
  {
    LODWORD(v15) = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)&word_180039196,
      v12,
      v13,
      (__int64)&v15);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180019550  mov     rax, rsp
0x180019553  mov     [rax+8], rbx
0x180019557  mov     [rax+18h], rsi
0x18001955b  mov     [rax+10h], edx
0x18001955e  push    rbp
0x18001955f  push    rdi
0x180019560  push    r14
0x180019562  mov     rbp, rsp
0x180019565  sub     rsp, 50h
0x180019569  mov     rsi, r9
0x18001956c  mov     qword ptr [rax-40h], 0
0x180019574  mov     r14, r8
0x180019577  mov     [rbp+var_10], 0
0x18001957f  lea     r9, [rbp+var_10]
0x180019583  mov     [rbp+TargetHandle], 0
0x18001958b  lea     r8, [rbp+arg_8]
0x18001958f  mov     qword ptr [rax-48h], 0
0x180019597  mov     edx, 1
0x18001959c  call    PsmpAllocateClientContext
0x1800195a1  mov     rbx, [rbp+var_10]
0x1800195a5  mov     edi, eax
0x1800195a7  test    eax, eax
0x1800195a9  js      short loc_1800195F5
0x1800195ab  mov     rdx, [rbx+38h]
0x1800195af  lea     r9, [rbp+TargetHandle]; TargetHandle
0x1800195b3  mov     r8, [rbx+10h]; TargetProcessHandle
0x1800195b7  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x1800195bb  mov     [rsp+50h+Options], 0; Options
0x1800195c3  mov     [rsp+50h+HandleAttributes], 0; HandleAttributes
0x1800195cb  mov     rdx, [rdx+38h]; SourceHandle
0x1800195cf  mov     [rsp+50h+DesiredAccess], 100000h; DesiredAccess
0x1800195d7  call    cs:__imp_NtDuplicateObject
0x1800195dd  mov     edi, eax
0x1800195df  test    eax, eax
0x1800195e1  js      short loc_1800195F5
0x1800195e3  mov     rax, [rbp+TargetHandle]
0x1800195e7  mov     [r14], rbx
0x1800195ea  xor     ebx, ebx
0x1800195ec  mov     [rbp+TargetHandle], rbx
0x1800195f0  xor     edi, edi
0x1800195f2  mov     [rsi], rax
0x1800195f5  test    rbx, rbx
0x1800195f8  jz      short loc_180019608
0x1800195fa  mov     rcx, rbx
0x1800195fd  mov     dword ptr [rbx], 0
0x180019603  call    PsmpDereferenceClientContext
0x180019608  mov     rcx, [rbp+TargetHandle]; Handle
0x18001960c  test    rcx, rcx
0x18001960f  jz      short loc_180019617
0x180019611  call    cs:__imp_NtClose
0x180019617  test    edi, edi
0x180019619  jns     short loc_180019653
0x18001961b  mov     eax, cs:dword_18003F080
0x180019621  cmp     eax, 4
0x180019624  jbe     short loc_180019653
0x180019626  mov     edx, 3
0x18001962b  lea     rcx, dword_18003F080
0x180019632  call    _tlgKeywordOn
0x180019637  test    al, al
0x180019639  jz      short loc_180019653
0x18001963b  lea     rax, [rbp+var_10]
0x18001963f  mov     dword ptr [rbp+var_10], edi
0x180019642  lea     rdx, word_180039196
0x180019649  mov     qword ptr [rsp+50h+DesiredAccess], rax
0x18001964e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180019653  lea     r11, [rsp+50h+var_s0]
0x180019658  mov     eax, edi
0x18001965a  mov     rbx, [r11+20h]
0x18001965e  mov     rsi, [r11+30h]
0x180019662  mov     rsp, r11
0x180019665  pop     r14
0x180019667  pop     rdi
0x180019668  pop     rbp
0x180019669  retn
```
