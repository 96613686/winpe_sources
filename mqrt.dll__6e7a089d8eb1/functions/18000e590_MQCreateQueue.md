# MQCreateQueue

- ea: `0x18000e590`
- end: `0x18000ec1a`
- name: `MQCreateQueue`
- size: `1674`
- prototype: `HRESULT __stdcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, MQQUEUEPROPS *pQueueProps, LPWSTR lpwcsFormatName, LPDWORD lpdwFormatNameLength)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180005488`
- `0x1800087f8`
- `0x1800091bc`
- `0x18000a364`
- `0x18000c764`
- `0x18000d74c`
- `0x18000d7e8`
- `0x18000d8b4`
- `0x18000e590`
- `0x18000f6a0`
- `0x18000fcf0`
- `0x180013c74`
- `0x180014458`
- `0x180017ce0`
- `0x180018134`
- `0x180018220`
- `0x18001a864`
- `0x18001d340`
- `0x180021060`
- `0x180021e3c`
- `0x180023c36`
- `0x180023ca0`

## pseudocode

```c
HRESULT __stdcall MQCreateQueue(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        MQQUEUEPROPS *pQueueProps,
        LPWSTR lpwcsFormatName,
        LPDWORD lpdwFormatNameLength)
{
  HRESULT v5; // ebx
  unsigned int *v6; // r8
  unsigned __int16 v7; // r8
  int Size; // ebx
  int v10; // eax
  unsigned int v11; // ecx
  struct tagPROPVARIANT *QueuePropVar; // rax
  LARGE_INTEGER hVal; // r13
  int v14; // edi
  int v15; // ebx
  int v16; // eax
  __int64 v17; // r15
  unsigned int v18; // r14d
  int v19; // edi
  HRESULT v20; // ebx
  int v21; // ecx
  __int64 v22; // rdi
  __int64 v23; // rbx
  const wchar_t *v24; // rax
  __int64 v25; // r8
  int v26; // r14d
  int v27; // edi
  __int64 v28; // rax
  unsigned int v29; // ecx
  int v30; // ebx
  HRESULT v31; // ebx
  int Object; // ebx
  int v33; // eax
  int v34; // ebx
  __int64 v35; // [rsp+0h] [rbp-118h] BYREF
  int v36; // [rsp+50h] [rbp-C8h]
  int v37; // [rsp+54h] [rbp-C4h]
  unsigned int v38; // [rsp+58h] [rbp-C0h]
  LPCWSTR lpwcsPathName; // [rsp+60h] [rbp-B8h] BYREF
  void *v40; // [rsp+68h] [rbp-B0h] BYREF
  HRESULT v41; // [rsp+70h] [rbp-A8h]
  HRESULT v42; // [rsp+74h] [rbp-A4h]
  HRESULT v43; // [rsp+78h] [rbp-A0h]
  void *v44; // [rsp+80h] [rbp-98h] BYREF
  void *v45; // [rsp+88h] [rbp-90h] BYREF
  char *v46; // [rsp+90h] [rbp-88h] BYREF
  LPDWORD lpdwFormatNameLengtha; // [rsp+98h] [rbp-80h]
  LPWSTR lpwcsFormatNamea; // [rsp+A0h] [rbp-78h]
  __int64 *v49; // [rsp+A8h] [rbp-70h]
  LARGE_INTEGER v50; // [rsp+B0h] [rbp-68h]
  int v51; // [rsp+B8h] [rbp-60h]
  int v52; // [rsp+BCh] [rbp-5Ch]
  GUID pGuid; // [rsp+C8h] [rbp-50h] BYREF

  v49 = &v35;
  lpdwFormatNameLengtha = lpdwFormatNameLength;
  lpwcsFormatNamea = lpwcsFormatName;
  v40 = pSecurityDescriptor;
  v5 = RtpOneTimeThreadInit();
  if ( v5 < 0 )
  {
    v7 = 1117;
    goto LABEL_3;
  }
  v38 = 1;
  v50.QuadPart = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  Size = RTpMakeSelfRelativeSDAndGetSize(&v40, &v45, v6);
  v10 = RTpConvertToMQCode(Size, 1u);
  v36 = v10;
  v37 = Size;
  if ( v10 < 0 )
  {
    v41 = LogHR(v10, (wchar_t *)L"rt/queue", 0x82u);
    local_unwind_0(v49, &loc_18000E6A9);
    return v41;
  }
  QueuePropVar = RTpGetQueuePropVar(v11, pQueueProps);
  if ( QueuePropVar )
    hVal = QueuePropVar->hVal;
  else
    hVal.QuadPart = 0;
  v50 = hVal;
  if ( !hVal.QuadPart )
  {
    v42 = LogHR(-1072824257, (wchar_t *)L"rt/queue", 0x8Cu);
    local_unwind_0(v49, &loc_18000E705);
    return v42;
  }
  lpwcsPathName = 0;
  v14 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))FnValidateAndExpandQueuePath)(
          (LARGE_INTEGER)hVal.QuadPart,
          &lpwcsPathName,
          &v44);
  *(_QWORD *)&pGuid.Data1 = 0;
  v15 = RTpCheckQueueProps(pQueueProps, 1u, v14 == 1, (struct tagMQQUEUEPROPS **)&pGuid, &v46);
  v16 = RTpConvertToMQCode(v15, 1u);
  v51 = v16;
  v52 = v15;
  if ( v16 < 0 || (v17 = *(_QWORD *)&pGuid.Data1, (v18 = **(_DWORD **)&pGuid.Data1) == 0) )
  {
    v43 = LogHR(v16, (wchar_t *)L"rt/queue", 0x96u);
    local_unwind_0(v49, &loc_18000EABC);
    return v43;
  }
  v19 = v14 - 1;
  if ( v19 )
  {
    if ( v19 != 1 )
    {
      v20 = -1072824300;
      v21 = -1072824300;
LABEL_43:
      v36 = RTpConvertToMQCode(v21, 1u);
      v26 = v36;
      v37 = v20;
      v27 = v36;
      goto LABEL_44;
    }
    pGuid = 0;
    v22 = *(_QWORD *)(v17 + 16);
    v23 = *(_QWORD *)(v17 + 8);
    v24 = MachineDomain();
    LODWORD(v23) = ADCreateObject(0, v24, v25, lpwcsPathName, v40, v18, v23, v22, &pGuid);
    v26 = RTpConvertToMQCode(v23, 1u);
    v27 = v26;
    v36 = v26;
    v37 = v23;
    if ( (unsigned int)(v26 + 1072824247) <= 0x3C && (v28 = 0x1000000200000001LL, _bittest64(&v28, v26 + 1072824247))
      || v26 == -1072824301
      || v26 == -1072824315
      || v26 >= 0 )
    {
      if ( g_fOnFailureCallServiceToCreatePublicQueue )
      {
LABEL_30:
        if ( v26 >= 0 )
        {
          v31 = MQInstanceToFormatName(&pGuid, lpwcsFormatNamea, lpdwFormatNameLengtha);
          v27 = RTpConvertToMQCode(v31, 1u);
          v36 = v27;
          v37 = v31;
          v26 = v27;
        }
        goto LABEL_44;
      }
    }
    else if ( g_fOnFailureCallServiceToCreatePublicQueue )
    {
      if ( (unsigned int)RTpIsLocalPublicQueue(lpwcsPathName) )
      {
        v30 = RtpCreateDSObject(
                v29,
                lpwcsPathName,
                v40,
                *(_DWORD *)v17,
                *(unsigned int *const *)(v17 + 8),
                *(struct tagPROPVARIANT *const *)(v17 + 16),
                &pGuid);
        v27 = RTpConvertToMQCode(v30, 1u);
        v36 = v27;
        v37 = v30;
        if ( v27 < 0 )
        {
          v26 = v27;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              14,
              WPP_048d7302c6dd33c9f28b1c15e91ff05f_Traceguids,
              (unsigned int)v26);
          v26 = v27;
        }
      }
      goto LABEL_30;
    }
    if ( v26 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_048d7302c6dd33c9f28b1c15e91ff05f_Traceguids,
        (unsigned int)v26);
    goto LABEL_30;
  }
  Object = RtpCreateObject(
             1u,
             lpwcsPathName,
             v40,
             v18,
             *(unsigned int *const *)(*(_QWORD *)&pGuid.Data1 + 8LL),
             *(struct tagPROPVARIANT *const *)(*(_QWORD *)&pGuid.Data1 + 16LL));
  v33 = RTpConvertToMQCode(Object, 1u);
  v27 = v33;
  v36 = v33;
  v37 = Object;
  v26 = -1072824283;
  if ( v33 == -1072824283 )
  {
    if ( !g_fOnFailureCallServiceToCreatePublicQueue )
      goto LABEL_41;
    v34 = RtpCreateObject(
            2u,
            lpwcsPathName,
            v40,
            *(_DWORD *)v17,
            *(unsigned int *const *)(v17 + 8),
            *(struct tagPROPVARIANT *const *)(v17 + 16));
    v33 = RTpConvertToMQCode(v34, 1u);
    v27 = v33;
    v36 = v33;
    v37 = v34;
  }
  v26 = v33;
LABEL_41:
  if ( v26 >= 0 )
  {
    v20 = MQPathNameToFormatName(lpwcsPathName, lpwcsFormatNamea, lpdwFormatNameLengtha);
    v21 = v20;
    goto LABEL_43;
  }
LABEL_44:
  if ( v26 == -1072824289 )
  {
    v27 = RTpConvertToMQCode(1074659337, 1u);
    v36 = v27;
    v37 = 1074659337;
  }
  MmDeallocate(v44);
  MmDeallocate(v45);
  MmDeallocate(v46);
  if ( v27 >= 0 )
  {
    if ( (v27 & 0xC0000000) != 0x40000000 )
    {
      v5 = v51;
      if ( v51 >= 0 )
        return v5;
      v7 = 1118;
LABEL_3:
      LogMsgHR(v5, (wchar_t *)L"rt/queue", v7);
      return v5;
    }
  }
  else
  {
    if ( v27 == -1072824315 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 508) & 2) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 62));
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 508) & 1) != 0 )
    {
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 62), v27);
    }
    LogMsgHR(v27, (wchar_t *)L"rt/queue", 0x45Fu);
  }
  return v27;
}

```

