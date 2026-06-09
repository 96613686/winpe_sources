# SetAutologonDetails(ushort const *,ushort const *,uchar const *,ulong,bool,bool)

- ea: `0x1800be424`
- end: `0x1800be942`
- name: `?SetAutologonDetails@@YAJPEBG0PEBEK_N2@Z`
- size: `1310`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *, unsigned int, bool, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032c50`
- `0x180053f60`

## callees

- `0x180008524`
- `0x180008544`
- `0x18002d0e0`
- `0x1800aecd4`
- `0x1800b8834`
- `0x1800be388`
- `0x1800be424`
- `0x1800bed68`
- `0x1800bef90`

## import_xrefs

- `SHLWAPI!SHDeleteValueW` at `0x1800be901`
- `SHLWAPI!SHDeleteValueW` at `0x1800be901`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800be81b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800be872`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800be81b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800be872`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be5a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be5e2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be5a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800be5e2`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryDWORD` at `0x1800be69c`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryDWORD` at `0x1800be69c`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x1800be4be`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x1800be643`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x1800be4be`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x1800be643`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryBOOL` at `0x1800be51f`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryBOOL` at `0x1800be51f`
- `SspiCli!SspiLocalFree` at `0x1800be7a6`
- `SspiCli!SspiLocalFree` at `0x1800be83d`
- `SspiCli!SspiLocalFree` at `0x1800be894`
- `SspiCli!SspiLocalFree` at `0x1800be7a6`
- `SspiCli!SspiLocalFree` at `0x1800be83d`
- `SspiCli!SspiLocalFree` at `0x1800be894`
- `CRYPT32!CryptProtectData` at `0x1800be76c`
- `CRYPT32!CryptProtectData` at `0x1800be76c`

## string_xrefs

