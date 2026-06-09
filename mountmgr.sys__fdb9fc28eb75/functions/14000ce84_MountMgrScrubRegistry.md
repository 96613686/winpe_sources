# MountMgrScrubRegistry

- ea: `0x14000ce84`
- end: `0x14000cf16`
- name: `MountMgrScrubRegistry`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400147a0`

## callees

- `0x140003280`
- `0x14000ce84`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000ceee`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000ceee`

## string_xrefs

- `0x14000cee1`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall MountMgrScrubRegistry(__int64 a1)
{
  __int64 result; // rax
  _QWORD v3[14]; // [rsp+30h] [rbp-19h] BYREF
  char v4; // [rsp+B8h] [rbp+6Fh] BYREF

  memset(v3, 0, sizeof(v3));
  while ( 1 )
  {
    v3[3] = &v4;
    v3[0] = ScrubRegistryRoutine;
    v4 = 0;
    result = RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\MountedDevices", v3, a1, 0);
    if ( !v4 )
      break;
    memset(v3, 0, sizeof(v3));
  }
  return result;
}

```

## disassembly

```asm
0x14000ce84  mov     [rsp-8+arg_0], rbx
0x14000ce89  mov     [rsp-8+arg_10], r14
0x14000ce8e  push    rbp
0x14000ce8f  lea     rbp, [rsp-57h]
0x14000ce94  sub     rsp, 0A0h
0x14000ce9b  xor     edx, edx; Val
0x14000ce9d  mov     rbx, rcx
0x14000cea0  lea     rcx, [rbp+57h+var_70]; void *
0x14000cea4  lea     r8d, [rdx+70h]; Size
0x14000cea8  call    memset
0x14000cead  lea     r14, ScrubRegistryRoutine
0x14000ceb4  jmp     short loc_14000CEC5
0x14000ceb6  xor     edx, edx; Val
0x14000ceb8  lea     rcx, [rbp+57h+var_70]; void *
0x14000cebc  lea     r8d, [rdx+70h]; Size
0x14000cec0  call    memset
0x14000cec5  lea     rax, [rbp+57h+arg_8]
0x14000cec9  mov     [rsp+0A0h+var_80], 0
0x14000ced2  mov     r9, rbx
0x14000ced5  mov     [rbp+57h+var_58], rax
0x14000ced9  lea     r8, [rbp+57h+var_70]
0x14000cedd  mov     [rbp+57h+var_70], r14
0x14000cee1  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000cee8  mov     [rbp+57h+arg_8], 0
0x14000ceec  xor     ecx, ecx
0x14000ceee  call    cs:__imp_RtlQueryRegistryValuesEx
0x14000cef5  nop     dword ptr [rax+rax+00h]
0x14000cefa  cmp     [rbp+57h+arg_8], 0
0x14000cefe  jnz     short loc_14000CEB6
0x14000cf00  lea     r11, [rsp+0A0h+var_s0]
0x14000cf08  mov     rbx, [r11+10h]
0x14000cf0c  mov     r14, [r11+20h]
0x14000cf10  mov     rsp, r11
0x14000cf13  pop     rbp
0x14000cf14  retn
```
