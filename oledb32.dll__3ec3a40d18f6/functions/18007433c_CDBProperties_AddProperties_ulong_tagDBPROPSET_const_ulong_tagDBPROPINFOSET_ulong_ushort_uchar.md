# CDBProperties::AddProperties(ulong,tagDBPROPSET const *,ulong *,tagDBPROPINFOSET * *,ulong *,ushort * *,uchar * *)

- ea: `0x18007433c`
- end: `0x18007473f`
- name: `?AddProperties@CDBProperties@@CAJKPEBUtagDBPROPSET@@PEAKPEAPEAUtagDBPROPINFOSET@@1PEAPEAGPEAPEAE@Z`
- size: `1027`
- prototype: `__int64 __fastcall(unsigned int, const struct tagDBPROPSET *, unsigned int *, struct tagDBPROPINFOSET **, unsigned int *, unsigned __int16 **, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180075620`

## callees

- `0x180013870`
- `0x180028e3c`
- `0x180029560`
- `0x18002bcf8`
- `0x18007433c`
- `0x180075dc0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180074533`
- `ole32!CoTaskMemAlloc` at `0x180074533`
- `ole32!CoTaskMemRealloc` at `0x1800743fb`
- `ole32!CoTaskMemRealloc` at `0x1800744f1`
- `ole32!CoTaskMemRealloc` at `0x1800743fb`
- `ole32!CoTaskMemRealloc` at `0x1800744f1`

## pseudocode

