# UlDuplicateHandle

- ea: `0x1c012d39c`
- end: `0x1c012d4c9`
- name: `UlDuplicateHandle`
- size: `301`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1c0139a20`
- `0x1c013a880`
- `0x1c015789c`

## callees

- `0x1c012d39c`

## import_xrefs

- `ntoskrnl!ZwDuplicateObject` at `0x1c012d47f`
- `ntoskrnl!ZwDuplicateObject` at `0x1c012d47f`
- `ntoskrnl!ZwClose` at `0x1c012d497`
- `ntoskrnl!ZwClose` at `0x1c012d4ad`
- `ntoskrnl!ZwClose` at `0x1c012d497`
- `ntoskrnl!ZwClose` at `0x1c012d4ad`
- `ntoskrnl!PsProcessType` at `0x1c012d3eb`
- `ntoskrnl!PsProcessType` at `0x1c012d429`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1c012d404`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1c012d445`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1c012d404`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1c012d445`

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
0x1c012d39c  mov     [rsp+arg_8], rbx
0x1c012d3a1  mov     [rsp+SourceProcessHandle], rcx
0x1c012d3a6  push    rbp
0x1c012d3a7  push    rsi
0x1c012d3a8  push    rdi
0x1c012d3a9  sub     rsp, 40h
0x1c012d3ad  mov     rcx, cs:UxSystemProcess; Object
0x1c012d3b4  mov     rsi, r9
0x1c012d3b7  mov     rdi, r8
0x1c012d3ba  mov     rbp, rdx
0x1c012d3bd  test    r8, r8
0x1c012d3c0  jnz     short loc_1C012D3CC
0x1c012d3c2  mov     eax, 0C000000Dh
0x1c012d3c7  jmp     loc_1C012D4BB
0x1c012d3cc  and     [rsp+58h+SourceProcessHandle], 0
0x1c012d3d2  lea     rax, [rsp+58h+SourceProcessHandle]
0x1c012d3d7  and     [rsp+58h+TargetProcessHandle], 0
0x1c012d3dd  mov     r9d, 1FFFFFh; DesiredAccess
0x1c012d3e3  mov     [rsp+58h+Handle], rax; Handle
0x1c012d3e8  xor     r8d, r8d; PassedAccessState
0x1c012d3eb  mov     rax, cs:__imp_PsProcessType
0x1c012d3f2  mov     [rsp+58h+AccessMode], 0; AccessMode
0x1c012d3f7  mov     rdx, [rax]
0x1c012d3fa  mov     [rsp+58h+ObjectType], rdx; ObjectType
0x1c012d3ff  mov     edx, 200h; HandleAttributes
0x1c012d404  call    cs:__imp_ObOpenObjectByPointer
0x1c012d40b  nop     dword ptr [rax+rax+00h]
0x1c012d410  mov     ebx, eax
0x1c012d412  test    eax, eax
0x1c012d414  js      short loc_1C012D48D
0x1c012d416  lea     rax, [rsp+58h+TargetProcessHandle]
0x1c012d41b  mov     r9d, 1FFFFFh; DesiredAccess
0x1c012d421  mov     [rsp+58h+Handle], rax; Options
0x1c012d426  xor     r8d, r8d; PassedAccessState
0x1c012d429  mov     rax, cs:__imp_PsProcessType
0x1c012d430  mov     edx, 200h; HandleAttributes
0x1c012d435  mov     [rsp+58h+AccessMode], 0; AccessMode
0x1c012d43a  mov     rcx, [rax]
0x1c012d43d  mov     [rsp+58h+ObjectType], rcx; ObjectType
0x1c012d442  mov     rcx, rdi; Object
0x1c012d445  call    cs:__imp_ObOpenObjectByPointer
0x1c012d44c  nop     dword ptr [rax+rax+00h]
0x1c012d451  mov     ebx, eax
0x1c012d453  test    eax, eax
0x1c012d455  js      short loc_1C012D48D
0x1c012d457  and     dword ptr [rsp+58h+Handle], 0
0x1c012d45c  mov     r9, rsi; TargetHandle
0x1c012d45f  mov     eax, [rsp+58h+HandleAttributes]
0x1c012d466  mov     rdx, rbp; SourceHandle
0x1c012d469  mov     r8, [rsp+58h+TargetProcessHandle]; TargetProcessHandle
0x1c012d46e  mov     rcx, [rsp+58h+SourceProcessHandle]; SourceProcessHandle
0x1c012d473  mov     dword ptr [rsp+58h+AccessMode], eax; HandleAttributes
0x1c012d477  mov     dword ptr [rsp+58h+ObjectType], 0F01FFh; DesiredAccess
0x1c012d47f  call    cs:__imp_ZwDuplicateObject
0x1c012d486  nop     dword ptr [rax+rax+00h]
0x1c012d48b  mov     ebx, eax
0x1c012d48d  mov     rcx, [rsp+58h+SourceProcessHandle]; Handle
0x1c012d492  test    rcx, rcx
0x1c012d495  jz      short loc_1C012D4A3
0x1c012d497  call    cs:__imp_ZwClose
0x1c012d49e  nop     dword ptr [rax+rax+00h]
0x1c012d4a3  mov     rcx, [rsp+58h+TargetProcessHandle]; Handle
0x1c012d4a8  test    rcx, rcx
0x1c012d4ab  jz      short loc_1C012D4B9
0x1c012d4ad  call    cs:__imp_ZwClose
0x1c012d4b4  nop     dword ptr [rax+rax+00h]
0x1c012d4b9  mov     eax, ebx
0x1c012d4bb  mov     rbx, [rsp+58h+arg_8]
0x1c012d4c0  add     rsp, 40h
0x1c012d4c4  pop     rdi
0x1c012d4c5  pop     rsi
0x1c012d4c6  pop     rbp
0x1c012d4c7  retn
```
