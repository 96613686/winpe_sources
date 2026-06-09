# ProcessIncomingCall(_VPN_DEVICE *,ulong)

- ea: `0x18002a7b0`
- end: `0x18002ab44`
- name: `?ProcessIncomingCall@@YAXPEAU_VPN_DEVICE@@K@Z`
- size: `916`
- prototype: `void __fastcall(struct _VPN_DEVICE *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a000`

## callees

- `0x180007c0c`
- `0x180028e90`
- `0x18002a7b0`
- `0x1800755b8`
- `0x18008beac`
- `0x18008c2d8`
- `0x18008c578`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!strstr` at `0x18002aa5f`
- `msvcrt!strstr` at `0x18002aad4`
- `msvcrt!strstr` at `0x18002aa5f`
- `msvcrt!strstr` at `0x18002aad4`
- `ntdll!RtlIpv6StringToAddressA` at `0x18002aa9c`
- `ntdll!RtlIpv6StringToAddressA` at `0x18002ab11`
- `ntdll!RtlIpv6StringToAddressA` at `0x18002aa9c`
- `ntdll!RtlIpv6StringToAddressA` at `0x18002ab11`
- `WS2_32!__imp_inet_addr` at `0x18002aa7b`
- `WS2_32!__imp_inet_addr` at `0x18002aaf0`
- `WS2_32!__imp_inet_addr` at `0x18002aa7b`
- `WS2_32!__imp_inet_addr` at `0x18002aaf0`

## string_xrefs

- `0x18002a850`: `IncomingCall for deviceId(%d)`
- `0x18002a8de`: `Incoming call failed as server is offline`

## pseudocode

```c
void __fastcall ProcessIncomingCall(struct _VPN_DEVICE *a1, unsigned int a2)
{
  __int64 v4; // rbx
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 *v10; // rdx
  __int64 v11; // r8
  const wchar_t *v12; // rcx
  const CHAR *v13; // rbx
  const CHAR *v14; // rbx
  struct in6_addr Addr; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+40h] [rbp-C0h]
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  PCSTR Terminator; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v19; // [rsp+58h] [rbp-A8h]
  struct in6_addr v20; // [rsp+68h] [rbp-98h]
  _BYTE v21[24]; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v23; // [rsp+A0h] [rbp-60h]
  int v24; // [rsp+A8h] [rbp-58h]
  int v25; // [rsp+ACh] [rbp-54h]
  _DWORD v26[27]; // [rsp+B0h] [rbp-50h] BYREF
  char v27; // [rsp+11Ch] [rbp+1Ch]
  unsigned int v28; // [rsp+124h] [rbp+24h]
  char v29; // [rsp+130h] [rbp+30h]
  unsigned int v30; // [rsp+138h] [rbp+38h]
  int v31; // [rsp+1D0h] [rbp+D0h]
  unsigned int v32; // [rsp+1D4h] [rbp+D4h]
  int v33; // [rsp+4B0h] [rbp+3B0h] BYREF
  _BYTE v34[2044]; // [rsp+4B4h] [rbp+3B4h] BYREF

  v17 = 0;
  memset_0(v26, 0, 0x400u);
  Terminator = 0;
  v33 = 0;
  v16 = 0;
  v19 = 0;
  v20 = 0;
  memset(v21, 0, sizeof(v21));
  Addr = 0;
  memset_0(v34, 0, sizeof(v34));
  v4 = -1;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v5 = *((unsigned int *)a1 + 4);
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, L"IncomingCall for deviceId(%d)", v5);
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)&v34[2 * v7 - 4] );
      v25 = 0;
      v24 = 2 * v7 + 2;
      v23 = (const wchar_t *)&v33;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
        v6,
        2u,
        &v22);
    }
  }
  if ( (unsigned int)((__int64 (*)(void))qword_1800CF6B0)() == 1 )
  {
    if ( (byte_1800CF404 & 8) == 0 )
    {
LABEL_11:
      RasLineDrop(a2, v8, v9, 0, &v17);
      RasLineCloseCall(a2);
      return;
    }
    do
      ++v4;
    while ( aIncomingCallFa[v4] );
    v23 = L"Incoming call failed as server is offline";
    v10 = RasDdmTraceError;
LABEL_10:
    v25 = 0;
    v24 = 2 * v4 + 2;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)v10,
      v9,
      2u,
      &v22);
    goto LABEL_11;
  }
  if ( !*((_DWORD *)a1 + 1) && !*((_DWORD *)a1 + 2) )
  {
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_11;
    v11 = *((unsigned int *)a1 + 4);
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, L"Ras or Routing is not enabled for deviceId(%d)", v11);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_11;
    do
      ++v4;
    while ( *(_WORD *)&v34[2 * v4 - 4] );
    v12 = (const wchar_t *)&v33;
