# edit_pathname

- ea: `0x140004bd4`
- end: `0x140004d05`
- name: `edit_pathname`
- size: `305`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x14000422c`
- `0x14000583c`
- `0x140006ea4`

## callees

- `0x140004bd4`
- `0x1400054bc`

## import_xrefs

- `archiveint!archive_entry_pathname` at `0x140004bea`
- `archiveint!archive_entry_pathname` at `0x140004bea`
- `archiveint!archive_entry_hardlink` at `0x140004bf6`
- `archiveint!archive_entry_hardlink` at `0x140004bf6`
- `archiveint!archive_entry_copy_hardlink` at `0x140004cf0`
- `archiveint!archive_entry_copy_hardlink` at `0x140004cf0`
- `archiveint!archive_entry_copy_pathname` at `0x140004cdf`
- `archiveint!archive_entry_copy_pathname` at `0x140004cdf`

## pseudocode

```c
__int64 __fastcall edit_pathname(__int64 a1, __int64 a2)
{
  __int64 v4; // rbp
  __int64 v5; // rax
  int v6; // r8d
  char *v7; // r15
  char *v8; // rdi
  const char *v9; // rbx
  int v10; // ecx
  char v11; // al
  char v12; // al
  char v13; // al
  char v14; // al
  const char *v15; // rax

  v4 = archive_entry_pathname(a2);
  v5 = archive_entry_hardlink(a2);
  v6 = *(_DWORD *)(a1 + 48);
  v7 = (char *)v5;
  v8 = (char *)v5;
  v9 = (const char *)v4;
  if ( v6 > 0 )
  {
    v10 = *(_DWORD *)(a1 + 48);
    while ( 1 )
    {
      v11 = *v9;
      if ( !*v9 )
        return 1;
      ++v9;
      if ( v11 == 47 || v11 == 92 )
        --v10;
      if ( v10 <= 0 )
      {
        while ( 1 )
        {
          v12 = *v9;
          if ( !*v9 )
            return 1;
          if ( v12 != 47 && v12 != 92 )
          {
            if ( !v9 )
              return 1;
            if ( v7 )
            {
              while ( 1 )
              {
                v13 = *v8;
                if ( !*v8 )
                  return 1;
                ++v8;
                if ( v13 == 47 || v13 == 92 )
                  --v6;
                if ( v6 <= 0 )
                {
                  while ( 1 )
                  {
                    v14 = *v8;
                    if ( !*v8 )
                      return 1;
                    if ( v14 != 47 && v14 != 92 )
                    {
                      if ( !v8 )
                        return 1;
                      goto LABEL_28;
                    }
                    ++v8;
                  }
                }
              }
            }
            goto LABEL_28;
          }
          ++v9;
        }
      }
    }
  }
LABEL_28:
  if ( (*(_BYTE *)(a1 + 36) & 2) != 0 )
  {
    if ( *v9 == 47 )
    {
      while ( v9[1] == 47 )
        ++v9;
    }
  }
  else
  {
    v15 = (const char *)strip_absolute_path(a1, v9);
    v9 = ".";
    if ( *v15 )
      v9 = v15;
    if ( v8 )
    {
      v8 = (char *)strip_absolute_path(a1, v8);
      if ( !*v8 )
        return 1;
    }
  }
  if ( v9 != (const char *)v4 )
    archive_entry_copy_pathname(a2, v9);
  if ( v8 != v7 )
    archive_entry_copy_hardlink(a2, v8);
  return 0;
}

