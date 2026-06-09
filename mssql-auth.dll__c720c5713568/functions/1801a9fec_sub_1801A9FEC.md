# sub_1801A9FEC

- ea: `0x1801a9fec`
- end: `0x1801aa219`
- name: `sub_1801A9FEC`
- size: `557`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18035e3e0`
- `0x18035ee30`

## callees

- `0x1801a9790`
- `0x1801a9f8c`
- `0x1801a9fec`
- `0x1801adc90`
- `0x1801b5ad0`

## import_xrefs

- `KERNEL32!SetFileInformationByHandle` at `0x1801aa056`
- `KERNEL32!SetFileInformationByHandle` at `0x1801aa178`
- `KERNEL32!SetFileInformationByHandle` at `0x1801aa1ac`
- `KERNEL32!SetFileInformationByHandle` at `0x1801aa056`
- `KERNEL32!SetFileInformationByHandle` at `0x1801aa178`
- `KERNEL32!SetFileInformationByHandle` at `0x1801aa1ac`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1801aa128`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1801aa128`
- `KERNEL32!GetLastError` at `0x1801aa0dc`
- `KERNEL32!GetLastError` at `0x1801aa136`
- `KERNEL32!GetLastError` at `0x1801aa1ce`
- `KERNEL32!GetLastError` at `0x1801aa0dc`
- `KERNEL32!GetLastError` at `0x1801aa136`
- `KERNEL32!GetLastError` at `0x1801aa1ce`
- `KERNEL32!CloseHandle` at `0x1801aa0a8`
- `KERNEL32!CloseHandle` at `0x1801aa14c`
- `KERNEL32!CloseHandle` at `0x1801aa0a8`
- `KERNEL32!CloseHandle` at `0x1801aa14c`

## pseudocode

```c
__int64 __fastcall sub_1801A9FEC(__int64 a1)
{
  char v2; // di
  int v3; // eax
  int v4; // ecx
  HANDLE v5; // rbx
  HANDLE v6; // rcx
  int v7; // eax
  DWORD LastError; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // [rsp+20h] [rbp-50h]
  HANDLE hFile; // [rsp+28h] [rbp-48h] BYREF
  int FileInformation; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v19[32]; // [rsp+38h] [rbp-38h] BYREF
  int v20; // [rsp+58h] [rbp-18h]

  v2 = 0;
  v3 = sub_1801A9F8C(&hFile, a1, 65920, 35651584);
  v4 = v3;
  if ( !v3 )
  {
    v2 = 1;
    goto LABEL_3;
  }
  if ( v3 != 5 )
  {
    LOBYTE(v16) = 0;
    v11 = v3 - 2;
    if ( !v11
      || (v12 = v11 - 1) == 0
      || (v13 = v12 - 50) == 0
      || (v14 = v13 - 11) == 0
      || (v15 = v14 - 59) == 0
      || v15 == 144 )
    {
      v4 = 0;
    }
    HIDWORD(v16) = v4;
LABEL_10:
    v6 = hFile;
    if ( hFile == (HANDLE)-1LL )
      return v16;
LABEL_11:
    if ( !CloseHandle(v6) )
      sub_1801B5AD0();
    return v16;
  }
  v7 = sub_1801A9F8C(&hFile, a1, 0x10000, 35651584);
  if ( v7 )
  {
    LOBYTE(v16) = 0;
    HIDWORD(v16) = v7;
    goto LABEL_10;
  }
LABEL_3:
  v5 = hFile;
  FileInformation = 19;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
  {
LABEL_4:
    LOBYTE(v16) = 1;
    HIDWORD(v16) = 0;
LABEL_5:
    if ( v5 == (HANDLE)-1LL )
      return v16;
    v6 = v5;
    goto LABEL_11;
  }
  LastError = GetLastError();
  if ( LastError != 1 && LastError != 50 && LastError != 87 )
    goto LABEL_16;
  LastError = sub_1801A9790(v5);
  if ( !LastError )
    goto LABEL_4;
  if ( LastError != 5 || !v2 )
  {
LABEL_16:
    LOBYTE(v16) = 0;
    goto LABEL_17;
  }
  if ( GetFileInformationByHandleEx(v5, FileBasicInfo, v19, 0x28u) )
  {
    if ( (v20 & 1) == 0 )
    {
      LOBYTE(v16) = 0;
      goto LABEL_33;
    }
    v20 ^= 1u;
    if ( !SetFileInformationByHandle(v5, FileBasicInfo, v19, 0x28u) )
      goto LABEL_22;
    v10 = sub_1801A9790(v5);
    if ( !v10 )
    {
      LOBYTE(v16) = 1;
      HIDWORD(v16) = 0;
      goto LABEL_24;
    }
    if ( v10 == 5 )
    {
      v20 |= 1u;
      LOBYTE(v16) = 0;
      if ( !SetFileInformationByHandle(v5, FileBasicInfo, v19, 0x28u) )
        goto LABEL_23;
LABEL_33:
      HIDWORD(v16) = 5;
      goto LABEL_24;
    }
    LOBYTE(v16) = 0;
    LastError = GetLastError();
LABEL_17:
    HIDWORD(v16) = LastError;
    goto LABEL_5;
  }
LABEL_22:
  LOBYTE(v16) = 0;
LABEL_23:
  HIDWORD(v16) = GetLastError();
LABEL_24:
  if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
    sub_1801B5AD0();
  return v16;
}

