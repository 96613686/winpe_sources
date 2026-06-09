# CADMCOMW::RestoreHelper(ushort const *,ulong,ulong,ushort const *,ulong,ulong)

- ea: `0x180008ae0`
- end: `0x180009054`
- name: `?RestoreHelper@CADMCOMW@@AEAAJPEBGKK0KK@Z`
- size: `1396`
- prototype: `__int64 __fastcall(CADMCOMW *this, const unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180008ab0`
- `0x180009060`
- `0x1800090c0`

## callees

- `0x180001cec`
- `0x18000238c`
- `0x180004388`
- `0x1800046a4`
- `0x180008ae0`
- `0x1800093bc`
- `0x180009ac4`
- `0x18000b2d4`
- `0x18000fb1e`
- `0x18000fb50`
- `0x180010010`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x180008e8e`
- `ADVAPI32!OpenSCManagerW` at `0x180008e8e`
- `ADVAPI32!OpenServiceW` at `0x180008fd3`
- `ADVAPI32!OpenServiceW` at `0x180008fd3`
- `ADVAPI32!CloseServiceHandle` at `0x180008fff`
- `ADVAPI32!CloseServiceHandle` at `0x180009011`
- `ADVAPI32!CloseServiceHandle` at `0x18000901f`
- `ADVAPI32!CloseServiceHandle` at `0x180008fff`
- `ADVAPI32!CloseServiceHandle` at `0x180009011`
- `ADVAPI32!CloseServiceHandle` at `0x18000901f`
- `ADVAPI32!StartServiceW` at `0x180008fe9`
- `ADVAPI32!StartServiceW` at `0x180008fe9`
- `KERNEL32!GetLastError` at `0x180008ea0`
- `KERNEL32!GetLastError` at `0x180008ea0`
- `IisRTL!PuDbgPrint` at `0x180008c34`
- `IisRTL!PuDbgPrint` at `0x180008c34`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180009029`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180009029`

## string_xrefs

- `0x180008c1b`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180008c22`: `AccessCheck failed hr = 0x%08x\n`
- `0x180008c10`: `CADMCOMW::RestoreHelper`

## pseudocode

