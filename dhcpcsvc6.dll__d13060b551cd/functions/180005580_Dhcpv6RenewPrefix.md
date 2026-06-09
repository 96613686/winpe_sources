# Dhcpv6RenewPrefix

- ea: `0x180005580`
- end: `0x180005630`
- name: `Dhcpv6RenewPrefix`
- size: `176`
- prototype: `DWORD __stdcall(LPWSTR adapterName, LPDHCPV6CAPI_CLASSID pclassId, LPDHCPV6PrefixLeaseInformation prefixleaseInfo, DWORD *pdwTimeToWait, DWORD bValidatePrefix)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180003650`
- `0x180005580`
- `0x180005640`
- `0x1800081c0`
- `0x1800082d0`
- `0x180008490`

## pseudocode

```c
DWORD __stdcall Dhcpv6RenewPrefix(
        LPWSTR adapterName,
        LPDHCPV6CAPI_CLASSID pclassId,
        LPDHCPV6PrefixLeaseInformation prefixleaseInfo,
        DWORD *pdwTimeToWait,
        DWORD bValidatePrefix)
{
  int v5; // ebx
  int v6; // esi
  int v7; // ebp
  int v8; // edi
  int v9; // ecx
  DWORD v10; // ebx

  v5 = (int)pdwTimeToWait;
  v6 = (int)prefixleaseInfo;
  v7 = (int)pclassId;
  v8 = (int)adapterName;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(adapterName, 33, WPP_cb48999f8e5838f952918348529d50de_Traceguids, adapterName);
  if ( DhcpIsFSEGuestSystem() )
  {
    v10 = 50;
    if ( (xmmword_18000F160 & 2) != 0 )
      WPP_SF_D(1025, 34, WPP_cb48999f8e5838f952918348529d50de_Traceguids, 50);
  }
  else
  {
    v10 = Dhcpv6RenewPrefixEx(v8, v7, v6, v5, bValidatePrefix, 0);
  }
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_SD(v9, 35, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, v8, v10);
  return v10;
}

```

## disassembly

```asm
0x180005580  push    rbx
0x180005582  push    rbp
0x180005583  push    rsi
0x180005584  push    rdi
0x180005585  sub     rsp, 38h
0x180005589  mov     rbx, r9
0x18000558c  mov     rsi, r8
0x18000558f  mov     rbp, rdx
0x180005592  mov     rdi, rcx
0x180005595  test    byte ptr cs:xmmword_18000F160, 10h
0x18000559c  jz      short loc_1800055B2
0x18000559e  mov     edx, 21h ; '!'
0x1800055a3  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x1800055aa  mov     r9, rcx
0x1800055ad  call    WPP_SF_S
0x1800055b2  call    DhcpIsFSEGuestSystem
0x1800055b7  test    eax, eax
0x1800055b9  jnz     short loc_1800055DF
0x1800055bb  mov     [rsp+58h+var_30], eax
0x1800055bf  mov     r9, rbx
0x1800055c2  mov     eax, [rsp+58h+bValidatePrefix]
0x1800055c9  mov     r8, rsi
0x1800055cc  mov     rdx, rbp
0x1800055cf  mov     [rsp+58h+var_38], eax
0x1800055d3  mov     rcx, rdi
0x1800055d6  call    Dhcpv6RenewPrefixEx
0x1800055db  mov     ebx, eax
0x1800055dd  jmp     short loc_180005604
0x1800055df  mov     ebx, 32h ; '2'
0x1800055e4  test    byte ptr cs:xmmword_18000F160, 2
0x1800055eb  jz      short loc_180005604
0x1800055ed  lea     edx, [rbx-10h]
0x1800055f0  mov     ecx, 401h
0x1800055f5  mov     r9d, ebx
0x1800055f8  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x1800055ff  call    WPP_SF_D
0x180005604  test    byte ptr cs:xmmword_18000F160, 10h
0x18000560b  jz      short loc_180005625
0x18000560d  mov     edx, 23h ; '#'
0x180005612  mov     [rsp+58h+var_38], ebx
0x180005616  mov     r9, rdi
0x180005619  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180005620  call    WPP_SF_SD
0x180005625  mov     eax, ebx
0x180005627  add     rsp, 38h
0x18000562b  pop     rdi
0x18000562c  pop     rsi
0x18000562d  pop     rbp
0x18000562e  pop     rbx
0x18000562f  retn
```
