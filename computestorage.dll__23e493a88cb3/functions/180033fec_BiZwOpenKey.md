# BiZwOpenKey

- ea: `0x180033fec`
- end: `0x180034052`
- name: `BiZwOpenKey`
- size: `102`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800322e4`
- `0x180033914`

## callees

- `0x180032bc4`
- `0x180033fec`
- `0x180039d48`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18003403b`
- `ntdll!ZwOpenKey` at `0x18003403b`

## pseudocode

```c
__int64 __fastcall BiZwOpenKey(__int64 *KeyHandle, ACCESS_MASK a2, struct _OBJECT_ATTRIBUTES *a3)
{
  unsigned __int64 RootDirectory; // rcx
  unsigned int v5; // eax
  int v6; // edx
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  RootDirectory = (unsigned __int64)a3->RootDirectory;
  if ( (RootDirectory & 1) != 0 )
  {
    v5 = OROpenKey(RootDirectory & 0xFFFFFFFFFFFFFFFEuLL, a3->ObjectName->Buffer, &v8);
    v6 = BiDosErrorToNtStatus(v5);
    if ( v6 >= 0 )
      *KeyHandle = v8 | 1;
  }
  else
  {
    return (unsigned int)ZwOpenKey((PHANDLE)KeyHandle, a2, a3);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180033fec  push    rbx
0x180033fee  sub     rsp, 20h
0x180033ff2  mov     rbx, rcx
0x180033ff5  mov     [rsp+28h+arg_10], 0
0x180033ffe  mov     rcx, [r8+8]
0x180034002  test    cl, 1
0x180034005  jz      short loc_180034038
0x180034007  mov     rdx, [r8+10h]
0x18003400b  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18003400f  lea     r8, [rsp+28h+arg_10]
0x180034014  mov     rdx, [rdx+8]
0x180034018  call    OROpenKey
0x18003401d  mov     ecx, eax
0x18003401f  call    BiDosErrorToNtStatus
0x180034024  mov     edx, eax; DesiredAccess
0x180034026  test    eax, eax
0x180034028  js      short loc_180034049
0x18003402a  mov     rax, [rsp+28h+arg_10]
0x18003402f  or      rax, 1
0x180034033  mov     [rbx], rax
0x180034036  jmp     short loc_180034049
0x180034038  mov     rcx, rbx; KeyHandle
0x18003403b  call    cs:__imp_ZwOpenKey
0x180034042  nop     dword ptr [rax+rax+00h]
0x180034047  mov     edx, eax
0x180034049  mov     eax, edx
0x18003404b  add     rsp, 20h
0x18003404f  pop     rbx
0x180034050  retn
```
