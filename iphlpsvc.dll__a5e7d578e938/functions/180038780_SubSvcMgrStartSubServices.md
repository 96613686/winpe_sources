# SubSvcMgrStartSubServices

- ea: `0x180038780`
- end: `0x180038935`
- name: `SubSvcMgrStartSubServices`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003da10`

## callees

- `0x180004f60`
- `0x18000d7c0`
- `0x180012dcc`
- `0x180038780`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003890d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003890d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388e3`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800388a7`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800388a7`

## string_xrefs

- `0x180038838`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x180038885`: `SubSvcMgrStartSubServices: starting subservice (%s)`
- `0x1800387a7`: `onecoreuap\net\netio\iphlpsvc\service\subsvcmgr.c`
- `0x18003882c`: `Sub Service`
- `0x1800388d0`: `Sub Service`

## pseudocode

```c
__int64 SubSvcMgrStartSubServices()
{
  DWORD LastError; // edi
  __int64 v1; // rbx
  _OWORD *v2; // rax
  void *v3; // rbp
  int v4; // eax
  __int64 v6; // [rsp+28h] [rbp-80h]
  __int128 v7; // [rsp+30h] [rbp-78h]
  __int128 v8; // [rsp+40h] [rbp-68h]
  __int128 v9; // [rsp+50h] [rbp-58h]

  LastError = 0;
  *(_QWORD *)&v7 = EventWrite0;
  v1 = 0;
  HIDWORD(v9) = 0;
  *((_QWORD *)&v7 + 1) = CleanupHelperService;
  *(_QWORD *)&v8 = &g_Reference;
  while ( 1 )
  {
    if ( (unsigned int)v1 >= 2 )
      return LastError;
    if ( *((_DWORD *)&gSubSvcInfoTable + 18 * v1 + 14) )
      break;
LABEL_9:
    v1 = (unsigned int)(v1 + 1);
  }
  *((_QWORD *)&v8 + 1) = *(&gSubSvcInfoTable + 9 * v1 + 5);
  *(_QWORD *)&v9 = (&gSubSvcInfoTable)[9 * v1 + 3];
  DWORD2(v9) = v1;
  v2 = (_OWORD *)MALLOC(0x30u);
  v3 = v2;
  if ( !v2 )
  {
    LastError = 8;
    do
    {
LABEL_15:
      if ( *((_DWORD *)&gSubSvcInfoTable + 18 * v1 + 14) )
        SetEvent((&gSubSvcInfoTable)[9 * v1 + 3]);
      v1 = (unsigned int)(v1 + 1);
    }
    while ( (unsigned int)v1 < 2 );
    return LastError;
  }
  LODWORD(v6) = 374;
  *v2 = v7;
  v2[1] = v8;
  v2[2] = v9;
  EventWrite0(
    0x40000,
    L"ReferenceService: ++%u (%hs) @ %ls:%u",
    ((unsigned int)g_Reference >> 1) & 0x3FFFFFFF,
    "Sub Service",
    L"onecoreuap\\net\\netio\\iphlpsvc\\service\\subsvcmgr.c",
    v6);
  do
  {
    v4 = g_Reference;
    if ( (g_Reference & 1) != 0 )
    {
      LastError = GetLastError();
      goto LABEL_12;
    }
  }
  while ( v4 != _InterlockedCompareExchange(&g_Reference, g_Reference + 2, g_Reference) );
  EventWrite0(0x800000, L"SubSvcMgrStartSubServices: starting subservice (%s)", (&gSubSvcInfoTable)[9 * v1]);
  if ( TrySubmitThreadpoolCallback(SubSvcMgrStartSubServiceHelper, v3, &CallbackEnvironment) )
    goto LABEL_9;
  LastError = GetLastError();
  DereferenceServiceEx("Sub Service", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\subsvcmgr.c", 388);
LABEL_12:
  if ( LastError )
    goto LABEL_15;
  return LastError;
}

```

## disassembly

```asm
0x180038780  mov     r11, rsp
0x180038783  push    rbx
0x180038784  push    rbp
0x180038785  push    rsi
0x180038786  push    rdi
0x180038787  push    r12
0x180038789  push    r15
0x18003878b  sub     rsp, 78h
0x18003878f  lea     rax, EventWrite0
0x180038796  movaps  [rsp+0A8h+var_48], xmm6
0x18003879b  xor     edi, edi
0x18003879d  lea     r15, gSubSvcInfoTable
0x1800387a4  xorps   xmm0, xmm0
0x1800387a7  lea     r12, aOnecoreuapNetN_38; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800387ae  movdqu  [rsp+0A8h+var_60], xmm0
0x1800387b4  mov     [r11-78h], rax
0x1800387b8  xor     ebx, ebx
0x1800387ba  lea     rax, CleanupHelperService
0x1800387c1  mov     [r11-50h], rdi
0x1800387c5  mov     [r11-70h], rax
0x1800387c9  lea     rax, g_Reference
0x1800387d0  mov     [r11-68h], rax
0x1800387d4  movups  xmm6, [rsp+0A8h+var_78]
0x1800387d9  cmp     ebx, 2
0x1800387dc  jnb     loc_180038920
0x1800387e2  lea     rsi, [rbx+rbx*8]
0x1800387e6  cmp     [r15+rsi*8+38h], edi
0x1800387eb  jz      loc_1800388B7
0x1800387f1  mov     rax, [r15+rsi*8+28h]
0x1800387f6  mov     ecx, 30h ; '0'; dwBytes
0x1800387fb  mov     qword ptr [rsp+0A8h+var_60], rax
0x180038800  mov     rax, [r15+rsi*8+30h]
0x180038805  mov     qword ptr [rsp+0A8h+var_60+8], rax
0x18003880a  mov     [rsp+0A8h+var_50], ebx
0x18003880e  call    MALLOC
0x180038813  mov     rbp, rax
0x180038816  test    rax, rax
0x180038819  jz      loc_1800388F7
0x18003881f  movups  xmm0, xmmword ptr [rsp+40h]
0x180038824  mov     dword ptr [rsp+0A8h+var_80], 176h
0x18003882c  lea     r9, aSubService; "Sub Service"
0x180038833  movups  xmm1, [rsp+0A8h+var_60+8]
0x180038838  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x18003883f  mov     ecx, 40000h
0x180038844  movups  xmmword ptr [rax], xmm6
0x180038847  mov     [rsp+0A8h+var_88], r12
0x18003884c  movups  xmmword ptr [rax+10h], xmm0
0x180038850  movups  xmmword ptr [rax+20h], xmm1
0x180038854  mov     r8d, cs:g_Reference
0x18003885b  shr     r8d, 1
0x18003885e  and     r8d, 3FFFFFFFh
0x180038865  call    EventWrite0
0x18003886a  mov     eax, cs:g_Reference
0x180038870  test    al, 1
0x180038872  jnz     short loc_1800388E3
0x180038874  lea     ecx, [rax+2]
0x180038877  lock cmpxchg cs:g_Reference, ecx
0x18003887f  jnz     short loc_18003886A
0x180038881  mov     r8, [r15+rsi*8]
0x180038885  lea     rdx, aSubsvcmgrstart; "SubSvcMgrStartSubServices: starting sub"...
0x18003888c  mov     ecx, 800000h
0x180038891  call    EventWrite0
0x180038896  lea     r8, CallbackEnvironment; pcbe
0x18003889d  mov     rdx, rbp; pv
0x1800388a0  lea     rcx, SubSvcMgrStartSubServiceHelper; pfns
0x1800388a7  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800388ae  nop     dword ptr [rax+rax+00h]
0x1800388b3  test    eax, eax
0x1800388b5  jz      short loc_1800388BE
0x1800388b7  inc     ebx
0x1800388b9  jmp     loc_1800387D9
0x1800388be  call    cs:__imp_GetLastError
0x1800388c5  nop     dword ptr [rax+rax+00h]
0x1800388ca  mov     r8d, 184h
0x1800388d0  lea     rcx, aSubService; "Sub Service"
0x1800388d7  mov     rdx, r12
0x1800388da  mov     edi, eax
0x1800388dc  call    DereferenceServiceEx
0x1800388e1  jmp     short loc_1800388F1
0x1800388e3  call    cs:__imp_GetLastError
0x1800388ea  nop     dword ptr [rax+rax+00h]
0x1800388ef  mov     edi, eax
0x1800388f1  test    edi, edi
0x1800388f3  jnz     short loc_1800388FC
0x1800388f5  jmp     short loc_180038920
0x1800388f7  mov     edi, 8
0x1800388fc  lea     rcx, [rbx+rbx*8]
0x180038900  cmp     dword ptr [r15+rcx*8+38h], 0
0x180038906  jz      short loc_180038919
0x180038908  mov     rcx, [r15+rcx*8+30h]; hEvent
0x18003890d  call    cs:__imp_SetEvent
0x180038914  nop     dword ptr [rax+rax+00h]
0x180038919  inc     ebx
0x18003891b  cmp     ebx, 2
0x18003891e  jb      short loc_1800388FC
0x180038920  movaps  xmm6, [rsp+0A8h+var_48]
0x180038925  mov     eax, edi
0x180038927  add     rsp, 78h
0x18003892b  pop     r15
0x18003892d  pop     r12
0x18003892f  pop     rdi
0x180038930  pop     rsi
0x180038931  pop     rbp
0x180038932  pop     rbx
0x180038933  retn
```
