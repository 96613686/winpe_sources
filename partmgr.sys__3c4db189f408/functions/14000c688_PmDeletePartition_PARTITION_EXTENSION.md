# PmDeletePartition(_PARTITION_EXTENSION *)

- ea: `0x14000c688`
- end: `0x14000c727`
- name: `?PmDeletePartition@@YAXPEAU_PARTITION_EXTENSION@@@Z`
- size: `159`
- prototype: `void __fastcall(struct _PARTITION_EXTENSION *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400087c0`
- `0x1400254c8`

## callees

- `0x14000c688`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c6bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c6ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c6bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c6ef`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c6ff`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c6ff`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000c6d8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000c6d8`
- `ntoskrnl!IoDeleteDevice` at `0x14000c70f`
- `ntoskrnl!IoDeleteDevice` at `0x14000c70f`

## pseudocode

```c
void __fastcall PmDeletePartition(struct _PARTITION_EXTENSION *a1)
{
  _QWORD **v2; // rdi
  _QWORD *v3; // rcx
  __int64 v4; // rax
  _QWORD *v5; // rdx
  void *v6; // rcx

  v2 = (_QWORD **)((char *)a1 + 312);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    v4 = *v3;
    if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    ExFreePoolWithTag(v3, 0);
  }
  RtlFreeUnicodeString((PUNICODE_STRING)a1 + 3);
  v6 = (void *)*((_QWORD *)a1 + 10);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  ObfDereferenceObject(*((PVOID *)a1 + 2));
  IoDeleteDevice(*((PDEVICE_OBJECT *)a1 + 1));
}

```

## disassembly

```asm
0x14000c688  mov     [rsp+arg_0], rbx
0x14000c68d  push    rdi
0x14000c68e  sub     rsp, 20h
0x14000c692  mov     rbx, rcx
0x14000c695  lea     rdi, [rcx+138h]
0x14000c69c  mov     rcx, [rdi]; P
0x14000c69f  cmp     rcx, rdi
0x14000c6a2  jz      short loc_14000C6D4
0x14000c6a4  mov     rax, [rcx]
0x14000c6a7  cmp     [rax+8], rcx
0x14000c6ab  jnz     short loc_14000C6CD
0x14000c6ad  mov     rdx, [rcx+8]
0x14000c6b1  cmp     [rdx], rcx
0x14000c6b4  jnz     short loc_14000C6CD
0x14000c6b6  mov     [rdx], rax
0x14000c6b9  mov     [rax+8], rdx
0x14000c6bd  xor     edx, edx; Tag
0x14000c6bf  call    cs:__imp_ExFreePoolWithTag
0x14000c6c6  nop     dword ptr [rax+rax+00h]
0x14000c6cb  jmp     short loc_14000C69C
0x14000c6cd  mov     ecx, 3
0x14000c6d2  int     29h; Win8: RtlFailFast(ecx)
0x14000c6d4  lea     rcx, [rbx+30h]; UnicodeString
0x14000c6d8  call    cs:__imp_RtlFreeUnicodeString
0x14000c6df  nop     dword ptr [rax+rax+00h]
0x14000c6e4  mov     rcx, [rbx+50h]; P
0x14000c6e8  test    rcx, rcx
0x14000c6eb  jz      short loc_14000C6FB
0x14000c6ed  xor     edx, edx; Tag
0x14000c6ef  call    cs:__imp_ExFreePoolWithTag
0x14000c6f6  nop     dword ptr [rax+rax+00h]
0x14000c6fb  mov     rcx, [rbx+10h]; Object
0x14000c6ff  call    cs:__imp_ObfDereferenceObject
0x14000c706  nop     dword ptr [rax+rax+00h]
0x14000c70b  mov     rcx, [rbx+8]; DeviceObject
0x14000c70f  call    cs:__imp_IoDeleteDevice
0x14000c716  nop     dword ptr [rax+rax+00h]
0x14000c71b  mov     rbx, [rsp+28h+arg_0]
0x14000c720  add     rsp, 20h
0x14000c724  pop     rdi
0x14000c725  retn
```
