# DeleteDriveLetterRoutine

- ea: `0x14000b3e0`
- end: `0x14000b49a`
- name: `DeleteDriveLetterRoutine`
- size: `186`
- prototype: `__int64 __usercall@<rax>(PCWSTR ValueName@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001b30`
- `0x14000b3e0`
- `0x140019ca0`

## import_xrefs

- `ntoskrnl!RtlDeleteRegistryValue` at `0x14000b456`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14000b456`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b430`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b430`
- `ntoskrnl!RtlCompareMemory` at `0x14000b417`
- `ntoskrnl!RtlCompareMemory` at `0x14000b417`

## string_xrefs

- `0x14000b44d`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall DeleteDriveLetterRoutine(
        PCWSTR ValueName,
        int a2,
        const void *a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  if ( a2 == 3 && a4 == *a5 && RtlCompareMemory(a5 + 1, a3, a4) == a4 )
  {
    RtlInitUnicodeString(&DestinationString, ValueName);
    if ( (unsigned __int8)IsDriveLetter(&DestinationString) )
      RtlDeleteRegistryValue(0, L"\\Registry\\Machine\\System\\MountedDevices", ValueName);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 102);
  }
  return 0;
}

```

## disassembly

```asm
0x14000b3e0  mov     [rsp+arg_0], rbx
0x14000b3e5  push    rdi
0x14000b3e6  sub     rsp, 30h
0x14000b3ea  xorps   xmm0, xmm0
0x14000b3ed  mov     r10, r8
0x14000b3f0  mov     rdi, rcx
0x14000b3f3  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x14000b3f8  cmp     edx, 3
0x14000b3fb  jnz     short loc_14000B464
0x14000b3fd  mov     rcx, [rsp+38h+arg_20]
0x14000b402  movzx   eax, word ptr [rcx]
0x14000b405  cmp     r9d, eax
0x14000b408  jnz     short loc_14000B464
0x14000b40a  add     rcx, 2; Source1
0x14000b40e  mov     r8d, r9d; Length
0x14000b411  mov     rdx, r10; Source2
0x14000b414  mov     ebx, r9d
0x14000b417  call    cs:__imp_RtlCompareMemory
0x14000b41e  nop     dword ptr [rax+rax+00h]
0x14000b423  cmp     rax, rbx
0x14000b426  jnz     short loc_14000B464
0x14000b428  mov     rdx, rdi; SourceString
0x14000b42b  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14000b430  call    cs:__imp_RtlInitUnicodeString
0x14000b437  nop     dword ptr [rax+rax+00h]
0x14000b43c  lea     rcx, [rsp+38h+DestinationString]; String2
0x14000b441  call    IsDriveLetter
0x14000b446  test    al, al
0x14000b448  jz      short loc_14000B48C
0x14000b44a  mov     r8, rdi; ValueName
0x14000b44d  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000b454  xor     ecx, ecx; RelativeTo
0x14000b456  call    cs:__imp_RtlDeleteRegistryValue
0x14000b45d  nop     dword ptr [rax+rax+00h]
0x14000b462  jmp     short loc_14000B48C
0x14000b464  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b46b  lea     rax, WPP_GLOBAL_Control
0x14000b472  cmp     rcx, rax
0x14000b475  jz      short loc_14000B48C
0x14000b477  mov     eax, [rcx+2Ch]
0x14000b47a  test    al, 1
0x14000b47c  jz      short loc_14000B48C
0x14000b47e  mov     rcx, [rcx+18h]
0x14000b482  mov     edx, 66h ; 'f'
0x14000b487  call    WPP_SF_
0x14000b48c  mov     rbx, [rsp+38h+arg_0]
0x14000b491  xor     eax, eax
0x14000b493  add     rsp, 30h
0x14000b497  pop     rdi
0x14000b498  retn
```
