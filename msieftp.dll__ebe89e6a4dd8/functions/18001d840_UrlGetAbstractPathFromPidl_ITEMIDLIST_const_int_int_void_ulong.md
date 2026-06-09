# UrlGetAbstractPathFromPidl(_ITEMIDLIST const *,int,int,void *,ulong)

- ea: `0x18001d840`
- end: `0x18001da28`
- name: `?UrlGetAbstractPathFromPidl@@YAJPEFBU_ITEMIDLIST@@HHPEAXK@Z`
- size: `488`
- prototype: `__int64 __usercall@<rax>(const struct _ITEMIDLIST *@<rcx>, int@<edx>, int@<r8d>, void *@<r9>, unsigned int)`
- caller_count: `8`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000cca4`
- `0x18000dc58`
- `0x18001357c`
- `0x180013f20`
- `0x1800142a0`
- `0x18001d4c0`
- `0x180020a4c`
- `0x1800254f0`

## callees

- `0x180002240`
- `0x18000d098`
- `0x18001bda4`
- `0x18001c330`
- `0x18001c410`
- `0x18001d840`
- `0x180021538`
- `0x1800215a0`
- `0x180021a48`

## import_xrefs

- `USER32!CharNextA` at `0x18001d967`
- `USER32!CharNextA` at `0x18001d967`

## pseudocode

```c
__int64 __fastcall UrlGetAbstractPathFromPidl(const struct _ITEMIDLIST *a1, int a2, int a3, char *a4, unsigned int a5)
{
  const struct _ITEMIDLIST *v8; // rdi
  const struct _ITEMIDLIST *v10; // rbx
  _WORD *v11; // rcx
  const CHAR *WireNameReference; // rsi
  unsigned __int16 v13[264]; // [rsp+30h] [rbp-248h] BYREF

  v8 = a1;
  if ( a1 && a1 != (const struct _ITEMIDLIST *)-2LL )
  {
    if ( a5 < 2 )
      return 2147942522LL;
    if ( a3 )
      *(_WORD *)a4 = 47;
    else
      *(_DWORD *)a4 = 47;
    if ( a1->mkid.cb && (unsigned int)FtpID_IsServerItemID(a1) )
      goto LABEL_39;
    while ( 1 )
    {
      if ( !v8->mkid.cb )
        return 0;
      if ( a2 )
      {
        v10 = v8 + 2;
        if ( v8->mkid.cb >= 0x27u && (*(_DWORD *)&v10->mkid.cb & 0xFFFCFFC2) == 0 )
        {
          if ( *(_DWORD *)&v10->mkid.cb == 17 )
          {
            v10 = v8 + 2;
LABEL_22:
            if ( v10 && (v10->mkid.cb & 0x21) != 1 )
              goto LABEL_32;
            goto LABEL_24;
          }
          if ( (*(_DWORD *)&v10->mkid.cb & 5) == 5 )
            goto LABEL_21;
        }
        v11 = (USHORT *)((char *)&v8->mkid.cb + v8->mkid.cb);
        if ( !v11 || !*v11 )
          goto LABEL_32;
      }
      if ( v8->mkid.cb < 0x27u )
      {
        v10 = v8 + 2;
        goto LABEL_24;
      }
LABEL_21:
      v10 = v8 + 2;
      if ( (*(_DWORD *)&v8[2].mkid.cb & 0xFFFCFFC2) == 0 )
        goto LABEL_22;
LABEL_24:
      if ( a3 )
      {
        WireNameReference = FtpItemID_GetWireNameReferenceEx(v8, 0);
        if ( WireNameReference )
        {
          WirePathAppendSlash(a4, a5);
          if ( *WireNameReference == 47 )
            WireNameReference = CharNextA(WireNameReference);
          StringCchCatA(a4, a5, WireNameReference);
        }
      }
      else if ( FtpItemID_GetDisplayName(v8, v13, 0x104u) >= 0 )
      {
        DisplayPathAppend((unsigned __int16 *)a4, a5, v13);
      }
LABEL_32:
      if ( v8->mkid.cb >= 0x27u
        && (*(_DWORD *)&v10->mkid.cb & 0xFFFCFFC2) == 0
        && ((v10->mkid.cb & 5) == 5 || (v10[9].mkid.cb & 0x100) != 0) )
      {
        if ( a3 )
          WirePathAppendSlash(a4, a5);
        else
          DisplayPathAppendSlash((unsigned __int16 *)a4, a5);
      }
LABEL_39:
      v8 = (const struct _ITEMIDLIST *)((char *)v8 + v8->mkid.cb);
      if ( !v8 )
        return 0;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001d840  mov     [rsp+arg_8], rbx
0x18001d845  mov     [rsp+arg_10], rsi
0x18001d84a  push    rdi
0x18001d84b  push    r12
0x18001d84d  push    r13
0x18001d84f  push    r14
0x18001d851  push    r15
0x18001d853  sub     rsp, 250h
0x18001d85a  mov     rax, cs:__security_cookie
0x18001d861  xor     rax, rsp
0x18001d864  mov     [rsp+278h+var_38], rax
0x18001d86c  xor     esi, esi
0x18001d86e  mov     r14, r9
0x18001d871  mov     r12d, r8d
0x18001d874  mov     r13d, edx
0x18001d877  mov     rdi, rcx
0x18001d87a  test    rcx, rcx
0x18001d87d  jz      loc_18001D9F6
0x18001d883  lea     rax, [rcx+2]
0x18001d887  test    rax, rax
0x18001d88a  jz      loc_18001D9F6
0x18001d890  cmp     [rsp+278h+arg_20], 2
0x18001d898  jnb     short loc_18001D8A4
0x18001d89a  mov     eax, 8007007Ah
0x18001d89f  jmp     loc_18001D9FB
0x18001d8a4  mov     r15d, 2Fh ; '/'
0x18001d8aa  test    r12d, r12d
0x18001d8ad  jz      short loc_18001D8B5
0x18001d8af  mov     [r9], r15w
0x18001d8b3  jmp     short loc_18001D8B8
0x18001d8b5  mov     [r9], r15d
0x18001d8b8  cmp     [rcx], si
0x18001d8bb  jz      short loc_18001D8CA
0x18001d8bd  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001d8c2  test    eax, eax
0x18001d8c4  jnz     loc_18001D9E6
0x18001d8ca  cmp     [rdi], si
0x18001d8cd  jz      loc_18001D9F2
0x18001d8d3  test    r13d, r13d
0x18001d8d6  jz      short loc_18001D913
0x18001d8d8  cmp     word ptr [rdi], 27h ; '''
0x18001d8dc  lea     rbx, [rdi+6]
0x18001d8e0  jb      short loc_18001D8FE
0x18001d8e2  test    dword ptr [rbx], 0FFFCFFC2h
0x18001d8e8  jnz     short loc_18001D8FE
0x18001d8ea  mov     eax, [rbx]
0x18001d8ec  cmp     eax, 11h
0x18001d8ef  jnz     short loc_18001D8F7
0x18001d8f1  lea     rbx, [rdi+6]
0x18001d8f5  jmp     short loc_18001D92B
0x18001d8f7  and     eax, 5
0x18001d8fa  cmp     al, 5
0x18001d8fc  jz      short loc_18001D91F
0x18001d8fe  movzx   ecx, word ptr [rdi]
0x18001d901  add     rcx, rdi
0x18001d904  jz      loc_18001D9AE
0x18001d90a  cmp     [rcx], si
0x18001d90d  jz      loc_18001D9AE
0x18001d913  cmp     word ptr [rdi], 27h ; '''
0x18001d917  jnb     short loc_18001D91F
0x18001d919  lea     rbx, [rdi+6]
0x18001d91d  jmp     short loc_18001D939
0x18001d91f  lea     rbx, [rdi+6]
0x18001d923  test    dword ptr [rbx], 0FFFCFFC2h
0x18001d929  jnz     short loc_18001D939
0x18001d92b  test    rbx, rbx
0x18001d92e  jz      short loc_18001D939
0x18001d930  mov     eax, [rbx]
0x18001d932  and     eax, 21h
0x18001d935  cmp     al, 1
0x18001d937  jnz     short loc_18001D9AE
0x18001d939  mov     rcx, rdi; struct _ITEMIDLIST *
0x18001d93c  test    r12d, r12d
0x18001d93f  jz      short loc_18001D986
0x18001d941  xor     edx, edx; unsigned int
0x18001d943  call    ?FtpItemID_GetWireNameReferenceEx@@YAPEBDPEFBU_ITEMIDLIST@@K@Z; FtpItemID_GetWireNameReferenceEx(_ITEMIDLIST const *,ulong)
0x18001d948  mov     rsi, rax
0x18001d94b  test    rax, rax
0x18001d94e  jz      short loc_18001D982
0x18001d950  mov     edx, [rsp+278h+arg_20]; unsigned int
0x18001d957  mov     rcx, r14; char *
0x18001d95a  call    ?WirePathAppendSlash@@YAJPEADK@Z; WirePathAppendSlash(char *,ulong)
0x18001d95f  cmp     [rsi], r15b
0x18001d962  jnz     short loc_18001D970
0x18001d964  mov     rcx, rsi; lpsz
0x18001d967  call    cs:__imp_CharNextA
0x18001d96d  mov     rsi, rax
0x18001d970  mov     edx, [rsp+278h+arg_20]; unsigned __int64
0x18001d977  mov     r8, rsi; char *
0x18001d97a  mov     rcx, r14; char *
0x18001d97d  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18001d982  xor     esi, esi
0x18001d984  jmp     short loc_18001D9AE
0x18001d986  mov     r8d, 104h; unsigned int
0x18001d98c  lea     rdx, [rsp+278h+var_248]; unsigned __int16 *
0x18001d991  call    ?FtpItemID_GetDisplayName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpItemID_GetDisplayName(_ITEMIDLIST const *,ushort *,ulong)
0x18001d996  test    eax, eax
0x18001d998  js      short loc_18001D9AE
0x18001d99a  mov     edx, [rsp+278h+arg_20]; unsigned int
0x18001d9a1  lea     r8, [rsp+278h+var_248]; unsigned __int16 *
0x18001d9a6  mov     rcx, r14; unsigned __int16 *
0x18001d9a9  call    ?DisplayPathAppend@@YAJPEAGKPEBG@Z; DisplayPathAppend(ushort *,ulong,ushort const *)
0x18001d9ae  cmp     word ptr [rdi], 27h ; '''
0x18001d9b2  jb      short loc_18001D9E6
0x18001d9b4  test    dword ptr [rbx], 0FFFCFFC2h
0x18001d9ba  jnz     short loc_18001D9E6
0x18001d9bc  mov     eax, [rbx]
0x18001d9be  and     eax, 5
0x18001d9c1  cmp     al, 5
0x18001d9c3  jz      short loc_18001D9CB
0x18001d9c5  test    byte ptr [rbx+1Ch], 1
0x18001d9c9  jz      short loc_18001D9E6
0x18001d9cb  mov     edx, [rsp+278h+arg_20]; unsigned int
0x18001d9d2  mov     rcx, r14; unsigned __int16 *
0x18001d9d5  test    r12d, r12d
0x18001d9d8  jz      short loc_18001D9E1
0x18001d9da  call    ?WirePathAppendSlash@@YAJPEADK@Z; WirePathAppendSlash(char *,ulong)
0x18001d9df  jmp     short loc_18001D9E6
0x18001d9e1  call    ?DisplayPathAppendSlash@@YAJPEAGK@Z; DisplayPathAppendSlash(ushort *,ulong)
0x18001d9e6  movzx   eax, word ptr [rdi]
0x18001d9e9  add     rdi, rax
0x18001d9ec  jnz     loc_18001D8CA
0x18001d9f2  xor     eax, eax
0x18001d9f4  jmp     short loc_18001D9FB
0x18001d9f6  mov     eax, 80070057h
0x18001d9fb  mov     rcx, [rsp+278h+var_38]
0x18001da03  xor     rcx, rsp; StackCookie
0x18001da06  call    __security_check_cookie
0x18001da0b  lea     r11, [rsp+278h+var_28]
0x18001da13  mov     rbx, [r11+38h]
0x18001da17  mov     rsi, [r11+40h]
0x18001da1b  mov     rsp, r11
0x18001da1e  pop     r15
0x18001da20  pop     r14
0x18001da22  pop     r13
0x18001da24  pop     r12
0x18001da26  pop     rdi
0x18001da27  retn
```
