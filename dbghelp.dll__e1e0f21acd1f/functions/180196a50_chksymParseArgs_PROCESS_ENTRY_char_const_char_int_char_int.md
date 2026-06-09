# chksymParseArgs(_PROCESS_ENTRY *,char const *,char *,int,char *,int)

- ea: `0x180196a50`
- end: `0x180196c75`
- name: `?chksymParseArgs@@YAPEAU_MODULE_ENTRY@@PEAU_PROCESS_ENTRY@@PEBDPEADH2H@Z`
- size: `549`
- prototype: `struct _MODULE_ENTRY *__usercall@<rax>(struct _PROCESS_ENTRY *@<rcx>, const char *@<rdx>, char *@<r8>, int@<r9d>, char *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18019a770`
- `0x18019ab80`

## callees

- `0x18000af48`
- `0x180014958`
- `0x180027430`
- `0x180196150`
- `0x180196a50`
- `0x180199704`
- `0x18019a480`
- `0x1801acd3c`
- `0x1801d6350`
- `0x180205010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__splitpath_s` at `0x180196b81`
- `api-ms-win-crt-private-l1-1-0!_o__splitpath_s` at `0x180196b81`

## string_xrefs

- `0x180196af5`: `\n%s - ignored because unknown file extension.\n`

## pseudocode

```c
struct _MODULE_ENTRY *__fastcall chksymParseArgs(void **a1, const char *Arg, char *a3, __int64 a4, char *a5)
{
  struct _MODULE_ENTRY *Module; // rbx
  int v9; // r14d
  char *v10; // rcx
  const CHAR *v11; // rcx
  ULONG64 Value[2]; // [rsp+50h] [rbp-B0h] BYREF
  char FullPath[272]; // [rsp+60h] [rbp-A0h] BYREF
  CHAR MultiByteStr[272]; // [rsp+170h] [rbp+70h] BYREF
  char Drive[272]; // [rsp+280h] [rbp+180h] BYREF
  char Dir[272]; // [rsp+390h] [rbp+290h] BYREF
  char Ext[272]; // [rsp+4A0h] [rbp+3A0h] BYREF

  Module = 0;
  Value[0] = 0;
  v9 = 1;
  do
  {
    Arg = GetArg(Arg, FullPath, (int)a3);
    if ( (unsigned int)extmatcha(FullPath, ".pdb") )
    {
      v10 = a5;
LABEL_6:
      strcpy_s_ex(v10, 0x105u, FullPath);
      continue;
    }
    if ( (unsigned int)extmatcha(FullPath, ".dbg") )
    {
      v10 = a3;
      goto LABEL_6;
    }
    if ( Module )
    {
      v11 = "\n%s - ignored because unknown file extension.\n";
LABEL_18:
      ExtensionApis.lpOutputRoutine(v11, FullPath);
      continue;
    }
    memset_0(Drive, 0, 0x105u);
    memset_0(Dir, 0, 0x105u);
    memset_0(MultiByteStr, 0, 0x105u);
    memset_0(Ext, 0, 0x105u);
    _splitpath_s(FullPath, Drive, 0x105u, Dir, 0x105u, MultiByteStr, 0x105u, Ext, 0x105u);
    if ( Drive[0] || Dir[0] || Ext[0] )
    {
      strcpy_s_ex(MultiByteStr, 0x105u, FullPath);
      v9 = 0;
    }
    Module = aFindModule(a1[6], (struct _PROCESS_ENTRY *)a1, MultiByteStr, v9, 0);
    if ( !Module )
    {
      if ( !GetExpressionEx(FullPath, Value, 0) )
      {
        v11 = "\n%s - ignored. The input name/address could not be resolved to a loaded module.\n";
        goto LABEL_18;
      }
      Module = GetModuleForPC((struct _PROCESS_ENTRY *)a1, Value[0], 0, 1, 1, 1);
      if ( !Module )
      {
        ExtensionApis.lpOutputRoutine("%I64lx is not a valid address\n", Value[0]);
        return 0;
      }
    }
  }
  while ( Arg );
  return Module;
}

```

## disassembly

