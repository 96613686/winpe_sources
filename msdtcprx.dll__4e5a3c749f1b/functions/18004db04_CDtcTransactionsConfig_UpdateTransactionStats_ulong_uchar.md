# CDtcTransactionsConfig::UpdateTransactionStats(ulong,uchar *)

- ea: `0x18004db04`
- end: `0x18004dce0`
- name: `?UpdateTransactionStats@CDtcTransactionsConfig@@AEAAJKPEAE@Z`
- size: `476`
- prototype: `int(CDtcTransactionsConfig *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004d310`

## callees

- `0x180003cf0`
- `0x18001de26`
- `0x18004db04`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dbd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dbd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004db88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004db88`

## string_xrefs

- `0x18004db21`: `com\complus\dtc\dtc\msdtcprx\src\dtctxconfig.cpp`
- `0x18004dba5`: `CoTaskMemAlloc failed.`
- `0x18004db39`: `CDtcTransactionsConfig::UpdateTransactionStats`
- `0x18004db6c`: `CDtcTransactionsConfig::UpdateTransactionStats`
- `0x18004db96`: `CDtcTransactionsConfig::UpdateTransactionStats`
- `0x18004dc03`: `CDtcTransactionsConfig::UpdateTransactionStats`
- `0x18004dc62`: `Completing the receive.`

## pseudocode

```c
__int64 __fastcall CDtcTransactionsConfig::UpdateTransactionStats(
        CDtcTransactionsConfig *this,
        unsigned int a2,
        unsigned __int8 *a3)
{
  SIZE_T v3; // rdi
  const wchar_t *v6; // r10
  unsigned int v7; // esi
  __int64 v8; // r9
  size_t v9; // rbp
  _DWORD *v10; // rax
  _DWORD *v11; // rdi
  __int64 v13; // [rsp+28h] [rbp-50h]

  v3 = a2;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    682,
    L"CDtcTransactionsConfig::UpdateTransactionStats",
    0,
    L"In");
  if ( (unsigned int)v3 < 0x60 )
  {
    v6 = L"Invalid argument: dwSize.";
    v7 = -2147024809;
    v8 = 686;
LABEL_5:
    LODWORD(v13) = v7;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
      v8,
      L"CDtcTransactionsConfig::UpdateTransactionStats",
      v13,
      v6);
    CoTaskMemFree(0);
    goto LABEL_14;
  }
  v9 = v3;
  v10 = CoTaskMemAlloc(v3);
  v11 = v10;
  if ( !v10 )
  {
    v7 = -2147024882;
    v6 = L"CoTaskMemAlloc failed.";
    v8 = 693;
    goto LABEL_5;
  }
  v7 = 0;
  memcpy_0(v10, a3, v9);
  (**((void (__fastcall ***)(char *))this + 10))((char *)this + 80);
  if ( !*((_DWORD *)this + 8) && !*((_QWORD *)this + 9) )
  {
    TraceStringInline(
      15,
      4,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
      701,
      L"CDtcTransactionsConfig::UpdateTransactionStats",
      0,
      L"Received tx stats for the first time.");
    *((_QWORD *)this + 9) = v11;
    if ( !*((_DWORD *)this + 35) || *((_QWORD *)this + 8) || !*v11 || !*(_DWORD *)(*((_QWORD *)this + 3) + 24LL) )
    {
      TraceStringInline(
        15,
        4,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
        708,
        L"CDtcTransactionsConfig::UpdateTransactionStats",
        0,
        L"Completing the receive.");
      *((_DWORD *)this + 8) = 1;
    }
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
LABEL_14:
  LODWORD(v13) = v7;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtctxconfig.cpp",
    720,
    L"CDtcTransactionsConfig::UpdateTransactionStats",
    v13,
    L"Out");
  return v7;
}

