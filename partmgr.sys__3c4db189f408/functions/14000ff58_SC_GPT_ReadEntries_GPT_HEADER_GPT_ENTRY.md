# SC_GPT::ReadEntries(GPT_HEADER *,GPT_ENTRY *)

- ea: `0x14000ff58`
- end: `0x14000ffc3`
- name: `?ReadEntries@SC_GPT@@AEAAJPEAVGPT_HEADER@@PEAVGPT_ENTRY@@@Z`
- size: `107`
- prototype: `int(SC_GPT *__hidden this, struct GPT_HEADER *, struct GPT_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000fec8`

## callees

- `0x140005950`
- `0x14000a93d`
- `0x14000ff58`

## pseudocode

```c
__int64 __fastcall SC_GPT::ReadEntries(SC_DISK **this, struct GPT_HEADER *a2, struct GPT_ENTRY *a3)
{
  ULONG v4; // esi
  int Sectors; // ebx

  v4 = *((_DWORD *)a2 + 20) * *((_DWORD *)a2 + 21);
  Sectors = SC_DISK::ReadSectors(
              *this,
              (-*((_DWORD *)*this + 59) & (v4 + *((_DWORD *)*this + 59) - 1)) >> *((_DWORD *)*this + 60),
              *((_QWORD *)a2 + 9),
              a3);
  if ( Sectors >= 0 && RtlComputeCrc32_0(0, (PUCHAR)a3, v4) != *((_DWORD *)a2 + 22) )
    return (unsigned int)-1073741774;
  return (unsigned int)Sectors;
}

```

## disassembly

```asm
0x14000ff58  push    rbx
0x14000ff5a  push    rbp
0x14000ff5b  push    rsi
0x14000ff5c  push    rdi
0x14000ff5d  sub     rsp, 28h
0x14000ff61  mov     esi, [rdx+54h]
0x14000ff64  mov     rdi, rdx
0x14000ff67  imul    esi, [rdx+50h]
0x14000ff6b  mov     rbp, r8
0x14000ff6e  mov     r10, [rcx]
0x14000ff71  mov     r9, r8; void *
0x14000ff74  mov     r8, [rdi+48h]; unsigned __int64
0x14000ff78  mov     eax, [r10+0ECh]
0x14000ff7f  mov     ecx, [r10+0F0h]
0x14000ff86  lea     edx, [rax-1]
0x14000ff89  neg     eax
0x14000ff8b  add     edx, esi
0x14000ff8d  and     edx, eax
0x14000ff8f  shr     edx, cl; unsigned int
0x14000ff91  mov     rcx, r10; this
0x14000ff94  call    ?ReadSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::ReadSectors(ulong,unsigned __int64,void *)
0x14000ff99  mov     ebx, eax
0x14000ff9b  test    eax, eax
0x14000ff9d  js      short loc_14000FFB7
0x14000ff9f  mov     r8d, esi; Length
0x14000ffa2  mov     rdx, rbp; Buffer
0x14000ffa5  xor     ecx, ecx; InitialCrc
0x14000ffa7  call    RtlComputeCrc32_0
0x14000ffac  cmp     eax, [rdi+58h]
0x14000ffaf  mov     ecx, 0C0000032h
0x14000ffb4  cmovnz  ebx, ecx
0x14000ffb7  mov     eax, ebx
0x14000ffb9  add     rsp, 28h
0x14000ffbd  pop     rdi
0x14000ffbe  pop     rsi
0x14000ffbf  pop     rbp
0x14000ffc0  pop     rbx
0x14000ffc1  retn
```
