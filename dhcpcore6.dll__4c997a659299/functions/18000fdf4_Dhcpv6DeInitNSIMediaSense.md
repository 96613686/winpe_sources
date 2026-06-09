# Dhcpv6DeInitNSIMediaSense

- ea: `0x18000fdf4`
- end: `0x18000fe86`
- name: `Dhcpv6DeInitNSIMediaSense`
- size: `146`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180012ee4`
- `0x18001cb0c`
- `0x18001ef90`

## callees

- `0x18000fdf4`

## import_xrefs

- `WINNSI!NsiDisconnectFromServer` at `0x18000fe69`
- `WINNSI!NsiDisconnectFromServer` at `0x18000fe69`
- `WINNSI!NsiRpcDeregisterChangeNotificationEx` at `0x18000fe41`
- `WINNSI!NsiRpcDeregisterChangeNotificationEx` at `0x18000fe41`

## pseudocode

```c
__int64 Dhcpv6DeInitNSIMediaSense()
{
  __int64 result; // rax
  __int128 v1; // [rsp+20h] [rbp-38h] BYREF
  __int128 v2; // [rsp+30h] [rbp-28h]
  __int64 v3; // [rsp+40h] [rbp-18h]

  v1 = 0;
  v2 = 0;
  v3 = 0;
  if ( (unsigned __int64)(qword_180042500 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    *((_QWORD *)&v1 + 1) = &NPI_MS_IPV6_MODULEID;
    LODWORD(v2) = 7;
    *((_QWORD *)&v2 + 1) = qword_180042500;
    NsiRpcDeregisterChangeNotificationEx(qword_180042508, &v1);
  }
  qword_180042500 = 0;
  result = qword_180042508 - 1;
  if ( (unsigned __int64)(qword_180042508 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    result = NsiDisconnectFromServer(qword_180042508);
  qword_180042508 = 0;
  return result;
}

```

## disassembly

```asm
0x18000fdf4  mov     r11, rsp
0x18000fdf7  sub     rsp, 58h
0x18000fdfb  mov     rcx, cs:qword_180042500
0x18000fe02  xor     eax, eax
0x18000fe04  xorps   xmm0, xmm0
0x18000fe07  movups  [rsp+58h+var_38], xmm0
0x18000fe0c  movups  [rsp+58h+var_28], xmm0
0x18000fe11  mov     [r11-18h], rax
0x18000fe15  lea     rax, [rcx-1]
0x18000fe19  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000fe1d  ja      short loc_18000FE4D
0x18000fe1f  lea     rax, NPI_MS_IPV6_MODULEID
0x18000fe26  mov     [r11-30h], rax
0x18000fe2a  lea     rdx, [r11-38h]
0x18000fe2e  mov     dword ptr [rsp+58h+var_28], 7
0x18000fe36  mov     [r11-20h], rcx
0x18000fe3a  mov     rcx, cs:qword_180042508
0x18000fe41  call    cs:__imp_NsiRpcDeregisterChangeNotificationEx
0x18000fe48  nop     dword ptr [rax+rax+00h]
0x18000fe4d  mov     rcx, cs:qword_180042508
0x18000fe54  mov     cs:qword_180042500, 0
0x18000fe5f  lea     rax, [rcx-1]
0x18000fe63  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000fe67  ja      short loc_18000FE75
0x18000fe69  call    cs:__imp_NsiDisconnectFromServer
0x18000fe70  nop     dword ptr [rax+rax+00h]
0x18000fe75  mov     cs:qword_180042508, 0
0x18000fe80  add     rsp, 58h
0x18000fe84  retn
```
