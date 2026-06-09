# SetRegistryClassIdBin

- ea: `0x1800058ec`
- end: `0x18000598c`
- name: `SetRegistryClassIdBin`
- size: `160`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x1800056d4`

## callees

- `0x1800058ec`
- `0x1800069d0`
- `0x180006a18`
- `0x18004d1a0`
- `0x18004dc9c`

## string_xrefs

- `0x180005918`: `System\CurrentControlSet\Services\Dhcp\Parameters\DhcpClientClassLocation`

## pseudocode

```c
__int64 __fastcall SetRegistryClassIdBin(void *a1, const BYTE *a2, DWORD a3)
{
  BOOL IsWCOSSystem; // eax
  wchar_t *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // ebx

  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_Sqd((_DWORD)a1, 14, (unsigned int)WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids, (_DWORD)a1, (char)a2, a3);
  IsWCOSSystem = DhcpIsWCOSSystem();
  v7 = L"OSDATA\\Networking\\Dhcp\\Client4\\DhcpClientClassLocation";
  if ( !IsWCOSSystem )
    v7 = L"System\\CurrentControlSet\\Services\\Dhcp\\Parameters\\DhcpClientClassLocation";
  v8 = SetClassIdForLocation(
         v7,
         (__int64)L"System\\CurrentControlSet\\Services\\Dhcp\\Parameters\\DhcpClientClassLocation",
         a1,
         a2,
         a3);
  v9 = v8;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 15, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids, v8);
  return v9;
}

```

## disassembly

```asm
0x1800058ec  mov     [rsp+arg_0], rbx
0x1800058f1  mov     [rsp+arg_8], rsi
0x1800058f6  push    rdi
0x1800058f7  sub     rsp, 30h
0x1800058fb  mov     ebx, r8d
0x1800058fe  mov     rdi, rdx
0x180005901  mov     rsi, rcx
0x180005904  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000590b  jnz     short loc_180005952
0x18000590d  call    DhcpIsWCOSSystem
0x180005912  test    eax, eax
0x180005914  mov     [rsp+38h+var_18], ebx; DWORD
0x180005918  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services\\Dh"...
0x18000591f  mov     r9, rdi
0x180005922  lea     rcx, aOsdataNetworki_2; "OSDATA\\Networking\\Dhcp\\Client4\\Dhcp"...
0x180005929  mov     r8, rsi
0x18000592c  cmovz   rcx, rdx; Src
0x180005930  call    SetClassIdForLocation
0x180005935  mov     ebx, eax
0x180005937  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000593e  jnz     short loc_180005971
0x180005940  mov     rsi, [rsp+38h+arg_8]
0x180005945  mov     eax, ebx
0x180005947  mov     rbx, [rsp+38h+arg_0]
0x18000594c  add     rsp, 30h
0x180005950  pop     rdi
0x180005951  retn
0x180005952  mov     edx, 0Eh
0x180005957  mov     [rsp+38h+var_10], ebx
0x18000595b  mov     r9, rsi
0x18000595e  mov     qword ptr [rsp+38h+var_18], rdi
0x180005963  lea     r8, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids
0x18000596a  call    WPP_SF_Sqd
0x18000596f  jmp     short loc_18000590D
0x180005971  mov     edx, 0Fh
0x180005976  lea     r8, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids
0x18000597d  mov     ecx, 404h
0x180005982  mov     r9d, ebx
0x180005985  call    WPP_SF_D
0x18000598a  jmp     short loc_180005940
```
