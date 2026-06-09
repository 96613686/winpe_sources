# CXMLReader::FixupType(CMetaData *,ushort)

- ea: `0x1800266ac`
- end: `0x18002679d`
- name: `?FixupType@CXMLReader@@AEAAXPEAVCMetaData@@G@Z`
- size: `241`
- prototype: `void(CXMLReader *__hidden this, struct CMetaData *, unsigned __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180024434`

## callees

- `0x180003c38`
- `0x180004384`
- `0x1800266ac`

## pseudocode

```c
void __fastcall CXMLReader::FixupType(CXMLReader *this, struct CMetaData *a2, unsigned __int16 a3)
{
  __int64 v3; // rbx
  unsigned __int16 Type; // ax
  int v6; // r9d
  __int64 v7; // r10
  CMetaData *v8; // r11

  v3 = *((_QWORD *)a2 + 4);
  Type = CMetaData::mdGetType(a2, a3);
  if ( v6 == 3 )
    goto LABEL_10;
  if ( v6 )
    return;
  switch ( Type )
  {
    case 8u:
LABEL_10:
      if ( !*(_DWORD *)(v3 + v7 + 1072) )
      {
        *(_WORD *)(v3 + v7 + 1052) = 130;
LABEL_14:
        *(_DWORD *)(*((_QWORD *)v8 + 4) + v7 + 1056) = 0;
        return;
      }
      *(_WORD *)(v3 + v7 + 1052) = 8;
      *(_DWORD *)(*((_QWORD *)v8 + 4) + v7 + 1056) = 0;
      *(_QWORD *)(*((_QWORD *)v8 + 4) + v7 + 1064) = 8;
LABEL_12:
      *(_DWORD *)(*((_QWORD *)v8 + 4) + v7 + 1072) = 0;
      return;
    case 0x8Bu:
      if ( (CMetaData::mdGetFlags(v8, a3) & 0x10) == 0 )
        return;
      *(_WORD *)(v3 + v7 + 1052) = 131;
      goto LABEL_14;
    case 0x40u:
    case 7u:
      *(_QWORD *)(v3 + v7 + 1064) = 8;
      goto LABEL_12;
  }
}

```

## disassembly

```asm
0x1800266ac  mov     [rsp+arg_0], rbx
0x1800266b1  push    rdi
0x1800266b2  sub     rsp, 20h
0x1800266b6  mov     rbx, [rdx+20h]
0x1800266ba  mov     r11, rdx
0x1800266bd  movzx   edi, r8w
0x1800266c1  mov     rcx, r11; this
0x1800266c4  imul    r10, rdi, 25B0h
0x1800266cb  movzx   edx, di; unsigned __int16
0x1800266ce  mov     r9d, [rbx+r10+420h]
0x1800266d6  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x1800266db  mov     edx, 8
0x1800266e0  cmp     r9d, 3
0x1800266e4  jz      short loc_180026734
0x1800266e6  test    r9d, r9d
0x1800266e9  jnz     loc_180026791
0x1800266ef  cmp     ax, dx
0x1800266f2  jz      short loc_180026734
0x1800266f4  mov     ecx, 8Bh
0x1800266f9  cmp     ax, cx
0x1800266fc  jnz     short loc_18002671E
0x1800266fe  movzx   edx, di; unsigned __int16
0x180026701  mov     rcx, r11; this
0x180026704  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x180026709  test    al, 10h
0x18002670b  jz      loc_180026791
0x180026711  mov     word ptr [rbx+r10+41Ch], 83h
0x18002671c  jmp     short loc_180026781
0x18002671e  cmp     ax, 40h ; '@'
0x180026722  jz      short loc_18002672A
0x180026724  cmp     ax, 7
0x180026728  jnz     short loc_180026791
0x18002672a  mov     [rbx+r10+428h], rdx
0x180026732  jmp     short loc_180026764
0x180026734  cmp     dword ptr [rbx+r10+430h], 0
0x18002673d  jz      short loc_180026776
0x18002673f  mov     [rbx+r10+41Ch], dx
0x180026748  mov     rax, [r11+20h]
0x18002674c  mov     dword ptr [rax+r10+420h], 0
0x180026758  mov     rax, [r11+20h]
0x18002675c  mov     [rax+r10+428h], rdx
0x180026764  mov     rax, [r11+20h]
0x180026768  mov     dword ptr [rax+r10+430h], 0
0x180026774  jmp     short loc_180026791
0x180026776  mov     word ptr [rbx+r10+41Ch], 82h
0x180026781  mov     rax, [r11+20h]
0x180026785  mov     dword ptr [rax+r10+420h], 0
0x180026791  mov     rbx, [rsp+28h+arg_0]
0x180026796  add     rsp, 20h
0x18002679a  pop     rdi
0x18002679b  retn
```
