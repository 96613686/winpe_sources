# FwRegSetBinary(HKEY__ *,ushort const *,ushort const *,uchar *,ulong)

- ea: `0x180001a58`
- end: `0x180001b79`
- name: `?FwRegSetBinary@@YAJPEAUHKEY__@@PEBG1PEAEK@Z`
- size: `289`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180001820`

## callees

- `0x180001a58`
- `0x1800028e0`
- `0x1800031a0`
- `0x180004750`
- `0x1800047e0`
- `0x18001f5f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180001aee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180001aee`

## string_xrefs

- `0x180001b50`: `RegSetValueExW`
- `0x180001b37`: `FwRegSetBinary`
- `0x180001b57`: `FwRegSetBinary`
- `0x180001b69`: `FwRegSetBinary`

## pseudocode

```c
__int64 __fastcall FwRegSetBinary(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        DWORD cbData)
{
  int v5; // ebx
  __int64 v8; // rbp
  int Key; // eax
  unsigned int v10; // eax

  v5 = 0;
  v8 = -2147483646;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids,
      (_DWORD)a2,
      (__int64)L"Collection");
  if ( a2 )
  {
    Key = FwRegCreateKey(HKEY_LOCAL_MACHINE, a2, 2u);
    v5 = Key;
    if ( Key < 0 )
    {
      FwReportReturnError("FwRegSetBinary", (unsigned int)Key);
      goto LABEL_9;
    }
    v8 = 0;
  }
  v10 = RegSetValueExW((HKEY)v8, L"Collection", 0, 3u, a4, cbData);
  if ( v10 )
    v5 = FwReportErrorAsWinError("FwRegSetBinary", "RegSetValueExW", v10);
LABEL_9:
  FwRegCloseKey(0);
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwRegSetBinary", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180001a58  mov     rax, rsp
0x180001a5b  mov     [rax+18h], r8
0x180001a5f  push    rbx
0x180001a60  push    rbp
0x180001a61  push    rsi
0x180001a62  push    rdi
0x180001a63  push    r12
0x180001a65  push    r14
0x180001a67  sub     rsp, 38h
0x180001a6b  xor     ebx, ebx
0x180001a6d  mov     r14, r9
0x180001a70  xor     edi, edi
0x180001a72  mov     rsi, rdx
0x180001a75  mov     [rax+18h], rdi
0x180001a79  mov     rbp, 0FFFFFFFF80000002h
0x180001a80  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a87  lea     rax, WPP_GLOBAL_Control
0x180001a8e  lea     r12, ValueName; "Collection"
0x180001a95  cmp     rcx, rax
0x180001a98  jz      short loc_180001AA0
0x180001a9a  test    byte ptr [rcx+1Ch], 8
0x180001a9e  jnz     short loc_180001B13
0x180001aa0  test    rsi, rsi
0x180001aa3  jz      short loc_180001ACF
0x180001aa5  lea     r9, [rsp+68h+arg_10]
0x180001aad  mov     r8d, 2; samDesired
0x180001ab3  mov     rdx, rsi; lpSubKey
0x180001ab6  mov     rcx, rbp; hKey
0x180001ab9  call    FwRegCreateKey
0x180001abe  mov     ebx, eax
0x180001ac0  test    eax, eax
0x180001ac2  js      short loc_180001B35
0x180001ac4  mov     rdi, [rsp+68h+arg_10]
0x180001acc  mov     rbp, rdi
0x180001acf  mov     eax, [rsp+68h+arg_20]
0x180001ad6  mov     r9d, 3; dwType
0x180001adc  mov     [rsp+68h+cbData], eax; cbData
0x180001ae0  xor     r8d, r8d; Reserved
0x180001ae3  mov     rdx, r12; lpValueName
0x180001ae6  mov     [rsp+68h+lpData], r14; lpData
0x180001aeb  mov     rcx, rbp; hKey
0x180001aee  call    cs:__imp_RegSetValueExW
0x180001af4  test    eax, eax
0x180001af6  jnz     short loc_180001B4D
0x180001af8  mov     rcx, rdi
0x180001afb  call    FwRegCloseKey
0x180001b00  test    ebx, ebx
0x180001b02  js      short loc_180001B67
0x180001b04  mov     eax, ebx
0x180001b06  add     rsp, 38h
0x180001b0a  pop     r14
0x180001b0c  pop     r12
0x180001b0e  pop     rdi
0x180001b0f  pop     rsi
0x180001b10  pop     rbp
0x180001b11  pop     rbx
0x180001b12  retn
0x180001b13  mov     rcx, [rcx+10h]
0x180001b17  lea     r8, WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids
0x180001b1e  mov     edx, 1Ah
0x180001b23  mov     [rsp+68h+lpData], r12
0x180001b28  mov     r9, rsi
0x180001b2b  call    WPP_SF_SS
0x180001b30  jmp     loc_180001AA0
0x180001b35  mov     edx, eax
0x180001b37  lea     rcx, aFwregsetbinary; "FwRegSetBinary"
0x180001b3e  call    FwReportReturnError
0x180001b43  mov     rdi, [rsp+68h+arg_10]
0x180001b4b  jmp     short loc_180001AF8
0x180001b4d  mov     r8d, eax
0x180001b50  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x180001b57  lea     rcx, aFwregsetbinary; "FwRegSetBinary"
0x180001b5e  call    FwReportErrorAsWinError
0x180001b63  mov     ebx, eax
0x180001b65  jmp     short loc_180001AF8
0x180001b67  mov     edx, ebx
0x180001b69  lea     rcx, aFwregsetbinary; "FwRegSetBinary"
0x180001b70  call    FwReportReturnError
0x180001b75  mov     ebx, eax
0x180001b77  jmp     short loc_180001B04
```