## disassembly

```asm
0x18000e590  push    rbx
0x18000e592  push    rdi
0x18000e593  push    r12
0x18000e595  push    r13
0x18000e597  push    r14
0x18000e599  push    r15
0x18000e59b  sub     rsp, 0E8h
0x18000e5a2  mov     rax, cs:__security_cookie
0x18000e5a9  xor     rax, rsp
0x18000e5ac  mov     [rsp+118h+var_40], rax
0x18000e5b4  mov     [rsp+118h+var_70], rsp
0x18000e5bc  mov     [rsp+118h+lpdwFormatNameLength], r9
0x18000e5c4  mov     [rsp+118h+lpwcsFormatName], r8
0x18000e5cc  mov     r14, rdx
0x18000e5cf  mov     [rsp+118h+var_B0], rcx
0x18000e5d4  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x18000e5d9  mov     ebx, eax
0x18000e5db  test    eax, eax
0x18000e5dd  jns     short loc_18000E617
0x18000e5df  mov     r8d, 45Dh; unsigned __int16
0x18000e5e5  lea     rdx, aRtQueue; "rt/queue"
0x18000e5ec  mov     ecx, ebx; int
0x18000e5ee  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000e5f3  mov     eax, ebx
0x18000e5f5  mov     rcx, [rsp+118h+var_40]
0x18000e5fd  xor     rcx, rsp; StackCookie
0x18000e600  call    __security_check_cookie
0x18000e605  add     rsp, 0E8h
0x18000e60c  pop     r15
0x18000e60e  pop     r14
0x18000e610  pop     r13
0x18000e612  pop     r12
0x18000e614  pop     rdi
0x18000e615  pop     rbx
0x18000e616  retn
0x18000e617  mov     r12d, 1
0x18000e61d  mov     [rsp+118h+var_C0], r12d
0x18000e622  mov     [rsp+118h+var_68], 0
0x18000e62e  mov     [rsp+118h+var_98], 0
0x18000e63a  mov     [rsp+118h+var_90], 0
0x18000e646  mov     [rsp+118h+var_88], 0
0x18000e652  lea     rdx, [rsp+118h+var_90]; void **
0x18000e65a  lea     rcx, [rsp+118h+var_B0]; void **
0x18000e65f  call    ?RTpMakeSelfRelativeSDAndGetSize@@YAJPEAPEAX0PEAK@Z; RTpMakeSelfRelativeSDAndGetSize(void * *,void * *,ulong *)
0x18000e664  mov     ebx, eax
0x18000e666  mov     edx, r12d; unsigned int
0x18000e669  mov     ecx, eax; int
0x18000e66b  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000e670  mov     [rsp+118h+var_C8], eax
0x18000e674  mov     [rsp+118h+var_C4], ebx
0x18000e678  test    eax, eax
0x18000e67a  jns     short loc_18000E6B2
0x18000e67c  mov     r8d, 82h; unsigned __int16
0x18000e682  lea     rdx, aRtQueue; "rt/queue"
0x18000e689  mov     ecx, eax; int
0x18000e68b  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000e690  mov     [rsp+118h+var_A8], eax
0x18000e694  lea     rdx, loc_18000E6A9
0x18000e69b  mov     rcx, [rsp+118h+var_70]
0x18000e6a3  call    _local_unwind_0
0x18000e6a8  nop
0x18000e6a9  mov     eax, [rsp+118h+var_A8]
0x18000e6ad  jmp     loc_18000E5F5
0x18000e6b2  mov     rdx, r14; struct tagMQQUEUEPROPS *
0x18000e6b5  call    ?RTpGetQueuePropVar@@YAPEAUtagPROPVARIANT@@KPEAUtagMQQUEUEPROPS@@@Z; RTpGetQueuePropVar(ulong,tagMQQUEUEPROPS *)
0x18000e6ba  test    rax, rax
0x18000e6bd  jz      short loc_18000E6C5
0x18000e6bf  mov     r13, [rax+8]
0x18000e6c3  jmp     short loc_18000E6C8
0x18000e6c5  xor     r13d, r13d
0x18000e6c8  mov     [rsp+118h+var_68], r13
0x18000e6d0  test    r13, r13
0x18000e6d3  jnz     short loc_18000E70E
0x18000e6d5  mov     r8d, 8Ch; unsigned __int16
0x18000e6db  lea     rdx, aRtQueue; "rt/queue"
0x18000e6e2  mov     ecx, 0C00E003Fh; int
0x18000e6e7  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000e6ec  mov     [rsp+118h+var_A4], eax
0x18000e6f0  lea     rdx, loc_18000E705
0x18000e6f7  mov     rcx, [rsp+118h+var_70]
0x18000e6ff  call    _local_unwind_0
0x18000e704  nop
0x18000e705  mov     eax, [rsp+118h+var_A4]
0x18000e709  jmp     loc_18000E5F5
0x18000e70e  mov     [rsp+118h+lpwcsPathName], 0
0x18000e717  lea     r8, [rsp+118h+var_98]
0x18000e71f  lea     rdx, [rsp+118h+lpwcsPathName]
0x18000e724  mov     rcx, r13
0x18000e727  call    ?FnValidateAndExpandQueuePath@@YA?AW4QUEUE_PATH_TYPE@@PEB_WPEAPEB_WPEAPEA_W@Z; FnValidateAndExpandQueuePath(wchar_t const *,wchar_t const * *,wchar_t * *)
0x18000e72c  mov     edi, eax
0x18000e72e  mov     qword ptr [rsp+118h+pGuid.Data1], 0
0x18000e73a  xor     r8d, r8d
0x18000e73d  cmp     eax, r12d
0x18000e740  setz    r8b; int
0x18000e744  lea     rax, [rsp+118h+var_88]
0x18000e74c  mov     [rsp+118h+var_F8], rax; char **
0x18000e751  lea     r9, [rsp+118h+pGuid]; struct tagMQQUEUEPROPS **
0x18000e759  mov     edx, r12d; unsigned int
0x18000e75c  mov     rcx, r14; struct tagMQQUEUEPROPS *
0x18000e75f  call    ?RTpCheckQueueProps@@YAJPEAUtagMQQUEUEPROPS@@KHPEAPEAU1@PEAPEAD@Z; RTpCheckQueueProps(tagMQQUEUEPROPS *,ulong,int,tagMQQUEUEPROPS * *,char * *)
0x18000e764  mov     ebx, eax
0x18000e766  mov     edx, r12d; unsigned int
0x18000e769  mov     ecx, eax; int
0x18000e76b  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000e770  mov     [rsp+118h+var_60], eax
0x18000e777  mov     [rsp+118h+var_5C], ebx
0x18000e77e  test    eax, eax
0x18000e780  js      loc_18000EA8F
0x18000e786  mov     r15, qword ptr [rsp+118h+pGuid.Data1]
0x18000e78e  mov     r14d, [r15]
0x18000e791  test    r14d, r14d
0x18000e794  jz      loc_18000EA8F
0x18000e79a  sub     edi, 1
0x18000e79d  jz      loc_18000E996
0x18000e7a3  cmp     edi, 1
0x18000e7a6  jz      short loc_18000E7B4
0x18000e7a8  mov     ebx, 0C00E0014h
0x18000e7ad  mov     ecx, ebx
0x18000e7af  jmp     loc_18000EA4C
0x18000e7b4  xorps   xmm0, xmm0
0x18000e7b7  movups  xmmword ptr [rsp+118h+pGuid.Data1], xmm0
0x18000e7bf  mov     rdi, [r15+10h]
0x18000e7c3  mov     rbx, [r15+8]
0x18000e7c7  call    ?MachineDomain@@YAPEB_WXZ; MachineDomain(void)
0x18000e7cc  lea     rcx, [rsp+118h+pGuid]
0x18000e7d4  mov     [rsp+118h+var_D8], rcx
0x18000e7d9  mov     [rsp+118h+var_E0], rdi
0x18000e7de  mov     [rsp+118h+var_E8], rbx
0x18000e7e3  mov     dword ptr [rsp+118h+var_F0], r14d
0x18000e7e8  mov     rcx, [rsp+118h+var_B0]
0x18000e7ed  mov     [rsp+118h+var_F8], rcx
0x18000e7f2  mov     r9, [rsp+118h+lpwcsPathName]
0x18000e7f7  mov     rdx, rax
0x18000e7fa  xor     ecx, ecx
0x18000e7fc  call    ?ADCreateObject@@YAJW4AD_OBJECT@@PEB_W_N1PEAXKQEBKQEBUtagPROPVARIANT@@PEAU_GUID@@@Z; ADCreateObject(AD_OBJECT,wchar_t const *,bool,wchar_t const *,void *,ulong,ulong const * const,tagPROPVARIANT const * const,_GUID *)
0x18000e801  mov     ebx, eax
0x18000e803  mov     edx, r12d; unsigned int
0x18000e806  mov     ecx, eax; int
0x18000e808  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000e80d  mov     r14d, eax
0x18000e810  mov     edi, eax
0x18000e812  mov     [rsp+118h+var_C8], eax
0x18000e816  mov     [rsp+118h+var_C4], ebx
0x18000e81a  add     eax, 3FF1FFB7h
0x18000e81f  cmp     eax, 3Ch ; '<'
0x18000e822  ja      short loc_18000E83B
0x18000e824  movsxd  rcx, eax
0x18000e827  mov     rax, 1000000200000001h
0x18000e831  bt      rax, rcx
0x18000e835  jb      loc_18000E952
0x18000e83b  cmp     r14d, 0C00E0013h
0x18000e842  jz      loc_18000E952
0x18000e848  cmp     r14d, 0C00E0005h
0x18000e84f  jz      loc_18000E952
0x18000e855  test    r14d, r14d
0x18000e858  jns     loc_18000E952
0x18000e85e  cmp     cs:?g_fOnFailureCallServiceToCreatePublicQueue@@3HA, 0; int g_fOnFailureCallServiceToCreatePublicQueue
0x18000e865  jz      loc_18000E95B
0x18000e86b  mov     rcx, [rsp+118h+lpwcsPathName]; wchar_t *
0x18000e870  call    ?RTpIsLocalPublicQueue@@YAHPEB_W@Z; RTpIsLocalPublicQueue(wchar_t const *)
0x18000e875  test    eax, eax
0x18000e877  jz      loc_18000E907
0x18000e87d  lea     rax, [rsp+118h+pGuid]
0x18000e885  mov     [rsp+118h+var_E8], rax; struct _GUID *
0x18000e88a  mov     rax, [r15+10h]
0x18000e88e  mov     [rsp+118h+var_F0], rax; struct tagPROPVARIANT *
0x18000e893  mov     rax, [r15+8]
0x18000e897  mov     [rsp+118h+var_F8], rax; unsigned int *
0x18000e89c  mov     r9d, [r15]; unsigned int
0x18000e89f  mov     r8, [rsp+118h+var_B0]; void *
0x18000e8a4  mov     rdx, [rsp+118h+lpwcsPathName]; wchar_t *
0x18000e8a9  call    ?RtpCreateDSObject@@YAJKPEB_WPEAXKQEAKQEAUtagPROPVARIANT@@PEAU_GUID@@@Z; RtpCreateDSObject(ulong,wchar_t const *,void *,ulong,ulong * const,tagPROPVARIANT * const,_GUID *)
0x18000e8ae  mov     ebx, eax
0x18000e8b0  mov     edx, r12d; unsigned int
0x18000e8b3  mov     ecx, eax; int
0x18000e8b5  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000e8ba  mov     edi, eax
0x18000e8bc  mov     [rsp+118h+var_C8], eax
0x18000e8c0  mov     [rsp+118h+var_C4], ebx
0x18000e8c4  test    eax, eax
0x18000e8c6  js      short loc_18000E904
0x18000e8c8  lea     r15, WPP_GLOBAL_Control
0x18000e8cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8d6  cmp     rcx, r15
0x18000e8d9  jz      short loc_18000E8FF
0x18000e8db  test    byte ptr [rcx+0E4h], 4
0x18000e8e2  jz      short loc_18000E8FF
0x18000e8e4  mov     edx, 0Eh
0x18000e8e9  mov     r9d, r14d
0x18000e8ec  lea     r8, WPP_048d7302c6dd33c9f28b1c15e91ff05f_Traceguids
0x18000e8f3  mov     rcx, [rcx+0D8h]
0x18000e8fa  call    WPP_SF_d
0x18000e8ff  mov     r14d, edi
0x18000e902  jmp     short loc_18000E90E
0x18000e904  mov     r14d, edi
0x18000e907  lea     r15, WPP_GLOBAL_Control
0x18000e90e  test    r14d, r14d
0x18000e911  js      loc_18000EA68
0x18000e917  mov     r8, [rsp+118h+lpdwFormatNameLength]; lpdwFormatNameLength
0x18000e91f  mov     rdx, [rsp+118h+lpwcsFormatName]; lpwcsFormatName
0x18000e927  lea     rcx, [rsp+118h+pGuid]; pGuid
0x18000e92f  call    MQInstanceToFormatName
0x18000e934  mov     ebx, eax
0x18000e936  mov     edx, r12d; unsigned int
0x18000e939  mov     ecx, eax; int
0x18000e93b  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000e940  mov     edi, eax
0x18000e942  mov     [rsp+118h+var_C8], eax
0x18000e946  mov     [rsp+118h+var_C4], ebx
0x18000e94a  mov     r14d, eax
0x18000e94d  jmp     loc_18000EA68
0x18000e952  cmp     cs:?g_fOnFailureCallServiceToCreatePublicQueue@@3HA, 0; int g_fOnFailureCallServiceToCreatePublicQueue
0x18000e959  jnz     short loc_18000E907
0x18000e95b  test    r14d, r14d
0x18000e95e  jns     short loc_18000E907
0x18000e960  lea     r15, WPP_GLOBAL_Control
0x18000e967  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e96e  cmp     rcx, r15
0x18000e971  jz      short loc_18000E90E
0x18000e973  test    [rcx+1Ch], r12b
0x18000e977  jz      short loc_18000E90E
0x18000e979  mov     edx, 0Dh
0x18000e97e  mov     r9d, r14d
0x18000e981  lea     r8, WPP_048d7302c6dd33c9f28b1c15e91ff05f_Traceguids
0x18000e988  mov     rcx, [rcx+10h]
0x18000e98c  call    WPP_SF_d
0x18000e991  jmp     loc_18000E90E
0x18000e996  mov     rax, [r15+10h]
0x18000e99a  mov     [rsp+118h+var_F0], rax; struct tagPROPVARIANT *
0x18000e99f  mov     rax, [r15+8]
0x18000e9a3  mov     [rsp+118h+var_F8], rax; unsigned int *
0x18000e9a8  mov     r9d, r14d; unsigned int
0x18000e9ab  mov     r8, [rsp+118h+var_B0]; void *
0x18000e9b0  mov     rdx, [rsp+118h+lpwcsPathName]; wchar_t *
0x18000e9b5  mov     ecx, r12d; unsigned int
0x18000e9b8  call    ?RtpCreateObject@@YAJKPEB_WPEAXKQEAKQEAUtagPROPVARIANT@@@Z; RtpCreateObject(ulong,wchar_t const *,void *,ulong,ulong * const,tagPROPVARIANT * const)
0x18000e9bd  mov     ebx, eax
0x18000e9bf  mov     edx, r12d; unsigned int
0x18000e9c2  mov     ecx, eax; int
0x18000e9c4  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000e9c9  mov     edi, eax
0x18000e9cb  mov     [rsp+118h+var_C8], eax
0x18000e9cf  mov     [rsp+118h+var_C4], ebx
0x18000e9d3  mov     r14d, 0C00E0025h
0x18000e9d9  cmp     eax, r14d
0x18000e9dc  jnz     short loc_18000EA26
0x18000e9de  cmp     cs:?g_fOnFailureCallServiceToCreatePublicQueue@@3HA, 0; int g_fOnFailureCallServiceToCreatePublicQueue
0x18000e9e5  jz      short loc_18000EA29
0x18000e9e7  mov     rax, [r15+10h]
0x18000e9eb  mov     [rsp+118h+var_F0], rax; struct tagPROPVARIANT *
0x18000e9f0  mov     rax, [r15+8]
0x18000e9f4  mov     [rsp+118h+var_F8], rax; unsigned int *
0x18000e9f9  mov     r9d, [r15]; unsigned int
0x18000e9fc  mov     r8, [rsp+118h+var_B0]; void *
0x18000ea01  mov     rdx, [rsp+118h+lpwcsPathName]; wchar_t *
0x18000ea06  mov     ecx, 2; unsigned int
0x18000ea0b  call    ?RtpCreateObject@@YAJKPEB_WPEAXKQEAKQEAUtagPROPVARIANT@@@Z; RtpCreateObject(ulong,wchar_t const *,void *,ulong,ulong * const,tagPROPVARIANT * const)
0x18000ea10  mov     ebx, eax
0x18000ea12  mov     edx, r12d; unsigned int
0x18000ea15  mov     ecx, eax; int
0x18000ea17  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000ea1c  mov     edi, eax
0x18000ea1e  mov     [rsp+118h+var_C8], eax
0x18000ea22  mov     [rsp+118h+var_C4], ebx
0x18000ea26  mov     r14d, eax
0x18000ea29  test    r14d, r14d
0x18000ea2c  js      short loc_18000EA61
0x18000ea2e  mov     r8, [rsp+118h+lpdwFormatNameLength]; lpdwFormatNameLength
0x18000ea36  mov     rdx, [rsp+118h+lpwcsFormatName]; lpwcsFormatName
0x18000ea3e  mov     rcx, [rsp+118h+lpwcsPathName]; lpwcsPathName
0x18000ea43  call    MQPathNameToFormatName
0x18000ea48  mov     ebx, eax
0x18000ea4a  mov     ecx, eax; int
0x18000ea4c  mov     edx, r12d; unsigned int
0x18000ea4f  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000ea54  mov     [rsp+118h+var_C8], eax
0x18000ea58  mov     r14d, eax
0x18000ea5b  mov     [rsp+118h+var_C4], ebx
0x18000ea5f  mov     edi, eax
0x18000ea61  lea     r15, WPP_GLOBAL_Control
0x18000ea68  cmp     r14d, 0C00E001Fh
0x18000ea6f  jnz     short loc_18000EA8A
0x18000ea71  mov     edx, r12d; unsigned int
0x18000ea74  mov     ebx, 400E0009h
0x18000ea79  mov     ecx, ebx; int
0x18000ea7b  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x18000ea80  mov     edi, eax
0x18000ea82  mov     [rsp+118h+var_C8], eax
0x18000ea86  mov     [rsp+118h+var_C4], ebx
0x18000ea8a  jmp     loc_18000EB34
0x18000ea8f  mov     r8d, 96h; unsigned __int16
0x18000ea95  lea     rdx, aRtQueue; "rt/queue"
0x18000ea9c  mov     ecx, eax; int
0x18000ea9e  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000eaa3  mov     [rsp+118h+var_A0], eax
0x18000eaa7  lea     rdx, loc_18000EABC
0x18000eaae  mov     rcx, [rsp+118h+var_70]
0x18000eab6  call    _local_unwind_0
0x18000eabb  nop
0x18000eabc  mov     eax, [rsp+118h+var_A0]
  ... truncated ...
```
