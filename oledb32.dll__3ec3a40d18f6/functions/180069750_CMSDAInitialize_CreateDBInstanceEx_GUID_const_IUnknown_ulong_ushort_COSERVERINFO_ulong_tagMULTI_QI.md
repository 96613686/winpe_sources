# CMSDAInitialize::CreateDBInstanceEx(_GUID const &,IUnknown *,ulong,ushort *,_COSERVERINFO *,ulong,tagMULTI_QI *)

- ea: `0x180069750`
- end: `0x180069c9b`
- name: `?CreateDBInstanceEx@CMSDAInitialize@@UEAAJAEBU_GUID@@PEAUIUnknown@@KPEAGPEAU_COSERVERINFO@@KPEAUtagMULTI_QI@@@Z`
- size: `1355`
- prototype: `__int64 __fastcall(CMSDAInitialize *__hidden this, const struct _GUID *, struct IUnknown *, unsigned int, unsigned __int16 *, struct _COSERVERINFO *, unsigned int, struct tagMULTI_QI *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180013870`
- `0x180029560`
- `0x180029c30`
- `0x18003c270`
- `0x180061814`
- `0x180069750`
- `0x180069d9c`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18006986c`
- `msvcrt!_wcsicmp` at `0x18006986c`
- `KERNEL32!GetComputerNameW` at `0x180069845`
- `KERNEL32!GetComputerNameW` at `0x180069845`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800697f1`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800697f1`

## string_xrefs

- `0x180069894`: `<CMSDAInitialize::CreateDBInstanceEx|OLEDB|ERR> `
- `0x1800698ee`: `<CMSDAInitialize::CreateDBInstanceEx|OLEDB|ERR> `
- `0x180069a81`: `<CMSDAInitialize::CreateDBInstanceEx|OLEDB|ERR> `
- `0x180069ac3`: `<CMSDAInitialize::CreateDBInstanceEx|OLEDB|ERR> `
- `0x180069b33`: `<CMSDAInitialize::CreateDBInstanceEx|OLEDB|ERR> `
- `0x180069b7a`: `<CMSDAInitialize::CreateDBInstanceEx|OLEDB|ERR> `
- `0x180069b59`: `<CMSDAInitialize::CreateDBInstanceEx|Trace|HR> `
- `0x180069c63`: `<CMSDAInitialize::CreateDBInstanceEx|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CMSDAInitialize::CreateDBInstanceEx(
        CMSDAInitialize *this,
        const struct _GUID *a2,
        struct IUnknown *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        struct _COSERVERINFO *a6,
        unsigned int a7,
        struct tagMULTI_QI *a8)
{
  unsigned int BidID; // eax
  LPWSTR pwszName; // rax
  WCHAR v14; // ax
  int v15; // ebx
  __int64 v16; // rdx
  COAUTHINFO *pAuthInfo; // rax
  __int64 v18; // rax
  int v19; // eax
  const IID *pIID; // rdx
  IUnknown **p_pItf; // r8
  __int64 v22; // r9
  char v23; // r15
  __int64 v24; // rsi
  HRESULT v25; // eax
  __int64 v26; // rax
  IUnknown *pItf; // rcx
  __int64 v28; // rcx
  HRESULT v29; // eax
  __int64 v30; // xmm1_8
  GUID *v32; // [rsp+28h] [rbp-A9h]
  unsigned __int16 *v33; // [rsp+30h] [rbp-A1h]
  char v34; // [rsp+50h] [rbp-81h]
  __int64 v35; // [rsp+58h] [rbp-79h] BYREF
  __int64 v36; // [rsp+60h] [rbp-71h] BYREF
  DWORD nSize; // [rsp+68h] [rbp-69h] BYREF
  struct IUnknown *v38; // [rsp+70h] [rbp-61h]
  __int128 v39; // [rsp+80h] [rbp-51h] BYREF
  __int64 v40; // [rsp+90h] [rbp-41h]
  WCHAR Buffer[16]; // [rsp+A0h] [rbp-31h] BYREF

