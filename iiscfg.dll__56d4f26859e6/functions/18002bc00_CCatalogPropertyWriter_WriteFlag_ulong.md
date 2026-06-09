# CCatalogPropertyWriter::WriteFlag(ulong)

- ea: `0x18002bc00`
- end: `0x18002bd99`
- name: `?WriteFlag@CCatalogPropertyWriter@@AEAAJK@Z`
- size: `409`
- prototype: `__int64 __fastcall(CCatalogPropertyWriter *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002bda0`

## callees

- `0x18002ac94`
- `0x18002bc00`
- `0x18002e110`

## import_xrefs

- `msvcrt!_ultow` at `0x18002bcbf`
- `msvcrt!_ultow` at `0x18002bd32`
- `msvcrt!_ultow` at `0x18002bcbf`
- `msvcrt!_ultow` at `0x18002bd32`

## pseudocode

```c
__int64 __fastcall CCatalogPropertyWriter::WriteFlag(CWriter **this, unsigned int a2)
{
  __int64 v3; // rdi
  __int64 result; // rax
  __int64 v5; // rsi
  __int64 v6; // rdi
  __int64 v7; // r8
  char *v8; // rdx
  CWriter *v9; // rax
  __int64 v10; // r8
  CWriter *v11; // rax
  wchar_t Buffer[32]; // [rsp+20h] [rbp-B8h] BYREF
  wchar_t v13[40]; // [rsp+60h] [rbp-78h] BYREF

  v3 = a2;
  result = CWriter::WriteToFile(*this, (char *)L"\t\t\t\t<Flag       InternalName =\"", g_cchBeginFlag, 0);
  if ( (int)result >= 0 )
  {
    v5 = 6 * v3;
    v6 = -1;
    v7 = -1;
    v8 = (char *)*((_QWORD *)this[29] + v5 + 2);
    do
      ++v7;
    while ( *(_WORD *)&v8[2 * v7] );
    result = CWriter::WriteToFile(*this, v8, v7, 0);
    if ( (int)result >= 0 )
    {
      result = CWriter::WriteToFile(*this, (char *)L"\"\t\tValue=\"", g_cchFlagValueEq, 0);
      if ( (int)result >= 0 )
      {
        v9 = this[29];
        Buffer[0] = 0;
        _ultow(**((_DWORD **)v9 + v5 + 4), Buffer, 10);
        v10 = -1;
        do
          ++v10;
        while ( Buffer[v10] );
        result = CWriter::WriteToFile(*this, (char *)Buffer, v10, 0);
        if ( (int)result >= 0 )
        {
          result = CWriter::WriteToFile(*this, (char *)L"\"\t\tID=\"", g_cchFlagIDEq, 0);
          if ( (int)result >= 0 )
          {
            v11 = this[29];
            v13[39] = 0;
            v13[0] = 0;
            _ultow(**((_DWORD **)v11 + v5 + 5), v13, 10);
            do
              ++v6;
            while ( v13[v6] );
            result = CWriter::WriteToFile(*this, (char *)v13, v6, 0);
            if ( (int)result >= 0 )
              return CWriter::WriteToFile(*this, (char *)L"\"\t/>\r\n", g_cchEndFlag, 0);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002bc00  mov     [rsp+arg_10], rbx
0x18002bc05  push    rbp
0x18002bc06  push    rsi
0x18002bc07  push    rdi
0x18002bc08  sub     rsp, 0C0h
0x18002bc0f  mov     rax, cs:__security_cookie
0x18002bc16  xor     rax, rsp
0x18002bc19  mov     [rsp+0D8h+var_28], rax
0x18002bc21  mov     r8d, cs:?g_cchBeginFlag@@3KA; unsigned int
0x18002bc28  mov     rbx, rcx
0x18002bc2b  mov     rcx, [rcx]; this
0x18002bc2e  xor     r9d, r9d; int
0x18002bc31  mov     edi, edx
0x18002bc33  lea     rdx, aFlagInternalna; "\t\t\t\t<Flag       InternalName =\""
0x18002bc3a  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002bc3f  xor     ebp, ebp
0x18002bc41  test    eax, eax
0x18002bc43  js      loc_18002BD76
0x18002bc49  mov     rax, [rbx+0E8h]
0x18002bc50  lea     rsi, [rdi+rdi*2]
0x18002bc54  add     rsi, rsi
0x18002bc57  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002bc5b  mov     r8, rdi
0x18002bc5e  mov     rdx, [rax+rsi*8+10h]; void *
0x18002bc63  inc     r8; unsigned int
0x18002bc66  cmp     [rdx+r8*2], bp
0x18002bc6b  jnz     short loc_18002BC63
0x18002bc6d  mov     rcx, [rbx]; this
0x18002bc70  xor     r9d, r9d; int
0x18002bc73  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002bc78  test    eax, eax
0x18002bc7a  js      loc_18002BD76
0x18002bc80  mov     r8d, cs:?g_cchFlagValueEq@@3KA; unsigned int
0x18002bc87  lea     rdx, aValue; "\"\t\tValue=\""
0x18002bc8e  mov     rcx, [rbx]; this
0x18002bc91  xor     r9d, r9d; int
0x18002bc94  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002bc99  test    eax, eax
0x18002bc9b  js      loc_18002BD76
0x18002bca1  mov     rax, [rbx+0E8h]
0x18002bca8  lea     rdx, [rsp+0D8h+Buffer]; Buffer
0x18002bcad  mov     [rsp+0D8h+Buffer], bp
0x18002bcb2  mov     r8d, 0Ah; Radix
0x18002bcb8  mov     rcx, [rax+rsi*8+20h]
0x18002bcbd  mov     ecx, [rcx]; Value
0x18002bcbf  call    cs:__imp__ultow
0x18002bcc5  lea     rax, [rsp+0D8h+Buffer]
0x18002bcca  mov     r8, rdi
0x18002bccd  inc     r8; unsigned int
0x18002bcd0  cmp     [rax+r8*2], bp
0x18002bcd5  jnz     short loc_18002BCCD
0x18002bcd7  mov     rcx, [rbx]; this
0x18002bcda  lea     rdx, [rsp+0D8h+Buffer]; void *
0x18002bcdf  xor     r9d, r9d; int
0x18002bce2  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002bce7  test    eax, eax
0x18002bce9  js      loc_18002BD76
0x18002bcef  mov     r8d, cs:?g_cchFlagIDEq@@3KA; unsigned int
0x18002bcf6  lea     rdx, aId; "\"\t\tID=\""
0x18002bcfd  mov     rcx, [rbx]; this
0x18002bd00  xor     r9d, r9d; int
0x18002bd03  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002bd08  test    eax, eax
0x18002bd0a  js      short loc_18002BD76
0x18002bd0c  mov     rax, [rbx+0E8h]
0x18002bd13  lea     rdx, [rsp+0D8h+var_78]; Buffer
0x18002bd18  mov     [rsp+0D8h+var_2A], bp
0x18002bd20  mov     r8d, 0Ah; Radix
0x18002bd26  mov     [rsp+0D8h+var_78], bp
0x18002bd2b  mov     rcx, [rax+rsi*8+28h]
0x18002bd30  mov     ecx, [rcx]; Value
0x18002bd32  call    cs:__imp__ultow
0x18002bd38  lea     rax, [rsp+0D8h+var_78]
0x18002bd3d  inc     rdi
0x18002bd40  cmp     [rax+rdi*2], bp
0x18002bd44  jnz     short loc_18002BD3D
0x18002bd46  mov     rcx, [rbx]; this
0x18002bd49  lea     rdx, [rsp+0D8h+var_78]; void *
0x18002bd4e  mov     r8d, edi; unsigned int
0x18002bd51  xor     r9d, r9d; int
0x18002bd54  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002bd59  test    eax, eax
0x18002bd5b  js      short loc_18002BD76
0x18002bd5d  mov     r8d, cs:?g_cchEndFlag@@3KA; unsigned int
0x18002bd64  lea     rdx, asc_18003D358; "\"\t/>\r\n"
0x18002bd6b  mov     rcx, [rbx]; this
0x18002bd6e  xor     r9d, r9d; int
0x18002bd71  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002bd76  mov     rcx, [rsp+0D8h+var_28]
0x18002bd7e  xor     rcx, rsp; StackCookie
0x18002bd81  call    __security_check_cookie
0x18002bd86  mov     rbx, [rsp+0D8h+arg_10]
0x18002bd8e  add     rsp, 0C0h
0x18002bd95  pop     rdi
0x18002bd96  pop     rsi
0x18002bd97  pop     rbp
0x18002bd98  retn
```
