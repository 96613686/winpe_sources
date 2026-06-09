# NpFsdSetSecurityInfo

- ea: `0x140015b90`
- end: `0x140015bef`
- name: `NpFsdSetSecurityInfo`
- size: `95`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140015b90`
- `0x140015bf8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140015ba0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140015ba0`
- `ntoskrnl!IofCompleteRequest` at `0x140015bd5`
- `ntoskrnl!IofCompleteRequest` at `0x140015bd5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015bb9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015bb9`

## pseudocode

```c
__int64 __fastcall NpFsdSetSecurityInfo(__int64 a1, IRP *a2)
{
  unsigned int v4; // ebx

  KeEnterCriticalRegion();
  v4 = NpCommonSetSecurityInfo(a1, (__int64)a2);
  KeLeaveCriticalRegion();
  if ( v4 != 259 )
  {
    a2->IoStatus.Status = v4;
    IofCompleteRequest(a2, 2);
  }
  return v4;
}

```

## disassembly

```asm
0x140015b90  mov     [rsp+arg_0], rbx
0x140015b95  push    rdi
0x140015b96  sub     rsp, 20h
0x140015b9a  mov     rdi, rdx
0x140015b9d  mov     rbx, rcx
0x140015ba0  call    cs:__imp_KeEnterCriticalRegion
0x140015ba7  nop     dword ptr [rax+rax+00h]
0x140015bac  mov     rdx, rdi
0x140015baf  mov     rcx, rbx
0x140015bb2  call    NpCommonSetSecurityInfo
0x140015bb7  mov     ebx, eax
0x140015bb9  call    cs:__imp_KeLeaveCriticalRegion
0x140015bc0  nop     dword ptr [rax+rax+00h]
0x140015bc5  cmp     ebx, 103h
0x140015bcb  jz      short loc_140015BE1
0x140015bcd  mov     dl, 2; PriorityBoost
0x140015bcf  mov     [rdi+30h], ebx
0x140015bd2  mov     rcx, rdi; Irp
0x140015bd5  call    cs:__imp_IofCompleteRequest
0x140015bdc  nop     dword ptr [rax+rax+00h]
0x140015be1  mov     eax, ebx
0x140015be3  mov     rbx, [rsp+28h+arg_0]
0x140015be8  add     rsp, 20h
0x140015bec  pop     rdi
0x140015bed  retn
```
