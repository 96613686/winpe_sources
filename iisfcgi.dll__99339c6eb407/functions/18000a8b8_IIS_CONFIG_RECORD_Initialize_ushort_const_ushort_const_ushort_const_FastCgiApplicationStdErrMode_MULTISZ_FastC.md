# IIS_CONFIG_RECORD::Initialize(ushort const *,ushort const *,ushort const *,FastCgiApplicationStdErrMode,MULTISZ *,FastCgiApplicationProtocol,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int,ulong)

- ea: `0x18000a8b8`
- end: `0x18000ab63`
- name: `?Initialize@IIS_CONFIG_RECORD@@QEAAJPEBG00W4FastCgiApplicationStdErrMode@@PEAVMULTISZ@@W4FastCgiApplicationProtocol@@KKKKKKKHK@Z`
- size: `683`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum FastCgiApplicationStdErrMode, struct MULTISZ *, enum FastCgiApplicationProtocol, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000a028`

## callees

- `0x180001b78`
- `0x18000a8b8`
- `0x18000edde`
- `0x18000ee10`

## import_xrefs

- `iisutil!IsPathUnc` at `0x18000a9c7`
- `iisutil!IsPathUnc` at `0x18000a9c7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a91a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a91a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ab38`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ab38`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a948`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a962`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a97f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a948`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a962`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a97f`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18000aa09`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18000aa09`
- `iisutil!SAFE_snwprintf` at `0x18000a931`
- `iisutil!SAFE_snwprintf` at `0x18000a931`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000aa74`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000aa74`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000aa26`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000aa3c`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000aa26`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000aa3c`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x18000aa56`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x18000aa56`

## pseudocode

```c
__int64 __fastcall IIS_CONFIG_RECORD::Initialize(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        const struct MULTISZ *a6,
        int a7,
        int a8,
        int a9,
        unsigned int a10,
        unsigned int a11,
        unsigned int a12,
        int a13,
        int a14,
        int a15,
        int a16)
{
  int DirectoryName; // ebx
  __int64 v21; // rsi
  __int64 v22; // r14
  unsigned int v23; // edx
  unsigned int v24; // r9d
  int v25; // eax
  unsigned int v26; // ecx
  unsigned int v27; // r8d
  int v29; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v30[32]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v31; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v32[264]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(v32, 0, 0x20Au);
  STRU::STRU((STRU *)v30, v32, 0x105u);
  DirectoryName = SAFE_snwprintf((struct STRU *)(a1 + 24), L"%s|%s", a2, a3);
  if ( DirectoryName < 0 )
    goto LABEL_27;
  DirectoryName = STRU::Copy((STRU *)(a1 + 80), a2);
  if ( DirectoryName < 0 )
    goto LABEL_27;
  DirectoryName = STRU::Copy((STRU *)(a1 + 136), a3);
  if ( DirectoryName < 0 )
    goto LABEL_27;
  DirectoryName = STRU::Copy((STRU *)(a1 + 192), a4);
  if ( DirectoryName < 0 )
    goto LABEL_27;
  if ( !*(_DWORD *)(a1 + 240) )
    goto LABEL_18;
  v21 = *(_QWORD *)(a1 + 224);
  v22 = -1;
  do
    ++v22;
  while ( *(_WORD *)(v21 + 2 * v22) );
  v29 = 0;
  if ( !v21 )
  {
    DirectoryName = -2147024809;
    goto LABEL_27;
  }
  DirectoryName = IsPathUnc((const unsigned __int16 *)v21, &v29);
  if ( DirectoryName >= 0 )
  {
    if ( v29 == 1 || (unsigned int)v22 >= 2 && *(_WORD *)(v21 + 2) == 58 || *(_WORD *)v21 == 92 )
    {
      v25 = STRU::Copy((STRU *)(a1 + 248), (const struct STRU *)(a1 + 192));
    }
    else
    {
      DirectoryName = GetDirectoryName(a2, v23, v31, v24);
      STRU::SyncWithBuffer((STRU *)v30);
      if ( DirectoryName < 0 )
        goto LABEL_27;
      DirectoryName = STRU::Append((STRU *)(a1 + 248), (const struct STRU *)v30);
      if ( DirectoryName < 0 )
        goto LABEL_27;
      v25 = STRU::Append((STRU *)(a1 + 248), (const struct STRU *)(a1 + 192));
    }
    DirectoryName = v25;
    if ( v25 < 0 )
      goto LABEL_27;
LABEL_18:
    if ( MULTISZ::Copy((MULTISZ *)(a1 + 312), a6) )
    {
      v26 = a12;
      if ( a12 <= a11 )
        v26 = a11 + 1;
      v27 = a10;
      if ( a10 <= v26 )
        v27 = v26 + 1;
      *(_DWORD *)(a1 + 304) = a5;
      *(_DWORD *)(a1 + 368) = a7;
      *(_DWORD *)(a1 + 372) = a8;
      *(_DWORD *)(a1 + 376) = a9;
      *(_DWORD *)(a1 + 392) = a13;
      *(_DWORD *)(a1 + 396) = a14;
      *(_DWORD *)(a1 + 400) = a15;
      *(_DWORD *)(a1 + 404) = a16;
      *(_QWORD *)a1 = *(_QWORD *)(a1 + 56);
      *(_WORD *)(a1 + 16) = *(_WORD *)(a1 + 72);
      *(_DWORD *)(a1 + 380) = v27;
      *(_DWORD *)(a1 + 384) = a11;
      *(_DWORD *)(a1 + 388) = v26;
      *(_QWORD *)(a1 + 8) = 0;
    }
    else
    {
      DirectoryName = -2147024882;
    }
  }
LABEL_27:
  STRU::~STRU((STRU *)v30);
  return (unsigned int)DirectoryName;
}

