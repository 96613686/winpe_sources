# write_text_utf16le_nolock

- ea: `0x18001c878`
- end: `0x18001c997`
- name: `write_text_utf16le_nolock`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001cc4c`

## callees

- `0x180018ac0`
- `0x18001c878`
- `0x180024ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c964`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001c948`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001c948`

## pseudocode

```c
__int64 __fastcall write_text_utf16le_nolock(__int64 a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // rbp
  __int16 *v6; // rsi
  void *v7; // r14
  char *v8; // rbx
  __int16 v9; // ax
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5118]; // [rsp+40h] [rbp-1428h] BYREF
  __int16 v15; // [rsp+143Eh] [rbp-2Ah] BYREF

  v5 = (unsigned __int64)a3 + a4;
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
          *(_DWORD *)(a1 + 8) += 2;
          *(_WORD *)v8 = 13;
          v8 += 2;
        }
        *(_WORD *)v8 = v9;
        v8 += 2;
      }
      while ( v8 < (char *)&v15 );
      NumberOfBytesWritten = 0;
      v10 = 2 * ((v8 - Buffer) >> 1);
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
0x18001c878  mov     [rsp+arg_0], rbx
0x18001c87d  mov     [rsp+arg_10], rbp
0x18001c882  push    rsi
0x18001c883  push    rdi
0x18001c884  push    r14
0x18001c886  mov     eax, 1450h
0x18001c88b  call    _alloca_probe
0x18001c890  sub     rsp, rax
0x18001c893  mov     rax, cs:__security_cookie
0x18001c89a  xor     rax, rsp
0x18001c89d  mov     [rsp+1468h+var_28], rax
0x18001c8a5  mov     eax, edx
0x18001c8a7  movsxd  r10, edx
0x18001c8aa  and     eax, 3Fh
0x18001c8ad  sar     r10, 6
0x18001c8b1  mov     rdi, rcx
0x18001c8b4  mov     ebp, r9d
0x18001c8b7  lea     rcx, __pioinfo
0x18001c8be  add     rbp, r8
0x18001c8c1  mov     rsi, r8
0x18001c8c4  lea     rdx, [rax+rax*8]
0x18001c8c8  mov     rax, [rcx+r10*8]
0x18001c8cc  mov     r14, [rax+rdx*8+28h]
0x18001c8d1  xor     eax, eax
0x18001c8d3  mov     [rdi], rax
0x18001c8d6  mov     [rdi+8], eax
0x18001c8d9  cmp     r8, rbp
0x18001c8dc  jnb     loc_18001C96C
0x18001c8e2  lea     rbx, [rsp+1468h+Buffer]
0x18001c8e7  cmp     rsi, rbp
0x18001c8ea  jnb     short loc_18001C91A
0x18001c8ec  movzx   eax, word ptr [rsi]
0x18001c8ef  add     rsi, 2
0x18001c8f3  cmp     ax, 0Ah
0x18001c8f7  jnz     short loc_18001C906
0x18001c8f9  add     dword ptr [rdi+8], 2
0x18001c8fd  mov     word ptr [rbx], 0Dh
0x18001c902  add     rbx, 2
0x18001c906  mov     [rbx], ax
0x18001c909  add     rbx, 2
0x18001c90d  lea     rax, [rsp+1468h+var_2A]
0x18001c915  cmp     rbx, rax
0x18001c918  jb      short loc_18001C8E7
0x18001c91a  lea     rax, [rsp+1468h+Buffer]
0x18001c91f  mov     [rsp+1468h+NumberOfBytesWritten], 0
0x18001c927  sub     rbx, rax
0x18001c92a  mov     [rsp+1468h+lpOverlapped], 0; lpOverlapped
0x18001c933  sar     rbx, 1
0x18001c936  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001c93b  add     ebx, ebx
0x18001c93d  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x18001c942  mov     r8d, ebx; nNumberOfBytesToWrite
0x18001c945  mov     rcx, r14; hFile
0x18001c948  call    cs:__imp_WriteFile
0x18001c94e  test    eax, eax
0x18001c950  jz      short loc_18001C964
0x18001c952  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x18001c956  add     [rdi+4], eax
0x18001c959  cmp     eax, ebx
0x18001c95b  jb      short loc_18001C96C
0x18001c95d  cmp     rsi, rbp
0x18001c960  jb      short loc_18001C8E2
0x18001c962  jmp     short loc_18001C96C
0x18001c964  call    cs:__imp_GetLastError
0x18001c96a  mov     [rdi], eax
0x18001c96c  mov     rax, rdi
0x18001c96f  mov     rcx, [rsp+1468h+var_28]
0x18001c977  xor     rcx, rsp; StackCookie
0x18001c97a  call    __security_check_cookie
0x18001c97f  lea     r11, [rsp+1468h+var_18]
0x18001c987  mov     rbx, [r11+20h]
0x18001c98b  mov     rbp, [r11+30h]
0x18001c98f  mov     rsp, r11
0x18001c992  pop     r14
0x18001c994  pop     rdi
0x18001c995  pop     rsi
0x18001c996  retn
```
