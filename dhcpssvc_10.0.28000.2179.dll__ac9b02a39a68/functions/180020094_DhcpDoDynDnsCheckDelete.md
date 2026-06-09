# DhcpDoDynDnsCheckDelete

- ea: `0x180020094`
- end: `0x180020600`
- name: `DhcpDoDynDnsCheckDelete`
- size: `1388`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800068e4`
- `0x1800083cc`
- `0x1800092e0`
- `0x1800503c8`
- `0x180051350`

## callees

- `0x18000282c`
- `0x180003228`
- `0x1800057e0`
- `0x18000c164`
- `0x18000e204`
- `0x18000e284`
- `0x18000e64c`
- `0x18000e7c0`
- `0x18001f248`
- `0x180020094`
- `0x180021fd4`
- `0x1800222bc`
- `0x18008f0b4`
- `0x180098a40`
- `0x1800cdac0`

## import_xrefs

- `WS2_32!__imp_inet_ntoa` at `0x18002011c`
- `WS2_32!__imp_inet_ntoa` at `0x1800201af`
- `WS2_32!__imp_inet_ntoa` at `0x1800204dd`
- `WS2_32!__imp_inet_ntoa` at `0x18002011c`
- `WS2_32!__imp_inet_ntoa` at `0x1800201af`
- `WS2_32!__imp_inet_ntoa` at `0x1800204dd`
- `KERNEL32!CompareFileTime` at `0x18002044f`
- `KERNEL32!CompareFileTime` at `0x18002044f`
- `KERNEL32!HeapFree` at `0x1800202e2`
- `KERNEL32!HeapFree` at `0x180020308`
- `KERNEL32!HeapFree` at `0x1800202e2`
- `KERNEL32!HeapFree` at `0x180020308`

## pseudocode

```c
__int64 __fastcall DhcpDoDynDnsCheckDelete(struct in_addr a1)
{
  __int64 v1; // rbx
  char *v2; // rax
  unsigned int Value; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  char v7; // di
  __int64 v8; // rbx
  char *v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  LPVOID v12; // r8
  unsigned int v13; // ebx
  unsigned int v14; // eax
  char v15; // bl
  __int64 v16; // rdi
  unsigned int v17; // eax
  int v18; // edx
  int v19; // r8d
  unsigned __int64 v21; // rbx
  _BYTE pvData[4]; // [rsp+30h] [rbp-50h] BYREF
  unsigned int pcbActual; // [rsp+34h] [rbp-4Ch] BYREF
  struct in_addr in; // [rsp+38h] [rbp-48h] BYREF
  int v25; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v26; // [rsp+44h] [rbp-3Ch] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-38h] BYREF
  LPVOID v28; // [rsp+50h] [rbp-30h] BYREF
  FILETIME FileTime1; // [rsp+58h] [rbp-28h] BYREF
  FILETIME FileTime2; // [rsp+60h] [rbp-20h] BYREF
  __int64 S_addr; // [rsp+68h] [rbp-18h] BYREF
  char v32; // [rsp+70h] [rbp-10h]

  in = a1;
  pvData[0] = 0;
  v25 = 0;
  lpMem = 0;
  v26 = 0;
  v28 = 0;
  if ( DhcpGlobalUseNoDns )
    return 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
  {
    v1 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v2 = inet_ntoa(a1);
    WPP_SF_s(v1, 16, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids, v2);
  }
  pcbActual = 1;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), pvData, &pcbActual);
  if ( Value )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 1;
    v5 = 17;
    goto LABEL_9;
  }
  v7 = pvData[0];
  if ( (pvData[0] & 0x10) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v9 = inet_ntoa(in);
      WPP_SF_s(v8, 18, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids, v9);
    }
    return 1;
  }
  pcbActual = 4;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 360), &v25, &pcbActual);
  if ( Value )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 1;
    v5 = 19;
    goto LABEL_9;
  }
  pcbActual = 0;
  if ( (unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 72), &lpMem, &pcbActual) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 1;
    v11 = 20;
    goto LABEL_66;
  }
  if ( (unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 24), &v28, &v26) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 1;
    v11 = 22;
    goto LABEL_66;
  }
  pvData[0] |= 3u;
  DhcpDnsAsyncDelete(in, (STRSAFE_LPCWSTR)lpMem, (__int64)v28, v25 & 1);
  if ( lpMem )
    HeapFree(gDhcpHeap, 0, lpMem);
  v12 = v28;
  lpMem = 0;
  if ( v28 )
    HeapFree(gDhcpHeap, 0, v28);
  pvData[0] |= 0xC0u;
  Value = DhcpJetPrepareUpdate(*(_QWORD *)DhcpGlobalClientTable, &in, (__int64)v12, 0);
  if ( Value )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 1;
    v5 = 23;
