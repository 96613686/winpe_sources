# CxPlatDataPathGetLocalAddresses

- ea: `0x1400392d0`
- end: `0x1400394be`
- name: `CxPlatDataPathGetLocalAddresses`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002de24`

## callees

- `0x1400392d0`
- `0x14003e928`
- `0x14003ed00`

## import_xrefs

- `NETIO!GetUnicastIpAddressTable` at `0x140039339`
- `NETIO!GetUnicastIpAddressTable` at `0x140039339`
- `NETIO!FreeMibTable` at `0x140039487`
- `NETIO!FreeMibTable` at `0x14003949c`
- `NETIO!FreeMibTable` at `0x140039487`
- `NETIO!FreeMibTable` at `0x14003949c`
- `NETIO!GetIpInterfaceTable` at `0x140039300`
- `NETIO!GetIpInterfaceTable` at `0x140039300`
- `ntoskrnl!ExAllocatePool2` at `0x140039376`
- `ntoskrnl!ExAllocatePool2` at `0x140039376`

## pseudocode

```c
__int64 __fastcall CxPlatDataPathGetLocalAddresses(__int64 a1, __int64 *a2, ULONG *a3)
{
  NTSTATUS IpInterfaceTable; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // ebx
  const char *v9; // r9
  PMIB_UNICASTIPADDRESS_TABLE v10; // r8
  __int64 Pool2; // rax
  __int64 v12; // rdx
  __int64 v13; // r10
  __int64 v14; // r9
  ULONG NumEntries; // eax
  MIB_IPINTERFACE_ROW *v16; // rdi
  unsigned int v17; // edx
  __int64 v18; // rcx
  __int64 v19; // r11
  int v20; // eax
  PMIB_UNICASTIPADDRESS_TABLE v22; // [rsp+40h] [rbp+20h] BYREF
  PMIB_IPINTERFACE_TABLE Table; // [rsp+58h] [rbp+38h] BYREF

  Table = 0;
  v22 = 0;
  IpInterfaceTable = GetIpInterfaceTable(0, &Table);
  v8 = IpInterfaceTable;
  if ( IpInterfaceTable < 0 )
  {
    if ( (Microsoft_QuicEnableBits & 4) == 0 )
    {
LABEL_5:
      v10 = v22;
      goto LABEL_22;
    }
    v9 = "GetIpInterfaceTable";
LABEL_4:
    McTemplateU0qs_EtwWriteTransfer(v7, v6, (unsigned int)IpInterfaceTable, v9);
    goto LABEL_5;
  }
  IpInterfaceTable = GetUnicastIpAddressTable(0, &v22);
  v8 = IpInterfaceTable;
  if ( IpInterfaceTable < 0 )
  {
    if ( (Microsoft_QuicEnableBits & 4) == 0 )
      goto LABEL_5;
    v9 = "GetUnicastIpAddressTable";
    goto LABEL_4;
  }
  Pool2 = ExAllocatePool2(66, 40LL * v22->NumEntries, 909402961);
  *a2 = Pool2;
  v13 = Pool2;
  if ( !Pool2 )
  {
    v8 = -1073741801;
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(v22->NumEntries, v12, "Addresses", 40LL * v22->NumEntries);
    goto LABEL_5;
  }
  v10 = v22;
  v14 = 0;
  NumEntries = v22->NumEntries;
  *a3 = v22->NumEntries;
  if ( NumEntries )
  {
    do
    {
      v16 = 0;
      v17 = 0;
      if ( Table->NumEntries )
      {
        while ( 1 )
        {
          v18 = v17;
          if ( Table->Table[v18].InterfaceIndex == v10->Table[v14].InterfaceIndex )
            break;
          if ( ++v17 >= Table->NumEntries )
            goto LABEL_18;
        }
        v16 = &Table->Table[v18];
      }
LABEL_18:
      v19 = 5 * v14;
      *(SOCKADDR_IN *)(v13 + 8 * v19) = v10->Table[v14].Address.Ipv4;
      *(_QWORD *)(v13 + 8 * v19 + 16) = *((_QWORD *)&v10->Table[v14].Address.si_family + 2);
      *(_DWORD *)(v13 + 8 * v19 + 24) = v10->Table[v14].Address.Ipv6.sin6_scope_id;
      *(_DWORD *)(v13 + 8 * v19 + 28) = v22->Table[v14].InterfaceIndex;
      *(_WORD *)(v13 + 8 * v19 + 32) = *((_WORD *)&v22->Table[v14].InterfaceLuid.Info + 3);
      if ( !v16 || (v20 = 1, !v16->Connected) )
        v20 = 2;
      *(_DWORD *)(v13 + 40 * v14 + 36) = v20;
      v14 = (unsigned int)(v14 + 1);
      v10 = v22;
    }
    while ( (unsigned int)v14 < v22->NumEntries );
  }
LABEL_22:
  if ( v10 )
    FreeMibTable(v10);
  if ( Table )
    FreeMibTable(Table);
  return v8;
}

