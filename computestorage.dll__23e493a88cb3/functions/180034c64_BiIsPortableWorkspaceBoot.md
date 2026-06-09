# BiIsPortableWorkspaceBoot

- ea: `0x180034c64`
- end: `0x180034d10`
- name: `BiIsPortableWorkspaceBoot`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180036c88`

## callees

- `0x18003223c`
- `0x180033260`
- `0x180033914`
- `0x180034c64`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180034cfb`
- `ntdll!RtlFreeHeap` at `0x180034cfb`

## string_xrefs

- `0x180034cbd`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control`
- `0x180034c86`: `\Registry\Machine\System\CurrentControlSet\Control\MiniNT`

## pseudocode

```c
bool BiIsPortableWorkspaceBoot()
{
  bool v0; // bl
  int v2; // [rsp+40h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp+10h] BYREF
  PVOID P; // [rsp+50h] [rbp+18h] BYREF

  P = 0;
  Handle = 0;
  v2 = 0;
  v0 = 0;
  if ( (int)BiOpenKey(0, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MiniNT", 131097, &Handle) < 0 )
  {
    if ( (int)BiGetRegistryValue(
                0,
                L"PortableOperatingSystem",
                L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control",
                4,
                &P,
                &v2) >= 0 )
    {
      v0 = *(_DWORD *)P != 0;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    }
  }
  else
  {
    BiCloseKey((unsigned __int64)Handle);
  }
  return v0;
}

```

## disassembly

```asm
0x180034c64  mov     rax, rsp
0x180034c67  push    rbx
0x180034c68  sub     rsp, 30h
0x180034c6c  lea     r9, [rax+10h]
0x180034c70  mov     qword ptr [rax+18h], 0
0x180034c78  mov     r8d, 20019h
0x180034c7e  mov     qword ptr [rax+10h], 0
0x180034c86  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x180034c8d  mov     dword ptr [rax+8], 0
0x180034c94  xor     ecx, ecx
0x180034c96  xor     bl, bl
0x180034c98  call    BiOpenKey
0x180034c9d  test    eax, eax
0x180034c9f  js      short loc_180034CAD
0x180034ca1  mov     rcx, [rsp+38h+Handle]; Handle
0x180034ca6  call    BiCloseKey
0x180034cab  jmp     short loc_180034D07
0x180034cad  lea     rax, [rsp+38h+arg_0]
0x180034cb2  mov     r9d, 4
0x180034cb8  mov     [rsp+38h+var_10], rax
0x180034cbd  lea     r8, aRegistryMachin_0; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x180034cc4  lea     rax, [rsp+38h+P]
0x180034cc9  xor     ecx, ecx
0x180034ccb  lea     rdx, aPortableoperat; "PortableOperatingSystem"
0x180034cd2  mov     [rsp+38h+var_18], rax
0x180034cd7  call    BiGetRegistryValue
0x180034cdc  test    eax, eax
0x180034cde  js      short loc_180034D07
0x180034ce0  mov     r8, [rsp+38h+P]; P
0x180034ce5  mov     rcx, gs:60h
0x180034cee  cmp     dword ptr [r8], 0
0x180034cf2  mov     rcx, [rcx+30h]; HeapHandle
0x180034cf6  setnz   bl
0x180034cf9  xor     edx, edx; Flags
0x180034cfb  call    cs:__imp_RtlFreeHeap
0x180034d02  nop     dword ptr [rax+rax+00h]
0x180034d07  mov     al, bl
0x180034d09  add     rsp, 30h
0x180034d0d  pop     rbx
0x180034d0e  retn
```
