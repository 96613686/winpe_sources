# CdLookupNextDirent

- ea: `0x140012718`
- end: `0x14001287d`
- name: `CdLookupNextDirent`
- size: `357`
- prototype: `char __fastcall(__int64, __int64, unsigned int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b1a4`
- `0x140012508`
- `0x140012884`
- `0x140018bec`

## callees

- `0x140011fd4`
- `0x140012718`

## import_xrefs

- `ntoskrnl!CcUnpinData` at `0x140012759`
- `ntoskrnl!CcUnpinData` at `0x140012849`
- `ntoskrnl!CcUnpinData` at `0x140012759`
- `ntoskrnl!CcUnpinData` at `0x140012849`
- `ntoskrnl!CcMapData` at `0x14001278b`
- `ntoskrnl!CcMapData` at `0x140012808`
- `ntoskrnl!CcMapData` at `0x14001278b`
- `ntoskrnl!CcMapData` at `0x140012808`

## pseudocode

```c
char __fastcall CdLookupNextDirent(__int64 a1, __int64 a2, unsigned int *a3, __int64 a4)
{
  PVOID *Bcb; // rsi
  unsigned int v6; // r8d
  char v7; // bl
  unsigned int v11; // eax
  unsigned int v12; // ecx
  union _LARGE_INTEGER v13; // rax
  ULONG v14; // ebp
  PVOID v15; // rcx
  union _LARGE_INTEGER FileOffset; // [rsp+80h] [rbp+18h] BYREF

  Bcb = (PVOID *)(a4 + 16);
  FileOffset.QuadPart = a3[2];
  v6 = *(_DWORD *)(a4 + 8);
  v7 = 0;
  if ( FileOffset.LowPart == v6 )
  {
    if ( *Bcb )
      goto LABEL_7;
  }
  else if ( *Bcb )
  {
    CcUnpinData(*Bcb);
    *Bcb = 0;
  }
  CcMapData(*(PFILE_OBJECT *)(a2 + 472), &FileOffset, a3[3], 1u, Bcb, (PVOID *)a4);
  *(_DWORD *)(a4 + 12) = a3[3];
  v6 = a3[2];
  *(_DWORD *)(a4 + 8) = v6;
LABEL_7:
  v11 = a3[6];
  *(_DWORD *)(a4 + 24) = v11;
  v12 = a3[7];
  if ( v12 )
  {
    *(_DWORD *)(a4 + 24) = v12 + v11;
    goto LABEL_10;
  }
  for ( v13.QuadPart = v6 + *(_DWORD *)(a4 + 12);
        ;
        v13.QuadPart = (unsigned int)(*(_DWORD *)(a4 + 8) + *(_DWORD *)(a4 + 12)) )
  {
    v15 = *Bcb;
    FileOffset = v13;
    if ( v15 )
    {
      CcUnpinData(v15);
      *Bcb = 0;
    }
LABEL_10:
    if ( !*Bcb )
    {
      v14 = *(_DWORD *)(a2 + 32) - FileOffset.LowPart;
      if ( v14 >= 0x800 )
      {
        v14 = 2048;
      }
      else if ( !v14 )
      {
        return v7;
      }
      CcMapData(*(PFILE_OBJECT *)(a2 + 472), &FileOffset, v14, 1u, Bcb, (PVOID *)a4);
      *(_DWORD *)(a4 + 8) = FileOffset.LowPart;
      *(_DWORD *)(a4 + 24) = 0;
      *(_DWORD *)(a4 + 12) = v14;
    }
    if ( *(_BYTE *)(*(unsigned int *)(a4 + 24) + *(_QWORD *)a4) )
      break;
  }
  v7 = 1;
  *(_DWORD *)(a4 + 28) = CdCheckRawDirentBounds(a1, a4);
  return v7;
}

```

## disassembly

