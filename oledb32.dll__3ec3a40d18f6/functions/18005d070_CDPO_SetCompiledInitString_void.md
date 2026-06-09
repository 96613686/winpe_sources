# CDPO::SetCompiledInitString(void *)

- ea: `0x18005d070`
- end: `0x18005d543`
- name: `?SetCompiledInitString@CDPO@@UEAAJPEAX@Z`
- size: `1235`
- prototype: `int(CDPO *__hidden this, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013870`
- `0x180013e30`
- `0x180015170`
- `0x180015504`
- `0x180022fd0`
- `0x180025664`
- `0x180029560`
- `0x180029694`
- `0x18002ec0c`
- `0x18005bb94`
- `0x18005d070`
- `0x18005d710`
- `0x180062670`

## import_xrefs

- `MSDART!mpFree` at `0x18005d4ff`
- `MSDART!mpFree` at `0x18005d4ff`
- `KERNEL32!EnterCriticalSection` at `0x18005d0da`
- `KERNEL32!EnterCriticalSection` at `0x18005d0da`
- `KERNEL32!LeaveCriticalSection` at `0x18005d4f1`
- `KERNEL32!LeaveCriticalSection` at `0x18005d4f1`

## string_xrefs

- `0x18005d105`: `<CDPO::SetCompiledInitString|OLEDB|ERR> `
- `0x18005d123`: `<CDPO::SetCompiledInitString|OLEDB|ERR> `
- `0x18005d199`: `<CDPO::SetCompiledInitString|OLEDB|ERR> `
- `0x18005d1b7`: `<CDPO::SetCompiledInitString|OLEDB|ERR> `
- `0x18005d238`: `<CDPO::SetCompiledInitString|OLEDB|ERR> `
- `0x18005d256`: `<CDPO::SetCompiledInitString|OLEDB|ERR> `
- `0x18005d2f2`: `<CDPO::SetCompiledInitString|OLEDB|ERR> `
- `0x18005d310`: `<CDPO::SetCompiledInitString|OLEDB|ERR> `
- `0x18005d3a9`: `<CDPO::SetCompiledInitString|OLEDB|ERR> `
- `0x18005d3c7`: `<CDPO::SetCompiledInitString|OLEDB|ERR> `
- `0x18005d473`: `<CDPO::SetCompiledInitString|OLEDB|ERR> `
- `0x18005d491`: `<CDPO::SetCompiledInitString|OLEDB|ERR> `
- `0x18005d09a`: `<CDPO::SetCompiledInitString|Trace|HR> `
- `0x18005d13e`: `<CDPO::SetCompiledInitString|Trace|HR> `
- `0x18005d1d2`: `<CDPO::SetCompiledInitString|Trace|HR> `
- `0x18005d271`: `<CDPO::SetCompiledInitString|Trace|HR> `
- `0x18005d32b`: `<CDPO::SetCompiledInitString|Trace|HR> `
- `0x18005d3e2`: `<CDPO::SetCompiledInitString|Trace|HR> `
- `0x18005d4ac`: `<CDPO::SetCompiledInitString|Trace|HR> `
- `0x18005d512`: `<CDPO::SetCompiledInitString|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CDPO::SetCompiledInitString(CDPO *this, CCompiledInitString *a2)
{
  struct _RTL_CRITICAL_SECTION *v6; // r15
  struct CCMProviderInfoManager *v7; // r8
  int v8; // edi
  int v9; // edi
  unsigned int v10; // edi
  int v11; // edi
  unsigned int v12; // ebx
  struct tagDBPROPSET *v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // ebx
  int pExceptionObject; // [rsp+30h] [rbp-58h] BYREF
  int v19; // [rsp+34h] [rbp-54h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v21; // [rsp+3Ch] [rbp-4Ch] BYREF
  int v22; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v23; // [rsp+44h] [rbp-44h] BYREF
  unsigned int v24; // [rsp+48h] [rbp-40h] BYREF
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+50h] [rbp-38h]
  int v26; // [rsp+98h] [rbp+10h] BYREF
  unsigned __int16 *v27; // [rsp+A0h] [rbp+18h] BYREF
  unsigned int *v28; // [rsp+A8h] [rbp+20h] BYREF

  if ( a2 )
  {
    v27 = 0;
    v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
    v25 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    try
    {
      v8 = CCompiledInitString::IndexProviderProps(a2, *((struct CCMProviderInfo **)this + 11), v7);
      if ( v8 < 0 )
      {
        if ( (bidGblFlags & 2) != 0
          && (OLEDBTraceErr(v8, L"<CDPO::SetCompiledInitString|OLEDB|ERR> ", 0x441u), (bidGblFlags & 2) != 0)
          && (OLEDBTraceErr(v8, L"<CDPO::SetCompiledInitString|OLEDB|ERR> ", 0x441u), (bidGblFlags & 2) != 0) )
        {
          pExceptionObject = bidTraceHR(
                               off_1800C8410[0],
                               1115145,
                               L"<CDPO::SetCompiledInitString|Trace|HR> ",
                               (unsigned int)v8);
        }
        else
        {
          pExceptionObject = v8;
        }
        throw (long *)&pExceptionObject;
      }
      v9 = CCompiledInitString::GatherExtendedProperties(a2, &v27);
      if ( v9 < 0 )
      {
        if ( (bidGblFlags & 2) != 0
          && (OLEDBTraceErr(v9, L"<CDPO::SetCompiledInitString|OLEDB|ERR> ", 0x446u), (bidGblFlags & 2) != 0)
          && (OLEDBTraceErr(v9, L"<CDPO::SetCompiledInitString|OLEDB|ERR> ", 0x446u), (bidGblFlags & 2) != 0) )
        {
          v19 = bidTraceHR(off_1800C8410[0], 1120265, L"<CDPO::SetCompiledInitString|Trace|HR> ", (unsigned int)v9);
        }
        else
        {
          v19 = v9;
        }
        throw (long *)&v19;
      }
      v10 = CCompiledInitString::SetNonExtendedProperties(
              a2,
              *((struct CCMProviderInfo **)this + 11),
              (CDPO *)((char *)this + 112),
              1);
      if ( (v10 & 0x80000000) != 0 )
      {
        if ( (bidGblFlags & 2) != 0
          && (OLEDBTraceErr(v10, L"<CDPO::SetCompiledInitString|OLEDB|ERR> ", 0x44Au), (bidGblFlags & 2) != 0)
          && (OLEDBTraceErr(v10, L"<CDPO::SetCompiledInitString|OLEDB|ERR> ", 0x44Au), (bidGblFlags & 2) != 0) )
        {
          v20 = bidTraceHR(off_1800C8410[0], 1124361, L"<CDPO::SetCompiledInitString|Trace|HR> ", v10);
        }
        else
        {
          v20 = v10;
        }
        throw (long *)&v20;
      }
      if ( v27 || CCompiledInitString::ContainsExtendedProperties(a2) )
      {
        v10 = CCompiledInitString::SetExtendedProperties(
                a2,
                *((struct CCMProviderInfo **)this + 11),
                (CDPO *)((char *)this + 112),
                &v27,
                1);
        if ( (v10 & 0x80000000) != 0 )
        {
          if ( (bidGblFlags & 2) != 0
            && (OLEDBTraceErr(v10, L"<CDPO::SetCompiledInitString|OLEDB|ERR> ", 0x450u), (bidGblFlags & 2) != 0)
            && (OLEDBTraceErr(v10, L"<CDPO::SetCompiledInitString|OLEDB|ERR> ", 0x450u), (bidGblFlags & 2) != 0) )
          {
            v21 = bidTraceHR(off_1800C8410[0], 1130505, L"<CDPO::SetCompiledInitString|Trace|HR> ", v10);
          }
          else
          {
            v21 = v10;
          }
          throw (long *)&v21;
        }
      }
      if ( *((_QWORD *)this + 8) && (*((_BYTE *)this + 200) & 1) == 0 )
      {
        v28 = 0;
        v11 = StoreTouchState((CDPO *)((char *)this + 112), &v28);
        if ( v11 < 0 )
        {
          if ( (bidGblFlags & 2) != 0
            && (OLEDBTraceErr(v11, L"<CDPO::SetCompiledInitString|OLEDB|ERR> ", 0x458u), (bidGblFlags & 2) != 0)
            && (OLEDBTraceErr(v11, L"<CDPO::SetCompiledInitString|OLEDB|ERR> ", 0x458u), (bidGblFlags & 2) != 0) )
          {
            v22 = bidTraceHR(off_1800C8410[0], 1138697, L"<CDPO::SetCompiledInitString|Trace|HR> ", (unsigned int)v11);
          }
          else
          {
            v22 = v11;
          }
          throw (long *)&v22;
        }
        v12 = *((_DWORD *)this + 28);
        v13 = (struct tagDBPROPSET *)*((_QWORD *)this + 15);
        v26 = CDCM::SetPropertiesPrivate((CDCM *)(*((_QWORD *)this + 8) + 24LL), (CDPO *)((char *)this + 112));
        FixupHRForOLEDBServices(v12, v13, &v26);
        RestoreTouchState((CDPO *)((char *)this + 112), &v28);
        v10 = v26;
        if ( v26 < 0 )
        {
          if ( (bidGblFlags & 2) != 0
            && (OLEDBTraceErr(v26, L"<CDPO::SetCompiledInitString|OLEDB|ERR> ", 0x461u), (bidGblFlags & 2) != 0)
            && (OLEDBTraceErr(v10, L"<CDPO::SetCompiledInitString|OLEDB|ERR> ", 0x461u), (bidGblFlags & 2) != 0) )
          {
            v23 = bidTraceHR(off_1800C8410[0], 1147913, L"<CDPO::SetCompiledInitString|Trace|HR> ", v10);
          }
          else
          {
            v23 = v10;
          }
          throw (long *)&v23;
        }
      }
    }
    catch ( long v24 )
    {
      v17 = v24;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v24, L"<CDPO::SetCompiledInitString|OLEDB|ERR> ", 0x466u);
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800C8898[0] )
            bidTraceA(off_1800C8410[0], 1154048, off_1800C8898[0], v17);
        }
      }
      v26 = v17;
      v10 = v17;
      v6 = v25;
    }
    LeaveCriticalSection(v6);
    mpFree(v27, v14, v15, v16);
    if ( (bidGblFlags & 2) != 0 )
      return (unsigned int)bidTraceHR(off_1800C8410[0], 1161225, L"<CDPO::SetCompiledInitString|Trace|HR> ", v10);
    return v10;
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    return (unsigned int)bidTraceHR(off_1800C8410[0], 1099785, L"<CDPO::SetCompiledInitString|Trace|HR> ", 1);
  }
  else
  {
    return 1;
  }
}

```

