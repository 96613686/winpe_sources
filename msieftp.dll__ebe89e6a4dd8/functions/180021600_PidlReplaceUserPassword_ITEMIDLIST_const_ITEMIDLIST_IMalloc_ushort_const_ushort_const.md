# PidlReplaceUserPassword(_ITEMIDLIST const *,_ITEMIDLIST * *,IMalloc *,ushort const *,ushort const *)

- ea: `0x180021600`
- end: `0x18002170d`
- name: `?PidlReplaceUserPassword@@YAJPEFBU_ITEMIDLIST@@PEAPEFAU1@PEAUIMalloc@@PEBG3@Z`
- size: `269`
- prototype: `__int64 __usercall@<rax>(const struct _ITEMIDLIST *@<rcx>, struct _ITEMIDLIST **@<rdx>, struct IMalloc *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001fdb0`
- `0x180024be8`

## callees

- `0x180002240`
- `0x18001cbd8`
- `0x18001cc1c`
- `0x18001d028`
- `0x18001d240`
- `0x18001d32c`
- `0x180021600`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x1800216d7`
- `SHELL32!__imp_ILCombine` at `0x1800216d7`
- `SHELL32!__imp_ILFree` at `0x1800216e5`
- `SHELL32!__imp_ILFree` at `0x1800216e5`

## pseudocode

```c
__int64 __fastcall PidlReplaceUserPassword(
        struct _ITEMIDLIST *a1,
        struct _ITEMIDLIST **a2,
        struct IMalloc *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  int Server; // edi
  unsigned __int16 v10; // di
  struct tagFTPSERVERIDLIST *DataThunk; // rax
  unsigned int TypeID; // eax
  struct _ITEMIDLIST *v13; // rax
  ITEMIDLIST *v14; // rcx
  LPCITEMIDLIST pidl1; // [rsp+40h] [rbp-358h] BYREF
  unsigned __int16 v17[128]; // [rsp+50h] [rbp-348h] BYREF
  WCHAR pwszSrc[256]; // [rsp+150h] [rbp-248h] BYREF

  Server = FtpPidl_GetServer(a1, pwszSrc, (unsigned int)a3);
  if ( !a4 )
  {
    a4 = v17;
    FtpPidl_GetUserName(a1, v17, 0x80u);
  }
  *a2 = 0;
  if ( Server >= 0 )
  {
    pidl1 = 0;
    v10 = 21;
    DataThunk = FtpServerID_GetDataThunk(a1);
    if ( DataThunk )
      v10 = *((_WORD *)DataThunk + 16);
    TypeID = FtpServerID_GetTypeID(a1);
    Server = FtpServerID_Create(pwszSrc, a4, a5, TypeID, v10, (struct _ITEMIDLIST **)&pidl1, a3, 1);
    if ( Server >= 0 )
    {
      v13 = ILCombine(pidl1, (struct _ITEMIDLIST *)((char *)a1 + a1->mkid.cb));
      v14 = (ITEMIDLIST *)pidl1;
      *a2 = v13;
      ILFree(v14);
    }
  }
  return (unsigned int)Server;
}

```

## disassembly

```asm
0x180021600  push    rbx
0x180021602  push    rbp
0x180021603  push    rsi
0x180021604  push    rdi
0x180021605  push    r14
0x180021607  push    r15
0x180021609  sub     rsp, 368h
0x180021610  mov     rax, cs:__security_cookie
0x180021617  xor     rax, rsp
0x18002161a  mov     [rsp+398h+var_48], rax
0x180021622  mov     r15, [rsp+398h+arg_20]
0x18002162a  mov     rsi, rdx
0x18002162d  lea     rdx, [rsp+398h+pwszSrc]; unsigned __int16 *
0x180021635  mov     rbp, r9
0x180021638  mov     r14, r8
0x18002163b  mov     rbx, rcx
0x18002163e  call    ?FtpPidl_GetServer@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetServer(_ITEMIDLIST const *,ushort *,ulong)
0x180021643  mov     edi, eax
0x180021645  test    rbp, rbp
0x180021648  jnz     short loc_180021662
0x18002164a  mov     r8d, 80h; unsigned int
0x180021650  lea     rdx, [rsp+398h+var_348]; unsigned __int16 *
0x180021655  mov     rcx, rbx; struct _ITEMIDLIST *
0x180021658  lea     rbp, [rsp+398h+var_348]
0x18002165d  call    ?FtpPidl_GetUserName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetUserName(_ITEMIDLIST const *,ushort *,ulong)
0x180021662  mov     qword ptr [rsi], 0
0x180021669  test    edi, edi
0x18002166b  js      short loc_1800216EB
0x18002166d  mov     rcx, rbx; struct _ITEMIDLIST *
0x180021670  mov     [rsp+398h+pidl1], 0
0x180021679  mov     edi, 15h
0x18002167e  call    ?FtpServerID_GetDataThunk@@YAPEFAUtagFTPSERVERIDLIST@@PEFAU_ITEMIDLIST@@@Z; FtpServerID_GetDataThunk(_ITEMIDLIST *)
0x180021683  test    rax, rax
0x180021686  jz      short loc_18002168C
0x180021688  movzx   edi, word ptr [rax+20h]
0x18002168c  mov     rcx, rbx; struct _ITEMIDLIST *
0x18002168f  call    ?FtpServerID_GetTypeID@@YAKPEFBU_ITEMIDLIST@@@Z; FtpServerID_GetTypeID(_ITEMIDLIST const *)
0x180021694  mov     [rsp+398h+var_360], 1; int
0x18002169c  lea     rcx, [rsp+398h+pidl1]
0x1800216a1  mov     [rsp+398h+var_368], r14; struct IMalloc *
0x1800216a6  mov     r9d, eax; unsigned int
0x1800216a9  mov     [rsp+398h+cchBuf], rcx; cchBuf
0x1800216ae  mov     r8, r15; unsigned __int16 *
0x1800216b1  lea     rcx, [rsp+398h+pwszSrc]; pwszSrc
0x1800216b9  mov     [rsp+398h+var_378], di; unsigned __int16
0x1800216be  mov     rdx, rbp; PCWSTR
0x1800216c1  call    ?FtpServerID_Create@@YAJPEBG00KGPEAPEFAU_ITEMIDLIST@@PEAUIMalloc@@H@Z; FtpServerID_Create(ushort const *,ushort const *,ushort const *,ulong,ushort,_ITEMIDLIST * *,IMalloc *,int)
0x1800216c6  mov     edi, eax
0x1800216c8  test    eax, eax
0x1800216ca  js      short loc_1800216EB
0x1800216cc  movzx   edx, word ptr [rbx]
0x1800216cf  mov     rcx, [rsp+398h+pidl1]; pidl1
0x1800216d4  add     rdx, rbx; pidl2
0x1800216d7  call    cs:__imp_ILCombine
0x1800216dd  mov     rcx, [rsp+398h+pidl1]; pidl
0x1800216e2  mov     [rsi], rax
0x1800216e5  call    cs:__imp_ILFree
0x1800216eb  mov     eax, edi
0x1800216ed  mov     rcx, [rsp+398h+var_48]
0x1800216f5  xor     rcx, rsp; StackCookie
0x1800216f8  call    __security_check_cookie
0x1800216fd  add     rsp, 368h
0x180021704  pop     r15
0x180021706  pop     r14
0x180021708  pop     rdi
0x180021709  pop     rsi
0x18002170a  pop     rbp
0x18002170b  pop     rbx
0x18002170c  retn
```
