# DhcpDoDynDnsCheckDelete

- ea: `0x180020bb4`
- end: `0x180021117`
- name: `DhcpDoDynDnsCheckDelete`
- size: `1379`
- prototype: `__int64 __fastcall(struct in_addr)`
- caller_count: `5`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800068b8`
- `0x1800083d0`
- `0x1800093a0`
- `0x180050708`
- `0x180051670`

## callees

- `0x180002854`
- `0x18000323c`
- `0x1800057f4`
- `0x18000c180`
- `0x18000eb58`
- `0x18000ebd4`
- `0x18000ef84`
- `0x18000f0f8`
- `0x18001fc7c`
- `0x180020bb4`
- `0x180022b28`
- `0x180022e04`
- `0x18008ef3c`
- `0x18009877c`
- `0x1800cc9e0`

## import_xrefs

- `WS2_32!__imp_inet_ntoa` at `0x180020c2c`
- `WS2_32!__imp_inet_ntoa` at `0x180020cc3`
- `WS2_32!__imp_inet_ntoa` at `0x180020fec`
- `WS2_32!__imp_inet_ntoa` at `0x180020c2c`
- `WS2_32!__imp_inet_ntoa` at `0x180020cc3`
- `WS2_32!__imp_inet_ntoa` at `0x180020fec`
- `KERNEL32!CompareFileTime` at `0x180020f62`
- `KERNEL32!CompareFileTime` at `0x180020f62`
- `KERNEL32!HeapFree` at `0x180020dfb`
- `KERNEL32!HeapFree` at `0x180020e1e`
- `KERNEL32!HeapFree` at `0x180020dfb`
- `KERNEL32!HeapFree` at `0x180020e1e`

## pseudocode

```c
__int64 __fastcall DhcpDoDynDnsCheckDelete(struct in_addr a1)
{
  char *v1; // rax
  unsigned int Value; // eax
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  char v6; // di
  char *v7; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  LPVOID v10; // r8
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  FILETIME DateTime; // rax
  unsigned int v16; // eax
  char v17; // bl
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  unsigned __int64 v22; // rbx
  __int64 pvData; // [rsp+30h] [rbp-50h] BYREF
  struct in_addr in; // [rsp+38h] [rbp-48h] BYREF
  __int64 v25; // [rsp+40h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-38h] BYREF
  LPVOID v27; // [rsp+50h] [rbp-30h] BYREF
  FILETIME FileTime1; // [rsp+58h] [rbp-28h] BYREF
  FILETIME FileTime2; // [rsp+60h] [rbp-20h] BYREF
  __int64 S_addr; // [rsp+68h] [rbp-18h] BYREF
  char v31; // [rsp+70h] [rbp-10h]

  v25 = 0;
  lpMem = 0;
  v27 = 0;
  in = a1;
  LOBYTE(pvData) = 0;
  if ( DhcpGlobalUseNoDns )
    return 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
  {
    v1 = inet_ntoa(a1);
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids, v1);
  }
  HIDWORD(pvData) = 1;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), &pvData, (unsigned int *)&pvData + 1);
  if ( Value )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 1;
    v4 = 17;
    goto LABEL_9;
  }
  v6 = pvData;
  if ( (pvData & 0x10) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      v7 = inet_ntoa(in);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids, v7);
    }
    return 1;
  }
  HIDWORD(pvData) = 4;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 360), &v25, (unsigned int *)&pvData + 1);
  if ( Value )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 1;
    v4 = 19;
    goto LABEL_9;
  }
  HIDWORD(pvData) = 0;
  if ( (unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 72), &lpMem, (unsigned int *)&pvData + 1) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 1;
    v9 = 20;
    goto LABEL_66;
  }
  if ( (unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 24), &v27, (unsigned int *)&v25 + 1) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 1;
    v9 = 22;
    goto LABEL_66;
  }
  LOBYTE(pvData) = pvData | 3;
  DhcpDnsAsyncDelete(in.S_un.S_addr, (LPCWSTR)lpMem, pvData, SHIDWORD(v25), (__int64)v27, v25 & 1);
  if ( lpMem )
    HeapFree(gDhcpHeap, 0, lpMem);
  lpMem = 0;
  v10 = v27;
  if ( v27 )
    HeapFree(gDhcpHeap, 0, v27);
  LOBYTE(pvData) = pvData | 0xC0;
  Value = DhcpJetPrepareUpdate(*(_QWORD *)DhcpGlobalClientTable, &in, v10, 0);
  if ( Value )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 1;
    v4 = 23;
