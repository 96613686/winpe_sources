# FatIsDirectoryEmpty

- ea: `0x140031b84`
- end: `0x140031d6b`
- name: `FatIsDirectoryEmpty`
- size: `487`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140024bd4`
- `0x14003b698`

## callees

- `0x14000c230`
- `0x14000cba0`
- `0x140024584`
- `0x140031b84`
- `0x140044518`

## import_xrefs

- `ntoskrnl!CcUnpinData` at `0x140031bf5`
- `ntoskrnl!CcUnpinData` at `0x140031c26`
- `ntoskrnl!CcUnpinData` at `0x140031d35`
- `ntoskrnl!CcUnpinData` at `0x14005d240`
- `ntoskrnl!CcUnpinData` at `0x140031bf5`
- `ntoskrnl!CcUnpinData` at `0x140031c26`
- `ntoskrnl!CcUnpinData` at `0x140031d35`
- `ntoskrnl!CcUnpinData` at `0x14005d240`

## pseudocode

```c
char __fastcall FatIsDirectoryEmpty(__int64 a1, __int64 a2, __int64 a3)
{
  char v5; // di
  int v6; // esi
  unsigned int v7; // ebx
  __int64 v8; // rcx
  PVOID Bcb; // [rsp+40h] [rbp-58h] BYREF
  __int64 v11; // [rsp+48h] [rbp-50h] BYREF
  PVOID v12; // [rsp+50h] [rbp-48h] BYREF
  void *Buf2[2]; // [rsp+58h] [rbp-40h] BYREF
  char v14; // [rsp+68h] [rbp-30h] BYREF

  v12 = 0;
  v5 = 0;
  v6 = 0;
  LODWORD(v11) = 0;
  v7 = *(_WORD *)a2 != 1284 ? 0x40 : 0;
  Bcb = 0;
  while ( 1 )
  {
    if ( v7 < *(_DWORD *)(a2 + 24) )
    {
      if ( (v7 & 0xFFF) == 0 || !Bcb )
      {
        if ( Bcb )
        {
          CcUnpinData(Bcb);
          Bcb = 0;
        }
        FatReadDirectoryFile(a1, a2, v7 & 0xFFFFF000, 0x1000u, 0, &Bcb, &v12, &v11);
        v12 = (char *)v12 + (v7 & 0xFFF);
        v6 = v11;
      }
    }
    else
    {
      v6 = -1073741807;
      LODWORD(v11) = -1073741807;
      if ( Bcb )
      {
        CcUnpinData(Bcb);
        Bcb = 0;
      }
    }
    if ( v6 == -1073741807 || !*(_BYTE *)v12 )
      break;
    if ( *(_BYTE *)v12 != 0xE5 && *((_BYTE *)v12 + 11) != 15 )
    {
      v8 = *(unsigned int *)(*(_QWORD *)(a2 + 184) + 200LL);
      if ( (v8 & 0x400000) == 0 )
        goto LABEL_20;
      Buf2[0] = (void *)786432;
      Buf2[1] = &v14;
      LOBYTE(a3) = 1;
      Fat8dot3ToString(v8, v12, a3, Buf2);
      if ( _EFS_SHORT != LOWORD(Buf2[0]) || memcmp(Buf1, Buf2[1], (unsigned __int16)_EFS_SHORT) )
      {
        v5 = 0;
        goto LABEL_20;
      }
    }
    v7 += 32;
    v12 = (char *)v12 + 32;
  }
  v5 = 1;
LABEL_20:
  if ( Bcb )
    CcUnpinData(Bcb);
  return v5;
}

