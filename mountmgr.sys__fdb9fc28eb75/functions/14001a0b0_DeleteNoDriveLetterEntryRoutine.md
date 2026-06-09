# DeleteNoDriveLetterEntryRoutine

- ea: `0x14001a0b0`
- end: `0x14001a17f`
- name: `DeleteNoDriveLetterEntryRoutine`
- size: `207`
- prototype: `__int64 __usercall@<rax>(PCWSTR ValueName@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140002260`
- `0x14001a0b0`

## import_xrefs

- `ntoskrnl!RtlDeleteRegistryValue` at `0x14001a112`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14001a112`
- `ntoskrnl!RtlCompareMemory` at `0x14001a0f0`
- `ntoskrnl!RtlCompareMemory` at `0x14001a0f0`

## string_xrefs

- `0x14001a109`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall DeleteNoDriveLetterEntryRoutine(
        PCWSTR ValueName,
        int a2,
        const void *a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  char v5; // bp
  const char *v8; // rax

  v5 = a4;
  if ( a2 == 3 && *ValueName == 35 && a4 == *a5 && RtlCompareMemory(a5 + 1, a3, a4) == a4 )
  {
    RtlDeleteRegistryValue(0, L"\\Registry\\Machine\\System\\MountedDevices", ValueName);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v8 = "TRUE";
    if ( a2 != 3 )
      v8 = "FALSE";
    WPP_SF_LSsd(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned int)"FALSE",
      (_DWORD)a3,
      a4,
      (__int64)ValueName,
      (__int64)v8,
      v5);
  }
  return 0;
}

```

## disassembly

```asm
0x14001a0b0  mov     [rsp+arg_8], rbp
0x14001a0b5  mov     [rsp+arg_10], rsi
0x14001a0ba  push    rdi
0x14001a0bb  sub     rsp, 40h
0x14001a0bf  mov     ebp, r9d
0x14001a0c2  mov     r10, r8
0x14001a0c5  mov     edi, edx
0x14001a0c7  mov     rsi, rcx
0x14001a0ca  cmp     edx, 3
0x14001a0cd  jnz     short loc_14001A120
0x14001a0cf  cmp     word ptr [rcx], 23h ; '#'
0x14001a0d3  jnz     short loc_14001A120
0x14001a0d5  mov     rcx, [rsp+48h+arg_20]
0x14001a0da  movzx   eax, word ptr [rcx]
0x14001a0dd  cmp     ebp, eax
0x14001a0df  jnz     short loc_14001A120
0x14001a0e1  add     rcx, 2; Source1
0x14001a0e5  mov     [rsp+48h+arg_0], rbx
0x14001a0ea  mov     r8d, ebp; Length
0x14001a0ed  mov     rdx, r10; Source2
0x14001a0f0  call    cs:__imp_RtlCompareMemory
0x14001a0f7  nop     dword ptr [rax+rax+00h]
0x14001a0fc  mov     rbx, [rsp+48h+arg_0]
0x14001a101  cmp     rax, rbp
0x14001a104  jnz     short loc_14001A120
0x14001a106  mov     r8, rsi; ValueName
0x14001a109  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14001a110  xor     ecx, ecx; RelativeTo
0x14001a112  call    cs:__imp_RtlDeleteRegistryValue
0x14001a119  nop     dword ptr [rax+rax+00h]
0x14001a11e  jmp     short loc_14001A16C
0x14001a120  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a127  lea     rax, WPP_GLOBAL_Control
0x14001a12e  cmp     rcx, rax
0x14001a131  jz      short loc_14001A16C
0x14001a133  mov     eax, [rcx+2Ch]
0x14001a136  test    al, 1
0x14001a138  jz      short loc_14001A16C
0x14001a13a  cmp     byte ptr [rcx+29h], 1
0x14001a13e  jb      short loc_14001A16C
0x14001a140  mov     rcx, [rcx+18h]
0x14001a144  lea     rdx, aFalse; "FALSE"
0x14001a14b  cmp     edi, 3
0x14001a14e  mov     [rsp+48h+var_18], ebp
0x14001a152  lea     rax, aTrue; "TRUE"
0x14001a159  cmovnz  rax, rdx
0x14001a15d  mov     [rsp+48h+var_20], rax
0x14001a162  mov     [rsp+48h+var_28], rsi
0x14001a167  call    WPP_SF_LSsd
0x14001a16c  xor     eax, eax
0x14001a16e  mov     rbp, [rsp+48h+arg_8]
0x14001a173  mov     rsi, [rsp+48h+arg_10]
0x14001a178  add     rsp, 40h
0x14001a17c  pop     rdi
0x14001a17d  retn
```