  v38 = a3;
  v35 = -1;
  if ( (bidGblFlags & 4) != 0 && off_1800C95D0[0] )
  {
    BidID = CMSDAInitialize::GetBidID(this);
    v33 = a5;
    bidScopeEnterW(&v35, off_1800C95D0[0], BidID, a2, (_DWORD)a3, a4);
  }
  SetErrorInfo(0, 0);
  if ( !a7 || !a8 )
  {
    v15 = -2147024809;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_68;
    OLEDBTraceErr(-2147024809, L"<CMSDAInitialize::CreateDBInstanceEx|OLEDB|ERR> ", 0x178u);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_68;
    v16 = 385033;
LABEL_64:
    v15 = bidTraceHR(off_1800C8468[0], v16, L"<CMSDAInitialize::CreateDBInstanceEx|Trace|HR> ", 2147942487LL);
    goto LABEL_65;
  }
  if ( a6 )
  {
    pwszName = a6->pwszName;
    if ( !pwszName || !*pwszName )
    {
      if ( (bidGblFlags & 2) == 0 )
      {
        v15 = -2147024809;
        goto LABEL_65;
      }
      v16 = 411657;
      goto LABEL_64;
    }
    if ( a4 == 1 )
    {
      nSize = 16;
      if ( GetComputerNameW(Buffer, &nSize) )
      {
        v14 = Buffer[0];
      }
      else
      {
        v14 = 0;
        Buffer[0] = 0;
      }
      if ( !v14 || _wcsicmp(a6->pwszName, Buffer) )
      {
        v15 = -2147024809;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_65;
        OLEDBTraceErr(-2147024809, L"<CMSDAInitialize::CreateDBInstanceEx|OLEDB|ERR> ", 0x18Au);
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_65;
        v16 = 403465;
        goto LABEL_64;
      }
    }
    pAuthInfo = a6->pAuthInfo;
    if ( pAuthInfo )
    {
      if ( a4 == 1 && (pAuthInfo->pwszServerPrincName || pAuthInfo->pAuthIdentityData) )
      {
        v15 = -2147024809;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_65;
        OLEDBTraceErr(-2147024809, L"<CMSDAInitialize::CreateDBInstanceEx|OLEDB|ERR> ", 0x19Eu);
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_65;
        v16 = 423945;
        goto LABEL_64;
      }
    }
  }
  v18 = *(_QWORD *)this;
  v33 = (unsigned __int16 *)&v36;
  v36 = 0;
  v32 = &IID_IUnknown;
  v19 = (*(__int64 (__fastcall **)(CMSDAInitialize *, const struct _GUID *, struct IUnknown *, _QWORD, unsigned __int16 *))(v18 + 40))(
          this,
          a2,
          a3,
          a4,
          a5);
  v22 = 0;
  v15 = v19;
  if ( v19 < 0 )
  {
    p_pItf = (IUnknown **)a7;
    LODWORD(pIID) = 0;
    do
    {
      v28 = (unsigned int)pIID;
      v29 = v15;
      if ( v15 == -2147217886 )
        v29 = -2147217886;
      a8[(unsigned int)pIID].pItf = 0;
      pIID = (const IID *)(unsigned int)((_DWORD)pIID + 1);
      a8[v28].hr = v29;
    }
    while ( (unsigned int)pIID < a7 );
    goto LABEL_59;
  }
  v34 = 0;
  v23 = 0;
  LODWORD(v24) = 0;
  while ( (unsigned int)v24 < a7 )
  {
    pIID = a8[(unsigned int)v24].pIID;
    if ( !pIID )
    {
      while ( (_DWORD)v24 )
      {
        v24 = (unsigned int)(v24 - 1);
        pItf = a8[v24].pItf;
        if ( pItf )
        {
          ((void (__fastcall *)(IUnknown *))pItf->lpVtbl->Release)(pItf);
          v22 = 0;
          a8[v24].pItf = 0;
        }
        a8[v24].hr = -2147467262;
      }
LABEL_46:
      if ( v15 != -2147217886 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v15, L"<CMSDAInitialize::CreateDBInstanceEx|OLEDB|ERR> ", 0x20Eu);
        v15 = -2147467262;
      }
      goto LABEL_59;
    }
    if ( v38 )
    {
      v26 = *(_QWORD *)&pIID->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
      if ( *(_QWORD *)&pIID->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
        v26 = *(_QWORD *)pIID->Data4 - *(_QWORD *)IID_IUnknown.Data4;
      p_pItf = &a8[(unsigned int)v24].pItf;
      if ( !v26 )
      {
        a8[(unsigned int)v24].hr = (**(__int64 (__fastcall ***)(__int64, const IID *, IUnknown **, _QWORD))v36)(
                                     v36,
                                     pIID,
                                     p_pItf,
                                     0);
        v22 = 0;
        v34 = 1;
        goto LABEL_41;
      }
      *p_pItf = 0;
      v15 = -2147217886;
      a8[(unsigned int)v24].hr = -2147217886;
    }
    else
    {
      v25 = (**(__int64 (__fastcall ***)(__int64, const IID *, IUnknown **, _QWORD))v36)(
              v36,
              pIID,
              &a8[(unsigned int)v24].pItf,
              0);
      v22 = 0;
      a8[(unsigned int)v24].hr = v25;
      if ( v25 >= 0 )
      {
        v34 = 1;
        goto LABEL_41;
      }
    }
    v23 = 1;
LABEL_41:
    LODWORD(v24) = v24 + 1;
  }
  if ( v34 )
  {
    v15 = v23 != 0 ? 0x80012 : 0;
    goto LABEL_59;
  }
  if ( v23 )
    goto LABEL_46;
  v15 = -2147024809;
  if ( (bidGblFlags & 2) != 0 )
    OLEDBTraceErr(-2147024809, L"<CMSDAInitialize::CreateDBInstanceEx|OLEDB|ERR> ", 0x205u);
LABEL_59:
  if ( v36 )
    (*(void (__fastcall **)(__int64, const IID *, IUnknown **, __int64))(*(_QWORD *)v36 + 16LL))(v36, pIID, p_pItf, v22);
LABEL_65:
  if ( v15 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(v15, L"<CMSDAInitialize::CreateDBInstanceEx|OLEDB|ERR> ", 0x22Eu);
LABEL_68:
    v15 = PostHResult(v15, &IID_IDataInitialize);
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( v15 < 0 )
    {
      if ( off_1800C9380[0] )
        bidTraceW(off_1800C8468[0], 575488, off_1800C9380[0], (unsigned int)v15, (_DWORD)a8, (_DWORD)v32, v33);
    }
    else if ( off_1800C9388[0] )
    {
      v30 = *(_QWORD *)&a8->hr;
      v39 = *(_OWORD *)&a8->pIID;
      v40 = v30;
      bidTraceW(off_1800C8468[0], 575488, off_1800C9388[0], (unsigned int)v15, a7, (unsigned int)&v39, v33);
    }
    if ( (bidGblFlags & 4) != 0 && v35 != -1 && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v35);
    if ( (bidGblFlags & 2) != 0 )
      return (unsigned int)bidTraceHR(
                             off_1800C8468[0],
                             576521,
                             L"<CMSDAInitialize::CreateDBInstanceEx|Trace|HR> ",
                             (unsigned int)v15);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180069750  push    rbp
0x180069752  push    rbx
0x180069753  push    rsi
0x180069754  push    rdi
0x180069755  push    r12
0x180069757  push    r13
0x180069759  push    r14
0x18006975b  push    r15
0x18006975d  lea     rbp, [rsp-7]
0x180069762  sub     rsp, 0D8h
0x180069769  mov     rax, cs:__security_cookie
0x180069770  xor     rax, rsp
0x180069773  mov     [rbp+3Fh+var_50], rax
0x180069777  test    byte ptr cs:_bidGblFlags, 4
0x18006977e  mov     edi, r9d
0x180069781  mov     r12, [rbp+3Fh+arg_20]
0x180069785  mov     r13, r8
0x180069788  mov     rbx, [rbp+3Fh+arg_28]
0x18006978c  mov     r15, rdx
0x18006978f  mov     r14, [rbp+3Fh+arg_38]
0x180069796  mov     rsi, rcx
0x180069799  mov     [rbp+3Fh+var_A0], r8
0x18006979d  mov     [rbp+3Fh+var_B8], 0FFFFFFFFFFFFFFFFh
0x1800697a5  jz      short loc_1800697ED
0x1800697a7  mov     rax, cs:off_1800C95D0; "<IDataInitialize::CreateDBInstanceEx|AP"...
0x1800697ae  test    rax, rax
0x1800697b1  jz      short loc_1800697ED
0x1800697b3  call    ?GetBidID@CMSDAInitialize@@QEAAHXZ; CMSDAInitialize::GetBidID(void)
0x1800697b8  mov     ecx, [rbp+3Fh+arg_30]
0x1800697bb  mov     r9, r15
0x1800697be  mov     rdx, cs:off_1800C95D0; "<IDataInitialize::CreateDBInstanceEx|AP"...
0x1800697c5  mov     r8d, eax
0x1800697c8  mov     [rsp+110h+var_C8], r14
0x1800697cd  mov     [rsp+110h+var_D0], ecx
0x1800697d1  lea     rcx, [rbp+3Fh+var_B8]
0x1800697d5  mov     [rsp+110h+var_D8], rbx
0x1800697da  mov     [rsp+110h+var_E0], r12
0x1800697df  mov     dword ptr [rsp+110h+var_E8], edi
0x1800697e3  mov     [rsp+110h+var_F0], r13
0x1800697e8  call    _bidScopeEnterW
0x1800697ed  xor     edx, edx; perrinfo
0x1800697ef  xor     ecx, ecx; dwReserved
0x1800697f1  call    cs:__imp_SetErrorInfo
0x1800697f7  xor     r9d, r9d
0x1800697fa  cmp     [rbp+3Fh+arg_30], r9d
0x1800697fe  jz      loc_180069B1C
0x180069804  test    r14, r14
0x180069807  jz      loc_180069B1C
0x18006980d  test    rbx, rbx
0x180069810  jz      loc_180069939
0x180069816  mov     rax, [rbx+8]
0x18006981a  test    rax, rax
0x18006981d  jz      loc_180069913
0x180069823  cmp     [rax], r9w
0x180069827  jz      loc_180069913
0x18006982d  cmp     edi, 1
0x180069830  jnz     loc_1800698B9
0x180069836  lea     rdx, [rbp+3Fh+nSize]; nSize
0x18006983a  mov     [rbp+3Fh+nSize], 10h
0x180069841  lea     rcx, [rbp+3Fh+Buffer]; lpBuffer
0x180069845  call    cs:__imp_GetComputerNameW
0x18006984b  xor     r9d, r9d
0x18006984e  test    eax, eax
0x180069850  jnz     short loc_18006985B
0x180069852  mov     eax, r9d
0x180069855  mov     [rbp+3Fh+Buffer], ax
0x180069859  jmp     short loc_18006985F
0x18006985b  movzx   eax, [rbp+3Fh+Buffer]
0x18006985f  test    ax, ax
0x180069862  jz      short loc_180069879
0x180069864  mov     rcx, [rbx+8]; String1
0x180069868  lea     rdx, [rbp+3Fh+Buffer]; String2
0x18006986c  call    cs:__imp__wcsicmp
0x180069872  xor     r9d, r9d
0x180069875  test    eax, eax
0x180069877  jz      short loc_1800698B9
0x180069879  mov     dil, 2
0x18006987c  mov     ebx, 80070057h
0x180069881  test    byte ptr cs:_bidGblFlags, dil
0x180069888  jz      loc_180069B67
0x18006988e  mov     r8d, 18Ah; unsigned int
0x180069894  lea     rdx, aCmsdainitializ_2; "<CMSDAInitialize::CreateDBInstanceEx|OL"...
0x18006989b  mov     ecx, ebx; int
0x18006989d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800698a2  test    byte ptr cs:_bidGblFlags, dil
0x1800698a9  jz      loc_180069B67
0x1800698af  mov     edx, 62809h
0x1800698b4  jmp     loc_180069B4F
0x1800698b9  mov     rax, [rbx+10h]
0x1800698bd  test    rax, rax
0x1800698c0  jz      short loc_180069939
0x1800698c2  cmp     edi, 1
0x1800698c5  jnz     short loc_180069939
0x1800698c7  cmp     [rax+8], r9
0x1800698cb  jnz     short loc_1800698D3
0x1800698cd  cmp     [rax+18h], r9
0x1800698d1  jz      short loc_180069939
0x1800698d3  mov     dil, 2
0x1800698d6  mov     ebx, 80070057h
0x1800698db  test    byte ptr cs:_bidGblFlags, dil
0x1800698e2  jz      loc_180069B67
0x1800698e8  mov     r8d, 19Eh; unsigned int
0x1800698ee  lea     rdx, aCmsdainitializ_2; "<CMSDAInitialize::CreateDBInstanceEx|OL"...
0x1800698f5  mov     ecx, ebx; int
0x1800698f7  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800698fc  test    byte ptr cs:_bidGblFlags, dil
0x180069903  jz      loc_180069B67
0x180069909  mov     edx, 67809h
0x18006990e  jmp     loc_180069B4F
0x180069913  mov     dil, 2
0x180069916  test    byte ptr cs:_bidGblFlags, dil
0x18006991d  jz      short loc_18006992F
0x18006991f  mov     r9d, 80070057h
0x180069925  mov     edx, 64809h
0x18006992a  jmp     loc_180069B52
0x18006992f  mov     ebx, 80070057h
0x180069934  jmp     loc_180069B67
0x180069939  mov     rax, [rsi]
0x18006993c  lea     rcx, [rbp+3Fh+var_B0]
0x180069940  mov     [rsp+110h+var_E0], rcx
0x180069945  mov     r8, r13
0x180069948  lea     rcx, IID_IUnknown
0x18006994f  mov     [rbp+3Fh+var_B0], r9
0x180069953  mov     [rsp+110h+var_E8], rcx
0x180069958  mov     r9d, edi
0x18006995b  mov     rax, [rax+28h]
0x18006995f  mov     rcx, rsi
0x180069962  mov     rdx, r15
0x180069965  mov     [rsp+110h+var_F0], r12
0x18006996a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006996f  xor     r9d, r9d
0x180069972  mov     ebx, eax
0x180069974  mov     dil, 2
0x180069977  test    eax, eax
0x180069979  js      loc_180069AD3
0x18006997f  mov     [rsp+110h+var_C0], r9b
0x180069984  mov     r15b, r9b
0x180069987  mov     esi, r9d
0x18006998a  mov     r12d, 80040E22h
0x180069990  cmp     esi, [rbp+3Fh+arg_30]
0x180069993  jnb     loc_180069A96
0x180069999  mov     eax, esi
0x18006999b  lea     r13, [rax+rax*2]
0x18006999f  mov     rdx, [r14+r13*8]
0x1800699a3  test    rdx, rdx
0x1800699a6  jz      loc_180069A65
0x1800699ac  cmp     [rbp+3Fh+var_A0], r9
0x1800699b0  jnz     short loc_1800699DC
0x1800699b2  mov     rcx, [rbp+3Fh+var_B0]
0x1800699b6  lea     r8, [r14+8]
0x1800699ba  lea     r8, [r8+r13*8]
0x1800699be  mov     rax, [rcx]
0x1800699c1  mov     rax, [rax]
0x1800699c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800699c9  xor     r9d, r9d
0x1800699cc  mov     [r14+r13*8+10h], eax
0x1800699d1  test    eax, eax
0x1800699d3  js      short loc_180069A2E
0x1800699d5  mov     [rsp+110h+var_C0], 1
0x1800699da  jmp     short loc_180069A31
0x1800699dc  mov     rax, [rdx]
0x1800699df  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1800699e6  jnz     short loc_1800699F3
0x1800699e8  mov     rax, [rdx+8]
0x1800699ec  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1800699f3  test    rax, rax
0x1800699f6  lea     r8, [r14+8]
0x1800699fa  lea     r8, [r8+r13*8]
0x1800699fe  setz    al
0x180069a01  test    al, al
0x180069a03  jz      short loc_180069A23
0x180069a05  mov     rcx, [rbp+3Fh+var_B0]
0x180069a09  mov     rax, [rcx]
0x180069a0c  mov     rax, [rax]
0x180069a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a14  mov     [r14+r13*8+10h], eax
0x180069a19  xor     r9d, r9d
0x180069a1c  mov     [rsp+110h+var_C0], 1
0x180069a21  jmp     short loc_180069A31
0x180069a23  mov     [r8], r9
0x180069a26  mov     ebx, r12d
0x180069a29  mov     [r14+r13*8+10h], r12d
0x180069a2e  mov     r15b, 1
0x180069a31  inc     esi
0x180069a33  jmp     loc_180069990
0x180069a38  dec     esi
0x180069a3a  lea     r15, [rsi+rsi*2]
0x180069a3e  mov     rcx, [r14+r15*8+8]
0x180069a43  test    rcx, rcx
0x180069a46  jz      short loc_180069A5C
0x180069a48  mov     rax, [rcx]
0x180069a4b  mov     rax, [rax+10h]
0x180069a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a54  xor     r9d, r9d
0x180069a57  mov     [r14+r15*8+8], r9
0x180069a5c  mov     dword ptr [r14+r15*8+10h], 80004002h
0x180069a65  test    esi, esi
0x180069a67  jnz     short loc_180069A38
0x180069a69  cmp     ebx, r12d
0x180069a6c  jz      loc_180069B05
0x180069a72  test    byte ptr cs:_bidGblFlags, dil
0x180069a79  jz      short loc_180069A8F
0x180069a7b  mov     r8d, 20Eh; unsigned int
0x180069a81  lea     rdx, aCmsdainitializ_2; "<CMSDAInitialize::CreateDBInstanceEx|OL"...
0x180069a88  mov     ecx, ebx; int
0x180069a8a  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180069a8f  mov     ebx, 80004002h
0x180069a94  jmp     short loc_180069B05
0x180069a96  cmp     [rsp+110h+var_C0], r9b
0x180069a9b  jz      short loc_180069AAA
0x180069a9d  neg     r15b
0x180069aa0  sbb     ebx, ebx
0x180069aa2  and     ebx, 80012h
0x180069aa8  jmp     short loc_180069B05
0x180069aaa  test    r15b, r15b
0x180069aad  jnz     short loc_180069A69
0x180069aaf  test    byte ptr cs:_bidGblFlags, dil
0x180069ab6  mov     ebx, 80070057h
0x180069abb  jz      short loc_180069B05
0x180069abd  mov     r8d, 205h; unsigned int
0x180069ac3  lea     rdx, aCmsdainitializ_2; "<CMSDAInitialize::CreateDBInstanceEx|OL"...
0x180069aca  mov     ecx, ebx; int
0x180069acc  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180069ad1  jmp     short loc_180069B05
0x180069ad3  mov     r8d, [rbp+3Fh+arg_30]
0x180069ad7  mov     edx, r9d
0x180069ada  test    r8d, r8d
0x180069add  jz      short loc_180069B05
0x180069adf  mov     r12d, 80040E22h
0x180069ae5  mov     eax, edx
0x180069ae7  cmp     ebx, r12d
0x180069aea  lea     rcx, [rax+rax*2]
0x180069aee  mov     eax, ebx
0x180069af0  cmovz   eax, r12d
0x180069af4  mov     [r14+rcx*8+8], r9
0x180069af9  inc     edx
0x180069afb  mov     [r14+rcx*8+10h], eax
0x180069b00  cmp     edx, r8d
0x180069b03  jb      short loc_180069AE5
0x180069b05  mov     rcx, [rbp+3Fh+var_B0]
0x180069b09  test    rcx, rcx
0x180069b0c  jz      short loc_180069B67
0x180069b0e  mov     rax, [rcx]
0x180069b11  mov     rax, [rax+10h]
0x180069b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069b1a  jmp     short loc_180069B67
0x180069b1c  mov     dil, 2
0x180069b1f  mov     ebx, 80070057h
0x180069b24  test    byte ptr cs:_bidGblFlags, dil
0x180069b2b  jz      short loc_180069B88
0x180069b2d  mov     r8d, 178h; unsigned int
0x180069b33  lea     rdx, aCmsdainitializ_2; "<CMSDAInitialize::CreateDBInstanceEx|OL"...
0x180069b3a  mov     ecx, ebx; int
0x180069b3c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180069b41  test    byte ptr cs:_bidGblFlags, dil
0x180069b48  jz      short loc_180069B88
0x180069b4a  mov     edx, 5E009h
0x180069b4f  mov     r9d, ebx
0x180069b52  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180069b59  lea     r8, aCmsdainitializ_10; "<CMSDAInitialize::CreateDBInstanceEx|Tr"...
0x180069b60  call    _bidTraceHR
0x180069b65  mov     ebx, eax
0x180069b67  test    ebx, ebx
0x180069b69  jns     short loc_180069B98
0x180069b6b  test    byte ptr cs:_bidGblFlags, dil
0x180069b72  jz      short loc_180069B88
0x180069b74  mov     r8d, 22Eh; unsigned int
0x180069b7a  lea     rdx, aCmsdainitializ_2; "<CMSDAInitialize::CreateDBInstanceEx|OL"...
0x180069b81  mov     ecx, ebx; int
0x180069b83  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180069b88  lea     rdx, IID_IDataInitialize; struct _GUID *
0x180069b8f  mov     ecx, ebx; int
0x180069b91  call    ?PostHResult@@YAJJPEBU_GUID@@@Z; PostHResult(long,_GUID const *)
0x180069b96  mov     ebx, eax
0x180069b98  test    byte ptr cs:_bidGblFlags, dil
0x180069b9f  jz      loc_180069C79
0x180069ba5  test    ebx, ebx
0x180069ba7  js      short loc_180069BF5
0x180069ba9  mov     rax, cs:off_1800C9388; "<IDataInitialize::CreateDBInstanceEx|AP"...
0x180069bb0  test    rax, rax
0x180069bb3  jz      short loc_180069C21
0x180069bb5  movups  xmm0, xmmword ptr [r14]
0x180069bb9  lea     rax, [rbp+3Fh+var_90]
0x180069bbd  mov     r8, cs:off_1800C9388; "<IDataInitialize::CreateDBInstanceEx|AP"...
0x180069bc4  movsd   xmm1, qword ptr [r14+10h]
0x180069bca  mov     r9d, ebx
0x180069bcd  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180069bd4  mov     edx, 8C800h
0x180069bd9  mov     [rsp+110h+var_E8], rax
0x180069bde  mov     eax, [rbp+3Fh+arg_30]
0x180069be1  movaps  [rbp+3Fh+var_90], xmm0
0x180069be5  mov     dword ptr [rsp+110h+var_F0], eax
0x180069be9  movsd   [rbp+3Fh+var_80], xmm1
0x180069bee  call    _bidTraceW
0x180069bf3  jmp     short loc_180069C21
0x180069bf5  mov     rax, cs:off_1800C9380; "<IDataInitialize::CreateDBInstanceEx|AP"...
0x180069bfc  test    rax, rax
0x180069bff  jz      short loc_180069C21
0x180069c01  mov     r8, cs:off_1800C9380; "<IDataInitialize::CreateDBInstanceEx|AP"...
0x180069c08  mov     r9d, ebx
  ... truncated ...
```
