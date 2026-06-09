# PmVerifySnapshotData(_DISK_SNAPSHOT_DATA *,ulong,uchar)

- ea: `0x14001c20c`
- end: `0x14001c2b7`
- name: `?PmVerifySnapshotData@@YAEPEAU_DISK_SNAPSHOT_DATA@@KE@Z`
- size: `171`
- prototype: `char __fastcall(UCHAR *Buffer, unsigned int, char)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d878`
- `0x14000da9c`
- `0x14000dbd0`

## callees

- `0x14001c20c`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14001c260`
- `ntoskrnl!RtlComputeCrc32` at `0x14001c260`

## pseudocode

```c
char __fastcall PmVerifySnapshotData(UCHAR *Buffer, unsigned int a2, char a3)
{
  char v3; // bp
  ULONG v7; // r8d
  int v8; // ebx
  ULONG v9; // eax
  unsigned int v10; // edx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // eax

  v3 = 0;
  if ( a2 >= 0x70 && *(_QWORD *)Buffer == 0x5452415050414E53LL && *((_DWORD *)Buffer + 2) == 1 )
  {
    v7 = *((_DWORD *)Buffer + 3);
    if ( v7 <= a2 && *((_DWORD *)Buffer + 5) <= 3u )
    {
      if ( !a3
        || (v8 = *((_DWORD *)Buffer + 4),
            *((_DWORD *)Buffer + 4) = 0,
            v9 = RtlComputeCrc32(0, Buffer, v7),
            *((_DWORD *)Buffer + 4) = v8,
            v9 == v8) )
      {
        v10 = *((_DWORD *)Buffer + 25);
        if ( !v10 || (v11 = *((_DWORD *)Buffer + 24), v11 >= 0x70) && v11 < a2 && v10 <= a2 - v11 )
        {
          v12 = *((_DWORD *)Buffer + 27);
          if ( !v12 )
            return 1;
          v13 = *((_DWORD *)Buffer + 26);
          if ( v13 >= 0x70 && v13 < a2 && v12 <= a2 - v13 )
            return 1;
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14001c20c  push    rbx
0x14001c20e  push    rbp
0x14001c20f  push    rsi
0x14001c210  push    rdi
0x14001c211  sub     rsp, 28h
0x14001c215  xor     bpl, bpl
0x14001c218  mov     al, r8b
0x14001c21b  mov     esi, edx
0x14001c21d  mov     rdi, rcx
0x14001c220  cmp     edx, 70h ; 'p'
0x14001c223  jb      loc_14001C2AA
0x14001c229  mov     rcx, 5452415050414E53h
0x14001c233  cmp     [rdi], rcx
0x14001c236  jnz     short loc_14001C2AA
0x14001c238  cmp     dword ptr [rdi+8], 1
0x14001c23c  jnz     short loc_14001C2AA
0x14001c23e  mov     r8d, [rdi+0Ch]; Length
0x14001c242  cmp     r8d, edx
0x14001c245  ja      short loc_14001C2AA
0x14001c247  cmp     dword ptr [rdi+14h], 3
0x14001c24b  ja      short loc_14001C2AA
0x14001c24d  test    al, al
0x14001c24f  jz      short loc_14001C273
0x14001c251  mov     ebx, [rdi+10h]
0x14001c254  mov     rdx, rdi; Buffer
0x14001c257  xor     ecx, ecx; InitialCrc
0x14001c259  mov     dword ptr [rdi+10h], 0
0x14001c260  call    cs:__imp_RtlComputeCrc32
0x14001c267  nop     dword ptr [rax+rax+00h]
0x14001c26c  mov     [rdi+10h], ebx
0x14001c26f  cmp     eax, ebx
0x14001c271  jnz     short loc_14001C2AA
0x14001c273  mov     edx, [rdi+64h]
0x14001c276  test    edx, edx
0x14001c278  jz      short loc_14001C28E
0x14001c27a  mov     ecx, [rdi+60h]
0x14001c27d  cmp     ecx, 70h ; 'p'
0x14001c280  jb      short loc_14001C2AA
0x14001c282  cmp     ecx, esi
0x14001c284  jnb     short loc_14001C2AA
0x14001c286  mov     eax, esi
0x14001c288  sub     eax, ecx
0x14001c28a  cmp     edx, eax
0x14001c28c  ja      short loc_14001C2AA
0x14001c28e  mov     ecx, [rdi+6Ch]
0x14001c291  test    ecx, ecx
0x14001c293  jz      short loc_14001C2A7
0x14001c295  mov     eax, [rdi+68h]
0x14001c298  cmp     eax, 70h ; 'p'
0x14001c29b  jb      short loc_14001C2AA
0x14001c29d  cmp     eax, esi
0x14001c29f  jnb     short loc_14001C2AA
0x14001c2a1  sub     esi, eax
0x14001c2a3  cmp     ecx, esi
0x14001c2a5  ja      short loc_14001C2AA
0x14001c2a7  mov     bpl, 1
0x14001c2aa  mov     al, bpl
0x14001c2ad  add     rsp, 28h
0x14001c2b1  pop     rdi
0x14001c2b2  pop     rsi
0x14001c2b3  pop     rbp
0x14001c2b4  pop     rbx
0x14001c2b5  retn
```