```asm
0x140012718  mov     r11, rsp
0x14001271b  push    rbx
0x14001271c  push    rbp
0x14001271d  push    rsi
0x14001271e  push    rdi
0x14001271f  push    r14
0x140012721  push    r15
0x140012723  sub     rsp, 38h
0x140012727  mov     eax, [r8+8]
0x14001272b  lea     rsi, [r9+10h]
0x14001272f  mov     rbp, r8
0x140012732  mov     [r11+18h], rax
0x140012736  mov     r8d, [r9+8]
0x14001273a  xor     ebx, ebx
0x14001273c  mov     rdi, r9
0x14001273f  mov     r14, rdx
0x140012742  mov     r15, rcx
0x140012745  cmp     eax, r8d
0x140012748  jnz     short loc_140012751
0x14001274a  cmp     [rsi], rbx
0x14001274d  jz      short loc_140012768
0x14001274f  jmp     short loc_1400127A5
0x140012751  mov     rcx, [rsi]; Bcb
0x140012754  test    rcx, rcx
0x140012757  jz      short loc_140012768
0x140012759  call    cs:__imp_CcUnpinData
0x140012760  nop     dword ptr [rax+rax+00h]
0x140012765  mov     [rsi], rbx
0x140012768  mov     r8d, [rbp+0Ch]; Length
0x14001276c  lea     rdx, [rsp+68h+FileOffset]; FileOffset
0x140012774  mov     rcx, [r14+1D8h]; FileObject
0x14001277b  mov     r9d, 1; Flags
0x140012781  mov     [rsp+68h+Buffer], rdi; Buffer
0x140012786  mov     [rsp+68h+Bcb], rsi; Bcb
0x14001278b  call    cs:__imp_CcMapData
0x140012792  nop     dword ptr [rax+rax+00h]
0x140012797  mov     eax, [rbp+0Ch]
0x14001279a  mov     [rdi+0Ch], eax
0x14001279d  mov     r8d, [rbp+8]
0x1400127a1  mov     [rdi+8], r8d
0x1400127a5  mov     eax, [rbp+18h]
0x1400127a8  mov     [rdi+18h], eax
0x1400127ab  mov     ecx, [rbp+1Ch]
0x1400127ae  test    ecx, ecx
0x1400127b0  jnz     short loc_1400127BA
0x1400127b2  mov     eax, [rdi+0Ch]
0x1400127b5  add     eax, r8d
0x1400127b8  jmp     short loc_140012835
0x1400127ba  add     eax, ecx
0x1400127bc  mov     [rdi+18h], eax
0x1400127bf  cmp     [rsi], rbx
0x1400127c2  jnz     short loc_140012824
0x1400127c4  mov     ebp, [r14+20h]
0x1400127c8  sub     ebp, dword ptr [rsp+68h+FileOffset]
0x1400127cf  cmp     ebp, 800h
0x1400127d5  jnb     short loc_1400127E1
0x1400127d7  test    ebp, ebp
0x1400127d9  jz      loc_14001286D
0x1400127df  jmp     short loc_1400127E6
0x1400127e1  mov     ebp, 800h
0x1400127e6  mov     rcx, [r14+1D8h]; FileObject
0x1400127ed  lea     rdx, [rsp+68h+FileOffset]; FileOffset
0x1400127f5  mov     [rsp+68h+Buffer], rdi; Buffer
0x1400127fa  mov     r9d, 1; Flags
0x140012800  mov     r8d, ebp; Length
0x140012803  mov     [rsp+68h+Bcb], rsi; Bcb
0x140012808  call    cs:__imp_CcMapData
0x14001280f  nop     dword ptr [rax+rax+00h]
0x140012814  mov     eax, dword ptr [rsp+68h+FileOffset]
0x14001281b  mov     [rdi+8], eax
0x14001281e  mov     [rdi+18h], ebx
0x140012821  mov     [rdi+0Ch], ebp
0x140012824  mov     ecx, [rdi+18h]
0x140012827  mov     rax, [rdi]
0x14001282a  cmp     [rcx+rax], bl
0x14001282d  jnz     short loc_14001285D
0x14001282f  mov     eax, [rdi+0Ch]
0x140012832  add     eax, [rdi+8]
0x140012835  mov     rcx, [rsi]; Bcb
0x140012838  mov     qword ptr [rsp+68h+FileOffset], rax
0x140012840  test    rcx, rcx
0x140012843  jz      loc_1400127BF
0x140012849  call    cs:__imp_CcUnpinData
0x140012850  nop     dword ptr [rax+rax+00h]
0x140012855  mov     [rsi], rbx
0x140012858  jmp     loc_1400127BF
0x14001285d  mov     rdx, rdi
0x140012860  mov     rcx, r15
0x140012863  mov     bl, 1
0x140012865  call    CdCheckRawDirentBounds
0x14001286a  mov     [rdi+1Ch], eax
0x14001286d  mov     al, bl
0x14001286f  add     rsp, 38h
0x140012873  pop     r15
0x140012875  pop     r14
0x140012877  pop     rdi
0x140012878  pop     rsi
0x140012879  pop     rbp
0x14001287a  pop     rbx
0x14001287b  retn
```
