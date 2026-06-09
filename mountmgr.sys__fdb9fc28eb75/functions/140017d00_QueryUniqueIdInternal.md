# QueryUniqueIdInternal

- ea: `0x140017d00`
- end: `0x140017dd8`
- name: `QueryUniqueIdInternal`
- size: `216`
- prototype: `__int64 __fastcall(__int64, PDEVICE_OBJECT DeviceObject)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fdb8`
- `0x140017a20`

## callees

- `0x140017bf0`
- `0x140017d00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140017d6b`
- `ntoskrnl!ExAllocatePool2` at `0x140017d6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017d4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017dbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017d4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017dbb`

## pseudocode

```c
__int64 __fastcall QueryUniqueIdInternal(struct _FILE_OBJECT *a1, PDEVICE_OBJECT DeviceObject, _QWORD *a3)
{
  int v3; // ebx
  unsigned __int16 *v4; // rsi
  unsigned int v5; // ebp
  ULONG v9; // r14d
  unsigned __int16 *Pool2; // rax
  NTSTATUS v12; // eax

  v3 = 0;
  v4 = 0;
  *a3 = 0;
  v5 = 0;
  v9 = 130;
  while ( 1 )
  {
    if ( v5 >= 2 )
    {
      if ( v3 < 0 )
      {
        if ( v4 )
LABEL_7:
          ExFreePoolWithTag(v4, 0);
      }
      else
      {
LABEL_4:
        *a3 = v4;
      }
      return (unsigned int)v3;
    }
    Pool2 = (unsigned __int16 *)ExAllocatePool2(258, v9, 1098149453);
    v4 = Pool2;
    if ( !Pool2 )
      return 3221225626LL;
    v12 = MountMgrSendDeviceControl(DeviceObject, 0x4D0000u, 0, 0, Pool2, v9, a1);
    v3 = v12;
    if ( v12 >= 0 )
      goto LABEL_4;
    if ( v12 != -2147483643 )
      goto LABEL_7;
    v9 = *v4 + 2;
    ExFreePoolWithTag(v4, 0);
    ++v5;
  }
}

```

## disassembly

```asm
0x140017d00  push    rbx
0x140017d02  push    rbp
0x140017d03  push    rsi
0x140017d04  push    rdi
0x140017d05  push    r12
0x140017d07  push    r14
0x140017d09  push    r15
0x140017d0b  sub     rsp, 40h
0x140017d0f  xor     ebx, ebx
0x140017d11  xor     esi, esi
0x140017d13  mov     [r8], rbx
0x140017d16  xor     ebp, ebp
0x140017d18  mov     rdi, r8
0x140017d1b  mov     r15, rdx
0x140017d1e  mov     r12, rcx
0x140017d21  mov     r14d, 82h
0x140017d27  cmp     ebp, 2
0x140017d2a  jb      short loc_140017D5D
0x140017d2c  test    ebx, ebx
0x140017d2e  js      short loc_140017D45
0x140017d30  mov     [rdi], rsi
0x140017d33  mov     eax, ebx
0x140017d35  add     rsp, 40h
0x140017d39  pop     r15
0x140017d3b  pop     r14
0x140017d3d  pop     r12
0x140017d3f  pop     rdi
0x140017d40  pop     rsi
0x140017d41  pop     rbp
0x140017d42  pop     rbx
0x140017d43  retn
0x140017d45  test    rsi, rsi
0x140017d48  jz      short loc_140017D33
0x140017d4a  xor     edx, edx; Tag
0x140017d4c  mov     rcx, rsi; P
0x140017d4f  call    cs:__imp_ExFreePoolWithTag
0x140017d56  nop     dword ptr [rax+rax+00h]
0x140017d5b  jmp     short loc_140017D33
0x140017d5d  mov     edx, r14d
0x140017d60  mov     ecx, 102h
0x140017d65  mov     r8d, 41746E4Dh
0x140017d6b  call    cs:__imp_ExAllocatePool2
0x140017d72  nop     dword ptr [rax+rax+00h]
0x140017d77  mov     rsi, rax
0x140017d7a  test    rax, rax
0x140017d7d  jz      short loc_140017DCE
0x140017d7f  mov     [rsp+78h+var_48], r12; __int64
0x140017d84  xor     r9d, r9d; InputBufferLength
0x140017d87  mov     [rsp+78h+var_50], r14d; ULONG
0x140017d8c  xor     r8d, r8d; InputBuffer
0x140017d8f  mov     edx, 4D0000h; IoControlCode
0x140017d94  mov     [rsp+78h+var_58], rax; PVOID
0x140017d99  mov     rcx, r15; DeviceObject
0x140017d9c  call    MountMgrSendDeviceControl
0x140017da1  mov     ebx, eax
0x140017da3  test    eax, eax
0x140017da5  jns     short loc_140017D30
0x140017da7  cmp     eax, 80000005h
0x140017dac  jnz     short loc_140017D4A
0x140017dae  movzx   r14d, word ptr [rsi]
0x140017db2  xor     edx, edx; Tag
0x140017db4  mov     rcx, rsi; P
0x140017db7  add     r14d, 2
0x140017dbb  call    cs:__imp_ExFreePoolWithTag
0x140017dc2  nop     dword ptr [rax+rax+00h]
0x140017dc7  inc     ebp
0x140017dc9  jmp     loc_140017D27
0x140017dce  mov     eax, 0C000009Ah
0x140017dd3  jmp     loc_140017D35
```
