# DhcpDestroyContextEx

- ea: `0x180002534`
- end: `0x1800026f5`
- name: `DhcpDestroyContextEx`
- size: `449`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `46`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800014f0`
- `0x180001670`
- `0x180001a70`
- `0x1800022fc`
- `0x1800159d0`
- `0x18001c18c`
- `0x18001f148`
- `0x18001f59c`
- `0x180020980`
- `0x180020f50`
- `0x18002107c`
- `0x180021db0`
- `0x180021ff0`
- `0x180022fb0`
- `0x1800249ec`
- `0x180027410`
- `0x180027558`
- `0x180027c70`
- `0x180027f74`
- `0x180028590`
- `0x180028724`
- `0x180028890`
- `0x180028a44`
- `0x180028d40`
- `0x180028f10`
- `0x180029260`
- `0x18002939c`
- `0x18002ace0`
- `0x18002ae58`
- `0x18002afb0`
- `0x18002c850`
- `0x18002c96c`
- `0x18002cb60`
- `0x18002ce90`
- `0x18002d120`
- `0x18002d3b0`
- `0x18002d68c`
- `0x18002d930`
- `0x18002dc54`
- `0x18002df40`
- `0x18002e164`
- `0x18003ba84`
- `0x18003c064`
- `0x18003c9d8`
- `0x18003ee24`
- `0x180042b38`

## callees

- `0x180002534`
- `0x1800057f0`
- `0x1800094f0`
- `0x18000b650`
- `0x180010200`
- `0x18001ebd4`
- `0x18004d200`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002613`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002613`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800025b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800025b6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002627`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002627`
- `WS2_32!WSACloseEvent` at `0x1800025fa`
- `WS2_32!WSACloseEvent` at `0x1800025fa`

## pseudocode

```c
__int64 __fastcall DhcpDestroyContextEx(__int64 a1)
{
  HKEY v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  unsigned int i; // edi
  _QWORD *v8; // rcx
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  v10 = a1;
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_S(1025, 43, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids, *(_QWORD *)(a1 + 56));
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McTemplateU0z_EtwEventWriteTransfer(a1, DestroyingDhcpContext, *(_QWORD *)(a1 + 56));
  TraceLogErrorv4(a1, 0, 10);
  *(_DWORD *)(a1 + 656) = 0;
  *(_DWORD *)(a1 + 1980) = 0;
  *(_DWORD *)(a1 + 580) = 0;
  ClearOptionsAndClasses(a1);
  v2 = *(HKEY *)(a1 + 728);
  if ( v2 )
    RegCloseKey(v2);
  v3 = *(void **)(a1 + 664);
  if ( v3 )
  {
    CloseHandle(v3);
    *(_QWORD *)(a1 + 664) = 0;
  }
  v4 = *(void **)(a1 + 1984);
  if ( v4 )
  {
    CloseHandle(v4);
    *(_QWORD *)(a1 + 1984) = 0;
  }
  v5 = *(void **)(a1 + 832);
  if ( v5 )
  {
    WSACloseEvent(v5);
    *(_QWORD *)(a1 + 832) = 0;
  }
  v6 = *(void **)(a1 + 2152);
  if ( v6 )
  {
    CloseHandle(v6);
    *(_QWORD *)(a1 + 2152) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 592));
  CloseDhcpSocket(a1);
  DhcpPunycodeFree(a1 + 432);
  DhcpPunycodeFree(a1 + 1888);
  if ( *(_QWORD *)(a1 + 1904) )
  {
    for ( i = 0; i < *(_DWORD *)(a1 + 1912); ++i )
    {
      v8 = (_QWORD *)(*(_QWORD *)(a1 + 1904) + 8 * (3LL * i + 1));
      if ( *v8 )
        DhcpPunycodeFree(v8);
    }
    DhcpPunycodeFree(a1 + 1904);
  }
  DhcpPunycodeFree(a1 + 496);
  if ( !g_fVelocityStaticRouteCleanup )
    DhcpPunycodeFree(a1 + 512);
  DhcpPunycodeFree(a1 + 544);
  *(_DWORD *)(a1 + 536) = 0;
  DhcpPunycodeFree(a1 + 528);
  *(_DWORD *)(a1 + 520) = 0;
  DhcpPunycodeFree(a1 + 2032);
  DhcpPunycodeFree(&v10);
  return 0;
}

