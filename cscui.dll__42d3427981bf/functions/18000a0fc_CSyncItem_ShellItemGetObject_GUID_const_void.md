# CSyncItem::_ShellItemGetObject(_GUID const &,void * *)

- ea: `0x18000a0fc`
- end: `0x18000a1f9`
- name: `?_ShellItemGetObject@CSyncItem@@AEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `253`
- prototype: `__int64 __fastcall(CSyncItem *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a080`
- `0x18001a2c0`

## callees

- `0x18000a0fc`
- `0x18004d010`

## import_xrefs

- `SHELL32!SHBindToFolderIDListParent` at `0x18000a188`
- `SHELL32!SHBindToFolderIDListParent` at `0x18000a188`
- `SHELL32!__imp_SHILCreateFromPath` at `0x18000a152`
- `SHELL32!__imp_SHILCreateFromPath` at `0x18000a152`
- `SHELL32!__imp_ILFree` at `0x18000a1d7`
- `SHELL32!__imp_ILFree` at `0x18000a1d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a1e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a1e1`

## pseudocode

```c
__int64 __fastcall CSyncItem::_ShellItemGetObject(CSyncItem *this, const struct _GUID *a2, void **a3)
{
  __int64 v3; // rcx
  HRESULT v6; // ebx
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-20h] BYREF
  PCWSTR pszPath; // [rsp+48h] [rbp-18h] BYREF
  LPCITEMIDLIST ppidlLast[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD rgfInOut; // [rsp+80h] [rbp+20h] BYREF
  void *ppv; // [rsp+98h] [rbp+38h] BYREF

  v3 = *((_QWORD *)this + 2);
  pszPath = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v3 + 32LL))(v3, &pszPath);
  if ( v6 >= 0 )
  {
    ppidl = 0;
    rgfInOut = 0;
    v6 = SHILCreateFromPath(pszPath, &ppidl, &rgfInOut);
    if ( v6 >= 0 )
    {
      ppv = 0;
      ppidlLast[0] = 0;
      v6 = SHBindToFolderIDListParent(0, ppidl, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, ppidlLast);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, LPCITEMIDLIST *, const struct _GUID *, _QWORD, void **))(*(_QWORD *)ppv + 80LL))(
               ppv,
               0,
               1,
               ppidlLast,
               a2,
               0,
               a3);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      ILFree(ppidl);
    }
    CoTaskMemFree((LPVOID)pszPath);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000a0fc  mov     [rsp-18h+arg_8], rbx
0x18000a101  push    rbp
0x18000a102  push    rsi
0x18000a103  push    rdi
0x18000a104  mov     rbp, rsp
0x18000a107  sub     rsp, 60h
0x18000a10b  mov     rcx, [rcx+10h]
0x18000a10f  mov     rsi, rdx
0x18000a112  mov     [rbp+pszPath], 0
0x18000a11a  lea     rdx, [rbp+pszPath]
0x18000a11e  mov     rdi, r8
0x18000a121  mov     rax, [rcx]
0x18000a124  mov     rax, [rax+20h]
0x18000a128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a12d  mov     ebx, eax
0x18000a12f  test    eax, eax
0x18000a131  js      loc_18000A1E7
0x18000a137  mov     rcx, [rbp+pszPath]; pszPath
0x18000a13b  lea     r8, [rbp+rgfInOut]; rgfInOut
0x18000a13f  lea     rdx, [rbp+ppidl]; ppidl
0x18000a143  mov     [rbp+ppidl], 0
0x18000a14b  mov     [rbp+rgfInOut], 0
0x18000a152  call    cs:__imp_SHILCreateFromPath
0x18000a158  mov     ebx, eax
0x18000a15a  test    eax, eax
0x18000a15c  js      short loc_18000A1DD
0x18000a15e  mov     rdx, [rbp+ppidl]; pidl
0x18000a162  lea     rax, [rbp+var_10]
0x18000a166  lea     r9, [rbp+ppv]; ppv
0x18000a16a  mov     [rsp+60h+ppidlLast], rax; ppidlLast
0x18000a16f  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18000a176  mov     [rbp+ppv], 0
0x18000a17e  xor     ecx, ecx; psfRoot
0x18000a180  mov     [rbp+var_10], 0
0x18000a188  call    cs:__imp_SHBindToFolderIDListParent
0x18000a18e  mov     ebx, eax
0x18000a190  test    eax, eax
0x18000a192  js      short loc_18000A1D3
0x18000a194  mov     rcx, [rbp+ppv]
0x18000a198  lea     r9, [rbp+var_10]
0x18000a19c  xor     edx, edx
0x18000a19e  mov     [rsp+60h+var_30], rdi
0x18000a1a3  mov     [rsp+60h+var_38], 0
0x18000a1ac  mov     [rsp+60h+ppidlLast], rsi
0x18000a1b1  mov     rax, [rcx]
0x18000a1b4  lea     r8d, [rdx+1]
0x18000a1b8  mov     rax, [rax+50h]
0x18000a1bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1c1  mov     rcx, [rbp+ppv]
0x18000a1c5  mov     ebx, eax
0x18000a1c7  mov     rax, [rcx]
0x18000a1ca  mov     rax, [rax+10h]
0x18000a1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1d3  mov     rcx, [rbp+ppidl]; pidl
0x18000a1d7  call    cs:__imp_ILFree
0x18000a1dd  mov     rcx, [rbp+pszPath]; pv
0x18000a1e1  call    cs:__imp_CoTaskMemFree
0x18000a1e7  mov     eax, ebx
0x18000a1e9  mov     rbx, [rsp+60h+arg_8]
0x18000a1f1  add     rsp, 60h
0x18000a1f5  pop     rdi
0x18000a1f6  pop     rsi
0x18000a1f7  pop     rbp
0x18000a1f8  retn
```
