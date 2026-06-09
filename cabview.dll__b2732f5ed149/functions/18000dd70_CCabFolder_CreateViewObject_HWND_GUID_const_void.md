# CCabFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x18000dd70`
- end: `0x18000de57`
- name: `?CreateViewObject@CCabFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `231`
- prototype: `int(CCabFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002620`
- `0x18000dd70`

## import_xrefs

- `SHELL32!__imp_SHCreateShellFolderView` at `0x18000de3c`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x18000de3c`
- `SHELL32!__imp_CDefFolderMenu_Create2` at `0x18000ddf1`
- `SHELL32!__imp_CDefFolderMenu_Create2` at `0x18000ddf1`

## pseudocode

```c
HRESULT __fastcall CCabFolder::CreateViewObject(
        unsigned __int64 this,
        HWND a2,
        const struct _GUID *a3,
        IContextMenu **ppcm)
{
  __int64 v4; // rax
  __int64 v5; // rax
  SFV_CREATE pcsfv; // [rsp+50h] [rbp-38h] BYREF

  v4 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellView.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1 )
    v4 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellView.Data4;
  if ( v4 )
  {
    v5 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
      v5 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
    if ( v5 )
    {
      *ppcm = 0;
      return -2147467262;
    }
    else
    {
      return CDefFolderMenu_Create2(
               *(LPCITEMIDLIST *)(this + 40),
               a2,
               0,
               0,
               (IShellFolder *)(this & -(__int64)(this != 8)),
               0,
               0,
               0,
               ppcm);
    }
  }
  else
  {
    *(_QWORD *)&pcsfv.cbSize = 32;
    pcsfv.psvOuter = 0;
    if ( this == 8 )
    {
      pcsfv.pshf = 0;
      pcsfv.psfvcb = 0;
    }
    else
    {
      pcsfv.pshf = (IShellFolder *)this;
      pcsfv.psfvcb = (IShellFolderViewCB *)(this + 8);
    }
    return SHCreateShellFolderView(&pcsfv, (IShellView **)ppcm);
  }
}

```

## disassembly

```asm
0x18000dd70  sub     rsp, 88h
0x18000dd77  mov     rax, cs:__security_cookie
0x18000dd7e  xor     rax, rsp
0x18000dd81  mov     [rsp+88h+var_18], rax
0x18000dd86  mov     rax, [r8]
0x18000dd89  sub     rax, qword ptr cs:IID_IShellView.Data1
0x18000dd90  jnz     short loc_18000DD9D
0x18000dd92  mov     rax, [r8+8]
0x18000dd96  sub     rax, qword ptr cs:IID_IShellView.Data4
0x18000dd9d  xor     r10d, r10d
0x18000dda0  test    rax, rax
0x18000dda3  jz      short loc_18000DE03
0x18000dda5  mov     rax, [r8]
0x18000dda8  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x18000ddaf  jnz     short loc_18000DDBC
0x18000ddb1  mov     rax, [r8+8]
0x18000ddb5  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x18000ddbc  test    rax, rax
0x18000ddbf  jnz     short loc_18000DDF9
0x18000ddc1  mov     [rsp+88h+ppcm], r9; ppcm
0x18000ddc6  lea     rax, [rcx-8]
0x18000ddca  mov     [rsp+88h+ahkeys], r10; ahkeys
0x18000ddcf  neg     rax
0x18000ddd2  mov     [rsp+88h+nKeys], r10d; nKeys
0x18000ddd7  sbb     r8, r8
0x18000ddda  mov     [rsp+88h+pfn], r10; pfn
0x18000dddf  and     r8, rcx
0x18000dde2  xor     r9d, r9d; apidl
0x18000dde5  mov     rcx, [rcx+28h]; pidlFolder
0x18000dde9  mov     [rsp+88h+psf], r8; psf
0x18000ddee  xor     r8d, r8d; cidl
0x18000ddf1  call    cs:__imp_CDefFolderMenu_Create2
0x18000ddf7  jmp     short loc_18000DE42
0x18000ddf9  mov     [r9], r10
0x18000ddfc  mov     eax, 80004002h
0x18000de01  jmp     short loc_18000DE42
0x18000de03  lea     rax, [rcx-8]
0x18000de07  mov     qword ptr [rsp+88h+pcsfv.cbSize], 20h ; ' '
0x18000de10  mov     [rsp+88h+pcsfv.psvOuter], r10
0x18000de15  test    rax, rax
0x18000de18  jz      short loc_18000DE2A
0x18000de1a  lea     rax, [rcx+8]
0x18000de1e  mov     [rsp+88h+pcsfv.pshf], rcx
0x18000de23  mov     [rsp+88h+pcsfv.psfvcb], rax
0x18000de28  jmp     short loc_18000DE34
0x18000de2a  mov     [rsp+88h+pcsfv.pshf], r10
0x18000de2f  mov     [rsp+88h+pcsfv.psfvcb], r10
0x18000de34  mov     rdx, r9; ppsv
0x18000de37  lea     rcx, [rsp+88h+pcsfv]; pcsfv
0x18000de3c  call    cs:__imp_SHCreateShellFolderView
0x18000de42  mov     rcx, [rsp+88h+var_18]
0x18000de47  xor     rcx, rsp; StackCookie
0x18000de4a  call    __security_check_cookie
0x18000de4f  add     rsp, 88h
0x18000de56  retn
```
