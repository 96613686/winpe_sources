# HasNoDriveLetterEntry

- ea: `0x14000a640`
- end: `0x14000a6b7`
- name: `HasNoDriveLetterEntry`
- size: `119`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000fcc0`
- `0x140014fc0`
- `0x140019af0`

## callees

- `0x140003280`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000a699`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000a699`

## string_xrefs

- `0x14000a690`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall HasNoDriveLetterEntry(__int64 a1)
{
  _QWORD v3[15]; // [rsp+30h] [rbp-78h] BYREF
  unsigned __int8 v4; // [rsp+B8h] [rbp+10h] BYREF

  memset(v3, 0, 0x70u);
  v4 = 0;
  v3[0] = &CheckForNoDriveLetterEntry;
  v3[3] = &v4;
  RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\MountedDevices", v3, a1, 0);
  return v4;
}

```

## disassembly

```asm
0x14000a640  push    rbx
0x14000a642  sub     rsp, 0A0h
0x14000a649  mov     rbx, rcx
0x14000a64c  xor     edx, edx; Val
0x14000a64e  lea     rcx, [rsp+0A8h+var_78]; void *
0x14000a653  mov     r8d, 70h ; 'p'; Size
0x14000a659  call    memset
0x14000a65e  lea     rax, CheckForNoDriveLetterEntry
0x14000a665  mov     [rsp+0A8h+arg_8], 0
0x14000a66d  mov     [rsp+0A8h+var_78], rax
0x14000a672  lea     r8, [rsp+0A8h+var_78]
0x14000a677  lea     rax, [rsp+0A8h+arg_8]
0x14000a67f  mov     [rsp+0A8h+var_88], 0
0x14000a688  mov     r9, rbx
0x14000a68b  mov     [rsp+0A8h+var_60], rax
0x14000a690  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000a697  xor     ecx, ecx
0x14000a699  call    cs:__imp_RtlQueryRegistryValuesEx
0x14000a6a0  nop     dword ptr [rax+rax+00h]
0x14000a6a5  movzx   eax, [rsp+0A8h+arg_8]
0x14000a6ad  add     rsp, 0A0h
0x14000a6b4  pop     rbx
0x14000a6b5  retn
```
