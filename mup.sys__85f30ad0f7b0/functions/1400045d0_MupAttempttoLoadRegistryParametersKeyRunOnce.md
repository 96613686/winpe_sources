# MupAttempttoLoadRegistryParametersKeyRunOnce

- ea: `0x1400045d0`
- end: `0x1400046ac`
- name: `MupAttempttoLoadRegistryParametersKeyRunOnce`
- size: `220`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140002a14`
- `0x140002e74`
- `0x1400045d0`
- `0x140016894`
- `0x140016a34`
- `0x140016b94`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140004652`
- `ntoskrnl!ZwClose` at `0x140004652`

## pseudocode

```c
__int64 __fastcall MupAttempttoLoadRegistryParametersKeyRunOnce(PRTL_RUN_ONCE a1, void **a2, PVOID *a3)
{
  HANDLE *v3; // rbx
  int v5; // edi

  v3 = a2 + 3;
  v5 = MupiOpenParametersKeyFromRegistry(a2 + 3);
  if ( v5 < 0
    || (MupEnableMailslots = MupiReadEnableMailslotsFromRegistry(*v3, 0),
        v5 = MupiRegisterParametersKeyRegistryChangeNotification(a2),
        v5 < 0) )
  {
    if ( *v3 )
    {
      ZwClose(*v3);
      *v3 = 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_511a9a8026a53b8720c76e64765e5363_Traceguids,
        (unsigned int)v5);
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x1400045d0  mov     [rsp+arg_0], rbx
0x1400045d5  mov     [rsp+arg_8], rsi
0x1400045da  push    rdi
0x1400045db  sub     rsp, 20h
0x1400045df  lea     rbx, [rdx+18h]
0x1400045e3  mov     rsi, rdx
0x1400045e6  mov     rcx, rbx
0x1400045e9  call    MupiOpenParametersKeyFromRegistry
0x1400045ee  mov     edi, eax
0x1400045f0  test    eax, eax
0x1400045f2  js      short loc_14000464A
0x1400045f4  mov     rcx, [rbx]; KeyHandle
0x1400045f7  xor     edx, edx
0x1400045f9  call    MupiReadEnableMailslotsFromRegistry
0x1400045fe  mov     rcx, rsi
0x140004601  mov     cs:MupEnableMailslots, al
0x140004607  call    MupiRegisterParametersKeyRegistryChangeNotification
0x14000460c  mov     edi, eax
0x14000460e  test    eax, eax
0x140004610  js      short loc_14000464A
0x140004612  mov     rcx, cs:WPP_GLOBAL_Control
0x140004619  lea     rax, WPP_GLOBAL_Control
0x140004620  cmp     rcx, rax
0x140004623  jz      short loc_140004643
0x140004625  test    dword ptr [rcx+2Ch], 2000000h
0x14000462c  jz      short loc_140004643
0x14000462e  mov     rcx, [rcx+18h]
0x140004632  lea     r8, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids
0x140004639  mov     edx, 0Ah
0x14000463e  call    WPP_SF_
0x140004643  mov     eax, 1
0x140004648  jmp     short loc_14000469B
0x14000464a  mov     rcx, [rbx]; Handle
0x14000464d  test    rcx, rcx
0x140004650  jz      short loc_140004665
0x140004652  call    cs:__imp_ZwClose
0x140004659  nop     dword ptr [rax+rax+00h]
0x14000465e  mov     qword ptr [rbx], 0
0x140004665  mov     rcx, cs:WPP_GLOBAL_Control
0x14000466c  lea     rax, WPP_GLOBAL_Control
0x140004673  cmp     rcx, rax
0x140004676  jz      short loc_140004699
0x140004678  test    dword ptr [rcx+2Ch], 1000000h
0x14000467f  jz      short loc_140004699
0x140004681  mov     rcx, [rcx+18h]
0x140004685  lea     r8, WPP_511a9a8026a53b8720c76e64765e5363_Traceguids
0x14000468c  mov     edx, 0Bh
0x140004691  mov     r9d, edi
0x140004694  call    WPP_SF_d
0x140004699  xor     eax, eax
0x14000469b  mov     rbx, [rsp+28h+arg_0]
0x1400046a0  mov     rsi, [rsp+28h+arg_8]
0x1400046a5  add     rsp, 20h
0x1400046a9  pop     rdi
0x1400046aa  retn
```
