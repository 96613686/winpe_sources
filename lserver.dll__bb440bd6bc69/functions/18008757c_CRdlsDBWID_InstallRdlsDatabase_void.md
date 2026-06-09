# CRdlsDBWID::InstallRdlsDatabase(void)

- ea: `0x18008757c`
- end: `0x180087d87`
- name: `?InstallRdlsDatabase@CRdlsDBWID@@IEAAJXZ`
- size: `2059`
- prototype: `__int64 __fastcall(CRdlsDBWID *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180088bd0`

## callees

- `0x180005665`
- `0x180077e9c`
- `0x180078a94`
- `0x180078be4`
- `0x18008625c`
- `0x180086464`
- `0x180086484`
- `0x180086754`
- `0x180086778`
- `0x180086d60`
- `0x18008757c`
- `0x180088430`
- `0x180088e68`
- `0x180096e04`
- `0x1800a0fb0`
- `0x1800a5010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800875e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18008776e`
- `OLEAUT32!__imp_SysFreeString` at `0x18008782b`
- `OLEAUT32!__imp_SysFreeString` at `0x180087896`
- `OLEAUT32!__imp_SysFreeString` at `0x1800878d5`
- `OLEAUT32!__imp_SysFreeString` at `0x180087a5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180087cb8`
- `OLEAUT32!__imp_SysFreeString` at `0x180087cc6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800875e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18008776e`
- `OLEAUT32!__imp_SysFreeString` at `0x18008782b`
- `OLEAUT32!__imp_SysFreeString` at `0x180087896`
- `OLEAUT32!__imp_SysFreeString` at `0x1800878d5`
- `OLEAUT32!__imp_SysFreeString` at `0x180087a5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180087cb8`
- `OLEAUT32!__imp_SysFreeString` at `0x180087cc6`

## string_xrefs

