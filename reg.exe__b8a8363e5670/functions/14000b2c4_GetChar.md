# GetChar

- ea: `0x14000b2c4`
- end: `0x14000b411`
- name: `GetChar`
- size: `333`
- prototype: `__int64 __fastcall(_WORD *)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000b418`
- `0x14000b54c`
- `0x14000b91c`
- `0x14000bbf0`
- `0x14000bd2c`
- `0x14000bdc4`
- `0x14000bf2c`
- `0x14000c0cc`
- `0x14000cd24`
- `0x14000cd84`

## callees

- `0x14000b2c4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000b321`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000b341`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000b321`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000b341`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14000b386`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14000b386`

## pseudocode

```c
__int64 __fastcall GetChar(_WORD *a1)
{
  int v1; // r8d
  bool v3; // cc
  int v4; // ecx
  int v5; // eax
  __int64 result; // rax
  int v7; // r9d
  unsigned int v8; // eax
  unsigned int v9; // eax
  int cbMultiByte; // [rsp+48h] [rbp+10h] BYREF

  v1 = qword_140055248;
  cbMultiByte = 0;
  v3 = (int)qword_140055248 < dword_140055250;
  if ( (_DWORD)qword_140055248 != dword_140055250 )
    goto LABEL_17;
  if ( s_fTreatFileAsUnicode != 1 )
  {
    if ( ReadFile(hObject, s_FileIo, 0x10000u, (LPDWORD)&cbMultiByte, 0) )
    {
      v5 = MultiByteToWideChar(3u, 1u, s_FileIo, cbMultiByte, &WideCharStr, 0x10000);
      v4 = cbMultiByte;
      goto LABEL_9;
    }
LABEL_6:
    g_FileErrorStringID = 703;
    return 0;
  }
  if ( !ReadFile(hObject, &WideCharStr, 0x10000u, (LPDWORD)&cbMultiByte, 0) )
    goto LABEL_6;
  v4 = cbMultiByte;
  v5 = cbMultiByte / 2;
LABEL_9:
  dword_140055250 = v5;
  v7 = v5;
  v1 = 0;
  v8 = v4 + HIDWORD(qword_140055254);
  LODWORD(qword_140055248) = 0;
  HIDWORD(qword_140055254) += v4;
  if ( (_DWORD)qword_140055254 )
  {
    v9 = v8 / (unsigned int)qword_140055254;
    if ( v9 > 0x64 )
      v9 = 100;
  }
  else
  {
    v9 = 100;
  }
  if ( unk_14005525C != v9 )
    unk_14005525C = v9;
  v3 = v7 > 0;
LABEL_17:
  if ( !v3 )
    return 0;
  result = 1;
  *a1 = *(_WORD *)&s_FileIo[2 * v1 + 0x20000];
  LODWORD(qword_140055248) = qword_140055248 + 1;
  return result;
}

```

## disassembly

```asm
0x14000b2c4  mov     rax, rsp
0x14000b2c7  mov     [rax+8], rbx
0x14000b2cb  push    rbp
0x14000b2cc  sub     rsp, 30h
0x14000b2d0  mov     r8d, dword ptr cs:qword_140055248
0x14000b2d7  lea     rbp, s_FileIo
0x14000b2de  mov     r9d, cs:dword_140055250
0x14000b2e5  mov     rbx, rcx
0x14000b2e8  mov     dword ptr [rax+10h], 0
0x14000b2ef  cmp     r8d, r9d
0x14000b2f2  jnz     loc_14000B3E6
0x14000b2f8  cmp     cs:s_fTreatFileAsUnicode, 1
0x14000b2ff  lea     r9, [rax+10h]; lpNumberOfBytesRead
0x14000b303  mov     rcx, cs:hObject; hFile
0x14000b30a  mov     r8d, 10000h; nNumberOfBytesToRead
0x14000b310  mov     qword ptr [rax-18h], 0
0x14000b318  jnz     short loc_14000B33E
0x14000b31a  lea     rdx, WideCharStr; lpBuffer
0x14000b321  call    cs:__imp_ReadFile
0x14000b328  nop     dword ptr [rax+rax+00h]
0x14000b32d  test    eax, eax
0x14000b32f  jz      short loc_14000B351
0x14000b331  mov     ecx, [rsp+38h+cbMultiByte]
0x14000b335  mov     eax, ecx
0x14000b337  cdq
0x14000b338  sub     eax, edx
0x14000b33a  sar     eax, 1
0x14000b33c  jmp     short loc_14000B396
0x14000b33e  mov     rdx, rbp; lpBuffer
0x14000b341  call    cs:__imp_ReadFile
0x14000b348  nop     dword ptr [rax+rax+00h]
0x14000b34d  test    eax, eax
0x14000b34f  jnz     short loc_14000B362
0x14000b351  mov     cs:g_FileErrorStringID, 2BFh
0x14000b35b  xor     eax, eax
0x14000b35d  jmp     loc_14000B405
0x14000b362  mov     r9d, [rsp+38h+cbMultiByte]; cbMultiByte
0x14000b367  lea     rax, WideCharStr
0x14000b36e  mov     edx, 1; dwFlags
0x14000b373  mov     [rsp+38h+cchWideChar], 10000h; cchWideChar
0x14000b37b  mov     r8, rbp; lpMultiByteStr
0x14000b37e  mov     [rsp+38h+lpWideCharStr], rax; lpWideCharStr
0x14000b383  lea     ecx, [rdx+2]; CodePage
0x14000b386  call    cs:__imp_MultiByteToWideChar
0x14000b38d  nop     dword ptr [rax+rax+00h]
0x14000b392  mov     ecx, [rsp+38h+cbMultiByte]
0x14000b396  mov     cs:dword_140055250, eax
0x14000b39c  mov     r9d, eax
0x14000b39f  mov     eax, dword ptr cs:qword_140055254+4
0x14000b3a5  xor     r8d, r8d
0x14000b3a8  add     eax, ecx
0x14000b3aa  mov     dword ptr cs:qword_140055248, r8d
0x14000b3b1  mov     ecx, dword ptr cs:qword_140055254
0x14000b3b7  mov     dword ptr cs:qword_140055254+4, eax
0x14000b3bd  test    ecx, ecx
0x14000b3bf  jz      short loc_14000B3D0
0x14000b3c1  xor     edx, edx
0x14000b3c3  div     ecx
0x14000b3c5  lea     ecx, [r8+64h]
0x14000b3c9  cmp     eax, ecx
0x14000b3cb  cmova   eax, ecx
0x14000b3ce  jmp     short loc_14000B3D5
0x14000b3d0  mov     eax, 64h ; 'd'
0x14000b3d5  cmp     dword ptr cs:unk_14005525C, eax
0x14000b3db  jz      short loc_14000B3E3
0x14000b3dd  mov     dword ptr cs:unk_14005525C, eax
0x14000b3e3  cmp     r8d, r9d
0x14000b3e6  jge     loc_14000B35B
0x14000b3ec  movsxd  rcx, r8d
0x14000b3ef  mov     eax, 1
0x14000b3f4  movzx   ecx, word ptr [rbp+rcx*2+20000h]
0x14000b3fc  mov     [rbx], cx
0x14000b3ff  inc     dword ptr cs:qword_140055248
0x14000b405  mov     rbx, [rsp+38h+arg_0]
0x14000b40a  add     rsp, 30h
0x14000b40e  pop     rbp
0x14000b40f  retn
```
