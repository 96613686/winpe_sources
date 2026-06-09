# MountMgrQueryBootDriveLetter

- ea: `0x14000ccb4`
- end: `0x14000cd4a`
- name: `MountMgrQueryBootDriveLetter`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000acd8`

## callees

- `0x140003280`
- `0x14000ccb4`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000cd17`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000cd17`

## pseudocode

```c
__int64 __fastcall MountMgrQueryBootDriveLetter(_BYTE *a1)
{
  __int64 result; // rax
  _QWORD v3[15]; // [rsp+30h] [rbp-78h] BYREF
  int v4; // [rsp+B0h] [rbp+8h] BYREF

  v4 = 0;
  memset(v3, 0, 0x70u);
  LODWORD(v3[1]) = 292;
  LODWORD(v3[4]) = 0x4000000;
  v3[2] = L"SystemBootDriveLetter";
  v3[3] = &v4;
  result = RtlQueryRegistryValuesEx(2, 0, v3, 0, 0);
  if ( (int)result >= 0 && (unsigned int)(v4 - 65) > 0x19 )
    result = 3221227787LL;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x14000ccb4  mov     rax, rsp
0x14000ccb7  push    rbx
0x14000ccb8  sub     rsp, 0A0h
0x14000ccbf  xor     edx, edx; Val
0x14000ccc1  mov     dword ptr [rax+8], 0
0x14000ccc8  mov     rbx, rcx
0x14000cccb  lea     rcx, [rax-78h]; void *
0x14000cccf  lea     r8d, [rdx+70h]; Size
0x14000ccd3  call    memset
0x14000ccd8  xor     edx, edx
0x14000ccda  mov     [rsp+0A8h+var_70], 124h
0x14000cce2  lea     rax, aSystembootdriv; "SystemBootDriveLetter"
0x14000cce9  mov     [rsp+0A8h+var_58], 4000000h
0x14000ccf1  mov     [rsp+0A8h+var_68], rax
0x14000ccf6  lea     r8, [rsp+0A8h+var_78]
0x14000ccfb  lea     rax, [rsp+0A8h+arg_0]
0x14000cd03  mov     [rsp+0A8h+var_88], 0
0x14000cd0c  lea     ecx, [rdx+2]
0x14000cd0f  mov     [rsp+0A8h+var_60], rax
0x14000cd14  xor     r9d, r9d
0x14000cd17  call    cs:__imp_RtlQueryRegistryValuesEx
0x14000cd1e  nop     dword ptr [rax+rax+00h]
0x14000cd23  mov     edx, [rsp+0A8h+arg_0]
0x14000cd2a  test    eax, eax
0x14000cd2c  js      short loc_14000CD3E
0x14000cd2e  lea     ecx, [rdx-41h]
0x14000cd31  mov     r8d, 0C000090Bh
0x14000cd37  cmp     ecx, 19h
0x14000cd3a  cmova   eax, r8d
0x14000cd3e  mov     [rbx], dl
0x14000cd40  add     rsp, 0A0h
0x14000cd47  pop     rbx
0x14000cd48  retn
```
