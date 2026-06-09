# MXXMLWriter::writeError(ISAXLocator *,ushort const *,long,ushort const *)

- ea: `0x1800cbc14`
- end: `0x1800cc0da`
- name: `?writeError@MXXMLWriter@@AEAAJPEAUISAXLocator@@PEBGJ1@Z`
- size: `1222`
- prototype: `__int64 __fastcall(MXXMLWriter *__hidden this, struct ISAXLocator *, const unsigned __int16 *, int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800c8bf0`
- `0x1800c8e70`
- `0x1800c9500`

## callees

- `0x18002ac90`
- `0x18002d7e0`
- `0x18002d8d0`
- `0x180031d90`
- `0x18005f9b8`
- `0x180064034`
- `0x1800cbc14`
- `0x1800f6cf4`
- `0x1800f6d88`
- `0x1800f6db8`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800cbf40`
- `msvcrt!_resetstkoflw` at `0x1800cc01b`
- `msvcrt!_resetstkoflw` at `0x1800cbf40`
- `msvcrt!_resetstkoflw` at `0x1800cc01b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cbf93`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cc06e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cbf93`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cc06e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800cbf2e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800cbfbf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800cc009`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800cc09a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800cbf2e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800cbfbf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800cc009`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800cc09a`

## pseudocode

```c
__int64 __fastcall MXXMLWriter::writeError(
        MXXMLWriter *this,
        struct ISAXLocator *a2,
        const unsigned __int16 *a3,
        int a4,
        const unsigned __int16 *a5)
{
  const unsigned __int16 *v6; // r15
  int v9; // edi
  const unsigned __int16 *v10; // r14
  int v11; // eax
  const unsigned __int16 *v12; // rdx
  int v13; // eax
  int v15; // [rsp+24h] [rbp-64h] BYREF
  int v16; // [rsp+28h] [rbp-60h] BYREF
  unsigned __int16 *v17; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int16 *v18; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v19[72]; // [rsp+40h] [rbp-48h] BYREF

  v6 = a3;
  v9 = ModelInit::init(v19, 0, a3);
  if ( v9 >= 0 )
  {
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    if ( *((_DWORD *)this + 40) )
    {
      v9 = (*(__int64 (__fastcall **)(MXXMLWriter *, _QWORD))(*(_QWORD *)this + 200LL))(this, 0);
      if ( v9 < 0 )
        goto LABEL_20;
    }
    else
    {
      v9 = 0;
      *((_DWORD *)this + 40) = 0;
    }
    OutputHelper::write(*((OutputHelper **)this + 21), L"\r\n");
    OutputHelper::write(*((OutputHelper **)this + 21), a5);
    OutputHelper::write(*((OutputHelper **)this + 21), L":\r\n");
    if ( !a2 )
      goto LABEL_17;
    v9 = ((__int64 (__fastcall *)(struct ISAXLocator *, int *))a2->lpVtbl->getLineNumber)(a2, &v15);
    if ( v9 >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(struct ISAXLocator *, int *))a2->lpVtbl->getColumnNumber)(a2, &v16);
      if ( v9 >= 0 )
      {
        v9 = ((__int64 (__fastcall *)(struct ISAXLocator *, unsigned __int16 **))a2->lpVtbl->getSystemId)(a2, &v17);
        if ( v9 >= 0 )
        {
          v9 = ((__int64 (__fastcall *)(struct ISAXLocator *, unsigned __int16 **))a2->lpVtbl->getPublicId)(a2, &v18);
          if ( v9 >= 0 )
          {
            OutputHelper::write(*((OutputHelper **)this + 21), L"Line Number: ");
            OutputHelper::writeDecimal(*((OutputHelper **)this + 21), v15);
            OutputHelper::write(*((OutputHelper **)this + 21), L"\r\nColumn Number: ");
            OutputHelper::writeDecimal(*((OutputHelper **)this + 21), v16);
            OutputHelper::write(*((OutputHelper **)this + 21), L"\r\n");
            OutputHelper::write(*((OutputHelper **)this + 21), L"SystemId: ");
            v10 = L"\"";
            if ( v17 )
            {
              OutputHelper::write(*((OutputHelper **)this + 21), L"\"");
              v11 = xstrlenw(v17, 0x7FFFFFFFu);
              OutputHelper::write(*((OutputHelper **)this + 21), v17, v11);
              v12 = L"\"";
            }
            else
            {
              v12 = L"NULL";
            }
            OutputHelper::write(*((OutputHelper **)this + 21), v12);
            OutputHelper::write(*((OutputHelper **)this + 21), L"\r\n");
            OutputHelper::write(*((OutputHelper **)this + 21), L"PublicId: ");
            if ( v18 )
            {
              OutputHelper::write(*((OutputHelper **)this + 21), L"\"");
              v13 = xstrlenw(v18, 0x7FFFFFFFu);
              OutputHelper::write(*((OutputHelper **)this + 21), v18, v13);
            }
            else
            {
              v10 = L"NULL";
            }
            OutputHelper::write(*((OutputHelper **)this + 21), v10);
            OutputHelper::write(*((OutputHelper **)this + 21), L"\r\n");
LABEL_17:
            OutputHelper::write(*((OutputHelper **)this + 21), L"Description: ");
            if ( !v6 )
              v6 = L"NULL";
            OutputHelper::write(*((OutputHelper **)this + 21), v6);
            OutputHelper::write(*((OutputHelper **)this + 21), L"\r\nError Code: ");
            OutputHelper::writeDecimal(*((OutputHelper **)this + 21), a4);
            OutputHelper::write(*((OutputHelper **)this + 21), L"\r\n");
          }
        }
      }
    }
