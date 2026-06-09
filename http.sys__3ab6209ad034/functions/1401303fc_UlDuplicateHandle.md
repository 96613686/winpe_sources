# UlDuplicateHandle

- ea: `0x1401303fc`
- end: `0x140130532`
- name: `UlDuplicateHandle`
- size: `310`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140137d1c`
- `0x140137fdc`
- `0x14013a748`
- `0x140143f64`
- `0x1401445d4`
- `0x140144c74`
- `0x1401470b0`

## callees

- `0x1401303fc`

## import_xrefs

- `ntoskrnl!ZwDuplicateObject` at `0x1401304e8`
- `ntoskrnl!ZwDuplicateObject` at `0x1401304e8`
- `ntoskrnl!ZwClose` at `0x140130500`
- `ntoskrnl!ZwClose` at `0x140130516`
- `ntoskrnl!ZwClose` at `0x140130500`
- `ntoskrnl!ZwClose` at `0x140130516`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14013046a`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401304ab`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14013046a`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401304ab`
- `ntoskrnl!PsProcessType` at `0x14013043c`
- `ntoskrnl!PsProcessType` at `0x14013048f`

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
0x1401303fc  mov     [rsp+arg_8], rbx
0x140130401  mov     [rsp+SourceProcessHandle], rcx
0x140130406  push    rbp
0x140130407  push    rsi
0x140130408  push    rdi
0x140130409  sub     rsp, 40h
0x14013040d  mov     rsi, r9
0x140130410  mov     rdi, r8
0x140130413  mov     rbp, rdx
0x140130416  test    r8, r8
0x140130419  jnz     short loc_140130425
0x14013041b  mov     eax, 0C000000Dh
0x140130420  jmp     loc_140130524
0x140130425  mov     rcx, cs:UxSystemProcess; Object
0x14013042c  lea     rax, [rsp+58h+SourceProcessHandle]
0x140130431  mov     [rsp+58h+Handle], rax; Handle
0x140130436  mov     r9d, 1FFFFFh; DesiredAccess
0x14013043c  mov     rax, cs:__imp_PsProcessType
0x140130443  xor     r8d, r8d; PassedAccessState
0x140130446  mov     [rsp+58h+AccessMode], 0; AccessMode
0x14013044b  mov     [rsp+58h+SourceProcessHandle], 0
0x140130454  mov     [rsp+58h+TargetProcessHandle], 0
0x14013045d  mov     rdx, [rax]
0x140130460  mov     [rsp+58h+ObjectType], rdx; ObjectType
0x140130465  mov     edx, 200h; HandleAttributes
0x14013046a  call    cs:__imp_ObOpenObjectByPointer
0x140130471  nop     dword ptr [rax+rax+00h]
0x140130476  mov     ebx, eax
0x140130478  test    eax, eax
0x14013047a  js      short loc_1401304F6
0x14013047c  lea     rax, [rsp+58h+TargetProcessHandle]
0x140130481  mov     r9d, 1FFFFFh; DesiredAccess
0x140130487  mov     [rsp+58h+Handle], rax; Handle
0x14013048c  xor     r8d, r8d; PassedAccessState
0x14013048f  mov     rax, cs:__imp_PsProcessType
0x140130496  mov     edx, 200h; HandleAttributes
0x14013049b  mov     [rsp+58h+AccessMode], 0; AccessMode
0x1401304a0  mov     rcx, [rax]
0x1401304a3  mov     [rsp+58h+ObjectType], rcx; ObjectType
0x1401304a8  mov     rcx, rdi; Object
0x1401304ab  call    cs:__imp_ObOpenObjectByPointer
0x1401304b2  nop     dword ptr [rax+rax+00h]
0x1401304b7  mov     ebx, eax
0x1401304b9  test    eax, eax
0x1401304bb  js      short loc_1401304F6
0x1401304bd  mov     eax, [rsp+58h+HandleAttributes]
0x1401304c4  mov     r9, rsi; TargetHandle
0x1401304c7  mov     r8, [rsp+58h+TargetProcessHandle]; TargetProcessHandle
0x1401304cc  mov     rdx, rbp; SourceHandle
0x1401304cf  mov     rcx, [rsp+58h+SourceProcessHandle]; SourceProcessHandle
0x1401304d4  mov     dword ptr [rsp+58h+Handle], 0; Options
0x1401304dc  mov     dword ptr [rsp+58h+AccessMode], eax; HandleAttributes
0x1401304e0  mov     dword ptr [rsp+58h+ObjectType], 0F01FFh; DesiredAccess
0x1401304e8  call    cs:__imp_ZwDuplicateObject
0x1401304ef  nop     dword ptr [rax+rax+00h]
0x1401304f4  mov     ebx, eax
0x1401304f6  mov     rcx, [rsp+58h+SourceProcessHandle]; Handle
0x1401304fb  test    rcx, rcx
0x1401304fe  jz      short loc_14013050C
0x140130500  call    cs:__imp_ZwClose
0x140130507  nop     dword ptr [rax+rax+00h]
0x14013050c  mov     rcx, [rsp+58h+TargetProcessHandle]; Handle
0x140130511  test    rcx, rcx
0x140130514  jz      short loc_140130522
0x140130516  call    cs:__imp_ZwClose
0x14013051d  nop     dword ptr [rax+rax+00h]
0x140130522  mov     eax, ebx
0x140130524  mov     rbx, [rsp+58h+arg_8]
0x140130529  add     rsp, 40h
0x14013052d  pop     rdi
0x14013052e  pop     rsi
0x14013052f  pop     rbp
0x140130530  retn
```
