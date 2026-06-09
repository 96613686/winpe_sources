# SplTunMgrApplyFilteringStateUnderLock

- ea: `0x18006892c`
- end: `0x180068bf9`
- name: `SplTunMgrApplyFilteringStateUnderLock`
- size: `717`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003b544`
- `0x180040c70`
- `0x1800688a0`
- `0x180068e5c`
- `0x1800690bc`

## callees

- `0x180008210`
- `0x18000d7c0`
- `0x180024250`
- `0x18006892c`
- `0x180068c94`
- `0x180068d68`

## import_xrefs

- `IPHLPAPI!FreeMibTable` at `0x180068b20`
- `IPHLPAPI!FreeMibTable` at `0x180068b20`
- `IPHLPAPI!GetIpInterfaceTable` at `0x1800689be`
- `IPHLPAPI!GetIpInterfaceTable` at `0x1800689be`
- `IPHLPAPI!CreateIpForwardEntry2` at `0x180068aba`
- `IPHLPAPI!CreateIpForwardEntry2` at `0x180068aba`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x180068bbd`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x180068bbd`

## string_xrefs

- `0x180068bed`: `SplTunMgrApplyFilteringStateUnderLock: CreateIpForwardEntry2 failed 0x%x`
- `0x180068bd2`: `SplTunMgrApplyFilteringStateUnderLock: DeleteIpForwardEntry2 failed 0x%x`

## pseudocode

```c
__int64 __fastcall SplTunMgrApplyFilteringStateUnderLock(int a1)
{
  int v2; // edi
  BOOL v3; // esi
  unsigned int v4; // ebx
  unsigned int IpInterfaceTable; // eax
  ULONG i; // r12d
  PMIB_IPINTERFACE_TABLE v7; // rdi
  unsigned __int64 v8; // rbp
  NET_LUID *p_InterfaceLuid; // r15
  unsigned int v10; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  const MIB_IPFORWARD_ROW2 *v14; // rcx
  unsigned int IpForwardEntry2; // eax
  unsigned int v16; // eax
  unsigned int v18; // eax
  __int64 v19; // rcx
  const MIB_IPFORWARD_ROW2 *v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // [rsp+20h] [rbp-38h]
  unsigned __int8 v23; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int8 v24; // [rsp+70h] [rbp+18h] BYREF
  PMIB_IPINTERFACE_TABLE Table; // [rsp+78h] [rbp+20h] BYREF

  Table = 0;
  v2 = 0;
  v24 = 0;
  v23 = 0;
  EventWriteEnterEx(0x20000, L"Entered: SplTunMgrApplyFilteringStateUnderLock");
  v3 = dword_1800CBC20 == 2 && dword_1800CBC24;
  EventWrite0(
    0x10000000,
    L"SplTunMgrApplyFilteringStateUnderLock: NewFilteringState = %d, global connected state = %d",
    v3);
  if ( v3 )
  {
    if ( !dword_1800CBC28 || a1 )
      v2 = 1;
  }
  else if ( dword_1800CBC28 )
  {
    dword_1800CBC28 = 0;
    goto LABEL_10;
  }
  v4 = 0;
  dword_1800CBC28 = v3;
  if ( !v2 )
    goto LABEL_29;
LABEL_10:
  IpInterfaceTable = GetIpInterfaceTable(0, &Table);
  v4 = IpInterfaceTable;
  if ( !IpInterfaceTable )
  {
    for ( i = 0; ; ++i )
    {
      v7 = Table;
      if ( i >= Table->NumEntries )
        goto LABEL_29;
      v8 = i;
      p_InterfaceLuid = &Table->Table[v8].InterfaceLuid;
      if ( p_InterfaceLuid->Value != qword_1800CBD00 )
      {
        v10 = SplTunMgrQueryInterfaceProperties(Table->Table[v8].Family, &Table->Table[v8].InterfaceLuid, &v23, &v24);
        v4 = v10;
        if ( v10 )
        {
          EventWrite0(
            0x10000000,
            L"SplTunMgrApplyFilteringStateUnderLock: SplTunMgrQueryInterfaceProperties failed 0x%x",
            v10);
          if ( v3 )
            goto LABEL_29;
          goto LABEL_40;
        }
        LODWORD(v22) = v24;
        EventWrite0(
          0x10000000,
          L"SplTunMgrApplyFilteringStateUnderLock: interface index = %d; disable default routes = %d; forcetunneling = %d",
          v7->Table[v8].InterfaceIndex,
          v23,
          v22);
        if ( v3 )
        {
          v13 = v7->Table[v8].Family != 2 ? 0x68 : 0;
          if ( !*(_DWORD *)((char *)&g_ProtocolStateSplTunMgr[9] + v13) )
            goto LABEL_25;
          if ( v23 )
            goto LABEL_26;
          v14 = (const MIB_IPFORWARD_ROW2 *)((char *)&g_ProtocolStateSplTunMgr[8] + v13);
          if ( p_InterfaceLuid->Value == v14->InterfaceLuid.Value )
          {
            IpForwardEntry2 = CreateIpForwardEntry2(v14);
            v4 = IpForwardEntry2;
            if ( IpForwardEntry2 )
            {
              EventWrite0(
                0x10000000,
                L"SplTunMgrApplyFilteringStateUnderLock: CreateIpForwardEntry2 failed 0x%x",
                IpForwardEntry2);
              goto LABEL_29;
            }
          }
LABEL_25:
          if ( v23 )
          {
LABEL_26:
            if ( v24 )
              continue;
          }
          LOBYTE(v12) = 1;
          LOBYTE(v11) = 1;
          v16 = SplTunMgrSetInterfaceProperties(v7->Table[v8].Family, &v7->Table[v8].InterfaceLuid, v11, v12);
          v4 = v16;
          if ( v16 )
          {
            EventWrite0(
              0x10000000,
              L"SplTunMgrApplyFilteringStateUnderLock: SplTunMgrSetInterfaceProperties failed 0x%x",
              v16);
            goto LABEL_29;
          }
          continue;
        }
        if ( v23 || v24 )
        {
          v18 = SplTunMgrSetInterfaceProperties(v7->Table[v8].Family, &v7->Table[v8].InterfaceLuid, 0, 0);
          v4 = v18;
          if ( v18 )
          {
            EventWrite0(
              0x10000000,
              L"SplTunMgrApplyFilteringStateUnderLock: SplTunMgrSetInterfaceProperties failed 0x%x",
              v18);
            v4 = 0;
          }
        }
        v19 = v7->Table[v8].Family != 2 ? 0x68 : 0;
        if ( *(_DWORD *)((char *)&g_ProtocolStateSplTunMgr[9] + v19) )
        {
          v20 = (const MIB_IPFORWARD_ROW2 *)((char *)&g_ProtocolStateSplTunMgr[8] + v19);
          if ( p_InterfaceLuid->Value == v20->InterfaceLuid.Value )
          {
            v21 = DeleteIpForwardEntry2(v20);
            v4 = v21;
            if ( v21 )
            {
              EventWrite0(0x10000000, L"SplTunMgrApplyFilteringStateUnderLock: DeleteIpForwardEntry2 failed 0x%x", v21);
LABEL_40:
              v4 = 0;
              continue;
            }
          }
        }
      }
    }
  }
  EventWrite0(0x10000000, L"SplTunMgrApplyFilteringStateUnderLock: GetIpInterfaceTable failed 0x%x", IpInterfaceTable);
LABEL_29:
  if ( Table )
    FreeMibTable(Table);
  EventWriteLeaveEx(0x20000, L"Leaving: SplTunMgrApplyFilteringStateUnderLock");
  return v4;
}