LABEL_18:
    v23 = v12;
    v10 = RasDdmTraceInfo;
    goto LABEL_10;
  }
  v26[0] = 1024;
  if ( (unsigned int)RasLineGetCallInfo(a2, v26) )
    goto LABEL_11;
  if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)a1 + 76) > *((_DWORD *)a1 + 75) )
  {
    _InterlockedAdd((volatile signed __int32 *)a1 + 76, 0xFFFFFFFF);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_11;
    v12 = L"Unable to find free ports.";
    do
      ++v4;
    while ( aUnableToFindFr[v4] );
    goto LABEL_18;
  }
  LODWORD(v19) = *((_DWORD *)a1 + 77);
  DWORD1(v19) = v31;
  *((_QWORD *)&v19 + 1) = (char *)v26 + v32;
  if ( (v29 & 8) != 0 )
  {
    v13 = (char *)v26 + v30;
    if ( strstr(v13, ":") )
    {
      *(_DWORD *)Addr.u.Byte = 2;
      RtlIpv6StringToAddressA(v13, &Terminator, (struct in6_addr *)&Addr.u.Word[2]);
    }
    else
    {
      *(_DWORD *)Addr.u.Byte = 1;
      *(_DWORD *)&Addr.u.Word[2] = inet_addr(v13);
    }
    *(_DWORD *)v21 = v16;
    v20 = Addr;
  }
  if ( (v27 & 8) != 0 )
  {
    v14 = (char *)v26 + v28;
    if ( strstr(v14, ":") )
    {
      *(_DWORD *)Addr.u.Byte = 2;
      RtlIpv6StringToAddressA(v14, &Terminator, (struct in6_addr *)&Addr.u.Word[2]);
    }
    else
    {
      *(_DWORD *)Addr.u.Byte = 1;
      *(_DWORD *)&Addr.u.Word[2] = inet_addr(v14);
    }
    *(_DWORD *)&v21[20] = v16;
    *(struct in6_addr *)&v21[4] = Addr;
  }
  DdmNotifyCaller(0, a2, 2);
}