LABEL_20:
    OutputHelper::flush(*((OutputHelper **)this + 21));
  }
  ModelInit::~ModelInit((ModelInit *)v19);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800cbc14  mov     [rsp+arg_0], rcx
0x1800cbc19  push    rbx
0x1800cbc1a  push    rsi
0x1800cbc1b  push    rdi
0x1800cbc1c  push    r12
0x1800cbc1e  push    r14
0x1800cbc20  push    r15
0x1800cbc22  sub     rsp, 58h
0x1800cbc26  mov     r12d, r9d
0x1800cbc29  mov     r15, r8
0x1800cbc2c  mov     rsi, rdx
0x1800cbc2f  mov     rbx, rcx
0x1800cbc32  xor     edx, edx
0x1800cbc34  lea     rcx, [rsp+88h+var_48]
0x1800cbc39  call    ?init@ModelInit@@QEAAJW4RentalEnum@@@Z; ModelInit::init(RentalEnum)
0x1800cbc3e  mov     edi, eax
0x1800cbc40  test    eax, eax
0x1800cbc42  js      loc_1800CC0C0
0x1800cbc48  mov     [rsp+88h+var_64], 0
0x1800cbc50  mov     [rsp+88h+var_60], 0
0x1800cbc58  mov     [rsp+88h+var_58], 0
0x1800cbc61  mov     [rsp+88h+var_50], 0
0x1800cbc6a  cmp     dword ptr [rbx+0A0h], 0
0x1800cbc71  jnz     short loc_1800CBC7D
0x1800cbc73  xor     edi, edi
0x1800cbc75  mov     [rbx+0A0h], edi
0x1800cbc7b  jmp     short loc_1800CBC9B
0x1800cbc7d  mov     rax, [rbx]
0x1800cbc80  xor     edx, edx
0x1800cbc82  mov     rcx, rbx
0x1800cbc85  mov     rax, [rax+0C8h]
0x1800cbc8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbc91  mov     edi, eax
0x1800cbc93  test    eax, eax
0x1800cbc95  js      loc_1800CBFF1
0x1800cbc9b  lea     rdx, asc_18012EF90; "\r\n"
0x1800cbca2  mov     rcx, [rbx+0A8h]; this
0x1800cbca9  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbcae  mov     rdx, [rsp+88h+arg_20]; unsigned __int16 *
0x1800cbcb6  mov     rcx, [rbx+0A8h]; this
0x1800cbcbd  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbcc2  lea     rdx, asc_180133828; ":\r\n"
0x1800cbcc9  mov     rcx, [rbx+0A8h]; this
0x1800cbcd0  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbcd5  test    rsi, rsi
0x1800cbcd8  jz      loc_1800CBEBE
0x1800cbcde  mov     rax, [rsi]
0x1800cbce1  lea     rdx, [rsp+88h+var_64]
0x1800cbce6  mov     rcx, rsi
0x1800cbce9  mov     rax, [rax+20h]
0x1800cbced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbcf2  mov     edi, eax
0x1800cbcf4  mov     [rsp+88h+var_68], eax
0x1800cbcf8  test    eax, eax
0x1800cbcfa  js      loc_1800CBFF1
0x1800cbd00  mov     rax, [rsi]
0x1800cbd03  lea     rdx, [rsp+88h+var_60]
0x1800cbd08  mov     rcx, rsi
0x1800cbd0b  mov     rax, [rax+18h]
0x1800cbd0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbd14  mov     edi, eax
0x1800cbd16  mov     [rsp+88h+var_68], eax
0x1800cbd1a  test    eax, eax
0x1800cbd1c  js      loc_1800CBFF1
0x1800cbd22  mov     rax, [rsi]
0x1800cbd25  lea     rdx, [rsp+88h+var_58]
0x1800cbd2a  mov     rcx, rsi
0x1800cbd2d  mov     rax, [rax+30h]
0x1800cbd31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbd36  mov     edi, eax
0x1800cbd38  mov     [rsp+88h+var_68], eax
0x1800cbd3c  test    eax, eax
0x1800cbd3e  js      loc_1800CBFF1
0x1800cbd44  mov     rax, [rsi]
0x1800cbd47  lea     rdx, [rsp+88h+var_50]
0x1800cbd4c  mov     rcx, rsi
0x1800cbd4f  mov     rax, [rax+28h]
0x1800cbd53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbd58  mov     edi, eax
0x1800cbd5a  mov     [rsp+88h+var_68], eax
0x1800cbd5e  test    eax, eax
0x1800cbd60  js      loc_1800CBFF1
0x1800cbd66  lea     rdx, aLineNumber; "Line Number: "
0x1800cbd6d  mov     rcx, [rbx+0A8h]; this
0x1800cbd74  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbd79  mov     edx, [rsp+88h+var_64]; int
0x1800cbd7d  mov     rcx, [rbx+0A8h]; this
0x1800cbd84  call    ?writeDecimal@OutputHelper@@QEAAXH@Z; OutputHelper::writeDecimal(int)
0x1800cbd89  lea     rdx, aColumnNumber; "\r\nColumn Number: "
0x1800cbd90  mov     rcx, [rbx+0A8h]; this
0x1800cbd97  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbd9c  mov     edx, [rsp+88h+var_60]; int
0x1800cbda0  mov     rcx, [rbx+0A8h]; this
0x1800cbda7  call    ?writeDecimal@OutputHelper@@QEAAXH@Z; OutputHelper::writeDecimal(int)
0x1800cbdac  lea     rdx, asc_18012EF90; "\r\n"
0x1800cbdb3  mov     rcx, [rbx+0A8h]; this
0x1800cbdba  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbdbf  lea     rdx, aSystemid; "SystemId: "
0x1800cbdc6  mov     rcx, [rbx+0A8h]; this
0x1800cbdcd  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbdd2  lea     r14, asc_1801310F0; "\""
0x1800cbdd9  cmp     [rsp+88h+var_58], 0
0x1800cbddf  jz      short loc_1800CBE1F
0x1800cbde1  mov     rdx, r14; unsigned __int16 *
0x1800cbde4  mov     rcx, [rbx+0A8h]; this
0x1800cbdeb  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbdf0  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800cbdf5  mov     rcx, [rsp+88h+var_58]; unsigned __int16 *
0x1800cbdfa  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x1800cbdff  mov     r8d, eax; int
0x1800cbe02  mov     rdx, [rsp+88h+var_58]; unsigned __int16 *
0x1800cbe07  mov     rcx, [rbx+0A8h]; this
0x1800cbe0e  call    ?write@OutputHelper@@QEAAXPEBGH@Z; OutputHelper::write(ushort const *,int)
0x1800cbe13  mov     rdx, r14
0x1800cbe16  lea     rsi, aNull; "NULL"
0x1800cbe1d  jmp     short loc_1800CBE29
0x1800cbe1f  lea     rsi, aNull; "NULL"
0x1800cbe26  mov     rdx, rsi; unsigned __int16 *
0x1800cbe29  mov     rcx, [rbx+0A8h]; this
0x1800cbe30  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbe35  lea     rdx, asc_18012EF90; "\r\n"
0x1800cbe3c  mov     rcx, [rbx+0A8h]; this
0x1800cbe43  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbe48  lea     rdx, aPublicid; "PublicId: "
0x1800cbe4f  mov     rcx, [rbx+0A8h]; this
0x1800cbe56  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbe5b  cmp     [rsp+88h+var_50], 0
0x1800cbe61  jz      short loc_1800CBE97
0x1800cbe63  mov     rdx, r14; unsigned __int16 *
0x1800cbe66  mov     rcx, [rbx+0A8h]; this
0x1800cbe6d  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbe72  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800cbe77  mov     rcx, [rsp+88h+var_50]; unsigned __int16 *
0x1800cbe7c  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x1800cbe81  mov     r8d, eax; int
0x1800cbe84  mov     rdx, [rsp+88h+var_50]; unsigned __int16 *
0x1800cbe89  mov     rcx, [rbx+0A8h]; this
0x1800cbe90  call    ?write@OutputHelper@@QEAAXPEBGH@Z; OutputHelper::write(ushort const *,int)
0x1800cbe95  jmp     short loc_1800CBE9A
0x1800cbe97  mov     r14, rsi
0x1800cbe9a  mov     rdx, r14; unsigned __int16 *
0x1800cbe9d  mov     rcx, [rbx+0A8h]; this
0x1800cbea4  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbea9  lea     rdx, asc_18012EF90; "\r\n"
0x1800cbeb0  mov     rcx, [rbx+0A8h]; this
0x1800cbeb7  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbebc  jmp     short loc_1800CBEC5
0x1800cbebe  lea     rsi, aNull; "NULL"
0x1800cbec5  lea     rdx, aDescription_0; "Description: "
0x1800cbecc  mov     rcx, [rbx+0A8h]; this
0x1800cbed3  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbed8  test    r15, r15
0x1800cbedb  cmovz   r15, rsi
0x1800cbedf  mov     rdx, r15; unsigned __int16 *
0x1800cbee2  mov     rcx, [rbx+0A8h]; this
0x1800cbee9  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbeee  lea     rdx, aErrorCode; "\r\nError Code: "
0x1800cbef5  mov     rcx, [rbx+0A8h]; this
0x1800cbefc  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbf01  mov     edx, r12d; int
0x1800cbf04  mov     rcx, [rbx+0A8h]; this
0x1800cbf0b  call    ?writeDecimal@OutputHelper@@QEAAXH@Z; OutputHelper::writeDecimal(int)
0x1800cbf10  lea     rdx, asc_18012EF90; "\r\n"
0x1800cbf17  mov     rcx, [rbx+0A8h]; this
0x1800cbf1e  call    ?write@OutputHelper@@QEAAXPEBG@Z; OutputHelper::write(ushort const *)
0x1800cbf23  jmp     loc_1800CBFF1
0x1800cbf28  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800cbf2e  call    cs:__imp_TlsGetValue
0x1800cbf34  mov     rbx, rax
0x1800cbf37  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800cbf3e  jnz     short loc_1800CBFB9
0x1800cbf40  call    cs:__imp__resetstkoflw
0x1800cbf46  test    eax, eax
0x1800cbf48  jnz     short loc_1800CBF9B
0x1800cbf4a  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800cbf51  test    rcx, rcx
0x1800cbf54  jz      short loc_1800CBF68
0x1800cbf56  cmp     [rcx+50h], rbx
0x1800cbf5a  jnz     short loc_1800CBF68
0x1800cbf5c  mov     rax, [rcx]
0x1800cbf5f  mov     rax, [rax+20h]
0x1800cbf63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbf68  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800cbf6f  test    rcx, rcx
0x1800cbf72  jz      short loc_1800CBF86
0x1800cbf74  cmp     [rcx+50h], rbx
0x1800cbf78  jnz     short loc_1800CBF86
0x1800cbf7a  mov     rax, [rcx]
0x1800cbf7d  mov     rax, [rax+20h]
0x1800cbf81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbf86  xor     r9d, r9d; lpArguments
0x1800cbf89  xor     r8d, r8d; nNumberOfArguments
0x1800cbf8c  xor     edx, edx; dwExceptionFlags
0x1800cbf8e  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800cbf93  call    cs:__imp_RaiseException
0x1800cbf99  jmp     short loc_1800CBFB9
0x1800cbf9b  mov     rax, [rbx+60h]
0x1800cbf9f  mov     [rbx+68h], rax
0x1800cbfa3  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800cbfaa  mov     [rbx+60h], rax
0x1800cbfae  mov     dword ptr [rbx+54h], 800703E9h
0x1800cbfb5  mov     byte ptr [rbx+78h], 0
0x1800cbfb9  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800cbfbf  call    cs:__imp_TlsGetValue
0x1800cbfc5  mov     rcx, [rax+60h]; struct Exception *
0x1800cbfc9  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x1800cbfce  mov     rdx, rax
0x1800cbfd1  mov     rcx, [rax]
0x1800cbfd4  mov     rax, [rcx+80h]
0x1800cbfdb  mov     rcx, rdx
0x1800cbfde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbfe3  mov     edi, eax
0x1800cbfe5  mov     [rsp+88h+var_68], eax
0x1800cbfe9  mov     rbx, [rsp+88h+arg_0]
0x1800cbff1  nop
0x1800cbff2  mov     rcx, [rbx+0A8h]; this
0x1800cbff9  call    ?flush@OutputHelper@@QEAAXXZ; OutputHelper::flush(void)
0x1800cbffe  jmp     loc_1800CC0C0
0x1800cc003  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800cc009  call    cs:__imp_TlsGetValue
0x1800cc00f  mov     rbx, rax
0x1800cc012  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800cc019  jnz     short loc_1800CC094
0x1800cc01b  call    cs:__imp__resetstkoflw
0x1800cc021  test    eax, eax
0x1800cc023  jnz     short loc_1800CC076
0x1800cc025  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800cc02c  test    rcx, rcx
0x1800cc02f  jz      short loc_1800CC043
0x1800cc031  cmp     [rcx+50h], rbx
0x1800cc035  jnz     short loc_1800CC043
0x1800cc037  mov     rax, [rcx]
0x1800cc03a  mov     rax, [rax+20h]
0x1800cc03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc043  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800cc04a  test    rcx, rcx
0x1800cc04d  jz      short loc_1800CC061
0x1800cc04f  cmp     [rcx+50h], rbx
0x1800cc053  jnz     short loc_1800CC061
0x1800cc055  mov     rax, [rcx]
0x1800cc058  mov     rax, [rax+20h]
0x1800cc05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc061  xor     r9d, r9d; lpArguments
0x1800cc064  xor     r8d, r8d; nNumberOfArguments
0x1800cc067  xor     edx, edx; dwExceptionFlags
0x1800cc069  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800cc06e  call    cs:__imp_RaiseException
0x1800cc074  jmp     short loc_1800CC094
0x1800cc076  mov     rax, [rbx+60h]
0x1800cc07a  mov     [rbx+68h], rax
0x1800cc07e  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800cc085  mov     [rbx+60h], rax
0x1800cc089  mov     dword ptr [rbx+54h], 800703E9h
0x1800cc090  mov     byte ptr [rbx+78h], 0
0x1800cc094  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800cc09a  call    cs:__imp_TlsGetValue
0x1800cc0a0  mov     rcx, [rax+60h]; struct Exception *
0x1800cc0a4  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x1800cc0a9  mov     rdx, rax
0x1800cc0ac  mov     rcx, [rax]
0x1800cc0af  mov     rax, [rcx+80h]
0x1800cc0b6  mov     rcx, rdx
0x1800cc0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc0be  mov     edi, eax
0x1800cc0c0  lea     rcx, [rsp+88h+var_48]; this
0x1800cc0c5  call    ??1ModelInit@@QEAA@XZ; ModelInit::~ModelInit(void)
0x1800cc0ca  mov     eax, edi
0x1800cc0cc  add     rsp, 58h
0x1800cc0d0  pop     r15
0x1800cc0d2  pop     r14
0x1800cc0d4  pop     r12
0x1800cc0d6  pop     rdi
0x1800cc0d7  pop     rsi
0x1800cc0d8  pop     rbx
0x1800cc0d9  retn
0x180104064  push    rbp
0x180104066  sub     rsp, 20h
0x18010406a  mov     rbp, rdx
0x18010406d  xor     edx, edx; bool
0x18010406f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z; Exception::fillException(_EXCEPTION_POINTERS *,bool)
0x180104074  nop
0x180104075  add     rsp, 20h
0x180104079  pop     rbp
0x18010407a  retn
0x18010407c  push    rbp
0x18010407e  sub     rsp, 20h
0x180104082  mov     rbp, rdx
0x180104085  xor     edx, edx; bool
0x180104087  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z; Exception::fillException(_EXCEPTION_POINTERS *,bool)
0x18010408c  nop
0x18010408d  add     rsp, 20h
0x180104091  pop     rbp
0x180104092  retn
```
