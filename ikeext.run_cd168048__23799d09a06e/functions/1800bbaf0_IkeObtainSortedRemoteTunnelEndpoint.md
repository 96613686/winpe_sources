# IkeObtainSortedRemoteTunnelEndpoint

- ea: `0x1800bbaf0`
- end: `0x1800bbc8c`
- name: `IkeObtainSortedRemoteTunnelEndpoint`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800bba50`

## callees

- `0x1800037c4`
- `0x1800061ec`
- `0x180008388`
- `0x1800163b0`
- `0x18004aa3c`
- `0x180050850`
- `0x1800bb4fc`
- `0x1800bb68c`
- `0x1800bb6c4`
- `0x1800bbaf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbbd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbbd0`
- `IPHLPAPI!FreeMibTable` at `0x1800bbc49`
- `IPHLPAPI!FreeMibTable` at `0x1800bbc49`
- `IPHLPAPI!CreateSortedAddressPairs` at `0x1800bbbc6`
- `IPHLPAPI!CreateSortedAddressPairs` at `0x1800bbbc6`

## string_xrefs

- `0x1800bbbdc`: `CreateSortedAddressPairs`

## pseudocode

```c
__int64 __fastcall IkeObtainSortedRemoteTunnelEndpoint(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // r8
  __int64 TunnelAddressFromSortedList; // rbx
  ULONG v8; // r9d
  __int64 v9; // rdi
  DWORD LastError; // eax
  __int64 v11; // rcx
  PSOCKADDR_IN6 v12; // rax
  __int64 v13; // rcx
  PSOCKADDR_IN6 DestinationAddressList; // [rsp+40h] [rbp-30h] BYREF
  SOCKADDR_IN6_LH *v16; // [rsp+48h] [rbp-28h] BYREF
  ULONG SortedAddressPairCount; // [rsp+50h] [rbp-20h] BYREF
  PSOCKADDR_IN6_PAIR SortedAddressPairList; // [rsp+58h] [rbp-18h] BYREF

  DestinationAddressList = 0;
  v16 = 0;
  SortedAddressPairList = 0;
  SortedAddressPairCount = 0;
  TraceLogHelper("IkeObtainSortedRemoteTunnelEndpoint", 1);
  TunnelAddressFromSortedList = WfpMemAllocArray(*(unsigned int *)(a2 + 56), 28, v6, &DestinationAddressList);
  if ( !TunnelAddressFromSortedList )
  {
    v8 = *(_DWORD *)(a2 + 56);
    v9 = 0;
    if ( v8 )
    {
      while ( 1 )
      {
        TunnelAddressFromSortedList = IkeConvertAddressForSort(
                                        *(_QWORD *)(a2 + 64) + 20 * v9,
                                        &DestinationAddressList[(unsigned int)v9]);
        if ( TunnelAddressFromSortedList )
          break;
        v8 = *(_DWORD *)(a2 + 56);
        v9 = (unsigned int)(v9 + 1);
        if ( (unsigned int)v9 >= v8 )
          goto LABEL_5;
      }
    }
    else
    {
LABEL_5:
      if ( CreateSortedAddressPairs(
             0,
             0,
             DestinationAddressList,
             v8,
             2u,
             &SortedAddressPairList,
             &SortedAddressPairCount) )
      {
        LastError = GetLastError();
        TunnelAddressFromSortedList = WfpReportSysErrorAsWinError(v11, "CreateSortedAddressPairs", LastError, 1);
      }
      else
      {
        TunnelAddressFromSortedList = FindTunnelAddressFromSortedList(
                                        a1,
                                        SortedAddressPairList,
                                        SortedAddressPairCount,
                                        &v16);
        if ( !TunnelAddressFromSortedList )
        {
          v12 = v16;
          if ( !v16 )
            v12 = DestinationAddressList;
          if ( IN6_IS_ADDR_V4MAPPED(&v12->sin6_addr) )
            *(_DWORD *)(a3 + 20) = *(_DWORD *)(v13 + 12);
          else
            *(_OWORD *)(a3 + 20) = *(_OWORD *)v13;
        }
      }
    }
  }
  WfpMemFree(&DestinationAddressList);
  if ( SortedAddressPairList )
    FreeMibTable(SortedAddressPairList);
  TraceLogHelper("IkeObtainSortedRemoteTunnelEndpoint", 0);
  return IkeReturnError(TunnelAddressFromSortedList, "IkeObtainSortedRemoteTunnelEndpoint");
}

