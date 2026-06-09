# sqlite3FindTable

- ea: `0x14005ae90`
- end: `0x14005b0ab`
- name: `sqlite3FindTable`
- size: `539`
- prototype: ``
- caller_count: `19`
- callee_count: `4`
- tags: ``

## callers

- `0x14001c0f0`
- `0x14003c13c`
- `0x140042df0`
- `0x140043df8`
- `0x140044150`
- `0x14004a928`
- `0x14004af6c`
- `0x14004b2f4`
- `0x1400507bc`
- `0x140052db4`
- `0x14005b9d0`
- `0x1400626b8`
- `0x140066370`
- `0x14006b2f0`
- `0x14006f318`
- `0x14006fc1c`
- `0x14007ec64`
- `0x14007ed5c`
- `0x14008ebb0`

## callees

- `0x14002c1b8`
- `0x14005ae90`
- `0x1400702ec`
- `0x14008eb20`

## string_xrefs

- `0x14005b082`: `sqlite_temp_master`

## pseudocode

```c
__int64 __fastcall sqlite3FindTable(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // r11d
  int v7; // edi
  __int64 v8; // r14
  __int64 v9; // r14
  __int64 v10; // rsi
  __int64 v11; // rbp
  char *v12; // rdx
  __int64 v13; // rcx
  __int64 result; // rax
  __int64 v15; // rcx
  const char *v16; // rdx
  int v17; // edi

  if ( !a3 )
  {
    result = *(_QWORD *)(findElementWithHash(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 56LL) + 8LL, a2, 0) + 16);
    if ( result )
      return result;
    v10 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 24LL) + 8LL, a2, 0) + 16);
    if ( v10 )
      return v10;
    v17 = 2;
    if ( *(int *)(a1 + 40) > 2 )
    {
      do
      {
        v10 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(32LL * v17 + *(_QWORD *)(a1 + 32) + 24) + 8LL, a2, 0) + 16);
        if ( v10 )
          return v10;
      }
      while ( ++v17 < *(_DWORD *)(a1 + 40) );
    }
    if ( (unsigned int)sqlite3_strnicmp(a2, "sqlite_", 7) )
      return v10;
    if ( (unsigned int)sqlite3StrICmp(a2 + 7, "schema") )
    {
      v12 = "temp_schema";
      v13 = a2 + 7;
      goto LABEL_28;
    }
    v15 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 24LL);
LABEL_18:
    v16 = "sqlite_master";
    return *(_QWORD *)(findElementWithHash(v15 + 8, v16, 0) + 16);
  }
  v6 = *(_DWORD *)(a1 + 40);
  v7 = 0;
  if ( v6 <= 0 )
  {
LABEL_6:
    if ( v7 >= v6 )
    {
      if ( (unsigned int)sqlite3StrICmp(a3, "main") )
        return 0;
      v7 = 0;
    }
  }
  else
  {
    v8 = *(_QWORD *)(a1 + 32);
    while ( (unsigned int)sqlite3StrICmp(a3, *(_QWORD *)(32LL * (unsigned int)v7 + v8)) )
    {
      if ( ++v7 >= v6 )
        goto LABEL_6;
    }
  }
  v9 = 32LL * v7;
  v10 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(v9 + *(_QWORD *)(a1 + 32) + 24) + 8LL, a2, 0) + 16);
  if ( v10 || (unsigned int)sqlite3_strnicmp(a2, "sqlite_", 7) )
    return v10;
  v11 = a2 + 7;
  if ( v7 != 1 )
  {
    if ( (unsigned int)sqlite3StrICmp(v11, "schema") )
      return v10;
    v15 = *(_QWORD *)(v9 + *(_QWORD *)(a1 + 32) + 24);
    goto LABEL_18;
  }
  if ( !(unsigned int)sqlite3StrICmp(v11, "temp_schema") || !(unsigned int)sqlite3StrICmp(v11, "schema") )
    goto LABEL_29;
  v12 = "master";
  v13 = v11;
LABEL_28:
  if ( !(unsigned int)sqlite3StrICmp(v13, v12) )
  {
LABEL_29:
    v16 = "sqlite_temp_master";
    v15 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 56LL);
    return *(_QWORD *)(findElementWithHash(v15 + 8, v16, 0) + 16);
  }
  return v10;
}

```

