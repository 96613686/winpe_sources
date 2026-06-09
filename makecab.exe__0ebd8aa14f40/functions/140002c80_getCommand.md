# getCommand

- ea: `0x140002c80`
- end: `0x140003135`
- name: `getCommand`
- size: `1205`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140001de0`

## callees

- `0x140002344`
- `0x140002c80`
- `0x1400038b8`
- `0x140003934`
- `0x140008620`
- `0x14000d698`
- `0x14000e406`
- `0x14000e450`

## import_xrefs

- `msvcrt!strspn` at `0x140002cba`
- `msvcrt!strspn` at `0x140002db8`
- `msvcrt!strspn` at `0x140002cba`
- `msvcrt!strspn` at `0x140002db8`
- `msvcrt!_stricmp` at `0x140002d3a`
- `msvcrt!_stricmp` at `0x140002e0c`
- `msvcrt!_stricmp` at `0x140002e2c`
- `msvcrt!_stricmp` at `0x140002e4c`
- `msvcrt!_stricmp` at `0x140002fa7`
- `msvcrt!_stricmp` at `0x140002fc7`
- `msvcrt!_stricmp` at `0x140002fe7`
- `msvcrt!_stricmp` at `0x14000309a`
- `msvcrt!_stricmp` at `0x1400030b7`
- `msvcrt!_stricmp` at `0x140002d3a`
- `msvcrt!_stricmp` at `0x140002e0c`
- `msvcrt!_stricmp` at `0x140002e2c`
- `msvcrt!_stricmp` at `0x140002e4c`
- `msvcrt!_stricmp` at `0x140002fa7`
- `msvcrt!_stricmp` at `0x140002fc7`
- `msvcrt!_stricmp` at `0x140002fe7`
- `msvcrt!_stricmp` at `0x14000309a`
- `msvcrt!_stricmp` at `0x1400030b7`
- `msvcrt!strpbrk` at `0x140002cd1`
- `msvcrt!strpbrk` at `0x140002ebd`
- `msvcrt!strpbrk` at `0x140002cd1`
- `msvcrt!strpbrk` at `0x140002ebd`

## string_xrefs

- `0x140002ea0`: `Delete`
- `0x140002ec8`: `Delete`
- `0x140002ea7`: `No variable name in %1 command`
- `0x140002cfb`: `Command name too long: %1`
- `0x140002ecf`: `Unexpected parameters on %1 command: %2`
- `0x140002f2e`: `%1 command without %2 command`
- `0x140002d66`: `Unknown command: %1`

## pseudocode

```c
__int64 __fastcall getCommand(__int64 a1, __int64 a2, const char *a3, __int64 a4)
{
  const char *v8; // r15
  char *v9; // rax
  size_t v10; // rbx
  char *v11; // r9
  const char *v12; // rdx
  int v13; // edi
  int v15; // edi
  const char *v16; // rbx
  int v17; // r9d
  int v18; // edi
  int v19; // edi
  int v20; // edi
  int v21; // edi
  const char *v22; // r9
  const char *v23; // rdx
  const char *v24; // r9
  const char *v25; // r9
  char *v26; // rbp
  char *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // r8
  char *v30; // rax
  __int16 v31; // ax
  int v32; // edi
  int v33; // edi
  int v34; // [rsp+30h] [rbp-98h] BYREF
  const char *v35; // [rsp+38h] [rbp-90h] BYREF
  __int64 v36; // [rsp+40h] [rbp-88h] BYREF
  char String2[56]; // [rsp+48h] [rbp-80h] BYREF

  v8 = &a3[strspn(a3, " \t") + 1];
  v9 = strpbrk(v8, " \t");
  if ( v9 )
  {
    v10 = v9 - v8;
  }
  else
  {
    v10 = -1;
    do
      ++v10;
    while ( v8[v10] );
  }
  if ( v10 >= 0x32 )
  {
    v11 = (char *)a3;
    v12 = "Command name too long: %1";
LABEL_12:
    ErrSet(a4, v12, "%s", v11);
    return 0;
  }
  memcpy_0(String2, v8, v10);
  v13 = 0;
  String2[v10] = 0;
  if ( !acsatMap )
  {
LABEL_11:
    v11 = String2;
    v12 = "Unknown command: %1";
    goto LABEL_12;
  }
  while ( _stricmp((&acsatMap)[2 * v13], String2) )
  {
    if ( !(&acsatMap)[2 * ++v13] )
      goto LABEL_11;
  }
  v15 = (int)(&acsatMap)[2 * v13 + 1];
  if ( !v15 )
    return 0;
  *(_DWORD *)a1 = v15;
  v16 = &v8[v10 + strspn(&v8[v10], " \t")];
  if ( v15 <= 7 )
  {
    if ( v15 == 7 )
    {
      if ( !*(_DWORD *)(a2 + 200) )
      {
        ErrSet(a4, "%1 command without %2 command", "%s%s", "InfEnd", "InfBegin");
        return 0;
      }
      *(_QWORD *)(a2 + 200) = 0;
      return 1;
    }
    v18 = v15 - 1;
    if ( !v18 )
      return 1;
    v19 = v18 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( !v20 )
      {
        if ( !*v16 )
        {
          v11 = "Delete";
          v12 = "No variable name in %1 command";
          goto LABEL_12;
        }
        if ( !strpbrk(v16, " \t") )
        {
          v34 = 32;
          v36 = a1 + 8;
          v35 = v16;
          return (unsigned int)copyBounded(&v36, &v34, &v35, 0) != 0;
        }
        v22 = "Delete";
        v23 = "Unexpected parameters on %1 command: %2";
        goto LABEL_31;
      }
      v21 = v20 - 1;
      if ( v21 )
      {
        if ( v21 != 2 )
          return 0;
        if ( !_stricmp(v16, "File") )
        {
          *(_DWORD *)(a2 + 204) = 3;
LABEL_28:
          *(_DWORD *)(a2 + 200) = 1;
          return 1;
        }
        if ( !_stricmp(v16, "Cabinet") )
        {
          *(_DWORD *)(a2 + 204) = 2;
          goto LABEL_28;
        }
        if ( !_stricmp(v16, "Disk") )
        {
          *(_DWORD *)(a2 + 204) = 1;
          goto LABEL_28;
        }
        v22 = "InfBegin";
        v23 = "Unknown keyword in %1 directive: %2";
LABEL_31:
        ErrSet(a4, v23, "%s%s", v22, v16);
        return 0;
      }
      return 1;
    }
    return parseSetCommand(a1, a2, v16, a4);
  }
  if ( v15 == 8 || v15 == 9 || v15 == 10 )
  {
    if ( !(unsigned int)processLineWithQuotes((int)a1 + 12, 512, (_DWORD)v16, v17) )
      return 0;
    v32 = v15 - 8;
    if ( v32 )
    {
      v33 = v32 - 1;
      if ( v33 )
      {
        if ( v33 == 1 )
          *(_DWORD *)(a1 + 8) = 1;
      }
      else
      {
        *(_DWORD *)(a1 + 8) = 2;
      }
    }
    else
    {
      *(_DWORD *)(a1 + 8) = 3;
    }
    *(_DWORD *)a1 = 8;
    return 1;
  }
  if ( v15 != 11 )
  {
    if ( v15 != 12 )
    {
      if ( v15 != 14 )
        return 0;
      return parseSetCommand(a1, a2, v16, a4);
    }
    if ( !_stricmp(v16, "Folder") )
    {
      *(_DWORD *)(a1 + 8) = 1;
      return 1;
    }
    if ( !_stricmp(v16, "Cabinet") )
    {
      *(_DWORD *)(a1 + 8) = 2;
      return 1;
    }
    if ( !_stricmp(v16, "Disk") )
    {
      *(_DWORD *)(a1 + 8) = 3;
      return 1;
    }
    v24 = "New";
LABEL_55:
    ErrSet(a4, "Unknown keyword in %1 directive: %2", "%s%s", v24, v16);
    *(_DWORD *)(a1 + 8) = 0;
    return 0;
  }
  v25 = "No";
  v26 = (char *)(a2 + 484);
  *(_DWORD *)(a1 + 8) = 0;
  v27 = v26;
  v28 = 2147483646;
  v29 = 2048;
  do
  {
    if ( !v28 )
      break;
    if ( !*v25 )
      break;
    *v27++ = *v25++;
    --v28;
    --v29;
  }
  while ( v29 );
  v30 = v27 - 1;
  if ( v29 )
    v30 = v27;
  *v30 = 0;
  StringCchCatA(v26, 0x800u, "Explicit");
  if ( !_stricmp(v16, "Explicit") )
  {
    *(_WORD *)(a1 + 10) |= 1u;
    v31 = *(_WORD *)(a1 + 8) | 1;
  }
  else
  {
    if ( _stricmp(v16, v26) )
    {
      v24 = "Option";
      goto LABEL_55;
    }
    *(_WORD *)(a1 + 10) |= 1u;
    v31 = *(_WORD *)(a1 + 8) & 0xFFFE;
  }
  *(_WORD *)(a1 + 8) = v31;
  return 1;
}