```c
__int64 __fastcall CDBProperties::AddProperties(
        unsigned int a1,
        const struct tagDBPROPSET *a2,
        unsigned int *a3,
        LPVOID *a4,
        unsigned int *a5,
        unsigned __int16 **a6,
        unsigned __int8 **a7)
{
  unsigned int PropertyInfo; // ebx
  LPVOID *v8; // r14
  unsigned int v9; // r12d
  unsigned int *v10; // rsi
  unsigned int v11; // eax
  struct tagDBPROPSET *v12; // r8
  const struct tagDBPROPSET *v13; // rdi
  struct tagDBPROPINFOSET *v14; // r14
  DBPROP *rgProperties; // r15
  int v16; // esi
  __int64 v17; // rbp
  unsigned int Property; // eax
  int v19; // ecx
  DBPROPINFO *v20; // rax
  __int64 i; // rsi
  DBPROP *v22; // r15
  int v23; // edx
  unsigned int Data1; // eax
  __int64 cPropertyInfos; // rdx
  struct tagDBPROPINFO *v26; // r9
  char *v27; // rax
  char *v28; // rbp
  __int64 v29; // r14
  LPVOID v30; // rax
  __int64 j; // rsi
  struct tagDBPROPINFO *v32; // r9
  __int64 v33; // rdx
  struct tagDBPROPSET *v35[11]; // [rsp+20h] [rbp-58h] BYREF
  const struct tagDBPROPSET *v37; // [rsp+88h] [rbp+10h]

  v37 = a2;
  PropertyInfo = 0;
  v8 = a4;
  v9 = 0;
  v10 = a3;
  v11 = a1;
  while ( 1 )
  {
    if ( v9 >= v11 )
    {
      if ( (bidGblFlags & 2) == 0 )
        return PropertyInfo;
      v33 = 184329;
      return (unsigned int)bidTraceHR(off_1800C84E0[0], v33, L"<CDBProperties::AddProperties|Trace|HR> ", PropertyInfo);
    }
    v12 = (struct tagDBPROPSET *)*v8;
    v13 = &a2[v9];
    v35[0] = 0;
    if ( FindPropSet(&v13->guidPropertySet, *v10, v12, v35) == -1 )
      break;
    v14 = (struct tagDBPROPINFOSET *)v35[0];
    if ( v13->cProperties )
    {
      rgProperties = v13->rgProperties;
      v16 = 0;
      v17 = 0;
      do
      {
        Property = FindProperty(v14, rgProperties[v17].dwPropertyID, (struct tagDBPROPINFO **)v35);
        v19 = v16 + 1;
        if ( Property != -1 )
          v19 = v16;
        v17 = (unsigned int)(v17 + 1);
        v16 = v19;
      }
      while ( (unsigned int)v17 < v13->cProperties );
      if ( v19 )
      {
        v20 = (DBPROPINFO *)CoTaskMemRealloc(v14->rgPropertyInfos, 48LL * (v19 + v14->cPropertyInfos));
        if ( !v20 )
        {
          PropertyInfo = -2147024882;
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147024882, L"<CDBProperties::AddProperties|OLEDB|ERR> ", 0x6Bu);
            if ( (bidGblFlags & 2) != 0 )
            {
              v33 = 109577;
              return (unsigned int)bidTraceHR(
                                     off_1800C84E0[0],
                                     v33,
                                     L"<CDBProperties::AddProperties|Trace|HR> ",
                                     PropertyInfo);
            }
          }
          return PropertyInfo;
        }
        v14->rgPropertyInfos = v20;
      }
    }
    for ( i = 0; (unsigned int)i < v13->cProperties; i = (unsigned int)(i + 1) )
    {
      v22 = v13->rgProperties;
      v35[0] = 0;
      if ( FindProperty(v14, v22[i].dwPropertyID, (struct tagDBPROPINFO **)v35) == -1 )
      {
        cPropertyInfos = v14->cPropertyInfos;
        v26 = &v14->rgPropertyInfos[cPropertyInfos];
        v14->cPropertyInfos = cPropertyInfos + 1;
        v26->dwPropertyID = v22[i].dwPropertyID;
        PropertyInfo = CDBProperties::HandleGetPropertyInfo(a6, a7, &v13->guidPropertySet, v26);
        if ( (PropertyInfo & 0x80000000) != 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(PropertyInfo, L"<CDBProperties::AddProperties|OLEDB|ERR> ", 0x8Fu);
            if ( (bidGblFlags & 2) != 0 )
            {
              v33 = 146441;
              return (unsigned int)bidTraceHR(
                                     off_1800C84E0[0],
                                     v33,
                                     L"<CDBProperties::AddProperties|Trace|HR> ",
                                     PropertyInfo);
            }
          }
          return PropertyInfo;
        }
      }
      else
      {
        Data1 = v35[0]->guidPropertySet.Data1;
        if ( Data1 )
        {
          if ( (Data1 & 0x400) == 0 && (v23 == 204 || v23 == 127 || v23 == 134) )
            v35[0]->guidPropertySet.Data1 = Data1 | 0x400;
        }
        else
        {
          PropertyInfo = CDBProperties::HandleGetPropertyInfo(
                           a6,
                           a7,
                           &v13->guidPropertySet,
                           (struct tagDBPROPINFO *)v35[0]);
          if ( (PropertyInfo & 0x80000000) != 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(PropertyInfo, L"<CDBProperties::AddProperties|OLEDB|ERR> ", 0x7Au);
              if ( (bidGblFlags & 2) != 0 )
              {
                v33 = 124937;
                return (unsigned int)bidTraceHR(
                                       off_1800C84E0[0],
                                       v33,
                                       L"<CDBProperties::AddProperties|Trace|HR> ",
                                       PropertyInfo);
              }
            }
            return PropertyInfo;
          }
          ++*a5;
        }
      }
    }
LABEL_31:
    v10 = a3;
    ++v9;
    v8 = a4;
    v11 = a1;
    a2 = v37;
  }
  v27 = (char *)CoTaskMemRealloc(*v8, 32LL * (*v10 + 1));
  v28 = v27;
  if ( !v27 )
  {
    PropertyInfo = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024882, L"<CDBProperties::AddProperties|OLEDB|ERR> ", 0x9Cu);
      if ( (bidGblFlags & 2) != 0 )
      {
        v33 = 159753;
        return (unsigned int)bidTraceHR(
                               off_1800C84E0[0],
                               v33,
                               L"<CDBProperties::AddProperties|Trace|HR> ",
                               PropertyInfo);
      }
    }
    return PropertyInfo;
  }
  *v8 = v27;
  v29 = 32LL * (*v10)++;
  *(GUID *)&v27[v29 + 12] = v13->guidPropertySet;
  *(_DWORD *)&v27[v29 + 8] = v13->cProperties;
  v30 = CoTaskMemAlloc(48LL * v13->cProperties);
  *(_QWORD *)&v28[v29] = v30;
  if ( v30 )
  {
    for ( j = 0; (unsigned int)j < v13->cProperties; j = (unsigned int)(j + 1) )
    {
      v32 = (struct tagDBPROPINFO *)(*(_QWORD *)&v28[v29] + 48 * j);
      v32->dwPropertyID = v13->rgProperties[j].dwPropertyID;
      PropertyInfo = CDBProperties::HandleGetPropertyInfo(a6, a7, &v13->guidPropertySet, v32);
      if ( (PropertyInfo & 0x80000000) != 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(PropertyInfo, L"<CDBProperties::AddProperties|OLEDB|ERR> ", 0xAFu);
          if ( (bidGblFlags & 2) != 0 )
          {
            v33 = 179209;
            return (unsigned int)bidTraceHR(
                                   off_1800C84E0[0],
                                   v33,
                                   L"<CDBProperties::AddProperties|Trace|HR> ",
                                   PropertyInfo);
          }
        }
        return PropertyInfo;
      }
    }
    goto LABEL_31;
  }
  PropertyInfo = -2147024882;
  if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(-2147024882, L"<CDBProperties::AddProperties|OLEDB|ERR> ", 0xA6u);
    if ( (bidGblFlags & 2) != 0 )
    {
      v33 = 169993;
      return (unsigned int)bidTraceHR(off_1800C84E0[0], v33, L"<CDBProperties::AddProperties|Trace|HR> ", PropertyInfo);
    }
  }
  return PropertyInfo;
}

```