- `0x1800be5d4`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x1800be595`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x1800be4de`: `shell\oobe\common\lib\autologon.cpp`
- `0x1800be543`: `shell\oobe\common\lib\autologon.cpp`
- `0x1800be60a`: `shell\oobe\common\lib\autologon.cpp`
- `0x1800be663`: `shell\oobe\common\lib\autologon.cpp`
- `0x1800be6bc`: `shell\oobe\common\lib\autologon.cpp`
- `0x1800be711`: `shell\oobe\common\lib\autologon.cpp`
- `0x1800be77a`: `shell\oobe\common\lib\autologon.cpp`
- `0x1800be7ee`: `shell\oobe\common\lib\autologon.cpp`
- `0x1800be8c8`: `shell\oobe\common\lib\autologon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SetAutologonDetails(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        DWORD a4,
        bool a5,
        bool a6)
{
  char v8; // bl
  unsigned __int8 v9; // di
  BOOL v10; // r15d
  int v11; // eax
  unsigned int LastError; // edi
  int v14; // eax
  HKEY v15; // rcx
  int v16; // r9d
  int v17; // eax
  int v18; // eax
  int v19; // eax
  unsigned __int8 *v20; // rdx
  bool v21; // cl
  unsigned int v22; // r8d
  int v23; // eax
  const char *v24; // r9
  __int64 v25; // rdx
  _BYTE *v26; // rcx
  int v27; // eax
  __int64 cbData; // rdx
  BYTE *pbData; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  BYTE *v32; // rcx
  __int64 v33; // rax
  _BYTE *v34; // rcx
  int v35; // eax
  unsigned int v36; // ebx
  int pdwType; // [rsp+20h] [rbp-50h]
  int pdwTypea; // [rsp+20h] [rbp-50h]
  DWORD pdwTypeb; // [rsp+20h] [rbp-50h]
  bool *v40; // [rsp+40h] [rbp-30h] BYREF
  char v41; // [rsp+48h] [rbp-28h]
  DATA_BLOB pDataOut; // [rsp+50h] [rbp-20h] BYREF
  DATA_BLOB pDataIn; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  PVOID DataBuffer; // [rsp+C0h] [rbp+50h] BYREF
  DWORD pcbData; // [rsp+C8h] [rbp+58h] BYREF

  pcbData = a4;
  DataBuffer = a3;
  v8 = 1;
  a5 = 1;
  v40 = &a5;
  v41 = 1;
  if ( !a1 || !*a1 || (v9 = 1, !a2) )
    v9 = 0;
  v10 = a2 == 0;
  UnattendLogW(0, L"Setting auto logon with fUseAuthBuffer = %d, fEnableAutologon = %d", a2 == 0, v9);
  if ( v9 )
  {
    v11 = SetPersistedRegistryString(
            L"Winlogon",
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            L"AutoAdminLogon",
            L"1");
    LastError = v11;
    if ( v11 > 0 )
      LastError = (unsigned __int16)v11 | 0x80070000;
    if ( (LastError & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)LastError,
        pdwType);
      v41 = 0;
      lambda_593abc42667a9590cca80463005afefb_::operator()(&v40);
      return LastError;
    }
    if ( a6 )
    {
      v14 = SetPersistedRegistryBOOL(
              L"Winlogon",
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
              L"SystemAutoLogon",
              1);
      LastError = v14;
      if ( v14 > 0 )
        LastError = (unsigned __int16)v14 | 0x80070000;
      if ( (LastError & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B,
          (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
          (const char *)LastError,
          pdwType);
        v41 = 0;
        lambda_593abc42667a9590cca80463005afefb_::operator()(&v40);
        return LastError;
      }
    }
    else
    {
      LODWORD(DataBuffer) = 0;
      pcbData = 4;
      if ( RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
             L"Enabled",
             0x10010u,
             0,
             &DataBuffer,
             &pcbData) )
      {
        pcbData = 4;
        RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
          L"Enabled",
          0x20010010u,
          0,
          &DataBuffer,
          &pcbData);
      }
      if ( (_DWORD)DataBuffer )
      {
        v17 = SHRegSetBOOL(v15, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"ForceAutoLogon", v16);
        LastError = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4F,
            (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
            (const char *)(unsigned int)v17,
            pdwType);
          v41 = 0;
          lambda_593abc42667a9590cca80463005afefb_::operator()(&v40);
          return LastError;
        }
      }
    }
    v18 = SetPersistedRegistryString(
            L"Winlogon",
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            L"DefaultUserName",
            a1);
    LastError = v18;
    if ( v18 > 0 )
      LastError = (unsigned __int16)v18 | 0x80070000;
    if ( (LastError & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)LastError,
        pdwType);
      v41 = 0;
      lambda_593abc42667a9590cca80463005afefb_::operator()(&v40);
      return LastError;
    }
    v19 = SetPersistedRegistryDWORD(
            L"Winlogon",
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            L"IsConnectedAutoLogon",
            0);
    LastError = v19;
    if ( v19 > 0 )
      LastError = (unsigned __int16)v19 | 0x80070000;
    if ( (LastError & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)LastError,
        pdwType);
      v41 = 0;
      lambda_593abc42667a9590cca80463005afefb_::operator()(&v40);
      return LastError;
    }
    if ( a2 )
    {
      v35 = SetAutologonPassword(a2);
      v36 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x70,
          (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
          (const char *)(unsigned int)v35,
          pdwType);
        v41 = 0;
        lambda_593abc42667a9590cca80463005afefb_::operator()(&v40);
        return v36;
      }
    }
    else
    {
      DataBuffer = 0;
      pcbData = 0;
      v23 = _EncryptOrDecryptSspiAuthenticationBuffer(v21, v20, v22, (unsigned __int8 **)&DataBuffer, &pcbData);
      LastError = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
          (const char *)(unsigned int)v23,
          pdwTypea);
        v41 = 0;
        lambda_593abc42667a9590cca80463005afefb_::operator()(&v40);
        return LastError;
      }
      pDataIn.cbData = pcbData;
      *(&pDataIn.cbData + 1) = 0;
      pDataIn.pbData = (BYTE *)DataBuffer;
      pDataOut = 0;
      if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x65,
                      (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
                      v24);
        v25 = pcbData;
        v26 = DataBuffer;
        if ( pcbData )
        {
          do
          {
            *v26++ = 0;
            --v25;
          }
          while ( v25 );
          v26 = DataBuffer;
        }
LABEL_36:
        SspiLocalFree(v26);
        v41 = 0;
        lambda_593abc42667a9590cca80463005afefb_::operator()(&v40);
        return LastError;
      }
      pdwTypeb = pDataOut.cbData;
      v27 = SHRegSetBinaryData(
              -2147483646,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
              L"ConnectedCredentials",
              pDataOut.pbData);
      LastError = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6C,
          (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
          (const char *)(unsigned int)v27,
          pdwTypeb);
        cbData = pDataOut.cbData;
        pbData = pDataOut.pbData;
        if ( pDataOut.cbData )
        {
          do
          {
            *pbData++ = 0;
            --cbData;
          }
          while ( cbData );
          pbData = pDataOut.pbData;
        }
        LocalFree(pbData);
        v30 = pcbData;
        v26 = DataBuffer;
        if ( pcbData )
        {
          do
          {
            *v26++ = 0;
            --v30;
          }
          while ( v30 );
          v26 = DataBuffer;
        }
        goto LABEL_36;
      }
      v31 = pDataOut.cbData;
      v32 = pDataOut.pbData;
      if ( pDataOut.cbData )
      {
        do
        {
          *v32++ = 0;
          --v31;
        }
        while ( v31 );
        v32 = pDataOut.pbData;
      }
      LocalFree(v32);
      v33 = pcbData;
      v34 = DataBuffer;
      if ( pcbData )
      {
        do
        {
          *v34++ = 0;
          --v33;
        }
        while ( v33 );
        v34 = DataBuffer;
      }
      SspiLocalFree(v34);
    }
    v8 = 0;
    v41 = 0;
    UnattendLogW(0, L"Successfully setting Auto-logon with fUseAuthBuffer = %d", v10);
  }
  else
  {
    a5 = 0;
  }
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"AutoLogonCount");
  UnattendLogW(0, L"Cleaned up the AutoLogon Count value");
  if ( v8 )
  {
    v41 = 0;
    lambda_593abc42667a9590cca80463005afefb_::operator()(&v40);
  }
  return 0;
}

```

