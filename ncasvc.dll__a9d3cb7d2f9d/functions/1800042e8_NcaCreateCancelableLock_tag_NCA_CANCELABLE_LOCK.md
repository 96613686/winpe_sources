# NcaCreateCancelableLock(_tag_NCA_CANCELABLE_LOCK *)

- ea: `0x1800042e8`
- end: `0x180004377`
- name: `?NcaCreateCancelableLock@@YAKPEAU_tag_NCA_CANCELABLE_LOCK@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(struct _tag_NCA_CANCELABLE_LOCK *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800026d0`

## callees

- `0x1800042e8`
- `0x180004380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004307`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004322`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000433d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004307`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004322`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000433d`

## pseudocode

```c
__int64 __fastcall NcaCreateCancelableLock(struct _tag_NCA_CANCELABLE_LOCK *a1)
{
  HANDLE EventW; // rax
  bool v3; // zf

  *(_OWORD *)a1 = 0;
  *((_OWORD *)a1 + 1) = 0;
  *(_QWORD *)a1 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)a1 + 1) = CreateEventW(0, 1, 1, 0);
  EventW = CreateEventW(0, 0, 1, 0);
  v3 = *(_QWORD *)a1 == 0;
  *((_QWORD *)a1 + 2) = EventW;
  if ( !v3 && *((_QWORD *)a1 + 1) && EventW )
    return 0;
  NcaDestroyCancelableLock(a1);
  return 14;
}

```

## disassembly

```asm
0x1800042e8  push    rbx
0x1800042ea  sub     rsp, 20h
0x1800042ee  xorps   xmm0, xmm0
0x1800042f1  xor     r9d, r9d; lpName
0x1800042f4  movups  xmmword ptr [rcx], xmm0
0x1800042f7  mov     rbx, rcx
0x1800042fa  xor     r8d, r8d; bInitialState
0x1800042fd  movups  xmmword ptr [rcx+10h], xmm0
0x180004301  lea     edx, [r9+1]; bManualReset
0x180004305  xor     ecx, ecx; lpEventAttributes
0x180004307  call    cs:__imp_CreateEventW
0x18000430e  nop     dword ptr [rax+rax+00h]
0x180004313  xor     r9d, r9d; lpName
0x180004316  xor     ecx, ecx; lpEventAttributes
0x180004318  mov     [rbx], rax
0x18000431b  lea     edx, [r9+1]; bManualReset
0x18000431f  mov     r8d, edx; bInitialState
0x180004322  call    cs:__imp_CreateEventW
0x180004329  nop     dword ptr [rax+rax+00h]
0x18000432e  xor     r9d, r9d; lpName
0x180004331  xor     edx, edx; bManualReset
0x180004333  xor     ecx, ecx; lpEventAttributes
0x180004335  mov     [rbx+8], rax
0x180004339  lea     r8d, [r9+1]; bInitialState
0x18000433d  call    cs:__imp_CreateEventW
0x180004344  nop     dword ptr [rax+rax+00h]
0x180004349  cmp     qword ptr [rbx], 0
0x18000434d  mov     [rbx+10h], rax
0x180004351  jz      short loc_180004363
0x180004353  cmp     qword ptr [rbx+8], 0
0x180004358  jz      short loc_180004363
0x18000435a  test    rax, rax
0x18000435d  jz      short loc_180004363
0x18000435f  xor     eax, eax
0x180004361  jmp     short loc_180004370
0x180004363  mov     rcx, rbx; struct _tag_NCA_CANCELABLE_LOCK *
0x180004366  call    ?NcaDestroyCancelableLock@@YAXPEAU_tag_NCA_CANCELABLE_LOCK@@@Z; NcaDestroyCancelableLock(_tag_NCA_CANCELABLE_LOCK *)
0x18000436b  mov     eax, 0Eh
0x180004370  add     rsp, 20h
0x180004374  pop     rbx
0x180004375  retn
```