```

## disassembly

```asm
0x1400392d0  mov     [rsp-18h+arg_8], rbx
0x1400392d5  mov     [rsp-18h+arg_10], rsi
0x1400392da  mov     [rsp-18h+arg_0], rcx
0x1400392df  push    rbp
0x1400392e0  push    rdi
0x1400392e1  push    r14
0x1400392e3  mov     rbp, rsp
0x1400392e6  sub     rsp, 20h
0x1400392ea  and     [rbp+Table], 0
0x1400392ef  mov     rsi, rdx
0x1400392f2  and     [rbp+arg_0], 0
0x1400392f7  lea     rdx, [rbp+Table]; Table
0x1400392fb  xor     ecx, ecx; Family
0x1400392fd  mov     rdi, r8
0x140039300  call    cs:__imp_GetIpInterfaceTable
0x140039307  nop     dword ptr [rax+rax+00h]
0x14003930c  mov     ebx, eax
0x14003930e  test    eax, eax
0x140039310  jns     short loc_140039333
0x140039312  test    cs:Microsoft_QuicEnableBits, 4
0x140039319  jz      short loc_14003932A
0x14003931b  lea     r9, aGetipinterface; "GetIpInterfaceTable"
0x140039322  mov     r8d, eax
0x140039325  call    McTemplateU0qs_EtwWriteTransfer
0x14003932a  mov     r8, [rbp+arg_0]
0x14003932e  jmp     loc_14003947F
0x140039333  xor     ecx, ecx; Family
0x140039335  lea     rdx, [rbp+arg_0]; Table
0x140039339  call    cs:__imp_GetUnicastIpAddressTable
0x140039340  nop     dword ptr [rax+rax+00h]
0x140039345  mov     ebx, eax
0x140039347  test    eax, eax
0x140039349  jns     short loc_14003935D
0x14003934b  test    cs:Microsoft_QuicEnableBits, 4
0x140039352  jz      short loc_14003932A
0x140039354  lea     r9, aGetunicastipad; "GetUnicastIpAddressTable"
0x14003935b  jmp     short loc_140039322
0x14003935d  mov     rax, [rbp+arg_0]
0x140039361  mov     r8d, 36346351h
0x140039367  mov     ecx, [rax]
0x140039369  lea     rdx, [rcx+rcx*4]
0x14003936d  mov     ecx, 42h ; 'B'
0x140039372  shl     rdx, 3
0x140039376  call    cs:__imp_ExAllocatePool2
0x14003937d  nop     dword ptr [rax+rax+00h]
0x140039382  mov     [rsi], rax
0x140039385  mov     r10, rax
0x140039388  test    rax, rax
0x14003938b  jnz     short loc_1400393BA
0x14003938d  test    cs:Microsoft_QuicEnableBits, 2
0x140039394  mov     ebx, 0C0000017h
0x140039399  jz      short loc_14003932A
0x14003939b  mov     rax, [rbp+arg_0]
0x14003939f  lea     r8, aAddresses; "Addresses"
0x1400393a6  mov     ecx, [rax]
0x1400393a8  lea     r9, [rcx+rcx*4]
0x1400393ac  shl     r9, 3
0x1400393b0  call    McTemplateU0sx_EtwWriteTransfer
0x1400393b5  jmp     loc_14003932A
0x1400393ba  mov     r8, [rbp+arg_0]
0x1400393be  xor     r9d, r9d
0x1400393c1  mov     eax, [r8]
0x1400393c4  mov     [rdi], eax
0x1400393c6  test    eax, eax
0x1400393c8  jz      loc_14003947F
0x1400393ce  mov     r11, [rbp+Table]
0x1400393d2  xor     edi, edi
0x1400393d4  xor     edx, edx
0x1400393d6  mov     esi, [r11]
0x1400393d9  test    esi, esi
0x1400393db  jz      short loc_140039408
0x1400393dd  lea     rcx, [r9+r9*4]
0x1400393e1  add     rcx, rcx
0x1400393e4  mov     r14d, [r8+rcx*8+30h]
0x1400393e9  mov     eax, edx
0x1400393eb  imul    rcx, rax, 0A8h
0x1400393f2  cmp     [rcx+r11+18h], r14d
0x1400393f7  jz      short loc_140039401
0x1400393f9  inc     edx
0x1400393fb  cmp     edx, esi
0x1400393fd  jb      short loc_1400393E9
0x1400393ff  jmp     short loc_140039408
0x140039401  lea     rdi, [r11+8]
0x140039405  add     rdi, rcx
0x140039408  lea     r11, [r9+r9*4]
0x14003940c  lea     rdx, [r9+r9*4]
0x140039410  add     rdx, rdx
0x140039413  movups  xmm0, xmmword ptr [r8+rdx*8+8]
0x140039419  movups  xmmword ptr [r10+r11*8], xmm0
0x14003941e  movsd   xmm1, qword ptr [r8+rdx*8+18h]
0x140039425  movsd   qword ptr [r10+r11*8+10h], xmm1
0x14003942c  mov     eax, [r8+rdx*8+20h]
0x140039431  mov     [r10+r11*8+18h], eax
0x140039436  mov     rax, [rbp+arg_0]
0x14003943a  mov     ecx, [rax+rdx*8+30h]
0x14003943e  mov     [r10+r11*8+1Ch], ecx
0x140039443  mov     rax, [rbp+arg_0]
0x140039447  movzx   ecx, word ptr [rax+rdx*8+2Eh]
0x14003944c  mov     [r10+r11*8+20h], cx
0x140039452  test    rdi, rdi
0x140039455  jz      short loc_140039465
0x140039457  cmp     byte ptr [rdi+9Ch], 0
0x14003945e  mov     eax, 1
0x140039463  jnz     short loc_14003946A
0x140039465  mov     eax, 2
0x14003946a  mov     [r10+r11*8+24h], eax
0x14003946f  inc     r9d
0x140039472  mov     r8, [rbp+arg_0]
0x140039476  cmp     r9d, [r8]
0x140039479  jb      loc_1400393CE
0x14003947f  test    r8, r8
0x140039482  jz      short loc_140039493
0x140039484  mov     rcx, r8; Memory
0x140039487  call    cs:__imp_FreeMibTable
0x14003948e  nop     dword ptr [rax+rax+00h]
0x140039493  mov     rcx, [rbp+Table]; Memory
0x140039497  test    rcx, rcx
0x14003949a  jz      short loc_1400394A8
0x14003949c  call    cs:__imp_FreeMibTable
0x1400394a3  nop     dword ptr [rax+rax+00h]
0x1400394a8  mov     rsi, [rsp+20h+arg_10]
0x1400394ad  mov     eax, ebx
0x1400394af  mov     rbx, [rsp+20h+arg_8]
0x1400394b4  add     rsp, 20h
0x1400394b8  pop     r14
0x1400394ba  pop     rdi
0x1400394bb  pop     rbp
0x1400394bc  retn
```
