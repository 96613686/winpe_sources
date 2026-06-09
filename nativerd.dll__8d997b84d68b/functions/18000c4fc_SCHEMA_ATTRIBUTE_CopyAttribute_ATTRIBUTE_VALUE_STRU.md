# SCHEMA_ATTRIBUTE::CopyAttribute(ATTRIBUTE_VALUE *,STRU *)

- ea: `0x18000c4fc`
- end: `0x18000c73a`
- name: `?CopyAttribute@SCHEMA_ATTRIBUTE@@QEAAJPEAVATTRIBUTE_VALUE@@PEAVSTRU@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(SCHEMA_ATTRIBUTE *__hidden this, struct ATTRIBUTE_VALUE *, struct STRU *)`
- caller_count: `7`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000c3f0`
- `0x18002eb10`
- `0x18002f4e0`
- `0x18003015c`
- `0x180030bfc`
- `0x180035114`
- `0x180057fa0`

## callees

- `0x18000c4fc`
- `0x180036894`
- `0x1800368f8`
- `0x18003c538`
- `0x180059c30`

## import_xrefs

- `msvcrt!_ultow_s` at `0x18000c67f`
- `msvcrt!_ultow_s` at `0x18000c67f`
- `msvcrt!_itow_s` at `0x18000c5af`
- `msvcrt!_itow_s` at `0x18000c5af`
- `msvcrt!_i64tow_s` at `0x18000c6b8`
- `msvcrt!_i64tow_s` at `0x18000c6b8`
- `msvcrt!_ui64tow_s` at `0x18000c6f1`
- `msvcrt!_ui64tow_s` at `0x18000c6f1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000c714`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000c714`

## pseudocode

```c
int __fastcall SCHEMA_ATTRIBUTE::CopyAttribute(SCHEMA_ATTRIBUTE *this, struct ATTRIBUTE_VALUE *a2, struct STRU *a3)
{
  unsigned int v5; // r8d
  int v6; // eax
  wchar_t *p_Buffer; // r11
  int v8; // ecx
  int v9; // r10d
  errno_t v10; // eax
  STRU *v12; // rcx
  const unsigned __int16 *v13; // rdx
  __int64 *v14; // rax
  unsigned int *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // [rsp+20h] [rbp-428h] BYREF
  int v18; // [rsp+30h] [rbp-418h] BYREF
  wchar_t Buffer; // [rsp+34h] [rbp-414h] BYREF

  if ( !a2 || !a3 )
    return -2147024809;
  v5 = *((_DWORD *)this + 5);
  if ( (v5 & 0x200) != 0 )
  {
    v6 = 1;
    v18 = 7864368;
  }
  else
  {
    v6 = 0;
  }
  p_Buffer = (wchar_t *)&v18;
  if ( v6 )
    p_Buffer = &Buffer;
  v8 = *((_DWORD *)this + 10);
  v9 = v6 != 0 ? 16 : 10;
  if ( v8 == 1 || (*((_DWORD *)a2 + 1) & 0x1F) == 1 )
  {
    v13 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
    goto LABEL_44;
  }
  switch ( v8 )
  {
    case 2:
      if ( (v5 & 0x20) == 0 || **((_DWORD **)a2 + 1) != 0x7FFFFFFF )
      {
        v10 = _itow_s(**((_DWORD **)a2 + 1), p_Buffer, 0x1FEu, v9);
LABEL_40:
        if ( v10 )
          return -2147418113;
        v13 = (const unsigned __int16 *)&v18;
        goto LABEL_44;
      }
LABEL_38:
      v13 = L"Infinite";
LABEL_44:
      v12 = a3;
      return STRU::Copy(v12, v13);
    case 4:
      v12 = a3;
      if ( **((_DWORD **)a2 + 1) )
        v13 = L"true";
      else
        v13 = L"false";
      return STRU::Copy(v12, v13);
    case 5:
      return SCHEMA_ATTRIBUTE::GetFlagsStringFromValue(this, **((_DWORD **)a2 + 1), a3);
    case 6:
      return SCHEMA_ATTRIBUTE::GetEnumStringFromValue(this, **((_DWORD **)a2 + 1), a3);
  }
  if ( v8 != 7 )
  {
    switch ( v8 )
    {
      case 9:
        if ( (v5 & 0x20) == 0 || **((_DWORD **)a2 + 1) != -1 )
        {
          v10 = _ultow_s(**((_DWORD **)a2 + 1), p_Buffer, 0x1FEu, v9);
          goto LABEL_40;
        }
        break;
      case 3:
        if ( (v5 & 0x20) == 0 || **((_QWORD **)a2 + 1) != 0x7FFFFFFFFFFFFFFFLL )
        {
          v10 = _i64tow_s(**((_QWORD **)a2 + 1), p_Buffer, 0x1FEu, v9);
          goto LABEL_40;
        }
        break;
      case 10:
        if ( (v5 & 0x20) == 0 || **((_QWORD **)a2 + 1) != -1 )
        {
          v10 = _ui64tow_s(**((_QWORD **)a2 + 1), p_Buffer, 0x1FEu, v9);
          goto LABEL_40;
        }
        break;
      default:
        return -2147024883;
    }
    goto LABEL_38;
  }
  v14 = (__int64 *)*((_QWORD *)a2 + 1);
  v15 = (unsigned int *)*((_QWORD *)this + 7);
  v16 = (v5 >> 5) & 1;
  v17 = *v14;
  if ( v15 )
    v15 = (unsigned int *)*v15;
  return ((__int64 (__fastcall *)(__int64 *, unsigned int *, __int64, struct STRU *))TIMESPAN_PARSER::GetString)(
           &v17,
           v15,
           v16,
           a3);
}

```