```

## disassembly

```asm
0x140004bd4  push    rbx
0x140004bd6  push    rbp
0x140004bd7  push    rsi
0x140004bd8  push    rdi
0x140004bd9  push    r14
0x140004bdb  push    r15
0x140004bdd  sub     rsp, 28h
0x140004be1  mov     r14, rcx
0x140004be4  mov     rsi, rdx
0x140004be7  mov     rcx, rdx
0x140004bea  call    cs:__imp_archive_entry_pathname
0x140004bf0  mov     rcx, rsi
0x140004bf3  mov     rbp, rax
0x140004bf6  call    cs:__imp_archive_entry_hardlink
0x140004bfc  mov     r8d, [r14+30h]
0x140004c00  mov     dl, 2Fh ; '/'
0x140004c02  mov     r15, rax
0x140004c05  mov     rdi, rax
0x140004c08  mov     rbx, rbp
0x140004c0b  test    r8d, r8d
0x140004c0e  jle     short loc_140004C87
0x140004c10  mov     ecx, r8d
0x140004c13  mov     r9b, 5Ch ; '\'
0x140004c16  mov     al, [rbx]
0x140004c18  test    al, al
0x140004c1a  jz      loc_140004CBF
0x140004c20  inc     rbx
0x140004c23  cmp     al, dl
0x140004c25  jz      short loc_140004C2C
0x140004c27  cmp     al, r9b
0x140004c2a  jnz     short loc_140004C2E
0x140004c2c  dec     ecx
0x140004c2e  test    ecx, ecx
0x140004c30  jg      short loc_140004C16
0x140004c32  jmp     short loc_140004C40
0x140004c34  cmp     al, dl
0x140004c36  jz      short loc_140004C3D
0x140004c38  cmp     al, r9b
0x140004c3b  jnz     short loc_140004C48
0x140004c3d  inc     rbx
0x140004c40  mov     al, [rbx]
0x140004c42  test    al, al
0x140004c44  jnz     short loc_140004C34
0x140004c46  jmp     short loc_140004CBF
0x140004c48  test    rbx, rbx
0x140004c4b  jz      short loc_140004CBF
0x140004c4d  test    r15, r15
0x140004c50  jz      short loc_140004C87
0x140004c52  mov     al, [rdi]
0x140004c54  test    al, al
0x140004c56  jz      short loc_140004CBF
0x140004c58  inc     rdi
0x140004c5b  cmp     al, dl
0x140004c5d  jz      short loc_140004C64
0x140004c5f  cmp     al, r9b
0x140004c62  jnz     short loc_140004C67
0x140004c64  dec     r8d
0x140004c67  test    r8d, r8d
0x140004c6a  jg      short loc_140004C52
0x140004c6c  jmp     short loc_140004C7A
0x140004c6e  cmp     al, dl
0x140004c70  jz      short loc_140004C77
0x140004c72  cmp     al, r9b
0x140004c75  jnz     short loc_140004C82
0x140004c77  inc     rdi
0x140004c7a  mov     al, [rdi]
0x140004c7c  test    al, al
0x140004c7e  jnz     short loc_140004C6E
0x140004c80  jmp     short loc_140004CBF
0x140004c82  test    rdi, rdi
0x140004c85  jz      short loc_140004CBF
0x140004c87  test    byte ptr [r14+24h], 2
0x140004c8c  jnz     short loc_140004CC6
0x140004c8e  mov     rdx, rbx
0x140004c91  mov     rcx, r14
0x140004c94  call    strip_absolute_path
0x140004c99  lea     rbx, asc_14000BB18; "."
0x140004ca0  cmp     byte ptr [rax], 0
0x140004ca3  cmovnz  rbx, rax
0x140004ca7  test    rdi, rdi
0x140004caa  jz      short loc_140004CD4
0x140004cac  mov     rdx, rdi
0x140004caf  mov     rcx, r14
0x140004cb2  call    strip_absolute_path
0x140004cb7  mov     rdi, rax
0x140004cba  cmp     byte ptr [rax], 0
0x140004cbd  jnz     short loc_140004CD4
0x140004cbf  mov     eax, 1
0x140004cc4  jmp     short loc_140004CF8
0x140004cc6  cmp     [rbx], dl
0x140004cc8  jnz     short loc_140004CD4
0x140004cca  cmp     [rbx+1], dl
0x140004ccd  jnz     short loc_140004CD4
0x140004ccf  inc     rbx
0x140004cd2  jmp     short loc_140004CCA
0x140004cd4  cmp     rbx, rbp
0x140004cd7  jz      short loc_140004CE5
0x140004cd9  mov     rdx, rbx
0x140004cdc  mov     rcx, rsi
0x140004cdf  call    cs:__imp_archive_entry_copy_pathname
0x140004ce5  cmp     rdi, r15
0x140004ce8  jz      short loc_140004CF6
0x140004cea  mov     rdx, rdi
0x140004ced  mov     rcx, rsi
0x140004cf0  call    cs:__imp_archive_entry_copy_hardlink
0x140004cf6  xor     eax, eax
0x140004cf8  add     rsp, 28h
0x140004cfc  pop     r15
0x140004cfe  pop     r14
0x140004d00  pop     rdi
0x140004d01  pop     rsi
0x140004d02  pop     rbp
0x140004d03  pop     rbx
0x140004d04  retn
```
