# NlpUserValidateOnDc(_DOMAIN_INFO *,_NETLOGON_LOGON_INFO_CLASS,uchar *,_NETLOGON_VALIDATION_INFO_CLASS,int,int,uchar * *,uchar *)

- ea: `0x180030d88`
- end: `0x180031216`
- name: `?NlpUserValidateOnDc@@YAJPEAU_DOMAIN_INFO@@W4_NETLOGON_LOGON_INFO_CLASS@@PEAEW4_NETLOGON_VALIDATION_INFO_CLASS@@HHPEAPEAE2@Z`
- size: `1166`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e730`
- `0x180031944`

## callees

- `0x18000bd98`
- `0x18000cbe0`
- `0x18000da94`
- `0x1800109fc`
- `0x18002707c`
- `0x18002de90`
- `0x18002fdb4`
- `0x180030d88`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030e78`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003115b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030e78`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003115b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031196`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800311e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031196`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800311e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003119c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003119c`
- `ntdll!RtlLeaveCriticalSection` at `0x180030f65`
- `ntdll!RtlLeaveCriticalSection` at `0x1800311c9`
- `ntdll!RtlLeaveCriticalSection` at `0x180030f65`
- `ntdll!RtlLeaveCriticalSection` at `0x1800311c9`
- `ntdll!RtlEnterCriticalSection` at `0x180030ed5`
- `ntdll!RtlEnterCriticalSection` at `0x1800310db`
- `ntdll!RtlEnterCriticalSection` at `0x180030ed5`
- `ntdll!RtlEnterCriticalSection` at `0x1800310db`
- `netutils!NetpwNameCompare` at `0x180030ef8`
- `netutils!NetpwNameCompare` at `0x180031105`
- `netutils!NetpwNameCompare` at `0x180030ef8`
- `netutils!NetpwNameCompare` at `0x180031105`
- `SAMSRV!SamIFree_SAMPR_DOMAIN_INFO_BUFFER` at `0x1800311f6`
- `SAMSRV!SamIFree_SAMPR_DOMAIN_INFO_BUFFER` at `0x1800311f6`
- `SAMSRV!SamrQueryInformationDomain` at `0x180031098`
- `SAMSRV!SamrQueryInformationDomain` at `0x180031098`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!SamISameSite` at `0x180030e04`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!SamISameSite` at `0x180030e04`

## pseudocode

