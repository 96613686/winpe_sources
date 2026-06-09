# write_text_utf8_nolock(int,char const * const,uint)

- ea: `0x140147d4c`
- end: `0x140147ec0`
- name: `?write_text_utf8_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `372`
- prototype: `__int64 __fastcall(__int64, int, __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140147244`

## callees

- `0x14012fc30`
- `0x14012fc90`
- `0x140147d4c`
- `0x1401577ec`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140147e89`
- `KERNEL32!GetLastError` at `0x140147e89`
- `KERNEL32!WriteFile` at `0x140147e64`
- `KERNEL32!WriteFile` at `0x140147e64`

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
  v8 = *(void **)(qword_14038C5D0[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
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
0x140147d4c  mov     [rsp+arg_0], rbx
0x140147d51  mov     [rsp+arg_10], rbp
0x140147d56  push    rsi
0x140147d57  push    rdi
0x140147d58  push    r12
0x140147d5a  push    r14
0x140147d5c  push    r15
0x140147d5e  mov     eax, 1470h
0x140147d63  call    __alloca_probe
0x140147d68  sub     rsp, rax
0x140147d6b  mov     rax, cs:__security_cookie
0x140147d72  xor     rax, rsp
0x140147d75  mov     [rsp+1498h+var_38], rax
0x140147d7d  movsxd  r10, edx
0x140147d80  mov     rbx, rcx
0x140147d83  mov     rax, r10
0x140147d86  mov     r14d, r9d
0x140147d89  sar     rax, 6
0x140147d8d  lea     rcx, qword_14038C5D0
0x140147d94  and     r10d, 3Fh
0x140147d98  add     r14, r8
0x140147d9b  mov     r15, r8
0x140147d9e  mov     rdi, r8
0x140147da1  mov     rax, [rcx+rax*8]
0x140147da5  lea     rdx, [r10+r10*8]
0x140147da9  mov     r12, [rax+rdx*8+28h]
0x140147dae  xor     eax, eax
0x140147db0  mov     [rbx], rax
0x140147db3  mov     [rbx+8], eax
0x140147db6  cmp     r8, r14
0x140147db9  jnb     loc_140147E91
0x140147dbf  lea     r9, [rsp+1498h+var_1448]
0x140147dc4  cmp     rdi, r14
0x140147dc7  jnb     short loc_140147DF5
0x140147dc9  movzx   eax, word ptr [rdi]
0x140147dcc  add     rdi, 2
0x140147dd0  cmp     ax, 0Ah
0x140147dd4  jnz     short loc_140147DE0
0x140147dd6  mov     word ptr [r9], 0Dh
0x140147ddc  add     r9, 2
0x140147de0  mov     [r9], ax
0x140147de4  add     r9, 2
0x140147de8  lea     rax, [rsp+1498h+var_DA0]
0x140147df0  cmp     r9, rax
0x140147df3  jb      short loc_140147DC4
0x140147df5  and     [rsp+1498h+var_1460], 0
0x140147dfb  lea     rax, [rsp+1498h+var_1448]
0x140147e00  and     [rsp+1498h+var_1468], 0
0x140147e06  lea     r8, [rsp+1498h+var_1448]
0x140147e0b  sub     r9, rax
0x140147e0e  mov     [rsp+1498h+var_1470], 0D55h
0x140147e16  lea     rax, [rsp+1498h+Overlapped]
0x140147e1e  sar     r9, 1
0x140147e21  xor     edx, edx
0x140147e23  mov     [rsp+1498h+lpOverlapped], rax; lpOverlapped
0x140147e28  mov     ecx, 0FDE9h
0x140147e2d  call    __acrt_WideCharToMultiByte
0x140147e32  mov     ebp, eax
0x140147e34  test    eax, eax
0x140147e36  jz      short loc_140147E89
0x140147e38  xor     esi, esi
0x140147e3a  test    eax, eax
0x140147e3c  jz      short loc_140147E76
0x140147e3e  and     [rsp+1498h+NumberOfBytesWritten], 0
0x140147e43  lea     rdx, [rsp+1498h+Overlapped]
0x140147e4b  and     [rsp+1498h+lpOverlapped], 0
0x140147e51  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140147e56  mov     ecx, esi
0x140147e58  mov     r8d, ebp
0x140147e5b  add     rdx, rcx; lpBuffer
0x140147e5e  sub     r8d, esi; nNumberOfBytesToWrite
0x140147e61  mov     rcx, r12; hFile
0x140147e64  call    cs:WriteFile
0x140147e6a  test    eax, eax
0x140147e6c  jz      short loc_140147E89
0x140147e6e  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x140147e72  cmp     esi, ebp
0x140147e74  jb      short loc_140147E3E
0x140147e76  mov     eax, edi
0x140147e78  sub     eax, r15d
0x140147e7b  mov     [rbx+4], eax
0x140147e7e  cmp     rdi, r14
0x140147e81  jb      loc_140147DBF
0x140147e87  jmp     short loc_140147E91
0x140147e89  call    cs:__imp_GetLastError
0x140147e8f  mov     [rbx], eax
0x140147e91  mov     rax, rbx
0x140147e94  mov     rcx, [rsp+1498h+var_38]
0x140147e9c  xor     rcx, rsp; StackCookie
0x140147e9f  call    __security_check_cookie
0x140147ea4  lea     r11, [rsp+1498h+var_28]
0x140147eac  mov     rbx, [r11+30h]
0x140147eb0  mov     rbp, [r11+40h]
0x140147eb4  mov     rsp, r11
0x140147eb7  pop     r15
0x140147eb9  pop     r14
0x140147ebb  pop     r12
0x140147ebd  pop     rdi
0x140147ebe  pop     rsi
0x140147ebf  retn
```
