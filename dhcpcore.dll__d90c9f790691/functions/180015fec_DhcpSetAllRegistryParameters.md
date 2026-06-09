# DhcpSetAllRegistryParameters

- ea: `0x180015fec`
- end: `0x18001644f`
- name: `DhcpSetAllRegistryParameters`
- size: `1123`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800205e4`
- `0x180020c4c`
- `0x1800221a8`
- `0x180025678`

## callees

- `0x180004c54`
- `0x1800057f0`
- `0x18000f51c`
- `0x1800127fc`
- `0x180014bd8`
- `0x180015fec`
- `0x18001cef0`
- `0x18004d310`
- `0x18004d4c0`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800160e7`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180016138`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180016189`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800161d5`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800160e7`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180016138`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180016189`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800161d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800163c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016403`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800163c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016403`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800162d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016300`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800163b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800162d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016300`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800163b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800160f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180016141`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180016192`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800161de`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800160f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180016141`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180016192`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800161de`

## pseudocode

```c
__int64 __fastcall DhcpSetAllRegistryParameters(__int64 a1, int a2)
{
  __int64 v4; // r14
  int v5; // esi
  int v6; // r14d
  int v7; // ebx
  __int64 v8; // r14
  int v9; // r14d
  int v10; // ebx
  __int64 v11; // r14
  int v12; // r14d
  int v13; // ebx
  __int64 v14; // r14
  int v15; // esi
  __int64 v16; // r9
  HKEY v17; // r8
  void *v18; // rdx
  LSTATUS v19; // r14d
  unsigned int v20; // r13d
  HKEY AltKey; // rsi
  __int64 v22; // r15
  __int64 v23; // rbx
  int v24; // r8d
  BYTE **v25; // rbx
  BYTE *v26; // rcx
  unsigned int lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+28h] [rbp-D8h]
  int v30; // [rsp+30h] [rbp-D0h] BYREF
  BYTE *v31; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpValueName; // [rsp+40h] [rbp-C0h]
  int v33; // [rsp+48h] [rbp-B8h] BYREF
  int v34; // [rsp+4Ch] [rbp-B4h]
  const WCHAR *v35; // [rsp+50h] [rbp-B0h]
  int v36; // [rsp+58h] [rbp-A8h]
  int v37; // [rsp+5Ch] [rbp-A4h]
  const WCHAR *v38; // [rsp+60h] [rbp-A0h]
  int v39; // [rsp+68h] [rbp-98h]
  int v40; // [rsp+6Ch] [rbp-94h]
  const wchar_t *v41; // [rsp+70h] [rbp-90h]
  int v42; // [rsp+78h] [rbp-88h]
  int v43; // [rsp+7Ch] [rbp-84h]
  const WCHAR *v44; // [rsp+80h] [rbp-80h]
  int v45; // [rsp+88h] [rbp-78h]
  int v46; // [rsp+8Ch] [rbp-74h]
  const wchar_t *v47; // [rsp+90h] [rbp-70h]
  int v48; // [rsp+98h] [rbp-68h]
  int v49; // [rsp+9Ch] [rbp-64h]
  const wchar_t *v50; // [rsp+A0h] [rbp-60h]
  int v51; // [rsp+A8h] [rbp-58h]
  int v52; // [rsp+ACh] [rbp-54h]
  const WCHAR *v53; // [rsp+B0h] [rbp-50h]
  int v54; // [rsp+B8h] [rbp-48h]
  int v55; // [rsp+BCh] [rbp-44h]
  __int64 v56; // [rsp+C0h] [rbp-40h]
  __int64 v57; // [rsp+C8h] [rbp-38h]
  const wchar_t *v58; // [rsp+D0h] [rbp-30h]
  int v59; // [rsp+D8h] [rbp-28h]
  int v60; // [rsp+DCh] [rbp-24h]
  const wchar_t *v61; // [rsp+E0h] [rbp-20h]
  int v62; // [rsp+E8h] [rbp-18h]
  int v63; // [rsp+ECh] [rbp-14h]
  const WCHAR *v64; // [rsp+F0h] [rbp-10h]
  int v65; // [rsp+F8h] [rbp-8h]
  int v66; // [rsp+FCh] [rbp-4h]

  v31 = 0;
  v30 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 53, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *(_QWORD *)(a1 + 24));
  v4 = *(_QWORD *)(a1 + 448);
  lpValueName = L"DhcpIPAddress";
  v5 = -1;
  v33 = *(_DWORD *)(a1 + 120);
  v35 = L"DhcpSubnetMask";
  v36 = *(_DWORD *)(a1 + 124);
  v38 = L"DhcpServer";
  v41 = L"Lease";
  v42 = *(_DWORD *)(a1 + 440);
  v44 = L"LeaseObtainedTime";
  v34 = 1;
  v37 = 1;
  v39 = a2;
  v40 = 1;
  v43 = 4;
  if ( v4 == 0xFFFFFFFFLL )
  {
    v6 = -1;
  }
  else
  {
    v7 = _time64(0);
    v6 = v7 + v4 - GetTickCount64() / 0x3E8;
  }
  v45 = v6;
  v8 = *(_QWORD *)(a1 + 456);
  v46 = 4;
  v47 = L"T1";
  if ( v8 == 0xFFFFFFFFLL )
  {
    v9 = -1;
  }
  else
  {
    v10 = _time64(0);
    v9 = v10 + v8 - GetTickCount64() / 0x3E8;
  }
  v48 = v9;
  v11 = *(_QWORD *)(a1 + 464);
  v49 = 4;
  v50 = L"T2";
  if ( v11 == 0xFFFFFFFFLL )
  {
    v12 = -1;
  }
  else
  {
    v13 = _time64(0);
    v12 = v13 + v11 - GetTickCount64() / 0x3E8;
  }
  v51 = v12;
  v14 = *(_QWORD *)(a1 + 472);
  v52 = 4;
  v53 = L"LeaseTerminatesTime";
  if ( v14 != 0xFFFFFFFFLL )
  {
    v15 = _time64(0);
    v5 = v14 - GetTickCount64() / 0x3E8 + v15;
  }
  v54 = v5;
  v58 = L"AddressType";
  v16 = *(_QWORD *)(a1 + 736);
  v17 = *(HKEY *)(a1 + 728);
  v18 = *(void **)(a1 + 56);
  v59 = *(_DWORD *)(a1 + 796);
  v61 = L"IsServerNapAware";
  v62 = *(_DWORD *)(a1 + 840);
  v64 = L"DhcpConnForceBroadcastFlag";
  v65 = *(_DWORD *)(a1 + 848);
  cbData = *(_DWORD *)(a1 + 152);
  lpData = *(_DWORD *)(a1 + 744);
  v55 = 4;
  v56 = 0;
  v57 = 0;
  v60 = 4;
  v63 = 4;
  v66 = 4;
  v19 = DhcpRegSaveOptions((_QWORD *)(a1 + 696), v18, v17, v16, lpData, cbData);
  v20 = 0;
  AltKey = DhcpRegGetAltKey(*(void **)(a1 + 56));
  v22 = 0;
  v23 = 0;
  do
  {
    v24 = *(int *)((char *)&v34 + v23 * 8);
    if ( v24 == 4 )
    {
      v19 = RegSetValueExW(*(HKEY *)(a1 + 728), (&lpValueName)[v23], 0, 4u, (const BYTE *)&v33 + v23 * 8, 4u);
      if ( AltKey )
        RegSetValueExW(AltKey, (&lpValueName)[v23], 0, 4u, (const BYTE *)&v33 + v23 * 8, 4u);
    }
    else if ( v24 )
    {
      v19 = RegSetIpAddress(*(HKEY *)(a1 + 728));
      if ( AltKey )
        RegSetIpAddress(AltKey);
    }
    else if ( AltKey )
    {
      RegCloseKey(AltKey);
      AltKey = 0;
    }
    if ( v19 )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_SD(
          1025,
          54,
          (unsigned int)WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids,
          (unsigned int)(&lpValueName)[v23],
          v19);
      v20 = v19;
    }
    ++v22;
    v23 += 2;
  }
  while ( v22 != 12 );
  if ( *(_DWORD *)&DhcpGlobalUseNetworkHint )
  {
    v25 = (BYTE **)(a1 + 1888);
    if ( *(_QWORD *)(a1 + 1888) )
    {
      DhcpPunycodeFree((LPVOID *)(a1 + 1888));
      *v25 = 0;
    }
    GetNetworkHint(*(_QWORD *)(a1 + 24), &v31, &v30, 0);
    v26 = v31;
    *v25 = v31;
    if ( v26 )
      RegSetValueExW(*(HKEY *)(a1 + 728), L"DhcpNetworkHint", 0, 1u, v26, 2 * v30);
  }
  if ( AltKey )
    RegCloseKey(AltKey);
  return v20;
}

```