```

## disassembly

```asm
0x18000a8b8  push    rbp
0x18000a8ba  push    rbx
0x18000a8bb  push    rsi
0x18000a8bc  push    rdi
0x18000a8bd  push    r12
0x18000a8bf  push    r13
0x18000a8c1  push    r14
0x18000a8c3  push    r15
0x18000a8c5  lea     rbp, [rsp-188h]
0x18000a8cd  sub     rsp, 288h
0x18000a8d4  mov     rax, cs:__security_cookie
0x18000a8db  xor     rax, rsp
0x18000a8de  mov     [rbp+1C0h+var_50], rax
0x18000a8e5  mov     r13, [rbp+1C0h+arg_28]
0x18000a8ec  mov     rsi, r8
0x18000a8ef  mov     r12, rdx
0x18000a8f2  mov     rdi, rcx
0x18000a8f5  xor     edx, edx; Val
0x18000a8f7  lea     rcx, [rsp+2C0h+var_260]; void *
0x18000a8fc  mov     r8d, 20Ah; Size
0x18000a902  mov     r14, r9
0x18000a905  call    memset_0
0x18000a90a  mov     r8d, 105h
0x18000a910  lea     rdx, [rsp+2C0h+var_260]
0x18000a915  lea     rcx, [rsp+2C0h+var_298]
0x18000a91a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000a920  lea     rcx, [rdi+18h]
0x18000a924  mov     r9, rsi
0x18000a927  mov     r8, r12
0x18000a92a  lea     rdx, aSS_0; "%s|%s"
0x18000a931  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x18000a937  mov     ebx, eax
0x18000a939  test    eax, eax
0x18000a93b  js      loc_18000AB33
0x18000a941  lea     rcx, [rdi+50h]
0x18000a945  mov     rdx, r12
0x18000a948  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a94e  mov     ebx, eax
0x18000a950  test    eax, eax
0x18000a952  js      loc_18000AB33
0x18000a958  lea     rcx, [rdi+88h]
0x18000a95f  mov     rdx, rsi
0x18000a962  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a968  mov     ebx, eax
0x18000a96a  test    eax, eax
0x18000a96c  js      loc_18000AB33
0x18000a972  lea     r15, [rdi+0C0h]
0x18000a979  mov     rdx, r14
0x18000a97c  mov     rcx, r15
0x18000a97f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a985  mov     ebx, eax
0x18000a987  xor     eax, eax
0x18000a989  test    ebx, ebx
0x18000a98b  js      loc_18000AB33
0x18000a991  cmp     [rdi+0F0h], eax
0x18000a997  jz      loc_18000AA4C
0x18000a99d  mov     rsi, [rdi+0E0h]
0x18000a9a4  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000a9a8  inc     r14
0x18000a9ab  cmp     [rsi+r14*2], ax
0x18000a9b0  jnz     short loc_18000A9A8
0x18000a9b2  mov     [rsp+2C0h+var_2A0], eax
0x18000a9b6  test    rsi, rsi
0x18000a9b9  jz      loc_18000AA7C
0x18000a9bf  lea     rdx, [rsp+2C0h+var_2A0]
0x18000a9c4  mov     rcx, rsi
0x18000a9c7  call    cs:__imp_?IsPathUnc@@YAJPEBGPEAH@Z; IsPathUnc(ushort const *,int *)
0x18000a9cd  mov     ebx, eax
0x18000a9cf  test    eax, eax
0x18000a9d1  js      loc_18000AB33
0x18000a9d7  cmp     [rsp+2C0h+var_2A0], 1
0x18000a9dc  jz      loc_18000AA6A
0x18000a9e2  cmp     r14d, 2
0x18000a9e6  jb      short loc_18000A9EF
0x18000a9e8  cmp     word ptr [rsi+2], 3Ah ; ':'
0x18000a9ed  jz      short loc_18000AA6A
0x18000a9ef  cmp     word ptr [rsi], 5Ch ; '\'
0x18000a9f3  jz      short loc_18000AA6A
0x18000a9f5  mov     r8, [rsp+2C0h+var_278]; unsigned __int16 *
0x18000a9fa  mov     rcx, r12; unsigned __int16 *
0x18000a9fd  call    ?GetDirectoryName@@YAJPEBGKPEAGK@Z; GetDirectoryName(ushort const *,ulong,ushort *,ulong)
0x18000aa02  lea     rcx, [rsp+2C0h+var_298]
0x18000aa07  mov     ebx, eax
0x18000aa09  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000aa0f  test    ebx, ebx
0x18000aa11  js      loc_18000AB33
0x18000aa17  lea     rsi, [rdi+0F8h]
0x18000aa1e  mov     rcx, rsi
0x18000aa21  lea     rdx, [rsp+2C0h+var_298]
0x18000aa26  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x18000aa2c  mov     ebx, eax
0x18000aa2e  test    eax, eax
0x18000aa30  js      loc_18000AB33
0x18000aa36  mov     rdx, r15
0x18000aa39  mov     rcx, rsi
0x18000aa3c  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x18000aa42  mov     ebx, eax
0x18000aa44  test    eax, eax
0x18000aa46  js      loc_18000AB33
0x18000aa4c  lea     rcx, [rdi+138h]
0x18000aa53  mov     rdx, r13
0x18000aa56  call    cs:__imp_?Copy@MULTISZ@@QEAAHAEBV1@@Z; MULTISZ::Copy(MULTISZ const &)
0x18000aa5c  test    eax, eax
0x18000aa5e  jnz     short loc_18000AA86
0x18000aa60  mov     ebx, 8007000Eh
0x18000aa65  jmp     loc_18000AB33
0x18000aa6a  lea     rcx, [rdi+0F8h]
0x18000aa71  mov     rdx, r15
0x18000aa74  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18000aa7a  jmp     short loc_18000AA42
0x18000aa7c  mov     ebx, 80070057h
0x18000aa81  jmp     loc_18000AB33
0x18000aa86  mov     ecx, [rbp+1C0h+arg_58]
0x18000aa8c  mov     edx, [rbp+1C0h+arg_50]
0x18000aa92  cmp     ecx, edx
0x18000aa94  ja      short loc_18000AA99
0x18000aa96  lea     ecx, [rdx+1]
0x18000aa99  mov     r8d, [rbp+1C0h+arg_48]
0x18000aaa0  cmp     r8d, ecx
0x18000aaa3  ja      short loc_18000AAA9
0x18000aaa5  lea     r8d, [rcx+1]
0x18000aaa9  mov     eax, [rbp+1C0h+arg_20]
0x18000aaaf  mov     [rdi+130h], eax
0x18000aab5  mov     eax, [rbp+1C0h+arg_30]
0x18000aabb  mov     [rdi+170h], eax
0x18000aac1  mov     eax, [rbp+1C0h+arg_38]
0x18000aac7  mov     [rdi+174h], eax
0x18000aacd  mov     eax, [rbp+1C0h+arg_40]
0x18000aad3  mov     [rdi+178h], eax
0x18000aad9  mov     eax, [rbp+1C0h+arg_60]
0x18000aadf  mov     [rdi+188h], eax
0x18000aae5  mov     eax, [rbp+1C0h+arg_68]
0x18000aaeb  mov     [rdi+18Ch], eax
0x18000aaf1  mov     eax, [rbp+1C0h+arg_70]
0x18000aaf7  mov     [rdi+190h], eax
0x18000aafd  mov     eax, [rbp+1C0h+arg_78]
0x18000ab03  mov     [rdi+194h], eax
0x18000ab09  mov     rax, [rdi+38h]
0x18000ab0d  mov     [rdi], rax
0x18000ab10  movzx   eax, word ptr [rdi+48h]
0x18000ab14  mov     [rdi+10h], ax
0x18000ab18  mov     [rdi+17Ch], r8d
0x18000ab1f  mov     [rdi+180h], edx
0x18000ab25  mov     [rdi+184h], ecx
0x18000ab2b  mov     qword ptr [rdi+8], 0
0x18000ab33  lea     rcx, [rsp+2C0h+var_298]
0x18000ab38  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ab3e  mov     eax, ebx
0x18000ab40  mov     rcx, [rbp+1C0h+var_50]
0x18000ab47  xor     rcx, rsp; StackCookie
0x18000ab4a  call    __security_check_cookie
0x18000ab4f  add     rsp, 288h
0x18000ab56  pop     r15
0x18000ab58  pop     r14
0x18000ab5a  pop     r13
0x18000ab5c  pop     r12
0x18000ab5e  pop     rdi
0x18000ab5f  pop     rsi
0x18000ab60  pop     rbx
0x18000ab61  pop     rbp
0x18000ab62  retn
```
