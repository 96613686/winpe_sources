# DnsInitializeModule(void)

- ea: `0x1800349d0`
- end: `0x180034c3c`
- name: `?DnsInitializeModule@@YAEXZ`
- size: `620`
- prototype: `unsigned __int8(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180033a64`

## callees

- `0x18000bdc0`
- `0x18000c110`
- `0x18000c750`
- `0x1800349d0`
- `0x18003f984`
- `0x18004b0d0`
- `0x18004ba34`
- `0x18004bf70`
- `0x180062368`
- `0x180063c08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034abb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034ac4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034b3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034b46`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034bc1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034bca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034abb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034ac4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034b3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034b46`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034bc1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034bca`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180034a29`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180034a6d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180034a7d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180034a29`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180034a6d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180034a7d`

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
  v0 = dword_1800A7518;
  v1 = byte_1800A751C;
  InitializeCriticalSection(&DnsComponentReference);
  byte_1800A751C = 0;
  qword_1800A7520 = (__int64)DnsCleanupProtocol;
  dword_1800A7518 = 1;
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
0x1800349d0  push    rbx
0x1800349d2  push    rbp
0x1800349d3  push    rdi
0x1800349d4  push    r12
0x1800349d6  push    r14
0x1800349d8  sub     rsp, 20h
0x1800349dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800349e3  lea     r14, WPP_GLOBAL_Control
0x1800349ea  lea     rbp, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x1800349f1  cmp     rcx, r14
0x1800349f4  jz      short loc_180034A13
0x1800349f6  test    byte ptr [rcx+1Ch], 10h
0x1800349fa  jz      short loc_180034A13
0x1800349fc  cmp     byte ptr [rcx+19h], 6
0x180034a00  jb      short loc_180034A13
0x180034a02  mov     rcx, [rcx+10h]
0x180034a06  mov     edx, 0Fh
0x180034a0b  mov     r8, rbp
0x180034a0e  call    WPP_SF_
0x180034a13  mov     edi, cs:dword_1800A7518
0x180034a19  lea     r12, ?DnsComponentReference@@3U_COMPONENT_REFERENCE@@A; _COMPONENT_REFERENCE DnsComponentReference
0x180034a20  mov     bl, cs:byte_1800A751C
0x180034a26  mov     rcx, r12; lpCriticalSection
0x180034a29  call    cs:__imp_InitializeCriticalSection
0x180034a2f  lea     rax, ?DnsCleanupProtocol@@YAXXZ; DnsCleanupProtocol(void)
0x180034a36  mov     cs:byte_1800A751C, 0
0x180034a3d  mov     r9b, bl; unsigned __int8
0x180034a40  mov     cs:qword_1800A7520, rax
0x180034a47  mov     r8d, edi; unsigned int
0x180034a4a  mov     cs:dword_1800A7518, 1
0x180034a54  lea     rdx, aInitialize; "INITIALIZE"
0x180034a5b  mov     rcx, r12; struct _COMPONENT_REFERENCE *
0x180034a5e  call    ?TraceCompRef@@YAXPEAU_COMPONENT_REFERENCE@@PEBDKE@Z; TraceCompRef(_COMPONENT_REFERENCE *,char const *,ulong,uchar)
0x180034a63  lea     rbx, ?DnsGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION DnsGlobalInfoLock
0x180034a6a  mov     rcx, rbx; lpCriticalSection
0x180034a6d  call    cs:__imp_InitializeCriticalSection
0x180034a73  lea     rdi, ?g_csDnsServerListLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csDnsServerListLock
0x180034a7a  mov     rcx, rdi; lpCriticalSection
0x180034a7d  call    cs:__imp_InitializeCriticalSection
0x180034a83  call    ?DnsInitializeFileManagement@@YAKXZ; DnsInitializeFileManagement(void)
0x180034a88  test    eax, eax
0x180034a8a  jz      short loc_180034B00
0x180034a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180034a93  cmp     rcx, r14
0x180034a96  jz      short loc_180034AB8
0x180034a98  test    byte ptr [rcx+1Ch], 10h
0x180034a9c  jz      short loc_180034AB8
0x180034a9e  cmp     byte ptr [rcx+19h], 2
0x180034aa2  jb      short loc_180034AB8
0x180034aa4  mov     rcx, [rcx+10h]
0x180034aa8  mov     edx, 12h
0x180034aad  mov     r9d, eax
0x180034ab0  mov     r8, rbp
0x180034ab3  call    WPP_SF_d
0x180034ab8  mov     rcx, rbx; lpCriticalSection
0x180034abb  call    cs:__imp_DeleteCriticalSection
0x180034ac1  mov     rcx, rdi; lpCriticalSection
0x180034ac4  call    cs:__imp_DeleteCriticalSection
0x180034aca  mov     rcx, r12; struct _COMPONENT_REFERENCE *
0x180034acd  call    ?DeleteComponentReference@@YAXPEAU_COMPONENT_REFERENCE@@@Z; DeleteComponentReference(_COMPONENT_REFERENCE *)
0x180034ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ad9  cmp     rcx, r14
0x180034adc  jz      loc_180034C01
0x180034ae2  test    byte ptr [rcx+1Ch], 10h
0x180034ae6  jz      loc_180034C01
0x180034aec  cmp     byte ptr [rcx+19h], 6
0x180034af0  jb      loc_180034C01
0x180034af6  mov     edx, 13h
0x180034afb  jmp     loc_180034BF5
0x180034b00  call    ?DnsInitializeTableManagement@@YAKXZ; DnsInitializeTableManagement(void)
0x180034b05  test    eax, eax
0x180034b07  jz      short loc_180034B7F
0x180034b09  mov     rcx, cs:WPP_GLOBAL_Control
0x180034b10  cmp     rcx, r14
0x180034b13  jz      short loc_180034B35
0x180034b15  test    byte ptr [rcx+1Ch], 10h
0x180034b19  jz      short loc_180034B35
0x180034b1b  cmp     byte ptr [rcx+19h], 2
0x180034b1f  jb      short loc_180034B35
0x180034b21  mov     rcx, [rcx+10h]
0x180034b25  mov     edx, 14h
0x180034b2a  mov     r9d, eax
0x180034b2d  mov     r8, rbp
0x180034b30  call    WPP_SF_d
0x180034b35  call    ?DnsShutdownFileManagement@@YAXXZ; DnsShutdownFileManagement(void)
0x180034b3a  mov     rcx, rbx; lpCriticalSection
0x180034b3d  call    cs:__imp_DeleteCriticalSection
0x180034b43  mov     rcx, rdi; lpCriticalSection
0x180034b46  call    cs:__imp_DeleteCriticalSection
0x180034b4c  mov     rcx, r12; struct _COMPONENT_REFERENCE *
0x180034b4f  call    ?DeleteComponentReference@@YAXPEAU_COMPONENT_REFERENCE@@@Z; DeleteComponentReference(_COMPONENT_REFERENCE *)
0x180034b54  mov     rcx, cs:WPP_GLOBAL_Control
0x180034b5b  cmp     rcx, r14
0x180034b5e  jz      loc_180034C01
0x180034b64  test    byte ptr [rcx+1Ch], 10h
0x180034b68  jz      loc_180034C01
0x180034b6e  cmp     byte ptr [rcx+19h], 6
0x180034b72  jb      loc_180034C01
0x180034b78  mov     edx, 15h
0x180034b7d  jmp     short loc_180034BF5
0x180034b7f  call    ?DnsInitializeInterfaceManagement@@YAKXZ; DnsInitializeInterfaceManagement(void)
0x180034b84  test    eax, eax
0x180034b86  jz      short loc_180034C05
0x180034b88  mov     rcx, cs:WPP_GLOBAL_Control
0x180034b8f  cmp     rcx, r14
0x180034b92  jz      short loc_180034BB4
0x180034b94  test    byte ptr [rcx+1Ch], 10h
0x180034b98  jz      short loc_180034BB4
0x180034b9a  cmp     byte ptr [rcx+19h], 2
0x180034b9e  jb      short loc_180034BB4
0x180034ba0  mov     rcx, [rcx+10h]
0x180034ba4  mov     edx, 16h
0x180034ba9  mov     r9d, eax
0x180034bac  mov     r8, rbp
0x180034baf  call    WPP_SF_d
0x180034bb4  call    ?DnsShutdownTableManagement@@YAXXZ; DnsShutdownTableManagement(void)
0x180034bb9  call    ?DnsShutdownFileManagement@@YAXXZ; DnsShutdownFileManagement(void)
0x180034bbe  mov     rcx, rbx; lpCriticalSection
0x180034bc1  call    cs:__imp_DeleteCriticalSection
0x180034bc7  mov     rcx, rdi; lpCriticalSection
0x180034bca  call    cs:__imp_DeleteCriticalSection
0x180034bd0  mov     rcx, r12; struct _COMPONENT_REFERENCE *
0x180034bd3  call    ?DeleteComponentReference@@YAXPEAU_COMPONENT_REFERENCE@@@Z; DeleteComponentReference(_COMPONENT_REFERENCE *)
0x180034bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180034bdf  cmp     rcx, r14
0x180034be2  jz      short loc_180034C01
0x180034be4  test    byte ptr [rcx+1Ch], 10h
0x180034be8  jz      short loc_180034C01
0x180034bea  cmp     byte ptr [rcx+19h], 6
0x180034bee  jb      short loc_180034C01
0x180034bf0  mov     edx, 17h
0x180034bf5  mov     rcx, [rcx+10h]
0x180034bf9  mov     r8, rbp
0x180034bfc  call    WPP_SF_
0x180034c01  xor     al, al
0x180034c03  jmp     short loc_180034C30
0x180034c05  mov     rcx, cs:WPP_GLOBAL_Control
0x180034c0c  cmp     rcx, r14
0x180034c0f  jz      short loc_180034C2E
0x180034c11  test    byte ptr [rcx+1Ch], 10h
0x180034c15  jz      short loc_180034C2E
0x180034c17  cmp     byte ptr [rcx+19h], 6
0x180034c1b  jb      short loc_180034C2E
0x180034c1d  mov     rcx, [rcx+10h]
0x180034c21  mov     edx, 18h
0x180034c26  mov     r8, rbp
0x180034c29  call    WPP_SF_
0x180034c2e  mov     al, 1
0x180034c30  add     rsp, 20h
0x180034c34  pop     r14
0x180034c36  pop     r12
0x180034c38  pop     rdi
0x180034c39  pop     rbp
0x180034c3a  pop     rbx
0x180034c3b  retn
```
