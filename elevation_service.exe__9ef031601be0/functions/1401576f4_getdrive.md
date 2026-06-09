# _getdrive

- ea: `0x1401576f4`
- end: `0x1401577ea`
- name: `_getdrive`
- size: `246`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14015a434`

## callees

- `0x14008d6b0`
- `0x14008d780`
- `0x14012fc90`
- `0x14013fd08`
- `0x1401576f4`
- `0x1401616e0`

## import_xrefs

- `KERNEL32!GetCurrentDirectoryW` at `0x140157734`
- `KERNEL32!GetCurrentDirectoryW` at `0x140157786`
- `KERNEL32!GetCurrentDirectoryW` at `0x140157734`
- `KERNEL32!GetCurrentDirectoryW` at `0x140157786`

## pseudocode

```c
int __cdecl getdrive()
{
  DWORD CurrentDirectoryW; // eax
  int v1; // edi
  int v2; // edi
  DWORD v3; // esi
  WCHAR *v4; // rax
  __int64 v5; // rdx
  int v6; // ecx
  WCHAR *v7; // rbx
  int v8; // ecx
  int v9; // edi
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  memset(Buffer, 0, 0x20Au);
  CurrentDirectoryW = GetCurrentDirectoryW(0x105u, Buffer);
  if ( CurrentDirectoryW > 0x104 )
  {
    v3 = CurrentDirectoryW + 1;
    v4 = (WCHAR *)sub_14008D780(CurrentDirectoryW + 1, 2);
    v1 = 0;
    v7 = v4;
    if ( v4 && GetCurrentDirectoryW(v3, v4) )
    {
      if ( *v7 && v7[1] == 58 )
      {
        v8 = *v7;
        v9 = v8 - 32;
        if ( (unsigned int)(v8 - 97) > 0x19 )
          v9 = *v7;
        v1 = v9 - 64;
      }
    }
    else
    {
      *(_DWORD *)sub_14013FD08(v6, v5) = 12;
    }
    sub_14008D6B0(v7);
  }
  else
  {
    v1 = 0;
    if ( Buffer[0] && Buffer[1] == 58 )
    {
      v2 = Buffer[0] - 32;
      if ( (unsigned int)Buffer[0] - 97 > 0x19 )
        v2 = Buffer[0];
      return v2 - 64;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1401576f4  mov     [rsp+arg_0], rbx
0x1401576f9  mov     [rsp+arg_8], rsi
0x1401576fe  push    rdi
0x1401576ff  sub     rsp, 240h
0x140157706  mov     rax, cs:__security_cookie
0x14015770d  xor     rax, rsp
0x140157710  mov     [rsp+248h+var_18], rax
0x140157718  xor     edx, edx; Val
0x14015771a  lea     rcx, [rsp+248h+Buffer]; Dst
0x14015771f  mov     r8d, 20Ah; Size
0x140157725  call    memset
0x14015772a  lea     rdx, [rsp+248h+Buffer]; lpBuffer
0x14015772f  mov     ecx, 105h; nBufferLength
0x140157734  call    cs:GetCurrentDirectoryW
0x14015773a  cmp     eax, 104h
0x14015773f  ja      short loc_140157768
0x140157741  xor     edi, edi
0x140157743  cmp     [rsp+248h+Buffer], di
0x140157748  jz      short loc_1401577C3
0x14015774a  cmp     [rsp+248h+var_226], 3Ah ; ':'
0x140157750  jnz     short loc_1401577C3
0x140157752  movzx   ecx, [rsp+248h+Buffer]
0x140157757  lea     eax, [rcx-61h]
0x14015775a  cmp     eax, 19h
0x14015775d  lea     edi, [rcx-20h]
0x140157760  cmova   edi, ecx
0x140157763  sub     edi, 40h ; '@'
0x140157766  jmp     short loc_1401577C3
0x140157768  lea     esi, [rax+1]
0x14015776b  mov     edx, 2
0x140157770  mov     ecx, esi
0x140157772  call    sub_14008D780
0x140157777  xor     edi, edi
0x140157779  mov     rbx, rax
0x14015777c  test    rax, rax
0x14015777f  jz      short loc_140157790
0x140157781  mov     rdx, rax; lpBuffer
0x140157784  mov     ecx, esi; nBufferLength
0x140157786  call    cs:GetCurrentDirectoryW
0x14015778c  test    eax, eax
0x14015778e  jnz     short loc_14015779D
0x140157790  call    sub_14013FD08
0x140157795  mov     dword ptr [rax], 0Ch
0x14015779b  jmp     short loc_1401577BB
0x14015779d  cmp     [rbx], di
0x1401577a0  jz      short loc_1401577BB
0x1401577a2  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1401577a7  jnz     short loc_1401577BB
0x1401577a9  movzx   ecx, word ptr [rbx]
0x1401577ac  lea     eax, [rcx-61h]
0x1401577af  cmp     eax, 19h
0x1401577b2  lea     edi, [rcx-20h]
0x1401577b5  cmova   edi, ecx
0x1401577b8  sub     edi, 40h ; '@'
0x1401577bb  mov     rcx, rbx
0x1401577be  call    sub_14008D6B0
0x1401577c3  mov     eax, edi
0x1401577c5  mov     rcx, [rsp+248h+var_18]
0x1401577cd  xor     rcx, rsp; StackCookie
0x1401577d0  call    __security_check_cookie
0x1401577d5  lea     r11, [rsp+248h+var_8]
0x1401577dd  mov     rbx, [r11+10h]
0x1401577e1  mov     rsi, [r11+18h]
0x1401577e5  mov     rsp, r11
0x1401577e8  pop     rdi
0x1401577e9  retn
```
