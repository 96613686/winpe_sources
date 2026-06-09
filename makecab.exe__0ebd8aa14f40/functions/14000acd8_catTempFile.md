# catTempFile

- ea: `0x14000acd8`
- end: `0x14000ae70`
- name: `catTempFile`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000cb80`

## callees

- `0x140008620`
- `0x140008ee4`
- `0x14000acd8`

## import_xrefs

- `msvcrt!fread` at `0x14000ada3`
- `msvcrt!fread` at `0x14000ada3`
- `msvcrt!fwrite` at `0x14000adcc`
- `msvcrt!fwrite` at `0x14000adcc`
- `msvcrt!feof` at `0x14000ade4`
- `msvcrt!feof` at `0x14000ade4`
- `msvcrt!ferror` at `0x14000adaf`
- `msvcrt!ferror` at `0x14000add7`
- `msvcrt!ferror` at `0x14000adaf`
- `msvcrt!ferror` at `0x14000add7`
- `msvcrt!fclose` at `0x14000ae50`
- `msvcrt!fclose` at `0x14000ae50`
- `msvcrt!fopen` at `0x14000ad4e`
- `msvcrt!fopen` at `0x14000ad4e`
- `msvcrt!malloc` at `0x14000ad07`
- `msvcrt!malloc` at `0x14000ad07`
- `msvcrt!free` at `0x14000ae01`
- `msvcrt!free` at `0x14000ae42`
- `msvcrt!free` at `0x14000ae01`
- `msvcrt!free` at `0x14000ae42`

## string_xrefs

- `0x14000ad6b`: `Cannot open %1: %2`
- `0x14000ad29`: `Out of memory copying %1 %2 to %3`
- `0x14000ae17`: `Read failed copying %1 %2 to %3`
- `0x14000ae0e`: `Write failed copying %1 %2 to %3`

## pseudocode

```c
__int64 __fastcall catTempFile(FILE *a1, const char *a2, FILE **a3, __int64 a4, __int64 a5)
{
  const char *v5; // r12
  const char *v6; // r14
  void *v9; // rsi
  FILE *v10; // rbx
  FILE *v11; // rax
  size_t v12; // r13
  const char *v14; // rdx

  v5 = (const char *)a3[2];
  v6 = (const char *)a3[1];
  v9 = malloc(0x800u);
  if ( v9 )
  {
    v10 = 0;
    v11 = fopen(v6, "rb");
    *a3 = v11;
    if ( !v11 )
      ErrSet(a5, "Cannot open %1: %2", "%s%s", (const char *)a3[2], (const char *)a3[1]);
    if ( *a3 )
    {
      v10 = *a3;
      while ( 1 )
      {
        if ( feof(v10) )
        {
          TmpClose(a3, a5);
          free(v9);
          return 1;
        }
        v12 = fread(v9, 1u, 0x800u, v10);
        if ( ferror(v10) )
          break;
        if ( v12 )
        {
          fwrite(v9, 1u, v12, a1);
          if ( ferror(a1) )
          {
            v14 = "Write failed copying %1 %2 to %3";
            goto LABEL_14;
          }
        }
      }
      v14 = "Read failed copying %1 %2 to %3";
LABEL_14:
      ErrSet(a5, v14, "%s%s%s", v5, v6, a2);
    }
    free(v9);
    if ( v10 )
      fclose(v10);
  }
  else
  {
    ErrSet(a5, "Out of memory copying %1 %2 to %3", "%s%s%s", v5, v6, a2);
  }
  return 0;
}