- `0x18008764d`: `] SET SINGLE_USER WITH ROLLBACK IMMEDIATE; DROP DATABASE[`
- `0x180087975`: `CREATE TABLE Rdls.RdlsVersion (     \n                [DataBaseVersion] INT NOT NULL,             \n                [TLSDomainSetupId] Rdls.SID,                \n                [TLSSetupId] Rdls.MaxString);`
- `0x180087947`: `CREATE TABLE Rdls.BackupSource (        \n                    [LastBackupTime] Rdls.FILETIME,             \n                    [LastRestoreTime] Rdls.FILETIME,            \n                    [DbFileName] Rdls.MaxPath,                  \n                    [ServerName] Rdls.MaxString,                \n                    [TLSDomainSetupId] Rdls.SID,                \n                    [TLSSetupId] Rdls.MaxString);`
- `0x180087919`: `CREATE TABLE Rdls.RdlsSecrets(                  \n                        [RdlsUUID]              Rdls.UUID NULL,         \n                        [RdlsName]              Rdls.FQDN PRIMARY KEY,  \n                        [PrimaryRdls]           INT,                    \n                        [RdlsServerIdBlob]      Rdls.LongBinary,        \n                        [RdlsRecentStatus]      Rdls.LastRunStatus,     \n                        [RdlsExchKeyBlob]       Rdls.LongBinary NULL,   \n      `
- `0x180087a2d`: `CREATE TABLE Rdls.IssuedLicense (               \n                        [InternalLicenseID] INT PRIMARY KEY NOT NULL,   \n                        [ExpireDate]        INT NOT NULL,               \n                        [FloppyBIOS]        INT NOT NULL,               \n                        [HarddiskSize]      INT NOT NULL,               \n                        [InternalKeyPackId] INT NOT NULL,               \n                        [IssueDate]         INT NOT NULL,               \n      `
- `0x1800879ff`: `CREATE TABLE Rdls.LicensedPack (                \n                        [InternalKeyPackId]     INT PRIMARY KEY NOT NULL, \n                        [ActivationDate]        INT NOT NULL,           \n                        [AgreementType]         Rdls.Byte NOT NULL,     \n                        [ChannelOfPurchase]     Rdls.Byte NOT NULL,     \n                        [ExpirationDate]        INT NOT NULL,           \n                        [KeyPackStatus]	        Rdls.Byte NOT NULL,     \n    `
- `0x1800879d1`: `CREATE TABLE Rdls.LICPACKDESCRECORD (           \n                        [InternalKeyPackId] INT PRIMARY KEY NOT NULL,   \n                        [LangId] INT NOT NULL,                          \n                        [LastModifyTime] Rdls.FILETIME NOT NULL,        \n                        [CompanyName] Rdls.MaxString,                   \n                        [EntryStatus] Rdls.Byte,                        \n                        [ProductDesc] Rdls.MaxString,                   \n      `
- `0x1800879a3`: `CREATE TABLE Rdls.WorkStorage (         \n                        [JobType] INT NOT NULL,                 \n                        [RestartTime] INT NOT NULL,             \n                        [ScheduledTime] INT NOT NULL,           \n                        [Data] Rdls.LongBinary);`
- `0x1800877af`: `] SET SINGLE_USER WITH ROLLBACK IMMEDIATE; `
- `0x180087af9`: `CreateOdbcExecutionContext, InstallRdlsDatabase`
- `0x180087a6d`: `CREATE SYNONYM RdlsSecrets FOR Rdls.RdlsSecrets;    \n    CREATE SYNONYM BackupSource FOR Rdls.BackupSource;                  \n    CREATE SYNONYM RdlsVersion FOR Rdls.RdlsVersion;                    \n    CREATE SYNONYM WorkStorage FOR Rdls.WorkStorage;                    \n    CREATE SYNONYM LICPACKDESCRECORD FOR Rdls.LICPACKDESCRECORD;        \n    CREATE SYNONYM LicensedPack FOR Rdls.LicensedPack;                  \n    CREATE SYNONYM IssuedLicense FOR Rdls.IssuedLicense;`
- `0x1800878e9`: `                                                          \n            CREATE TYPE [Rdls].[Byte] FROM TINYINT NULL;                      \n            CREATE TYPE [Rdls].[Word] FROM SMALLINT NULL;                     \n            CREATE TYPE [Rdls].[DWORD] FROM INT NULL;                         \n            CREATE TYPE [Rdls].[FILETIME] FROM BIGINT NULL;                   \n            CREATE TYPE [Rdls].[LastRunStatus] FROM [varbinary](20) NULL;     \n            CREATE TYPE [Rdls].[NetBiosN`
- `0x1800878a7`: `CREATE SCHEMA Rdls;`
- `0x180087bd4`: `Sequence KeypackIdCounter, InstallRdlsDatabase`
- `0x180087b75`: `CREATE SEQUENCE Rdls.KeypackIdCounter AS INT START WITH 1 INCREMENT BY 1`
- `0x180087b69`: `pOdbcExecContext->ExecuteSql, InstallRdlsDatabase`
- `0x180087c85`: `Index Creation, InstallRdlsDatabase`
- `0x180087c43`: `Sequence LicenseIdCounter, InstallRdlsDatabase`
- `0x180087be8`: `CREATE SEQUENCE [Rdls].[LicenseIdCounter] AS INT START WITH 1 INCREMENT BY 1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRdlsDBWID::InstallRdlsDatabase(const unsigned __int16 **this)
{
  const unsigned __int16 **v2; // rbx
  __int64 v3; // rdi
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // r8
  OLECHAR *v8; // rax
  BSTR *p_bstrString; // rsi
  unsigned __int16 **v10; // r15
  char *v11; // r12
  char *v12; // rax
  char *v13; // r13
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // r8
  OLECHAR *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r8
  unsigned __int16 *v21; // rax
  __int64 v22; // r8
  OLECHAR *v23; // rax
  __int64 v24; // r8
  OLECHAR *v25; // rax
  char *v26; // rbx
  char *v27; // rbx
  char *v28; // rbx
  char *v29; // rbx
  char *v30; // rbx
  char *v31; // rbx
  char *v32; // rbx
  __int64 v33; // r8
  int v34; // r9d
  OLECHAR *v35; // rax
  unsigned __int16 *v36; // rcx
  int RdlsDBIndexes; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v39; // edx
  const char *v40; // r8
  unsigned int v41; // esi
  unsigned int v42; // r15d
  __int64 (__fastcall *v43)(struct IOdbcExecutionContext *, BSTR); // rax
  CRdlsDBWID *v44; // rcx
  __int64 v45; // r8
  int v47; // [rsp+30h] [rbp-D8h]
  OLECHAR *v48; // [rsp+38h] [rbp-D0h] BYREF
  char *v49; // [rsp+40h] [rbp-C8h] BYREF
  struct IOdbcExecutionContext *v50; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v51; // [rsp+50h] [rbp-B8h]
  char *v52; // [rsp+58h] [rbp-B0h]
  char *v53; // [rsp+60h] [rbp-A8h]
  char *v54; // [rsp+68h] [rbp-A0h]
  char *v55; // [rsp+70h] [rbp-98h]
  char *v56; // [rsp+78h] [rbp-90h]
  char *v57; // [rsp+80h] [rbp-88h]
  char *v58; // [rsp+88h] [rbp-80h]
  char v59[8]; // [rsp+90h] [rbp-78h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int16 *v61; // [rsp+A0h] [rbp-68h] BYREF
  char v62; // [rsp+A8h] [rbp-60h] BYREF
  char v63; // [rsp+B0h] [rbp-58h] BYREF
  char v64; // [rsp+B8h] [rbp-50h] BYREF
  char v65; // [rsp+C0h] [rbp-48h] BYREF
  char v66; // [rsp+C8h] [rbp-40h] BYREF
  char v67; // [rsp+D0h] [rbp-38h] BYREF
  char v68; // [rsp+D8h] [rbp-30h] BYREF
  char v69; // [rsp+E0h] [rbp-28h] BYREF
  char v70; // [rsp+E8h] [rbp-20h] BYREF
  char v71; // [rsp+F0h] [rbp-18h] BYREF
  char v72; // [rsp+F8h] [rbp-10h] BYREF
  char v73; // [rsp+100h] [rbp-8h] BYREF

  memset_0(&bstrString, 0, 0x90u);
  v48 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v59);
  v2 = this + 2;
  v3 = -1;
  if ( *((_DWORD *)this + 2) )
  {
    LODWORD(v51) = 12;
    p_bstrString = &bstrString;
    v10 = &v61;
    v11 = &v62;
    v49 = &v63;
    v52 = &v64;
    v53 = &v65;
    v54 = &v66;
    v55 = &v67;
    v56 = &v68;
    v57 = &v69;
    v12 = &v70;
    v13 = &v71;
  }
  else
  {
    SysFreeString(0);
    v48 = 0;
    v4 = -1;
    do
      ++v4;
    while ( aIfExistsSelect[v4] );
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, L"IF EXISTS(SELECT name FROM sys.databases WHERE name = '", v4);
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, *v2);
    v5 = -1;
    do
      ++v5;
    while ( aBeginAlterData[v5] );
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, L"') BEGIN ALTER DATABASE[", v5);
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, *v2);
    v6 = -1;
    do
      ++v6;
    while ( aSetSingleUserW[v6] );
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, L"] SET SINGLE_USER WITH ROLLBACK IMMEDIATE; DROP DATABASE[", v6);
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, *v2);
    v7 = -1;
    do
      ++v7;
    while ( aEnd[v7] );
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, L"] END", v7);
    v8 = v48;
    v48 = 0;
    bstrString = v8;
    v61 = CRdlsDBWID::PrepareDBCreateSqlCmd((CRdlsDBWID *)this);
    LODWORD(v51) = 14;
    p_bstrString = (BSTR *)&v62;
    v10 = (unsigned __int16 **)&v63;
    v11 = &v64;
    v49 = &v65;
    v52 = &v66;
    v53 = &v67;
    v54 = &v68;
    v55 = &v69;
    v56 = &v70;
    v57 = &v71;
    v12 = &v72;
    v13 = &v73;
  }
  v58 = v12;
  SysFreeString(0);
  v48 = 0;
  v14 = -1;
  do
    ++v14;
  while ( aAlterDatabase_0[v14] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, L"ALTER DATABASE [", v14);
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, *v2);
  v15 = -1;
  do
    ++v15;
  while ( aSetSingleUserW_0[v15] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, L"] SET SINGLE_USER WITH ROLLBACK IMMEDIATE; ", v15);
  v16 = -1;
  do
    ++v16;
  while ( aAlterDatabase_0[v16] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, L"ALTER DATABASE [", v16);
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, *v2);
  v17 = -1;
  do
    ++v17;
  while ( aSetAllowSnapsh[v17] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, L"] SET ALLOW_SNAPSHOT_ISOLATION ON;", v17);
  v18 = v48;
  v48 = 0;
  *p_bstrString = v18;
  SysFreeString(0);
  v48 = 0;
  v19 = -1;
  do
    ++v19;
  while ( aUse[v19] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, L"USE ", v19);
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, *v2);
  v20 = -1;
  do
    ++v20;
  while ( asc_1800C145C[v20] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, L";", v20);
  v21 = v48;
  v48 = 0;
  *v10 = v21;
  SysFreeString(0);
  v48 = 0;
  v22 = -1;
  do
    ++v22;
  while ( aCreateSchemaRd[v22] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, L"CREATE SCHEMA Rdls;", v22);
  v23 = v48;
  v48 = 0;
  *(_QWORD *)v11 = v23;
  SysFreeString(0);
  v48 = 0;
  v24 = -1;
  do
    ++v24;
  while ( asc_1800C4450[v24] );
  ATL::CComBSTR::Append(
    (ATL::CComBSTR *)&v48,
    L"                                                          \n"
     "            CREATE TYPE [Rdls].[Byte] FROM TINYINT NULL;                      \n"
     "            CREATE TYPE [Rdls].[Word] FROM SMALLINT NULL;                     \n"
     "            CREATE TYPE [Rdls].[DWORD] FROM INT NULL;                         \n"
     "            CREATE TYPE [Rdls].[FILETIME] FROM BIGINT NULL;                   \n"
     "            CREATE TYPE [Rdls].[LastRunStatus] FROM [varbinary](20) NULL;     \n"
     "            CREATE TYPE [Rdls].[NetBiosName] FROM [nvarchar](15) NULL;        \n"
     "            CREATE TYPE [Rdls].[MachineName] FROM [nvarchar](32) NULL;        \n"
     "            CREATE TYPE [Rdls].[UUID] FROM [nvarchar](49) NULL;              \n"
     "            CREATE TYPE [Rdls].[SID] FROM [varbinary](85) NULL;               \n"
     "            CREATE TYPE [Rdls].[FQDN] FROM [nvarchar](256) NULL;              \n"
     "            CREATE TYPE [Rdls].[UserName] FROM [nvarchar](256) NULL;          \n"
     "            CREATE TYPE [Rdls].[PropertyName] FROM [nvarchar](256) NULL;      \n"
     "            CREATE TYPE [Rdls].[PropertyValue] FROM [nvarchar](256) NULL;     \n"
     "            CREATE TYPE [Rdls].[MaxString] FROM [nvarchar](256) NULL;         \n"
     "            CREATE TYPE [Rdls].[MaxPath] FROM [nvarchar](261) NULL;           \n"
     "            CREATE TYPE [Rdls].[LongText] FROM [nvarchar](MAX) NULL;          \n"
     "            CREATE TYPE [Rdls].[LongBinary] FROM [varbinary](MAX) NULL;       \n"
     "        ",
    v24);
  v25 = v48;
  v48 = 0;
  *(_QWORD *)v49 = v25;
  ATL::CComBSTR::CComBSTR(
    (ATL::CComBSTR *)&v49,
    L"CREATE TABLE Rdls.RdlsSecrets(                  \n"
     "                        [RdlsUUID]              Rdls.UUID NULL,         \n"
     "                        [RdlsName]              Rdls.FQDN PRIMARY KEY,  \n"
     "                        [PrimaryRdls]           INT,                    \n"
     "                        [RdlsServerIdBlob]      Rdls.LongBinary,        \n"
     "                        [RdlsRecentStatus]      Rdls.LastRunStatus,     \n"
     "                        [RdlsExchKeyBlob]       Rdls.LongBinary NULL,   \n"
     "                        [RdlsSignKeyBlob]       Rdls.LongBinary NULL,   \n"
     "                        [RdlsExchangeCHX509CertChainBlob]   Rdls.LongBinary NULL,   \n"
     "                        [RdlsSignatureCHX509CertChainBlob]  Rdls.LongBinary NULL,   \n"
     "                        [RdlsSecretsHash]                   Rdls.LongBinary);");
  v26 = v49;
  v49 = 0;
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v49);
  *(_QWORD *)v52 = v26;
  ATL::CComBSTR::CComBSTR(
    (ATL::CComBSTR *)&v49,
    L"CREATE TABLE Rdls.BackupSource (        \n"
     "                    [LastBackupTime] Rdls.FILETIME,             \n"
     "                    [LastRestoreTime] Rdls.FILETIME,            \n"
     "                    [DbFileName] Rdls.MaxPath,                  \n"
     "                    [ServerName] Rdls.MaxString,                \n"
     "                    [TLSDomainSetupId] Rdls.SID,                \n"
     "                    [TLSSetupId] Rdls.MaxString);");
  v27 = v49;
  v49 = 0;
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v49);
  *(_QWORD *)v53 = v27;
  ATL::CComBSTR::CComBSTR(
    (ATL::CComBSTR *)&v49,
    L"CREATE TABLE Rdls.RdlsVersion (     \n"
     "                [DataBaseVersion] INT NOT NULL,             \n"
     "                [TLSDomainSetupId] Rdls.SID,                \n"
     "                [TLSSetupId] Rdls.MaxString);");
  v28 = v49;
  v49 = 0;
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v49);
  *(_QWORD *)v54 = v28;
  ATL::CComBSTR::CComBSTR(
    (ATL::CComBSTR *)&v49,
    L"CREATE TABLE Rdls.WorkStorage (         \n"
     "                        [JobType] INT NOT NULL,                 \n"
     "                        [RestartTime] INT NOT NULL,             \n"
     "                        [ScheduledTime] INT NOT NULL,           \n"
     "                        [Data] Rdls.LongBinary);");
  v29 = v49;
  v49 = 0;
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v49);
  *(_QWORD *)v55 = v29;
  ATL::CComBSTR::CComBSTR(
    (ATL::CComBSTR *)&v49,
    L"CREATE TABLE Rdls.LICPACKDESCRECORD (           \n"
     "                        [InternalKeyPackId] INT PRIMARY KEY NOT NULL,   \n"
     "                        [LangId] INT NOT NULL,                          \n"
     "                        [LastModifyTime] Rdls.FILETIME NOT NULL,        \n"
     "                        [CompanyName] Rdls.MaxString,                   \n"
     "                        [EntryStatus] Rdls.Byte,                        \n"
     "                        [ProductDesc] Rdls.MaxString,                   \n"
     "                        [ProductName] Rdls.MaxString);");
  v30 = v49;
  v49 = 0;
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v49);
  *(_QWORD *)v56 = v30;
  ATL::CComBSTR::CComBSTR(
    (ATL::CComBSTR *)&v49,
    L"CREATE TABLE Rdls.LicensedPack (                \n"
     "                        [InternalKeyPackId]     INT PRIMARY KEY NOT NULL, \n"
     "                        [ActivationDate]        INT NOT NULL,           \n"
     "                        [AgreementType]         Rdls.Byte NOT NULL,     \n"
     "                        [ChannelOfPurchase]     Rdls.Byte NOT NULL,     \n"
     "                        [ExpirationDate]        INT NOT NULL,           \n"
     "                        [KeyPackStatus]\t        Rdls.Byte NOT NULL,     \n"
     "                        [LastModifyTime]        Rdls.FILETIME NOT NULL, \n"
     "                        [LicenseType]           Rdls.Byte NOT NULL,     \n"
     "                        [NextSerialNumber]      INT NOT NULL,           \n"
     "                        [NumberLicenses]        INT NOT NULL,           \n"
     "                        [PlatformType]          INT NOT NULL,           \n"
     "                        [ProductFlag]           INT NOT NULL,           \n"
     "                        [ProductMajorVersion]   Rdls.Word NOT NULL,     \n"
     "                        [ProductMinorVersion]   Rdls.Word NOT NULL,     \n"
     "                        [TotalLicenses]         INT NOT NULL,           \n"
     "                        [BeginSerialNumber]     Rdls.MaxString,         \n"
     "                        [CompanyName]           Rdls.MaxString,       \n"
     "                        [DomainName]            Rdls.MaxString,       \n"
     "                        [EntryStatus]           Rdls.Byte,              \n"
     "                        [KeyPackAttribute]      INT,                    \n"
     "                        [LPID]                  Rdls.MaxString,       \n"
     "                        [ProductID]             Rdls.MaxString,       \n"
     "                        [ServerName]            Rdls.MaxString,       \n"
     "                        [TLSSetupId]            Rdls.MaxString);");
  v31 = v49;
  v49 = 0;
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v49);
  *(_QWORD *)v57 = v31;
  ATL::CComBSTR::CComBSTR(
    (ATL::CComBSTR *)&v49,
    L"CREATE TABLE Rdls.IssuedLicense (               \n"
     "                        [InternalLicenseID] INT PRIMARY KEY NOT NULL,   \n"
     "                        [ExpireDate]        INT NOT NULL,               \n"
     "                        [FloppyBIOS]        INT NOT NULL,               \n"
     "                        [HarddiskSize]      INT NOT NULL,               \n"
     "                        [InternalKeyPackId] INT NOT NULL,               \n"
     "                        [IssueDate]         INT NOT NULL,               \n"
     "                        [LastModifyTime]    Rdls.FILETIME NOT NULL,     \n"
     "                        [LicenseStatus]     Rdls.Byte NOT NULL,         \n"
     "                        [MatchHint1]        float NOT NULL,             \n"
     "                        [NumLicenses]       INT NOT NULL,               \n"
     "                        [RAMSize]           INT NOT NULL,               \n"
     "                        [SystemBIOS]        INT NOT NULL,               \n"
     "                        [VideoBIOS]         INT NOT NULL,               \n"
     "                        [EntryStatus]       Rdls.Byte,                  \n"
     "                        [KeyPackLicenseId]  INT,                        \n"
     "                        [MachineName]       Rdls.MachineName,           \n"
     "                        [UserName]          Rdls.UserName);");
  v32 = v49;
  v49 = 0;
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v49);
  *(_QWORD *)v58 = v32;
  SysFreeString(0);
  v48 = 0;
  v33 = -1;
  do
    ++v33;
  while ( aCreateSynonymR[v33] );
  ATL::CComBSTR::Append(
    (ATL::CComBSTR *)&v48,
    L"CREATE SYNONYM RdlsSecrets FOR Rdls.RdlsSecrets;    \n"
     "    CREATE SYNONYM BackupSource FOR Rdls.BackupSource;                  \n"
     "    CREATE SYNONYM RdlsVersion FOR Rdls.RdlsVersion;                    \n"
     "    CREATE SYNONYM WorkStorage FOR Rdls.WorkStorage;                    \n"
     "    CREATE SYNONYM LICPACKDESCRECORD FOR Rdls.LICPACKDESCRECORD;        \n"
     "    CREATE SYNONYM LicensedPack FOR Rdls.LicensedPack;                  \n"
     "    CREATE SYNONYM IssuedLicense FOR Rdls.IssuedLicense;",
    v33);
  v35 = v48;
  v48 = 0;
  *(_QWORD *)v13 = v35;
  v50 = 0;
  if ( *((_DWORD *)this + 2) )
    v36 = (unsigned __int16 *)this[5];
  else
    v36 = (unsigned __int16 *)this[4];
  RdlsDBIndexes = CreateOdbcExecutionContext(v36, &v50, 32, v34);
  if ( RdlsDBIndexes >= 0 )
  {
    v41 = 0;
    v42 = v51;
    while ( 1 )
    {
      v43 = *(__int64 (__fastcall **)(struct IOdbcExecutionContext *, BSTR))(*(_QWORD *)v50 + 112LL);
      if ( v41 >= v42 )
        break;
      RdlsDBIndexes = v43(v50, (&bstrString)[v41]);
      if ( RdlsDBIndexes < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v39 = 13;
          v40 = "pOdbcExecContext->ExecuteSql, InstallRdlsDatabase";
          goto LABEL_61;
        }
        goto LABEL_62;
      }
      ++v41;
    }
    v43(v50, L"CREATE SEQUENCE Rdls.KeypackIdCounter AS INT START WITH 1 INCREMENT BY 1");
    RdlsDBIndexes = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, const wchar_t *))(*(_QWORD *)v50 + 112LL))(
                      v50,
                      L"ALTER SEQUENCE Rdls.KeypackIdCounter RESTART WITH 1;");
    if ( RdlsDBIndexes >= 0 )
    {
      (*(void (__fastcall **)(struct IOdbcExecutionContext *, const wchar_t *))(*(_QWORD *)v50 + 112LL))(
        v50,
        L"CREATE SEQUENCE [Rdls].[LicenseIdCounter] AS INT START WITH 1 INCREMENT BY 1");
      RdlsDBIndexes = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, const wchar_t *))(*(_QWORD *)v50 + 112LL))(
                        v50,
                        L"ALTER SEQUENCE [Rdls].[LicenseIdCounter] RESTART WITH 1;");
      if ( RdlsDBIndexes >= 0 )
      {
        RdlsDBIndexes = CRdlsDBWID::CreateRdlsDBIndexes(v44, v50);
        if ( RdlsDBIndexes < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v39 = 16;
          v40 = "Index Creation, InstallRdlsDatabase";
          goto LABEL_61;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v39 = 15;
        v40 = "Sequence LicenseIdCounter, InstallRdlsDatabase";
        goto LABEL_61;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v39 = 14;
      v40 = "Sequence KeypackIdCounter, InstallRdlsDatabase";
      goto LABEL_61;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v39 = 12;
    v40 = "CreateOdbcExecutionContext, InstallRdlsDatabase";
LABEL_61:
    v47 = RdlsDBIndexes;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v39,
      (unsigned int)WPP_c9aedbd3feee3e98c50752067cbb8264_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v40,
      v47,
      v48);
  }
LABEL_62:
  if ( bstrString )
    SysFreeString(bstrString);
  SysFreeString(0);
  v48 = 0;
  v45 = -1;
  do
    ++v45;
  while ( aUseMasterAlter[v45] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, L"USE master; ALTER DATABASE[", v45);
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, this[2]);
  do
    ++v3;
  while ( aSetMultiUser[v3] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v48, L"] SET MULTI_USER; ", v3);
  (*(void (__fastcall **)(struct IOdbcExecutionContext *, OLECHAR *))(*(_QWORD *)v50 + 112LL))(v50, v48);
  ComPlainSmartPtr<IOdbcExecutionContext>::~ComPlainSmartPtr<IOdbcExecutionContext>(&v50);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v59);
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v48);
  return (unsigned int)RdlsDBIndexes;
}

```

