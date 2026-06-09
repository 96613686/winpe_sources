# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::IncomingLEOobPairing(void)

- ea: `0x18002fd84`
- end: `0x18002ff03`
- name: `?IncomingLEOobPairing@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ`
- size: `383`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180030930`

## callees

- `0x18000270c`
- `0x180012384`
- `0x18002c9b8`
- `0x18002dcb0`
- `0x18002fd84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fe50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fe50`
- `deviceassociation!DafCloseAssociationContext` at `0x18002fe42`
- `deviceassociation!DafCloseAssociationContext` at `0x18002fe42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::IncomingLEOobPairing(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *this,
        __int64 a2,
        __int64 a3)
{
  char v4; // di
  unsigned int v5; // ebx
  __int64 v6; // rbp
  DWORD LastError; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // edx
  int v11; // r8d
  int v12; // eax
  bool v13; // cf
  _QWORD v15[2]; // [rsp+60h] [rbp-38h] BYREF
  unsigned int v16; // [rsp+A0h] [rbp+8h] BYREF

  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *((_QWORD *)WPP_GLOBAL_Control + 5));
  v15[0] = this;
  v15[1] = &v16;
  v5 = wil::ResultFromException__lambda_16d72a4e5775df5b079aaa4debecd85d___(v15, a2, a3);
  v16 = v5;
  v6 = *((_QWORD *)this + 255);
  if ( v6 )
  {
    LastError = GetLastError();
    DafCloseAssociationContext(v6, v8, v9);
    SetLastError(LastError);
    v5 = v16;
  }
  *((_QWORD *)this + 255) = 0;
  memset_0((char *)this + 152, 0, 0x760u);
  v12 = 0;
  if ( v5 )
    v13 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v13 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (LOBYTE(v12) = !v13, !v12) )
    v4 = 0;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = v4;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, *((_QWORD *)WPP_GLOBAL_Control + 5));
    return v16;
  }
  return v5;
}

```

## disassembly

```asm
0x18002fd84  mov     [rsp+arg_8], rbx
0x18002fd89  mov     [rsp+arg_10], rbp
0x18002fd8e  push    rsi
0x18002fd8f  push    rdi
0x18002fd90  push    r12
0x18002fd92  push    r14
0x18002fd94  push    r15
0x18002fd96  sub     rsp, 70h
0x18002fd9a  mov     rsi, rcx
0x18002fd9d  lea     r14, WPP_GLOBAL_Control
0x18002fda4  mov     dil, 1
0x18002fda7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fdae  cmp     rcx, r14
0x18002fdb1  jz      short loc_18002FDBE
0x18002fdb3  cmp     byte ptr [rcx+19h], 5
0x18002fdb7  jb      short loc_18002FDBE
0x18002fdb9  mov     dl, dil
0x18002fdbc  jmp     short loc_18002FDC0
0x18002fdbe  xor     dl, dl
0x18002fdc0  lea     r15, WPP_RECORDER_INITIALIZED
0x18002fdc7  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002fdce  setnz   r8b
0x18002fdd2  lea     r12, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002fdd9  test    dl, dl
0x18002fddb  jnz     short loc_18002FDE2
0x18002fddd  test    r8b, r8b
0x18002fde0  jz      short loc_18002FE00
0x18002fde2  mov     [rsp+98h+var_50], rsi
0x18002fde7  mov     [rsp+98h+var_60], r12
0x18002fdec  mov     [rsp+98h+var_68], 2Fh ; '/'
0x18002fdf3  mov     r9, [rcx+28h]
0x18002fdf7  mov     rcx, [rcx+10h]
0x18002fdfb  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002fe00  mov     [rsp+98h+var_38], rsi
0x18002fe05  lea     rax, [rsp+98h+arg_0]
0x18002fe0d  mov     [rsp+98h+var_30], rax
0x18002fe12  lea     rcx, [rsp+98h+var_38]
0x18002fe17  call    wil__ResultFromException__lambda_16d72a4e5775df5b079aaa4debecd85d___
0x18002fe1c  mov     ebx, eax
0x18002fe1e  mov     [rsp+98h+arg_0], eax
0x18002fe25  mov     rbp, [rsi+7F8h]
0x18002fe2c  test    rbp, rbp
0x18002fe2f  jz      short loc_18002FE64
0x18002fe31  call    cs:__imp_GetLastError
0x18002fe38  nop     dword ptr [rax+rax+00h]
0x18002fe3d  mov     ebx, eax
0x18002fe3f  mov     rcx, rbp
0x18002fe42  call    cs:__imp_DafCloseAssociationContext
0x18002fe49  nop     dword ptr [rax+rax+00h]
0x18002fe4e  mov     ecx, ebx; dwErrCode
0x18002fe50  call    cs:__imp_SetLastError
0x18002fe57  nop     dword ptr [rax+rax+00h]
0x18002fe5c  nop
0x18002fe5d  mov     ebx, [rsp+98h+arg_0]
0x18002fe64  and     qword ptr [rsi+7F8h], 0
0x18002fe6c  lea     rcx, [rsi+98h]; void *
0x18002fe73  xor     edx, edx; Val
0x18002fe75  mov     r8d, 760h; Size
0x18002fe7b  call    memset_0
0x18002fe80  xor     eax, eax
0x18002fe82  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe89  test    ebx, ebx
0x18002fe8b  jnz     short loc_18002FE93
0x18002fe8d  cmp     byte ptr [rcx+19h], 5
0x18002fe91  jmp     short loc_18002FE97
0x18002fe93  cmp     byte ptr [rcx+19h], 2
0x18002fe97  setnb   al
0x18002fe9a  cmp     rcx, r14
0x18002fe9d  jz      short loc_18002FEA3
0x18002fe9f  test    eax, eax
0x18002fea1  jnz     short loc_18002FEA6
0x18002fea3  xor     dil, dil
0x18002fea6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002fead  setnz   r8b
0x18002feb1  test    dil, dil
0x18002feb4  jnz     short loc_18002FEBB
0x18002feb6  test    r8b, r8b
0x18002feb9  jz      short loc_18002FEE7
0x18002febb  mov     [rsp+98h+var_48], ebx
0x18002febf  mov     [rsp+98h+var_50], rsi
0x18002fec4  mov     [rsp+98h+var_60], r12
0x18002fec9  mov     [rsp+98h+var_68], 32h ; '2'
0x18002fed0  mov     r9, [rcx+28h]
0x18002fed4  mov     dl, dil
0x18002fed7  mov     rcx, [rcx+10h]
0x18002fedb  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002fee0  mov     ebx, [rsp+98h+arg_0]
0x18002fee7  mov     eax, ebx
0x18002fee9  lea     r11, [rsp+98h+var_28]
0x18002feee  mov     rbx, [r11+38h]
0x18002fef2  mov     rbp, [r11+40h]
0x18002fef6  mov     rsp, r11
0x18002fef9  pop     r15
0x18002fefb  pop     r14
0x18002fefd  pop     r12
0x18002feff  pop     rdi
0x18002ff00  pop     rsi
0x18002ff01  retn
```
