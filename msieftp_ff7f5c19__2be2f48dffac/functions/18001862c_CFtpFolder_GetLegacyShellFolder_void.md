# CFtpFolder::_GetLegacyShellFolder(void)

- ea: `0x18001862c`
- end: `0x180018763`
- name: `?_GetLegacyShellFolder@CFtpFolder@@IEAAPEAUIShellFolder@@XZ`
- size: `311`
- prototype: `struct IShellFolder *__fastcall(CFtpFolder *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800162d0`

## callees

- `0x180018568`
- `0x18001862c`
- `0x18001bda4`
- `0x18001cee4`
- `0x18001cf40`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x180018696`
- `SHELL32!__imp_ILFindLastID` at `0x180018696`
- `SHELL32!__imp_ILClone` at `0x180018677`
- `SHELL32!__imp_ILClone` at `0x180018677`
- `SHELL32!__imp_ILFree` at `0x180018745`
- `SHELL32!__imp_ILFree` at `0x18001874e`
- `SHELL32!__imp_ILFree` at `0x180018745`
- `SHELL32!__imp_ILFree` at `0x18001874e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018661`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018661`

## pseudocode

```c
struct IShellFolder *__fastcall CFtpFolder::_GetLegacyShellFolder(CFtpFolder *this)
{
  const ITEMIDLIST *v2; // rax
  ITEMIDLIST *v3; // rdi
  const struct _ITEMIDLIST *ID; // rax
  struct _ITEMIDLIST *v5; // rsi
  LPITEMIDLIST v6; // rbx
  int v7; // ebx
  LPVOID v8; // rcx
  LPVOID ppv; // [rsp+68h] [rbp+38h] BYREF
  __int64 v11; // [rsp+70h] [rbp+40h] BYREF
  LPITEMIDLIST pidl; // [rsp+78h] [rbp+48h] BYREF

  ppv = 0;
  if ( CoCreateInstance(&GUID_e7e4bc40_e76a_11ce_a9bb_00aa004ae837, 0, 1u, &IID_IShellFolder, &ppv) >= 0 )
  {
    v2 = ILClone((LPCITEMIDLIST)(*((_QWORD *)this + 6) + *((int *)this + 16)));
    v3 = (ITEMIDLIST *)v2;
    if ( v2 )
    {
      if ( v2->mkid.cb )
      {
        ID = ILFindLastID(v2);
        pidl = 0;
        v5 = (struct _ITEMIDLIST *)ID;
        if ( !(unsigned int)FtpID_IsServerItemID(ID) )
        {
          FtpPidl_SetFileItemType(v5, 0);
          FtpPidl_SetAttributes(v3, 0x80u);
        }
        if ( (int)CFtpFolder::_GetLegacyPidl(this, v3, &pidl) >= 0 )
        {
          v6 = pidl;
          v11 = 0;
          if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                 ppv,
                 &GUID_000214ea_0000_0000_c000_000000000046,
                 &v11) < 0
            || (v7 = (*(__int64 (__fastcall **)(__int64, LPITEMIDLIST))(*(_QWORD *)v11 + 32LL))(v11, v6),
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11),
                v7 < 0) )
          {
            v8 = ppv;
            ppv = 0;
            if ( v8 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
          }
          ILFree(pidl);
        }
        ILFree(v3);
      }
    }
  }
  return (struct IShellFolder *)ppv;
}

```

## disassembly

