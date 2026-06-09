# LmGetFullPath

- ea: `0x14004e090`
- end: `0x14004e377`
- name: `LmGetFullPath`
- size: `743`
- prototype: `__int64 __fastcall(char *, const char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400447ac`
- `0x14004de44`

## callees

- `0x1400149d4`
- `0x14002bb04`
- `0x14004e090`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e19e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e19e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e192`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e192`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004e2fa`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004e2fa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004e2e5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004e2e5`
- `ntoskrnl!ExAllocatePool2` at `0x14004e0cd`
- `ntoskrnl!ExAllocatePool2` at `0x14004e170`
- `ntoskrnl!ExAllocatePool2` at `0x14004e2ab`
- `ntoskrnl!ExAllocatePool2` at `0x14004e32f`
- `ntoskrnl!ExAllocatePool2` at `0x14004e0cd`
- `ntoskrnl!ExAllocatePool2` at `0x14004e170`
- `ntoskrnl!ExAllocatePool2` at `0x14004e2ab`
- `ntoskrnl!ExAllocatePool2` at `0x14004e32f`

## pseudocode

```c
__int64 __fastcall LmGetFullPath(char *a1, const char **a2)
{
  char *v2; // rbx
  char v4; // cl
  __int64 v5; // rdi
  unsigned int v6; // edi
  char *Pool2; // rax
  const char *v8; // r14
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // rdi
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rdi
  const char *v15; // rax
  __int64 result; // rax
  __int64 v17; // rax
  char *v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rdi
  char *v23; // rax
  __int64 v24; // rdi
  unsigned int v25; // edi
  char *v26; // rax

  v2 = a1;
  v4 = a1[1];
  if ( v4 == 58 )
  {
    v5 = -1;
    do
      ++v5;
    while ( v2[v5] );
    v6 = v5 + 13;
    Pool2 = (char *)ExAllocatePool2(64, v6, 825320014);
    v8 = Pool2;
    if ( Pool2 )
    {
      StringCbCopyA(Pool2, v6, "\\DosDevices\\");
LABEL_6:
      Nbtstrcat(v8);
LABEL_18:
      *a2 = v8;
      return 0;
    }
    return 3221225473LL;
  }
  v9 = *(_QWORD *)(v2 + 1) - 0x6F526D6574737953LL;
  if ( *(_QWORD *)(v2 + 1) == 0x6F526D6574737953LL )
    v9 = *(unsigned __int16 *)(v2 + 9) - 29807LL;
  if ( !v9 )
    goto LABEL_10;
  v19 = *(_QWORD *)v2 - 0x69766544736F445CLL;
  if ( *(_QWORD *)v2 == 0x69766544736F445CLL )
    v19 = *((unsigned int *)v2 + 2) - 1551066467LL;
  if ( v19 )
  {
    v20 = *(_QWORD *)v2 - 0x69766544736F445CLL;
    if ( *(_QWORD *)v2 == 0x69766544736F445CLL )
      v20 = *((_QWORD *)v2 + 1) - 0x5C434E555C736563LL;
    v10 = 3;
    if ( v20 )
      v10 = 1;
  }
  else
  {
LABEL_10:
    v10 = 3;
  }
  if ( v4 == 92 && *v2 == 92 )
  {
LABEL_40:
    v22 = -1;
    do
      ++v22;
    while ( v2[v22] );
    v23 = (char *)ExAllocatePool2(64, (unsigned int)v22 + 16LL, 858874446);
    v8 = v23;
    if ( v23 )
    {
      StringCbCopyA(v23, (unsigned int)(v22 + 16), "\\DosDevices\\UNC");
      goto LABEL_6;
    }
    return 3221225473LL;
  }
  if ( v10 != 3 )
  {
    v21 = v10 - 1;
    if ( !v21 )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(&Resource, 1u);
      v24 = -1;
      do
        ++v24;
      while ( v2[v24] );
      v25 = dword_140039658 + 1 + v24;
      v26 = (char *)ExAllocatePool2(64, v25, 842097230);
      v8 = v26;
      if ( v26 )
      {
        StringCbCopyA(v26, v25, (STRSAFE_LPCSTR)Src);
        v8[dword_140039658] = 0;
        Nbtstrcat(v8);
      }
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
      if ( v8 )
        goto LABEL_18;
      return 3221225473LL;
    }
    if ( v21 != 1 )
      return 3221225473LL;
    goto LABEL_40;
  }
  v11 = -1;
  while ( v2[++v11] != 0 )
    ;
  v13 = (unsigned int)(v11 + 1);
  v14 = v13;
  v15 = (const char *)ExAllocatePool2(64, v13, 875651662);
  v8 = v15;
  if ( !v15 )
    return 3221225473LL;
  if ( !v14 )
    goto LABEL_18;
  if ( v14 <= 0x7FFFFFFF )
  {
    v17 = 2147483646;
    v18 = (char *)v8;
    do
    {
      if ( !v17 )
        break;
      if ( !*v2 )
        break;
      *v18++ = *v2++;
      --v17;
      --v14;
    }
    while ( v14 );
    v15 = v18 - 1;
    if ( v14 )
      v15 = v18;
  }
  *v15 = 0;
  result = 0;
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x14004e090  push    rbx
0x14004e092  push    rsi
0x14004e093  push    rdi
0x14004e094  push    r14
0x14004e096  push    r15
0x14004e098  sub     rsp, 20h
0x14004e09c  mov     rbx, rcx
0x14004e09f  mov     r15, rdx
0x14004e0a2  movzx   ecx, byte ptr [rcx+1]
0x14004e0a6  cmp     cl, 3Ah ; ':'
0x14004e0a9  jnz     short loc_14004E109
0x14004e0ab  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x14004e0b2  inc     rdi
0x14004e0b5  cmp     byte ptr [rbx+rdi], 0
0x14004e0b9  jnz     short loc_14004E0B2
0x14004e0bb  add     edi, 0Dh
0x14004e0be  mov     r8d, 3131624Eh
0x14004e0c4  mov     edx, edi
0x14004e0c6  mov     ecx, 40h ; '@'
0x14004e0cb  mov     esi, edi
0x14004e0cd  call    cs:__imp_ExAllocatePool2
0x14004e0d4  nop     dword ptr [rax+rax+00h]
0x14004e0d9  mov     r14, rax
0x14004e0dc  test    rax, rax
0x14004e0df  jz      loc_14004E184
0x14004e0e5  lea     r8, pszSrc; "\\DosDevices\\"
0x14004e0ec  mov     edx, esi; cbDest
0x14004e0ee  mov     rcx, rax; pszDest
0x14004e0f1  call    StringCbCopyA
0x14004e0f6  mov     r8d, edi
0x14004e0f9  mov     rdx, rbx
0x14004e0fc  mov     rcx, r14; SourceString
0x14004e0ff  call    Nbtstrcat
0x14004e104  jmp     loc_14004E1AF
0x14004e109  mov     r8, [rbx+1]
0x14004e10d  mov     rax, 6F526D6574737953h
0x14004e117  sub     r8, rax
0x14004e11a  jnz     short loc_14004E12C
0x14004e11c  movzx   r8d, word ptr [rbx+9]
0x14004e121  mov     eax, 746Fh
0x14004e126  movzx   eax, ax
0x14004e129  sub     r8, rax
0x14004e12c  test    r8, r8
0x14004e12f  jnz     loc_14004E214
0x14004e135  mov     eax, 3
0x14004e13a  cmp     cl, 5Ch ; '\'
0x14004e13d  jz      loc_14004E26A
0x14004e143  cmp     eax, 3
0x14004e146  jnz     loc_14004E274
0x14004e14c  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x14004e153  cmp     byte ptr [rbx+rdi+1], 0
0x14004e158  lea     rdi, [rdi+1]
0x14004e15c  jnz     short loc_14004E153
0x14004e15e  lea     eax, [rdi+1]
0x14004e161  mov     r8d, 3431624Eh
0x14004e167  mov     edx, eax
0x14004e169  mov     ecx, 40h ; '@'
0x14004e16e  mov     edi, eax
0x14004e170  call    cs:__imp_ExAllocatePool2
0x14004e177  nop     dword ptr [rax+rax+00h]
0x14004e17c  mov     r14, rax
0x14004e17f  test    rax, rax
0x14004e182  jnz     short loc_14004E1C1
0x14004e184  mov     eax, 0C0000001h
0x14004e189  jmp     short loc_14004E1B4
0x14004e18b  lea     rcx, Resource; Resource
0x14004e192  call    cs:__imp_ExReleaseResourceLite
0x14004e199  nop     dword ptr [rax+rax+00h]
0x14004e19e  call    cs:__imp_KeLeaveCriticalRegion
0x14004e1a5  nop     dword ptr [rax+rax+00h]
0x14004e1aa  test    r14, r14
0x14004e1ad  jz      short loc_14004E184
0x14004e1af  mov     [r15], r14
0x14004e1b2  xor     eax, eax
0x14004e1b4  add     rsp, 20h
0x14004e1b8  pop     r15
0x14004e1ba  pop     r14
0x14004e1bc  pop     rdi
0x14004e1bd  pop     rsi
0x14004e1be  pop     rbx
0x14004e1bf  retn
0x14004e1c1  test    rdi, rdi
0x14004e1c4  jz      short loc_14004E1AF
0x14004e1c6  cmp     rdi, 7FFFFFFFh
0x14004e1cd  ja      short loc_14004E1FF
0x14004e1cf  mov     eax, 7FFFFFFEh
0x14004e1d4  mov     rdx, r14
0x14004e1d7  test    rax, rax
0x14004e1da  jz      short loc_14004E1F4
0x14004e1dc  movzx   ecx, byte ptr [rbx]
0x14004e1df  test    cl, cl
0x14004e1e1  jz      short loc_14004E1F4
0x14004e1e3  mov     [rdx], cl
0x14004e1e5  inc     rbx
0x14004e1e8  inc     rdx
0x14004e1eb  dec     rax
0x14004e1ee  sub     rdi, 1
0x14004e1f2  jnz     short loc_14004E1D7
0x14004e1f4  test    rdi, rdi
0x14004e1f7  lea     rax, [rdx-1]
0x14004e1fb  cmovnz  rax, rdx
0x14004e1ff  mov     byte ptr [rax], 0
0x14004e202  xor     eax, eax
0x14004e204  mov     [r15], r14
0x14004e207  add     rsp, 20h
0x14004e20b  pop     r15
0x14004e20d  pop     r14
0x14004e20f  pop     rdi
0x14004e210  pop     rsi
0x14004e211  pop     rbx
0x14004e212  retn
0x14004e214  mov     rdx, [rbx]
0x14004e217  mov     r8, 69766544736F445Ch
0x14004e221  sub     rdx, r8
0x14004e224  jnz     short loc_14004E231
0x14004e226  mov     edx, [rbx+8]
0x14004e229  mov     eax, 5C736563h
0x14004e22e  sub     rdx, rax
0x14004e231  test    rdx, rdx
0x14004e234  jz      loc_14004E135
0x14004e23a  mov     rdx, [rbx]
0x14004e23d  sub     rdx, r8
0x14004e240  jnz     short loc_14004E253
0x14004e242  mov     rdx, [rbx+8]
0x14004e246  mov     rax, 5C434E555C736563h
0x14004e250  sub     rdx, rax
0x14004e253  test    rdx, rdx
0x14004e256  mov     eax, 3
0x14004e25b  mov     r8d, 1
0x14004e261  cmovnz  eax, r8d
0x14004e265  jmp     loc_14004E13A
0x14004e26a  cmp     byte ptr [rbx], 5Ch ; '\'
0x14004e26d  jz      short loc_14004E28A
0x14004e26f  jmp     loc_14004E143
0x14004e274  test    eax, eax
0x14004e276  jz      loc_14004E0AB
0x14004e27c  sub     eax, 1
0x14004e27f  jz      short loc_14004E2E5
0x14004e281  cmp     eax, 1
0x14004e284  jnz     loc_14004E184
0x14004e28a  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x14004e291  inc     rdi
0x14004e294  cmp     byte ptr [rbx+rdi], 0
0x14004e298  jnz     short loc_14004E291
0x14004e29a  mov     edx, edi
0x14004e29c  mov     ecx, 40h ; '@'
0x14004e2a1  add     rdx, 10h
0x14004e2a5  mov     r8d, 3331624Eh
0x14004e2ab  call    cs:__imp_ExAllocatePool2
0x14004e2b2  nop     dword ptr [rax+rax+00h]
0x14004e2b7  mov     r14, rax
0x14004e2ba  test    rax, rax
0x14004e2bd  jz      loc_14004E184
0x14004e2c3  lea     r10d, [rdi+10h]
0x14004e2c7  mov     rcx, rax; pszDest
0x14004e2ca  mov     edx, r10d; cbDest
0x14004e2cd  lea     r8, aDosdevicesUnc; "\\DosDevices\\UNC"
0x14004e2d4  call    StringCbCopyA
0x14004e2d9  mov     r8d, r10d
0x14004e2dc  lea     rdx, [rbx+1]
0x14004e2e0  jmp     loc_14004E0FC
0x14004e2e5  call    cs:__imp_KeEnterCriticalRegion
0x14004e2ec  nop     dword ptr [rax+rax+00h]
0x14004e2f1  mov     dl, 1; Wait
0x14004e2f3  lea     rcx, Resource; Resource
0x14004e2fa  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004e301  nop     dword ptr [rax+rax+00h]
0x14004e306  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x14004e30d  inc     rdi
0x14004e310  cmp     byte ptr [rbx+rdi], 0
0x14004e314  jnz     short loc_14004E30D
0x14004e316  mov     eax, cs:dword_140039658
0x14004e31c  mov     r8d, 3231624Eh
0x14004e322  inc     eax
0x14004e324  mov     ecx, 40h ; '@'
0x14004e329  add     edi, eax
0x14004e32b  mov     edx, edi
0x14004e32d  mov     esi, edi
0x14004e32f  call    cs:__imp_ExAllocatePool2
0x14004e336  nop     dword ptr [rax+rax+00h]
0x14004e33b  mov     r14, rax
0x14004e33e  test    rax, rax
0x14004e341  jz      loc_14004E18B
0x14004e347  mov     r8, cs:Src; pszSrc
0x14004e34e  mov     edx, esi; cbDest
0x14004e350  mov     rcx, rax; pszDest
0x14004e353  call    StringCbCopyA
0x14004e358  mov     r10d, cs:dword_140039658
0x14004e35f  mov     r8d, edi
0x14004e362  mov     rdx, rbx
0x14004e365  mov     rcx, r14; SourceString
0x14004e368  mov     byte ptr [r10+r14], 0
0x14004e36d  call    Nbtstrcat
0x14004e372  jmp     loc_14004E18B
```
