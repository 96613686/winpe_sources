# newDiskIfNecessary

- ea: `0x1400072bc`
- end: `0x1400074fb`
- name: `newDiskIfNecessary`
- size: `575`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140004398`
- `0x14000488c`

## callees

- `0x140006834`
- `0x1400068d8`
- `0x140006a34`
- `0x1400072bc`
- `0x140008244`
- `0x140008f3c`
- `0x14000907c`
- `0x140009454`
- `0x14000c488`
- `0x14000dfd8`

## import_xrefs

- `msvcrt!atol` at `0x140007310`
- `msvcrt!atol` at `0x140007346`
- `msvcrt!atol` at `0x140007310`
- `msvcrt!atol` at `0x140007346`
- `msvcrt!atoi` at `0x140007304`
- `msvcrt!atoi` at `0x14000733a`
- `msvcrt!atoi` at `0x140007304`
- `msvcrt!atoi` at `0x14000733a`

## string_xrefs

- `0x14000742f`: `DiskDirectoryTemplate`
- `0x1400074b3`: `DiskLabelTemplate`
- `0x140007406`: `disk directory name`
- `0x140007421`: `DiskDirectory*`

## pseudocode

```c
_BOOL8 __fastcall newDiskIfNecessary(__int64 a1, int a2, int a3, int a4, __int64 a5)
{
  int v8; // r14d
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rcx
  int v12; // ebp
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rdi
  int v16; // r15d
  int v17; // r14d
  unsigned int MaxDiskSize; // eax
  __int64 v20; // r8
  char *v21; // rcx
  __int64 v23; // r8
  int v24; // [rsp+28h] [rbp-60h]

  v8 = a4;
  v9 = VarFind(*(_QWORD *)(a1 + 16), "ClusterSize", a5);
  if ( v9 )
    v10 = atol(*(const char **)(v9 + 8));
  else
    v10 = atoi("1.44M");
  v11 = *(_QWORD *)(a1 + 16);
  *(_DWORD *)(a1 + 68) = v10;
  v12 = v10;
  v13 = VarFind(v11, "MaxDiskFileCount", a5);
  if ( v13 )
    v14 = atol(*(const char **)(v13 + 8));
  else
    v14 = atoi("1.44M");
  v15 = -1;
  v16 = v14;
  if ( a2 != -1 && !*(_DWORD *)(a1 + 220) )
  {
    v17 = v12 + a2 - 1 - (v12 + a2 - 1) % v12;
    if ( v17 <= *(_DWORD *)(a1 + 48) && ((unsigned int)inCabinet(a1, a5) || *(_DWORD *)(a1 + 60) < v16) )
    {
      *(_DWORD *)(a1 + 48) -= v17;
      if ( !(unsigned int)inCabinet(a1, a5) )
        ++*(_DWORD *)(a1 + 60);
      return 1;
    }
    v8 = a4;
  }
  ++*(_DWORD *)(a1 + 36);
  *(_DWORD *)(a1 + 220) = 0;
  MaxDiskSize = getMaxDiskSize(a1, a5);
  *(_DWORD *)(a1 + 48) = MaxDiskSize;
  if ( MaxDiskSize == -1 || !(unsigned int)setDiskParameters(a1, 0, MaxDiskSize, a5) )
    return 0;
  if ( a3 )
    *(_DWORD *)(a1 + 48) += (v12 + a2 - 1) % v12 - (v12 + a2 - 1);
  v24 = *(_DWORD *)(a1 + 36);
  *(_QWORD *)(a1 + 60) = 1;
  if ( !(unsigned int)getVarWithOverride(
                        a1,
                        a1 + 2868,
                        v20,
                        "DiskDirectory*",
                        "DiskDirectoryTemplate",
                        v24,
                        "disk directory name",
                        a5) )
    return 0;
  v21 = (char *)(a1 + 2868);
  if ( !(v8 ? ensureDirectoryUNC(v21, 0, a5) : (unsigned int)ensureDirectory(v21, 0, a5)) )
    return 0;
  do
    ++v15;
  while ( *(_BYTE *)(v15 + a1 + 2868) );
  if ( v15 )
    appendPathSeparator(v15 + a1 + 2867);
  return (unsigned int)getVarWithOverride(
                         a1,
                         a1 + 2612,
                         v23,
                         "DiskLabel*",
                         "DiskLabelTemplate",
                         *(_DWORD *)(a1 + 36),
                         "disk label name",
                         a5)
      && (unsigned int)infAddDisk(a1, *(unsigned int *)(a1 + 36), a1 + 2612, a5) != 0;
}

