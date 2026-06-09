# Dhcpv6DestroyContextEx

- ea: `0x18000bb2c`
- end: `0x18000bc80`
- name: `Dhcpv6DestroyContextEx`
- size: `340`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `18`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009520`
- `0x1800097f0`
- `0x180009a70`
- `0x18000aaa0`
- `0x18000c884`
- `0x180010340`
- `0x1800108f0`
- `0x180010d18`
- `0x18001b314`
- `0x18001c720`
- `0x180026858`
- `0x180026e30`
- `0x180027120`
- `0x180027440`
- `0x180027540`
- `0x1800276b0`
- `0x180027900`
- `0x180027a08`

## callees

- `0x18000bb2c`
- `0x18000c740`
- `0x18000c780`
- `0x18000c7dc`
- `0x180018864`
- `0x18002836c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bbb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bbb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bb90`
- `WS2_32!WSACloseEvent` at `0x18000bbd6`
- `WS2_32!WSACloseEvent` at `0x18000bbd6`

## pseudocode

```c
__int64 __fastcall Dhcpv6DestroyContextEx(__int64 a1, _QWORD *a2, int a3)
{
  _QWORD *v4; // rdx
  int v5; // r8d
  __int64 v6; // rcx
  unsigned int v7; // r8d
  HKEY v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  LPVOID v12; // [rsp+30h] [rbp+8h] BYREF

  v12 = (LPVOID)a1;
  *(_DWORD *)(a1 + 600) = 0;
  *(_QWORD *)(a1 + 544) = 0x7FFFFFFFFFFFFFFFLL;
  Dhcpv6DestroyOptionsList((_QWORD *)(a1 + 616), a2, a3);
  Dhcpv6DestroyOptionsList((_QWORD *)(a1 + 632), v4, v5);
  v7 = *(_DWORD *)(a1 + 664);
  if ( v7 )
    Dhcpv6DelClass(v6, *(_QWORD *)(a1 + 656), v7);
  v8 = *(HKEY *)(a1 + 648);
  if ( v8 )
  {
    RegCloseKey(v8);
    *(_QWORD *)(a1 + 648) = 0;
  }
  v9 = *(void **)(a1 + 584);
  if ( v9 )
  {
    CloseHandle(v9);
    *(_QWORD *)(a1 + 584) = 0;
  }
  v10 = *(void **)(a1 + 8904);
  if ( v10 )
  {
    WSACloseEvent(v10);
    *(_QWORD *)(a1 + 8904) = 0;
  }
  CloseDhcpv6Socket(a1);
  if ( *(_QWORD *)(a1 + 456) )
    DhcpFree((LPVOID *)(a1 + 456));
  if ( *(_QWORD *)(a1 + 480) )
    DhcpFree((LPVOID *)(a1 + 480));
  if ( *(_QWORD *)(a1 + 80) )
    DhcpFree((LPVOID *)(a1 + 80));
  if ( *(_QWORD *)(a1 + 9040) )
    DhcpFree((LPVOID *)(a1 + 9040));
  if ( *(_QWORD *)(a1 + 56) )
    DhcpFree((LPVOID *)(a1 + 56));
  if ( *(_QWORD *)(a1 + 8952) )
    DhcpFree((LPVOID *)(a1 + 8952));
  Dhcpv6FreeIanaAddressList(a1 + 104);
  Dhcpv6FreeIanaAddressList(a1 + 120);
  DhcpFree(&v12);
  return 0;
}

```

## disassembly

```asm
0x18000bb2c  mov     [rsp+arg_0], rcx
0x18000bb31  push    rbx
0x18000bb32  sub     rsp, 20h
0x18000bb36  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000bb40  mov     dword ptr [rcx+258h], 0
0x18000bb4a  mov     [rcx+220h], rax
0x18000bb51  mov     rbx, rcx
0x18000bb54  add     rcx, 268h
0x18000bb5b  call    Dhcpv6DestroyOptionsList
0x18000bb60  lea     rcx, [rbx+278h]
0x18000bb67  call    Dhcpv6DestroyOptionsList
0x18000bb6c  mov     r8d, [rbx+298h]
0x18000bb73  test    r8d, r8d
0x18000bb76  jz      short loc_18000BB84
0x18000bb78  mov     rdx, [rbx+290h]
0x18000bb7f  call    Dhcpv6DelClass
0x18000bb84  mov     rcx, [rbx+288h]; hKey
0x18000bb8b  test    rcx, rcx
0x18000bb8e  jz      short loc_18000BBA7
0x18000bb90  call    cs:__imp_RegCloseKey
0x18000bb97  nop     dword ptr [rax+rax+00h]
0x18000bb9c  mov     qword ptr [rbx+288h], 0
0x18000bba7  mov     rcx, [rbx+248h]; hObject
0x18000bbae  test    rcx, rcx
0x18000bbb1  jz      short loc_18000BBCA
0x18000bbb3  call    cs:__imp_CloseHandle
0x18000bbba  nop     dword ptr [rax+rax+00h]
0x18000bbbf  mov     qword ptr [rbx+248h], 0
0x18000bbca  mov     rcx, [rbx+22C8h]; hEvent
0x18000bbd1  test    rcx, rcx
0x18000bbd4  jz      short loc_18000BBED
0x18000bbd6  call    cs:__imp_WSACloseEvent
0x18000bbdd  nop     dword ptr [rax+rax+00h]
0x18000bbe2  mov     qword ptr [rbx+22C8h], 0
0x18000bbed  mov     rcx, rbx
0x18000bbf0  call    CloseDhcpv6Socket
0x18000bbf5  lea     rcx, [rbx+1C8h]
0x18000bbfc  cmp     qword ptr [rcx], 0
0x18000bc00  jz      short loc_18000BC07
0x18000bc02  call    DhcpFree
0x18000bc07  lea     rcx, [rbx+1E0h]
0x18000bc0e  cmp     qword ptr [rcx], 0
0x18000bc12  jz      short loc_18000BC19
0x18000bc14  call    DhcpFree
0x18000bc19  lea     rcx, [rbx+50h]
0x18000bc1d  cmp     qword ptr [rcx], 0
0x18000bc21  jz      short loc_18000BC28
0x18000bc23  call    DhcpFree
0x18000bc28  lea     rcx, [rbx+2350h]
0x18000bc2f  cmp     qword ptr [rcx], 0
0x18000bc33  jz      short loc_18000BC3A
0x18000bc35  call    DhcpFree
0x18000bc3a  lea     rcx, [rbx+38h]
0x18000bc3e  cmp     qword ptr [rcx], 0
0x18000bc42  jz      short loc_18000BC49
0x18000bc44  call    DhcpFree
0x18000bc49  lea     rcx, [rbx+22F8h]
0x18000bc50  cmp     qword ptr [rcx], 0
0x18000bc54  jz      short loc_18000BC5B
0x18000bc56  call    DhcpFree
0x18000bc5b  lea     rcx, [rbx+68h]
0x18000bc5f  call    Dhcpv6FreeIanaAddressList
0x18000bc64  lea     rcx, [rbx+78h]
0x18000bc68  call    Dhcpv6FreeIanaAddressList
0x18000bc6d  lea     rcx, [rsp+28h+arg_0]
0x18000bc72  call    DhcpFree
0x18000bc77  xor     eax, eax
0x18000bc79  add     rsp, 20h
0x18000bc7d  pop     rbx
0x18000bc7e  retn
```
