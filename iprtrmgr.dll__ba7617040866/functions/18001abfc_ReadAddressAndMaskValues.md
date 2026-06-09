# ReadAddressAndMaskValues

- ea: `0x18001abfc`
- end: `0x18001afa8`
- name: `ReadAddressAndMaskValues`
- size: `940`
- prototype: `__int64 __fastcall(HKEY hKey, LPCSTR lpValueName, LPCSTR, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001afb0`

## callees

- `0x18000ac60`
- `0x18001a8ec`
- `0x18001abfc`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001ad0c`
- `KERNEL32!HeapFree` at `0x18001adc6`
- `KERNEL32!HeapFree` at `0x18001ae5a`
- `KERNEL32!HeapFree` at `0x18001ae6c`
- `KERNEL32!HeapFree` at `0x18001aeee`
- `KERNEL32!HeapFree` at `0x18001af00`
- `KERNEL32!HeapFree` at `0x18001af16`
- `KERNEL32!HeapFree` at `0x18001ad0c`
- `KERNEL32!HeapFree` at `0x18001adc6`
- `KERNEL32!HeapFree` at `0x18001ae5a`
- `KERNEL32!HeapFree` at `0x18001ae6c`
- `KERNEL32!HeapFree` at `0x18001aeee`
- `KERNEL32!HeapFree` at `0x18001af00`
- `KERNEL32!HeapFree` at `0x18001af16`
- `KERNEL32!HeapAlloc` at `0x18001acaa`
- `KERNEL32!HeapAlloc` at `0x18001adac`
- `KERNEL32!HeapAlloc` at `0x18001acaa`
- `KERNEL32!HeapAlloc` at `0x18001adac`
- `ADVAPI32!RegQueryValueExA` at `0x18001ac7d`
- `ADVAPI32!RegQueryValueExA` at `0x18001acf4`
- `ADVAPI32!RegQueryValueExA` at `0x18001ad82`
- `ADVAPI32!RegQueryValueExA` at `0x18001ae41`
- `ADVAPI32!RegQueryValueExA` at `0x18001ac7d`
- `ADVAPI32!RegQueryValueExA` at `0x18001acf4`
- `ADVAPI32!RegQueryValueExA` at `0x18001ad82`
- `ADVAPI32!RegQueryValueExA` at `0x18001ae41`

## string_xrefs

- `0x18001af4e`: `ReadAddressAndMaskValues: Registry reported size = %d with error %d for size of %hs`
- `0x18001ade8`: `ReadAddressAndMaskValues: Error allocating %d bytes for %hs`
- `0x18001ad1d`: `ReadAddressAndMaskValues: Error %d reading %hs from registry`
- `0x18001ae7d`: `ReadAddressAndMaskValues: Error %d reading %hs from registry`

## pseudocode

```c
__int64 __fastcall ReadAddressAndMaskValues(HKEY hKey, LPCSTR lpValueName, LPCSTR a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // eax
  BYTE *lpData; // rdi
  DWORD v11; // r8d
  LPCSTR v12; // r9
  unsigned int v13; // esi
  unsigned int v15; // esi
  BYTE *v16; // rsi
  unsigned int v17; // r14d
  unsigned int v18; // ebx
  DWORD lpcbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[2044]; // [rsp+44h] [rbp-BCh] BYREF

  Type = 0;
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  lpcbData = 0;
  cbData = 0;
  v9 = RegQueryValueExA(hKey, lpValueName, 0, &Type, 0, &cbData);
  if ( !cbData || v9 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v22) = 0;
      FormatRRASErrorString(
        &v22,
        L"ReadAddressAndMaskValues: Registry reported size = %d with error %d for size of %hs",
        cbData,
        v9,
        lpValueName);
LABEL_29:
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v22);
    }
    return 1015;
  }
  lpData = (BYTE *)HeapAlloc(IPRouterHeap, 8u, cbData + 4);
  if ( !lpData )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v11 = cbData;
      v12 = lpValueName;
      LOWORD(v22) = 0;
      goto LABEL_16;
    }
    return 8;
  }
  v13 = RegQueryValueExA(hKey, lpValueName, 0, &Type, lpData, &cbData);
  if ( v13 )
  {
    HeapFree(IPRouterHeap, 0, lpData);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v22) = 0;
      FormatRRASErrorString(&v22, L"ReadAddressAndMaskValues: Error %d reading %hs from registry", v13, lpValueName);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v22);
    }
    return v13;
  }
  v15 = RegQueryValueExA(hKey, a3, 0, &Type, 0, &lpcbData);
  if ( !lpcbData || v15 )
  {
    HeapFree(IPRouterHeap, 0, lpData);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v22) = 0;
      FormatRRASErrorString(
        &v22,
        L"ReadAddressAndMaskValues: Registry reported size = %d with error %d for size of %hs",
        lpcbData,
        v15,
        a3);
      goto LABEL_29;
    }
    return 1015;
  }
  v16 = (BYTE *)HeapAlloc(IPRouterHeap, 8u, lpcbData + 4);
  if ( !v16 )
  {
    HeapFree(IPRouterHeap, 0, lpData);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v11 = lpcbData;
      LOWORD(v22) = 0;
      v12 = a3;
LABEL_16:
      FormatRRASErrorString(&v22, L"ReadAddressAndMaskValues: Error allocating %d bytes for %hs", v11 + 4, v12);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v22);
    }
    return 8;
  }
  v17 = RegQueryValueExA(hKey, a3, 0, &Type, v16, &lpcbData);
  if ( v17 )
  {
    HeapFree(IPRouterHeap, 0, lpData);
    HeapFree(IPRouterHeap, 0, v16);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v22) = 0;
      FormatRRASErrorString(&v22, L"ReadAddressAndMaskValues: Error %d reading %hs from registry", v17, a3);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v22);
    }
    return v17;
  }
  else
  {
    v18 = ParseAddressAndMask((char *)lpData, a4, a5);
    HeapFree(IPRouterHeap, 0, lpData);
    HeapFree(IPRouterHeap, 0, v16);
    return v18;
  }
}

