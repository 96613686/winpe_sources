# VIDMM_SYSTEM_HEAP::GenerateSectionHandle(VIDMM_HEAP_ALLOC const *,void * *)

- ea: `0x1400c5460`
- end: `0x1400c5558`
- name: `?GenerateSectionHandle@VIDMM_SYSTEM_HEAP@@UEAAJPEBUVIDMM_HEAP_ALLOC@@PEAPEAX@Z`
- size: `248`
- prototype: `__int64 __fastcall(VIDMM_SYSTEM_HEAP *__hidden this, const struct VIDMM_HEAP_ALLOC *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400045ec`
- `0x1400c5460`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x1400c5529`
- `ntoskrnl!ObCloseHandle` at `0x1400c5529`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400c54ae`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400c54ae`
- `ntoskrnl!ObGetObjectType` at `0x1400c547d`
- `ntoskrnl!ObGetObjectType` at `0x1400c547d`
- `watchdog!WdLogSingleEntry2` at `0x1400c54cc`
- `watchdog!WdLogSingleEntry2` at `0x1400c54cc`

## string_xrefs

- `0x1400c54e1`: `Unable to open section object 0x%I64p into handle table, Status = 0x%I64p`

## pseudocode

```c
__int64 __fastcall VIDMM_SYSTEM_HEAP::GenerateSectionHandle(VIDMM_SYSTEM_HEAP *this, PVOID *a2, void **a3)
{
  PVOID v3; // rcx
  struct _OBJECT_TYPE *ObjectType; // rax
  NTSTATUS v7; // eax
  __int64 v8; // rsi
  int v9; // r8d
  HANDLE Handle; // [rsp+88h] [rbp+10h] BYREF

  v3 = *a2;
  Handle = 0;
  ObjectType = (struct _OBJECT_TYPE *)ObGetObjectType(v3);
  v7 = ObOpenObjectByPointer(*a2, 0, 0, 0xC0000000, ObjectType, 1, &Handle);
  v8 = v7;
  if ( v7 >= 0 )
  {
    *a3 = Handle;
    return 0;
  }
  else
  {
    WdLogSingleEntry2(1, *a2, v7);
    WdLogGlobalForLineNumber = 1212;
    DxgkLogInternalTriageEvent(
      (unsigned int)*a2,
      0x40000,
      v9,
      (unsigned int)L"Unable to open section object 0x%I64p into handle table, Status = 0x%I64p",
      (__int64)*a2,
      v8,
      0,
      0);
    if ( Handle )
      ObCloseHandle(Handle, ((unsigned __int64)Handle & 0xFFFFFFFF80000000uLL) == 0);
    *a3 = 0;
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x1400c5460  mov     rax, rsp
0x1400c5463  push    rbx
0x1400c5464  push    rsi
0x1400c5465  push    rdi
0x1400c5466  push    r14
0x1400c5468  sub     rsp, 58h
0x1400c546c  mov     rcx, [rdx]
0x1400c546f  mov     rdi, r8
0x1400c5472  mov     r14, rdx
0x1400c5475  mov     qword ptr [rax+10h], 0
0x1400c547d  call    cs:__imp_ObGetObjectType
0x1400c5484  nop     dword ptr [rax+rax+00h]
0x1400c5489  lea     rcx, [rsp+78h+arg_8]
0x1400c5491  mov     r9d, 0C0000000h; DesiredAccess
0x1400c5497  mov     [rsp+78h+Handle], rcx; Handle
0x1400c549c  xor     r8d, r8d; PassedAccessState
0x1400c549f  mov     rcx, [r14]; Object
0x1400c54a2  xor     edx, edx; HandleAttributes
0x1400c54a4  mov     [rsp+78h+AccessMode], 1; AccessMode
0x1400c54a9  mov     [rsp+78h+ObjectType], rax; ObjectType
0x1400c54ae  call    cs:__imp_ObOpenObjectByPointer
0x1400c54b5  nop     dword ptr [rax+rax+00h]
0x1400c54ba  movsxd  rsi, eax
0x1400c54bd  test    eax, eax
0x1400c54bf  jns     short loc_1400C5540
0x1400c54c1  mov     rdx, [r14]
0x1400c54c4  mov     r8, rsi
0x1400c54c7  mov     ecx, 1
0x1400c54cc  call    cs:__imp_WdLogSingleEntry2
0x1400c54d3  nop     dword ptr [rax+rax+00h]
0x1400c54d8  mov     [rsp+78h+var_40], 0
0x1400c54e1  lea     r9, aUnableToOpenSe; "Unable to open section object 0x%I64p i"...
0x1400c54e8  mov     cs:WdLogGlobalForLineNumber, 4BCh
0x1400c54f2  mov     edx, 40000h
0x1400c54f7  mov     rcx, [r14]
0x1400c54fa  mov     [rsp+78h+Handle], 0
0x1400c5503  mov     qword ptr [rsp+78h+AccessMode], rsi
0x1400c5508  mov     [rsp+78h+ObjectType], rcx
0x1400c550d  call    DxgkLogInternalTriageEvent
0x1400c5512  mov     rcx, [rsp+78h+arg_8]; Handle
0x1400c551a  test    rcx, rcx
0x1400c551d  jz      short loc_1400C5535
0x1400c551f  test    rcx, 0FFFFFFFF80000000h
0x1400c5526  setz    dl; PreviousMode
0x1400c5529  call    cs:__imp_ObCloseHandle
0x1400c5530  nop     dword ptr [rax+rax+00h]
0x1400c5535  mov     qword ptr [rdi], 0
0x1400c553c  mov     eax, esi
0x1400c553e  jmp     short loc_1400C554D
0x1400c5540  mov     rax, [rsp+78h+arg_8]
0x1400c5548  mov     [rdi], rax
0x1400c554b  xor     eax, eax
0x1400c554d  add     rsp, 58h
0x1400c5551  pop     r14
0x1400c5553  pop     rdi
0x1400c5554  pop     rsi
0x1400c5555  pop     rbx
0x1400c5556  retn
```
