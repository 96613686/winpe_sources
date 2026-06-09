# Dhcpv6ReleasePrefix

- ea: `0x1800051b0`
- end: `0x18000525b`
- name: `Dhcpv6ReleasePrefix`
- size: `171`
- prototype: `DWORD __stdcall(LPWSTR adapterName, LPDHCPV6CAPI_CLASSID classId, LPDHCPV6PrefixLeaseInformation leaseInfo)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180003650`
- `0x1800051b0`
- `0x180005270`
- `0x1800081c0`
- `0x1800082d0`
- `0x180008490`

## pseudocode

```c
DWORD __stdcall Dhcpv6ReleasePrefix(
        LPWSTR adapterName,
        LPDHCPV6CAPI_CLASSID classId,
        LPDHCPV6PrefixLeaseInformation leaseInfo)
{
  int v6; // ecx
  DWORD v7; // ebx

  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(adapterName, 41, WPP_cb48999f8e5838f952918348529d50de_Traceguids, adapterName);
  if ( DhcpIsFSEGuestSystem() )
  {
    v7 = 50;
    if ( (xmmword_18000F160 & 2) != 0 )
      WPP_SF_D(1025, 42, WPP_cb48999f8e5838f952918348529d50de_Traceguids, 50);
  }
  else
  {
    v7 = Dhcpv6ReleasePrefixEx(adapterName, classId, leaseInfo, 0);
  }
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_SD(v6, 43, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, (_DWORD)adapterName, v7);
  return v7;
}

```

## disassembly

```asm
0x1800051b0  mov     [rsp+arg_0], rbx
0x1800051b5  mov     [rsp+arg_8], rsi
0x1800051ba  push    rdi
0x1800051bb  sub     rsp, 30h
0x1800051bf  mov     rbx, r8
0x1800051c2  mov     rsi, rdx
0x1800051c5  mov     rdi, rcx
0x1800051c8  test    byte ptr cs:xmmword_18000F160, 10h
0x1800051cf  jz      short loc_1800051E5
0x1800051d1  mov     edx, 29h ; ')'
0x1800051d6  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x1800051dd  mov     r9, rcx
0x1800051e0  call    WPP_SF_S
0x1800051e5  call    DhcpIsFSEGuestSystem
0x1800051ea  test    eax, eax
0x1800051ec  jnz     short loc_180005203
0x1800051ee  xor     r9d, r9d
0x1800051f1  mov     r8, rbx
0x1800051f4  mov     rdx, rsi
0x1800051f7  mov     rcx, rdi
0x1800051fa  call    Dhcpv6ReleasePrefixEx
0x1800051ff  mov     ebx, eax
0x180005201  jmp     short loc_180005228
0x180005203  mov     ebx, 32h ; '2'
0x180005208  test    byte ptr cs:xmmword_18000F160, 2
0x18000520f  jz      short loc_180005228
0x180005211  lea     edx, [rbx-8]
0x180005214  mov     ecx, 401h
0x180005219  mov     r9d, ebx
0x18000521c  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180005223  call    WPP_SF_D
0x180005228  test    byte ptr cs:xmmword_18000F160, 10h
0x18000522f  jz      short loc_180005249
0x180005231  mov     edx, 2Bh ; '+'
0x180005236  mov     [rsp+38h+var_18], ebx
0x18000523a  mov     r9, rdi
0x18000523d  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180005244  call    WPP_SF_SD
0x180005249  mov     rsi, [rsp+38h+arg_8]
0x18000524e  mov     eax, ebx
0x180005250  mov     rbx, [rsp+38h+arg_0]
0x180005255  add     rsp, 30h
0x180005259  pop     rdi
0x18000525a  retn
```