```

## disassembly

```asm
0x18004db04  push    rbx
0x18004db06  push    rbp
0x18004db07  push    rsi
0x18004db08  push    rdi
0x18004db09  push    r12
0x18004db0b  push    r13
0x18004db0d  push    r14
0x18004db0f  sub     rsp, 40h
0x18004db13  mov     edi, edx
0x18004db15  lea     rax, aIn_0; "In"
0x18004db1c  mov     [rsp+78h+var_48], rax
0x18004db21  lea     r12, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004db28  mov     edx, 6
0x18004db2d  mov     [rsp+78h+var_50], 0
0x18004db36  mov     r14, r8
0x18004db39  lea     rbp, aCdtctransactio_1; "CDtcTransactionsConfig::UpdateTransacti"...
0x18004db40  mov     rbx, rcx
0x18004db43  mov     [rsp+78h+var_58], rbp
0x18004db48  mov     r9d, 2AAh
0x18004db4e  mov     r8, r12
0x18004db51  lea     r13d, [rdx+9]
0x18004db55  mov     ecx, r13d
0x18004db58  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004db5d  cmp     edi, 60h ; '`'
0x18004db60  jnb     short loc_18004DB82
0x18004db62  mov     rdx, rbp
0x18004db65  lea     r10, aInvalidArgumen; "Invalid argument: dwSize."
0x18004db6c  lea     rbp, aCdtctransactio_1; "CDtcTransactionsConfig::UpdateTransacti"...
0x18004db73  xor     edi, edi
0x18004db75  mov     esi, 80070057h
0x18004db7a  mov     r9d, 2AEh
0x18004db80  jmp     short loc_18004DBB2
0x18004db82  mov     rcx, rdi; cb
0x18004db85  mov     rbp, rdi
0x18004db88  call    cs:__imp_CoTaskMemAlloc
0x18004db8e  mov     rdi, rax
0x18004db91  test    rax, rax
0x18004db94  jnz     short loc_18004DBE1
0x18004db96  lea     rbp, aCdtctransactio_1; "CDtcTransactionsConfig::UpdateTransacti"...
0x18004db9d  mov     esi, 8007000Eh
0x18004dba2  mov     rdx, rbp
0x18004dba5  lea     r10, aCotaskmemalloc; "CoTaskMemAlloc failed."
0x18004dbac  mov     r9d, 2B5h
0x18004dbb2  mov     [rsp+78h+var_48], r10
0x18004dbb7  mov     eax, 1
0x18004dbbc  mov     dword ptr [rsp+78h+var_50], esi
0x18004dbc0  mov     r8, r12
0x18004dbc3  mov     [rsp+78h+var_58], rdx
0x18004dbc8  mov     ecx, r13d
0x18004dbcb  movzx   edx, al
0x18004dbce  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004dbd3  mov     rcx, rdi; pv
0x18004dbd6  call    cs:__imp_CoTaskMemFree
0x18004dbdc  jmp     loc_18004DCA4
0x18004dbe1  mov     r8, rbp; Size
0x18004dbe4  mov     rdx, r14; Src
0x18004dbe7  mov     rcx, rdi; void *
0x18004dbea  xor     esi, esi
0x18004dbec  call    memcpy_0
0x18004dbf1  lea     r14, [rbx+50h]
0x18004dbf5  mov     rax, [r14]
0x18004dbf8  mov     rcx, r14
0x18004dbfb  mov     rax, [rax]
0x18004dbfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc03  lea     rbp, aCdtctransactio_1; "CDtcTransactionsConfig::UpdateTransacti"...
0x18004dc0a  cmp     [rbx+20h], esi
0x18004dc0d  jnz     loc_18004DC95
0x18004dc13  cmp     [rbx+48h], rsi
0x18004dc17  jnz     short loc_18004DC95
0x18004dc19  lea     rax, aReceivedTxStat; "Received tx stats for the first time."
0x18004dc20  mov     r9d, 2BDh
0x18004dc26  mov     [rsp+78h+var_48], rax
0x18004dc2b  lea     edx, [rsi+4]
0x18004dc2e  mov     [rsp+78h+var_50], rsi
0x18004dc33  mov     r8, r12
0x18004dc36  mov     ecx, r13d
0x18004dc39  mov     [rsp+78h+var_58], rbp
0x18004dc3e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004dc43  mov     [rbx+48h], rdi
0x18004dc47  cmp     [rbx+8Ch], esi
0x18004dc4d  jz      short loc_18004DC62
0x18004dc4f  cmp     [rbx+40h], rsi
0x18004dc53  jnz     short loc_18004DC62
0x18004dc55  cmp     [rdi], esi
0x18004dc57  jz      short loc_18004DC62
0x18004dc59  mov     rax, [rbx+18h]
0x18004dc5d  cmp     [rax+18h], esi
0x18004dc60  jnz     short loc_18004DC95
0x18004dc62  lea     rax, aCompletingTheR; "Completing the receive."
0x18004dc69  mov     r9d, 2C4h
0x18004dc6f  mov     [rsp+78h+var_48], rax
0x18004dc74  mov     r8, r12
0x18004dc77  mov     [rsp+78h+var_50], rsi
0x18004dc7c  mov     edx, 4
0x18004dc81  mov     ecx, r13d
0x18004dc84  mov     [rsp+78h+var_58], rbp
0x18004dc89  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004dc8e  mov     dword ptr [rbx+20h], 1
0x18004dc95  mov     rax, [r14]
0x18004dc98  mov     rcx, r14
0x18004dc9b  mov     rax, [rax+10h]
0x18004dc9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dca4  lea     rax, aOut; "Out"
0x18004dcab  mov     r9d, 2D0h
0x18004dcb1  mov     [rsp+78h+var_48], rax
0x18004dcb6  mov     r8, r12
0x18004dcb9  mov     dword ptr [rsp+78h+var_50], esi
0x18004dcbd  mov     edx, 6
0x18004dcc2  mov     ecx, r13d
0x18004dcc5  mov     [rsp+78h+var_58], rbp
0x18004dcca  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004dccf  mov     eax, esi
0x18004dcd1  add     rsp, 40h
0x18004dcd5  pop     r14
0x18004dcd7  pop     r13
0x18004dcd9  pop     r12
0x18004dcdb  pop     rdi
0x18004dcdc  pop     rsi
0x18004dcdd  pop     rbp
0x18004dcde  pop     rbx
0x18004dcdf  retn
```
