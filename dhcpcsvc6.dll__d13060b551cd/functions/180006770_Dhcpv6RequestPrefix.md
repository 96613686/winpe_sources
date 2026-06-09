# Dhcpv6RequestPrefix

- ea: `0x180006770`
- end: `0x180006815`
- name: `Dhcpv6RequestPrefix`
- size: `165`
- prototype: `DWORD __stdcall(LPWSTR adapterName, LPDHCPV6CAPI_CLASSID pclassId, LPDHCPV6PrefixLeaseInformation prefixleaseInfo, DWORD *pdwTimeToWait)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180003650`
- `0x180006770`
- `0x180006820`
- `0x1800081c0`
- `0x1800082d0`
- `0x180008490`

## pseudocode

```c
DWORD __stdcall Dhcpv6RequestPrefix(
        LPWSTR adapterName,
        LPDHCPV6CAPI_CLASSID pclassId,
        LPDHCPV6PrefixLeaseInformation prefixleaseInfo,
        DWORD *pdwTimeToWait)
{
  int v4; // ebx
  int v5; // esi
  int v6; // ebp
  int v7; // edi
  int v8; // ecx
  DWORD v9; // ebx

  v4 = (int)pdwTimeToWait;
  v5 = (int)prefixleaseInfo;
  v6 = (int)pclassId;
  v7 = (int)adapterName;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(adapterName, 25, WPP_cb48999f8e5838f952918348529d50de_Traceguids, adapterName);
  if ( DhcpIsFSEGuestSystem() )
  {
    v9 = 50;
    if ( (xmmword_18000F160 & 2) != 0 )
      WPP_SF_D(1025, 26, WPP_cb48999f8e5838f952918348529d50de_Traceguids, 50);
  }
  else
  {
    v9 = Dhcpv6RequestPrefixEx(v7, v6, v5, v4, 0);
  }
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_SD(v8, 27, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, v7, v9);
  return v9;
}

```

## disassembly

```asm
0x180006770  push    rbx
0x180006772  push    rbp
0x180006773  push    rsi
0x180006774  push    rdi
0x180006775  sub     rsp, 38h
0x180006779  mov     rbx, r9
0x18000677c  mov     rsi, r8
0x18000677f  mov     rbp, rdx
0x180006782  mov     rdi, rcx
0x180006785  test    byte ptr cs:xmmword_18000F160, 10h
0x18000678c  jz      short loc_1800067A2
0x18000678e  mov     edx, 19h
0x180006793  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x18000679a  mov     r9, rcx
0x18000679d  call    WPP_SF_S
0x1800067a2  call    DhcpIsFSEGuestSystem
0x1800067a7  test    eax, eax
0x1800067a9  jnz     short loc_1800067C4
0x1800067ab  mov     r9, rbx
0x1800067ae  mov     [rsp+58h+var_38], eax
0x1800067b2  mov     r8, rsi
0x1800067b5  mov     rdx, rbp
0x1800067b8  mov     rcx, rdi
0x1800067bb  call    Dhcpv6RequestPrefixEx
0x1800067c0  mov     ebx, eax
0x1800067c2  jmp     short loc_1800067E9
0x1800067c4  mov     ebx, 32h ; '2'
0x1800067c9  test    byte ptr cs:xmmword_18000F160, 2
0x1800067d0  jz      short loc_1800067E9
0x1800067d2  lea     edx, [rbx-18h]
0x1800067d5  mov     ecx, 401h
0x1800067da  mov     r9d, ebx
0x1800067dd  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x1800067e4  call    WPP_SF_D
0x1800067e9  test    byte ptr cs:xmmword_18000F160, 10h
0x1800067f0  jz      short loc_18000680A
0x1800067f2  mov     edx, 1Bh
0x1800067f7  mov     [rsp+58h+var_38], ebx
0x1800067fb  mov     r9, rdi
0x1800067fe  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180006805  call    WPP_SF_SD
0x18000680a  mov     eax, ebx
0x18000680c  add     rsp, 38h
0x180006810  pop     rdi
0x180006811  pop     rsi
0x180006812  pop     rbp
0x180006813  pop     rbx
0x180006814  retn
```