```asm
0x180196a50  push    rbp
0x180196a52  push    rbx
0x180196a53  push    rsi
0x180196a54  push    rdi
0x180196a55  push    r12
0x180196a57  push    r14
0x180196a59  push    r15
0x180196a5b  lea     rbp, [rsp-4C0h]
0x180196a63  sub     rsp, 5C0h
0x180196a6a  mov     rax, cs:__security_cookie
0x180196a71  xor     rax, rsp
0x180196a74  mov     [rbp+4F0h+var_40], rax
0x180196a7b  mov     r12, [rbp+4F0h+arg_20]
0x180196a82  xor     ebx, ebx
0x180196a84  mov     r15, r8
0x180196a87  mov     [rsp+5F0h+Value], 0
0x180196a90  mov     rsi, rdx
0x180196a93  mov     rdi, rcx
0x180196a96  lea     r14d, [rbx+1]
0x180196a9a  lea     rdx, [rsp+5F0h+FullPath]; char *
0x180196a9f  mov     rcx, rsi; char *
0x180196aa2  call    ?GetArg@@YAPEBDPEBDPEADH@Z; GetArg(char const *,char *,int)
0x180196aa7  lea     rdx, aPdb; ".pdb"
0x180196aae  mov     rsi, rax
0x180196ab1  lea     rcx, [rsp+5F0h+FullPath]; char *
0x180196ab6  call    ?extmatcha@@YAHPEBD0@Z; extmatcha(char const *,char const *)
0x180196abb  test    eax, eax
0x180196abd  jz      short loc_180196AC4
0x180196abf  mov     rcx, r12
0x180196ac2  jmp     short loc_180196ADC
0x180196ac4  lea     rdx, aDbg_2; ".dbg"
0x180196acb  lea     rcx, [rsp+5F0h+FullPath]; char *
0x180196ad0  call    ?extmatcha@@YAHPEBD0@Z; extmatcha(char const *,char const *)
0x180196ad5  test    eax, eax
0x180196ad7  jz      short loc_180196AF0
0x180196ad9  mov     rcx, r15; char *
0x180196adc  mov     edx, 105h; unsigned __int64
0x180196ae1  lea     r8, [rsp+5F0h+FullPath]; char *
0x180196ae6  call    ?strcpy_s_ex@@YAHPEAD_KPEBD@Z; strcpy_s_ex(char *,unsigned __int64,char const *)
0x180196aeb  jmp     loc_180196C48
0x180196af0  test    rbx, rbx
0x180196af3  jz      short loc_180196B01
0x180196af5  lea     rcx, aSIgnoredBecaus; "\n%s - ignored because unknown file ext"...
0x180196afc  jmp     loc_180196C37
0x180196b01  mov     ebx, 105h
0x180196b06  lea     rcx, [rbp+4F0h+Drive]; void *
0x180196b0d  mov     r8d, ebx; Size
0x180196b10  xor     edx, edx; Val
0x180196b12  call    memset_0
0x180196b17  mov     r8d, ebx; Size
0x180196b1a  lea     rcx, [rbp+4F0h+Dir]; void *
0x180196b21  xor     edx, edx; Val
0x180196b23  call    memset_0
0x180196b28  mov     r8d, ebx; Size
0x180196b2b  lea     rcx, [rbp+4F0h+MultiByteStr]; void *
0x180196b2f  xor     edx, edx; Val
0x180196b31  call    memset_0
0x180196b36  mov     r8d, ebx; Size
0x180196b39  lea     rcx, [rbp+4F0h+var_150]; void *
0x180196b40  xor     edx, edx; Val
0x180196b42  call    memset_0
0x180196b47  mov     [rsp+5F0h+ExtCount], rbx; ExtCount
0x180196b4c  lea     rax, [rbp+4F0h+var_150]
0x180196b53  mov     [rsp+5F0h+Ext], rax; Ext
0x180196b58  lea     r9, [rbp+4F0h+Dir]; Dir
0x180196b5f  lea     rax, [rbp+4F0h+MultiByteStr]
0x180196b63  mov     [rsp+5F0h+FilenameCount], rbx; FilenameCount
0x180196b68  mov     [rsp+5F0h+Filename], rax; Filename
0x180196b6d  lea     rdx, [rbp+4F0h+Drive]; Drive
0x180196b74  mov     r8d, ebx; DriveCount
0x180196b77  mov     [rsp+5F0h+DirCount], rbx; DirCount
0x180196b7c  lea     rcx, [rsp+5F0h+FullPath]; FullPath
0x180196b81  call    cs:__imp__splitpath_s
0x180196b87  cmp     [rbp+4F0h+Drive], 0
0x180196b8e  jnz     short loc_180196BA2
0x180196b90  cmp     [rbp+4F0h+Dir], 0
0x180196b97  jnz     short loc_180196BA2
0x180196b99  cmp     [rbp+4F0h+var_150], 0
0x180196ba0  jz      short loc_180196BB6
0x180196ba2  lea     r8, [rsp+5F0h+FullPath]; char *
0x180196ba7  mov     rdx, rbx; unsigned __int64
0x180196baa  lea     rcx, [rbp+4F0h+MultiByteStr]; char *
0x180196bae  call    ?strcpy_s_ex@@YAHPEAD_KPEBD@Z; strcpy_s_ex(char *,unsigned __int64,char const *)
0x180196bb3  xor     r14d, r14d
0x180196bb6  mov     rcx, [rdi+30h]; void *
0x180196bba  lea     r8, [rbp+4F0h+MultiByteStr]; lpMultiByteStr
0x180196bbe  mov     r9d, r14d; int
0x180196bc1  mov     dword ptr [rsp+5F0h+DirCount], 0; int
0x180196bc9  mov     rdx, rdi; struct _PROCESS_ENTRY *
0x180196bcc  call    ?aFindModule@@YAPEAU_MODULE_ENTRY@@PEAXPEAU_PROCESS_ENTRY@@PEBDHH@Z; aFindModule(void *,_PROCESS_ENTRY *,char const *,int,int)
0x180196bd1  mov     rbx, rax
0x180196bd4  test    rax, rax
0x180196bd7  jnz     short loc_180196C48
0x180196bd9  xor     r8d, r8d; Remainder
0x180196bdc  lea     rdx, [rsp+5F0h+Value]; Value
0x180196be1  lea     rcx, [rsp+5F0h+FullPath]; Expression
0x180196be6  call    GetExpressionEx
0x180196beb  test    eax, eax
0x180196bed  jz      short loc_180196C30
0x180196bef  mov     rdx, [rsp+5F0h+Value]; unsigned __int64
0x180196bf4  mov     r9b, 1; bool
0x180196bf7  mov     byte ptr [rsp+5F0h+Filename], 1; bool
0x180196bfc  xor     r8d, r8d; bool
0x180196bff  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x180196c02  mov     byte ptr [rsp+5F0h+DirCount], 1; bool
0x180196c07  call    ?GetModuleForPC@@YAPEAU_MODULE_ENTRY@@PEAU_PROCESS_ENTRY@@_K_N222@Z; GetModuleForPC(_PROCESS_ENTRY *,unsigned __int64,bool,bool,bool,bool)
0x180196c0c  mov     rbx, rax
0x180196c0f  test    rax, rax
0x180196c12  jnz     short loc_180196C48
0x180196c14  mov     rdx, [rsp+5F0h+Value]
0x180196c19  lea     rcx, aI64lxIsNotAVal; "%I64lx is not a valid address\n"
0x180196c20  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180196c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180196c2c  xor     eax, eax
0x180196c2e  jmp     short loc_180196C54
0x180196c30  lea     rcx, aSIgnoredTheInp; "\n%s - ignored. The input name/address "...
0x180196c37  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x180196c3e  lea     rdx, [rsp+5F0h+FullPath]
0x180196c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180196c48  test    rsi, rsi
0x180196c4b  jnz     loc_180196A9A
0x180196c51  mov     rax, rbx
0x180196c54  mov     rcx, [rbp+4F0h+var_40]
0x180196c5b  xor     rcx, rsp; StackCookie
0x180196c5e  call    __security_check_cookie
0x180196c63  add     rsp, 5C0h
0x180196c6a  pop     r15
0x180196c6c  pop     r14
0x180196c6e  pop     r12
0x180196c70  pop     rdi
0x180196c71  pop     rsi
0x180196c72  pop     rbx
0x180196c73  pop     rbp
0x180196c74  retn
```