## disassembly

```asm
0x18000c4fc  push    rbx
0x18000c4fe  sub     rsp, 440h
0x18000c505  mov     rax, cs:__security_cookie
0x18000c50c  xor     rax, rsp
0x18000c50f  mov     [rsp+448h+var_18], rax
0x18000c517  mov     rbx, r8
0x18000c51a  mov     r9, rcx
0x18000c51d  test    rdx, rdx
0x18000c520  jz      loc_18000C71C
0x18000c526  test    rbx, rbx
0x18000c529  jz      loc_18000C71C
0x18000c52f  mov     r8d, [rcx+14h]
0x18000c533  bt      r8d, 9
0x18000c538  jnb     short loc_18000C549
0x18000c53a  mov     eax, 1
0x18000c53f  mov     [rsp+448h+var_418], 780030h
0x18000c547  jmp     short loc_18000C54B
0x18000c549  xor     eax, eax
0x18000c54b  test    eax, eax
0x18000c54d  lea     rcx, [rsp+448h+Buffer]
0x18000c552  lea     r11, [rsp+448h+var_418]
0x18000c557  cmovnz  r11, rcx
0x18000c55b  mov     ecx, [r9+28h]
0x18000c55f  neg     eax
0x18000c561  sbb     r10d, r10d
0x18000c564  and     r10d, 6
0x18000c568  add     r10d, 0Ah
0x18000c56c  cmp     ecx, 1
0x18000c56f  jz      loc_18000C70D
0x18000c575  mov     eax, [rdx+4]
0x18000c578  and     al, 1Fh
0x18000c57a  cmp     al, 1
0x18000c57c  jz      loc_18000C70D
0x18000c582  cmp     ecx, 2
0x18000c585  jnz     short loc_18000C5C4
0x18000c587  test    r8b, 20h
0x18000c58b  jz      short loc_18000C59D
0x18000c58d  mov     rax, [rdx+8]
0x18000c591  cmp     dword ptr [rax], 7FFFFFFFh
0x18000c597  jz      loc_18000C6D5
0x18000c59d  mov     rcx, [rdx+8]
0x18000c5a1  mov     r9d, r10d; Radix
0x18000c5a4  mov     r8d, 1FEh; BufferCount
0x18000c5aa  mov     rdx, r11; Buffer
0x18000c5ad  mov     ecx, [rcx]; Value
0x18000c5af  call    cs:__imp__itow_s
0x18000c5b5  jmp     loc_18000C6F7
0x18000c5ba  mov     eax, 8000FFFFh
0x18000c5bf  jmp     loc_18000C721
0x18000c5c4  cmp     ecx, 4
0x18000c5c7  jnz     short loc_18000C5ED
0x18000c5c9  mov     rax, [rdx+8]
0x18000c5cd  mov     rcx, rbx
0x18000c5d0  cmp     dword ptr [rax], 0
0x18000c5d3  jz      short loc_18000C5E1
0x18000c5d5  lea     rdx, aTrue; "true"
0x18000c5dc  jmp     loc_18000C714
0x18000c5e1  lea     rdx, aFalse; "false"
0x18000c5e8  jmp     loc_18000C714
0x18000c5ed  cmp     ecx, 5
0x18000c5f0  jnz     short loc_18000C608
0x18000c5f2  mov     rdx, [rdx+8]
0x18000c5f6  mov     r8, rbx; struct STRU *
0x18000c5f9  mov     rcx, r9; this
0x18000c5fc  mov     edx, [rdx]; unsigned int
0x18000c5fe  call    ?GetFlagsStringFromValue@SCHEMA_ATTRIBUTE@@AEAAJKPEAVSTRU@@@Z; SCHEMA_ATTRIBUTE::GetFlagsStringFromValue(ulong,STRU *)
0x18000c603  jmp     loc_18000C721
0x18000c608  cmp     ecx, 6
0x18000c60b  jnz     short loc_18000C623
0x18000c60d  mov     rdx, [rdx+8]
0x18000c611  mov     r8, rbx; struct STRU *
0x18000c614  mov     rcx, r9; this
0x18000c617  mov     edx, [rdx]; unsigned int
0x18000c619  call    ?GetEnumStringFromValue@SCHEMA_ATTRIBUTE@@AEAAJKPEAVSTRU@@@Z; SCHEMA_ATTRIBUTE::GetEnumStringFromValue(ulong,STRU *)
0x18000c61e  jmp     loc_18000C721
0x18000c623  cmp     ecx, 7
0x18000c626  jnz     short loc_18000C659
0x18000c628  mov     rax, [rdx+8]
0x18000c62c  mov     rdx, [r9+38h]
0x18000c630  shr     r8d, 5
0x18000c634  and     r8d, 1
0x18000c638  mov     rcx, [rax]
0x18000c63b  mov     [rsp+448h+var_428], rcx
0x18000c640  test    rdx, rdx
0x18000c643  jz      short loc_18000C647
0x18000c645  mov     edx, [rdx]
0x18000c647  mov     r9, rbx
0x18000c64a  lea     rcx, [rsp+448h+var_428]
0x18000c64f  call    ?GetString@TIMESPAN_PARSER@@QEAAJW4TIMESPAN_FORMAT@@HPEAVSTRU@@@Z; TIMESPAN_PARSER::GetString(TIMESPAN_FORMAT,int,STRU *)
0x18000c654  jmp     loc_18000C721
0x18000c659  cmp     ecx, 9
0x18000c65c  jnz     short loc_18000C687
0x18000c65e  test    r8b, 20h
0x18000c662  jz      short loc_18000C66D
0x18000c664  mov     rax, [rdx+8]
0x18000c668  cmp     dword ptr [rax], 0FFFFFFFFh
0x18000c66b  jz      short loc_18000C6D5
0x18000c66d  mov     rcx, [rdx+8]
0x18000c671  mov     r9d, r10d; Radix
0x18000c674  mov     r8d, 1FEh; BufferCount
0x18000c67a  mov     rdx, r11; Buffer
0x18000c67d  mov     ecx, [rcx]; Value
0x18000c67f  call    cs:__imp__ultow_s
0x18000c685  jmp     short loc_18000C6F7
0x18000c687  cmp     ecx, 3
0x18000c68a  jnz     short loc_18000C6C0
0x18000c68c  test    r8b, 20h
0x18000c690  jz      short loc_18000C6A5
0x18000c692  mov     rax, [rdx+8]
0x18000c696  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18000c6a0  cmp     [rax], rcx
0x18000c6a3  jz      short loc_18000C6D5
0x18000c6a5  mov     rcx, [rdx+8]
0x18000c6a9  mov     r9d, r10d; Radix
0x18000c6ac  mov     r8d, 1FEh; BufferCount
0x18000c6b2  mov     rdx, r11; Buffer
0x18000c6b5  mov     rcx, [rcx]; Value
0x18000c6b8  call    cs:__imp__i64tow_s
0x18000c6be  jmp     short loc_18000C6F7
0x18000c6c0  cmp     ecx, 0Ah
0x18000c6c3  jnz     short loc_18000C706
0x18000c6c5  test    r8b, 20h
0x18000c6c9  jz      short loc_18000C6DE
0x18000c6cb  mov     rax, [rdx+8]
0x18000c6cf  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x18000c6d3  jnz     short loc_18000C6DE
0x18000c6d5  lea     rdx, aInfinite; "Infinite"
0x18000c6dc  jmp     short loc_18000C711
0x18000c6de  mov     rcx, [rdx+8]
0x18000c6e2  mov     r9d, r10d; Radix
0x18000c6e5  mov     r8d, 1FEh; BufferCount
0x18000c6eb  mov     rdx, r11; Buffer
0x18000c6ee  mov     rcx, [rcx]; Value
0x18000c6f1  call    cs:__imp__ui64tow_s
0x18000c6f7  test    eax, eax
0x18000c6f9  jnz     loc_18000C5BA
0x18000c6ff  lea     rdx, [rsp+448h+var_418]
0x18000c704  jmp     short loc_18000C711
0x18000c706  mov     eax, 8007000Dh
0x18000c70b  jmp     short loc_18000C721
0x18000c70d  mov     rdx, [rdx+8]
0x18000c711  mov     rcx, rbx
0x18000c714  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000c71a  jmp     short loc_18000C721
0x18000c71c  mov     eax, 80070057h
0x18000c721  mov     rcx, [rsp+448h+var_18]
0x18000c729  xor     rcx, rsp; StackCookie
0x18000c72c  call    __security_check_cookie
0x18000c731  add     rsp, 440h
0x18000c738  pop     rbx
0x18000c739  retn
```
