# UpdateFirewall

- ea: `0x18002e6d4`
- end: `0x18002e7fa`
- name: `UpdateFirewall`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002e260`
- `0x18002e460`

## callees

- `0x180001e00`
- `0x18001abcc`
- `0x18002e6d4`
- `0x1800338c0`
- `0x180033900`
- `0x180033de4`
- `0x18003431c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002e752`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002e77c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002e752`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002e77c`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWIndicatePortInUse` at `0x18002e76e`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWIndicatePortInUse` at `0x18002e76e`

## pseudocode

```c
__int64 __fastcall UpdateFirewall(__int64 a1, unsigned int a2)
{
  unsigned __int16 v3; // di
  unsigned int v4; // edi
  int TickCount64; // ebx
  int v6; // eax
  __int64 v7; // rcx
  int v8; // esi

  v3 = a1;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_Dd(a1, 18, WPP_52380679383138217cb423d182f11bb5_Traceguids, a2, (unsigned __int16)a1);
  if ( (unsigned __int8)IsFWIndicatePortInUsePresent() )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_d(1028, 20, WPP_52380679383138217cb423d182f11bb5_Traceguids, a2);
    TickCount64 = GetTickCount64();
    v4 = FWIndicatePortInUse(4, v3);
    v6 = GetTickCount64();
    v8 = v6 - TickCount64;
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_Dd(v7, 21, WPP_52380679383138217cb423d182f11bb5_Traceguids, v4, v6 - TickCount64);
    if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
      McTemplateU0qqq_EtwEventWriteTransfer((unsigned int)Dhcp_Context, (unsigned int)FirewallPortExempted, v8, 0, v4);
  }
  else
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_(1025, 19, WPP_52380679383138217cb423d182f11bb5_Traceguids);
    v4 = 573;
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 22, WPP_52380679383138217cb423d182f11bb5_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18002e6d4  push    rbx
0x18002e6d6  push    rbp
0x18002e6d7  push    rsi
0x18002e6d8  push    rdi
0x18002e6d9  sub     rsp, 38h
0x18002e6dd  mov     ebx, edx
0x18002e6df  movzx   edi, cx
0x18002e6e2  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e6e9  lea     rbp, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x18002e6f0  jz      short loc_18002E706
0x18002e6f2  mov     edx, 12h
0x18002e6f7  mov     [rsp+58h+var_38], edi
0x18002e6fb  mov     r9d, ebx
0x18002e6fe  mov     r8, rbp
0x18002e701  call    WPP_SF_Dd
0x18002e706  call    IsFWIndicatePortInUsePresent
0x18002e70b  test    al, al
0x18002e70d  jnz     short loc_18002E734
0x18002e70f  test    byte ptr cs:xmmword_1800423E0, 2
0x18002e716  jz      short loc_18002E72A
0x18002e718  mov     edx, 13h
0x18002e71d  mov     ecx, 401h
0x18002e722  mov     r8, rbp
0x18002e725  call    WPP_SF_
0x18002e72a  mov     edi, 23Dh
0x18002e72f  jmp     loc_18002E7D0
0x18002e734  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e73b  jz      short loc_18002E752
0x18002e73d  mov     edx, 14h
0x18002e742  mov     ecx, 404h
0x18002e747  mov     r9d, ebx
0x18002e74a  mov     r8, rbp
0x18002e74d  call    WPP_SF_d
0x18002e752  call    cs:__imp_GetTickCount64
0x18002e759  nop     dword ptr [rax+rax+00h]
0x18002e75e  mov     r8d, 1
0x18002e764  movzx   edx, di
0x18002e767  mov     rbx, rax
0x18002e76a  lea     ecx, [r8+3]
0x18002e76e  call    cs:__imp_FWIndicatePortInUse
0x18002e775  nop     dword ptr [rax+rax+00h]
0x18002e77a  mov     edi, eax
0x18002e77c  call    cs:__imp_GetTickCount64
0x18002e783  nop     dword ptr [rax+rax+00h]
0x18002e788  mov     rsi, rax
0x18002e78b  sub     esi, ebx
0x18002e78d  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e794  jz      short loc_18002E7AA
0x18002e796  mov     edx, 15h
0x18002e79b  mov     [rsp+58h+var_38], esi
0x18002e79f  mov     r9d, edi
0x18002e7a2  mov     r8, rbp
0x18002e7a5  call    WPP_SF_Dd
0x18002e7aa  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x18002e7b1  jz      short loc_18002E7D0
0x18002e7b3  xor     r9d, r9d
0x18002e7b6  mov     [rsp+58h+var_38], edi
0x18002e7ba  mov     r8d, esi
0x18002e7bd  lea     rdx, FirewallPortExempted
0x18002e7c4  lea     rcx, Dhcp_Context
0x18002e7cb  call    McTemplateU0qqq_EtwEventWriteTransfer
0x18002e7d0  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e7d7  jz      short loc_18002E7EE
0x18002e7d9  mov     edx, 16h
0x18002e7de  mov     ecx, 404h
0x18002e7e3  mov     r9d, edi
0x18002e7e6  mov     r8, rbp
0x18002e7e9  call    WPP_SF_D
0x18002e7ee  mov     eax, edi
0x18002e7f0  add     rsp, 38h
0x18002e7f4  pop     rdi
0x18002e7f5  pop     rsi
0x18002e7f6  pop     rbp
0x18002e7f7  pop     rbx
0x18002e7f8  retn
```
