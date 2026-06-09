# AslpFileMappingGetFileKind

- ea: `0x14000c334`
- end: `0x14000c45a`
- name: `AslpFileMappingGetFileKind`
- size: `294`
- prototype: `__int64 __fastcall(_QWORD *, int *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000bde8`
- `0x14000bea0`
- `0x140010c90`

## callees

- `0x140007074`
- `0x14000c334`

## pseudocode

```c
__int64 __fastcall AslpFileMappingGetFileKind(_QWORD *a1, int *a2)
{
  unsigned __int64 v3; // rdx
  unsigned int v4; // edi
  __int64 v5; // rcx
  int v6; // ebx
  __int64 v7; // r8

  v3 = a1[2];
  v4 = 0;
  if ( !v3 || !a1[4] )
  {
    *a2 = 1;
    return 0;
  }
  if ( v3 < 0x40 )
  {
    *a2 = 3;
    return 0;
  }
  v5 = a1[3];
  v6 = 3;
  if ( !v5 || v5 == -1 )
  {
    v4 = -1073741811;
    AslLogCallPrintf(1, "AslpFileMappingGetFileKind", 1343, "File mapping invalid [%x]", -1073741811);
  }
  else if ( *(_WORD *)v5 == 23117 )
  {
    v6 = 4;
    v7 = *(unsigned int *)(v5 + 60);
    if ( v3 >= v7 + 4 )
    {
      if ( *(_DWORD *)(v7 + v5) == 17744 )
      {
        v6 = 6;
      }
      else if ( *(_WORD *)(v7 + v5) == 17742 )
      {
        v6 = 5;
      }
    }
  }
  *a2 = v6;
  return v4;
}

```

## disassembly

```asm
0x14000c334  mov     [rsp+arg_0], rbx
0x14000c339  mov     [rsp+arg_10], rsi
0x14000c33e  mov     [rsp+arg_8], rdx
0x14000c343  push    rdi
0x14000c344  sub     rsp, 40h
0x14000c348  mov     rsi, rdx
0x14000c34b  mov     rdx, [rcx+10h]
0x14000c34f  xor     edi, edi
0x14000c351  test    rdx, rdx
0x14000c354  jz      loc_14000C442
0x14000c35a  cmp     [rcx+20h], rdi
0x14000c35e  jz      loc_14000C442
0x14000c364  cmp     rdx, 40h ; '@'
0x14000c368  jnb     short loc_14000C375
0x14000c36a  mov     dword ptr [rsi], 3
0x14000c370  jmp     loc_14000C448
0x14000c375  mov     rcx, [rcx+18h]
0x14000c379  mov     ebx, 3
0x14000c37e  mov     [rsp+48h+var_18], ebx
0x14000c382  test    rcx, rcx
0x14000c385  jz      loc_14000C415
0x14000c38b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000c38f  jz      loc_14000C415
0x14000c395  mov     eax, 5A4Dh
0x14000c39a  cmp     [rcx], ax
0x14000c39d  jnz     short loc_14000C3DC
0x14000c39f  mov     ebx, 4
0x14000c3a4  mov     [rsp+48h+var_18], ebx
0x14000c3a8  mov     r8d, [rcx+3Ch]
0x14000c3ac  lea     rax, [r8+4]
0x14000c3b0  cmp     rdx, rax
0x14000c3b3  jb      short loc_14000C3DC
0x14000c3b5  cmp     dword ptr [r8+rcx], 4550h
0x14000c3bd  jnz     short loc_14000C3C6
0x14000c3bf  mov     ebx, 6
0x14000c3c4  jmp     short loc_14000C3D8
0x14000c3c6  mov     edx, 5
0x14000c3cb  mov     eax, 454Eh
0x14000c3d0  cmp     [r8+rcx], ax
0x14000c3d5  cmovz   ebx, edx
0x14000c3d8  mov     [rsp+48h+var_18], ebx
0x14000c3dc  mov     [rsp+48h+var_14], edi
0x14000c3e0  jmp     short loc_14000C43C
0x14000c3e2  mov     edi, eax
0x14000c3e4  mov     [rsp+48h+var_14], eax
0x14000c3e8  mov     [rsp+48h+var_28], eax
0x14000c3ec  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x14000c3f3  mov     r8d, 591h
0x14000c3f9  lea     rdx, aAslpfilemappin_0; "AslpFileMappingGetFileKind"
0x14000c400  mov     ecx, 1
0x14000c405  call    AslLogCallPrintf
0x14000c40a  mov     rsi, [rsp+48h+arg_8]
0x14000c40f  mov     ebx, [rsp+48h+var_18]
0x14000c413  jmp     short loc_14000C43C
0x14000c415  mov     edi, 0C000000Dh
0x14000c41a  mov     [rsp+48h+var_28], edi
0x14000c41e  lea     r9, aFileMappingInv; "File mapping invalid [%x]"
0x14000c425  mov     r8d, 53Fh
0x14000c42b  lea     rdx, aAslpfilemappin_0; "AslpFileMappingGetFileKind"
0x14000c432  mov     ecx, 1
0x14000c437  call    AslLogCallPrintf
0x14000c43c  mov     [rsi], ebx
0x14000c43e  mov     eax, edi
0x14000c440  jmp     short loc_14000C44A
0x14000c442  mov     dword ptr [rsi], 1
0x14000c448  xor     eax, eax
0x14000c44a  mov     rbx, [rsp+48h+arg_0]
0x14000c44f  mov     rsi, [rsp+48h+arg_10]
0x14000c454  add     rsp, 40h
0x14000c458  pop     rdi
0x14000c459  retn
0x14001188a  push    rbp
0x14001188c  sub     rsp, 30h
0x140011890  mov     rbp, rdx
0x140011893  mov     rax, [rcx]
0x140011896  xor     ecx, ecx
0x140011898  cmp     dword ptr [rax], 0C00000FDh
0x14001189e  setnz   cl
0x1400118a1  mov     [rbp+38h], ecx
0x1400118a4  mov     eax, [rbp+38h]
0x1400118a7  add     rsp, 30h
0x1400118ab  pop     rbp
0x1400118ac  retn
```
