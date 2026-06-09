# winDelete

- ea: `0x14009eae0`
- end: `0x14009ebbd`
- name: `winDelete`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400a0d90`

## callees

- `0x14008ac90`
- `0x14009eae0`
- `0x14009fa4c`
- `0x14009fb28`
- `0x1400a07a8`
- `0x1400a1544`
- `0x1400a8010`

## string_xrefs

- `0x14009eb80`: `winDelete`

## pseudocode

```c
__int64 __fastcall winDelete(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // ebx
  __int64 v4; // rdi
  int v6; // eax
  DWORD v7; // edx
  unsigned int v8; // ebx
  _DWORD v9[6]; // [rsp+30h] [rbp-18h] BYREF
  DWORD v10; // [rsp+68h] [rbp+20h] BYREF

  v9[0] = 0;
  v3 = a2;
  v10 = 0;
  v4 = winUtf8ToUnicode(a2, a2, a3);
  if ( !v4 )
    return 3082;
  while ( 1 )
  {
    v6 = ((__int64 (__fastcall *)(__int64))off_1400C5BF0)(v4);
    if ( v6 == -1 )
    {
      v7 = off_1400C5C68();
      if ( v7 - 2 <= 1 )
      {
        v8 = 5898;
        goto LABEL_12;
      }
LABEL_10:
      v8 = winLogErrorAtLine(2570, v7, (unsigned int)"winDelete", v3, 51229);
      goto LABEL_13;
    }
    if ( (v6 & 0x10) != 0 )
      goto LABEL_7;
    if ( (unsigned int)((__int64 (__fastcall *)(__int64))off_1400C5AE8)(v4) )
      break;
    if ( !(unsigned int)winRetryIoerr(v9, &v10) )
    {
LABEL_7:
      v7 = v10;
      goto LABEL_10;
    }
  }
  v8 = 0;
LABEL_12:
  winLogIoerr(v9[0], 51231);
LABEL_13:
  sqlite3_free(v4);
  return v8;
}

```

## disassembly

```asm
0x14009eae0  mov     [rsp+arg_0], rbx
0x14009eae5  push    rdi
0x14009eae6  sub     rsp, 40h
0x14009eaea  mov     rcx, rdx
0x14009eaed  mov     [rsp+48h+var_18], 0
0x14009eaf5  mov     rbx, rdx
0x14009eaf8  mov     [rsp+48h+arg_18], 0
0x14009eb00  call    winUtf8ToUnicode
0x14009eb05  mov     rdi, rax
0x14009eb08  test    rax, rax
0x14009eb0b  jnz     short loc_14009EB17
0x14009eb0d  mov     eax, 0C0Ah
0x14009eb12  jmp     loc_14009EBB2
0x14009eb17  mov     rax, cs:off_1400C5BF0
0x14009eb1e  mov     rcx, rdi
0x14009eb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009eb26  cmp     eax, 0FFFFFFFFh
0x14009eb29  jz      short loc_14009EB5F
0x14009eb2b  test    al, 10h
0x14009eb2d  jnz     short loc_14009EB55
0x14009eb2f  mov     rax, cs:off_1400C5AE8
0x14009eb36  mov     rcx, rdi
0x14009eb39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009eb3e  test    eax, eax
0x14009eb40  jnz     short loc_14009EB5B
0x14009eb42  lea     rdx, [rsp+48h+arg_18]
0x14009eb47  lea     rcx, [rsp+48h+var_18]
0x14009eb4c  call    winRetryIoerr
0x14009eb51  test    eax, eax
0x14009eb53  jnz     short loc_14009EB17
0x14009eb55  mov     edx, [rsp+48h+arg_18]
0x14009eb59  jmp     short loc_14009EB75
0x14009eb5b  xor     ebx, ebx
0x14009eb5d  jmp     short loc_14009EB9A
0x14009eb5f  mov     rax, cs:off_1400C5C68
0x14009eb66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009eb6b  mov     edx, eax
0x14009eb6d  add     eax, 0FFFFFFFEh
0x14009eb70  cmp     eax, 1
0x14009eb73  jbe     short loc_14009EB95
0x14009eb75  mov     r9, rbx
0x14009eb78  mov     [rsp+48h+var_28], 0C81Dh
0x14009eb80  lea     r8, aWindelete; "winDelete"
0x14009eb87  mov     ecx, 0A0Ah
0x14009eb8c  call    winLogErrorAtLine
0x14009eb91  mov     ebx, eax
0x14009eb93  jmp     short loc_14009EBA8
0x14009eb95  mov     ebx, 170Ah
0x14009eb9a  mov     ecx, [rsp+48h+var_18]
0x14009eb9e  mov     edx, 0C81Fh
0x14009eba3  call    winLogIoerr
0x14009eba8  mov     rcx, rdi
0x14009ebab  call    sqlite3_free
0x14009ebb0  mov     eax, ebx
0x14009ebb2  mov     rbx, [rsp+48h+arg_0]
0x14009ebb7  add     rsp, 40h
0x14009ebbb  pop     rdi
0x14009ebbc  retn
```
