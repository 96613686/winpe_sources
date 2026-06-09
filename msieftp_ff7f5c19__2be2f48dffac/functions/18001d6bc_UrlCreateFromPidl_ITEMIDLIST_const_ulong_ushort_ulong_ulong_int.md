# UrlCreateFromPidl(_ITEMIDLIST const *,ulong,ushort *,ulong,ulong,int)

- ea: `0x18001d6bc`
- end: `0x18001d838`
- name: `?UrlCreateFromPidl@@YAJPEFBU_ITEMIDLIST@@KPEAGKKH@Z`
- size: `380`
- prototype: `__int64 __usercall@<rax>(const struct _ITEMIDLIST *@<rcx>, unsigned int@<edx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, int)`
- caller_count: `12`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000f25c`
- `0x1800109dc`
- `0x180015ec0`
- `0x180016a40`
- `0x18001876c`
- `0x180018b4c`
- `0x18001aae4`
- `0x18001fea8`
- `0x180022fb0`
- `0x180024068`
- `0x1800258d4`
- `0x1800261b0`

## callees

- `0x180002240`
- `0x1800096c4`
- `0x18001bda4`
- `0x18001c53c`
- `0x18001d3c4`
- `0x18001d4c0`
- `0x18001d6bc`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x18001d72c`
- `SHELL32!__imp_ILFindLastID` at `0x18001d72c`

## pseudocode

```c
__int64 __fastcall UrlCreateFromPidl(
        const struct _ITEMIDLIST *a1,
        __int16 a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        int a6)
{
  unsigned __int64 v6; // rbp
  const struct _ITEMIDLIST *ID; // rax
  const struct _ITEMIDLIST *v11; // rdi
  unsigned int DisplayName; // ebx
  __int64 v13; // rdx
  _WORD *v14; // rax
  unsigned __int16 *v15; // r8
  __int64 v16; // rcx
  _WORD *v17; // rdx
  _BYTE v20[528]; // [rsp+30h] [rbp-248h] BYREF

  v6 = a4;
  *a3 = 0;
  if ( !a1 || a1 == (const struct _ITEMIDLIST *)-2LL || !(unsigned int)FtpID_IsServerItemID(a1) || !(_DWORD)v6 )
    return 2147942487LL;
  if ( (a2 & 1) != 0 )
  {
    ID = ILFindLastID(a1);
    v11 = ID;
    if ( ID && ID->mkid.cb )
    {
      DisplayName = FtpPidl_GetDisplayName(ID, a3, v6);
      if ( a2 < 0 && (unsigned int)FtpID_IsServerItemID(v11) )
      {
        v13 = 2147483646;
        v14 = v20;
        v15 = a3;
        v16 = 260;
        do
        {
          if ( !v13 )
            break;
          if ( !*v15 )
            break;
          *v14++ = *v15++;
          --v13;
          --v16;
        }
        while ( v16 );
        v17 = v14 - 1;
        if ( v16 )
          v17 = v14;
        *v17 = 0;
        StringCchPrintfW(a3, v6, L"ftp://%s/", v20);
      }
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  else if ( (a2 & 0xC000) != 0 )
  {
    return (unsigned int)ParseUrlCreateFromPidl(a1, a3, v6, a5, a6);
  }
  else
  {
    return (unsigned int)GetFullPrettyName(a1, a3, v6);
  }
  return DisplayName;
}

```

## disassembly

