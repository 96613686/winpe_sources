# CADMCOMW::CreateNewContext(ulong,_MD_CHANGE_OBJECT_W *,int)

- ea: `0x180003590`
- end: `0x180003c8f`
- name: `?CreateNewContext@CADMCOMW@@AEAAJKPEAU_MD_CHANGE_OBJECT_W@@H@Z`
- size: `1791`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, struct _MD_CHANGE_OBJECT_W *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180007a50`
- `0x180009770`

## callees

- `0x180001064`
- `0x1800010a4`
- `0x1800010bc`
- `0x180001c3c`
- `0x180003048`
- `0x180003590`
- `0x1800076b8`
- `0x180009b4c`
- `0x18000fb06`
- `0x18000fb1e`
- `0x18000fb50`
- `0x180010010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180003ba6`
- `KERNEL32!SetEvent` at `0x180003ba6`
- `KERNEL32!LeaveCriticalSection` at `0x180003bc8`
- `KERNEL32!LeaveCriticalSection` at `0x180003c48`
- `KERNEL32!LeaveCriticalSection` at `0x180003bc8`
- `KERNEL32!LeaveCriticalSection` at `0x180003c48`
- `KERNEL32!EnterCriticalSection` at `0x180003b99`
- `KERNEL32!EnterCriticalSection` at `0x180003b99`
- `KERNEL32!GetLastError` at `0x180003bb0`
- `KERNEL32!GetLastError` at `0x180003bb0`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003674`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003674`
- `IisRTL!PuDbgPrint` at `0x1800036bc`
- `IisRTL!PuDbgPrint` at `0x180003776`
- `IisRTL!PuDbgPrint` at `0x1800037fd`
- `IisRTL!PuDbgPrint` at `0x180003878`
- `IisRTL!PuDbgPrint` at `0x180003a0e`
- `IisRTL!PuDbgPrint` at `0x180003a7d`
- `IisRTL!PuDbgPrint` at `0x180003ae7`
- `IisRTL!PuDbgPrint` at `0x180003c0e`
- `IisRTL!PuDbgPrint` at `0x1800036bc`
- `IisRTL!PuDbgPrint` at `0x180003776`
- `IisRTL!PuDbgPrint` at `0x1800037fd`
- `IisRTL!PuDbgPrint` at `0x180003878`
- `IisRTL!PuDbgPrint` at `0x180003a0e`
- `IisRTL!PuDbgPrint` at `0x180003a7d`
- `IisRTL!PuDbgPrint` at `0x180003ae7`
- `IisRTL!PuDbgPrint` at `0x180003c0e`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800035f7`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800035f7`

## string_xrefs

- `0x18000369e`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180003758`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x1800037c2`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180003865`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180003a07`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180003a65`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180003ace`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180003c07`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180003692`: `CADMCOMW::CreateNewContext`
- `0x18000374a`: `CADMCOMW::CreateNewContext`
- `0x1800037b4`: `CADMCOMW::CreateNewContext`
- `0x180003859`: `CADMCOMW::CreateNewContext`
- `0x1800039f5`: `CADMCOMW::CreateNewContext`
- `0x180003a57`: `CADMCOMW::CreateNewContext`
- `0x180003ac3`: `CADMCOMW::CreateNewContext`
- `0x18000376a`: `Normalizing the path %S.\n`
- `0x180003ad5`: `NormalizeMDPath failed with 0x%08x.\n`
- `0x1800037f1`: `Checking the path %S with length %d against the scope [%S] with length %d and flags 0x%08x.\n`
- `0x1800039ee`: `No paths in the notification matched the scope.\n`
- `0x180003bf5`: `NOTIFY_CONTEXT::CreateNewContext`

## pseudocode

```c
__int64 __fastcall CADMCOMW::CreateNewContext(CADMCOMW *this, unsigned int a2, struct _MD_CHANGE_OBJECT_W *a3, int a4)
{
  unsigned __int64 v4; // r13
  CReaderWriterLock3 *v5; // rdi
  CADMCOMW *v6; // r14
  struct _MD_CHANGE_OBJECT_W *v8; // rsi
  __int64 v9; // rax
  unsigned __int16 *v10; // rcx
  __int64 v11; // r8
  unsigned __int16 *v12; // r9
  unsigned __int16 *v13; // rdx
  signed int v14; // ebx
  unsigned int v15; // ebx
  unsigned int v16; // r12d
  struct _MD_CHANGE_OBJECT_W *v17; // rax
  unsigned int v18; // r15d
  unsigned int v19; // r13d
  struct _MD_CHANGE_OBJECT_W *v20; // rdi
  CADMCOMW *v21; // rcx
  __int64 v22; // r14
  int v23; // eax
  CADMCOMW *v24; // rcx
  unsigned int v25; // ebx
  int v26; // eax
  const char *v27; // rcx
  LPWSTR pszMDPath; // rax
  __int64 v29; // rdi
  unsigned __int64 v30; // rdi
  _WORD *v31; // rax
  _WORD *v32; // rdx
  struct _MD_CHANGE_OBJECT_W *v33; // r9
  __int64 v34; // rax
  LPWSTR v35; // rcx
  _WORD *v36; // rcx
  DWORD dwMDNumDataIDs; // eax
  __int64 v38; // rbx
  DWORD *v39; // rax
  int v40; // ebx
  const char *v41; // rax
  _QWORD *v43; // rax
  NOTIFY_CONTEXT *v44; // rdi
  _QWORD *v45; // rax
  __int64 v46; // rcx
  signed int LastError; // eax
  _QWORD *v48; // rdx
  unsigned int v49; // [rsp+20h] [rbp-E0h]
  struct _MD_CHANGE_OBJECT_W *v51; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v52; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v53; // [rsp+64h] [rbp-9Ch]
  unsigned int v54; // [rsp+68h] [rbp-98h]
  int v55; // [rsp+6Ch] [rbp-94h]
  struct _MD_CHANGE_OBJECT_W *v56; // [rsp+70h] [rbp-90h] BYREF
  CADMCOMW *v57; // [rsp+78h] [rbp-88h]
  unsigned __int16 v58[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v59[520]; // [rsp+290h] [rbp+190h] BYREF

  v4 = a2;
  v5 = (CADMCOMW *)((char *)this + 800);
  v57 = this;
  v6 = this;
  v55 = a4;
  v51 = a3;
  v52 = 0;
  v8 = 0;
  v56 = 0;
  CReaderWriterLock3::ReadLock((CADMCOMW *)((char *)this + 800));
  v9 = 2147483646;
  v10 = (unsigned __int16 *)((char *)v6 + 256);
  v11 = 257;
  v12 = v58;
  do
  {
    if ( !v9 )
      break;
    if ( !*v10 )
      break;
    *v12++ = *v10++;
    --v9;
    --v11;
  }
  while ( v11 );
  v13 = v12 - 1;
  v14 = v11 == 0 ? 0x8007007A : 0;
  if ( v11 )
    v13 = v12;
  *v13 = 0;
  if ( !v11 )
    goto LABEL_52;
  v15 = *((_DWORD *)v6 + 194);
  v16 = *((_DWORD *)v6 + 193);
  v53 = v15;
  v54 = v16;
  CReaderWriterLock3::ReadUnlock(v5);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
      5338,
      "CADMCOMW::CreateNewContext",
      "Got the scope [%S] with length %d and flags 0x%08x.\n",
      v58,
      v16,
      v15);
  if ( a4 )
  {
    v17 = (struct _MD_CHANGE_OBJECT_W *)operator new[](saturated_mul(v4, 0x18u));
    v56 = v17;
    v8 = v17;
    if ( !v17 )
    {
      v14 = -2147024882;
      goto LABEL_52;
    }
    memset_0(v17, 0, 24 * v4);
  }
  v18 = 0;
  v19 = 0;
  if ( !a2 )
  {
LABEL_46:
    v40 = v55;
    if ( v55 && !v18 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
          5439,
          "CADMCOMW::CreateNewContext",
          "No paths in the notification matched the scope.\n");
      v14 = 1;
      goto LABEL_51;
    }
    v51 = v8;
    if ( (v18 != 0) == (v8 != 0) )
    {
      v43 = operator new(0x38u);
      v44 = (NOTIFY_CONTEXT *)v43;
      if ( v43 )
      {
        v43[1] = v6;
        *(_DWORD *)v43 = 1481917262;
        *((_DWORD *)v43 + 4) = v18;
        v43[3] = v8;
        *((_DWORD *)v43 + 8) = v40;
        v45 = v43 + 5;
        v45[1] = v45;
        *v45 = v45;
        v46 = *((_QWORD *)v44 + 1);
        if ( v46 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 8LL))(v46);
        v51 = 0;
        v8 = 0;
        EnterCriticalSection(&NOTIFY_CONTEXT::s_critSec);
        if ( SetEvent(NOTIFY_CONTEXT::s_hDataAvailable) )
        {
          v48 = (_QWORD *)qword_180016ED8;
          if ( *(struct _LIST_ENTRY **)qword_180016ED8 != &NOTIFY_CONTEXT::s_listEntry )
            __fastfail(3u);
          *((_QWORD *)v44 + 5) = &NOTIFY_CONTEXT::s_listEntry;
          *((_QWORD *)v44 + 6) = v48;
          *v48 = (char *)v44 + 40;
          qword_180016ED8 = (__int64)v44 + 40;
          LeaveCriticalSection(&NOTIFY_CONTEXT::s_critSec);
          v14 = 0;
        }
        else
        {
          LastError = GetLastError();
          v14 = LastError;
          if ( LastError > 0 )
            v14 = (unsigned __int16)LastError | 0x80070000;
          LeaveCriticalSection(&NOTIFY_CONTEXT::s_critSec);
          if ( v14 < 0 )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
                5682,
                "NOTIFY_CONTEXT::CreateNewContext",
                "NOTIFY_CONTEXT::AddToList failed with 0x%08x.\n",
                v14);
            NOTIFY_CONTEXT::~NOTIFY_CONTEXT(v44);
            operator delete(v44);
            goto LABEL_54;
          }
        }
      }
      else
      {
        v14 = -2147024882;
      }
    }
    else
    {
      v14 = -2147024809;
    }
    if ( v8 )
      DeleteChangeObjectArray(v18, &v51);
    goto LABEL_54;
  }
  v20 = v51;
  while ( 1 )
  {
    v21 = (CADMCOMW *)(3LL * v19);
    v22 = v19;
    if ( v16 <= 1 )
      goto LABEL_27;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        5356,
        "CADMCOMW::CreateNewContext",
        "Normalizing the path %S.\n",
        v20[v22].pszMDPath);
    v23 = CADMCOMW::NormalizeMDPath(v21, v20[v19].pszMDPath, v16, v59, v49, &v52);
    v14 = v23;
    if ( v23 < 0 )
      break;
    v25 = v52;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        5375,
        "CADMCOMW::CreateNewContext",
        "Checking the path %S with length %d against the scope [%S] with length %d and flags 0x%08x.\n",
        v59,
        v52,
        v58,
        v16,
        v53);
    v26 = CADMCOMW::CheckNotificationScope(v24, v59, v25, v58, v16, v53);
    if ( v26 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v27 = "failed";
        if ( v26 >= 0 )
          v27 = "rejected the notification";
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
          5382,
          "CADMCOMW::CreateNewContext",
          "CheckNotificationScope %s with 0x%08x.\n",
          v27,
          v26);
      }
      goto LABEL_44;
    }