## disassembly

```asm
0x18007433c  mov     rax, rsp
0x18007433f  mov     [rax+20h], r9
0x180074343  mov     [rax+18h], r8
0x180074347  mov     [rax+10h], rdx
0x18007434b  mov     [rax+8], ecx
0x18007434e  push    rbx
0x18007434f  push    rbp
0x180074350  push    rsi
0x180074351  push    rdi
0x180074352  push    r12
0x180074354  push    r13
0x180074356  push    r14
0x180074358  push    r15
0x18007435a  sub     rsp, 38h
0x18007435e  xor     ebx, ebx
0x180074360  mov     r14, r9
0x180074363  xor     r12d, r12d
0x180074366  mov     rsi, r8
0x180074369  mov     eax, ecx
0x18007436b  cmp     r12d, eax
0x18007436e  jnb     loc_180074706
0x180074374  mov     r8, [r14]; struct tagDBPROPSET *
0x180074377  lea     r9, [rsp+78h+var_58]; struct tagDBPROPSET **
0x18007437c  mov     edi, r12d
0x18007437f  shl     rdi, 5
0x180074383  add     rdi, rdx
0x180074386  mov     [rsp+78h+var_58], 0
0x18007438f  mov     edx, [rsi]; unsigned int
0x180074391  lea     r13, [rdi+0Ch]
0x180074395  mov     rcx, r13; struct _GUID *
0x180074398  call    ?FindPropSet@@YAKAEBU_GUID@@KPEAUtagDBPROPSET@@PEAPEAU2@@Z; FindPropSet(_GUID const &,ulong,tagDBPROPSET *,tagDBPROPSET * *)
0x18007439d  cmp     eax, 0FFFFFFFFh
0x1800743a0  jz      loc_1800744E6
0x1800743a6  cmp     dword ptr [rdi+8], 0
0x1800743aa  mov     r14, [rsp+78h+var_58]
0x1800743af  jbe     short loc_18007440D
0x1800743b1  mov     r15, [rdi]
0x1800743b4  xor     esi, esi
0x1800743b6  xor     ebp, ebp
0x1800743b8  lea     rdx, ds:0[rbp*8]
0x1800743c0  mov     rcx, r14; struct tagDBPROPINFOSET *
0x1800743c3  add     rdx, rbp
0x1800743c6  lea     r8, [rsp+78h+var_58]; struct tagDBPROPINFO **
0x1800743cb  mov     edx, [r15+rdx*8]; unsigned int
0x1800743cf  call    ?FindProperty@@YAKPEAUtagDBPROPINFOSET@@KPEAPEAUtagDBPROPINFO@@@Z; FindProperty(tagDBPROPINFOSET *,ulong,tagDBPROPINFO * *)
0x1800743d4  cmp     eax, 0FFFFFFFFh
0x1800743d7  lea     ecx, [rsi+1]
0x1800743da  cmovnz  ecx, esi
0x1800743dd  inc     ebp
0x1800743df  mov     esi, ecx
0x1800743e1  cmp     ebp, [rdi+8]
0x1800743e4  jb      short loc_1800743B8
0x1800743e6  test    ecx, ecx
0x1800743e8  jz      short loc_18007440D
0x1800743ea  mov     eax, [r14+8]
0x1800743ee  add     eax, ecx
0x1800743f0  mov     rcx, [r14]; pv
0x1800743f3  lea     rdx, [rax+rax*2]
0x1800743f7  shl     rdx, 4; cb
0x1800743fb  call    cs:__imp_CoTaskMemRealloc
0x180074401  test    rax, rax
0x180074404  jz      loc_1800745B4
0x18007440a  mov     [r14], rax
0x18007440d  xor     esi, esi
0x18007440f  cmp     esi, [rdi+8]
0x180074412  jnb     loc_18007458D
0x180074418  mov     r15, [rdi]
0x18007441b  lea     rbp, [rsi+rsi*8]
0x18007441f  lea     r8, [rsp+78h+var_58]; struct tagDBPROPINFO **
0x180074424  mov     [rsp+78h+var_58], 0
0x18007442d  mov     rcx, r14; struct tagDBPROPINFOSET *
0x180074430  mov     edx, [r15+rbp*8]; unsigned int
0x180074434  call    ?FindProperty@@YAKPEAUtagDBPROPINFOSET@@KPEAPEAUtagDBPROPINFO@@@Z; FindProperty(tagDBPROPINFOSET *,ulong,tagDBPROPINFO * *)
0x180074439  cmp     eax, 0FFFFFFFFh
0x18007443c  jz      short loc_18007449F
0x18007443e  mov     rcx, [rsp+78h+var_58]
0x180074443  mov     eax, [rcx+0Ch]
0x180074446  test    eax, eax
0x180074448  jnz     short loc_18007447B
0x18007444a  mov     rdx, [rsp+78h+arg_30]; unsigned __int8 **
0x180074452  mov     r9, rcx; struct tagDBPROPINFO *
0x180074455  mov     rcx, [rsp+78h+arg_28]; unsigned __int16 **
0x18007445d  mov     r8, r13; struct _GUID *
0x180074460  call    ?HandleGetPropertyInfo@CDBProperties@@CAJPEAPEAGPEAPEAEAEBU_GUID@@PEAUtagDBPROPINFO@@@Z; CDBProperties::HandleGetPropertyInfo(ushort * *,uchar * *,_GUID const &,tagDBPROPINFO *)
0x180074465  mov     ebx, eax
0x180074467  test    eax, eax
0x180074469  js      loc_1800745F3
0x18007446f  mov     rax, [rsp+78h+arg_20]
0x180074477  inc     dword ptr [rax]
0x180074479  jmp     short loc_1800744DF
0x18007447b  bt      eax, 0Ah
0x18007447f  jb      short loc_1800744DF
0x180074481  cmp     edx, 0CCh
0x180074487  jz      short loc_180074496
0x180074489  cmp     edx, 7Fh
0x18007448c  jz      short loc_180074496
0x18007448e  cmp     edx, 86h
0x180074494  jnz     short loc_1800744DF
0x180074496  bts     eax, 0Ah
0x18007449a  mov     [rcx+0Ch], eax
0x18007449d  jmp     short loc_1800744DF
0x18007449f  mov     edx, [r14+8]
0x1800744a3  mov     r8, r13; struct _GUID *
0x1800744a6  mov     rcx, [rsp+78h+arg_28]; unsigned __int16 **
0x1800744ae  lea     eax, [rdx+1]
0x1800744b1  lea     r9, [rdx+rdx*2]
0x1800744b5  mov     rdx, [rsp+78h+arg_30]; unsigned __int8 **
0x1800744bd  shl     r9, 4
0x1800744c1  add     r9, [r14]; struct tagDBPROPINFO *
0x1800744c4  mov     [r14+8], eax
0x1800744c8  mov     eax, [r15+rbp*8]
0x1800744cc  mov     [r9+8], eax
0x1800744d0  call    ?HandleGetPropertyInfo@CDBProperties@@CAJPEAPEAGPEAPEAEAEBU_GUID@@PEAUtagDBPROPINFO@@@Z; CDBProperties::HandleGetPropertyInfo(ushort * *,uchar * *,_GUID const &,tagDBPROPINFO *)
0x1800744d5  mov     ebx, eax
0x1800744d7  test    eax, eax
0x1800744d9  js      loc_18007462D
0x1800744df  inc     esi
0x1800744e1  jmp     loc_18007440F
0x1800744e6  mov     edx, [rsi]
0x1800744e8  mov     rcx, [r14]; pv
0x1800744eb  inc     edx
0x1800744ed  shl     rdx, 5; cb
0x1800744f1  call    cs:__imp_CoTaskMemRealloc
0x1800744f7  mov     rbp, rax
0x1800744fa  test    rax, rax
0x1800744fd  jz      loc_1800746D2
0x180074503  mov     [r14], rax
0x180074506  mov     edx, [rsi]
0x180074508  mov     r14d, edx
0x18007450b  shl     r14, 5
0x18007450f  lea     ecx, [rdx+1]
0x180074512  mov     [rsi], ecx
0x180074514  movups  xmm0, xmmword ptr [r13+0]
0x180074519  movdqu  xmmword ptr [r14+rax+0Ch], xmm0
0x180074520  mov     eax, [rdi+8]
0x180074523  mov     [r14+rbp+8], eax
0x180074528  mov     eax, [rdi+8]
0x18007452b  lea     rcx, [rax+rax*2]
0x18007452f  shl     rcx, 4; cb
0x180074533  call    cs:__imp_CoTaskMemAlloc
0x180074539  mov     [r14+rbp], rax
0x18007453d  test    rax, rax
0x180074540  jz      loc_18007469E
0x180074546  xor     esi, esi
0x180074548  cmp     esi, [rdi+8]
0x18007454b  jnb     short loc_18007458D
0x18007454d  mov     rax, [rdi]
0x180074550  lea     rcx, [rsi+rsi*8]
0x180074554  mov     rdx, [rsp+78h+arg_30]; unsigned __int8 **
0x18007455c  lea     r9, [rsi+rsi*2]
0x180074560  shl     r9, 4
0x180074564  mov     r8, r13; struct _GUID *
0x180074567  add     r9, [r14+rbp]; struct tagDBPROPINFO *
0x18007456b  mov     ecx, [rax+rcx*8]
0x18007456e  mov     [r9+8], ecx
0x180074572  mov     rcx, [rsp+78h+arg_28]; unsigned __int16 **
0x18007457a  call    ?HandleGetPropertyInfo@CDBProperties@@CAJPEAPEAGPEAPEAEAEBU_GUID@@PEAUtagDBPROPINFO@@@Z; CDBProperties::HandleGetPropertyInfo(ushort * *,uchar * *,_GUID const &,tagDBPROPINFO *)
0x18007457f  mov     ebx, eax
0x180074581  test    eax, eax
0x180074583  js      loc_180074667
0x180074589  inc     esi
0x18007458b  jmp     short loc_180074548
0x18007458d  mov     rsi, [rsp+78h+arg_10]
0x180074595  inc     r12d
0x180074598  mov     r14, [rsp+78h+arg_18]
0x1800745a0  mov     eax, [rsp+78h+arg_0]
0x1800745a7  mov     rdx, [rsp+78h+arg_8]
0x1800745af  jmp     loc_18007436B
0x1800745b4  mov     eax, cs:_bidGblFlags
0x1800745ba  mov     ebx, 8007000Eh
0x1800745bf  test    al, 2
0x1800745c1  jz      loc_18007472C
0x1800745c7  mov     r8d, 6Bh ; 'k'; unsigned int
0x1800745cd  lea     rdx, aCdbpropertiesA_0; "<CDBProperties::AddProperties|OLEDB|ERR"...
0x1800745d4  mov     ecx, ebx; int
0x1800745d6  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800745db  mov     eax, cs:_bidGblFlags
0x1800745e1  test    al, 2
0x1800745e3  jz      loc_18007472C
0x1800745e9  mov     edx, 1AC09h
0x1800745ee  jmp     loc_180074714
0x1800745f3  mov     eax, cs:_bidGblFlags
0x1800745f9  test    al, 2
0x1800745fb  jz      loc_18007472C
0x180074601  mov     r8d, 7Ah ; 'z'; unsigned int
0x180074607  lea     rdx, aCdbpropertiesA_0; "<CDBProperties::AddProperties|OLEDB|ERR"...
0x18007460e  mov     ecx, ebx; int
0x180074610  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180074615  mov     eax, cs:_bidGblFlags
0x18007461b  test    al, 2
0x18007461d  jz      loc_18007472C
0x180074623  mov     edx, 1E809h
0x180074628  jmp     loc_180074714
0x18007462d  mov     eax, cs:_bidGblFlags
0x180074633  test    al, 2
0x180074635  jz      loc_18007472C
0x18007463b  mov     r8d, 8Fh; unsigned int
0x180074641  lea     rdx, aCdbpropertiesA_0; "<CDBProperties::AddProperties|OLEDB|ERR"...
0x180074648  mov     ecx, ebx; int
0x18007464a  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007464f  mov     eax, cs:_bidGblFlags
0x180074655  test    al, 2
0x180074657  jz      loc_18007472C
0x18007465d  mov     edx, 23C09h
0x180074662  jmp     loc_180074714
0x180074667  mov     eax, cs:_bidGblFlags
0x18007466d  test    al, 2
0x18007466f  jz      loc_18007472C
0x180074675  mov     r8d, 0AFh; unsigned int
0x18007467b  lea     rdx, aCdbpropertiesA_0; "<CDBProperties::AddProperties|OLEDB|ERR"...
0x180074682  mov     ecx, ebx; int
0x180074684  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180074689  mov     eax, cs:_bidGblFlags
0x18007468f  test    al, 2
0x180074691  jz      loc_18007472C
0x180074697  mov     edx, 2BC09h
0x18007469c  jmp     short loc_180074714
0x18007469e  mov     eax, cs:_bidGblFlags
0x1800746a4  mov     ebx, 8007000Eh
0x1800746a9  test    al, 2
0x1800746ab  jz      short loc_18007472C
0x1800746ad  mov     r8d, 0A6h; unsigned int
0x1800746b3  lea     rdx, aCdbpropertiesA_0; "<CDBProperties::AddProperties|OLEDB|ERR"...
0x1800746ba  mov     ecx, ebx; int
0x1800746bc  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800746c1  mov     eax, cs:_bidGblFlags
0x1800746c7  test    al, 2
0x1800746c9  jz      short loc_18007472C
0x1800746cb  mov     edx, 29809h
0x1800746d0  jmp     short loc_180074714
0x1800746d2  mov     eax, cs:_bidGblFlags
0x1800746d8  mov     ebx, 8007000Eh
0x1800746dd  test    al, 2
0x1800746df  jz      short loc_18007472C
0x1800746e1  mov     r8d, 9Ch; unsigned int
0x1800746e7  lea     rdx, aCdbpropertiesA_0; "<CDBProperties::AddProperties|OLEDB|ERR"...
0x1800746ee  mov     ecx, ebx; int
0x1800746f0  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800746f5  mov     eax, cs:_bidGblFlags
0x1800746fb  test    al, 2
0x1800746fd  jz      short loc_18007472C
0x1800746ff  mov     edx, 27009h
0x180074704  jmp     short loc_180074714
0x180074706  test    byte ptr cs:_bidGblFlags, 2
0x18007470d  jz      short loc_18007472C
0x18007470f  mov     edx, 2D009h
0x180074714  mov     rcx, cs:off_1800C84E0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18007471b  lea     r8, aCdbpropertiesA; "<CDBProperties::AddProperties|Trace|HR>"...
0x180074722  mov     r9d, ebx
0x180074725  call    _bidTraceHR
0x18007472a  mov     ebx, eax
0x18007472c  mov     eax, ebx
0x18007472e  add     rsp, 38h
0x180074732  pop     r15
0x180074734  pop     r14
0x180074736  pop     r13
0x180074738  pop     r12
0x18007473a  pop     rdi
0x18007473b  pop     rsi
0x18007473c  pop     rbp
0x18007473d  pop     rbx
0x18007473e  retn
```
