# AslpFileMappingGetFileKind

- ea: `0x180012918`
- end: `0x180012a3e`
- name: `AslpFileMappingGetFileKind`
- size: `294`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dcf4`
- `0x18000ddac`
- `0x180011f2c`

## callees

- `0x18000e240`
- `0x180012918`

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
0x180012918  mov     [rsp+arg_0], rbx
0x18001291d  mov     [rsp+arg_10], rsi
0x180012922  mov     [rsp+arg_8], rdx
0x180012927  push    rdi
0x180012928  sub     rsp, 40h
0x18001292c  mov     rsi, rdx
0x18001292f  mov     rdx, [rcx+10h]
0x180012933  xor     edi, edi
0x180012935  test    rdx, rdx
0x180012938  jz      loc_180012A26
0x18001293e  cmp     [rcx+20h], rdi
0x180012942  jz      loc_180012A26
0x180012948  cmp     rdx, 40h ; '@'
0x18001294c  jnb     short loc_180012959
0x18001294e  mov     dword ptr [rsi], 3
0x180012954  jmp     loc_180012A2C
0x180012959  mov     rcx, [rcx+18h]
0x18001295d  mov     ebx, 3
0x180012962  mov     [rsp+48h+var_18], ebx
0x180012966  test    rcx, rcx
0x180012969  jz      loc_1800129F9
0x18001296f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180012973  jz      loc_1800129F9
0x180012979  mov     eax, 5A4Dh
0x18001297e  cmp     [rcx], ax
0x180012981  jnz     short loc_1800129C0
0x180012983  mov     ebx, 4
0x180012988  mov     [rsp+48h+var_18], ebx
0x18001298c  mov     r8d, [rcx+3Ch]
0x180012990  lea     rax, [r8+4]
0x180012994  cmp     rdx, rax
0x180012997  jb      short loc_1800129C0
0x180012999  cmp     dword ptr [r8+rcx], 4550h
0x1800129a1  jnz     short loc_1800129AA
0x1800129a3  mov     ebx, 6
0x1800129a8  jmp     short loc_1800129BC
0x1800129aa  mov     edx, 5
0x1800129af  mov     eax, 454Eh
0x1800129b4  cmp     [r8+rcx], ax
0x1800129b9  cmovz   ebx, edx
0x1800129bc  mov     [rsp+48h+var_18], ebx
0x1800129c0  mov     [rsp+48h+var_14], edi
0x1800129c4  jmp     short loc_180012A20
0x1800129c6  mov     edi, eax
0x1800129c8  mov     [rsp+48h+var_14], eax
0x1800129cc  mov     [rsp+48h+var_28], eax
0x1800129d0  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x1800129d7  mov     r8d, 591h
0x1800129dd  lea     rdx, aAslpfilemappin_0; "AslpFileMappingGetFileKind"
0x1800129e4  mov     ecx, 1
0x1800129e9  call    AslLogCallPrintf
0x1800129ee  mov     rsi, [rsp+48h+arg_8]
0x1800129f3  mov     ebx, [rsp+48h+var_18]
0x1800129f7  jmp     short loc_180012A20
0x1800129f9  mov     edi, 0C000000Dh
0x1800129fe  mov     [rsp+48h+var_28], edi
0x180012a02  lea     r9, aFileMappingInv; "File mapping invalid [%x]"
0x180012a09  mov     r8d, 53Fh
0x180012a0f  lea     rdx, aAslpfilemappin_0; "AslpFileMappingGetFileKind"
0x180012a16  mov     ecx, 1
0x180012a1b  call    AslLogCallPrintf
0x180012a20  mov     [rsi], ebx
0x180012a22  mov     eax, edi
0x180012a24  jmp     short loc_180012A2E
0x180012a26  mov     dword ptr [rsi], 1
0x180012a2c  xor     eax, eax
0x180012a2e  mov     rbx, [rsp+48h+arg_0]
0x180012a33  mov     rsi, [rsp+48h+arg_10]
0x180012a38  add     rsp, 40h
0x180012a3c  pop     rdi
0x180012a3d  retn
0x1800197be  push    rbp
0x1800197c0  sub     rsp, 30h
0x1800197c4  mov     rbp, rdx
0x1800197c7  mov     rax, [rcx]
0x1800197ca  xor     ecx, ecx
0x1800197cc  cmp     dword ptr [rax], 0C00000FDh
0x1800197d2  setnz   cl
0x1800197d5  mov     [rbp+38h], ecx
0x1800197d8  mov     eax, [rbp+38h]
0x1800197db  add     rsp, 30h
0x1800197df  pop     rbp
0x1800197e0  retn
```
