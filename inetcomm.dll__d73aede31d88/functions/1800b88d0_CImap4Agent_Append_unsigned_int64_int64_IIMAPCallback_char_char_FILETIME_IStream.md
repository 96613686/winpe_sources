# CImap4Agent::Append(unsigned __int64,__int64,IIMAPCallback *,char *,char *,_FILETIME,IStream *)

- ea: `0x1800b88d0`
- end: `0x1800b8d12`
- name: `?Append@CImap4Agent@@UEAAJ_K_JPEAUIIMAPCallback@@PEAD3U_FILETIME@@PEAUIStream@@@Z`
- size: `1090`
- prototype: `__int64 __usercall@<rax>(CImap4Agent *__hidden this@<rcx>, unsigned __int64@<rdx>, __int64@<r8>, struct IIMAPCallback *@<r9>, char *, char *, struct _FILETIME, struct IStream *)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800299d0`
- `0x1800b80f4`
- `0x1800b88d0`
- `0x1800b8d18`
- `0x1800ba230`
- `0x1800badd8`
- `0x1800bb0d0`
- `0x1800c00d8`
- `0x1800c06e4`
- `0x1800c0be0`
- `0x1800c17cc`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!HrGetStreamSize` at `0x1800b8a47`
- `MSOERT2!HrGetStreamSize` at `0x1800b8a47`
- `KERNEL32!FileTimeToSystemTime` at `0x1800b89f2`
- `KERNEL32!FileTimeToSystemTime` at `0x1800b89f2`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1800b89e0`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1800b89e0`
- `KERNEL32!GetTimeZoneInformation` at `0x1800b8a1c`
- `KERNEL32!GetTimeZoneInformation` at `0x1800b8a1c`

## pseudocode

```c
__int64 __fastcall CImap4Agent::Append(
        CImap4Agent *this,
        __int64 a2,
        __int64 a3,
        struct IIMAPCallback *a4,
        char *a5,
        char *a6,
        FILETIME FileTime,
        struct IStream *a8)
{
  struct IStream *v10; // r13
  int v13; // eax
  void *v15; // rax
  CIMAPCmdInfo *v16; // rax
  struct tagIMAPLineFragmentQueue **v17; // r14
  int inited; // ebx
  DWORD v19; // eax
  DWORD v20; // eax
  LONG StandardBias; // edi
  LONG Bias; // edi
  int v23; // ebx
  int v24; // edi
  int v25; // edx
  int v26; // esi
  __int64 v27; // rdi
  struct tagIMAPLineFragment *v28; // rax
  struct tagIMAPLineFragment *v29; // rbx
  CImap4Agent *v30; // rcx
  STRSAFE_LPSTR v31; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v32; // [rsp+88h] [rbp-78h] BYREF
  char *v33; // [rsp+90h] [rbp-70h] BYREF
  char *v34; // [rsp+98h] [rbp-68h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+A0h] [rbp-60h] BYREF
  char *v36; // [rsp+A8h] [rbp-58h]
  struct _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-50h] BYREF
  struct _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+C0h] [rbp-40h] BYREF
  char pszDest[512]; // [rsp+170h] [rbp+70h] BYREF

  v10 = a8;
  v36 = a5;
  LocalFileTime = 0;
  SystemTime = 0;
  memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
  v32 = 0;
  memset_0(pszDest, 0, sizeof(pszDest));
  v13 = *((_DWORD *)this + 696);
  if ( v13 < 3 && v13 != 1 )
    return 2148322526LL;
  v34 = 0;
  v15 = operator new(0x50u);
  if ( !v15
    || (v16 = (CIMAPCmdInfo *)CIMAPCmdInfo::CIMAPCmdInfo(v15, this, 12, 3, a2, a3, a4),
        (v17 = (struct tagIMAPLineFragmentQueue **)v16) == 0) )
  {
    inited = -2147024882;
    goto LABEL_35;
  }
  inited = CIMAPCmdInfo::InitNew(v16);
  if ( inited < 0 )
    goto LABEL_33;
  if ( !FileTimeToLocalFileTime(&FileTime, &LocalFileTime) || !FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
  {
    *(_DWORD *)&SystemTime.wYear = 788431;
    *(_DWORD *)&SystemTime.wDayOfWeek = 2031621;
    *(_DWORD *)&SystemTime.wHour = 3866647;
    *(_DWORD *)&SystemTime.wSecond = 65470523;
  }
  v19 = GetTimeZoneInformation(&TimeZoneInformation);
  if ( v19 )
  {
    v20 = v19 - 1;
    if ( !v20 )
    {
      StandardBias = TimeZoneInformation.StandardBias;
      goto LABEL_15;
    }
    if ( v20 == 1 )
    {
      StandardBias = TimeZoneInformation.DaylightBias;
LABEL_15:
      Bias = TimeZoneInformation.Bias + StandardBias;
      goto LABEL_17;
    }
  }
  Bias = TimeZoneInformation.Bias;
LABEL_17:
  inited = HrGetStreamSize(v10, &v32);
  if ( inited < 0 )
    goto LABEL_33;
  v33 = 0;
  inited = CIMAPCmdInfo::GetTag((CIMAPCmdInfo *)v17, (const char **)&v33);
  if ( inited < 0 )
    goto LABEL_33;
  v31 = pszDest;
  StringCchPrintfExA(pszDest, 0x200u, &v31, 0, 0, "%s APPEND", v33);
  inited = CImap4Agent::_MultiByteToModifiedUTF7(this, v36, &v34);
  if ( inited < 0 )
    goto LABEL_33;
  inited = CImap4Agent::AppendSendAString(this, (struct CIMAPCmdInfo *)v17, pszDest, &v31, 0x200u, v34, 1);
  if ( inited < 0 )
    goto LABEL_33;
  v23 = Bias / 60;
  LODWORD(v33) = (((Bias / 60) >> 31) & 0xFFFFFFFE) + 45;
  if ( a6 )
    StringCchPrintfExA(
      v31,
      512LL - ((unsigned int)v31 - ((unsigned int)&TimeZoneInformation.StandardName[30] + 112)),
      &v31,
      0,
      0,
      " %.250s",
      a6);
  v24 = Bias % 60;
  v25 = -v24;
  if ( v24 > 0 )
    v25 = v24;
  v26 = -v23;
  if ( v23 > 0 )
    v26 = v23;
  StringCchPrintfExA(
    v31,
    512LL - ((unsigned int)v31 - (unsigned int)pszDest),
    &v31,
    0,
    0,
    " \"%2d-%.3s-%04d %02d:%02d:%02d %c%02d%02d\" {%lu}\r\n",
    SystemTime.wDay,
    off_1800D4000[SystemTime.wMonth],
    SystemTime.wYear,
    SystemTime.wHour,
    SystemTime.wMinute,
    SystemTime.wSecond,
    (_DWORD)v33,
    v26,
    v25,
    v32);
  inited = CImap4Agent::SendCmdLine(
             this,
             (struct CIMAPCmdInfo *)v17,
             0,
             pszDest,
             (_DWORD)v31 - ((unsigned int)&TimeZoneInformation.StandardName[30] + 112));
  if ( inited < 0 )
    goto LABEL_33;
  v27 = v32;
  v28 = (struct tagIMAPLineFragment *)operator new(0x28u);
  v29 = v28;
  if ( !v28 )
  {
    inited = -2147024882;
LABEL_33:
    (*(void (__fastcall **)(struct tagIMAPLineFragmentQueue **, __int64))*v17)(v17, 1);
    goto LABEL_35;
  }
  *((_QWORD *)v28 + 1) = v27;
  *(_DWORD *)v28 = 1;
  *((_DWORD *)v28 + 1) = 1;
  ((void (__fastcall *)(struct IStream *))v10->lpVtbl->AddRef)(v10);
  *((_QWORD *)v29 + 2) = v10;
  *((_QWORD *)v29 + 3) = 0;
  *((_QWORD *)v29 + 4) = 0;
  CImap4Agent::EnqueueFragment(v30, v29, v17[3]);
  inited = CImap4Agent::SendCmdLine(this, (struct CIMAPCmdInfo *)v17, 0, "\r\n", 2u);
  if ( inited < 0 )
    goto LABEL_33;
  inited = CImap4Agent::SubmitIMAPCommand(this, (struct CIMAPCmdInfo *)v17);
  if ( inited < 0 )
    goto LABEL_33;
LABEL_35:
  if ( v34 )
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800b88d0  push    rbp
0x1800b88d2  push    rbx
0x1800b88d3  push    rsi
0x1800b88d4  push    rdi
0x1800b88d5  push    r12
0x1800b88d7  push    r13
0x1800b88d9  push    r14
0x1800b88db  push    r15
0x1800b88dd  lea     rbp, [rsp-288h]
0x1800b88e5  sub     rsp, 388h
0x1800b88ec  mov     rax, cs:__security_cookie
0x1800b88f3  xor     rax, rsp
0x1800b88f6  mov     [rbp+2C0h+var_50], rax
0x1800b88fd  mov     rax, [rbp+2C0h+arg_20]
0x1800b8904  mov     rdi, r8
0x1800b8907  mov     rsi, [rbp+2C0h+arg_28]
0x1800b890e  mov     rbx, rdx
0x1800b8911  mov     r13, [rbp+2C0h+arg_38]
0x1800b8918  mov     r15, rcx
0x1800b891b  xorps   xmm0, xmm0
0x1800b891e  mov     [rbp+2C0h+var_318], rax
0x1800b8922  xor     edx, edx; Val
0x1800b8924  mov     qword ptr [rbp+2C0h+LocalFileTime.dwLowDateTime], 0
0x1800b892c  mov     r8d, 0ACh; Size
0x1800b8932  lea     rcx, [rbp+2C0h+TimeZoneInformation]; void *
0x1800b8936  movups  xmmword ptr [rbp+2C0h+SystemTime.wYear], xmm0
0x1800b893a  mov     r14, r9
0x1800b893d  call    memset_0
0x1800b8942  mov     r12d, 200h
0x1800b8948  mov     [rbp+2C0h+var_338], 0
0x1800b894f  mov     r8d, r12d; Size
0x1800b8952  lea     rcx, [rbp+2C0h+pszDest]; void *
0x1800b8956  xor     edx, edx; Val
0x1800b8958  call    memset_0
0x1800b895d  mov     eax, [r15+0AE0h]
0x1800b8964  cmp     eax, 3
0x1800b8967  jge     short loc_1800B8978
0x1800b8969  cmp     eax, 1
0x1800b896c  jz      short loc_1800B8978
0x1800b896e  mov     eax, 800CCCDEh
0x1800b8973  jmp     loc_1800B8CEF
0x1800b8978  mov     ecx, 50h ; 'P'; Size
0x1800b897d  mov     [rbp+2C0h+var_328], 0
0x1800b8985  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b898a  test    rax, rax
0x1800b898d  jz      loc_1800B8CCC
0x1800b8993  mov     r8d, 0Ch
0x1800b8999  mov     qword ptr [rsp+3C0h+var_390], r14
0x1800b899e  mov     [rsp+3C0h+var_398], rdi
0x1800b89a3  mov     rdx, r15
0x1800b89a6  mov     rcx, rax
0x1800b89a9  mov     qword ptr [rsp+3C0h+dwFlags], rbx
0x1800b89ae  lea     r9d, [r8-9]
0x1800b89b2  call    ??0CIMAPCmdInfo@@QEAA@PEAVCImap4Agent@@W4IMAP_COMMAND@@W4SERVERSTATE@@_K_JPEAUIIMAPCallback@@@Z; CIMAPCmdInfo::CIMAPCmdInfo(CImap4Agent *,IMAP_COMMAND,SERVERSTATE,unsigned __int64,__int64,IIMAPCallback *)
0x1800b89b7  mov     r14, rax
0x1800b89ba  test    rax, rax
0x1800b89bd  jz      loc_1800B8CCC
0x1800b89c3  mov     rcx, rax; this
0x1800b89c6  call    ?InitNew@CIMAPCmdInfo@@QEAAJXZ; CIMAPCmdInfo::InitNew(void)
0x1800b89cb  mov     ebx, eax
0x1800b89cd  test    eax, eax
0x1800b89cf  js      loc_1800B8CB7
0x1800b89d5  lea     rdx, [rbp+2C0h+LocalFileTime]; lpLocalFileTime
0x1800b89d9  lea     rcx, [rbp+2C0h+FileTime]; lpFileTime
0x1800b89e0  call    cs:__imp_FileTimeToLocalFileTime
0x1800b89e6  test    eax, eax
0x1800b89e8  jz      short loc_1800B89FC
0x1800b89ea  lea     rdx, [rbp+2C0h+SystemTime]; lpSystemTime
0x1800b89ee  lea     rcx, [rbp+2C0h+LocalFileTime]; lpFileTime
0x1800b89f2  call    cs:__imp_FileTimeToSystemTime
0x1800b89f8  test    eax, eax
0x1800b89fa  jnz     short loc_1800B8A18
0x1800b89fc  mov     dword ptr [rbp+2C0h+SystemTime.wYear], 0C07CFh
0x1800b8a03  mov     dword ptr [rbp+2C0h+SystemTime.wDayOfWeek], 1F0005h
0x1800b8a0a  mov     dword ptr [rbp+2C0h+SystemTime.wHour], 3B0017h
0x1800b8a11  mov     dword ptr [rbp+2C0h+SystemTime.wSecond], 3E7003Bh
0x1800b8a18  lea     rcx, [rbp+2C0h+TimeZoneInformation]; lpTimeZoneInformation
0x1800b8a1c  call    cs:__imp_GetTimeZoneInformation
0x1800b8a22  test    eax, eax
0x1800b8a24  jz      short loc_1800B8A3D
0x1800b8a26  sub     eax, 1
0x1800b8a29  jz      short loc_1800B8A35
0x1800b8a2b  cmp     eax, 1
0x1800b8a2e  jnz     short loc_1800B8A3D
0x1800b8a30  mov     edi, [rbp+2C0h+TimeZoneInformation.DaylightBias]
0x1800b8a33  jmp     short loc_1800B8A38
0x1800b8a35  mov     edi, [rbp+2C0h+TimeZoneInformation.StandardBias]
0x1800b8a38  add     edi, [rbp+2C0h+TimeZoneInformation.Bias]
0x1800b8a3b  jmp     short loc_1800B8A40
0x1800b8a3d  mov     edi, [rbp+2C0h+TimeZoneInformation.Bias]
0x1800b8a40  lea     rdx, [rbp+2C0h+var_338]
0x1800b8a44  mov     rcx, r13
0x1800b8a47  call    cs:__imp_HrGetStreamSize
0x1800b8a4d  mov     ebx, eax
0x1800b8a4f  test    eax, eax
0x1800b8a51  js      loc_1800B8CB7
0x1800b8a57  lea     rdx, [rbp+2C0h+var_330]; char **
0x1800b8a5b  mov     [rbp+2C0h+var_330], 0
0x1800b8a63  mov     rcx, r14; this
0x1800b8a66  call    ?GetTag@CIMAPCmdInfo@@QEAAJPEAPEBD@Z; CIMAPCmdInfo::GetTag(char const * *)
0x1800b8a6b  mov     ebx, eax
0x1800b8a6d  test    eax, eax
0x1800b8a6f  js      loc_1800B8CB7
0x1800b8a75  lea     rax, [rbp+2C0h+pszDest]
0x1800b8a79  xor     r9d, r9d; unsigned __int64 *
0x1800b8a7c  mov     [rbp+2C0h+var_340], rax
0x1800b8a80  lea     r8, [rbp+2C0h+var_340]; char **
0x1800b8a84  mov     rax, [rbp+2C0h+var_330]
0x1800b8a88  lea     rcx, [rbp+2C0h+pszDest]; pszDest
0x1800b8a8c  mov     qword ptr [rsp+3C0h+var_390], rax
0x1800b8a91  mov     rdx, r12; cbDest
0x1800b8a94  lea     rax, aSAppend; "%s APPEND"
0x1800b8a9b  mov     [rsp+3C0h+var_398], rax; char *
0x1800b8aa0  mov     qword ptr [rsp+3C0h+dwFlags], 0; dwFlags
0x1800b8aa9  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x1800b8aae  mov     rdx, [rbp+2C0h+var_318]; char *
0x1800b8ab2  lea     r8, [rbp+2C0h+var_328]; char **
0x1800b8ab6  mov     rcx, r15; this
0x1800b8ab9  call    ?_MultiByteToModifiedUTF7@CImap4Agent@@AEAAJPEBDPEAPEAD@Z; CImap4Agent::_MultiByteToModifiedUTF7(char const *,char * *)
0x1800b8abe  mov     ebx, eax
0x1800b8ac0  test    eax, eax
0x1800b8ac2  js      loc_1800B8CB7
0x1800b8ac8  mov     rax, [rbp+2C0h+var_328]
0x1800b8acc  lea     r9, [rbp+2C0h+var_340]; char **
0x1800b8ad0  mov     [rsp+3C0h+var_390], 1; int
0x1800b8ad8  lea     r8, [rbp+2C0h+pszDest]; char *
0x1800b8adc  mov     [rsp+3C0h+var_398], rax; char *
0x1800b8ae1  mov     rdx, r14; struct CIMAPCmdInfo *
0x1800b8ae4  mov     rcx, r15; this
0x1800b8ae7  mov     [rsp+3C0h+dwFlags], r12d; unsigned int
0x1800b8aec  call    ?AppendSendAString@CImap4Agent@@AEAAJPEAVCIMAPCmdInfo@@PEADPEAPEADKPEBDH@Z; CImap4Agent::AppendSendAString(CIMAPCmdInfo *,char *,char * *,ulong,char const *,int)
0x1800b8af1  mov     ebx, eax
0x1800b8af3  test    eax, eax
0x1800b8af5  js      loc_1800B8CB7
0x1800b8afb  mov     eax, 88888889h
0x1800b8b00  imul    edi
0x1800b8b02  lea     ebx, [rdi+rdx]
0x1800b8b05  sar     ebx, 5
0x1800b8b08  mov     eax, ebx
0x1800b8b0a  shr     eax, 1Fh
0x1800b8b0d  add     ebx, eax
0x1800b8b0f  mov     eax, ebx
0x1800b8b11  sar     eax, 1Fh
0x1800b8b14  and     eax, 0FFFFFFFEh
0x1800b8b17  add     eax, 2Dh ; '-'
0x1800b8b1a  mov     dword ptr [rbp+2C0h+var_330], eax
0x1800b8b1d  test    rsi, rsi
0x1800b8b20  jz      short loc_1800B8B5D
0x1800b8b22  mov     eax, dword ptr [rbp+2C0h+var_340]
0x1800b8b25  lea     rcx, [rbp+2C0h+pszDest]
0x1800b8b29  sub     eax, ecx
0x1800b8b2b  mov     qword ptr [rsp+3C0h+var_390], rsi
0x1800b8b30  mov     ecx, eax
0x1800b8b32  lea     r8, [rbp+2C0h+var_340]; char **
0x1800b8b36  lea     rax, a250s; " %.250s"
0x1800b8b3d  mov     rdx, r12
0x1800b8b40  sub     rdx, rcx; cbDest
0x1800b8b43  mov     [rsp+3C0h+var_398], rax; char *
0x1800b8b48  mov     rcx, [rbp+2C0h+var_340]; pszDest
0x1800b8b4c  xor     r9d, r9d; unsigned __int64 *
0x1800b8b4f  mov     qword ptr [rsp+3C0h+dwFlags], 0; dwFlags
0x1800b8b58  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x1800b8b5d  movzx   r8d, [rbp+2C0h+SystemTime.wSecond]
0x1800b8b62  lea     rcx, [rbp+2C0h+pszDest]
0x1800b8b66  movzx   r9d, [rbp+2C0h+SystemTime.wMinute]
0x1800b8b6b  mov     esi, ebx
0x1800b8b6d  movzx   r10d, [rbp+2C0h+SystemTime.wHour]
0x1800b8b72  movzx   r11d, [rbp+2C0h+SystemTime.wYear]
0x1800b8b77  imul    eax, ebx, 3Ch ; '<'
0x1800b8b7a  sub     edi, eax
0x1800b8b7c  mov     eax, dword ptr [rbp+2C0h+var_340]
0x1800b8b7f  mov     edx, edi
0x1800b8b81  neg     edx
0x1800b8b83  cmovs   edx, edi
0x1800b8b86  movzx   edi, [rbp+2C0h+SystemTime.wDay]
0x1800b8b8a  neg     esi
0x1800b8b8c  cmovs   esi, ebx
0x1800b8b8f  movzx   ebx, [rbp+2C0h+SystemTime.wMonth]
0x1800b8b93  sub     eax, ecx
0x1800b8b95  mov     ecx, eax
0x1800b8b97  mov     eax, [rbp+2C0h+var_338]
0x1800b8b9a  sub     r12, rcx
0x1800b8b9d  mov     rcx, [rbp+2C0h+var_340]; pszDest
0x1800b8ba1  mov     [rsp+3C0h+var_348], eax
0x1800b8ba5  mov     eax, dword ptr [rbp+2C0h+var_330]
0x1800b8ba8  mov     [rsp+3C0h+var_350], edx
0x1800b8bac  mov     rdx, r12; cbDest
0x1800b8baf  mov     [rsp+3C0h+var_358], esi
0x1800b8bb3  mov     [rsp+3C0h+var_360], eax
0x1800b8bb7  lea     rax, off_1800D4000; "Filler"
0x1800b8bbe  mov     rax, [rax+rbx*8]
0x1800b8bc2  mov     [rsp+3C0h+var_368], r8d
0x1800b8bc7  lea     r8, [rbp+2C0h+var_340]; char **
0x1800b8bcb  mov     [rsp+3C0h+var_370], r9d
0x1800b8bd0  xor     r9d, r9d; unsigned __int64 *
0x1800b8bd3  mov     [rsp+3C0h+var_378], r10d
0x1800b8bd8  mov     [rsp+3C0h+var_380], r11d
0x1800b8bdd  mov     [rsp+3C0h+var_388], rax
0x1800b8be2  lea     rax, a2d3s04d02d02d0; " \"%2d-%.3s-%04d %02d:%02d:%02d %c%02d%"...
0x1800b8be9  mov     [rsp+3C0h+var_390], edi
0x1800b8bed  mov     [rsp+3C0h+var_398], rax; char *
0x1800b8bf2  mov     qword ptr [rsp+3C0h+dwFlags], 0; dwFlags
0x1800b8bfb  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x1800b8c00  mov     eax, dword ptr [rbp+2C0h+var_340]
0x1800b8c03  lea     rcx, [rbp+2C0h+pszDest]
0x1800b8c07  sub     eax, ecx
0x1800b8c09  lea     r9, [rbp+2C0h+pszDest]; char *
0x1800b8c0d  mov     rcx, r15; this
0x1800b8c10  mov     [rsp+3C0h+dwFlags], eax; unsigned int
0x1800b8c14  xor     r8d, r8d; unsigned int
0x1800b8c17  mov     rdx, r14; struct CIMAPCmdInfo *
0x1800b8c1a  call    ?SendCmdLine@CImap4Agent@@AEAAJPEAVCIMAPCmdInfo@@KPEBDK@Z; CImap4Agent::SendCmdLine(CIMAPCmdInfo *,ulong,char const *,ulong)
0x1800b8c1f  mov     ebx, eax
0x1800b8c21  test    eax, eax
0x1800b8c23  js      loc_1800B8CB7
0x1800b8c29  mov     edi, [rbp+2C0h+var_338]
0x1800b8c2c  mov     ecx, 28h ; '('; Size
0x1800b8c31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b8c36  mov     rbx, rax
0x1800b8c39  test    rax, rax
0x1800b8c3c  jz      short loc_1800B8CB2
0x1800b8c3e  mov     eax, 1
0x1800b8c43  mov     [rbx+8], rdi
0x1800b8c47  mov     [rbx], eax
0x1800b8c49  mov     [rbx+4], eax
0x1800b8c4c  mov     rcx, [r13+0]
0x1800b8c50  mov     rax, [rcx+8]
0x1800b8c54  mov     rcx, r13
0x1800b8c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8c5c  mov     [rbx+10h], r13
0x1800b8c60  mov     rdx, rbx; struct tagIMAPLineFragment *
0x1800b8c63  mov     qword ptr [rbx+18h], 0
0x1800b8c6b  mov     qword ptr [rbx+20h], 0
0x1800b8c73  mov     r8, [r14+18h]; struct tagIMAPLineFragmentQueue *
0x1800b8c77  call    ?EnqueueFragment@CImap4Agent@@AEAAXPEAUtagIMAPLineFragment@@PEAUtagIMAPLineFragmentQueue@@@Z; CImap4Agent::EnqueueFragment(tagIMAPLineFragment *,tagIMAPLineFragmentQueue *)
0x1800b8c7c  mov     rdx, r14; struct CIMAPCmdInfo *
0x1800b8c7f  mov     [rsp+3C0h+dwFlags], 2; unsigned int
0x1800b8c87  lea     r9, c_szCRLF; "\r\n"
0x1800b8c8e  xor     r8d, r8d; unsigned int
0x1800b8c91  mov     rcx, r15; this
0x1800b8c94  call    ?SendCmdLine@CImap4Agent@@AEAAJPEAVCIMAPCmdInfo@@KPEBDK@Z; CImap4Agent::SendCmdLine(CIMAPCmdInfo *,ulong,char const *,ulong)
0x1800b8c99  mov     ebx, eax
0x1800b8c9b  test    eax, eax
0x1800b8c9d  js      short loc_1800B8CB7
0x1800b8c9f  mov     rdx, r14; struct CIMAPCmdInfo *
0x1800b8ca2  mov     rcx, r15; this
0x1800b8ca5  call    ?SubmitIMAPCommand@CImap4Agent@@AEAAJPEAVCIMAPCmdInfo@@@Z; CImap4Agent::SubmitIMAPCommand(CIMAPCmdInfo *)
0x1800b8caa  mov     ebx, eax
0x1800b8cac  test    eax, eax
0x1800b8cae  jns     short loc_1800B8CD1
0x1800b8cb0  jmp     short loc_1800B8CB7
0x1800b8cb2  mov     ebx, 8007000Eh
0x1800b8cb7  mov     rax, [r14]
0x1800b8cba  mov     edx, 1
0x1800b8cbf  mov     rcx, r14
0x1800b8cc2  mov     rax, [rax]
0x1800b8cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8cca  jmp     short loc_1800B8CD1
0x1800b8ccc  mov     ebx, 8007000Eh
0x1800b8cd1  mov     rdx, [rbp+2C0h+var_328]
0x1800b8cd5  test    rdx, rdx
0x1800b8cd8  jz      short loc_1800B8CED
0x1800b8cda  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800b8ce1  mov     rax, [rcx]
0x1800b8ce4  mov     rax, [rax+28h]
0x1800b8ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8ced  mov     eax, ebx
0x1800b8cef  mov     rcx, [rbp+2C0h+var_50]
0x1800b8cf6  xor     rcx, rsp; StackCookie
0x1800b8cf9  call    __security_check_cookie
0x1800b8cfe  add     rsp, 388h
0x1800b8d05  pop     r15
0x1800b8d07  pop     r14
0x1800b8d09  pop     r13
0x1800b8d0b  pop     r12
0x1800b8d0d  pop     rdi
0x1800b8d0e  pop     rsi
0x1800b8d0f  pop     rbx
0x1800b8d10  pop     rbp
0x1800b8d11  retn
```
