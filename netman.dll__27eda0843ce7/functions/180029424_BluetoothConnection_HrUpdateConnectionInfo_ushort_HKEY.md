# BluetoothConnection::HrUpdateConnectionInfo(ushort *,HKEY__ *)

- ea: `0x180029424`
- end: `0x1800295f1`
- name: `?HrUpdateConnectionInfo@BluetoothConnection@@AEAAJPEAGPEAUHKEY__@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(BluetoothConnection *this, const BYTE *, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180029128`

## callees

- `0x180001710`
- `0x1800052b4`
- `0x18000538c`
- `0x180019200`
- `0x18002930c`
- `0x180029424`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800294ea`
- `ADVAPI32!RegSetValueExW` at `0x180029592`
- `ADVAPI32!RegSetValueExW` at `0x1800294ea`
- `ADVAPI32!RegSetValueExW` at `0x180029592`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BluetoothConnection::HrUpdateConnectionInfo(BluetoothConnection *this, const BYTE *a2, HKEY a3)
{
  BluetoothConnection *v5; // rcx
  signed int RegValue; // ebx
  __int64 v7; // rax
  LSTATUS v8; // eax
  bool v9; // sf
  BluetoothConnection *v10; // rcx
  LSTATUS v11; // eax
  BYTE Data[8]; // [rsp+30h] [rbp-38h] BYREF

  *(_DWORD *)Data = 0;
  v5 = (BluetoothConnection *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids);
  RegValue = BluetoothConnection::HrQueryRegValue(v5, a3, c_szPnPInstanceId, 0);
  if ( RegValue == -2147024894 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids, a2);
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&a2[2 * v7] );
    v8 = RegSetValueExW(a3, c_szPnPInstanceId, 0, 1u, a2, 2 * v7);
    RegValue = v8;
    if ( v8 > 0 )
      RegValue = (unsigned __int16)v8 | 0x80070000;
  }
  v9 = RegValue < 0;
  if ( !RegValue )
  {
    v10 = (BluetoothConnection *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids);
    RegValue = BluetoothConnection::HrQueryRegValue(v10, a3, c_szMediaSubType, 0);
    if ( RegValue == -2147024894 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids, 7);
      *(_DWORD *)Data = 7;
      v11 = RegSetValueExW(a3, c_szMediaSubType, 0, 4u, Data, 4u);
      RegValue = v11;
      if ( v11 > 0 )
        RegValue = (unsigned __int16)v11 | 0x80070000;
    }
    v9 = RegValue < 0;
  }
  if ( v9 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids,
      (unsigned int)RegValue);
  return (unsigned int)RegValue;
}

```

## disassembly

