# CMailTransferSource::RemoveItem(IShellItem *,ulong)

- ea: `0x180028eb0`
- end: `0x1800290c4`
- name: `?RemoveItem@CMailTransferSource@@UEAAJPEAUIShellItem@@K@Z`
- size: `532`
- prototype: `int(CMailTransferSource *__hidden this, struct IShellItem *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005210`
- `0x18001bb40`
- `0x18001f6d8`
- `0x180028eb0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!ILRemoveLastID` at `0x180028f6d`
- `api-ms-win-shell-namespace-l1-1-0!ILRemoveLastID` at `0x180028f6d`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x180028f20`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x180028f20`
- `api-ms-win-shell-namespace-l1-1-0!ILFindLastID` at `0x180028f60`
- `api-ms-win-shell-namespace-l1-1-0!ILFindLastID` at `0x180028f60`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180029085`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180029096`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180029085`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180029096`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x180028f3d`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x180028f3d`

## pseudocode

```c
__int64 __fastcall CMailTransferSource::RemoveItem(CMailTransferSource *this, IUnknown *a2, __int16 a3)
{
  LPITEMIDLIST v6; // r14
  HRESULT v7; // ebx
  LPITEMIDLIST v8; // rdi
  struct IShellItemVtbl *lpVtbl; // rax
  int i; // esi
  __int64 v11; // rcx
  __int64 v12; // [rsp+40h] [rbp-29h] BYREF
  struct _ITEMID_CHILD *ID; // [rsp+48h] [rbp-21h] BYREF
  _OWORD v14[3]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v15; // [rsp+80h] [rbp+17h]
  LPITEMIDLIST ppidl; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( (a3 & 0x400) != 0 )
    return 2555907;
  ppidl = 0;
  if ( (int)ATL::CComObject<CMessageContextMenu>::CreateInstance(&ppidl) >= 0 && (v6 = ppidl) != 0 )
  {
    (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&ppidl->mkid.cb + 8LL))(ppidl);
    ppidl = 0;
    v7 = SHGetIDListFromObject(a2, &ppidl);
    if ( v7 >= 0 )
    {
      if ( ppidl )
      {
        v8 = ILClone(ppidl);
        v7 = v8 == 0 ? 0x8007000E : 0;
        if ( v8 )
        {
          ID = (struct _ITEMID_CHILD *)ILFindLastID(ppidl);
          ILRemoveLastID(v8);
          v7 = CMessageContextMenu::Init((CMessageContextMenu *)v6, v8, &ID, 1u, 0);
          if ( v7 >= 0 )
          {
            v14[0] = 0;
            v15 = 0;
            LODWORD(v14[0]) = 56;
            v14[1] = 0x63u;
            v14[2] = 0;
            v7 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)((char *)&v6[5].mkid.cb + 1) + 32LL))(
                   (__int64)&v6[5].mkid.cb + 1,
                   v14);
            ID = 0;
            lpVtbl = (struct IShellItemVtbl *)a2->lpVtbl;
            v12 = 0;
            ((void (__fastcall *)(IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
              a2,
              &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
              &v12);
            if ( v12 )
              (*(void (__fastcall **)(__int64, const PROPERTYKEY *, struct _ITEMID_CHILD **))(*(_QWORD *)v12 + 152LL))(
                v12,
                &PKEY_Size,
                &ID);
            for ( i = 0; i < *((_DWORD *)this + 18); ++i )
            {
              if ( i >= 0 && i < *((_DWORD *)this + 18) )
              {
                v11 = *(_QWORD *)(*((_QWORD *)this + 8) + 8LL * i);
                if ( v11 )
                  (*(void (__fastcall **)(__int64, struct _ITEMID_CHILD *, struct _ITEMID_CHILD *, _QWORD, _DWORD, _DWORD, _DWORD))(*(_QWORD *)v11 + 24LL))(
                    v11,
                    ID,
                    ID,
                    0,
                    0,
                    0,
                    0);
              }
            }
            ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v12);
          }
          ILFree(v8);
        }
      }
      else
      {
        v7 = -2147024809;
      }
      ILFree(ppidl);
    }
    (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&v6->mkid.cb + 16LL))(v6);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180028eb0  push    rbp
0x180028eb2  push    rbx
0x180028eb3  push    rsi
0x180028eb4  push    rdi
0x180028eb5  push    r14
0x180028eb7  push    r15
0x180028eb9  lea     rbp, [rsp-2Fh]
0x180028ebe  sub     rsp, 98h
0x180028ec5  mov     rsi, rdx
0x180028ec8  mov     r15, rcx
0x180028ecb  bt      r8d, 0Ah
0x180028ed0  jnb     short loc_180028EDC
0x180028ed2  mov     eax, 270003h
0x180028ed7  jmp     loc_1800290B4
0x180028edc  lea     rcx, [rbp+57h+ppidl]
0x180028ee0  mov     [rbp+57h+ppidl], 0
0x180028ee8  call    ?CreateInstance@?$CComObject@VCMessageContextMenu@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMessageContextMenu>::CreateInstance(ATL::CComObject<CMessageContextMenu> * *)
0x180028eed  test    eax, eax
0x180028eef  js      loc_1800290AD
0x180028ef5  mov     r14, [rbp+57h+ppidl]
0x180028ef9  test    r14, r14
0x180028efc  jz      loc_1800290AD
0x180028f02  mov     rax, [r14]
0x180028f05  mov     rcx, r14
0x180028f08  mov     rax, [rax+8]
0x180028f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f11  lea     rdx, [rbp+57h+ppidl]; ppidl
0x180028f15  mov     [rbp+57h+ppidl], 0
0x180028f1d  mov     rcx, rsi; punk
0x180028f20  call    cs:__imp_SHGetIDListFromObject
0x180028f26  mov     ebx, eax
0x180028f28  test    eax, eax
0x180028f2a  js      loc_18002909C
0x180028f30  mov     rcx, [rbp+57h+ppidl]; pidl
0x180028f34  test    rcx, rcx
0x180028f37  jz      loc_18002908D
0x180028f3d  call    cs:__imp_ILClone
0x180028f43  mov     rdi, rax
0x180028f46  neg     rax
0x180028f49  sbb     ebx, ebx
0x180028f4b  not     ebx
0x180028f4d  and     ebx, 8007000Eh
0x180028f53  test    rdi, rdi
0x180028f56  jz      loc_180029092
0x180028f5c  mov     rcx, [rbp+57h+ppidl]; pidl
0x180028f60  call    cs:__imp_ILFindLastID
0x180028f66  mov     rcx, rdi; pidl
0x180028f69  mov     [rbp+57h+var_78], rax
0x180028f6d  call    cs:__imp_ILRemoveLastID
0x180028f73  mov     r9d, 1; unsigned int
0x180028f79  mov     [rsp+0C0h+var_A0], 0; struct IContextMenu *
0x180028f82  lea     r8, [rbp+57h+var_78]; struct _ITEMID_CHILD **
0x180028f86  mov     rdx, rdi; pidl
0x180028f89  mov     rcx, r14; this
0x180028f8c  call    ?Init@CMessageContextMenu@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBQEFBU_ITEMID_CHILD@@IPEAUIContextMenu@@@Z; CMessageContextMenu::Init(_ITEMIDLIST_ABSOLUTE const *,_ITEMID_CHILD const * const *,uint,IContextMenu *)
0x180028f91  mov     ebx, eax
0x180028f93  test    eax, eax
0x180028f95  js      loc_180029082
0x180028f9b  xorps   xmm0, xmm0
0x180028f9e  lea     rcx, [r14+10h]
0x180028fa2  xor     eax, eax
0x180028fa4  lea     rdx, [rbp+57h+var_70]
0x180028fa8  movups  [rbp+57h+var_70], xmm0
0x180028fac  mov     [rbp+57h+var_40], rax
0x180028fb0  movups  [rbp+57h+var_60], xmm0
0x180028fb4  mov     dword ptr [rbp+57h+var_70], 38h ; '8'
0x180028fbb  mov     qword ptr [rbp+57h+var_60], 63h ; 'c'
0x180028fc3  movups  [rbp+57h+var_50], xmm0
0x180028fc7  mov     rax, [rcx]
0x180028fca  mov     rax, [rax+20h]
0x180028fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fd3  mov     ebx, eax
0x180028fd5  mov     [rbp+57h+var_78], 0
0x180028fdd  mov     rax, [rsi]
0x180028fe0  lea     r8, [rbp+57h+var_80]
0x180028fe4  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180028feb  mov     [rbp+57h+var_80], 0
0x180028ff3  mov     rcx, rsi
0x180028ff6  mov     rax, [rax]
0x180028ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ffe  mov     rcx, [rbp+57h+var_80]
0x180029002  test    rcx, rcx
0x180029005  jz      short loc_180029021
0x180029007  mov     rax, [rcx]
0x18002900a  lea     r8, [rbp+57h+var_78]
0x18002900e  lea     rdx, PKEY_Size
0x180029015  mov     rax, [rax+98h]
0x18002901c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029021  xor     esi, esi
0x180029023  cmp     [r15+48h], esi
0x180029027  jle     short loc_180029079
0x180029029  test    esi, esi
0x18002902b  js      short loc_180029071
0x18002902d  cmp     esi, [r15+48h]
0x180029031  jge     short loc_180029071
0x180029033  mov     rax, [r15+40h]
0x180029037  movsxd  rcx, esi
0x18002903a  mov     rcx, [rax+rcx*8]
0x18002903e  test    rcx, rcx
0x180029041  jz      short loc_180029071
0x180029043  mov     rax, [rcx]
0x180029046  xor     r9d, r9d
0x180029049  mov     rdx, [rbp+57h+var_78]
0x18002904d  mov     [rsp+0C0h+var_90], 0
0x180029055  mov     r8, rdx
0x180029058  mov     [rsp+0C0h+var_98], 0
0x180029060  mov     rax, [rax+18h]
0x180029064  mov     dword ptr [rsp+0C0h+var_A0], 0
0x18002906c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029071  inc     esi
0x180029073  cmp     esi, [r15+48h]
0x180029077  jl      short loc_180029029
0x180029079  lea     rcx, [rbp+57h+var_80]
0x18002907d  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180029082  mov     rcx, rdi; pidl
0x180029085  call    cs:__imp_ILFree
0x18002908b  jmp     short loc_180029092
0x18002908d  mov     ebx, 80070057h
0x180029092  mov     rcx, [rbp+57h+ppidl]; pidl
0x180029096  call    cs:__imp_ILFree
0x18002909c  mov     rax, [r14]
0x18002909f  mov     rcx, r14
0x1800290a2  mov     rax, [rax+10h]
0x1800290a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290ab  jmp     short loc_1800290B2
0x1800290ad  mov     ebx, 8007000Eh
0x1800290b2  mov     eax, ebx
0x1800290b4  add     rsp, 98h
0x1800290bb  pop     r15
0x1800290bd  pop     r14
0x1800290bf  pop     rdi
0x1800290c0  pop     rsi
0x1800290c1  pop     rbx
0x1800290c2  pop     rbp
0x1800290c3  retn
```
