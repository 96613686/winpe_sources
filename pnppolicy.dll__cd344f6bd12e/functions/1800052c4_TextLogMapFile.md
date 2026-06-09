# TextLogMapFile

- ea: `0x1800052c4`
- end: `0x18000542a`
- name: `TextLogMapFile`
- size: `358`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800063bc`
- `0x180006590`

## callees

- `0x180004e0c`
- `0x180005018`
- `0x1800052c4`
- `0x180005970`
- `0x1800059f4`
- `0x180005fc4`
- `0x180007ed4`
- `0x180007f70`

## import_xrefs

- `KERNEL32!GetFileSize` at `0x180005353`
- `KERNEL32!GetFileSize` at `0x180005353`

## pseudocode

```c
__int64 __fastcall TextLogMapFile(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  _QWORD *v4; // r14
  int v8; // r13d
  unsigned int v9; // ebp
  unsigned int v10; // esi
  DWORD FileSize; // eax
  int LogStatus; // eax
  __int64 v13; // rax
  unsigned int v14; // edi
  unsigned int i; // edx
  unsigned int v16; // ecx
  _BYTE v18[104]; // [rsp+30h] [rbp-68h] BYREF
  unsigned int v19; // [rsp+B8h] [rbp+20h] BYREF

  *(_QWORD *)a2 = -1;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 48) = 0;
  *(_DWORD *)(a2 + 44) = a4 & 1;
  v4 = (_QWORD *)(a2 + 16);
  *(_QWORD *)(a2 + 16) = 0;
  v19 = 0;
  v8 = a3;
  v9 = pSetupOpenFileForWrite(
         *(const WCHAR **)(a1 + 16),
         (a4 & 6) != 0 ? 0x10000 : 0,
         a3,
         30000,
         (HANDLE *)a2,
         (LONG *)&v19);
  if ( v9 )
    goto LABEL_15;
  v10 = v19;
  if ( v19 )
  {
    if ( (a4 & 2) != 0
      && v19 >= *(_DWORD *)(a1 + 8)
      && *(_DWORD *)(a1 + 24) < 4u
      && (*(_DWORD *)(a1 + 12) & 0x2000) == 0 )
    {
      *(_DWORD *)(a2 + 48) = 1;
    }
  }
  else
  {
    WriteTextLogFileHeader(*(HANDLE *)a2);
    FileSize = GetFileSize(*(HANDLE *)a2, 0);
    *(_DWORD *)(a1 + 12) &= ~0x1000u;
    v10 = FileSize;
    LogStatus = TextLogGetLogStatus(a1);
    if ( (LogStatus & 0x1000) != 0 )
      TextLogSetLogStatus(a1, LogStatus & 0xFFFFEFFF);
  }
  v9 = pSetupMapFileForWrite(*(void **)a2, v10 + v8, (HANDLE *)(a2 + 8), v4);
  if ( v9 )
  {
LABEL_15:
    TextLogUnmapFile(a2);
    v16 = TextLogMapErrors++;
    if ( v16 > 5 )
      *(_DWORD *)a1 = 0;
  }
  else
  {
    v13 = *v4 + v10;
    *(_QWORD *)(a2 + 32) = a1;
    v14 = 0;
    *(_QWORD *)(a2 + 24) = v13;
    for ( i = 0; (unsigned int)TextLogEnumerateOpenSections(a2, i, (__int64)v18); i = v14 )
      ++v14;
    *(_DWORD *)(a2 + 40) = *(_DWORD *)(a2 + 24) - 20 * v14 - *(_DWORD *)v4;
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x1800052c4  mov     r11, rsp
0x1800052c7  push    rbx
0x1800052c8  push    rbp
0x1800052c9  push    rsi
0x1800052ca  push    rdi
0x1800052cb  push    r12
0x1800052cd  push    r13
0x1800052cf  push    r14
0x1800052d1  push    r15
0x1800052d3  sub     rsp, 58h
0x1800052d7  xor     esi, esi
0x1800052d9  mov     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x1800052e0  mov     eax, r9d
0x1800052e3  mov     [rdx+8], rsi
0x1800052e7  and     eax, 1
0x1800052ea  mov     [rdx+30h], esi
0x1800052ed  mov     [rdx+2Ch], eax
0x1800052f0  lea     r14, [rdx+10h]
0x1800052f4  mov     eax, r9d
0x1800052f7  mov     [r14], rsi
0x1800052fa  mov     rbx, rdx
0x1800052fd  mov     [r11+20h], esi
0x180005301  and     al, 6
0x180005303  mov     r15d, r9d
0x180005306  neg     al
0x180005308  mov     rdi, rcx
0x18000530b  mov     rcx, [rcx+10h]
0x18000530f  lea     rax, [r11+20h]
0x180005313  sbb     edx, edx
0x180005315  mov     [r11-70h], rax
0x180005319  and     edx, 10000h
0x18000531f  mov     [r11-78h], rbx
0x180005323  mov     r9d, 7530h
0x180005329  mov     r13d, r8d
0x18000532c  call    pSetupOpenFileForWrite
0x180005331  mov     ebp, eax
0x180005333  test    eax, eax
0x180005335  jnz     loc_1800053F8
0x18000533b  mov     esi, [rsp+98h+arg_18]
0x180005342  test    esi, esi
0x180005344  jnz     short loc_18000537F
0x180005346  mov     rcx, [rbx]; hFile
0x180005349  call    WriteTextLogFileHeader
0x18000534e  mov     rcx, [rbx]; hFile
0x180005351  xor     edx, edx; lpFileSizeHigh
0x180005353  call    cs:__imp_GetFileSize
0x180005359  mov     ebp, 0FFFFEFFFh
0x18000535e  mov     rcx, rdi
0x180005361  and     [rdi+0Ch], ebp
0x180005364  mov     esi, eax
0x180005366  call    TextLogGetLogStatus
0x18000536b  bt      eax, 0Ch
0x18000536f  jnb     short loc_1800053A0
0x180005371  and     eax, ebp
0x180005373  mov     rcx, rdi
0x180005376  mov     edx, eax
0x180005378  call    TextLogSetLogStatus
0x18000537d  jmp     short loc_1800053A0
0x18000537f  test    r15b, 2
0x180005383  jz      short loc_1800053A0
0x180005385  cmp     esi, [rdi+8]
0x180005388  jb      short loc_1800053A0
0x18000538a  cmp     dword ptr [rdi+18h], 4
0x18000538e  jnb     short loc_1800053A0
0x180005390  test    dword ptr [rdi+0Ch], 2000h
0x180005397  jnz     short loc_1800053A0
0x180005399  mov     dword ptr [rbx+30h], 1
0x1800053a0  mov     rcx, [rbx]
0x1800053a3  lea     edx, [rsi+r13]
0x1800053a7  mov     r9, r14
0x1800053aa  lea     r8, [rbx+8]
0x1800053ae  call    pSetupMapFileForWrite
0x1800053b3  mov     ebp, eax
0x1800053b5  test    eax, eax
0x1800053b7  jnz     short loc_1800053F6
0x1800053b9  mov     eax, esi
0x1800053bb  add     rax, [r14]
0x1800053be  mov     [rbx+20h], rdi
0x1800053c2  xor     edi, edi
0x1800053c4  mov     [rbx+18h], rax
0x1800053c8  xor     edx, edx
0x1800053ca  jmp     short loc_1800053D0
0x1800053cc  inc     edi
0x1800053ce  mov     edx, edi
0x1800053d0  lea     r8, [rsp+98h+var_68]
0x1800053d5  mov     rcx, rbx
0x1800053d8  call    TextLogEnumerateOpenSections
0x1800053dd  test    eax, eax
0x1800053df  jnz     short loc_1800053CC
0x1800053e1  mov     ecx, [rbx+18h]
0x1800053e4  lea     eax, [rdi+rdi*4]
0x1800053e7  shl     eax, 2
0x1800053ea  sub     ecx, eax
0x1800053ec  sub     ecx, [r14]
0x1800053ef  mov     [rbx+28h], ecx
0x1800053f2  xor     ebp, ebp
0x1800053f4  jmp     short loc_180005417
0x1800053f6  xor     esi, esi
0x1800053f8  mov     rcx, rbx
0x1800053fb  call    TextLogUnmapFile
0x180005400  mov     eax, cs:TextLogMapErrors
0x180005406  mov     ecx, eax
0x180005408  inc     eax
0x18000540a  mov     cs:TextLogMapErrors, eax
0x180005410  cmp     ecx, 5
0x180005413  jbe     short loc_180005417
0x180005415  mov     [rdi], esi
0x180005417  mov     eax, ebp
0x180005419  add     rsp, 58h
0x18000541d  pop     r15
0x18000541f  pop     r14
0x180005421  pop     r13
0x180005423  pop     r12
0x180005425  pop     rdi
0x180005426  pop     rsi
0x180005427  pop     rbp
0x180005428  pop     rbx
0x180005429  retn
```