```

## disassembly

```asm
0x18002a7b0  mov     [rsp-8+arg_10], rbx
0x18002a7b5  push    rbp
0x18002a7b6  push    rsi
0x18002a7b7  push    rdi
0x18002a7b8  push    r12
0x18002a7ba  push    r14
0x18002a7bc  lea     rbp, [rsp-0BC0h]
0x18002a7c4  sub     rsp, 0CC0h
0x18002a7cb  mov     rax, cs:__security_cookie
0x18002a7d2  xor     rax, rsp
0x18002a7d5  mov     [rbp+0BE0h+var_30], rax
0x18002a7dc  mov     esi, edx
0x18002a7de  mov     rdi, rcx
0x18002a7e1  xor     r14d, r14d
0x18002a7e4  lea     rcx, [rbp+0BE0h+var_C30]; void *
0x18002a7e8  xor     edx, edx; Val
0x18002a7ea  mov     [rsp+0CE0h+var_C98], r14d
0x18002a7ef  mov     r8d, 400h; Size
0x18002a7f5  call    memset_0
0x18002a7fa  xorps   xmm0, xmm0
0x18002a7fd  mov     [rsp+0CE0h+Terminator], r14
0x18002a802  xor     eax, eax
0x18002a804  mov     [rbp+0BE0h+var_830], r14d
0x18002a80b  xor     edx, edx; Val
0x18002a80d  mov     [rbp+0BE0h+var_C58], rax
0x18002a811  mov     r8d, 7FCh; Size
0x18002a817  mov     [rsp+0CE0h+var_CA0], eax
0x18002a81b  lea     rcx, [rbp+0BE0h+var_82C]; void *
0x18002a822  movups  [rsp+0CE0h+var_C88], xmm0
0x18002a827  movups  [rsp+0CE0h+var_C78], xmm0
0x18002a82c  movups  [rsp+0CE0h+var_C68], xmm0
0x18002a831  movups  xmmword ptr [rsp+0CE0h+Addr.u], xmm0
0x18002a836  call    memset_0
0x18002a83b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002a83f  lea     r12d, [r14+2]
0x18002a843  test    cs:byte_1800CF404, 10h
0x18002a84a  jz      short loc_18002A8C0
0x18002a84c  mov     r8d, [rdi+10h]
0x18002a850  lea     rdx, aIncomingcallFo; "IncomingCall for deviceId(%d)"
0x18002a857  lea     rcx, [rbp+0BE0h+var_830]
0x18002a85e  mov     word ptr [rbp+0BE0h+var_830], r14w
0x18002a866  call    FormatRRASErrorString
0x18002a86b  test    cs:byte_1800CF404, 10h
0x18002a872  jz      short loc_18002A8C0
0x18002a874  lea     rcx, [rbp+0BE0h+var_830]
0x18002a87b  mov     rax, rbx
0x18002a87e  inc     rax
0x18002a881  cmp     [rcx+rax*2], r14w
0x18002a886  jnz     short loc_18002A87E
0x18002a888  lea     eax, ds:2[rax*2]
0x18002a88f  mov     [rbp+0BE0h+var_C34], r14d
0x18002a893  lea     rcx, [rbp+0BE0h+var_830]
0x18002a89a  mov     [rbp+0BE0h+var_C38], eax
0x18002a89d  lea     rax, [rbp+0BE0h+var_C50]
0x18002a8a1  mov     [rbp+0BE0h+var_C40], rcx
0x18002a8a5  mov     r9d, r12d
0x18002a8a8  mov     [rsp+0CE0h+var_CC0], rax
0x18002a8ad  lea     rdx, RasDdmTraceInfo
0x18002a8b4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002a8bb  call    McGenEventWrite_EventWriteTransfer
0x18002a8c0  mov     rax, cs:qword_1800CF6B0
0x18002a8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a8cc  cmp     eax, 1
0x18002a8cf  jnz     loc_18002A962
0x18002a8d5  test    cs:byte_1800CF404, 8
0x18002a8dc  jz      short loc_18002A920
0x18002a8de  lea     rdx, aIncomingCallFa; "Incoming call failed as server is offli"...
0x18002a8e5  inc     rbx
0x18002a8e8  cmp     [rdx+rbx*2], r14w
0x18002a8ed  jnz     short loc_18002A8E5
0x18002a8ef  mov     [rbp+0BE0h+var_C40], rdx
0x18002a8f3  lea     rdx, RasDdmTraceError
0x18002a8fa  lea     eax, ds:2[rbx*2]
0x18002a901  mov     [rbp+0BE0h+var_C34], r14d
0x18002a905  mov     [rbp+0BE0h+var_C38], eax
0x18002a908  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002a90f  lea     rax, [rbp+0BE0h+var_C50]
0x18002a913  mov     r9d, r12d
0x18002a916  mov     [rsp+0CE0h+var_CC0], rax
0x18002a91b  call    McGenEventWrite_EventWriteTransfer
0x18002a920  lea     rax, [rsp+0CE0h+var_C98]
0x18002a925  xor     r9d, r9d
0x18002a928  mov     ecx, esi
0x18002a92a  mov     [rsp+0CE0h+var_CC0], rax
0x18002a92f  call    RasLineDrop
0x18002a934  mov     ecx, esi
0x18002a936  call    RasLineCloseCall
0x18002a93b  mov     rcx, [rbp+0BE0h+var_30]
0x18002a942  xor     rcx, rsp; StackCookie
0x18002a945  call    __security_check_cookie
0x18002a94a  mov     rbx, [rsp+0CE0h+arg_10]
0x18002a952  add     rsp, 0CC0h
0x18002a959  pop     r14
0x18002a95b  pop     r12
0x18002a95d  pop     rdi
0x18002a95e  pop     rsi
0x18002a95f  pop     rbp
0x18002a960  retn
0x18002a962  cmp     [rdi+4], r14d
0x18002a966  jnz     short loc_18002A9C7
0x18002a968  cmp     [rdi+8], r14d
0x18002a96c  jnz     short loc_18002A9C7
0x18002a96e  test    cs:byte_1800CF404, 10h
0x18002a975  jz      short loc_18002A920
0x18002a977  mov     r8d, [rdi+10h]
0x18002a97b  lea     rdx, aRasOrRoutingIs; "Ras or Routing is not enabled for devic"...
0x18002a982  lea     rcx, [rbp+0BE0h+var_830]
0x18002a989  mov     word ptr [rbp+0BE0h+var_830], r14w
0x18002a991  call    FormatRRASErrorString
0x18002a996  test    cs:byte_1800CF404, 10h
0x18002a99d  jz      short loc_18002A920
0x18002a99f  lea     rax, [rbp+0BE0h+var_830]
0x18002a9a6  inc     rbx
0x18002a9a9  cmp     [rax+rbx*2], r14w
0x18002a9ae  jnz     short loc_18002A9A6
0x18002a9b0  lea     rcx, [rbp+0BE0h+var_830]
0x18002a9b7  mov     [rbp+0BE0h+var_C40], rcx
0x18002a9bb  lea     rdx, RasDdmTraceInfo
0x18002a9c2  jmp     loc_18002A8FA
0x18002a9c7  lea     rdx, [rbp+0BE0h+var_C30]
0x18002a9cb  mov     [rbp+0BE0h+var_C30], 400h
0x18002a9d2  mov     ecx, esi
0x18002a9d4  call    RasLineGetCallInfo
0x18002a9d9  test    eax, eax
0x18002a9db  jnz     loc_18002A920
0x18002a9e1  mov     eax, 1
0x18002a9e6  lock xadd [rdi+130h], eax
0x18002a9ee  inc     eax
0x18002a9f0  cmp     eax, [rdi+12Ch]
0x18002a9f6  jbe     short loc_18002AA1F
0x18002a9f8  lock add [rdi+130h], ebx
0x18002a9ff  test    cs:byte_1800CF404, 10h
0x18002aa06  jz      loc_18002A920
0x18002aa0c  lea     rcx, aUnableToFindFr; "Unable to find free ports."
0x18002aa13  inc     rbx
0x18002aa16  cmp     [rcx+rbx*2], r14w
0x18002aa1b  jnz     short loc_18002AA13
0x18002aa1d  jmp     short loc_18002A9B7
0x18002aa1f  mov     eax, [rdi+134h]
0x18002aa25  lea     rcx, [rbp+0BE0h+var_C30]
0x18002aa29  mov     dword ptr [rsp+0CE0h+var_C88], eax
0x18002aa2d  mov     eax, [rbp+0BE0h+var_B10]
0x18002aa33  mov     dword ptr [rsp+0CE0h+var_C88+4], eax
0x18002aa37  mov     eax, [rbp+0BE0h+var_B0C]
0x18002aa3d  add     rcx, rax
0x18002aa40  test    [rbp+0BE0h+var_BB0], 8
0x18002aa44  mov     qword ptr [rsp+0CE0h+var_C88+8], rcx
0x18002aa49  jz      short loc_18002AABA
0x18002aa4b  mov     eax, [rbp+0BE0h+var_BA8]
0x18002aa4e  lea     rbx, [rbp+0BE0h+var_C30]
0x18002aa52  add     rbx, rax
0x18002aa55  lea     rdx, asc_1800A4930; ":"
0x18002aa5c  mov     rcx, rbx; Str
0x18002aa5f  call    cs:__imp_strstr
0x18002aa66  nop     dword ptr [rax+rax+00h]
0x18002aa6b  mov     rcx, rbx; S
0x18002aa6e  test    rax, rax
0x18002aa71  jnz     short loc_18002AA8D
0x18002aa73  mov     dword ptr [rsp+0CE0h+Addr.u], 1
0x18002aa7b  call    cs:__imp_inet_addr
0x18002aa82  nop     dword ptr [rax+rax+00h]
0x18002aa87  mov     dword ptr [rsp+0CE0h+Addr.u+4], eax
0x18002aa8b  jmp     short loc_18002AAA8
0x18002aa8d  lea     r8, [rsp+0CE0h+Addr.u+4]; Addr
0x18002aa92  mov     dword ptr [rsp+0CE0h+Addr.u], r12d
0x18002aa97  lea     rdx, [rsp+0CE0h+Terminator]; Terminator
0x18002aa9c  call    cs:__imp_RtlIpv6StringToAddressA
0x18002aaa3  nop     dword ptr [rax+rax+00h]
0x18002aaa8  movups  xmm0, xmmword ptr [rsp+0CE0h+Addr.u]
0x18002aaad  mov     eax, [rsp+0CE0h+var_CA0]
0x18002aab1  mov     dword ptr [rsp+0CE0h+var_C68], eax
0x18002aab5  movups  [rsp+0CE0h+var_C78], xmm0
0x18002aaba  test    [rbp+0BE0h+var_BC4], 8
0x18002aabe  jz      short loc_18002AB2E
0x18002aac0  mov     eax, [rbp+0BE0h+var_BBC]
0x18002aac3  lea     rbx, [rbp+0BE0h+var_C30]
0x18002aac7  add     rbx, rax
0x18002aaca  lea     rdx, asc_1800A4930; ":"
0x18002aad1  mov     rcx, rbx; Str
0x18002aad4  call    cs:__imp_strstr
0x18002aadb  nop     dword ptr [rax+rax+00h]
0x18002aae0  mov     rcx, rbx; S
0x18002aae3  test    rax, rax
0x18002aae6  jnz     short loc_18002AB02
0x18002aae8  mov     dword ptr [rsp+0CE0h+Addr.u], 1
0x18002aaf0  call    cs:__imp_inet_addr
0x18002aaf7  nop     dword ptr [rax+rax+00h]
0x18002aafc  mov     dword ptr [rsp+0CE0h+Addr.u+4], eax
0x18002ab00  jmp     short loc_18002AB1D
0x18002ab02  lea     r8, [rsp+0CE0h+Addr.u+4]; Addr
0x18002ab07  mov     dword ptr [rsp+0CE0h+Addr.u], r12d
0x18002ab0c  lea     rdx, [rsp+0CE0h+Terminator]; Terminator
0x18002ab11  call    cs:__imp_RtlIpv6StringToAddressA
0x18002ab18  nop     dword ptr [rax+rax+00h]
0x18002ab1d  movups  xmm0, xmmword ptr [rsp+0CE0h+Addr.u]
0x18002ab22  mov     eax, [rsp+0CE0h+var_CA0]
0x18002ab26  mov     dword ptr [rbp+0BE0h+var_C58+4], eax
0x18002ab29  movups  [rsp+0CE0h+var_C68+4], xmm0
0x18002ab2e  lea     r9, [rsp+0CE0h+var_C88]
0x18002ab33  mov     r8d, r12d
0x18002ab36  mov     edx, esi
0x18002ab38  xor     ecx, ecx
0x18002ab3a  call    ?DdmNotifyCaller@@YAXPEAXKW4_DDM_DRIVER_NOTIFICATION_MSG_ID@@0@Z; DdmNotifyCaller(void *,ulong,_DDM_DRIVER_NOTIFICATION_MSG_ID,void *)
0x18002ab3f  jmp     loc_18002A93B
```
