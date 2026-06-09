# FatDeleteEfsAttributeOnDirectory

- ea: `0x14003172c`
- end: `0x140031900`
- name: `FatDeleteEfsAttributeOnDirectory`
- size: `468`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1400034f0`
- `0x140024bd4`

## callees

- `0x14000c230`
- `0x14000cba0`
- `0x140024584`
- `0x14003172c`
- `0x14003a3e0`
- `0x140044518`

## import_xrefs

- `ntoskrnl!CcUnpinData` at `0x140031791`
- `ntoskrnl!CcUnpinData` at `0x1400317b8`
- `ntoskrnl!CcUnpinData` at `0x1400318d0`
- `ntoskrnl!CcUnpinData` at `0x14005d1e8`
- `ntoskrnl!CcUnpinData` at `0x140031791`
- `ntoskrnl!CcUnpinData` at `0x1400317b8`
- `ntoskrnl!CcUnpinData` at `0x1400318d0`
- `ntoskrnl!CcUnpinData` at `0x14005d1e8`

## pseudocode

```c
char __fastcall FatDeleteEfsAttributeOnDirectory(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // edi
  unsigned int v6; // ebx
  PVOID v7; // rcx
  __int64 v9; // [rsp+40h] [rbp-58h] BYREF
  PVOID v10; // [rsp+48h] [rbp-50h] BYREF
  PVOID Bcb; // [rsp+50h] [rbp-48h] BYREF
  void *Buf2[2]; // [rsp+58h] [rbp-40h] BYREF
  char v13; // [rsp+68h] [rbp-30h] BYREF

  v10 = 0;
  v5 = 0;
  LODWORD(v9) = 0;
  v6 = *(_WORD *)a2 != 1284 ? 0x40 : 0;
  v7 = 0;
  Bcb = 0;
  while ( 1 )
  {
    if ( v6 < *(_DWORD *)(a2 + 24) )
    {
      if ( (v6 & 0xFFF) == 0 || !v7 )
      {
        if ( v7 )
        {
          CcUnpinData(v7);
          Bcb = 0;
        }
        FatReadDirectoryFile(a1, a2, v6 & 0xFFFFF000, 0x1000u, 0, &Bcb, &v10, &v9);
        v10 = (char *)v10 + (v6 & 0xFFF);
        v7 = Bcb;
        v5 = v9;
      }
    }
    else
    {
      v5 = -1073741807;
      LODWORD(v9) = -1073741807;
      if ( v7 )
      {
        CcUnpinData(v7);
        v7 = 0;
        Bcb = 0;
      }
    }
    if ( v5 == -1073741807 || !*(_BYTE *)v10 )
      break;
    if ( *(_BYTE *)v10 != 0xE5 && *((_BYTE *)v10 + 11) != 15 )
    {
      Buf2[0] = (void *)786432;
      Buf2[1] = &v13;
      LOBYTE(a3) = 1;
      Fat8dot3ToString(v7, v10, a3, Buf2);
      if ( _EFS_SHORT == LOWORD(Buf2[0]) && !memcmp(Buf1, Buf2[1], (unsigned __int16)_EFS_SHORT) )
        FatDeleteFile(a1, a2, v6, v6, (__int64)v10, 0);
      v7 = Bcb;
    }
    v6 += 32;
    v10 = (char *)v10 + 32;
  }
  if ( v7 )
    CcUnpinData(v7);
  return 0;
}