```

## disassembly

```asm
0x140031b84  mov     r11, rsp
0x140031b87  mov     [r11+18h], rbx
0x140031b8b  mov     [r11+20h], rsi
0x140031b8f  push    rdi
0x140031b90  push    r14
0x140031b92  push    r15
0x140031b94  sub     rsp, 80h
0x140031b9b  mov     rax, cs:__security_cookie
0x140031ba2  xor     rax, rsp
0x140031ba5  mov     [rsp+98h+var_20], rax
0x140031baa  mov     r14, rdx
0x140031bad  mov     r15, rcx
0x140031bb0  mov     qword ptr [r11-48h], 0
0x140031bb8  xor     dil, dil
0x140031bbb  xor     esi, esi
0x140031bbd  mov     dword ptr [rsp+98h+var_50], esi
0x140031bc1  mov     ecx, 504h
0x140031bc6  movzx   eax, word ptr [rdx]
0x140031bc9  sub     ax, cx
0x140031bcc  neg     ax
0x140031bcf  sbb     ebx, ebx
0x140031bd1  and     ebx, 40h
0x140031bd4  mov     [r11-58h], rsi
0x140031bd8  cmp     ebx, [r14+18h]
0x140031bdc  jb      short loc_140031C0C
0x140031bde  mov     esi, 0C0000011h
0x140031be3  mov     dword ptr [rsp+98h+var_50], esi
0x140031be7  mov     rcx, [rsp+98h+Bcb]; Bcb
0x140031bec  test    rcx, rcx
0x140031bef  jz      loc_140031C89
0x140031bf5  call    cs:__imp_CcUnpinData
0x140031bfc  nop     dword ptr [rax+rax+00h]
0x140031c01  mov     [rsp+98h+Bcb], 0
0x140031c0a  jmp     short loc_140031C89
0x140031c0c  test    ebx, 0FFFh
0x140031c12  jz      short loc_140031C1C
0x140031c14  cmp     [rsp+98h+Bcb], 0
0x140031c1a  jnz     short loc_140031C89
0x140031c1c  mov     rcx, [rsp+98h+Bcb]; Bcb
0x140031c21  test    rcx, rcx
0x140031c24  jz      short loc_140031C3B
0x140031c26  call    cs:__imp_CcUnpinData
0x140031c2d  nop     dword ptr [rax+rax+00h]
0x140031c32  mov     [rsp+98h+Bcb], 0
0x140031c3b  mov     r8d, ebx
0x140031c3e  and     r8d, 0FFFFF000h; int
0x140031c45  lea     rax, [rsp+98h+var_50]
0x140031c4a  mov     [rsp+98h+var_60], rax; __int64
0x140031c4f  lea     rax, [rsp+98h+var_48]
0x140031c54  mov     [rsp+98h+var_68], rax; PVOID *
0x140031c59  lea     rax, [rsp+98h+Bcb]
0x140031c5e  mov     [rsp+98h+var_70], rax; PVOID *
0x140031c63  mov     [rsp+98h+var_78], 0; char
0x140031c68  mov     r9d, 1000h; int
0x140031c6e  mov     rdx, r14; int
0x140031c71  mov     rcx, r15; int
0x140031c74  call    FatReadDirectoryFile
0x140031c79  mov     eax, ebx
0x140031c7b  and     eax, 0FFFh
0x140031c80  add     [rsp+98h+var_48], rax
0x140031c85  mov     esi, dword ptr [rsp+98h+var_50]
0x140031c89  cmp     esi, 0C0000011h
0x140031c8f  jz      loc_140031D28
0x140031c95  mov     rcx, [rsp+98h+var_48]
0x140031c9a  mov     al, [rcx]
0x140031c9c  test    al, al
0x140031c9e  jz      loc_140031D28
0x140031ca4  cmp     al, 0E5h
0x140031ca6  jz      short loc_140031D1A
0x140031ca8  cmp     byte ptr [rcx+0Bh], 0Fh
0x140031cac  jz      short loc_140031D1A
0x140031cae  mov     rax, [r14+0B8h]
0x140031cb5  mov     ecx, [rax+0C8h]
0x140031cbb  bt      ecx, 16h
0x140031cbf  jnb     short loc_140031D2B
0x140031cc1  xorps   xmm0, xmm0
0x140031cc4  movups  xmmword ptr [rsp+98h+Buf2], xmm0
0x140031cc9  mov     eax, 0Ch
0x140031cce  mov     word ptr [rsp+98h+Buf2+2], ax
0x140031cd3  lea     rax, [rsp+98h+var_30]
0x140031cd8  mov     [rsp+98h+Buf2+8], rax
0x140031cdd  lea     r9, [rsp+98h+Buf2]
0x140031ce2  mov     r8b, 1
0x140031ce5  mov     rdx, [rsp+98h+var_48]
0x140031cea  call    Fat8dot3ToString
0x140031cef  movzx   eax, cs:$EFS_SHORT
0x140031cf6  cmp     ax, word ptr [rsp+98h+Buf2]
0x140031cfb  jnz     short loc_140031D15
0x140031cfd  mov     r8d, eax; Size
0x140031d00  mov     rdx, [rsp+98h+Buf2+8]; Buf2
0x140031d05  mov     rcx, cs:Buf1; Buf1
0x140031d0c  call    memcmp
0x140031d11  test    eax, eax
0x140031d13  jz      short loc_140031D1A
0x140031d15  xor     dil, dil
0x140031d18  jmp     short loc_140031D2B
0x140031d1a  add     ebx, 20h ; ' '
0x140031d1d  add     [rsp+98h+var_48], 20h ; ' '
0x140031d23  jmp     loc_140031BD8
0x140031d28  mov     dil, 1
0x140031d2b  mov     rcx, [rsp+98h+Bcb]; Bcb
0x140031d30  test    rcx, rcx
0x140031d33  jz      short loc_140031D41
0x140031d35  call    cs:__imp_CcUnpinData
0x140031d3c  nop     dword ptr [rax+rax+00h]
0x140031d41  mov     al, dil
0x140031d44  mov     rcx, [rsp+98h+var_20]
0x140031d49  xor     rcx, rsp; StackCookie
0x140031d4c  call    __security_check_cookie
0x140031d51  lea     r11, [rsp+98h+var_18]
0x140031d59  mov     rbx, [r11+30h]
0x140031d5d  mov     rsi, [r11+38h]
0x140031d61  mov     rsp, r11
0x140031d64  pop     r15
0x140031d66  pop     r14
0x140031d68  pop     rdi
0x140031d69  retn
0x14005d22e  push    rbp
0x14005d230  sub     rsp, 40h
0x14005d234  mov     rbp, rdx
0x14005d237  mov     rcx, [rbp+40h]; Bcb
0x14005d23b  test    rcx, rcx
0x14005d23e  jz      short loc_14005D24D
0x14005d240  call    cs:__imp_CcUnpinData
0x14005d247  nop     dword ptr [rax+rax+00h]
0x14005d24c  nop
0x14005d24d  add     rsp, 40h
0x14005d251  pop     rbp
0x14005d252  retn
```
