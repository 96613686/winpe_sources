# IsPrivatePhoneBook(ushort * const)

- ea: `0x180010884`
- end: `0x180010920`
- name: `?IsPrivatePhoneBook@@YAHQEAG@Z`
- size: `156`
- prototype: `__int64 __fastcall(PCNZWCH lpString2)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011940`

## callees

- `0x180010884`
- `0x18002c1b0`
- `0x18002f382`
- `0x18002f3b0`

## import_xrefs

- `RASAPI32!IsPublicPhonebook` at `0x1800108b2`
- `RASAPI32!IsPublicPhonebook` at `0x1800108b2`
- `RASAPI32!GetPersonalPhonebookPath` at `0x1800108db`
- `RASAPI32!GetPersonalPhonebookPath` at `0x1800108db`

## pseudocode

```c
_BOOL8 __fastcall IsPrivatePhoneBook(PCNZWCH lpString2)
{
  _BOOL8 result; // rax
  WCHAR String1[264]; // [rsp+20h] [rbp-228h] BYREF

  result = 0;
  if ( lpString2 )
  {
    if ( *lpString2 )
    {
      if ( !(unsigned int)IsPublicPhonebook() )
      {
        memset_0(String1, 0, 0x20Au);
        if ( !(unsigned int)GetPersonalPhonebookPath(0, String1, 261)
          || (unsigned int)CompareStringWrapW(String1, lpString2) )
        {
          return 1;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010884  mov     [rsp+arg_8], rbx
0x180010889  push    rdi
0x18001088a  sub     rsp, 240h
0x180010891  mov     rax, cs:__security_cookie
0x180010898  xor     rax, rsp
0x18001089b  mov     [rsp+248h+var_18], rax
0x1800108a3  xor     edi, edi
0x1800108a5  mov     rbx, rcx
0x1800108a8  test    rcx, rcx
0x1800108ab  jz      short loc_1800108FD
0x1800108ad  cmp     [rcx], di
0x1800108b0  jz      short loc_1800108FD
0x1800108b2  call    cs:__imp_IsPublicPhonebook
0x1800108b8  test    eax, eax
0x1800108ba  jnz     short loc_1800108FD
0x1800108bc  xor     edx, edx; Val
0x1800108be  lea     rcx, [rsp+248h+String1]; void *
0x1800108c3  mov     r8d, 20Ah; Size
0x1800108c9  call    memset_0
0x1800108ce  mov     r8d, 105h
0x1800108d4  lea     rdx, [rsp+248h+String1]
0x1800108d9  xor     ecx, ecx
0x1800108db  call    cs:__imp_GetPersonalPhonebookPath
0x1800108e1  test    eax, eax
0x1800108e3  jz      short loc_1800108F6
0x1800108e5  mov     rdx, rbx; lpString2
0x1800108e8  lea     rcx, [rsp+248h+String1]; lpString1
0x1800108ed  call    CompareStringWrapW
0x1800108f2  test    eax, eax
0x1800108f4  jz      short loc_1800108FD
0x1800108f6  mov     eax, 1
0x1800108fb  jmp     short loc_1800108FF
0x1800108fd  xor     eax, eax
0x1800108ff  mov     rcx, [rsp+248h+var_18]
0x180010907  xor     rcx, rsp; StackCookie
0x18001090a  call    __security_check_cookie
0x18001090f  mov     rbx, [rsp+248h+arg_8]
0x180010917  add     rsp, 240h
0x18001091e  pop     rdi
0x18001091f  retn
```