```

## disassembly

```asm
0x14003172c  mov     [rsp+arg_10], rbx
0x140031731  push    rsi
0x140031732  push    rdi
0x140031733  push    r14
0x140031735  sub     rsp, 80h
0x14003173c  mov     rax, cs:__security_cookie
0x140031743  xor     rax, rsp
0x140031746  mov     [rsp+98h+var_20], rax
0x14003174b  mov     rsi, rdx
0x14003174e  mov     r14, rcx
0x140031751  mov     [rsp+98h+var_50], 0
0x14003175a  xor     edi, edi
0x14003175c  mov     dword ptr [rsp+98h+var_58], edi
0x140031760  mov     ecx, 504h
0x140031765  movzx   eax, word ptr [rdx]
0x140031768  sub     ax, cx
0x14003176b  neg     ax
0x14003176e  sbb     ebx, ebx
0x140031770  and     ebx, 40h
0x140031773  xor     ecx, ecx; Bcb
0x140031775  mov     [rsp+98h+Bcb], rcx
0x14003177a  cmp     ebx, [rsi+18h]
0x14003177d  jb      short loc_1400317A6
0x14003177f  mov     edi, 0C0000011h
0x140031784  mov     dword ptr [rsp+98h+var_58], edi
0x140031788  test    rcx, rcx
0x14003178b  jz      loc_140031820
0x140031791  call    cs:__imp_CcUnpinData
0x140031798  nop     dword ptr [rax+rax+00h]
0x14003179d  xor     ecx, ecx
0x14003179f  mov     [rsp+98h+Bcb], rcx
0x1400317a4  jmp     short loc_140031820
0x1400317a6  test    ebx, 0FFFh
0x1400317ac  jz      short loc_1400317B3
0x1400317ae  test    rcx, rcx
0x1400317b1  jnz     short loc_140031820
0x1400317b3  test    rcx, rcx
0x1400317b6  jz      short loc_1400317CD
0x1400317b8  call    cs:__imp_CcUnpinData
0x1400317bf  nop     dword ptr [rax+rax+00h]
0x1400317c4  mov     [rsp+98h+Bcb], 0
0x1400317cd  mov     r8d, ebx
0x1400317d0  and     r8d, 0FFFFF000h; int
0x1400317d7  lea     rax, [rsp+98h+var_58]
0x1400317dc  mov     [rsp+98h+var_60], rax; __int64
0x1400317e1  lea     rax, [rsp+98h+var_50]
0x1400317e6  mov     [rsp+98h+var_68], rax; PVOID *
0x1400317eb  lea     rax, [rsp+98h+Bcb]
0x1400317f0  mov     [rsp+98h+var_70], rax; PVOID *
0x1400317f5  mov     [rsp+98h+var_78], 0; char
0x1400317fa  mov     r9d, 1000h; int
0x140031800  mov     rdx, rsi; int
0x140031803  mov     rcx, r14; int
0x140031806  call    FatReadDirectoryFile
0x14003180b  mov     eax, ebx
0x14003180d  and     eax, 0FFFh
0x140031812  add     [rsp+98h+var_50], rax
0x140031817  mov     rcx, [rsp+98h+Bcb]; Bcb
0x14003181c  mov     edi, dword ptr [rsp+98h+var_58]
0x140031820  cmp     edi, 0C0000011h
0x140031826  jz      loc_1400318CB
0x14003182c  mov     rdx, [rsp+98h+var_50]
0x140031831  mov     al, [rdx]
0x140031833  test    al, al
0x140031835  jz      loc_1400318CB
0x14003183b  cmp     al, 0E5h
0x14003183d  jz      short loc_1400318BD
0x14003183f  cmp     byte ptr [rdx+0Bh], 0Fh
0x140031843  jz      short loc_1400318BD
0x140031845  xorps   xmm0, xmm0
0x140031848  movups  xmmword ptr [rsp+98h+Buf2], xmm0
0x14003184d  mov     eax, 0Ch
0x140031852  mov     word ptr [rsp+98h+Buf2+2], ax
0x140031857  lea     rax, [rsp+98h+var_30]
0x14003185c  mov     [rsp+98h+Buf2+8], rax
0x140031861  lea     r9, [rsp+98h+Buf2]
0x140031866  mov     r8b, 1
0x140031869  call    Fat8dot3ToString
0x14003186e  movzx   eax, cs:$EFS_SHORT
0x140031875  cmp     ax, word ptr [rsp+98h+Buf2]
0x14003187a  jnz     short loc_1400318B8
0x14003187c  mov     r8d, eax; Size
0x14003187f  mov     rdx, [rsp+98h+Buf2+8]; Buf2
0x140031884  mov     rcx, cs:Buf1; Buf1
0x14003188b  call    memcmp
0x140031890  test    eax, eax
0x140031892  jnz     short loc_1400318B8
0x140031894  mov     [rsp+98h+var_70], 0
0x14003189d  mov     rax, [rsp+98h+var_50]
0x1400318a2  mov     qword ptr [rsp+98h+var_78], rax
0x1400318a7  mov     r9d, ebx
0x1400318aa  mov     r8d, ebx
0x1400318ad  mov     rdx, rsi
0x1400318b0  mov     rcx, r14
0x1400318b3  call    FatDeleteFile
0x1400318b8  mov     rcx, [rsp+98h+Bcb]
0x1400318bd  add     ebx, 20h ; ' '
0x1400318c0  add     [rsp+98h+var_50], 20h ; ' '
0x1400318c6  jmp     loc_14003177A
0x1400318cb  test    rcx, rcx
0x1400318ce  jz      short loc_1400318DC
0x1400318d0  call    cs:__imp_CcUnpinData
0x1400318d7  nop     dword ptr [rax+rax+00h]
0x1400318dc  xor     al, al
0x1400318de  mov     rcx, [rsp+98h+var_20]
0x1400318e3  xor     rcx, rsp; StackCookie
0x1400318e6  call    __security_check_cookie
0x1400318eb  mov     rbx, [rsp+98h+arg_10]
0x1400318f3  add     rsp, 80h
0x1400318fa  pop     r14
0x1400318fc  pop     rdi
0x1400318fd  pop     rsi
0x1400318fe  retn
0x14005d1d6  push    rbp
0x14005d1d8  sub     rsp, 40h
0x14005d1dc  mov     rbp, rdx
0x14005d1df  mov     rcx, [rbp+50h]; Bcb
0x14005d1e3  test    rcx, rcx
0x14005d1e6  jz      short loc_14005D1F5
0x14005d1e8  call    cs:__imp_CcUnpinData
0x14005d1ef  nop     dword ptr [rax+rax+00h]
0x14005d1f4  nop
0x14005d1f5  add     rsp, 40h
0x14005d1f9  pop     rbp
0x14005d1fa  retn
```
