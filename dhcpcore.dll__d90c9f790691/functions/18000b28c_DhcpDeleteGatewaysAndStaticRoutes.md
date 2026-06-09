# DhcpDeleteGatewaysAndStaticRoutes

- ea: `0x18000b28c`
- end: `0x18000b469`
- name: `DhcpDeleteGatewaysAndStaticRoutes`
- size: `477`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180016458`
- `0x1800205e4`
- `0x18003dd50`

## callees

- `0x1800057f0`
- `0x180009310`
- `0x18000b28c`
- `0x18000b470`
- `0x18000b564`
- `0x18000b650`
- `0x180040fd8`
- `0x18004bcc4`
- `0x18004d4c0`
- `0x18004dbc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b302`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b302`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b2ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b2ef`

## pseudocode

```c
__int64 __fastcall DhcpDeleteGatewaysAndStaticRoutes(__int64 a1)
{
  unsigned int v2; // esi
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // eax
  unsigned int v8; // ebp
  int v9; // edx
  __int64 v10; // rcx
  int v11; // r8d

  v2 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 57, WPP_c340248efe383a4e03597a9397b959ee_Traceguids, *(_QWORD *)(a1 + 24));
  v3 = DhcpDeleteGateways(a1);
  v6 = v3;
  if ( v3 && (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_dJ(1025, 58, WPP_c340248efe383a4e03597a9397b959ee_Traceguids, v3, *(_QWORD *)(a1 + 24));
  v7 = DhcpDeleteStaticRoutes(a1, v4, v5, v6);
  if ( v7 && (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_dJ(1025, 59, WPP_c340248efe383a4e03597a9397b959ee_Traceguids, v7, *(_QWORD *)(a1 + 24));
  if ( *(_DWORD *)(a1 + 492) )
  {
    *(_DWORD *)(a1 + 492) = 0;
    DhcpPunycodeFree(a1 + 496);
    *(_QWORD *)(a1 + 496) = 0;
  }
  if ( *(_DWORD *)(a1 + 504) )
  {
    *(_DWORD *)(a1 + 504) = 0;
    DhcpPunycodeFree(a1 + 512);
    *(_QWORD *)(a1 + 512) = 0;
  }
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 672));
  v8 = DhcpClearAllOptions(a1);
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 672));
  if ( v8 )
  {
    v2 = v8;
    if ( (xmmword_1800616A0 & 2) == 0 )
      goto LABEL_12;
    WPP_SF_dJ(1025, 60, WPP_c340248efe383a4e03597a9397b959ee_Traceguids, v8, *(_QWORD *)(a1 + 24));
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_SJD(v10, v9, v11, *(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 24), v2);
LABEL_12:
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McTemplateU0zq_EtwEventWriteTransfer(v10, DeleteGatewayStaticRoutes, *(_QWORD *)(a1 + 56), v2);
  TraceLogErrorv4(a1, v2, 7);
  return v2;
}

