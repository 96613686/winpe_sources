# DeleteNoDriveLetterEntry

- ea: `0x14000b588`
- end: `0x14000b5e0`
- name: `DeleteNoDriveLetterEntry`
- size: `88`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000a050`
- `0x14000be4c`
- `0x140018560`

## callees

- `0x140003280`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000b5ca`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000b5ca`

## string_xrefs

- `0x14000b5c3`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall DeleteNoDriveLetterEntry(__int64 a1)
{
  _QWORD v3[15]; // [rsp+30h] [rbp-78h] BYREF

  memset(&v3[1], 0, 0x68u);
  v3[0] = DeleteNoDriveLetterEntryRoutine;
  return RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\MountedDevices", v3, a1, 0);
}

```

## disassembly

```asm
0x14000b588  push    rbx
0x14000b58a  sub     rsp, 0A0h
0x14000b591  xor     edx, edx; Val
0x14000b593  mov     rbx, rcx
0x14000b596  lea     rcx, [rsp+0A8h+var_70]; void *
0x14000b59b  lea     r8d, [rdx+68h]; Size
0x14000b59f  call    memset
0x14000b5a4  lea     rax, DeleteNoDriveLetterEntryRoutine
0x14000b5ab  mov     [rsp+0A8h+var_88], 0
0x14000b5b4  mov     r9, rbx
0x14000b5b7  mov     [rsp+0A8h+var_78], rax
0x14000b5bc  lea     r8, [rsp+0A8h+var_78]
0x14000b5c1  xor     ecx, ecx
0x14000b5c3  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000b5ca  call    cs:__imp_RtlQueryRegistryValuesEx
0x14000b5d1  nop     dword ptr [rax+rax+00h]
0x14000b5d6  add     rsp, 0A0h
0x14000b5dd  pop     rbx
0x14000b5de  retn
```
