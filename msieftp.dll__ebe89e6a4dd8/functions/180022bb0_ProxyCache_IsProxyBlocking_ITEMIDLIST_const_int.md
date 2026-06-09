# ProxyCache_IsProxyBlocking(_ITEMIDLIST const *,int *)

- ea: `0x180022bb0`
- end: `0x180022db9`
- name: `?ProxyCache_IsProxyBlocking@@YAHPEFBU_ITEMIDLIST@@PEAH@Z`
- size: `521`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018b4c`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18001cbd8`
- `0x180022bb0`
- `0x1800271f0`

## import_xrefs

- `SHLWAPI!StrCmpW` at `0x180022c98`
- `SHLWAPI!StrCmpW` at `0x180022d68`
- `SHLWAPI!StrCmpW` at `0x180022c98`
- `SHLWAPI!StrCmpW` at `0x180022d68`
- `SHLWAPI!SHGetValueW` at `0x180022c21`
- `SHLWAPI!SHGetValueW` at `0x180022c21`

## pseudocode

```c
__int64 __fastcall ProxyCache_IsProxyBlocking(const struct _ITEMIDLIST *a1, int *a2)
{
  unsigned int v4; // ebp
  int v5; // edi
  __int64 v6; // rcx
  WCHAR *v7; // r9
  __int64 v8; // r8
  WCHAR *v9; // rax
  WCHAR *v10; // rcx
  unsigned int v11; // edx
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  unsigned int v15; // edx
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // r8d
  int i; // ebx
  __int64 v20; // rsi
  DWORD pcbData[4]; // [rsp+30h] [rbp-1098h] BYREF
  WCHAR psz1[2088]; // [rsp+40h] [rbp-1088h] BYREF

  pcbData[0] = 4168;
  v4 = 0;
  v5 = 15;
  if ( SHGetValueW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\LAN",
         L"ProxyServer",
         0,
         psz1,
         pcbData) )
  {
    goto LABEL_14;
  }
  if ( !word_180034AB0 )
  {
    v6 = 2147483646;
    v7 = psz1;
    v8 = 2084;
    v9 = &word_180034AB0;
    do
    {
      if ( !v6 )
        break;
      if ( !*v7 )
        break;
      *v9++ = *v7++;
      --v6;
      --v8;
    }
    while ( v8 );
    v10 = v9 - 1;
    if ( v8 )
      v10 = v9;
    *v10 = 0;
  }
  if ( !StrCmpW(psz1, &word_180034AB0) )
  {
LABEL_14:
    v14 = dword_180035AF8;
  }
  else
  {
    dword_180035AFC = 0;
    v11 = 0;
    do
    {
      v12 = (int)v11++;
      v13 = 516 * v12;
      *(_DWORD *)((char *)&qword_180032A20[64] + v13) = 0;
      *(_WORD *)((char *)qword_180032A20 + v13) = 0;
    }
    while ( v11 < 0xF );
    v14 = 1;
    dword_180035AF8 = 1;
  }
  *a2 = 0;
  if ( v14 )
  {
    memset_0(psz1, 0, 0x200u);
    FtpPidl_GetServer(a1, psz1, v18);
    for ( i = dword_180035AFC; *((_WORD *)qword_180032A20 + 258 * i); --i )
    {
      if ( i < 0 )
        i = 14;
      v20 = 516LL * (unsigned int)i;
      if ( !StrCmpW(psz1, (PCWSTR)((char *)qword_180032A20 + v20)) )
      {
        v4 = 1;
        *a2 = *(_DWORD *)((char *)&qword_180032A20[64] + v20);
        return v4;
      }
      if ( !--v5 )
        return v4;
    }
  }
  else
  {
    dword_180035AFC = 0;
    v15 = 0;
    do
    {
      v16 = (int)v15++;
      v17 = 516 * v16;
      *(_DWORD *)((char *)&qword_180032A20[64] + v17) = 0;
      *(_WORD *)((char *)qword_180032A20 + v17) = 0;
    }
    while ( v15 < 0xF );
    dword_180035AF8 = 1;
  }
  return v4;
}

```

## disassembly

