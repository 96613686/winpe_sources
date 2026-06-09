# CRasDiagHelper::IsRASLowOnHealth(ushort * *)

- ea: `0x180007828`
- end: `0x180007b3a`
- name: `?IsRASLowOnHealth@CRasDiagHelper@@AEAAHPEAPEAG@Z`
- size: `786`
- prototype: `__int64 __fastcall(CRasDiagHelper *this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180007b70`

## callees

- `0x180007828`
- `0x18000b864`
- `0x18000c9c4`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180007a59`
- `KERNEL32!CompareStringOrdinal` at `0x180007a82`
- `KERNEL32!CompareStringOrdinal` at `0x180007aa9`
- `KERNEL32!CompareStringOrdinal` at `0x180007a59`
- `KERNEL32!CompareStringOrdinal` at `0x180007a82`
- `KERNEL32!CompareStringOrdinal` at `0x180007aa9`
- `KERNEL32!SetLastError` at `0x180007875`
- `KERNEL32!SetLastError` at `0x180007988`
- `KERNEL32!SetLastError` at `0x180007875`
- `KERNEL32!SetLastError` at `0x180007988`
- `RASAPI32!RasEnumConnectionsW` at `0x180007898`
- `RASAPI32!RasEnumConnectionsW` at `0x1800078e2`
- `RASAPI32!RasEnumConnectionsW` at `0x180007898`
- `RASAPI32!RasEnumConnectionsW` at `0x1800078e2`
- `RASAPI32!RasEnumDevicesW` at `0x1800079ab`
- `RASAPI32!RasEnumDevicesW` at `0x1800079ef`
- `RASAPI32!RasEnumDevicesW` at `0x1800079ab`
- `RASAPI32!RasEnumDevicesW` at `0x1800079ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000785c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800078c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000796f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800079ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000785c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800078c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000796f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800079ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007956`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800079bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800078b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007956`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800079bf`

## string_xrefs

- `0x180007b28`: `RAS device was detected but no active connection. We will show the wizard to dial/configure a RAS connection.`

## pseudocode

```c
__int64 __fastcall CRasDiagHelper::IsRASLowOnHealth(CRasDiagHelper *this, unsigned __int16 **a2)
{
  unsigned int v2; // esi
  struct tagRASCONNW *v5; // rbx
  signed int v6; // eax
  struct tagRASCONNW *v7; // rax
  bool v8; // sf
  const wchar_t *v9; // rax
  struct tagRASDEVINFOW *v10; // rdi
  signed int v11; // eax
  struct tagRASDEVINFOW *v12; // rax
  DWORD v13; // r14d
  bool v14; // sf
  const WCHAR *szDeviceType; // r12
  signed int v17; // [rsp+28h] [rbp-8h]
  DWORD v18; // [rsp+78h] [rbp+48h] BYREF
  DWORD v19; // [rsp+80h] [rbp+50h] BYREF

  v2 = 0;
  if ( a2 )
    *a2 = 0;
  v19 = 0;
  v18 = 1388;
  v5 = (struct tagRASCONNW *)CoTaskMemAlloc(0x56Cu);
  if ( !v5 )
    goto LABEL_4;
  v5->dwSize = v18;
  v6 = RasEnumConnectionsW(v5, &v18, &v19);
  if ( v6 == 603 )
  {
    CoTaskMemFree(v5);
    v7 = (struct tagRASCONNW *)CoTaskMemAlloc(v18);
    v5 = v7;
    if ( !v7 )
    {
LABEL_4:
      SetLastError(8u);
      v6 = -2147024882;
LABEL_12:
      v17 = v6;
      v9 = L"IsRASLowOnHealth::EnumRasConnections failed with error: 0x%x.";
LABEL_13:
      CRasLogger::Log((char *)this + 1208, 2, 1, L"CRasDiagHelper", v9, v17);
      return v2;
    }
    v7->dwSize = 1388;
    v6 = RasEnumConnectionsW(v7, &v18, &v19);
  }
  v8 = v6 < 0;
  if ( v6 )
  {
    if ( v6 > 0 )
    {
      v6 = (unsigned __int16)v6 | 0x80070000;
      v8 = v6 < 0;
    }
    if ( v8 )
      goto LABEL_12;
  }
  else
  {
    if ( v19 )
    {
      CRasLogger::Log(
        (char *)this + 1208,
        2,
        1,
        L"CRasDiagHelper",
        L"IsRASLowOnHealth::We have an active RAS connection. So network should be up. Returning.");
      return v2;
    }
    if ( v5 )
      CoTaskMemFree(v5);
  }
  v19 = 0;
  v18 = 296;
  v10 = (struct tagRASDEVINFOW *)CoTaskMemAlloc(0x128u);
  if ( !v10 )
    goto LABEL_19;
  v10->dwSize = v18;
  v11 = RasEnumDevicesW(v10, &v18, &v19);
  if ( v11 == 603 )
  {
    CoTaskMemFree(v10);
    v12 = (struct tagRASDEVINFOW *)CoTaskMemAlloc(v18);
    v10 = v12;
    if ( !v12 )
    {
LABEL_19:
      SetLastError(8u);
      v11 = -2147024882;
LABEL_27:
      v17 = v11;
      v9 = L"IsRASLowOnHealth::EnumRasDevices failed with error: 0x%x.";
      goto LABEL_13;
    }
    v12->dwSize = 296;
    v11 = RasEnumDevicesW(v12, &v18, &v19);
  }
  if ( v11 )
  {
    v10 = 0;
    v13 = 0;
    v14 = v11 < 0;
    if ( v11 > 0 )
    {
      v11 = (unsigned __int16)v11 | 0x80070000;
      v14 = v11 < 0;
    }
    if ( v14 )
      goto LABEL_27;
  }
  else
  {
    v13 = v19;
  }
  if ( v13 )
  {
    while ( 1 )
    {
      szDeviceType = v10[v2].szDeviceType;
      if ( CompareStringOrdinal(szDeviceType, -1, L"modem", -1, 1) == 2
        || CompareStringOrdinal(szDeviceType, -1, L"isdn", -1, 1) == 2
        || CompareStringOrdinal(szDeviceType, -1, L"PPPoE", -1, 1) == 2 )
      {
        break;
      }
      if ( ++v2 >= v13 )
        goto LABEL_34;
    }
    if ( a2 )
      LoadStringWithAlloc(0x3EAu, a2, 0x100u);
    v2 = 1;
    *(struct _GUID *)((char *)this + 1192) = ID_RAS_LOWH_REPAIR_NO_INTERNET_CONNECTIVITY;
    CRasLogger::Log(
      (char *)this + 1208,
      2,
      1,
      L"CRasDiagHelper",
      L"RAS device was detected but no active connection. We will show the wizard to dial/configure a RAS connection.");
  }
  else
  {
LABEL_34:
    v2 = 0;
    CRasLogger::Log((char *)this + 1208, 2, 1, L"CRasDiagHelper", L"There were no RAS modems found. Bailing out...");
  }
  return v2;
}

