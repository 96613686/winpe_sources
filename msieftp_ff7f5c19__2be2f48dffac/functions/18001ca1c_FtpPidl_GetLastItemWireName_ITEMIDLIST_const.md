# FtpPidl_GetLastItemWireName(_ITEMIDLIST const *)

- ea: `0x18001ca1c`
- end: `0x18001cac7`
- name: `?FtpPidl_GetLastItemWireName@@YAPEBDPEFBU_ITEMIDLIST@@@Z`
- size: `171`
- prototype: `const char *__fastcall(const struct _ITEMIDLIST *)`
- caller_count: `10`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d920`
- `0x18000dc58`
- `0x18000e358`
- `0x180011920`
- `0x180017960`
- `0x1800182c4`
- `0x18001da30`
- `0x18001e2d4`
- `0x18001ea10`
- `0x180020efc`

## callees

- `0x18001bda4`
- `0x18001c410`
- `0x18001ca1c`
- `0x18001db50`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x18001ca35`
- `SHELL32!__imp_ILFindLastID` at `0x18001ca35`

## pseudocode

```c
const char *__fastcall FtpPidl_GetLastItemWireName(const struct _ITEMIDLIST *a1)
{
  const char *result; // rax
  LPITEMIDLIST ID; // rax
  const struct _ITEMIDLIST *i; // rbx
  const struct _ITEMIDLIST *v5; // rsi

  result = 0;
  if ( a1 )
  {
    ID = ILFindLastID(a1);
    i = ID;
    if ( ID->mkid.cb >= 0x27u
      && (*(_DWORD *)&ID[2].mkid.cb & 0xFFFCFFC2) == 0
      && (ID[2].mkid.cb & 0x21) != 1
      && ID != a1 )
    {
      v5 = ID;
      for ( i = a1;
            (unsigned int)_FtpItemID_CompareOneID(0, (const struct _ITEMIDLIST *)((char *)i + i->mkid.cb), v5, 0);
            i = (const struct _ITEMIDLIST *)((char *)i + i->mkid.cb) )
      {
        if ( !i->mkid.cb )
          return 0;
      }
    }
    if ( !(unsigned int)FtpID_IsServerItemID(i)
      && (i->mkid.cb < 0x27u || (*(_DWORD *)&i[2].mkid.cb & 0xFFFCFFC2) != 0 || (i[2].mkid.cb & 0x21) == 1) )
    {
      return FtpItemID_GetWireNameReferenceEx(i, 0);
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ca1c  push    rbx
0x18001ca1e  push    rbp
0x18001ca1f  push    rsi
0x18001ca20  push    rdi
0x18001ca21  sub     rsp, 28h
0x18001ca25  xor     ebp, ebp
0x18001ca27  mov     rdi, rcx
0x18001ca2a  mov     eax, ebp
0x18001ca2c  test    rcx, rcx
0x18001ca2f  jz      loc_18001CABE
0x18001ca35  call    cs:__imp_ILFindLastID
0x18001ca3b  mov     rbx, rax
0x18001ca3e  cmp     word ptr [rax], 27h ; '''
0x18001ca42  jb      short loc_18001CA8A
0x18001ca44  test    dword ptr [rax+6], 0FFFCFFC2h
0x18001ca4b  jnz     short loc_18001CA8A
0x18001ca4d  mov     eax, [rax+6]
0x18001ca50  and     eax, 21h
0x18001ca53  cmp     al, 1
0x18001ca55  jz      short loc_18001CA8A
0x18001ca57  cmp     rbx, rdi
0x18001ca5a  jz      short loc_18001CA8A
0x18001ca5c  mov     rsi, rbx
0x18001ca5f  mov     rbx, rdi
0x18001ca62  movzx   edx, word ptr [rbx]
0x18001ca65  xor     r9d, r9d; unsigned int
0x18001ca68  add     rdx, rbx; struct _ITEMIDLIST *
0x18001ca6b  mov     r8, rsi; struct _ITEMIDLIST *
0x18001ca6e  xor     ecx, ecx; __int64
0x18001ca70  call    ?_FtpItemID_CompareOneID@@YAJ_JPEFBU_ITEMIDLIST@@1K@Z; _FtpItemID_CompareOneID(__int64,_ITEMIDLIST const *,_ITEMIDLIST const *,ulong)
0x18001ca75  test    eax, eax
0x18001ca77  jz      short loc_18001CA8A
0x18001ca79  cmp     [rbx], bp
0x18001ca7c  jz      short loc_18001CA86
0x18001ca7e  movzx   eax, word ptr [rbx]
0x18001ca81  add     rbx, rax
0x18001ca84  jmp     short loc_18001CA62
0x18001ca86  xor     eax, eax
0x18001ca88  jmp     short loc_18001CABE
0x18001ca8a  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001ca8d  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001ca92  test    eax, eax
0x18001ca94  jnz     short loc_18001CABB
0x18001ca96  cmp     word ptr [rbx], 27h ; '''
0x18001ca9a  jb      short loc_18001CAAF
0x18001ca9c  test    dword ptr [rbx+6], 0FFFCFFC2h
0x18001caa3  jnz     short loc_18001CAAF
0x18001caa5  mov     eax, [rbx+6]
0x18001caa8  and     eax, 21h
0x18001caab  cmp     al, 1
0x18001caad  jnz     short loc_18001CABB
0x18001caaf  xor     edx, edx; unsigned int
0x18001cab1  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001cab4  call    ?FtpItemID_GetWireNameReferenceEx@@YAPEBDPEFBU_ITEMIDLIST@@K@Z; FtpItemID_GetWireNameReferenceEx(_ITEMIDLIST const *,ulong)
0x18001cab9  jmp     short loc_18001CABE
0x18001cabb  mov     rax, rbp
0x18001cabe  add     rsp, 28h
0x18001cac2  pop     rdi
0x18001cac3  pop     rsi
0x18001cac4  pop     rbp
0x18001cac5  pop     rbx
0x18001cac6  retn
```