```asm
0x180022bb0  mov     [rsp+arg_10], rbx
0x180022bb5  mov     [rsp+arg_18], rbp
0x180022bba  push    rsi
0x180022bbb  push    rdi
0x180022bbc  push    r13
0x180022bbe  push    r14
0x180022bc0  push    r15
0x180022bc2  mov     eax, 10A0h
0x180022bc7  call    _alloca_probe
0x180022bcc  sub     rsp, rax
0x180022bcf  mov     rax, cs:__security_cookie
0x180022bd6  xor     rax, rsp
0x180022bd9  mov     [rsp+10C8h+var_38], rax
0x180022be1  lea     rax, [rsp+10C8h+var_1098]
0x180022be6  mov     [rsp+10C8h+var_1098], 1048h
0x180022bee  mov     [rsp+10C8h+pcbData], rax; pcbData
0x180022bf3  lea     r8, aProxyserver; "ProxyServer"
0x180022bfa  lea     rax, [rsp+10C8h+psz1]
0x180022bff  mov     r14, rdx
0x180022c02  mov     rbx, rcx
0x180022c05  mov     [rsp+10C8h+pvData], rax; pvData
0x180022c0a  xor     r15d, r15d
0x180022c0d  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180022c14  xor     r9d, r9d; pdwType
0x180022c17  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180022c1e  mov     ebp, r15d
0x180022c21  call    cs:__imp_SHGetValueW
0x180022c27  lea     r13, qword_180032A20
0x180022c2e  lea     edi, [r15+0Fh]
0x180022c32  test    eax, eax
0x180022c34  jnz     loc_180022CD6
0x180022c3a  cmp     cs:word_180034AB0, r15w
0x180022c42  jnz     short loc_180022C8C
0x180022c44  mov     ecx, 7FFFFFFEh
0x180022c49  lea     r9, [rsp+10C8h+psz1]
0x180022c4e  mov     r8d, 824h
0x180022c54  lea     rax, word_180034AB0
0x180022c5b  test    rcx, rcx
0x180022c5e  jz      short loc_180022C7D
0x180022c60  movzx   edx, word ptr [r9]
0x180022c64  test    dx, dx
0x180022c67  jz      short loc_180022C7D
0x180022c69  mov     [rax], dx
0x180022c6c  add     r9, 2
0x180022c70  add     rax, 2
0x180022c74  dec     rcx
0x180022c77  sub     r8, 1
0x180022c7b  jnz     short loc_180022C5B
0x180022c7d  test    r8, r8
0x180022c80  lea     rcx, [rax-2]
0x180022c84  cmovnz  rcx, rax
0x180022c88  mov     [rcx], r15w
0x180022c8c  lea     rdx, word_180034AB0; psz2
0x180022c93  lea     rcx, [rsp+10C8h+psz1]; psz1
0x180022c98  call    cs:__imp_StrCmpW
0x180022c9e  test    eax, eax
0x180022ca0  jz      short loc_180022CD6
0x180022ca2  mov     cs:dword_180035AFC, r15d
0x180022ca9  mov     edx, r15d
0x180022cac  movsxd  rax, edx
0x180022caf  inc     edx
0x180022cb1  imul    rcx, rax, 204h
0x180022cb8  mov     [rcx+r13+200h], r15d
0x180022cc0  mov     [rcx+r13], r15w
0x180022cc5  cmp     edx, edi
0x180022cc7  jb      short loc_180022CAC
0x180022cc9  mov     eax, 1
0x180022cce  mov     cs:dword_180035AF8, eax
0x180022cd4  jmp     short loc_180022CDC
0x180022cd6  mov     eax, cs:dword_180035AF8
0x180022cdc  mov     [r14], r15d
0x180022cdf  test    eax, eax
0x180022ce1  jnz     short loc_180022D16
0x180022ce3  mov     cs:dword_180035AFC, r15d
0x180022cea  mov     edx, r15d
0x180022ced  movsxd  rax, edx
0x180022cf0  inc     edx
0x180022cf2  imul    rcx, rax, 204h
0x180022cf9  mov     [rcx+r13+200h], r15d
0x180022d01  mov     [rcx+r13], r15w
0x180022d06  cmp     edx, edi
0x180022d08  jb      short loc_180022CED
0x180022d0a  mov     cs:dword_180035AF8, 1
0x180022d14  jmp     short loc_180022D8B
0x180022d16  xor     edx, edx; Val
0x180022d18  lea     rcx, [rsp+10C8h+psz1]; void *
0x180022d1d  mov     r8d, 200h; Size
0x180022d23  call    memset_0
0x180022d28  lea     rdx, [rsp+10C8h+psz1]; unsigned __int16 *
0x180022d2d  mov     rcx, rbx; struct _ITEMIDLIST *
0x180022d30  call    ?FtpPidl_GetServer@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetServer(_ITEMIDLIST const *,ushort *,ulong)
0x180022d35  mov     ebx, cs:dword_180035AFC
0x180022d3b  movsxd  rax, ebx
0x180022d3e  imul    rcx, rax, 204h
0x180022d45  cmp     [rcx+r13], r15w
0x180022d4a  jz      short loc_180022D8B
0x180022d4c  mov     eax, 0Eh
0x180022d51  lea     rcx, [rsp+10C8h+psz1]; psz1
0x180022d56  test    ebx, ebx
0x180022d58  cmovs   ebx, eax
0x180022d5b  mov     eax, ebx
0x180022d5d  imul    rsi, rax, 204h
0x180022d64  lea     rdx, [rsi+r13]; psz2
0x180022d68  call    cs:__imp_StrCmpW
0x180022d6e  test    eax, eax
0x180022d70  jz      short loc_180022D7B
0x180022d72  dec     ebx
0x180022d74  sub     edi, 1
0x180022d77  jnz     short loc_180022D3B
0x180022d79  jmp     short loc_180022D8B
0x180022d7b  mov     eax, [rsi+r13+200h]
0x180022d83  mov     ebp, 1
0x180022d88  mov     [r14], eax
0x180022d8b  mov     eax, ebp
0x180022d8d  mov     rcx, [rsp+10C8h+var_38]
0x180022d95  xor     rcx, rsp; StackCookie
0x180022d98  call    __security_check_cookie
0x180022d9d  lea     r11, [rsp+10C8h+var_28]
0x180022da5  mov     rbx, [r11+40h]
0x180022da9  mov     rbp, [r11+48h]
0x180022dad  mov     rsp, r11
0x180022db0  pop     r15
0x180022db2  pop     r14
0x180022db4  pop     r13
0x180022db6  pop     rdi
0x180022db7  pop     rsi
0x180022db8  retn
```
