# SplTunMgrApplyFilteringStateUnderLock

- ea: `0x18006890c`
- end: `0x180068bd9`
- name: `SplTunMgrApplyFilteringStateUnderLock`
- size: `717`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003b534`
- `0x180040cb0`
- `0x180068880`
- `0x180068e3c`
- `0x18006909c`

## callees

- `0x180008200`
- `0x18000d7b0`
- `0x180024240`
- `0x18006890c`
- `0x180068c74`
- `0x180068d48`

## import_xrefs

- `IPHLPAPI!FreeMibTable` at `0x180068b00`
- `IPHLPAPI!FreeMibTable` at `0x180068b00`
- `IPHLPAPI!GetIpInterfaceTable` at `0x18006899e`
- `IPHLPAPI!GetIpInterfaceTable` at `0x18006899e`
- `IPHLPAPI!CreateIpForwardEntry2` at `0x180068a9a`
- `IPHLPAPI!CreateIpForwardEntry2` at `0x180068a9a`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x180068b9d`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x180068b9d`

## string_xrefs

- `0x180068bcd`: `SplTunMgrApplyFilteringStateUnderLock: CreateIpForwardEntry2 failed 0x%x`
- `0x180068bb2`: `SplTunMgrApplyFilteringStateUnderLock: DeleteIpForwardEntry2 failed 0x%x`

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
0x18006890c  mov     rax, rsp
0x18006890f  mov     [rax+8], rbx
0x180068913  push    rbp
0x180068914  push    rsi
0x180068915  push    rdi
0x180068916  push    r12
0x180068918  push    r15
0x18006891a  sub     rsp, 30h
0x18006891e  mov     ebx, ecx
0x180068920  mov     qword ptr [rax+20h], 0
0x180068928  xor     edi, edi
0x18006892a  lea     rdx, aEnteredSpltunm; "Entered: SplTunMgrApplyFilteringStateUn"...
0x180068931  mov     ecx, 20000h
0x180068936  mov     [rax+18h], dil
0x18006893a  mov     [rax+10h], dil
0x18006893e  call    EventWriteEnterEx
0x180068943  cmp     cs:dword_1800CBC20, 2
0x18006894a  lea     ebp, [rdi+1]
0x18006894d  mov     r9d, cs:dword_1800CBC24
0x180068954  jnz     short loc_18006895F
0x180068956  test    r9d, r9d
0x180068959  jz      short loc_18006895F
0x18006895b  mov     esi, ebp
0x18006895d  jmp     short loc_180068961
0x18006895f  xor     esi, esi
0x180068961  mov     r8d, esi
0x180068964  lea     rdx, aSpltunmgrapply_3; "SplTunMgrApplyFilteringStateUnderLock: "...
0x18006896b  mov     ecx, 10000000h
0x180068970  call    EventWrite0
0x180068975  test    esi, esi
0x180068977  jz      short loc_1800689BC
0x180068979  cmp     cs:dword_1800CBC28, edi
0x18006897f  jz      short loc_180068985
0x180068981  test    ebx, ebx
0x180068983  jz      short loc_180068987
0x180068985  mov     edi, ebp
0x180068987  xor     ebx, ebx
0x180068989  mov     cs:dword_1800CBC28, esi
0x18006898f  test    edi, edi
0x180068991  jz      loc_180068AF3
0x180068997  xor     ecx, ecx; Family
0x180068999  lea     rdx, [rsp+58h+Table]; Table
0x18006899e  call    cs:__imp_GetIpInterfaceTable
0x1800689a5  nop     dword ptr [rax+rax+00h]
0x1800689aa  mov     ebx, eax
0x1800689ac  test    eax, eax
0x1800689ae  jz      short loc_1800689CC
0x1800689b0  lea     rdx, aSpltunmgrapply_2; "SplTunMgrApplyFilteringStateUnderLock: "...
0x1800689b7  jmp     loc_180068AE6
0x1800689bc  cmp     cs:dword_1800CBC28, edi
0x1800689c2  jz      short loc_180068987
0x1800689c4  mov     cs:dword_1800CBC28, esi
0x1800689ca  jmp     short loc_180068997
0x1800689cc  xor     r12d, r12d
0x1800689cf  mov     rdi, [rsp+58h+Table]
0x1800689d4  cmp     r12d, [rdi]
0x1800689d7  jnb     loc_180068AF3
0x1800689dd  mov     eax, r12d
0x1800689e0  lea     r15, [rdi+10h]
0x1800689e4  imul    rbp, rax, 0A8h
0x1800689eb  mov     rax, cs:qword_1800CBD00
0x1800689f2  add     r15, rbp
0x1800689f5  cmp     [r15], rax
0x1800689f8  jz      loc_180068BC5
0x1800689fe  movzx   ecx, word ptr [rdi+rbp+8]
0x180068a03  lea     r9, [rsp+58h+arg_10]
0x180068a08  lea     r8, [rsp+58h+arg_8]
0x180068a0d  mov     rdx, r15
0x180068a10  call    SplTunMgrQueryInterfaceProperties
0x180068a15  mov     ebx, eax
0x180068a17  mov     ecx, 10000000h
0x180068a1c  test    eax, eax
0x180068a1e  jz      short loc_180068A3C
0x180068a20  mov     r8d, eax
0x180068a23  lea     rdx, aSpltunmgrapply_1; "SplTunMgrApplyFilteringStateUnderLock: "...
0x180068a2a  call    EventWrite0
0x180068a2f  test    esi, esi
0x180068a31  jnz     loc_180068AF3
0x180068a37  jmp     loc_180068BC3
0x180068a3c  movzx   eax, [rsp+58h+arg_10]
0x180068a41  lea     rdx, aSpltunmgrapply_5; "SplTunMgrApplyFilteringStateUnderLock: "...
0x180068a48  movzx   r9d, [rsp+58h+arg_8]
0x180068a4e  mov     r8d, [rdi+rbp+18h]
0x180068a53  mov     dword ptr [rsp+58h+var_38], eax
0x180068a57  call    EventWrite0
0x180068a5c  test    esi, esi
0x180068a5e  jz      loc_180068B31
0x180068a64  movzx   eax, word ptr [rdi+rbp+8]
0x180068a69  lea     rdx, g_ProtocolStateSplTunMgr
0x180068a70  sub     ax, 2
0x180068a74  neg     ax
0x180068a77  sbb     rcx, rcx
0x180068a7a  and     ecx, 68h
0x180068a7d  cmp     dword ptr [rcx+rdx+48h], 0
0x180068a82  jz      short loc_180068AB0
0x180068a84  cmp     [rsp+58h+arg_8], 0
0x180068a89  jnz     short loc_180068AB7
0x180068a8b  add     rcx, 40h ; '@'
0x180068a8f  add     rcx, rdx; Row
0x180068a92  mov     rax, [rcx]
0x180068a95  cmp     [r15], rax
0x180068a98  jnz     short loc_180068AB0
0x180068a9a  call    cs:__imp_CreateIpForwardEntry2
0x180068aa1  nop     dword ptr [rax+rax+00h]
0x180068aa6  mov     ebx, eax
0x180068aa8  test    eax, eax
0x180068aaa  jnz     loc_180068BCD
0x180068ab0  cmp     [rsp+58h+arg_8], 0
0x180068ab5  jz      short loc_180068AC2
0x180068ab7  cmp     [rsp+58h+arg_10], 0
0x180068abc  jnz     loc_180068BC5
0x180068ac2  movzx   ecx, word ptr [rdi+rbp+8]
0x180068ac7  mov     r9b, 1
0x180068aca  mov     r8b, r9b
0x180068acd  mov     rdx, r15
0x180068ad0  call    SplTunMgrSetInterfaceProperties
0x180068ad5  mov     ebx, eax
0x180068ad7  test    eax, eax
0x180068ad9  jz      loc_180068BC5
0x180068adf  lea     rdx, aSpltunmgrapply; "SplTunMgrApplyFilteringStateUnderLock: "...
0x180068ae6  mov     r8d, eax
0x180068ae9  mov     ecx, 10000000h
0x180068aee  call    EventWrite0
0x180068af3  mov     rdi, [rsp+58h+Table]
0x180068af8  test    rdi, rdi
0x180068afb  jz      short loc_180068B0C
0x180068afd  mov     rcx, rdi; Memory
0x180068b00  call    cs:__imp_FreeMibTable
0x180068b07  nop     dword ptr [rax+rax+00h]
0x180068b0c  lea     rdx, aLeavingSpltunm_3; "Leaving: SplTunMgrApplyFilteringStateUn"...
0x180068b13  mov     ecx, 20000h
0x180068b18  call    EventWriteLeaveEx
0x180068b1d  mov     eax, ebx
0x180068b1f  mov     rbx, [rsp+58h+arg_0]
0x180068b24  add     rsp, 30h
0x180068b28  pop     r15
0x180068b2a  pop     r12
0x180068b2c  pop     rdi
0x180068b2d  pop     rsi
0x180068b2e  pop     rbp
0x180068b2f  retn
0x180068b31  cmp     [rsp+58h+arg_8], 0
0x180068b36  jnz     short loc_180068B3F
0x180068b38  cmp     [rsp+58h+arg_10], 0
0x180068b3d  jz      short loc_180068B6E
0x180068b3f  movzx   ecx, word ptr [rdi+rbp+8]
0x180068b44  xor     r9d, r9d
0x180068b47  xor     r8d, r8d
0x180068b4a  mov     rdx, r15
0x180068b4d  call    SplTunMgrSetInterfaceProperties
0x180068b52  mov     ebx, eax
0x180068b54  test    eax, eax
0x180068b56  jz      short loc_180068B6E
0x180068b58  mov     r8d, eax
0x180068b5b  lea     rdx, aSpltunmgrapply; "SplTunMgrApplyFilteringStateUnderLock: "...
0x180068b62  mov     ecx, 10000000h
0x180068b67  call    EventWrite0
0x180068b6c  xor     ebx, ebx
0x180068b6e  movzx   eax, word ptr [rdi+rbp+8]
0x180068b73  lea     rdx, g_ProtocolStateSplTunMgr
0x180068b7a  sub     ax, 2
0x180068b7e  neg     ax
0x180068b81  sbb     rcx, rcx
0x180068b84  and     ecx, 68h
0x180068b87  cmp     dword ptr [rcx+rdx+48h], 0
0x180068b8c  jz      short loc_180068BC5
0x180068b8e  add     rcx, 40h ; '@'
0x180068b92  add     rcx, rdx; Row
0x180068b95  mov     rax, [rcx]
0x180068b98  cmp     [r15], rax
0x180068b9b  jnz     short loc_180068BC5
0x180068b9d  call    cs:__imp_DeleteIpForwardEntry2
0x180068ba4  nop     dword ptr [rax+rax+00h]
0x180068ba9  mov     ebx, eax
0x180068bab  test    eax, eax
0x180068bad  jz      short loc_180068BC5
0x180068baf  mov     r8d, eax
0x180068bb2  lea     rdx, aSpltunmgrapply_0; "SplTunMgrApplyFilteringStateUnderLock: "...
0x180068bb9  mov     ecx, 10000000h
0x180068bbe  call    EventWrite0
0x180068bc3  xor     ebx, ebx
0x180068bc5  inc     r12d
0x180068bc8  jmp     loc_1800689CF
0x180068bcd  lea     rdx, aSpltunmgrapply_4; "SplTunMgrApplyFilteringStateUnderLock: "...
0x180068bd4  jmp     loc_180068AE6
```
