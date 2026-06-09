# FindModule(void *,_PROCESS_ENTRY *,ushort const *,int,int)

- ea: `0x180018e6c`
- end: `0x180019084`
- name: `?FindModule@@YAPEAU_MODULE_ENTRY@@PEAXPEAU_PROCESS_ENTRY@@PEBGHH@Z`
- size: `536`
- prototype: `struct _MODULE_ENTRY *__usercall@<rax>(void *@<rcx>, struct _PROCESS_ENTRY *@<rdx>, const unsigned __int16 *@<r8>, int@<r9d>, int)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1801a2dd8`
- `0x1801a3f20`
- `0x1801a7540`
- `0x1801acd3c`

## callees

- `0x18000a820`
- `0x180012ed4`
- `0x180018e6c`
- `0x180027430`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018ede`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018f06`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001906e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018ede`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018f06`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001906e`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180018feb`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001903e`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180018feb`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001903e`

## pseudocode

```c
struct _MODULE_ENTRY *__fastcall FindModule(
        void *a1,
        struct _PROCESS_ENTRY *a2,
        const unsigned __int16 *a3,
        int a4,
        int a5)
{
  char *v8; // r14
  char *v9; // rbx
  char *v10; // r15
  struct _MODULE_ENTRY *v11; // rsi
  wchar_t *v12; // rcx
  char *v13; // rcx
  wchar_t Filename[264]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Ext[264]; // [rsp+260h] [rbp+160h] BYREF
  wchar_t Drive[264]; // [rsp+470h] [rbp+370h] BYREF
  wchar_t Dir[264]; // [rsp+680h] [rbp+580h] BYREF

  if ( a3 )
  {
    if ( *a3 )
    {
      v8 = (char *)a2 + 16;
      v9 = (char *)*((_QWORD *)a2 + 2);
      if ( v9 )
      {
        while ( 1 )
        {
          if ( v9 == v8 )
            return 0;
          v10 = *(char **)v9;
          v11 = (struct _MODULE_ENTRY *)v9;
          if ( a4 )
          {
            v12 = (wchar_t *)(v9 + 46);
          }
          else
          {
            memset_0(Drive, 0, 0x20Au);
            memset_0(Dir, 0, 0x20Au);
            memset_0(Filename, 0, 0x20Au);
            memset_0(Ext, 0, 0x20Au);
            _wsplitpath_s(a3, Drive, 0x105u, Dir, 0x105u, Filename, 0x105u, Ext, 0x105u);
            if ( Drive[0] || Dir[0] )
            {
              if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)v9 + 38), a3) )
                goto LABEL_10;
              goto LABEL_8;
            }
            _wsplitpath_s(*((const wchar_t **)v9 + 38), 0, 0, 0, 0, Filename, 0x105u, Ext, 0x105u);
            wcscat_s_ex(Filename, 0x105u, Ext);
            v12 = Filename;
          }
          if ( !(unsigned int)_o__wcsicmp(v12, a3) )
            goto LABEL_10;
LABEL_8:
          v13 = v9 + 174;
          v9 = v10;
          if ( *((_WORD *)v11 + 87) && !(unsigned int)_o__wcsicmp(v13, a3) )
          {
LABEL_10:
            if ( !a5 || (unsigned int)LoadSymbols(a1, v11, 0) )
              return v11;
            return 0;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180018e6c  mov     [rsp-8+arg_18], rbx
0x180018e71  push    rbp
0x180018e72  push    rsi
0x180018e73  push    rdi
0x180018e74  push    r12
0x180018e76  push    r13
0x180018e78  push    r14
0x180018e7a  push    r15
0x180018e7c  lea     rbp, [rsp-7A0h]
0x180018e84  sub     rsp, 8A0h
0x180018e8b  mov     rax, cs:__security_cookie
0x180018e92  xor     rax, rsp
0x180018e95  mov     [rbp+7D0h+var_40], rax
0x180018e9c  mov     rdi, r8
0x180018e9f  mov     r13d, r9d
0x180018ea2  xor     r8d, r8d
0x180018ea5  mov     r12, rcx
0x180018ea8  test    rdi, rdi
0x180018eab  jz      loc_180018F33
0x180018eb1  cmp     [rdi], r8w
0x180018eb5  jz      short loc_180018F33
0x180018eb7  lea     r14, [rdx+10h]
0x180018ebb  mov     rbx, [r14]
0x180018ebe  test    rbx, rbx
0x180018ec1  jz      short loc_180018F33
0x180018ec3  cmp     rbx, r14
0x180018ec6  jz      short loc_180018F33
0x180018ec8  mov     r15, [rbx]
0x180018ecb  mov     rsi, rbx
0x180018ece  test    r13d, r13d
0x180018ed1  jz      loc_180018F5F
0x180018ed7  lea     rcx, [rbx+2Eh]
0x180018edb  mov     rdx, rdi
0x180018ede  call    cs:__imp__o__wcsicmp
0x180018ee4  xor     r8d, r8d
0x180018ee7  test    eax, eax
0x180018ee9  mov     ecx, r8d
0x180018eec  setz    cl
0x180018eef  test    ecx, ecx
0x180018ef1  jnz     short loc_180018F13
0x180018ef3  lea     rcx, [rsi+0AEh]
0x180018efa  mov     rbx, r15
0x180018efd  cmp     [rcx], r8w
0x180018f01  jz      short loc_180018EC3
0x180018f03  mov     rdx, rdi
0x180018f06  call    cs:__imp__o__wcsicmp
0x180018f0c  xor     r8d, r8d
0x180018f0f  test    eax, eax
0x180018f11  jnz     short loc_180018EC3
0x180018f13  cmp     [rbp+7D0h+arg_20], r8d
0x180018f1a  jz      short loc_180018F2E
0x180018f1c  xor     r8d, r8d; unsigned int
0x180018f1f  mov     rdx, rsi; struct _MODULE_ENTRY *
0x180018f22  mov     rcx, r12; void *
0x180018f25  call    ?LoadSymbols@@YAHPEAXPEAU_MODULE_ENTRY@@K@Z; LoadSymbols(void *,_MODULE_ENTRY *,ulong)
0x180018f2a  test    eax, eax
0x180018f2c  jz      short loc_180018F33
0x180018f2e  mov     rax, rsi
0x180018f31  jmp     short loc_180018F35
0x180018f33  xor     eax, eax
0x180018f35  mov     rcx, [rbp+7D0h+var_40]
0x180018f3c  xor     rcx, rsp; StackCookie
0x180018f3f  call    __security_check_cookie
0x180018f44  mov     rbx, [rsp+8D0h+arg_18]
0x180018f4c  add     rsp, 8A0h
0x180018f53  pop     r15
0x180018f55  pop     r14
0x180018f57  pop     r13
0x180018f59  pop     r12
0x180018f5b  pop     rdi
0x180018f5c  pop     rsi
0x180018f5d  pop     rbp
0x180018f5e  retn
0x180018f5f  xor     edx, edx; Val
0x180018f61  lea     rcx, [rbp+7D0h+Drive]; void *
0x180018f68  mov     r8d, 20Ah; Size
0x180018f6e  call    memset_0
0x180018f73  xor     edx, edx; Val
0x180018f75  lea     rcx, [rbp+7D0h+Dir]; void *
0x180018f7c  mov     r8d, 20Ah; Size
0x180018f82  call    memset_0
0x180018f87  xor     edx, edx; Val
0x180018f89  lea     rcx, [rsp+8D0h+var_880]; void *
0x180018f8e  mov     r8d, 20Ah; Size
0x180018f94  call    memset_0
0x180018f99  xor     edx, edx; Val
0x180018f9b  lea     rcx, [rbp+7D0h+var_670]; void *
0x180018fa2  mov     r8d, 20Ah; Size
0x180018fa8  call    memset_0
0x180018fad  mov     ecx, 105h
0x180018fb2  lea     rax, [rbp+7D0h+var_670]
0x180018fb9  mov     [rsp+8D0h+ExtCount], rcx; ExtCount
0x180018fbe  lea     r9, [rbp+7D0h+Dir]; Dir
0x180018fc5  mov     [rsp+8D0h+Ext], rax; Ext
0x180018fca  lea     rdx, [rbp+7D0h+Drive]; Drive
0x180018fd1  mov     [rsp+8D0h+FilenameCount], rcx; FilenameCount
0x180018fd6  lea     rax, [rsp+8D0h+var_880]
0x180018fdb  mov     [rsp+8D0h+Filename], rax; Filename
0x180018fe0  mov     r8d, ecx; DriveCount
0x180018fe3  mov     [rsp+8D0h+DirCount], rcx; DirCount
0x180018fe8  mov     rcx, rdi; FullPath
0x180018feb  call    cs:__imp__wsplitpath_s
0x180018ff1  xor     ecx, ecx
0x180018ff3  cmp     [rbp+7D0h+Drive], cx
0x180018ffa  jnz     short loc_180019064
0x180018ffc  cmp     [rbp+7D0h+Dir], cx
0x180019003  jnz     short loc_180019064
0x180019005  mov     edx, 105h
0x18001900a  lea     rax, [rbp+7D0h+var_670]
0x180019011  mov     [rsp+8D0h+ExtCount], rdx; ExtCount
0x180019016  xor     r9d, r9d; Dir
0x180019019  mov     [rsp+8D0h+Ext], rax; Ext
0x18001901e  xor     r8d, r8d; DriveCount
0x180019021  mov     [rsp+8D0h+FilenameCount], rdx; FilenameCount
0x180019026  lea     rax, [rsp+8D0h+var_880]
0x18001902b  mov     [rsp+8D0h+Filename], rax; Filename
0x180019030  xor     edx, edx; Drive
0x180019032  mov     [rsp+8D0h+DirCount], rcx; DirCount
0x180019037  mov     rcx, [rbx+130h]; FullPath
0x18001903e  call    cs:__imp__wsplitpath_s
0x180019044  lea     r8, [rbp+7D0h+var_670]; unsigned __int16 *
0x18001904b  mov     edx, 105h; unsigned __int64
0x180019050  lea     rcx, [rsp+8D0h+var_880]; unsigned __int16 *
0x180019055  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x18001905a  lea     rcx, [rsp+8D0h+var_880]
0x18001905f  jmp     loc_180018EDB
0x180019064  mov     rcx, [rbx+130h]
0x18001906b  mov     rdx, rdi
0x18001906e  call    cs:__imp__o__wcsicmp
0x180019074  xor     r8d, r8d
0x180019077  test    eax, eax
0x180019079  jz      loc_180018F13
0x18001907f  jmp     loc_180018EF3
```
