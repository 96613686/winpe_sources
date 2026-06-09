# GetClusteredServiceName(void)

- ea: `0x1800141cc`
- end: `0x18001462b`
- name: `?GetClusteredServiceName@@YA_NXZ`
- size: `1119`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014054`

## callees

- `0x18000c62c`
- `0x18000c654`
- `0x18000d87c`
- `0x180012c84`
- `0x180013e54`
- `0x180013eec`
- `0x180013f64`
- `0x180013fdc`
- `0x1800141cc`
- `0x180014828`
- `0x18001e35a`
- `0x18001e380`
- `0x180022010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800144e4`
- `msvcrt!_wcsicmp` at `0x1800144e4`
- `KERNEL32!GetProcAddress` at `0x180014221`
- `KERNEL32!GetProcAddress` at `0x180014238`
- `KERNEL32!GetProcAddress` at `0x18001424f`
- `KERNEL32!GetProcAddress` at `0x180014266`
- `KERNEL32!GetProcAddress` at `0x180014282`
- `KERNEL32!GetProcAddress` at `0x180014299`
- `KERNEL32!GetProcAddress` at `0x1800142b5`
- `KERNEL32!GetProcAddress` at `0x180014221`
- `KERNEL32!GetProcAddress` at `0x180014238`
- `KERNEL32!GetProcAddress` at `0x18001424f`
- `KERNEL32!GetProcAddress` at `0x180014266`
- `KERNEL32!GetProcAddress` at `0x180014282`
- `KERNEL32!GetProcAddress` at `0x180014299`
- `KERNEL32!GetProcAddress` at `0x1800142b5`
- `KERNEL32!GetComputerNameW` at `0x18001420d`
- `KERNEL32!GetComputerNameW` at `0x18001420d`

## string_xrefs

- `0x180014213`: `OpenCluster`
- `0x18001422a`: `OpenClusterNode`
- `0x180014241`: `ClusterOpenEnum`
- `0x180014274`: `OpenClusterResource`

## pseudocode

```c
char GetClusteredServiceName(void)
{
  FARPROC ProcAddress; // r14
  FARPROC v1; // rdi
  FARPROC v2; // rsi
  FARPROC v3; // r15
  FARPROC v4; // r13
  FARPROC v5; // rbx
  FARPROC v6; // rax
  unsigned int (*v7)(struct _HRESOURCE *, struct _HNODE *, unsigned int, void *, unsigned int, void *, unsigned int, unsigned int *); // r12
  __int64 v8; // rax
  __int64 v9; // rbx
  int v10; // eax
  char v11; // r14
  __int64 v12; // rsi
  unsigned int v13; // r15d
  struct _HRESOURCE *v14; // rax
  struct _HRESOURCE *v15; // rdi
  int v16; // eax
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  DWORD nSize; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+3Ch] [rbp-C4h] BYREF
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  struct _HRESOURCE *v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int (__fastcall *v25)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // [rsp+58h] [rbp-A8h]
  unsigned int (__fastcall *v26)(struct _HRESOURCE *, wchar_t *, int *); // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v28[384]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[200]; // [rsp+1F0h] [rbp+F0h] BYREF
  wchar_t String2[200]; // [rsp+380h] [rbp+280h] BYREF

  nSize = 200;
  GetComputerNameW(Buffer, &nSize);
  ProcAddress = GetProcAddress(g_hLib, "OpenCluster");
  v1 = GetProcAddress(g_hLib, "OpenClusterNode");
  v2 = GetProcAddress(g_hLib, "ClusterOpenEnum");
  v3 = GetProcAddress(g_hLib, "ClusterEnum");
  v25 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))v3;
  v4 = GetProcAddress(g_hLib, "OpenClusterResource");
  v5 = GetProcAddress(g_hLib, "GetClusterResourceNetworkName");
  v26 = (unsigned int (__fastcall *)(struct _HRESOURCE *, wchar_t *, int *))v5;
  v6 = GetProcAddress(g_hLib, "ClusterResourceControl");
  v7 = (unsigned int (*)(struct _HRESOURCE *, struct _HNODE *, unsigned int, void *, unsigned int, void *, unsigned int, unsigned int *))v6;
  if ( !ProcAddress || !v1 || !v2 || !v3 || !v4 || !v5 || !v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids);
    return 0;
  }
  v8 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0);
  v9 = v8;
  v24 = v8;
  if ( v8 )
  {
    v27 = ((__int64 (__fastcall *)(__int64, WCHAR *))v1)(v8, Buffer);
    if ( v27 )
    {
      v10 = StringCchCopyW(&String1, 0xC8u, L"MSMQTriggers");
      if ( v10 >= 0 )
      {
        v11 = 1;
LABEL_41:
        CClusterNode::~CClusterNode((CClusterNode *)&v27);
        CAutoCluster::~CAutoCluster((CAutoCluster *)&v24);
        return v11;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids,
          (unsigned int)v10);
    }
    else
    {
      v21 = 4;
      v12 = ((__int64 (__fastcall *)(__int64, __int64))v2)(v9, 4);
      v18 = v12;
      if ( v12 )
      {
        v13 = 0;
        memset_0(v28, 0, 0x176u);
        v11 = 1;
        while ( 1 )
        {
          v20 = 186;
          if ( v25(v12, v13, &v21, v28, &v20) )
            goto LABEL_39;
          v14 = (struct _HRESOURCE *)((__int64 (__fastcall *)(__int64, _BYTE *))v4)(v9, v28);
          v15 = v14;
          v23 = v14;
          if ( !v14 )
            break;
          if ( IsResourceMSMQTriggers(v14, v7) )
          {
            v22 = 200;
            if ( v26(v15, String2, &v22) )
            {
              if ( !_wcsicmp(Buffer, String2) )
              {
                v16 = StringCchPrintfW(&String1, 0xC8u, L"%s$%s", L"MSMQTriggers", v28);
                if ( v16 >= 0 )
                {
                  CClusterResource::~CClusterResource((CClusterResource *)&v23);
                  CClusterEnum::~CClusterEnum((CClusterEnum *)&v18);
                  goto LABEL_41;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    25,
                    WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids,
                    (unsigned int)v16);
                goto LABEL_38;
              }
            }
          }
          ++v13;
          CClusterResource::~CClusterResource((CClusterResource *)&v23);
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids);
LABEL_38:
        CClusterResource::~CClusterResource((CClusterResource *)&v23);
        goto LABEL_39;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids);
LABEL_39:
      CClusterEnum::~CClusterEnum((CClusterEnum *)&v18);
    }
    v11 = 0;
    goto LABEL_41;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids);
  CAutoCluster::~CAutoCluster((CAutoCluster *)&v24);
  return 0;
}