LABEL_9:
    v5 = Value;
LABEL_71:
    WPP_SF_D(v3[2], v4, &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids, v5);
    return 1;
  }
  HIDWORD(pvData) = 1;
  v11 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), &pvData, 1u);
  if ( !(unsigned int)MemServerIsReservedAddress(DhcpGlobalThisServer, in.S_un.S_addr) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids);
    v31 = 0;
    S_addr = in.S_un.S_addr;
    HIDWORD(pvData) = 9;
    v11 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 24), &S_addr, 9u);
    goto LABEL_42;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids);
LABEL_42:
    v3 = WPP_GLOBAL_Control;
  }
  if ( v6 < 0 )
  {
    DateTime = (FILETIME)DhcpGetDateTime(v3, v12, v13, v14);
    FileTime2 = 0;
    FileTime1 = DateTime;
    HIDWORD(pvData) = 8;
    v11 = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 88), &FileTime2, (unsigned int *)&pvData + 1);
    if ( v11 )
    {
LABEL_67:
      v3 = WPP_GLOBAL_Control;
LABEL_68:
      if ( v3 == &WPP_GLOBAL_Control || (*((_BYTE *)v3 + 28) & 0x10) == 0 )
        return 1;
      v4 = 30;
      v5 = v11;
      goto LABEL_71;
    }
    if ( CompareFileTime(&FileTime1, &FileTime2) >= 0 )
    {
      v22 = (*(_QWORD *)&FileTime1 - *(_QWORD *)&FileTime2) / 0x3E8uLL;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        {
          WPP_SF_dD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids,
            (unsigned int)v22,
            ((*(_QWORD *)&FileTime1 - *(_QWORD *)&FileTime2) / 0x3E8uLL) >> 32);
          v8 = WPP_GLOBAL_Control;
        }
        if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x40000) != 0 )
        {
          WPP_SF_q(v8[2], 28, &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids, 1728000000);
          v8 = WPP_GLOBAL_Control;
        }
      }
      if ( v22 >= 0x66FF3000 )
      {
        if ( v8 == &WPP_GLOBAL_Control || (*((_DWORD *)v8 + 7) & 0x40000) == 0 )
          return 1;
        v9 = 29;
LABEL_66:
        WPP_SF_(v8[2], v9, &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids);
        return 1;
      }
      goto LABEL_51;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids);
    }
    v16 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 88), &FileTime1, 8u);
    v3 = WPP_GLOBAL_Control;
    v11 = v16;
  }
  if ( v11 )
    goto LABEL_68;
LABEL_51:
  v11 = DhcpJetCommitUpdate();
  if ( v11 )
    goto LABEL_67;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
  {
    v17 = pvData;
    v18 = (unsigned int)inet_ntoa(in);
    WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, v18, v17);
  }
  return 0;
}