```

## disassembly

```asm
0x18001abfc  push    rbp
0x18001abfe  push    rbx
0x18001abff  push    rsi
0x18001ac00  push    rdi
0x18001ac01  push    r12
0x18001ac03  push    r13
0x18001ac05  push    r14
0x18001ac07  push    r15
0x18001ac09  lea     rbp, [rsp-758h]
0x18001ac11  sub     rsp, 858h
0x18001ac18  mov     rax, cs:__security_cookie
0x18001ac1f  xor     rax, rsp
0x18001ac22  mov     [rbp+790h+var_50], rax
0x18001ac29  mov     r13, [rbp+790h+arg_20]
0x18001ac30  mov     rbx, r8
0x18001ac33  mov     r14, rdx
0x18001ac36  mov     r15, rcx
0x18001ac39  xor     esi, esi
0x18001ac3b  lea     rcx, [rsp+890h+var_84C]; void *
0x18001ac40  xor     edx, edx; Val
0x18001ac42  mov     [rsp+890h+Type], esi
0x18001ac46  mov     r8d, 7FCh; Size
0x18001ac4c  mov     [rsp+890h+var_850], esi
0x18001ac50  mov     r12, r9
0x18001ac53  call    memset_0
0x18001ac58  lea     rax, [rsp+890h+cbData]
0x18001ac5d  mov     [rsp+890h+var_860], esi
0x18001ac61  mov     [rsp+890h+lpcbData], rax; lpcbData
0x18001ac66  lea     r9, [rsp+890h+Type]; lpType
0x18001ac6b  xor     r8d, r8d; lpReserved
0x18001ac6e  mov     [rsp+890h+lpData], rsi; lpData
0x18001ac73  mov     rdx, r14; lpValueName
0x18001ac76  mov     [rsp+890h+cbData], esi
0x18001ac7a  mov     rcx, r15; hKey
0x18001ac7d  call    cs:__imp_RegQueryValueExA
0x18001ac83  mov     r8d, [rsp+890h+cbData]
0x18001ac88  mov     r9d, eax
0x18001ac8b  test    r8d, r8d
0x18001ac8e  jz      loc_18001AF3B
0x18001ac94  test    eax, eax
0x18001ac96  jnz     loc_18001AF3B
0x18001ac9c  mov     rcx, cs:IPRouterHeap; hHeap
0x18001aca3  lea     edx, [rsi+8]; dwFlags
0x18001aca6  add     r8d, 4; dwBytes
0x18001acaa  call    cs:__imp_HeapAlloc
0x18001acb0  mov     rdi, rax
0x18001acb3  test    rax, rax
0x18001acb6  jnz     short loc_18001ACD7
0x18001acb8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001acbf  jz      loc_18001AE1A
0x18001acc5  mov     r8d, [rsp+890h+cbData]
0x18001acca  mov     r9, r14
0x18001accd  mov     word ptr [rsp+890h+var_850], si
0x18001acd2  jmp     loc_18001ADE4
0x18001acd7  lea     rax, [rsp+890h+cbData]
0x18001acdc  xor     r8d, r8d; lpReserved
0x18001acdf  mov     [rsp+890h+lpcbData], rax; lpcbData
0x18001ace4  lea     r9, [rsp+890h+Type]; lpType
0x18001ace9  mov     rdx, r14; lpValueName
0x18001acec  mov     [rsp+890h+lpData], rdi; lpData
0x18001acf1  mov     rcx, r15; hKey
0x18001acf4  call    cs:__imp_RegQueryValueExA
0x18001acfa  mov     esi, eax
0x18001acfc  test    eax, eax
0x18001acfe  jz      short loc_18001AD61
0x18001ad00  mov     rcx, cs:IPRouterHeap; hHeap
0x18001ad07  mov     r8, rdi; lpMem
0x18001ad0a  xor     edx, edx; dwFlags
0x18001ad0c  call    cs:__imp_HeapFree
0x18001ad12  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001ad19  jz      short loc_18001AD5A
0x18001ad1b  xor     ecx, ecx
0x18001ad1d  lea     rdx, aReadaddressand; "ReadAddressAndMaskValues: Error %d read"...
0x18001ad24  mov     word ptr [rsp+890h+var_850], cx
0x18001ad29  mov     r9, r14
0x18001ad2c  lea     rcx, [rsp+890h+var_850]
0x18001ad31  mov     r8d, esi
0x18001ad34  call    FormatRRASErrorString
0x18001ad39  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001ad40  jz      short loc_18001AD5A
0x18001ad42  lea     r8, [rsp+890h+var_850]
0x18001ad47  lea     rdx, RasRtrMgrTraceError
0x18001ad4e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001ad55  call    McTemplateU0z_EventWriteTransfer
0x18001ad5a  mov     eax, esi
0x18001ad5c  jmp     loc_18001AF85
0x18001ad61  lea     rax, [rsp+890h+var_860]
0x18001ad66  xor     r8d, r8d; lpReserved
0x18001ad69  mov     [rsp+890h+lpcbData], rax; lpcbData
0x18001ad6e  lea     r9, [rsp+890h+Type]; lpType
0x18001ad73  mov     rdx, rbx; lpValueName
0x18001ad76  mov     [rsp+890h+lpData], 0; lpData
0x18001ad7f  mov     rcx, r15; hKey
0x18001ad82  call    cs:__imp_RegQueryValueExA
0x18001ad88  mov     esi, eax
0x18001ad8a  mov     eax, [rsp+890h+var_860]
0x18001ad8e  test    eax, eax
0x18001ad90  jz      loc_18001AF0A
0x18001ad96  test    esi, esi
0x18001ad98  jnz     loc_18001AF0A
0x18001ad9e  mov     rcx, cs:IPRouterHeap; hHeap
0x18001ada5  lea     r8d, [rax+4]; dwBytes
0x18001ada9  lea     edx, [rsi+8]; dwFlags
0x18001adac  call    cs:__imp_HeapAlloc
0x18001adb2  mov     rsi, rax
0x18001adb5  test    rax, rax
0x18001adb8  jnz     short loc_18001AE24
0x18001adba  mov     rcx, cs:IPRouterHeap; hHeap
0x18001adc1  mov     r8, rdi; lpMem
0x18001adc4  xor     edx, edx; dwFlags
0x18001adc6  call    cs:__imp_HeapFree
0x18001adcc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001add3  jz      short loc_18001AE1A
0x18001add5  mov     r8d, [rsp+890h+var_860]
0x18001adda  xor     eax, eax
0x18001addc  mov     word ptr [rsp+890h+var_850], ax
0x18001ade1  mov     r9, rbx
0x18001ade4  add     r8d, 4
0x18001ade8  lea     rdx, aReadaddressand_0; "ReadAddressAndMaskValues: Error allocat"...
0x18001adef  lea     rcx, [rsp+890h+var_850]
0x18001adf4  call    FormatRRASErrorString
0x18001adf9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001ae00  jz      short loc_18001AE1A
0x18001ae02  lea     r8, [rsp+890h+var_850]
0x18001ae07  lea     rdx, RasRtrMgrTraceError
0x18001ae0e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001ae15  call    McTemplateU0z_EventWriteTransfer
0x18001ae1a  mov     eax, 8
0x18001ae1f  jmp     loc_18001AF85
0x18001ae24  lea     rax, [rsp+890h+var_860]
0x18001ae29  xor     r8d, r8d; lpReserved
0x18001ae2c  mov     [rsp+890h+lpcbData], rax; lpcbData
0x18001ae31  lea     r9, [rsp+890h+Type]; lpType
0x18001ae36  mov     rdx, rbx; lpValueName
0x18001ae39  mov     [rsp+890h+lpData], rsi; lpData
0x18001ae3e  mov     rcx, r15; hKey
0x18001ae41  call    cs:__imp_RegQueryValueExA
0x18001ae47  mov     r14d, eax
0x18001ae4a  test    eax, eax
0x18001ae4c  jz      short loc_18001AEC2
0x18001ae4e  mov     rcx, cs:IPRouterHeap; hHeap
0x18001ae55  mov     r8, rdi; lpMem
0x18001ae58  xor     edx, edx; dwFlags
0x18001ae5a  call    cs:__imp_HeapFree
0x18001ae60  mov     rcx, cs:IPRouterHeap; hHeap
0x18001ae67  mov     r8, rsi; lpMem
0x18001ae6a  xor     edx, edx; dwFlags
0x18001ae6c  call    cs:__imp_HeapFree
0x18001ae72  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001ae79  jz      short loc_18001AEBA
0x18001ae7b  xor     eax, eax
0x18001ae7d  lea     rdx, aReadaddressand; "ReadAddressAndMaskValues: Error %d read"...
0x18001ae84  mov     r9, rbx
0x18001ae87  mov     word ptr [rsp+890h+var_850], ax
0x18001ae8c  mov     r8d, r14d
0x18001ae8f  lea     rcx, [rsp+890h+var_850]
0x18001ae94  call    FormatRRASErrorString
0x18001ae99  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001aea0  jz      short loc_18001AEBA
0x18001aea2  lea     r8, [rsp+890h+var_850]
0x18001aea7  lea     rdx, RasRtrMgrTraceError
0x18001aeae  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001aeb5  call    McTemplateU0z_EventWriteTransfer
0x18001aeba  mov     eax, r14d
0x18001aebd  jmp     loc_18001AF85
0x18001aec2  mov     r9d, [rsp+890h+var_860]
0x18001aec7  mov     r8, rsi
0x18001aeca  mov     edx, [rsp+890h+cbData]
0x18001aece  mov     rcx, rdi; Str
0x18001aed1  mov     [rsp+890h+lpcbData], r13; __int64
0x18001aed6  mov     [rsp+890h+lpData], r12; __int64
0x18001aedb  call    ParseAddressAndMask
0x18001aee0  mov     rcx, cs:IPRouterHeap; hHeap
0x18001aee7  mov     r8, rdi; lpMem
0x18001aeea  xor     edx, edx; dwFlags
0x18001aeec  mov     ebx, eax
0x18001aeee  call    cs:__imp_HeapFree
0x18001aef4  mov     rcx, cs:IPRouterHeap; hHeap
0x18001aefb  mov     r8, rsi; lpMem
0x18001aefe  xor     edx, edx; dwFlags
0x18001af00  call    cs:__imp_HeapFree
0x18001af06  mov     eax, ebx
0x18001af08  jmp     short loc_18001AF85
0x18001af0a  mov     rcx, cs:IPRouterHeap; hHeap
0x18001af11  mov     r8, rdi; lpMem
0x18001af14  xor     edx, edx; dwFlags
0x18001af16  call    cs:__imp_HeapFree
0x18001af1c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001af23  jz      short loc_18001AF80
0x18001af25  mov     r8d, [rsp+890h+var_860]
0x18001af2a  xor     eax, eax
0x18001af2c  mov     word ptr [rsp+890h+var_850], ax
0x18001af31  mov     r9d, esi
0x18001af34  mov     [rsp+890h+lpData], rbx
0x18001af39  jmp     short loc_18001AF4E
0x18001af3b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001af42  jz      short loc_18001AF80
0x18001af44  mov     word ptr [rsp+890h+var_850], si
0x18001af49  mov     [rsp+890h+lpData], r14
0x18001af4e  lea     rdx, aReadaddressand_1; "ReadAddressAndMaskValues: Registry repo"...
0x18001af55  lea     rcx, [rsp+890h+var_850]
0x18001af5a  call    FormatRRASErrorString
0x18001af5f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001af66  jz      short loc_18001AF80
0x18001af68  lea     r8, [rsp+890h+var_850]
0x18001af6d  lea     rdx, RasRtrMgrTraceError
0x18001af74  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001af7b  call    McTemplateU0z_EventWriteTransfer
0x18001af80  mov     eax, 3F7h
0x18001af85  mov     rcx, [rbp+790h+var_50]
0x18001af8c  xor     rcx, rsp; StackCookie
0x18001af8f  call    __security_check_cookie
0x18001af94  add     rsp, 858h
0x18001af9b  pop     r15
0x18001af9d  pop     r14
0x18001af9f  pop     r13
0x18001afa1  pop     r12
0x18001afa3  pop     rdi
0x18001afa4  pop     rsi
0x18001afa5  pop     rbx
0x18001afa6  pop     rbp
0x18001afa7  retn
```
