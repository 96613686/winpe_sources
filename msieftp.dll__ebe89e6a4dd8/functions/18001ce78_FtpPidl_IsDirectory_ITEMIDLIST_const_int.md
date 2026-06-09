# FtpPidl_IsDirectory(_ITEMIDLIST const *,int)

- ea: `0x18001ce78`
- end: `0x18001cedb`
- name: `?FtpPidl_IsDirectory@@YAHPEFBU_ITEMIDLIST@@H@Z`
- size: `99`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST *, int)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e710`
- `0x180011534`
- `0x180011ae8`
- `0x180017960`
- `0x180018dc0`
- `0x18001b1b8`
- `0x18001db50`
- `0x18001ea10`

## callees

- `0x18001bda4`
- `0x18001ce78`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x18001ce8b`
- `SHELL32!__imp_ILFindLastID` at `0x18001ce8b`

## pseudocode

```c
__int64 __fastcall FtpPidl_IsDirectory(const struct _ITEMIDLIST *a1, int a2)
{
  unsigned int v3; // ebx
  LPITEMIDLIST ID; // rdi

  v3 = 0;
  ID = ILFindLastID(a1);
  if ( !(unsigned int)FtpID_IsServerItemID(ID) && ID->mkid.cb >= 0x27u && (*(_DWORD *)&ID[2].mkid.cb & 0xFFFCFFC2) == 0 )
  {
    LOBYTE(v3) = (ID[2].mkid.cb & 5) == 5;
    if ( a2 )
    {
      if ( *(_DWORD *)&ID[2].mkid.cb == 17 )
        return 1;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18001ce78  mov     [rsp+arg_0], rbx
0x18001ce7d  mov     [rsp+arg_8], rsi
0x18001ce82  push    rdi
0x18001ce83  sub     rsp, 20h
0x18001ce87  mov     esi, edx
0x18001ce89  xor     ebx, ebx
0x18001ce8b  call    cs:__imp_ILFindLastID
0x18001ce91  mov     rcx, rax; struct _ITEMIDLIST *
0x18001ce94  mov     rdi, rax
0x18001ce97  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001ce9c  test    eax, eax
0x18001ce9e  jnz     short loc_18001CEC9
0x18001cea0  cmp     word ptr [rdi], 27h ; '''
0x18001cea4  jb      short loc_18001CEC9
0x18001cea6  test    dword ptr [rdi+6], 0FFFCFFC2h
0x18001cead  jnz     short loc_18001CEC9
0x18001ceaf  mov     eax, [rdi+6]
0x18001ceb2  and     eax, 5
0x18001ceb5  cmp     al, 5
0x18001ceb7  setz    bl
0x18001ceba  test    esi, esi
0x18001cebc  jz      short loc_18001CEC9
0x18001cebe  cmp     dword ptr [rdi+6], 11h
0x18001cec2  jnz     short loc_18001CEC9
0x18001cec4  mov     ebx, 1
0x18001cec9  mov     rsi, [rsp+28h+arg_8]
0x18001cece  mov     eax, ebx
0x18001ced0  mov     rbx, [rsp+28h+arg_0]
0x18001ced5  add     rsp, 20h
0x18001ced9  pop     rdi
0x18001ceda  retn
```
