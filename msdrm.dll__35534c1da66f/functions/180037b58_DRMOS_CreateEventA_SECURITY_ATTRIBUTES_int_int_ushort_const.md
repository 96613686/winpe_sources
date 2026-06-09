# DRMOS::CreateEventA(_SECURITY_ATTRIBUTES *,int,int,ushort const *)

- ea: `0x180037b58`
- end: `0x180037bb8`
- name: `?CreateEventA@DRMOS@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z`
- size: `96`
- prototype: `void *__fastcall(LPSECURITY_ATTRIBUTES lpEventAttributes, struct _SECURITY_ATTRIBUTES *, int, int, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800098e8`
- `0x180018ea0`
- `0x180020348`
- `0x18002325c`
- `0x18002b454`

## callees

- `0x180001284`
- `0x1800379a4`
- `0x180037b58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037b92`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180037b92`

## pseudocode

```c
HANDLE __fastcall DRMOS::CreateEventA(
        LPSECURITY_ATTRIBUTES lpEventAttributes,
        struct _SECURITY_ATTRIBUTES *a2,
        unsigned __int16 **a3,
        DRMOS *a4)
{
  HANDLE EventW; // rbx
  BOOL v6; // edi
  LPCWSTR lpName[3]; // [rsp+20h] [rbp-18h] BYREF

  EventW = 0;
  lpName[0] = 0;
  v6 = (int)a3;
  if ( (int)DRMOS::AddPerUserPrefix(a4, (const unsigned __int16 *)lpName, a3) >= 0 )
    EventW = CreateEventW(lpEventAttributes, 1, v6, lpName[0]);
  operator delete((void *)lpName[0]);
  return EventW;
}

```

## disassembly

```asm
0x180037b58  mov     rax, rsp
0x180037b5b  mov     [rax+8], rbx
0x180037b5f  mov     [rax+10h], rsi
0x180037b63  push    rdi
0x180037b64  sub     rsp, 30h
0x180037b68  mov     rsi, rcx
0x180037b6b  lea     rdx, [rax-18h]; unsigned __int16 *
0x180037b6f  xor     ebx, ebx
0x180037b71  mov     rcx, r9; this
0x180037b74  mov     [rax-18h], rbx
0x180037b78  mov     edi, r8d
0x180037b7b  call    ?AddPerUserPrefix@DRMOS@@YAJPEBGPEAPEAG@Z; DRMOS::AddPerUserPrefix(ushort const *,ushort * *)
0x180037b80  test    eax, eax
0x180037b82  js      short loc_180037B9B
0x180037b84  mov     r9, [rsp+38h+lpName]; lpName
0x180037b89  lea     edx, [rbx+1]; bManualReset
0x180037b8c  mov     r8d, edi; bInitialState
0x180037b8f  mov     rcx, rsi; lpEventAttributes
0x180037b92  call    cs:__imp_CreateEventW
0x180037b98  mov     rbx, rax
0x180037b9b  mov     rcx, [rsp+38h+lpName]; Block
0x180037ba0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180037ba5  mov     rsi, [rsp+38h+arg_8]
0x180037baa  mov     rax, rbx
0x180037bad  mov     rbx, [rsp+38h+arg_0]
0x180037bb2  add     rsp, 30h
0x180037bb6  pop     rdi
0x180037bb7  retn
```