```

## disassembly

```asm
0x180002534  mov     [rsp+arg_0], rcx
0x180002539  push    rbx
0x18000253a  push    rbp
0x18000253b  push    rsi
0x18000253c  push    rdi
0x18000253d  sub     rsp, 28h
0x180002541  mov     rbx, rcx
0x180002544  test    byte ptr cs:xmmword_1800616A0, 2
0x18000254b  jz      short loc_180002567
0x18000254d  mov     r9, [rbx+38h]
0x180002551  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x180002558  mov     edx, 2Bh ; '+'
0x18000255d  mov     ecx, 401h
0x180002562  call    WPP_SF_S
0x180002567  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x18000256e  jz      short loc_180002580
0x180002570  mov     r8, [rbx+38h]
0x180002574  lea     rdx, DestroyingDhcpContext
0x18000257b  call    McTemplateU0z_EtwEventWriteTransfer
0x180002580  xor     edx, edx
0x180002582  mov     rcx, rbx
0x180002585  lea     r8d, [rdx+0Ah]
0x180002589  call    TraceLogErrorv4
0x18000258e  xor     ebp, ebp
0x180002590  mov     rcx, rbx
0x180002593  mov     [rbx+290h], ebp
0x180002599  mov     [rbx+7BCh], ebp
0x18000259f  mov     [rbx+244h], ebp
0x1800025a5  call    ClearOptionsAndClasses
0x1800025aa  mov     rcx, [rbx+2D8h]; hKey
0x1800025b1  test    rcx, rcx
0x1800025b4  jz      short loc_1800025BC
0x1800025b6  call    cs:__imp_RegCloseKey
0x1800025bc  mov     rcx, [rbx+298h]; hObject
0x1800025c3  test    rcx, rcx
0x1800025c6  jz      short loc_1800025D5
0x1800025c8  call    cs:__imp_CloseHandle
0x1800025ce  mov     [rbx+298h], rbp
0x1800025d5  mov     rcx, [rbx+7C0h]; hObject
0x1800025dc  test    rcx, rcx
0x1800025df  jz      short loc_1800025EE
0x1800025e1  call    cs:__imp_CloseHandle
0x1800025e7  mov     [rbx+7C0h], rbp
0x1800025ee  mov     rcx, [rbx+340h]; hEvent
0x1800025f5  test    rcx, rcx
0x1800025f8  jz      short loc_180002607
0x1800025fa  call    cs:__imp_WSACloseEvent
0x180002600  mov     [rbx+340h], rbp
0x180002607  mov     rcx, [rbx+868h]; hObject
0x18000260e  test    rcx, rcx
0x180002611  jz      short loc_180002620
0x180002613  call    cs:__imp_CloseHandle
0x180002619  mov     [rbx+868h], rbp
0x180002620  lea     rcx, [rbx+250h]; lpCriticalSection
0x180002627  call    cs:__imp_DeleteCriticalSection
0x18000262d  mov     rcx, rbx
0x180002630  call    CloseDhcpSocket
0x180002635  lea     rcx, [rbx+1B0h]
0x18000263c  call    DhcpPunycodeFree
0x180002641  lea     rcx, [rbx+760h]
0x180002648  call    DhcpPunycodeFree
0x18000264d  lea     rsi, [rbx+770h]
0x180002654  cmp     [rsi], rbp
0x180002657  jz      short loc_180002690
0x180002659  mov     edi, ebp
0x18000265b  cmp     [rbx+778h], ebp
0x180002661  jbe     short loc_180002688
0x180002663  mov     eax, edi
0x180002665  lea     rcx, [rax+rax*2]
0x180002669  mov     rax, [rsi]
0x18000266c  lea     rcx, [rcx+1]
0x180002670  lea     rcx, [rax+rcx*8]
0x180002674  cmp     [rcx], rbp
0x180002677  jz      short loc_18000267E
0x180002679  call    DhcpPunycodeFree
0x18000267e  inc     edi
0x180002680  cmp     edi, [rbx+778h]
0x180002686  jb      short loc_180002663
0x180002688  mov     rcx, rsi
0x18000268b  call    DhcpPunycodeFree
0x180002690  lea     rcx, [rbx+1F0h]
0x180002697  call    DhcpPunycodeFree
0x18000269c  cmp     cs:g_fVelocityStaticRouteCleanup, ebp
0x1800026a2  jnz     short loc_1800026B0
0x1800026a4  lea     rcx, [rbx+200h]
0x1800026ab  call    DhcpPunycodeFree
0x1800026b0  lea     rcx, [rbx+220h]
0x1800026b7  call    DhcpPunycodeFree
0x1800026bc  lea     rcx, [rbx+210h]
0x1800026c3  mov     [rbx+218h], ebp
0x1800026c9  call    DhcpPunycodeFree
0x1800026ce  lea     rcx, [rbx+7F0h]
0x1800026d5  mov     [rbx+208h], ebp
0x1800026db  call    DhcpPunycodeFree
0x1800026e0  lea     rcx, [rsp+48h+arg_0]
0x1800026e5  call    DhcpPunycodeFree
0x1800026ea  xor     eax, eax
0x1800026ec  add     rsp, 28h
0x1800026f0  pop     rdi
0x1800026f1  pop     rsi
0x1800026f2  pop     rbp
0x1800026f3  pop     rbx
0x1800026f4  retn
```
