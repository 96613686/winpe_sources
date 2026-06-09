# DiscRADIUSServer

- ea: `0x180003f80`
- end: `0x18000410e`
- name: `DiscRADIUSServer`
- size: `398`
- prototype: `__int64 __fastcall(__int64, char, __int64, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003f80`
- `0x180004af8`
- `0x180004e84`

## import_xrefs

- `ISCSIUM!DiscpAddStringToMultiSzList` at `0x180004077`
- `ISCSIUM!DiscpAddStringToMultiSzList` at `0x180004077`
- `ISCSIUM!DiscpRemoveStringFromMultiSzList` at `0x18000408f`
- `ISCSIUM!DiscpRemoveStringFromMultiSzList` at `0x18000408f`
- `ISCSIUM!DiscpGetRegistryValue` at `0x180004030`
- `ISCSIUM!DiscpGetRegistryValue` at `0x180004030`
- `ISCSIUM!DiscpAllocMemory` at `0x180004044`
- `ISCSIUM!DiscpAllocMemory` at `0x180004044`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x180003ff9`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x180003ff9`
- `ISCSIUM!DiscpFreeMemory` at `0x1800040d5`
- `ISCSIUM!DiscpFreeMemory` at `0x1800040d5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800040bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800040bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800040df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800040df`

## pseudocode

```c
__int64 __fastcall DiscRADIUSServer(__int64 a1, char a2, __int64 a3, char a4)
{
  unsigned int v7; // ebx
  unsigned int RegistryValue; // eax
  BYTE *v9; // rax
  BYTE *lpData; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF

  hKey = 0;
  lpData = 0;
  cbData = 0;
  if ( a1 && (!a2 || !a4) )
  {
    v7 = DiscpCheckCallerIsAdmin(a1);
    if ( v7 || !a2 && !a4 )
      return v7;
    v7 = DiscpOpenRegistryKey(&hKey, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Radius", 983103);
    if ( v7 )
    {
LABEL_23:
      DiscpAddRemoveRADIUSServerForHBA(a1, a2);
      return v7;
    }
    RegistryValue = DiscpGetRegistryValue(hKey, 0, L"RADIUSServerAddresses", 7, 0, &lpData, &cbData);
    v7 = RegistryValue;
    if ( RegistryValue == 2 )
    {
      cbData = 2;
      v9 = (BYTE *)DiscpAllocMemory(2);
      lpData = v9;
      if ( v9 )
      {
        *(_WORD *)v9 = 0;
        v7 = 0;
LABEL_13:
        if ( a2 )
          v7 = DiscpAddStringToMultiSzList(&lpData, &cbData, a1);
        if ( a4 )
          v7 = DiscpRemoveStringFromMultiSzList(&lpData, &cbData, a1);
        if ( v7 )
          v7 = -268500981;
        else
          v7 = RegSetValueExW(hKey, L"RADIUSServerAddresses", 0, 7u, lpData, cbData);
        if ( lpData )
          DiscpFreeMemory(lpData);
        goto LABEL_22;
      }
      v7 = 8;
    }
    else if ( !RegistryValue )
    {
      goto LABEL_13;
    }
LABEL_22:
    RegCloseKey(hKey);
    goto LABEL_23;
  }
  return 87;
}

```

## disassembly

