# write_text_ansi_nolock

- ea: `0x18035bf6c`
- end: `0x18035c073`
- name: `write_text_ansi_nolock`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18035c424`

## callees

- `0x18032f050`
- `0x18032f0b0`
- `0x18035bf6c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18035c040`
- `KERNEL32!GetLastError` at `0x18035c040`
- `KERNEL32!WriteFile` at `0x18035c024`
- `KERNEL32!WriteFile` at `0x18035c024`

## pseudocode

```c
__int64 __fastcall write_text_ansi_nolock(__int64 a1, int a2, char *a3, int a4)
{
  unsigned __int64 v5; // rbp
  char *v6; // rsi
  void *v7; // r14
  char *v8; // rbx
  char v9; // al
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5119]; // [rsp+40h] [rbp-1428h] BYREF
  char v15; // [rsp+143Fh] [rbp-29h] BYREF

  v5 = (unsigned __int64)&a3[a4];
  v6 = a3;
  v7 = *(void **)(_pioinfo[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)a3 < v5 )
  {
    while ( 1 )
    {
      v8 = Buffer;
      do
      {
        if ( (unsigned __int64)v6 >= v5 )
          break;
        v9 = *v6++;
        if ( v9 == 10 )
        {
          ++*(_DWORD *)(a1 + 8);
          *v8++ = 13;
        }
        *v8++ = v9;
      }
      while ( v8 < &v15 );
      NumberOfBytesWritten = 0;
      v10 = (_DWORD)v8 - (unsigned int)Buffer;
      if ( !WriteFile(v7, Buffer, v10, &NumberOfBytesWritten, 0) )
        break;
      v11 = NumberOfBytesWritten;
      *(_DWORD *)(a1 + 4) += NumberOfBytesWritten;
      if ( v11 < v10 || (unsigned __int64)v6 >= v5 )
        return a1;
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x18035bf6c  mov     [rsp+arg_0], rbx
0x18035bf71  mov     [rsp+arg_10], rbp
0x18035bf76  push    rsi
0x18035bf77  push    rdi
0x18035bf78  push    r14
0x18035bf7a  mov     eax, 1450h
0x18035bf7f  call    _alloca_probe
0x18035bf84  sub     rsp, rax
0x18035bf87  mov     rax, cs:__security_cookie
0x18035bf8e  xor     rax, rsp
0x18035bf91  mov     [rsp+1468h+var_28], rax
0x18035bf99  movsxd  r10, edx
0x18035bf9c  mov     rdi, rcx
0x18035bf9f  mov     rax, r10
0x18035bfa2  mov     ebp, r9d
0x18035bfa5  sar     rax, 6
0x18035bfa9  lea     rcx, __pioinfo
0x18035bfb0  and     r10d, 3Fh
0x18035bfb4  add     rbp, r8
0x18035bfb7  mov     rsi, r8
0x18035bfba  mov     rax, [rcx+rax*8]
0x18035bfbe  lea     rdx, [r10+r10*8]
0x18035bfc2  mov     r14, [rax+rdx*8+28h]
0x18035bfc7  xor     eax, eax
0x18035bfc9  mov     [rdi], rax
0x18035bfcc  mov     [rdi+8], eax
0x18035bfcf  cmp     r8, rbp
0x18035bfd2  jnb     short loc_18035C048
0x18035bfd4  lea     rbx, [rsp+1468h+Buffer]
0x18035bfd9  cmp     rsi, rbp
0x18035bfdc  jnb     short loc_18035C002
0x18035bfde  mov     al, [rsi]
0x18035bfe0  inc     rsi
0x18035bfe3  cmp     al, 0Ah
0x18035bfe5  jnz     short loc_18035BFF0
0x18035bfe7  inc     dword ptr [rdi+8]
0x18035bfea  mov     byte ptr [rbx], 0Dh
0x18035bfed  inc     rbx
0x18035bff0  mov     [rbx], al
0x18035bff2  inc     rbx
0x18035bff5  lea     rax, [rsp+1468h+var_29]
0x18035bffd  cmp     rbx, rax
0x18035c000  jb      short loc_18035BFD9
0x18035c002  and     [rsp+1468h+NumberOfBytesWritten], 0
0x18035c007  lea     rax, [rsp+1468h+Buffer]
0x18035c00c  and     [rsp+1468h+var_1448], 0
0x18035c012  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18035c017  sub     ebx, eax
0x18035c019  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x18035c01e  mov     r8d, ebx; nNumberOfBytesToWrite
0x18035c021  mov     rcx, r14; hFile
0x18035c024  call    cs:__imp_WriteFile
0x18035c02a  test    eax, eax
0x18035c02c  jz      short loc_18035C040
0x18035c02e  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x18035c032  add     [rdi+4], eax
0x18035c035  cmp     eax, ebx
0x18035c037  jb      short loc_18035C048
0x18035c039  cmp     rsi, rbp
0x18035c03c  jb      short loc_18035BFD4
0x18035c03e  jmp     short loc_18035C048
0x18035c040  call    cs:__imp_GetLastError
0x18035c046  mov     [rdi], eax
0x18035c048  mov     rax, rdi
0x18035c04b  mov     rcx, [rsp+1468h+var_28]
0x18035c053  xor     rcx, rsp; StackCookie
0x18035c056  call    __security_check_cookie
0x18035c05b  lea     r11, [rsp+1468h+var_18]
0x18035c063  mov     rbx, [r11+20h]
0x18035c067  mov     rbp, [r11+30h]
0x18035c06b  mov     rsp, r11
0x18035c06e  pop     r14
0x18035c070  pop     rdi
0x18035c071  pop     rsi
0x18035c072  retn
```
