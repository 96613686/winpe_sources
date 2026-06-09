# BiCreateEfiEntry

- ea: `0x140832524`
- end: `0x1408326e5`
- name: `BiCreateEfiEntry`
- size: `449`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x14098ea24`
- `0x140ae3180`

## callees

- `0x14073683c`
- `0x140831eb8`
- `0x14083217c`
- `0x140832524`
- `0x140832b58`
- `0x140991c7c`
- `0x140993780`
- `0x140994084`
- `0x140994700`
- `0x140ae9ef0`
- `0x140bb19f0`

## string_xrefs

- `0x14083264c`: `Created new boot entry %d '%ws'`
- `0x1408325cc`: `Created boot entry %d '%ws' using cached variable`
- `0x14083269a`: `BiCreateEfiEntry failed %x`

## pseudocode

```c
__int64 __fastcall BiCreateEfiEntry(__int64 a1, __int64 a2)
{
  unsigned int *v3; // rdi
  int v5; // eax
  void *v6; // r14
  int SavedBootEntry; // ebx
  unsigned int v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int v13; // [rsp+58h] [rbp+38h] BYREF
  PVOID P; // [rsp+60h] [rbp+40h] BYREF
  void *v15; // [rsp+68h] [rbp+48h] BYREF

  v13 = 0;
  v3 = 0;
  v15 = 0;
  P = 0;
  v5 = BcdOpenObject(a1, a2 + 16, &v15);
  v6 = v15;
  SavedBootEntry = v5;
  if ( v5 < 0 )
    goto LABEL_16;
  if ( (*(_DWORD *)(a2 + 48) & 2) == 0 )
  {
    SavedBootEntry = BiCreateBootEntry((__int64)v15, &P);
    if ( SavedBootEntry >= 0 )
    {
      v3 = (unsigned int *)P;
      SavedBootEntry = BiAddBootEntry(P, &v13);
      if ( SavedBootEntry >= 0 )
      {
        BiLogMessage(2, L"Created new boot entry %d '%ws'", v13, (char *)v3 + v3[4]);
        v3[2] = v13;
        v10 = v13;
        *(_DWORD *)(a2 + 48) |= 0x21u;
        *(_DWORD *)(a2 + 32) = v10;
        *(_QWORD *)(a2 + 40) = v3;
        SavedBootEntry = BiSaveFirmwareVariable(v6, v11, v3, v3[1]);
        if ( SavedBootEntry >= 0 )
        {
          *(_DWORD *)(a2 + 48) |= 2u;
          goto LABEL_17;
        }
      }
      goto LABEL_16;
    }
    goto LABEL_15;
  }
  SavedBootEntry = BiGetSavedBootEntry(v15, &P);
  if ( SavedBootEntry < 0 )
  {
LABEL_15:
    v3 = (unsigned int *)P;
    goto LABEL_16;
  }
  v3 = (unsigned int *)P;
  if ( (*(_DWORD *)(a2 + 48) & 8) == 0 )
  {
    SavedBootEntry = BiUpdateObjectReferenceInEfiEntry(P, v6);
    if ( SavedBootEntry >= 0 )
    {
      *(_DWORD *)(a2 + 48) |= 0x20u;
      goto LABEL_7;
    }
LABEL_16:
    BiLogMessage(4, L"BiCreateEfiEntry failed %x", (unsigned int)SavedBootEntry);
    goto LABEL_17;
  }
LABEL_7:
  SavedBootEntry = BiAddBootEntry(v3, &v13);
  if ( SavedBootEntry < 0 )
    goto LABEL_16;
  BiLogMessage(2, L"Created boot entry %d '%ws' using cached variable", v13, (char *)v3 + v3[4]);
  v3[2] = v13;
  v8 = v13;
  *(_DWORD *)(a2 + 48) |= 1u;
  *(_DWORD *)(a2 + 32) = v8;
  *(_QWORD *)(a2 + 40) = v3;
  SavedBootEntry = BiSaveFirmwareVariable(v6, v9, v3, v3[1]);
  if ( SavedBootEntry < 0 )
    goto LABEL_16;
  SavedBootEntry = BiUpdateEfiEntry(a1, a2);
  if ( SavedBootEntry < 0 )
    goto LABEL_16;
LABEL_17:
  if ( v6 )
    BcdCloseObject(v6);
  if ( (*(_DWORD *)(a2 + 48) & 1) == 0 && v3 )
    ExFreePoolWithTag(v3, 0x4B444342u);
  return (unsigned int)SavedBootEntry;
}