LABEL_9:
    v6 = Value;
LABEL_71:
    WPP_SF_D(v4[2], v5, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids, v6);
    return 1;
  }
  pcbActual = 1;
  v13 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), pvData, 1u);
  if ( !(unsigned int)MemServerIsReservedAddress(DhcpGlobalThisServer, in.S_un.S_addr) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids);
    v32 = 0;
    S_addr = in.S_un.S_addr;
    pcbActual = 9;
    v13 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 24), &S_addr, 9u);
    goto LABEL_42;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids);
LABEL_42:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v7 < 0 )
  {
    FileTime1 = (FILETIME)DhcpGetDateTime();
    FileTime2 = 0;
    pcbActual = 8;
    v13 = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 88), &FileTime2, &pcbActual);
    if ( v13 )
    {
LABEL_67:
      v4 = WPP_GLOBAL_Control;
LABEL_68:
      if ( v4 == &WPP_GLOBAL_Control || (*((_BYTE *)v4 + 28) & 0x10) == 0 )
        return 1;
      v5 = 30;
      v6 = v13;
      goto LABEL_71;
    }
    if ( CompareFileTime(&FileTime1, &FileTime2) >= 0 )
    {
      v21 = (*(_QWORD *)&FileTime1 - *(_QWORD *)&FileTime2) / 0x3E8uLL;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        {
          WPP_SF_dD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids,
            (unsigned int)v21,
            ((*(_QWORD *)&FileTime1 - *(_QWORD *)&FileTime2) / 0x3E8uLL) >> 32);
          v10 = WPP_GLOBAL_Control;
        }
        if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x40000) != 0 )
        {
          WPP_SF_q(v10[2], 28, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids, 1728000000);
          v10 = WPP_GLOBAL_Control;
        }
      }
      if ( v21 >= 0x66FF3000 )
      {
        if ( v10 == &WPP_GLOBAL_Control || (*((_DWORD *)v10 + 7) & 0x40000) == 0 )
          return 1;
        v11 = 29;
LABEL_66:
        WPP_SF_(v10[2], v11, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids);
        return 1;
      }
      goto LABEL_51;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids);
    }
    v14 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 88), &FileTime1, 8u);
    v4 = WPP_GLOBAL_Control;
    v13 = v14;
  }
  if ( v13 )
    goto LABEL_68;
LABEL_51:
  v13 = DhcpJetCommitUpdate();
  if ( v13 )
    goto LABEL_67;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
  {
    v15 = pvData[0];
    v16 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v17 = (unsigned int)inet_ntoa(in);
    WPP_SF_sD(v16, v18, v19, v17, v15);
  }
  return 0;
}

