# CFtpEidl::_HandleSoftLinks(void *,_ITEMIDLIST *,char *,ulong)

- ea: `0x1800157fc`
- end: `0x1800158df`
- name: `?_HandleSoftLinks@CFtpEidl@@IEAAJPEAXPEFAU_ITEMIDLIST@@PEADK@Z`
- size: `227`
- prototype: `int(CFtpEidl *__hidden this, void *, struct _ITEMIDLIST *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800159c4`

## callees

- `0x18000cbfc`
- `0x18000cc64`
- `0x18000cca4`
- `0x18000cd98`
- `0x1800157fc`
- `0x18001c46c`
- `0x18001c4fc`
- `0x18001cee4`
- `0x18001cf40`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180015896`
- `SHELL32!__imp_ILFree` at `0x180015896`

## pseudocode

```c
__int64 __fastcall CFtpEidl::_HandleSoftLinks(CFtpEidl *this, void *a2, struct _ITEMIDLIST *a3, char *a4)
{
  unsigned int v8; // edi
  const struct _ITEMIDLIST *v9; // r14
  int v10; // edx
  LPITEMIDLIST pidl; // [rsp+20h] [rbp-38h] BYREF

  v8 = 0;
  if ( !FtpPidl_GetAttributes(a3) )
  {
    if ( !*a4 )
      FtpGetCurrentDirectoryWrap(a2, a4, 0x104u);
    if ( (int)FtpSetCurrentDirectoryPidlWrap(a2, a3, 0, 0) < 0 )
    {
      FtpPidl_SetAttributes(a3, 0x480u);
      v10 = 0;
    }
    else
    {
      v9 = *(const struct _ITEMIDLIST **)(*(_QWORD *)(*((_QWORD *)this + 6) + 16LL) + 104LL);
      if ( v9 )
      {
        pidl = 0;
        if ( (int)FtpGetCurrentDirectoryPidlWrap(a2, &pidl) >= 0 )
        {
          v8 = (unsigned int)FtpItemID_IsParent(v9, pidl) == 0 ? 0x800704C7 : 0;
          ILFree(pidl);
        }
      }
      FtpSetCurrentDirectoryWrap(a2, a4);
      FtpPidl_SetAttributes(a3, 0x410u);
      v10 = 1;
    }
    FtpPidl_SetFileItemType(a3, v10);
  }
  return v8;
}

```

## disassembly

```asm
0x1800157fc  push    rbx
0x1800157fe  push    rbp
0x1800157ff  push    rsi
0x180015800  push    rdi
0x180015801  push    r14
0x180015803  sub     rsp, 30h
0x180015807  mov     r14, rcx
0x18001580a  mov     rbp, r9
0x18001580d  mov     rcx, r8; struct _ITEMIDLIST *
0x180015810  mov     rbx, r8
0x180015813  mov     rsi, rdx
0x180015816  xor     edi, edi
0x180015818  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x18001581d  test    eax, eax
0x18001581f  jnz     loc_1800158D2
0x180015825  cmp     [rbp+0], dil
0x180015829  jnz     short loc_18001583C
0x18001582b  mov     r8d, 104h; unsigned int
0x180015831  mov     rdx, rbp; char *
0x180015834  mov     rcx, rsi; void *
0x180015837  call    ?FtpGetCurrentDirectoryWrap@@YAJPEAXPEADK@Z; FtpGetCurrentDirectoryWrap(void *,char *,ulong)
0x18001583c  xor     r9d, r9d; int
0x18001583f  xor     r8d, r8d; int
0x180015842  mov     rdx, rbx; struct _ITEMIDLIST *
0x180015845  mov     rcx, rsi; void *
0x180015848  call    ?FtpSetCurrentDirectoryPidlWrap@@YAJPEAXPEFBU_ITEMIDLIST@@HH@Z; FtpSetCurrentDirectoryPidlWrap(void *,_ITEMIDLIST const *,int,int)
0x18001584d  test    eax, eax
0x18001584f  js      short loc_1800158BB
0x180015851  mov     rax, [r14+30h]
0x180015855  mov     rcx, [rax+10h]
0x180015859  mov     r14, [rcx+68h]
0x18001585d  test    r14, r14
0x180015860  jz      short loc_18001589C
0x180015862  lea     rdx, [rsp+58h+pidl]; struct _ITEMIDLIST **
0x180015867  mov     [rsp+58h+pidl], rdi
0x18001586c  mov     rcx, rsi; void *
0x18001586f  call    ?FtpGetCurrentDirectoryPidlWrap@@YAJPEAXPEAPEFAU_ITEMIDLIST@@@Z; FtpGetCurrentDirectoryPidlWrap(void *,_ITEMIDLIST * *)
0x180015874  test    eax, eax
0x180015876  js      short loc_18001589C
0x180015878  mov     rdx, [rsp+58h+pidl]; struct _ITEMIDLIST *
0x18001587d  mov     rcx, r14; struct _ITEMIDLIST *
0x180015880  call    ?FtpItemID_IsParent@@YAHPEFBU_ITEMIDLIST@@0@Z; FtpItemID_IsParent(_ITEMIDLIST const *,_ITEMIDLIST const *)
0x180015885  mov     rcx, [rsp+58h+pidl]; pidl
0x18001588a  neg     eax
0x18001588c  sbb     edi, edi
0x18001588e  not     edi
0x180015890  and     edi, 800704C7h
0x180015896  call    cs:__imp_ILFree
0x18001589c  mov     rdx, rbp; char *
0x18001589f  mov     rcx, rsi; void *
0x1800158a2  call    ?FtpSetCurrentDirectoryWrap@@YAJPEAXPEBD@Z; FtpSetCurrentDirectoryWrap(void *,char const *)
0x1800158a7  mov     edx, 410h; unsigned int
0x1800158ac  mov     rcx, rbx; struct _ITEMIDLIST *
0x1800158af  call    ?FtpPidl_SetAttributes@@YAJPEFAU_ITEMIDLIST@@K@Z; FtpPidl_SetAttributes(_ITEMIDLIST *,ulong)
0x1800158b4  mov     edx, 1
0x1800158b9  jmp     short loc_1800158CA
0x1800158bb  mov     edx, 480h; unsigned int
0x1800158c0  mov     rcx, rbx; struct _ITEMIDLIST *
0x1800158c3  call    ?FtpPidl_SetAttributes@@YAJPEFAU_ITEMIDLIST@@K@Z; FtpPidl_SetAttributes(_ITEMIDLIST *,ulong)
0x1800158c8  xor     edx, edx; int
0x1800158ca  mov     rcx, rbx; struct _ITEMIDLIST *
0x1800158cd  call    ?FtpPidl_SetFileItemType@@YAJPEFAU_ITEMIDLIST@@H@Z; FtpPidl_SetFileItemType(_ITEMIDLIST *,int)
0x1800158d2  mov     eax, edi
0x1800158d4  add     rsp, 30h
0x1800158d8  pop     r14
0x1800158da  pop     rdi
0x1800158db  pop     rsi
0x1800158dc  pop     rbp
0x1800158dd  pop     rbx
0x1800158de  retn
```
