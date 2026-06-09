# mp3MainDataRead(CBitStream &,CBitStream &,MP3SI const &,MPEG_INFO const &)

- ea: `0x180006574`
- end: `0x180006622`
- name: `?mp3MainDataRead@@YA_NAEAVCBitStream@@0AEBUMP3SI@@AEBUMPEG_INFO@@@Z`
- size: `174`
- prototype: `char __fastcall(struct CBitStream *, struct CBitStream *this, const struct MP3SI *, const struct MPEG_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000625c`

## callees

- `0x180006544`
- `0x180006574`
- `0x180006700`
- `0x180006730`

## pseudocode

```c
char __fastcall mp3MainDataRead(
        struct CBitStream *a1,
        struct CBitStream *this,
        const struct MP3SI *a3,
        const struct MPEG_INFO *a4)
{
  struct CBitStream *v6; // r10
  int v7; // ebx
  char v8; // al
  int v9; // ebx
  int v10; // esi
  int v11; // eax
  CBitStream *v12; // rcx

  v6 = a1;
  v7 = (*((_DWORD *)a4 + 2) - *((_DWORD *)a4 + 5)) / 8;
  v8 = *((_BYTE *)a4 + 32);
  if ( *(_DWORD *)a4 == 1 )
    v9 = v7 - (v8 != 0 ? 17 : 9);
  else
    v9 = v7 - (v8 != 0 ? 32 : 17);
  v10 = *((_DWORD *)this + 6);
  v11 = (*((_DWORD *)this + 5) - v10) / 8;
  if ( v11 < v9 )
    CBitStream::Ff(this, 8 * (v9 - v11));
  if ( (unsigned int)CBitStream::Fill(this, v6, v9) != v9 || v10 >> 3 < *(_DWORD *)a3 )
    return 0;
  CBitStream::Ff(this, *((_DWORD *)this + 6));
  CBitStream::Rewind(v12, 8 * (v9 + *(_DWORD *)a3));
  return 1;
}

```

## disassembly

```asm
0x180006574  push    rbx
0x180006576  push    rsi
0x180006577  push    rdi
0x180006578  push    r14
0x18000657a  sub     rsp, 28h
0x18000657e  mov     eax, [r9+8]
0x180006582  mov     rdi, rdx
0x180006585  sub     eax, [r9+14h]
0x180006589  mov     r14, r8
0x18000658c  cdq
0x18000658d  mov     r8d, 8
0x180006593  idiv    r8d
0x180006596  cmp     dword ptr [r9], 1
0x18000659a  mov     r10, rcx
0x18000659d  mov     ebx, eax
0x18000659f  mov     al, [r9+20h]
0x1800065a3  jz      short loc_1800065FF
0x1800065a5  neg     al
0x1800065a7  sbb     eax, eax
0x1800065a9  and     eax, 0Fh
0x1800065ac  add     eax, 11h
0x1800065af  sub     ebx, eax
0x1800065b1  mov     eax, [rdi+14h]
0x1800065b4  mov     esi, [rdi+18h]
0x1800065b7  sub     eax, esi
0x1800065b9  cdq
0x1800065ba  idiv    r8d
0x1800065bd  cmp     eax, ebx
0x1800065bf  jl      short loc_180006611
0x1800065c1  mov     r8d, ebx; int
0x1800065c4  mov     rdx, r10; struct CBitStream *
0x1800065c7  mov     rcx, rdi; this
0x1800065ca  call    ?Fill@CBitStream@@QEAAHAEAV1@H@Z; CBitStream::Fill(CBitStream &,int)
0x1800065cf  cmp     eax, ebx
0x1800065d1  jnz     short loc_18000660D
0x1800065d3  sar     esi, 3
0x1800065d6  cmp     esi, [r14]
0x1800065d9  jl      short loc_18000660D
0x1800065db  mov     edx, [rdi+18h]; int
0x1800065de  mov     rcx, rdi; this
0x1800065e1  call    ?Ff@CBitStream@@QEAA_NH@Z; CBitStream::Ff(int)
0x1800065e6  mov     edx, [r14]
0x1800065e9  add     edx, ebx
0x1800065eb  shl     edx, 3; int
0x1800065ee  call    ?Rewind@CBitStream@@QEAA_NH@Z; CBitStream::Rewind(int)
0x1800065f3  mov     al, 1
0x1800065f5  add     rsp, 28h
0x1800065f9  pop     r14
0x1800065fb  pop     rdi
0x1800065fc  pop     rsi
0x1800065fd  pop     rbx
0x1800065fe  retn
0x1800065ff  neg     al
0x180006601  sbb     ecx, ecx
0x180006603  and     ecx, r8d
0x180006606  add     ecx, 9
0x180006609  sub     ebx, ecx
0x18000660b  jmp     short loc_1800065B1
0x18000660d  xor     al, al
0x18000660f  jmp     short loc_1800065F5
0x180006611  mov     edx, ebx
0x180006613  mov     rcx, rdi; this
0x180006616  sub     edx, eax
0x180006618  shl     edx, 3; int
0x18000661b  call    ?Ff@CBitStream@@QEAA_NH@Z; CBitStream::Ff(int)
0x180006620  jmp     short loc_1800065C1
```
