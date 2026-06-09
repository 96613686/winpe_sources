# CXMLReader::ProcessColumnChild(CParseNode *,ushort,CMetaData *)

- ea: `0x180027c4c`
- end: `0x180027d1e`
- name: `?ProcessColumnChild@CXMLReader@@AEAAJPEAVCParseNode@@GPEAVCMetaData@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CParseNode *, unsigned __int16, struct CMetaData *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180024434`

## callees

- `0x18002701c`
- `0x1800275e4`
- `0x180027c4c`

## pseudocode

```c
__int64 __fastcall CXMLReader::ProcessColumnChild(
        CXMLReader *this,
        struct CParseNode *a2,
        unsigned __int16 a3,
        struct CMetaData *a4)
{
  int v8; // ebp
  __int64 v9; // rbx
  unsigned int v10; // r14d
  __int64 v11; // rdx

  v8 = 0;
  if ( CXMLReader::IsMatch(
         (__int64)this,
         *((unsigned __int16 **)a2 + 4),
         *(_DWORD *)a2,
         *((_DWORD *)a2 + 1),
         (wchar_t *)&wszDataType,
         8,
         1)
    || CXMLReader::IsMatch(
         (__int64)this,
         *((unsigned __int16 **)a2 + 4),
         *(_DWORD *)a2,
         *((_DWORD *)a2 + 1),
         (wchar_t *)&wszDefault,
         7,
         1) )
  {
    LODWORD(v9) = *((_DWORD *)a2 + 11);
    v10 = *((_DWORD *)this + 108);
    while ( 1 )
    {
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= v10 )
        break;
      v11 = *(_QWORD *)(*((_QWORD *)this + 53) + 8 * v9);
      if ( *(struct CParseNode **)(v11 + 16) == a2 && *(_DWORD *)(v11 + 8) == 2 )
      {
        v8 = CXMLReader::ProcessColumnAttribute(this, (struct CParseNode *)v11, a3, a4);
        if ( v8 < 0 )
          break;
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180027c4c  push    rbx
0x180027c4e  push    rbp
0x180027c4f  push    rsi
0x180027c50  push    rdi
0x180027c51  push    r12
0x180027c53  push    r14
0x180027c55  push    r15
0x180027c57  sub     rsp, 40h
0x180027c5b  mov     r15, r9
0x180027c5e  mov     [rsp+78h+var_48], 1
0x180027c66  mov     r9d, [rdx+4]
0x180027c6a  lea     rax, ?wszDataType@@3PAGA; "datatype"
0x180027c71  movzx   r12d, r8w
0x180027c75  mov     [rsp+78h+var_50], 8
0x180027c7d  mov     r8d, [rdx]
0x180027c80  mov     rdi, rdx
0x180027c83  mov     rdx, [rdx+20h]
0x180027c87  mov     rsi, rcx
0x180027c8a  xor     ebp, ebp
0x180027c8c  mov     [rsp+78h+var_58], rax
0x180027c91  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180027c96  test    al, al
0x180027c98  jnz     short loc_180027CCD
0x180027c9a  mov     r9d, [rdi+4]
0x180027c9e  lea     rax, ?wszDefault@@3PAGA; "Default"
0x180027ca5  mov     r8d, [rdi]
0x180027ca8  mov     rcx, rsi
0x180027cab  mov     rdx, [rdi+20h]
0x180027caf  mov     [rsp+78h+var_48], 1
0x180027cb7  mov     [rsp+78h+var_50], 7
0x180027cbf  mov     [rsp+78h+var_58], rax
0x180027cc4  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180027cc9  test    al, al
0x180027ccb  jz      short loc_180027D0C
0x180027ccd  mov     ebx, [rdi+2Ch]
0x180027cd0  mov     r14d, [rsi+1B0h]
0x180027cd7  jmp     short loc_180027D05
0x180027cd9  mov     rax, [rsi+1A8h]
0x180027ce0  mov     rdx, [rax+rbx*8]; struct CParseNode *
0x180027ce4  cmp     [rdx+10h], rdi
0x180027ce8  jnz     short loc_180027D05
0x180027cea  cmp     dword ptr [rdx+8], 2
0x180027cee  jnz     short loc_180027D05
0x180027cf0  mov     r9, r15; struct CMetaData *
0x180027cf3  movzx   r8d, r12w; unsigned __int16
0x180027cf7  mov     rcx, rsi; this
0x180027cfa  call    ?ProcessColumnAttribute@CXMLReader@@AEAAJPEAVCParseNode@@GPEAVCMetaData@@@Z; CXMLReader::ProcessColumnAttribute(CParseNode *,ushort,CMetaData *)
0x180027cff  mov     ebp, eax
0x180027d01  test    eax, eax
0x180027d03  js      short loc_180027D0C
0x180027d05  inc     ebx
0x180027d07  cmp     ebx, r14d
0x180027d0a  jb      short loc_180027CD9
0x180027d0c  mov     eax, ebp
0x180027d0e  add     rsp, 40h
0x180027d12  pop     r15
0x180027d14  pop     r14
0x180027d16  pop     r12
0x180027d18  pop     rdi
0x180027d19  pop     rsi
0x180027d1a  pop     rbp
0x180027d1b  pop     rbx
0x180027d1c  retn
```