```

## disassembly

```asm
0x140002c80  push    rbx
0x140002c82  push    rbp
0x140002c83  push    rsi
0x140002c84  push    rdi
0x140002c85  push    r12
0x140002c87  push    r14
0x140002c89  push    r15
0x140002c8b  sub     rsp, 90h
0x140002c92  mov     rax, cs:__security_cookie
0x140002c99  xor     rax, rsp
0x140002c9c  mov     [rsp+0C8h+var_48], rax
0x140002ca4  mov     rbp, rdx
0x140002ca7  mov     rsi, rcx
0x140002caa  lea     rdx, Control; " \t"
0x140002cb1  mov     rcx, r8; Str
0x140002cb4  mov     r14, r9
0x140002cb7  mov     rdi, r8
0x140002cba  call    cs:__imp_strspn
0x140002cc0  lea     r15, [rdi+1]
0x140002cc4  add     r15, rax
0x140002cc7  lea     rdx, Control; " \t"
0x140002cce  mov     rcx, r15; Str
0x140002cd1  call    cs:__imp_strpbrk
0x140002cd7  mov     rbx, rax
0x140002cda  test    rax, rax
0x140002cdd  jnz     short loc_140002CEF
0x140002cdf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140002ce3  inc     rbx
0x140002ce6  cmp     byte ptr [r15+rbx], 0
0x140002ceb  jnz     short loc_140002CE3
0x140002ced  jmp     short loc_140002CF2
0x140002cef  sub     rbx, r15
0x140002cf2  cmp     rbx, 32h ; '2'
0x140002cf6  jb      short loc_140002D04
0x140002cf8  mov     r9, rdi
0x140002cfb  lea     rdx, aCommandNameToo; "Command name too long: %1"
0x140002d02  jmp     short loc_140002D6D
0x140002d04  mov     r8, rbx; Size
0x140002d07  lea     rcx, [rsp+0C8h+String2]; void *
0x140002d0c  mov     rdx, r15; Src
0x140002d0f  call    memcpy_0
0x140002d14  xor     edi, edi
0x140002d16  mov     [rsp+rbx+0C8h+String2], 0
0x140002d1b  cmp     cs:acsatMap, rdi
0x140002d22  jz      short loc_140002D61
0x140002d24  lea     rax, acsatMap
0x140002d2b  movsxd  r12, edi
0x140002d2e  lea     rdx, [rsp+0C8h+String2]; String2
0x140002d33  add     r12, r12
0x140002d36  mov     rcx, [rax+r12*8]; String1
0x140002d3a  call    cs:__imp__stricmp
0x140002d40  lea     rcx, acsatMap
0x140002d47  test    eax, eax
0x140002d49  jz      short loc_140002DA0
0x140002d4b  inc     edi
0x140002d4d  movsxd  rax, edi
0x140002d50  add     rax, rax
0x140002d53  cmp     qword ptr [rcx+rax*8], 0
0x140002d58  lea     rax, acsatMap
0x140002d5f  jnz     short loc_140002D2B
0x140002d61  lea     r9, [rsp+0C8h+String2]
0x140002d66  lea     rdx, aUnknownCommand; "Unknown command: %1"
0x140002d6d  lea     r8, aS_4; "%s"
0x140002d74  mov     rcx, r14
0x140002d77  call    ErrSet
0x140002d7c  xor     eax, eax
0x140002d7e  mov     rcx, [rsp+0C8h+var_48]
0x140002d86  xor     rcx, rsp; StackCookie
0x140002d89  call    __security_check_cookie
0x140002d8e  add     rsp, 90h
0x140002d95  pop     r15
0x140002d97  pop     r14
0x140002d99  pop     r12
0x140002d9b  pop     rdi
0x140002d9c  pop     rsi
0x140002d9d  pop     rbp
0x140002d9e  pop     rbx
0x140002d9f  retn
0x140002da0  mov     edi, [rcx+r12*8+8]
0x140002da5  test    edi, edi
0x140002da7  jz      short loc_140002D7C
0x140002da9  add     rbx, r15
0x140002dac  mov     [rsi], edi
0x140002dae  mov     rcx, rbx; Str
0x140002db1  lea     rdx, Control; " \t"
0x140002db8  call    cs:__imp_strspn
0x140002dbe  add     rbx, rax
0x140002dc1  cmp     edi, 7
0x140002dc4  jg      loc_140002F4A
0x140002dca  jz      loc_140002F12
0x140002dd0  test    edi, edi
0x140002dd2  jz      short loc_140002D7C
0x140002dd4  sub     edi, 1
0x140002dd7  jz      loc_140002E6A
0x140002ddd  sub     edi, 1
0x140002de0  jz      loc_140002F87
0x140002de6  sub     edi, 1
0x140002de9  jz      loc_140002E9B
0x140002def  sub     edi, 1
0x140002df2  jz      short loc_140002E6A
0x140002df4  sub     edi, 1
0x140002df7  jz      short loc_140002D7C
0x140002df9  cmp     edi, 1
0x140002dfc  jnz     loc_140002D7C
0x140002e02  lea     rdx, aFile; "File"
0x140002e09  mov     rcx, rbx; String1
0x140002e0c  call    cs:__imp__stricmp
0x140002e12  test    eax, eax
0x140002e14  jnz     short loc_140002E22
0x140002e16  mov     dword ptr [rbp+0CCh], 3
0x140002e20  jmp     short loc_140002E60
0x140002e22  lea     rdx, aCabinet; "Cabinet"
0x140002e29  mov     rcx, rbx; String1
0x140002e2c  call    cs:__imp__stricmp
0x140002e32  test    eax, eax
0x140002e34  jnz     short loc_140002E42
0x140002e36  mov     dword ptr [rbp+0CCh], 2
0x140002e40  jmp     short loc_140002E60
0x140002e42  lea     rdx, aDisk_2; "Disk"
0x140002e49  mov     rcx, rbx; String1
0x140002e4c  call    cs:__imp__stricmp
0x140002e52  test    eax, eax
0x140002e54  jnz     short loc_140002E74
0x140002e56  mov     dword ptr [rbp+0CCh], 1
0x140002e60  mov     dword ptr [rbp+0C8h], 1
0x140002e6a  mov     eax, 1
0x140002e6f  jmp     loc_140002D7E
0x140002e74  lea     r9, aInfbegin; "InfBegin"
0x140002e7b  lea     rdx, aUnknownKeyword; "Unknown keyword in %1 directive: %2"
0x140002e82  mov     [rsp+0C8h+var_A8], rbx
0x140002e87  lea     r8, aSS_1; "%s%s"
0x140002e8e  mov     rcx, r14
0x140002e91  call    ErrSet
0x140002e96  jmp     loc_140002D7C
0x140002e9b  cmp     byte ptr [rbx], 0
0x140002e9e  jnz     short loc_140002EB3
0x140002ea0  lea     r9, aDelete; "Delete"
0x140002ea7  lea     rdx, aNoVariableName; "No variable name in %1 command"
0x140002eae  jmp     loc_140002D6D
0x140002eb3  lea     rdx, Control; " \t"
0x140002eba  mov     rcx, rbx; Str
0x140002ebd  call    cs:__imp_strpbrk
0x140002ec3  test    rax, rax
0x140002ec6  jz      short loc_140002ED8
0x140002ec8  lea     r9, aDelete; "Delete"
0x140002ecf  lea     rdx, aUnexpectedPara; "Unexpected parameters on %1 command: %2"
0x140002ed6  jmp     short loc_140002E82
0x140002ed8  lea     rax, [rsi+8]
0x140002edc  mov     [rsp+0C8h+var_98], 20h ; ' '
0x140002ee4  xor     r9d, r9d
0x140002ee7  mov     [rsp+0C8h+var_88], rax
0x140002eec  lea     r8, [rsp+0C8h+var_90]
0x140002ef1  mov     [rsp+0C8h+var_90], rbx
0x140002ef6  lea     rdx, [rsp+0C8h+var_98]
0x140002efb  lea     rcx, [rsp+0C8h+var_88]
0x140002f00  call    copyBounded
0x140002f05  test    eax, eax
0x140002f07  jz      loc_140002D7C
0x140002f0d  jmp     loc_140002E6A
0x140002f12  cmp     dword ptr [rbp+0C8h], 0
0x140002f19  jnz     short loc_140002F3A
0x140002f1b  lea     rax, aInfbegin; "InfBegin"
0x140002f22  mov     [rsp+0C8h+var_A8], rax
0x140002f27  lea     r9, aInfend; "InfEnd"
0x140002f2e  lea     rdx, a1CommandWithou; "%1 command without %2 command"
0x140002f35  jmp     loc_140002E87
0x140002f3a  mov     qword ptr [rbp+0C8h], 0
0x140002f45  jmp     loc_140002E6A
0x140002f4a  mov     ecx, edi
0x140002f4c  sub     ecx, 8
0x140002f4f  jz      loc_1400030E8
0x140002f55  sub     ecx, 1
0x140002f58  jz      loc_1400030E8
0x140002f5e  sub     ecx, 1
0x140002f61  jz      loc_1400030E8
0x140002f67  sub     ecx, 1
0x140002f6a  jz      loc_14000302B
0x140002f70  sub     ecx, 1
0x140002f73  jz      short loc_140002F9D
0x140002f75  sub     ecx, 1
0x140002f78  jz      loc_140002D7C
0x140002f7e  cmp     ecx, 1
0x140002f81  jnz     loc_140002D7C
0x140002f87  mov     r9, r14
0x140002f8a  mov     r8, rbx
0x140002f8d  mov     rdx, rbp
0x140002f90  mov     rcx, rsi
0x140002f93  call    parseSetCommand
0x140002f98  jmp     loc_140002D7E
0x140002f9d  lea     rdx, aFolder; "Folder"
0x140002fa4  mov     rcx, rbx; String1
0x140002fa7  call    cs:__imp__stricmp
0x140002fad  test    eax, eax
0x140002faf  jnz     short loc_140002FBD
0x140002fb1  mov     dword ptr [rsi+8], 1
0x140002fb8  jmp     loc_140002E6A
0x140002fbd  lea     rdx, aCabinet; "Cabinet"
0x140002fc4  mov     rcx, rbx; String1
0x140002fc7  call    cs:__imp__stricmp
0x140002fcd  test    eax, eax
0x140002fcf  jnz     short loc_140002FDD
0x140002fd1  mov     dword ptr [rsi+8], 2
0x140002fd8  jmp     loc_140002E6A
0x140002fdd  lea     rdx, aDisk_2; "Disk"
0x140002fe4  mov     rcx, rbx; String1
0x140002fe7  call    cs:__imp__stricmp
0x140002fed  test    eax, eax
0x140002fef  jnz     short loc_140002FFD
0x140002ff1  mov     dword ptr [rsi+8], 3
0x140002ff8  jmp     loc_140002E6A
0x140002ffd  lea     r9, aNew; "New"
0x140003004  lea     r8, aSS_1; "%s%s"
0x14000300b  mov     [rsp+0C8h+var_A8], rbx
0x140003010  lea     rdx, aUnknownKeyword; "Unknown keyword in %1 directive: %2"
0x140003017  mov     rcx, r14
0x14000301a  call    ErrSet
0x14000301f  mov     dword ptr [rsi+8], 0
0x140003026  jmp     loc_140002D7C
0x14000302b  xor     eax, eax
0x14000302d  lea     r9, String2; "No"
0x140003034  add     rbp, 1E4h
0x14000303b  mov     [rsi+8], eax
0x14000303e  mov     r10d, 800h
0x140003044  mov     rcx, rbp
0x140003047  mov     eax, 7FFFFFFEh
0x14000304c  mov     r8d, r10d
0x14000304f  mov     edi, 1
0x140003054  test    rax, rax
0x140003057  jz      short loc_140003070
0x140003059  mov     dl, [r9]
0x14000305c  test    dl, dl
0x14000305e  jz      short loc_140003070
0x140003060  mov     [rcx], dl
0x140003062  add     r9, rdi
0x140003065  add     rcx, rdi
0x140003068  sub     rax, rdi
0x14000306b  sub     r8, rdi
0x14000306e  jnz     short loc_140003054
0x140003070  test    r8, r8
0x140003073  lea     rax, [rcx-1]
0x140003077  lea     r8, pszSrc; "Explicit"
0x14000307e  mov     rdx, r10; cchDest
0x140003081  cmovnz  rax, rcx
0x140003085  mov     rcx, rbp; pszDest
0x140003088  mov     byte ptr [rax], 0
0x14000308b  call    StringCchCatA
0x140003090  lea     rdx, pszSrc; "Explicit"
0x140003097  mov     rcx, rbx; String1
0x14000309a  call    cs:__imp__stricmp
0x1400030a0  test    eax, eax
0x1400030a2  jnz     short loc_1400030B1
0x1400030a4  or      [rsi+0Ah], di
0x1400030a8  movzx   eax, word ptr [rsi+8]
0x1400030ac  or      ax, di
0x1400030af  jmp     short loc_1400030D1
0x1400030b1  mov     rdx, rbp; String2
0x1400030b4  mov     rcx, rbx; String1
0x1400030b7  call    cs:__imp__stricmp
0x1400030bd  test    eax, eax
0x1400030bf  jnz     short loc_1400030DC
0x1400030c1  or      [rsi+0Ah], di
0x1400030c5  mov     ecx, 0FFFEh
0x1400030ca  movzx   eax, word ptr [rsi+8]
0x1400030ce  and     ax, cx
0x1400030d1  mov     [rsi+8], ax
0x1400030d5  mov     eax, edi
0x1400030d7  jmp     loc_140002D7E
0x1400030dc  lea     r9, aOption; "Option"
0x1400030e3  jmp     loc_140003004
0x1400030e8  lea     rcx, [rsi+0Ch]
0x1400030ec  mov     [rsp+0C8h+var_A0], r14
0x1400030f1  mov     r8, rbx
0x1400030f4  mov     edx, 200h
0x1400030f9  call    processLineWithQuotes
0x1400030fe  test    eax, eax
0x140003100  jz      loc_140002D7C
0x140003106  sub     edi, 8
0x140003109  jz      short loc_140003123
0x14000310b  sub     edi, 1
0x14000310e  jz      short loc_14000311A
0x140003110  cmp     edi, 1
0x140003113  jnz     short loc_14000312A
0x140003115  mov     [rsi+8], edi
0x140003118  jmp     short loc_14000312A
0x14000311a  mov     dword ptr [rsi+8], 2
0x140003121  jmp     short loc_14000312A
0x140003123  mov     dword ptr [rsi+8], 3
0x14000312a  mov     dword ptr [rsi], 8
0x140003130  jmp     loc_140002E6A
```
