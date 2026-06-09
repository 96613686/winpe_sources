# UpdateFirewall

- ea: `0x1800454d0`
- end: `0x1800455e1`
- name: `UpdateFirewall`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800450b0`
- `0x180045290`

## callees

- `0x180009090`
- `0x18001e1d4`
- `0x1800454d0`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d9e8`
- `0x18004dc54`
- `0x18004dd28`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004554e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004556c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004554e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004556c`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWIndicatePortInUse` at `0x180045564`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWIndicatePortInUse` at `0x180045564`

## pseudocode

```c
__int64 __fastcall UpdateFirewall(__int64 a1, unsigned int a2)
{
  unsigned __int16 v3; // di
  unsigned int v4; // edi
  int TickCount64; // ebx
  int v6; // eax
  int v7; // ecx
  int v8; // esi

  v3 = a1;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_ld(a1, 18, WPP_52380679383138217cb423d182f11bb5_Traceguids, a2, (unsigned __int16)a1);
  if ( (unsigned __int8)IsFWIndicatePortInUsePresent() )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_d(1028, 20, WPP_52380679383138217cb423d182f11bb5_Traceguids, a2);
    TickCount64 = GetTickCount64();
    v4 = FWIndicatePortInUse(4, v3);
    v6 = GetTickCount64();
    v8 = v6 - TickCount64;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_Dd(1028, 21, WPP_52380679383138217cb423d182f11bb5_Traceguids, v4, v6 - TickCount64);
    if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
      McTemplateU0qqq_EtwEventWriteTransfer(v7, (unsigned int)FirewallPortExempted, v8, 0, v4);
  }
  else
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_(1025, 19, WPP_52380679383138217cb423d182f11bb5_Traceguids);
    v4 = 573;
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 22, WPP_52380679383138217cb423d182f11bb5_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800454d0  push    rbx
0x1800454d2  push    rbp
0x1800454d3  push    rsi
0x1800454d4  push    rdi
0x1800454d5  sub     rsp, 38h
0x1800454d9  mov     ebx, edx
0x1800454db  movzx   edi, cx
0x1800454de  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800454e5  lea     rbp, WPP_52380679383138217cb423d182f11bb5_Traceguids
0x1800454ec  jz      short loc_180045502
0x1800454ee  mov     edx, 12h
0x1800454f3  mov     [rsp+58h+var_38], edi
0x1800454f7  mov     r9d, ebx
0x1800454fa  mov     r8, rbp
0x1800454fd  call    WPP_SF_ld
0x180045502  call    IsFWIndicatePortInUsePresent
0x180045507  test    al, al
0x180045509  jnz     short loc_180045530
0x18004550b  test    byte ptr cs:xmmword_1800616A0, 2
0x180045512  jz      short loc_180045526
0x180045514  mov     edx, 13h
0x180045519  mov     ecx, 401h
0x18004551e  mov     r8, rbp
0x180045521  call    WPP_SF_
0x180045526  mov     edi, 23Dh
0x18004552b  jmp     loc_1800455B8
0x180045530  test    byte ptr cs:xmmword_1800616A0, 10h
0x180045537  jz      short loc_18004554E
0x180045539  mov     edx, 14h
0x18004553e  mov     ecx, 404h
0x180045543  mov     r9d, ebx
0x180045546  mov     r8, rbp
0x180045549  call    WPP_SF_d
0x18004554e  call    cs:__imp_GetTickCount64
0x180045554  mov     r8d, 1
0x18004555a  movzx   edx, di
0x18004555d  mov     rbx, rax
0x180045560  lea     ecx, [r8+3]
0x180045564  call    cs:__imp_FWIndicatePortInUse
0x18004556a  mov     edi, eax
0x18004556c  call    cs:__imp_GetTickCount64
0x180045572  mov     rsi, rax
0x180045575  sub     esi, ebx
0x180045577  test    byte ptr cs:xmmword_1800616A0, 10h
0x18004557e  jz      short loc_180045599
0x180045580  mov     edx, 15h
0x180045585  mov     [rsp+58h+var_38], esi
0x180045589  mov     ecx, 404h
0x18004558e  mov     r9d, edi
0x180045591  mov     r8, rbp
0x180045594  call    WPP_SF_Dd
0x180045599  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x1800455a0  jz      short loc_1800455B8
0x1800455a2  xor     r9d, r9d
0x1800455a5  mov     [rsp+58h+var_38], edi
0x1800455a9  mov     r8d, esi
0x1800455ac  lea     rdx, FirewallPortExempted
0x1800455b3  call    McTemplateU0qqq_EtwEventWriteTransfer
0x1800455b8  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800455bf  jz      short loc_1800455D6
0x1800455c1  mov     edx, 16h
0x1800455c6  mov     ecx, 404h
0x1800455cb  mov     r9d, edi
0x1800455ce  mov     r8, rbp
0x1800455d1  call    WPP_SF_D
0x1800455d6  mov     eax, edi
0x1800455d8  add     rsp, 38h
0x1800455dc  pop     rdi
0x1800455dd  pop     rsi
0x1800455de  pop     rbp
0x1800455df  pop     rbx
0x1800455e0  retn
```
