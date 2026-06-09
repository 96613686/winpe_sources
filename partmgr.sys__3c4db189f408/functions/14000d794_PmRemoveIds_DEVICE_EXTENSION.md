# PmRemoveIds(_DEVICE_EXTENSION *)

- ea: `0x14000d794`
- end: `0x14000d86f`
- name: `?PmRemoveIds@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140005b2c`
- `0x14000743c`

## callees

- `0x14000d794`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000d80f`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000d847`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000d80f`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000d847`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d7d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d7d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d7b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d7b5`

## pseudocode

```c
__int64 __fastcall PmRemoveIds(struct _DEVICE_EXTENSION *a1)
{
  char *DeviceExtension; // rsi
  KIRQL v3; // al
  _QWORD *v4; // rax
  _QWORD *v5; // rdx
  __int64 v6; // rcx
  _QWORD **v7; // rbx
  _QWORD *v8; // rdx
  _QWORD *v9; // rax

  DeviceExtension = (char *)PmControlObject->DeviceExtension;
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
  *((_DWORD *)a1 + 129) &= ~0x800u;
  KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v3);
  v4 = (_QWORD *)((char *)a1 + 616);
  v5 = (_QWORD *)*((_QWORD *)a1 + 77);
  if ( v5 != (_QWORD *)((char *)a1 + 616) )
  {
    if ( (_QWORD *)v5[1] != v4 || (v6 = *v5, *(_QWORD **)(*v5 + 8LL) != v5) )
LABEL_10:
      __fastfail(3u);
    *v4 = v6;
    *(_QWORD *)(v6 + 8) = v4;
    RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(DeviceExtension + 200), v5);
  }
  v7 = (_QWORD **)((char *)a1 + 632);
  while ( 1 )
  {
    v8 = *v7;
    if ( *v7 == v7 )
      return 0;
    if ( (_QWORD **)v8[1] != v7 )
      goto LABEL_10;
    v9 = (_QWORD *)*v8;
    if ( *(_QWORD **)(*v8 + 8LL) != v8 )
      goto LABEL_10;
    *v7 = v9;
    v9[1] = v7;
    RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(DeviceExtension + 304), v8);
  }
}

```

## disassembly

```asm
0x14000d794  mov     [rsp+arg_0], rbx
0x14000d799  mov     [rsp+arg_8], rsi
0x14000d79e  push    rdi
0x14000d79f  sub     rsp, 20h
0x14000d7a3  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x14000d7aa  mov     rdi, rcx
0x14000d7ad  add     rcx, 70h ; 'p'; SpinLock
0x14000d7b1  mov     rsi, [rax+40h]
0x14000d7b5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d7bc  nop     dword ptr [rax+rax+00h]
0x14000d7c1  mov     edx, [rdi+204h]
0x14000d7c7  lea     rcx, [rdi+70h]; SpinLock
0x14000d7cb  btr     edx, 0Bh
0x14000d7cf  mov     [rdi+204h], edx
0x14000d7d5  mov     dl, al; NewIrql
0x14000d7d7  call    cs:__imp_KeReleaseSpinLock
0x14000d7de  nop     dword ptr [rax+rax+00h]
0x14000d7e3  lea     rax, [rdi+268h]
0x14000d7ea  mov     rdx, [rax]; Buffer
0x14000d7ed  cmp     rdx, rax
0x14000d7f0  jz      short loc_14000D81B
0x14000d7f2  cmp     [rdx+8], rax
0x14000d7f6  jnz     short loc_14000D855
0x14000d7f8  mov     rcx, [rdx]
0x14000d7fb  cmp     [rcx+8], rdx
0x14000d7ff  jnz     short loc_14000D855
0x14000d801  mov     [rax], rcx
0x14000d804  mov     [rcx+8], rax
0x14000d808  lea     rcx, [rsi+0C8h]; Table
0x14000d80f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14000d816  nop     dword ptr [rax+rax+00h]
0x14000d81b  lea     rbx, [rdi+278h]
0x14000d822  mov     rdx, [rbx]; Buffer
0x14000d825  cmp     rdx, rbx
0x14000d828  jz      short loc_14000D85C
0x14000d82a  cmp     [rdx+8], rbx
0x14000d82e  jnz     short loc_14000D855
0x14000d830  mov     rax, [rdx]
0x14000d833  cmp     [rax+8], rdx
0x14000d837  jnz     short loc_14000D855
0x14000d839  mov     [rbx], rax
0x14000d83c  lea     rcx, [rsi+130h]; Table
0x14000d843  mov     [rax+8], rbx
0x14000d847  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14000d84e  nop     dword ptr [rax+rax+00h]
0x14000d853  jmp     short loc_14000D822
0x14000d855  mov     ecx, 3
0x14000d85a  int     29h; Win8: RtlFailFast(ecx)
0x14000d85c  mov     rbx, [rsp+28h+arg_0]
0x14000d861  xor     eax, eax
0x14000d863  mov     rsi, [rsp+28h+arg_8]
0x14000d868  add     rsp, 20h
0x14000d86c  pop     rdi
0x14000d86d  retn
```
