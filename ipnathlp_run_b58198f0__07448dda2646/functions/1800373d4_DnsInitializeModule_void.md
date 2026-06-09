# DnsInitializeModule(void)

- ea: `0x1800373d4`
- end: `0x180037686`
- name: `?DnsInitializeModule@@YAEXZ`
- size: `690`
- prototype: `unsigned __int8(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180036364`

## callees

- `0x18000c6c0`
- `0x18000ca20`
- `0x18000d090`
- `0x1800373d4`
- `0x180042f24`
- `0x18004ed18`
- `0x18004fa34`
- `0x18004fc6c`
- `0x180066fa0`
- `0x180068a34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800374d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800374e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037567`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037576`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800375fe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003760d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800374d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800374e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037567`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037576`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800375fe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003760d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003742d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180037477`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003748d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003742d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180037477`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003748d`

## pseudocode

```c
unsigned __int8 DnsInitializeModule(void)
{
  unsigned int v0; // edi
  unsigned __int8 v1; // bl
  unsigned int v2; // eax
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // eax
  unsigned int v6; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids);
  }
  v0 = dword_1800AE5D8;
  v1 = byte_1800AE5DC;
  InitializeCriticalSection(&DnsComponentReference);
  byte_1800AE5DC = 0;
  qword_1800AE5E0 = (__int64)DnsCleanupProtocol;
  dword_1800AE5D8 = 1;
  TraceCompRef((struct _COMPONENT_REFERENCE *)&DnsComponentReference, "INITIALIZE", v0, v1);
  InitializeCriticalSection(&DnsGlobalInfoLock);
  InitializeCriticalSection(&g_csDnsServerListLock);
  v2 = DnsInitializeFileManagement();
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids, v2);
    }
    DeleteCriticalSection(&DnsGlobalInfoLock);
    DeleteCriticalSection(&g_csDnsServerListLock);
    DeleteComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
    {
      return 0;
    }
    v4 = 19;
LABEL_32:
    WPP_SF_(v3[2], v4, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids);
    return 0;
  }
  v5 = DnsInitializeTableManagement();
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids, v5);
    }
    DnsShutdownFileManagement();
    DeleteCriticalSection(&DnsGlobalInfoLock);
    DeleteCriticalSection(&g_csDnsServerListLock);
    DeleteComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
    {
      return 0;
    }
    v4 = 21;
    goto LABEL_32;
  }
  v6 = DnsInitializeInterfaceManagement();
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids, v6);
    }
    DnsShutdownTableManagement();
    DnsShutdownFileManagement();
    DeleteCriticalSection(&DnsGlobalInfoLock);
    DeleteCriticalSection(&g_csDnsServerListLock);
    DeleteComponentReference((struct _COMPONENT_REFERENCE *)&DnsComponentReference);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
    {
      return 0;
    }
    v4 = 23;
    goto LABEL_32;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids);
  }
  return 1;
}

```

## disassembly

