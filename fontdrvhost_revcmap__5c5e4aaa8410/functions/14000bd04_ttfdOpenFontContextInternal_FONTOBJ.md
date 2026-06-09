# ttfdOpenFontContextInternal(_FONTOBJ *)

- ea: `0x14000bd04`
- end: `0x14000bee1`
- name: `?ttfdOpenFontContextInternal@@YAPEAU_TT_FONTCONTEXT@@PEAU_FONTOBJ@@@Z`
- size: `477`
- prototype: `struct _TT_FONTCONTEXT *__fastcall(struct _FONTOBJ *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140015c74`

## callees

- `0x1400020f4`
- `0x14000b694`
- `0x14000bd04`
- `0x14000c008`
- `0x140015cdc`
- `0x140048348`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x14000be95`
- `KERNEL32!GlobalFree` at `0x14000beb6`
- `KERNEL32!GlobalFree` at `0x14000be95`
- `KERNEL32!GlobalFree` at `0x14000beb6`
- `KERNEL32!GlobalAlloc` at `0x14000bd5c`
- `KERNEL32!GlobalAlloc` at `0x14000be42`
- `KERNEL32!GlobalAlloc` at `0x14000bd5c`
- `KERNEL32!GlobalAlloc` at `0x14000be42`

## pseudocode

```c
struct _TT_FONTCONTEXT *__fastcall ttfdOpenFontContextInternal(struct _FONTOBJ *a1)
{
  ULONG_PTR iFile; // rdi
  __int64 v3; // rax
  ULONG iFace; // ebx
  ULONG_PTR v5; // rbp
  __int64 v6; // r15
  __int64 v7; // rbx
  char *v8; // rax
  struct _FONTOBJ *v9; // rcx
  char *v10; // rsi
  struct _TT_FONTCONTEXT *result; // rax
  unsigned int v12; // ecx
  unsigned int v13; // edx
  HGLOBAL v14; // rax

  iFile = a1->iFile;
  if ( !iFile )
    return 0;
  v3 = *(_QWORD *)(iFile + 48);
  iFace = a1->iFace;
  v5 = *(_QWORD *)(v3 + 56);
  if ( !*(_DWORD *)iFile && !EngMapFontFileFD(*(_QWORD *)(v3 + 56), (PULONG *)(iFile + 16), (ULONG *)(iFile + 24)) )
    return 0;
  v6 = iFace - 1;
  v7 = *(_QWORD *)(iFile + 16 * (v6 + 3));
  if ( !*(_DWORD *)(v7 + 48) )
  {
    v12 = *(_DWORD *)(v7 + 380);
    v13 = v12 + *(_DWORD *)(v7 + 384);
    *(_QWORD *)(v7 + 64) = *(_QWORD *)(iFile + 16);
    *(_DWORD *)(v7 + 72) = *(_DWORD *)(iFile + 24);
    if ( v13 < v12 || v13 + 1680 < v13 || (v14 = GlobalAlloc(0x40u, v13 + 1680), (*(_QWORD *)(v7 + 24) = v14) == 0) )
    {
      if ( !*(_DWORD *)iFile )
        EngUnmapFontFileFD(v5);
      return 0;
    }
    if ( !(unsigned int)bInitInAndOut((struct _TT_FONTFILE *)v7) )
    {
      if ( !*(_DWORD *)iFile )
        EngUnmapFontFileFD(v5);
LABEL_22:
      GlobalFree(*(HGLOBAL *)(v7 + 24));
      *(_QWORD *)(v7 + 24) = 0;
      return 0;
    }
    if ( !*(_WORD *)(v7 + 412) )
      vGetMinD((struct _TT_FONTFILE *)v7);
  }
  v8 = (char *)GlobalAlloc(0, 0x1A0u);
  *(_QWORD *)(v7 + 40) = v8;
  v10 = v8;
  if ( v8 )
  {
    *(_QWORD *)v8 = a1;
    *((_QWORD *)v8 + 1) = v7;
    *((_QWORD *)v8 + 24) = v7 + 112;
    *((_DWORD *)v8 + 10) = a1->flFontType;
    *(SIZE *)(v8 + 44) = a1->sizLogResPpi;
    *((_DWORD *)v8 + 13) = a1->ulStyleSize;
    *((_QWORD *)v8 + 22) = *(_QWORD *)(v7 + 24);
    *((_QWORD *)v8 + 23) = *(_QWORD *)(v7 + 24) + 224LL;
    *((_DWORD *)v8 + 77) = (*(_DWORD *)(iFile + 16 * v6 + 44) & 1) == 0;
    if ( bNewXform(v9, (struct _TT_FONTCONTEXT *)v8) )
    {
      *((_DWORD *)v10 + 76) = 0;
      result = (struct _TT_FONTCONTEXT *)v10;
      *((_WORD *)v10 + 201) = -1;
      ++*(_DWORD *)(v7 + 48);
      *(_QWORD *)(v7 + 40) = 0;
      ++*(_DWORD *)iFile;
      return result;
    }
    GlobalFree(v10);
    *(_QWORD *)(v7 + 40) = 0;
  }
  if ( !*(_DWORD *)iFile )
    EngUnmapFontFileFD(v5);
  if ( !*(_DWORD *)(v7 + 48) )
    goto LABEL_22;
  return 0;
}

