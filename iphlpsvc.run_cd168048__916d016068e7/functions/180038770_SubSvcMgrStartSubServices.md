# SubSvcMgrStartSubServices

- ea: `0x180038770`
- end: `0x180038925`
- name: `SubSvcMgrStartSubServices`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003da00`

## callees

- `0x180004f50`
- `0x18000d7b0`
- `0x180012dbc`
- `0x180038770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800388fd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800388fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388d3`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180038897`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180038897`

## string_xrefs

- `0x180038828`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x180038875`: `SubSvcMgrStartSubServices: starting subservice (%s)`
- `0x180038797`: `onecoreuap\net\netio\iphlpsvc\service\subsvcmgr.c`
- `0x18003881c`: `Sub Service`
- `0x1800388c0`: `Sub Service`

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
0x180038770  mov     r11, rsp
0x180038773  push    rbx
0x180038774  push    rbp
0x180038775  push    rsi
0x180038776  push    rdi
0x180038777  push    r12
0x180038779  push    r15
0x18003877b  sub     rsp, 78h
0x18003877f  lea     rax, EventWrite0
0x180038786  movaps  [rsp+0A8h+var_48], xmm6
0x18003878b  xor     edi, edi
0x18003878d  lea     r15, gSubSvcInfoTable
0x180038794  xorps   xmm0, xmm0
0x180038797  lea     r12, aOnecoreuapNetN_38; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003879e  movdqu  [rsp+0A8h+var_60], xmm0
0x1800387a4  mov     [r11-78h], rax
0x1800387a8  xor     ebx, ebx
0x1800387aa  lea     rax, CleanupHelperService
0x1800387b1  mov     [r11-50h], rdi
0x1800387b5  mov     [r11-70h], rax
0x1800387b9  lea     rax, g_Reference
0x1800387c0  mov     [r11-68h], rax
0x1800387c4  movups  xmm6, [rsp+0A8h+var_78]
0x1800387c9  cmp     ebx, 2
0x1800387cc  jnb     loc_180038910
0x1800387d2  lea     rsi, [rbx+rbx*8]
0x1800387d6  cmp     [r15+rsi*8+38h], edi
0x1800387db  jz      loc_1800388A7
0x1800387e1  mov     rax, [r15+rsi*8+28h]
0x1800387e6  mov     ecx, 30h ; '0'; dwBytes
0x1800387eb  mov     qword ptr [rsp+0A8h+var_60], rax
0x1800387f0  mov     rax, [r15+rsi*8+30h]
0x1800387f5  mov     qword ptr [rsp+0A8h+var_60+8], rax
0x1800387fa  mov     [rsp+0A8h+var_50], ebx
0x1800387fe  call    MALLOC
0x180038803  mov     rbp, rax
0x180038806  test    rax, rax
0x180038809  jz      loc_1800388E7
0x18003880f  movups  xmm0, xmmword ptr [rsp+40h]
0x180038814  mov     dword ptr [rsp+0A8h+var_80], 176h
0x18003881c  lea     r9, aSubService; "Sub Service"
0x180038823  movups  xmm1, [rsp+0A8h+var_60+8]
0x180038828  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x18003882f  mov     ecx, 40000h
0x180038834  movups  xmmword ptr [rax], xmm6
0x180038837  mov     [rsp+0A8h+var_88], r12
0x18003883c  movups  xmmword ptr [rax+10h], xmm0
0x180038840  movups  xmmword ptr [rax+20h], xmm1
0x180038844  mov     r8d, cs:g_Reference
0x18003884b  shr     r8d, 1
0x18003884e  and     r8d, 3FFFFFFFh
0x180038855  call    EventWrite0
0x18003885a  mov     eax, cs:g_Reference
0x180038860  test    al, 1
0x180038862  jnz     short loc_1800388D3
0x180038864  lea     ecx, [rax+2]
0x180038867  lock cmpxchg cs:g_Reference, ecx
0x18003886f  jnz     short loc_18003885A
0x180038871  mov     r8, [r15+rsi*8]
0x180038875  lea     rdx, aSubsvcmgrstart; "SubSvcMgrStartSubServices: starting sub"...
0x18003887c  mov     ecx, 800000h
0x180038881  call    EventWrite0
0x180038886  lea     r8, CallbackEnvironment; pcbe
0x18003888d  mov     rdx, rbp; pv
0x180038890  lea     rcx, SubSvcMgrStartSubServiceHelper; pfns
0x180038897  call    cs:__imp_TrySubmitThreadpoolCallback
0x18003889e  nop     dword ptr [rax+rax+00h]
0x1800388a3  test    eax, eax
0x1800388a5  jz      short loc_1800388AE
0x1800388a7  inc     ebx
0x1800388a9  jmp     loc_1800387C9
0x1800388ae  call    cs:__imp_GetLastError
0x1800388b5  nop     dword ptr [rax+rax+00h]
0x1800388ba  mov     r8d, 184h
0x1800388c0  lea     rcx, aSubService; "Sub Service"
0x1800388c7  mov     rdx, r12
0x1800388ca  mov     edi, eax
0x1800388cc  call    DereferenceServiceEx
0x1800388d1  jmp     short loc_1800388E1
0x1800388d3  call    cs:__imp_GetLastError
0x1800388da  nop     dword ptr [rax+rax+00h]
0x1800388df  mov     edi, eax
0x1800388e1  test    edi, edi
0x1800388e3  jnz     short loc_1800388EC
0x1800388e5  jmp     short loc_180038910
0x1800388e7  mov     edi, 8
0x1800388ec  lea     rcx, [rbx+rbx*8]
0x1800388f0  cmp     dword ptr [r15+rcx*8+38h], 0
0x1800388f6  jz      short loc_180038909
0x1800388f8  mov     rcx, [r15+rcx*8+30h]; hEvent
0x1800388fd  call    cs:__imp_SetEvent
0x180038904  nop     dword ptr [rax+rax+00h]
0x180038909  inc     ebx
0x18003890b  cmp     ebx, 2
0x18003890e  jb      short loc_1800388EC
0x180038910  movaps  xmm6, [rsp+0A8h+var_48]
0x180038915  mov     eax, edi
0x180038917  add     rsp, 78h
0x18003891b  pop     r15
0x18003891d  pop     r12
0x18003891f  pop     rdi
0x180038920  pop     rsi
0x180038921  pop     rbp
0x180038922  pop     rbx
0x180038923  retn
```
