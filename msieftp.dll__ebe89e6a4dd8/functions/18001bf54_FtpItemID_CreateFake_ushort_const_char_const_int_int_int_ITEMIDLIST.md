# FtpItemID_CreateFake(ushort const *,char const *,int,int,int,_ITEMIDLIST * *)

- ea: `0x18001bf54`
- end: `0x18001c09b`
- name: `?FtpItemID_CreateFake@@YAJPEBGPEBDHHHPEAPEFAU_ITEMIDLIST@@@Z`
- size: `327`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszPath@<rcx>, const char *@<rdx>, int@<r8d>, int@<r9d>, int, struct _ITEMIDLIST **)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800112d4`
- `0x18001b3ec`
- `0x18001b710`
- `0x18001b91c`
- `0x1800222ec`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18001bde4`
- `0x18001bf54`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18001bfab`
- `SHLWAPI!PathFindExtensionW` at `0x18001bfab`

## pseudocode

```c
__int64 __fastcall FtpItemID_CreateFake(LPCWSTR pszPath, char *a2, int a3, int a4, int a5, struct _ITEMIDLIST **a6)
{
  bool v10; // zf
  __int64 v11; // r9
  __int64 v12; // r8
  char *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  char *v16; // rcx
  char *v17; // rcx
  char *v18; // rax
  int v20; // [rsp+20h] [rbp-378h] BYREF
  int v21; // [rsp+24h] [rbp-374h]
  __int64 v22; // [rsp+28h] [rbp-370h]
  char v23; // [rsp+40h] [rbp-358h] BYREF
  char v24; // [rsp+144h] [rbp-254h] BYREF

  memset_0(&v20, 0, 0x330u);
  if ( a3 )
  {
    v10 = a4 == 0;
  }
  else
  {
    if ( !pszPath )
    {
LABEL_7:
      v21 = 144;
      v20 = a5 != 0 ? 33 : 5;
      goto LABEL_8;
    }
    v10 = *PathFindExtensionW(pszPath) == 0;
  }
  if ( v10 )
    goto LABEL_7;
  v20 = 9;
  v21 = 128;
LABEL_8:
  v11 = 2147483646;
  v22 = 0;
  v12 = 260;
  v13 = &v24;
  v14 = 2147483646;
  v15 = 260;
  do
  {
    if ( !v14 )
      break;
    if ( !*pszPath )
      break;
    *(_WORD *)v13 = *pszPath++;
    v13 += 2;
    --v14;
    --v15;
  }
  while ( v15 );
  v16 = v13 - 2;
  if ( v15 )
    v16 = v13;
  *(_WORD *)v16 = 0;
  if ( a2 )
  {
    v17 = &v23;
    do
    {
      if ( !v11 )
        break;
      if ( !*a2 )
        break;
      *v17++ = *a2++;
      --v11;
      --v12;
    }
    while ( v12 );
    v18 = v17 - 1;
    if ( v12 )
      v18 = v17;
    *v18 = 0;
  }
  return FtpItemID_Alloc((const struct tagFTPIDLIST *)&v20, a6);
}

