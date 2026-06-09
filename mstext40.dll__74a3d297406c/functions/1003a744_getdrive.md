# __getdrive

- ea: `0x1003a744`
- end: `0x1003a813`
- name: `__getdrive`
- size: `207`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x10034055`
- `0x10034242`

## callees

- `0x1002b81a`
- `0x1002d6dc`
- `0x1002df32`
- `0x100336b6`
- `0x1003a744`

## import_xrefs

- `KERNEL32!GetCurrentDirectoryW` at `0x1003a770`
- `KERNEL32!GetCurrentDirectoryW` at `0x1003a7bd`
- `KERNEL32!GetCurrentDirectoryW` at `0x1003a770`
- `KERNEL32!GetCurrentDirectoryW` at `0x1003a7bd`

## pseudocode

```c
int __cdecl _getdrive()
{
  WCHAR *v0; // esi
  int v1; // ebx
  signed int CurrentDirectoryW; // edi
  WCHAR *v3; // eax
  unsigned int v4; // eax
  int v6; // [esp+10h] [ebp-214h]
  WCHAR Buffer[262]; // [esp+14h] [ebp-210h] BYREF

  v0 = Buffer;
  v1 = 0;
  v6 = 0;
  CurrentDirectoryW = GetCurrentDirectoryW(0x105u, Buffer);
  if ( CurrentDirectoryW > 260 )
  {
    v3 = (WCHAR *)_calloc_crt(CurrentDirectoryW + 1, 2);
    v0 = v3;
    if ( v3 )
    {
      v6 = 1;
      CurrentDirectoryW = GetCurrentDirectoryW(CurrentDirectoryW + 1, v3);
    }
    else
    {
      CurrentDirectoryW = 0;
      *_errno() = 12;
    }
  }
  if ( CurrentDirectoryW )
  {
    if ( v0[1] == 58 )
    {
      v4 = *v0;
      if ( v4 >= 0x61 && v4 <= 0x7A )
        v4 -= 32;
      v1 = v4 - 64;
    }
  }
  else
  {
    *_errno() = 12;
  }
  if ( v6 )
    free(v0);
  return v1;
}

```

## disassembly

```asm
0x1003a744  push    ebp
0x1003a745  mov     ebp, esp
0x1003a747  sub     esp, 218h
0x1003a74d  mov     eax, ___security_cookie
0x1003a752  xor     eax, ebp
0x1003a754  mov     [ebp+var_4], eax
0x1003a757  push    ebx
0x1003a758  push    esi
0x1003a759  push    edi
0x1003a75a  lea     esi, [ebp+Buffer]
0x1003a760  xor     ebx, ebx
0x1003a762  mov     eax, esi
0x1003a764  mov     [ebp+var_214], ebx
0x1003a76a  push    eax; lpBuffer
0x1003a76b  push    105h; nBufferLength
0x1003a770  call    ds:__imp__GetCurrentDirectoryW@8
0x1003a776  mov     edi, eax
0x1003a778  cmp     edi, 104h
0x1003a77e  jle     short loc_1003A7C5
0x1003a780  lea     eax, [edi+1]
0x1003a783  push    2
0x1003a785  push    eax
0x1003a786  mov     [ebp+nBufferLength], eax
0x1003a78c  call    __calloc_crt
0x1003a791  mov     esi, eax
0x1003a793  pop     ecx
0x1003a794  pop     ecx
0x1003a795  test    esi, esi
0x1003a797  jnz     short loc_1003A7A8
0x1003a799  call    __errno
0x1003a79e  mov     edi, ebx
0x1003a7a0  mov     dword ptr [eax], 0Ch
0x1003a7a6  jmp     short loc_1003A7C5
0x1003a7a8  mov     [ebp+var_214], 1
0x1003a7b2  test    edi, edi
0x1003a7b4  jz      short loc_1003A7E5
0x1003a7b6  push    esi; lpBuffer
0x1003a7b7  push    [ebp+nBufferLength]; nBufferLength
0x1003a7bd  call    ds:__imp__GetCurrentDirectoryW@8
0x1003a7c3  mov     edi, eax
0x1003a7c5  test    edi, edi
0x1003a7c7  jz      short loc_1003A7E5
0x1003a7c9  cmp     word ptr [esi+2], 3Ah ; ':'
0x1003a7ce  jnz     short loc_1003A7F0
0x1003a7d0  movzx   eax, word ptr [esi]
0x1003a7d3  cmp     eax, 61h ; 'a'
0x1003a7d6  jb      short loc_1003A7E0
0x1003a7d8  cmp     eax, 7Ah ; 'z'
0x1003a7db  ja      short loc_1003A7E0
0x1003a7dd  sub     eax, 20h ; ' '
0x1003a7e0  lea     ebx, [eax-40h]
0x1003a7e3  jmp     short loc_1003A7F0
0x1003a7e5  call    __errno
0x1003a7ea  mov     dword ptr [eax], 0Ch
0x1003a7f0  cmp     [ebp+var_214], 0
0x1003a7f7  jz      short loc_1003A800
0x1003a7f9  push    esi; Block
0x1003a7fa  call    _free
0x1003a7ff  pop     ecx
0x1003a800  mov     ecx, [ebp+var_4]
0x1003a803  mov     eax, ebx
0x1003a805  pop     edi
0x1003a806  pop     esi
0x1003a807  xor     ecx, ebp; StackCookie
0x1003a809  pop     ebx
0x1003a80a  call    @__security_check_cookie@4
0x1003a80f  mov     esp, ebp
0x1003a811  pop     ebp
0x1003a812  retn
```
