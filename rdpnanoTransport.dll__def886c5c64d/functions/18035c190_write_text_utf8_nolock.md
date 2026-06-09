# write_text_utf8_nolock

- ea: `0x18035c190`
- end: `0x18035c304`
- name: `write_text_utf8_nolock`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18035c424`

## callees

- `0x18032f050`
- `0x18032f0b0`
- `0x180359e98`
- `0x18035c190`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18035c2cd`
- `KERNEL32!GetLastError` at `0x18035c2cd`
- `KERNEL32!WriteFile` at `0x18035c2a8`
- `KERNEL32!WriteFile` at `0x18035c2a8`

## pseudocode

```c
__int64 __fastcall write_text_utf8_nolock(__int64 a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // r14
  int v6; // r15d
  __int16 *v7; // rdi
  void *v8; // r12
  char *v9; // r9
  __int16 v10; // ax
  unsigned int v11; // ebp
  unsigned int v12; // esi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-1458h] BYREF
  _BYTE v15[1704]; // [rsp+50h] [rbp-1448h] BYREF
  char v16; // [rsp+6F8h] [rbp-DA0h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+700h] [rbp-D98h] BYREF

  v5 = (unsigned __int64)a3 + a4;
  v6 = (int)a3;
  v7 = a3;
  v8 = *(void **)(_pioinfo[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)a3 < v5 )
  {
LABEL_2:
    v9 = v15;
    do
    {
      if ( (unsigned __int64)v7 >= v5 )
        break;
      v10 = *v7++;
      if ( v10 == 10 )
      {
        *(_WORD *)v9 = 13;
        v9 += 2;
      }
      *(_WORD *)v9 = v10;
      v9 += 2;
    }
    while ( v9 < &v16 );
    v11 = _acrt_WideCharToMultiByte(65001, 0, (unsigned int)v15, (v9 - v15) >> 1, (unsigned int)&Overlapped, 3413, 0, 0);
    if ( v11 )
    {
      v12 = 0;
      while ( 1 )
      {
        NumberOfBytesWritten = 0;
        if ( !WriteFile(v8, (char *)&Overlapped + v12, v11 - v12, &NumberOfBytesWritten, 0) )
          break;
        v12 += NumberOfBytesWritten;
        if ( v12 >= v11 )
        {
          *(_DWORD *)(a1 + 4) = (_DWORD)v7 - v6;
          if ( (unsigned __int64)v7 < v5 )
            goto LABEL_2;
          return a1;
        }
      }
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x18035c190  mov     [rsp+arg_0], rbx
0x18035c195  mov     [rsp+arg_10], rbp
0x18035c19a  push    rsi
0x18035c19b  push    rdi
0x18035c19c  push    r12
0x18035c19e  push    r14
0x18035c1a0  push    r15
0x18035c1a2  mov     eax, 1470h
0x18035c1a7  call    _alloca_probe
0x18035c1ac  sub     rsp, rax
0x18035c1af  mov     rax, cs:__security_cookie
0x18035c1b6  xor     rax, rsp
0x18035c1b9  mov     [rsp+1498h+var_38], rax
0x18035c1c1  movsxd  r10, edx
0x18035c1c4  mov     rbx, rcx
0x18035c1c7  mov     rax, r10
0x18035c1ca  mov     r14d, r9d
0x18035c1cd  sar     rax, 6
0x18035c1d1  lea     rcx, __pioinfo
0x18035c1d8  and     r10d, 3Fh
0x18035c1dc  add     r14, r8
0x18035c1df  mov     r15, r8
0x18035c1e2  mov     rdi, r8
0x18035c1e5  mov     rax, [rcx+rax*8]
0x18035c1e9  lea     rdx, [r10+r10*8]
0x18035c1ed  mov     r12, [rax+rdx*8+28h]
0x18035c1f2  xor     eax, eax
0x18035c1f4  mov     [rbx], rax
0x18035c1f7  mov     [rbx+8], eax
0x18035c1fa  cmp     r8, r14
0x18035c1fd  jnb     loc_18035C2D5
0x18035c203  lea     r9, [rsp+1498h+var_1448]
0x18035c208  cmp     rdi, r14
0x18035c20b  jnb     short loc_18035C239
0x18035c20d  movzx   eax, word ptr [rdi]
0x18035c210  add     rdi, 2
0x18035c214  cmp     ax, 0Ah
0x18035c218  jnz     short loc_18035C224
0x18035c21a  mov     word ptr [r9], 0Dh
0x18035c220  add     r9, 2
0x18035c224  mov     [r9], ax
0x18035c228  add     r9, 2
0x18035c22c  lea     rax, [rsp+1498h+var_DA0]
0x18035c234  cmp     r9, rax
0x18035c237  jb      short loc_18035C208
0x18035c239  and     [rsp+1498h+var_1460], 0
0x18035c23f  lea     rax, [rsp+1498h+var_1448]
0x18035c244  and     [rsp+1498h+var_1468], 0
0x18035c24a  lea     r8, [rsp+1498h+var_1448]
0x18035c24f  sub     r9, rax
0x18035c252  mov     [rsp+1498h+var_1470], 0D55h
0x18035c25a  lea     rax, [rsp+1498h+Overlapped]
0x18035c262  sar     r9, 1
0x18035c265  xor     edx, edx
0x18035c267  mov     [rsp+1498h+lpOverlapped], rax; lpOverlapped
0x18035c26c  mov     ecx, 0FDE9h
0x18035c271  call    __acrt_WideCharToMultiByte
0x18035c276  mov     ebp, eax
0x18035c278  test    eax, eax
0x18035c27a  jz      short loc_18035C2CD
0x18035c27c  xor     esi, esi
0x18035c27e  test    eax, eax
0x18035c280  jz      short loc_18035C2BA
0x18035c282  and     [rsp+1498h+NumberOfBytesWritten], 0
0x18035c287  lea     rdx, [rsp+1498h+Overlapped]
0x18035c28f  and     [rsp+1498h+lpOverlapped], 0
0x18035c295  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18035c29a  mov     ecx, esi
0x18035c29c  mov     r8d, ebp
0x18035c29f  add     rdx, rcx; lpBuffer
0x18035c2a2  sub     r8d, esi; nNumberOfBytesToWrite
0x18035c2a5  mov     rcx, r12; hFile
0x18035c2a8  call    cs:__imp_WriteFile
0x18035c2ae  test    eax, eax
0x18035c2b0  jz      short loc_18035C2CD
0x18035c2b2  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x18035c2b6  cmp     esi, ebp
0x18035c2b8  jb      short loc_18035C282
0x18035c2ba  mov     eax, edi
0x18035c2bc  sub     eax, r15d
0x18035c2bf  mov     [rbx+4], eax
0x18035c2c2  cmp     rdi, r14
0x18035c2c5  jb      loc_18035C203
0x18035c2cb  jmp     short loc_18035C2D5
0x18035c2cd  call    cs:__imp_GetLastError
0x18035c2d3  mov     [rbx], eax
0x18035c2d5  mov     rax, rbx
0x18035c2d8  mov     rcx, [rsp+1498h+var_38]
0x18035c2e0  xor     rcx, rsp; StackCookie
0x18035c2e3  call    __security_check_cookie
0x18035c2e8  lea     r11, [rsp+1498h+var_28]
0x18035c2f0  mov     rbx, [r11+30h]
0x18035c2f4  mov     rbp, [r11+40h]
0x18035c2f8  mov     rsp, r11
0x18035c2fb  pop     r15
0x18035c2fd  pop     r14
0x18035c2ff  pop     r12
0x18035c301  pop     rdi
0x18035c302  pop     rsi
0x18035c303  retn
```
