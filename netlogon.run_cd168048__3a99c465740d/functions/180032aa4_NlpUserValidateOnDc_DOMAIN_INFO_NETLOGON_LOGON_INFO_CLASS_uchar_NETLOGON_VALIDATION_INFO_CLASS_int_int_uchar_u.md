# NlpUserValidateOnDc(_DOMAIN_INFO *,_NETLOGON_LOGON_INFO_CLASS,uchar *,_NETLOGON_VALIDATION_INFO_CLASS,int,int,uchar * *,uchar *)

- ea: `0x180032aa4`
- end: `0x180032f87`
- name: `?NlpUserValidateOnDc@@YAJPEAU_DOMAIN_INFO@@W4_NETLOGON_LOGON_INFO_CLASS@@PEAEW4_NETLOGON_VALIDATION_INFO_CLASS@@HHPEAPEAE2@Z`
- size: `1251`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003033c`
- `0x180033710`

## callees

- `0x18000c440`
- `0x18000d324`
- `0x18000e0e0`
- `0x1800110ac`
- `0x1800283ec`
- `0x18002fa20`
- `0x180031a3c`
- `0x180032aa4`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032b9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032ea7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032b9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032ea7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032ee8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032f45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032ee8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032f45`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180032ef4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180032ef4`
- `ntdll!RtlLeaveCriticalSection` at `0x180032c99`
- `ntdll!RtlLeaveCriticalSection` at `0x180032f27`
- `ntdll!RtlLeaveCriticalSection` at `0x180032c99`
- `ntdll!RtlLeaveCriticalSection` at `0x180032f27`
- `ntdll!RtlEnterCriticalSection` at `0x180032bfd`
- `ntdll!RtlEnterCriticalSection` at `0x180032e1b`
- `ntdll!RtlEnterCriticalSection` at `0x180032bfd`
- `ntdll!RtlEnterCriticalSection` at `0x180032e1b`
- `netutils!NetpwNameCompare` at `0x180032c26`
- `netutils!NetpwNameCompare` at `0x180032e4b`
- `netutils!NetpwNameCompare` at `0x180032c26`
- `netutils!NetpwNameCompare` at `0x180032e4b`
- `SAMSRV!SamIFree_SAMPR_DOMAIN_INFO_BUFFER` at `0x180032f60`
- `SAMSRV!SamIFree_SAMPR_DOMAIN_INFO_BUFFER` at `0x180032f60`
- `SAMSRV!SamrQueryInformationDomain` at `0x180032dd2`
- `SAMSRV!SamrQueryInformationDomain` at `0x180032dd2`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!SamISameSite` at `0x180032b20`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!SamISameSite` at `0x180032b20`

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
  if ( !dword_1800F825C || a6 )
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
0x180032aa4  mov     rax, rsp
0x180032aa7  mov     [rax+20h], r9d
0x180032aab  mov     [rax+10h], edx
0x180032aae  push    rbx
0x180032aaf  push    rbp
0x180032ab0  push    rsi
0x180032ab1  push    rdi
0x180032ab2  push    r12
0x180032ab4  push    r13
0x180032ab6  push    r14
0x180032ab8  push    r15
0x180032aba  sub     rsp, 58h
0x180032abe  xor     ebx, ebx
0x180032ac0  mov     r15d, r9d
0x180032ac3  cmp     dword ptr [rcx+24Ch], 2
0x180032aca  mov     r13, r8
0x180032acd  mov     ebp, edx
0x180032acf  mov     [rax+8], bl
0x180032ad2  mov     rsi, rcx
0x180032ad5  mov     [rax+18h], ebx
0x180032ad8  mov     [rax-58h], rbx
0x180032adc  jnz     loc_180032F70
0x180032ae2  cmp     cs:?NlGlobalCDC@@3HA, ebx; int NlGlobalCDC
0x180032ae8  mov     edi, [rsp+98h+arg_28]
0x180032aef  jnz     short loc_180032AF9
0x180032af1  test    edi, edi
0x180032af3  jnz     loc_180032F70
0x180032af9  cmp     cs:dword_1800F825C, ebx
0x180032aff  mov     r14d, 4
0x180032b05  jz      short loc_180032B73
0x180032b07  test    edi, edi
0x180032b09  jnz     short loc_180032B73
0x180032b0b  call    IsDsGetServersAndSitesForNetLogonPresent
0x180032b10  test    al, al
0x180032b12  jz      loc_180032BB8
0x180032b18  lea     rcx, [rsp+98h+arg_0]
0x180032b20  call    cs:__imp_SamISameSite
0x180032b27  nop     dword ptr [rax+rax+00h]
0x180032b2c  mov     ebx, eax
0x180032b2e  test    eax, eax
0x180032b30  js      loc_180032BBD
0x180032b36  xor     ebx, ebx
0x180032b38  mov     rdx, rsi; struct _DOMAIN_INFO *
0x180032b3b  mov     ecx, r14d; unsigned int
0x180032b3e  cmp     [rsp+98h+arg_0], bl
0x180032b45  jnz     short loc_180032B67
0x180032b47  lea     r8, aNlpuservalidat_20; "NlpUserValidateOnPdc: Ignored a user va"...
0x180032b4e  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180032b53  mov     rax, [rsp+98h+arg_38]
0x180032b5b  mov     [rax], bl
0x180032b5d  mov     ebx, 0C0000064h
0x180032b62  jmp     loc_180032F51
0x180032b67  lea     r8, aNlpuservalidat_19; "NlpUserValidateOnPdc: BDC and PDC are i"...
0x180032b6e  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180032b73  mov     r12d, [rsp+98h+arg_20]
0x180032b7b  mov     r14, rbx
0x180032b7e  test    r12d, r12d
0x180032b81  jz      loc_180032CD9
0x180032b87  test    edi, edi
0x180032b89  jnz     loc_180032CD9
0x180032b8f  movzx   edx, word ptr [r13+20h]
0x180032b94  xor     ecx, ecx; uFlags
0x180032b96  add     rdx, 2; uBytes
0x180032b9a  call    cs:__imp_LocalAlloc
0x180032ba1  nop     dword ptr [rax+rax+00h]
0x180032ba6  mov     r14, rax
0x180032ba9  test    rax, rax
0x180032bac  jnz     short loc_180032BD6
0x180032bae  mov     ebx, 0C0000017h
0x180032bb3  jmp     loc_180032F51
0x180032bb8  mov     ebx, 0C00000BBh
0x180032bbd  lea     r8, aNlpuservalidat_6; "NlpUserValidateOnPdc: Cannot SamISameSi"...
0x180032bc4  mov     rdx, rsi; struct _DOMAIN_INFO *
0x180032bc7  mov     ecx, 100h; unsigned int
0x180032bcc  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180032bd1  jmp     loc_180032F51
0x180032bd6  movzx   r8d, word ptr [r13+20h]; Size
0x180032bdb  mov     rcx, r14; void *
0x180032bde  mov     rdx, [r13+28h]; Src
0x180032be2  mov     ebp, ebx
0x180032be4  call    memcpy_0
0x180032be9  movzx   ecx, word ptr [r13+20h]
0x180032bee  shr     rcx, 1
0x180032bf1  mov     [r14+rcx*2], bx
0x180032bf6  lea     rcx, [rsi+190h]; CriticalSection
0x180032bfd  call    cs:__imp_RtlEnterCriticalSection
0x180032c04  nop     dword ptr [rax+rax+00h]
0x180032c09  lea     r15, [rsi+280h]
0x180032c10  mov     rbx, [r15]
0x180032c13  cmp     rbx, r15
0x180032c16  jz      short loc_180032C92
0x180032c18  xor     r9d, r9d
0x180032c1b  lea     rdx, [rbx+18h]
0x180032c1f  mov     rcx, r14
0x180032c22  lea     r8d, [r9+1]
0x180032c26  call    cs:__imp_NetpwNameCompare
0x180032c2d  nop     dword ptr [rax+rax+00h]
0x180032c32  test    eax, eax
0x180032c34  jz      short loc_180032C3B
0x180032c36  mov     rbx, [rbx]
0x180032c39  jmp     short loc_180032C13
0x180032c3b  mov     ecx, [rbx+10h]; unsigned int
0x180032c3e  call    ?NetpDcElapsedTime@@YAKK@Z; NetpDcElapsedTime(ulong)
0x180032c43  cmp     dword ptr [rbx+14h], 0Ah
0x180032c47  jbe     short loc_180032C56
0x180032c49  cmp     eax, 493E0h
0x180032c4e  mov     eax, 1
0x180032c53  cmovb   ebp, eax
0x180032c56  mov     rax, [rbx]
0x180032c59  cmp     [rax+8], rbx
0x180032c5d  jnz     loc_180032F0F
0x180032c63  mov     rdx, [rbx+8]
0x180032c67  cmp     [rdx], rbx
0x180032c6a  jnz     loc_180032F0F
0x180032c70  mov     [rdx], rax
0x180032c73  mov     [rax+8], rdx
0x180032c77  mov     rax, [r15]
0x180032c7a  cmp     [rax+8], r15
0x180032c7e  jnz     loc_180032F0F
0x180032c84  mov     [rbx], rax
0x180032c87  mov     [rbx+8], r15
0x180032c8b  mov     [rax+8], rbx
0x180032c8f  mov     [r15], rbx
0x180032c92  lea     rcx, [rsi+190h]; CriticalSection
0x180032c99  call    cs:__imp_RtlLeaveCriticalSection
0x180032ca0  nop     dword ptr [rax+rax+00h]
0x180032ca5  test    ebp, ebp
0x180032ca7  jz      short loc_180032CCA
0x180032ca9  mov     r9, r14
0x180032cac  lea     r8, aAvoidSendToPdc; "Avoid send to PDC since user %ws failed"...
0x180032cb3  mov     rdx, rsi; struct _DOMAIN_INFO *
0x180032cb6  mov     ecx, 4; unsigned int
0x180032cbb  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180032cc0  mov     ebx, 0C0000064h
0x180032cc5  jmp     loc_180032F42
0x180032cca  mov     ebp, [rsp+98h+arg_8]
0x180032cd1  mov     r15d, [rsp+98h+arg_18]
0x180032cd9  mov     rcx, rsi; struct _DOMAIN_INFO *
0x180032cdc  call    ?NlRefDomClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@@Z; NlRefDomClientSession(_DOMAIN_INFO *)
0x180032ce1  mov     [rsp+98h+hMem], rax
0x180032ce6  mov     rcx, rax
0x180032ce9  test    rax, rax
0x180032cec  jnz     short loc_180032CF8
0x180032cee  mov     ebx, 0C00000DEh
0x180032cf3  jmp     loc_180032F3D
0x180032cf8  lea     rax, [rsp+98h+arg_10]
0x180032d00  mov     r9, r13
0x180032d03  mov     [rsp+98h+var_60], rax
0x180032d08  mov     r8d, ebp
0x180032d0b  mov     rax, [rsp+98h+arg_38]
0x180032d13  xor     edx, edx
0x180032d15  mov     [rsp+98h+var_68], rax
0x180032d1a  mov     rax, [rsp+98h+arg_30]
0x180032d22  mov     [rsp+98h+var_70], rax
0x180032d27  mov     dword ptr [rsp+98h+var_78], r15d
0x180032d2c  call    ?NlpUserValidateHigher@@YAJPEAU_CLIENT_SESSION@@EW4_NETLOGON_LOGON_INFO_CLASS@@PEAEW4_NETLOGON_VALIDATION_INFO_CLASS@@PEAPEAE2PEAK@Z; NlpUserValidateHigher(_CLIENT_SESSION *,uchar,_NETLOGON_LOGON_INFO_CLASS,uchar *,_NETLOGON_VALIDATION_INFO_CLASS,uchar * *,uchar *,ulong *)
0x180032d31  xor     r15d, r15d
0x180032d34  mov     ebx, eax
0x180032d36  test    eax, eax
0x180032d38  js      short loc_180032D90
0x180032d3a  test    byte ptr cs:?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A, 4; _NETLOGON_PARAMETERS NlGlobalParameters
0x180032d41  jz      short loc_180032D90
0x180032d43  lea     rax, aFalse; "FALSE"
0x180032d4a  test    edi, edi
0x180032d4c  lea     r10, aTrue; "TRUE"
0x180032d53  mov     ecx, ebp; enum _NETLOGON_LOGON_INFO_CLASS
0x180032d55  cmovz   r10, rax
0x180032d59  lea     rdx, [r13+30h]
0x180032d5d  lea     r8, [r13+20h]
0x180032d61  call    ?NlpLogonTypeToText@@YAPEADW4_NETLOGON_LOGON_INFO_CLASS@@@Z; NlpLogonTypeToText(_NETLOGON_LOGON_INFO_CLASS)
0x180032d66  mov     [rsp+98h+var_60], r10
0x180032d6b  lea     ecx, [r15+4]; unsigned int
0x180032d6f  mov     [rsp+98h+var_68], rdx
0x180032d74  mov     r9, rax
0x180032d77  mov     [rsp+98h+var_70], r8
0x180032d7c  mov     rdx, rsi; struct _DOMAIN_INFO *
0x180032d7f  lea     r8, aSamlogonHsLogo_1; "SamLogon: %hs logon of %wZ\\%wZ from %w"...
0x180032d86  mov     [rsp+98h+var_78], r13
0x180032d8b  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180032d90  test    edi, edi
0x180032d92  jnz     loc_180032F33
0x180032d98  test    r12d, r12d
0x180032d9b  jz      loc_180032F33
0x180032da1  cmp     ebx, 0C000006Ah
0x180032da7  jz      short loc_180032DC1
0x180032da9  cmp     ebx, 0C0000071h
0x180032daf  jz      short loc_180032DC1
0x180032db1  cmp     ebx, 0C0000224h
0x180032db7  jz      short loc_180032DC1
0x180032db9  cmp     ebx, 0C0000234h
0x180032dbf  jmp     short loc_180032E08
0x180032dc1  mov     rcx, [rsi+178h]
0x180032dc8  lea     r8, [rsp+98h+var_58]
0x180032dcd  mov     edx, 0Ch
0x180032dd2  call    cs:__imp_SamrQueryInformationDomain
0x180032dd9  nop     dword ptr [rax+rax+00h]
0x180032dde  test    eax, eax
0x180032de0  jns     short loc_180032DFE
0x180032de2  mov     r9d, eax
0x180032de5  lea     r8, aNlpuservalidat_1; "NlpUserValidateOnPdc: SamrQueryInformat"...
0x180032dec  mov     rdx, rsi; struct _DOMAIN_INFO *
0x180032def  mov     ecx, 100h; unsigned int
0x180032df4  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180032df9  jmp     loc_180032F33
0x180032dfe  mov     rax, [rsp+98h+var_58]
0x180032e03  cmp     [rax+10h], r15w
0x180032e08  jnz     loc_180032F33
0x180032e0e  mov     ebp, r15d
0x180032e11  lea     r15, [rsi+190h]
0x180032e18  mov     rcx, r15; CriticalSection
0x180032e1b  call    cs:__imp_RtlEnterCriticalSection
0x180032e22  nop     dword ptr [rax+rax+00h]
0x180032e27  add     rsi, 280h
0x180032e2e  xor     r12d, r12d
0x180032e31  mov     rdi, [rsi]
0x180032e34  lea     r13d, [r12+1]
0x180032e39  cmp     rdi, rsi
0x180032e3c  jz      short loc_180032E86
0x180032e3e  lea     rdx, [rdi+18h]
0x180032e42  xor     r9d, r9d
0x180032e45  mov     r8d, r13d
0x180032e48  mov     rcx, r14
0x180032e4b  call    cs:__imp_NetpwNameCompare
0x180032e52  nop     dword ptr [rax+rax+00h]
0x180032e57  mov     rcx, [rdi]
0x180032e5a  test    eax, eax
0x180032e5c  jz      short loc_180032E66
0x180032e5e  add     ebp, r13d
0x180032e61  mov     rdi, rcx
0x180032e64  jmp     short loc_180032E39
0x180032e66  cmp     [rcx+8], rdi
0x180032e6a  jnz     loc_180032F0F
0x180032e70  mov     rax, [rdi+8]
0x180032e74  cmp     [rax], rdi
0x180032e77  jnz     loc_180032F0F
0x180032e7d  mov     [rax], rcx
0x180032e80  mov     [rcx+8], rax
0x180032e84  jmp     short loc_180032EF4
0x180032e86  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032e8a  inc     rax
0x180032e8d  cmp     [r14+rax*2], r12w
0x180032e92  jnz     short loc_180032E8A
0x180032e94  lea     eax, ds:2[rax*2]
0x180032e9b  mov     ecx, 40h ; '@'; uFlags
0x180032ea0  lea     rdx, [rax+20h]; uBytes
0x180032ea4  mov     r13d, eax
0x180032ea7  call    cs:__imp_LocalAlloc
0x180032eae  nop     dword ptr [rax+rax+00h]
0x180032eb3  mov     rdi, rax
0x180032eb6  test    rax, rax
0x180032eb9  jz      short loc_180032F24
0x180032ebb  lea     rcx, [rax+18h]; void *
0x180032ebf  mov     r8d, r13d; Size
0x180032ec2  mov     rdx, r14; Src
0x180032ec5  call    memcpy_0
0x180032eca  cmp     ebp, 32h ; '2'
0x180032ecd  jb      short loc_180032EF4
0x180032ecf  mov     rcx, [rsi+8]; hMem
0x180032ed3  cmp     [rcx], rsi
0x180032ed6  jnz     short loc_180032F0F
0x180032ed8  mov     rax, [rcx+8]
0x180032edc  cmp     [rax], rcx
0x180032edf  jnz     short loc_180032F0F
0x180032ee1  mov     [rsi+8], rax
0x180032ee5  mov     [rax], rsi
0x180032ee8  call    cs:__imp_LocalFree
0x180032eef  nop     dword ptr [rax+rax+00h]
0x180032ef4  call    cs:__imp_GetTickCount
0x180032efb  nop     dword ptr [rax+rax+00h]
0x180032f00  inc     dword ptr [rdi+14h]
0x180032f03  mov     [rdi+10h], eax
0x180032f06  mov     rax, [rsi]
0x180032f09  cmp     [rax+8], rsi
0x180032f0d  jz      short loc_180032F16
0x180032f0f  mov     ecx, 3
0x180032f14  int     29h; Win8: RtlFailFast(ecx)
0x180032f16  mov     [rdi], rax
0x180032f19  mov     [rdi+8], rsi
0x180032f1d  mov     [rax+8], rdi
0x180032f21  mov     [rsi], rdi
0x180032f24  mov     rcx, r15; CriticalSection
0x180032f27  call    cs:__imp_RtlLeaveCriticalSection
0x180032f2e  nop     dword ptr [rax+rax+00h]
0x180032f33  mov     rcx, [rsp+98h+hMem]; hMem
0x180032f38  call    ?NlUnrefClientSession@@YAXPEAU_CLIENT_SESSION@@@Z; NlUnrefClientSession(_CLIENT_SESSION *)
0x180032f3d  test    r14, r14
0x180032f40  jz      short loc_180032F51
0x180032f42  mov     rcx, r14; hMem
0x180032f45  call    cs:__imp_LocalFree
0x180032f4c  nop     dword ptr [rax+rax+00h]
0x180032f51  mov     rcx, [rsp+98h+var_58]
0x180032f56  test    rcx, rcx
0x180032f59  jz      short loc_180032F6C
0x180032f5b  mov     edx, 0Ch
0x180032f60  call    cs:__imp_SamIFree_SAMPR_DOMAIN_INFO_BUFFER
0x180032f67  nop     dword ptr [rax+rax+00h]
0x180032f6c  mov     eax, ebx
0x180032f6e  jmp     short loc_180032F75
0x180032f70  mov     eax, 0C00000DEh
0x180032f75  add     rsp, 58h
  ... truncated ...
```