```asm
0x180029424  mov     [rsp+arg_0], rbx
0x180029429  push    rbp
0x18002942a  push    rsi
0x18002942b  push    rdi
0x18002942c  push    r14
0x18002942e  push    r15
0x180029430  sub     rsp, 40h
0x180029434  mov     rax, cs:__security_cookie
0x18002943b  xor     rax, rsp
0x18002943e  mov     [rsp+68h+var_30], rax
0x180029443  xor     ebp, ebp
0x180029445  mov     rsi, r8
0x180029448  mov     dword ptr [rsp+68h+Data], ebp
0x18002944c  mov     rdi, rdx
0x18002944f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029456  lea     r14, WPP_GLOBAL_Control
0x18002945d  lea     r15, WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids
0x180029464  cmp     rcx, r14
0x180029467  jz      short loc_18002947E
0x180029469  test    byte ptr [rcx+1Ch], 8
0x18002946d  jz      short loc_18002947E
0x18002946f  mov     rcx, [rcx+10h]
0x180029473  lea     edx, [rbp+0Ch]
0x180029476  mov     r8, r15
0x180029479  call    WPP_SF_
0x18002947e  xor     r9d, r9d; unsigned __int8 **
0x180029481  lea     r8, ?c_szPnPInstanceId@@3PAGA; "PnpInstanceID"
0x180029488  mov     rdx, rsi; HKEY
0x18002948b  call    ?HrQueryRegValue@BluetoothConnection@@AEAAJPEAUHKEY__@@PEAGPEAPEAE@Z; BluetoothConnection::HrQueryRegValue(HKEY__ *,ushort *,uchar * *)
0x180029490  mov     ebx, eax
0x180029492  cmp     eax, 80070002h
0x180029497  jnz     short loc_1800294FF
0x180029499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800294a0  cmp     rcx, r14
0x1800294a3  jz      short loc_1800294BF
0x1800294a5  test    byte ptr [rcx+1Ch], 8
0x1800294a9  jz      short loc_1800294BF
0x1800294ab  mov     rcx, [rcx+10h]
0x1800294af  mov     edx, 0Dh
0x1800294b4  mov     r9, rdi
0x1800294b7  mov     r8, r15
0x1800294ba  call    WPP_SF_S
0x1800294bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800294c3  inc     rax
0x1800294c6  cmp     [rdi+rax*2], bp
0x1800294ca  jnz     short loc_1800294C3
0x1800294cc  add     eax, eax
0x1800294ce  lea     rdx, ?c_szPnPInstanceId@@3PAGA; "PnpInstanceID"
0x1800294d5  mov     [rsp+68h+cbData], eax; cbData
0x1800294d9  mov     r9d, 1; dwType
0x1800294df  xor     r8d, r8d; Reserved
0x1800294e2  mov     [rsp+68h+lpData], rdi; lpData
0x1800294e7  mov     rcx, rsi; hKey
0x1800294ea  call    cs:__imp_RegSetValueExW
0x1800294f0  mov     ebx, eax
0x1800294f2  test    eax, eax
0x1800294f4  jle     short loc_1800294FF
0x1800294f6  movzx   ebx, ax
0x1800294f9  or      ebx, 80070000h
0x1800294ff  test    ebx, ebx
0x180029501  jnz     loc_1800295A9
0x180029507  mov     rcx, cs:WPP_GLOBAL_Control
0x18002950e  cmp     rcx, r14
0x180029511  jz      short loc_180029528
0x180029513  test    byte ptr [rcx+1Ch], 8
0x180029517  jz      short loc_180029528
0x180029519  mov     rcx, [rcx+10h]
0x18002951d  lea     edx, [rbx+0Eh]
0x180029520  mov     r8, r15
0x180029523  call    WPP_SF_
0x180029528  xor     r9d, r9d; unsigned __int8 **
0x18002952b  lea     r8, ?c_szMediaSubType@@3PAGA; "MediaSubType"
0x180029532  mov     rdx, rsi; HKEY
0x180029535  call    ?HrQueryRegValue@BluetoothConnection@@AEAAJPEAUHKEY__@@PEAGPEAPEAE@Z; BluetoothConnection::HrQueryRegValue(HKEY__ *,ushort *,uchar * *)
0x18002953a  mov     ebx, eax
0x18002953c  cmp     eax, 80070002h
0x180029541  jnz     short loc_1800295A7
0x180029543  mov     rcx, cs:WPP_GLOBAL_Control
0x18002954a  mov     ebx, 7
0x18002954f  cmp     rcx, r14
0x180029552  jz      short loc_18002956C
0x180029554  test    byte ptr [rcx+1Ch], 8
0x180029558  jz      short loc_18002956C
0x18002955a  mov     rcx, [rcx+10h]
0x18002955e  lea     edx, [rbx+8]
0x180029561  mov     r9d, ebx
0x180029564  mov     r8, r15
0x180029567  call    WPP_SF_d
0x18002956c  mov     r9d, 4; dwType
0x180029572  mov     dword ptr [rsp+68h+Data], ebx
0x180029576  lea     rax, [rsp+68h+Data]
0x18002957b  mov     [rsp+68h+cbData], r9d; cbData
0x180029580  xor     r8d, r8d; Reserved
0x180029583  mov     [rsp+68h+lpData], rax; lpData
0x180029588  lea     rdx, ?c_szMediaSubType@@3PAGA; "MediaSubType"
0x18002958f  mov     rcx, rsi; hKey
0x180029592  call    cs:__imp_RegSetValueExW
0x180029598  mov     ebx, eax
0x18002959a  test    eax, eax
0x18002959c  jle     short loc_1800295A7
0x18002959e  movzx   ebx, ax
0x1800295a1  or      ebx, 80070000h
0x1800295a7  test    ebx, ebx
0x1800295a9  jns     short loc_1800295D1
0x1800295ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800295b2  cmp     rcx, r14
0x1800295b5  jz      short loc_1800295D1
0x1800295b7  test    byte ptr [rcx+1Ch], 1
0x1800295bb  jz      short loc_1800295D1
0x1800295bd  mov     rcx, [rcx+10h]
0x1800295c1  mov     edx, 10h
0x1800295c6  mov     r9d, ebx
0x1800295c9  mov     r8, r15
0x1800295cc  call    WPP_SF_d
0x1800295d1  mov     eax, ebx
0x1800295d3  mov     rcx, [rsp+68h+var_30]
0x1800295d8  xor     rcx, rsp; StackCookie
0x1800295db  call    __security_check_cookie
0x1800295e0  mov     rbx, [rsp+68h+arg_0]
0x1800295e5  add     rsp, 40h
0x1800295e9  pop     r15
0x1800295eb  pop     r14
0x1800295ed  pop     rdi
0x1800295ee  pop     rsi
0x1800295ef  pop     rbp
0x1800295f0  retn
```
