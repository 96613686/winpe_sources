# CFtpSite_Create(_ITEMIDLIST const *,ushort const *,IMalloc *,CFtpSite * *)

- ea: `0x18001f418`
- end: `0x18001f693`
- name: `?CFtpSite_Create@@YAJPEFBU_ITEMIDLIST@@PEBGPEAUIMalloc@@PEAPEAVCFtpSite@@@Z`
- size: `635`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST *, LPCWSTR psz, IUnknown *punk, struct CFtpSite **)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18001ff7c`

## callees

- `0x180002240`
- `0x18001965c`
- `0x18001c870`
- `0x18001cad0`
- `0x18001cbd8`
- `0x18001cc1c`
- `0x18001d240`
- `0x18001d32c`
- `0x18001f418`
- `0x180023adc`
- `0x180026f48`
- `0x180026ff0`
- `0x180028010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_Set` at `0x18001f4f1`
- `SHLWAPI!__imp_IUnknown_Set` at `0x18001f4f1`

## pseudocode

```c
__int64 __fastcall CFtpSite_Create(struct _ITEMIDLIST *a1, LPCWSTR psz, IUnknown *punk, struct CFtpSite **a4)
{
  struct CFtpSite *v8; // rbx
  int v9; // ebp
  int v10; // ecx
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  __int16 v14; // di
  struct tagFTPSERVERIDLIST *DataThunk; // rax
  int v16; // edi
  __int16 TypeID; // ax
  WCHAR v19[128]; // [rsp+20h] [rbp-548h] BYREF
  WCHAR v20[128]; // [rsp+120h] [rbp-448h] BYREF
  WCHAR v21[128]; // [rsp+220h] [rbp-348h] BYREF
  WCHAR psza[256]; // [rsp+320h] [rbp-248h] BYREF

  v8 = (struct CFtpSite *)operator new(0xC8u);
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 1;
    *(_QWORD *)v8 = &CFtpSite::`vftable';
    _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
    *((_QWORD *)v8 + 17) = 0;
    *((_QWORD *)v8 + 18) = 0;
    *((_QWORD *)v8 + 19) = 0;
    *((_BYTE *)v8 + 176) = 0;
    _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
    *((_QWORD *)v8 + 4) = 0;
    *((_QWORD *)v8 + 5) = 0;
    *((_QWORD *)v8 + 6) = 0;
    *((_QWORD *)v8 + 7) = 0;
    *((_QWORD *)v8 + 8) = 0;
    *((_QWORD *)v8 + 9) = 0;
    *((_QWORD *)v8 + 10) = 0;
    *((_QWORD *)v8 + 11) = 0;
    *((_QWORD *)v8 + 12) = 0;
    *((_QWORD *)v8 + 13) = 0;
    *((_QWORD *)v8 + 14) = 0;
    *((_QWORD *)v8 + 15) = 0;
  }
  else
  {
    v8 = 0;
  }
  *a4 = 0;
  v9 = -2147024882;
  if ( v8 )
  {
    Str_SetPtrW((LPWSTR *)v8 + 15, psz);
    IUnknown_Set((IUnknown **)v8 + 7, punk);
    v9 = CFtpList_Create(v10, 0, 0xAu, (struct CFtpList **)v8 + 5);
    if ( v9 < 0 )
    {
      v9 = -2147467259;
      (*(void (__fastcall **)(struct CFtpSite *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    else
    {
      if ( !a1 || a1 == (struct _ITEMIDLIST *)-2LL )
      {
        Str_SetPtrW((LPWSTR *)v8 + 8, 0);
        Str_SetPtrW((LPWSTR *)v8 + 10, 0);
        Str_SetPtrW((LPWSTR *)v8 + 11, 0);
        Str_SetPtrW((LPWSTR *)v8 + 12, 0);
        Pidl_Set((char *)v8 + 72, 0);
        v16 = 0;
      }
      else
      {
        FtpPidl_GetServer(a1, psza, v11);
        Str_SetPtrW((LPWSTR *)v8 + 8, psza);
        Str_SetPtrW((LPWSTR *)v8 + 17, psza);
        Pidl_Set((char *)v8 + 72, a1);
        FtpPidl_GetUserName(a1, v20, 0x80u);
        Str_SetPtrW((LPWSTR *)v8 + 10, v20);
        if ( FtpPidl_GetPassword(a1, v19, v12, 1) < 0 )
          v19[0] = 0;
        Str_SetPtrW((LPWSTR *)v8 + 11, v19);
        FtpPidl_GetFragment(a1, v21, v13);
        Str_SetPtrW((LPWSTR *)v8 + 12, v21);
        v14 = 21;
        DataThunk = FtpServerID_GetDataThunk(a1);
        if ( DataThunk )
          v14 = *((_WORD *)DataThunk + 16);
        *((_WORD *)v8 + 64) = v14;
        v16 = 0;
        TypeID = FtpServerID_GetTypeID(a1);
        if ( (TypeID & 0x800) != 0 )
          v16 = 2 - ((TypeID & 0x1000) != 0);
      }
      *((_DWORD *)v8 + 33) = v16;
      *a4 = v8;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001f418  push    rbx
0x18001f41a  push    rbp
0x18001f41b  push    rsi
0x18001f41c  push    rdi
0x18001f41d  push    r12
0x18001f41f  push    r14
0x18001f421  push    r15
0x18001f423  sub     rsp, 530h
0x18001f42a  mov     rax, cs:__security_cookie
0x18001f431  xor     rax, rsp
0x18001f434  mov     [rsp+568h+var_48], rax
0x18001f43c  mov     rsi, rcx
0x18001f43f  mov     r14, r9
0x18001f442  mov     ecx, 0C8h; unsigned __int64
0x18001f447  mov     r15, r8
0x18001f44a  mov     rdi, rdx
0x18001f44d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f452  xor     r12d, r12d
0x18001f455  mov     rbx, rax
0x18001f458  test    rax, rax
0x18001f45b  jz      short loc_18001F4CA
0x18001f45d  lea     rax, ??_7CFtpSite@@6B@; const CFtpSite::`vftable'
0x18001f464  mov     dword ptr [rbx+8], 1
0x18001f46b  mov     [rbx], rax
0x18001f46e  lock inc cs:?g_cRef@@3KA; ulong g_cRef
0x18001f475  mov     [rbx+88h], r12
0x18001f47c  mov     [rbx+90h], r12
0x18001f483  mov     [rbx+98h], r12
0x18001f48a  mov     [rbx+0B0h], r12b
0x18001f491  lock inc cs:?g_cRef@@3KA; ulong g_cRef
0x18001f498  mov     [rbx+20h], r12
0x18001f49c  mov     [rbx+28h], r12
0x18001f4a0  mov     [rbx+30h], r12
0x18001f4a4  mov     [rbx+38h], r12
0x18001f4a8  mov     [rbx+40h], r12
0x18001f4ac  mov     [rbx+48h], r12
0x18001f4b0  mov     [rbx+50h], r12
0x18001f4b4  mov     [rbx+58h], r12
0x18001f4b8  mov     [rbx+60h], r12
0x18001f4bc  mov     [rbx+68h], r12
0x18001f4c0  mov     [rbx+70h], r12
0x18001f4c4  mov     [rbx+78h], r12
0x18001f4c8  jmp     short loc_18001F4CD
0x18001f4ca  mov     rbx, r12
0x18001f4cd  mov     [r14], r12
0x18001f4d0  mov     ebp, 8007000Eh
0x18001f4d5  test    rbx, rbx
0x18001f4d8  jz      loc_18001F66F
0x18001f4de  lea     rcx, [rbx+78h]; ppsz
0x18001f4e2  mov     rdx, rdi; psz
0x18001f4e5  call    Str_SetPtrW
0x18001f4ea  lea     rcx, [rbx+38h]; ppunk
0x18001f4ee  mov     rdx, r15; punk
0x18001f4f1  call    cs:__imp_IUnknown_Set
0x18001f4f7  xor     edx, edx; int (*)(void *, void *)
0x18001f4f9  lea     r9, [rbx+28h]; struct CFtpList **
0x18001f4fd  lea     r8d, [rdx+0Ah]; unsigned int
0x18001f501  call    ?CFtpList_Create@@YAJHP6AHPEAX0@ZIPEAPEAVCFtpList@@@Z; CFtpList_Create(int,int (*)(void *,void *),uint,CFtpList * *)
0x18001f506  mov     ebp, eax
0x18001f508  test    eax, eax
0x18001f50a  js      loc_18001F65B
0x18001f510  test    rsi, rsi
0x18001f513  jz      loc_18001F616
0x18001f519  lea     rcx, [rsi+2]
0x18001f51d  test    rcx, rcx
0x18001f520  jz      loc_18001F616
0x18001f526  lea     rdx, [rsp+568h+psz]; unsigned __int16 *
0x18001f52e  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001f531  call    ?FtpPidl_GetServer@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetServer(_ITEMIDLIST const *,ushort *,ulong)
0x18001f536  lea     rcx, [rbx+40h]; ppsz
0x18001f53a  lea     rdx, [rsp+568h+psz]; psz
0x18001f542  call    Str_SetPtrW
0x18001f547  lea     rcx, [rbx+88h]; ppsz
0x18001f54e  lea     rdx, [rsp+568h+psz]; psz
0x18001f556  call    Str_SetPtrW
0x18001f55b  lea     rcx, [rbx+48h]
0x18001f55f  mov     rdx, rsi
0x18001f562  call    Pidl_Set
0x18001f567  mov     r8d, 80h; unsigned int
0x18001f56d  lea     rdx, [rsp+568h+var_448]; unsigned __int16 *
0x18001f575  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001f578  call    ?FtpPidl_GetUserName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetUserName(_ITEMIDLIST const *,ushort *,ulong)
0x18001f57d  lea     rcx, [rbx+50h]; ppsz
0x18001f581  lea     rdx, [rsp+568h+var_448]; psz
0x18001f589  call    Str_SetPtrW
0x18001f58e  mov     r9d, 1; int
0x18001f594  lea     rdx, [rsp+568h+var_548]; unsigned __int16 *
0x18001f599  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001f59c  call    ?FtpPidl_GetPassword@@YAJPEFBU_ITEMIDLIST@@PEAGKH@Z; FtpPidl_GetPassword(_ITEMIDLIST const *,ushort *,ulong,int)
0x18001f5a1  test    eax, eax
0x18001f5a3  jns     short loc_18001F5AB
0x18001f5a5  mov     [rsp+568h+var_548], r12w
0x18001f5ab  lea     rcx, [rbx+58h]; ppsz
0x18001f5af  lea     rdx, [rsp+568h+var_548]; psz
0x18001f5b4  call    Str_SetPtrW
0x18001f5b9  lea     rdx, [rsp+568h+var_348]; unsigned __int16 *
0x18001f5c1  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001f5c4  call    ?FtpPidl_GetFragment@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetFragment(_ITEMIDLIST const *,ushort *,ulong)
0x18001f5c9  lea     rcx, [rbx+60h]; ppsz
0x18001f5cd  lea     rdx, [rsp+568h+var_348]; psz
0x18001f5d5  call    Str_SetPtrW
0x18001f5da  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001f5dd  mov     edi, 15h
0x18001f5e2  call    ?FtpServerID_GetDataThunk@@YAPEFAUtagFTPSERVERIDLIST@@PEFAU_ITEMIDLIST@@@Z; FtpServerID_GetDataThunk(_ITEMIDLIST *)
0x18001f5e7  test    rax, rax
0x18001f5ea  jz      short loc_18001F5F0
0x18001f5ec  movzx   edi, word ptr [rax+20h]
0x18001f5f0  mov     [rbx+80h], di
0x18001f5f7  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001f5fa  mov     edi, r12d
0x18001f5fd  call    ?FtpServerID_GetTypeID@@YAKPEFBU_ITEMIDLIST@@@Z; FtpServerID_GetTypeID(_ITEMIDLIST const *)
0x18001f602  bt      eax, 0Bh
0x18001f606  jnb     short loc_18001F650
0x18001f608  and     eax, 1000h
0x18001f60d  neg     eax
0x18001f60f  sbb     edi, edi
0x18001f611  add     edi, 2
0x18001f614  jmp     short loc_18001F650
0x18001f616  lea     rcx, [rbx+40h]; ppsz
0x18001f61a  xor     edx, edx; psz
0x18001f61c  call    Str_SetPtrW
0x18001f621  lea     rcx, [rbx+50h]; ppsz
0x18001f625  xor     edx, edx; psz
0x18001f627  call    Str_SetPtrW
0x18001f62c  lea     rcx, [rbx+58h]; ppsz
0x18001f630  xor     edx, edx; psz
0x18001f632  call    Str_SetPtrW
0x18001f637  lea     rcx, [rbx+60h]; ppsz
0x18001f63b  xor     edx, edx; psz
0x18001f63d  call    Str_SetPtrW
0x18001f642  lea     rcx, [rbx+48h]
0x18001f646  xor     edx, edx
0x18001f648  call    Pidl_Set
0x18001f64d  mov     edi, r12d
0x18001f650  mov     [rbx+84h], edi
0x18001f656  mov     [r14], rbx
0x18001f659  jmp     short loc_18001F66F
0x18001f65b  mov     rax, [rbx]
0x18001f65e  mov     rcx, rbx
0x18001f661  mov     ebp, 80004005h
0x18001f666  mov     rax, [rax+10h]
0x18001f66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f66f  mov     eax, ebp
0x18001f671  mov     rcx, [rsp+568h+var_48]
0x18001f679  xor     rcx, rsp; StackCookie
0x18001f67c  call    __security_check_cookie
0x18001f681  add     rsp, 530h
0x18001f688  pop     r15
0x18001f68a  pop     r14
0x18001f68c  pop     r12
0x18001f68e  pop     rdi
0x18001f68f  pop     rsi
0x18001f690  pop     rbp
0x18001f691  pop     rbx
0x18001f692  retn
```
