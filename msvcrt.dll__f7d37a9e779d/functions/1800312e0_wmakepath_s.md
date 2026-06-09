# _wmakepath_s

- ea: `0x1800312e0`
- end: `0x180031440`
- name: `_wmakepath_s`
- size: `352`
- prototype: `errno_t __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Drive, const wchar_t *Dir, const wchar_t *Filename, const wchar_t *Ext)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800312b0`

## callees

- `0x180007f00`
- `0x18002f050`
- `0x1800312e0`

## pseudocode

```c
errno_t __cdecl wmakepath_s(
        wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Drive,
        const wchar_t *Dir,
        const wchar_t *Filename,
        const wchar_t *Ext)
{
  __int64 v7; // r10
  wchar_t *v8; // r11
  const wchar_t *v9; // rcx
  const wchar_t *v10; // rcx
  const wchar_t *v11; // rcx
  int *v12; // rax
  int v13; // ebx

  if ( !Buffer || !BufferCount )
  {
    v12 = errno();
    v13 = 22;
LABEL_32:
    *v12 = v13;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  v7 = 0;
  v8 = Buffer;
  if ( Drive && *Drive )
  {
    if ( BufferCount <= 2 )
      goto LABEL_29;
    *Buffer = *Drive;
    v7 = 2;
    Buffer[1] = 58;
    v8 = Buffer + 2;
  }
  if ( Dir && *Dir )
  {
    do
    {
      if ( ++v7 >= BufferCount )
        goto LABEL_29;
      v9 = Dir;
      *v8++ = *Dir++;
    }
    while ( *Dir );
    if ( *v9 != 47 && *v9 != 92 )
    {
      if ( ++v7 >= BufferCount )
        goto LABEL_29;
      *v8++ = 92;
    }
  }
  v10 = Filename;
  if ( Filename )
  {
    while ( *v10 )
    {
      if ( ++v7 >= BufferCount )
        goto LABEL_29;
      *v8++ = *v10++;
    }
  }
  v11 = Ext;
  if ( Ext && *Ext )
  {
    if ( *Ext == 46 )
      goto LABEL_27;
    if ( ++v7 >= BufferCount )
      goto LABEL_29;
    *v8++ = 46;
LABEL_27:
    while ( *v11 )
    {
      if ( ++v7 >= BufferCount )
        goto LABEL_29;
      *v8++ = *v11++;
    }
  }
  if ( v7 + 1 > BufferCount )
  {
LABEL_29:
    *Buffer = 0;
    v12 = errno();
    v13 = 34;
    goto LABEL_32;
  }
  *v8 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800312e0  mov     [rsp+arg_0], rbx
0x1800312e5  push    rdi
0x1800312e6  sub     rsp, 30h
0x1800312ea  xor     edi, edi
0x1800312ec  mov     rbx, rcx
0x1800312ef  test    rcx, rcx
0x1800312f2  jz      loc_180031413
0x1800312f8  test    rdx, rdx
0x1800312fb  jz      loc_180031413
0x180031301  mov     r10d, edi
0x180031304  mov     r11, rcx
0x180031307  test    r8, r8
0x18003130a  jz      short loc_180031330
0x18003130c  movzx   eax, word ptr [r8]
0x180031310  test    ax, ax
0x180031313  jz      short loc_180031330
0x180031315  cmp     rdx, 2
0x180031319  jbe     loc_1800313FC
0x18003131f  mov     [rcx], ax
0x180031322  lea     r10d, [rdi+2]
0x180031326  mov     word ptr [rcx+2], 3Ah ; ':'
0x18003132c  lea     r11, [rcx+4]
0x180031330  test    r9, r9
0x180031333  jz      short loc_180031384
0x180031335  cmp     [r9], di
0x180031339  jz      short loc_180031384
0x18003133b  inc     r10
0x18003133e  cmp     r10, rdx
0x180031341  jnb     loc_1800313FC
0x180031347  movzx   eax, word ptr [r9]
0x18003134b  mov     rcx, r9
0x18003134e  mov     [r11], ax
0x180031352  add     r9, 2
0x180031356  add     r11, 2
0x18003135a  cmp     [r9], di
0x18003135e  jnz     short loc_18003133B
0x180031360  cmp     word ptr [rcx], 2Fh ; '/'
0x180031364  jz      short loc_180031384
0x180031366  mov     eax, 5Ch ; '\'
0x18003136b  cmp     [rcx], ax
0x18003136e  jz      short loc_180031384
0x180031370  inc     r10
0x180031373  cmp     r10, rdx
0x180031376  jnb     loc_1800313FC
0x18003137c  mov     [r11], ax
0x180031380  add     r11, 2
0x180031384  mov     rcx, [rsp+38h+Filename]
0x180031389  test    rcx, rcx
0x18003138c  jz      short loc_1800313AC
0x18003138e  jmp     short loc_1800313A7
0x180031390  inc     r10
0x180031393  cmp     r10, rdx
0x180031396  jnb     short loc_1800313FC
0x180031398  movzx   eax, word ptr [rcx]
0x18003139b  mov     [r11], ax
0x18003139f  add     r11, 2
0x1800313a3  add     rcx, 2
0x1800313a7  cmp     [rcx], di
0x1800313aa  jnz     short loc_180031390
0x1800313ac  mov     rcx, [rsp+38h+Ext]
0x1800313b1  test    rcx, rcx
0x1800313b4  jz      short loc_1800313F3
0x1800313b6  cmp     [rcx], di
0x1800313b9  jz      short loc_1800313F3
0x1800313bb  mov     eax, 2Eh ; '.'
0x1800313c0  cmp     [rcx], ax
0x1800313c3  jz      short loc_1800313EE
0x1800313c5  inc     r10
0x1800313c8  cmp     r10, rdx
0x1800313cb  jnb     short loc_1800313FC
0x1800313cd  mov     [r11], ax
0x1800313d1  add     r11, 2
0x1800313d5  jmp     short loc_1800313EE
0x1800313d7  inc     r10
0x1800313da  cmp     r10, rdx
0x1800313dd  jnb     short loc_1800313FC
0x1800313df  movzx   eax, word ptr [rcx]
0x1800313e2  mov     [r11], ax
0x1800313e6  add     r11, 2
0x1800313ea  add     rcx, 2
0x1800313ee  cmp     [rcx], di
0x1800313f1  jnz     short loc_1800313D7
0x1800313f3  lea     rax, [r10+1]
0x1800313f7  cmp     rax, rdx
0x1800313fa  jbe     short loc_18003140B
0x1800313fc  mov     [rbx], di
0x1800313ff  call    _errno
0x180031404  mov     ebx, 22h ; '"'
0x180031409  jmp     short loc_18003141D
0x18003140b  mov     [r11], di
0x18003140f  xor     eax, eax
0x180031411  jmp     short loc_180031435
0x180031413  call    _errno
0x180031418  mov     ebx, 16h
0x18003141d  xor     r9d, r9d; LineNo
0x180031420  mov     [rsp+38h+Reserved], rdi; Reserved
0x180031425  xor     r8d, r8d; FileName
0x180031428  mov     [rax], ebx
0x18003142a  xor     edx, edx; FunctionName
0x18003142c  xor     ecx, ecx; Expression
0x18003142e  call    _invalid_parameter
0x180031433  mov     eax, ebx
0x180031435  mov     rbx, [rsp+38h+arg_0]
0x18003143a  add     rsp, 30h
0x18003143e  pop     rdi
0x18003143f  retn
```