```

## disassembly

```asm
0x14000acd8  mov     [rsp+arg_8], rbx
0x14000acdd  mov     [rsp+arg_10], rsi
0x14000ace2  mov     [rsp+Stream], rcx
0x14000ace7  push    rdi
0x14000ace8  push    r12
0x14000acea  push    r13
0x14000acec  push    r14
0x14000acee  push    r15
0x14000acf0  sub     rsp, 30h
0x14000acf4  mov     r12, [r8+10h]
0x14000acf8  mov     ecx, 800h; Size
0x14000acfd  mov     r14, [r8+8]
0x14000ad01  mov     rdi, r8
0x14000ad04  mov     r15, rdx
0x14000ad07  call    cs:__imp_malloc
0x14000ad0d  mov     rsi, rax
0x14000ad10  test    rax, rax
0x14000ad13  jnz     short loc_14000AD42
0x14000ad15  mov     rcx, [rsp+58h+arg_20]
0x14000ad1d  lea     r8, aSSS; "%s%s%s"
0x14000ad24  mov     [rsp+58h+var_30], r15
0x14000ad29  lea     rdx, aOutOfMemoryCop; "Out of memory copying %1 %2 to %3"
0x14000ad30  mov     r9, r12
0x14000ad33  mov     [rsp+58h+var_38], r14
0x14000ad38  call    ErrSet
0x14000ad3d  jmp     loc_14000AE56
0x14000ad42  lea     rdx, aRb; "rb"
0x14000ad49  mov     rcx, r14; FileName
0x14000ad4c  xor     ebx, ebx
0x14000ad4e  call    cs:__imp_fopen
0x14000ad54  mov     [rdi], rax
0x14000ad57  test    rax, rax
0x14000ad5a  jnz     short loc_14000AD84
0x14000ad5c  mov     rax, [rdi+8]
0x14000ad60  lea     r8, aSS_1; "%s%s"
0x14000ad67  mov     r9, [rdi+10h]
0x14000ad6b  lea     rdx, aCannotOpen12; "Cannot open %1: %2"
0x14000ad72  mov     rcx, [rsp+58h+arg_20]
0x14000ad7a  mov     [rsp+58h+var_38], rax
0x14000ad7f  call    ErrSet
0x14000ad84  cmp     [rdi], rbx
0x14000ad87  jz      loc_14000AE3F
0x14000ad8d  mov     rbx, [rdi]
0x14000ad90  jmp     short loc_14000ADE1
0x14000ad92  mov     r9, rbx; Stream
0x14000ad95  mov     edx, 1; ElementSize
0x14000ad9a  mov     r8d, 800h; ElementCount
0x14000ada0  mov     rcx, rsi; Buffer
0x14000ada3  call    cs:__imp_fread
0x14000ada9  mov     rcx, rbx; Stream
0x14000adac  mov     r13, rax
0x14000adaf  call    cs:__imp_ferror
0x14000adb5  test    eax, eax
0x14000adb7  jnz     short loc_14000AE17
0x14000adb9  test    r13, r13
0x14000adbc  jz      short loc_14000ADE1
0x14000adbe  mov     r9, [rsp+58h+Stream]; Stream
0x14000adc3  lea     edx, [rax+1]; ElementSize
0x14000adc6  mov     r8, r13; ElementCount
0x14000adc9  mov     rcx, rsi; Buffer
0x14000adcc  call    cs:__imp_fwrite
0x14000add2  mov     rcx, [rsp+58h+Stream]; Stream
0x14000add7  call    cs:__imp_ferror
0x14000addd  test    eax, eax
0x14000addf  jnz     short loc_14000AE0E
0x14000ade1  mov     rcx, rbx; Stream
0x14000ade4  call    cs:__imp_feof
0x14000adea  test    eax, eax
0x14000adec  jz      short loc_14000AD92
0x14000adee  mov     rdx, [rsp+58h+arg_20]
0x14000adf6  mov     rcx, rdi
0x14000adf9  call    TmpClose
0x14000adfe  mov     rcx, rsi; Block
0x14000ae01  call    cs:__imp_free
0x14000ae07  mov     eax, 1
0x14000ae0c  jmp     short loc_14000AE58
0x14000ae0e  lea     rdx, aWriteFailedCop; "Write failed copying %1 %2 to %3"
0x14000ae15  jmp     short loc_14000AE1E
0x14000ae17  lea     rdx, aReadFailedCopy; "Read failed copying %1 %2 to %3"
0x14000ae1e  mov     rcx, [rsp+58h+arg_20]
0x14000ae26  lea     r8, aSSS; "%s%s%s"
0x14000ae2d  mov     [rsp+58h+var_30], r15
0x14000ae32  mov     r9, r12
0x14000ae35  mov     [rsp+58h+var_38], r14
0x14000ae3a  call    ErrSet
0x14000ae3f  mov     rcx, rsi; Block
0x14000ae42  call    cs:__imp_free
0x14000ae48  test    rbx, rbx
0x14000ae4b  jz      short loc_14000AE56
0x14000ae4d  mov     rcx, rbx; Stream
0x14000ae50  call    cs:__imp_fclose
0x14000ae56  xor     eax, eax
0x14000ae58  mov     rbx, [rsp+58h+arg_8]
0x14000ae5d  mov     rsi, [rsp+58h+arg_10]
0x14000ae62  add     rsp, 30h
0x14000ae66  pop     r15
0x14000ae68  pop     r14
0x14000ae6a  pop     r13
0x14000ae6c  pop     r12
0x14000ae6e  pop     rdi
0x14000ae6f  retn
```
