# std::basic_ios<ushort,std::char_traits<ushort>>::setstate(int,bool)

- ea: `0x1800093d4`
- end: `0x18000949b`
- name: `?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z`
- size: `199`
- prototype: `void __fastcall(__int64, int, char)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180007018`
- `0x180007208`
- `0x1800075d8`
- `0x180009260`

## callees

- `0x180001dfc`
- `0x1800074d4`
- `0x1800093b8`
- `0x1800093d4`

## pseudocode

```c
void __fastcall std::basic_ios<unsigned short>::setstate(__int64 a1, int a2, char a3)
{
  int v3; // edx
  char v4; // al
  int v5; // eax
  int v6; // eax
  const struct std::error_code *v7; // rax
  const struct std::error_code *error_code; // rax
  const struct std::error_code *v9; // rax
  _BYTE v10[16]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF

  if ( a2 )
  {
    v3 = *(_DWORD *)(a1 + 16) | a2;
    v4 = v3 | 4;
    if ( *(_QWORD *)(a1 + 72) )
      v4 = v3;
    v5 = v4 & 0x17;
    *(_DWORD *)(a1 + 16) = v5;
    v6 = *(_DWORD *)(a1 + 20) & v5;
    if ( v6 )
    {
      if ( !a3 )
      {
        if ( (v6 & 4) == 0 )
        {
          if ( (v6 & 2) != 0 )
          {
            error_code = (const struct std::error_code *)std::make_error_code(v10);
            std::ios_base::failure::failure(
              (std::ios_base::failure *)pExceptionObject,
              "ios_base::failbit set",
              error_code);
            throw (std::ios_base::failure *)pExceptionObject;
          }
          v9 = (const struct std::error_code *)std::make_error_code(v10);
          std::ios_base::failure::failure((std::ios_base::failure *)pExceptionObject, "ios_base::eofbit set", v9);
          throw (std::ios_base::failure *)pExceptionObject;
        }
        v7 = (const struct std::error_code *)std::make_error_code(v10);
        std::ios_base::failure::failure((std::ios_base::failure *)pExceptionObject, "ios_base::badbit set", v7);
        throw (std::ios_base::failure *)pExceptionObject;
      }
      throw;
    }
  }
}

```

## disassembly

```asm
0x1800093d4  sub     rsp, 68h
0x1800093d8  test    edx, edx
0x1800093da  jz      short loc_18000940B
0x1800093dc  or      edx, [rcx+10h]
0x1800093df  mov     eax, edx
0x1800093e1  or      eax, 4
0x1800093e4  cmp     qword ptr [rcx+48h], 0
0x1800093e9  cmovnz  eax, edx
0x1800093ec  and     eax, 17h
0x1800093ef  mov     [rcx+10h], eax
0x1800093f2  and     eax, [rcx+14h]
0x1800093f5  jz      short loc_18000940B
0x1800093f7  test    r8b, r8b
0x1800093fa  jnz     short loc_180009410
0x1800093fc  lea     rcx, [rsp+68h+var_48]
0x180009401  test    al, 4
0x180009403  jnz     short loc_18000941A
0x180009405  test    al, 2
0x180009407  jz      short loc_180009470
0x180009409  jmp     short loc_180009445
0x18000940b  add     rsp, 68h
0x18000940f  retn
0x180009410  xor     edx, edx; pThrowInfo
0x180009412  xor     ecx, ecx; pExceptionObject
0x180009414  call    _CxxThrowException_0
0x18000941a  call    ?make_error_code@std@@YA?AVerror_code@1@W4io_errc@31@@Z; std::make_error_code(std::io_errc::io_errc)
0x18000941f  mov     r8, rax; struct std::error_code *
0x180009422  lea     rdx, aIosBaseBadbitS; "ios_base::badbit set"
0x180009429  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000942e  call    ??0failure@ios_base@std@@QEAA@PEBDAEBVerror_code@2@@Z; std::ios_base::failure::failure(char const *,std::error_code const &)
0x180009433  lea     rdx, _TI4?AVfailure@ios_base@std@@; pThrowInfo
0x18000943a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000943f  call    _CxxThrowException_0
0x180009445  call    ?make_error_code@std@@YA?AVerror_code@1@W4io_errc@31@@Z; std::make_error_code(std::io_errc::io_errc)
0x18000944a  mov     r8, rax; struct std::error_code *
0x18000944d  lea     rdx, aIosBaseFailbit; "ios_base::failbit set"
0x180009454  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180009459  call    ??0failure@ios_base@std@@QEAA@PEBDAEBVerror_code@2@@Z; std::ios_base::failure::failure(char const *,std::error_code const &)
0x18000945e  lea     rdx, _TI4?AVfailure@ios_base@std@@; pThrowInfo
0x180009465  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000946a  call    _CxxThrowException_0
0x180009470  call    ?make_error_code@std@@YA?AVerror_code@1@W4io_errc@31@@Z; std::make_error_code(std::io_errc::io_errc)
0x180009475  mov     r8, rax; struct std::error_code *
0x180009478  lea     rdx, aIosBaseEofbitS; "ios_base::eofbit set"
0x18000947f  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180009484  call    ??0failure@ios_base@std@@QEAA@PEBDAEBVerror_code@2@@Z; std::ios_base::failure::failure(char const *,std::error_code const &)
0x180009489  lea     rdx, _TI4?AVfailure@ios_base@std@@; pThrowInfo
0x180009490  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180009495  call    _CxxThrowException_0
```
