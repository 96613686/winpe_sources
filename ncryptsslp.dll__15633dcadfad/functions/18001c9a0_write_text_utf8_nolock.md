# write_text_utf8_nolock

- ea: `0x18001c9a0`
- end: `0x18001cb1e`
- name: `write_text_utf8_nolock`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001cc4c`

## callees

- `0x1800186e0`
- `0x180018ac0`
- `0x18001c9a0`
- `0x180024ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cae7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001cac2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001cac2`

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
  _BYTE v17[3424]; // [rsp+700h] [rbp-D98h] BYREF

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
    v11 = _acrt_WideCharToMultiByte(65001, 0, (unsigned int)v15, (v9 - v15) >> 1, (unsigned int)v17, 3413, 0, 0);
    if ( v11 )
    {
      v12 = 0;
      while ( 1 )
      {
        NumberOfBytesWritten = 0;
        if ( !WriteFile(v8, &v17[v12], v11 - v12, &NumberOfBytesWritten, 0) )
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
0x18001c9a0  mov     [rsp+arg_0], rbx
0x18001c9a5  mov     [rsp+arg_10], rbp
0x18001c9aa  push    rsi
0x18001c9ab  push    rdi
0x18001c9ac  push    r12
0x18001c9ae  push    r14
0x18001c9b0  push    r15
0x18001c9b2  mov     eax, 1470h
0x18001c9b7  call    _alloca_probe
0x18001c9bc  sub     rsp, rax
0x18001c9bf  mov     rax, cs:__security_cookie
0x18001c9c6  xor     rax, rsp
0x18001c9c9  mov     [rsp+1498h+var_38], rax
0x18001c9d1  mov     eax, edx
0x18001c9d3  movsxd  r10, edx
0x18001c9d6  and     eax, 3Fh
0x18001c9d9  sar     r10, 6
0x18001c9dd  mov     rbx, rcx
0x18001c9e0  mov     r14d, r9d
0x18001c9e3  lea     rcx, __pioinfo
0x18001c9ea  add     r14, r8
0x18001c9ed  mov     r15, r8
0x18001c9f0  mov     rdi, r8
0x18001c9f3  lea     rdx, [rax+rax*8]
0x18001c9f7  mov     rax, [rcx+r10*8]
0x18001c9fb  mov     r12, [rax+rdx*8+28h]
0x18001ca00  xor     eax, eax
0x18001ca02  mov     [rbx], rax
0x18001ca05  mov     [rbx+8], eax
0x18001ca08  cmp     r8, r14
0x18001ca0b  jnb     loc_18001CAEF
0x18001ca11  lea     r9, [rsp+1498h+var_1448]
0x18001ca16  cmp     rdi, r14
0x18001ca19  jnb     short loc_18001CA47
0x18001ca1b  movzx   eax, word ptr [rdi]
0x18001ca1e  add     rdi, 2
0x18001ca22  cmp     ax, 0Ah
0x18001ca26  jnz     short loc_18001CA32
0x18001ca28  mov     word ptr [r9], 0Dh
0x18001ca2e  add     r9, 2
0x18001ca32  mov     [r9], ax
0x18001ca36  add     r9, 2
0x18001ca3a  lea     rax, [rsp+1498h+var_DA0]
0x18001ca42  cmp     r9, rax
0x18001ca45  jb      short loc_18001CA16
0x18001ca47  mov     [rsp+1498h+var_1460], 0
0x18001ca50  lea     rax, [rsp+1498h+var_1448]
0x18001ca55  sub     r9, rax
0x18001ca58  mov     [rsp+1498h+var_1468], 0
0x18001ca61  lea     rax, [rsp+1498h+var_D98]
0x18001ca69  sar     r9, 1
0x18001ca6c  mov     [rsp+1498h+var_1470], 0D55h
0x18001ca74  lea     r8, [rsp+1498h+var_1448]
0x18001ca79  xor     edx, edx
0x18001ca7b  mov     [rsp+1498h+lpOverlapped], rax
0x18001ca80  mov     ecx, 0FDE9h
0x18001ca85  call    __acrt_WideCharToMultiByte
0x18001ca8a  mov     ebp, eax
0x18001ca8c  test    eax, eax
0x18001ca8e  jz      short loc_18001CAE7
0x18001ca90  xor     esi, esi
0x18001ca92  test    eax, eax
0x18001ca94  jz      short loc_18001CAD4
0x18001ca96  mov     ecx, esi
0x18001ca98  lea     rdx, [rsp+1498h+var_D98]
0x18001caa0  mov     r8d, ebp
0x18001caa3  mov     [rsp+1498h+NumberOfBytesWritten], 0
0x18001caab  add     rdx, rcx; lpBuffer
0x18001caae  mov     [rsp+1498h+lpOverlapped], 0; lpOverlapped
0x18001cab7  mov     rcx, r12; hFile
0x18001caba  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001cabf  sub     r8d, esi; nNumberOfBytesToWrite
0x18001cac2  call    cs:__imp_WriteFile
0x18001cac8  test    eax, eax
0x18001caca  jz      short loc_18001CAE7
0x18001cacc  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x18001cad0  cmp     esi, ebp
0x18001cad2  jb      short loc_18001CA96
0x18001cad4  mov     eax, edi
0x18001cad6  sub     eax, r15d
0x18001cad9  mov     [rbx+4], eax
0x18001cadc  cmp     rdi, r14
0x18001cadf  jb      loc_18001CA11
0x18001cae5  jmp     short loc_18001CAEF
0x18001cae7  call    cs:__imp_GetLastError
0x18001caed  mov     [rbx], eax
0x18001caef  mov     rax, rbx
0x18001caf2  mov     rcx, [rsp+1498h+var_38]
0x18001cafa  xor     rcx, rsp; StackCookie
0x18001cafd  call    __security_check_cookie
0x18001cb02  lea     r11, [rsp+1498h+var_28]
0x18001cb0a  mov     rbx, [r11+30h]
0x18001cb0e  mov     rbp, [r11+40h]
0x18001cb12  mov     rsp, r11
0x18001cb15  pop     r15
0x18001cb17  pop     r14
0x18001cb19  pop     r12
0x18001cb1b  pop     rdi
0x18001cb1c  pop     rsi
0x18001cb1d  retn
```