LABEL_27:
    pszMDPath = v20[v19].pszMDPath;
    v29 = -1;
    do
      ++v29;
    while ( pszMDPath[v29] );
    if ( !v8 )
    {
      v14 = -2147467261;
      goto LABEL_54;
    }
    v30 = v29 + 1;
    v31 = operator new[](saturated_mul(v30, 2u));
    v32 = v31;
    v8[v18].pszMDPath = v31;
    if ( !v31 )
      goto LABEL_61;
    if ( v30 )
    {
      if ( v30 > 0x7FFFFFFF )
      {
        v14 = -2147024809;
        *v31 = 0;
        goto LABEL_51;
      }
      v33 = v51;
      v34 = 2147483646;
      v35 = v51[v19].pszMDPath;
      do
      {
        if ( !v34 )
          break;
        if ( !*v35 )
          break;
        *v32++ = *v35++;
        --v34;
        --v30;
      }
      while ( v30 );
      v36 = v32 - 1;
      if ( v30 )
        v36 = v32;
      v14 = v30 == 0 ? 0x8007007A : 0;
      *v36 = 0;
    }
    else
    {
      v14 = -2147024809;
      v33 = v51;
    }
    if ( v14 < 0 )
      goto LABEL_51;
    v8[v18].dwMDChangeType = v33[v22].dwMDChangeType;
    dwMDNumDataIDs = v33[v22].dwMDNumDataIDs;
    v8[v18].dwMDNumDataIDs = dwMDNumDataIDs;
    v38 = dwMDNumDataIDs;
    v39 = (DWORD *)operator new[](saturated_mul(dwMDNumDataIDs, 4u));
    v8[v18].pdwMDDataIDs = v39;
    if ( !v39 )
    {
LABEL_61:
      v14 = -2147024882;
      goto LABEL_51;
    }
    v20 = v51;
    memcpy_0(v39, v51[v22].pdwMDDataIDs, 4 * v38);
    v16 = v54;
    ++v18;
