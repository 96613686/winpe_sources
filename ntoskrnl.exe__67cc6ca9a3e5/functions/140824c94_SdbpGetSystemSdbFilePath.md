# SdbpGetSystemSdbFilePath

- ea: `0x140824c94`
- end: `0x140824db1`
- name: `SdbpGetSystemSdbFilePath`
- size: `285`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140824284`
- `0x140824354`

## callees

- `0x1406e8590`
- `0x140824c94`
- `0x14097d158`

## string_xrefs

- `0x140824d45`: `GetPathFunction (for SdbFileType %d, IsLtRs3: %d) failed [%x]`
- `0x140824cf5`: `SdbFileDetails missing function pointer for path.`
- `0x140824d02`: `SdbpGetSystemSdbFilePath`
- `0x140824d54`: `SdbpGetSystemSdbFilePath`
- `0x140824d86`: `SdbpGetSystemSdbFilePath`

## pseudocode

```c
__int64 __fastcall SdbpGetSystemSdbFilePath(_WORD *a1, __int64 a2, int a3)
{
  unsigned __int64 i; // rdx
  __int64 *v5; // rcx
  int v6; // ebx

  *a1 = 0;
  if ( a3 && a3 < 13 )
  {
    for ( i = 1; ; ++i )
    {
      if ( i >= 0xD )
        goto LABEL_13;
      v5 = &qword_14000B070[4 * i];
      if ( *(_DWORD *)v5 == a3 )
        break;
    }
    if ( !v5 )
    {
LABEL_13:
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpGetSystemSdbFilePath",
        1373,
        (unsigned int)"SdbFileDetails missing array item for SdbFileType: %d");
      return (unsigned int)-1073741275;
    }
    if ( v5[2] )
    {
      v6 = guard_dispatch_icall_no_overrides(a1);
      if ( v6 >= 0 )
        return 0;
      else
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpGetSystemSdbFilePath",
          1397,
          (unsigned int)"GetPathFunction (for SdbFileType %d, IsLtRs3: %d) failed [%x]");
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
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140824c94  mov     [rsp+arg_0], rbx
0x140824c99  push    rdi
0x140824c9a  sub     rsp, 40h
0x140824c9e  xor     eax, eax
0x140824ca0  mov     edi, r8d
0x140824ca3  mov     [rcx], ax
0x140824ca6  mov     r10, rcx
0x140824ca9  test    r8d, r8d
0x140824cac  jz      loc_140824D9E
0x140824cb2  cmp     r8d, 0Dh
0x140824cb6  jge     loc_140824D9E
0x140824cbc  lea     edx, [rax+1]
0x140824cbf  cmp     rdx, 0Dh
0x140824cc3  jnb     loc_140824D75
0x140824cc9  mov     rax, rdx
0x140824ccc  lea     rcx, qword_14000B070
0x140824cd3  shl     rax, 5
0x140824cd7  add     rcx, rax
0x140824cda  cmp     [rcx], edi
0x140824cdc  jz      short loc_140824CE3
0x140824cde  inc     rdx
0x140824ce1  jmp     short loc_140824CBF
0x140824ce3  test    rcx, rcx
0x140824ce6  jz      loc_140824D75
0x140824cec  mov     rax, [rcx+10h]
0x140824cf0  test    rax, rax
0x140824cf3  jnz     short loc_140824D1B
0x140824cf5  lea     r9, aSdbfiledetails_0; "SdbFileDetails missing function pointer"...
0x140824cfc  mov     r8d, 56Bh
0x140824d02  lea     rdx, aSdbpgetsystems_0; "SdbpGetSystemSdbFilePath"
0x140824d09  lea     ecx, [rax+1]
0x140824d0c  call    AslLogCallPrintf
0x140824d11  mov     ebx, 0C00000E5h
0x140824d16  jmp     loc_140824DA3
0x140824d1b  mov     r8, [rsp+48h+arg_20]
0x140824d20  test    r8, r8
0x140824d23  jnz     short loc_140824D29
0x140824d25  mov     r8, [rcx+8]
0x140824d29  mov     r9, [rsp+48h+arg_28]
0x140824d2e  mov     edx, 104h
0x140824d33  mov     rcx, r10
0x140824d36  call    _guard_dispatch_icall_no_overrides
0x140824d3b  mov     ebx, eax
0x140824d3d  test    eax, eax
0x140824d3f  jns     short loc_140824D71
0x140824d41  mov     [rsp+48h+var_18], eax
0x140824d45  lea     r9, aGetpathfunctio; "GetPathFunction (for SdbFileType %d, Is"...
0x140824d4c  mov     [rsp+48h+var_20], 0
0x140824d54  lea     rdx, aSdbpgetsystems_0; "SdbpGetSystemSdbFilePath"
0x140824d5b  mov     r8d, 575h
0x140824d61  mov     [rsp+48h+var_28], edi
0x140824d65  mov     ecx, 1
0x140824d6a  call    AslLogCallPrintf
0x140824d6f  jmp     short loc_140824DA3
0x140824d71  xor     ebx, ebx
0x140824d73  jmp     short loc_140824DA3
0x140824d75  lea     r9, aSdbfiledetails; "SdbFileDetails missing array item for S"...
0x140824d7c  mov     [rsp+48h+var_28], edi
0x140824d80  mov     r8d, 55Dh
0x140824d86  lea     rdx, aSdbpgetsystems_0; "SdbpGetSystemSdbFilePath"
0x140824d8d  mov     ecx, 1
0x140824d92  call    AslLogCallPrintf
0x140824d97  mov     ebx, 0C0000225h
0x140824d9c  jmp     short loc_140824DA3
0x140824d9e  mov     ebx, 0C00000F1h
0x140824da3  mov     eax, ebx
0x140824da5  mov     rbx, [rsp+48h+arg_0]
0x140824daa  add     rsp, 40h
0x140824dae  pop     rdi
0x140824daf  retn
```
