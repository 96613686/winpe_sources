# IopLiveDumpInitRegistrySettings

- ea: `0x1405d9e6c`
- end: `0x1405da034`
- name: `IopLiveDumpInitRegistrySettings`
- size: `456`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140500334`

## callees

- `0x1405d66fc`
- `0x1405d671c`
- `0x1405d9e6c`
- `0x14094b0a0`
- `0x140ab52a8`

## string_xrefs

- `0x1405d9e84`: `\Registry\Machine\System\CurrentControlSet\Control\LiveDump`
- `0x1405d9fd1`: `EnableIoSpaceWriteProtection`
- `0x1405d9f07`: `MirrorSystemPartitionOnly`

## pseudocode

```c
NTSTATUS __fastcall IopLiveDumpInitRegistrySettings(__int64 a1)
{
  NTSTATUS result; // eax
  unsigned int RegistryULongValue; // eax
  int v4; // ecx
  unsigned __int64 v5; // rax
  unsigned int v6; // ecx
  __int16 RegistryBoolValue; // ax
  HANDLE v8; // rcx
  char v9; // al
  HANDLE v10; // rcx
  char v11; // al
  HANDLE v12; // rcx
  __int16 v13; // ax
  HANDLE v14; // rcx
  __int16 v15; // ax
  HANDLE v16; // rcx
  int v17; // eax
  HANDLE v18; // rcx
  int v19; // eax
  HANDLE v20; // rcx
  int v21; // eax
  HANDLE v22; // rcx
  char v23; // [rsp+20h] [rbp-20h]
  _QWORD v24[2]; // [rsp+30h] [rbp-10h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp+18h] BYREF

  Handle = 0;
  v24[0] = 7864438;
  v24[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\LiveDump";
  v23 = 0;
  result = IopOpenRegistryKey(&Handle, 0, v24, 131097, v23);
  if ( result >= 0 )
  {
    RegistryULongValue = IopGetRegistryULongValue(Handle, L"DumpFileSize");
    v4 = *(_DWORD *)(a1 + 80);
    if ( RegistryULongValue )
    {
      v5 = (unsigned __int64)RegistryULongValue << 20;
      v6 = v4 | 0x200;
    }
    else
    {
      v5 = 0;
      v6 = v4 & 0xFFFFFDFF;
    }
    *(_DWORD *)(a1 + 80) = v6;
    *(_QWORD *)(a1 + 1152) = v5;
    RegistryBoolValue = IopGetRegistryBoolValue(Handle, L"UtilizeIOSpace");
    v8 = Handle;
    *(_DWORD *)(a1 + 80) ^= ((unsigned __int16)*(_DWORD *)(a1 + 80)
                           ^ (unsigned __int16)(RegistryBoolValue << 11))
                          & 0x800;
    v9 = IopGetRegistryBoolValue(v8, L"MirrorSystemPartitionOnly");
    v10 = Handle;
    *(_DWORD *)(a1 + 80) ^= ((unsigned __int8)*(_DWORD *)(a1 + 80) ^ (unsigned __int8)(32 * v9)) & 0x20;
    v11 = IopGetRegistryBoolValue(v10, L"EnableInstrumentation");
    v12 = Handle;
    *(_DWORD *)(a1 + 80) ^= ((unsigned __int8)*(_DWORD *)(a1 + 80) ^ (unsigned __int8)(v11 << 7)) & 0x80;
    v13 = IopGetRegistryBoolValue(v12, L"SkipDisablingInterrupts");
    v14 = Handle;
    *(_DWORD *)(a1 + 80) ^= ((unsigned __int16)*(_DWORD *)(a1 + 80) ^ (unsigned __int16)(v13 << 8)) & 0x100;
    v15 = IopGetRegistryBoolValue(v14, L"EnableDynamicLowMemoryThreshold");
    v16 = Handle;
    *(_DWORD *)(a1 + 80) ^= ((unsigned __int16)*(_DWORD *)(a1 + 80) ^ (unsigned __int16)(v15 << 13)) & 0x2000;
    v17 = IopGetRegistryBoolValue(v16, L"EnableAdditionalEventTracing");
    v18 = Handle;
    *(_DWORD *)(a1 + 80) ^= (*(_DWORD *)(a1 + 80) ^ (v17 << 17)) & 0x20000;
    v19 = IopGetRegistryBoolValue(v18, L"EnableIoSpaceCorruptionDetection");
    v20 = Handle;
    *(_DWORD *)(a1 + 80) ^= (*(_DWORD *)(a1 + 80) ^ (v19 << 18)) & 0x40000;
    v21 = IopGetRegistryBoolValue(v20, L"EnableIoSpaceWriteProtection");
    v22 = Handle;
    *(_DWORD *)(a1 + 80) ^= (*(_DWORD *)(a1 + 80) ^ (v21 << 19)) & 0x80000;
    result = IopGetRegistryULongValue(v22, L"SimulateError");
    *(_DWORD *)(a1 + 1248) = result;
  }
  else
  {
    *(_DWORD *)(a1 + 80) &= 0xFFFDD45F;
  }
  if ( Handle )
    return ObCloseHandle(Handle, 0);
  return result;
}

```

## disassembly

```asm
0x1405d9e6c  mov     [rsp-8+arg_0], rbx
0x1405d9e71  push    rbp
0x1405d9e72  mov     rbp, rsp
0x1405d9e75  sub     rsp, 40h
0x1405d9e79  mov     rbx, rcx
0x1405d9e7c  mov     [rbp+Handle], 0
0x1405d9e84  lea     rax, aRegistryMachin_121; "\\Registry\\Machine\\System\\CurrentCon"...
0x1405d9e8b  mov     [rbp+var_10], 780076h
0x1405d9e93  lea     rcx, [rbp+Handle]
0x1405d9e97  mov     [rbp+var_8], rax
0x1405d9e9b  mov     r9d, 20019h
0x1405d9ea1  mov     [rsp+40h+var_20], 0
0x1405d9ea6  lea     r8, [rbp+var_10]
0x1405d9eaa  xor     edx, edx
0x1405d9eac  call    IopOpenRegistryKey
0x1405d9eb1  test    eax, eax
0x1405d9eb3  jns     short loc_1405D9EC1
0x1405d9eb5  and     dword ptr [rbx+50h], 0FFFDD45Fh
0x1405d9ebc  jmp     loc_1405DA018
0x1405d9ec1  mov     rcx, [rbp+Handle]
0x1405d9ec5  lea     rdx, aDumpfilesize; "DumpFileSize"
0x1405d9ecc  call    IopGetRegistryULongValue
0x1405d9ed1  mov     ecx, [rbx+50h]
0x1405d9ed4  test    eax, eax
0x1405d9ed6  jz      short loc_1405D9EE4
0x1405d9ed8  mov     eax, eax
0x1405d9eda  shl     rax, 14h
0x1405d9ede  bts     ecx, 9
0x1405d9ee2  jmp     short loc_1405D9EEA
0x1405d9ee4  xor     eax, eax
0x1405d9ee6  btr     ecx, 9
0x1405d9eea  mov     [rbx+50h], ecx
0x1405d9eed  lea     rdx, aUtilizeiospace; "UtilizeIOSpace"
0x1405d9ef4  mov     [rbx+480h], rax
0x1405d9efb  mov     rcx, [rbp+Handle]
0x1405d9eff  call    IopGetRegistryBoolValue
0x1405d9f04  mov     ecx, [rbx+50h]
0x1405d9f07  lea     rdx, aMirrorsystempa; "MirrorSystemPartitionOnly"
0x1405d9f0e  shl     eax, 0Bh
0x1405d9f11  xor     eax, ecx
0x1405d9f13  and     eax, 800h
0x1405d9f18  xor     eax, ecx
0x1405d9f1a  mov     rcx, [rbp+Handle]
0x1405d9f1e  mov     [rbx+50h], eax
0x1405d9f21  call    IopGetRegistryBoolValue
0x1405d9f26  mov     ecx, [rbx+50h]
0x1405d9f29  lea     rdx, aEnableinstrume; "EnableInstrumentation"
0x1405d9f30  shl     eax, 5
0x1405d9f33  xor     eax, ecx
0x1405d9f35  and     eax, 20h
0x1405d9f38  xor     eax, ecx
0x1405d9f3a  mov     rcx, [rbp+Handle]
0x1405d9f3e  mov     [rbx+50h], eax
0x1405d9f41  call    IopGetRegistryBoolValue
0x1405d9f46  mov     ecx, [rbx+50h]
0x1405d9f49  lea     rdx, aSkipdisablingi; "SkipDisablingInterrupts"
0x1405d9f50  shl     eax, 7
0x1405d9f53  xor     eax, ecx
0x1405d9f55  and     eax, 80h
0x1405d9f5a  xor     eax, ecx
0x1405d9f5c  mov     rcx, [rbp+Handle]
0x1405d9f60  mov     [rbx+50h], eax
0x1405d9f63  call    IopGetRegistryBoolValue
0x1405d9f68  mov     ecx, [rbx+50h]
0x1405d9f6b  lea     rdx, aEnabledynamicl; "EnableDynamicLowMemoryThreshold"
0x1405d9f72  shl     eax, 8
0x1405d9f75  xor     eax, ecx
0x1405d9f77  and     eax, 100h
0x1405d9f7c  xor     eax, ecx
0x1405d9f7e  mov     rcx, [rbp+Handle]
0x1405d9f82  mov     [rbx+50h], eax
0x1405d9f85  call    IopGetRegistryBoolValue
0x1405d9f8a  mov     ecx, [rbx+50h]
0x1405d9f8d  lea     rdx, aEnableaddition; "EnableAdditionalEventTracing"
0x1405d9f94  shl     eax, 0Dh
0x1405d9f97  xor     eax, ecx
0x1405d9f99  and     eax, 2000h
0x1405d9f9e  xor     eax, ecx
0x1405d9fa0  mov     rcx, [rbp+Handle]
0x1405d9fa4  mov     [rbx+50h], eax
0x1405d9fa7  call    IopGetRegistryBoolValue
0x1405d9fac  mov     ecx, [rbx+50h]
0x1405d9faf  lea     rdx, aEnableiospacec; "EnableIoSpaceCorruptionDetection"
0x1405d9fb6  shl     eax, 11h
0x1405d9fb9  xor     eax, ecx
0x1405d9fbb  and     eax, 20000h
0x1405d9fc0  xor     eax, ecx
0x1405d9fc2  mov     rcx, [rbp+Handle]
0x1405d9fc6  mov     [rbx+50h], eax
0x1405d9fc9  call    IopGetRegistryBoolValue
0x1405d9fce  mov     ecx, [rbx+50h]
0x1405d9fd1  lea     rdx, aEnableiospacew; "EnableIoSpaceWriteProtection"
0x1405d9fd8  shl     eax, 12h
0x1405d9fdb  xor     eax, ecx
0x1405d9fdd  and     eax, 40000h
0x1405d9fe2  xor     eax, ecx
0x1405d9fe4  mov     rcx, [rbp+Handle]
0x1405d9fe8  mov     [rbx+50h], eax
0x1405d9feb  call    IopGetRegistryBoolValue
0x1405d9ff0  mov     ecx, [rbx+50h]
0x1405d9ff3  lea     rdx, aSimulateerror; "SimulateError"
0x1405d9ffa  shl     eax, 13h
0x1405d9ffd  xor     eax, ecx
0x1405d9fff  and     eax, 80000h
0x1405da004  xor     eax, ecx
0x1405da006  mov     rcx, [rbp+Handle]
0x1405da00a  mov     [rbx+50h], eax
0x1405da00d  call    IopGetRegistryULongValue
0x1405da012  mov     [rbx+4E0h], eax
0x1405da018  mov     rcx, [rbp+Handle]; Handle
0x1405da01c  test    rcx, rcx
0x1405da01f  jz      short loc_1405DA028
0x1405da021  xor     edx, edx; PreviousMode
0x1405da023  call    ObCloseHandle
0x1405da028  mov     rbx, [rsp+40h+arg_0]
0x1405da02d  add     rsp, 40h
0x1405da031  pop     rbp
0x1405da032  retn
```