## disassembly

```asm
0x180015fec  mov     [rsp-8+arg_10], rbx
0x180015ff1  push    rbp
0x180015ff2  push    rsi
0x180015ff3  push    rdi
0x180015ff4  push    r12
0x180015ff6  push    r13
0x180015ff8  push    r14
0x180015ffa  push    r15
0x180015ffc  lea     rbp, [rsp-10h]
0x180016001  sub     rsp, 110h
0x180016008  mov     rax, cs:__security_cookie
0x18001600f  xor     rax, rsp
0x180016012  mov     [rbp+40h+var_40], rax
0x180016016  xor     r12d, r12d
0x180016019  mov     ebx, edx
0x18001601b  mov     [rsp+140h+var_108], r12
0x180016020  mov     rdi, rcx
0x180016023  mov     [rsp+140h+var_110], r12d
0x180016028  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001602f  jz      short loc_18001604B
0x180016031  mov     r9, [rdi+18h]
0x180016035  lea     edx, [r12+35h]
0x18001603a  mov     ecx, 404h
0x18001603f  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180016046  call    WPP_SF_q
0x18001604b  mov     r14, [rdi+1C0h]
0x180016052  lea     rax, aDhcpipaddress; "DhcpIPAddress"
0x180016059  mov     [rsp+140h+lpValueName], rax
0x18001605e  mov     esi, 0FFFFFFFFh
0x180016063  mov     eax, [rdi+78h]
0x180016066  mov     r15d, 4
0x18001606c  mov     [rsp+140h+var_F8], eax
0x180016070  lea     rax, aDhcpsubnetmask_0; "DhcpSubnetMask"
0x180016077  mov     [rsp+140h+var_F0], rax
0x18001607c  mov     r13, 624DD2F1A9FBE77h
0x180016086  mov     eax, [rdi+7Ch]
0x180016089  mov     [rsp+140h+var_E8], eax
0x18001608d  lea     rax, aDhcpserver; "DhcpServer"
0x180016094  mov     [rsp+140h+var_E0], rax
0x180016099  lea     rax, aLease; "Lease"
0x1800160a0  mov     [rsp+140h+var_D0], rax
0x1800160a5  mov     eax, [rdi+1B8h]
0x1800160ab  mov     [rsp+140h+var_C8], eax
0x1800160af  lea     rax, aLeaseobtainedt; "LeaseObtainedTime"
0x1800160b6  mov     [rbp+40h+var_C0], rax
0x1800160ba  mov     [rsp+140h+var_F4], 1
0x1800160c2  mov     [rsp+140h+var_E4], 1
0x1800160ca  mov     [rsp+140h+var_D8], ebx
0x1800160ce  mov     [rsp+140h+var_D4], 1
0x1800160d6  mov     [rsp+140h+var_C4], r15d
0x1800160db  cmp     r14, rsi
0x1800160de  jnz     short loc_1800160E5
0x1800160e0  mov     r14d, esi
0x1800160e3  jmp     short loc_180016112
0x1800160e5  xor     ecx, ecx; Time
0x1800160e7  call    cs:__imp__time64
0x1800160ed  mov     rbx, rax
0x1800160f0  call    cs:__imp_GetTickCount64
0x1800160f6  mov     rcx, rax
0x1800160f9  mov     rax, r13
0x1800160fc  mul     rcx
0x1800160ff  sub     rcx, rdx
0x180016102  shr     rcx, 1
0x180016105  add     rcx, rdx
0x180016108  shr     rcx, 9
0x18001610c  sub     r14d, ecx
0x18001610f  add     r14d, ebx
0x180016112  mov     [rbp+40h+var_B8], r14d
0x180016116  lea     rax, aT1; "T1"
0x18001611d  mov     r14, [rdi+1C8h]
0x180016124  mov     [rbp+40h+var_B4], r15d
0x180016128  mov     [rbp+40h+var_B0], rax
0x18001612c  cmp     r14, rsi
0x18001612f  jnz     short loc_180016136
0x180016131  mov     r14d, esi
0x180016134  jmp     short loc_180016163
0x180016136  xor     ecx, ecx; Time
0x180016138  call    cs:__imp__time64
0x18001613e  mov     rbx, rax
0x180016141  call    cs:__imp_GetTickCount64
0x180016147  mov     rcx, rax
0x18001614a  mov     rax, r13
0x18001614d  mul     rcx
0x180016150  sub     rcx, rdx
0x180016153  shr     rcx, 1
0x180016156  add     rcx, rdx
0x180016159  shr     rcx, 9
0x18001615d  sub     r14d, ecx
0x180016160  add     r14d, ebx
0x180016163  mov     [rbp+40h+var_A8], r14d
0x180016167  lea     rax, aT2; "T2"
0x18001616e  mov     r14, [rdi+1D0h]
0x180016175  mov     [rbp+40h+var_A4], r15d
0x180016179  mov     [rbp+40h+var_A0], rax
0x18001617d  cmp     r14, rsi
0x180016180  jnz     short loc_180016187
0x180016182  mov     r14d, esi
0x180016185  jmp     short loc_1800161B4
0x180016187  xor     ecx, ecx; Time
0x180016189  call    cs:__imp__time64
0x18001618f  mov     rbx, rax
0x180016192  call    cs:__imp_GetTickCount64
0x180016198  mov     rcx, rax
0x18001619b  mov     rax, r13
0x18001619e  mul     rcx
0x1800161a1  sub     rcx, rdx
0x1800161a4  shr     rcx, 1
0x1800161a7  add     rcx, rdx
0x1800161aa  shr     rcx, 9
0x1800161ae  sub     r14d, ecx
0x1800161b1  add     r14d, ebx
0x1800161b4  mov     [rbp+40h+var_98], r14d
0x1800161b8  lea     rax, aLeaseterminate; "LeaseTerminatesTime"
0x1800161bf  mov     r14, [rdi+1D8h]
0x1800161c6  mov     [rbp+40h+var_94], r15d
0x1800161ca  mov     [rbp+40h+var_90], rax
0x1800161ce  cmp     r14, rsi
0x1800161d1  jz      short loc_180016200
0x1800161d3  xor     ecx, ecx; Time
0x1800161d5  call    cs:__imp__time64
0x1800161db  mov     rsi, rax
0x1800161de  call    cs:__imp_GetTickCount64
0x1800161e4  mov     rcx, rax
0x1800161e7  mov     rax, r13
0x1800161ea  mul     rcx
0x1800161ed  sub     rcx, rdx
0x1800161f0  shr     rcx, 1
0x1800161f3  add     rcx, rdx
0x1800161f6  shr     rcx, 9
0x1800161fa  sub     r14d, ecx
0x1800161fd  add     esi, r14d
0x180016200  lea     rax, aAddresstype; "AddressType"
0x180016207  mov     [rbp+40h+var_88], esi
0x18001620a  mov     [rbp+40h+var_70], rax
0x18001620e  lea     rcx, [rdi+2B8h]
0x180016215  mov     eax, [rdi+31Ch]
0x18001621b  mov     r9, [rdi+2E0h]
0x180016222  mov     r8, [rdi+2D8h]
0x180016229  mov     rdx, [rdi+38h]
0x18001622d  mov     [rbp+40h+var_68], eax
0x180016230  lea     rax, aIsservernapawa; "IsServerNapAware"
0x180016237  mov     [rbp+40h+var_60], rax
0x18001623b  mov     eax, [rdi+348h]
0x180016241  mov     [rbp+40h+var_58], eax
0x180016244  lea     rax, aDhcpconnforceb; "DhcpConnForceBroadcastFlag"
0x18001624b  mov     [rbp+40h+var_50], rax
0x18001624f  mov     eax, [rdi+350h]
0x180016255  mov     [rbp+40h+var_48], eax
0x180016258  mov     eax, [rdi+98h]
0x18001625e  mov     [rsp+140h+cbData], eax
0x180016262  mov     eax, [rdi+2E8h]
0x180016268  mov     dword ptr [rsp+140h+lpData], eax
0x18001626c  mov     [rbp+40h+var_84], r15d
0x180016270  mov     [rbp+40h+var_80], r12
0x180016274  mov     [rbp+40h+var_78], r12
0x180016278  mov     [rbp+40h+var_64], r15d
0x18001627c  mov     [rbp+40h+var_54], r15d
0x180016280  mov     [rbp+40h+var_44], r15d
0x180016284  call    DhcpRegSaveOptions
0x180016289  mov     rcx, [rdi+38h]; void *
0x18001628d  mov     r14d, eax
0x180016290  mov     r13d, r12d
0x180016293  call    DhcpRegGetAltKey
0x180016298  mov     rsi, rax
0x18001629b  mov     r15, r12
0x18001629e  mov     rbx, r12
0x1800162a1  mov     r8d, [rsp+rbx+140h+var_F4]
0x1800162a6  mov     eax, 4
0x1800162ab  cmp     r8d, eax
0x1800162ae  jnz     loc_1800163F2
0x1800162b4  mov     rdx, [rsp+rbx+140h+lpValueName]; lpValueName
0x1800162b9  lea     r12, [rsp+140h+var_F8]
0x1800162be  mov     rcx, [rdi+2D8h]; hKey
0x1800162c5  add     r12, rbx
0x1800162c8  mov     [rsp+140h+cbData], eax; cbData
0x1800162cc  mov     r9d, eax; dwType
0x1800162cf  xor     r8d, r8d; Reserved
0x1800162d2  mov     [rsp+140h+lpData], r12; lpData
0x1800162d7  call    cs:__imp_RegSetValueExW
0x1800162dd  mov     r14d, eax
0x1800162e0  test    rsi, rsi
0x1800162e3  jz      short loc_180016306
0x1800162e5  mov     rdx, [rsp+rbx+140h+lpValueName]; lpValueName
0x1800162ea  mov     r9d, 4; dwType
0x1800162f0  mov     [rsp+140h+cbData], r9d; cbData
0x1800162f5  xor     r8d, r8d; Reserved
0x1800162f8  mov     rcx, rsi; hKey
0x1800162fb  mov     [rsp+140h+lpData], r12; lpData
0x180016300  call    cs:__imp_RegSetValueExW
0x180016306  xor     r12d, r12d
0x180016309  test    r14d, r14d
0x18001630c  jz      short loc_18001633A
0x18001630e  test    byte ptr cs:xmmword_1800616A0, 2
0x180016315  jz      short loc_180016337
0x180016317  mov     r9, [rsp+rbx+140h+lpValueName]
0x18001631c  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180016323  mov     edx, 36h ; '6'
0x180016328  mov     dword ptr [rsp+140h+lpData], r14d
0x18001632d  mov     ecx, 401h
0x180016332  call    WPP_SF_SD
0x180016337  mov     r13d, r14d
0x18001633a  inc     r15
0x18001633d  add     rbx, 10h
0x180016341  cmp     r15, 0Ch
0x180016345  jnz     loc_1800162A1
0x18001634b  cmp     cs:DhcpGlobalUseNetworkHint, r12d
0x180016352  jz      short loc_1800163BA
0x180016354  lea     rbx, [rdi+760h]
0x18001635b  cmp     [rbx], r12
0x18001635e  jz      short loc_18001636B
0x180016360  mov     rcx, rbx
0x180016363  call    DhcpPunycodeFree
0x180016368  mov     [rbx], r12
0x18001636b  mov     rcx, [rdi+18h]
0x18001636f  lea     r8, [rsp+140h+var_110]
0x180016374  xor     r9d, r9d
0x180016377  lea     rdx, [rsp+140h+var_108]
0x18001637c  call    GetNetworkHint
0x180016381  mov     rcx, [rsp+140h+var_108]
0x180016386  mov     [rbx], rcx
0x180016389  test    rcx, rcx
0x18001638c  jz      short loc_1800163BA
0x18001638e  mov     eax, [rsp+140h+var_110]
0x180016392  lea     rdx, ValueName; "DhcpNetworkHint"
0x180016399  add     eax, eax
0x18001639b  mov     r9d, 1; dwType
0x1800163a1  mov     [rsp+140h+cbData], eax; cbData
0x1800163a5  xor     r8d, r8d; Reserved
0x1800163a8  mov     [rsp+140h+lpData], rcx; lpData
0x1800163ad  mov     rcx, [rdi+2D8h]; hKey
0x1800163b4  call    cs:__imp_RegSetValueExW
0x1800163ba  test    rsi, rsi
0x1800163bd  jz      short loc_1800163C8
0x1800163bf  mov     rcx, rsi; hKey
0x1800163c2  call    cs:__imp_RegCloseKey
0x1800163c8  mov     eax, r13d
0x1800163cb  mov     rcx, [rbp+40h+var_40]
0x1800163cf  xor     rcx, rsp; StackCookie
0x1800163d2  call    __security_check_cookie
0x1800163d7  mov     rbx, [rsp+140h+arg_10]
0x1800163df  add     rsp, 110h
0x1800163e6  pop     r15
0x1800163e8  pop     r14
0x1800163ea  pop     r13
0x1800163ec  pop     r12
0x1800163ee  pop     rdi
0x1800163ef  pop     rsi
0x1800163f0  pop     rbp
0x1800163f1  retn
0x1800163f2  test    r8d, r8d
0x1800163f5  jnz     short loc_180016411
0x1800163f7  test    rsi, rsi
0x1800163fa  jz      loc_180016309
0x180016400  mov     rcx, rsi; hKey
0x180016403  call    cs:__imp_RegCloseKey
0x180016409  mov     rsi, r12
0x18001640c  jmp     loc_180016309
0x180016411  mov     r9d, [rsp+rbx+140h+var_F8]
0x180016416  mov     rdx, [rsp+rbx+140h+lpValueName]
0x18001641b  mov     rcx, [rdi+2D8h]; hKey
0x180016422  call    RegSetIpAddress
0x180016427  mov     r14d, eax
0x18001642a  test    rsi, rsi
0x18001642d  jz      loc_180016309
0x180016433  mov     r9d, [rsp+rbx+140h+var_F8]
0x180016438  mov     rcx, rsi; hKey
0x18001643b  mov     r8d, [rsp+rbx+140h+var_F4]
0x180016440  mov     rdx, [rsp+rbx+140h+lpValueName]
0x180016445  call    RegSetIpAddress
0x18001644a  jmp     loc_180016309
```
