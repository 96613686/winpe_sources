# WriteStringKey

- ea: `0x1001c420`
- end: `0x1001c522`
- name: `WriteStringKey`
- size: `258`
- prototype: `int __stdcall(HANDLE hFile, LPCWCH lpWideCharStr, LPCWCH)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1001ad40`
- `0x1001c3a0`
- `0x1001c3d0`

## callees

- `0x10008f90`
- `0x1000b070`
- `0x1000b200`
- `0x1000bd80`
- `0x1001c420`

## pseudocode

```c
int __stdcall WriteStringKey(HANDLE hFile, LPCWCH lpWideCharStr, LPCWCH a3)
{
  int v3; // ebx
  unsigned int v4; // kr00_4
  unsigned int v5; // kr04_4
  unsigned int v6; // esi
  CHAR *v7; // ebp
  int v9; // edi
  CHAR *v10; // esi
  void *v11; // kr08_4
  void *v12; // ecx
  void *v13; // kr0C_4
  void *v14; // ecx

  v3 = 0;
  v4 = wcslen(lpWideCharStr);
  v5 = wcslen(a3);
  v6 = v5 + 1;
  v7 = (CHAR *)MemAllocate(2 * (v4 + 1));
  if ( !v7 )
    return -1011;
  v9 = 2 * v6;
  v10 = (CHAR *)MemAllocate(2 * v6);
  if ( v10 )
  {
    ErrWideNToMultiByteCb(lpWideCharStr, v4 + 1, v7, 2 * (v4 + 1));
    ErrWideNToMultiByteCb(a3, v5 + 1, v10, v9);
    v11 = (void *)strlen(v7);
    DOSWriteFile(v11, hFile, v7, (DWORD)v11);
    DOSWriteFile(v12, hFile, "=", 1u);
    v13 = (void *)strlen(v10);
    DOSWriteFile(v13, hFile, v10, (DWORD)v13);
    DOSWriteFile(v14, hFile, &dword_1003E67C, 2u);
  }
  else
  {
    v3 = -1011;
  }
  MemFree(v7);
  if ( v10 )
    MemFree(v10);
  return v3;
}

```

## disassembly