```asm
0x1800373d4  push    rbx
0x1800373d6  push    rbp
0x1800373d7  push    rdi
0x1800373d8  push    r12
0x1800373da  push    r14
0x1800373dc  sub     rsp, 20h
0x1800373e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800373e7  lea     r14, WPP_GLOBAL_Control
0x1800373ee  lea     rbp, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x1800373f5  cmp     rcx, r14
0x1800373f8  jz      short loc_180037417
0x1800373fa  test    byte ptr [rcx+1Ch], 10h
0x1800373fe  jz      short loc_180037417
0x180037400  cmp     byte ptr [rcx+19h], 6
0x180037404  jb      short loc_180037417
0x180037406  mov     rcx, [rcx+10h]
0x18003740a  mov     edx, 0Fh
0x18003740f  mov     r8, rbp
0x180037412  call    WPP_SF_
0x180037417  mov     edi, cs:dword_1800AE5D8
0x18003741d  lea     r12, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; _COMPONENT_REFERENCE DnsComponentReference
0x180037424  mov     bl, cs:byte_1800AE5DC
0x18003742a  mov     rcx, r12; lpCriticalSection
0x18003742d  call    cs:__imp_InitializeCriticalSection
0x180037434  nop     dword ptr [rax+rax+00h]
0x180037439  lea     rax, ?DnsCleanupProtocol@@YAXXZ; DnsCleanupProtocol(void)
0x180037440  mov     cs:byte_1800AE5DC, 0
0x180037447  mov     r9b, bl; unsigned __int8
0x18003744a  mov     cs:qword_1800AE5E0, rax
0x180037451  mov     r8d, edi; unsigned int
0x180037454  mov     cs:dword_1800AE5D8, 1
0x18003745e  lea     rdx, aInitialize; "INITIALIZE"
0x180037465  mov     rcx, r12; struct _COMPONENT_REFERENCE *
0x180037468  call    ?TraceCompRef@@YAXPEAU_COMPONENT_REFERENCE@@PEBDKE@Z; TraceCompRef(_COMPONENT_REFERENCE *,char const *,ulong,uchar)
0x18003746d  lea     rbx, ?DnsGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION DnsGlobalInfoLock
0x180037474  mov     rcx, rbx; lpCriticalSection
0x180037477  call    cs:__imp_InitializeCriticalSection
0x18003747e  nop     dword ptr [rax+rax+00h]
0x180037483  lea     rdi, ?g_csDnsServerListLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csDnsServerListLock
0x18003748a  mov     rcx, rdi; lpCriticalSection
0x18003748d  call    cs:__imp_InitializeCriticalSection
0x180037494  nop     dword ptr [rax+rax+00h]
0x180037499  call    ?DnsInitializeFileManagement@@YAKXZ; DnsInitializeFileManagement(void)
0x18003749e  test    eax, eax
0x1800374a0  jz      loc_180037526
0x1800374a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800374ad  cmp     rcx, r14
0x1800374b0  jz      short loc_1800374D2
0x1800374b2  test    byte ptr [rcx+1Ch], 10h
0x1800374b6  jz      short loc_1800374D2
0x1800374b8  cmp     byte ptr [rcx+19h], 2
0x1800374bc  jb      short loc_1800374D2
0x1800374be  mov     rcx, [rcx+10h]
0x1800374c2  mov     edx, 12h
0x1800374c7  mov     r9d, eax
0x1800374ca  mov     r8, rbp
0x1800374cd  call    WPP_SF_d
0x1800374d2  mov     rcx, rbx; lpCriticalSection
0x1800374d5  call    cs:__imp_DeleteCriticalSection
0x1800374dc  nop     dword ptr [rax+rax+00h]
0x1800374e1  mov     rcx, rdi; lpCriticalSection
0x1800374e4  call    cs:__imp_DeleteCriticalSection
0x1800374eb  nop     dword ptr [rax+rax+00h]
0x1800374f0  mov     rcx, r12; struct _COMPONENT_REFERENCE *
0x1800374f3  call    ?DeleteComponentReference@@YAXPEAU_COMPONENT_REFERENCE@@@Z; DeleteComponentReference(_COMPONENT_REFERENCE *)
0x1800374f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800374ff  cmp     rcx, r14
0x180037502  jz      loc_18003764A
0x180037508  test    byte ptr [rcx+1Ch], 10h
0x18003750c  jz      loc_18003764A
0x180037512  cmp     byte ptr [rcx+19h], 6
0x180037516  jb      loc_18003764A
0x18003751c  mov     edx, 13h
0x180037521  jmp     loc_18003763E
0x180037526  call    ?DnsInitializeTableManagement@@YAKXZ; DnsInitializeTableManagement(void)
0x18003752b  test    eax, eax
0x18003752d  jz      loc_1800375B8
0x180037533  mov     rcx, cs:WPP_GLOBAL_Control
0x18003753a  cmp     rcx, r14
0x18003753d  jz      short loc_18003755F
0x18003753f  test    byte ptr [rcx+1Ch], 10h
0x180037543  jz      short loc_18003755F
0x180037545  cmp     byte ptr [rcx+19h], 2
0x180037549  jb      short loc_18003755F
0x18003754b  mov     rcx, [rcx+10h]
0x18003754f  mov     edx, 14h
0x180037554  mov     r9d, eax
0x180037557  mov     r8, rbp
0x18003755a  call    WPP_SF_d
0x18003755f  call    ?DnsShutdownFileManagement@@YAXXZ; DnsShutdownFileManagement(void)
0x180037564  mov     rcx, rbx; lpCriticalSection
0x180037567  call    cs:__imp_DeleteCriticalSection
0x18003756e  nop     dword ptr [rax+rax+00h]
0x180037573  mov     rcx, rdi; lpCriticalSection
0x180037576  call    cs:__imp_DeleteCriticalSection
0x18003757d  nop     dword ptr [rax+rax+00h]
0x180037582  mov     rcx, r12; struct _COMPONENT_REFERENCE *
0x180037585  call    ?DeleteComponentReference@@YAXPEAU_COMPONENT_REFERENCE@@@Z; DeleteComponentReference(_COMPONENT_REFERENCE *)
0x18003758a  mov     rcx, cs:WPP_GLOBAL_Control
0x180037591  cmp     rcx, r14
0x180037594  jz      loc_18003764A
0x18003759a  test    byte ptr [rcx+1Ch], 10h
0x18003759e  jz      loc_18003764A
0x1800375a4  cmp     byte ptr [rcx+19h], 6
0x1800375a8  jb      loc_18003764A
0x1800375ae  mov     edx, 15h
0x1800375b3  jmp     loc_18003763E
0x1800375b8  call    ?DnsInitializeInterfaceManagement@@YAKXZ; DnsInitializeInterfaceManagement(void)
0x1800375bd  test    eax, eax
0x1800375bf  jz      loc_18003764E
0x1800375c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800375cc  cmp     rcx, r14
0x1800375cf  jz      short loc_1800375F1
0x1800375d1  test    byte ptr [rcx+1Ch], 10h
0x1800375d5  jz      short loc_1800375F1
0x1800375d7  cmp     byte ptr [rcx+19h], 2
0x1800375db  jb      short loc_1800375F1
0x1800375dd  mov     rcx, [rcx+10h]
0x1800375e1  mov     edx, 16h
0x1800375e6  mov     r9d, eax
0x1800375e9  mov     r8, rbp
0x1800375ec  call    WPP_SF_d
0x1800375f1  call    ?DnsShutdownTableManagement@@YAXXZ; DnsShutdownTableManagement(void)
0x1800375f6  call    ?DnsShutdownFileManagement@@YAXXZ; DnsShutdownFileManagement(void)
0x1800375fb  mov     rcx, rbx; lpCriticalSection
0x1800375fe  call    cs:__imp_DeleteCriticalSection
0x180037605  nop     dword ptr [rax+rax+00h]
0x18003760a  mov     rcx, rdi; lpCriticalSection
0x18003760d  call    cs:__imp_DeleteCriticalSection
0x180037614  nop     dword ptr [rax+rax+00h]
0x180037619  mov     rcx, r12; struct _COMPONENT_REFERENCE *
0x18003761c  call    ?DeleteComponentReference@@YAXPEAU_COMPONENT_REFERENCE@@@Z; DeleteComponentReference(_COMPONENT_REFERENCE *)
0x180037621  mov     rcx, cs:WPP_GLOBAL_Control
0x180037628  cmp     rcx, r14
0x18003762b  jz      short loc_18003764A
0x18003762d  test    byte ptr [rcx+1Ch], 10h
0x180037631  jz      short loc_18003764A
0x180037633  cmp     byte ptr [rcx+19h], 6
0x180037637  jb      short loc_18003764A
0x180037639  mov     edx, 17h
0x18003763e  mov     rcx, [rcx+10h]
0x180037642  mov     r8, rbp
0x180037645  call    WPP_SF_
0x18003764a  xor     al, al
0x18003764c  jmp     short loc_180037679
0x18003764e  mov     rcx, cs:WPP_GLOBAL_Control
0x180037655  cmp     rcx, r14
0x180037658  jz      short loc_180037677
0x18003765a  test    byte ptr [rcx+1Ch], 10h
0x18003765e  jz      short loc_180037677
0x180037660  cmp     byte ptr [rcx+19h], 6
0x180037664  jb      short loc_180037677
0x180037666  mov     rcx, [rcx+10h]
0x18003766a  mov     edx, 18h
0x18003766f  mov     r8, rbp
0x180037672  call    WPP_SF_
0x180037677  mov     al, 1
0x180037679  add     rsp, 20h
0x18003767d  pop     r14
0x18003767f  pop     r12
0x180037681  pop     rdi
0x180037682  pop     rbp
0x180037683  pop     rbx
0x180037684  retn
```
