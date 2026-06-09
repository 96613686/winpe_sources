# CPersistStreamInit::GetXMLColumnName(CRowInfo &,ushort)

- ea: `0x18001be2c`
- end: `0x18001c098`
- name: `?GetXMLColumnName@CPersistStreamInit@@AEAAJAEAVCRowInfo@@G@Z`
- size: `620`
- prototype: `int(CPersistStreamInit *__hidden this, struct CRowInfo *, unsigned __int16)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18001b768`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x1800041b4`
- `0x18001be2c`
- `0x18001c208`
- `0x18001c29c`
- `0x180023b84`

## import_xrefs

- `msvcrt!_itow_s` at `0x18001c00d`
- `msvcrt!_itow_s` at `0x18001c00d`
- `msvcrt!_itoa_s` at `0x18001bfb5`
- `msvcrt!_itoa_s` at `0x18001bfb5`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::GetXMLColumnName(
        CPersistStreamInit *this,
        struct CRowInfo *a2,
        unsigned __int16 a3)
{
  char *v4; // rsi
  __int64 v5; // rbx
  unsigned int v6; // edi
  unsigned __int16 *Name; // rax
  unsigned int v8; // edx
  CPersistStreamInit *v9; // r9
  wchar_t *v10; // r10
  wchar_t *v11; // r14
  _BYTE *v12; // r15
  char IsValidTagName; // r12
  void *v14; // rbp
  bool IsUniqueColumnName; // al
  unsigned __int8 *v16; // rax
  int v17; // edi
  size_t v18; // r8
  __int64 v19; // r8
  char v22; // [rsp+88h] [rbp+10h]
  char *v24; // [rsp+98h] [rbp+20h] BYREF

  v22 = 0;
  v24 = 0;
  v4 = 0;
  LODWORD(v5) = 0;
  v6 = 0;
  Name = CMetaData::mdGetName(a2, a3);
  v11 = Name;
  if ( !Name )
    goto LABEL_9;
  v5 = -1;
  do
    ++v5;
  while ( Name[v5] != (_WORD)v10 );
  if ( (_DWORD)v5 )
  {
    v12 = (char *)v9 + 64;
    IsValidTagName = (char)v10;
    if ( *((_BYTE *)v9 + 64) != (_BYTE)v10 )
    {
      LODWORD(v5) = ToUTF8(Name, v5, &v24);
      if ( (_DWORD)v5 == -1 )
        return (unsigned int)-2147024882;
      v4 = v24;
      v10 = 0;
      v9 = this;
      v22 = 1;
    }
  }
  else
  {
LABEL_9:
    IsValidTagName = 1;
    v12 = (char *)v9 + 64;
  }
  v14 = v11;
  if ( *v12 != (_BYTE)v10 )
    v14 = v4;
  if ( !IsValidTagName )
  {
    IsValidTagName = CPersistStreamInit::IsValidTagName(v9, v14, v5);
    v10 = 0;
  }
  if ( *v12 == (_BYTE)v10 )
  {
    LODWORD(v5) = (_DWORD)v10;
    v11 = v10;
  }
  if ( !IsValidTagName )
  {
    IsUniqueColumnName = CPersistStreamInit::IsUniqueColumnName(this, a2, a3, v14);
    LOBYTE(v10) = 0;
    if ( IsUniqueColumnName )
      goto LABEL_37;
  }
  if ( (int)v5 >= 7 )
  {
LABEL_25:
    v17 = a3;
    LOBYTE(v24) = 1;
    do
    {
      v18 = (unsigned int)v5 - 1LL;
      if ( *v12 )
      {
        *v4 = 99;
        _itoa_s(v17, v4 + 1, v18, 10);
      }
      else
      {
        *v11 = 99;
        _itow_s(v17, v11 + 1, v18, 10);
      }
      ++v17;
    }
    while ( !CPersistStreamInit::IsUniqueColumnName(this, a2, a3, v14) );
    v6 = 0;
    IsValidTagName = (char)v24;
LABEL_37:
    v19 = 2LL * a3;
    *(_BYTE *)(*((_QWORD *)a2 + 8) + 8 * v19 + 8) = IsValidTagName;
    *(_QWORD *)(*((_QWORD *)a2 + 8) + 8 * v19) = v14;
    *(_BYTE *)(*((_QWORD *)a2 + 8) + 8 * v19 + 9) = v22;
    *(_BYTE *)(*((_QWORD *)a2 + 8) + 8 * v19 + 10) = *v12;
    return v6;
  }
  if ( *v12 == (_BYTE)v10 )
  {
    v16 = MMMAlloc(0xEu, v8);
    v11 = (wchar_t *)v16;
  }
  else
  {
    if ( v4 )
      operator delete((unsigned __int8 *)v4);
    v16 = MMMAlloc(7u, v8);
    v4 = (char *)v16;
  }
  if ( v16 )
  {
    v14 = v16;
    v22 = 1;
    LODWORD(v5) = 7;
    goto LABEL_25;
  }
  v6 = -2147024882;
  if ( v22 )
  {
    if ( v11 )
      operator delete((unsigned __int8 *)v11);
    if ( v4 )
      operator delete((unsigned __int8 *)v4);
  }
  return v6;
}

```