## disassembly

```asm
0x1800be424  mov     [rsp-38h+arg_0], rbx
0x1800be429  mov     [rsp-38h+arg_18], r9d
0x1800be42e  mov     [rsp-38h+DataBuffer], r8
0x1800be433  push    rbp
0x1800be434  push    rsi
0x1800be435  push    rdi
0x1800be436  push    r12
0x1800be438  push    r13
0x1800be43a  push    r14
0x1800be43c  push    r15
0x1800be43e  mov     rbp, rsp
0x1800be441  sub     rsp, 70h
0x1800be445  mov     rsi, rdx
0x1800be448  mov     r14, rcx
0x1800be44b  mov     ebx, 1
0x1800be450  mov     [rbp+arg_20], bl
0x1800be453  lea     rax, [rbp+arg_20]
0x1800be457  mov     [rbp+var_30], rax
0x1800be45b  mov     [rbp+var_28], bl
0x1800be45e  xor     r12d, r12d
0x1800be461  test    rcx, rcx
0x1800be464  jz      short loc_1800BE474
0x1800be466  cmp     [rcx], r12w
0x1800be46a  jz      short loc_1800BE474
0x1800be46c  test    rdx, rdx
0x1800be46f  mov     dil, bl
0x1800be472  jnz     short loc_1800BE477
0x1800be474  mov     dil, r12b
0x1800be477  mov     r15d, r12d
0x1800be47a  test    rsi, rsi
0x1800be47d  setz    r15b
0x1800be481  movzx   r9d, dil
0x1800be485  mov     r8d, r15d
0x1800be488  lea     rdx, aSettingAutoLog; "Setting auto logon with fUseAuthBuffer "...
0x1800be48f  xor     ecx, ecx
0x1800be491  call    UnattendLogW
0x1800be496  lea     r13, aSoftwareMicros_16; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800be49d  test    dil, dil
0x1800be4a0  jz      loc_1800BE8EC
0x1800be4a6  lea     r9, a1; "1"
0x1800be4ad  lea     r8, aAutoadminlogon; "AutoAdminLogon"
0x1800be4b4  mov     rdx, r13
0x1800be4b7  lea     rcx, aWinlogon; "Winlogon"
0x1800be4be  call    cs:__imp_SetPersistedRegistryString
0x1800be4c4  mov     edi, eax
0x1800be4c6  test    eax, eax
0x1800be4c8  jle     short loc_1800BE4D3
0x1800be4ca  movzx   edi, ax
0x1800be4cd  or      edi, 80070000h
0x1800be4d3  test    edi, edi
0x1800be4d5  jns     short loc_1800BE505
0x1800be4d7  mov     rcx, [rbp+38h]; this
0x1800be4db  mov     r9d, edi; char *
0x1800be4de  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x1800be4e5  mov     edx, 48h ; 'H'; void *
0x1800be4ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be4ef  nop
0x1800be4f0  mov     [rbp+var_28], r12b
0x1800be4f4  lea     rcx, [rbp+var_30]
0x1800be4f8  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x1800be4fd  nop
0x1800be4fe  mov     eax, edi
0x1800be500  jmp     loc_1800BE92A
0x1800be505  cmp     [rbp+arg_28], r12b
0x1800be509  jz      short loc_1800BE565
0x1800be50b  mov     r9d, ebx
0x1800be50e  lea     r8, aSystemautologo; "SystemAutoLogon"
0x1800be515  mov     rdx, r13
0x1800be518  lea     rcx, aWinlogon; "Winlogon"
0x1800be51f  call    cs:__imp_SetPersistedRegistryBOOL
0x1800be525  mov     edi, eax
0x1800be527  test    eax, eax
0x1800be529  jle     short loc_1800BE534
0x1800be52b  movzx   edi, ax
0x1800be52e  or      edi, 80070000h
0x1800be534  test    edi, edi
0x1800be536  jns     loc_1800BE62F
0x1800be53c  mov     rcx, [rbp+38h]; this
0x1800be540  mov     r9d, edi; char *
0x1800be543  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x1800be54a  mov     edx, 4Bh ; 'K'; void *
0x1800be54f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be554  nop
0x1800be555  mov     [rbp+var_28], r12b
0x1800be559  lea     rcx, [rbp+var_30]
0x1800be55d  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x1800be562  nop
0x1800be563  jmp     short loc_1800BE4FE
0x1800be565  mov     dword ptr [rbp+DataBuffer], r12d
0x1800be569  mov     edi, 4
0x1800be56e  mov     [rbp+arg_18], edi
0x1800be571  lea     rax, [rbp+arg_18]
0x1800be575  mov     [rsp+70h+pcbData], rax; pcbData
0x1800be57a  lea     rax, [rbp+DataBuffer]
0x1800be57e  mov     [rsp+70h+pvData], rax; pvData
0x1800be583  mov     [rsp+70h+pdwType], r12; pdwType
0x1800be588  mov     r9d, 10010h; dwFlags
0x1800be58e  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x1800be595  lea     rdx, aOsdataSoftware_0; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x1800be59c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800be5a3  call    cs:__imp_RegGetValueW
0x1800be5a9  test    eax, eax
0x1800be5ab  jz      short loc_1800BE5E8
0x1800be5ad  mov     [rbp+arg_18], edi
0x1800be5b0  lea     rax, [rbp+arg_18]
0x1800be5b4  mov     [rsp+70h+pcbData], rax; pcbData
0x1800be5b9  lea     rax, [rbp+DataBuffer]
0x1800be5bd  mov     [rsp+70h+pvData], rax; pvData
0x1800be5c2  mov     [rsp+70h+pdwType], r12; int
0x1800be5c7  mov     r9d, 20010010h; dwFlags
0x1800be5cd  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x1800be5d4  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800be5db  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800be5e2  call    cs:__imp_RegGetValueW
0x1800be5e8  cmp     dword ptr [rbp+DataBuffer], r12d
0x1800be5ec  jz      short loc_1800BE62F
0x1800be5ee  lea     r8, aForceautologon; "ForceAutoLogon"
0x1800be5f5  mov     rdx, r13; unsigned __int16 *
0x1800be5f8  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1800be5fd  mov     edi, eax
0x1800be5ff  test    eax, eax
0x1800be601  jns     short loc_1800BE62F
0x1800be603  mov     rcx, [rbp+38h]; this
0x1800be607  mov     r9d, eax; char *
0x1800be60a  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x1800be611  mov     edx, 4Fh ; 'O'; void *
0x1800be616  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be61b  nop
0x1800be61c  mov     [rbp+var_28], r12b
0x1800be620  lea     rcx, [rbp+var_30]
0x1800be624  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x1800be629  nop
0x1800be62a  jmp     loc_1800BE4FE
0x1800be62f  mov     r9, r14
0x1800be632  lea     r8, aDefaultusernam; "DefaultUserName"
0x1800be639  mov     rdx, r13
0x1800be63c  lea     rcx, aWinlogon; "Winlogon"
0x1800be643  call    cs:__imp_SetPersistedRegistryString
0x1800be649  mov     edi, eax
0x1800be64b  test    eax, eax
0x1800be64d  jle     short loc_1800BE658
0x1800be64f  movzx   edi, ax
0x1800be652  or      edi, 80070000h
0x1800be658  test    edi, edi
0x1800be65a  jns     short loc_1800BE688
0x1800be65c  mov     rcx, [rbp+38h]; this
0x1800be660  mov     r9d, edi; char *
0x1800be663  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x1800be66a  mov     edx, 52h ; 'R'; void *
0x1800be66f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be674  nop
0x1800be675  mov     [rbp+var_28], r12b
0x1800be679  lea     rcx, [rbp+var_30]
0x1800be67d  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x1800be682  nop
0x1800be683  jmp     loc_1800BE4FE
0x1800be688  xor     r9d, r9d
0x1800be68b  lea     r8, aIsconnectedaut; "IsConnectedAutoLogon"
0x1800be692  mov     rdx, r13
0x1800be695  lea     rcx, aWinlogon; "Winlogon"
0x1800be69c  call    cs:__imp_SetPersistedRegistryDWORD
0x1800be6a2  mov     edi, eax
0x1800be6a4  test    eax, eax
0x1800be6a6  jle     short loc_1800BE6B1
0x1800be6a8  movzx   edi, ax
0x1800be6ab  or      edi, 80070000h
0x1800be6b1  test    edi, edi
0x1800be6b3  jns     short loc_1800BE6E1
0x1800be6b5  mov     rcx, [rbp+38h]; this
0x1800be6b9  mov     r9d, edi; char *
0x1800be6bc  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x1800be6c3  mov     edx, 53h ; 'S'; void *
0x1800be6c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be6cd  nop
0x1800be6ce  mov     [rbp+var_28], r12b
0x1800be6d2  lea     rcx, [rbp+var_30]
0x1800be6d6  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x1800be6db  nop
0x1800be6dc  jmp     loc_1800BE4FE
0x1800be6e1  test    rsi, rsi
0x1800be6e4  jnz     loc_1800BE8B3
0x1800be6ea  mov     [rbp+DataBuffer], r12
0x1800be6ee  mov     [rbp+arg_18], r12d
0x1800be6f2  lea     rax, [rbp+arg_18]
0x1800be6f6  mov     [rsp+70h+pdwType], rax; int
0x1800be6fb  lea     r9, [rbp+DataBuffer]; unsigned __int8 **
0x1800be6ff  call    ?_EncryptOrDecryptSspiAuthenticationBuffer@@YAJ_NPEAEKPEAPEAEPEAK@Z; _EncryptOrDecryptSspiAuthenticationBuffer(bool,uchar *,ulong,uchar * *,ulong *)
0x1800be704  mov     edi, eax
0x1800be706  test    eax, eax
0x1800be708  jns     short loc_1800BE734
0x1800be70a  mov     rcx, [rbp+38h]; this
0x1800be70e  mov     r9d, eax; char *
0x1800be711  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x1800be718  lea     edx, [rsi+5Ch]; void *
0x1800be71b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be720  nop
0x1800be721  mov     [rbp+var_28], r12b
0x1800be725  lea     rcx, [rbp+var_30]
0x1800be729  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x1800be72e  nop
0x1800be72f  jmp     loc_1800BE4FE
0x1800be734  mov     eax, [rbp+arg_18]
0x1800be737  mov     [rbp+pDataIn.cbData], eax
0x1800be73a  xor     eax, eax
0x1800be73c  mov     dword ptr [rbp+pDataIn+4], eax
0x1800be73f  mov     rax, [rbp+DataBuffer]
0x1800be743  mov     [rbp+pDataIn.pbData], rax
0x1800be747  xorps   xmm0, xmm0
0x1800be74a  movups  xmmword ptr [rbp+pDataOut.cbData], xmm0
0x1800be74e  lea     rax, [rbp+pDataOut]
0x1800be752  mov     [rsp+70h+pcbData], rax; pDataOut
0x1800be757  mov     dword ptr [rsp+70h+pvData], ebx; dwFlags
0x1800be75b  mov     [rsp+70h+pdwType], r12; pPromptStruct
0x1800be760  xor     r9d, r9d; pvReserved
0x1800be763  xor     r8d, r8d; pOptionalEntropy
0x1800be766  xor     edx, edx; szDataDescr
0x1800be768  lea     rcx, [rbp+pDataIn]; pDataIn
0x1800be76c  call    cs:__imp_CryptProtectData
0x1800be772  test    eax, eax
0x1800be774  jnz     short loc_1800BE7C0
0x1800be776  mov     rcx, [rbp+38h]; this
0x1800be77a  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x1800be781  lea     edx, [rax+65h]; void *
0x1800be784  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800be789  mov     edi, eax
0x1800be78b  mov     edx, [rbp+arg_18]
0x1800be78e  mov     rcx, [rbp+DataBuffer]
0x1800be792  test    rdx, rdx
0x1800be795  jz      short loc_1800BE7A6
0x1800be797  mov     [rcx], r12b
0x1800be79a  add     rcx, rbx
0x1800be79d  sub     rdx, rbx
0x1800be7a0  jnz     short loc_1800BE797
0x1800be7a2  mov     rcx, [rbp+DataBuffer]; DataBuffer
0x1800be7a6  call    cs:__imp_SspiLocalFree
0x1800be7ac  nop
0x1800be7ad  mov     [rbp+var_28], r12b
0x1800be7b1  lea     rcx, [rbp+var_30]
0x1800be7b5  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x1800be7ba  nop
0x1800be7bb  jmp     loc_1800BE4FE
0x1800be7c0  mov     eax, [rbp+pDataOut.cbData]
0x1800be7c3  mov     dword ptr [rsp+70h+pdwType], eax; int
0x1800be7c7  mov     r9, [rbp+pDataOut.pbData]
0x1800be7cb  lea     r8, aConnectedcrede; "ConnectedCredentials"
0x1800be7d2  mov     rdx, r13
0x1800be7d5  mov     rcx, 0FFFFFFFF80000002h
0x1800be7dc  call    SHRegSetBinaryData
0x1800be7e1  mov     edi, eax
0x1800be7e3  test    eax, eax
0x1800be7e5  jns     short loc_1800BE857
0x1800be7e7  mov     rcx, [rbp+38h]; this
0x1800be7eb  mov     r9d, eax; char *
0x1800be7ee  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x1800be7f5  mov     edx, 6Ch ; 'l'; void *
0x1800be7fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be7ff  nop
0x1800be800  mov     edx, [rbp+pDataOut.cbData]
0x1800be803  mov     rcx, [rbp+pDataOut.pbData]
0x1800be807  test    rdx, rdx
0x1800be80a  jz      short loc_1800BE81B
0x1800be80c  mov     [rcx], r12b
0x1800be80f  add     rcx, rbx
0x1800be812  sub     rdx, rbx
0x1800be815  jnz     short loc_1800BE80C
0x1800be817  mov     rcx, [rbp+pDataOut.pbData]; hMem
0x1800be81b  call    cs:__imp_LocalFree
0x1800be821  nop
0x1800be822  mov     eax, [rbp+arg_18]
0x1800be825  mov     rcx, [rbp+DataBuffer]
0x1800be829  test    rax, rax
0x1800be82c  jz      short loc_1800BE83D
0x1800be82e  mov     [rcx], r12b
0x1800be831  add     rcx, rbx
0x1800be834  sub     rax, rbx
0x1800be837  jnz     short loc_1800BE82E
0x1800be839  mov     rcx, [rbp+DataBuffer]; DataBuffer
0x1800be83d  call    cs:__imp_SspiLocalFree
0x1800be843  nop
0x1800be844  mov     [rbp+var_28], r12b
0x1800be848  lea     rcx, [rbp+var_30]
0x1800be84c  call    _lambda_593abc42667a9590cca80463005afefb___operator__
0x1800be851  nop
0x1800be852  jmp     loc_1800BE4FE
0x1800be857  mov     eax, [rbp+pDataOut.cbData]
0x1800be85a  mov     rcx, [rbp+pDataOut.pbData]
0x1800be85e  test    rax, rax
0x1800be861  jz      short loc_1800BE872
0x1800be863  mov     [rcx], r12b
0x1800be866  add     rcx, rbx
0x1800be869  sub     rax, rbx
0x1800be86c  jnz     short loc_1800BE863
0x1800be86e  mov     rcx, [rbp+pDataOut.pbData]; hMem
0x1800be872  call    cs:__imp_LocalFree
0x1800be878  nop
0x1800be879  mov     eax, [rbp+arg_18]
0x1800be87c  mov     rcx, [rbp+DataBuffer]
0x1800be880  test    rax, rax
0x1800be883  jz      short loc_1800BE894
0x1800be885  mov     [rcx], r12b
  ... truncated ...
```
