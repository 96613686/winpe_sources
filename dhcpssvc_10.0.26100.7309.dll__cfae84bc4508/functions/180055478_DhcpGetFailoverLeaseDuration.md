# DhcpGetFailoverLeaseDuration

- ea: `0x180055478`
- end: `0x180055752`
- name: `DhcpGetFailoverLeaseDuration`
- size: `730`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800559a8`
- `0x180058034`
- `0x180059550`
- `0x18005ad38`

## callees

- `0x18000323c`
- `0x18001e828`
- `0x180055478`
- `0x180057dcc`
- `0x18009f8f4`
- `0x18009fac4`

## import_xrefs

- `msvcrt!time` at `0x1800555d9`
- `msvcrt!time` at `0x180055685`
- `msvcrt!time` at `0x1800555d9`
- `msvcrt!time` at `0x180055685`
- `ADVAPI32!RegCloseKey` at `0x180055527`
- `ADVAPI32!RegCloseKey` at `0x180055527`
- `ADVAPI32!RegOpenKeyExW` at `0x1800554f0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800554f0`
- `WS2_32!__imp_ntohl` at `0x1800555b3`
- `WS2_32!__imp_ntohl` at `0x1800555b3`
- `KERNEL32!HeapFree` at `0x18005572d`
- `KERNEL32!HeapFree` at `0x18005572d`

## string_xrefs

- `0x1800554ad`: `System\CurrentControlSet\Services\DhcpServer\Parameters`

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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_079646765da4361deec0b4ab82b940ea_Traceguids);
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
0x180055478  mov     [rsp-38h+arg_0], rbx
0x18005547d  mov     [rsp-38h+arg_18], r9
0x180055482  mov     [rsp-38h+arg_8], edx
0x180055486  push    rbp
0x180055487  push    rsi
0x180055488  push    rdi
0x180055489  push    r12
0x18005548b  push    r13
0x18005548d  push    r14
0x18005548f  push    r15
0x180055491  mov     rbp, rsp
0x180055494  sub     rsp, 60h
0x180055498  xor     esi, esi
0x18005549a  mov     [rbp+var_10], 4
0x1800554a1  lea     rax, [rbp+arg_8]
0x1800554a5  mov     qword ptr [rbp+var_2C+4], rsi
0x1800554a9  mov     [rbp+var_18], rax
0x1800554ad  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Dh"...
0x1800554b4  mov     rbx, r8
0x1800554b7  mov     dword ptr [rbp+var_2C], esi
0x1800554ba  mov     r13, rcx
0x1800554bd  mov     [rbp+arg_10], esi
0x1800554c0  lea     rax, [rbp+hKey]
0x1800554c4  mov     [rbp+hKey], rsi
0x1800554c8  lea     r14d, [rsi+1]
0x1800554cc  mov     [rbp+var_30], esi
0x1800554cf  mov     r9d, 20019h; samDesired
0x1800554d5  mov     [rbp+var_C], r14d
0x1800554d9  xor     r8d, r8d; ulOptions
0x1800554dc  mov     [rsp+60h+phkResult], rax; phkResult
0x1800554e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800554e8  mov     edi, esi
0x1800554ea  mov     r12d, esi
0x1800554ed  mov     r15d, esi
0x1800554f0  call    cs:__imp_RegOpenKeyExW
0x1800554f7  nop     dword ptr [rax+rax+00h]
0x1800554fc  test    eax, eax
0x1800554fe  jnz     short loc_180055533
0x180055500  mov     rcx, [rbp+hKey]; hKey
0x180055504  lea     r9, [rbp+var_30]
0x180055508  lea     r8d, [rsi+4]
0x18005550c  lea     rdx, aEnablerenewreb; "EnableRenewRebindOptions"
0x180055513  call    DhcpRegGetValue
0x180055518  test    eax, eax
0x18005551a  jnz     short loc_180055523
0x18005551c  cmp     [rbp+var_30], esi
0x18005551f  cmovnz  r15d, r14d
0x180055523  mov     rcx, [rbp+hKey]; hKey
0x180055527  call    cs:__imp_RegCloseKey
0x18005552e  nop     dword ptr [rax+rax+00h]
0x180055533  mov     r14, [rbp+arg_28]
0x180055537  xor     eax, eax
0x180055539  mov     rsi, [rbp+arg_20]
0x18005553d  cmp     [r13+90h], rax
0x180055544  jz      short loc_18005556D
0x180055546  mov     [rsp+60h+phkResult], rax; __int64
0x18005554b  lea     rdx, [rbp+arg_10]
0x18005554f  mov     rcx, r13; int
0x180055552  test    r15d, r15d
0x180055555  jnz     short loc_18005555F
0x180055557  xor     r9d, r9d
0x18005555a  xor     r8d, r8d
0x18005555d  jmp     short loc_180055565
0x18005555f  mov     r9, r14
0x180055562  mov     r8, rsi
0x180055565  call    GetLeaseInfo
0x18005556a  mov     edi, [rbp+arg_10]
0x18005556d  mov     r8, cs:DhcpGlobalClientTable
0x180055574  lea     r9, [rbp+var_18]
0x180055578  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18005557f  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180055586  mov     dword ptr [rsp+60h+phkResult], 1; int
0x18005558e  mov     r8, [r8]
0x180055591  call    DhcpDALJetOpenKey
0x180055596  test    eax, eax
0x180055598  jz      short loc_180055614
0x18005559a  mov     rax, [r13+58h]
0x18005559e  mov     r8d, [rax+10D0h]
0x1800555a5  mov     [rbx], r8d
0x1800555a8  mov     rcx, [rbp+arg_30]
0x1800555ac  test    rcx, rcx
0x1800555af  jz      short loc_1800555CC
0x1800555b1  mov     ecx, [rcx]; netlong
0x1800555b3  call    cs:__imp_ntohl
0x1800555ba  nop     dword ptr [rax+rax+00h]
0x1800555bf  mov     r8d, [rbx]
0x1800555c2  cmp     r8d, eax
0x1800555c5  jbe     short loc_1800555CC
0x1800555c7  mov     r8d, eax
0x1800555ca  mov     [rbx], eax
0x1800555cc  shr     r8d, 1
0x1800555cf  add     edi, r8d
0x1800555d2  cmp     edi, r8d
0x1800555d5  jb      short loc_1800555EC
0x1800555d7  xor     ecx, ecx; Time
0x1800555d9  call    cs:__imp_time
0x1800555e0  nop     dword ptr [rax+rax+00h]
0x1800555e5  lea     ecx, [rax+rdi]
0x1800555e8  cmp     ecx, eax
0x1800555ea  jnb     short loc_1800555EF
0x1800555ec  or      ecx, 0FFFFFFFFh
0x1800555ef  mov     rax, [rbp+arg_18]
0x1800555f3  mov     [rax], ecx
0x1800555f5  test    r15d, r15d
0x1800555f8  jnz     loc_1800556EA
0x1800555fe  mov     eax, [rbx]
0x180055600  shr     eax, 1
0x180055602  mov     [rsi], eax
0x180055604  mov     eax, [rbx]
0x180055606  shr     eax, 3
0x180055609  imul    eax, 7
0x18005560c  mov     [r14], eax
0x18005560f  jmp     loc_18005571B
0x180055614  mov     r8, cs:DhcpGlobalClientTable
0x18005561b  lea     rax, [rbp+var_2C]
0x18005561f  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x180055626  lea     r9, [rbp+var_2C+4]
0x18005562a  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180055631  mov     [rsp+60h+phkResult], rax; __int64
0x180055636  mov     r8d, [r8+0E8h]; columnid
0x18005563d  call    DhcpDALJetGetValue
0x180055642  test    eax, eax
0x180055644  jz      short loc_180055674
0x180055646  mov     rcx, cs:WPP_GLOBAL_Control
0x18005564d  lea     rax, WPP_GLOBAL_Control
0x180055654  cmp     rcx, rax
0x180055657  jz      short loc_180055674
0x180055659  test    byte ptr [rcx+1Ch], 10h
0x18005565d  jz      short loc_180055674
0x18005565f  mov     rcx, [rcx+10h]
0x180055663  lea     r8, WPP_079646765da4361deec0b4ab82b940ea_Traceguids
0x18005566a  mov     edx, 82h
0x18005566f  call    WPP_SF_
0x180055674  mov     r8, qword ptr [rbp+var_2C+4]
0x180055678  test    r8, r8
0x18005567b  jz      short loc_180055683
0x18005567d  cmp     dword ptr [r8], 0FFFFFFFFh
0x180055681  jz      short loc_1800556E0
0x180055683  xor     ecx, ecx; Time
0x180055685  call    cs:__imp_time
0x18005568c  nop     dword ptr [rax+rax+00h]
0x180055691  mov     r8, qword ptr [rbp+var_2C+4]
0x180055695  xor     ecx, ecx
0x180055697  test    r8, r8
0x18005569a  jz      short loc_1800556B8
0x18005569c  cmp     [r8], eax
0x18005569f  jb      short loc_1800556A8
0x1800556a1  mov     ecx, [r8]
0x1800556a4  sub     ecx, eax
0x1800556a6  jmp     short loc_1800556AB
0x1800556a8  or      ecx, 0FFFFFFFFh
0x1800556ab  cmp     [r8], eax
0x1800556ae  sbb     r12d, r12d
0x1800556b1  and     r12d, 80070216h
0x1800556b8  mov     rax, [r13+58h]
0x1800556bc  mov     edx, [rax+10D0h]
0x1800556c2  xor     eax, eax
0x1800556c4  test    r12d, r12d
0x1800556c7  cmovns  eax, ecx
0x1800556ca  or      r8d, 0FFFFFFFFh
0x1800556ce  lea     ecx, [rax+rdx]
0x1800556d1  cmp     ecx, edx
0x1800556d3  cmovnb  r8d, ecx
0x1800556d7  cmp     r8d, edi
0x1800556da  jb      loc_1800555A5
0x1800556e0  mov     [rbx], edi
0x1800556e2  mov     r8d, edi
0x1800556e5  jmp     loc_1800555A8
0x1800556ea  mov     eax, [r14]
0x1800556ed  test    eax, eax
0x1800556ef  jz      short loc_1800556F5
0x1800556f1  cmp     eax, [rbx]
0x1800556f3  jbe     short loc_180055700
0x1800556f5  mov     eax, [rbx]
0x1800556f7  shr     eax, 3
0x1800556fa  imul    eax, 7
0x1800556fd  mov     [r14], eax
0x180055700  cmp     dword ptr [rsi], 0
0x180055703  jz      short loc_180055709
0x180055705  cmp     [rsi], eax
0x180055707  jbe     short loc_18005571B
0x180055709  mov     eax, [rbx]
0x18005570b  shr     eax, 1
0x18005570d  mov     [rsi], eax
0x18005570f  mov     ecx, [r14]
0x180055712  cmp     eax, ecx
0x180055714  jbe     short loc_18005571B
0x180055716  lea     eax, [rcx-1]
0x180055719  mov     [rsi], eax
0x18005571b  mov     r8, qword ptr [rbp+var_2C+4]; lpMem
0x18005571f  test    r8, r8
0x180055722  jz      short loc_180055739
0x180055724  mov     rcx, cs:gDhcpHeap; hHeap
0x18005572b  xor     edx, edx; dwFlags
0x18005572d  call    cs:__imp_HeapFree
0x180055734  nop     dword ptr [rax+rax+00h]
0x180055739  mov     rbx, [rsp+60h+arg_0]
0x180055741  add     rsp, 60h
0x180055745  pop     r15
0x180055747  pop     r14
0x180055749  pop     r13
0x18005574b  pop     r12
0x18005574d  pop     rdi
0x18005574e  pop     rsi
0x18005574f  pop     rbp
0x180055750  retn
```