```

## disassembly

```asm
0x1400072bc  mov     [rsp+arg_18], r9d
0x1400072c1  push    rbx
0x1400072c2  push    rbp
0x1400072c3  push    rsi
0x1400072c4  push    rdi
0x1400072c5  push    r12
0x1400072c7  push    r13
0x1400072c9  push    r14
0x1400072cb  push    r15
0x1400072cd  sub     rsp, 48h
0x1400072d1  mov     rsi, [rsp+88h+arg_20]
0x1400072d9  mov     r13d, r8d
0x1400072dc  mov     r12d, edx
0x1400072df  mov     rbx, rcx
0x1400072e2  mov     rcx, [rcx+10h]
0x1400072e6  lea     rdx, aClustersize; "ClusterSize"
0x1400072ed  mov     r8, rsi
0x1400072f0  mov     r14d, r9d
0x1400072f3  call    VarFind
0x1400072f8  test    rax, rax
0x1400072fb  jnz     short loc_14000730C
0x1400072fd  lea     rcx, a144m; "1.44M"
0x140007304  call    cs:__imp_atoi
0x14000730a  jmp     short loc_140007316
0x14000730c  mov     rcx, [rax+8]; String
0x140007310  call    cs:__imp_atol
0x140007316  mov     rcx, [rbx+10h]
0x14000731a  lea     rdx, aMaxdiskfilecou; "MaxDiskFileCount"
0x140007321  mov     r8, rsi
0x140007324  mov     [rbx+44h], eax
0x140007327  mov     ebp, eax
0x140007329  call    VarFind
0x14000732e  test    rax, rax
0x140007331  jnz     short loc_140007342
0x140007333  lea     rcx, a144m; "1.44M"
0x14000733a  call    cs:__imp_atoi
0x140007340  jmp     short loc_14000734C
0x140007342  mov     rcx, [rax+8]; String
0x140007346  call    cs:__imp_atol
0x14000734c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140007350  mov     r15d, eax
0x140007353  cmp     r12d, edi
0x140007356  jz      short loc_1400073B5
0x140007358  cmp     dword ptr [rbx+0DCh], 0
0x14000735f  jnz     short loc_1400073B5
0x140007361  lea     r14d, [r12-1]
0x140007366  add     r14d, ebp
0x140007369  mov     eax, r14d
0x14000736c  cdq
0x14000736d  idiv    ebp
0x14000736f  sub     r14d, edx
0x140007372  cmp     r14d, [rbx+30h]
0x140007376  jg      short loc_1400073AD
0x140007378  mov     rdx, rsi
0x14000737b  mov     rcx, rbx
0x14000737e  call    inCabinet
0x140007383  test    eax, eax
0x140007385  jnz     short loc_14000738D
0x140007387  cmp     [rbx+3Ch], r15d
0x14000738b  jge     short loc_1400073AD
0x14000738d  sub     [rbx+30h], r14d
0x140007391  mov     rdx, rsi
0x140007394  mov     rcx, rbx
0x140007397  call    inCabinet
0x14000739c  test    eax, eax
0x14000739e  jnz     short loc_1400073A3
0x1400073a0  inc     dword ptr [rbx+3Ch]
0x1400073a3  mov     eax, 1
0x1400073a8  jmp     loc_1400074EA
0x1400073ad  mov     r14d, [rsp+88h+arg_18]
0x1400073b5  inc     dword ptr [rbx+24h]
0x1400073b8  xor     r15d, r15d
0x1400073bb  mov     rdx, rsi
0x1400073be  mov     [rbx+0DCh], r15d
0x1400073c5  mov     rcx, rbx
0x1400073c8  call    getMaxDiskSize
0x1400073cd  mov     [rbx+30h], eax
0x1400073d0  cmp     eax, edi
0x1400073d2  jz      loc_1400074E8
0x1400073d8  mov     r9, rsi
0x1400073db  mov     r8d, eax
0x1400073de  xor     edx, edx
0x1400073e0  mov     rcx, rbx
0x1400073e3  call    setDiskParameters
0x1400073e8  test    eax, eax
0x1400073ea  jz      loc_1400074E8
0x1400073f0  test    r13d, r13d
0x1400073f3  jz      short loc_140007406
0x1400073f5  lea     ecx, [r12-1]
0x1400073fa  add     ecx, ebp
0x1400073fc  mov     eax, ecx
0x1400073fe  cdq
0x1400073ff  idiv    ebp
0x140007401  sub     edx, ecx
0x140007403  add     [rbx+30h], edx
0x140007406  lea     rax, aDiskDirectoryN; "disk directory name"
0x14000740d  mov     [rsp+88h+var_50], rsi
0x140007412  mov     [rsp+88h+var_58], rax
0x140007417  lea     rbp, [rbx+0B34h]
0x14000741e  mov     eax, [rbx+24h]
0x140007421  lea     r9, aDiskdirectory; "DiskDirectory*"
0x140007428  mov     [rsp+88h+var_60], eax
0x14000742c  mov     rdx, rbp
0x14000742f  lea     rax, aDiskdirectoryt; "DiskDirectoryTemplate"
0x140007436  mov     qword ptr [rbx+3Ch], 1
0x14000743e  mov     rcx, rbx
0x140007441  mov     [rsp+88h+var_68], rax
0x140007446  call    getVarWithOverride
0x14000744b  test    eax, eax
0x14000744d  jz      loc_1400074E8
0x140007453  xor     edx, edx
0x140007455  mov     r8, rsi
0x140007458  mov     rcx, rbp; lpCurrentChar
0x14000745b  test    r14d, r14d
0x14000745e  jz      short loc_140007467
0x140007460  call    ensureDirectoryUNC
0x140007465  jmp     short loc_14000746C
0x140007467  call    ensureDirectory
0x14000746c  test    eax, eax
0x14000746e  jz      short loc_1400074E8
0x140007470  inc     rdi
0x140007473  cmp     [rdi+rbp], r15b
0x140007477  jnz     short loc_140007470
0x140007479  test    rdi, rdi
0x14000747c  jz      short loc_14000748A
0x14000747e  lea     rcx, [rbp-1]
0x140007482  add     rcx, rdi
0x140007485  call    appendPathSeparator
0x14000748a  lea     rax, aDiskLabelName; "disk label name"
0x140007491  mov     [rsp+88h+var_50], rsi
0x140007496  mov     [rsp+88h+var_58], rax
0x14000749b  lea     rdi, [rbx+0A34h]
0x1400074a2  mov     eax, [rbx+24h]
0x1400074a5  lea     r9, aDisklabel; "DiskLabel*"
0x1400074ac  mov     [rsp+88h+var_60], eax
0x1400074b0  mov     rdx, rdi
0x1400074b3  lea     rax, aDisklabeltempl; "DiskLabelTemplate"
0x1400074ba  mov     rcx, rbx
0x1400074bd  mov     [rsp+88h+var_68], rax
0x1400074c2  call    getVarWithOverride
0x1400074c7  test    eax, eax
0x1400074c9  jz      short loc_1400074E8
0x1400074cb  mov     edx, [rbx+24h]
0x1400074ce  mov     r9, rsi
0x1400074d1  mov     r8, rdi
0x1400074d4  mov     rcx, rbx
0x1400074d7  call    infAddDisk
0x1400074dc  test    eax, eax
0x1400074de  mov     ecx, r15d
0x1400074e1  setnz   cl
0x1400074e4  mov     eax, ecx
0x1400074e6  jmp     short loc_1400074EA
0x1400074e8  xor     eax, eax
0x1400074ea  add     rsp, 48h
0x1400074ee  pop     r15
0x1400074f0  pop     r14
0x1400074f2  pop     r13
0x1400074f4  pop     r12
0x1400074f6  pop     rdi
0x1400074f7  pop     rsi
0x1400074f8  pop     rbp
0x1400074f9  pop     rbx
0x1400074fa  retn
```
