# SdbpShouldMapSdbToKernelMemory

- ea: `0x1408208b8`
- end: `0x1408209f8`
- name: `SdbpShouldMapSdbToKernelMemory`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14081f9a4`

## callees

- `0x1406ca3c4`
- `0x1406daa70`
- `0x140732e68`
- `0x1408208b8`
- `0x14097d158`
- `0x140ac65d4`
- `0x140ac67cc`

## string_xrefs

- `0x1408209bc`: `AslRegistryGetUInt32 failed to read EnableKernelMemoryMap value from appcompat key [%x]`
- `0x14082092c`: `AslRegistryGetUInt32 failed to read DisableKernelMemoryMap value from appcompat key [%x]`
- `0x140820975`: `AslRegistryGetKey failed to open appcompat key [%x]`
- `0x1408208d4`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`

## pseudocode

```c
bool SdbpShouldMapSdbToKernelMemory()
{
  int Key; // eax
  char v1; // bl
  int v2; // r8d
  int UInt32; // eax
  int v4; // ecx
  int v5; // ebx
  int v6; // eax
  int v7; // ecx
  int v8; // ebx
  int v10; // [rsp+20h] [rbp-18h]
  int v11; // [rsp+20h] [rbp-18h]
  int v12; // [rsp+20h] [rbp-18h]
  int v13; // [rsp+40h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp+10h] BYREF

  Handle = 0;
  v13 = 0;
  if ( (unsigned int)Feature_MapSdbFilesToKernelMemory__private_IsEnabledDeviceUsageNoInline() )
  {
    Key = AslRegistryGetKey(&Handle, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags", 0x80000100, 1);
    if ( Key < 0 )
    {
      v1 = 1;
      v2 = 2415;
LABEL_12:
      v11 = Key;
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpShouldMapSdbToKernelMemory",
        v2,
        (unsigned int)"AslRegistryGetKey failed to open appcompat key [%x]",
        v11);
      return v1;
    }
    UInt32 = AslRegistryGetUInt32(&v13, Handle, L"DisableKernelMemoryMap");
    if ( UInt32 >= 0 )
    {
      v5 = v13;
    }
    else
    {
      if ( !(unsigned int)AslFileNotFound((unsigned int)UInt32) )
      {
        v10 = v4;
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpShouldMapSdbToKernelMemory",
          2420,
          (unsigned int)"AslRegistryGetUInt32 failed to read DisableKernelMemoryMap value from appcompat key [%x]",
          v10);
      }
      v5 = 0;
    }
    ZwClose(Handle);
    return v5 == 0;
  }
  else
  {
    Key = AslRegistryGetKey(&Handle, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags", 0x80000100, 1);
    if ( Key < 0 )
    {
      v1 = 0;
      v2 = 2436;
      goto LABEL_12;
    }
    v6 = AslRegistryGetUInt32(&v13, Handle, L"EnableKernelMemoryMap");
    if ( v6 >= 0 )
    {
      v8 = v13;
    }
    else
    {
      if ( !(unsigned int)AslFileNotFound((unsigned int)v6) )
      {
        v12 = v7;
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpShouldMapSdbToKernelMemory",
          2441,
          (unsigned int)"AslRegistryGetUInt32 failed to read EnableKernelMemoryMap value from appcompat key [%x]",
          v12);
      }
      v8 = 0;
    }
    ZwClose(Handle);
    return v8 != 0;
  }
}

```

## disassembly

