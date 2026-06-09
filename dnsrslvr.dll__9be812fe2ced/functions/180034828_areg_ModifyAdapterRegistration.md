# areg_ModifyAdapterRegistration

- ea: `0x180034828`
- end: `0x180034b2c`
- name: `areg_ModifyAdapterRegistration`
- size: `772`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003473c`

## callees

- `0x180012bb0`
- `0x1800259f0`
- `0x180026270`
- `0x180034828`
- `0x1800363e0`
- `0x180046ec0`
- `0x180047818`
- `0x18004aad8`
- `0x18004ae7c`
- `0x18007c3dc`
- `0x180085fb8`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!DnsGlobals` at `0x180034a18`
- `DNSAPI!DnsModifyRecordsInSet_W` at `0x1800349f0`
- `DNSAPI!DnsModifyRecordsInSet_W` at `0x1800349f0`
- `DNSAPI!Update_ReplaceAddressRecordsW` at `0x180034aa0`
- `DNSAPI!Update_ReplaceAddressRecordsW` at `0x180034aa0`

## pseudocode

```c
__int64 __fastcall areg_ModifyAdapterRegistration(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
{
  __int64 DnsRecordSetUnion; // r13
  int v10; // edx
  int v11; // ecx
  int v12; // r8d
  DWORD v13; // ebx
  __int64 PreviousRegistrationInfo; // r12
  unsigned int v15; // ebx
  unsigned int v16; // eax
  unsigned int updated; // eax
  _BYTE v20[64]; // [rsp+50h] [rbp-B0h] BYREF
  int pExtraList; // [rsp+90h] [rbp-70h] BYREF
  int v22; // [rsp+94h] [rbp-6Ch]
  int v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+A8h] [rbp-58h]
  _DWORD v25[2]; // [rsp+F0h] [rbp-10h] BYREF
  int *p_pExtraList; // [rsp+F8h] [rbp-8h]
  int v27; // [rsp+100h] [rbp+0h]

  DnsRecordSetUnion = 0;
  memset_0(v20, 0, sizeof(v20));
  memset_0(v25, 0, 0x60u);
  memset_0(&pExtraList, 0, 0x60u);
  v13 = 0;
  if ( !g_fVelocityRpcUpdate )
    v13 = 512;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qqqqd(v11, v10, v12, a1, a2, a3, a4);
  if ( a5 == 1 && *(_DWORD *)(a1 + 340) == 1 )
    v13 |= 0x10000u;
  PreviousRegistrationInfo = areg_GetPreviousRegistrationInfo(a1, a5, v20);
  if ( !PreviousRegistrationInfo )
    goto LABEL_35;
  if ( SBYTE2(xmmword_1800AB5A0) < 0 )
    WPP_SF_(1047, 96, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
  DnsRecordSetUnion = areg_CreateDnsRecordSetUnion(a3, PreviousRegistrationInfo);
  if ( DnsRecordSetUnion )
  {
LABEL_35:
    if ( a4
      && !(unsigned int)Dns_NameCompare_W(*(PCNZWCH *)(a4 + 8), *(PCNZWCH *)(a3 + 8))
      && !(unsigned int)areg_IsAnotherUpdateName(a1, *(_QWORD *)(a4 + 8), a5) )
    {
      if ( SBYTE2(xmmword_1800AB5A0) < 0 )
        WPP_SF_S(1047, 98, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, *(_QWORD *)(a4 + 8));
      memset_0(&pExtraList, 0, 0x60u);
      pExtraList = -2147483647;
      v22 = 96;
      v24 = *(_QWORD *)(a2 + 96);
      v23 = 10;
      v16 = DnsModifyRecordsInSet_W(0, (PDNS_RECORD)a4, v13, 0, &pExtraList, 0);
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 99, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, v16);
    }
    if ( DnsGlobals[7] && a5 == 1 )
      v13 |= 0x4000u;
    memset_0(v25, 0, 0x60u);
    v25[0] = -2147483647;
    v25[1] = 96;
    v27 = 2;
    memset_0(&pExtraList, 0, 0x60u);
    v24 = *(_QWORD *)(a1 + 96);
    pExtraList = -2147483647;
    if ( DnsRecordSetUnion )
      a3 = DnsRecordSetUnion;
    v22 = 96;
    v23 = 10;
    p_pExtraList = &pExtraList;
    updated = Update_ReplaceAddressRecordsW(a3, v13, 0, v25, 0);
    v15 = updated;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 100, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, updated);
    areg_SetUpdateStatus(a1, v25, a5);
  }
  else
  {
    if ( SBYTE3(xmmword_1800AB5A0) < 0 )
      WPP_SF_(1055, 97, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
    v15 = 14;
  }
  Dns_RecordListFree(PreviousRegistrationInfo);
  Dns_RecordListFree(DnsRecordSetUnion);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 101, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x180034828  push    rbp
0x18003482a  push    rbx
0x18003482b  push    rsi
0x18003482c  push    rdi
0x18003482d  push    r12
0x18003482f  push    r13
0x180034831  push    r14
0x180034833  push    r15
0x180034835  lea     rbp, [rsp-68h]
0x18003483a  sub     rsp, 168h
0x180034841  mov     rax, cs:__security_cookie
0x180034848  xor     rax, rsp
0x18003484b  mov     [rbp+0A0h+var_50], rax
0x18003484f  mov     edi, [rbp+0A0h+arg_20]
0x180034855  mov     r15, r8
0x180034858  mov     r12, rdx
0x18003485b  mov     [rsp+1A0h+var_160], rdx
0x180034860  mov     rsi, rcx
0x180034863  xor     r13d, r13d
0x180034866  xor     edx, edx; Val
0x180034868  lea     rcx, [rsp+1A0h+var_150]; void *
0x18003486d  mov     r14, r9
0x180034870  lea     r8d, [r13+40h]; Size
0x180034874  call    memset_0
0x180034879  lea     ebx, [r13+60h]
0x18003487d  xor     edx, edx; Val
0x18003487f  mov     r8d, ebx; Size
0x180034882  lea     rcx, [rbp+0A0h+var_B0]; void *
0x180034886  call    memset_0
0x18003488b  mov     r8d, ebx; Size
0x18003488e  lea     rcx, [rbp+0A0h+var_110]; void *
0x180034892  xor     edx, edx; Val
0x180034894  call    memset_0
0x180034899  xor     ebx, ebx
0x18003489b  mov     eax, 200h
0x1800348a0  cmp     cs:g_fVelocityRpcUpdate, ebx
0x1800348a6  cmovz   ebx, eax
0x1800348a9  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800348b0  jz      short loc_1800348CD
0x1800348b2  mov     [rsp+1A0h+var_168], edi
0x1800348b6  mov     r9, rsi
0x1800348b9  mov     [rsp+1A0h+var_170], r14
0x1800348be  mov     [rsp+1A0h+pReserved], r15
0x1800348c3  mov     [rsp+1A0h+pExtraList], r12
0x1800348c8  call    WPP_SF_qqqqd
0x1800348cd  cmp     edi, 1
0x1800348d0  jnz     short loc_1800348DE
0x1800348d2  cmp     [rsi+154h], edi
0x1800348d8  jnz     short loc_1800348DE
0x1800348da  bts     ebx, 10h
0x1800348de  lea     r8, [rsp+1A0h+var_150]
0x1800348e3  mov     edx, edi
0x1800348e5  mov     rcx, rsi
0x1800348e8  call    areg_GetPreviousRegistrationInfo
0x1800348ed  mov     r12, rax
0x1800348f0  test    rax, rax
0x1800348f3  jz      short loc_18003494D
0x1800348f5  cmp     byte ptr cs:xmmword_1800AB5A0+2, r13b
0x1800348fc  jge     short loc_180034914
0x1800348fe  mov     edx, 60h ; '`'
0x180034903  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x18003490a  mov     ecx, 417h
0x18003490f  call    WPP_SF_
0x180034914  mov     rdx, r12
0x180034917  mov     rcx, r15
0x18003491a  call    areg_CreateDnsRecordSetUnion
0x18003491f  mov     r13, rax
0x180034922  test    rax, rax
0x180034925  jnz     short loc_18003494D
0x180034927  cmp     byte ptr cs:xmmword_1800AB5A0+3, al
0x18003492d  jge     short loc_180034943
0x18003492f  lea     edx, [rax+61h]
0x180034932  mov     ecx, 41Fh
0x180034937  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x18003493e  call    WPP_SF_
0x180034943  mov     ebx, 0Eh
0x180034948  jmp     loc_180034AD8
0x18003494d  test    r14, r14
0x180034950  jz      loc_180034A18
0x180034956  mov     rdx, [r15+8]; lpString2
0x18003495a  mov     rcx, [r14+8]; lpString1
0x18003495e  call    Dns_NameCompare_W
0x180034963  test    eax, eax
0x180034965  jnz     loc_180034A18
0x18003496b  mov     rdx, [r14+8]
0x18003496f  mov     r8d, edi
0x180034972  mov     rcx, rsi
0x180034975  call    areg_IsAnotherUpdateName
0x18003497a  test    eax, eax
0x18003497c  jnz     loc_180034A18
0x180034982  cmp     byte ptr cs:xmmword_1800AB5A0+2, al
0x180034988  jge     short loc_1800349A2
0x18003498a  mov     r9, [r14+8]
0x18003498e  lea     edx, [rax+62h]
0x180034991  mov     ecx, 417h
0x180034996  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x18003499d  call    WPP_SF_S
0x1800349a2  xor     edx, edx; Val
0x1800349a4  lea     rcx, [rbp+0A0h+var_110]; void *
0x1800349a8  lea     r8d, [rdx+60h]; Size
0x1800349ac  call    memset_0
0x1800349b1  mov     rax, [rsp+1A0h+var_160]
0x1800349b6  xor     r9d, r9d; hCredentials
0x1800349b9  mov     [rsp+1A0h+pReserved], 0; pReserved
0x1800349c2  mov     r8d, ebx; Options
0x1800349c5  mov     rdx, r14; pDeleteRecords
0x1800349c8  mov     [rbp+0A0h+var_110], 80000001h
0x1800349cf  xor     ecx, ecx; pAddRecords
0x1800349d1  mov     [rbp+0A0h+var_10C], 60h ; '`'
0x1800349d8  mov     rax, [rax+60h]
0x1800349dc  mov     [rbp+0A0h+var_F8], rax
0x1800349e0  lea     rax, [rbp+0A0h+var_110]
0x1800349e4  mov     [rsp+1A0h+pExtraList], rax; pExtraList
0x1800349e9  mov     [rbp+0A0h+var_100], 0Ah
0x1800349f0  call    cs:__imp_DnsModifyRecordsInSet_W
0x1800349f6  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800349fd  jz      short loc_180034A18
0x1800349ff  mov     edx, 63h ; 'c'
0x180034a04  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180034a0b  mov     ecx, 40Bh
0x180034a10  mov     r9d, eax
0x180034a13  call    WPP_SF_d
0x180034a18  mov     rax, cs:__imp_DnsGlobals
0x180034a1f  cmp     dword ptr [rax+1Ch], 0
0x180034a23  jz      short loc_180034A2E
0x180034a25  cmp     edi, 1
0x180034a28  jnz     short loc_180034A2E
0x180034a2a  bts     ebx, 0Eh
0x180034a2e  mov     r14d, 60h ; '`'
0x180034a34  lea     rcx, [rbp+0A0h+var_B0]; void *
0x180034a38  mov     r8d, r14d; Size
0x180034a3b  xor     edx, edx; Val
0x180034a3d  call    memset_0
0x180034a42  mov     r8d, r14d; Size
0x180034a45  mov     [rbp+0A0h+var_B0], 80000001h
0x180034a4c  xor     edx, edx; Val
0x180034a4e  mov     [rbp+0A0h+var_AC], r14d
0x180034a52  lea     rcx, [rbp+0A0h+var_110]; void *
0x180034a56  mov     [rbp+0A0h+var_A0], 2
0x180034a5d  call    memset_0
0x180034a62  mov     rax, [rsi+60h]
0x180034a66  lea     r9, [rbp+0A0h+var_B0]
0x180034a6a  test    r13, r13
0x180034a6d  mov     [rbp+0A0h+var_F8], rax
0x180034a71  lea     rax, [rbp+0A0h+var_110]
0x180034a75  mov     [rbp+0A0h+var_110], 80000001h
0x180034a7c  cmovnz  r15, r13
0x180034a80  mov     [rbp+0A0h+var_10C], r14d
0x180034a84  mov     rcx, r15
0x180034a87  mov     [rbp+0A0h+var_100], 0Ah
0x180034a8e  xor     r8d, r8d
0x180034a91  mov     [rbp+0A0h+var_A8], rax
0x180034a95  mov     edx, ebx
0x180034a97  mov     [rsp+1A0h+pExtraList], 0
0x180034aa0  call    cs:__imp_Update_ReplaceAddressRecordsW
0x180034aa6  mov     ebx, eax
0x180034aa8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180034aaf  jz      short loc_180034AC9
0x180034ab1  lea     edx, [r14+4]
0x180034ab5  mov     ecx, 40Bh
0x180034aba  mov     r9d, eax
0x180034abd  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180034ac4  call    WPP_SF_d
0x180034ac9  mov     r8d, edi
0x180034acc  lea     rdx, [rbp+0A0h+var_B0]
0x180034ad0  mov     rcx, rsi
0x180034ad3  call    areg_SetUpdateStatus
0x180034ad8  mov     rcx, r12
0x180034adb  call    Dns_RecordListFree
0x180034ae0  mov     rcx, r13
0x180034ae3  call    Dns_RecordListFree
0x180034ae8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180034aef  jz      short loc_180034B0A
0x180034af1  mov     edx, 65h ; 'e'
0x180034af6  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180034afd  mov     ecx, 40Bh
0x180034b02  mov     r9d, ebx
0x180034b05  call    WPP_SF_d
0x180034b0a  mov     eax, ebx
0x180034b0c  mov     rcx, [rbp+0A0h+var_50]
0x180034b10  xor     rcx, rsp; StackCookie
0x180034b13  call    __security_check_cookie
0x180034b18  add     rsp, 168h
0x180034b1f  pop     r15
0x180034b21  pop     r14
0x180034b23  pop     r13
0x180034b25  pop     r12
0x180034b27  pop     rdi
0x180034b28  pop     rsi
0x180034b29  pop     rbx
0x180034b2a  pop     rbp
0x180034b2b  retn
```
