# EnableDhcp

- ea: `0x18003f2d0`
- end: `0x18003f419`
- name: `EnableDhcp`
- size: `329`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027c70`
- `0x180027f74`

## callees

- `0x180009038`
- `0x18001a2e4`
- `0x1800202ec`
- `0x18003f2d0`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d200`
- `0x18004d4c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f36c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f36c`

## pseudocode

```c
__int64 __fastcall EnableDhcp(__int64 a1)
{
  int v1; // eax
  HKEY v4; // rcx
  unsigned int v5; // edi
  __int64 v6; // rcx
  int Data; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_DWORD *)(a1 + 792);
  Data = 0;
  if ( v1 )
    return 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    WPP_SF_q(1028, 33, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids, *(_QWORD *)(a1 + 24));
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_S(1028, 34, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids, *(_QWORD *)(a1 + 56));
  }
  v4 = *(HKEY *)(a1 + 728);
  Data = 1;
  v5 = RegSetValueExW(v4, L"EnableDhcp", 0, 4u, (const BYTE *)&Data, 4u);
  if ( v5 )
    goto LABEL_12;
  v5 = SetEventNotification(1, *(_QWORD *)(a1 + 56));
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(v6, DhcpEnabled, *(unsigned int *)(a1 + 48));
  *(_DWORD *)(a1 + 792) = 1;
  *(_DWORD *)(a1 + 788) = 0;
  ScheduleDhcpRenewal(a1, 0, ReObtainInitialParameters, 0);
  if ( v5 )
  {
LABEL_12:
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 35, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids, v5);
  }
  else if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    WPP_SF_(1028, 36, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids);
  }
  return v5;
}

```

## disassembly

```asm
0x18003f2d0  mov     [rsp+arg_8], rbx
0x18003f2d5  push    rdi
0x18003f2d6  sub     rsp, 30h
0x18003f2da  mov     eax, [rcx+318h]
0x18003f2e0  mov     rbx, rcx
0x18003f2e3  mov     [rsp+38h+Data], 0
0x18003f2eb  test    eax, eax
0x18003f2ed  jz      short loc_18003F2F6
0x18003f2ef  xor     eax, eax
0x18003f2f1  jmp     loc_18003F40E
0x18003f2f6  mov     al, byte ptr cs:xmmword_1800616A0
0x18003f2fc  test    al, 10h
0x18003f2fe  jz      short loc_18003F33E
0x18003f300  mov     r9, [rbx+18h]
0x18003f304  lea     r8, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids
0x18003f30b  mov     edx, 21h ; '!'
0x18003f310  mov     ecx, 404h
0x18003f315  call    WPP_SF_q
0x18003f31a  mov     al, byte ptr cs:xmmword_1800616A0
0x18003f320  test    al, 10h
0x18003f322  jz      short loc_18003F33E
0x18003f324  mov     r9, [rbx+38h]
0x18003f328  lea     r8, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids
0x18003f32f  mov     edx, 22h ; '"'
0x18003f334  mov     ecx, 404h
0x18003f339  call    WPP_SF_S
0x18003f33e  mov     rcx, [rbx+2D8h]; hKey
0x18003f345  lea     rax, [rsp+38h+Data]
0x18003f34a  mov     r9d, 4; dwType
0x18003f350  mov     [rsp+38h+Data], 1
0x18003f358  mov     [rsp+38h+cbData], r9d; cbData
0x18003f35d  lea     rdx, aEnabledhcp; "EnableDhcp"
0x18003f364  xor     r8d, r8d; Reserved
0x18003f367  mov     [rsp+38h+lpData], rax; lpData
0x18003f36c  call    cs:__imp_RegSetValueExW
0x18003f372  mov     edi, eax
0x18003f374  test    eax, eax
0x18003f376  jnz     short loc_18003F3EA
0x18003f378  mov     rdx, [rbx+38h]
0x18003f37c  lea     ecx, [rax+1]
0x18003f37f  call    SetEventNotification
0x18003f384  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x18003f38b  mov     edi, eax
0x18003f38d  jz      short loc_18003F39F
0x18003f38f  mov     r8d, [rbx+30h]
0x18003f393  lea     rdx, DhcpEnabled
0x18003f39a  call    McTemplateU0q_EtwEventWriteTransfer
0x18003f39f  mov     dword ptr [rbx+318h], 1
0x18003f3a9  lea     r8, ReObtainInitialParameters
0x18003f3b0  xor     r9d, r9d
0x18003f3b3  mov     dword ptr [rbx+314h], 0
0x18003f3bd  xor     edx, edx
0x18003f3bf  mov     rcx, rbx
0x18003f3c2  call    ScheduleDhcpRenewal
0x18003f3c7  test    edi, edi
0x18003f3c9  jnz     short loc_18003F3EA
0x18003f3cb  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003f3d2  jz      short loc_18003F40C
0x18003f3d4  lea     edx, [rdi+24h]
0x18003f3d7  mov     ecx, 404h
0x18003f3dc  lea     r8, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids
0x18003f3e3  call    WPP_SF_
0x18003f3e8  jmp     short loc_18003F40C
0x18003f3ea  test    byte ptr cs:xmmword_1800616A0, 2
0x18003f3f1  jz      short loc_18003F40C
0x18003f3f3  mov     edx, 23h ; '#'
0x18003f3f8  lea     r8, WPP_da8b49cc2af8370da0dc466f7a1bd175_Traceguids
0x18003f3ff  mov     ecx, 401h
0x18003f404  mov     r9d, edi
0x18003f407  call    WPP_SF_D
0x18003f40c  mov     eax, edi
0x18003f40e  mov     rbx, [rsp+38h+arg_8]
0x18003f413  add     rsp, 30h
0x18003f417  pop     rdi
0x18003f418  retn
```
