# GetChar

- ea: `0x14000ac00`
- end: `0x14000ad3a`
- name: `GetChar`
- size: `314`
- prototype: `__int64 __fastcall(_WORD *)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000ad40`
- `0x14000ae58`
- `0x14000b1d4`
- `0x14000b480`
- `0x14000b5a8`
- `0x14000b640`
- `0x14000b7a8`
- `0x14000b93c`
- `0x14000c500`
- `0x14000c560`

## callees

- `0x14000ac00`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000ac5d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000ac77`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000ac5d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000ac77`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14000acb6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14000acb6`

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

  v1 = qword_140054248;
  cbMultiByte = 0;
  v3 = (int)qword_140054248 < dword_140054250;
  if ( (_DWORD)qword_140054248 != dword_140054250 )
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
  dword_140054250 = v5;
  v7 = v5;
  v1 = 0;
  v8 = v4 + MEMORY[0x140054258];
  LODWORD(qword_140054248) = 0;
  LODWORD(MEMORY[0x140054258]) = v4 + MEMORY[0x140054258];
  if ( qword_140054254 )
  {
    v9 = v8 / qword_140054254;
    if ( v9 > 0x64 )
      v9 = 100;
  }
  else
  {
    v9 = 100;
  }
  if ( HIDWORD(MEMORY[0x140054258]) != v9 )
    HIDWORD(MEMORY[0x140054258]) = v9;
  v3 = v7 > 0;
LABEL_17:
  if ( !v3 )
    return 0;
  result = 1;
  *a1 = *(_WORD *)&s_FileIo[2 * v1 + 0x20000];
  LODWORD(qword_140054248) = qword_140054248 + 1;
  return result;
}

```

## disassembly

```asm
0x14000ac00  mov     rax, rsp
0x14000ac03  mov     [rax+8], rbx
0x14000ac07  push    rbp
0x14000ac08  sub     rsp, 30h
0x14000ac0c  mov     r8d, dword ptr cs:qword_140054248
0x14000ac13  lea     rbp, s_FileIo
0x14000ac1a  mov     r9d, cs:dword_140054250
0x14000ac21  mov     rbx, rcx
0x14000ac24  mov     dword ptr [rax+10h], 0
0x14000ac2b  cmp     r8d, r9d
0x14000ac2e  jnz     loc_14000AD10
0x14000ac34  cmp     cs:s_fTreatFileAsUnicode, 1
0x14000ac3b  lea     r9, [rax+10h]; lpNumberOfBytesRead
0x14000ac3f  mov     rcx, cs:hObject; hFile
0x14000ac46  mov     r8d, 10000h; nNumberOfBytesToRead
0x14000ac4c  mov     qword ptr [rax-18h], 0
0x14000ac54  jnz     short loc_14000AC74
0x14000ac56  lea     rdx, WideCharStr; lpBuffer
0x14000ac5d  call    cs:__imp_ReadFile
0x14000ac63  test    eax, eax
0x14000ac65  jz      short loc_14000AC81
0x14000ac67  mov     ecx, [rsp+38h+cbMultiByte]
0x14000ac6b  mov     eax, ecx
0x14000ac6d  cdq
0x14000ac6e  sub     eax, edx
0x14000ac70  sar     eax, 1
0x14000ac72  jmp     short loc_14000ACC0
0x14000ac74  mov     rdx, rbp; lpBuffer
0x14000ac77  call    cs:__imp_ReadFile
0x14000ac7d  test    eax, eax
0x14000ac7f  jnz     short loc_14000AC92
0x14000ac81  mov     cs:g_FileErrorStringID, 2BFh
0x14000ac8b  xor     eax, eax
0x14000ac8d  jmp     loc_14000AD2F
0x14000ac92  mov     r9d, [rsp+38h+cbMultiByte]; cbMultiByte
0x14000ac97  lea     rax, WideCharStr
0x14000ac9e  mov     edx, 1; dwFlags
0x14000aca3  mov     [rsp+38h+cchWideChar], 10000h; cchWideChar
0x14000acab  mov     r8, rbp; lpMultiByteStr
0x14000acae  mov     [rsp+38h+lpWideCharStr], rax; lpWideCharStr
0x14000acb3  lea     ecx, [rdx+2]; CodePage
0x14000acb6  call    cs:__imp_MultiByteToWideChar
0x14000acbc  mov     ecx, [rsp+38h+cbMultiByte]
0x14000acc0  mov     cs:dword_140054250, eax
0x14000acc6  mov     r9d, eax
0x14000acc9  mov     eax, dword ptr cs:qword_140054254+4
0x14000accf  xor     r8d, r8d
0x14000acd2  add     eax, ecx
0x14000acd4  mov     dword ptr cs:qword_140054248, r8d
0x14000acdb  mov     ecx, dword ptr cs:qword_140054254
0x14000ace1  mov     dword ptr cs:qword_140054254+4, eax
0x14000ace7  test    ecx, ecx
0x14000ace9  jz      short loc_14000ACFA
0x14000aceb  xor     edx, edx
0x14000aced  div     ecx
0x14000acef  lea     ecx, [r8+64h]
0x14000acf3  cmp     eax, ecx
0x14000acf5  cmova   eax, ecx
0x14000acf8  jmp     short loc_14000ACFF
0x14000acfa  mov     eax, 64h ; 'd'
0x14000acff  cmp     dword ptr cs:unk_14005425C, eax
0x14000ad05  jz      short loc_14000AD0D
0x14000ad07  mov     dword ptr cs:unk_14005425C, eax
0x14000ad0d  cmp     r8d, r9d
0x14000ad10  jge     loc_14000AC8B
0x14000ad16  movsxd  rcx, r8d
0x14000ad19  mov     eax, 1
0x14000ad1e  movzx   ecx, word ptr [rbp+rcx*2+20000h]
0x14000ad26  mov     [rbx], cx
0x14000ad29  inc     dword ptr cs:qword_140054248
0x14000ad2f  mov     rbx, [rsp+38h+arg_0]
0x14000ad34  add     rsp, 30h
0x14000ad38  pop     rbp
0x14000ad39  retn
```
