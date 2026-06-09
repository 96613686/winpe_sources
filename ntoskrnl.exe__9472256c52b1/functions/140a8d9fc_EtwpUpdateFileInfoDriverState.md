# EtwpUpdateFileInfoDriverState

- ea: `0x140a8d9fc`
- end: `0x140a8dab8`
- name: `EtwpUpdateFileInfoDriverState`
- size: `188`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140a8d6a4`
- `0x140ad63d4`
- `0x140c8511c`

## callees

- `0x140403380`
- `0x1404af6b0`
- `0x1405164e4`
- `0x1406df580`
- `0x1406e0f00`
- `0x1407db5b4`
- `0x1409f2760`
- `0x140a8d9fc`

## string_xrefs

- `0x140a8da54`: `\Registry\Machine\System\CurrentControlSet\Services\FileInfo`
- `0x140a8da8e`: `\Registry\Machine\System\CurrentControlSet\Services\FileInfo`
- `0x140b73288`: `\Registry\Machine\System\CurrentControlSet\Services\FileInfo`

## pseudocode

```c
__int64 __fastcall EtwpUpdateFileInfoDriverState(__int64 a1, __int64 a2, int a3, __int64 a4, unsigned int a5)
{
  _QWORD *v5; // r9
  int updated; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // edi
  NTSTATUS v11; // eax
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  if ( !a3 )
  {
    if ( !(unsigned __int8)PerfIsGroupOnInGroupMaskNoFence(100663808, a1) && dword_140E4E464 )
    {
      WmiTraceRundownNotify(*v5, a5);
      EtwpUpdateFileInfoDriverRegistration(0);
      RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\FileInfo");
      ZwUnloadDriver(&DestinationString);
      dword_140E4E464 = 0;
    }
    return 0;
  }
  if ( !(unsigned __int8)PerfIsGroupOnInGroupMaskNoFence(100663808, a2) )
    return 0;
  v10 = 0;
  if ( !(unsigned int)WmiQueryTraceProviderCount(v9, v8) )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\FileInfo");
    v11 = ZwLoadDriver(&DestinationString);
    if ( (int)(v11 + 0x80000000) >= 0 && v11 != -1073741554 )
      return (unsigned int)-1073741204;
    dword_140E4E464 = 1;
    v10 = 1;
  }
  updated = EtwpUpdateFileInfoDriverRegistration(1);
  if ( updated >= 0 )
    return 0;
  if ( v10 )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\FileInfo");
    ZwUnloadDriver(&DestinationString);
    dword_140E4E464 = 0;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140a8d9fc  mov     [rsp+arg_0], rbx
0x140a8da01  push    rdi
0x140a8da02  sub     rsp, 30h
0x140a8da06  xorps   xmm0, xmm0
0x140a8da09  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140a8da0e  test    r8d, r8d
0x140a8da11  jnz     short loc_140A8DA3D
0x140a8da13  mov     rdx, rcx
0x140a8da16  mov     ecx, 6000200h
0x140a8da1b  call    PerfIsGroupOnInGroupMaskNoFence
0x140a8da20  test    al, al
0x140a8da22  jnz     short loc_140A8DA2D
0x140a8da24  cmp     cs:dword_140E4E464, 0
0x140a8da2b  jnz     short loc_140A8DA7B
0x140a8da2d  xor     ebx, ebx
0x140a8da2f  mov     eax, ebx
0x140a8da31  mov     rbx, [rsp+38h+arg_0]
0x140a8da36  add     rsp, 30h
0x140a8da3a  pop     rdi
0x140a8da3b  retn
0x140a8da3d  mov     ecx, 6000200h
0x140a8da42  call    PerfIsGroupOnInGroupMaskNoFence
0x140a8da47  test    al, al
0x140a8da49  jz      short loc_140A8DA2D
0x140a8da4b  jmp     loc_140B7327A
0x140a8da50  test    edi, edi
0x140a8da52  jz      short loc_140A8DA2F
0x140a8da54  lea     rdx, aRegistryMachin_105; "\\Registry\\Machine\\System\\CurrentCon"...
0x140a8da5b  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140a8da60  call    RtlInitUnicodeString
0x140a8da65  lea     rcx, [rsp+38h+DestinationString]; DriverServiceName
0x140a8da6a  call    ZwUnloadDriver
0x140a8da6f  mov     cs:dword_140E4E464, 0
0x140a8da79  jmp     short loc_140A8DA2F
0x140a8da7b  mov     edx, [rsp+38h+arg_20]
0x140a8da7f  mov     rcx, [r9]
0x140a8da82  call    WmiTraceRundownNotify
0x140a8da87  xor     ecx, ecx
0x140a8da89  call    EtwpUpdateFileInfoDriverRegistration
0x140a8da8e  lea     rdx, aRegistryMachin_105; "\\Registry\\Machine\\System\\CurrentCon"...
0x140a8da95  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140a8da9a  call    RtlInitUnicodeString
0x140a8da9f  lea     rcx, [rsp+38h+DestinationString]; DriverServiceName
0x140a8daa4  call    ZwUnloadDriver
0x140a8daa9  mov     cs:dword_140E4E464, 0
0x140a8dab3  jmp     loc_140A8DA2D
0x140b7327a  xor     edi, edi
0x140b7327c  call    WmiQueryTraceProviderCount
0x140b73281  lea     ebx, [rdi+1]
0x140b73284  test    eax, eax
0x140b73286  jnz     short loc_140B732C8
0x140b73288  lea     rdx, aRegistryMachin_105; "\\Registry\\Machine\\System\\CurrentCon"...
0x140b7328f  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140b73294  call    RtlInitUnicodeString
0x140b73299  lea     rcx, [rsp+38h+DestinationString]; DriverServiceName
0x140b7329e  call    ZwLoadDriver
0x140b732a3  mov     edx, 80000000h
0x140b732a8  lea     ecx, [rax+rdx]
0x140b732ab  test    edx, ecx
0x140b732ad  jnz     short loc_140B732C0
0x140b732af  cmp     eax, 0C000010Eh
0x140b732b4  jz      short loc_140B732C0
0x140b732b6  mov     ebx, 0C000026Ch
0x140b732bb  jmp     loc_140A8DA2F
0x140b732c0  mov     cs:dword_140E4E464, ebx
0x140b732c6  mov     edi, ebx
0x140b732c8  mov     ecx, ebx
0x140b732ca  call    EtwpUpdateFileInfoDriverRegistration
0x140b732cf  mov     ebx, eax
0x140b732d1  test    eax, eax
0x140b732d3  jns     loc_140A8DA2D
0x140b732d9  jmp     loc_140A8DA50
```