## disassembly

```asm
0x14005ae90  push    rbx
0x14005ae92  push    rbp
0x14005ae93  push    rsi
0x14005ae94  push    rdi
0x14005ae95  push    r14
0x14005ae97  sub     rsp, 20h
0x14005ae9b  mov     rsi, r8
0x14005ae9e  mov     rbp, rdx
0x14005aea1  mov     rbx, rcx
0x14005aea4  test    r8, r8
0x14005aea7  jz      loc_14005AFB4
0x14005aead  mov     r11d, [rcx+28h]
0x14005aeb1  xor     edi, edi
0x14005aeb3  test    r11d, r11d
0x14005aeb6  jle     short loc_14005AED9
0x14005aeb8  mov     r14, [rcx+20h]
0x14005aebc  mov     edx, edi
0x14005aebe  mov     rcx, rsi
0x14005aec1  shl     rdx, 5
0x14005aec5  mov     rdx, [rdx+r14]
0x14005aec9  call    sqlite3StrICmp
0x14005aece  test    eax, eax
0x14005aed0  jz      short loc_14005AEF7
0x14005aed2  inc     edi
0x14005aed4  cmp     edi, r11d
0x14005aed7  jl      short loc_14005AEBC
0x14005aed9  cmp     edi, r11d
0x14005aedc  jl      short loc_14005AEF7
0x14005aede  lea     rdx, aMain; "main"
0x14005aee5  mov     rcx, rsi
0x14005aee8  call    sqlite3StrICmp
0x14005aeed  test    eax, eax
0x14005aeef  jnz     loc_14005AF84
0x14005aef5  xor     edi, edi
0x14005aef7  mov     rax, [rbx+20h]
0x14005aefb  xor     r8d, r8d
0x14005aefe  movsxd  r14, edi
0x14005af01  mov     rdx, rbp
0x14005af04  shl     r14, 5
0x14005af08  mov     rcx, [r14+rax+18h]
0x14005af0d  add     rcx, 8
0x14005af11  call    findElementWithHash
0x14005af16  mov     rsi, [rax+10h]
0x14005af1a  test    rsi, rsi
0x14005af1d  jnz     loc_14005B09D
0x14005af23  lea     r8d, [rsi+7]
0x14005af27  mov     rcx, rbp
0x14005af2a  lea     rdx, aSqlite_0; "sqlite_"
0x14005af31  call    sqlite3_strnicmp
0x14005af36  test    eax, eax
0x14005af38  jnz     loc_14005B09D
0x14005af3e  add     rbp, 7
0x14005af42  mov     rcx, rbp
0x14005af45  cmp     edi, 1
0x14005af48  jnz     short loc_14005AF8B
0x14005af4a  lea     rdx, aSqliteTempSche+7; "temp_schema"
0x14005af51  call    sqlite3StrICmp
0x14005af56  test    eax, eax
0x14005af58  jz      loc_14005B07E
0x14005af5e  lea     rdx, aSqliteSchema+7; "schema"
0x14005af65  mov     rcx, rbp
0x14005af68  call    sqlite3StrICmp
0x14005af6d  test    eax, eax
0x14005af6f  jz      loc_14005B07E
0x14005af75  lea     rdx, aSqliteMaster+7; "master"
0x14005af7c  mov     rcx, rbp
0x14005af7f  jmp     loc_14005B075
0x14005af84  xor     eax, eax
0x14005af86  jmp     loc_14005B0A0
0x14005af8b  lea     rdx, aSqliteSchema+7; "schema"
0x14005af92  call    sqlite3StrICmp
0x14005af97  test    eax, eax
0x14005af99  jnz     loc_14005B09D
0x14005af9f  mov     rax, [rbx+20h]
0x14005afa3  mov     rcx, [r14+rax+18h]
0x14005afa8  lea     rdx, aSqliteMaster; "sqlite_master"
0x14005afaf  jmp     loc_14005B08D
0x14005afb4  mov     rax, [rcx+20h]
0x14005afb8  xor     r8d, r8d
0x14005afbb  mov     rcx, [rax+38h]
0x14005afbf  add     rcx, 8
0x14005afc3  call    findElementWithHash
0x14005afc8  mov     rax, [rax+10h]
0x14005afcc  test    rax, rax
0x14005afcf  jnz     loc_14005B0A0
0x14005afd5  mov     rax, [rbx+20h]
0x14005afd9  xor     r8d, r8d
0x14005afdc  mov     rdx, rbp
0x14005afdf  mov     rcx, [rax+18h]
0x14005afe3  add     rcx, 8
0x14005afe7  call    findElementWithHash
0x14005afec  mov     rsi, [rax+10h]
0x14005aff0  test    rsi, rsi
0x14005aff3  jnz     loc_14005B09D
0x14005aff9  lea     edi, [rsi+2]
0x14005affc  cmp     [rbx+28h], edi
0x14005afff  jle     short loc_14005B030
0x14005b001  mov     rax, [rbx+20h]
0x14005b005  xor     r8d, r8d
0x14005b008  movsxd  rcx, edi
0x14005b00b  mov     rdx, rbp
0x14005b00e  shl     rcx, 5
0x14005b012  mov     rcx, [rcx+rax+18h]
0x14005b017  add     rcx, 8
0x14005b01b  call    findElementWithHash
0x14005b020  mov     rsi, [rax+10h]
0x14005b024  test    rsi, rsi
0x14005b027  jnz     short loc_14005B09D
0x14005b029  inc     edi
0x14005b02b  cmp     edi, [rbx+28h]
0x14005b02e  jl      short loc_14005B001
0x14005b030  mov     r8d, 7
0x14005b036  lea     rdx, aSqlite_0; "sqlite_"
0x14005b03d  mov     rcx, rbp
0x14005b040  call    sqlite3_strnicmp
0x14005b045  test    eax, eax
0x14005b047  jnz     short loc_14005B09D
0x14005b049  lea     rdx, aSqliteSchema+7; "schema"
0x14005b050  lea     rcx, [rbp+7]
0x14005b054  call    sqlite3StrICmp
0x14005b059  test    eax, eax
0x14005b05b  jnz     short loc_14005B06A
0x14005b05d  mov     rax, [rbx+20h]
0x14005b061  mov     rcx, [rax+18h]
0x14005b065  jmp     loc_14005AFA8
0x14005b06a  lea     rdx, aSqliteTempSche+7; "temp_schema"
0x14005b071  lea     rcx, [rbp+7]
0x14005b075  call    sqlite3StrICmp
0x14005b07a  test    eax, eax
0x14005b07c  jnz     short loc_14005B09D
0x14005b07e  mov     rax, [rbx+20h]
0x14005b082  lea     rdx, aSqliteTempMast; "sqlite_temp_master"
0x14005b089  mov     rcx, [rax+38h]
0x14005b08d  xor     r8d, r8d
0x14005b090  add     rcx, 8
0x14005b094  call    findElementWithHash
0x14005b099  mov     rsi, [rax+10h]
0x14005b09d  mov     rax, rsi
0x14005b0a0  add     rsp, 20h
0x14005b0a4  pop     r14
0x14005b0a6  pop     rdi
0x14005b0a7  pop     rsi
0x14005b0a8  pop     rbp
0x14005b0a9  pop     rbx
0x14005b0aa  retn
```