```

## disassembly

```asm
0x140832524  mov     [rsp-28h+arg_0], rbx
0x140832529  push    rbp
0x14083252a  push    rsi
0x14083252b  push    rdi
0x14083252c  push    r14
0x14083252e  push    r15
0x140832530  mov     rbp, rsp
0x140832533  sub     rsp, 20h
0x140832537  mov     rsi, rdx
0x14083253a  mov     [rbp+arg_8], 0
0x140832541  xor     edi, edi
0x140832543  mov     [rbp+arg_18], 0
0x14083254b  add     rdx, 10h
0x14083254f  mov     [rbp+P], rdi
0x140832553  lea     r8, [rbp+arg_18]
0x140832557  mov     r15, rcx
0x14083255a  call    BcdOpenObject
0x14083255f  mov     r14, [rbp+arg_18]
0x140832563  mov     ebx, eax
0x140832565  test    eax, eax
0x140832567  js      loc_140832697
0x14083256d  mov     eax, [rsi+30h]
0x140832570  lea     rdx, [rbp+P]
0x140832574  mov     rcx, r14
0x140832577  test    al, 2
0x140832579  jz      loc_140832627
0x14083257f  call    BiGetSavedBootEntry
0x140832584  mov     ebx, eax
0x140832586  test    eax, eax
0x140832588  js      loc_140832693
0x14083258e  mov     eax, [rsi+30h]
0x140832591  mov     rdi, [rbp+P]
0x140832595  test    al, 8
0x140832597  jnz     short loc_1408325B2
0x140832599  mov     rdx, r14
0x14083259c  mov     rcx, rdi
0x14083259f  call    BiUpdateObjectReferenceInEfiEntry
0x1408325a4  mov     ebx, eax
0x1408325a6  test    eax, eax
0x1408325a8  js      loc_140832697
0x1408325ae  or      dword ptr [rsi+30h], 20h
0x1408325b2  lea     rdx, [rbp+arg_8]
0x1408325b6  mov     rcx, rdi
0x1408325b9  call    BiAddBootEntry
0x1408325be  mov     ebx, eax
0x1408325c0  test    eax, eax
0x1408325c2  js      loc_140832697
0x1408325c8  mov     r9d, [rdi+10h]
0x1408325cc  lea     rdx, aCreatedBootEnt; "Created boot entry %d '%ws' using cache"...
0x1408325d3  mov     r8d, [rbp+arg_8]
0x1408325d7  add     r9, rdi
0x1408325da  mov     ecx, 2
0x1408325df  call    BiLogMessage
0x1408325e4  mov     ecx, [rbp+arg_8]
0x1408325e7  mov     r8, rdi
0x1408325ea  mov     [rdi+8], ecx
0x1408325ed  mov     rcx, r14
0x1408325f0  mov     eax, [rbp+arg_8]
0x1408325f3  or      dword ptr [rsi+30h], 1
0x1408325f7  mov     [rsi+20h], eax
0x1408325fa  mov     [rsi+28h], rdi
0x1408325fe  mov     r9d, [rdi+4]
0x140832602  call    BiSaveFirmwareVariable
0x140832607  mov     ebx, eax
0x140832609  test    eax, eax
0x14083260b  js      loc_140832697
0x140832611  mov     rdx, rsi
0x140832614  mov     rcx, r15
0x140832617  call    BiUpdateEfiEntry
0x14083261c  mov     ebx, eax
0x14083261e  test    eax, eax
0x140832620  js      short loc_140832697
0x140832622  jmp     loc_1408326AB
0x140832627  call    BiCreateBootEntry
0x14083262c  mov     ebx, eax
0x14083262e  test    eax, eax
0x140832630  js      short loc_140832693
0x140832632  mov     rdi, [rbp+P]
0x140832636  lea     rdx, [rbp+arg_8]
0x14083263a  mov     rcx, rdi
0x14083263d  call    BiAddBootEntry
0x140832642  mov     ebx, eax
0x140832644  test    eax, eax
0x140832646  js      short loc_140832697
0x140832648  mov     r9d, [rdi+10h]
0x14083264c  lea     rdx, aCreatedNewBoot; "Created new boot entry %d '%ws'"
0x140832653  mov     r8d, [rbp+arg_8]
0x140832657  add     r9, rdi
0x14083265a  mov     ecx, 2
0x14083265f  call    BiLogMessage
0x140832664  mov     ecx, [rbp+arg_8]
0x140832667  mov     r8, rdi
0x14083266a  mov     [rdi+8], ecx
0x14083266d  mov     rcx, r14
0x140832670  mov     eax, [rbp+arg_8]
0x140832673  or      dword ptr [rsi+30h], 21h
0x140832677  mov     [rsi+20h], eax
0x14083267a  mov     [rsi+28h], rdi
0x14083267e  mov     r9d, [rdi+4]
0x140832682  call    BiSaveFirmwareVariable
0x140832687  mov     ebx, eax
0x140832689  test    eax, eax
0x14083268b  js      short loc_140832697
0x14083268d  or      dword ptr [rsi+30h], 2
0x140832691  jmp     short loc_1408326AB
0x140832693  mov     rdi, [rbp+P]
0x140832697  mov     r8d, ebx
0x14083269a  lea     rdx, aBicreateefient; "BiCreateEfiEntry failed %x"
0x1408326a1  mov     ecx, 4
0x1408326a6  call    BiLogMessage
0x1408326ab  test    r14, r14
0x1408326ae  jz      short loc_1408326B8
0x1408326b0  mov     rcx, r14
0x1408326b3  call    BcdCloseObject
0x1408326b8  mov     eax, [rsi+30h]
0x1408326bb  test    al, 1
0x1408326bd  jnz     short loc_1408326D1
0x1408326bf  test    rdi, rdi
0x1408326c2  jz      short loc_1408326D1
0x1408326c4  mov     edx, 4B444342h; Tag
0x1408326c9  mov     rcx, rdi; P
0x1408326cc  call    ExFreePoolWithTag
0x1408326d1  mov     eax, ebx
0x1408326d3  mov     rbx, [rsp+20h+arg_0]
0x1408326d8  add     rsp, 20h
0x1408326dc  pop     r15
0x1408326de  pop     r14
0x1408326e0  pop     rdi
0x1408326e1  pop     rsi
0x1408326e2  pop     rbp
0x1408326e3  retn
```
