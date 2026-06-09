# sub_1802AEF2C

- ea: `0x1802aef2c`
- end: `0x1802af342`
- name: `sub_1802AEF2C`
- size: `1046`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1802a9fa0`

## callees

- `0x180024ed8`
- `0x18013f000`
- `0x1801a1648`
- `0x1801a2548`
- `0x1801a5180`
- `0x1801a569c`
- `0x1801a8df4`
- `0x1801b98e4`
- `0x1801b9c6c`
- `0x1802aef2c`
- `0x180b74870`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1802af17c`
- `KERNEL32!WriteFile` at `0x1802af25e`
- `KERNEL32!WriteFile` at `0x1802af17c`
- `KERNEL32!WriteFile` at `0x1802af25e`
- `KERNEL32!CreateFileW` at `0x1802af0df`
- `KERNEL32!CreateFileW` at `0x1802af0df`
- `KERNEL32!CloseHandle` at `0x1802af317`
- `KERNEL32!CloseHandle` at `0x1802af317`
- `KERNEL32!GetLastError` at `0x1802af0f2`
- `KERNEL32!GetLastError` at `0x1802af186`
- `KERNEL32!GetLastError` at `0x1802af268`
- `KERNEL32!GetLastError` at `0x1802af0f2`
- `KERNEL32!GetLastError` at `0x1802af186`
- `KERNEL32!GetLastError` at `0x1802af268`

## pseudocode

```c
__int64 __fastcall sub_1802AEF2C(__int64 a1, __int64 a2, __int64 a3)
{
  DWORD LastError; // ebx
  __int64 v8; // rsi
  __int64 v9; // r8
  int v10; // edi
  __int64 v11; // r8
  const WCHAR *v12; // rcx
  HANDLE FileW; // rax
  _QWORD *v14; // rcx
  int v15; // edx
  LPCWSTR *v16; // r9
  _BYTE *v17; // rdi
  _BYTE *v18; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  int v21; // edx
  LPCWSTR *v22; // r9
  char dwCreationDisposition; // [rsp+20h] [rbp-C8h]
  char dwCreationDispositiona; // [rsp+20h] [rbp-C8h]
  LPCVOID lpBuffer[2]; // [rsp+50h] [rbp-98h] BYREF
  __int64 v26; // [rsp+60h] [rbp-88h]
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp-78h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+78h] [rbp-70h] BYREF
  __int128 v29; // [rsp+88h] [rbp-60h]
  char Buffer; // [rsp+98h] [rbp-50h] BYREF
  int v31; // [rsp+99h] [rbp-4Fh]

  LastError = 0;
  if ( !word_181042C40[0] )
  {
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 8) != 0 )
      sub_1801A1648(*((_QWORD *)hDevice + 2), 10, qword_180C7E8C0);
    return 0;
  }
  v8 = -1;
  *(_OWORD *)lpFileName = 0;
  v29 = 0;
  v9 = -1;
  do
    ++v9;
  while ( word_181042C40[v9] );
  sub_1801A2548(lpFileName);
  v10 = sub_180024ED8(word_181042C40, -1);
  if ( v10 < 0 )
  {
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 2) != 0 )
      sub_1801A569C(*((_QWORD *)hDevice + 2), 11, (unsigned int)qword_180C7E8C0, (unsigned int)word_181042C40, v10);
    if ( (v10 & 0x1FFF0000) == 0x70000 )
    {
      LastError = (unsigned __int16)v10;
    }
    else
    {
      switch ( v10 )
      {
        case -2147467263:
          LastError = 50;
          break;
        case -2147024890:
          LastError = 6;
          break;
        case -2147024882:
          LastError = 8;
          break;
        default:
          LastError = 87;
          if ( v10 != -2147024809 )
            LastError = 1359;
          break;
      }
    }
    goto LABEL_58;
  }
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a3 + 2 * v11) );
  sub_1801B9C6C(lpFileName, a3, v11);
  v12 = (const WCHAR *)lpFileName;
  if ( *((_QWORD *)&v29 + 1) > 7u )
    v12 = lpFileName[0];
  FileW = CreateFileW(v12, 0xC0000000, 1u, 0, 2u, 0x80u, 0);
  v8 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v14 = hDevice;
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 2) != 0 )
    {
      v15 = 12;
LABEL_31:
      dwCreationDisposition = LastError;
LABEL_32:
      v16 = lpFileName;
      if ( *((_QWORD *)&v29 + 1) > 7u )
        LODWORD(v16) = lpFileName[0];
      sub_1801A569C(v14[2], v15, (unsigned int)qword_180C7E8C0, (_DWORD)v16, dwCreationDisposition);
      goto LABEL_58;
    }
    goto LABEL_58;
  }
  NumberOfBytesWritten = 0;
  Buffer = -34;
  v31 = a2;
  if ( WriteFile(FileW, &Buffer, 4u, &NumberOfBytesWritten, 0) )
  {
    if ( NumberOfBytesWritten != 4 )
    {
      LastError = 29;
      v14 = hDevice;
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
      {
        v15 = 14;
        dwCreationDisposition = 29;
        goto LABEL_32;
      }
      goto LABEL_58;
    }
    *(_OWORD *)lpBuffer = 0;
    v26 = 0;
    sub_1801A8DF4(lpBuffer, a2);
    v17 = lpBuffer[0];
    sub_180B74870(lpBuffer[0], a1, a2);
    if ( a2 )
    {
      v18 = v17;
      v19 = a2;
      do
      {
        *v18 = *((_BYTE *)qword_180C7E780 + (unsigned __int8)*v18);
        ++v18;
        --v19;
      }
      while ( v19 );
    }
    if ( WriteFile((HANDLE)v8, v17, a2, &NumberOfBytesWritten, 0) )
    {
      if ( NumberOfBytesWritten != (_DWORD)a2 )
      {
        LastError = 29;
        v20 = hDevice;
        if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
        {
          v21 = 16;
          dwCreationDispositiona = 29;
          goto LABEL_54;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v20 = hDevice;
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
      {
        v21 = 15;
        dwCreationDispositiona = LastError;
LABEL_54:
        v22 = lpFileName;
        if ( *((_QWORD *)&v29 + 1) > 7u )
          LODWORD(v22) = lpFileName[0];
        sub_1801A569C(v20[2], v21, (unsigned int)qword_180C7E8C0, (_DWORD)v22, dwCreationDispositiona);
      }
    }
    sub_1801B98E4(lpBuffer);
    goto LABEL_58;
  }
  LastError = GetLastError();
  v14 = hDevice;
  if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
  {
    v15 = 13;
    goto LABEL_31;
  }
LABEL_58:
  sub_1801A5180(lpFileName);
  if ( v8 != -1 )
    CloseHandle((HANDLE)v8);
  return LastError;
}

```

