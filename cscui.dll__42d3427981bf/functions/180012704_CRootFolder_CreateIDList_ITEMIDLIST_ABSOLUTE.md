# CRootFolder::CreateIDList(_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x180012704`
- end: `0x18001285b`
- name: `?CreateIDList@CRootFolder@@SAJPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d8d0`

## callees

- `0x180012704`
- `0x18004c636`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHELL32!SHGetDesktopFolder` at `0x180012741`
- `SHELL32!SHGetDesktopFolder` at `0x180012741`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800127da`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800127da`
- `ole32!CreateBindCtx` at `0x180012761`
- `ole32!CreateBindCtx` at `0x180012761`

## pseudocode

```c
__int64 __fastcall CRootFolder::CreateIDList(struct _ITEMIDLIST_ABSOLUTE **a1)
{
  HRESULT v2; // ebx
  LPBC ppbc; // [rsp+40h] [rbp-C0h] BYREF
  IShellFolder *ppshf; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v6[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v7; // [rsp+58h] [rbp-A8h]
  int v8; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v10[154]; // [rsp+66h] [rbp-9Ah] BYREF

  *a1 = 0;
  ppshf = 0;
  v2 = SHGetDesktopFolder(&ppshf);
  if ( v2 >= 0 )
  {
    ppbc = 0;
    v2 = CreateBindCtx(0, &ppbc);
    if ( v2 >= 0 )
    {
      v7 = 4096;
      v6[0] = 16;
      v6[1] = 2;
      ((void (__fastcall *)(LPBC, _DWORD *))ppbc->lpVtbl->SetBindOptions)(ppbc, v6);
      v8 = *(_DWORD *)L"::";
      sz = asc_18005579C[2];
      memset_0(v10, 0, sizeof(v10));
      StringFromGUID2(&CLSID_OfflineFilesFolder, &sz, 78);
      v2 = ((__int64 (__fastcall *)(IShellFolder *, _QWORD, LPBC, int *, _QWORD, struct _ITEMIDLIST_ABSOLUTE **, _QWORD))ppshf->lpVtbl->ParseDisplayName)(
             ppshf,
             0,
             ppbc,
             &v8,
             0,
             a1,
             0);
      ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    }
    ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180012704  mov     [rsp-8+arg_8], rbx
0x180012709  mov     [rsp-8+arg_10], rdi
0x18001270e  push    rbp
0x18001270f  lea     rbp, [rsp-10h]
0x180012714  sub     rsp, 110h
0x18001271b  mov     rax, cs:__security_cookie
0x180012722  xor     rax, rsp
0x180012725  mov     [rbp+10h+var_10], rax
0x180012729  mov     rdi, rcx
0x18001272c  mov     qword ptr [rcx], 0
0x180012733  lea     rcx, [rsp+110h+ppshf]; ppshf
0x180012738  mov     [rsp+110h+ppshf], 0
0x180012741  call    cs:__imp_SHGetDesktopFolder
0x180012747  mov     ebx, eax
0x180012749  test    eax, eax
0x18001274b  js      loc_180012838
0x180012751  lea     rdx, [rsp+110h+ppbc]; ppbc
0x180012756  mov     [rsp+110h+ppbc], 0
0x18001275f  xor     ecx, ecx; reserved
0x180012761  call    cs:__imp_CreateBindCtx
0x180012767  mov     ebx, eax
0x180012769  test    eax, eax
0x18001276b  js      loc_180012827
0x180012771  mov     rcx, [rsp+110h+ppbc]
0x180012776  lea     rdx, [rsp+110h+var_C0]
0x18001277b  mov     [rsp+110h+var_B8], 1000h
0x180012784  mov     [rsp+110h+var_C0], 10h
0x18001278c  mov     [rsp+110h+var_BC], 2
0x180012794  mov     rax, [rcx]
0x180012797  mov     rax, [rax+30h]
0x18001279b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127a0  mov     eax, dword ptr cs:asc_18005579C; "::"
0x1800127a6  lea     rcx, [rsp+110h+var_AA]; void *
0x1800127ab  mov     [rsp+110h+var_B0], eax
0x1800127af  xor     edx, edx; Val
0x1800127b1  movzx   eax, word ptr cs:asc_18005579C+4; ""
0x1800127b8  mov     r8d, 9Ah; Size
0x1800127be  mov     [rsp+110h+sz], ax
0x1800127c3  call    memset_0
0x1800127c8  mov     r8d, 4Eh ; 'N'; cchMax
0x1800127ce  lea     rdx, [rsp+110h+sz]; lpsz
0x1800127d3  lea     rcx, CLSID_OfflineFilesFolder; rguid
0x1800127da  call    cs:__imp_StringFromGUID2
0x1800127e0  mov     rcx, [rsp+110h+ppshf]
0x1800127e5  lea     r9, [rsp+110h+var_B0]
0x1800127ea  mov     r8, [rsp+110h+ppbc]
0x1800127ef  xor     edx, edx
0x1800127f1  mov     [rsp+110h+var_E0], 0
0x1800127fa  mov     [rsp+110h+var_E8], rdi
0x1800127ff  mov     rax, [rcx]
0x180012802  mov     [rsp+110h+var_F0], 0
0x18001280b  mov     rax, [rax+18h]
0x18001280f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012814  mov     rcx, [rsp+110h+ppbc]
0x180012819  mov     ebx, eax
0x18001281b  mov     rax, [rcx]
0x18001281e  mov     rax, [rax+10h]
0x180012822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012827  mov     rcx, [rsp+110h+ppshf]
0x18001282c  mov     rax, [rcx]
0x18001282f  mov     rax, [rax+10h]
0x180012833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012838  mov     eax, ebx
0x18001283a  mov     rcx, [rbp+10h+var_10]
0x18001283e  xor     rcx, rsp; StackCookie
0x180012841  call    __security_check_cookie
0x180012846  lea     r11, [rsp+110h+var_s0]
0x18001284e  mov     rbx, [r11+18h]
0x180012852  mov     rdi, [r11+20h]
0x180012856  mov     rsp, r11
0x180012859  pop     rbp
0x18001285a  retn
```