```

## disassembly

```asm
0x180020bb4  mov     [rsp-18h+arg_8], rbx
0x180020bb9  mov     [rsp-18h+arg_10], rdi
0x180020bbe  mov     [rsp-18h+arg_18], r13
0x180020bc3  push    rbp
0x180020bc4  push    r14
0x180020bc6  push    r15
0x180020bc8  mov     rbp, rsp
0x180020bcb  sub     rsp, 80h
0x180020bd2  mov     rax, cs:__security_cookie
0x180020bd9  xor     rax, rsp
0x180020bdc  mov     [rbp+var_8], rax
0x180020be0  and     [rbp+var_40], 0
0x180020be4  and     [rbp+lpMem], 0
0x180020be9  and     [rbp+var_3C], 0
0x180020bed  and     [rbp+var_30], 0
0x180020bf2  cmp     cs:DhcpGlobalUseNoDns, 0
0x180020bf9  mov     dword ptr [rbp+in.S_un], ecx
0x180020bfc  mov     [rbp+pvData], 0
0x180020c00  jnz     loc_1800210E8
0x180020c06  mov     rax, cs:WPP_GLOBAL_Control
0x180020c0d  lea     r14, WPP_GLOBAL_Control
0x180020c14  lea     r15, WPP_5e79908d56a839214a8dcc812d846f36_Traceguids
0x180020c1b  mov     r13d, 40000h
0x180020c21  cmp     rax, r14
0x180020c24  jz      short loc_180020C53
0x180020c26  test    [rax+1Ch], r13d
0x180020c2a  jz      short loc_180020C53
0x180020c2c  call    cs:__imp_inet_ntoa
0x180020c33  nop     dword ptr [rax+rax+00h]
0x180020c38  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c3f  mov     edx, 10h
0x180020c44  mov     r9, rax
0x180020c47  mov     r8, r15
0x180020c4a  mov     rcx, [rcx+10h]
0x180020c4e  call    WPP_SF_s
0x180020c53  mov     rcx, cs:DhcpGlobalClientTable
0x180020c5a  lea     r8, [rbp+pcbActual]; pcbActual
0x180020c5e  mov     [rbp+pcbActual], 1
0x180020c65  lea     rdx, [rbp+pvData]; pvData
0x180020c69  mov     ecx, [rcx+28h]; columnid
0x180020c6c  call    DhcpJetGetValue
0x180020c71  test    eax, eax
0x180020c73  jz      short loc_180020C9C
0x180020c75  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c7c  cmp     rcx, r14
0x180020c7f  jz      loc_1800210E8
0x180020c85  test    byte ptr [rcx+1Ch], 10h
0x180020c89  jz      loc_1800210E8
0x180020c8f  mov     edx, 11h
0x180020c94  mov     r9d, eax
0x180020c97  jmp     loc_1800210DC
0x180020c9c  mov     dil, [rbp+pvData]
0x180020ca0  test    dil, 10h
0x180020ca4  jnz     short loc_180020CEF
0x180020ca6  mov     rax, cs:WPP_GLOBAL_Control
0x180020cad  cmp     rax, r14
0x180020cb0  jz      loc_1800210E8
0x180020cb6  test    [rax+1Ch], r13d
0x180020cba  jz      loc_1800210E8
0x180020cc0  mov     ecx, dword ptr [rbp+in.S_un]; in
0x180020cc3  call    cs:__imp_inet_ntoa
0x180020cca  nop     dword ptr [rax+rax+00h]
0x180020ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cd6  mov     edx, 12h
0x180020cdb  mov     r9, rax
0x180020cde  mov     r8, r15
0x180020ce1  mov     rcx, [rcx+10h]
0x180020ce5  call    WPP_SF_s
0x180020cea  jmp     loc_1800210E8
0x180020cef  mov     rcx, cs:DhcpGlobalClientTable
0x180020cf6  lea     r8, [rbp+pcbActual]; pcbActual
0x180020cfa  mov     [rbp+pcbActual], 4
0x180020d01  lea     rdx, [rbp+var_40]; pvData
0x180020d05  mov     ecx, [rcx+168h]; columnid
0x180020d0b  call    DhcpJetGetValue
0x180020d10  test    eax, eax
0x180020d12  jz      short loc_180020D38
0x180020d14  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d1b  cmp     rcx, r14
0x180020d1e  jz      loc_1800210E8
0x180020d24  test    byte ptr [rcx+1Ch], 10h
0x180020d28  jz      loc_1800210E8
0x180020d2e  mov     edx, 13h
0x180020d33  jmp     loc_180020C94
0x180020d38  mov     rcx, cs:DhcpGlobalClientTable
0x180020d3f  lea     r8, [rbp+pcbActual]; pcbActual
0x180020d43  and     [rbp+pcbActual], 0
0x180020d47  lea     rdx, [rbp+lpMem]; pvData
0x180020d4b  mov     ecx, [rcx+48h]; columnid
0x180020d4e  call    DhcpJetGetValue
0x180020d53  test    eax, eax
0x180020d55  jz      short loc_180020D7B
0x180020d57  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d5e  cmp     rcx, r14
0x180020d61  jz      loc_1800210E8
0x180020d67  test    byte ptr [rcx+1Ch], 10h
0x180020d6b  jz      loc_1800210E8
0x180020d71  mov     edx, 14h
0x180020d76  jmp     loc_1800210B4
0x180020d7b  mov     rcx, cs:DhcpGlobalClientTable
0x180020d82  lea     r8, [rbp+var_3C]; pcbActual
0x180020d86  lea     rdx, [rbp+var_30]; pvData
0x180020d8a  mov     ecx, [rcx+18h]; columnid
0x180020d8d  call    DhcpJetGetValue
0x180020d92  test    eax, eax
0x180020d94  jz      short loc_180020DBA
0x180020d96  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d9d  cmp     rcx, r14
0x180020da0  jz      loc_1800210E8
0x180020da6  test    byte ptr [rcx+1Ch], 10h
0x180020daa  jz      loc_1800210E8
0x180020db0  mov     edx, 16h
0x180020db5  jmp     loc_1800210B4
0x180020dba  mov     eax, [rbp+var_40]
0x180020dbd  mov     r8b, [rbp+pvData]
0x180020dc1  and     eax, 1
0x180020dc4  mov     r9d, [rbp+var_3C]
0x180020dc8  or      r8b, 3
0x180020dcc  mov     rdx, [rbp+lpMem]; lpSrcStr
0x180020dd0  mov     ecx, dword ptr [rbp+in.S_un]; hostlong
0x180020dd3  mov     [rsp+80h+var_58], eax; int
0x180020dd7  mov     rax, [rbp+var_30]
0x180020ddb  mov     [rsp+80h+var_60], rax; __int64
0x180020de0  mov     [rbp+pvData], r8b
0x180020de4  call    DhcpDnsAsyncDelete
0x180020de9  mov     r8, [rbp+lpMem]; lpMem
0x180020ded  test    r8, r8
0x180020df0  jz      short loc_180020E07
0x180020df2  mov     rcx, cs:gDhcpHeap; hHeap
0x180020df9  xor     edx, edx; dwFlags
0x180020dfb  call    cs:__imp_HeapFree
0x180020e02  nop     dword ptr [rax+rax+00h]
0x180020e07  and     [rbp+lpMem], 0
0x180020e0c  mov     r8, [rbp+var_30]; lpMem
0x180020e10  test    r8, r8
0x180020e13  jz      short loc_180020E2A
0x180020e15  mov     rcx, cs:gDhcpHeap; hHeap
0x180020e1c  xor     edx, edx; dwFlags
0x180020e1e  call    cs:__imp_HeapFree
0x180020e25  nop     dword ptr [rax+rax+00h]
0x180020e2a  mov     rcx, cs:DhcpGlobalClientTable
0x180020e31  lea     rdx, [rbp+in]
0x180020e35  or      [rbp+pvData], 0C0h
0x180020e39  xor     r9d, r9d
0x180020e3c  mov     rcx, [rcx]
0x180020e3f  call    DhcpJetPrepareUpdate
0x180020e44  test    eax, eax
0x180020e46  jz      short loc_180020E6C
0x180020e48  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e4f  cmp     rcx, r14
0x180020e52  jz      loc_1800210E8
0x180020e58  test    byte ptr [rcx+1Ch], 10h
0x180020e5c  jz      loc_1800210E8
0x180020e62  mov     edx, 17h
0x180020e67  jmp     loc_180020C94
0x180020e6c  mov     rcx, cs:DhcpGlobalClientTable
0x180020e73  lea     rdx, [rbp+pvData]; pvData
0x180020e77  mov     eax, 1
0x180020e7c  mov     [rbp+pcbActual], eax
0x180020e7f  mov     r8d, eax; cbData
0x180020e82  mov     ecx, [rcx+28h]; columnid
0x180020e85  call    DhcpJetSetValue
0x180020e8a  mov     edx, dword ptr [rbp+in.S_un]
0x180020e8d  mov     ebx, eax
0x180020e8f  mov     rcx, cs:DhcpGlobalThisServer
0x180020e96  call    MemServerIsReservedAddress
0x180020e9b  test    eax, eax
0x180020e9d  jnz     short loc_180020EF0
0x180020e9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ea6  cmp     rcx, r14
0x180020ea9  jz      short loc_180020EC0
0x180020eab  test    [rcx+1Ch], r13d
0x180020eaf  jz      short loc_180020EC0
0x180020eb1  mov     rcx, [rcx+10h]
0x180020eb5  lea     edx, [rax+18h]
0x180020eb8  mov     r8, r15
0x180020ebb  call    WPP_SF_
0x180020ec0  mov     rcx, cs:DhcpGlobalClientTable
0x180020ec7  lea     rdx, [rbp+var_18]; pvData
0x180020ecb  xor     eax, eax
0x180020ecd  mov     r8d, 9; cbData
0x180020ed3  mov     [rbp+var_18], rax
0x180020ed7  mov     [rbp+var_10], al
0x180020eda  mov     eax, dword ptr [rbp+in.S_un]
0x180020edd  mov     dword ptr [rbp+var_18], eax
0x180020ee0  mov     [rbp+pcbActual], r8d
0x180020ee4  mov     ecx, [rcx+18h]; columnid
0x180020ee7  call    DhcpJetSetValue
0x180020eec  mov     ebx, eax
0x180020eee  jmp     short loc_180020F13
0x180020ef0  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ef7  cmp     rcx, r14
0x180020efa  jz      short loc_180020F1A
0x180020efc  test    [rcx+1Ch], r13d
0x180020f00  jz      short loc_180020F1A
0x180020f02  mov     rcx, [rcx+10h]
0x180020f06  mov     edx, 19h
0x180020f0b  mov     r8, r15
0x180020f0e  call    WPP_SF_
0x180020f13  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f1a  test    dil, dil
0x180020f1d  jns     loc_180020FB9
0x180020f23  call    DhcpGetDateTime
0x180020f28  mov     rcx, cs:DhcpGlobalClientTable
0x180020f2f  lea     r8, [rbp+pcbActual]; pcbActual
0x180020f33  and     qword ptr [rbp+FileTime2.dwLowDateTime], 0
0x180020f38  lea     rdx, [rbp+FileTime2]; pvData
0x180020f3c  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x180020f40  mov     edi, 8
0x180020f45  mov     [rbp+pcbActual], edi
0x180020f48  mov     ecx, [rcx+58h]; columnid
0x180020f4b  call    DhcpJetGetValue
0x180020f50  mov     ebx, eax
0x180020f52  test    eax, eax
0x180020f54  jnz     loc_1800210C2
0x180020f5a  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180020f5e  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180020f62  call    cs:__imp_CompareFileTime
0x180020f69  nop     dword ptr [rax+rax+00h]
0x180020f6e  test    eax, eax
0x180020f70  jns     loc_180021016
0x180020f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f7d  cmp     rcx, r14
0x180020f80  jz      short loc_180020F9A
0x180020f82  test    dword ptr [rcx+1Ch], 10000000h
0x180020f89  jz      short loc_180020F9A
0x180020f8b  mov     rcx, [rcx+10h]
0x180020f8f  lea     edx, [rdi+12h]
0x180020f92  mov     r8, r15
0x180020f95  call    WPP_SF_
0x180020f9a  mov     rcx, cs:DhcpGlobalClientTable
0x180020fa1  lea     rdx, [rbp+FileTime1]; pvData
0x180020fa5  mov     r8d, edi; cbData
0x180020fa8  mov     ecx, [rcx+58h]; columnid
0x180020fab  call    DhcpJetSetValue
0x180020fb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fb7  mov     ebx, eax
0x180020fb9  test    ebx, ebx
0x180020fbb  jnz     loc_1800210C9
0x180020fc1  call    DhcpJetCommitUpdate
0x180020fc6  mov     ebx, eax
0x180020fc8  test    eax, eax
0x180020fca  jnz     loc_1800210C2
0x180020fd0  mov     rax, cs:WPP_GLOBAL_Control
0x180020fd7  cmp     rax, r14
0x180020fda  jz      short loc_18002100F
0x180020fdc  test    dword ptr [rax+1Ch], 10000000h
0x180020fe3  jz      short loc_18002100F
0x180020fe5  mov     ecx, dword ptr [rbp+in.S_un]; in
0x180020fe8  movzx   ebx, [rbp+pvData]
0x180020fec  call    cs:__imp_inet_ntoa
0x180020ff3  nop     dword ptr [rax+rax+00h]
0x180020ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fff  mov     r9, rax
0x180021002  mov     dword ptr [rsp+80h+var_60], ebx
0x180021006  mov     rcx, [rcx+10h]
0x18002100a  call    WPP_SF_sD
0x18002100f  xor     eax, eax
0x180021011  jmp     loc_1800210ED
0x180021016  mov     rbx, qword ptr [rbp+FileTime1.dwLowDateTime]
0x18002101a  mov     rax, 624DD2F1A9FBE77h
0x180021024  sub     rbx, qword ptr [rbp+FileTime2.dwLowDateTime]
0x180021028  mul     rbx
0x18002102b  sub     rbx, rdx
0x18002102e  shr     rbx, 1
0x180021031  add     rbx, rdx
0x180021034  shr     rbx, 9
0x180021038  mov     rcx, cs:WPP_GLOBAL_Control
0x18002103f  mov     edi, 66FF3000h
0x180021044  cmp     rcx, r14
0x180021047  jz      short loc_18002109B
0x180021049  test    [rcx+1Ch], r13d
0x18002104d  jz      short loc_180021075
0x18002104f  mov     rcx, [rcx+10h]
0x180021053  mov     rax, rbx
0x180021056  shr     rax, 20h
0x18002105a  mov     edx, 1Bh
0x18002105f  mov     r9d, ebx
0x180021062  mov     dword ptr [rsp+80h+var_60], eax
0x180021066  mov     r8, r15
0x180021069  call    WPP_SF_dD
0x18002106e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021075  cmp     rcx, r14
0x180021078  jz      short loc_18002109B
0x18002107a  test    [rcx+1Ch], r13d
0x18002107e  jz      short loc_18002109B
0x180021080  mov     rcx, [rcx+10h]
0x180021084  mov     edx, 1Ch
0x180021089  mov     r9, rdi
0x18002108c  mov     r8, r15
0x18002108f  call    WPP_SF_q
0x180021094  mov     rcx, cs:WPP_GLOBAL_Control
0x18002109b  cmp     rbx, rdi
0x18002109e  jb      loc_180020FC1
0x1800210a4  cmp     rcx, r14
0x1800210a7  jz      short loc_1800210E8
0x1800210a9  test    [rcx+1Ch], r13d
0x1800210ad  jz      short loc_1800210E8
0x1800210af  mov     edx, 1Dh
0x1800210b4  mov     rcx, [rcx+10h]
  ... truncated ...
```