```asm
0x180003f80  mov     [rsp-18h+arg_8], rbx
0x180003f85  mov     [rsp-18h+arg_10], rsi
0x180003f8a  push    rbp
0x180003f8b  push    rdi
0x180003f8c  push    r14
0x180003f8e  mov     rbp, rsp
0x180003f91  sub     rsp, 50h
0x180003f95  mov     [rbp+hKey], 0
0x180003f9d  mov     sil, r9b
0x180003fa0  mov     [rbp+var_10], 0
0x180003fa8  mov     dil, dl
0x180003fab  mov     [rbp+arg_0], 0
0x180003fb2  mov     r14, rcx
0x180003fb5  test    rcx, rcx
0x180003fb8  jz      loc_1800040F4
0x180003fbe  test    dl, dl
0x180003fc0  jz      short loc_180003FCB
0x180003fc2  test    r9b, r9b
0x180003fc5  jnz     loc_1800040F4
0x180003fcb  call    DiscpCheckCallerIsAdmin
0x180003fd0  mov     ebx, eax
0x180003fd2  test    eax, eax
0x180003fd4  jnz     loc_1800040F0
0x180003fda  test    dil, dil
0x180003fdd  jnz     short loc_180003FE8
0x180003fdf  test    sil, sil
0x180003fe2  jz      loc_1800040F0
0x180003fe8  mov     r8d, 0F003Fh
0x180003fee  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180003ff5  lea     rcx, [rbp+hKey]
0x180003ff9  call    cs:__imp_DiscpOpenRegistryKey
0x180003fff  mov     ebx, eax
0x180004001  test    eax, eax
0x180004003  jnz     loc_1800040E5
0x180004009  mov     rcx, [rbp+hKey]
0x18000400d  lea     rax, [rbp+arg_0]
0x180004011  mov     [rsp+50h+var_20], rax
0x180004016  lea     r9d, [rbx+7]
0x18000401a  lea     rax, [rbp+var_10]
0x18000401e  xor     edx, edx
0x180004020  mov     qword ptr [rsp+50h+cbData], rax
0x180004025  lea     r8, ValueName; "RADIUSServerAddresses"
0x18000402c  mov     byte ptr [rsp+50h+lpData], bl
0x180004030  call    cs:__imp_DiscpGetRegistryValue
0x180004036  mov     ecx, 2
0x18000403b  mov     ebx, eax
0x18000403d  cmp     eax, ecx
0x18000403f  jnz     short loc_180004063
0x180004041  mov     [rbp+arg_0], ecx
0x180004044  call    cs:__imp_DiscpAllocMemory
0x18000404a  mov     [rbp+var_10], rax
0x18000404e  test    rax, rax
0x180004051  jz      short loc_18000405C
0x180004053  xor     ecx, ecx
0x180004055  mov     [rax], cx
0x180004058  xor     ebx, ebx
0x18000405a  jmp     short loc_180004067
0x18000405c  mov     ebx, 8
0x180004061  jmp     short loc_1800040DB
0x180004063  test    eax, eax
0x180004065  jnz     short loc_1800040DB
0x180004067  test    dil, dil
0x18000406a  jz      short loc_18000407F
0x18000406c  mov     r8, r14
0x18000406f  lea     rdx, [rbp+arg_0]
0x180004073  lea     rcx, [rbp+var_10]
0x180004077  call    cs:__imp_DiscpAddStringToMultiSzList
0x18000407d  mov     ebx, eax
0x18000407f  test    sil, sil
0x180004082  jz      short loc_180004097
0x180004084  mov     r8, r14
0x180004087  lea     rdx, [rbp+arg_0]
0x18000408b  lea     rcx, [rbp+var_10]
0x18000408f  call    cs:__imp_DiscpRemoveStringFromMultiSzList
0x180004095  mov     ebx, eax
0x180004097  test    ebx, ebx
0x180004099  jnz     short loc_1800040C7
0x18000409b  mov     eax, [rbp+arg_0]
0x18000409e  lea     r9d, [rbx+7]; dwType
0x1800040a2  mov     rcx, [rbp+hKey]; hKey
0x1800040a6  lea     rdx, ValueName; "RADIUSServerAddresses"
0x1800040ad  mov     [rsp+50h+cbData], eax; cbData
0x1800040b1  xor     r8d, r8d; Reserved
0x1800040b4  mov     rax, [rbp+var_10]
0x1800040b8  mov     [rsp+50h+lpData], rax; lpData
0x1800040bd  call    cs:__imp_RegSetValueExW
0x1800040c3  mov     ebx, eax
0x1800040c5  jmp     short loc_1800040CC
0x1800040c7  mov     ebx, 0EFFF000Bh
0x1800040cc  mov     rcx, [rbp+var_10]
0x1800040d0  test    rcx, rcx
0x1800040d3  jz      short loc_1800040DB
0x1800040d5  call    cs:__imp_DiscpFreeMemory
0x1800040db  mov     rcx, [rbp+hKey]; hKey
0x1800040df  call    cs:__imp_RegCloseKey
0x1800040e5  mov     dl, dil
0x1800040e8  mov     rcx, r14
0x1800040eb  call    DiscpAddRemoveRADIUSServerForHBA
0x1800040f0  mov     eax, ebx
0x1800040f2  jmp     short loc_1800040F9
0x1800040f4  mov     eax, 57h ; 'W'
0x1800040f9  lea     r11, [rsp+50h+var_s0]
0x1800040fe  mov     rbx, [r11+28h]
0x180004102  mov     rsi, [r11+30h]
0x180004106  mov     rsp, r11
0x180004109  pop     r14
0x18000410b  pop     rdi
0x18000410c  pop     rbp
0x18000410d  retn
```