```asm
0x1408208b8  push    rbx
0x1408208ba  sub     rsp, 30h
0x1408208be  mov     [rsp+38h+Handle], 0
0x1408208c7  mov     [rsp+38h+arg_0], 0
0x1408208cf  call    Feature_MapSdbFilesToKernelMemory__private_IsEnabledDeviceUsageNoInline
0x1408208d4  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x1408208db  mov     r9d, 1
0x1408208e1  lea     rcx, [rsp+38h+Handle]
0x1408208e6  mov     r8d, 80000100h
0x1408208ec  test    eax, eax
0x1408208ee  jz      short loc_140820964
0x1408208f0  call    AslRegistryGetKey
0x1408208f5  test    eax, eax
0x1408208f7  jns     short loc_140820903
0x1408208f9  mov     bl, 1
0x1408208fb  mov     r8d, 96Fh
0x140820901  jmp     short loc_140820975
0x140820903  mov     rdx, [rsp+38h+Handle]
0x140820908  lea     r8, aDisablekernelm; "DisableKernelMemoryMap"
0x14082090f  lea     rcx, [rsp+38h+arg_0]
0x140820914  call    AslRegistryGetUInt32
0x140820919  mov     ecx, eax
0x14082091b  test    eax, eax
0x14082091d  jns     short loc_14082094C
0x14082091f  call    AslFileNotFound
0x140820924  test    eax, eax
0x140820926  jnz     short loc_140820948
0x140820928  mov     [rsp+38h+var_18], ecx
0x14082092c  lea     r9, aAslregistryget_6; "AslRegistryGetUInt32 failed to read Dis"...
0x140820933  lea     ecx, [rax+1]
0x140820936  mov     r8d, 974h
0x14082093c  lea     rdx, aSdbpshouldmaps; "SdbpShouldMapSdbToKernelMemory"
0x140820943  call    AslLogCallPrintf
0x140820948  xor     ebx, ebx
0x14082094a  jmp     short loc_140820950
0x14082094c  mov     ebx, [rsp+38h+arg_0]
0x140820950  mov     rcx, [rsp+38h+Handle]; Handle
0x140820955  call    ZwClose
0x14082095a  test    ebx, ebx
0x14082095c  setz    bl
0x14082095f  jmp     loc_1408209EF
0x140820964  call    AslRegistryGetKey
0x140820969  test    eax, eax
0x14082096b  jns     short loc_140820993
0x14082096d  xor     bl, bl
0x14082096f  mov     r8d, 984h
0x140820975  lea     r9, aAslregistryget; "AslRegistryGetKey failed to open appcom"...
0x14082097c  mov     [rsp+38h+var_18], eax
0x140820980  lea     rdx, aSdbpshouldmaps; "SdbpShouldMapSdbToKernelMemory"
0x140820987  mov     ecx, 1
0x14082098c  call    AslLogCallPrintf
0x140820991  jmp     short loc_1408209EF
0x140820993  mov     rdx, [rsp+38h+Handle]
0x140820998  lea     r8, aEnablekernelme; "EnableKernelMemoryMap"
0x14082099f  lea     rcx, [rsp+38h+arg_0]
0x1408209a4  call    AslRegistryGetUInt32
0x1408209a9  mov     ecx, eax
0x1408209ab  test    eax, eax
0x1408209ad  jns     short loc_1408209DC
0x1408209af  call    AslFileNotFound
0x1408209b4  test    eax, eax
0x1408209b6  jnz     short loc_1408209D8
0x1408209b8  mov     [rsp+38h+var_18], ecx
0x1408209bc  lea     r9, aAslregistryget_9; "AslRegistryGetUInt32 failed to read Ena"...
0x1408209c3  lea     ecx, [rax+1]
0x1408209c6  mov     r8d, 989h
0x1408209cc  lea     rdx, aSdbpshouldmaps; "SdbpShouldMapSdbToKernelMemory"
0x1408209d3  call    AslLogCallPrintf
0x1408209d8  xor     ebx, ebx
0x1408209da  jmp     short loc_1408209E0
0x1408209dc  mov     ebx, [rsp+38h+arg_0]
0x1408209e0  mov     rcx, [rsp+38h+Handle]; Handle
0x1408209e5  call    ZwClose
0x1408209ea  test    ebx, ebx
0x1408209ec  setnz   bl
0x1408209ef  mov     al, bl
0x1408209f1  add     rsp, 30h
0x1408209f5  pop     rbx
0x1408209f6  retn
```