```asm
0x1001c420  mov     ecx, [esp+lpWideCharStr]
0x1001c424  sub     esp, 8
0x1001c427  push    ebx
0x1001c428  push    ebp
0x1001c429  push    esi
0x1001c42a  xor     ebx, ebx
0x1001c42c  lea     edx, [ecx+2]
0x1001c42f  nop
0x1001c430  mov     ax, [ecx]
0x1001c433  add     ecx, 2
0x1001c436  test    ax, ax
0x1001c439  jnz     short loc_1001C430
0x1001c43b  sub     ecx, edx
0x1001c43d  sar     ecx, 1
0x1001c43f  lea     edx, [ecx+1]
0x1001c442  mov     ecx, [esp+14h+arg_8]
0x1001c446  mov     [esp+14h+cchWideChar], edx
0x1001c44a  lea     esi, [ecx+2]
0x1001c44d  lea     ecx, [ecx+0]
0x1001c450  mov     ax, [ecx]
0x1001c453  add     ecx, 2
0x1001c456  test    ax, ax
0x1001c459  jnz     short loc_1001C450
0x1001c45b  sub     ecx, esi
0x1001c45d  lea     eax, [edx+edx]
0x1001c460  sar     ecx, 1
0x1001c462  push    eax; Size
0x1001c463  lea     esi, [ecx+1]
0x1001c466  mov     [esp+18h+var_4], esi
0x1001c46a  call    _MemAllocate@4; MemAllocate(x)
0x1001c46f  mov     ebp, eax
0x1001c471  test    ebp, ebp
0x1001c473  jnz     short loc_1001C483
0x1001c475  pop     esi
0x1001c476  pop     ebp
0x1001c477  mov     eax, 0FFFFFC0Dh
0x1001c47c  pop     ebx
0x1001c47d  add     esp, 8
0x1001c480  retn    0Ch
0x1001c483  push    edi
0x1001c484  lea     edi, [esi+esi]
0x1001c487  push    edi; Size
0x1001c488  call    _MemAllocate@4; MemAllocate(x)
0x1001c48d  mov     esi, eax
0x1001c48f  test    esi, esi
0x1001c491  jnz     short loc_1001C49A
0x1001c493  mov     ebx, 0FFFFFC0Dh
0x1001c498  jmp     short loc_1001C506
0x1001c49a  mov     ecx, [esp+18h+cchWideChar]
0x1001c49e  lea     eax, [ecx+ecx]
0x1001c4a1  push    eax; int
0x1001c4a2  push    ebp; lpMultiByteStr
0x1001c4a3  push    ecx; cchWideChar
0x1001c4a4  push    [esp+24h+lpWideCharStr]; lpWideCharStr
0x1001c4a8  call    _ErrWideNToMultiByteCb@16; ErrWideNToMultiByteCb(x,x,x,x)
0x1001c4ad  push    edi; int
0x1001c4ae  push    esi; lpMultiByteStr
0x1001c4af  push    [esp+20h+var_4]; cchWideChar
0x1001c4b3  push    [esp+24h+arg_8]; lpWideCharStr
0x1001c4b7  call    _ErrWideNToMultiByteCb@16; ErrWideNToMultiByteCb(x,x,x,x)
0x1001c4bc  mov     ecx, ebp
0x1001c4be  lea     edx, [ecx+1]
0x1001c4c1  mov     al, [ecx]
0x1001c4c3  inc     ecx
0x1001c4c4  test    al, al
0x1001c4c6  jnz     short loc_1001C4C1
0x1001c4c8  mov     edi, [esp+18h+hFile]
0x1001c4cc  sub     ecx, edx
0x1001c4ce  push    ecx; nNumberOfBytesToWrite
0x1001c4cf  push    ebp; lpBuffer
0x1001c4d0  push    edi; hFile
0x1001c4d1  call    _DOSWriteFile@12; DOSWriteFile(x,x,x)
0x1001c4d6  push    1; nNumberOfBytesToWrite
0x1001c4d8  push    offset asc_10002070; "="
0x1001c4dd  push    edi; hFile
0x1001c4de  call    _DOSWriteFile@12; DOSWriteFile(x,x,x)
0x1001c4e3  mov     ecx, esi
0x1001c4e5  lea     edx, [ecx+1]
0x1001c4e8  mov     al, [ecx]
0x1001c4ea  inc     ecx
0x1001c4eb  test    al, al
0x1001c4ed  jnz     short loc_1001C4E8
0x1001c4ef  sub     ecx, edx
0x1001c4f1  push    ecx; nNumberOfBytesToWrite
0x1001c4f2  push    esi; lpBuffer
0x1001c4f3  push    edi; hFile
0x1001c4f4  call    _DOSWriteFile@12; DOSWriteFile(x,x,x)
0x1001c4f9  push    2; nNumberOfBytesToWrite
0x1001c4fb  push    offset dword_1003E67C; lpBuffer
0x1001c500  push    edi; hFile
0x1001c501  call    _DOSWriteFile@12; DOSWriteFile(x,x,x)
0x1001c506  push    ebp
0x1001c507  call    _MemFree@4; MemFree(x)
0x1001c50c  pop     edi
0x1001c50d  test    esi, esi
0x1001c50f  jz      short loc_1001C517
0x1001c511  push    esi
0x1001c512  call    _MemFree@4; MemFree(x)
0x1001c517  pop     esi
0x1001c518  pop     ebp
0x1001c519  mov     eax, ebx
0x1001c51b  pop     ebx
0x1001c51c  add     esp, 8
0x1001c51f  retn    0Ch
```
