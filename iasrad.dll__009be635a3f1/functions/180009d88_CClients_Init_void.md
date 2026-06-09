# CClients::Init(void)

- ea: `0x180009d88`
- end: `0x180009e3c`
- name: `?Init@CClients@@QEAAJXZ`
- size: `180`
- prototype: `__int64 __fastcall(CClients *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b560`

## callees

- `0x180009d88`
- `0x18002e230`

## import_xrefs

- `iassvcs!IASGetProductLimits` at `0x180009db2`
- `iassvcs!IASGetProductLimits` at `0x180009db2`
- `KERNEL32!GetLastError` at `0x180009e1d`
- `KERNEL32!GetLastError` at `0x180009e1d`
- `KERNEL32!CreateEventW` at `0x180009e0e`
- `KERNEL32!CreateEventW` at `0x180009e0e`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180009df8`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180009df8`

## pseudocode

```c
signed int __fastcall CClients::Init(CClients *this)
{
  signed int result; // eax
  bool v3; // cc
  bool v4; // zf
  HANDLE EventW; // rax
  __int64 v6; // [rsp+30h] [rbp-28h] BYREF
  int v7; // [rsp+38h] [rbp-20h]

  v6 = 0;
  v7 = 0;
  result = IASGetProductLimits(0, &v6);
  v3 = result <= 0;
  if ( !result )
  {
    v4 = HIDWORD(v6) == 0;
    *((_DWORD *)this + 20) = v6;
    *((_BYTE *)this + 84) = !v4;
    result = CoGetClassObject(
               &GUID_6bc096da_0ce6_11d1_baae_00c04fc2e20d,
               1u,
               0,
               &GUID_00000001_0000_0000_c000_000000000046,
               (LPVOID *)this + 5);
    if ( result < 0 )
      return result;
    EventW = CreateEventW(0, 1, 1, 0);
    *((_QWORD *)this + 9) = EventW;
    if ( EventW )
      return 0;
    result = GetLastError();
    v3 = result <= 0;
  }
  if ( !v3 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180009d88  push    rbx
0x180009d8a  sub     rsp, 50h
0x180009d8e  mov     rax, cs:__security_cookie
0x180009d95  xor     rax, rsp
0x180009d98  mov     [rsp+58h+var_18], rax
0x180009d9d  xor     eax, eax
0x180009d9f  lea     rdx, [rsp+58h+var_28]
0x180009da4  mov     rbx, rcx
0x180009da7  mov     [rsp+58h+var_28], rax
0x180009dac  xor     ecx, ecx
0x180009dae  mov     [rsp+58h+var_20], eax
0x180009db2  call    cs:__imp_IASGetProductLimits
0x180009db8  test    eax, eax
0x180009dba  jz      short loc_180009DC8
0x180009dbc  jle     short loc_180009E29
0x180009dbe  movzx   eax, ax
0x180009dc1  or      eax, 80070000h
0x180009dc6  jmp     short loc_180009E29
0x180009dc8  mov     eax, dword ptr [rsp+58h+var_28]
0x180009dcc  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180009dd3  cmp     dword ptr [rsp+58h+var_28+4], 0
0x180009dd8  lea     rcx, _GUID_6bc096da_0ce6_11d1_baae_00c04fc2e20d; rclsid
0x180009ddf  mov     [rbx+50h], eax
0x180009de2  setnz   al
0x180009de5  xor     r8d, r8d; pvReserved
0x180009de8  mov     [rbx+54h], al
0x180009deb  lea     rax, [rbx+28h]
0x180009def  mov     [rsp+58h+ppv], rax; ppv
0x180009df4  lea     edx, [r8+1]; dwClsContext
0x180009df8  call    cs:__imp_CoGetClassObject
0x180009dfe  test    eax, eax
0x180009e00  js      short loc_180009E29
0x180009e02  xor     r9d, r9d; lpName
0x180009e05  xor     ecx, ecx; lpEventAttributes
0x180009e07  lea     edx, [r9+1]; bManualReset
0x180009e0b  mov     r8d, edx; bInitialState
0x180009e0e  call    cs:__imp_CreateEventW
0x180009e14  mov     [rbx+48h], rax
0x180009e18  test    rax, rax
0x180009e1b  jnz     short loc_180009E27
0x180009e1d  call    cs:__imp_GetLastError
0x180009e23  test    eax, eax
0x180009e25  jmp     short loc_180009DBC
0x180009e27  xor     eax, eax
0x180009e29  mov     rcx, [rsp+58h+var_18]
0x180009e2e  xor     rcx, rsp; StackCookie
0x180009e31  call    __security_check_cookie
0x180009e36  add     rsp, 50h
0x180009e3a  pop     rbx
0x180009e3b  retn
```
