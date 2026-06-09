# SdbpShouldMapSdbToKernelMemory

- ea: `0x140822828`
- end: `0x140822968`
- name: `SdbpShouldMapSdbToKernelMemory`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140821914`

## callees

- `0x1406cd024`
- `0x1406dd5c0`
- `0x140737628`
- `0x140822828`
- `0x1408c2f88`
- `0x140acb824`
- `0x140acba1c`

## string_xrefs

- `0x14082289c`: `AslRegistryGetUInt32 failed to read DisableKernelMemoryMap value from appcompat key [%x]`
- `0x14082292c`: `AslRegistryGetUInt32 failed to read EnableKernelMemoryMap value from appcompat key [%x]`
- `0x140822844`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x1408228e5`: `AslRegistryGetKey failed to open appcompat key [%x]`

## pseudocode

```c
bool SdbpShouldMapSdbToKernelMemory()
{
  char v0; // bl
  int v1; // r8d
  int UInt32; // eax
  int v3; // ebx
  int v4; // eax
  int v5; // ebx
  int v7; // [rsp+40h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp+10h] BYREF

  Handle = 0;
  v7 = 0;
  if ( (unsigned int)Feature_MapSdbFilesToKernelMemory__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( (int)AslRegistryGetKey(
                &Handle,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                0x80000100,
                1) < 0 )
    {
      v0 = 1;
      v1 = 2413;
LABEL_12:
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpShouldMapSdbToKernelMemory",
        v1,
        (unsigned int)"AslRegistryGetKey failed to open appcompat key [%x]");
      return v0;
    }
    UInt32 = AslRegistryGetUInt32(&v7, Handle, L"DisableKernelMemoryMap");
    if ( UInt32 >= 0 )
    {
      v3 = v7;
    }
    else
    {
      if ( !(unsigned int)AslFileNotFound((unsigned int)UInt32) )
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpShouldMapSdbToKernelMemory",
          2418,
          (unsigned int)"AslRegistryGetUInt32 failed to read DisableKernelMemoryMap value from appcompat key [%x]");
      v3 = 0;
    }
    ZwClose(Handle);
    return v3 == 0;
  }
  else
  {
    if ( (int)AslRegistryGetKey(
                &Handle,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                0x80000100,
                1) < 0 )
    {
      v0 = 0;
      v1 = 2434;
      goto LABEL_12;
    }
    v4 = AslRegistryGetUInt32(&v7, Handle, L"EnableKernelMemoryMap");
    if ( v4 >= 0 )
    {
      v5 = v7;
    }
    else
    {
      if ( !(unsigned int)AslFileNotFound((unsigned int)v4) )
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpShouldMapSdbToKernelMemory",
          2439,
          (unsigned int)"AslRegistryGetUInt32 failed to read EnableKernelMemoryMap value from appcompat key [%x]");
      v5 = 0;
    }
    ZwClose(Handle);
    return v5 != 0;
  }
}

```

## disassembly

```asm
0x140822828  push    rbx
0x14082282a  sub     rsp, 30h
0x14082282e  mov     [rsp+38h+Handle], 0
0x140822837  mov     [rsp+38h+arg_0], 0
0x14082283f  call    Feature_MapSdbFilesToKernelMemory__private_IsEnabledDeviceUsageNoInline
0x140822844  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x14082284b  mov     r9d, 1
0x140822851  lea     rcx, [rsp+38h+Handle]
0x140822856  mov     r8d, 80000100h
0x14082285c  test    eax, eax
0x14082285e  jz      short loc_1408228D4
0x140822860  call    AslRegistryGetKey
0x140822865  test    eax, eax
0x140822867  jns     short loc_140822873
0x140822869  mov     bl, 1
0x14082286b  mov     r8d, 96Dh
0x140822871  jmp     short loc_1408228E5
0x140822873  mov     rdx, [rsp+38h+Handle]
0x140822878  lea     r8, aDisablekernelm; "DisableKernelMemoryMap"
0x14082287f  lea     rcx, [rsp+38h+arg_0]
0x140822884  call    AslRegistryGetUInt32
0x140822889  mov     ecx, eax
0x14082288b  test    eax, eax
0x14082288d  jns     short loc_1408228BC
0x14082288f  call    AslFileNotFound
0x140822894  test    eax, eax
0x140822896  jnz     short loc_1408228B8
0x140822898  mov     [rsp+38h+var_18], ecx
0x14082289c  lea     r9, aAslregistryget_6; "AslRegistryGetUInt32 failed to read Dis"...
0x1408228a3  lea     ecx, [rax+1]
0x1408228a6  mov     r8d, 972h
0x1408228ac  lea     rdx, aSdbpshouldmaps; "SdbpShouldMapSdbToKernelMemory"
0x1408228b3  call    AslLogCallPrintf
0x1408228b8  xor     ebx, ebx
0x1408228ba  jmp     short loc_1408228C0
0x1408228bc  mov     ebx, [rsp+38h+arg_0]
0x1408228c0  mov     rcx, [rsp+38h+Handle]; Handle
0x1408228c5  call    ZwClose
0x1408228ca  test    ebx, ebx
0x1408228cc  setz    bl
0x1408228cf  jmp     loc_14082295F
0x1408228d4  call    AslRegistryGetKey
0x1408228d9  test    eax, eax
0x1408228db  jns     short loc_140822903
0x1408228dd  xor     bl, bl
0x1408228df  mov     r8d, 982h
0x1408228e5  lea     r9, aAslregistryget; "AslRegistryGetKey failed to open appcom"...
0x1408228ec  mov     [rsp+38h+var_18], eax
0x1408228f0  lea     rdx, aSdbpshouldmaps; "SdbpShouldMapSdbToKernelMemory"
0x1408228f7  mov     ecx, 1
0x1408228fc  call    AslLogCallPrintf
0x140822901  jmp     short loc_14082295F
0x140822903  mov     rdx, [rsp+38h+Handle]
0x140822908  lea     r8, aEnablekernelme; "EnableKernelMemoryMap"
0x14082290f  lea     rcx, [rsp+38h+arg_0]
0x140822914  call    AslRegistryGetUInt32
0x140822919  mov     ecx, eax
0x14082291b  test    eax, eax
0x14082291d  jns     short loc_14082294C
0x14082291f  call    AslFileNotFound
0x140822924  test    eax, eax
0x140822926  jnz     short loc_140822948
0x140822928  mov     [rsp+38h+var_18], ecx
0x14082292c  lea     r9, aAslregistryget_9; "AslRegistryGetUInt32 failed to read Ena"...
0x140822933  lea     ecx, [rax+1]
0x140822936  mov     r8d, 987h
0x14082293c  lea     rdx, aSdbpshouldmaps; "SdbpShouldMapSdbToKernelMemory"
0x140822943  call    AslLogCallPrintf
0x140822948  xor     ebx, ebx
0x14082294a  jmp     short loc_140822950
0x14082294c  mov     ebx, [rsp+38h+arg_0]
0x140822950  mov     rcx, [rsp+38h+Handle]; Handle
0x140822955  call    ZwClose
0x14082295a  test    ebx, ebx
0x14082295c  setnz   bl
0x14082295f  mov     al, bl
0x140822961  add     rsp, 30h
0x140822965  pop     rbx
0x140822966  retn
```
