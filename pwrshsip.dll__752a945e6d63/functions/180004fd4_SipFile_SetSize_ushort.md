# SipFile::SetSize(ushort *)

- ea: `0x180004fd4`
- end: `0x1800050a8`
- name: `?SetSize@SipFile@@QEAAKPEAG@Z`
- size: `212`
- prototype: `unsigned int __fastcall(SipFile *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180002c00`

## callees

- `0x180001008`
- `0x180003648`
- `0x180004700`
- `0x180004fd4`
- `0x180005220`

## import_xrefs

- `KERNEL32!SetEndOfFile` at `0x18000508d`
- `KERNEL32!SetEndOfFile` at `0x18000508d`

## pseudocode

```c
__int64 __fastcall SipFile::SetSize(HANDLE *this, unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  const WCHAR *v4; // rsi
  __int64 v5; // rbp
  DWORD v6; // r8d
  unsigned __int8 *v7; // rdi
  unsigned int v9; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int8 *v10; // [rsp+70h] [rbp+18h] BYREF

  if ( a2 && (*a2 = 0, v4 = (const WCHAR *)this[9], v10 = 0, v9 = 0, v4) )
  {
    v5 = -1;
    do
      ++v5;
    while ( v4[v5] );
    v3 = SipFile::ConvertUnicodeStringToFileEncoding((SipFile *)this, v4, v5, (CHAR **)&v10, &v9);
    if ( v3 )
    {
      v7 = v10;
    }
    else
    {
      v6 = v9;
      if ( v9 )
      {
        v7 = v10;
      }
      else
      {
        v7 = (unsigned __int8 *)v4;
        v6 = 2 * v5;
      }
      v3 = SipFile::Write(this, 0, v6, v7);
    }
    if ( v7 != (unsigned __int8 *)v4 )
      operator delete(v7);
    if ( !v3 )
    {
      SipFile::InvalidateCache((SipFile *)this);
      return SetEndOfFile(this[4]);
    }
  }
  else
  {
    return 87;
  }
  return v3;
}

```

## disassembly

```asm
0x180004fd4  mov     [rsp+arg_0], rbx
0x180004fd9  push    rbp
0x180004fda  push    rsi
0x180004fdb  push    rdi
0x180004fdc  push    r14
0x180004fde  push    r15
0x180004fe0  sub     rsp, 30h
0x180004fe4  xor     r15d, r15d
0x180004fe7  mov     r14, rcx
0x180004fea  test    rdx, rdx
0x180004fed  jnz     short loc_180004FF9
0x180004fef  mov     ebx, 57h ; 'W'
0x180004ff4  jmp     loc_180005095
0x180004ff9  mov     [rdx], r15w
0x180004ffd  mov     rsi, [rcx+48h]
0x180005001  mov     [rsp+58h+arg_10], r15
0x180005006  mov     [rsp+58h+arg_8], r15d
0x18000500b  test    rsi, rsi
0x18000500e  jz      short loc_180004FEF
0x180005010  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180005014  inc     rbp
0x180005017  cmp     [rsi+rbp*2], r15w
0x18000501c  jnz     short loc_180005014
0x18000501e  lea     rax, [rsp+58h+arg_8]
0x180005023  mov     r8d, ebp; cchWideChar
0x180005026  lea     r9, [rsp+58h+arg_10]; unsigned __int8 **
0x18000502b  mov     [rsp+58h+var_38], rax; unsigned int *
0x180005030  mov     rdx, rsi; lpWideCharStr
0x180005033  call    ?ConvertUnicodeStringToFileEncoding@SipFile@@IEAAKPEBGKPEAPEAEPEAK@Z; SipFile::ConvertUnicodeStringToFileEncoding(ushort const *,ulong,uchar * *,ulong *)
0x180005038  mov     ebx, eax
0x18000503a  test    eax, eax
0x18000503c  jnz     short loc_18000506B
0x18000503e  mov     r8d, [rsp+58h+arg_8]; unsigned int
0x180005043  test    r8d, r8d
0x180005046  jnz     short loc_180005055
0x180005048  mov     rdi, rsi
0x18000504b  lea     r8d, ds:0[rbp*2]
0x180005053  jmp     short loc_18000505A
0x180005055  mov     rdi, [rsp+58h+arg_10]
0x18000505a  mov     r9, rdi; void *
0x18000505d  xor     edx, edx; unsigned __int64
0x18000505f  mov     rcx, r14; this
0x180005062  call    ?Write@SipFile@@QEAAK_KKPEBX@Z; SipFile::Write(unsigned __int64,ulong,void const *)
0x180005067  mov     ebx, eax
0x180005069  jmp     short loc_180005070
0x18000506b  mov     rdi, [rsp+58h+arg_10]
0x180005070  cmp     rdi, rsi
0x180005073  jz      short loc_18000507D
0x180005075  mov     rcx, rdi; Block
0x180005078  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000507d  test    ebx, ebx
0x18000507f  jnz     short loc_180005095
0x180005081  mov     rcx, r14; this
0x180005084  call    ?InvalidateCache@SipFile@@AEAAXXZ; SipFile::InvalidateCache(void)
0x180005089  mov     rcx, [r14+20h]; hFile
0x18000508d  call    cs:__imp_SetEndOfFile
0x180005093  mov     ebx, eax
0x180005095  mov     eax, ebx
0x180005097  mov     rbx, [rsp+58h+arg_0]
0x18000509c  add     rsp, 30h
0x1800050a0  pop     r15
0x1800050a2  pop     r14
0x1800050a4  pop     rdi
0x1800050a5  pop     rsi
0x1800050a6  pop     rbp
0x1800050a7  retn
```
