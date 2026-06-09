# DeleteQMSAsInternal

- ea: `0x18002e94c`
- end: `0x18002ebb1`
- name: `DeleteQMSAsInternal`
- size: `613`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011390`

## callees

- `0x18000e510`
- `0x18002e94c`
- `0x18002f3b8`

## import_xrefs

- `fwpuclnt!FwpmEngineClose0` at `0x18002eb98`
- `fwpuclnt!FwpmEngineClose0` at `0x18002eb98`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x18002eb89`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x18002eb89`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002eb76`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002eb76`
- `fwpuclnt!IPsecSaContextEnum0` at `0x18002ea44`
- `fwpuclnt!IPsecSaContextEnum0` at `0x18002ea44`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002e996`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002e996`
- `fwpuclnt!IPsecSaContextDeleteById0` at `0x18002eafb`
- `fwpuclnt!IPsecSaContextDeleteById0` at `0x18002eafb`
- `fwpuclnt!IPsecSaContextCreateEnumHandle0` at `0x18002e9ea`
- `fwpuclnt!IPsecSaContextCreateEnumHandle0` at `0x18002e9ea`

## pseudocode

```c
__int64 __fastcall DeleteQMSAsInternal(__int64 a1)
{
  DWORD v2; // eax
  DWORD v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rcx
  DWORD v8; // eax
  _QWORD *v9; // r11
  __int64 v10; // r15
  __int64 v11; // rsi
  IPSEC_SA_CONTEXT0 *v12; // r14
  IPSEC_SA_DETAILS0 *inboundSa; // rdx
  IPSEC_SA_DETAILS0 *outboundSa; // rdx
  DWORD v15; // eax
  HANDLE enumHandle; // [rsp+30h] [rbp-10h] BYREF
  UINT32 numEntriesReturned; // [rsp+78h] [rbp+38h] BYREF
  HANDLE engineHandle; // [rsp+80h] [rbp+40h] BYREF
  IPSEC_SA_CONTEXT0 **entries; // [rsp+88h] [rbp+48h] BYREF

  engineHandle = 0;
  enumHandle = 0;
  numEntriesReturned = 0;
  entries = 0;
  v2 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v5 = 45;
    goto LABEL_5;
  }
  v2 = IPsecSaContextCreateEnumHandle0(engineHandle, 0, &enumHandle);
  v3 = v2;
  if ( v2 == 1753 )
    goto LABEL_38;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v5 = 46;
LABEL_5:
    v6 = v2;
    goto LABEL_6;
  }
  v8 = IPsecSaContextEnum0(engineHandle, enumHandle, 0xFFFFFFFF, &entries, &numEntriesReturned);
  v3 = 0;
  if ( v8 != 1753 )
    v3 = v8;
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_39;
    v5 = 47;
    v6 = v3;
LABEL_6:
    v7 = v4[2];
    goto LABEL_7;
  }
  if ( !numEntriesReturned )
    goto LABEL_38;
  if ( !entries )
  {
    v3 = 0;
    goto LABEL_41;
  }
  if ( !numEntriesReturned )
  {
LABEL_38:
    v3 = 0;
    goto LABEL_39;
  }
  v9 = WPP_GLOBAL_Control;
  v10 = a1 + 136;
  v11 = 0;
  v3 = 0;
  do
  {
    v12 = entries[v11];
    inboundSa = v12->inboundSa;
    if ( inboundSa && (unsigned int)MatchQMSAs(v10, &inboundSa->traffic)
      || (outboundSa = v12->outboundSa) != 0 && (unsigned int)MatchQMSAs(v10, &outboundSa->traffic) )
    {
      v15 = IPsecSaContextDeleteById0(engineHandle, v12->saContextId);
      if ( !v15 )
        goto LABEL_31;
      v3 = v15;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v15);
LABEL_31:
        v9 = WPP_GLOBAL_Control;
      }
    }
    v11 = (unsigned int)(v11 + 1);
  }
  while ( (unsigned int)v11 < numEntriesReturned );
  if ( v3 && v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
  {
    v7 = v9[2];
    v5 = 49;
    v6 = v3;
LABEL_7:
    WPP_SF_d(v7, v5, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v6);
  }
LABEL_39:
  if ( entries )
    FwpmFreeMemory0((void **)&entries);
LABEL_41:
  if ( enumHandle )
    IkeextSaDestroyEnumHandle0(engineHandle, enumHandle);
  if ( engineHandle )
    FwpmEngineClose0(engineHandle);
  return v3;
}