## disassembly

```asm
0x18005d070  mov     [rsp+arg_0], rbx
0x18005d075  push    rsi
0x18005d076  push    rdi
0x18005d077  push    r12
0x18005d079  push    r14
0x18005d07b  push    r15
0x18005d07d  sub     rsp, 60h
0x18005d081  mov     r14, rdx
0x18005d084  mov     rsi, rcx
0x18005d087  test    rdx, rdx
0x18005d08a  jnz     short loc_18005D0C2
0x18005d08c  mov     bl, 2
0x18005d08e  test    byte ptr cs:_bidGblFlags, bl
0x18005d094  jz      short loc_18005D0B6
0x18005d096  lea     r9d, [rdx+1]
0x18005d09a  lea     r8, aCdpoSetcompile; "<CDPO::SetCompiledInitString|Trace|HR> "
0x18005d0a1  mov     edx, 10C809h
0x18005d0a6  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005d0ad  call    _bidTraceHR
0x18005d0b2  mov     ebx, eax
0x18005d0b4  jmp     short loc_18005D0BB
0x18005d0b6  mov     ebx, 1
0x18005d0bb  mov     eax, ebx
0x18005d0bd  jmp     loc_18005D52E
0x18005d0c2  mov     [rsp+88h+arg_10], 0
0x18005d0ce  lea     r15, [rcx+10h]
0x18005d0d2  mov     [rsp+88h+var_38], r15
0x18005d0d7  mov     rcx, r15; lpCriticalSection
0x18005d0da  call    cs:__imp_EnterCriticalSection
0x18005d0e0  nop
0x18005d0e1  mov     rdx, [rsi+58h]; struct CCMProviderInfo *
0x18005d0e5  mov     rcx, r14; this
0x18005d0e8  call    ?IndexProviderProps@CCompiledInitString@@QEAAJPEAVCCMProviderInfo@@PEAVCCMProviderInfoManager@@@Z; CCompiledInitString::IndexProviderProps(CCMProviderInfo *,CCMProviderInfoManager *)
0x18005d0ed  mov     edi, eax
0x18005d0ef  test    eax, eax
0x18005d0f1  jns     short loc_18005D171
0x18005d0f3  mov     eax, cs:_bidGblFlags
0x18005d0f9  mov     bl, 2
0x18005d0fb  test    bl, al
0x18005d0fd  jz      short loc_18005D15C
0x18005d0ff  mov     r8d, 441h; unsigned int
0x18005d105  lea     rdx, aCdpoSetcompile_0; "<CDPO::SetCompiledInitString|OLEDB|ERR>"...
0x18005d10c  mov     ecx, edi; int
0x18005d10e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005d113  mov     eax, cs:_bidGblFlags
0x18005d119  test    bl, al
0x18005d11b  jz      short loc_18005D15C
0x18005d11d  mov     r8d, 441h; unsigned int
0x18005d123  lea     rdx, aCdpoSetcompile_0; "<CDPO::SetCompiledInitString|OLEDB|ERR>"...
0x18005d12a  mov     ecx, edi; int
0x18005d12c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005d131  mov     eax, cs:_bidGblFlags
0x18005d137  test    bl, al
0x18005d139  jz      short loc_18005D15C
0x18005d13b  mov     r9d, edi
0x18005d13e  lea     r8, aCdpoSetcompile; "<CDPO::SetCompiledInitString|Trace|HR> "
0x18005d145  mov     edx, 110409h
0x18005d14a  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005d151  call    _bidTraceHR
0x18005d156  mov     [rsp+88h+pExceptionObject], eax
0x18005d15a  jmp     short loc_18005D160
0x18005d15c  mov     [rsp+88h+pExceptionObject], edi
0x18005d160  lea     rdx, _TI1J; pThrowInfo
0x18005d167  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18005d16c  call    _CxxThrowException_0
0x18005d171  lea     rdx, [rsp+88h+arg_10]; unsigned __int16 **
0x18005d179  mov     rcx, r14; this
0x18005d17c  call    ?GatherExtendedProperties@CCompiledInitString@@QEAAJPEAPEAG@Z; CCompiledInitString::GatherExtendedProperties(ushort * *)
0x18005d181  mov     edi, eax
0x18005d183  test    eax, eax
0x18005d185  jns     short loc_18005D205
0x18005d187  mov     eax, cs:_bidGblFlags
0x18005d18d  mov     bl, 2
0x18005d18f  test    bl, al
0x18005d191  jz      short loc_18005D1F0
0x18005d193  mov     r8d, 446h; unsigned int
0x18005d199  lea     rdx, aCdpoSetcompile_0; "<CDPO::SetCompiledInitString|OLEDB|ERR>"...
0x18005d1a0  mov     ecx, edi; int
0x18005d1a2  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005d1a7  mov     eax, cs:_bidGblFlags
0x18005d1ad  test    bl, al
0x18005d1af  jz      short loc_18005D1F0
0x18005d1b1  mov     r8d, 446h; unsigned int
0x18005d1b7  lea     rdx, aCdpoSetcompile_0; "<CDPO::SetCompiledInitString|OLEDB|ERR>"...
0x18005d1be  mov     ecx, edi; int
0x18005d1c0  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005d1c5  mov     eax, cs:_bidGblFlags
0x18005d1cb  test    bl, al
0x18005d1cd  jz      short loc_18005D1F0
0x18005d1cf  mov     r9d, edi
0x18005d1d2  lea     r8, aCdpoSetcompile; "<CDPO::SetCompiledInitString|Trace|HR> "
0x18005d1d9  mov     edx, 111809h
0x18005d1de  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005d1e5  call    _bidTraceHR
0x18005d1ea  mov     [rsp+88h+var_54], eax
0x18005d1ee  jmp     short loc_18005D1F4
0x18005d1f0  mov     [rsp+88h+var_54], edi
0x18005d1f4  lea     rdx, _TI1J; pThrowInfo
0x18005d1fb  lea     rcx, [rsp+88h+var_54]; pExceptionObject
0x18005d200  call    _CxxThrowException_0
0x18005d205  lea     r12, [rsi+70h]
0x18005d209  mov     ebx, 1
0x18005d20e  mov     r9d, ebx; int
0x18005d211  mov     r8, r12; struct CDSLPropertySetArray *
0x18005d214  mov     rdx, [rsi+58h]; struct CCMProviderInfo *
0x18005d218  mov     rcx, r14; this
0x18005d21b  call    ?SetNonExtendedProperties@CCompiledInitString@@QEAAJPEAVCCMProviderInfo@@AEAVCDSLPropertySetArray@@H@Z; CCompiledInitString::SetNonExtendedProperties(CCMProviderInfo *,CDSLPropertySetArray &,int)
0x18005d220  mov     edi, eax
0x18005d222  test    eax, eax
0x18005d224  jns     short loc_18005D2A4
0x18005d226  mov     eax, cs:_bidGblFlags
0x18005d22c  mov     bl, 2
0x18005d22e  test    bl, al
0x18005d230  jz      short loc_18005D28F
0x18005d232  mov     r8d, 44Ah; unsigned int
0x18005d238  lea     rdx, aCdpoSetcompile_0; "<CDPO::SetCompiledInitString|OLEDB|ERR>"...
0x18005d23f  mov     ecx, edi; int
0x18005d241  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005d246  mov     eax, cs:_bidGblFlags
0x18005d24c  test    bl, al
0x18005d24e  jz      short loc_18005D28F
0x18005d250  mov     r8d, 44Ah; unsigned int
0x18005d256  lea     rdx, aCdpoSetcompile_0; "<CDPO::SetCompiledInitString|OLEDB|ERR>"...
0x18005d25d  mov     ecx, edi; int
0x18005d25f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005d264  mov     eax, cs:_bidGblFlags
0x18005d26a  test    bl, al
0x18005d26c  jz      short loc_18005D28F
0x18005d26e  mov     r9d, edi
0x18005d271  lea     r8, aCdpoSetcompile; "<CDPO::SetCompiledInitString|Trace|HR> "
0x18005d278  mov     edx, 112809h
0x18005d27d  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005d284  call    _bidTraceHR
0x18005d289  mov     [rsp+88h+var_50], eax
0x18005d28d  jmp     short loc_18005D293
0x18005d28f  mov     [rsp+88h+var_50], edi
0x18005d293  lea     rdx, _TI1J; pThrowInfo
0x18005d29a  lea     rcx, [rsp+88h+var_50]; pExceptionObject
0x18005d29f  call    _CxxThrowException_0
0x18005d2a4  cmp     [rsp+88h+arg_10], 0
0x18005d2ad  jnz     short loc_18005D2BF
0x18005d2af  mov     rcx, r14; this
0x18005d2b2  call    ?ContainsExtendedProperties@CCompiledInitString@@QEBA_NXZ; CCompiledInitString::ContainsExtendedProperties(void)
0x18005d2b7  test    al, al
0x18005d2b9  jz      loc_18005D35E
0x18005d2bf  mov     [rsp+88h+var_68], ebx; int
0x18005d2c3  lea     r9, [rsp+88h+arg_10]; unsigned __int16 **
0x18005d2cb  mov     r8, r12; struct CDSLPropertySetArray *
0x18005d2ce  mov     rdx, [rsi+58h]; struct CCMProviderInfo *
0x18005d2d2  mov     rcx, r14; this
0x18005d2d5  call    ?SetExtendedProperties@CCompiledInitString@@QEAAJPEAVCCMProviderInfo@@AEAVCDSLPropertySetArray@@PEAPEAGH@Z; CCompiledInitString::SetExtendedProperties(CCMProviderInfo *,CDSLPropertySetArray &,ushort * *,int)
0x18005d2da  mov     edi, eax
0x18005d2dc  test    eax, eax
0x18005d2de  jns     short loc_18005D35E
0x18005d2e0  mov     eax, cs:_bidGblFlags
0x18005d2e6  mov     bl, 2
0x18005d2e8  test    bl, al
0x18005d2ea  jz      short loc_18005D349
0x18005d2ec  mov     r8d, 450h; unsigned int
0x18005d2f2  lea     rdx, aCdpoSetcompile_0; "<CDPO::SetCompiledInitString|OLEDB|ERR>"...
0x18005d2f9  mov     ecx, edi; int
0x18005d2fb  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005d300  mov     eax, cs:_bidGblFlags
0x18005d306  test    bl, al
0x18005d308  jz      short loc_18005D349
0x18005d30a  mov     r8d, 450h; unsigned int
0x18005d310  lea     rdx, aCdpoSetcompile_0; "<CDPO::SetCompiledInitString|OLEDB|ERR>"...
0x18005d317  mov     ecx, edi; int
0x18005d319  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005d31e  mov     eax, cs:_bidGblFlags
0x18005d324  test    bl, al
0x18005d326  jz      short loc_18005D349
0x18005d328  mov     r9d, edi
0x18005d32b  lea     r8, aCdpoSetcompile; "<CDPO::SetCompiledInitString|Trace|HR> "
0x18005d332  mov     edx, 114009h
0x18005d337  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005d33e  call    _bidTraceHR
0x18005d343  mov     [rsp+88h+var_4C], eax
0x18005d347  jmp     short loc_18005D34D
0x18005d349  mov     [rsp+88h+var_4C], edi
0x18005d34d  lea     rdx, _TI1J; pThrowInfo
0x18005d354  lea     rcx, [rsp+88h+var_4C]; pExceptionObject
0x18005d359  call    _CxxThrowException_0
0x18005d35e  cmp     qword ptr [rsi+40h], 0
0x18005d363  jz      loc_18005D4E0
0x18005d369  test    [rsi+0C8h], bl
0x18005d36f  jnz     loc_18005D4E0
0x18005d375  mov     [rsp+88h+arg_18], 0
0x18005d381  lea     rdx, [rsp+88h+arg_18]; unsigned int **
0x18005d389  mov     rcx, r12; struct CDSLPropertySetArray *
0x18005d38c  call    ?StoreTouchState@@YAJPEAVCDSLPropertySetArray@@PEAPEAK@Z; StoreTouchState(CDSLPropertySetArray *,ulong * *)
0x18005d391  mov     edi, eax
0x18005d393  test    eax, eax
0x18005d395  jns     short loc_18005D415
0x18005d397  mov     eax, cs:_bidGblFlags
0x18005d39d  mov     bl, 2
0x18005d39f  test    bl, al
0x18005d3a1  jz      short loc_18005D400
0x18005d3a3  mov     r8d, 458h; unsigned int
0x18005d3a9  lea     rdx, aCdpoSetcompile_0; "<CDPO::SetCompiledInitString|OLEDB|ERR>"...
0x18005d3b0  mov     ecx, edi; int
0x18005d3b2  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005d3b7  mov     eax, cs:_bidGblFlags
0x18005d3bd  test    bl, al
0x18005d3bf  jz      short loc_18005D400
0x18005d3c1  mov     r8d, 458h; unsigned int
0x18005d3c7  lea     rdx, aCdpoSetcompile_0; "<CDPO::SetCompiledInitString|OLEDB|ERR>"...
0x18005d3ce  mov     ecx, edi; int
0x18005d3d0  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005d3d5  mov     eax, cs:_bidGblFlags
0x18005d3db  test    bl, al
0x18005d3dd  jz      short loc_18005D400
0x18005d3df  mov     r9d, edi
0x18005d3e2  lea     r8, aCdpoSetcompile; "<CDPO::SetCompiledInitString|Trace|HR> "
0x18005d3e9  mov     edx, 116009h
0x18005d3ee  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005d3f5  call    _bidTraceHR
0x18005d3fa  mov     [rsp+88h+var_48], eax
0x18005d3fe  jmp     short loc_18005D404
0x18005d400  mov     [rsp+88h+var_48], edi
0x18005d404  lea     rdx, _TI1J; pThrowInfo
0x18005d40b  lea     rcx, [rsp+88h+var_48]; pExceptionObject
0x18005d410  call    _CxxThrowException_0
0x18005d415  mov     ebx, [r12]
0x18005d419  mov     rdi, [rsi+78h]
0x18005d41d  mov     rcx, [rsi+40h]
0x18005d421  add     rcx, 18h; this
0x18005d425  mov     rdx, r12; struct CDPOPropertySetArray *
0x18005d428  call    ?SetPropertiesPrivate@CDCM@@QEAAJPEAVCDPOPropertySetArray@@@Z; CDCM::SetPropertiesPrivate(CDPOPropertySetArray *)
0x18005d42d  mov     [rsp+88h+arg_8], eax
0x18005d434  lea     r8, [rsp+88h+arg_8]; int *
0x18005d43c  mov     rdx, rdi; struct tagDBPROPSET *
0x18005d43f  mov     ecx, ebx; unsigned int
0x18005d441  call    ?FixupHRForOLEDBServices@@YAXKPEAUtagDBPROPSET@@AEAJ@Z; FixupHRForOLEDBServices(ulong,tagDBPROPSET *,long &)
0x18005d446  lea     rdx, [rsp+88h+arg_18]; unsigned int **
0x18005d44e  mov     rcx, r12; struct CDSLPropertySetArray *
0x18005d451  call    ?RestoreTouchState@@YAXPEAVCDSLPropertySetArray@@PEAPEAK@Z; RestoreTouchState(CDSLPropertySetArray *,ulong * *)
0x18005d456  mov     edi, [rsp+88h+arg_8]
0x18005d45d  test    edi, edi
0x18005d45f  jns     short loc_18005D4E0
0x18005d461  mov     eax, cs:_bidGblFlags
0x18005d467  mov     bl, 2
0x18005d469  test    bl, al
0x18005d46b  jz      short loc_18005D4CA
0x18005d46d  mov     r8d, 461h; unsigned int
0x18005d473  lea     rdx, aCdpoSetcompile_0; "<CDPO::SetCompiledInitString|OLEDB|ERR>"...
0x18005d47a  mov     ecx, edi; int
0x18005d47c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005d481  mov     eax, cs:_bidGblFlags
0x18005d487  test    bl, al
0x18005d489  jz      short loc_18005D4CA
0x18005d48b  mov     r8d, 461h; unsigned int
0x18005d491  lea     rdx, aCdpoSetcompile_0; "<CDPO::SetCompiledInitString|OLEDB|ERR>"...
0x18005d498  mov     ecx, edi; int
0x18005d49a  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005d49f  mov     eax, cs:_bidGblFlags
0x18005d4a5  test    bl, al
0x18005d4a7  jz      short loc_18005D4CA
0x18005d4a9  mov     r9d, edi
0x18005d4ac  lea     r8, aCdpoSetcompile; "<CDPO::SetCompiledInitString|Trace|HR> "
0x18005d4b3  mov     edx, 118409h
0x18005d4b8  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005d4bf  call    _bidTraceHR
0x18005d4c4  mov     [rsp+88h+var_44], eax
0x18005d4c8  jmp     short loc_18005D4CE
0x18005d4ca  mov     [rsp+88h+var_44], edi
0x18005d4ce  lea     rdx, _TI1J; pThrowInfo
0x18005d4d5  lea     rcx, [rsp+88h+var_44]; pExceptionObject
0x18005d4da  call    _CxxThrowException_0
0x18005d4e0  jmp     short loc_18005D4EE
0x18005d4e2  mov     edi, [rsp+88h+arg_8]
0x18005d4e9  mov     r15, [rsp+88h+var_38]
0x18005d4ee  mov     rcx, r15; lpCriticalSection
0x18005d4f1  call    cs:__imp_LeaveCriticalSection
0x18005d4f7  mov     rcx, [rsp+88h+arg_10]
0x18005d4ff  call    cs:__imp_mpFree
0x18005d505  mov     bl, 2
0x18005d507  test    byte ptr cs:_bidGblFlags, bl
0x18005d50d  jz      short loc_18005D52C
0x18005d50f  mov     r9d, edi
0x18005d512  lea     r8, aCdpoSetcompile; "<CDPO::SetCompiledInitString|Trace|HR> "
0x18005d519  mov     edx, 11B809h
0x18005d51e  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005d525  call    _bidTraceHR
0x18005d52a  mov     edi, eax
0x18005d52c  mov     eax, edi
0x18005d52e  mov     rbx, [rsp+88h+arg_0]
0x18005d536  add     rsp, 60h
0x18005d53a  pop     r15
0x18005d53c  pop     r14
0x18005d53e  pop     r12
0x18005d540  pop     rdi
0x18005d541  pop     rsi
0x18005d542  retn
```
