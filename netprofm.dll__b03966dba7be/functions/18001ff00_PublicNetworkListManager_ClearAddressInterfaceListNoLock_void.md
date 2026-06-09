# PublicNetworkListManager::ClearAddressInterfaceListNoLock(void)

- ea: `0x18001ff00`
- end: `0x18001ffd1`
- name: `?ClearAddressInterfaceListNoLock@PublicNetworkListManager@@AEAAXXZ`
- size: `209`
- prototype: `void __fastcall(PublicNetworkListManager *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022b2c`
- `0x1800299c0`
- `0x18002a294`

## callees

- `0x180006770`
- `0x180006810`
- `0x18000bf8c`
- `0x18001ff00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff8c`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x18001ff7a`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x18001ff7a`

## pseudocode

```c
void __fastcall PublicNetworkListManager::ClearAddressInterfaceListNoLock(PublicNetworkListManager *this)
{
  unsigned int IPPhysicalInterfaceForDestination; // ebp
  _QWORD *v3; // rdi

  IPPhysicalInterfaceForDestination = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  while ( *((_QWORD *)this + 76) )
  {
    v3 = *(_QWORD **)(**((_QWORD **)this + 75) + 16LL);
    std::list<ADDRESS_INTERFACE_DATA *>::_Unchecked_erase();
    if ( v3 )
    {
      if ( v3[41] )
      {
        IPPhysicalInterfaceForDestination = CloseGetIPPhysicalInterfaceForDestination(v3 + 41);
        v3[41] = 0;
      }
    }
    CoTaskMemFree(v3);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      163,
      &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
      IPPhysicalInterfaceForDestination);
}

```

## disassembly

```asm
0x18001ff00  mov     [rsp+arg_8], rbx
0x18001ff05  mov     [rsp+arg_10], rbp
0x18001ff0a  push    rsi
0x18001ff0b  push    rdi
0x18001ff0c  push    r15
0x18001ff0e  sub     rsp, 20h
0x18001ff12  mov     rsi, rcx
0x18001ff15  xor     ebp, ebp
0x18001ff17  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff1e  lea     r15, WPP_GLOBAL_Control
0x18001ff25  cmp     rcx, r15
0x18001ff28  jz      short loc_18001FF45
0x18001ff2a  test    byte ptr [rcx+1Ch], 8
0x18001ff2e  jz      short loc_18001FF45
0x18001ff30  mov     rcx, [rcx+10h]
0x18001ff34  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x18001ff3b  mov     edx, 0A2h
0x18001ff40  call    WPP_SF_
0x18001ff45  cmp     qword ptr [rsi+260h], 0
0x18001ff4d  jz      short loc_18001FF94
0x18001ff4f  lea     rcx, [rsi+258h]
0x18001ff56  mov     rax, [rcx]
0x18001ff59  mov     rdx, [rax]
0x18001ff5c  mov     rdi, [rdx+10h]
0x18001ff60  call    ?_Unchecked_erase@?$list@PEAUADDRESS_INTERFACE_DATA@@V?$allocator@PEAUADDRESS_INTERFACE_DATA@@@std@@@std@@AEAAPEAU?$_List_node@PEAUADDRESS_INTERFACE_DATA@@PEAX@2@QEAU32@@Z; std::list<ADDRESS_INTERFACE_DATA *>::_Unchecked_erase(std::_List_node<ADDRESS_INTERFACE_DATA *,void *> * const)
0x18001ff65  test    rdi, rdi
0x18001ff68  jz      short loc_18001FF89
0x18001ff6a  lea     rbx, [rdi+148h]
0x18001ff71  cmp     qword ptr [rbx], 0
0x18001ff75  jz      short loc_18001FF89
0x18001ff77  mov     rcx, rbx
0x18001ff7a  call    cs:__imp_CloseGetIPPhysicalInterfaceForDestination
0x18001ff80  mov     ebp, eax
0x18001ff82  mov     qword ptr [rbx], 0
0x18001ff89  mov     rcx, rdi; pv
0x18001ff8c  call    cs:__imp_CoTaskMemFree
0x18001ff92  jmp     short loc_18001FF45
0x18001ff94  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff9b  cmp     rcx, r15
0x18001ff9e  jz      short loc_18001FFBE
0x18001ffa0  test    byte ptr [rcx+1Ch], 8
0x18001ffa4  jz      short loc_18001FFBE
0x18001ffa6  mov     rcx, [rcx+10h]
0x18001ffaa  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x18001ffb1  mov     edx, 0A3h
0x18001ffb6  mov     r9d, ebp
0x18001ffb9  call    WPP_SF_d
0x18001ffbe  mov     rbx, [rsp+38h+arg_8]
0x18001ffc3  mov     rbp, [rsp+38h+arg_10]
0x18001ffc8  add     rsp, 20h
0x18001ffcc  pop     r15
0x18001ffce  pop     rdi
0x18001ffcf  pop     rsi
0x18001ffd0  retn
```