## disassembly

```asm
0x1802aef2c  push    rbx
0x1802aef2e  push    rsi
0x1802aef2f  push    rdi
0x1802aef30  push    r12
0x1802aef32  push    r13
0x1802aef34  push    r14
0x1802aef36  push    r15
0x1802aef38  sub     rsp, 0B0h
0x1802aef3f  mov     rax, cs:__security_cookie
0x1802aef46  xor     rax, rsp
0x1802aef49  mov     [rsp+0E8h+var_48], rax
0x1802aef51  mov     r12, r8
0x1802aef54  mov     r14, rdx
0x1802aef57  mov     r13, rcx
0x1802aef5a  xor     ebx, ebx
0x1802aef5c  cmp     cs:word_181042C40, bx
0x1802aef63  jnz     short loc_1802AEF9C
0x1802aef65  lea     rax, hDevice
0x1802aef6c  mov     rcx, cs:hDevice
0x1802aef73  cmp     rcx, rax
0x1802aef76  jz      short loc_1802AEF95
0x1802aef78  mov     ebx, 8
0x1802aef7d  test    [rcx+1Ch], bl
0x1802aef80  jz      short loc_1802AEF95
0x1802aef82  lea     edx, [rbx+2]
0x1802aef85  lea     r8, qword_180C7E8C0
0x1802aef8c  mov     rcx, [rcx+10h]
0x1802aef90  call    sub_1801A1648
0x1802aef95  xor     eax, eax
0x1802aef97  jmp     loc_1802AF31F
0x1802aef9c  or      r15, 0FFFFFFFFFFFFFFFFh
0x1802aefa0  mov     rsi, r15
0x1802aefa3  mov     [rsp+0E8h+var_A0], r15
0x1802aefa8  xorps   xmm0, xmm0
0x1802aefab  movups  xmmword ptr [rsp+0E8h+lpFileName], xmm0
0x1802aefb0  xorps   xmm1, xmm1
0x1802aefb3  movdqu  [rsp+0E8h+var_60], xmm1
0x1802aefbc  lea     rdi, word_181042C40
0x1802aefc3  mov     r8, r15
0x1802aefc6  inc     r8
0x1802aefc9  cmp     [rdi+r8*2], bx
0x1802aefce  jnz     short loc_1802AEFC6
0x1802aefd0  mov     rdx, rdi
0x1802aefd3  lea     rcx, [rsp+0E8h+lpFileName]
0x1802aefd8  call    sub_1801A2548
0x1802aefdd  nop
0x1802aefde  mov     rdx, r15
0x1802aefe1  mov     rcx, rdi
0x1802aefe4  call    sub_180024ED8
0x1802aefe9  mov     edi, eax
0x1802aefeb  test    eax, eax
0x1802aefed  jns     loc_1802AF090
0x1802aeff3  lea     rax, hDevice
0x1802aeffa  mov     rcx, cs:hDevice
0x1802af001  cmp     rcx, rax
0x1802af004  jz      short loc_1802AF02C
0x1802af006  test    byte ptr [rcx+1Ch], 2
0x1802af00a  jz      short loc_1802AF02C
0x1802af00c  mov     edx, 0Bh
0x1802af011  mov     [rsp+0E8h+dwCreationDisposition], edi
0x1802af015  lea     r9, word_181042C40
0x1802af01c  lea     r8, qword_180C7E8C0
0x1802af023  mov     rcx, [rcx+10h]
0x1802af027  call    sub_1801A569C
0x1802af02c  mov     eax, edi
0x1802af02e  and     eax, 1FFF0000h
0x1802af033  cmp     eax, 70000h
0x1802af038  jnz     short loc_1802AF042
0x1802af03a  movzx   ebx, di
0x1802af03d  jmp     loc_1802AF2F5
0x1802af042  cmp     edi, 80004001h
0x1802af048  jz      short loc_1802AF086
0x1802af04a  cmp     edi, 80070006h
0x1802af050  jz      short loc_1802AF07C
0x1802af052  cmp     edi, 8007000Eh
0x1802af058  jz      short loc_1802AF072
0x1802af05a  mov     ebx, 57h ; 'W'
0x1802af05f  mov     eax, 54Fh
0x1802af064  cmp     edi, 80070057h
0x1802af06a  cmovnz  ebx, eax
0x1802af06d  jmp     loc_1802AF2F5
0x1802af072  mov     ebx, 8
0x1802af077  jmp     loc_1802AF2F5
0x1802af07c  mov     ebx, 6
0x1802af081  jmp     loc_1802AF2F5
0x1802af086  mov     ebx, 32h ; '2'
0x1802af08b  jmp     loc_1802AF2F5
0x1802af090  mov     r8, r15
0x1802af093  inc     r8
0x1802af096  cmp     [r12+r8*2], bx
0x1802af09b  jnz     short loc_1802AF093
0x1802af09d  mov     rdx, r12
0x1802af0a0  lea     rcx, [rsp+0E8h+lpFileName]
0x1802af0a5  call    sub_1801B9C6C
0x1802af0aa  lea     rcx, [rsp+0E8h+lpFileName]
0x1802af0af  cmp     qword ptr [rsp+0E8h+var_60+8], 7
0x1802af0b8  cmova   rcx, [rsp+0E8h+lpFileName]; lpFileName
0x1802af0be  mov     [rsp+0E8h+hTemplateFile], rbx; hTemplateFile
0x1802af0c3  mov     [rsp+0E8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1802af0cb  mov     [rsp+0E8h+dwCreationDisposition], 2; dwCreationDisposition
0x1802af0d3  xor     r9d, r9d; lpSecurityAttributes
0x1802af0d6  mov     edx, 0C0000000h; dwDesiredAccess
0x1802af0db  lea     r8d, [r9+1]; dwShareMode
0x1802af0df  call    cs:__imp_CreateFileW
0x1802af0e5  mov     rsi, rax
0x1802af0e8  mov     [rsp+0E8h+var_A0], rax
0x1802af0ed  cmp     rax, r15
0x1802af0f0  jnz     short loc_1802AF14D
0x1802af0f2  call    cs:__imp_GetLastError
0x1802af0f8  mov     ebx, eax
0x1802af0fa  lea     rax, hDevice
0x1802af101  mov     rcx, cs:hDevice
0x1802af108  cmp     rcx, rax
0x1802af10b  jz      loc_1802AF2F5
0x1802af111  test    byte ptr [rcx+1Ch], 2
0x1802af115  jz      loc_1802AF2F5
0x1802af11b  mov     edx, 0Ch
0x1802af120  mov     [rsp+0E8h+dwCreationDisposition], ebx
0x1802af124  lea     r9, [rsp+0E8h+lpFileName]
0x1802af129  cmp     qword ptr [rsp+0E8h+var_60+8], 7
0x1802af132  cmova   r9, [rsp+0E8h+lpFileName]
0x1802af138  lea     r8, qword_180C7E8C0
0x1802af13f  mov     rcx, [rcx+10h]
0x1802af143  call    sub_1801A569C
0x1802af148  jmp     loc_1802AF2F5
0x1802af14d  mov     [rsp+0E8h+NumberOfBytesWritten], ebx
0x1802af151  mov     [rsp+0E8h+Buffer], 0DEh
0x1802af159  mov     [rsp+0E8h+var_4F], r14d
0x1802af161  mov     qword ptr [rsp+0E8h+dwCreationDisposition], rbx; lpOverlapped
0x1802af166  lea     r9, [rsp+0E8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802af16b  mov     r8d, 4; nNumberOfBytesToWrite
0x1802af171  lea     rdx, [rsp+0E8h+Buffer]; lpBuffer
0x1802af179  mov     rcx, rsi; hFile
0x1802af17c  call    cs:__imp_WriteFile
0x1802af182  test    eax, eax
0x1802af184  jnz     short loc_1802AF1B9
0x1802af186  call    cs:__imp_GetLastError
0x1802af18c  mov     ebx, eax
0x1802af18e  lea     rax, hDevice
0x1802af195  mov     rcx, cs:hDevice
0x1802af19c  cmp     rcx, rax
0x1802af19f  jz      loc_1802AF2F5
0x1802af1a5  test    byte ptr [rcx+1Ch], 1
0x1802af1a9  jz      loc_1802AF2F5
0x1802af1af  mov     edx, 0Dh
0x1802af1b4  jmp     loc_1802AF120
0x1802af1b9  cmp     [rsp+0E8h+NumberOfBytesWritten], 4
0x1802af1be  jz      short loc_1802AF1F8
0x1802af1c0  mov     r8d, 1Dh
0x1802af1c6  mov     ebx, r8d
0x1802af1c9  lea     rax, hDevice
0x1802af1d0  mov     rcx, cs:hDevice
0x1802af1d7  cmp     rcx, rax
0x1802af1da  jz      loc_1802AF2F5
0x1802af1e0  test    byte ptr [rcx+1Ch], 1
0x1802af1e4  jz      loc_1802AF2F5
0x1802af1ea  lea     edx, [r8-0Fh]
0x1802af1ee  mov     [rsp+0E8h+dwCreationDisposition], r8d
0x1802af1f3  jmp     loc_1802AF124
0x1802af1f8  xorps   xmm0, xmm0
0x1802af1fb  xor     eax, eax
0x1802af1fd  movups  xmmword ptr [rsp+0E8h+lpBuffer], xmm0
0x1802af202  mov     [rsp+0E8h+var_88], rax
0x1802af207  mov     rdx, r14
0x1802af20a  lea     rcx, [rsp+0E8h+lpBuffer]
0x1802af20f  call    sub_1801A8DF4
0x1802af214  mov     r8, r14
0x1802af217  mov     rdx, r13
0x1802af21a  mov     rdi, [rsp+0E8h+lpBuffer]
0x1802af21f  mov     rcx, rdi
0x1802af222  call    sub_180B74870
0x1802af227  test    r14, r14
0x1802af22a  jz      short loc_1802AF24B
0x1802af22c  mov     rcx, rdi
0x1802af22f  mov     rdx, r14
0x1802af232  movzx   eax, byte ptr [rcx]
0x1802af235  lea     r8, qword_180C7E780
0x1802af23c  mov     al, [rax+r8]
0x1802af240  mov     [rcx], al
0x1802af242  inc     rcx
0x1802af245  sub     rdx, 1
0x1802af249  jnz     short loc_1802AF232
0x1802af24b  mov     qword ptr [rsp+0E8h+dwCreationDisposition], rbx; lpOverlapped
0x1802af250  lea     r9, [rsp+0E8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802af255  mov     r8d, r14d; nNumberOfBytesToWrite
0x1802af258  mov     rdx, rdi; lpBuffer
0x1802af25b  mov     rcx, rsi; hFile
0x1802af25e  call    cs:__imp_WriteFile
0x1802af264  test    eax, eax
0x1802af266  jnz     short loc_1802AF294
0x1802af268  call    cs:__imp_GetLastError
0x1802af26e  mov     ebx, eax
0x1802af270  lea     rax, hDevice
0x1802af277  mov     rcx, cs:hDevice
0x1802af27e  cmp     rcx, rax
0x1802af281  jz      short loc_1802AF2EA
0x1802af283  test    byte ptr [rcx+1Ch], 1
0x1802af287  jz      short loc_1802AF2EA
0x1802af289  mov     edx, 0Fh
0x1802af28e  mov     [rsp+0E8h+dwCreationDisposition], ebx
0x1802af292  jmp     short loc_1802AF2C6
0x1802af294  cmp     [rsp+0E8h+NumberOfBytesWritten], r14d
0x1802af299  jz      short loc_1802AF2EA
0x1802af29b  mov     r8d, 1Dh
0x1802af2a1  mov     ebx, r8d
0x1802af2a4  lea     rax, hDevice
0x1802af2ab  mov     rcx, cs:hDevice
0x1802af2b2  cmp     rcx, rax
0x1802af2b5  jz      short loc_1802AF2EA
0x1802af2b7  test    byte ptr [rcx+1Ch], 1
0x1802af2bb  jz      short loc_1802AF2EA
0x1802af2bd  lea     edx, [r8-0Dh]
0x1802af2c1  mov     [rsp+0E8h+dwCreationDisposition], r8d
0x1802af2c6  lea     r9, [rsp+0E8h+lpFileName]
0x1802af2cb  cmp     qword ptr [rsp+0E8h+var_60+8], 7
0x1802af2d4  cmova   r9, [rsp+0E8h+lpFileName]
0x1802af2da  lea     r8, qword_180C7E8C0
0x1802af2e1  mov     rcx, [rcx+10h]
0x1802af2e5  call    sub_1801A569C
0x1802af2ea  lea     rcx, [rsp+0E8h+lpBuffer]
0x1802af2ef  call    sub_1801B98E4
0x1802af2f4  nop
0x1802af2f5  lea     rcx, [rsp+0E8h+lpFileName]
0x1802af2fa  call    sub_1801A5180
0x1802af2ff  nop
0x1802af300  jmp     short loc_1802AF30F
0x1802af302  or      r15, 0FFFFFFFFFFFFFFFFh
0x1802af306  mov     rsi, [rsp+0E8h+var_A0]
0x1802af30b  mov     ebx, [rsp+0E8h+var_A8]
0x1802af30f  cmp     rsi, r15
0x1802af312  jz      short loc_1802AF31D
0x1802af314  mov     rcx, rsi; hObject
0x1802af317  call    cs:__imp_CloseHandle
0x1802af31d  mov     eax, ebx
0x1802af31f  mov     rcx, [rsp+0E8h+var_48]
0x1802af327  xor     rcx, rsp; StackCookie
0x1802af32a  call    __security_check_cookie
0x1802af32f  add     rsp, 0B0h
0x1802af336  pop     r15
0x1802af338  pop     r14
0x1802af33a  pop     r13
0x1802af33c  pop     r12
0x1802af33e  pop     rdi
0x1802af33f  pop     rsi
0x1802af340  pop     rbx
0x1802af341  retn
```
