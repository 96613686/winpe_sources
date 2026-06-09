# DhcpGetFailoverLeaseDuration

- ea: `0x18005518c`
- end: `0x180055466`
- name: `DhcpGetFailoverLeaseDuration`
- size: `730`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800556d0`
- `0x180057cf8`
- `0x18005923c`
- `0x18005a9ec`

## callees

- `0x180003228`
- `0x18001dde0`
- `0x18005518c`
- `0x180057a90`
- `0x1800a05b8`
- `0x1800a0788`

## import_xrefs

- `msvcrt!time` at `0x1800552ed`
- `msvcrt!time` at `0x180055399`
- `msvcrt!time` at `0x1800552ed`
- `msvcrt!time` at `0x180055399`
- `ADVAPI32!RegCloseKey` at `0x18005523b`
- `ADVAPI32!RegCloseKey` at `0x18005523b`
- `ADVAPI32!RegOpenKeyExW` at `0x180055204`
- `ADVAPI32!RegOpenKeyExW` at `0x180055204`
- `WS2_32!__imp_ntohl` at `0x1800552c7`
- `WS2_32!__imp_ntohl` at `0x1800552c7`
- `KERNEL32!HeapFree` at `0x180055441`
- `KERNEL32!HeapFree` at `0x180055441`

## string_xrefs

- `0x1800551c1`: `System\CurrentControlSet\Services\DhcpServer\Parameters`

## pseudocode

```c
int __fastcall DhcpGetFailoverLeaseDuration(__int64 a1, int a2, u_long *a3, int *a4, u_long *a5, int *a6, u_long *a7)
{
  unsigned int v9; // edi
  signed int v10; // r12d
  int *v11; // r14
  u_long *v12; // rsi
  unsigned int v13; // r8d
  u_long v14; // eax
  unsigned int v15; // r8d
  unsigned int v16; // edi
  unsigned int v17; // eax
  int v18; // ecx
  int result; // eax
  unsigned int v20; // eax
  int v21; // ecx
  unsigned int v22; // edx
  int v23; // eax
  _DWORD v24[3]; // [rsp+34h] [rbp-2Ch] BYREF
  HKEY hKey[2]; // [rsp+40h] [rbp-20h] BYREF
  int v26; // [rsp+50h] [rbp-10h]
  int v27; // [rsp+54h] [rbp-Ch]
  int v28; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v29; // [rsp+B0h] [rbp+50h]
  int *v30; // [rsp+B8h] [rbp+58h]

  v30 = a4;
  v28 = a2;
  v26 = 4;
  hKey[1] = (HKEY)&v28;
  memset(v24, 0, sizeof(v24));
  v29 = 0;
  hKey[0] = 0;
  v27 = 1;
  v9 = 0;
  v10 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\DhcpServer\\Parameters",
          0,
          0x20019u,
          hKey) )
  {
    DhcpRegGetValue(hKey[0], L"EnableRenewRebindOptions");
    RegCloseKey(hKey[0]);
  }
  v11 = a6;
  v12 = a5;
  if ( *(_QWORD *)(a1 + 144) )
  {
    GetLeaseInfo(a1, 0);
    v9 = v29;
  }
  if ( (unsigned int)DhcpDALJetOpenKey(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 1) )
  {
    v13 = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 4304LL);
  }
  else
  {
    if ( (unsigned int)DhcpDALJetGetValue(
                         DhcpGlobalJetServerSession,
                         DhcpGlobalClientTableHandle,
                         *(_DWORD *)(DhcpGlobalClientTable + 232),
                         (__int64)v24)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_8d34d085f3b73e207e43a51a56ca0bcb_Traceguids);
    }
    if ( *(_QWORD *)&v24[1] && **(_DWORD **)&v24[1] == -1 )
      goto LABEL_31;
    v20 = time(0);
    v21 = 0;
    if ( *(_QWORD *)&v24[1] )
    {
      if ( **(_DWORD **)&v24[1] < v20 )
        v21 = -1;
      else
        v21 = **(_DWORD **)&v24[1] - v20;
      v10 = **(_DWORD **)&v24[1] < v20 ? 0x80070216 : 0;
    }
    v22 = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 4304LL);
    v23 = 0;
    if ( v10 >= 0 )
      v23 = v21;
    v13 = -1;
    if ( v23 + v22 >= v22 )
      v13 = v23 + v22;
    if ( v13 >= v9 )
    {
LABEL_31:
      *a3 = v9;
      v13 = v9;
      goto LABEL_8;
    }
  }
  *a3 = v13;
