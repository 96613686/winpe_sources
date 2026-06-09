# CDevInventory::ExecWmiQuery(IEnumWbemClassObject * *,ushort const *)

- ea: `0x180039d44`
- end: `0x18003a4d4`
- name: `?ExecWmiQuery@CDevInventory@@SAJPEAPEAUIEnumWbemClassObject@@PEBG@Z`
- size: `1936`
- prototype: `__int64 __fastcall(struct IEnumWbemClassObject **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003af48`

## callees

- `0x180006d02`
- `0x180007014`
- `0x180039b5c`
- `0x180039d44`
- `0x18006041c`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003a00c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003a040`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003a00c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003a040`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180039f07`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003a198`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180039f07`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003a198`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180039d9e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180039d9e`
- `OLEAUT32!__imp_SysAllocString` at `0x180039e76`
- `OLEAUT32!__imp_SysAllocString` at `0x180039fcf`
- `OLEAUT32!__imp_SysAllocString` at `0x180039e76`
- `OLEAUT32!__imp_SysAllocString` at `0x180039fcf`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003a019`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003a019`
- `OLEAUT32!__imp_SysFreeString` at `0x180039ec3`
- `OLEAUT32!__imp_SysFreeString` at `0x180039fc2`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a08d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a473`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a4c2`
- `OLEAUT32!__imp_SysFreeString` at `0x180039ec3`
- `OLEAUT32!__imp_SysFreeString` at `0x180039fc2`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a08d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a473`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a4c2`

## string_xrefs

- `0x180039dbd`: `[0x%08x] CoCreateInstance failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CDevInventory::ExecWmiQuery(IUnknown **a1, const unsigned __int16 *a2)
{
  OLECHAR *v3; // rdi
  HRESULT v4; // eax
  int v5; // esi
  const char *v6; // r15
  FILE *v7; // rax
  FILE *v8; // rax
  FILE *v9; // rax
  __int64 v10; // r8
  LPVOID v11; // rbx
  __int64 v12; // rsi
  BSTR v13; // rax
  int v14; // ecx
  OLECHAR *v15; // r14
  HRESULT v16; // eax
  FILE *v17; // rax
  FILE *v18; // rax
  FILE *v19; // rax
  int v20; // ecx
  IUnknown *v21; // r14
  struct IUnknownVtbl *lpVtbl; // r13
  int v23; // esi
  WCHAR *v24; // rax
  int v25; // ecx
  OLECHAR *v26; // rbx
  int v27; // eax
  FILE *v28; // rax
  FILE *v29; // rax
  FILE *v30; // rax
  HRESULT v31; // eax
  FILE *v32; // rax
  FILE *v33; // rax
  FILE *v34; // rax
  FILE *v35; // rax
  FILE *v36; // rax
  FILE *v37; // rax
  FILE *v38; // rax
  FILE *v39; // rax
  FILE *v40; // rax
  FILE *v41; // rax
  FILE *v42; // rax
  FILE *v43; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-48h]
  __int64 v46; // [rsp+B0h] [rbp+48h] BYREF
  IUnknown *pProxy; // [rsp+B8h] [rbp+50h] BYREF
  LPVOID v48; // [rsp+C0h] [rbp+58h] BYREF
  OLECHAR *v49; // [rsp+C8h] [rbp+60h]

  v48 = 0;
  pProxy = 0;
  v3 = 0;
  v49 = 0;
  v46 = 0;
  if ( !a1 )
  {
    v5 = -2147024809;
    v6 = "[0x%08x] Invalid Arguments";
    AslLogCallPrintf(2, "CDevInventory::ExecWmiQuery", 1367, "[0x%08x] Invalid Arguments", -2147024809);
    if ( EnableDevInvStdErrLog )
    {
      v41 = o___acrt_iob_func_0(2u);
      fprintf(v41, "Error: %s, %u: ", "CDevInventory::ExecWmiQuery", 1367);
      v42 = o___acrt_iob_func_0(2u);
      fprintf(v42, "[0x%08x] Invalid Arguments", -2147024809);
      v43 = o___acrt_iob_func_0(2u);
      fprintf(v43, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "[0x%08x] Invalid Arguments", -2147024809);
    v10 = 1367;
    goto LABEL_53;
  }
  v4 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &v48);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( v4 == -2147221164 )
      goto LABEL_54;
    goto LABEL_4;
  }
  v11 = v48;
  if ( !v48 )
  {
LABEL_4:
    v6 = "[0x%08x] CoCreateInstance failed";
    AslLogCallPrintf(2, "CDevInventory::ExecWmiQuery", 1379, "[0x%08x] CoCreateInstance failed", v4);
    if ( EnableDevInvStdErrLog )
    {
      v7 = o___acrt_iob_func_0(2u);
      fprintf(v7, "Error: %s, %u: ", "CDevInventory::ExecWmiQuery", 1379);
      v8 = o___acrt_iob_func_0(2u);
      fprintf(v8, "[0x%08x] CoCreateInstance failed", v5);
      v9 = o___acrt_iob_func_0(2u);
      fprintf(v9, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "[0x%08x] CoCreateInstance failed", v5);
    v10 = 1379;
    goto LABEL_53;
  }
  v12 = *(_QWORD *)v48;
  v13 = SysAllocString(L"ROOT\\CIMV2");
  v15 = v13;
  if ( !v13 )
    ATL::AtlThrowImpl(v14);
  v5 = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(v12 + 24))(
         v11,
         v13,
         0,
         0,
         0,
         0,
         0,
         0,
         &pProxy);
  SysFreeString(v15);
  if ( v5 < 0 || !pProxy )
  {
    v6 = "[0x%08x] ConnectServer failed";
    AslLogCallPrintf(2, "CDevInventory::ExecWmiQuery", 1386, "[0x%08x] ConnectServer failed", v5);
    if ( EnableDevInvStdErrLog )
    {
      v38 = o___acrt_iob_func_0(2u);
      fprintf(v38, "Error: %s, %u: ", "CDevInventory::ExecWmiQuery", 1386);
      v39 = o___acrt_iob_func_0(2u);
      fprintf(v39, "[0x%08x] ConnectServer failed", v5);
      v40 = o___acrt_iob_func_0(2u);
      fprintf(v40, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "[0x%08x] ConnectServer failed", v5);
    v10 = 1386;
    goto LABEL_53;
  }
  v16 = CoSetProxyBlanket(
          pProxy,
          0xFFFFFFFF,
          0xFFFFFFFF,
          (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
          0,
          3u,
          (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
          0x800u);
  v5 = v16;
  if ( v16 < 0 )
  {
    v6 = "[0x%08x] CoSetProxyBlanket failed";
    AslLogCallPrintf(2, "CDevInventory::ExecWmiQuery", 1404, "[0x%08x] CoSetProxyBlanket failed", v16);
    if ( EnableDevInvStdErrLog )
    {
      v17 = o___acrt_iob_func_0(2u);
      fprintf(v17, "Error: %s, %u: ", "CDevInventory::ExecWmiQuery", 1404);
      v18 = o___acrt_iob_func_0(2u);
      fprintf(v18, "[0x%08x] CoSetProxyBlanket failed", v5);
      v19 = o___acrt_iob_func_0(2u);
      fprintf(v19, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "[0x%08x] CoSetProxyBlanket failed", v5);
    v10 = 1404;
    goto LABEL_53;
  }
  SysFreeString(0);
  v3 = SysAllocString(L"select Capacity from Win32_PhysicalMemory");
  v49 = v3;
  if ( !v3 )
    ATL::AtlThrowImpl(v20);
  v21 = pProxy;
  lpVtbl = pProxy->lpVtbl;
  v23 = MultiByteToWideChar(3u, 0, "WQL", -1, 0, 0);
  v24 = SysAllocStringLen(0, v23 - 1);
  v26 = v24;
  if ( v24 && MultiByteToWideChar(3u, 0, "WQL", -1, v24, v23) != v23 )
  {
    SysFreeString(v26);
LABEL_63:
    ATL::AtlThrowImpl(v25);
  }
  if ( !v26 )
    goto LABEL_63;
  v5 = ((__int64 (__fastcall *)(IUnknown *, OLECHAR *, OLECHAR *, __int64, _QWORD, __int64 *))lpVtbl[6].Release)(
         v21,
         v26,
         v3,
         48,
         0,
         &v46);
  SysFreeString(v26);
  if ( v5 >= 0 && v46 )
  {
    v27 = (**(__int64 (__fastcall ***)(__int64, GUID *, IUnknown **))v46)(v46, &IID_IEnumWbemClassObject, a1);
    v5 = v27;
    if ( v27 >= 0 )
    {
      v31 = CoSetProxyBlanket(
              *a1,
              0xFFFFFFFF,
              0xFFFFFFFF,
              (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
              0,
              3u,
              (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
              0x800u);
      v5 = v31;
      if ( v31 >= 0 )
      {
        v5 = 0;
        goto LABEL_54;
      }
      v6 = "[0x%08x] CoSetProxyBlanket failed";
      AslLogCallPrintf(2, "CDevInventory::ExecWmiQuery", 1441, "[0x%08x] CoSetProxyBlanket failed", v31);
      if ( EnableDevInvStdErrLog )
      {
        v32 = o___acrt_iob_func_0(2u);
        fprintf(v32, "Error: %s, %u: ", "CDevInventory::ExecWmiQuery", 1441);
        v33 = o___acrt_iob_func_0(2u);
        fprintf(v33, "[0x%08x] CoSetProxyBlanket failed", v5);
        v34 = o___acrt_iob_func_0(2u);
        fprintf(v34, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "[0x%08x] CoSetProxyBlanket failed", v5);
      v10 = 1441;
    }
    else
    {
      v6 = "[0x%08x] QueryInterface failed";
      AslLogCallPrintf(2, "CDevInventory::ExecWmiQuery", 1423, "[0x%08x] QueryInterface failed", v27);
      if ( EnableDevInvStdErrLog )
      {
        v28 = o___acrt_iob_func_0(2u);
        fprintf(v28, "Error: %s, %u: ", "CDevInventory::ExecWmiQuery", 1423);
        v29 = o___acrt_iob_func_0(2u);
        fprintf(v29, "[0x%08x] QueryInterface failed", v5);
        v30 = o___acrt_iob_func_0(2u);
        fprintf(v30, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "[0x%08x] QueryInterface failed", v5);
      v10 = 1423;
    }
  }
  else
  {
    v6 = "[0x%08x] ExecQuery failed";
    AslLogCallPrintf(2, "CDevInventory::ExecWmiQuery", 1416, "[0x%08x] ExecQuery failed", v5);
    if ( EnableDevInvStdErrLog )
    {
      v35 = o___acrt_iob_func_0(2u);
      fprintf(v35, "Error: %s, %u: ", "CDevInventory::ExecWmiQuery", 1416);
      v36 = o___acrt_iob_func_0(2u);
      fprintf(v36, "[0x%08x] ExecQuery failed", v5);
      v37 = o___acrt_iob_func_0(2u);
      fprintf(v37, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "[0x%08x] ExecQuery failed", v5);
    v10 = 1416;
  }
LABEL_53:
  LODWORD(ppv) = v5;
  AslLogCallPrintf(1, "CDevInventory::ExecWmiQuery", v10, v6, ppv);
LABEL_54:
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  SysFreeString(v3);
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  if ( v48 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v48 + 16LL))(v48);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180039d44  mov     [rsp-40h+pProxy], rdx
0x180039d49  push    rbp
0x180039d4a  push    rbx
0x180039d4b  push    rsi
0x180039d4c  push    rdi
0x180039d4d  push    r12
0x180039d4f  push    r13
0x180039d51  push    r14
0x180039d53  push    r15
0x180039d55  mov     rbp, rsp
0x180039d58  sub     rsp, 68h
0x180039d5c  mov     r15, rcx
0x180039d5f  xor     r13d, r13d
0x180039d62  mov     [rbp+arg_10], r13
0x180039d66  mov     [rbp+pProxy], r13
0x180039d6a  mov     edi, r13d
0x180039d6d  mov     [rbp+arg_18], r13
0x180039d71  mov     [rbp+arg_0], r13
0x180039d75  test    rcx, rcx
0x180039d78  jz      loc_18003A3A2
0x180039d7e  lea     rax, [rbp+arg_10]
0x180039d82  mov     [rsp+68h+ppv], rax; ppv
0x180039d87  lea     r9, IID_IWbemLocator; riid
0x180039d8e  lea     r12d, [r13+1]
0x180039d92  mov     r8d, r12d; dwClsContext
0x180039d95  xor     edx, edx; pUnkOuter
0x180039d97  lea     rcx, CLSID_WbemLocator; rclsid
0x180039d9e  call    cs:__imp_CoCreateInstance
0x180039da4  mov     esi, eax
0x180039da6  test    eax, eax
0x180039da8  jns     loc_180039E5F
0x180039dae  cmp     eax, 80040154h
0x180039db3  jz      loc_18003A45A
0x180039db9  mov     dword ptr [rsp+68h+ppv], esi
0x180039dbd  lea     r15, a0x08xCocreatei; "[0x%08x] CoCreateInstance failed"
0x180039dc4  mov     r9, r15
0x180039dc7  mov     r8d, 563h
0x180039dcd  lea     rbx, aCdevinventoryE; "CDevInventory::ExecWmiQuery"
0x180039dd4  mov     rdx, rbx
0x180039dd7  mov     r14d, 2
0x180039ddd  mov     ecx, r14d
0x180039de0  call    AslLogCallPrintf
0x180039de5  cmp     cs:EnableDevInvStdErrLog, r13d
0x180039dec  jz      short loc_180039E3B
0x180039dee  mov     ecx, r14d; Ix
0x180039df1  call    _o___acrt_iob_func_0
0x180039df6  mov     rcx, rax; Stream
0x180039df9  mov     r9d, 563h
0x180039dff  mov     r8, rbx
0x180039e02  lea     rdx, Format; "Error: %s, %u: "
0x180039e09  call    fprintf
0x180039e0e  mov     ecx, r14d; Ix
0x180039e11  call    _o___acrt_iob_func_0
0x180039e16  mov     rcx, rax; Stream
0x180039e19  mov     r8d, esi
0x180039e1c  mov     rdx, r15; Format
0x180039e1f  call    fprintf
0x180039e24  mov     ecx, r14d; Ix
0x180039e27  call    _o___acrt_iob_func_0
0x180039e2c  mov     rcx, rax; Stream
0x180039e2f  lea     rdx, asc_18011EAD8; "\n"
0x180039e36  call    fprintf
0x180039e3b  cmp     cs:g_DeviceMapLogFunction, r13
0x180039e42  jz      short loc_180039E54
0x180039e44  mov     r8d, esi
0x180039e47  mov     rdx, r15
0x180039e4a  mov     ecx, 2000000h
0x180039e4f  call    TraceMessageCallback
0x180039e54  mov     r8d, 563h
0x180039e5a  jmp     loc_180039FB8
0x180039e5f  mov     rbx, [rbp+arg_10]
0x180039e63  test    rbx, rbx
0x180039e66  jz      loc_180039DB9
0x180039e6c  mov     rsi, [rbx]
0x180039e6f  lea     rcx, psz; "ROOT\\CIMV2"
0x180039e76  call    cs:__imp_SysAllocString
0x180039e7c  mov     r14, rax
0x180039e7f  mov     [rbp+var_18], rax
0x180039e83  test    rax, rax
0x180039e86  jz      loc_18003A4CE
0x180039e8c  lea     rax, [rbp+pProxy]
0x180039e90  mov     [rsp+68h+var_28], rax
0x180039e95  mov     qword ptr [rsp+68h+dwCapabilities], r13
0x180039e9a  mov     [rsp+68h+pAuthInfo], r13
0x180039e9f  mov     [rsp+68h+dwImpLevel], r13d
0x180039ea4  mov     [rsp+68h+ppv], r13
0x180039ea9  xor     r9d, r9d
0x180039eac  xor     r8d, r8d
0x180039eaf  mov     rdx, r14
0x180039eb2  mov     rcx, rbx
0x180039eb5  mov     rax, [rsi+18h]
0x180039eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ebe  mov     esi, eax
0x180039ec0  mov     rcx, r14; bstrString
0x180039ec3  call    cs:__imp_SysFreeString
0x180039ec9  test    esi, esi
0x180039ecb  js      loc_18003A2FC
0x180039ed1  mov     rcx, [rbp+pProxy]; pProxy
0x180039ed5  test    rcx, rcx
0x180039ed8  jz      loc_18003A2FC
0x180039ede  mov     [rsp+68h+dwCapabilities], 800h; dwCapabilities
0x180039ee6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180039eea  mov     [rsp+68h+pAuthInfo], rbx; pAuthInfo
0x180039eef  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x180039ef7  mov     dword ptr [rsp+68h+ppv], r13d; dwAuthnLevel
0x180039efc  mov     r9, rbx; pServerPrincName
0x180039eff  or      eax, 0FFFFFFFFh
0x180039f02  mov     r8d, eax; dwAuthzSvc
0x180039f05  mov     edx, eax; dwAuthnSvc
0x180039f07  call    cs:__imp_CoSetProxyBlanket
0x180039f0d  mov     esi, eax
0x180039f0f  test    eax, eax
0x180039f11  jns     loc_180039FC0
0x180039f17  mov     dword ptr [rsp+68h+ppv], eax
0x180039f1b  lea     r15, a0x08xCosetprox; "[0x%08x] CoSetProxyBlanket failed"
0x180039f22  mov     r9, r15
0x180039f25  mov     r8d, 57Ch
0x180039f2b  lea     rbx, aCdevinventoryE; "CDevInventory::ExecWmiQuery"
0x180039f32  mov     rdx, rbx
0x180039f35  mov     r14d, 2
0x180039f3b  mov     ecx, r14d
0x180039f3e  call    AslLogCallPrintf
0x180039f43  cmp     cs:EnableDevInvStdErrLog, r13d
0x180039f4a  jz      short loc_180039F99
0x180039f4c  mov     ecx, r14d; Ix
0x180039f4f  call    _o___acrt_iob_func_0
0x180039f54  mov     rcx, rax; Stream
0x180039f57  mov     r9d, 57Ch
0x180039f5d  mov     r8, rbx
0x180039f60  lea     rdx, Format; "Error: %s, %u: "
0x180039f67  call    fprintf
0x180039f6c  mov     ecx, r14d; Ix
0x180039f6f  call    _o___acrt_iob_func_0
0x180039f74  mov     rcx, rax; Stream
0x180039f77  mov     r8d, esi
0x180039f7a  mov     rdx, r15; Format
0x180039f7d  call    fprintf
0x180039f82  mov     ecx, r14d; Ix
0x180039f85  call    _o___acrt_iob_func_0
0x180039f8a  mov     rcx, rax; Stream
0x180039f8d  lea     rdx, asc_18011EAD8; "\n"
0x180039f94  call    fprintf
0x180039f99  cmp     cs:g_DeviceMapLogFunction, r13
0x180039fa0  jz      short loc_180039FB2
0x180039fa2  mov     r8d, esi
0x180039fa5  mov     rdx, r15
0x180039fa8  mov     ecx, 2000000h
0x180039fad  call    TraceMessageCallback
0x180039fb2  mov     r8d, 57Ch
0x180039fb8  mov     ecx, r12d
0x180039fbb  jmp     loc_18003A44A
0x180039fc0  xor     ecx, ecx; bstrString
0x180039fc2  call    cs:__imp_SysFreeString
0x180039fc8  lea     rcx, aSelectCapacity; "select Capacity from Win32_PhysicalMemo"...
0x180039fcf  call    cs:__imp_SysAllocString
0x180039fd5  mov     rdi, rax
0x180039fd8  mov     [rbp+arg_18], rax
0x180039fdc  test    rax, rax
0x180039fdf  jz      loc_18003A4B9
0x180039fe5  mov     r14, [rbp+pProxy]
0x180039fe9  mov     r13, [r14]
0x180039fec  mov     [rsp+68h+dwImpLevel], 0; cchWideChar
0x180039ff4  mov     [rsp+68h+ppv], 0; lpWideCharStr
0x180039ffd  mov     r9d, ebx; cbMultiByte
0x18003a000  lea     r8, MultiByteStr; "WQL"
0x18003a007  xor     edx, edx; dwFlags
0x18003a009  lea     ecx, [rdx+3]; CodePage
0x18003a00c  call    cs:__imp_MultiByteToWideChar
0x18003a012  mov     esi, eax
0x18003a014  lea     edx, [rax-1]; ui
0x18003a017  xor     ecx, ecx; strIn
0x18003a019  call    cs:__imp_SysAllocStringLen
0x18003a01f  mov     rbx, rax
0x18003a022  test    rax, rax
0x18003a025  jz      short loc_18003A04E
0x18003a027  mov     [rsp+68h+dwImpLevel], esi; cchWideChar
0x18003a02b  mov     [rsp+68h+ppv], rax; lpWideCharStr
0x18003a030  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18003a034  lea     r8, MultiByteStr; "WQL"
0x18003a03b  xor     edx, edx; dwFlags
0x18003a03d  lea     ecx, [rdx+3]; CodePage
0x18003a040  call    cs:__imp_MultiByteToWideChar
0x18003a046  cmp     eax, esi
0x18003a048  jnz     loc_18003A4BF
0x18003a04e  mov     [rbp+var_18], rbx
0x18003a052  test    rbx, rbx
0x18003a055  jz      loc_18003A4C8
0x18003a05b  lea     rax, [rbp+arg_0]
0x18003a05f  mov     qword ptr [rsp+68h+dwImpLevel], rax
0x18003a064  mov     [rsp+68h+ppv], 0
0x18003a06d  mov     r9d, 30h ; '0'
0x18003a073  mov     r8, rdi
0x18003a076  mov     rdx, rbx
0x18003a079  mov     rcx, r14
0x18003a07c  mov     rax, [r13+0A0h]
0x18003a083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a088  mov     esi, eax
0x18003a08a  mov     rcx, rbx; bstrString
0x18003a08d  call    cs:__imp_SysFreeString
0x18003a093  xor     r13d, r13d
0x18003a096  test    esi, esi
0x18003a098  js      loc_18003A256
0x18003a09e  mov     rcx, [rbp+arg_0]
0x18003a0a2  test    rcx, rcx
0x18003a0a5  jz      loc_18003A256
0x18003a0ab  mov     rax, [rcx]
0x18003a0ae  mov     r8, r15
0x18003a0b1  lea     rdx, IID_IEnumWbemClassObject
0x18003a0b8  mov     rax, [rax]
0x18003a0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0c0  mov     esi, eax
0x18003a0c2  test    eax, eax
0x18003a0c4  jns     loc_18003A16E
0x18003a0ca  mov     dword ptr [rsp+68h+ppv], eax
0x18003a0ce  lea     r15, a0x08xQueryinte; "[0x%08x] QueryInterface failed"
0x18003a0d5  mov     r9, r15
0x18003a0d8  mov     r8d, 58Fh
0x18003a0de  lea     rbx, aCdevinventoryE; "CDevInventory::ExecWmiQuery"
0x18003a0e5  mov     rdx, rbx
0x18003a0e8  lea     r14d, [r13+2]
0x18003a0ec  mov     ecx, r14d
0x18003a0ef  call    AslLogCallPrintf
0x18003a0f4  cmp     cs:EnableDevInvStdErrLog, r13d
0x18003a0fb  jz      short loc_18003A14A
0x18003a0fd  mov     ecx, r14d; Ix
0x18003a100  call    _o___acrt_iob_func_0
0x18003a105  mov     rcx, rax; Stream
0x18003a108  mov     r9d, 58Fh
0x18003a10e  mov     r8, rbx
0x18003a111  lea     rdx, Format; "Error: %s, %u: "
0x18003a118  call    fprintf
0x18003a11d  mov     ecx, r14d; Ix
0x18003a120  call    _o___acrt_iob_func_0
0x18003a125  mov     rcx, rax; Stream
0x18003a128  mov     r8d, esi
0x18003a12b  mov     rdx, r15; Format
0x18003a12e  call    fprintf
0x18003a133  mov     ecx, r14d; Ix
0x18003a136  call    _o___acrt_iob_func_0
0x18003a13b  mov     rcx, rax; Stream
0x18003a13e  lea     rdx, asc_18011EAD8; "\n"
0x18003a145  call    fprintf
0x18003a14a  cmp     cs:g_DeviceMapLogFunction, r13
0x18003a151  jz      short loc_18003A163
0x18003a153  mov     r8d, esi
0x18003a156  mov     rdx, r15
0x18003a159  mov     ecx, 2000000h
0x18003a15e  call    TraceMessageCallback
0x18003a163  mov     r8d, 58Fh
0x18003a169  jmp     loc_180039FB8
0x18003a16e  mov     [rsp+68h+dwCapabilities], 800h; dwCapabilities
0x18003a176  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003a17a  mov     [rsp+68h+pAuthInfo], rax; pAuthInfo
0x18003a17f  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x18003a187  mov     dword ptr [rsp+68h+ppv], r13d; dwAuthnLevel
0x18003a18c  mov     r9, rax; pServerPrincName
0x18003a18f  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18003a192  mov     r8d, edx; dwAuthzSvc
0x18003a195  mov     rcx, [r15]; pProxy
0x18003a198  call    cs:__imp_CoSetProxyBlanket
0x18003a19e  mov     esi, eax
0x18003a1a0  test    eax, eax
0x18003a1a2  jns     loc_18003A24E
0x18003a1a8  mov     dword ptr [rsp+68h+ppv], eax
0x18003a1ac  lea     r15, a0x08xCosetprox; "[0x%08x] CoSetProxyBlanket failed"
0x18003a1b3  mov     r9, r15
0x18003a1b6  mov     r8d, 5A1h
0x18003a1bc  lea     rbx, aCdevinventoryE; "CDevInventory::ExecWmiQuery"
0x18003a1c3  mov     rdx, rbx
0x18003a1c6  mov     r14d, 2
0x18003a1cc  mov     ecx, r14d
0x18003a1cf  call    AslLogCallPrintf
0x18003a1d4  cmp     cs:EnableDevInvStdErrLog, r13d
0x18003a1db  jz      short loc_18003A22A
0x18003a1dd  mov     ecx, r14d; Ix
0x18003a1e0  call    _o___acrt_iob_func_0
0x18003a1e5  mov     rcx, rax; Stream
0x18003a1e8  mov     r9d, 5A1h
0x18003a1ee  mov     r8, rbx
0x18003a1f1  lea     rdx, Format; "Error: %s, %u: "
0x18003a1f8  call    fprintf
0x18003a1fd  mov     ecx, r14d; Ix
0x18003a200  call    _o___acrt_iob_func_0
0x18003a205  mov     rcx, rax; Stream
0x18003a208  mov     r8d, esi
0x18003a20b  mov     rdx, r15; Format
0x18003a20e  call    fprintf
0x18003a213  mov     ecx, r14d; Ix
0x18003a216  call    _o___acrt_iob_func_0
0x18003a21b  mov     rcx, rax; Stream
0x18003a21e  lea     rdx, asc_18011EAD8; "\n"
0x18003a225  call    fprintf
0x18003a22a  cmp     cs:g_DeviceMapLogFunction, r13
0x18003a231  jz      short loc_18003A243
0x18003a233  mov     r8d, esi
0x18003a236  mov     rdx, r15
0x18003a239  mov     ecx, 2000000h
0x18003a23e  call    TraceMessageCallback
0x18003a243  mov     r8d, 5A1h
0x18003a249  jmp     loc_180039FB8
  ... truncated ...
```