LABEL_44:
    if ( ++v19 >= a2 )
    {
      v6 = v57;
      goto LABEL_46;
    }
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
      5362,
      "CADMCOMW::CreateNewContext",
      "NormalizeMDPath failed with 0x%08x.\n",
      v23);
LABEL_51:
  LODWORD(v4) = a2;
LABEL_52:
  if ( v8 )
    DeleteChangeObjectArray((unsigned int)v4, &v56);
LABEL_54:
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v41 = "failed";
    if ( v14 >= 0 )
      v41 = "succeeded";
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
      5458,
      "CADMCOMW::CreateNewContext",
      "%s with 0x%08x.\n",
      v41,
      v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180003590  mov     [rsp-8+arg_18], rbx
0x180003595  push    rbp
0x180003596  push    rsi
0x180003597  push    rdi
0x180003598  push    r12
0x18000359a  push    r13
0x18000359c  push    r14
0x18000359e  push    r15
0x1800035a0  lea     rbp, [rsp-5B0h]
0x1800035a8  sub     rsp, 6B0h
0x1800035af  mov     rax, cs:__security_cookie
0x1800035b6  xor     rax, rsp
0x1800035b9  mov     [rbp+5E0h+var_40], rax
0x1800035c0  xor     r12d, r12d
0x1800035c3  mov     r13d, edx
0x1800035c6  lea     rdi, [rcx+320h]
0x1800035cd  mov     [rsp+6E0h+var_668], rcx
0x1800035d2  mov     r14, rcx
0x1800035d5  mov     [rsp+6E0h+var_674], r9d
0x1800035da  mov     rcx, rdi
0x1800035dd  mov     [rsp+6E0h+var_688], r8
0x1800035e2  mov     r15d, r9d
0x1800035e5  mov     [rsp+6E0h+var_690], r13d
0x1800035ea  mov     [rsp+6E0h+var_680], r12d
0x1800035ef  mov     esi, r12d
0x1800035f2  mov     [rsp+6E0h+var_670], r12
0x1800035f7  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800035fd  mov     eax, 7FFFFFFEh
0x180003602  lea     rcx, [r14+100h]
0x180003609  mov     r8d, 101h
0x18000360f  lea     r9, [rbp+5E0h+var_660]
0x180003613  test    rax, rax
0x180003616  jz      short loc_180003635
0x180003618  movzx   edx, word ptr [rcx]
0x18000361b  test    dx, dx
0x18000361e  jz      short loc_180003635
0x180003620  mov     [r9], dx
0x180003624  add     rcx, 2
0x180003628  add     r9, 2
0x18000362c  dec     rax
0x18000362f  sub     r8, 1
0x180003633  jnz     short loc_180003613
0x180003635  mov     rax, r8
0x180003638  lea     rdx, [r9-2]
0x18000363c  neg     rax
0x18000363f  sbb     ebx, ebx
0x180003641  not     ebx
0x180003643  and     ebx, 8007007Ah
0x180003649  test    r8, r8
0x18000364c  cmovnz  rdx, r9
0x180003650  mov     [rdx], r12w
0x180003654  jz      loc_180003A1E
0x18000365a  mov     ebx, [r14+308h]
0x180003661  mov     rcx, rdi
0x180003664  mov     r12d, [r14+304h]
0x18000366b  mov     [rsp+6E0h+var_67C], ebx
0x18000366f  mov     [rsp+6E0h+var_678], r12d
0x180003674  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000367a  test    byte ptr cs:g_dwDebugFlags, 3
0x180003681  jz      short loc_1800036C2
0x180003683  mov     rcx, cs:g_pDebug
0x18000368a  lea     rax, [rbp+5E0h+var_660]
0x18000368e  mov     dword ptr [rsp+6E0h+var_6A8], ebx
0x180003692  lea     r9, aCadmcomwCreate; "CADMCOMW::CreateNewContext"
0x180003699  mov     [rsp+6E0h+var_6B0], r12d
0x18000369e  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x1800036a5  mov     [rsp+6E0h+var_6B8], rax
0x1800036aa  mov     r8d, 14DAh
0x1800036b0  lea     rax, aGotTheScopeSWi; "Got the scope [%S] with length %d and f"...
0x1800036b7  mov     qword ptr [rsp+6E0h+var_6C0], rax
0x1800036bc  call    cs:__imp_PuDbgPrint
0x1800036c2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800036c6  xor     edi, edi
0x1800036c8  test    r15d, r15d
0x1800036cb  jz      short loc_18000370F
0x1800036cd  lea     eax, [rcx+19h]
0x1800036d0  mul     r13
0x1800036d3  cmovb   rax, rcx
0x1800036d7  mov     rcx, rax; unsigned __int64
0x1800036da  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800036df  mov     [rsp+6E0h+var_670], rax
0x1800036e4  mov     rsi, rax
0x1800036e7  test    rax, rax
0x1800036ea  jnz     short loc_1800036F6
0x1800036ec  mov     ebx, 8007000Eh
0x1800036f1  jmp     loc_180003A1E
0x1800036f6  lea     r8, ds:0[r13*2]
0x1800036fe  xor     edx, edx; Val
0x180003700  add     r8, r13
0x180003703  mov     rcx, rax; void *
0x180003706  shl     r8, 3; Size
0x18000370a  call    memset_0
0x18000370f  mov     r15d, edi
0x180003712  mov     r13d, edi
0x180003715  cmp     [rsp+6E0h+var_690], edi
0x180003719  jbe     loc_1800039C6
0x18000371f  mov     rdi, [rsp+6E0h+var_688]
0x180003724  mov     eax, r13d
0x180003727  lea     rcx, [rax+rax*2]
0x18000372b  lea     r14, ds:0[rcx*8]
0x180003733  cmp     r12d, 1
0x180003737  jbe     loc_180003883
0x18000373d  test    byte ptr cs:g_dwDebugFlags, 3
0x180003744  jz      short loc_18000377C
0x180003746  mov     rax, [r14+rdi]
0x18000374a  lea     r9, aCadmcomwCreate; "CADMCOMW::CreateNewContext"
0x180003751  mov     rcx, cs:g_pDebug
0x180003758  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x18000375f  mov     [rsp+6E0h+var_6B8], rax
0x180003764  mov     r8d, 14ECh
0x18000376a  lea     rax, aNormalizingThe_1; "Normalizing the path %S.\n"
0x180003771  mov     qword ptr [rsp+6E0h+var_6C0], rax; unsigned int
0x180003776  call    cs:__imp_PuDbgPrint
0x18000377c  mov     rdx, [rdi+r14]; unsigned __int16 *
0x180003780  lea     rax, [rsp+6E0h+var_680]
0x180003785  lea     r9, [rbp+5E0h+var_450]; unsigned __int16 *
0x18000378c  mov     [rsp+6E0h+var_6B8], rax; unsigned int *
0x180003791  mov     r8d, r12d; unsigned int
0x180003794  call    ?NormalizeMDPath@CADMCOMW@@AEAAJPEBGKPEAGKPEAK@Z; CADMCOMW::NormalizeMDPath(ushort const *,ulong,ushort *,ulong,ulong *)
0x180003799  mov     ebx, eax
0x18000379b  test    eax, eax
0x18000379d  js      loc_180003AAF
0x1800037a3  test    byte ptr cs:g_dwDebugFlags, 3
0x1800037aa  mov     ebx, [rsp+6E0h+var_680]
0x1800037ae  jz      short loc_180003803
0x1800037b0  mov     eax, [rsp+6E0h+var_67C]
0x1800037b4  lea     r9, aCadmcomwCreate; "CADMCOMW::CreateNewContext"
0x1800037bb  mov     rcx, cs:g_pDebug
0x1800037c2  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x1800037c9  mov     [rsp+6E0h+var_698], eax
0x1800037cd  mov     r8d, 14FFh
0x1800037d3  mov     [rsp+6E0h+var_6A0], r12d
0x1800037d8  lea     rax, [rbp+5E0h+var_660]
0x1800037dc  mov     [rsp+6E0h+var_6A8], rax
0x1800037e1  lea     rax, [rbp+5E0h+var_450]
0x1800037e8  mov     [rsp+6E0h+var_6B0], ebx
0x1800037ec  mov     [rsp+6E0h+var_6B8], rax
0x1800037f1  lea     rax, aCheckingThePat; "Checking the path %S with length %d aga"...
0x1800037f8  mov     qword ptr [rsp+6E0h+var_6C0], rax
0x1800037fd  call    cs:__imp_PuDbgPrint
0x180003803  mov     eax, [rsp+6E0h+var_67C]
0x180003807  lea     r9, [rbp+5E0h+var_660]; unsigned __int16 *
0x18000380b  mov     dword ptr [rsp+6E0h+var_6B8], eax; unsigned int
0x18000380f  lea     rdx, [rbp+5E0h+var_450]; unsigned __int16 *
0x180003816  mov     r8d, ebx; unsigned int
0x180003819  mov     [rsp+6E0h+var_6C0], r12d; unsigned int
0x18000381e  call    ?CheckNotificationScope@CADMCOMW@@AEAAJPEBGK0KK@Z; CADMCOMW::CheckNotificationScope(ushort const *,ulong,ushort const *,ulong,ulong)
0x180003823  test    eax, eax
0x180003825  jz      short loc_180003883
0x180003827  test    byte ptr cs:g_dwDebugFlags, 3
0x18000382e  jz      loc_1800039B3
0x180003834  mov     [rsp+6E0h+var_6B0], eax
0x180003838  lea     rdx, aRejectedTheNot; "rejected the notification"
0x18000383f  test    eax, eax
0x180003841  lea     rcx, aFailed; "failed"
0x180003848  lea     rax, aChecknotificat; "CheckNotificationScope %s with 0x%08x."...
0x18000384f  mov     r8d, 1506h
0x180003855  cmovns  rcx, rdx
0x180003859  lea     r9, aCadmcomwCreate; "CADMCOMW::CreateNewContext"
0x180003860  mov     [rsp+6E0h+var_6B8], rcx
0x180003865  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x18000386c  mov     rcx, cs:g_pDebug
0x180003873  mov     qword ptr [rsp+6E0h+var_6C0], rax
0x180003878  call    cs:__imp_PuDbgPrint
0x18000387e  jmp     loc_1800039B3
0x180003883  mov     rax, [rdi+r14]
0x180003887  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000388b  mov     rdi, rcx
0x18000388e  xor     r12d, r12d
0x180003891  inc     rdi
0x180003894  cmp     [rax+rdi*2], r12w
0x180003899  jnz     short loc_180003891
0x18000389b  test    rsi, rsi
0x18000389e  jz      loc_180003B0D
0x1800038a4  inc     rdi
0x1800038a7  mov     eax, 2
0x1800038ac  mul     rdi
0x1800038af  cmovb   rax, rcx
0x1800038b3  mov     rcx, rax; unsigned __int64
0x1800038b6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800038bb  mov     ecx, r15d
0x1800038be  xor     r10d, r10d
0x1800038c1  mov     rdx, rax
0x1800038c4  lea     r12, [rcx+rcx*2]
0x1800038c8  mov     [rsi+r12*8], rax
0x1800038cc  test    rax, rax
0x1800038cf  jz      loc_180003AF2
0x1800038d5  test    rdi, rdi
0x1800038d8  jz      short loc_180003937
0x1800038da  cmp     rdi, 7FFFFFFFh
0x1800038e1  ja      loc_180003AFC
0x1800038e7  mov     r9, [rsp+6E0h+var_688]
0x1800038ec  mov     eax, 7FFFFFFEh
0x1800038f1  mov     rcx, [r9+r14]
0x1800038f5  test    rax, rax
0x1800038f8  jz      short loc_180003919
0x1800038fa  movzx   r8d, word ptr [rcx]
0x1800038fe  test    r8w, r8w
0x180003902  jz      short loc_180003919
0x180003904  mov     [rdx], r8w
0x180003908  add     rcx, 2
0x18000390c  add     rdx, 2
0x180003910  dec     rax
0x180003913  sub     rdi, 1
0x180003917  jnz     short loc_1800038F5
0x180003919  test    rdi, rdi
0x18000391c  lea     rcx, [rdx-2]
0x180003920  cmovnz  rcx, rdx
0x180003924  neg     rdi
0x180003927  sbb     ebx, ebx
0x180003929  not     ebx
0x18000392b  and     ebx, 8007007Ah
0x180003931  mov     [rcx], r10w
0x180003935  jmp     short loc_18000394A
0x180003937  mov     ebx, 80070057h
0x18000393c  test    rdi, rdi
0x18000393f  jnz     loc_180003AFC
0x180003945  mov     r9, [rsp+6E0h+var_688]
0x18000394a  test    ebx, ebx
0x18000394c  js      loc_180003A19
0x180003952  mov     eax, [r9+r14+8]
0x180003957  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000395e  mov     [rsi+r12*8+8], eax
0x180003963  mov     eax, [r9+r14+0Ch]
0x180003968  mov     [rsi+r12*8+0Ch], eax
0x18000396d  mov     ebx, eax
0x18000396f  mov     eax, 4
0x180003974  mul     rbx
0x180003977  cmovb   rax, rcx
0x18000397b  mov     rcx, rax; unsigned __int64
0x18000397e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003983  mov     [rsi+r12*8+10h], rax
0x180003988  test    rax, rax
0x18000398b  jz      loc_180003AF2
0x180003991  mov     rdi, [rsp+6E0h+var_688]
0x180003996  lea     r8, ds:0[rbx*4]; Size
0x18000399e  mov     rcx, rax; void *
0x1800039a1  mov     rdx, [rdi+r14+10h]; Src
0x1800039a6  call    memcpy_0
0x1800039ab  mov     r12d, [rsp+6E0h+var_678]
0x1800039b0  inc     r15d
0x1800039b3  inc     r13d
0x1800039b6  cmp     r13d, [rsp+6E0h+var_690]
0x1800039bb  jb      loc_180003724
0x1800039c1  mov     r14, [rsp+6E0h+var_668]
0x1800039c6  mov     ebx, [rsp+6E0h+var_674]
0x1800039ca  xor     r12d, r12d
0x1800039cd  test    ebx, ebx
0x1800039cf  jz      loc_180003B17
0x1800039d5  test    r15d, r15d
0x1800039d8  jnz     loc_180003B17
0x1800039de  test    byte ptr cs:g_dwDebugFlags, 3
0x1800039e5  jz      short loc_180003A14
0x1800039e7  mov     rcx, cs:g_pDebug
0x1800039ee  lea     rax, aNoPathsInTheNo; "No paths in the notification matched th"...
0x1800039f5  lea     r9, aCadmcomwCreate; "CADMCOMW::CreateNewContext"
0x1800039fc  mov     qword ptr [rsp+6E0h+var_6C0], rax
0x180003a01  mov     r8d, 153Fh
0x180003a07  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180003a0e  call    cs:__imp_PuDbgPrint
0x180003a14  mov     ebx, 1
0x180003a19  mov     r13d, [rsp+6E0h+var_690]
0x180003a1e  test    rsi, rsi
0x180003a21  jz      short loc_180003A30
0x180003a23  lea     rdx, [rsp+6E0h+var_670]
0x180003a28  mov     ecx, r13d
0x180003a2b  call    _DeleteChangeObjectArray
0x180003a30  test    byte ptr cs:g_dwDebugFlags, 3
0x180003a37  jz      short loc_180003A83
0x180003a39  test    ebx, ebx
0x180003a3b  mov     [rsp+6E0h+var_6B0], ebx
0x180003a3f  lea     rcx, aSucceeded; "succeeded"
0x180003a46  mov     r8d, 1552h
0x180003a4c  lea     rax, aFailed; "failed"
0x180003a53  cmovns  rax, rcx
0x180003a57  lea     r9, aCadmcomwCreate; "CADMCOMW::CreateNewContext"
0x180003a5e  mov     rcx, cs:g_pDebug
0x180003a65  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180003a6c  mov     [rsp+6E0h+var_6B8], rax
0x180003a71  lea     rax, aSWith0x08x; "%s with 0x%08x.\n"
0x180003a78  mov     qword ptr [rsp+6E0h+var_6C0], rax
0x180003a7d  call    cs:__imp_PuDbgPrint
0x180003a83  mov     eax, ebx
0x180003a85  mov     rcx, [rbp+5E0h+var_40]
0x180003a8c  xor     rcx, rsp; StackCookie
0x180003a8f  call    __security_check_cookie
0x180003a94  mov     rbx, [rsp+6E0h+arg_18]
0x180003a9c  add     rsp, 6B0h
0x180003aa3  pop     r15
0x180003aa5  pop     r14
0x180003aa7  pop     r13
0x180003aa9  pop     r12
0x180003aab  pop     rdi
0x180003aac  pop     rsi
0x180003aad  pop     rbp
0x180003aae  retn
0x180003aaf  test    byte ptr cs:g_dwDebugFlags, 3
0x180003ab6  jz      loc_180003A19
0x180003abc  mov     rcx, cs:g_pDebug
0x180003ac3  lea     r9, aCadmcomwCreate; "CADMCOMW::CreateNewContext"
  ... truncated ...
```
