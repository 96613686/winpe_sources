# SdbpGetSystemSdbFilePath

- ea: `0x140826c04`
- end: `0x140826d21`
- name: `SdbpGetSystemSdbFilePath`
- size: `285`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1408261f4`
- `0x1408262c4`

## callees

- `0x1406eb0e0`
- `0x140826c04`
- `0x1408c2f88`

## string_xrefs

- `0x140826cb5`: `GetPathFunction (for SdbFileType %d, IsLtRs3: %d) failed [%x]`
- `0x140826c72`: `SdbpGetSystemSdbFilePath`
- `0x140826cc4`: `SdbpGetSystemSdbFilePath`
- `0x140826cf6`: `SdbpGetSystemSdbFilePath`
- `0x140826c65`: `SdbFileDetails missing function pointer for path.`

## pseudocode

```c
__int64 __fastcall SdbpGetSystemSdbFilePath(_WORD *a1, __int64 a2, int a3, __int64 a4, __int64 a5)
{
  unsigned __int64 i; // rdx
  __int64 *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // r8
  int v11; // eax

  *a1 = 0;
  if ( a3 && a3 < 13 )
  {
    for ( i = 1; ; ++i )
    {
      if ( i >= 0xD )
        goto LABEL_15;
      v8 = &qword_14000B060[4 * i];
      if ( *(_DWORD *)v8 == a3 )
        break;
    }
    if ( !v8 )
    {
LABEL_15:
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpGetSystemSdbFilePath",
        1373,
        (unsigned int)"SdbFileDetails missing array item for SdbFileType: %d",
        a3);
      return (unsigned int)-1073741275;
    }
    if ( v8[2] )
    {
      v10 = a5;
      if ( !a5 )
        v10 = v8[1];
      v11 = guard_dispatch_icall_no_overrides(a1, 260, v10);
      v9 = v11;
      if ( v11 >= 0 )
        return 0;
      else
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpGetSystemSdbFilePath",
          1397,
          (unsigned int)"GetPathFunction (for SdbFileType %d, IsLtRs3: %d) failed [%x]",
          a3,
          0,
          v11);
    }
    else
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpGetSystemSdbFilePath",
        1387,
        (unsigned int)"SdbFileDetails missing function pointer for path.");
      return (unsigned int)-1073741595;
    }
  }
  else
  {
    return (unsigned int)-1073741583;
  }
  return v9;
}

```

## disassembly

```asm
0x140826c04  mov     [rsp+arg_0], rbx
0x140826c09  push    rdi
0x140826c0a  sub     rsp, 40h
0x140826c0e  xor     eax, eax
0x140826c10  mov     edi, r8d
0x140826c13  mov     [rcx], ax
0x140826c16  mov     r10, rcx
0x140826c19  test    r8d, r8d
0x140826c1c  jz      loc_140826D0E
0x140826c22  cmp     r8d, 0Dh
0x140826c26  jge     loc_140826D0E
0x140826c2c  lea     edx, [rax+1]
0x140826c2f  cmp     rdx, 0Dh
0x140826c33  jnb     loc_140826CE5
0x140826c39  mov     rax, rdx
0x140826c3c  lea     rcx, qword_14000B060
0x140826c43  shl     rax, 5
0x140826c47  add     rcx, rax
0x140826c4a  cmp     [rcx], edi
0x140826c4c  jz      short loc_140826C53
0x140826c4e  inc     rdx
0x140826c51  jmp     short loc_140826C2F
0x140826c53  test    rcx, rcx
0x140826c56  jz      loc_140826CE5
0x140826c5c  mov     rax, [rcx+10h]
0x140826c60  test    rax, rax
0x140826c63  jnz     short loc_140826C8B
0x140826c65  lea     r9, aSdbfiledetails_0; "SdbFileDetails missing function pointer"...
0x140826c6c  mov     r8d, 56Bh
0x140826c72  lea     rdx, aSdbpgetsystems_0; "SdbpGetSystemSdbFilePath"
0x140826c79  lea     ecx, [rax+1]
0x140826c7c  call    AslLogCallPrintf
0x140826c81  mov     ebx, 0C00000E5h
0x140826c86  jmp     loc_140826D13
0x140826c8b  mov     r8, [rsp+48h+arg_20]
0x140826c90  test    r8, r8
0x140826c93  jnz     short loc_140826C99
0x140826c95  mov     r8, [rcx+8]
0x140826c99  mov     r9, [rsp+48h+arg_28]
0x140826c9e  mov     edx, 104h
0x140826ca3  mov     rcx, r10
0x140826ca6  call    _guard_dispatch_icall_no_overrides
0x140826cab  mov     ebx, eax
0x140826cad  test    eax, eax
0x140826caf  jns     short loc_140826CE1
0x140826cb1  mov     [rsp+48h+var_18], eax
0x140826cb5  lea     r9, aGetpathfunctio; "GetPathFunction (for SdbFileType %d, Is"...
0x140826cbc  mov     [rsp+48h+var_20], 0
0x140826cc4  lea     rdx, aSdbpgetsystems_0; "SdbpGetSystemSdbFilePath"
0x140826ccb  mov     r8d, 575h
0x140826cd1  mov     [rsp+48h+var_28], edi
0x140826cd5  mov     ecx, 1
0x140826cda  call    AslLogCallPrintf
0x140826cdf  jmp     short loc_140826D13
0x140826ce1  xor     ebx, ebx
0x140826ce3  jmp     short loc_140826D13
0x140826ce5  lea     r9, aSdbfiledetails; "SdbFileDetails missing array item for S"...
0x140826cec  mov     [rsp+48h+var_28], edi
0x140826cf0  mov     r8d, 55Dh
0x140826cf6  lea     rdx, aSdbpgetsystems_0; "SdbpGetSystemSdbFilePath"
0x140826cfd  mov     ecx, 1
0x140826d02  call    AslLogCallPrintf
0x140826d07  mov     ebx, 0C0000225h
0x140826d0c  jmp     short loc_140826D13
0x140826d0e  mov     ebx, 0C00000F1h
0x140826d13  mov     eax, ebx
0x140826d15  mov     rbx, [rsp+48h+arg_0]
0x140826d1a  add     rsp, 40h
0x140826d1e  pop     rdi
0x140826d1f  retn
```
