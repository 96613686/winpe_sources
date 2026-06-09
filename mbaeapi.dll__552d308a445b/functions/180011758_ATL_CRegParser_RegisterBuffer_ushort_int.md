# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180011758`
- end: `0x1800118e2`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800118e8`

## callees

- `0x1800024e0`
- `0x180010b7c`
- `0x180010d9c`
- `0x180011758`
- `0x180011ac8`
- `0x1800588d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800117f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800117f6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800118c7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800118c7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800117dd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800117dd`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
  HKEY v9; // rsi
  __int64 v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *(_QWORD *)this = pv;
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken(this, String1);
        if ( Token < 0 )
          break;
        v8 = 0;
        while ( lstrcmpiW(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * v8]) )
        {
          if ( (unsigned int)++v8 >= 0xE )
            goto LABEL_7;
        }
        v9 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v8 + 1);
        if ( !v9 )
          goto LABEL_7;
        Token = ATL::CRegParser::NextToken(this, String1);
        if ( Token < 0 )
          break;
        if ( String1[0] != 123 )
        {
LABEL_7:
          Token = -2147352567;
          break;
        }
        if ( a3 )
        {
          v10 = *(_QWORD *)this;
          Token = ATL::CRegParser::RegisterSubkeys(this, String1, v9, a3, 0);
          if ( Token < 0 )
          {
            *(_QWORD *)this = v10;
            ATL::CRegParser::RegisterSubkeys(this, String1, v9, 0, 0);
            break;
          }
        }
        else
        {
          Token = ATL::CRegParser::RegisterSubkeys(this, String1, v9, 0, 0);
          if ( Token < 0 )
            break;
        }
        while ( **(_WORD **)this == 9 || **(_WORD **)this == 10 || **(_WORD **)this == 13 || **(_WORD **)this == 32 )
          *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
      }
      while ( **(_WORD **)this );
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x180011758  push    rbx
0x18001175a  push    rbp
0x18001175b  push    rsi
0x18001175c  push    rdi
0x18001175d  push    r13
0x18001175f  push    r14
0x180011761  push    r15
0x180011763  mov     eax, 2050h
0x180011768  call    _alloca_probe
0x18001176d  sub     rsp, rax
0x180011770  mov     rax, cs:__security_cookie
0x180011777  xor     rax, rsp
0x18001177a  mov     [rsp+2088h+var_48], rax
0x180011782  mov     r15d, r8d
0x180011785  mov     [rsp+2088h+pv], 0
0x18001178e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180011793  mov     rdi, rcx
0x180011796  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18001179b  mov     ebx, eax
0x18001179d  test    eax, eax
0x18001179f  js      short loc_1800117FE
0x1800117a1  mov     rbp, [rsp+2088h+pv]
0x1800117a6  xor     eax, eax
0x1800117a8  mov     [rdi], rbp
0x1800117ab  cmp     ax, [rbp+0]
0x1800117af  jz      short loc_1800117F3
0x1800117b1  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800117b8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800117bd  mov     rcx, rdi; this
0x1800117c0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800117c5  mov     ebx, eax
0x1800117c7  test    eax, eax
0x1800117c9  js      short loc_1800117F3
0x1800117cb  xor     ebx, ebx
0x1800117cd  movsxd  rsi, ebx
0x1800117d0  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800117d5  add     rsi, rsi
0x1800117d8  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800117dd  call    cs:__imp_lstrcmpiW
0x1800117e3  test    eax, eax
0x1800117e5  jz      short loc_180011820
0x1800117e7  inc     ebx
0x1800117e9  cmp     ebx, 0Eh
0x1800117ec  jb      short loc_1800117CD
0x1800117ee  mov     ebx, 80020009h
0x1800117f3  mov     rcx, rbp; pv
0x1800117f6  call    cs:__imp_CoTaskMemFree
0x1800117fc  mov     eax, ebx
0x1800117fe  mov     rcx, [rsp+2088h+var_48]
0x180011806  xor     rcx, rsp; StackCookie
0x180011809  call    __security_check_cookie
0x18001180e  add     rsp, 2050h
0x180011815  pop     r15
0x180011817  pop     r14
0x180011819  pop     r13
0x18001181b  pop     rdi
0x18001181c  pop     rsi
0x18001181d  pop     rbp
0x18001181e  pop     rbx
0x18001181f  retn
0x180011820  mov     rsi, [r13+rsi*8+8]
0x180011825  test    rsi, rsi
0x180011828  jz      short loc_1800117EE
0x18001182a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001182f  mov     rcx, rdi; this
0x180011832  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011837  mov     ebx, eax
0x180011839  test    eax, eax
0x18001183b  js      short loc_1800117F3
0x18001183d  mov     eax, 7Bh ; '{'
0x180011842  cmp     ax, [rsp+2088h+String1]
0x180011847  jnz     short loc_1800117EE
0x180011849  mov     [rsp+2088h+var_2068], 0; int
0x180011851  mov     r8, rsi; HKEY
0x180011854  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180011859  mov     rcx, rdi; this
0x18001185c  test    r15d, r15d
0x18001185f  jz      short loc_180011895
0x180011861  mov     r14, [rdi]
0x180011864  mov     r9d, r15d; int
0x180011867  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001186c  mov     ebx, eax
0x18001186e  test    eax, eax
0x180011870  jns     short loc_1800118A7
0x180011872  xor     r9d, r9d; int
0x180011875  mov     [rdi], r14
0x180011878  mov     r8, rsi; HKEY
0x18001187b  mov     [rsp+2088h+var_2068], 0; int
0x180011883  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180011888  mov     rcx, rdi; this
0x18001188b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180011890  jmp     loc_1800117F3
0x180011895  xor     r9d, r9d; int
0x180011898  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001189d  mov     ebx, eax
0x18001189f  test    eax, eax
0x1800118a1  js      loc_1800117F3
0x1800118a7  mov     r8, [rdi]
0x1800118aa  movzx   edx, word ptr [r8]
0x1800118ae  mov     ecx, edx
0x1800118b0  sub     ecx, 9
0x1800118b3  jz      short loc_1800118C4
0x1800118b5  sub     ecx, 1
0x1800118b8  jz      short loc_1800118C4
0x1800118ba  sub     ecx, 3
0x1800118bd  jz      short loc_1800118C4
0x1800118bf  cmp     ecx, 13h
0x1800118c2  jnz     short loc_1800118D2
0x1800118c4  mov     rcx, r8; lpsz
0x1800118c7  call    cs:__imp_CharNextW
0x1800118cd  mov     [rdi], rax
0x1800118d0  jmp     short loc_1800118A7
0x1800118d2  xor     eax, eax
0x1800118d4  cmp     ax, dx
0x1800118d7  jnz     loc_1800117B8
0x1800118dd  jmp     loc_1800117F3
```
