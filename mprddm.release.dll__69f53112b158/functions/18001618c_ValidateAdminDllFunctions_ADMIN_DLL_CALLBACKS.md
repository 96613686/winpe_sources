# ValidateAdminDllFunctions(_ADMIN_DLL_CALLBACKS *)

- ea: `0x18001618c`
- end: `0x1800164ad`
- name: `?ValidateAdminDllFunctions@@YAKPEAU_ADMIN_DLL_CALLBACKS@@@Z`
- size: `801`
- prototype: `unsigned int __fastcall(struct _ADMIN_DLL_CALLBACKS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800167fc`

## callees

- `0x180007c0c`
- `0x18001618c`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `rtutils!RouterLogEventStringW` at `0x180016476`
- `rtutils!RouterLogEventStringW` at `0x180016476`

## string_xrefs

- `0x1800162c3`: `ValidateAdminDllFunctions: Only one is implemented in lpfnMprAdminGetIpv6AddressForUser:%p or lpfnMprAdminReleaseIpV6AddressForUser:%p`
- `0x180016313`: `ValidateAdminDllFunctions: Only one is implemented in lpfnMprAdminGetIpAddressForUser:%p or lpfnMprAdminReleaseIpAddressForUser:%p`
- `0x1800163dc`: `ValidateAdminDllFunctions: one of the following is not implemented in lpfnRasAdminLinkHangupNotification:%p or lpfnRasAdminAcceptNewLink:%p`
- `0x180016273`: `ValidateAdminDllFunctions: one of the following is not implemented in lpfnRasAdminAcceptNewConnectionEx:%p or lpfnRasAdminConnectionHangupNotificationEx %p`

## pseudocode