```asm
0x18001d6bc  mov     [rsp+arg_8], rbx
0x18001d6c1  push    rbp
0x18001d6c2  push    rsi
0x18001d6c3  push    rdi
0x18001d6c4  push    r14
0x18001d6c6  push    r15
0x18001d6c8  sub     rsp, 250h
0x18001d6cf  mov     rax, cs:__security_cookie
0x18001d6d6  xor     rax, rsp
0x18001d6d9  mov     [rsp+278h+var_38], rax
0x18001d6e1  xor     r15d, r15d
0x18001d6e4  mov     ebp, r9d
0x18001d6e7  mov     [r8], r15w
0x18001d6eb  mov     rsi, r8
0x18001d6ee  mov     r14d, edx
0x18001d6f1  mov     rbx, rcx
0x18001d6f4  test    rcx, rcx
0x18001d6f7  jz      loc_18001D80C
0x18001d6fd  lea     rax, [rcx+2]
0x18001d701  test    rax, rax
0x18001d704  jz      loc_18001D80C
0x18001d70a  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001d70f  test    eax, eax
0x18001d711  jz      loc_18001D80C
0x18001d717  test    ebp, ebp
0x18001d719  jz      loc_18001D80C
0x18001d71f  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001d722  test    r14b, 1
0x18001d726  jz      loc_18001D7D8
0x18001d72c  call    cs:__imp_ILFindLastID
0x18001d732  mov     rdi, rax
0x18001d735  test    rax, rax
0x18001d738  jz      loc_18001D7D1
0x18001d73e  cmp     [rax], r15w
0x18001d742  jz      loc_18001D7D1
0x18001d748  mov     r8d, ebp; unsigned int
0x18001d74b  mov     rdx, rsi; unsigned __int16 *
0x18001d74e  mov     rcx, rax; struct _ITEMIDLIST *
0x18001d751  call    ?FtpPidl_GetDisplayName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetDisplayName(_ITEMIDLIST const *,ushort *,ulong)
0x18001d756  mov     ebx, eax
0x18001d758  bt      r14d, 0Fh
0x18001d75d  jnb     loc_18001D808
0x18001d763  mov     rcx, rdi; struct _ITEMIDLIST *
0x18001d766  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001d76b  test    eax, eax
0x18001d76d  jz      loc_18001D808
0x18001d773  mov     edx, 7FFFFFFEh
0x18001d778  lea     rax, [rsp+278h+var_248]
0x18001d77d  mov     r8, rsi
0x18001d780  mov     ecx, 104h
0x18001d785  test    rdx, rdx
0x18001d788  jz      short loc_18001D7A9
0x18001d78a  movzx   r9d, word ptr [r8]
0x18001d78e  test    r9w, r9w
0x18001d792  jz      short loc_18001D7A9
0x18001d794  mov     [rax], r9w
0x18001d798  add     r8, 2
0x18001d79c  add     rax, 2
0x18001d7a0  dec     rdx
0x18001d7a3  sub     rcx, 1
0x18001d7a7  jnz     short loc_18001D785
0x18001d7a9  test    rcx, rcx
0x18001d7ac  lea     rdx, [rax-2]
0x18001d7b0  lea     r9, [rsp+278h+var_248]
0x18001d7b5  mov     rcx, rsi; unsigned __int16 *
0x18001d7b8  cmovnz  rdx, rax
0x18001d7bc  lea     r8, aFtpS; "ftp://%s/"
0x18001d7c3  mov     [rdx], r15w
0x18001d7c7  mov     rdx, rbp; unsigned __int64
0x18001d7ca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d7cf  jmp     short loc_18001D808
0x18001d7d1  mov     ebx, 80004005h
0x18001d7d6  jmp     short loc_18001D808
0x18001d7d8  mov     r8d, ebp; unsigned int
0x18001d7db  mov     rdx, rsi; unsigned __int16 *
0x18001d7de  test    r14d, 0C000h
0x18001d7e5  jnz     short loc_18001D7EE
0x18001d7e7  call    ?GetFullPrettyName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; GetFullPrettyName(_ITEMIDLIST const *,ushort *,ulong)
0x18001d7ec  jmp     short loc_18001D806
0x18001d7ee  mov     eax, [rsp+278h+arg_28]
0x18001d7f5  mov     r9d, [rsp+278h+arg_20]; unsigned int
0x18001d7fd  mov     [rsp+278h+var_258], eax; int
0x18001d801  call    ?ParseUrlCreateFromPidl@@YAJPEFBU_ITEMIDLIST@@PEAGKKH@Z; ParseUrlCreateFromPidl(_ITEMIDLIST const *,ushort *,ulong,ulong,int)
0x18001d806  mov     ebx, eax
0x18001d808  mov     eax, ebx
0x18001d80a  jmp     short loc_18001D811
0x18001d80c  mov     eax, 80070057h
0x18001d811  mov     rcx, [rsp+278h+var_38]
0x18001d819  xor     rcx, rsp; StackCookie
0x18001d81c  call    __security_check_cookie
0x18001d821  mov     rbx, [rsp+278h+arg_8]
0x18001d829  add     rsp, 250h
0x18001d830  pop     r15
0x18001d832  pop     r14
0x18001d834  pop     rdi
0x18001d835  pop     rsi
0x18001d836  pop     rbp
0x18001d837  retn
```