```

## disassembly

```asm
0x18002e94c  mov     [rsp-28h+arg_0], rbx
0x18002e951  push    rbp
0x18002e952  push    rsi
0x18002e953  push    rdi
0x18002e954  push    r14
0x18002e956  push    r15
0x18002e958  mov     rbp, rsp
0x18002e95b  sub     rsp, 40h
0x18002e95f  xor     r9d, r9d; session
0x18002e962  mov     [rbp+arg_10], 0
0x18002e96a  mov     rdi, rcx
0x18002e96d  mov     [rbp+enumHandle], 0
0x18002e975  lea     rax, [rbp+arg_10]
0x18002e979  mov     [rbp+numEntriesReturned], 0
0x18002e980  xor     r8d, r8d; authIdentity
0x18002e983  mov     [rbp+entries], 0
0x18002e98b  lea     edx, [r9+0Ah]; authnService
0x18002e98f  mov     [rsp+40h+engineHandle], rax; engineHandle
0x18002e994  xor     ecx, ecx; serverName
0x18002e996  call    cs:__imp_FwpmEngineOpen0
0x18002e99c  mov     ebx, eax
0x18002e99e  test    eax, eax
0x18002e9a0  jz      short loc_18002E9E0
0x18002e9a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9a9  lea     rdi, WPP_GLOBAL_Control
0x18002e9b0  cmp     rcx, rdi
0x18002e9b3  jz      loc_18002EB6B
0x18002e9b9  test    byte ptr [rcx+1Ch], 10h
0x18002e9bd  jz      loc_18002EB6B
0x18002e9c3  mov     edx, 2Dh ; '-'
0x18002e9c8  mov     r9d, eax
0x18002e9cb  mov     rcx, [rcx+10h]
0x18002e9cf  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002e9d6  call    WPP_SF_d
0x18002e9db  jmp     loc_18002EB6B
0x18002e9e0  mov     rcx, [rbp+arg_10]; engineHandle
0x18002e9e4  lea     r8, [rbp+enumHandle]; enumHandle
0x18002e9e8  xor     edx, edx; enumTemplate
0x18002e9ea  call    cs:__imp_IPsecSaContextCreateEnumHandle0
0x18002e9f0  mov     esi, 6D9h
0x18002e9f5  mov     ebx, eax
0x18002e9f7  cmp     eax, esi
0x18002e9f9  jz      loc_18002EB69
0x18002e9ff  test    eax, eax
0x18002ea01  jz      short loc_18002EA2B
0x18002ea03  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea0a  lea     rdi, WPP_GLOBAL_Control
0x18002ea11  cmp     rcx, rdi
0x18002ea14  jz      loc_18002EB6B
0x18002ea1a  test    byte ptr [rcx+1Ch], 10h
0x18002ea1e  jz      loc_18002EB6B
0x18002ea24  mov     edx, 2Eh ; '.'
0x18002ea29  jmp     short loc_18002E9C8
0x18002ea2b  mov     rdx, [rbp+enumHandle]; enumHandle
0x18002ea2f  lea     rax, [rbp+numEntriesReturned]
0x18002ea33  mov     rcx, [rbp+arg_10]; engineHandle
0x18002ea37  lea     r9, [rbp+entries]; entries
0x18002ea3b  or      r8d, 0FFFFFFFFh; numEntriesRequested
0x18002ea3f  mov     [rsp+40h+engineHandle], rax; numEntriesReturned
0x18002ea44  call    cs:__imp_IPsecSaContextEnum0
0x18002ea4a  xor     ebx, ebx
0x18002ea4c  cmp     eax, esi
0x18002ea4e  cmovnz  ebx, eax
0x18002ea51  test    ebx, ebx
0x18002ea53  jz      short loc_18002EA83
0x18002ea55  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea5c  lea     rdi, WPP_GLOBAL_Control
0x18002ea63  cmp     rcx, rdi
0x18002ea66  jz      loc_18002EB6B
0x18002ea6c  test    byte ptr [rcx+1Ch], 10h
0x18002ea70  jz      loc_18002EB6B
0x18002ea76  mov     edx, 2Fh ; '/'
0x18002ea7b  mov     r9d, ebx
0x18002ea7e  jmp     loc_18002E9CB
0x18002ea83  mov     eax, [rbp+numEntriesReturned]
0x18002ea86  test    eax, eax
0x18002ea88  jz      loc_18002EB69
0x18002ea8e  cmp     [rbp+entries], 0
0x18002ea93  jz      loc_18002EB65
0x18002ea99  test    eax, eax
0x18002ea9b  jz      loc_18002EB69
0x18002eaa1  mov     r11, cs:WPP_GLOBAL_Control
0x18002eaa8  lea     r15, [rdi+88h]
0x18002eaaf  xor     esi, esi
0x18002eab1  lea     rdi, WPP_GLOBAL_Control
0x18002eab8  xor     ebx, ebx
0x18002eaba  mov     rax, [rbp+entries]
0x18002eabe  mov     r14, [rax+rsi*8]
0x18002eac2  mov     rdx, [r14+8]
0x18002eac6  test    rdx, rdx
0x18002eac9  jz      short loc_18002EADB
0x18002eacb  add     rdx, 8
0x18002eacf  mov     rcx, r15
0x18002ead2  call    MatchQMSAs
0x18002ead7  test    eax, eax
0x18002ead9  jnz     short loc_18002EAF4
0x18002eadb  mov     rdx, [r14+10h]
0x18002eadf  test    rdx, rdx
0x18002eae2  jz      short loc_18002EB39
0x18002eae4  add     rdx, 8
0x18002eae8  mov     rcx, r15
0x18002eaeb  call    MatchQMSAs
0x18002eaf0  test    eax, eax
0x18002eaf2  jz      short loc_18002EB39
0x18002eaf4  mov     rdx, [r14]; id
0x18002eaf7  mov     rcx, [rbp+arg_10]; engineHandle
0x18002eafb  call    cs:__imp_IPsecSaContextDeleteById0
0x18002eb01  test    eax, eax
0x18002eb03  jz      short loc_18002EB32
0x18002eb05  mov     ebx, eax
0x18002eb07  mov     r11, cs:WPP_GLOBAL_Control
0x18002eb0e  cmp     r11, rdi
0x18002eb11  jz      short loc_18002EB39
0x18002eb13  test    byte ptr [r11+1Ch], 10h
0x18002eb18  jz      short loc_18002EB39
0x18002eb1a  mov     rcx, [r11+10h]
0x18002eb1e  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002eb25  mov     edx, 30h ; '0'
0x18002eb2a  mov     r9d, eax
0x18002eb2d  call    WPP_SF_d
0x18002eb32  mov     r11, cs:WPP_GLOBAL_Control
0x18002eb39  inc     esi
0x18002eb3b  cmp     esi, [rbp+numEntriesReturned]
0x18002eb3e  jb      loc_18002EABA
0x18002eb44  test    ebx, ebx
0x18002eb46  jz      short loc_18002EB6B
0x18002eb48  cmp     r11, rdi
0x18002eb4b  jz      short loc_18002EB6B
0x18002eb4d  test    byte ptr [r11+1Ch], 10h
0x18002eb52  jz      short loc_18002EB6B
0x18002eb54  mov     rcx, [r11+10h]
0x18002eb58  mov     edx, 31h ; '1'
0x18002eb5d  mov     r9d, ebx
0x18002eb60  jmp     loc_18002E9CF
0x18002eb65  xor     ebx, ebx
0x18002eb67  jmp     short loc_18002EB7C
0x18002eb69  xor     ebx, ebx
0x18002eb6b  cmp     [rbp+entries], 0
0x18002eb70  jz      short loc_18002EB7C
0x18002eb72  lea     rcx, [rbp+entries]; p
0x18002eb76  call    cs:__imp_FwpmFreeMemory0
0x18002eb7c  mov     rdx, [rbp+enumHandle]; enumHandle
0x18002eb80  test    rdx, rdx
0x18002eb83  jz      short loc_18002EB8F
0x18002eb85  mov     rcx, [rbp+arg_10]; engineHandle
0x18002eb89  call    cs:__imp_IkeextSaDestroyEnumHandle0
0x18002eb8f  mov     rcx, [rbp+arg_10]; engineHandle
0x18002eb93  test    rcx, rcx
0x18002eb96  jz      short loc_18002EB9E
0x18002eb98  call    cs:__imp_FwpmEngineClose0
0x18002eb9e  mov     eax, ebx
0x18002eba0  mov     rbx, [rsp+40h+arg_0]
0x18002eba5  add     rsp, 40h
0x18002eba9  pop     r15
0x18002ebab  pop     r14
0x18002ebad  pop     rdi
0x18002ebae  pop     rsi
0x18002ebaf  pop     rbp
0x18002ebb0  retn
```
