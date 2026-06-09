# SC_DISK::GetFruIdDescPost(_STORAGE_FRU_ID_DESCRIPTOR *)

- ea: `0x14000ec70`
- end: `0x14000ece6`
- name: `?GetFruIdDescPost@SC_DISK@@AEAAJPEAU_STORAGE_FRU_ID_DESCRIPTOR@@@Z`
- size: `118`
- prototype: `__int64 __fastcall(SC_DISK *__hidden this, struct _STORAGE_FRU_ID_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000ecf0`

## callees

- `0x140004878`
- `0x14000a530`
- `0x14000ec70`
- `0x140011140`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ecc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ecc7`

## pseudocode

```c
__int64 __fastcall SC_DISK::GetFruIdDescPost(
        struct _UNICODE_STRING *this,
        struct _STORAGE_FRU_ID_DESCRIPTOR *a2,
        __int64 a3)
{
  char *v5; // rax
  char *v6; // rdi
  unsigned int v7; // ebx

  v5 = (char *)SC_ENV::Allocate((unsigned int)(*((_DWORD *)a2 + 2) + 1), (__int64)a2, a3, 0);
  v6 = v5;
  if ( v5 )
  {
    memmove(v5, (char *)a2 + 12, *((unsigned int *)a2 + 2));
    v7 = ScAnsiToUnicodeString(v6, this + 18);
    ExFreePoolWithTag(v6, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v7;
}

```

## disassembly

```asm
0x14000ec70  mov     [rsp+arg_0], rbx
0x14000ec75  mov     [rsp+arg_8], rsi
0x14000ec7a  push    rdi
0x14000ec7b  sub     rsp, 20h
0x14000ec7f  mov     rsi, rcx
0x14000ec82  xor     r9d, r9d; unsigned int
0x14000ec85  mov     ecx, [rdx+8]
0x14000ec88  mov     rbx, rdx
0x14000ec8b  inc     ecx; unsigned __int64
0x14000ec8d  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14000ec92  mov     rdi, rax
0x14000ec95  test    rax, rax
0x14000ec98  jnz     short loc_14000ECA1
0x14000ec9a  mov     ebx, 0C000009Ah
0x14000ec9f  jmp     short loc_14000ECD3
0x14000eca1  mov     r8d, [rbx+8]; Size
0x14000eca5  lea     rdx, [rbx+0Ch]; Src
0x14000eca9  mov     rcx, rdi; void *
0x14000ecac  call    memmove
0x14000ecb1  lea     rdx, [rsi+120h]; struct _UNICODE_STRING *
0x14000ecb8  mov     rcx, rdi; SourceString
0x14000ecbb  call    ?ScAnsiToUnicodeString@@YAJPEADPEAU_UNICODE_STRING@@@Z; ScAnsiToUnicodeString(char *,_UNICODE_STRING *)
0x14000ecc0  mov     ebx, eax
0x14000ecc2  xor     edx, edx; Tag
0x14000ecc4  mov     rcx, rdi; P
0x14000ecc7  call    cs:__imp_ExFreePoolWithTag
0x14000ecce  nop     dword ptr [rax+rax+00h]
0x14000ecd3  mov     rsi, [rsp+28h+arg_8]
0x14000ecd8  mov     eax, ebx
0x14000ecda  mov     rbx, [rsp+28h+arg_0]
0x14000ecdf  add     rsp, 20h
0x14000ece3  pop     rdi
0x14000ece4  retn
```