```

## disassembly

```asm
0x18000b28c  push    rbx
0x18000b28e  push    rbp
0x18000b28f  push    rsi
0x18000b290  push    rdi
0x18000b291  sub     rsp, 38h
0x18000b295  mov     rdi, rcx
0x18000b298  xor     esi, esi
0x18000b29a  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000b2a1  jnz     loc_18000B345
0x18000b2a7  mov     rcx, rdi
0x18000b2aa  call    DhcpDeleteGateways
0x18000b2af  mov     r9d, eax
0x18000b2b2  test    eax, eax
0x18000b2b4  jnz     loc_18000B364
0x18000b2ba  mov     rcx, rdi
0x18000b2bd  call    DhcpDeleteStaticRoutes
0x18000b2c2  mov     r9d, eax
0x18000b2c5  test    eax, eax
0x18000b2c7  jnz     loc_18000B395
0x18000b2cd  cmp     [rdi+1ECh], esi
0x18000b2d3  jnz     loc_18000B3C6
0x18000b2d9  cmp     [rdi+1F8h], esi
0x18000b2df  jnz     loc_18000B3E3
0x18000b2e5  lea     rbx, [rdi+2A0h]
0x18000b2ec  mov     rcx, rbx; SRWLock
0x18000b2ef  call    cs:__imp_AcquireSRWLockExclusive
0x18000b2f5  mov     rcx, rdi
0x18000b2f8  call    DhcpClearAllOptions
0x18000b2fd  mov     rcx, rbx; SRWLock
0x18000b300  mov     ebp, eax
0x18000b302  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b308  test    ebp, ebp
0x18000b30a  jnz     loc_18000B400
0x18000b310  test    byte ptr cs:xmmword_1800616A0, 2
0x18000b317  jnz     loc_18000B436
0x18000b31d  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x18000b324  jnz     loc_18000B451
0x18000b32a  mov     r8d, 7
0x18000b330  mov     edx, esi
0x18000b332  mov     rcx, rdi
0x18000b335  call    TraceLogErrorv4
0x18000b33a  mov     eax, esi
0x18000b33c  add     rsp, 38h
0x18000b340  pop     rdi
0x18000b341  pop     rsi
0x18000b342  pop     rbp
0x18000b343  pop     rbx
0x18000b344  retn
0x18000b345  mov     r9, [rdi+18h]
0x18000b349  lea     r8, WPP_c340248efe383a4e03597a9397b959ee_Traceguids
0x18000b350  mov     edx, 39h ; '9'
0x18000b355  mov     ecx, 404h
0x18000b35a  call    WPP_SF_q
0x18000b35f  jmp     loc_18000B2A7
0x18000b364  test    byte ptr cs:xmmword_1800616A0, 2
0x18000b36b  jz      loc_18000B2BA
0x18000b371  mov     rax, [rdi+18h]
0x18000b375  lea     r8, WPP_c340248efe383a4e03597a9397b959ee_Traceguids
0x18000b37c  mov     edx, 3Ah ; ':'
0x18000b381  mov     [rsp+58h+var_38], rax
0x18000b386  mov     ecx, 401h
0x18000b38b  call    WPP_SF_dJ
0x18000b390  jmp     loc_18000B2BA
0x18000b395  test    byte ptr cs:xmmword_1800616A0, 2
0x18000b39c  jz      loc_18000B2CD
0x18000b3a2  mov     rax, [rdi+18h]
0x18000b3a6  lea     r8, WPP_c340248efe383a4e03597a9397b959ee_Traceguids
0x18000b3ad  mov     edx, 3Bh ; ';'
0x18000b3b2  mov     [rsp+58h+var_38], rax
0x18000b3b7  mov     ecx, 401h
0x18000b3bc  call    WPP_SF_dJ
0x18000b3c1  jmp     loc_18000B2CD
0x18000b3c6  lea     rbx, [rdi+1F0h]
0x18000b3cd  mov     [rdi+1ECh], esi
0x18000b3d3  mov     rcx, rbx
0x18000b3d6  call    DhcpPunycodeFree
0x18000b3db  mov     [rbx], rsi
0x18000b3de  jmp     loc_18000B2D9
0x18000b3e3  lea     rbx, [rdi+200h]
0x18000b3ea  mov     [rdi+1F8h], esi
0x18000b3f0  mov     rcx, rbx
0x18000b3f3  call    DhcpPunycodeFree
0x18000b3f8  mov     [rbx], rsi
0x18000b3fb  jmp     loc_18000B2E5
0x18000b400  mov     esi, ebp
0x18000b402  test    byte ptr cs:xmmword_1800616A0, 2
0x18000b409  jz      loc_18000B31D
0x18000b40f  mov     rax, [rdi+18h]
0x18000b413  lea     r8, WPP_c340248efe383a4e03597a9397b959ee_Traceguids
0x18000b41a  mov     edx, 3Ch ; '<'
0x18000b41f  mov     [rsp+58h+var_38], rax
0x18000b424  mov     ecx, 401h
0x18000b429  mov     r9d, ebp
0x18000b42c  call    WPP_SF_dJ
0x18000b431  jmp     loc_18000B310
0x18000b436  mov     rax, [rdi+18h]
0x18000b43a  mov     r9, [rdi+38h]
0x18000b43e  mov     [rsp+58h+var_30], esi
0x18000b442  mov     [rsp+58h+var_38], rax
0x18000b447  call    WPP_SF_SJD
0x18000b44c  jmp     loc_18000B31D
0x18000b451  mov     r8, [rdi+38h]
0x18000b455  lea     rdx, DeleteGatewayStaticRoutes
0x18000b45c  mov     r9d, esi
0x18000b45f  call    McTemplateU0zq_EtwEventWriteTransfer
0x18000b464  jmp     loc_18000B32A
```
