# EtwpUpdateFileInfoDriverState

- ea: `0x140a8703c`
- end: `0x140a870f8`
- name: `EtwpUpdateFileInfoDriverState`
- size: `188`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140a86ce4`
- `0x140ad1344`
- `0x140c822bc`

## callees

- `0x1403f2d50`
- `0x1404a16a0`
- `0x140510304`
- `0x1406dca30`
- `0x1406de3b0`
- `0x1407d88f4`
- `0x140a8703c`
- `0x140aa249c`

## string_xrefs

- `0x140a87094`: `\Registry\Machine\System\CurrentControlSet\Services\FileInfo`
- `0x140a870ce`: `\Registry\Machine\System\CurrentControlSet\Services\FileInfo`
- `0x140b70ff6`: `\Registry\Machine\System\CurrentControlSet\Services\FileInfo`

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
    if ( !(unsigned __int8)PerfIsGroupOnInGroupMaskNoFence(100663808) && dword_140E4E490 )
    {
      WmiTraceRundownNotify(*v5, a5);
      EtwpUpdateFileInfoDriverRegistration(0);
      RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\FileInfo");
      ZwUnloadDriver(&DestinationString);
      dword_140E4E490 = 0;
    }
    return 0;
  }
  if ( !(unsigned __int8)PerfIsGroupOnInGroupMaskNoFence(100663808) )
    return 0;
  v10 = 0;
  if ( !(unsigned int)WmiQueryTraceProviderCount(v9, v8) )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\FileInfo");
    v11 = ZwLoadDriver(&DestinationString);
    if ( (int)(v11 + 0x80000000) >= 0 && v11 != -1073741554 )
      return (unsigned int)-1073741204;
    dword_140E4E490 = 1;
    v10 = 1;
  }
  updated = EtwpUpdateFileInfoDriverRegistration(1);
  if ( updated >= 0 )
    return 0;
  if ( v10 )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\FileInfo");
    ZwUnloadDriver(&DestinationString);
    dword_140E4E490 = 0;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140a8703c  mov     [rsp+arg_0], rbx
0x140a87041  push    rdi
0x140a87042  sub     rsp, 30h
0x140a87046  xorps   xmm0, xmm0
0x140a87049  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140a8704e  test    r8d, r8d
0x140a87051  jnz     short loc_140A8707D
0x140a87053  mov     rdx, rcx
0x140a87056  mov     ecx, 6000200h
0x140a8705b  call    PerfIsGroupOnInGroupMaskNoFence
0x140a87060  test    al, al
0x140a87062  jnz     short loc_140A8706D
0x140a87064  cmp     cs:dword_140E4E490, 0
0x140a8706b  jnz     short loc_140A870BB
0x140a8706d  xor     ebx, ebx
0x140a8706f  mov     eax, ebx
0x140a87071  mov     rbx, [rsp+38h+arg_0]
0x140a87076  add     rsp, 30h
0x140a8707a  pop     rdi
0x140a8707b  retn
0x140a8707d  mov     ecx, 6000200h
0x140a87082  call    PerfIsGroupOnInGroupMaskNoFence
0x140a87087  test    al, al
0x140a87089  jz      short loc_140A8706D
0x140a8708b  jmp     loc_140B70FE8
0x140a87090  test    edi, edi
0x140a87092  jz      short loc_140A8706F
0x140a87094  lea     rdx, aRegistryMachin_105; "\\Registry\\Machine\\System\\CurrentCon"...
0x140a8709b  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140a870a0  call    RtlInitUnicodeString
0x140a870a5  lea     rcx, [rsp+38h+DestinationString]; DriverServiceName
0x140a870aa  call    ZwUnloadDriver
0x140a870af  mov     cs:dword_140E4E490, 0
0x140a870b9  jmp     short loc_140A8706F
0x140a870bb  mov     edx, [rsp+38h+arg_20]
0x140a870bf  mov     rcx, [r9]
0x140a870c2  call    WmiTraceRundownNotify
0x140a870c7  xor     ecx, ecx
0x140a870c9  call    EtwpUpdateFileInfoDriverRegistration
0x140a870ce  lea     rdx, aRegistryMachin_105; "\\Registry\\Machine\\System\\CurrentCon"...
0x140a870d5  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140a870da  call    RtlInitUnicodeString
0x140a870df  lea     rcx, [rsp+38h+DestinationString]; DriverServiceName
0x140a870e4  call    ZwUnloadDriver
0x140a870e9  mov     cs:dword_140E4E490, 0
0x140a870f3  jmp     loc_140A8706D
0x140b70fe8  xor     edi, edi
0x140b70fea  call    WmiQueryTraceProviderCount
0x140b70fef  lea     ebx, [rdi+1]
0x140b70ff2  test    eax, eax
0x140b70ff4  jnz     short loc_140B71036
0x140b70ff6  lea     rdx, aRegistryMachin_105; "\\Registry\\Machine\\System\\CurrentCon"...
0x140b70ffd  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140b71002  call    RtlInitUnicodeString
0x140b71007  lea     rcx, [rsp+38h+DestinationString]; DriverServiceName
0x140b7100c  call    ZwLoadDriver
0x140b71011  mov     edx, 80000000h
0x140b71016  lea     ecx, [rax+rdx]
0x140b71019  test    edx, ecx
0x140b7101b  jnz     short loc_140B7102E
0x140b7101d  cmp     eax, 0C000010Eh
0x140b71022  jz      short loc_140B7102E
0x140b71024  mov     ebx, 0C000026Ch
0x140b71029  jmp     loc_140A8706F
0x140b7102e  mov     cs:dword_140E4E490, ebx
0x140b71034  mov     edi, ebx
0x140b71036  mov     ecx, ebx
0x140b71038  call    EtwpUpdateFileInfoDriverRegistration
0x140b7103d  mov     ebx, eax
0x140b7103f  test    eax, eax
0x140b71041  jns     loc_140A8706D
0x140b71047  jmp     loc_140A87090
```