```c
__int64 __fastcall ValidateAdminDllFunctions(struct _ADMIN_DLL_CALLBACKS *a1)
{
  char v2; // dl
  unsigned int v3; // edi
  __int64 v4; // r8
  __int64 v5; // rax
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rax
  const wchar_t *v12; // rcx
  __int64 v13; // r9
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+48h] [rbp-C0h] BYREF
  const wchar_t *v16; // [rsp+58h] [rbp-B0h]
  int v17; // [rsp+60h] [rbp-A8h]
  int v18; // [rsp+64h] [rbp-A4h]
  int v19; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v20[2044]; // [rsp+6Ch] [rbp-9Ch] BYREF

  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v2 = *((_BYTE *)a1 + 8);
  v3 = 0;
  if ( v2 != 1 && *((_BYTE *)a1 + 8) != 2 )
    goto LABEL_50;
  v4 = *((_QWORD *)a1 + 4);
  v5 = *((_QWORD *)a1 + 5);
  if ( v4 )
  {
    if ( v5 )
      goto LABEL_5;
LABEL_18:
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_50;
    LOWORD(v19) = 0;
    FormatRRASErrorString(
      &v19,
      L"ValidateAdminDllFunctions: Only one is implemented in lpfnMprAdminGetIpv6AddressForUser:%p or lpfnMprAdminReleaseI"
       "pV6AddressForUser:%p",
      v4,
      v5);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_50;
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&v20[2 * v11 - 4] );
LABEL_48:
    v12 = (const wchar_t *)&v19;
LABEL_49:
    v16 = v12;
    v17 = 2 * v11 + 2;
    v18 = 0;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
      v8,
      2u,
      &v15);
    goto LABEL_50;
  }
  if ( v5 )
    goto LABEL_18;
LABEL_5:
  v6 = *((_QWORD *)a1 + 2);
  v7 = *((_QWORD *)a1 + 3);
  if ( !v6 )
  {
    if ( !v7 )
      goto LABEL_7;
    goto LABEL_24;
  }
  if ( !v7 )
  {
LABEL_24:
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_50;
    LOWORD(v19) = 0;
    FormatRRASErrorString(
      &v19,
      L"ValidateAdminDllFunctions: Only one is implemented in lpfnMprAdminGetIpAddressForUser:%p or lpfnMprAdminReleaseIpA"
       "ddressForUser:%p",
      v6,
      v7);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_50;
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&v20[2 * v11 - 4] );
    goto LABEL_48;
  }
LABEL_7:
  v8 = *((_QWORD *)a1 + 13);
  if ( !v8 || !*((_QWORD *)a1 + 9) )
  {
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_50;
    v13 = *((_QWORD *)a1 + 9);
    LOWORD(v19) = 0;
    FormatRRASErrorString(
      &v19,
      L"ValidateAdminDllFunctions: one of the following is not implemented in lpfnRasAdminLinkHangupNotification:%p or lpf"
       "nRasAdminAcceptNewLink:%p",
      v8,
      v13);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_50;
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&v20[2 * v11 - 4] );
    goto LABEL_48;
  }
  if ( v2 == 2 )
  {
    v9 = *((_QWORD *)a1 + 16);
    if ( v9 && *((_QWORD *)a1 + 19) )
      return v3;
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_50;
    v10 = *((_QWORD *)a1 + 19);
    LOWORD(v19) = 0;
    FormatRRASErrorString(
      &v19,
      L"ValidateAdminDllFunctions: one of the following is not implemented in lpfnRasAdminAcceptNewConnectionEx:%p or lpfn"
       "RasAdminConnectionHangupNotificationEx %p",
      v9,
      v10);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_50;
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&v20[2 * v11 - 4] );
    goto LABEL_48;
  }
  if ( v2 != 1 )
    return v3;
  if ( !*((_QWORD *)a1 + 6) && !*((_QWORD *)a1 + 7) && !*((_QWORD *)a1 + 8) )
  {
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_50;
    v12 = L"Accept New Connection is not implemented";
    v11 = -1;
    do
      ++v11;
    while ( aAcceptNewConne[v11] );
    goto LABEL_49;
  }
  if ( *((_QWORD *)a1 + 10) || *((_QWORD *)a1 + 11) || *((_QWORD *)a1 + 12) )
    return v3;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v12 = L"Connection hangup is not implemented";
    v11 = -1;
    do
      ++v11;
    while ( aConnectionHang[v11] );
    goto LABEL_49;
  }
LABEL_50:
  v3 = 87;
  if ( dword_1800CF4E4 )
    RouterLogEventStringW(hLogHandle, 1u, 0x4E91u, 0, 0, 0x57u, 0);
  return v3;
}

```

## disassembly