```

## disassembly

```asm
0x1800141cc  push    rbp
0x1800141ce  push    rbx
0x1800141cf  push    rsi
0x1800141d0  push    rdi
0x1800141d1  push    r12
0x1800141d3  push    r13
0x1800141d5  push    r14
0x1800141d7  push    r15
0x1800141d9  lea     rbp, [rsp-428h]
0x1800141e1  sub     rsp, 528h
0x1800141e8  mov     rax, cs:__security_cookie
0x1800141ef  xor     rax, rsp
0x1800141f2  mov     [rbp+460h+var_50], rax
0x1800141f9  mov     [rsp+560h+nSize], 0C8h
0x180014201  lea     rdx, [rsp+560h+nSize]; nSize
0x180014206  lea     rcx, [rbp+460h+Buffer]; lpBuffer
0x18001420d  call    cs:__imp_GetComputerNameW
0x180014213  lea     rdx, aOpencluster; "OpenCluster"
0x18001421a  mov     rcx, cs:?g_hLib@@3VCAutoFreeLibrary@@A; hModule
0x180014221  call    cs:__imp_GetProcAddress
0x180014227  mov     r14, rax
0x18001422a  lea     rdx, aOpenclusternod; "OpenClusterNode"
0x180014231  mov     rcx, cs:?g_hLib@@3VCAutoFreeLibrary@@A; hModule
0x180014238  call    cs:__imp_GetProcAddress
0x18001423e  mov     rdi, rax
0x180014241  lea     rdx, aClusteropenenu; "ClusterOpenEnum"
0x180014248  mov     rcx, cs:?g_hLib@@3VCAutoFreeLibrary@@A; hModule
0x18001424f  call    cs:__imp_GetProcAddress
0x180014255  mov     rsi, rax
0x180014258  lea     rdx, aClusterenum; "ClusterEnum"
0x18001425f  mov     rcx, cs:?g_hLib@@3VCAutoFreeLibrary@@A; hModule
0x180014266  call    cs:__imp_GetProcAddress
0x18001426c  mov     r15, rax
0x18001426f  mov     [rsp+560h+var_508], rax
0x180014274  lea     rdx, aOpenclusterres; "OpenClusterResource"
0x18001427b  mov     rcx, cs:?g_hLib@@3VCAutoFreeLibrary@@A; hModule
0x180014282  call    cs:__imp_GetProcAddress
0x180014288  mov     r13, rax
0x18001428b  lea     rdx, aGetclusterreso; "GetClusterResourceNetworkName"
0x180014292  mov     rcx, cs:?g_hLib@@3VCAutoFreeLibrary@@A; hModule
0x180014299  call    cs:__imp_GetProcAddress
0x18001429f  mov     rbx, rax
0x1800142a2  mov     [rsp+560h+var_500], rax
0x1800142a7  lea     rdx, aClusterresourc; "ClusterResourceControl"
0x1800142ae  mov     rcx, cs:?g_hLib@@3VCAutoFreeLibrary@@A; hModule
0x1800142b5  call    cs:__imp_GetProcAddress
0x1800142bb  mov     r12, rax
0x1800142be  test    r14, r14
0x1800142c1  jz      loc_1800145D8
0x1800142c7  test    rdi, rdi
0x1800142ca  jz      loc_1800145D8
0x1800142d0  test    rsi, rsi
0x1800142d3  jz      loc_1800145D8
0x1800142d9  test    r15, r15
0x1800142dc  jz      loc_1800145D8
0x1800142e2  test    r13, r13
0x1800142e5  jz      loc_1800145D8
0x1800142eb  test    rbx, rbx
0x1800142ee  jz      loc_1800145D8
0x1800142f4  test    rax, rax
0x1800142f7  jz      loc_1800145D8
0x1800142fd  xor     ecx, ecx
0x1800142ff  mov     rax, r14
0x180014302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014307  mov     rbx, rax
0x18001430a  mov     [rsp+560h+var_510], rax
0x18001430f  test    rax, rax
0x180014312  jnz     short loc_180014350
0x180014314  lea     rax, WPP_GLOBAL_Control
0x18001431b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014322  cmp     rcx, rax
0x180014325  jz      short loc_180014341
0x180014327  test    byte ptr [rcx+1Ch], 4
0x18001432b  jz      short loc_180014341
0x18001432d  lea     edx, [rbx+15h]
0x180014330  lea     r8, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids
0x180014337  mov     rcx, [rcx+10h]
0x18001433b  call    WPP_SF_
0x180014340  nop
0x180014341  lea     rcx, [rsp+560h+var_510]; this
0x180014346  call    ??1CAutoCluster@@QEAA@XZ; CAutoCluster::~CAutoCluster(void)
0x18001434b  jmp     loc_180014606
0x180014350  lea     rdx, [rbp+460h+Buffer]
0x180014357  mov     rcx, rbx
0x18001435a  mov     rax, rdi
0x18001435d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014362  mov     [rsp+560h+var_4F8], rax
0x180014367  test    rax, rax
0x18001436a  jz      short loc_1800143D6
0x18001436c  lea     r8, aMsmqtriggers; "MSMQTriggers"
0x180014373  mov     edx, 0C8h; unsigned __int64
0x180014378  lea     rcx, String1; wchar_t *
0x18001437f  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180014384  mov     r9d, eax
0x180014387  test    eax, eax
0x180014389  jns     short loc_1800143CB
0x18001438b  lea     rax, WPP_GLOBAL_Control
0x180014392  mov     rcx, cs:WPP_GLOBAL_Control
0x180014399  cmp     rcx, rax
0x18001439c  jz      loc_1800145BB
0x1800143a2  mov     r14d, 1
0x1800143a8  test    [rcx+1Ch], r14b
0x1800143ac  jz      loc_1800145BB
0x1800143b2  lea     edx, [r14+15h]
0x1800143b6  lea     r8, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids
0x1800143bd  mov     rcx, [rcx+10h]
0x1800143c1  call    WPP_SF_d
0x1800143c6  jmp     loc_1800145BB
0x1800143cb  mov     r14d, 1
0x1800143d1  jmp     loc_1800145BE
0x1800143d6  mov     [rsp+560h+var_520], 4
0x1800143de  mov     edx, 4
0x1800143e3  mov     rcx, rbx
0x1800143e6  mov     rax, rsi
0x1800143e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143ee  mov     rsi, rax
0x1800143f1  mov     [rsp+560h+var_530], rax
0x1800143f6  test    rax, rax
0x1800143f9  jnz     short loc_180014434
0x1800143fb  lea     rax, WPP_GLOBAL_Control
0x180014402  mov     rcx, cs:WPP_GLOBAL_Control
0x180014409  cmp     rcx, rax
0x18001440c  jz      loc_1800145B1
0x180014412  test    byte ptr [rcx+1Ch], 4
0x180014416  jz      loc_1800145B1
0x18001441c  lea     edx, [rsi+17h]
0x18001441f  lea     r8, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids
0x180014426  mov     rcx, [rcx+10h]
0x18001442a  call    WPP_SF_
0x18001442f  jmp     loc_1800145B1
0x180014434  xor     r15d, r15d
0x180014437  xor     edx, edx; Val
0x180014439  mov     r8d, 176h; Size
0x18001443f  lea     rcx, [rsp+560h+var_4F0]; void *
0x180014444  call    memset_0
0x180014449  lea     r14d, [r15+1]
0x18001444d  mov     [rsp+560h+var_524], 0BAh
0x180014455  lea     rax, [rsp+560h+var_524]
0x18001445a  mov     [rsp+560h+var_540], rax
0x18001445f  lea     r9, [rsp+560h+var_4F0]
0x180014464  lea     r8, [rsp+560h+var_520]
0x180014469  mov     edx, r15d
0x18001446c  mov     rcx, rsi
0x18001446f  mov     rax, [rsp+560h+var_508]
0x180014474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014479  test    eax, eax
0x18001447b  jnz     loc_1800145B1
0x180014481  lea     rdx, [rsp+560h+var_4F0]
0x180014486  mov     rcx, rbx
0x180014489  mov     rax, r13
0x18001448c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014491  mov     rdi, rax
0x180014494  mov     [rsp+560h+var_518], rax
0x180014499  test    rax, rax
0x18001449c  jz      loc_180014577
0x1800144a2  mov     rdx, r12; unsigned int (*)(struct _HRESOURCE *, struct _HNODE *, unsigned int, void *, unsigned int, void *, unsigned int, unsigned int *)
0x1800144a5  mov     rcx, rax; struct _HRESOURCE *
0x1800144a8  call    ?IsResourceMSMQTriggers@@YA_NPEAU_HRESOURCE@@P6AK0PEAU_HNODE@@KPEAXK2KPEAK@Z@Z; IsResourceMSMQTriggers(_HRESOURCE *,ulong (*)(_HRESOURCE *,_HNODE *,ulong,void *,ulong,void *,ulong,ulong *))
0x1800144ad  test    al, al
0x1800144af  jz      short loc_1800144EE
0x1800144b1  mov     [rsp+560h+var_51C], 0C8h
0x1800144b9  lea     r8, [rsp+560h+var_51C]
0x1800144be  lea     rdx, [rbp+460h+String2]
0x1800144c5  mov     rcx, rdi
0x1800144c8  mov     rax, [rsp+560h+var_500]
0x1800144cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144d2  test    eax, eax
0x1800144d4  jz      short loc_1800144EE
0x1800144d6  lea     rdx, [rbp+460h+String2]; String2
0x1800144dd  lea     rcx, [rbp+460h+Buffer]; String1
0x1800144e4  call    cs:__imp__wcsicmp
0x1800144ea  test    eax, eax
0x1800144ec  jz      short loc_180014500
0x1800144ee  add     r15d, r14d
0x1800144f1  lea     rcx, [rsp+560h+var_518]; this
0x1800144f6  call    ??1CClusterResource@@QEAA@XZ; CClusterResource::~CClusterResource(void)
0x1800144fb  jmp     loc_18001444D
0x180014500  lea     rax, [rsp+560h+var_4F0]
0x180014505  mov     [rsp+560h+var_540], rax
0x18001450a  lea     r9, aMsmqtriggers; "MSMQTriggers"
0x180014511  lea     r8, aSS_1; "%s$%s"
0x180014518  mov     edx, 0C8h; unsigned __int64
0x18001451d  lea     rcx, String1; wchar_t *
0x180014524  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180014529  mov     r9d, eax
0x18001452c  test    eax, eax
0x18001452e  jns     short loc_180014560
0x180014530  lea     rax, WPP_GLOBAL_Control
0x180014537  mov     rcx, cs:WPP_GLOBAL_Control
0x18001453e  cmp     rcx, rax
0x180014541  jz      short loc_1800145A6
0x180014543  test    [rcx+1Ch], r14b
0x180014547  jz      short loc_1800145A6
0x180014549  mov     edx, 19h
0x18001454e  lea     r8, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids
0x180014555  mov     rcx, [rcx+10h]
0x180014559  call    WPP_SF_d
0x18001455e  jmp     short loc_1800145A6
0x180014560  lea     rcx, [rsp+560h+var_518]; this
0x180014565  call    ??1CClusterResource@@QEAA@XZ; CClusterResource::~CClusterResource(void)
0x18001456a  nop
0x18001456b  lea     rcx, [rsp+560h+var_530]; this
0x180014570  call    ??1CClusterEnum@@QEAA@XZ; CClusterEnum::~CClusterEnum(void)
0x180014575  jmp     short loc_1800145BE
0x180014577  lea     rax, WPP_GLOBAL_Control
0x18001457e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014585  cmp     rcx, rax
0x180014588  jz      short loc_1800145A6
0x18001458a  test    byte ptr [rcx+1Ch], 4
0x18001458e  jz      short loc_1800145A6
0x180014590  mov     edx, 18h
0x180014595  lea     r8, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids
0x18001459c  mov     rcx, [rcx+10h]
0x1800145a0  call    WPP_SF_
0x1800145a5  nop
0x1800145a6  lea     rcx, [rsp+560h+var_518]; this
0x1800145ab  call    ??1CClusterResource@@QEAA@XZ; CClusterResource::~CClusterResource(void)
0x1800145b0  nop
0x1800145b1  lea     rcx, [rsp+560h+var_530]; this
0x1800145b6  call    ??1CClusterEnum@@QEAA@XZ; CClusterEnum::~CClusterEnum(void)
0x1800145bb  xor     r14b, r14b
0x1800145be  lea     rcx, [rsp+560h+var_4F8]; this
0x1800145c3  call    ??1CClusterNode@@QEAA@XZ; CClusterNode::~CClusterNode(void)
0x1800145c8  nop
0x1800145c9  lea     rcx, [rsp+560h+var_510]; this
0x1800145ce  call    ??1CAutoCluster@@QEAA@XZ; CAutoCluster::~CAutoCluster(void)
0x1800145d3  mov     al, r14b
0x1800145d6  jmp     short loc_180014608
0x1800145d8  lea     rax, WPP_GLOBAL_Control
0x1800145df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145e6  cmp     rcx, rax
0x1800145e9  jz      short loc_180014606
0x1800145eb  test    byte ptr [rcx+1Ch], 4
0x1800145ef  jz      short loc_180014606
0x1800145f1  mov     edx, 14h
0x1800145f6  lea     r8, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids
0x1800145fd  mov     rcx, [rcx+10h]
0x180014601  call    WPP_SF_
0x180014606  xor     al, al
0x180014608  mov     rcx, [rbp+460h+var_50]
0x18001460f  xor     rcx, rsp; StackCookie
0x180014612  call    __security_check_cookie
0x180014617  add     rsp, 528h
0x18001461e  pop     r15
0x180014620  pop     r14
0x180014622  pop     r13
0x180014624  pop     r12
0x180014626  pop     rdi
0x180014627  pop     rsi
0x180014628  pop     rbx
0x180014629  pop     rbp
0x18001462a  retn
```
