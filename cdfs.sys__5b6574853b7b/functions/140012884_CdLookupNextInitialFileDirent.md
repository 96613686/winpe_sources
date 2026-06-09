# CdLookupNextInitialFileDirent

- ea: `0x140012884`
- end: `0x140012926`
- name: `CdLookupNextInitialFileDirent`
- size: `162`
- prototype: `char __fastcall(__int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000dc38`
- `0x140010f68`
- `0x140011138`
- `0x1400120cc`
- `0x140012198`
- `0x14001233c`

## callees

- `0x140012718`
- `0x140012884`
- `0x14001292c`

## pseudocode

```c
char __fastcall CdLookupNextInitialFileDirent(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  unsigned int *v5; // r8
  int v8; // eax
  char v9; // r14
  __int64 v10; // rdx
  char Dirent; // si

  v3 = *(_QWORD *)a3;
  v5 = *(unsigned int **)(a3 + 8);
  v8 = *(_DWORD *)(a3 + 24);
  *(_QWORD *)a3 = v5;
  *(_QWORD *)(a3 + 8) = v3;
  if ( (v8 & 1) != 0 )
    v5 = *(unsigned int **)(a3 + 16);
  *(_DWORD *)(a3 + 24) = 0;
  *(_WORD *)(a3 + 40) = 0;
  *(_QWORD *)(a3 + 32) = 0;
  while ( 1 )
  {
    v9 = *(_BYTE *)(v5[6] + (unsigned __int64)((*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) & 1) == 0) + *(_QWORD *)v5 + 24);
    Dirent = CdLookupNextDirent(a1, a2, v5, v3);
    if ( !Dirent )
      break;
    CdUpdateDirentFromRawDirent(a1, v10, v3, *(_QWORD *)(a3 + 8) + 32LL);
    if ( v9 >= 0 )
      break;
    v5 = (unsigned int *)v3;
  }
  return Dirent;
}

```

## disassembly

```asm
0x140012884  push    rbx
0x140012886  push    rbp
0x140012887  push    rsi
0x140012888  push    rdi
0x140012889  push    r14
0x14001288b  push    r15
0x14001288d  sub     rsp, 28h
0x140012891  mov     rdi, [r8]
0x140012894  mov     rbx, r8
0x140012897  mov     r8, [r8+8]
0x14001289b  mov     r15, rdx
0x14001289e  mov     rbp, rcx
0x1400128a1  mov     eax, [rbx+18h]
0x1400128a4  mov     [rbx], r8
0x1400128a7  mov     [rbx+8], rdi
0x1400128ab  test    al, 1
0x1400128ad  jz      short loc_1400128B3
0x1400128af  mov     r8, [rbx+10h]
0x1400128b3  xor     eax, eax
0x1400128b5  mov     dword ptr [rbx+18h], 0
0x1400128bc  mov     [rbx+28h], ax
0x1400128c0  mov     qword ptr [rbx+20h], 0
0x1400128c8  mov     rax, [rbp+10h]
0x1400128cc  mov     r9, rdi
0x1400128cf  mov     rdx, r15
0x1400128d2  mov     ecx, [rax+30h]
0x1400128d5  mov     eax, [r8+18h]
0x1400128d9  not     ecx
0x1400128db  and     ecx, 1
0x1400128de  add     rcx, rax
0x1400128e1  mov     rax, [r8]
0x1400128e4  mov     r14b, [rcx+rax+18h]
0x1400128e9  mov     rcx, rbp
0x1400128ec  call    CdLookupNextDirent
0x1400128f1  mov     sil, al
0x1400128f4  test    al, al
0x1400128f6  jz      short loc_140012915
0x1400128f8  mov     r9, [rbx+8]
0x1400128fc  mov     r8, rdi
0x1400128ff  add     r9, 20h ; ' '
0x140012903  mov     rcx, rbp
0x140012906  call    CdUpdateDirentFromRawDirent
0x14001290b  test    r14b, r14b
0x14001290e  jns     short loc_140012915
0x140012910  mov     r8, rdi
0x140012913  jmp     short loc_1400128C8
0x140012915  mov     al, sil
0x140012918  add     rsp, 28h
0x14001291c  pop     r15
0x14001291e  pop     r14
0x140012920  pop     rdi
0x140012921  pop     rsi
0x140012922  pop     rbp
0x140012923  pop     rbx
0x140012924  retn
```