```

## disassembly

```asm
0x180007828  mov     [rsp-38h+arg_0], rbx
0x18000782d  push    rbp
0x18000782e  push    rsi
0x18000782f  push    rdi
0x180007830  push    r12
0x180007832  push    r13
0x180007834  push    r14
0x180007836  push    r15
0x180007838  mov     rbp, rsp
0x18000783b  sub     rsp, 30h
0x18000783f  xor     esi, esi
0x180007841  mov     r15, rdx
0x180007844  mov     r13, rcx
0x180007847  test    rdx, rdx
0x18000784a  jz      short loc_18000784F
0x18000784c  mov     [rdx], rsi
0x18000784f  mov     edi, 56Ch
0x180007854  mov     [rbp+arg_10], esi
0x180007857  mov     ecx, edi; cb
0x180007859  mov     [rbp+arg_8], edi
0x18000785c  call    cs:__imp_CoTaskMemAlloc
0x180007863  nop     dword ptr [rax+rax+00h]
0x180007868  mov     rbx, rax
0x18000786b  test    rax, rax
0x18000786e  jnz     short loc_180007888
0x180007870  mov     ecx, 8; dwErrCode
0x180007875  call    cs:__imp_SetLastError
0x18000787c  nop     dword ptr [rax+rax+00h]
0x180007881  mov     eax, 8007000Eh
0x180007886  jmp     short loc_180007904
0x180007888  mov     eax, [rbp+arg_8]
0x18000788b  lea     r8, [rbp+arg_10]; LPDWORD
0x18000788f  lea     rdx, [rbp+arg_8]; LPDWORD
0x180007893  mov     [rbx], eax
0x180007895  mov     rcx, rbx; struct tagRASCONNW *
0x180007898  call    cs:__imp_RasEnumConnectionsW
0x18000789f  nop     dword ptr [rax+rax+00h]
0x1800078a4  mov     r14d, 25Bh
0x1800078aa  cmp     eax, r14d
0x1800078ad  jnz     short loc_1800078EE
0x1800078af  mov     rcx, rbx; pv
0x1800078b2  call    cs:__imp_CoTaskMemFree
0x1800078b9  nop     dword ptr [rax+rax+00h]
0x1800078be  mov     ecx, [rbp+arg_8]; cb
0x1800078c1  call    cs:__imp_CoTaskMemAlloc
0x1800078c8  nop     dword ptr [rax+rax+00h]
0x1800078cd  mov     rbx, rax
0x1800078d0  test    rax, rax
0x1800078d3  jz      short loc_180007870
0x1800078d5  lea     r8, [rbp+arg_10]; LPDWORD
0x1800078d9  mov     [rax], edi
0x1800078db  lea     rdx, [rbp+arg_8]; LPDWORD
0x1800078df  mov     rcx, rax; struct tagRASCONNW *
0x1800078e2  call    cs:__imp_RasEnumConnectionsW
0x1800078e9  nop     dword ptr [rax+rax+00h]
0x1800078ee  mov     r12d, 80070000h
0x1800078f4  test    eax, eax
0x1800078f6  jz      short loc_180007938
0x1800078f8  jle     short loc_180007902
0x1800078fa  movzx   eax, ax
0x1800078fd  or      eax, r12d
0x180007900  test    eax, eax
0x180007902  jns     short loc_180007962
0x180007904  mov     [rsp+30h+var_8], eax
0x180007908  lea     rax, aIsraslowonheal_0; "IsRASLowOnHealth::EnumRasConnections fa"...
0x18000790f  mov     ebx, 1
0x180007914  mov     qword ptr [rsp+30h+bIgnoreCase], rax
0x180007919  lea     rcx, [r13+4B8h]
0x180007920  movsx   r8d, bx
0x180007924  lea     r9, aCrasdiaghelper; "CRasDiagHelper"
0x18000792b  lea     edx, [rbx+1]
0x18000792e  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x180007933  jmp     loc_180007AEF
0x180007938  cmp     [rbp+arg_10], esi
0x18000793b  jz      short loc_18000794E
0x18000793d  mov     ebx, 1
0x180007942  lea     rax, aIsraslowonheal; "IsRASLowOnHealth::We have an active RAS"...
0x180007949  jmp     loc_180007ACE
0x18000794e  test    rbx, rbx
0x180007951  jz      short loc_180007962
0x180007953  mov     rcx, rbx; pv
0x180007956  call    cs:__imp_CoTaskMemFree
0x18000795d  nop     dword ptr [rax+rax+00h]
0x180007962  mov     ebx, 128h
0x180007967  mov     [rbp+arg_10], esi
0x18000796a  mov     ecx, ebx; cb
0x18000796c  mov     [rbp+arg_8], ebx
0x18000796f  call    cs:__imp_CoTaskMemAlloc
0x180007976  nop     dword ptr [rax+rax+00h]
0x18000797b  mov     rdi, rax
0x18000797e  test    rax, rax
0x180007981  jnz     short loc_18000799B
0x180007983  mov     ecx, 8; dwErrCode
0x180007988  call    cs:__imp_SetLastError
0x18000798f  nop     dword ptr [rax+rax+00h]
0x180007994  mov     eax, 8007000Eh
0x180007999  jmp     short loc_180007A12
0x18000799b  mov     eax, [rbp+arg_8]
0x18000799e  lea     r8, [rbp+arg_10]; LPDWORD
0x1800079a2  lea     rdx, [rbp+arg_8]; LPDWORD
0x1800079a6  mov     [rdi], eax
0x1800079a8  mov     rcx, rdi; struct tagRASDEVINFOW *
0x1800079ab  call    cs:__imp_RasEnumDevicesW
0x1800079b2  nop     dword ptr [rax+rax+00h]
0x1800079b7  cmp     eax, r14d
0x1800079ba  jnz     short loc_1800079FB
0x1800079bc  mov     rcx, rdi; pv
0x1800079bf  call    cs:__imp_CoTaskMemFree
0x1800079c6  nop     dword ptr [rax+rax+00h]
0x1800079cb  mov     ecx, [rbp+arg_8]; cb
0x1800079ce  call    cs:__imp_CoTaskMemAlloc
0x1800079d5  nop     dword ptr [rax+rax+00h]
0x1800079da  mov     rdi, rax
0x1800079dd  test    rax, rax
0x1800079e0  jz      short loc_180007983
0x1800079e2  lea     r8, [rbp+arg_10]; LPDWORD
0x1800079e6  mov     [rax], ebx
0x1800079e8  lea     rdx, [rbp+arg_8]; LPDWORD
0x1800079ec  mov     rcx, rax; struct tagRASDEVINFOW *
0x1800079ef  call    cs:__imp_RasEnumDevicesW
0x1800079f6  nop     dword ptr [rax+rax+00h]
0x1800079fb  test    eax, eax
0x1800079fd  jz      short loc_180007A22
0x1800079ff  xor     edi, edi
0x180007a01  xor     r14d, r14d
0x180007a04  test    eax, eax
0x180007a06  jle     short loc_180007A10
0x180007a08  movzx   eax, ax
0x180007a0b  or      eax, r12d
0x180007a0e  test    eax, eax
0x180007a10  jns     short loc_180007A26
0x180007a12  mov     [rsp+30h+var_8], eax
0x180007a16  lea     rax, aIsraslowonheal_1; "IsRASLowOnHealth::EnumRasDevices failed"...
0x180007a1d  jmp     loc_18000790F
0x180007a22  mov     r14d, [rbp+arg_10]
0x180007a26  mov     ebx, 1
0x180007a2b  test    r14d, r14d
0x180007a2e  jz      loc_180007AC5
0x180007a34  mov     eax, esi
0x180007a36  lea     r8, aModem; "modem"
0x180007a3d  imul    r12, rax, 128h
0x180007a44  or      r9d, 0FFFFFFFFh; cchCount2
0x180007a48  mov     [rsp+30h+bIgnoreCase], ebx; bIgnoreCase
0x180007a4c  add     r12, 4
0x180007a50  or      edx, r9d; cchCount1
0x180007a53  add     r12, rdi
0x180007a56  mov     rcx, r12; lpString1
0x180007a59  call    cs:__imp_CompareStringOrdinal
0x180007a60  nop     dword ptr [rax+rax+00h]
0x180007a65  cmp     eax, 2
0x180007a68  jz      loc_180007B07
0x180007a6e  or      edx, 0FFFFFFFFh; cchCount1
0x180007a71  mov     [rsp+30h+bIgnoreCase], ebx; bIgnoreCase
0x180007a75  mov     r9d, edx; cchCount2
0x180007a78  lea     r8, aIsdn; "isdn"
0x180007a7f  mov     rcx, r12; lpString1
0x180007a82  call    cs:__imp_CompareStringOrdinal
0x180007a89  nop     dword ptr [rax+rax+00h]
0x180007a8e  cmp     eax, 2
0x180007a91  jz      short loc_180007B07
0x180007a93  or      eax, 0FFFFFFFFh
0x180007a96  mov     [rsp+30h+bIgnoreCase], ebx; bIgnoreCase
0x180007a9a  mov     r9d, eax; cchCount2
0x180007a9d  lea     r8, aPppoe; "PPPoE"
0x180007aa4  mov     edx, eax; cchCount1
0x180007aa6  mov     rcx, r12; lpString1
0x180007aa9  call    cs:__imp_CompareStringOrdinal
0x180007ab0  nop     dword ptr [rax+rax+00h]
0x180007ab5  cmp     eax, 2
0x180007ab8  jz      short loc_180007B07
0x180007aba  add     esi, ebx
0x180007abc  cmp     esi, r14d
0x180007abf  jb      loc_180007A34
0x180007ac5  xor     esi, esi
0x180007ac7  lea     rax, aThereWereNoRas; "There were no RAS modems found. Bailing"...
0x180007ace  lea     r9, aCrasdiaghelper; "CRasDiagHelper"
0x180007ad5  movsx   r8d, bx
0x180007ad9  mov     edx, 2
0x180007ade  mov     qword ptr [rsp+30h+bIgnoreCase], rax
0x180007ae3  lea     rcx, [r13+4B8h]
0x180007aea  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x180007aef  mov     rbx, [rsp+30h+arg_0]
0x180007af4  mov     eax, esi
0x180007af6  add     rsp, 30h
0x180007afa  pop     r15
0x180007afc  pop     r14
0x180007afe  pop     r13
0x180007b00  pop     r12
0x180007b02  pop     rdi
0x180007b03  pop     rsi
0x180007b04  pop     rbp
0x180007b05  retn
0x180007b07  test    r15, r15
0x180007b0a  jz      short loc_180007B1F
0x180007b0c  mov     r8d, 100h; unsigned int
0x180007b12  mov     rdx, r15; unsigned __int16 **
0x180007b15  mov     ecx, 3EAh; uID
0x180007b1a  call    ?LoadStringWithAlloc@@YAJIPEAPEAGI@Z; LoadStringWithAlloc(uint,ushort * *,uint)
0x180007b1f  movups  xmm0, xmmword ptr cs:ID_RAS_LOWH_REPAIR_NO_INTERNET_CONNECTIVITY.Data1
0x180007b26  mov     esi, ebx
0x180007b28  lea     rax, aRasDeviceWasDe; "RAS device was detected but no active c"...
0x180007b2f  movdqu  xmmword ptr [r13+4A8h], xmm0
0x180007b38  jmp     short loc_180007ACE
```
