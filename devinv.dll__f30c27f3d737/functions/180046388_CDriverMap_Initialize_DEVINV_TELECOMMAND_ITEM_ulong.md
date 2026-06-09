# CDriverMap::Initialize(_DEVINV_TELECOMMAND_ITEM *,ulong)

- ea: `0x180046388`
- end: `0x1800466eb`
- name: `?Initialize@CDriverMap@@QEAAJPEAU_DEVINV_TELECOMMAND_ITEM@@K@Z`
- size: `867`
- prototype: `__int64 __fastcall(CDriverMap *__hidden this, struct _DEVINV_TELECOMMAND_ITEM *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023180`

## callees

- `0x180006270`
- `0x180006d02`
- `0x180007014`
- `0x180038290`
- `0x1800443bc`
- `0x180046388`
- `0x1800466f4`
- `0x18004e618`
- `0x1800509bc`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004642b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004642b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046617`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180046419`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180046419`

## string_xrefs

- `0x180046440`: `[0x%08x] Failed to open SCM manager`
- `0x18004645e`: `Opened SCM Manager`
- `0x180046634`: `[%#x] Failed to initialize Driver Package Reader`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDriverMap::Initialize(CDriverMap *this, struct _DEVINV_TELECOMMAND_ITEM *a2, int a3)
{
  _OWORD *v4; // rcx
  __int64 v5; // rax
  SC_HANDLE v6; // rax
  signed int LastError; // eax
  unsigned int v8; // ebx
  const char *v9; // rdi
  __int64 v10; // r12
  FILE *v11; // rax
  FILE *v12; // rax
  FILE *v13; // rax
  unsigned __int16 v14; // dx
  unsigned __int16 v15; // cx
  unsigned __int16 v16; // r8
  FILE *v17; // rax
  FILE *v18; // rax
  FILE *v19; // rax
  unsigned __int16 v20; // dx
  unsigned __int16 v21; // cx
  unsigned __int16 v22; // r8
  DriverPackageReaderDrvStore *v23; // rax
  signed int v24; // eax
  FILE *v25; // rax
  FILE *v26; // rax
  FILE *v27; // rax
  unsigned int v29; // [rsp+20h] [rbp-28h]
  __int64 v30; // [rsp+20h] [rbp-28h]
  DriverPackageReaderDrvStore *v31; // [rsp+50h] [rbp+8h]
  DriverPackageReaderDism *v32; // [rsp+50h] [rbp+8h]

  if ( a2 )
  {
    v4 = (_OWORD *)((char *)this + 240);
    v5 = 4;
    do
    {
      *v4 = *(_OWORD *)a2;
      v4[1] = *((_OWORD *)a2 + 1);
      v4[2] = *((_OWORD *)a2 + 2);
      v4[3] = *((_OWORD *)a2 + 3);
      v4[4] = *((_OWORD *)a2 + 4);
      v4[5] = *((_OWORD *)a2 + 5);
      v4[6] = *((_OWORD *)a2 + 6);
      v4[7] = *((_OWORD *)a2 + 7);
      v4 += 8;
      a2 = (struct _DEVINV_TELECOMMAND_ITEM *)((char *)a2 + 128);
      --v5;
    }
    while ( v5 );
    *(_QWORD *)v4 = *(_QWORD *)a2;
  }
  *(_DWORD *)this = a3;
  CDriverMap::m_fProcessWow64 = CDriverMap::CheckProcessWow64();
  v6 = OpenSCManagerW(0, 0, 4u);
  *((_QWORD *)this + 21) = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = "[0x%08x] Failed to open SCM manager";
    v10 = 77;
    goto LABEL_28;
  }
  AslLogCallPrintf(3, "CDriverMap::Initialize", 80, "Opened SCM Manager");
  if ( EnableDevInvStdErrLog )
  {
    v11 = o___acrt_iob_func_0(2u);
    fprintf(v11, "Info: %s, %u: ", "CDriverMap::Initialize", 80);
    v12 = o___acrt_iob_func_0(2u);
    fprintf(v12, "Opened SCM Manager");
    v13 = o___acrt_iob_func_0(2u);
    fprintf(v13, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x4000000, "Opened SCM Manager");
  v8 = CDriverMap::InitializeImportFunctions(this);
  if ( (v8 & 0x80000000) != 0 )
  {
    v9 = "[0x%08x] Failed to initialize import functions";
    v10 = 85;
LABEL_28:
    v29 = v8;
    AslLogCallPrintf(2, "CDriverMap::Initialize", v10, v9, v29);
    if ( EnableDevInvStdErrLog )
    {
      v25 = o___acrt_iob_func_0(2u);
      fprintf(v25, "Error: %s, %u: ", "CDriverMap::Initialize", v10);
      v26 = o___acrt_iob_func_0(2u);
      fprintf(v26, v9, v8);
      v27 = o___acrt_iob_func_0(2u);
      fprintf(v27, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, v9, v8);
    LODWORD(v30) = v8;
    AslLogCallPrintf(1, "CDriverMap::Initialize", v10, v9, v30);
    return v8;
  }
  AslLogCallPrintf(3, "CDriverMap::Initialize", 88, "Initialized import functions");
  if ( EnableDevInvStdErrLog )
  {
    v17 = o___acrt_iob_func_0(2u);
    fprintf(v17, "Info: %s, %u: ", "CDriverMap::Initialize", 88);
    v18 = o___acrt_iob_func_0(2u);
    fprintf(v18, "Initialized import functions");
    v19 = o___acrt_iob_func_0(2u);
    fprintf(v19, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x4000000, "Initialized import functions");
  if ( IsWindowsVersionOrGreaterEx(v15, v14, v16, 0x4563u)
    || IsWindowsVersionOrGreaterEx(v21, v20, v22, 0x3839u) && (*(_DWORD *)this & 0x200000) == 0 )
  {
    v31 = (DriverPackageReaderDrvStore *)operator new(0x20u);
    v23 = DriverPackageReaderDrvStore::DriverPackageReaderDrvStore(v31, this);
  }
  else
  {
    v32 = (DriverPackageReaderDism *)operator new(0x58u);
    v23 = DriverPackageReaderDism::DriverPackageReaderDism(v32, this);
  }
  *((_QWORD *)this + 23) = v23;
  v24 = GetLastError();
  v8 = v24;
  if ( v24 > 0 )
    v8 = (unsigned __int16)v24 | 0x80070000;
  if ( (v8 & 0x80000000) != 0 )
  {
    v9 = "[%#x] Failed to initialize Driver Package Reader";
    v10 = 106;
    goto LABEL_28;
  }
  return v8;
}

```

## disassembly

```asm
0x180046388  mov     [rsp+arg_8], rbx
0x18004638d  mov     [rsp+arg_10], rbp
0x180046392  push    rsi
0x180046393  push    rdi
0x180046394  push    r12
0x180046396  sub     rsp, 30h
0x18004639a  mov     rdi, rcx
0x18004639d  mov     ebx, 4
0x1800463a2  test    rdx, rdx
0x1800463a5  jz      short loc_180046404
0x1800463a7  add     rcx, 0F0h
0x1800463ae  mov     eax, ebx
0x1800463b0  lea     r9d, [rbx+7Ch]
0x1800463b4  movups  xmm0, xmmword ptr [rdx]
0x1800463b7  movups  xmmword ptr [rcx], xmm0
0x1800463ba  movups  xmm1, xmmword ptr [rdx+10h]
0x1800463be  movups  xmmword ptr [rcx+10h], xmm1
0x1800463c2  movups  xmm0, xmmword ptr [rdx+20h]
0x1800463c6  movups  xmmword ptr [rcx+20h], xmm0
0x1800463ca  movups  xmm1, xmmword ptr [rdx+30h]
0x1800463ce  movups  xmmword ptr [rcx+30h], xmm1
0x1800463d2  movups  xmm0, xmmword ptr [rdx+40h]
0x1800463d6  movups  xmmword ptr [rcx+40h], xmm0
0x1800463da  movups  xmm1, xmmword ptr [rdx+50h]
0x1800463de  movups  xmmword ptr [rcx+50h], xmm1
0x1800463e2  movups  xmm0, xmmword ptr [rdx+60h]
0x1800463e6  movups  xmmword ptr [rcx+60h], xmm0
0x1800463ea  movups  xmm1, xmmword ptr [rdx+70h]
0x1800463ee  movups  xmmword ptr [rcx+70h], xmm1
0x1800463f2  add     rcx, r9
0x1800463f5  add     rdx, r9
0x1800463f8  sub     rax, 1
0x1800463fc  jnz     short loc_1800463B4
0x1800463fe  mov     rax, [rdx]
0x180046401  mov     [rcx], rax
0x180046404  mov     [rdi], r8d
0x180046407  call    ?CheckProcessWow64@CDriverMap@@SAHXZ; CDriverMap::CheckProcessWow64(void)
0x18004640c  mov     cs:?m_fProcessWow64@CDriverMap@@0HA, eax; int CDriverMap::m_fProcessWow64
0x180046412  mov     r8d, ebx; dwDesiredAccess
0x180046415  xor     edx, edx; lpDatabaseName
0x180046417  xor     ecx, ecx; lpMachineName
0x180046419  call    cs:__imp_OpenSCManagerW
0x18004641f  mov     [rdi+0A8h], rax
0x180046426  test    rax, rax
0x180046429  jnz     short loc_18004645E
0x18004642b  call    cs:__imp_GetLastError
0x180046431  mov     ebx, eax
0x180046433  test    eax, eax
0x180046435  jle     short loc_180046440
0x180046437  movzx   ebx, ax
0x18004643a  or      ebx, 80070000h
0x180046440  lea     rdi, a0x08xFailedToO_1; "[0x%08x] Failed to open SCM manager"
0x180046447  mov     r12d, 4Dh ; 'M'
0x18004644d  lea     rsi, aCdrivermapInit_0; "CDriverMap::Initialize"
0x180046454  lea     ebp, [r12-4Bh]
0x180046459  jmp     loc_180046641
0x18004645e  lea     rbx, aOpenedScmManag; "Opened SCM Manager"
0x180046465  mov     r9, rbx
0x180046468  mov     r12d, 50h ; 'P'
0x18004646e  mov     r8d, r12d
0x180046471  lea     rsi, aCdrivermapInit_0; "CDriverMap::Initialize"
0x180046478  mov     rdx, rsi
0x18004647b  lea     ecx, [r12-4Dh]
0x180046480  call    AslLogCallPrintf
0x180046485  lea     ebp, [r12-4Eh]
0x18004648a  cmp     cs:EnableDevInvStdErrLog, 0
0x180046491  jz      short loc_1800464D7
0x180046493  mov     ecx, ebp; Ix
0x180046495  call    _o___acrt_iob_func_0
0x18004649a  mov     rcx, rax; Stream
0x18004649d  mov     r9d, r12d
0x1800464a0  mov     r8, rsi
0x1800464a3  lea     rdx, aInfoSU; "Info: %s, %u: "
0x1800464aa  call    fprintf
0x1800464af  mov     ecx, ebp; Ix
0x1800464b1  call    _o___acrt_iob_func_0
0x1800464b6  mov     rcx, rax; Stream
0x1800464b9  mov     rdx, rbx; Format
0x1800464bc  call    fprintf
0x1800464c1  mov     ecx, ebp; Ix
0x1800464c3  call    _o___acrt_iob_func_0
0x1800464c8  mov     rcx, rax; Stream
0x1800464cb  lea     rdx, asc_18011EAD8; "\n"
0x1800464d2  call    fprintf
0x1800464d7  mov     r12d, 4000000h
0x1800464dd  cmp     cs:g_DeviceMapLogFunction, 0
0x1800464e5  jz      short loc_1800464F2
0x1800464e7  mov     rdx, rbx
0x1800464ea  mov     ecx, r12d
0x1800464ed  call    TraceMessageCallback
0x1800464f2  mov     rcx, rdi; this
0x1800464f5  call    ?InitializeImportFunctions@CDriverMap@@AEAAJXZ; CDriverMap::InitializeImportFunctions(void)
0x1800464fa  mov     ebx, eax
0x1800464fc  mov     rdx, rsi
0x1800464ff  test    eax, eax
0x180046501  jns     short loc_180046515
0x180046503  lea     rdi, a0x08xFailedToI_0; "[0x%08x] Failed to initialize import fu"...
0x18004650a  mov     r12d, 55h ; 'U'
0x180046510  jmp     loc_180046644
0x180046515  lea     rbx, aInitializedImp; "Initialized import functions"
0x18004651c  mov     r9, rbx
0x18004651f  mov     r8d, 58h ; 'X'
0x180046525  lea     ecx, [r8-55h]
0x180046529  call    AslLogCallPrintf
0x18004652e  cmp     cs:EnableDevInvStdErrLog, 0
0x180046535  jz      short loc_18004657E
0x180046537  mov     ecx, ebp; Ix
0x180046539  call    _o___acrt_iob_func_0
0x18004653e  mov     rcx, rax; Stream
0x180046541  mov     r9d, 58h ; 'X'
0x180046547  mov     r8, rsi
0x18004654a  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180046551  call    fprintf
0x180046556  mov     ecx, ebp; Ix
0x180046558  call    _o___acrt_iob_func_0
0x18004655d  mov     rcx, rax; Stream
0x180046560  mov     rdx, rbx; Format
0x180046563  call    fprintf
0x180046568  mov     ecx, ebp; Ix
0x18004656a  call    _o___acrt_iob_func_0
0x18004656f  mov     rcx, rax; Stream
0x180046572  lea     rdx, asc_18011EAD8; "\n"
0x180046579  call    fprintf
0x18004657e  cmp     cs:g_DeviceMapLogFunction, 0
0x180046586  jz      short loc_180046593
0x180046588  mov     rdx, rbx
0x18004658b  mov     ecx, r12d
0x18004658e  call    TraceMessageCallback
0x180046593  mov     r9d, 4563h; unsigned __int16
0x180046599  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18004659e  test    al, al
0x1800465a0  jz      short loc_1800465BF
0x1800465a2  mov     ecx, 20h ; ' '; Size
0x1800465a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800465ac  mov     [rsp+48h+arg_0], rax
0x1800465b1  mov     rdx, rdi; struct CDriverMap *
0x1800465b4  mov     rcx, rax; this
0x1800465b7  call    ??0DriverPackageReaderDrvStore@@QEAA@PEAVCDriverMap@@@Z; DriverPackageReaderDrvStore::DriverPackageReaderDrvStore(CDriverMap *)
0x1800465bc  nop
0x1800465bd  jmp     short loc_18004660E
0x1800465bf  mov     r9d, 3839h; unsigned __int16
0x1800465c5  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x1800465ca  test    al, al
0x1800465cc  jz      short loc_1800465F3
0x1800465ce  test    dword ptr [rdi], 200000h
0x1800465d4  jnz     short loc_1800465F3
0x1800465d6  mov     ecx, 20h ; ' '; Size
0x1800465db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800465e0  mov     [rsp+48h+arg_0], rax
0x1800465e5  mov     rdx, rdi; struct CDriverMap *
0x1800465e8  mov     rcx, rax; this
0x1800465eb  call    ??0DriverPackageReaderDrvStore@@QEAA@PEAVCDriverMap@@@Z; DriverPackageReaderDrvStore::DriverPackageReaderDrvStore(CDriverMap *)
0x1800465f0  nop
0x1800465f1  jmp     short loc_18004660E
0x1800465f3  mov     ecx, 58h ; 'X'; Size
0x1800465f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800465fd  mov     [rsp+48h+arg_0], rax
0x180046602  mov     rdx, rdi; struct CDriverMap *
0x180046605  mov     rcx, rax; this
0x180046608  call    ??0DriverPackageReaderDism@@QEAA@PEAVCDriverMap@@@Z; DriverPackageReaderDism::DriverPackageReaderDism(CDriverMap *)
0x18004660d  nop
0x18004660e  mov     ecx, 0B8h
0x180046613  mov     [rdi+rcx], rax
0x180046617  call    cs:__imp_GetLastError
0x18004661d  mov     ebx, eax
0x18004661f  test    eax, eax
0x180046621  jle     short loc_18004662C
0x180046623  movzx   ebx, ax
0x180046626  or      ebx, 80070000h
0x18004662c  test    ebx, ebx
0x18004662e  jns     loc_1800466D6
0x180046634  lea     rdi, aXFailedToIniti; "[%#x] Failed to initialize Driver Packa"...
0x18004663b  mov     r12d, 6Ah ; 'j'
0x180046641  mov     rdx, rsi
0x180046644  mov     dword ptr [rsp+48h+var_28], ebx
0x180046648  mov     r9, rdi
0x18004664b  mov     r8, r12
0x18004664e  mov     ecx, ebp
0x180046650  call    AslLogCallPrintf
0x180046655  cmp     cs:EnableDevInvStdErrLog, 0
0x18004665c  jz      short loc_1800466A5
0x18004665e  mov     ecx, ebp; Ix
0x180046660  call    _o___acrt_iob_func_0
0x180046665  mov     r9d, r12d
0x180046668  mov     r8, rsi
0x18004666b  lea     rdx, Format; "Error: %s, %u: "
0x180046672  mov     rcx, rax; Stream
0x180046675  call    fprintf
0x18004667a  mov     ecx, ebp; Ix
0x18004667c  call    _o___acrt_iob_func_0
0x180046681  mov     r8d, ebx
0x180046684  mov     rdx, rdi; Format
0x180046687  mov     rcx, rax; Stream
0x18004668a  call    fprintf
0x18004668f  mov     ecx, ebp; Ix
0x180046691  call    _o___acrt_iob_func_0
0x180046696  lea     rdx, asc_18011EAD8; "\n"
0x18004669d  mov     rcx, rax; Stream
0x1800466a0  call    fprintf
0x1800466a5  cmp     cs:g_DeviceMapLogFunction, 0
0x1800466ad  jz      short loc_1800466BF
0x1800466af  mov     r8d, ebx
0x1800466b2  mov     rdx, rdi
0x1800466b5  mov     ecx, 2000000h
0x1800466ba  call    TraceMessageCallback
0x1800466bf  mov     dword ptr [rsp+48h+var_28], ebx
0x1800466c3  mov     r9, rdi
0x1800466c6  mov     r8, r12
0x1800466c9  mov     rdx, rsi
0x1800466cc  mov     ecx, 1
0x1800466d1  call    AslLogCallPrintf
0x1800466d6  mov     eax, ebx
0x1800466d8  mov     rbx, [rsp+48h+arg_8]
0x1800466dd  mov     rbp, [rsp+48h+arg_10]
0x1800466e2  add     rsp, 30h
0x1800466e6  pop     r12
0x1800466e8  pop     rdi
0x1800466e9  pop     rsi
0x1800466ea  retn
```
