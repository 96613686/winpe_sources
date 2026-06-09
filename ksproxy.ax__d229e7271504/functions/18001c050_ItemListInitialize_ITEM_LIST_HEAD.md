# ItemListInitialize(_ITEM_LIST_HEAD *)

- ea: `0x18001c050`
- end: `0x18001c0a8`
- name: `?ItemListInitialize@@YAKPEAU_ITEM_LIST_HEAD@@@Z`
- size: `88`
- prototype: `DWORD __fastcall(struct _ITEM_LIST_HEAD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800137b8`

## callees

- `0x18001c050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001c093`
- `KERNEL32!CreateMutexW` at `0x18001c079`
- `KERNEL32!CreateMutexW` at `0x18001c079`

## pseudocode

```c
DWORD __fastcall ItemListInitialize(struct _ITEM_LIST_HEAD *a1)
{
  HANDLE MutexW; // rax

  a1->tail.bLink = &a1->head;
  a1->head.bLink = &a1->tail;
  a1->head.fLink = &a1->tail;
  a1->tail.fLink = &a1->head;
  a1->count = 0;
  MutexW = CreateMutexW(0, 0, 0);
  a1->mutex = MutexW;
  if ( MutexW )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x18001c050  push    rbx
0x18001c052  sub     rsp, 20h
0x18001c056  lea     rax, [rcx+10h]
0x18001c05a  mov     [rcx+18h], rcx
0x18001c05e  mov     [rcx+8], rax
0x18001c062  mov     rbx, rcx
0x18001c065  mov     [rcx], rax
0x18001c068  xor     r8d, r8d; lpName
0x18001c06b  mov     [rax], rcx
0x18001c06e  xor     edx, edx; bInitialOwner
0x18001c070  mov     dword ptr [rcx+20h], 0
0x18001c077  xor     ecx, ecx; lpMutexAttributes
0x18001c079  call    cs:__imp_CreateMutexW
0x18001c080  nop     dword ptr [rax+rax+00h]
0x18001c085  mov     [rbx+28h], rax
0x18001c089  test    rax, rax
0x18001c08c  jnz     short loc_18001C09F
0x18001c08e  add     rsp, 20h
0x18001c092  pop     rbx
0x18001c093  jmp     cs:__imp_GetLastError
0x18001c09f  xor     eax, eax
0x18001c0a1  add     rsp, 20h
0x18001c0a5  pop     rbx
0x18001c0a6  retn
```