```asm
0x18001618c  mov     rax, rsp
0x18001618f  mov     [rax+10h], rbx
0x180016193  mov     [rax+18h], rsi
0x180016197  mov     [rax+20h], rdi
0x18001619b  push    rbp
0x18001619c  lea     rbp, [rax-778h]
0x1800161a3  sub     rsp, 870h
0x1800161aa  mov     rax, cs:__security_cookie
0x1800161b1  xor     rax, rsp
0x1800161b4  mov     [rbp+770h+var_10], rax
0x1800161bb  mov     rbx, rcx
0x1800161be  xor     esi, esi
0x1800161c0  lea     rcx, [rsp+870h+var_80C]; void *
0x1800161c5  mov     [rsp+870h+var_810], esi
0x1800161c9  xor     edx, edx; Val
0x1800161cb  mov     r8d, 7FCh; Size
0x1800161d1  call    memset_0
0x1800161d6  movzx   edx, byte ptr [rbx+8]
0x1800161da  mov     edi, esi
0x1800161dc  mov     ecx, edx
0x1800161de  sub     ecx, 1
0x1800161e1  jz      short loc_1800161EC
0x1800161e3  cmp     ecx, 1
0x1800161e6  jnz     loc_180016449
0x1800161ec  mov     r8, [rbx+20h]
0x1800161f0  mov     rax, [rbx+28h]
0x1800161f4  mov     r9, rax
0x1800161f7  test    r8, r8
0x1800161fa  jz      loc_1800162AD
0x180016200  test    rax, rax
0x180016203  jz      loc_1800162B6
0x180016209  mov     r8, [rbx+10h]
0x18001620d  mov     rax, [rbx+18h]
0x180016211  mov     r9, rax
0x180016214  test    r8, r8
0x180016217  jz      loc_1800162FD
0x18001621d  test    rax, rax
0x180016220  jz      loc_180016306
0x180016226  mov     r8, [rbx+68h]
0x18001622a  test    r8, r8
0x18001622d  jz      loc_1800163CF
0x180016233  cmp     [rbx+48h], rsi
0x180016237  jz      loc_1800163CF
0x18001623d  cmp     dl, 2
0x180016240  jnz     loc_18001634D
0x180016246  mov     r8, [rbx+80h]
0x18001624d  test    r8, r8
0x180016250  jz      short loc_18001625F
0x180016252  cmp     [rbx+98h], rsi
0x180016259  jnz     loc_180016482
0x18001625f  test    cs:byte_1800CF404, 10h
0x180016266  jz      loc_180016449
0x18001626c  mov     r9, [rbx+98h]
0x180016273  lea     rdx, aValidateadmind; "ValidateAdminDllFunctions: one of the f"...
0x18001627a  lea     rcx, [rsp+870h+var_810]
0x18001627f  mov     word ptr [rsp+870h+var_810], si
0x180016284  call    FormatRRASErrorString
0x180016289  test    cs:byte_1800CF404, 10h
0x180016290  jz      loc_180016449
0x180016296  lea     rcx, [rsp+870h+var_810]
0x18001629b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001629f  inc     rax
0x1800162a2  cmp     [rcx+rax*2], si
0x1800162a6  jnz     short loc_18001629F
0x1800162a8  jmp     loc_18001640D
0x1800162ad  test    rax, rax
0x1800162b0  jz      loc_180016209
0x1800162b6  test    cs:byte_1800CF404, 10h
0x1800162bd  jz      loc_180016449
0x1800162c3  lea     rdx, aValidateadmind_2; "ValidateAdminDllFunctions: Only one is "...
0x1800162ca  mov     word ptr [rsp+870h+var_810], si
0x1800162cf  lea     rcx, [rsp+870h+var_810]
0x1800162d4  call    FormatRRASErrorString
0x1800162d9  test    cs:byte_1800CF404, 10h
0x1800162e0  jz      loc_180016449
0x1800162e6  lea     rcx, [rsp+870h+var_810]
0x1800162eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800162ef  inc     rax
0x1800162f2  cmp     [rcx+rax*2], si
0x1800162f6  jnz     short loc_1800162EF
0x1800162f8  jmp     loc_18001640D
0x1800162fd  test    rax, rax
0x180016300  jz      loc_180016226
0x180016306  test    cs:byte_1800CF404, 10h
0x18001630d  jz      loc_180016449
0x180016313  lea     rdx, aValidateadmind_0; "ValidateAdminDllFunctions: Only one is "...
0x18001631a  mov     word ptr [rsp+870h+var_810], si
0x18001631f  lea     rcx, [rsp+870h+var_810]
0x180016324  call    FormatRRASErrorString
0x180016329  test    cs:byte_1800CF404, 10h
0x180016330  jz      loc_180016449
0x180016336  lea     rcx, [rsp+870h+var_810]
0x18001633b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001633f  inc     rax
0x180016342  cmp     [rcx+rax*2], si
0x180016346  jnz     short loc_18001633F
0x180016348  jmp     loc_18001640D
0x18001634d  cmp     dl, 1
0x180016350  jnz     loc_180016482
0x180016356  cmp     [rbx+30h], rsi
0x18001635a  jnz     short loc_18001638E
0x18001635c  cmp     [rbx+38h], rsi
0x180016360  jnz     short loc_18001638E
0x180016362  cmp     [rbx+40h], rsi
0x180016366  jnz     short loc_18001638E
0x180016368  test    cs:byte_1800CF404, 10h
0x18001636f  jz      loc_180016449
0x180016375  lea     rcx, aAcceptNewConne; "Accept New Connection is not implemente"...
0x18001637c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016380  inc     rax
0x180016383  cmp     [rcx+rax*2], si
0x180016387  jnz     short loc_180016380
0x180016389  jmp     loc_180016412
0x18001638e  cmp     [rbx+50h], rsi
0x180016392  jnz     loc_180016482
0x180016398  cmp     [rbx+58h], rsi
0x18001639c  jnz     loc_180016482
0x1800163a2  cmp     [rbx+60h], rsi
0x1800163a6  jnz     loc_180016482
0x1800163ac  test    cs:byte_1800CF404, 10h
0x1800163b3  jz      loc_180016449
0x1800163b9  lea     rcx, aConnectionHang; "Connection hangup is not implemented"
0x1800163c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800163c4  inc     rax
0x1800163c7  cmp     [rcx+rax*2], si
0x1800163cb  jnz     short loc_1800163C4
0x1800163cd  jmp     short loc_180016412
0x1800163cf  test    cs:byte_1800CF404, 10h
0x1800163d6  jz      short loc_180016449
0x1800163d8  mov     r9, [rbx+48h]
0x1800163dc  lea     rdx, aValidateadmind_1; "ValidateAdminDllFunctions: one of the f"...
0x1800163e3  lea     rcx, [rsp+870h+var_810]
0x1800163e8  mov     word ptr [rsp+870h+var_810], si
0x1800163ed  call    FormatRRASErrorString
0x1800163f2  test    cs:byte_1800CF404, 10h
0x1800163f9  jz      short loc_180016449
0x1800163fb  lea     rcx, [rsp+870h+var_810]
0x180016400  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016404  inc     rax
0x180016407  cmp     [rcx+rax*2], si
0x18001640b  jnz     short loc_180016404
0x18001640d  lea     rcx, [rsp+870h+var_810]
0x180016412  lea     eax, ds:2[rax*2]
0x180016419  mov     [rsp+870h+var_820], rcx
0x18001641e  mov     [rsp+870h+var_818], eax
0x180016422  lea     rdx, RasDdmTraceInfo
0x180016429  lea     rax, [rsp+870h+var_830]
0x18001642e  mov     [rsp+870h+var_814], esi
0x180016432  mov     r9d, 2
0x180016438  mov     [rsp+870h+plpszSubStringArray], rax
0x18001643d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016444  call    McGenEventWrite_EventWriteTransfer
0x180016449  cmp     cs:dword_1800CF4E4, esi
0x18001644f  mov     edi, 57h ; 'W'
0x180016454  jbe     short loc_180016482
0x180016456  mov     rcx, cs:hLogHandle; hLogHandle
0x18001645d  lea     edx, [rdi-56h]; dwEventType
0x180016460  mov     [rsp+870h+dwErrorIndex], esi; dwErrorIndex
0x180016464  xor     r9d, r9d; dwSubStringCount
0x180016467  mov     [rsp+870h+dwErrorCode], edi; dwErrorCode
0x18001646b  mov     r8d, 4E91h; dwMessageId
0x180016471  mov     [rsp+870h+plpszSubStringArray], rsi; plpszSubStringArray
0x180016476  call    cs:__imp_RouterLogEventStringW
0x18001647d  nop     dword ptr [rax+rax+00h]
0x180016482  mov     eax, edi
0x180016484  mov     rcx, [rbp+770h+var_10]
0x18001648b  xor     rcx, rsp; StackCookie
0x18001648e  call    __security_check_cookie
0x180016493  lea     r11, [rsp+870h+var_s0]
0x18001649b  mov     rbx, [r11+18h]
0x18001649f  mov     rsi, [r11+20h]
0x1800164a3  mov     rdi, [r11+28h]
0x1800164a7  mov     rsp, r11
0x1800164aa  pop     rbp
0x1800164ab  retn
```