```

## disassembly

```asm
0x14000bd04  push    rbx
0x14000bd06  push    rbp
0x14000bd07  push    rsi
0x14000bd08  push    rdi
0x14000bd09  push    r12
0x14000bd0b  push    r14
0x14000bd0d  push    r15
0x14000bd0f  sub     rsp, 20h
0x14000bd13  mov     rdi, [rcx+18h]
0x14000bd17  xor     r12d, r12d
0x14000bd1a  mov     r14, rcx
0x14000bd1d  test    rdi, rdi
0x14000bd20  jz      loc_14000BE37
0x14000bd26  mov     rax, [rdi+30h]
0x14000bd2a  mov     ebx, [rcx+4]
0x14000bd2d  mov     rbp, [rax+38h]
0x14000bd31  cmp     [rdi], r12d
0x14000bd34  jz      loc_14000BE78
0x14000bd3a  lea     eax, [rbx-1]
0x14000bd3d  mov     r15d, eax
0x14000bd40  add     rax, 3
0x14000bd44  add     rax, rax
0x14000bd47  mov     rbx, [rdi+rax*8]
0x14000bd4b  cmp     [rbx+30h], r12d
0x14000bd4f  jz      loc_14000BE04
0x14000bd55  mov     edx, 1A0h; dwBytes
0x14000bd5a  xor     ecx, ecx; uFlags
0x14000bd5c  call    cs:__imp_GlobalAlloc
0x14000bd62  mov     [rbx+28h], rax
0x14000bd66  mov     rsi, rax
0x14000bd69  test    rax, rax
0x14000bd6c  jz      loc_14000BE9F
0x14000bd72  mov     [rax], r14
0x14000bd75  add     r15, r15
0x14000bd78  mov     [rax+8], rbx
0x14000bd7c  mov     rdx, rsi; struct _TT_FONTCONTEXT *
0x14000bd7f  lea     rax, [rbx+70h]
0x14000bd83  mov     [rsi+0C0h], rax
0x14000bd8a  mov     eax, [r14+0Ch]
0x14000bd8e  mov     [rsi+28h], eax
0x14000bd91  mov     rax, [r14+20h]
0x14000bd95  mov     [rsi+2Ch], rax
0x14000bd99  mov     eax, [r14+28h]
0x14000bd9d  mov     [rsi+34h], eax
0x14000bda0  mov     rax, [rbx+18h]
0x14000bda4  mov     [rsi+0B0h], rax
0x14000bdab  mov     rax, [rbx+18h]
0x14000bdaf  add     rax, 0E0h
0x14000bdb5  mov     [rsi+0B8h], rax
0x14000bdbc  mov     eax, [rdi+r15*8+2Ch]
0x14000bdc1  not     eax
0x14000bdc3  and     eax, 1
0x14000bdc6  mov     [rsi+134h], eax
0x14000bdcc  call    ?bNewXform@@YAHPEAU_FONTOBJ@@PEAU_TT_FONTCONTEXT@@@Z; bNewXform(_FONTOBJ *,_TT_FONTCONTEXT *)
0x14000bdd1  test    eax, eax
0x14000bdd3  jz      loc_14000BE92
0x14000bdd9  mov     [rsi+130h], r12d
0x14000bde0  mov     rax, rsi
0x14000bde3  mov     word ptr [rsi+192h], 0FFFFh
0x14000bdec  inc     dword ptr [rbx+30h]
0x14000bdef  mov     [rbx+28h], r12
0x14000bdf3  inc     dword ptr [rdi]
0x14000bdf5  add     rsp, 20h
0x14000bdf9  pop     r15
0x14000bdfb  pop     r14
0x14000bdfd  pop     r12
0x14000bdff  pop     rdi
0x14000be00  pop     rsi
0x14000be01  pop     rbp
0x14000be02  pop     rbx
0x14000be03  retn
0x14000be04  mov     rax, [rdi+10h]
0x14000be08  mov     ecx, [rbx+17Ch]
0x14000be0e  mov     edx, [rbx+180h]
0x14000be14  add     edx, ecx
0x14000be16  mov     [rbx+40h], rax
0x14000be1a  mov     eax, [rdi+18h]
0x14000be1d  mov     [rbx+48h], eax
0x14000be20  cmp     edx, ecx
0x14000be22  jb      short loc_14000BE2E
0x14000be24  lea     eax, [rdx+690h]
0x14000be2a  cmp     eax, edx
0x14000be2c  jnb     short loc_14000BE3B
0x14000be2e  cmp     [rdi], r12d
0x14000be31  jz      loc_14000BED4
0x14000be37  xor     eax, eax
0x14000be39  jmp     short loc_14000BDF5
0x14000be3b  mov     edx, eax; dwBytes
0x14000be3d  mov     ecx, 40h ; '@'; uFlags
0x14000be42  call    cs:__imp_GlobalAlloc
0x14000be48  mov     [rbx+18h], rax
0x14000be4c  test    rax, rax
0x14000be4f  jz      short loc_14000BE2E
0x14000be51  mov     rcx, rbx; struct _TT_FONTFILE *
0x14000be54  call    ?bInitInAndOut@@YAHPEAU_TT_FONTFILE@@@Z; bInitInAndOut(_TT_FONTFILE *)
0x14000be59  test    eax, eax
0x14000be5b  jz      short loc_14000BEC5
0x14000be5d  cmp     [rbx+19Ch], r12w
0x14000be65  jnz     loc_14000BD55
0x14000be6b  mov     rcx, rbx; struct _TT_FONTFILE *
0x14000be6e  call    ?vGetMinD@@YAXPEAU_TT_FONTFILE@@@Z; vGetMinD(_TT_FONTFILE *)
0x14000be73  jmp     loc_14000BD55
0x14000be78  lea     r8, [rdi+18h]; pcjBuf
0x14000be7c  mov     rcx, rbp; iFile
0x14000be7f  lea     rdx, [rdi+10h]; ppjBuf
0x14000be83  call    EngMapFontFileFD
0x14000be88  test    eax, eax
0x14000be8a  jnz     loc_14000BD3A
0x14000be90  jmp     short loc_14000BE37
0x14000be92  mov     rcx, rsi; hMem
0x14000be95  call    cs:__imp_GlobalFree
0x14000be9b  mov     [rbx+28h], r12
0x14000be9f  cmp     [rdi], r12d
0x14000bea2  jnz     short loc_14000BEAC
0x14000bea4  mov     rcx, rbp; iFile
0x14000bea7  call    EngUnmapFontFileFD
0x14000beac  cmp     [rbx+30h], r12d
0x14000beb0  jnz     short loc_14000BE37
0x14000beb2  mov     rcx, [rbx+18h]; hMem
0x14000beb6  call    cs:__imp_GlobalFree
0x14000bebc  mov     [rbx+18h], r12
0x14000bec0  jmp     loc_14000BE37
0x14000bec5  cmp     [rdi], r12d
0x14000bec8  jnz     short loc_14000BEB2
0x14000beca  mov     rcx, rbp; iFile
0x14000becd  call    EngUnmapFontFileFD
0x14000bed2  jmp     short loc_14000BEB2
0x14000bed4  mov     rcx, rbp; iFile
0x14000bed7  call    EngUnmapFontFileFD
0x14000bedc  jmp     loc_14000BE37
```
