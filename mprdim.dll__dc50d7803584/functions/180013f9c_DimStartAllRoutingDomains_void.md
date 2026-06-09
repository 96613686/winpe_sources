# DimStartAllRoutingDomains(void)

- ea: `0x180013f9c`
- end: `0x18001423e`
- name: `?DimStartAllRoutingDomains@@YAKXZ`
- size: `674`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011eb0`

## callees

- `0x18000def0`
- `0x18000df70`
- `0x180013f9c`
- `0x1800304f8`
- `0x180030514`
- `0x180030630`
- `0x180033e60`
- `0x1800357c8`
- `0x180045cf0`
- `0x180045d40`
- `0x180045d7c`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141d7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800141cc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800141cc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800141e2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800141e2`
- `ADVAPI32!EventActivityIdControl` at `0x180014139`
- `ADVAPI32!EventActivityIdControl` at `0x180014139`

## string_xrefs

- `0x18001403d`: `DimStartAllRoutingDomains: CDimThreadPool.Initialize failed with error %d`
- `0x1800140a6`: `DimStartAllRoutingDomains: Error %d occured while enumerating Routing Domains from config store.`

## pseudocode

```c
__int64 DimStartAllRoutingDomains(void)
{
  unsigned int v0; // edx
  unsigned int v1; // r8d
  unsigned int v2; // eax
  unsigned int v3; // ebx
  int v4; // edi
  unsigned int i; // esi
  __int64 v6; // rcx
  char *v7; // r15
  __int128 *v8; // r9
  struct _TP_WORK *v9; // rax
  unsigned int v11; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v13; // [rsp+40h] [rbp-C0h] BYREF
  _TP_CALLBACK_ENVIRON_V3 pcbe; // [rsp+50h] [rbp-B0h] BYREF
  char v15; // [rsp+98h] [rbp-68h]
  GUID ActivityId; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v17; // [rsp+B0h] [rbp-50h] BYREF
  int v18; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v19; // [rsp+C4h] [rbp-3Ch]
  __int128 v20; // [rsp+D4h] [rbp-2Ch]
  int v21; // [rsp+E4h] [rbp-1Ch]
  int v22; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v23[2044]; // [rsp+F4h] [rbp-Ch] BYREF

  v11 = 0;
  lpMem = 0;
  v13 = 0;
  v15 = 0;
  ActivityId = 0;
  v17 = 0;
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v2 = CDimThreadPool::Initialize((CDimThreadPool *)&v13, v0, v1);
  v3 = v2;
  if ( v2 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_30;
    LOWORD(v22) = 0;
    FormatRRASErrorString(&v22, L"DimStartAllRoutingDomains: CDimThreadPool.Initialize failed with error %d", v2);
    goto LABEL_4;
  }
  v3 = EnumerateRoutingDomains(1u, &v11, (struct _MPRI_ROUTING_DOMAIN_INFO_EX **)&lpMem);
  if ( v3 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_30;
    LOWORD(v22) = 0;
    FormatRRASErrorString(
      &v22,
      L"DimStartAllRoutingDomains: Error %d occured while enumerating Routing Domains from config store.",
      v3);
LABEL_4:
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v22);
    goto LABEL_30;
  }
  v4 = 0;
  for ( i = 0; i < v11; ++i )
  {
    v6 = 540LL * i;
    if ( *((_BYTE *)lpMem + v6) == 1 )
    {
      v7 = (char *)lpMem + v6;
      if ( v4 )
        ReSetActivityId(&ActivityId);
      EventActivityIdControl(1u, &ActivityId);
      EtwStartRRASActivity((struct _GUID *)(v7 + 520));
      if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
      {
        LOWORD(v22) = 0;
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v22, L"DimStartAllRoutingDomains: Adding routing domain(%s) to RtrMgtr and DDM.", v7 + 4);
        if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
        {
          v8 = &v17;
          if ( v7 != (char *)-520LL )
            LODWORD(v8) = (_DWORD)v7 + 520;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceInfo,
            (unsigned int)&v22,
            (_DWORD)v8,
            0,
            (__int64)&v18);
        }
      }
      v4 = 1;
      if ( v15 )
      {
        v9 = CreateThreadpoolWork(DimStartRoutingDomainCallBack, v7 + 520, &pcbe);
        if ( v9 )
          SubmitThreadpoolWork(v9);
        else
          GetLastError();
      }
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v22) = 0;
        FormatRRASErrorString(
          &v22,
          L"DimStartAllRoutingDomains: Skipping routing domain having un-supported  version: %d.",
          *((unsigned __int8 *)lpMem + v6));
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v22);
      }
      v3 = 50;
    }
  }
  CDimThreadPool::Uninitialize((CDimThreadPool *)&v13, 0);
  if ( v4 )
    ReSetActivityId(&ActivityId);
LABEL_30:
  MprCommonFree(lpMem);
  CDimThreadPool::~CDimThreadPool((CDimThreadPool *)&v13);
  return v3;
}

```