```c
__int64 __fastcall NlpUserValidateOnDc(
        __int64 a1,
        enum _NETLOGON_LOGON_INFO_CLASS a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        int a6,
        void **a7,
        _BYTE *a8)
{
  unsigned int v8; // r15d
  enum _NETLOGON_LOGON_INFO_CLASS v10; // ebp
  int v12; // edi
  int v13; // ebx
  int v14; // r12d
  _WORD *v15; // r14
  _WORD *v16; // rax
  int v17; // ebp
  __int64 *v18; // r15
  __int64 *i; // rbx
  unsigned int v20; // eax
  __int64 *v21; // rax
  __int64 **v22; // rdx
  __int64 v23; // rax
  char *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r10
  bool v28; // zf
  int v29; // eax
  unsigned int v30; // ebp
  struct _RTL_CRITICAL_SECTION *v31; // r15
  char **v32; // rsi
  char *j; // rdi
  int v34; // eax
  char *v35; // rcx
  char **v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  unsigned int v39; // r13d
  char *v40; // rax
  char ***v41; // rcx
  char *v42; // rax
  DWORD TickCount; // eax
  char *v44; // rax
  __int64 v46; // [rsp+40h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-50h]
  char v48; // [rsp+A0h] [rbp+8h] BYREF
  enum _NETLOGON_LOGON_INFO_CLASS v49; // [rsp+A8h] [rbp+10h]
  unsigned int v50; // [rsp+B0h] [rbp+18h] BYREF
  unsigned int v51; // [rsp+B8h] [rbp+20h]

  v51 = a4;
  v49 = a2;
  v8 = a4;
  v28 = *(_DWORD *)(a1 + 588) == 2;
  v10 = a2;
  v48 = 0;
  v50 = 0;
  v46 = 0;
  if ( !v28 )
    return 3221225694LL;
  v12 = a6;
  if ( !NlGlobalCDC )
  {
    if ( a6 )
      return 3221225694LL;
  }
  if ( !dword_1800F125C || a6 )
  {
LABEL_11:
    v14 = a5;
    v15 = 0;
    if ( a5 && !v12 )
    {
      v16 = LocalAlloc(0, *(unsigned __int16 *)(a3 + 32) + 2LL);
      v15 = v16;
      if ( !v16 )
      {
        v13 = -1073741801;
        goto LABEL_67;
      }
      v17 = 0;
      memcpy_0(v16, *(const void **)(a3 + 40), *(unsigned __int16 *)(a3 + 32));
      v15[(unsigned __int64)*(unsigned __int16 *)(a3 + 32) >> 1] = 0;
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 400));
      v18 = (__int64 *)(a1 + 640);
      for ( i = *(__int64 **)(a1 + 640); i != v18; i = (__int64 *)*i )
      {
        if ( !(unsigned int)NetpwNameCompare(v15, i + 3, 1) )
        {
          v20 = NetpDcElapsedTime(*((_DWORD *)i + 4));
          if ( *((_DWORD *)i + 5) > 0xAu && v20 < 0x493E0 )
            v17 = 1;
          v21 = (__int64 *)*i;
          if ( *(__int64 **)(*i + 8) != i )
            goto LABEL_61;
          v22 = (__int64 **)i[1];
          if ( *v22 != i )
            goto LABEL_61;
          *v22 = v21;
          v21[1] = (__int64)v22;
          v23 = *v18;
          if ( *(__int64 **)(*v18 + 8) != v18 )
            goto LABEL_61;
          *i = v23;
          i[1] = (__int64)v18;
          *(_QWORD *)(v23 + 8) = i;
          *v18 = (__int64)i;
          break;
        }
      }
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 400));
      if ( v17 )
      {
        NlPrintDomRoutine(4u, (struct _DOMAIN_INFO *)a1, L"Avoid send to PDC since user %ws failed recently\n", v15);
        v13 = -1073741724;
        goto LABEL_66;
      }
      v10 = v49;
      v8 = v51;
    }
    hMem = NlRefDomClientSession((struct _DOMAIN_INFO *)a1);
    if ( !hMem )
    {
      v13 = -1073741602;
      goto LABEL_65;
    }
    v13 = NlpUserValidateHigher((__int64)hMem, 0, v10, a3, v8, a7, a8, &v50);
    if ( v13 >= 0 && (NlGlobalParameters & 4) != 0 )
    {
      v24 = NlpLogonTypeToText(v10);
      NlPrintDomRoutine(
        4u,
        (struct _DOMAIN_INFO *)a1,
        L"SamLogon: %hs logon of %wZ\\%wZ from %wZ successfully handled on DC(UseHub is %hs).\n",
        v24,
        a3,
        v26,
        v25,
        v27);
    }
    if ( !v12 && v14 )
    {
      if ( v13 != -1073741718 && v13 != -1073741711 && v13 != -1073741276 )
      {
        v28 = v13 == -1073741260;
        goto LABEL_45;
      }
      v29 = SamrQueryInformationDomain(*(_QWORD *)(a1 + 376), 12, &v46);
      if ( v29 >= 0 )
      {
        v28 = *(_WORD *)(v46 + 16) == 0;
LABEL_45:
        if ( v28 )
        {
          v30 = 0;
          v31 = (struct _RTL_CRITICAL_SECTION *)(a1 + 400);
          RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 400));
          v32 = (char **)(a1 + 640);
          for ( j = *v32; j != (char *)v32; j = *(char **)j )
          {
            v34 = NetpwNameCompare(v15, j + 24, 1);
            v35 = *(char **)j;
            if ( !v34 )
            {
              if ( *((char **)v35 + 1) == j )
              {
                v36 = (char **)*((_QWORD *)j + 1);
                if ( *v36 == j )
                {
                  *v36 = v35;
                  *((_QWORD *)v35 + 1) = v36;
                  goto LABEL_60;
                }
              }
LABEL_61:
              __fastfail(3u);
            }
            ++v30;
          }
          v37 = -1;
          do
            ++v37;
          while ( v15[v37] );
          v38 = (unsigned int)(2 * v37 + 2);
          v39 = v38;
          v40 = (char *)LocalAlloc(0x40u, v38 + 32);
          j = v40;
          if ( v40 )
          {
            memcpy_0(v40 + 24, v15, v39);
            if ( v30 >= 0x32 )
            {
              v41 = (char ***)v32[1];
              if ( *v41 != v32 )
                goto LABEL_61;
              v42 = (char *)v41[1];
              if ( *(char ****)v42 != v41 )
                goto LABEL_61;
              v32[1] = v42;
              *(_QWORD *)v42 = v32;
              LocalFree(v41);
            }
LABEL_60:
            TickCount = GetTickCount();
            ++*((_DWORD *)j + 5);
            *((_DWORD *)j + 4) = TickCount;
            v44 = *v32;
            if ( *((char ***)*v32 + 1) != v32 )
              goto LABEL_61;
            *(_QWORD *)j = v44;
            *((_QWORD *)j + 1) = v32;
            *((_QWORD *)v44 + 1) = j;
            *v32 = j;
          }
          RtlLeaveCriticalSection(v31);
        }
        goto LABEL_64;
      }
      NlPrintDomRoutine(
        0x100u,
        (struct _DOMAIN_INFO *)a1,
        L"NlpUserValidateOnPdc: SamrQueryInformationDomain failed: 0x%lx\n",
        (unsigned int)v29);
    }
LABEL_64:
    NlUnrefClientSession(hMem);
LABEL_65:
    if ( !v15 )
      goto LABEL_67;
LABEL_66:
    LocalFree(v15);
    goto LABEL_67;
  }
  if ( !(unsigned __int8)IsDsGetServersAndSitesForNetLogonPresent() )
  {
    v13 = -1073741637;
    goto LABEL_16;
  }
  v13 = SamISameSite(&v48);
  if ( v13 < 0 )
  {
LABEL_16:
    NlPrintDomRoutine(0x100u, (struct _DOMAIN_INFO *)a1, L"NlpUserValidateOnPdc: Cannot SamISameSite.\n");
    goto LABEL_67;
  }
  if ( v48 )
  {
    NlPrintDomRoutine(4u, (struct _DOMAIN_INFO *)a1, L"NlpUserValidateOnPdc: BDC and PDC are in the same site.\n");
    goto LABEL_11;
  }
  NlPrintDomRoutine(
    4u,
    (struct _DOMAIN_INFO *)a1,
    L"NlpUserValidateOnPdc: Ignored a user validation on a PDC in remote site.\n");
  *a8 = 0;
  v13 = -1073741724;
LABEL_67:
  if ( v46 )
    SamIFree_SAMPR_DOMAIN_INFO_BUFFER(v46, 12);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180030d88  mov     rax, rsp
0x180030d8b  mov     [rax+20h], r9d
0x180030d8f  mov     [rax+10h], edx
0x180030d92  push    rbx
0x180030d93  push    rbp
0x180030d94  push    rsi
0x180030d95  push    rdi
0x180030d96  push    r12
0x180030d98  push    r13
0x180030d9a  push    r14
0x180030d9c  push    r15
0x180030d9e  sub     rsp, 58h
0x180030da2  xor     ebx, ebx
0x180030da4  mov     r15d, r9d
0x180030da7  cmp     dword ptr [rcx+24Ch], 2
0x180030dae  mov     r13, r8
0x180030db1  mov     ebp, edx
0x180030db3  mov     [rax+8], bl
0x180030db6  mov     rsi, rcx
0x180030db9  mov     [rax+18h], ebx
0x180030dbc  mov     [rax-58h], rbx
0x180030dc0  jnz     loc_180031200
0x180030dc6  cmp     cs:?NlGlobalCDC@@3HA, ebx; int NlGlobalCDC
0x180030dcc  mov     edi, [rsp+98h+arg_28]
0x180030dd3  jnz     short loc_180030DDD
0x180030dd5  test    edi, edi
0x180030dd7  jnz     loc_180031200
0x180030ddd  cmp     cs:dword_1800F125C, ebx
0x180030de3  mov     r14d, 4
0x180030de9  jz      short loc_180030E51
0x180030deb  test    edi, edi
0x180030ded  jnz     short loc_180030E51
0x180030def  call    IsDsGetServersAndSitesForNetLogonPresent
0x180030df4  test    al, al
0x180030df6  jz      loc_180030E90
0x180030dfc  lea     rcx, [rsp+98h+arg_0]
0x180030e04  call    cs:__imp_SamISameSite
0x180030e0a  mov     ebx, eax
0x180030e0c  test    eax, eax
0x180030e0e  js      loc_180030E95
0x180030e14  xor     ebx, ebx
0x180030e16  mov     rdx, rsi; struct _DOMAIN_INFO *
0x180030e19  mov     ecx, r14d; unsigned int
0x180030e1c  cmp     [rsp+98h+arg_0], bl
0x180030e23  jnz     short loc_180030E45
0x180030e25  lea     r8, aNlpuservalidat_20; "NlpUserValidateOnPdc: Ignored a user va"...
0x180030e2c  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180030e31  mov     rax, [rsp+98h+arg_38]
0x180030e39  mov     [rax], bl
0x180030e3b  mov     ebx, 0C0000064h
0x180030e40  jmp     loc_1800311E7
0x180030e45  lea     r8, aNlpuservalidat_19; "NlpUserValidateOnPdc: BDC and PDC are i"...
0x180030e4c  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180030e51  mov     r12d, [rsp+98h+arg_20]
0x180030e59  mov     r14, rbx
0x180030e5c  test    r12d, r12d
0x180030e5f  jz      loc_180030F9F
0x180030e65  test    edi, edi
0x180030e67  jnz     loc_180030F9F
0x180030e6d  movzx   edx, word ptr [r13+20h]
0x180030e72  xor     ecx, ecx; uFlags
0x180030e74  add     rdx, 2; uBytes
0x180030e78  call    cs:__imp_LocalAlloc
0x180030e7e  mov     r14, rax
0x180030e81  test    rax, rax
0x180030e84  jnz     short loc_180030EAE
0x180030e86  mov     ebx, 0C0000017h
0x180030e8b  jmp     loc_1800311E7
0x180030e90  mov     ebx, 0C00000BBh
0x180030e95  lea     r8, aNlpuservalidat_6; "NlpUserValidateOnPdc: Cannot SamISameSi"...
0x180030e9c  mov     rdx, rsi; struct _DOMAIN_INFO *
0x180030e9f  mov     ecx, 100h; unsigned int
0x180030ea4  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180030ea9  jmp     loc_1800311E7
0x180030eae  movzx   r8d, word ptr [r13+20h]; Size
0x180030eb3  mov     rcx, r14; void *
0x180030eb6  mov     rdx, [r13+28h]; Src
0x180030eba  mov     ebp, ebx
0x180030ebc  call    memcpy_0
0x180030ec1  movzx   ecx, word ptr [r13+20h]
0x180030ec6  shr     rcx, 1
0x180030ec9  mov     [r14+rcx*2], bx
0x180030ece  lea     rcx, [rsi+190h]; CriticalSection
0x180030ed5  call    cs:__imp_RtlEnterCriticalSection
0x180030edb  lea     r15, [rsi+280h]
0x180030ee2  mov     rbx, [r15]
0x180030ee5  cmp     rbx, r15
0x180030ee8  jz      short loc_180030F5E
0x180030eea  xor     r9d, r9d
0x180030eed  lea     rdx, [rbx+18h]
0x180030ef1  mov     rcx, r14
0x180030ef4  lea     r8d, [r9+1]
0x180030ef8  call    cs:__imp_NetpwNameCompare
0x180030efe  test    eax, eax
0x180030f00  jz      short loc_180030F07
0x180030f02  mov     rbx, [rbx]
0x180030f05  jmp     short loc_180030EE5
0x180030f07  mov     ecx, [rbx+10h]; unsigned int
0x180030f0a  call    ?NetpDcElapsedTime@@YAKK@Z; NetpDcElapsedTime(ulong)
0x180030f0f  cmp     dword ptr [rbx+14h], 0Ah
0x180030f13  jbe     short loc_180030F22
0x180030f15  cmp     eax, 493E0h
0x180030f1a  mov     eax, 1
0x180030f1f  cmovb   ebp, eax
0x180030f22  mov     rax, [rbx]
0x180030f25  cmp     [rax+8], rbx
0x180030f29  jnz     loc_1800311B1
0x180030f2f  mov     rdx, [rbx+8]
0x180030f33  cmp     [rdx], rbx
0x180030f36  jnz     loc_1800311B1
0x180030f3c  mov     [rdx], rax
0x180030f3f  mov     [rax+8], rdx
0x180030f43  mov     rax, [r15]
0x180030f46  cmp     [rax+8], r15
0x180030f4a  jnz     loc_1800311B1
0x180030f50  mov     [rbx], rax
0x180030f53  mov     [rbx+8], r15
0x180030f57  mov     [rax+8], rbx
0x180030f5b  mov     [r15], rbx
0x180030f5e  lea     rcx, [rsi+190h]; CriticalSection
0x180030f65  call    cs:__imp_RtlLeaveCriticalSection
0x180030f6b  test    ebp, ebp
0x180030f6d  jz      short loc_180030F90
0x180030f6f  mov     r9, r14
0x180030f72  lea     r8, aAvoidSendToPdc; "Avoid send to PDC since user %ws failed"...
0x180030f79  mov     rdx, rsi; struct _DOMAIN_INFO *
0x180030f7c  mov     ecx, 4; unsigned int
0x180030f81  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180030f86  mov     ebx, 0C0000064h
0x180030f8b  jmp     loc_1800311DE
0x180030f90  mov     ebp, [rsp+98h+arg_8]
0x180030f97  mov     r15d, [rsp+98h+arg_18]
0x180030f9f  mov     rcx, rsi; struct _DOMAIN_INFO *
0x180030fa2  call    ?NlRefDomClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@@Z; NlRefDomClientSession(_DOMAIN_INFO *)
0x180030fa7  mov     [rsp+98h+hMem], rax
0x180030fac  mov     rcx, rax
0x180030faf  test    rax, rax
0x180030fb2  jnz     short loc_180030FBE
0x180030fb4  mov     ebx, 0C00000DEh
0x180030fb9  jmp     loc_1800311D9
0x180030fbe  lea     rax, [rsp+98h+arg_10]
0x180030fc6  mov     r9, r13
0x180030fc9  mov     [rsp+98h+var_60], rax
0x180030fce  mov     r8d, ebp
0x180030fd1  mov     rax, [rsp+98h+arg_38]
0x180030fd9  xor     edx, edx
0x180030fdb  mov     [rsp+98h+var_68], rax
0x180030fe0  mov     rax, [rsp+98h+arg_30]
0x180030fe8  mov     [rsp+98h+var_70], rax
0x180030fed  mov     dword ptr [rsp+98h+var_78], r15d
0x180030ff2  call    ?NlpUserValidateHigher@@YAJPEAU_CLIENT_SESSION@@EW4_NETLOGON_LOGON_INFO_CLASS@@PEAEW4_NETLOGON_VALIDATION_INFO_CLASS@@PEAPEAE2PEAK@Z; NlpUserValidateHigher(_CLIENT_SESSION *,uchar,_NETLOGON_LOGON_INFO_CLASS,uchar *,_NETLOGON_VALIDATION_INFO_CLASS,uchar * *,uchar *,ulong *)
0x180030ff7  xor     r15d, r15d
0x180030ffa  mov     ebx, eax
0x180030ffc  test    eax, eax
0x180030ffe  js      short loc_180031056
0x180031000  test    byte ptr cs:?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A, 4; _NETLOGON_PARAMETERS NlGlobalParameters
0x180031007  jz      short loc_180031056
0x180031009  lea     rax, aFalse; "FALSE"
0x180031010  test    edi, edi
0x180031012  lea     r10, aTrue; "TRUE"
0x180031019  mov     ecx, ebp; enum _NETLOGON_LOGON_INFO_CLASS
0x18003101b  cmovz   r10, rax
0x18003101f  lea     rdx, [r13+30h]
0x180031023  lea     r8, [r13+20h]
0x180031027  call    ?NlpLogonTypeToText@@YAPEADW4_NETLOGON_LOGON_INFO_CLASS@@@Z; NlpLogonTypeToText(_NETLOGON_LOGON_INFO_CLASS)
0x18003102c  mov     [rsp+98h+var_60], r10
0x180031031  lea     ecx, [r15+4]; unsigned int
0x180031035  mov     [rsp+98h+var_68], rdx
0x18003103a  mov     r9, rax
0x18003103d  mov     [rsp+98h+var_70], r8
0x180031042  mov     rdx, rsi; struct _DOMAIN_INFO *
0x180031045  lea     r8, aSamlogonHsLogo_1; "SamLogon: %hs logon of %wZ\\%wZ from %w"...
0x18003104c  mov     [rsp+98h+var_78], r13
0x180031051  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180031056  test    edi, edi
0x180031058  jnz     loc_1800311CF
0x18003105e  test    r12d, r12d
0x180031061  jz      loc_1800311CF
0x180031067  cmp     ebx, 0C000006Ah
0x18003106d  jz      short loc_180031087
0x18003106f  cmp     ebx, 0C0000071h
0x180031075  jz      short loc_180031087
0x180031077  cmp     ebx, 0C0000224h
0x18003107d  jz      short loc_180031087
0x18003107f  cmp     ebx, 0C0000234h
0x180031085  jmp     short loc_1800310C8
0x180031087  mov     rcx, [rsi+178h]
0x18003108e  lea     r8, [rsp+98h+var_58]
0x180031093  mov     edx, 0Ch
0x180031098  call    cs:__imp_SamrQueryInformationDomain
0x18003109e  test    eax, eax
0x1800310a0  jns     short loc_1800310BE
0x1800310a2  mov     r9d, eax
0x1800310a5  lea     r8, aNlpuservalidat_1; "NlpUserValidateOnPdc: SamrQueryInformat"...
0x1800310ac  mov     rdx, rsi; struct _DOMAIN_INFO *
0x1800310af  mov     ecx, 100h; unsigned int
0x1800310b4  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800310b9  jmp     loc_1800311CF
0x1800310be  mov     rax, [rsp+98h+var_58]
0x1800310c3  cmp     [rax+10h], r15w
0x1800310c8  jnz     loc_1800311CF
0x1800310ce  mov     ebp, r15d
0x1800310d1  lea     r15, [rsi+190h]
0x1800310d8  mov     rcx, r15; CriticalSection
0x1800310db  call    cs:__imp_RtlEnterCriticalSection
0x1800310e1  add     rsi, 280h
0x1800310e8  xor     r12d, r12d
0x1800310eb  mov     rdi, [rsi]
0x1800310ee  lea     r13d, [r12+1]
0x1800310f3  cmp     rdi, rsi
0x1800310f6  jz      short loc_18003113A
0x1800310f8  lea     rdx, [rdi+18h]
0x1800310fc  xor     r9d, r9d
0x1800310ff  mov     r8d, r13d
0x180031102  mov     rcx, r14
0x180031105  call    cs:__imp_NetpwNameCompare
0x18003110b  mov     rcx, [rdi]
0x18003110e  test    eax, eax
0x180031110  jz      short loc_18003111A
0x180031112  add     ebp, r13d
0x180031115  mov     rdi, rcx
0x180031118  jmp     short loc_1800310F3
0x18003111a  cmp     [rcx+8], rdi
0x18003111e  jnz     loc_1800311B1
0x180031124  mov     rax, [rdi+8]
0x180031128  cmp     [rax], rdi
0x18003112b  jnz     loc_1800311B1
0x180031131  mov     [rax], rcx
0x180031134  mov     [rcx+8], rax
0x180031138  jmp     short loc_18003119C
0x18003113a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003113e  inc     rax
0x180031141  cmp     [r14+rax*2], r12w
0x180031146  jnz     short loc_18003113E
0x180031148  lea     eax, ds:2[rax*2]
0x18003114f  mov     ecx, 40h ; '@'; uFlags
0x180031154  lea     rdx, [rax+20h]; uBytes
0x180031158  mov     r13d, eax
0x18003115b  call    cs:__imp_LocalAlloc
0x180031161  mov     rdi, rax
0x180031164  test    rax, rax
0x180031167  jz      short loc_1800311C6
0x180031169  lea     rcx, [rax+18h]; void *
0x18003116d  mov     r8d, r13d; Size
0x180031170  mov     rdx, r14; Src
0x180031173  call    memcpy_0
0x180031178  cmp     ebp, 32h ; '2'
0x18003117b  jb      short loc_18003119C
0x18003117d  mov     rcx, [rsi+8]; hMem
0x180031181  cmp     [rcx], rsi
0x180031184  jnz     short loc_1800311B1
0x180031186  mov     rax, [rcx+8]
0x18003118a  cmp     [rax], rcx
0x18003118d  jnz     short loc_1800311B1
0x18003118f  mov     [rsi+8], rax
0x180031193  mov     [rax], rsi
0x180031196  call    cs:__imp_LocalFree
0x18003119c  call    cs:__imp_GetTickCount
0x1800311a2  inc     dword ptr [rdi+14h]
0x1800311a5  mov     [rdi+10h], eax
0x1800311a8  mov     rax, [rsi]
0x1800311ab  cmp     [rax+8], rsi
0x1800311af  jz      short loc_1800311B8
0x1800311b1  mov     ecx, 3
0x1800311b6  int     29h; Win8: RtlFailFast(ecx)
0x1800311b8  mov     [rdi], rax
0x1800311bb  mov     [rdi+8], rsi
0x1800311bf  mov     [rax+8], rdi
0x1800311c3  mov     [rsi], rdi
0x1800311c6  mov     rcx, r15; CriticalSection
0x1800311c9  call    cs:__imp_RtlLeaveCriticalSection
0x1800311cf  mov     rcx, [rsp+98h+hMem]; hMem
0x1800311d4  call    ?NlUnrefClientSession@@YAXPEAU_CLIENT_SESSION@@@Z; NlUnrefClientSession(_CLIENT_SESSION *)
0x1800311d9  test    r14, r14
0x1800311dc  jz      short loc_1800311E7
0x1800311de  mov     rcx, r14; hMem
0x1800311e1  call    cs:__imp_LocalFree
0x1800311e7  mov     rcx, [rsp+98h+var_58]
0x1800311ec  test    rcx, rcx
0x1800311ef  jz      short loc_1800311FC
0x1800311f1  mov     edx, 0Ch
0x1800311f6  call    cs:__imp_SamIFree_SAMPR_DOMAIN_INFO_BUFFER
0x1800311fc  mov     eax, ebx
0x1800311fe  jmp     short loc_180031205
0x180031200  mov     eax, 0C00000DEh
0x180031205  add     rsp, 58h
0x180031209  pop     r15
0x18003120b  pop     r14
0x18003120d  pop     r13
0x18003120f  pop     r12
0x180031211  pop     rdi
0x180031212  pop     rsi
0x180031213  pop     rbp
0x180031214  pop     rbx
0x180031215  retn
```
