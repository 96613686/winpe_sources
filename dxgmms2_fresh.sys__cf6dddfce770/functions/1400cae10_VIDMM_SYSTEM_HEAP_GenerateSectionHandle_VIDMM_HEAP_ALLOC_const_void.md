# VIDMM_SYSTEM_HEAP::GenerateSectionHandle(VIDMM_HEAP_ALLOC const *,void * *)

- ea: `0x1400cae10`
- end: `0x1400caf08`
- name: `?GenerateSectionHandle@VIDMM_SYSTEM_HEAP@@UEAAJPEBUVIDMM_HEAP_ALLOC@@PEAPEAX@Z`
- size: `248`
- prototype: `__int64 __fastcall(VIDMM_SYSTEM_HEAP *__hidden this, const struct VIDMM_HEAP_ALLOC *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140004268`
- `0x1400cae10`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x1400caed9`
- `ntoskrnl!ObCloseHandle` at `0x1400caed9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400cae5e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400cae5e`
- `ntoskrnl!ObGetObjectType` at `0x1400cae2d`
- `ntoskrnl!ObGetObjectType` at `0x1400cae2d`
- `watchdog!WdLogSingleEntry2` at `0x1400cae7c`
- `watchdog!WdLogSingleEntry2` at `0x1400cae7c`

## string_xrefs

- `0x1400cae91`: `Unable to open section object 0x%I64p into handle table, Status = 0x%I64p`

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
0x1400cae10  mov     rax, rsp
0x1400cae13  push    rbx
0x1400cae14  push    rsi
0x1400cae15  push    rdi
0x1400cae16  push    r14
0x1400cae18  sub     rsp, 58h
0x1400cae1c  mov     rcx, [rdx]
0x1400cae1f  mov     rdi, r8
0x1400cae22  mov     r14, rdx
0x1400cae25  mov     qword ptr [rax+10h], 0
0x1400cae2d  call    cs:__imp_ObGetObjectType
0x1400cae34  nop     dword ptr [rax+rax+00h]
0x1400cae39  lea     rcx, [rsp+78h+arg_8]
0x1400cae41  mov     r9d, 0C0000000h; DesiredAccess
0x1400cae47  mov     [rsp+78h+Handle], rcx; Handle
0x1400cae4c  xor     r8d, r8d; PassedAccessState
0x1400cae4f  mov     rcx, [r14]; Object
0x1400cae52  xor     edx, edx; HandleAttributes
0x1400cae54  mov     [rsp+78h+AccessMode], 1; AccessMode
0x1400cae59  mov     [rsp+78h+ObjectType], rax; ObjectType
0x1400cae5e  call    cs:__imp_ObOpenObjectByPointer
0x1400cae65  nop     dword ptr [rax+rax+00h]
0x1400cae6a  movsxd  rsi, eax
0x1400cae6d  test    eax, eax
0x1400cae6f  jns     short loc_1400CAEF0
0x1400cae71  mov     rdx, [r14]
0x1400cae74  mov     r8, rsi
0x1400cae77  mov     ecx, 1
0x1400cae7c  call    cs:__imp_WdLogSingleEntry2
0x1400cae83  nop     dword ptr [rax+rax+00h]
0x1400cae88  mov     [rsp+78h+var_40], 0
0x1400cae91  lea     r9, aUnableToOpenSe; "Unable to open section object 0x%I64p i"...
0x1400cae98  mov     cs:WdLogGlobalForLineNumber, 4BCh
0x1400caea2  mov     edx, 40000h
0x1400caea7  mov     rcx, [r14]
0x1400caeaa  mov     [rsp+78h+Handle], 0
0x1400caeb3  mov     qword ptr [rsp+78h+AccessMode], rsi
0x1400caeb8  mov     [rsp+78h+ObjectType], rcx
0x1400caebd  call    DxgkLogInternalTriageEvent
0x1400caec2  mov     rcx, [rsp+78h+arg_8]; Handle
0x1400caeca  test    rcx, rcx
0x1400caecd  jz      short loc_1400CAEE5
0x1400caecf  test    rcx, 0FFFFFFFF80000000h
0x1400caed6  setz    dl; PreviousMode
0x1400caed9  call    cs:__imp_ObCloseHandle
0x1400caee0  nop     dword ptr [rax+rax+00h]
0x1400caee5  mov     qword ptr [rdi], 0
0x1400caeec  mov     eax, esi
0x1400caeee  jmp     short loc_1400CAEFD
0x1400caef0  mov     rax, [rsp+78h+arg_8]
0x1400caef8  mov     [rdi], rax
0x1400caefb  xor     eax, eax
0x1400caefd  add     rsp, 58h
0x1400caf01  pop     r14
0x1400caf03  pop     rdi
0x1400caf04  pop     rsi
0x1400caf05  pop     rbx
0x1400caf06  retn
```