```

## disassembly

```asm
0x1800bbaf0  mov     [rsp-28h+arg_18], rbx
0x1800bbaf5  push    rbp
0x1800bbaf6  push    rsi
0x1800bbaf7  push    rdi
0x1800bbaf8  push    r12
0x1800bbafa  push    r15
0x1800bbafc  mov     rbp, rsp
0x1800bbaff  sub     rsp, 70h
0x1800bbb03  mov     rax, cs:__security_cookie
0x1800bbb0a  xor     rax, rsp
0x1800bbb0d  mov     [rbp+var_10], rax
0x1800bbb11  mov     rsi, rdx
0x1800bbb14  mov     [rbp+DestinationAddressList], 0
0x1800bbb1c  mov     r12, rcx
0x1800bbb1f  mov     [rbp+var_28], 0
0x1800bbb27  mov     edx, 1
0x1800bbb2c  mov     [rbp+var_18], 0
0x1800bbb34  lea     rcx, aIkeobtainsorte; "IkeObtainSortedRemoteTunnelEndpoint"
0x1800bbb3b  mov     [rbp+var_20], 0
0x1800bbb42  mov     r15, r8
0x1800bbb45  call    TraceLogHelper
0x1800bbb4a  mov     ecx, [rsi+38h]
0x1800bbb4d  lea     r9, [rbp+DestinationAddressList]
0x1800bbb51  mov     edx, 1Ch
0x1800bbb56  call    WfpMemAllocArray
0x1800bbb5b  mov     rbx, rax
0x1800bbb5e  test    rax, rax
0x1800bbb61  jnz     loc_1800BBC37
0x1800bbb67  mov     r9d, [rsi+38h]
0x1800bbb6b  xor     edi, edi
0x1800bbb6d  test    r9d, r9d
0x1800bbb70  jz      short loc_1800BBBA4
0x1800bbb72  mov     eax, edi
0x1800bbb74  lea     rcx, [rdi+rdi*4]
0x1800bbb78  imul    rdx, rax, 1Ch
0x1800bbb7c  mov     rax, [rsi+40h]
0x1800bbb80  add     rdx, [rbp+DestinationAddressList]
0x1800bbb84  lea     rcx, [rax+rcx*4]
0x1800bbb88  call    IkeConvertAddressForSort
0x1800bbb8d  mov     rbx, rax
0x1800bbb90  test    rax, rax
0x1800bbb93  jnz     loc_1800BBC37
0x1800bbb99  mov     r9d, [rsi+38h]; DestinationAddressCount
0x1800bbb9d  inc     edi
0x1800bbb9f  cmp     edi, r9d
0x1800bbba2  jb      short loc_1800BBB72
0x1800bbba4  mov     r8, [rbp+DestinationAddressList]; DestinationAddressList
0x1800bbba8  lea     rax, [rbp+var_20]
0x1800bbbac  mov     [rsp+70h+SortedAddressPairCount], rax; SortedAddressPairCount
0x1800bbbb1  xor     edx, edx; SourceAddressCount
0x1800bbbb3  lea     rax, [rbp+var_18]
0x1800bbbb7  xor     ecx, ecx; SourceAddressList
0x1800bbbb9  mov     [rsp+70h+SortedAddressPairList], rax; SortedAddressPairList
0x1800bbbbe  mov     [rsp+70h+AddressSortOptions], 2; AddressSortOptions
0x1800bbbc6  call    cs:__imp_CreateSortedAddressPairs
0x1800bbbcc  test    eax, eax
0x1800bbbce  jz      short loc_1800BBBF0
0x1800bbbd0  call    cs:__imp_GetLastError
0x1800bbbd6  mov     r9d, 1
0x1800bbbdc  lea     rdx, aCreatesortedad_0; "CreateSortedAddressPairs"
0x1800bbbe3  mov     r8d, eax
0x1800bbbe6  call    WfpReportSysErrorAsWinError
0x1800bbbeb  mov     rbx, rax
0x1800bbbee  jmp     short loc_1800BBC37
0x1800bbbf0  mov     r8d, [rbp+var_20]
0x1800bbbf4  lea     r9, [rbp+var_28]
0x1800bbbf8  mov     rdx, [rbp+var_18]
0x1800bbbfc  mov     rcx, r12
0x1800bbbff  call    FindTunnelAddressFromSortedList
0x1800bbc04  mov     rbx, rax
0x1800bbc07  test    rax, rax
0x1800bbc0a  jnz     short loc_1800BBC37
0x1800bbc0c  mov     rax, [rbp+var_28]
0x1800bbc10  test    rax, rax
0x1800bbc13  cmovz   rax, [rbp+DestinationAddressList]
0x1800bbc18  lea     rcx, [rax+8]; a
0x1800bbc1c  call    IN6_IS_ADDR_V4MAPPED
0x1800bbc21  test    al, al
0x1800bbc23  jz      short loc_1800BBC2E
0x1800bbc25  mov     eax, [rcx+0Ch]
0x1800bbc28  mov     [r15+14h], eax
0x1800bbc2c  jmp     short loc_1800BBC37
0x1800bbc2e  movups  xmm0, xmmword ptr [rcx]
0x1800bbc31  movdqu  xmmword ptr [r15+14h], xmm0
0x1800bbc37  lea     rcx, [rbp+DestinationAddressList]
0x1800bbc3b  call    WfpMemFree
0x1800bbc40  mov     rcx, [rbp+var_18]; Memory
0x1800bbc44  test    rcx, rcx
0x1800bbc47  jz      short loc_1800BBC4F
0x1800bbc49  call    cs:__imp_FreeMibTable
0x1800bbc4f  xor     edx, edx
0x1800bbc51  lea     rcx, aIkeobtainsorte; "IkeObtainSortedRemoteTunnelEndpoint"
0x1800bbc58  call    TraceLogHelper
0x1800bbc5d  lea     rdx, aIkeobtainsorte; "IkeObtainSortedRemoteTunnelEndpoint"
0x1800bbc64  mov     rcx, rbx
0x1800bbc67  call    IkeReturnError
0x1800bbc6c  mov     rcx, [rbp+var_10]
0x1800bbc70  xor     rcx, rsp; StackCookie
0x1800bbc73  call    __security_check_cookie
0x1800bbc78  mov     rbx, [rsp+70h+arg_18]
0x1800bbc80  add     rsp, 70h
0x1800bbc84  pop     r15
0x1800bbc86  pop     r12
0x1800bbc88  pop     rdi
0x1800bbc89  pop     rsi
0x1800bbc8a  pop     rbp
0x1800bbc8b  retn
```