```

## disassembly

```asm
0x18001bf54  push    rbx
0x18001bf56  push    rbp
0x18001bf57  push    rsi
0x18001bf58  push    rdi
0x18001bf59  push    r14
0x18001bf5b  push    r15
0x18001bf5d  sub     rsp, 368h
0x18001bf64  mov     rax, cs:__security_cookie
0x18001bf6b  xor     rax, rsp
0x18001bf6e  mov     [rsp+398h+var_48], rax
0x18001bf76  mov     r14, [rsp+398h+arg_28]
0x18001bf7e  mov     ebx, r8d
0x18001bf81  mov     rsi, rdx
0x18001bf84  mov     rdi, rcx
0x18001bf87  xor     edx, edx; Val
0x18001bf89  lea     rcx, [rsp+398h+var_378]; void *
0x18001bf8e  mov     r8d, 330h; Size
0x18001bf94  mov     ebp, r9d
0x18001bf97  call    memset_0
0x18001bf9c  xor     r15d, r15d
0x18001bf9f  test    ebx, ebx
0x18001bfa1  jnz     short loc_18001BFB7
0x18001bfa3  test    rdi, rdi
0x18001bfa6  jz      short loc_18001BFCD
0x18001bfa8  mov     rcx, rdi; pszPath
0x18001bfab  call    cs:__imp_PathFindExtensionW
0x18001bfb1  cmp     r15w, [rax]
0x18001bfb5  jmp     short loc_18001BFB9
0x18001bfb7  test    ebp, ebp
0x18001bfb9  jz      short loc_18001BFCD
0x18001bfbb  mov     [rsp+398h+var_378], 9
0x18001bfc3  mov     [rsp+398h+var_374], 80h
0x18001bfcb  jmp     short loc_18001BFE8
0x18001bfcd  neg     [rsp+398h+arg_20]
0x18001bfd4  mov     [rsp+398h+var_374], 90h
0x18001bfdc  sbb     eax, eax
0x18001bfde  and     eax, 1Ch
0x18001bfe1  add     eax, 5
0x18001bfe4  mov     [rsp+398h+var_378], eax
0x18001bfe8  mov     r9d, 7FFFFFFEh
0x18001bfee  mov     [rsp+398h+var_370], r15
0x18001bff3  mov     r8d, 104h
0x18001bff9  lea     rax, [rsp+398h+var_254]
0x18001c001  mov     ecx, r9d
0x18001c004  mov     edx, r8d
0x18001c007  test    rcx, rcx
0x18001c00a  jz      short loc_18001C02B
0x18001c00c  movzx   r10d, word ptr [rdi]
0x18001c010  test    r10w, r10w
0x18001c014  jz      short loc_18001C02B
0x18001c016  mov     [rax], r10w
0x18001c01a  add     rdi, 2
0x18001c01e  add     rax, 2
0x18001c022  dec     rcx
0x18001c025  sub     rdx, 1
0x18001c029  jnz     short loc_18001C007
0x18001c02b  test    rdx, rdx
0x18001c02e  lea     rcx, [rax-2]
0x18001c032  cmovnz  rcx, rax
0x18001c036  mov     [rcx], r15w
0x18001c03a  test    rsi, rsi
0x18001c03d  jz      short loc_18001C06E
0x18001c03f  lea     rcx, [rsp+398h+var_358]
0x18001c044  test    r9, r9
0x18001c047  jz      short loc_18001C060
0x18001c049  mov     al, [rsi]
0x18001c04b  test    al, al
0x18001c04d  jz      short loc_18001C060
0x18001c04f  mov     [rcx], al
0x18001c051  inc     rsi
0x18001c054  inc     rcx
0x18001c057  dec     r9
0x18001c05a  sub     r8, 1
0x18001c05e  jnz     short loc_18001C044
0x18001c060  test    r8, r8
0x18001c063  lea     rax, [rcx-1]
0x18001c067  cmovnz  rax, rcx
0x18001c06b  mov     [rax], r15b
0x18001c06e  mov     rdx, r14; struct _ITEMIDLIST **
0x18001c071  lea     rcx, [rsp+398h+var_378]; Src
0x18001c076  call    ?FtpItemID_Alloc@@YAJPEBUtagFTPIDLIST@@PEAPEFAU_ITEMIDLIST@@@Z; FtpItemID_Alloc(tagFTPIDLIST const *,_ITEMIDLIST * *)
0x18001c07b  mov     rcx, [rsp+398h+var_48]
0x18001c083  xor     rcx, rsp; StackCookie
0x18001c086  call    __security_check_cookie
0x18001c08b  add     rsp, 368h
0x18001c092  pop     r15
0x18001c094  pop     r14
0x18001c096  pop     rdi
0x18001c097  pop     rsi
0x18001c098  pop     rbp
0x18001c099  pop     rbx
0x18001c09a  retn
```
