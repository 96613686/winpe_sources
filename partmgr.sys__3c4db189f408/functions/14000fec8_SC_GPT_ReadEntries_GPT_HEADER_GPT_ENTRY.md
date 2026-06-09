# SC_GPT::ReadEntries(GPT_HEADER *,GPT_ENTRY * *)

- ea: `0x14000fec8`
- end: `0x14000ff52`
- name: `?ReadEntries@SC_GPT@@AEAAJPEAVGPT_HEADER@@PEAPEAVGPT_ENTRY@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(SC_GPT *__hidden this, struct GPT_HEADER *, struct GPT_ENTRY **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400100ac`

## callees

- `0x14000a530`
- `0x14000fec8`
- `0x14000ff58`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ff39`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ff39`

## pseudocode

```c
__int64 __fastcall SC_GPT::ReadEntries(SC_GPT *this, struct GPT_HEADER *a2, struct GPT_ENTRY **a3)
{
  __int64 v3; // rax
  int v6; // ecx
  struct GPT_ENTRY *v8; // rax
  struct GPT_ENTRY *v9; // rdi
  int Entries; // ebx

  v3 = *(_QWORD *)this;
  v6 = *((_DWORD *)a2 + 20) * *((_DWORD *)a2 + 21);
  *a3 = 0;
  v8 = (struct GPT_ENTRY *)SC_ENV::Allocate(
                             -*(_DWORD *)(v3 + 236) & (unsigned int)(*(_DWORD *)(v3 + 236) + v6 - 1),
                             (unsigned int)a2,
                             (unsigned __int8)a3,
                             1u);
  v9 = v8;
  if ( v8 )
  {
    Entries = SC_GPT::ReadEntries(this, a2, v8);
    if ( Entries < 0 )
      ExFreePoolWithTag(v9, 0);
    else
      *a3 = v9;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)Entries;
}

```

## disassembly

```asm
0x14000fec8  push    rbx
0x14000feca  push    rsi
0x14000fecb  push    rdi
0x14000fecc  push    r14
0x14000fece  sub     rsp, 28h
0x14000fed2  mov     rax, [rcx]
0x14000fed5  mov     r14, rcx
0x14000fed8  mov     ecx, [rdx+54h]
0x14000fedb  mov     rsi, r8
0x14000fede  imul    ecx, [rdx+50h]
0x14000fee2  mov     rbx, rdx
0x14000fee5  mov     qword ptr [r8], 0
0x14000feec  mov     r9d, [rax+0ECh]
0x14000fef3  dec     ecx
0x14000fef5  add     ecx, r9d
0x14000fef8  neg     r9d
0x14000fefb  mov     eax, r9d
0x14000fefe  mov     r9d, 1; unsigned int
0x14000ff04  and     rcx, rax; unsigned __int64
0x14000ff07  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14000ff0c  mov     rdi, rax
0x14000ff0f  test    rax, rax
0x14000ff12  jnz     short loc_14000FF1B
0x14000ff14  mov     ebx, 0C000009Ah
0x14000ff19  jmp     short loc_14000FF45
0x14000ff1b  mov     r8, rdi; struct GPT_ENTRY *
0x14000ff1e  mov     rdx, rbx; struct GPT_HEADER *
0x14000ff21  mov     rcx, r14; this
0x14000ff24  call    ?ReadEntries@SC_GPT@@AEAAJPEAVGPT_HEADER@@PEAVGPT_ENTRY@@@Z; SC_GPT::ReadEntries(GPT_HEADER *,GPT_ENTRY *)
0x14000ff29  mov     ebx, eax
0x14000ff2b  test    eax, eax
0x14000ff2d  js      short loc_14000FF34
0x14000ff2f  mov     [rsi], rdi
0x14000ff32  jmp     short loc_14000FF45
0x14000ff34  xor     edx, edx; Tag
0x14000ff36  mov     rcx, rdi; P
0x14000ff39  call    cs:__imp_ExFreePoolWithTag
0x14000ff40  nop     dword ptr [rax+rax+00h]
0x14000ff45  mov     eax, ebx
0x14000ff47  add     rsp, 28h
0x14000ff4b  pop     r14
0x14000ff4d  pop     rdi
0x14000ff4e  pop     rsi
0x14000ff4f  pop     rbx
0x14000ff50  retn
```