```

## disassembly

```asm
0x180020094  mov     [rsp-18h+arg_8], rbx
0x180020099  mov     [rsp-18h+arg_10], rdi
0x18002009e  mov     [rsp-18h+arg_18], r13
0x1800200a3  push    rbp
0x1800200a4  push    r14
0x1800200a6  push    r15
0x1800200a8  mov     rbp, rsp
0x1800200ab  sub     rsp, 80h
0x1800200b2  mov     rax, cs:__security_cookie
0x1800200b9  xor     rax, rsp
0x1800200bc  mov     [rbp+var_8], rax
0x1800200c0  cmp     cs:DhcpGlobalUseNoDns, 0
0x1800200c7  mov     dword ptr [rbp+in.S_un], ecx
0x1800200ca  mov     [rbp+pvData], 0
0x1800200ce  mov     [rbp+var_40], 0
0x1800200d5  mov     [rbp+lpMem], 0
0x1800200dd  mov     [rbp+var_3C], 0
0x1800200e4  mov     [rbp+var_30], 0
0x1800200ec  jnz     loc_1800205D1
0x1800200f2  mov     rbx, cs:WPP_GLOBAL_Control
0x1800200f9  lea     r14, WPP_GLOBAL_Control
0x180020100  lea     r15, WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids
0x180020107  mov     r13d, 40000h
0x18002010d  cmp     rbx, r14
0x180020110  jz      short loc_18002013B
0x180020112  test    [rbx+1Ch], r13d
0x180020116  jz      short loc_18002013B
0x180020118  mov     rbx, [rbx+10h]
0x18002011c  call    cs:__imp_inet_ntoa
0x180020123  nop     dword ptr [rax+rax+00h]
0x180020128  mov     edx, 10h
0x18002012d  mov     r8, r15
0x180020130  mov     r9, rax
0x180020133  mov     rcx, rbx
0x180020136  call    WPP_SF_s
0x18002013b  mov     rcx, cs:DhcpGlobalClientTable
0x180020142  lea     r8, [rbp+pcbActual]; pcbActual
0x180020146  mov     [rbp+pcbActual], 1
0x18002014d  lea     rdx, [rbp+pvData]; pvData
0x180020151  mov     ecx, [rcx+28h]; columnid
0x180020154  call    DhcpJetGetValue
0x180020159  test    eax, eax
0x18002015b  jz      short loc_180020184
0x18002015d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020164  cmp     rcx, r14
0x180020167  jz      loc_1800205D1
0x18002016d  test    byte ptr [rcx+1Ch], 10h
0x180020171  jz      loc_1800205D1
0x180020177  mov     edx, 11h
0x18002017c  mov     r9d, eax
0x18002017f  jmp     loc_1800205C5
0x180020184  mov     dil, [rbp+pvData]
0x180020188  test    dil, 10h
0x18002018c  jnz     short loc_1800201D3
0x18002018e  mov     rbx, cs:WPP_GLOBAL_Control
0x180020195  cmp     rbx, r14
0x180020198  jz      loc_1800205D1
0x18002019e  test    [rbx+1Ch], r13d
0x1800201a2  jz      loc_1800205D1
0x1800201a8  mov     ecx, dword ptr [rbp+in.S_un]; in
0x1800201ab  mov     rbx, [rbx+10h]
0x1800201af  call    cs:__imp_inet_ntoa
0x1800201b6  nop     dword ptr [rax+rax+00h]
0x1800201bb  mov     edx, 12h
0x1800201c0  mov     r8, r15
0x1800201c3  mov     r9, rax
0x1800201c6  mov     rcx, rbx
0x1800201c9  call    WPP_SF_s
0x1800201ce  jmp     loc_1800205D1
0x1800201d3  mov     rcx, cs:DhcpGlobalClientTable
0x1800201da  lea     r8, [rbp+pcbActual]; pcbActual
0x1800201de  mov     [rbp+pcbActual], 4
0x1800201e5  lea     rdx, [rbp+var_40]; pvData
0x1800201e9  mov     ecx, [rcx+168h]; columnid
0x1800201ef  call    DhcpJetGetValue
0x1800201f4  test    eax, eax
0x1800201f6  jz      short loc_18002021C
0x1800201f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201ff  cmp     rcx, r14
0x180020202  jz      loc_1800205D1
0x180020208  test    byte ptr [rcx+1Ch], 10h
0x18002020c  jz      loc_1800205D1
0x180020212  mov     edx, 13h
0x180020217  jmp     loc_18002017C
0x18002021c  mov     rcx, cs:DhcpGlobalClientTable
0x180020223  lea     r8, [rbp+pcbActual]; pcbActual
0x180020227  mov     [rbp+pcbActual], 0
0x18002022e  lea     rdx, [rbp+lpMem]; pvData
0x180020232  mov     ecx, [rcx+48h]; columnid
0x180020235  call    DhcpJetGetValue
0x18002023a  test    eax, eax
0x18002023c  jz      short loc_180020262
0x18002023e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020245  cmp     rcx, r14
0x180020248  jz      loc_1800205D1
0x18002024e  test    byte ptr [rcx+1Ch], 10h
0x180020252  jz      loc_1800205D1
0x180020258  mov     edx, 14h
0x18002025d  jmp     loc_18002059D
0x180020262  mov     rcx, cs:DhcpGlobalClientTable
0x180020269  lea     r8, [rbp+var_3C]; pcbActual
0x18002026d  lea     rdx, [rbp+var_30]; pvData
0x180020271  mov     ecx, [rcx+18h]; columnid
0x180020274  call    DhcpJetGetValue
0x180020279  test    eax, eax
0x18002027b  jz      short loc_1800202A1
0x18002027d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020284  cmp     rcx, r14
0x180020287  jz      loc_1800205D1
0x18002028d  test    byte ptr [rcx+1Ch], 10h
0x180020291  jz      loc_1800205D1
0x180020297  mov     edx, 16h
0x18002029c  jmp     loc_18002059D
0x1800202a1  mov     eax, [rbp+var_40]
0x1800202a4  mov     r8b, [rbp+pvData]
0x1800202a8  and     eax, 1
0x1800202ab  mov     r9d, [rbp+var_3C]
0x1800202af  or      r8b, 3
0x1800202b3  mov     rdx, [rbp+lpMem]; pszSrc
0x1800202b7  mov     ecx, dword ptr [rbp+in.S_un]; in
0x1800202ba  mov     [rsp+80h+var_58], eax; int
0x1800202be  mov     rax, [rbp+var_30]
0x1800202c2  mov     [rsp+80h+var_60], rax; __int64
0x1800202c7  mov     [rbp+pvData], r8b
0x1800202cb  call    DhcpDnsAsyncDelete
0x1800202d0  mov     r8, [rbp+lpMem]; lpMem
0x1800202d4  test    r8, r8
0x1800202d7  jz      short loc_1800202EE
0x1800202d9  mov     rcx, cs:gDhcpHeap; hHeap
0x1800202e0  xor     edx, edx; dwFlags
0x1800202e2  call    cs:__imp_HeapFree
0x1800202e9  nop     dword ptr [rax+rax+00h]
0x1800202ee  mov     r8, [rbp+var_30]; lpMem
0x1800202f2  mov     [rbp+lpMem], 0
0x1800202fa  test    r8, r8
0x1800202fd  jz      short loc_180020314
0x1800202ff  mov     rcx, cs:gDhcpHeap; hHeap
0x180020306  xor     edx, edx; dwFlags
0x180020308  call    cs:__imp_HeapFree
0x18002030f  nop     dword ptr [rax+rax+00h]
0x180020314  mov     rcx, cs:DhcpGlobalClientTable
0x18002031b  lea     rdx, [rbp+in]
0x18002031f  or      [rbp+pvData], 0C0h
0x180020323  xor     r9d, r9d
0x180020326  mov     rcx, [rcx]
0x180020329  call    DhcpJetPrepareUpdate
0x18002032e  test    eax, eax
0x180020330  jz      short loc_180020356
0x180020332  mov     rcx, cs:WPP_GLOBAL_Control
0x180020339  cmp     rcx, r14
0x18002033c  jz      loc_1800205D1
0x180020342  test    byte ptr [rcx+1Ch], 10h
0x180020346  jz      loc_1800205D1
0x18002034c  mov     edx, 17h
0x180020351  jmp     loc_18002017C
0x180020356  mov     rcx, cs:DhcpGlobalClientTable
0x18002035d  lea     rdx, [rbp+pvData]; pvData
0x180020361  mov     eax, 1
0x180020366  mov     [rbp+pcbActual], eax
0x180020369  mov     r8d, eax; cbData
0x18002036c  mov     ecx, [rcx+28h]; columnid
0x18002036f  call    DhcpJetSetValue
0x180020374  mov     edx, dword ptr [rbp+in.S_un]
0x180020377  mov     ebx, eax
0x180020379  mov     rcx, cs:DhcpGlobalThisServer
0x180020380  call    MemServerIsReservedAddress
0x180020385  test    eax, eax
0x180020387  jnz     short loc_1800203DA
0x180020389  mov     rcx, cs:WPP_GLOBAL_Control
0x180020390  cmp     rcx, r14
0x180020393  jz      short loc_1800203AA
0x180020395  test    [rcx+1Ch], r13d
0x180020399  jz      short loc_1800203AA
0x18002039b  mov     rcx, [rcx+10h]
0x18002039f  lea     edx, [rax+18h]
0x1800203a2  mov     r8, r15
0x1800203a5  call    WPP_SF_
0x1800203aa  mov     rcx, cs:DhcpGlobalClientTable
0x1800203b1  lea     rdx, [rbp+var_18]; pvData
0x1800203b5  xor     eax, eax
0x1800203b7  mov     r8d, 9; cbData
0x1800203bd  mov     [rbp+var_18], rax
0x1800203c1  mov     [rbp+var_10], al
0x1800203c4  mov     eax, dword ptr [rbp+in.S_un]
0x1800203c7  mov     dword ptr [rbp+var_18], eax
0x1800203ca  mov     [rbp+pcbActual], r8d
0x1800203ce  mov     ecx, [rcx+18h]; columnid
0x1800203d1  call    DhcpJetSetValue
0x1800203d6  mov     ebx, eax
0x1800203d8  jmp     short loc_1800203FD
0x1800203da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203e1  cmp     rcx, r14
0x1800203e4  jz      short loc_180020404
0x1800203e6  test    [rcx+1Ch], r13d
0x1800203ea  jz      short loc_180020404
0x1800203ec  mov     rcx, [rcx+10h]
0x1800203f0  mov     edx, 19h
0x1800203f5  mov     r8, r15
0x1800203f8  call    WPP_SF_
0x1800203fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180020404  test    dil, dil
0x180020407  jns     loc_1800204A6
0x18002040d  call    DhcpGetDateTime
0x180020412  mov     rcx, cs:DhcpGlobalClientTable
0x180020419  lea     r8, [rbp+pcbActual]; pcbActual
0x18002041d  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x180020421  lea     rdx, [rbp+FileTime2]; pvData
0x180020425  mov     qword ptr [rbp+FileTime2.dwLowDateTime], 0
0x18002042d  mov     edi, 8
0x180020432  mov     [rbp+pcbActual], edi
0x180020435  mov     ecx, [rcx+58h]; columnid
0x180020438  call    DhcpJetGetValue
0x18002043d  mov     ebx, eax
0x18002043f  test    eax, eax
0x180020441  jnz     loc_1800205AB
0x180020447  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18002044b  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18002044f  call    cs:__imp_CompareFileTime
0x180020456  nop     dword ptr [rax+rax+00h]
0x18002045b  test    eax, eax
0x18002045d  jns     loc_1800204FF
0x180020463  mov     rcx, cs:WPP_GLOBAL_Control
0x18002046a  cmp     rcx, r14
0x18002046d  jz      short loc_180020487
0x18002046f  test    dword ptr [rcx+1Ch], 10000000h
0x180020476  jz      short loc_180020487
0x180020478  mov     rcx, [rcx+10h]
0x18002047c  lea     edx, [rdi+12h]
0x18002047f  mov     r8, r15
0x180020482  call    WPP_SF_
0x180020487  mov     rcx, cs:DhcpGlobalClientTable
0x18002048e  lea     rdx, [rbp+FileTime1]; pvData
0x180020492  mov     r8d, edi; cbData
0x180020495  mov     ecx, [rcx+58h]; columnid
0x180020498  call    DhcpJetSetValue
0x18002049d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800204a4  mov     ebx, eax
0x1800204a6  test    ebx, ebx
0x1800204a8  jnz     loc_1800205B2
0x1800204ae  call    DhcpJetCommitUpdate
0x1800204b3  mov     ebx, eax
0x1800204b5  test    eax, eax
0x1800204b7  jnz     loc_1800205AB
0x1800204bd  mov     rdi, cs:WPP_GLOBAL_Control
0x1800204c4  cmp     rdi, r14
0x1800204c7  jz      short loc_1800204F8
0x1800204c9  test    dword ptr [rdi+1Ch], 10000000h
0x1800204d0  jz      short loc_1800204F8
0x1800204d2  mov     ecx, dword ptr [rbp+in.S_un]; in
0x1800204d5  movzx   ebx, [rbp+pvData]
0x1800204d9  mov     rdi, [rdi+10h]
0x1800204dd  call    cs:__imp_inet_ntoa
0x1800204e4  nop     dword ptr [rax+rax+00h]
0x1800204e9  mov     rcx, rdi
0x1800204ec  mov     dword ptr [rsp+80h+var_60], ebx
0x1800204f0  mov     r9, rax
0x1800204f3  call    WPP_SF_sD
0x1800204f8  xor     eax, eax
0x1800204fa  jmp     loc_1800205D6
0x1800204ff  mov     rbx, qword ptr [rbp+FileTime1.dwLowDateTime]
0x180020503  mov     rax, 624DD2F1A9FBE77h
0x18002050d  sub     rbx, qword ptr [rbp+FileTime2.dwLowDateTime]
0x180020511  mul     rbx
0x180020514  sub     rbx, rdx
0x180020517  shr     rbx, 1
0x18002051a  add     rbx, rdx
0x18002051d  shr     rbx, 9
0x180020521  mov     rcx, cs:WPP_GLOBAL_Control
0x180020528  mov     edi, 66FF3000h
0x18002052d  cmp     rcx, r14
0x180020530  jz      short loc_180020584
0x180020532  test    [rcx+1Ch], r13d
0x180020536  jz      short loc_18002055E
0x180020538  mov     rcx, [rcx+10h]
0x18002053c  mov     rax, rbx
0x18002053f  shr     rax, 20h
0x180020543  mov     edx, 1Bh
0x180020548  mov     r9d, ebx
0x18002054b  mov     dword ptr [rsp+80h+var_60], eax
0x18002054f  mov     r8, r15
0x180020552  call    WPP_SF_dD
0x180020557  mov     rcx, cs:WPP_GLOBAL_Control
0x18002055e  cmp     rcx, r14
0x180020561  jz      short loc_180020584
0x180020563  test    [rcx+1Ch], r13d
0x180020567  jz      short loc_180020584
0x180020569  mov     rcx, [rcx+10h]
0x18002056d  mov     edx, 1Ch
0x180020572  mov     r9, rdi
0x180020575  mov     r8, r15
0x180020578  call    WPP_SF_q
0x18002057d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020584  cmp     rbx, rdi
0x180020587  jb      loc_1800204AE
0x18002058d  cmp     rcx, r14
0x180020590  jz      short loc_1800205D1
0x180020592  test    [rcx+1Ch], r13d
0x180020596  jz      short loc_1800205D1
0x180020598  mov     edx, 1Dh
0x18002059d  mov     rcx, [rcx+10h]
  ... truncated ...
```
