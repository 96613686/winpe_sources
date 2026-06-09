# FID_GetAssociations(IShellFolder *,_ITEMIDLIST const *,void * *)

- ea: `0x180022840`
- end: `0x180022942`
- name: `?FID_GetAssociations@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST@@PEAPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(struct IShellFolder *, const struct _ITEMIDLIST *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022948`

## callees

- `0x180022840`
- `0x180032010`

## import_xrefs

- `SHLWAPI!AssocCreate` at `0x1800228e7`
- `SHLWAPI!AssocCreate` at `0x1800228e7`

## pseudocode

```c
__int64 __fastcall FID_GetAssociations(struct IShellFolder *a1, const struct _ITEMIDLIST *a2, void **a3)
{
  int v5; // ebx
  struct IShellFolderVtbl *lpVtbl; // rcx
  CLSID clsid; // [rsp+40h] [rbp-10h] BYREF
  int v9; // [rsp+80h] [rbp+30h] BYREF
  const struct _ITEMIDLIST *v10; // [rsp+88h] [rbp+38h] BYREF
  void *ppv; // [rsp+90h] [rbp+40h] BYREF

  v10 = a2;
  *a3 = 0;
  v5 = ((__int64 (__fastcall *)(struct IShellFolder *, _QWORD, __int64, const struct _ITEMIDLIST **, GUID *, _QWORD, void **))a1->lpVtbl->GetUIObjectOf)(
         a1,
         0,
         1,
         &v10,
         &IID_IQueryAssociations,
         0,
         a3);
  if ( v5 < 0 )
  {
    lpVtbl = a1->lpVtbl;
    v9 = 671088640;
    ppv = 0;
    if ( ((int (__fastcall *)(struct IShellFolder *, __int64, const struct _ITEMIDLIST **, int *))lpVtbl->GetAttributesOf)(
           a1,
           1,
           &v10,
           &v9) >= 0
      && (v9 & 0x28000000) != 0 )
    {
      clsid = CLSID_QueryAssociations;
      if ( AssocCreate(&clsid, &IID_IQueryAssociations, &ppv) >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
               ppv,
               0,
               L"Folder",
               0,
               0);
        if ( v5 < 0 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        else
          *a3 = ppv;
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180022840  mov     r11, rsp
0x180022843  mov     [r11+10h], rdx
0x180022847  push    rbp
0x180022848  push    rbx
0x180022849  push    rsi
0x18002284a  push    rdi
0x18002284b  push    r12
0x18002284d  mov     rbp, rsp
0x180022850  sub     rsp, 50h
0x180022854  mov     [r11-48h], r8
0x180022858  lea     r12, IID_IQueryAssociations
0x18002285f  mov     qword ptr [r8], 0
0x180022866  lea     r9, [rbp+arg_8]
0x18002286a  mov     rax, [rcx]
0x18002286d  xor     edx, edx
0x18002286f  mov     rdi, r8
0x180022872  mov     qword ptr [r11-50h], 0
0x18002287a  mov     rsi, rcx
0x18002287d  mov     [r11-58h], r12
0x180022881  mov     rax, [rax+50h]
0x180022885  lea     r8d, [rdx+1]
0x180022889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002288e  mov     ebx, eax
0x180022890  test    eax, eax
0x180022892  jns     loc_180022935
0x180022898  mov     rcx, [rsi]
0x18002289b  lea     r9, [rbp+arg_0]
0x18002289f  lea     r8, [rbp+arg_8]
0x1800228a3  mov     [rbp+arg_0], 28000000h
0x1800228aa  mov     edx, 1
0x1800228af  mov     [rbp+ppv], 0
0x1800228b7  mov     rax, [rcx+48h]
0x1800228bb  mov     rcx, rsi
0x1800228be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228c3  test    eax, eax
0x1800228c5  js      short loc_180022935
0x1800228c7  test    [rbp+arg_0], 28000000h
0x1800228ce  jz      short loc_180022935
0x1800228d0  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x1800228d7  lea     r8, [rbp+ppv]; ppv
0x1800228db  mov     rdx, r12; riid
0x1800228de  lea     rcx, [rbp+clsid]; clsid
0x1800228e2  movdqu  xmmword ptr [rbp+clsid.Data1], xmm0
0x1800228e7  call    cs:__imp_AssocCreate
0x1800228ed  test    eax, eax
0x1800228ef  js      short loc_180022935
0x1800228f1  mov     rcx, [rbp+ppv]
0x1800228f5  lea     r8, aFolder; "Folder"
0x1800228fc  xor     r9d, r9d
0x1800228ff  mov     [rsp+50h+var_30], 0
0x180022908  xor     edx, edx
0x18002290a  mov     rax, [rcx]
0x18002290d  mov     rax, [rax+18h]
0x180022911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022916  mov     ebx, eax
0x180022918  test    eax, eax
0x18002291a  js      short loc_180022925
0x18002291c  mov     rax, [rbp+ppv]
0x180022920  mov     [rdi], rax
0x180022923  jmp     short loc_180022935
0x180022925  mov     rcx, [rbp+ppv]
0x180022929  mov     rax, [rcx]
0x18002292c  mov     rax, [rax+10h]
0x180022930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022935  mov     eax, ebx
0x180022937  add     rsp, 50h
0x18002293b  pop     r12
0x18002293d  pop     rdi
0x18002293e  pop     rsi
0x18002293f  pop     rbx
0x180022940  pop     rbp
0x180022941  retn
```