## disassembly

```asm
0x18008757c  mov     rax, rsp
0x18008757f  mov     [rax+10h], rbx
0x180087583  mov     [rax+18h], rsi
0x180087587  mov     [rax+20h], rdi
0x18008758b  push    rbp
0x18008758c  push    r12
0x18008758e  push    r13
0x180087590  push    r14
0x180087592  push    r15
0x180087594  lea     rbp, [rax-58h]
0x180087598  sub     rsp, 130h
0x18008759f  mov     rax, cs:__security_cookie
0x1800875a6  xor     rax, rsp
0x1800875a9  mov     [rbp+50h+var_30], rax
0x1800875ad  mov     r14, rcx
0x1800875b0  xor     edx, edx; Val
0x1800875b2  mov     r8d, 90h; Size
0x1800875b8  lea     rcx, [rbp+50h+bstrString]; void *
0x1800875bc  call    memset_0
0x1800875c1  xor     esi, esi
0x1800875c3  mov     [rsp+150h+var_120], rsi
0x1800875c8  lea     rcx, [rbp+50h+var_C8]
0x1800875cc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800875d1  nop
0x1800875d2  lea     rbx, [r14+10h]
0x1800875d6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800875da  cmp     [r14+8], esi
0x1800875de  jnz     loc_18008770D
0x1800875e4  xor     ecx, ecx; bstrString
0x1800875e6  call    cs:__imp_SysFreeString
0x1800875ed  nop     dword ptr [rax+rax+00h]
0x1800875f2  mov     [rsp+150h+var_120], rsi
0x1800875f7  lea     rdx, aIfExistsSelect; "IF EXISTS(SELECT name FROM sys.database"...
0x1800875fe  mov     r8, rdi
0x180087601  inc     r8; int
0x180087604  cmp     [rdx+r8*2], si
0x180087609  jnz     short loc_180087601
0x18008760b  lea     rcx, [rsp+150h+var_120]; this
0x180087610  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180087615  mov     rdx, [rbx]; unsigned __int16 *
0x180087618  lea     rcx, [rsp+150h+var_120]; this
0x18008761d  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180087622  lea     rdx, aBeginAlterData; "') BEGIN ALTER DATABASE["
0x180087629  mov     r8, rdi
0x18008762c  inc     r8; int
0x18008762f  cmp     [rdx+r8*2], si
0x180087634  jnz     short loc_18008762C
0x180087636  lea     rcx, [rsp+150h+var_120]; this
0x18008763b  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180087640  mov     rdx, [rbx]; unsigned __int16 *
0x180087643  lea     rcx, [rsp+150h+var_120]; this
0x180087648  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18008764d  lea     rdx, aSetSingleUserW; "] SET SINGLE_USER WITH ROLLBACK IMMEDIA"...
0x180087654  mov     r8, rdi
0x180087657  inc     r8; int
0x18008765a  cmp     [rdx+r8*2], si
0x18008765f  jnz     short loc_180087657
0x180087661  lea     rcx, [rsp+150h+var_120]; this
0x180087666  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008766b  mov     rdx, [rbx]; unsigned __int16 *
0x18008766e  lea     rcx, [rsp+150h+var_120]; this
0x180087673  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180087678  lea     rdx, aEnd; "] END"
0x18008767f  mov     r8, rdi
0x180087682  inc     r8; int
0x180087685  cmp     [rdx+r8*2], si
0x18008768a  jnz     short loc_180087682
0x18008768c  lea     rcx, [rsp+150h+var_120]; this
0x180087691  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180087696  mov     rax, [rsp+150h+var_120]
0x18008769b  mov     [rsp+150h+var_120], rsi
0x1800876a0  mov     [rbp+50h+bstrString], rax
0x1800876a4  mov     rcx, r14; this
0x1800876a7  call    ?PrepareDBCreateSqlCmd@CRdlsDBWID@@IEAAPEAGXZ; CRdlsDBWID::PrepareDBCreateSqlCmd(void)
0x1800876ac  mov     [rbp+50h+var_B8], rax
0x1800876b0  mov     dword ptr [rsp+150h+var_108], 0Eh
0x1800876b8  lea     rsi, [rbp+50h+var_B0]
0x1800876bc  lea     r15, [rbp+50h+var_A8]
0x1800876c0  lea     r12, [rbp+50h+var_A0]
0x1800876c4  lea     rax, [rbp+50h+var_98]
0x1800876c8  mov     [rsp+150h+var_118], rax
0x1800876cd  lea     rax, [rbp+50h+var_90]
0x1800876d1  mov     [rsp+150h+var_100], rax
0x1800876d6  lea     rax, [rbp+50h+var_88]
0x1800876da  mov     [rsp+150h+var_F8], rax
0x1800876df  lea     rax, [rbp+50h+var_80]
0x1800876e3  mov     [rsp+150h+var_F0], rax
0x1800876e8  lea     rax, [rbp+50h+var_78]
0x1800876ec  mov     [rsp+150h+var_E8], rax
0x1800876f1  lea     rax, [rbp+50h+var_70]
0x1800876f5  mov     [rsp+150h+var_E0], rax
0x1800876fa  lea     rax, [rbp+50h+var_68]
0x1800876fe  mov     [rsp+150h+var_D8], rax
0x180087703  lea     rax, [rbp+50h+var_60]
0x180087707  lea     r13, [rbp+50h+var_58]
0x18008770b  jmp     short loc_180087768
0x18008770d  mov     dword ptr [rsp+150h+var_108], 0Ch
0x180087715  lea     rsi, [rbp+50h+bstrString]
0x180087719  lea     r15, [rbp+50h+var_B8]
0x18008771d  lea     r12, [rbp+50h+var_B0]
0x180087721  lea     rax, [rbp+50h+var_A8]
0x180087725  mov     [rsp+150h+var_118], rax
0x18008772a  lea     rax, [rbp+50h+var_A0]
0x18008772e  mov     [rsp+150h+var_100], rax
0x180087733  lea     rax, [rbp+50h+var_98]
0x180087737  mov     [rsp+150h+var_F8], rax
0x18008773c  lea     rax, [rbp+50h+var_90]
0x180087740  mov     [rsp+150h+var_F0], rax
0x180087745  lea     rax, [rbp+50h+var_88]
0x180087749  mov     [rsp+150h+var_E8], rax
0x18008774e  lea     rax, [rbp+50h+var_80]
0x180087752  mov     [rsp+150h+var_E0], rax
0x180087757  lea     rax, [rbp+50h+var_78]
0x18008775b  mov     [rsp+150h+var_D8], rax
0x180087760  lea     rax, [rbp+50h+var_70]
0x180087764  lea     r13, [rbp+50h+var_68]
0x180087768  mov     [rbp+50h+var_D0], rax
0x18008776c  xor     ecx, ecx; bstrString
0x18008776e  call    cs:__imp_SysFreeString
0x180087775  nop     dword ptr [rax+rax+00h]
0x18008777a  xor     eax, eax
0x18008777c  mov     [rsp+150h+var_120], rax
0x180087781  lea     rcx, aAlterDatabase_0; "ALTER DATABASE ["
0x180087788  mov     r8, rdi
0x18008778b  inc     r8; int
0x18008778e  cmp     [rcx+r8*2], ax
0x180087793  jnz     short loc_18008778B
0x180087795  mov     rdx, rcx; unsigned __int16 *
0x180087798  lea     rcx, [rsp+150h+var_120]; this
0x18008779d  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800877a2  mov     rdx, [rbx]; unsigned __int16 *
0x1800877a5  lea     rcx, [rsp+150h+var_120]; this
0x1800877aa  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800877af  lea     rdx, aSetSingleUserW_0; "] SET SINGLE_USER WITH ROLLBACK IMMEDIA"...
0x1800877b6  mov     r8, rdi
0x1800877b9  xor     ecx, ecx
0x1800877bb  inc     r8; int
0x1800877be  cmp     [rdx+r8*2], cx
0x1800877c3  jnz     short loc_1800877BB
0x1800877c5  lea     rcx, [rsp+150h+var_120]; this
0x1800877ca  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800877cf  mov     r8, rdi
0x1800877d2  xor     eax, eax
0x1800877d4  lea     rdx, aAlterDatabase_0; "ALTER DATABASE ["
0x1800877db  inc     r8; int
0x1800877de  cmp     [rdx+r8*2], ax
0x1800877e3  jnz     short loc_1800877DB
0x1800877e5  lea     rcx, [rsp+150h+var_120]; this
0x1800877ea  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800877ef  mov     rdx, [rbx]; unsigned __int16 *
0x1800877f2  lea     rcx, [rsp+150h+var_120]; this
0x1800877f7  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800877fc  lea     rdx, aSetAllowSnapsh; "] SET ALLOW_SNAPSHOT_ISOLATION ON;"
0x180087803  mov     r8, rdi
0x180087806  xor     eax, eax
0x180087808  inc     r8; int
0x18008780b  cmp     [rdx+r8*2], ax
0x180087810  jnz     short loc_180087808
0x180087812  lea     rcx, [rsp+150h+var_120]; this
0x180087817  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008781c  mov     rax, [rsp+150h+var_120]
0x180087821  xor     ecx, ecx; bstrString
0x180087823  mov     [rsp+150h+var_120], rcx
0x180087828  mov     [rsi], rax
0x18008782b  call    cs:__imp_SysFreeString
0x180087832  nop     dword ptr [rax+rax+00h]
0x180087837  xor     esi, esi
0x180087839  mov     [rsp+150h+var_120], rsi
0x18008783e  lea     rdx, aUse; "USE "
0x180087845  mov     r8, rdi
0x180087848  inc     r8; int
0x18008784b  cmp     [rdx+r8*2], si
0x180087850  jnz     short loc_180087848
0x180087852  lea     rcx, [rsp+150h+var_120]; this
0x180087857  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008785c  mov     rdx, [rbx]; unsigned __int16 *
0x18008785f  lea     rcx, [rsp+150h+var_120]; this
0x180087864  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180087869  lea     rdx, asc_1800C145C; ";"
0x180087870  mov     r8, rdi
0x180087873  inc     r8; int
0x180087876  cmp     [rdx+r8*2], si
0x18008787b  jnz     short loc_180087873
0x18008787d  lea     rcx, [rsp+150h+var_120]; this
0x180087882  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180087887  mov     rax, [rsp+150h+var_120]
0x18008788c  mov     [rsp+150h+var_120], rsi
0x180087891  mov     [r15], rax
0x180087894  xor     ecx, ecx; bstrString
0x180087896  call    cs:__imp_SysFreeString
0x18008789d  nop     dword ptr [rax+rax+00h]
0x1800878a2  mov     [rsp+150h+var_120], rsi
0x1800878a7  lea     rdx, aCreateSchemaRd; "CREATE SCHEMA Rdls;"
0x1800878ae  mov     r8, rdi
0x1800878b1  inc     r8; int
0x1800878b4  cmp     [rdx+r8*2], si
0x1800878b9  jnz     short loc_1800878B1
0x1800878bb  lea     rcx, [rsp+150h+var_120]; this
0x1800878c0  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800878c5  mov     rax, [rsp+150h+var_120]
0x1800878ca  mov     [rsp+150h+var_120], rsi
0x1800878cf  mov     [r12], rax
0x1800878d3  xor     ecx, ecx; bstrString
0x1800878d5  call    cs:__imp_SysFreeString
0x1800878dc  nop     dword ptr [rax+rax+00h]
0x1800878e1  xor     r12d, r12d
0x1800878e4  mov     [rsp+150h+var_120], r12
0x1800878e9  lea     rdx, asc_1800C4450; "                                       "...
0x1800878f0  mov     r8, rdi
0x1800878f3  inc     r8; int
0x1800878f6  cmp     [rdx+r8*2], r12w
0x1800878fb  jnz     short loc_1800878F3
0x1800878fd  lea     rcx, [rsp+150h+var_120]; this
0x180087902  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180087907  mov     rax, [rsp+150h+var_120]
0x18008790c  mov     [rsp+150h+var_120], r12
0x180087911  mov     rcx, [rsp+150h+var_118]
0x180087916  mov     [rcx], rax
0x180087919  lea     rdx, aCreateTableRdl_3; "CREATE TABLE Rdls.RdlsSecrets(         "...
0x180087920  lea     rcx, [rsp+150h+var_118]; this
0x180087925  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18008792a  nop
0x18008792b  mov     rbx, [rsp+150h+var_118]
0x180087930  mov     [rsp+150h+var_118], r12
0x180087935  lea     rcx, [rsp+150h+var_118]; this
0x18008793a  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18008793f  mov     rax, [rsp+150h+var_100]
0x180087944  mov     [rax], rbx
0x180087947  lea     rdx, aCreateTableRdl_1; "CREATE TABLE Rdls.BackupSource (       "...
0x18008794e  lea     rcx, [rsp+150h+var_118]; this
0x180087953  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180087958  nop
0x180087959  mov     rbx, [rsp+150h+var_118]
0x18008795e  mov     [rsp+150h+var_118], r12
0x180087963  lea     rcx, [rsp+150h+var_118]; this
0x180087968  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18008796d  mov     rax, [rsp+150h+var_F8]
0x180087972  mov     [rax], rbx
0x180087975  lea     rdx, aCreateTableRdl_5; "CREATE TABLE Rdls.RdlsVersion (     \n "...
0x18008797c  lea     rcx, [rsp+150h+var_118]; this
0x180087981  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180087986  nop
0x180087987  mov     rbx, [rsp+150h+var_118]
0x18008798c  mov     [rsp+150h+var_118], r12
0x180087991  lea     rcx, [rsp+150h+var_118]; this
0x180087996  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18008799b  mov     rax, [rsp+150h+var_F0]
0x1800879a0  mov     [rax], rbx
0x1800879a3  lea     rdx, aCreateTableRdl; "CREATE TABLE Rdls.WorkStorage (        "...
0x1800879aa  lea     rcx, [rsp+150h+var_118]; this
0x1800879af  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800879b4  nop
0x1800879b5  mov     rbx, [rsp+150h+var_118]
0x1800879ba  mov     [rsp+150h+var_118], r12
0x1800879bf  lea     rcx, [rsp+150h+var_118]; this
0x1800879c4  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x1800879c9  mov     rax, [rsp+150h+var_E8]
0x1800879ce  mov     [rax], rbx
0x1800879d1  lea     rdx, aCreateTableRdl_4; "CREATE TABLE Rdls.LICPACKDESCRECORD (  "...
0x1800879d8  lea     rcx, [rsp+150h+var_118]; this
0x1800879dd  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800879e2  nop
0x1800879e3  mov     rbx, [rsp+150h+var_118]
0x1800879e8  mov     [rsp+150h+var_118], r12
0x1800879ed  lea     rcx, [rsp+150h+var_118]; this
0x1800879f2  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x1800879f7  mov     rax, [rsp+150h+var_E0]
0x1800879fc  mov     [rax], rbx
0x1800879ff  lea     rdx, aCreateTableRdl_2; "CREATE TABLE Rdls.LicensedPack (       "...
0x180087a06  lea     rcx, [rsp+150h+var_118]; this
0x180087a0b  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180087a10  nop
0x180087a11  mov     rbx, [rsp+150h+var_118]
0x180087a16  mov     [rsp+150h+var_118], r12
0x180087a1b  lea     rcx, [rsp+150h+var_118]; this
0x180087a20  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x180087a25  mov     rax, [rsp+150h+var_D8]
0x180087a2a  mov     [rax], rbx
0x180087a2d  lea     rdx, aCreateTableRdl_0; "CREATE TABLE Rdls.IssuedLicense (      "...
0x180087a34  lea     rcx, [rsp+150h+var_118]; this
0x180087a39  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180087a3e  nop
0x180087a3f  mov     rbx, [rsp+150h+var_118]
0x180087a44  mov     [rsp+150h+var_118], r12
0x180087a49  lea     rcx, [rsp+150h+var_118]; this
0x180087a4e  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x180087a53  mov     rax, [rbp+50h+var_D0]
0x180087a57  mov     [rax], rbx
0x180087a5a  xor     ecx, ecx; bstrString
0x180087a5c  call    cs:__imp_SysFreeString
0x180087a63  nop     dword ptr [rax+rax+00h]
0x180087a68  mov     [rsp+150h+var_120], r12
0x180087a6d  lea     rdx, aCreateSynonymR; "CREATE SYNONYM RdlsSecrets FOR Rdls.Rdl"...
0x180087a74  mov     r8, rdi
0x180087a77  inc     r8; int
0x180087a7a  cmp     [rdx+r8*2], r12w
0x180087a7f  jnz     short loc_180087A77
0x180087a81  lea     rcx, [rsp+150h+var_120]; this
0x180087a86  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180087a8b  mov     rax, [rsp+150h+var_120]
  ... truncated ...
```
