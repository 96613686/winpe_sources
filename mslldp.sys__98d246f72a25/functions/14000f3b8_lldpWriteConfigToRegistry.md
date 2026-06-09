# lldpWriteConfigToRegistry

- ea: `0x14000f3b8`
- end: `0x14000f514`
- name: `lldpWriteConfigToRegistry`
- size: `348`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140010150`
- `0x1400114d0`

## callees

- `0x140004a60`
- `0x140004b00`
- `0x140006630`
- `0x14000f3b8`
- `0x140012500`

## import_xrefs

- `ntoskrnl!RtlCreateRegistryKey` at `0x14000f454`
- `ntoskrnl!RtlCreateRegistryKey` at `0x14000f454`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14000f4c8`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14000f4c8`

## pseudocode

```c
__int64 __fastcall lldpWriteConfigToRegistry(__int64 a1, int a2, int a3)
{
  __int64 v3; // rdi
  unsigned int RegistryKey; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  int ValueData; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v9; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR *v10; // [rsp+40h] [rbp-C0h]
  WCHAR Path[104]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = a2;
  v10 = Path;
  ValueData = a3;
  v9 = 13369344;
  if ( (unsigned __int8)lldpGetRegistryKeyName(a1, &v9) )
  {
    v10[(unsigned __int64)(unsigned __int16)v9 >> 1] = 0;
    RegistryKey = RtlCreateRegistryKey(1u, Path);
    if ( RegistryKey )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return RegistryKey;
      v7 = 22;
    }
    else
    {
      RegistryKey = RtlWriteRegistryValue(1u, Path, (&lldpParameterRules)[3 * v3], 4u, &ValueData, 4u);
      if ( !RegistryKey )
        return 0;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return RegistryKey;
      v7 = 23;
    }
    WPP_SF_d(v6->AttachedDevice, v7, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids, RegistryKey);
    return RegistryKey;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids);
  return 3221225473LL;
}

```

## disassembly

```asm
0x14000f3b8  push    rbp
0x14000f3ba  push    rbx
0x14000f3bb  push    rdi
0x14000f3bc  lea     rbp, [rsp-30h]
0x14000f3c1  sub     rsp, 130h
0x14000f3c8  mov     rax, cs:__security_cookie
0x14000f3cf  xor     rax, rsp
0x14000f3d2  mov     [rbp+40h+var_20], rax
0x14000f3d6  movsxd  rdi, edx
0x14000f3d9  lea     rax, [rsp+140h+Path]
0x14000f3de  lea     rdx, [rsp+140h+var_108]
0x14000f3e3  mov     [rsp+140h+var_100], rax
0x14000f3e8  mov     [rsp+140h+var_110], r8d
0x14000f3ed  mov     [rsp+140h+var_108], 0CC0000h
0x14000f3f6  call    lldpGetRegistryKeyName
0x14000f3fb  test    al, al
0x14000f3fd  jnz     short loc_14000F437
0x14000f3ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f406  lea     rax, WPP_GLOBAL_Control
0x14000f40d  cmp     rcx, rax
0x14000f410  jz      short loc_14000F42D
0x14000f412  cmp     byte ptr [rcx+29h], 2
0x14000f416  jb      short loc_14000F42D
0x14000f418  mov     rcx, [rcx+18h]
0x14000f41c  lea     r8, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids
0x14000f423  mov     edx, 15h
0x14000f428  call    WPP_SF_
0x14000f42d  mov     eax, 0C0000001h
0x14000f432  jmp     loc_14000F4FC
0x14000f437  mov     rax, [rsp+140h+var_100]
0x14000f43c  xor     ecx, ecx
0x14000f43e  movzx   edx, word ptr [rsp+140h+var_108]
0x14000f443  shr     rdx, 1
0x14000f446  mov     [rax+rdx*2], cx
0x14000f44a  lea     rdx, [rsp+140h+Path]; Path
0x14000f44f  mov     ecx, 1; RelativeTo
0x14000f454  call    cs:__imp_RtlCreateRegistryKey
0x14000f45b  nop     dword ptr [rax+rax+00h]
0x14000f460  mov     ebx, eax
0x14000f462  test    eax, eax
0x14000f464  jz      short loc_14000F49B
0x14000f466  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f46d  lea     rax, WPP_GLOBAL_Control
0x14000f474  cmp     rcx, rax
0x14000f477  jz      short loc_14000F497
0x14000f479  cmp     byte ptr [rcx+29h], 2
0x14000f47d  jb      short loc_14000F497
0x14000f47f  mov     edx, 16h
0x14000f484  mov     rcx, [rcx+18h]
0x14000f488  lea     r8, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids
0x14000f48f  mov     r9d, ebx
0x14000f492  call    WPP_SF_d
0x14000f497  mov     eax, ebx
0x14000f499  jmp     short loc_14000F4FC
0x14000f49b  mov     r9d, 4; ValueType
0x14000f4a1  lea     rdx, lldpParameterRules
0x14000f4a8  lea     rax, [rsp+140h+var_110]
0x14000f4ad  mov     [rsp+140h+ValueLength], r9d; ValueLength
0x14000f4b2  lea     r8, [rdi+rdi*2]
0x14000f4b6  mov     [rsp+140h+ValueData], rax; ValueData
0x14000f4bb  mov     r8, [rdx+r8*8]; ValueName
0x14000f4bf  lea     rdx, [rsp+140h+Path]; Path
0x14000f4c4  lea     ecx, [r9-3]; RelativeTo
0x14000f4c8  call    cs:__imp_RtlWriteRegistryValue
0x14000f4cf  nop     dword ptr [rax+rax+00h]
0x14000f4d4  mov     ebx, eax
0x14000f4d6  test    eax, eax
0x14000f4d8  jz      short loc_14000F4FA
0x14000f4da  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f4e1  lea     rax, WPP_GLOBAL_Control
0x14000f4e8  cmp     rcx, rax
0x14000f4eb  jz      short loc_14000F497
0x14000f4ed  cmp     byte ptr [rcx+29h], 2
0x14000f4f1  jb      short loc_14000F497
0x14000f4f3  mov     edx, 17h
0x14000f4f8  jmp     short loc_14000F484
0x14000f4fa  xor     eax, eax
0x14000f4fc  mov     rcx, [rbp+40h+var_20]
0x14000f500  xor     rcx, rsp; StackCookie
0x14000f503  call    __security_check_cookie
0x14000f508  add     rsp, 130h
0x14000f50f  pop     rdi
0x14000f510  pop     rbx
0x14000f511  pop     rbp
0x14000f512  retn
```