```c
__int64 __fastcall CADMCOMW::RestoreHelper(
        CADMCOMW *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7)
{
  CADMCOMW *v8; // r13
  unsigned int v9; // r14d
  unsigned int v10; // r15d
  unsigned int v11; // r12d
  unsigned __int64 v12; // rax
  int v13; // ebx
  int v14; // edi
  int v15; // eax
  int v16; // r10d
  _WORD *v17; // r8
  __int64 v18; // rcx
  const wchar_t *v19; // rax
  __int64 v20; // rdx
  _WORD *v21; // rcx
  __int64 **v22; // r13
  bool v23; // zf
  __int64 v24; // rdx
  _WORD *v25; // rcx
  _QWORD *v26; // r15
  SC_HANDLE v27; // r12
  CADMCOMW *v28; // rcx
  __int64 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  SC_HANDLE v32; // rdi
  unsigned int i; // esi
  SC_HANDLE v34; // rax
  unsigned __int16 *v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+60h] [rbp-A0h]
  int v39; // [rsp+68h] [rbp-98h] BYREF
  CADMCOMW *v40; // [rsp+70h] [rbp-90h]
  int v41; // [rsp+78h] [rbp-88h]
  unsigned int v42; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v43; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v44; // [rsp+84h] [rbp-7Ch] BYREF
  int v45; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v46; // [rsp+8Ch] [rbp-74h]
  int v47; // [rsp+90h] [rbp-70h] BYREF
  __int64 v48; // [rsp+98h] [rbp-68h] BYREF
  const unsigned __int16 *v49; // [rsp+A0h] [rbp-60h]
  _QWORD v50[4]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD *v51; // [rsp+C8h] [rbp-38h]
  int v52; // [rsp+D0h] [rbp-30h]
  __int16 v53; // [rsp+D4h] [rbp-2Ch]
  _BYTE v54[208]; // [rsp+E0h] [rbp-20h] BYREF

  v49 = a5;
  v8 = this;
  v40 = this;
  v51 = v50;
  v46 = a4;
  v50[0] = 0;
  v52 = 32;
  v9 = 0;
  v53 = 256;
  v42 = 0;
  memset_0(v54, 0, 0xC8u);
  v10 = 0;
  v39 = 0;
  v11 = 0;
  v45 = 0;
  v48 = 0;
  v43 = 0;
  v44 = 0;
  v47 = 0;
  if ( a7 != 1 && (a7 != 2 || !a2) )
    goto LABEL_8;
  if ( a2 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    if ( v12 >= 0x64 )
    {
LABEL_8:
      v13 = -2147024809;
      goto LABEL_75;
    }
  }
  v37 = 0;
  v14 = 0;
  v15 = CADMCOMW::AccessCheck(
          (__int64)v8,
          0,
          &byte_1800127D8,
          0,
          2u,
          0,
          (struct COpenHandle *)&g_ohMasterRootHandle,
          0,
          &v47);
  v13 = v15;
  if ( v15 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        3091,
        "CADMCOMW::RestoreHelper",
        "AccessCheck failed hr = 0x%08x\n",
        v15);
    goto LABEL_45;
  }
  v16 = 0;
  v41 = 0;
  while ( 1 )
  {
    v17 = v54;
    v18 = 2147483646;
    v19 = a2;
    if ( a7 != 1 )
      break;
    if ( !a2 )
      v19 = &byte_1800127D8;
    v20 = 100;
    do
    {
      if ( !v18 )
        break;
      if ( !*v19 )
        break;
      *v17++ = *v19++;
      --v18;
      --v20;
    }
    while ( v20 );
    v21 = v17 - 1;
    if ( v20 )
      v21 = v17;
    v13 = v20 == 0 ? 0x8007007A : 0;
    *v21 = 0;
    if ( !v20 )
      goto LABEL_44;
    v22 = (__int64 **)((char *)v8 + 32);
    v13 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *, int *, int *, __int64 *, int))(**v22 + 496))(
            *v22,
            v54,
            &v39,
            &v45,
            &v48,
            v16);
    if ( (a6 & 1) != 0 )
      goto LABEL_40;
    if ( v39 == a3 )
    {
      v23 = v45 == v46;
      goto LABEL_37;
    }
LABEL_38:
    ++v41;
    if ( v13 < 0 )
      goto LABEL_41;
    v16 = v41;
    v8 = v40;
  }
  if ( !a2 )
    v19 = L"MDBackUp";
  v24 = 100;
  do
  {
    if ( !v18 )
      break;
    if ( !*v19 )
      break;
    *v17++ = *v19++;
    --v18;
    --v24;
  }
  while ( v24 );
  v25 = v17 - 1;
  if ( v24 )
    v25 = v17;
  v13 = v24 == 0 ? 0x8007007A : 0;
  *v25 = 0;
  if ( !v24 )
    goto LABEL_44;
  v22 = (__int64 **)((char *)v8 + 32);
  v13 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *, int *, __int64 *, int))(**v22 + 432))(*v22, v54, &v39, &v48, v16);
  if ( v39 == a3 )
    goto LABEL_40;
  v23 = a3 == -2;
LABEL_37:
  if ( !v23 )
    goto LABEL_38;
LABEL_40:
  if ( v13 < 0 )
  {
LABEL_41:
    v8 = v40;
    if ( v13 == -2147024637 )
    {
      if ( a7 == 1 )
        v13 = (a6 & 1) != 0 ? -2147024894 : -2146646014;
      else
        v13 = -2147024809;
    }
LABEL_44:
    v14 = 0;
    goto LABEL_45;
  }
  v13 = CADMCOMW::DisableHistory(v40, &v43, &v44);
  if ( v13 < 0 )
  {
    v10 = v43;
    v14 = 0;
    v11 = v44;
    v8 = v40;
  }
  else
  {
    v13 = CADMCOMW::EnumAndStopDependentServices(v28, &v42, (struct BUFFER *)v50);
    if ( v13 < 0 )
      goto LABEL_66;
    _InterlockedDecrement(&g_AclCache);
    v37 = 1;
    CAdminAclCache::Flush((CAdminAclCache *)&g_AclCache);
    v29 = *v22;
    v30 = **v22;
    if ( a7 == 1 )
    {
      LODWORD(v36) = a6;
      v31 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, _QWORD, _QWORD, unsigned __int16 *))(v30 + 488))(
              v29,
              a2,
              a3,
              v46,
              v36);
    }
    else
    {
      v31 = v49
          ? (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, _QWORD, _QWORD, const unsigned __int16 *))(v30 + 464))(
              v29,
              a2,
              a3,
              a6,
              v49)
          : (*(unsigned __int64 (__fastcall **)(__int64 *, const unsigned __int16 *, _QWORD, _QWORD))(v30 + 416))(
              v29,
              a2,
              a3,
              a6);
    }
    v13 = v31;
    if ( v31 < 0 )
    {
LABEL_66:
      v10 = v43;
      v11 = v44;
    }
    v9 = v42;
    v8 = v40;
    v14 = v37;
  }
LABEL_45:
  if ( v47 )
    CADMCOMW::AuditAccess(v8, 0x119Eu, v13, 0, 0, 0, 0, 0, 0, 0, a2);
  if ( v10 || v11 )
    CADMCOMW::SetHistoryAndEWR(v8, v10, v11);
  if ( v14 )
    _InterlockedIncrement(&g_AclCache);
  if ( v9 )
  {
    v26 = v51;
    if ( v51 )
    {
      v27 = OpenSCManagerW(0, 0, 0xF003Fu);
      if ( v27 )
      {
        v32 = 0;
        for ( i = 0; i < v9; ++i )
        {
          if ( ((*((_DWORD *)&v26[6 * (v9 - i) - 3] - 1) - 1) & 0xFFFFFFFD) != 0 )
          {
            v34 = OpenServiceW(v27, (LPCWSTR)v26[6 * (v9 - i) - 6], 0xF01FFu);
            v32 = v34;
            if ( v34 )
            {
              StartServiceW(v34, 0, 0);
              WaitForServiceStatus(v32, 4u);
              CloseServiceHandle(v32);
              v32 = 0;
            }
          }
        }
        CloseServiceHandle(v27);
        if ( v32 )
          CloseServiceHandle(v32);
      }
      else
      {
        GetLastError();
      }
    }
  }
LABEL_75:
  BUFFER::~BUFFER((BUFFER *)v50);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180008ae0  push    rbp
0x180008ae2  push    rbx
0x180008ae3  push    rsi
0x180008ae4  push    rdi
0x180008ae5  push    r12
0x180008ae7  push    r13
0x180008ae9  push    r14
0x180008aeb  push    r15
0x180008aed  lea     rbp, [rsp-0C8h]
0x180008af5  sub     rsp, 1C8h
0x180008afc  mov     rax, cs:__security_cookie
0x180008b03  xor     rax, rsp
0x180008b06  mov     [rbp+100h+var_50], rax
0x180008b0d  mov     rax, [rbp+100h+arg_20]
0x180008b14  xor     ebx, ebx
0x180008b16  mov     [rbp+100h+var_160], rax
0x180008b1a  mov     rsi, rdx
0x180008b1d  lea     rax, [rbp+100h+var_158]
0x180008b21  mov     [rsp+200h+var_19C], r8d
0x180008b26  mov     r13, rcx
0x180008b29  mov     [rsp+200h+var_190], rcx
0x180008b2e  xor     edx, edx; Val
0x180008b30  mov     [rbp+100h+var_138], rax
0x180008b34  mov     r8d, 0C8h; Size
0x180008b3a  mov     [rbp+100h+var_174], r9d
0x180008b3e  lea     rcx, [rbp+100h+var_120]; void *
0x180008b42  mov     [rbp+100h+var_158], rbx
0x180008b46  mov     [rbp+100h+var_130], 20h ; ' '
0x180008b4d  mov     r14d, ebx
0x180008b50  mov     [rbp+100h+var_12C], 100h
0x180008b56  mov     [rsp+200h+var_184], ebx
0x180008b5a  call    memset_0
0x180008b5f  cmp     [rbp+100h+arg_30], 1
0x180008b66  mov     r15d, ebx
0x180008b69  mov     [rsp+200h+var_198], ebx
0x180008b6d  mov     r12d, ebx
0x180008b70  mov     [rbp+100h+var_178], ebx
0x180008b73  mov     [rbp+100h+var_168], rbx
0x180008b77  mov     [rbp+100h+var_180], ebx
0x180008b7a  mov     [rbp+100h+var_17C], ebx
0x180008b7d  mov     [rbp+100h+var_170], ebx
0x180008b80  jz      short loc_180008B90
0x180008b82  cmp     [rbp+100h+arg_30], 2
0x180008b89  jnz     short loc_180008BA8
0x180008b8b  test    rsi, rsi
0x180008b8e  jz      short loc_180008BA8
0x180008b90  test    rsi, rsi
0x180008b93  jz      short loc_180008BB2
0x180008b95  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008b99  inc     rax
0x180008b9c  cmp     [rsi+rax*2], bx
0x180008ba0  jnz     short loc_180008B99
0x180008ba2  cmp     rax, 64h ; 'd'
0x180008ba6  jb      short loc_180008BB2
0x180008ba8  mov     ebx, 80070057h
0x180008bad  jmp     loc_180009025
0x180008bb2  lea     rax, [rbp+100h+var_170]
0x180008bb6  mov     [rsp+200h+var_1A0], ebx
0x180008bba  mov     [rsp+200h+var_1C0], rax
0x180008bbf  lea     r8, byte_1800127D8
0x180008bc6  mov     qword ptr [rsp+200h+var_1C8], rbx
0x180008bcb  lea     rax, ?g_ohMasterRootHandle@@3VCOpenHandle@@A; COpenHandle g_ohMasterRootHandle
0x180008bd2  mov     [rsp+200h+var_1D0], rax
0x180008bd7  xor     r9d, r9d
0x180008bda  mov     qword ptr [rsp+200h+var_1D8], rbx
0x180008bdf  xor     edx, edx
0x180008be1  mov     rcx, r13
0x180008be4  mov     dword ptr [rsp+200h+var_1E0], 2
0x180008bec  mov     edi, ebx
0x180008bee  call    ?AccessCheck@CADMCOMW@@QEAAJKPEBGW4ACTP_ACCESSTYPE@@1PEAU_METADATA_RECORD@@PEAVCOpenHandle@@PEAH4@Z; CADMCOMW::AccessCheck(ulong,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,COpenHandle *,int *,int *)
0x180008bf3  xor     r11d, r11d
0x180008bf6  mov     ebx, eax
0x180008bf8  test    eax, eax
0x180008bfa  jns     short loc_180008C42
0x180008bfc  test    byte ptr cs:g_dwDebugFlags, 3
0x180008c03  jz      loc_180008E0F
0x180008c09  mov     rcx, cs:g_pDebug
0x180008c10  lea     r9, aCadmcomwRestor; "CADMCOMW::RestoreHelper"
0x180008c17  mov     [rsp+200h+var_1D8], eax
0x180008c1b  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180008c22  lea     rax, aAccesscheckFai; "AccessCheck failed hr = 0x%08x\n"
0x180008c29  mov     r8d, 0C13h
0x180008c2f  mov     [rsp+200h+var_1E0], rax
0x180008c34  call    cs:__imp_PuDbgPrint
0x180008c3a  xor     r11d, r11d
0x180008c3d  jmp     loc_180008E0F
0x180008c42  mov     edi, [rbp+100h+arg_28]
0x180008c48  mov     r10d, r11d
0x180008c4b  mov     [rsp+200h+var_188], r11d
0x180008c50  cmp     [rbp+100h+arg_30], 1
0x180008c57  lea     r8, [rbp+100h+var_120]
0x180008c5b  mov     ecx, 7FFFFFFEh
0x180008c60  mov     rax, rsi
0x180008c63  jnz     loc_180008D1F
0x180008c69  lea     rdx, byte_1800127D8
0x180008c70  test    rsi, rsi
0x180008c73  cmovz   rax, rdx
0x180008c77  mov     edx, 64h ; 'd'
0x180008c7c  test    rcx, rcx
0x180008c7f  jz      short loc_180008CA0
0x180008c81  movzx   r9d, word ptr [rax]
0x180008c85  test    r9w, r9w
0x180008c89  jz      short loc_180008CA0
0x180008c8b  mov     [r8], r9w
0x180008c8f  add     rax, 2
0x180008c93  add     r8, 2
0x180008c97  dec     rcx
0x180008c9a  sub     rdx, 1
0x180008c9e  jnz     short loc_180008C7C
0x180008ca0  test    rdx, rdx
0x180008ca3  lea     rcx, [r8-2]
0x180008ca7  mov     rax, rdx
0x180008caa  cmovnz  rcx, r8
0x180008cae  neg     rax
0x180008cb1  sbb     ebx, ebx
0x180008cb3  not     ebx
0x180008cb5  and     ebx, 8007007Ah
0x180008cbb  mov     [rcx], r11w
0x180008cbf  test    rdx, rdx
0x180008cc2  jz      loc_180008E0C
0x180008cc8  lea     rdx, [rbp+100h+var_168]
0x180008ccc  mov     [rsp+200h+var_1D8], r10d
0x180008cd1  mov     [rsp+200h+var_1E0], rdx
0x180008cd6  lea     r9, [rbp+100h+var_178]
0x180008cda  add     r13, 20h ; ' '
0x180008cde  lea     r8, [rsp+200h+var_198]
0x180008ce3  lea     rdx, [rbp+100h+var_120]
0x180008ce7  mov     rcx, [r13+0]
0x180008ceb  mov     rax, [rcx]
0x180008cee  mov     rax, [rax+1F0h]
0x180008cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cfa  mov     ebx, eax
0x180008cfc  test    dil, 1
0x180008d00  jnz     loc_180008DD2
0x180008d06  mov     eax, [rsp+200h+var_19C]
0x180008d0a  cmp     [rsp+200h+var_198], eax
0x180008d0e  jnz     loc_180008DB8
0x180008d14  mov     eax, [rbp+100h+var_174]
0x180008d17  cmp     [rbp+100h+var_178], eax
0x180008d1a  jmp     loc_180008DB6
0x180008d1f  lea     rdx, aMdbackup; "MDBackUp"
0x180008d26  test    rsi, rsi
0x180008d29  cmovz   rax, rdx
0x180008d2d  mov     edx, 64h ; 'd'
0x180008d32  test    rcx, rcx
0x180008d35  jz      short loc_180008D56
0x180008d37  movzx   r9d, word ptr [rax]
0x180008d3b  test    r9w, r9w
0x180008d3f  jz      short loc_180008D56
0x180008d41  mov     [r8], r9w
0x180008d45  add     rax, 2
0x180008d49  add     r8, 2
0x180008d4d  dec     rcx
0x180008d50  sub     rdx, 1
0x180008d54  jnz     short loc_180008D32
0x180008d56  test    rdx, rdx
0x180008d59  lea     rcx, [r8-2]
0x180008d5d  mov     rax, rdx
0x180008d60  cmovnz  rcx, r8
0x180008d64  neg     rax
0x180008d67  sbb     ebx, ebx
0x180008d69  not     ebx
0x180008d6b  and     ebx, 8007007Ah
0x180008d71  mov     [rcx], r11w
0x180008d75  test    rdx, rdx
0x180008d78  jz      loc_180008E0C
0x180008d7e  add     r13, 20h ; ' '
0x180008d82  mov     dword ptr [rsp+200h+var_1E0], r10d
0x180008d87  lea     r9, [rbp+100h+var_168]
0x180008d8b  lea     r8, [rsp+200h+var_198]
0x180008d90  lea     rdx, [rbp+100h+var_120]
0x180008d94  mov     rcx, [r13+0]
0x180008d98  mov     rax, [rcx]
0x180008d9b  mov     rax, [rax+1B0h]
0x180008da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008da7  mov     ebx, eax
0x180008da9  mov     eax, [rsp+200h+var_19C]
0x180008dad  cmp     [rsp+200h+var_198], eax
0x180008db1  jz      short loc_180008DD2
0x180008db3  cmp     eax, 0FFFFFFFEh
0x180008db6  jz      short loc_180008DD2
0x180008db8  inc     [rsp+200h+var_188]
0x180008dbc  xor     r11d, r11d
0x180008dbf  test    ebx, ebx
0x180008dc1  js      short loc_180008DDD
0x180008dc3  mov     r10d, [rsp+200h+var_188]
0x180008dc8  mov     r13, [rsp+200h+var_190]
0x180008dcd  jmp     loc_180008C50
0x180008dd2  xor     r11d, r11d
0x180008dd5  test    ebx, ebx
0x180008dd7  jns     loc_180008EB5
0x180008ddd  mov     r13, [rsp+200h+var_190]
0x180008de2  cmp     ebx, 80070103h
0x180008de8  jnz     short loc_180008E0C
0x180008dea  cmp     [rbp+100h+arg_30], 1
0x180008df1  jnz     loc_180008EAB
0x180008df7  and     dil, 1
0x180008dfb  neg     dil
0x180008dfe  sbb     ebx, ebx
0x180008e00  and     ebx, 0FFFA3800h
0x180008e06  add     ebx, 800CC802h
0x180008e0c  mov     edi, r12d
0x180008e0f  cmp     [rbp+100h+var_170], r11d
0x180008e13  jz      short loc_180008E4B
0x180008e15  mov     [rsp+200h+var_1B0], rsi; unsigned __int16 *
0x180008e1a  xor     r9d, r9d; unsigned int
0x180008e1d  mov     [rsp+200h+var_1B8], r11; struct _METADATA_RECORD *
0x180008e22  mov     r8d, ebx; int
0x180008e25  mov     [rsp+200h+var_1C0], r11; struct _METADATA_RECORD *
0x180008e2a  mov     edx, 119Eh; unsigned int
0x180008e2f  mov     [rsp+200h+var_1C8], r11d; unsigned int
0x180008e34  mov     rcx, r13; this
0x180008e37  mov     [rsp+200h+var_1D0], r11; unsigned __int16 *
0x180008e3c  mov     [rsp+200h+var_1D8], r11d; unsigned int
0x180008e41  mov     [rsp+200h+var_1E0], r11; unsigned __int16 *
0x180008e46  call    ?AuditAccess@CADMCOMW@@AEAAJKJKPEBGK0KPEAU_METADATA_RECORD@@10@Z; CADMCOMW::AuditAccess(ulong,long,ulong,ushort const *,ulong,ushort const *,ulong,_METADATA_RECORD *,_METADATA_RECORD *,ushort const *)
0x180008e4b  test    r15d, r15d
0x180008e4e  jnz     short loc_180008E55
0x180008e50  test    r12d, r12d
0x180008e53  jz      short loc_180008E63
0x180008e55  mov     r8d, r12d; unsigned int
0x180008e58  mov     edx, r15d; unsigned int
0x180008e5b  mov     rcx, r13; this
0x180008e5e  call    ?SetHistoryAndEWR@CADMCOMW@@AEAAJKK@Z; CADMCOMW::SetHistoryAndEWR(ulong,ulong)
0x180008e63  test    edi, edi
0x180008e65  jz      short loc_180008E6E
0x180008e67  lock inc cs:?g_AclCache@@3VCAdminAclCache@@A; CAdminAclCache g_AclCache
0x180008e6e  test    r14d, r14d
0x180008e71  jz      loc_180009025
0x180008e77  mov     r15, [rbp+100h+var_138]
0x180008e7b  test    r15, r15
0x180008e7e  jz      loc_180009025
0x180008e84  xor     edx, edx; lpDatabaseName
0x180008e86  xor     ecx, ecx; lpMachineName
0x180008e88  mov     r8d, 0F003Fh; dwDesiredAccess
0x180008e8e  call    cs:__imp_OpenSCManagerW
0x180008e94  mov     r12, rax
0x180008e97  test    rax, rax
0x180008e9a  jnz     loc_180008FA1
0x180008ea0  call    cs:__imp_GetLastError
0x180008ea6  jmp     loc_180009025
0x180008eab  mov     ebx, 80070057h
0x180008eb0  jmp     loc_180008E0C
0x180008eb5  mov     rcx, [rsp+200h+var_190]; this
0x180008eba  lea     r8, [rbp+100h+var_17C]; unsigned int *
0x180008ebe  lea     rdx, [rbp+100h+var_180]; unsigned int *
0x180008ec2  call    ?DisableHistory@CADMCOMW@@AEAAJPEAK0@Z; CADMCOMW::DisableHistory(ulong *,ulong *)
0x180008ec7  xor     r11d, r11d
0x180008eca  mov     ebx, eax
0x180008ecc  test    eax, eax
0x180008ece  js      loc_180008F8C
0x180008ed4  lea     r8, [rbp+100h+var_158]; struct BUFFER *
0x180008ed8  lea     rdx, [rsp+200h+var_184]; unsigned int *
0x180008edd  call    ?EnumAndStopDependentServices@CADMCOMW@@AEAAJPEAKPEAVBUFFER@@@Z; CADMCOMW::EnumAndStopDependentServices(ulong *,BUFFER *)
0x180008ee2  xor     r11d, r11d
0x180008ee5  mov     ebx, eax
0x180008ee7  test    eax, eax
0x180008ee9  js      loc_180008F82
0x180008eef  lock dec cs:?g_AclCache@@3VCAdminAclCache@@A; CAdminAclCache g_AclCache
0x180008ef6  lea     rcx, ?g_AclCache@@3VCAdminAclCache@@A; this
0x180008efd  mov     [rsp+200h+var_1A0], 1
0x180008f05  call    ?Flush@CAdminAclCache@@QEAAJXZ; CAdminAclCache::Flush(void)
0x180008f0a  cmp     [rbp+100h+arg_30], 1
0x180008f11  mov     rcx, [r13+0]
0x180008f15  mov     rax, [rcx]
0x180008f18  jnz     short loc_180008F2B
0x180008f1a  mov     r9d, [rbp+100h+var_174]
0x180008f1e  mov     rax, [rax+1E8h]
0x180008f25  mov     dword ptr [rsp+200h+var_1E0], edi
0x180008f29  jmp     short loc_180008F59
0x180008f2b  mov     rdx, [rbp+100h+var_160]
0x180008f2f  mov     r9d, edi
0x180008f32  test    rdx, rdx
0x180008f35  jnz     short loc_180008F4D
0x180008f37  mov     r8d, [rsp+200h+var_19C]
0x180008f3c  mov     rdx, rsi
0x180008f3f  mov     rax, [rax+1A0h]
0x180008f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f4b  jmp     short loc_180008F66
0x180008f4d  mov     rax, [rax+1D0h]
0x180008f54  mov     [rsp+200h+var_1E0], rdx
0x180008f59  mov     r8d, [rsp+200h+var_19C]
0x180008f5e  mov     rdx, rsi
0x180008f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f66  xor     r11d, r11d
0x180008f69  mov     ebx, eax
0x180008f6b  test    eax, eax
0x180008f6d  js      short loc_180008F82
0x180008f6f  mov     r14d, [rsp+200h+var_184]
0x180008f74  mov     r13, [rsp+200h+var_190]
0x180008f79  mov     edi, [rsp+200h+var_1A0]
0x180008f7d  jmp     loc_180008E0F
0x180008f82  mov     r15d, [rbp+100h+var_180]
0x180008f86  mov     r12d, [rbp+100h+var_17C]
0x180008f8a  jmp     short loc_180008F6F
0x180008f8c  mov     r15d, [rbp+100h+var_180]
0x180008f90  mov     edi, r11d
0x180008f93  mov     r12d, [rbp+100h+var_17C]
0x180008f97  mov     r13, [rsp+200h+var_190]
0x180008f9c  jmp     loc_180008E0F
  ... truncated ...
```