```asm
0x18001862c  push    rbp
0x18001862e  push    rbx
0x18001862f  push    rsi
0x180018630  push    rdi
0x180018631  push    r14
0x180018633  mov     rbp, rsp
0x180018636  sub     rsp, 30h
0x18001863a  xor     r14d, r14d
0x18001863d  lea     rax, [rbp+arg_8]
0x180018641  mov     rbx, rcx
0x180018644  mov     [rbp+arg_8], r14
0x180018648  lea     r9, IID_IShellFolder; riid
0x18001864f  mov     [rsp+30h+ppv], rax; ppv
0x180018654  xor     edx, edx; pUnkOuter
0x180018656  lea     rcx, _GUID_e7e4bc40_e76a_11ce_a9bb_00aa004ae837; rclsid
0x18001865d  lea     r8d, [r14+1]; dwClsContext
0x180018661  call    cs:__imp_CoCreateInstance
0x180018667  test    eax, eax
0x180018669  js      loc_180018754
0x18001866f  movsxd  rcx, dword ptr [rbx+40h]
0x180018673  add     rcx, [rbx+30h]; pidl
0x180018677  call    cs:__imp_ILClone
0x18001867d  mov     rdi, rax
0x180018680  test    rax, rax
0x180018683  jz      loc_180018754
0x180018689  cmp     [rax], r14w
0x18001868d  jz      loc_180018754
0x180018693  mov     rcx, rax; pidl
0x180018696  call    cs:__imp_ILFindLastID
0x18001869c  mov     rcx, rax; struct _ITEMIDLIST *
0x18001869f  mov     [rbp+pidl], r14
0x1800186a3  mov     rsi, rax
0x1800186a6  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x1800186ab  test    eax, eax
0x1800186ad  jnz     short loc_1800186C6
0x1800186af  xor     edx, edx; int
0x1800186b1  mov     rcx, rsi; struct _ITEMIDLIST *
0x1800186b4  call    ?FtpPidl_SetFileItemType@@YAJPEFAU_ITEMIDLIST@@H@Z; FtpPidl_SetFileItemType(_ITEMIDLIST *,int)
0x1800186b9  mov     edx, 80h; unsigned int
0x1800186be  mov     rcx, rdi; struct _ITEMIDLIST *
0x1800186c1  call    ?FtpPidl_SetAttributes@@YAJPEFAU_ITEMIDLIST@@K@Z; FtpPidl_SetAttributes(_ITEMIDLIST *,ulong)
0x1800186c6  lea     r8, [rbp+pidl]; struct _ITEMIDLIST **
0x1800186ca  mov     rdx, rdi; struct _ITEMIDLIST *
0x1800186cd  mov     rcx, rbx; this
0x1800186d0  call    ?_GetLegacyPidl@CFtpFolder@@IEAAJPEFBU_ITEMIDLIST@@PEAPEFAU2@@Z; CFtpFolder::_GetLegacyPidl(_ITEMIDLIST const *,_ITEMIDLIST * *)
0x1800186d5  test    eax, eax
0x1800186d7  js      short loc_18001874B
0x1800186d9  mov     rcx, [rbp+arg_8]
0x1800186dd  lea     r8, [rbp+arg_10]
0x1800186e1  mov     rbx, [rbp+pidl]
0x1800186e5  lea     rdx, _GUID_000214ea_0000_0000_c000_000000000046
0x1800186ec  mov     [rbp+arg_10], r14
0x1800186f0  mov     rax, [rcx]
0x1800186f3  mov     rax, [rax]
0x1800186f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186fb  test    eax, eax
0x1800186fd  js      short loc_180018728
0x1800186ff  mov     rcx, [rbp+arg_10]
0x180018703  mov     rdx, rbx
0x180018706  mov     rax, [rcx]
0x180018709  mov     rax, [rax+20h]
0x18001870d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018712  mov     rcx, [rbp+arg_10]
0x180018716  mov     ebx, eax
0x180018718  mov     rdx, [rcx]
0x18001871b  mov     rax, [rdx+10h]
0x18001871f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018724  test    ebx, ebx
0x180018726  jns     short loc_180018741
0x180018728  mov     rcx, [rbp+arg_8]
0x18001872c  mov     [rbp+arg_8], r14
0x180018730  test    rcx, rcx
0x180018733  jz      short loc_180018741
0x180018735  mov     rax, [rcx]
0x180018738  mov     rax, [rax+10h]
0x18001873c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018741  mov     rcx, [rbp+pidl]; pidl
0x180018745  call    cs:__imp_ILFree
0x18001874b  mov     rcx, rdi; pidl
0x18001874e  call    cs:__imp_ILFree
0x180018754  mov     rax, [rbp+arg_8]
0x180018758  add     rsp, 30h
0x18001875c  pop     r14
0x18001875e  pop     rdi
0x18001875f  pop     rsi
0x180018760  pop     rbx
0x180018761  pop     rbp
0x180018762  retn
```
