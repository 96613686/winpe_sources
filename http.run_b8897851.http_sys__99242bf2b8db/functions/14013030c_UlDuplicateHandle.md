# UlDuplicateHandle

- ea: `0x14013030c`
- end: `0x140130442`
- name: `UlDuplicateHandle`
- size: `310`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140137c2c`
- `0x140137eec`
- `0x14013a658`
- `0x140143e74`
- `0x1401444e4`
- `0x140144b84`
- `0x140146fc0`

## callees

- `0x14013030c`

## import_xrefs

- `ntoskrnl!ZwDuplicateObject` at `0x1401303f8`
- `ntoskrnl!ZwDuplicateObject` at `0x1401303f8`
- `ntoskrnl!ZwClose` at `0x140130410`
- `ntoskrnl!ZwClose` at `0x140130426`
- `ntoskrnl!ZwClose` at `0x140130410`
- `ntoskrnl!ZwClose` at `0x140130426`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14013037a`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401303bb`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14013037a`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401303bb`
- `ntoskrnl!PsProcessType` at `0x14013034c`
- `ntoskrnl!PsProcessType` at `0x14013039f`

## pseudocode

```c
__int64 __fastcall UlDuplicateHandle(void *a1, void *a2, void *a3, void **a4, __int64 a5, ULONG HandleAttributes)
{
  NTSTATUS v10; // ebx
  HANDLE SourceProcessHandle; // [rsp+60h] [rbp+8h] BYREF
  HANDLE TargetProcessHandle; // [rsp+70h] [rbp+18h] BYREF

  SourceProcessHandle = a1;
  if ( !a3 )
    return 3221225485LL;
  SourceProcessHandle = 0;
  TargetProcessHandle = 0;
  v10 = ObOpenObjectByPointer(
          UxSystemProcess,
          0x200u,
          0,
          0x1FFFFFu,
          (POBJECT_TYPE)PsProcessType,
          0,
          &SourceProcessHandle);
  if ( v10 >= 0 )
  {
    v10 = ObOpenObjectByPointer(a3, 0x200u, 0, 0x1FFFFFu, (POBJECT_TYPE)PsProcessType, 0, &TargetProcessHandle);
    if ( v10 >= 0 )
      v10 = ZwDuplicateObject(SourceProcessHandle, a2, TargetProcessHandle, a4, 0xF01FFu, HandleAttributes, 0);
  }
  if ( SourceProcessHandle )
    ZwClose(SourceProcessHandle);
  if ( TargetProcessHandle )
    ZwClose(TargetProcessHandle);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14013030c  mov     [rsp+arg_8], rbx
0x140130311  mov     [rsp+SourceProcessHandle], rcx
0x140130316  push    rbp
0x140130317  push    rsi
0x140130318  push    rdi
0x140130319  sub     rsp, 40h
0x14013031d  mov     rsi, r9
0x140130320  mov     rdi, r8
0x140130323  mov     rbp, rdx
0x140130326  test    r8, r8
0x140130329  jnz     short loc_140130335
0x14013032b  mov     eax, 0C000000Dh
0x140130330  jmp     loc_140130434
0x140130335  mov     rcx, cs:UxSystemProcess; Object
0x14013033c  lea     rax, [rsp+58h+SourceProcessHandle]
0x140130341  mov     [rsp+58h+Handle], rax; Handle
0x140130346  mov     r9d, 1FFFFFh; DesiredAccess
0x14013034c  mov     rax, cs:__imp_PsProcessType
0x140130353  xor     r8d, r8d; PassedAccessState
0x140130356  mov     [rsp+58h+AccessMode], 0; AccessMode
0x14013035b  mov     [rsp+58h+SourceProcessHandle], 0
0x140130364  mov     [rsp+58h+TargetProcessHandle], 0
0x14013036d  mov     rdx, [rax]
0x140130370  mov     [rsp+58h+ObjectType], rdx; ObjectType
0x140130375  mov     edx, 200h; HandleAttributes
0x14013037a  call    cs:__imp_ObOpenObjectByPointer
0x140130381  nop     dword ptr [rax+rax+00h]
0x140130386  mov     ebx, eax
0x140130388  test    eax, eax
0x14013038a  js      short loc_140130406
0x14013038c  lea     rax, [rsp+58h+TargetProcessHandle]
0x140130391  mov     r9d, 1FFFFFh; DesiredAccess
0x140130397  mov     [rsp+58h+Handle], rax; Handle
0x14013039c  xor     r8d, r8d; PassedAccessState
0x14013039f  mov     rax, cs:__imp_PsProcessType
0x1401303a6  mov     edx, 200h; HandleAttributes
0x1401303ab  mov     [rsp+58h+AccessMode], 0; AccessMode
0x1401303b0  mov     rcx, [rax]
0x1401303b3  mov     [rsp+58h+ObjectType], rcx; ObjectType
0x1401303b8  mov     rcx, rdi; Object
0x1401303bb  call    cs:__imp_ObOpenObjectByPointer
0x1401303c2  nop     dword ptr [rax+rax+00h]
0x1401303c7  mov     ebx, eax
0x1401303c9  test    eax, eax
0x1401303cb  js      short loc_140130406
0x1401303cd  mov     eax, [rsp+58h+HandleAttributes]
0x1401303d4  mov     r9, rsi; TargetHandle
0x1401303d7  mov     r8, [rsp+58h+TargetProcessHandle]; TargetProcessHandle
0x1401303dc  mov     rdx, rbp; SourceHandle
0x1401303df  mov     rcx, [rsp+58h+SourceProcessHandle]; SourceProcessHandle
0x1401303e4  mov     dword ptr [rsp+58h+Handle], 0; Options
0x1401303ec  mov     dword ptr [rsp+58h+AccessMode], eax; HandleAttributes
0x1401303f0  mov     dword ptr [rsp+58h+ObjectType], 0F01FFh; DesiredAccess
0x1401303f8  call    cs:__imp_ZwDuplicateObject
0x1401303ff  nop     dword ptr [rax+rax+00h]
0x140130404  mov     ebx, eax
0x140130406  mov     rcx, [rsp+58h+SourceProcessHandle]; Handle
0x14013040b  test    rcx, rcx
0x14013040e  jz      short loc_14013041C
0x140130410  call    cs:__imp_ZwClose
0x140130417  nop     dword ptr [rax+rax+00h]
0x14013041c  mov     rcx, [rsp+58h+TargetProcessHandle]; Handle
0x140130421  test    rcx, rcx
0x140130424  jz      short loc_140130432
0x140130426  call    cs:__imp_ZwClose
0x14013042d  nop     dword ptr [rax+rax+00h]
0x140130432  mov     eax, ebx
0x140130434  mov     rbx, [rsp+58h+arg_8]
0x140130439  add     rsp, 40h
0x14013043d  pop     rdi
0x14013043e  pop     rsi
0x14013043f  pop     rbp
0x140130440  retn
```