LABEL_8:
  if ( a7 )
  {
    v14 = ntohl(*a7);
    v13 = *a3;
    if ( *a3 > v14 )
    {
      v13 = v14;
      *a3 = v14;
    }
  }
  v15 = v13 >> 1;
  v16 = v15 + v9;
  if ( v16 < v15 || (v17 = time(0), v18 = v17 + v16, v17 + v16 < v17) )
    v18 = -1;
  *v30 = v18;
  *v12 = *a3 >> 1;
  result = 7 * (*a3 >> 3);
  *v11 = result;
  if ( *(_QWORD *)&v24[1] )
    return HeapFree(gDhcpHeap, 0, *(LPVOID *)&v24[1]);
  return result;
}

```

## disassembly

```asm
0x18005518c  mov     [rsp-38h+arg_0], rbx
0x180055191  mov     [rsp-38h+arg_18], r9
0x180055196  mov     [rsp-38h+arg_8], edx
0x18005519a  push    rbp
0x18005519b  push    rsi
0x18005519c  push    rdi
0x18005519d  push    r12
0x18005519f  push    r13
0x1800551a1  push    r14
0x1800551a3  push    r15
0x1800551a5  mov     rbp, rsp
0x1800551a8  sub     rsp, 60h
0x1800551ac  xor     esi, esi
0x1800551ae  mov     [rbp+var_10], 4
0x1800551b5  lea     rax, [rbp+arg_8]
0x1800551b9  mov     qword ptr [rbp+var_2C+4], rsi
0x1800551bd  mov     [rbp+var_18], rax
0x1800551c1  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Dh"...
0x1800551c8  mov     rbx, r8
0x1800551cb  mov     dword ptr [rbp+var_2C], esi
0x1800551ce  mov     r13, rcx
0x1800551d1  mov     [rbp+arg_10], esi
0x1800551d4  lea     rax, [rbp+hKey]
0x1800551d8  mov     [rbp+hKey], rsi
0x1800551dc  lea     r14d, [rsi+1]
0x1800551e0  mov     [rbp+var_30], esi
0x1800551e3  mov     r9d, 20019h; samDesired
0x1800551e9  mov     [rbp+var_C], r14d
0x1800551ed  xor     r8d, r8d; ulOptions
0x1800551f0  mov     [rsp+60h+phkResult], rax; phkResult
0x1800551f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800551fc  mov     edi, esi
0x1800551fe  mov     r12d, esi
0x180055201  mov     r15d, esi
0x180055204  call    cs:__imp_RegOpenKeyExW
0x18005520b  nop     dword ptr [rax+rax+00h]
0x180055210  test    eax, eax
0x180055212  jnz     short loc_180055247
0x180055214  mov     rcx, [rbp+hKey]; hKey
0x180055218  lea     r9, [rbp+var_30]
0x18005521c  lea     r8d, [rsi+4]
0x180055220  lea     rdx, aEnablerenewreb; "EnableRenewRebindOptions"
0x180055227  call    DhcpRegGetValue
0x18005522c  test    eax, eax
0x18005522e  jnz     short loc_180055237
0x180055230  cmp     [rbp+var_30], esi
0x180055233  cmovnz  r15d, r14d
0x180055237  mov     rcx, [rbp+hKey]; hKey
0x18005523b  call    cs:__imp_RegCloseKey
0x180055242  nop     dword ptr [rax+rax+00h]
0x180055247  mov     r14, [rbp+arg_28]
0x18005524b  xor     eax, eax
0x18005524d  mov     rsi, [rbp+arg_20]
0x180055251  cmp     [r13+90h], rax
0x180055258  jz      short loc_180055281
0x18005525a  mov     [rsp+60h+phkResult], rax; __int64
0x18005525f  lea     rdx, [rbp+arg_10]
0x180055263  mov     rcx, r13; int
0x180055266  test    r15d, r15d
0x180055269  jnz     short loc_180055273
0x18005526b  xor     r9d, r9d
0x18005526e  xor     r8d, r8d
0x180055271  jmp     short loc_180055279
0x180055273  mov     r9, r14
0x180055276  mov     r8, rsi
0x180055279  call    GetLeaseInfo
0x18005527e  mov     edi, [rbp+arg_10]
0x180055281  mov     r8, cs:DhcpGlobalClientTable
0x180055288  lea     r9, [rbp+var_18]
0x18005528c  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x180055293  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18005529a  mov     dword ptr [rsp+60h+phkResult], 1; int
0x1800552a2  mov     r8, [r8]
0x1800552a5  call    DhcpDALJetOpenKey
0x1800552aa  test    eax, eax
0x1800552ac  jz      short loc_180055328
0x1800552ae  mov     rax, [r13+58h]
0x1800552b2  mov     r8d, [rax+10D0h]
0x1800552b9  mov     [rbx], r8d
0x1800552bc  mov     rcx, [rbp+arg_30]
0x1800552c0  test    rcx, rcx
0x1800552c3  jz      short loc_1800552E0
0x1800552c5  mov     ecx, [rcx]; netlong
0x1800552c7  call    cs:__imp_ntohl
0x1800552ce  nop     dword ptr [rax+rax+00h]
0x1800552d3  mov     r8d, [rbx]
0x1800552d6  cmp     r8d, eax
0x1800552d9  jbe     short loc_1800552E0
0x1800552db  mov     r8d, eax
0x1800552de  mov     [rbx], eax
0x1800552e0  shr     r8d, 1
0x1800552e3  add     edi, r8d
0x1800552e6  cmp     edi, r8d
0x1800552e9  jb      short loc_180055300
0x1800552eb  xor     ecx, ecx; Time
0x1800552ed  call    cs:__imp_time
0x1800552f4  nop     dword ptr [rax+rax+00h]
0x1800552f9  lea     ecx, [rax+rdi]
0x1800552fc  cmp     ecx, eax
0x1800552fe  jnb     short loc_180055303
0x180055300  or      ecx, 0FFFFFFFFh
0x180055303  mov     rax, [rbp+arg_18]
0x180055307  mov     [rax], ecx
0x180055309  test    r15d, r15d
0x18005530c  jnz     loc_1800553FE
0x180055312  mov     eax, [rbx]
0x180055314  shr     eax, 1
0x180055316  mov     [rsi], eax
0x180055318  mov     eax, [rbx]
0x18005531a  shr     eax, 3
0x18005531d  imul    eax, 7
0x180055320  mov     [r14], eax
0x180055323  jmp     loc_18005542F
0x180055328  mov     r8, cs:DhcpGlobalClientTable
0x18005532f  lea     rax, [rbp+var_2C]
0x180055333  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18005533a  lea     r9, [rbp+var_2C+4]
0x18005533e  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180055345  mov     [rsp+60h+phkResult], rax; __int64
0x18005534a  mov     r8d, [r8+0E8h]; columnid
0x180055351  call    DhcpDALJetGetValue
0x180055356  test    eax, eax
0x180055358  jz      short loc_180055388
0x18005535a  mov     rcx, cs:WPP_GLOBAL_Control
0x180055361  lea     rax, WPP_GLOBAL_Control
0x180055368  cmp     rcx, rax
0x18005536b  jz      short loc_180055388
0x18005536d  test    byte ptr [rcx+1Ch], 10h
0x180055371  jz      short loc_180055388
0x180055373  mov     rcx, [rcx+10h]
0x180055377  lea     r8, WPP_8d34d085f3b73e207e43a51a56ca0bcb_Traceguids
0x18005537e  mov     edx, 82h
0x180055383  call    WPP_SF_
0x180055388  mov     r8, qword ptr [rbp+var_2C+4]
0x18005538c  test    r8, r8
0x18005538f  jz      short loc_180055397
0x180055391  cmp     dword ptr [r8], 0FFFFFFFFh
0x180055395  jz      short loc_1800553F4
0x180055397  xor     ecx, ecx; Time
0x180055399  call    cs:__imp_time
0x1800553a0  nop     dword ptr [rax+rax+00h]
0x1800553a5  mov     r8, qword ptr [rbp+var_2C+4]
0x1800553a9  xor     ecx, ecx
0x1800553ab  test    r8, r8
0x1800553ae  jz      short loc_1800553CC
0x1800553b0  cmp     [r8], eax
0x1800553b3  jb      short loc_1800553BC
0x1800553b5  mov     ecx, [r8]
0x1800553b8  sub     ecx, eax
0x1800553ba  jmp     short loc_1800553BF
0x1800553bc  or      ecx, 0FFFFFFFFh
0x1800553bf  cmp     [r8], eax
0x1800553c2  sbb     r12d, r12d
0x1800553c5  and     r12d, 80070216h
0x1800553cc  mov     rax, [r13+58h]
0x1800553d0  mov     edx, [rax+10D0h]
0x1800553d6  xor     eax, eax
0x1800553d8  test    r12d, r12d
0x1800553db  cmovns  eax, ecx
0x1800553de  or      r8d, 0FFFFFFFFh
0x1800553e2  lea     ecx, [rax+rdx]
0x1800553e5  cmp     ecx, edx
0x1800553e7  cmovnb  r8d, ecx
0x1800553eb  cmp     r8d, edi
0x1800553ee  jb      loc_1800552B9
0x1800553f4  mov     [rbx], edi
0x1800553f6  mov     r8d, edi
0x1800553f9  jmp     loc_1800552BC
0x1800553fe  mov     eax, [r14]
0x180055401  test    eax, eax
0x180055403  jz      short loc_180055409
0x180055405  cmp     eax, [rbx]
0x180055407  jbe     short loc_180055414
0x180055409  mov     eax, [rbx]
0x18005540b  shr     eax, 3
0x18005540e  imul    eax, 7
0x180055411  mov     [r14], eax
0x180055414  cmp     dword ptr [rsi], 0
0x180055417  jz      short loc_18005541D
0x180055419  cmp     [rsi], eax
0x18005541b  jbe     short loc_18005542F
0x18005541d  mov     eax, [rbx]
0x18005541f  shr     eax, 1
0x180055421  mov     [rsi], eax
0x180055423  mov     ecx, [r14]
0x180055426  cmp     eax, ecx
0x180055428  jbe     short loc_18005542F
0x18005542a  lea     eax, [rcx-1]
0x18005542d  mov     [rsi], eax
0x18005542f  mov     r8, qword ptr [rbp+var_2C+4]; lpMem
0x180055433  test    r8, r8
0x180055436  jz      short loc_18005544D
0x180055438  mov     rcx, cs:gDhcpHeap; hHeap
0x18005543f  xor     edx, edx; dwFlags
0x180055441  call    cs:__imp_HeapFree
0x180055448  nop     dword ptr [rax+rax+00h]
0x18005544d  mov     rbx, [rsp+60h+arg_0]
0x180055455  add     rsp, 60h
0x180055459  pop     r15
0x18005545b  pop     r14
0x18005545d  pop     r13
0x18005545f  pop     r12
0x180055461  pop     rdi
0x180055462  pop     rsi
0x180055463  pop     rbp
0x180055464  retn
```