```

## disassembly

```asm
0x1801a9fec  mov     [rsp-8+arg_8], rbx
0x1801a9ff1  mov     [rsp-8+arg_10], rsi
0x1801a9ff6  mov     [rsp-8+arg_18], rdi
0x1801a9ffb  push    rbp
0x1801a9ffc  mov     rbp, rsp
0x1801a9fff  sub     rsp, 70h
0x1801aa003  mov     rax, cs:__security_cookie
0x1801aa00a  xor     rax, rsp
0x1801aa00d  mov     [rbp+var_10], rax
0x1801aa011  mov     rbx, rcx
0x1801aa014  mov     rdx, rcx
0x1801aa017  xor     esi, esi
0x1801aa019  lea     rcx, [rbp+hFile]
0x1801aa01d  mov     r9d, 2200000h
0x1801aa023  mov     r8d, 10180h
0x1801aa029  mov     dil, sil
0x1801aa02c  call    sub_1801A9F8C
0x1801aa031  mov     ecx, eax
0x1801aa033  test    eax, eax
0x1801aa035  jnz     short loc_1801AA072
0x1801aa037  mov     dil, 1
0x1801aa03a  mov     rbx, [rbp+hFile]
0x1801aa03e  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1801aa042  mov     r9d, 4; dwBufferSize
0x1801aa048  mov     [rbp+FileInformation], 13h
0x1801aa04f  mov     rcx, rbx; hFile
0x1801aa052  lea     edx, [r9+11h]; FileInformationClass
0x1801aa056  call    cs:SetFileInformationByHandle
0x1801aa05c  test    eax, eax
0x1801aa05e  jz      short loc_1801AA0DC
0x1801aa060  mov     byte ptr [rbp+var_50], 1
0x1801aa064  mov     dword ptr [rbp+var_50+4], esi
0x1801aa067  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801aa06b  jz      short loc_1801AA0B6
0x1801aa06d  mov     rcx, rbx
0x1801aa070  jmp     short loc_1801AA0A8
0x1801aa072  cmp     eax, 5
0x1801aa075  jnz     loc_1801AA1DF
0x1801aa07b  mov     r9d, 2200000h
0x1801aa081  lea     rcx, [rbp+hFile]
0x1801aa085  mov     r8d, 10000h
0x1801aa08b  mov     rdx, rbx
0x1801aa08e  call    sub_1801A9F8C
0x1801aa093  test    eax, eax
0x1801aa095  jz      short loc_1801AA03A
0x1801aa097  mov     byte ptr [rbp+var_50], sil
0x1801aa09b  mov     dword ptr [rbp+var_50+4], eax
0x1801aa09e  mov     rcx, [rbp+hFile]; hObject
0x1801aa0a2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801aa0a6  jz      short loc_1801AA0B6
0x1801aa0a8  call    cs:__imp_CloseHandle
0x1801aa0ae  test    eax, eax
0x1801aa0b0  jz      loc_1801AA20D
0x1801aa0b6  mov     rax, [rbp+var_50]
0x1801aa0ba  mov     rcx, [rbp+var_10]
0x1801aa0be  xor     rcx, rsp; StackCookie
0x1801aa0c1  call    __security_check_cookie
0x1801aa0c6  lea     r11, [rsp+70h+var_s0]
0x1801aa0cb  mov     rbx, [r11+18h]
0x1801aa0cf  mov     rsi, [r11+20h]
0x1801aa0d3  mov     rdi, [r11+28h]
0x1801aa0d7  mov     rsp, r11
0x1801aa0da  pop     rbp
0x1801aa0db  retn
0x1801aa0dc  call    cs:__imp_GetLastError
0x1801aa0e2  mov     ecx, eax
0x1801aa0e4  sub     ecx, 1
0x1801aa0e7  jz      short loc_1801AA0FF
0x1801aa0e9  sub     ecx, 31h ; '1'
0x1801aa0ec  jz      short loc_1801AA0FF
0x1801aa0ee  cmp     ecx, 25h ; '%'
0x1801aa0f1  jz      short loc_1801AA0FF
0x1801aa0f3  mov     byte ptr [rbp+var_50], sil
0x1801aa0f7  mov     dword ptr [rbp+var_50+4], eax
0x1801aa0fa  jmp     loc_1801AA067
0x1801aa0ff  mov     rcx, rbx; hFile
0x1801aa102  call    sub_1801A9790
0x1801aa107  test    eax, eax
0x1801aa109  jz      loc_1801AA060
0x1801aa10f  cmp     eax, 5
0x1801aa112  jnz     short loc_1801AA0F3
0x1801aa114  test    dil, dil
0x1801aa117  jz      short loc_1801AA0F3
0x1801aa119  lea     edi, [rax+23h]
0x1801aa11c  xor     edx, edx; FileInformationClass
0x1801aa11e  mov     r9d, edi; dwBufferSize
0x1801aa121  lea     r8, [rbp+var_38]; lpFileInformation
0x1801aa125  mov     rcx, rbx; hFile
0x1801aa128  call    cs:GetFileInformationByHandleEx
0x1801aa12e  test    eax, eax
0x1801aa130  jnz     short loc_1801AA15F
0x1801aa132  mov     byte ptr [rbp+var_50], sil
0x1801aa136  call    cs:__imp_GetLastError
0x1801aa13c  mov     dword ptr [rbp+var_50+4], eax
0x1801aa13f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801aa143  jz      loc_1801AA0B6
0x1801aa149  mov     rcx, rbx; hObject
0x1801aa14c  call    cs:__imp_CloseHandle
0x1801aa152  test    eax, eax
0x1801aa154  jz      loc_1801AA213
0x1801aa15a  jmp     loc_1801AA0B6
0x1801aa15f  mov     eax, [rbp+var_18]
0x1801aa162  test    al, 1
0x1801aa164  jz      short loc_1801AA1D9
0x1801aa166  xor     eax, 1
0x1801aa169  lea     r8, [rbp+var_38]; lpFileInformation
0x1801aa16d  mov     r9d, edi; dwBufferSize
0x1801aa170  mov     [rbp+var_18], eax
0x1801aa173  xor     edx, edx; FileInformationClass
0x1801aa175  mov     rcx, rbx; hFile
0x1801aa178  call    cs:SetFileInformationByHandle
0x1801aa17e  test    eax, eax
0x1801aa180  jz      short loc_1801AA132
0x1801aa182  mov     rcx, rbx; hFile
0x1801aa185  call    sub_1801A9790
0x1801aa18a  test    eax, eax
0x1801aa18c  jnz     short loc_1801AA197
0x1801aa18e  mov     byte ptr [rbp+var_50], 1
0x1801aa192  mov     dword ptr [rbp+var_50+4], esi
0x1801aa195  jmp     short loc_1801AA13F
0x1801aa197  cmp     eax, 5
0x1801aa19a  jnz     short loc_1801AA1CA
0x1801aa19c  or      [rbp+var_18], 1
0x1801aa1a0  lea     r8, [rbp+var_38]; lpFileInformation
0x1801aa1a4  mov     r9d, edi; dwBufferSize
0x1801aa1a7  xor     edx, edx; FileInformationClass
0x1801aa1a9  mov     rcx, rbx; hFile
0x1801aa1ac  call    cs:SetFileInformationByHandle
0x1801aa1b2  mov     byte ptr [rbp+var_50], sil
0x1801aa1b6  test    eax, eax
0x1801aa1b8  jz      loc_1801AA136
0x1801aa1be  mov     dword ptr [rbp+var_50+4], 5
0x1801aa1c5  jmp     loc_1801AA13F
0x1801aa1ca  mov     byte ptr [rbp+var_50], sil
0x1801aa1ce  call    cs:__imp_GetLastError
0x1801aa1d4  jmp     loc_1801AA0F7
0x1801aa1d9  mov     byte ptr [rbp+var_50], sil
0x1801aa1dd  jmp     short loc_1801AA1BE
0x1801aa1df  mov     byte ptr [rbp+var_50], sil
0x1801aa1e3  sub     eax, 2
0x1801aa1e6  jz      short loc_1801AA203
0x1801aa1e8  sub     eax, 1
0x1801aa1eb  jz      short loc_1801AA203
0x1801aa1ed  sub     eax, 32h ; '2'
0x1801aa1f0  jz      short loc_1801AA203
0x1801aa1f2  sub     eax, 0Bh
0x1801aa1f5  jz      short loc_1801AA203
0x1801aa1f7  sub     eax, 3Bh ; ';'
0x1801aa1fa  jz      short loc_1801AA203
0x1801aa1fc  cmp     eax, 90h
0x1801aa201  jnz     short loc_1801AA205
0x1801aa203  mov     ecx, esi
0x1801aa205  mov     dword ptr [rbp+var_50+4], ecx
0x1801aa208  jmp     loc_1801AA09E
0x1801aa20d  call    sub_1801B5AD0
0x1801aa213  call    sub_1801B5AD0
```
