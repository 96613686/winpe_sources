# GetActivityLoggingArray

- ea: `0x180031c84`
- end: `0x180031de8`
- name: `GetActivityLoggingArray`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180032b90`

## callees

- `0x180031a70`
- `0x180031b08`
- `0x180031c84`

## import_xrefs

- `msvcrt!malloc` at `0x180031c9e`
- `msvcrt!malloc` at `0x180031c9e`

## string_xrefs

- `0x180031d52`: `Delete`
- `0x180031d0a`: `Write`
- `0x180031cc0`: `Mount`
- `0x180031d2e`: `Create`

## pseudocode

```c
__int64 __fastcall GetActivityLoggingArray(char a1, _QWORD *a2, unsigned int *a3)
{
  char *v6; // rax
  char *v7; // rsi
  int v9; // edi
  unsigned int v10; // ebx

  v6 = (char *)malloc(0x40u);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  v10 = 0;
  if ( (a1 & 1) != 0 )
  {
    v9 = AllocateAndCopyStringp(v6, L"Mount");
    if ( v9 < 0 )
      goto LABEL_29;
    v10 = 1;
  }
  if ( (a1 & 4) != 0 )
  {
    v9 = AllocateAndCopyStringp(&v7[8 * v10], L"Read");
    if ( v9 < 0 )
      goto LABEL_29;
    ++v10;
  }
  if ( (a1 & 8) != 0 )
  {
    v9 = AllocateAndCopyStringp(&v7[8 * v10], L"Write");
    if ( v9 < 0 )
      goto LABEL_29;
    ++v10;
  }
  if ( (a1 & 0x10) != 0 )
  {
    v9 = AllocateAndCopyStringp(&v7[8 * v10], L"Create");
    if ( v9 < 0 )
      goto LABEL_29;
    ++v10;
  }
  if ( (a1 & 0x20) != 0 )
  {
    v9 = AllocateAndCopyStringp(&v7[8 * v10], L"Delete");
    if ( v9 < 0 )
      goto LABEL_29;
    ++v10;
  }
  if ( (a1 & 0x40) != 0 )
  {
    v9 = AllocateAndCopyStringp(&v7[8 * v10], L"Lock");
    if ( v9 < 0 )
      goto LABEL_29;
    ++v10;
  }
  if ( a1 < 0 )
  {
    v9 = AllocateAndCopyStringp(&v7[8 * v10], L"Unlock");
    if ( v9 < 0 )
      goto LABEL_29;
    ++v10;
  }
  if ( !v10 )
  {
    v9 = AllocateAndCopyStringp(v7, L"none");
    if ( v9 >= 0 )
    {
      v10 = 1;
      goto LABEL_27;
    }
LABEL_29:
    FreeStringArray(v7, v10);
    return (unsigned int)v9;
  }
LABEL_27:
  *a2 = v7;
  *a3 = v10;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180031c84  push    rbx
0x180031c86  push    rbp
0x180031c87  push    rsi
0x180031c88  push    rdi
0x180031c89  push    r14
0x180031c8b  push    r15
0x180031c8d  sub     rsp, 28h
0x180031c91  mov     ebp, ecx
0x180031c93  mov     r14, r8
0x180031c96  mov     ecx, 40h ; '@'; Size
0x180031c9b  mov     r15, rdx
0x180031c9e  call    cs:__imp_malloc
0x180031ca4  mov     rsi, rax
0x180031ca7  test    rax, rax
0x180031caa  jnz     short loc_180031CB6
0x180031cac  mov     eax, 8007000Eh
0x180031cb1  jmp     loc_180031DCF
0x180031cb6  xor     edi, edi
0x180031cb8  xor     ebx, ebx
0x180031cba  test    bpl, 1
0x180031cbe  jz      short loc_180031CDE
0x180031cc0  lea     rdx, aMount_0; "Mount"
0x180031cc7  mov     rcx, rsi
0x180031cca  call    AllocateAndCopyStringp
0x180031ccf  mov     edi, eax
0x180031cd1  test    eax, eax
0x180031cd3  js      loc_180031DDC
0x180031cd9  mov     ebx, 1
0x180031cde  test    bpl, 4
0x180031ce2  jz      short loc_180031D02
0x180031ce4  mov     eax, ebx
0x180031ce6  lea     rdx, aRead; "Read"
0x180031ced  lea     rcx, [rsi+rax*8]
0x180031cf1  call    AllocateAndCopyStringp
0x180031cf6  mov     edi, eax
0x180031cf8  test    eax, eax
0x180031cfa  js      loc_180031DDC
0x180031d00  inc     ebx
0x180031d02  test    bpl, 8
0x180031d06  jz      short loc_180031D26
0x180031d08  mov     eax, ebx
0x180031d0a  lea     rdx, aWrite; "Write"
0x180031d11  lea     rcx, [rsi+rax*8]
0x180031d15  call    AllocateAndCopyStringp
0x180031d1a  mov     edi, eax
0x180031d1c  test    eax, eax
0x180031d1e  js      loc_180031DDC
0x180031d24  inc     ebx
0x180031d26  test    bpl, 10h
0x180031d2a  jz      short loc_180031D4A
0x180031d2c  mov     eax, ebx
0x180031d2e  lea     rdx, aCreate; "Create"
0x180031d35  lea     rcx, [rsi+rax*8]
0x180031d39  call    AllocateAndCopyStringp
0x180031d3e  mov     edi, eax
0x180031d40  test    eax, eax
0x180031d42  js      loc_180031DDC
0x180031d48  inc     ebx
0x180031d4a  test    bpl, 20h
0x180031d4e  jz      short loc_180031D6A
0x180031d50  mov     eax, ebx
0x180031d52  lea     rdx, aDelete; "Delete"
0x180031d59  lea     rcx, [rsi+rax*8]
0x180031d5d  call    AllocateAndCopyStringp
0x180031d62  mov     edi, eax
0x180031d64  test    eax, eax
0x180031d66  js      short loc_180031DDC
0x180031d68  inc     ebx
0x180031d6a  test    bpl, 40h
0x180031d6e  jz      short loc_180031D8A
0x180031d70  mov     eax, ebx
0x180031d72  lea     rdx, aLock; "Lock"
0x180031d79  lea     rcx, [rsi+rax*8]
0x180031d7d  call    AllocateAndCopyStringp
0x180031d82  mov     edi, eax
0x180031d84  test    eax, eax
0x180031d86  js      short loc_180031DDC
0x180031d88  inc     ebx
0x180031d8a  test    bpl, bpl
0x180031d8d  jns     short loc_180031DA9
0x180031d8f  mov     eax, ebx
0x180031d91  lea     rdx, aUnlock; "Unlock"
0x180031d98  lea     rcx, [rsi+rax*8]
0x180031d9c  call    AllocateAndCopyStringp
0x180031da1  mov     edi, eax
0x180031da3  test    eax, eax
0x180031da5  js      short loc_180031DDC
0x180031da7  inc     ebx
0x180031da9  test    ebx, ebx
0x180031dab  jnz     short loc_180031DC7
0x180031dad  lea     rdx, aNone; "none"
0x180031db4  mov     rcx, rsi
0x180031db7  call    AllocateAndCopyStringp
0x180031dbc  mov     edi, eax
0x180031dbe  test    eax, eax
0x180031dc0  js      short loc_180031DDC
0x180031dc2  mov     ebx, 1
0x180031dc7  mov     [r15], rsi
0x180031dca  mov     [r14], ebx
0x180031dcd  mov     eax, edi
0x180031dcf  add     rsp, 28h
0x180031dd3  pop     r15
0x180031dd5  pop     r14
0x180031dd7  pop     rdi
0x180031dd8  pop     rsi
0x180031dd9  pop     rbp
0x180031dda  pop     rbx
0x180031ddb  retn
0x180031ddc  mov     edx, ebx
0x180031dde  mov     rcx, rsi
0x180031de1  call    FreeStringArray
0x180031de6  jmp     short loc_180031DCD
```
