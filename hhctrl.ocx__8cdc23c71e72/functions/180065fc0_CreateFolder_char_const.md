# CreateFolder(char const *)

- ea: `0x180065fc0`
- end: `0x18006609a`
- name: `?CreateFolder@@YAHPEBD@Z`
- size: `218`
- prototype: `__int64 __fastcall(const char *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002b6d4`
- `0x180065fc0`

## callees

- `0x180042da8`
- `0x18004f794`
- `0x180065fc0`
- `0x18006a7ac`

## import_xrefs

- `msvcrt!free` at `0x18006601e`
- `msvcrt!free` at `0x180066057`
- `msvcrt!free` at `0x180066087`
- `msvcrt!free` at `0x18006601e`
- `msvcrt!free` at `0x180066057`
- `msvcrt!free` at `0x180066087`
- `KERNEL32!CreateDirectoryA` at `0x18006600c`
- `KERNEL32!CreateDirectoryA` at `0x180066077`
- `KERNEL32!CreateDirectoryA` at `0x18006600c`
- `KERNEL32!CreateDirectoryA` at `0x180066077`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateFolder(const char *a1)
{
  char *v1; // rbx
  __int64 v2; // rdx
  __int64 v4; // rdx
  _BYTE *v5; // rdi
  unsigned int v6; // edi
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+20h] [rbp-28h] BYREF

  if ( a1 )
  {
    v1 = lcStrDup(a1);
    if ( !v1 )
      OOM();
  }
  else
  {
    v1 = 0;
  }
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  if ( CreateDirectoryA(v1, &SecurityAttributes) )
  {
    if ( v1 )
      free(v1);
    return 1;
  }
  else
  {
    LOBYTE(v2) = 92;
    v5 = (_BYTE *)StrRChr(v1, v2);
    if ( v5 || (LOBYTE(v4) = 47, (v5 = (_BYTE *)StrRChr(v1, v4)) != 0) )
    {
      *v5 = 0;
      CreateFolder(v1);
      *v5 = 92;
      v6 = CreateDirectoryA(v1, &SecurityAttributes);
      if ( v1 )
        free(v1);
      return v6;
    }
    else
    {
      if ( v1 )
        free(v1);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180065fc0  mov     [rsp+arg_8], rbx
0x180065fc5  push    rdi
0x180065fc6  sub     rsp, 40h
0x180065fca  xor     edi, edi
0x180065fcc  test    rcx, rcx
0x180065fcf  jz      short loc_180065FE9
0x180065fd1  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x180065fd6  mov     rbx, rax
0x180065fd9  mov     [rsp+48h+arg_0], rax
0x180065fde  test    rax, rax
0x180065fe1  jnz     short loc_180065FF1
0x180065fe3  call    ?OOM@@YAXXZ; OOM(void)
0x180065fe9  mov     rbx, rdi
0x180065fec  mov     [rsp+48h+arg_0], rbx
0x180065ff1  mov     qword ptr [rsp+48h+SecurityAttributes.nLength], 18h
0x180065ffa  mov     qword ptr [rsp+48h+SecurityAttributes.bInheritHandle], rdi
0x180065fff  mov     [rsp+48h+SecurityAttributes.lpSecurityDescriptor], rdi
0x180066004  lea     rdx, [rsp+48h+SecurityAttributes]; lpSecurityAttributes
0x180066009  mov     rcx, rbx; lpPathName
0x18006600c  call    cs:__imp_CreateDirectoryA
0x180066012  test    eax, eax
0x180066014  jz      short loc_18006602B
0x180066016  test    rbx, rbx
0x180066019  jz      short loc_180066024
0x18006601b  mov     rcx, rbx; Block
0x18006601e  call    cs:__imp_free
0x180066024  mov     eax, 1
0x180066029  jmp     short loc_18006608F
0x18006602b  mov     dl, 5Ch ; '\'
0x18006602d  mov     rcx, rbx
0x180066030  call    StrRChr
0x180066035  mov     rdi, rax
0x180066038  test    rax, rax
0x18006603b  jnz     short loc_180066061
0x18006603d  mov     dl, 2Fh ; '/'
0x18006603f  mov     rcx, rbx
0x180066042  call    StrRChr
0x180066047  mov     rdi, rax
0x18006604a  test    rax, rax
0x18006604d  jnz     short loc_180066061
0x18006604f  test    rbx, rbx
0x180066052  jz      short loc_18006605D
0x180066054  mov     rcx, rbx; Block
0x180066057  call    cs:__imp_free
0x18006605d  xor     eax, eax
0x18006605f  jmp     short loc_18006608F
0x180066061  mov     byte ptr [rdi], 0
0x180066064  mov     rcx, rbx; char *
0x180066067  call    ?CreateFolder@@YAHPEBD@Z; CreateFolder(char const *)
0x18006606c  mov     byte ptr [rdi], 5Ch ; '\'
0x18006606f  lea     rdx, [rsp+48h+SecurityAttributes]; lpSecurityAttributes
0x180066074  mov     rcx, rbx; lpPathName
0x180066077  call    cs:__imp_CreateDirectoryA
0x18006607d  mov     edi, eax
0x18006607f  test    rbx, rbx
0x180066082  jz      short loc_18006608D
0x180066084  mov     rcx, rbx; Block
0x180066087  call    cs:__imp_free
0x18006608d  mov     eax, edi
0x18006608f  mov     rbx, [rsp+48h+arg_8]
0x180066094  add     rsp, 40h
0x180066098  pop     rdi
0x180066099  retn
```