## disassembly

```asm
0x18001be2c  mov     rax, rsp
0x18001be2f  mov     [rax+18h], r8w
0x18001be34  mov     [rax+8], rcx
0x18001be38  push    rbx
0x18001be39  push    rbp
0x18001be3a  push    rsi
0x18001be3b  push    rdi
0x18001be3c  push    r12
0x18001be3e  push    r13
0x18001be40  push    r14
0x18001be42  push    r15
0x18001be44  sub     rsp, 38h
0x18001be48  xor     r10d, r10d
0x18001be4b  mov     r13, rdx
0x18001be4e  mov     r9, rcx
0x18001be51  mov     [rsp+78h+arg_8], r10b
0x18001be59  mov     rcx, r13; this
0x18001be5c  mov     [rax+20h], r10
0x18001be60  movzx   edx, r8w; unsigned __int16
0x18001be64  mov     [rsp+78h+var_58], r10d
0x18001be69  mov     esi, r10d
0x18001be6c  mov     ebx, r10d
0x18001be6f  mov     edi, r10d
0x18001be72  call    ?mdGetName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetName(ushort)
0x18001be77  mov     r14, rax
0x18001be7a  test    rax, rax
0x18001be7d  jz      short loc_18001BEE2
0x18001be7f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001be83  inc     rbx
0x18001be86  cmp     [rax+rbx*2], r10w
0x18001be8b  jnz     short loc_18001BE83
0x18001be8d  test    ebx, ebx
0x18001be8f  jz      short loc_18001BEE2
0x18001be91  lea     r15, [r9+40h]
0x18001be95  mov     r12b, r10b
0x18001be98  cmp     [r15], r10b
0x18001be9b  jz      short loc_18001BEE9
0x18001be9d  lea     r8, [rsp+78h+arg_18]; char **
0x18001bea5  mov     edx, ebx; int
0x18001bea7  mov     rcx, r14; unsigned __int16 *
0x18001beaa  call    ?ToUTF8@@YAHPEAGHPEAPEAD@Z; ToUTF8(ushort *,int,char * *)
0x18001beaf  mov     ebx, eax
0x18001beb1  cmp     eax, 0FFFFFFFFh
0x18001beb4  jz      short loc_18001BED8
0x18001beb6  mov     rsi, [rsp+78h+arg_18]
0x18001bebe  xor     r10d, r10d
0x18001bec1  mov     r9, [rsp+78h+arg_0]
0x18001bec9  mov     [rsp+78h+var_58], r10d
0x18001bece  mov     [rsp+78h+arg_8], 1
0x18001bed6  jmp     short loc_18001BEE9
0x18001bed8  mov     edi, 8007000Eh
0x18001bedd  jmp     loc_18001C084
0x18001bee2  mov     r12b, 1
0x18001bee5  lea     r15, [r9+40h]
0x18001bee9  cmp     [r15], r10b
0x18001beec  mov     rbp, r14
0x18001beef  cmovnz  rbp, rsi
0x18001bef3  test    r12b, r12b
0x18001bef6  jnz     short loc_18001BF0C
0x18001bef8  mov     r8d, ebx; unsigned int
0x18001befb  mov     rdx, rbp; void *
0x18001befe  mov     rcx, r9; this
0x18001bf01  call    ?IsValidTagName@CPersistStreamInit@@AEBA_NPEAXK@Z; CPersistStreamInit::IsValidTagName(void *,ulong)
0x18001bf06  mov     r12b, al
0x18001bf09  xor     r10d, r10d
0x18001bf0c  cmp     [r15], r10b
0x18001bf0f  jnz     short loc_18001BF17
0x18001bf11  mov     ebx, r10d
0x18001bf14  mov     r14, r10
0x18001bf17  test    r12b, r12b
0x18001bf1a  jnz     short loc_18001BF43
0x18001bf1c  movzx   r8d, [rsp+78h+arg_10]; unsigned __int16
0x18001bf25  mov     r9, rbp; void *
0x18001bf28  mov     rcx, [rsp+78h+arg_0]; this
0x18001bf30  mov     rdx, r13; struct CRowInfo *
0x18001bf33  call    ?IsUniqueColumnName@CPersistStreamInit@@AEBA_NAEAVCRowInfo@@GPEAX@Z; CPersistStreamInit::IsUniqueColumnName(CRowInfo &,ushort,void *)
0x18001bf38  xor     r10d, r10d
0x18001bf3b  test    al, al
0x18001bf3d  jnz     loc_18001C04B
0x18001bf43  mov     r12d, 7
0x18001bf49  cmp     ebx, r12d
0x18001bf4c  jge     short loc_18001BF7E
0x18001bf4e  cmp     [r15], r10b
0x18001bf51  jz      short loc_18001BFC3
0x18001bf53  test    rsi, rsi
0x18001bf56  jz      short loc_18001BF60
0x18001bf58  mov     rcx, rsi; void *
0x18001bf5b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001bf60  mov     ecx, r12d; unsigned int
0x18001bf63  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18001bf68  mov     rsi, rax
0x18001bf6b  test    rax, rax
0x18001bf6e  jz      short loc_18001BFD2
0x18001bf70  mov     rbp, rax
0x18001bf73  mov     [rsp+78h+arg_8], 1
0x18001bf7b  mov     ebx, r12d
0x18001bf7e  movzx   edi, [rsp+78h+arg_10]
0x18001bf86  mov     eax, 63h ; 'c'
0x18001bf8b  mov     r12, [rsp+78h+arg_0]
0x18001bf93  mov     byte ptr [rsp+78h+arg_18], 1
0x18001bf9b  mov     ebx, ebx
0x18001bf9d  cmp     byte ptr [r15], 0
0x18001bfa1  lea     r8, [rbx-1]; BufferCount
0x18001bfa5  mov     r9d, 0Ah; Radix
0x18001bfab  mov     ecx, edi; Value
0x18001bfad  jz      short loc_18001C005
0x18001bfaf  lea     rdx, [rsi+1]; Buffer
0x18001bfb3  mov     [rsi], al
0x18001bfb5  call    cs:__imp__itoa_s
0x18001bfbc  nop     dword ptr [rax+rax+00h]
0x18001bfc1  jmp     short loc_18001C019
0x18001bfc3  mov     ecx, 0Eh; unsigned int
0x18001bfc8  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18001bfcd  mov     r14, rax
0x18001bfd0  jmp     short loc_18001BF6B
0x18001bfd2  cmp     [rsp+78h+arg_8], 0
0x18001bfda  mov     edi, 8007000Eh
0x18001bfdf  jz      loc_18001C084
0x18001bfe5  test    r14, r14
0x18001bfe8  jz      short loc_18001BFF2
0x18001bfea  mov     rcx, r14; void *
0x18001bfed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001bff2  test    rsi, rsi
0x18001bff5  jz      loc_18001C084
0x18001bffb  mov     rcx, rsi; void *
0x18001bffe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c003  jmp     short loc_18001C084
0x18001c005  lea     rdx, [r14+2]; Buffer
0x18001c009  mov     [r14], ax
0x18001c00d  call    cs:__imp__itow_s
0x18001c014  nop     dword ptr [rax+rax+00h]
0x18001c019  movzx   r8d, [rsp+78h+arg_10]; unsigned __int16
0x18001c022  mov     r9, rbp; void *
0x18001c025  mov     rdx, r13; struct CRowInfo *
0x18001c028  mov     rcx, r12; this
0x18001c02b  inc     edi
0x18001c02d  call    ?IsUniqueColumnName@CPersistStreamInit@@AEBA_NAEAVCRowInfo@@GPEAX@Z; CPersistStreamInit::IsUniqueColumnName(CRowInfo &,ushort,void *)
0x18001c032  test    al, al
0x18001c034  mov     eax, 63h ; 'c'
0x18001c039  jz      loc_18001BF9D
0x18001c03f  mov     edi, [rsp+78h+var_58]
0x18001c043  mov     r12b, byte ptr [rsp+78h+arg_18]
0x18001c04b  mov     rcx, [r13+40h]
0x18001c04f  movzx   r8d, [rsp+78h+arg_10]
0x18001c058  mov     al, [rsp+78h+arg_8]
0x18001c05f  add     r8, r8
0x18001c062  mov     [rcx+r8*8+8], r12b
0x18001c067  mov     rcx, [r13+40h]
0x18001c06b  mov     [rcx+r8*8], rbp
0x18001c06f  mov     rcx, [r13+40h]
0x18001c073  mov     [rcx+r8*8+9], al
0x18001c078  mov     rdx, [r13+40h]
0x18001c07c  mov     cl, [r15]
0x18001c07f  mov     [rdx+r8*8+0Ah], cl
0x18001c084  mov     eax, edi
0x18001c086  add     rsp, 38h
0x18001c08a  pop     r15
0x18001c08c  pop     r14
0x18001c08e  pop     r13
0x18001c090  pop     r12
0x18001c092  pop     rdi
0x18001c093  pop     rsi
0x18001c094  pop     rbp
0x18001c095  pop     rbx
0x18001c096  retn
```
