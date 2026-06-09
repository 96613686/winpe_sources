# DRMOS::OpenEventA(ulong,int,ushort const *)

- ea: `0x1800385a0`
- end: `0x1800385f1`
- name: `?OpenEventA@DRMOS@@YAPEAXKHPEBG@Z`
- size: `81`
- prototype: `void *(DRMOS *__hidden this, unsigned int, int, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001a09c`
- `0x18001d914`
- `0x18002b454`
- `0x180030cc0`
- `0x180031b5c`
- `0x180033398`

## callees

- `0x180001284`
- `0x1800379a4`
- `0x1800385a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800385d0`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800385d0`

## pseudocode

```c
HANDLE __fastcall DRMOS::OpenEventA(DRMOS *this, BOOL a2, DRMOS *a3, const unsigned __int16 *a4)
{
  HANDLE v5; // rbx
  LPCWSTR lpName; // [rsp+48h] [rbp+20h] BYREF

  v5 = 0;
  lpName = 0;
  if ( (int)DRMOS::AddPerUserPrefix(a3, (const unsigned __int16 *)&lpName, (unsigned __int16 **)a3) >= 0 )
    v5 = OpenEventW(0x1F0003u, a2, lpName);
  operator delete((void *)lpName);
  return v5;
}

```

## disassembly

```asm
0x1800385a0  mov     [rsp+arg_0], rbx
0x1800385a5  push    rdi
0x1800385a6  sub     rsp, 20h
0x1800385aa  mov     edi, edx
0x1800385ac  xor     ebx, ebx
0x1800385ae  lea     rdx, [rsp+28h+lpName]; unsigned __int16 *
0x1800385b3  mov     [rsp+28h+lpName], rbx
0x1800385b8  mov     rcx, r8; this
0x1800385bb  call    ?AddPerUserPrefix@DRMOS@@YAJPEBGPEAPEAG@Z; DRMOS::AddPerUserPrefix(ushort const *,ushort * *)
0x1800385c0  test    eax, eax
0x1800385c2  js      short loc_1800385D9
0x1800385c4  mov     r8, [rsp+28h+lpName]; lpName
0x1800385c9  mov     edx, edi; bInheritHandle
0x1800385cb  mov     ecx, 1F0003h; dwDesiredAccess
0x1800385d0  call    cs:__imp_OpenEventW
0x1800385d6  mov     rbx, rax
0x1800385d9  mov     rcx, [rsp+28h+lpName]; Block
0x1800385de  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800385e3  mov     rax, rbx
0x1800385e6  mov     rbx, [rsp+28h+arg_0]
0x1800385eb  add     rsp, 20h
0x1800385ef  pop     rdi
0x1800385f0  retn
```