## disassembly

```asm
0x180013f9c  push    rbp
0x180013f9e  push    rbx
0x180013f9f  push    rsi
0x180013fa0  push    rdi
0x180013fa1  push    r14
0x180013fa3  push    r15
0x180013fa5  lea     rbp, [rsp-808h]
0x180013fad  sub     rsp, 908h
0x180013fb4  mov     rax, cs:__security_cookie
0x180013fbb  xor     rax, rsp
0x180013fbe  mov     [rbp+830h+var_40], rax
0x180013fc5  mov     [rsp+930h+var_900], 0
0x180013fcd  mov     [rsp+930h+lpMem], 0
0x180013fd6  xorps   xmm0, xmm0
0x180013fd9  movdqa  [rsp+930h+var_8F0], xmm0
0x180013fdf  mov     [rbp+830h+var_898], 0
0x180013fe3  movups  xmmword ptr [rbp+830h+ActivityId.Data1], xmm0
0x180013fe7  xorps   xmm1, xmm1
0x180013fea  movups  [rbp+830h+var_880], xmm1
0x180013fee  xor     eax, eax
0x180013ff0  mov     [rbp+830h+var_840], eax
0x180013ff3  xor     edx, edx; Val
0x180013ff5  mov     r8d, 7FCh; Size
0x180013ffb  lea     rcx, [rbp+830h+var_83C]; void *
0x180013fff  call    memset_0
0x180014004  xor     eax, eax
0x180014006  mov     [rbp+830h+var_870], eax
0x180014009  xorps   xmm0, xmm0
0x18001400c  movups  [rbp+830h+var_86C], xmm0
0x180014010  movups  [rbp+830h+var_85C], xmm0
0x180014014  mov     [rbp+830h+var_84C], eax
0x180014017  lea     rcx, [rsp+930h+var_8F0]; this
0x18001401c  call    ?Initialize@CDimThreadPool@@QEAAKKK@Z; CDimThreadPool::Initialize(ulong,ulong)
0x180014021  mov     ebx, eax
0x180014023  test    eax, eax
0x180014025  jz      short loc_180014076
0x180014027  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18001402e  jz      loc_180014208
0x180014034  xor     ecx, ecx
0x180014036  mov     word ptr [rbp+830h+var_840], cx
0x18001403a  mov     r8d, eax
0x18001403d  lea     rdx, aDimstartallrou_1; "DimStartAllRoutingDomains: CDimThreadPo"...
0x180014044  lea     rcx, [rbp+830h+var_840]
0x180014048  call    FormatRRASErrorString
0x18001404d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180014054  jz      loc_180014208
0x18001405a  lea     r8, [rbp+830h+var_840]
0x18001405e  lea     rdx, RasDimTraceError
0x180014065  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001406c  call    McTemplateU0z_EventWriteTransfer
0x180014071  jmp     loc_180014208
0x180014076  lea     r8, [rsp+930h+lpMem]; struct _MPRI_ROUTING_DOMAIN_INFO_EX **
0x18001407b  lea     rdx, [rsp+930h+var_900]; unsigned int *
0x180014080  mov     ecx, 1; unsigned int
0x180014085  call    EnumerateRoutingDomains
0x18001408a  mov     ebx, eax
0x18001408c  test    eax, eax
0x18001408e  jz      short loc_1800140AF
0x180014090  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180014097  jz      loc_180014208
0x18001409d  xor     eax, eax
0x18001409f  mov     word ptr [rbp+830h+var_840], ax
0x1800140a3  mov     r8d, ebx
0x1800140a6  lea     rdx, aDimstartallrou; "DimStartAllRoutingDomains: Error %d occ"...
0x1800140ad  jmp     short loc_180014044
0x1800140af  xor     edi, edi
0x1800140b1  xor     esi, esi
0x1800140b3  cmp     esi, [rsp+930h+var_900]
0x1800140b7  jnb     loc_1800141EF
0x1800140bd  mov     eax, esi
0x1800140bf  imul    rcx, rax, 21Ch
0x1800140c6  mov     rdx, [rsp+930h+lpMem]
0x1800140cb  cmp     byte ptr [rcx+rdx], 1
0x1800140cf  jz      short loc_18001411F
0x1800140d1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800140d8  jz      short loc_180014115
0x1800140da  xor     eax, eax
0x1800140dc  mov     word ptr [rbp+830h+var_840], ax
0x1800140e0  movzx   r8d, byte ptr [rcx+rdx]
0x1800140e5  lea     rdx, aDimstartallrou_0; "DimStartAllRoutingDomains: Skipping rou"...
0x1800140ec  lea     rcx, [rbp+830h+var_840]
0x1800140f0  call    FormatRRASErrorString
0x1800140f5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800140fc  jz      short loc_180014115
0x1800140fe  lea     r8, [rbp+830h+var_840]
0x180014102  lea     rdx, RasDimTraceError
0x180014109  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014110  call    McTemplateU0z_EventWriteTransfer
0x180014115  mov     ebx, 32h ; '2'
0x18001411a  jmp     loc_1800141E8
0x18001411f  lea     r15, [rcx+rdx]
0x180014123  test    edi, edi
0x180014125  jz      short loc_180014130
0x180014127  lea     rcx, [rbp+830h+ActivityId]; ActivityId
0x18001412b  call    ReSetActivityId
0x180014130  lea     rdx, [rbp+830h+ActivityId]; ActivityId
0x180014134  mov     ecx, 1; ControlCode
0x180014139  call    cs:__imp_EventActivityIdControl
0x18001413f  lea     r14, [r15+208h]
0x180014146  mov     rcx, r14; struct _GUID *
0x180014149  call    EtwStartRRASActivity
0x18001414e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180014155  jz      short loc_1800141B2
0x180014157  xor     eax, eax
0x180014159  mov     word ptr [rbp+830h+var_840], ax
0x18001415d  mov     word ptr [rbp+830h+var_870], ax
0x180014161  lea     r8, [r15+4]
0x180014165  lea     rdx, aDimstartallrou_2; "DimStartAllRoutingDomains: Adding routi"...
0x18001416c  lea     rcx, [rbp+830h+var_840]
0x180014170  call    FormatRRASErrorString
0x180014175  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18001417c  jz      short loc_1800141B2
0x18001417e  lea     r9, [rbp+830h+var_880]
0x180014182  test    r14, r14
0x180014185  cmovnz  r9, r14
0x180014189  lea     rax, [rbp+830h+var_870]
0x18001418d  mov     [rsp+930h+var_908], rax
0x180014192  mov     [rsp+930h+var_910], 0
0x18001419b  lea     r8, [rbp+830h+var_840]
0x18001419f  lea     rdx, RasDimParamTraceInfo
0x1800141a6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800141ad  call    McTemplateU0zjzz_EventWriteTransfer
0x1800141b2  mov     edi, 1
0x1800141b7  cmp     [rbp+830h+var_898], 0
0x1800141bb  jz      short loc_1800141E8
0x1800141bd  lea     r8, [rsp+930h+pcbe]; pcbe
0x1800141c2  mov     rdx, r14; pv
0x1800141c5  lea     rcx, ?DimStartRoutingDomainCallBack@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800141cc  call    cs:__imp_CreateThreadpoolWork
0x1800141d2  test    rax, rax
0x1800141d5  jnz     short loc_1800141DF
0x1800141d7  call    cs:__imp_GetLastError
0x1800141dd  jmp     short loc_1800141E8
0x1800141df  mov     rcx, rax; pwk
0x1800141e2  call    cs:__imp_SubmitThreadpoolWork
0x1800141e8  inc     esi
0x1800141ea  jmp     loc_1800140B3
0x1800141ef  xor     edx, edx; bool
0x1800141f1  lea     rcx, [rsp+930h+var_8F0]; this
0x1800141f6  call    ?Uninitialize@CDimThreadPool@@QEAAX_N@Z; CDimThreadPool::Uninitialize(bool)
0x1800141fb  test    edi, edi
0x1800141fd  jz      short loc_180014208
0x1800141ff  lea     rcx, [rbp+830h+ActivityId]; ActivityId
0x180014203  call    ReSetActivityId
0x180014208  mov     rcx, [rsp+930h+lpMem]; lpMem
0x18001420d  call    MprCommonFree
0x180014212  nop
0x180014213  lea     rcx, [rsp+930h+var_8F0]; this
0x180014218  call    ??1CDimThreadPool@@QEAA@XZ; CDimThreadPool::~CDimThreadPool(void)
0x18001421d  mov     eax, ebx
0x18001421f  mov     rcx, [rbp+830h+var_40]
0x180014226  xor     rcx, rsp; StackCookie
0x180014229  call    __security_check_cookie
0x18001422e  add     rsp, 908h
0x180014235  pop     r15
0x180014237  pop     r14
0x180014239  pop     rdi
0x18001423a  pop     rsi
0x18001423b  pop     rbx
0x18001423c  pop     rbp
0x18001423d  retn
```