```

## disassembly

```asm
0x18006892c  mov     rax, rsp
0x18006892f  mov     [rax+8], rbx
0x180068933  push    rbp
0x180068934  push    rsi
0x180068935  push    rdi
0x180068936  push    r12
0x180068938  push    r15
0x18006893a  sub     rsp, 30h
0x18006893e  mov     ebx, ecx
0x180068940  mov     qword ptr [rax+20h], 0
0x180068948  xor     edi, edi
0x18006894a  lea     rdx, aEnteredSpltunm; "Entered: SplTunMgrApplyFilteringStateUn"...
0x180068951  mov     ecx, 20000h
0x180068956  mov     [rax+18h], dil
0x18006895a  mov     [rax+10h], dil
0x18006895e  call    EventWriteEnterEx
0x180068963  cmp     cs:dword_1800CBC20, 2
0x18006896a  lea     ebp, [rdi+1]
0x18006896d  mov     r9d, cs:dword_1800CBC24
0x180068974  jnz     short loc_18006897F
0x180068976  test    r9d, r9d
0x180068979  jz      short loc_18006897F
0x18006897b  mov     esi, ebp
0x18006897d  jmp     short loc_180068981
0x18006897f  xor     esi, esi
0x180068981  mov     r8d, esi
0x180068984  lea     rdx, aSpltunmgrapply_3; "SplTunMgrApplyFilteringStateUnderLock: "...
0x18006898b  mov     ecx, 10000000h
0x180068990  call    EventWrite0
0x180068995  test    esi, esi
0x180068997  jz      short loc_1800689DC
0x180068999  cmp     cs:dword_1800CBC28, edi
0x18006899f  jz      short loc_1800689A5
0x1800689a1  test    ebx, ebx
0x1800689a3  jz      short loc_1800689A7
0x1800689a5  mov     edi, ebp
0x1800689a7  xor     ebx, ebx
0x1800689a9  mov     cs:dword_1800CBC28, esi
0x1800689af  test    edi, edi
0x1800689b1  jz      loc_180068B13
0x1800689b7  xor     ecx, ecx; Family
0x1800689b9  lea     rdx, [rsp+58h+Table]; Table
0x1800689be  call    cs:__imp_GetIpInterfaceTable
0x1800689c5  nop     dword ptr [rax+rax+00h]
0x1800689ca  mov     ebx, eax
0x1800689cc  test    eax, eax
0x1800689ce  jz      short loc_1800689EC
0x1800689d0  lea     rdx, aSpltunmgrapply_2; "SplTunMgrApplyFilteringStateUnderLock: "...
0x1800689d7  jmp     loc_180068B06
0x1800689dc  cmp     cs:dword_1800CBC28, edi
0x1800689e2  jz      short loc_1800689A7
0x1800689e4  mov     cs:dword_1800CBC28, esi
0x1800689ea  jmp     short loc_1800689B7
0x1800689ec  xor     r12d, r12d
0x1800689ef  mov     rdi, [rsp+58h+Table]
0x1800689f4  cmp     r12d, [rdi]
0x1800689f7  jnb     loc_180068B13
0x1800689fd  mov     eax, r12d
0x180068a00  lea     r15, [rdi+10h]
0x180068a04  imul    rbp, rax, 0A8h
0x180068a0b  mov     rax, cs:qword_1800CBD00
0x180068a12  add     r15, rbp
0x180068a15  cmp     [r15], rax
0x180068a18  jz      loc_180068BE5
0x180068a1e  movzx   ecx, word ptr [rdi+rbp+8]
0x180068a23  lea     r9, [rsp+58h+arg_10]
0x180068a28  lea     r8, [rsp+58h+arg_8]
0x180068a2d  mov     rdx, r15
0x180068a30  call    SplTunMgrQueryInterfaceProperties
0x180068a35  mov     ebx, eax
0x180068a37  mov     ecx, 10000000h
0x180068a3c  test    eax, eax
0x180068a3e  jz      short loc_180068A5C
0x180068a40  mov     r8d, eax
0x180068a43  lea     rdx, aSpltunmgrapply_1; "SplTunMgrApplyFilteringStateUnderLock: "...
0x180068a4a  call    EventWrite0
0x180068a4f  test    esi, esi
0x180068a51  jnz     loc_180068B13
0x180068a57  jmp     loc_180068BE3
0x180068a5c  movzx   eax, [rsp+58h+arg_10]
0x180068a61  lea     rdx, aSpltunmgrapply_5; "SplTunMgrApplyFilteringStateUnderLock: "...
0x180068a68  movzx   r9d, [rsp+58h+arg_8]
0x180068a6e  mov     r8d, [rdi+rbp+18h]
0x180068a73  mov     dword ptr [rsp+58h+var_38], eax
0x180068a77  call    EventWrite0
0x180068a7c  test    esi, esi
0x180068a7e  jz      loc_180068B51
0x180068a84  movzx   eax, word ptr [rdi+rbp+8]
0x180068a89  lea     rdx, g_ProtocolStateSplTunMgr
0x180068a90  sub     ax, 2
0x180068a94  neg     ax
0x180068a97  sbb     rcx, rcx
0x180068a9a  and     ecx, 68h
0x180068a9d  cmp     dword ptr [rcx+rdx+48h], 0
0x180068aa2  jz      short loc_180068AD0
0x180068aa4  cmp     [rsp+58h+arg_8], 0
0x180068aa9  jnz     short loc_180068AD7
0x180068aab  add     rcx, 40h ; '@'
0x180068aaf  add     rcx, rdx; Row
0x180068ab2  mov     rax, [rcx]
0x180068ab5  cmp     [r15], rax
0x180068ab8  jnz     short loc_180068AD0
0x180068aba  call    cs:__imp_CreateIpForwardEntry2
0x180068ac1  nop     dword ptr [rax+rax+00h]
0x180068ac6  mov     ebx, eax
0x180068ac8  test    eax, eax
0x180068aca  jnz     loc_180068BED
0x180068ad0  cmp     [rsp+58h+arg_8], 0
0x180068ad5  jz      short loc_180068AE2
0x180068ad7  cmp     [rsp+58h+arg_10], 0
0x180068adc  jnz     loc_180068BE5
0x180068ae2  movzx   ecx, word ptr [rdi+rbp+8]
0x180068ae7  mov     r9b, 1
0x180068aea  mov     r8b, r9b
0x180068aed  mov     rdx, r15
0x180068af0  call    SplTunMgrSetInterfaceProperties
0x180068af5  mov     ebx, eax
0x180068af7  test    eax, eax
0x180068af9  jz      loc_180068BE5
0x180068aff  lea     rdx, aSpltunmgrapply; "SplTunMgrApplyFilteringStateUnderLock: "...
0x180068b06  mov     r8d, eax
0x180068b09  mov     ecx, 10000000h
0x180068b0e  call    EventWrite0
0x180068b13  mov     rdi, [rsp+58h+Table]
0x180068b18  test    rdi, rdi
0x180068b1b  jz      short loc_180068B2C
0x180068b1d  mov     rcx, rdi; Memory
0x180068b20  call    cs:__imp_FreeMibTable
0x180068b27  nop     dword ptr [rax+rax+00h]
0x180068b2c  lea     rdx, aLeavingSpltunm_3; "Leaving: SplTunMgrApplyFilteringStateUn"...
0x180068b33  mov     ecx, 20000h
0x180068b38  call    EventWriteLeaveEx
0x180068b3d  mov     eax, ebx
0x180068b3f  mov     rbx, [rsp+58h+arg_0]
0x180068b44  add     rsp, 30h
0x180068b48  pop     r15
0x180068b4a  pop     r12
0x180068b4c  pop     rdi
0x180068b4d  pop     rsi
0x180068b4e  pop     rbp
0x180068b4f  retn
0x180068b51  cmp     [rsp+58h+arg_8], 0
0x180068b56  jnz     short loc_180068B5F
0x180068b58  cmp     [rsp+58h+arg_10], 0
0x180068b5d  jz      short loc_180068B8E
0x180068b5f  movzx   ecx, word ptr [rdi+rbp+8]
0x180068b64  xor     r9d, r9d
0x180068b67  xor     r8d, r8d
0x180068b6a  mov     rdx, r15
0x180068b6d  call    SplTunMgrSetInterfaceProperties
0x180068b72  mov     ebx, eax
0x180068b74  test    eax, eax
0x180068b76  jz      short loc_180068B8E
0x180068b78  mov     r8d, eax
0x180068b7b  lea     rdx, aSpltunmgrapply; "SplTunMgrApplyFilteringStateUnderLock: "...
0x180068b82  mov     ecx, 10000000h
0x180068b87  call    EventWrite0
0x180068b8c  xor     ebx, ebx
0x180068b8e  movzx   eax, word ptr [rdi+rbp+8]
0x180068b93  lea     rdx, g_ProtocolStateSplTunMgr
0x180068b9a  sub     ax, 2
0x180068b9e  neg     ax
0x180068ba1  sbb     rcx, rcx
0x180068ba4  and     ecx, 68h
0x180068ba7  cmp     dword ptr [rcx+rdx+48h], 0
0x180068bac  jz      short loc_180068BE5
0x180068bae  add     rcx, 40h ; '@'
0x180068bb2  add     rcx, rdx; Row
0x180068bb5  mov     rax, [rcx]
0x180068bb8  cmp     [r15], rax
0x180068bbb  jnz     short loc_180068BE5
0x180068bbd  call    cs:__imp_DeleteIpForwardEntry2
0x180068bc4  nop     dword ptr [rax+rax+00h]
0x180068bc9  mov     ebx, eax
0x180068bcb  test    eax, eax
0x180068bcd  jz      short loc_180068BE5
0x180068bcf  mov     r8d, eax
0x180068bd2  lea     rdx, aSpltunmgrapply_0; "SplTunMgrApplyFilteringStateUnderLock: "...
0x180068bd9  mov     ecx, 10000000h
0x180068bde  call    EventWrite0
0x180068be3  xor     ebx, ebx
0x180068be5  inc     r12d
0x180068be8  jmp     loc_1800689EF
0x180068bed  lea     rdx, aSpltunmgrapply_4; "SplTunMgrApplyFilteringStateUnderLock: "...
0x180068bf4  jmp     loc_180068B06
```
