# CCabFolder::CompareIDs(__int64,_ITEMIDLIST const *,_ITEMIDLIST const *)

- ea: `0x18000d9d0`
- end: `0x18000da1e`
- name: `?CompareIDs@CCabFolder@@UEAAJ_JPEFBU_ITEMIDLIST@@1@Z`
- size: `78`
- prototype: `__int64 __fastcall(CCabFolder *__hidden this, __int64, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000d9d0`
- `0x18000da24`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000d9e6`
- `KERNEL32!lstrcmpiW` at `0x18000d9e6`

## pseudocode

```c
__int64 __fastcall CCabFolder::CompareIDs(
        unsigned __int64 this,
        __int64 a2,
        struct _ITEMIDLIST *a3,
        struct _ITEMIDLIST *a4)
{
  int v4; // ecx

  if ( (a2 & 0x10000000) == 0 )
    return CompareIDsImpl((struct IShellFolder2 *)(this & -(__int64)(this != 8)), a2, a3, a4);
  v4 = lstrcmpiW((LPCWSTR)((char *)&a3[5].mkid.cb + 1), (LPCWSTR)((char *)&a4[5].mkid.cb + 1));
  if ( v4 >= 0 )
    return v4 > 0;
  else
    return 0xFFFF;
}

```

## disassembly

```asm
0x18000d9d0  sub     rsp, 28h
0x18000d9d4  mov     r10, rcx
0x18000d9d7  bt      rdx, 1Ch
0x18000d9dc  jnb     short loc_18000DA08
0x18000d9de  lea     rdx, [r9+10h]; lpString2
0x18000d9e2  lea     rcx, [r8+10h]; lpString1
0x18000d9e6  call    cs:__imp_lstrcmpiW
0x18000d9ec  mov     ecx, eax
0x18000d9ee  test    eax, eax
0x18000d9f0  jns     short loc_18000D9FC
0x18000d9f2  mov     eax, 0FFFFh
0x18000d9f7  add     rsp, 28h
0x18000d9fb  retn
0x18000d9fc  xor     eax, eax
0x18000d9fe  test    ecx, ecx
0x18000da00  setnle  al
0x18000da03  add     rsp, 28h
0x18000da07  retn
0x18000da08  lea     rax, [rcx-8]
0x18000da0c  neg     rax
0x18000da0f  sbb     rcx, rcx
0x18000da12  and     rcx, r10; struct IShellFolder2 *
0x18000da15  add     rsp, 28h
0x18000da19  jmp     ?CompareIDsImpl@@YAJPEAUIShellFolder2@@_JPEFBU_ITEMIDLIST@@2@Z; CompareIDsImpl(IShellFolder2 *,__int64,_ITEMIDLIST const *,_ITEMIDLIST const *)
```
