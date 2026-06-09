# PropVariantToIDList

- ea: `0x180053c14`
- end: `0x180053e4f`
- name: `PropVariantToIDList`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043dd4`

## callees

- `0x18001d1dc`
- `0x18004cd7c`
- `0x1800506dc`
- `0x180053b6c`
- `0x180053c14`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053ded`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053ded`
- `SHCORE!IStream_Read` at `0x180053dc3`
- `SHCORE!IStream_Read` at `0x180053dc3`
- `SHCORE!IStream_Size` at `0x180053d7d`
- `SHCORE!IStream_Size` at `0x180053d7d`
- `SHELL32!SHParseDisplayName` at `0x180053e1a`
- `SHELL32!SHParseDisplayName` at `0x180053e1a`
- `SHELL32!SHGetSpecialFolderLocation` at `0x180053e38`
- `SHELL32!SHGetSpecialFolderLocation` at `0x180053e38`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180053cef`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180053cef`

## pseudocode

```c
__int64 __fastcall PropVariantToIDList(unsigned __int16 *a1, struct _ITEMIDLIST_ABSOLUTE **a2)
{
  unsigned int v3; // r8d
  unsigned int v5; // ebx
  unsigned int v6; // r8d
  unsigned int v7; // r8d
  unsigned int v8; // r8d
  unsigned int v9; // r8d
  unsigned int v10; // r8d
  int v11; // edx
  struct IUnknown *v12; // rcx
  struct IUnknown **v14; // rcx
  const struct _ITEMIDLIST_RELATIVE *v15; // r11
  const struct _ITEMIDLIST_RELATIVE *v16; // rcx
  int (__fastcall ***v17)(_QWORD, GUID *, IStream **); // rcx
  void *v18; // rcx
  ITEMIDLIST *v19; // rdi
  ULARGE_INTEGER pui; // [rsp+50h] [rbp+20h] BYREF
  IStream *pstm; // [rsp+58h] [rbp+28h] BYREF
  void *pv; // [rsp+60h] [rbp+30h] BYREF

  *a2 = 0;
  v3 = *a1;
  v5 = -2147024809;
  if ( v3 > 0x14 )
  {
    if ( v3 != 21 )
    {
      if ( v3 != 31 )
      {
        switch ( v3 )
        {
          case 0x42u:
            v17 = (int (__fastcall ***)(_QWORD, GUID *, IStream **))*((_QWORD *)a1 + 1);
            pstm = 0;
            if ( (**v17)(v17, &GUID_0000000c_0000_0000_c000_000000000046, &pstm) >= 0 )
            {
              pui.QuadPart = 0;
              v5 = IStream_Size(pstm, &pui);
              if ( (v5 & 0x80000000) == 0 )
              {
                v5 = -2147024809;
                if ( !pui.HighPart )
                {
                  pv = 0;
                  v5 = CTCoAllocPolicy::Alloc(v18, 1u, pui.LowPart, &pv);
                  if ( (v5 & 0x80000000) == 0 )
                  {
                    v19 = (ITEMIDLIST *)pv;
                    v5 = IStream_Read(pstm, pv, pui.LowPart);
                    if ( (v5 & 0x80000000) == 0 )
                    {
                      v5 = -2147024809;
                      if ( IDListContainerIsConsistent(v19, pui.LowPart) )
                      {
                        *a2 = (struct _ITEMIDLIST_ABSOLUTE *)v19;
                        v19 = 0;
                        v5 = 0;
                      }
                    }
                    CoTaskMemFree(v19);
                  }
                }
              }
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
            }
            return v5;
          case 0x1011u:
            if ( !IDListContainerIsConsistent(*((LPCITEMIDLIST *)a1 + 2), *((_DWORD *)a1 + 2)) )
              return v5;
            v16 = (const struct _ITEMIDLIST_RELATIVE *)*((_QWORD *)a1 + 2);
            break;
          case 0x2011u:
            if ( SafeArrayGetDim(*((SAFEARRAY **)a1 + 1)) != 1
              || !IDListContainerIsConsistent(
                    *(LPCITEMIDLIST *)(*((_QWORD *)a1 + 1) + 16LL),
                    *(_DWORD *)(*((_QWORD *)a1 + 1) + 24LL)) )
            {
              return v5;
            }
            v16 = v15;
            break;
          case 0x4009u:
            v14 = (struct IUnknown **)*((_QWORD *)a1 + 1);
            if ( !v14 )
              return v5;
            v12 = *v14;
            return (unsigned int)_GetIDListFromObject(v12, a2);
          default:
            return v5;
        }
        return (unsigned int)SHILClone(v16, a2);
      }
      return (unsigned int)SHParseDisplayName(*((PCWSTR *)a1 + 1), 0, (LPITEMIDLIST *)a2, 0, 0);
    }
    goto LABEL_38;
  }
  if ( v3 == 20 )
  {
LABEL_38:
    if ( *((_QWORD *)a1 + 1) >= 0xFFFFu )
      return v5;
    v11 = *((_DWORD *)a1 + 2);
    return (unsigned int)SHGetSpecialFolderLocation(0, v11 | 0x8000, (LPITEMIDLIST *)a2);
  }
  v6 = v3 - 2;
  if ( !v6 )
  {
    v11 = (__int16)a1[4];
    return (unsigned int)SHGetSpecialFolderLocation(0, v11 | 0x8000, (LPITEMIDLIST *)a2);
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    v8 = v7 - 5;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 4;
        if ( v10 )
        {
          if ( v10 != 6 )
            return v5;
          goto LABEL_9;
        }
      }
      v12 = (struct IUnknown *)*((_QWORD *)a1 + 1);
      return (unsigned int)_GetIDListFromObject(v12, a2);
    }
    return (unsigned int)SHParseDisplayName(*((PCWSTR *)a1 + 1), 0, (LPITEMIDLIST *)a2, 0, 0);
  }
LABEL_9:
  v11 = *((_DWORD *)a1 + 2);
  if ( v11 < 0xFFFF )
    return (unsigned int)SHGetSpecialFolderLocation(0, v11 | 0x8000, (LPITEMIDLIST *)a2);
  return v5;
}

```

## disassembly

```asm
0x180053c14  mov     [rsp-18h+arg_18], rbx
0x180053c19  push    rbp
0x180053c1a  push    rsi
0x180053c1b  push    rdi
0x180053c1c  mov     rbp, rsp
0x180053c1f  sub     rsp, 30h
0x180053c23  mov     qword ptr [rdx], 0
0x180053c2a  mov     rsi, rdx
0x180053c2d  movzx   r8d, word ptr [rcx]
0x180053c31  mov     rdi, rcx
0x180053c34  mov     ebx, 80070057h
0x180053c39  cmp     r8d, 14h
0x180053c3d  ja      short loc_180053C9C
0x180053c3f  jz      loc_180053E22
0x180053c45  sub     r8d, 2
0x180053c49  jz      short loc_180053C93
0x180053c4b  sub     r8d, 1
0x180053c4f  jz      short loc_180053C71
0x180053c51  sub     r8d, 5
0x180053c55  jz      loc_180053E05
0x180053c5b  sub     r8d, 1
0x180053c5f  jz      short loc_180053C85
0x180053c61  sub     r8d, 4
0x180053c65  jz      short loc_180053C85
0x180053c67  cmp     r8d, 6
0x180053c6b  jnz     loc_180053E40
0x180053c71  mov     edx, [rcx+8]; struct _ITEMIDLIST_ABSOLUTE **
0x180053c74  cmp     edx, 0FFFFh
0x180053c7a  jge     loc_180053E40
0x180053c80  jmp     loc_180053E2F
0x180053c85  mov     rcx, [rcx+8]; struct IUnknown *
0x180053c89  call    ?_GetIDListFromObject@@YAJPEAUIUnknown@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; _GetIDListFromObject(IUnknown *,_ITEMIDLIST_ABSOLUTE * *)
0x180053c8e  jmp     loc_180053E3E
0x180053c93  movsx   edx, word ptr [rcx+8]
0x180053c97  jmp     loc_180053E2F
0x180053c9c  cmp     r8d, 15h
0x180053ca0  jz      loc_180053E22
0x180053ca6  cmp     r8d, 1Fh
0x180053caa  jz      loc_180053E05
0x180053cb0  cmp     r8d, 42h ; 'B'
0x180053cb4  jz      loc_180053D43
0x180053cba  cmp     r8d, 1011h
0x180053cc1  jz      short loc_180053D29
0x180053cc3  cmp     r8d, 2011h
0x180053cca  jz      short loc_180053CEB
0x180053ccc  cmp     r8d, 4009h
0x180053cd3  jnz     loc_180053E40
0x180053cd9  mov     rcx, [rcx+8]
0x180053cdd  test    rcx, rcx
0x180053ce0  jz      loc_180053E40
0x180053ce6  mov     rcx, [rcx]
0x180053ce9  jmp     short loc_180053C89
0x180053ceb  mov     rcx, [rcx+8]; psa
0x180053cef  call    cs:__imp_SafeArrayGetDim
0x180053cf5  cmp     eax, 1
0x180053cf8  jnz     loc_180053E40
0x180053cfe  mov     rdx, [rdi+8]
0x180053d02  mov     r11, [rdx+10h]
0x180053d06  mov     edx, [rdx+18h]; cbAlloc
0x180053d09  mov     rcx, r11; pidl
0x180053d0c  call    IDListContainerIsConsistent
0x180053d11  test    eax, eax
0x180053d13  jz      loc_180053E40
0x180053d19  mov     rcx, r11; struct _ITEMIDLIST_RELATIVE *
0x180053d1c  mov     rdx, rsi; struct _ITEMIDLIST_RELATIVE **
0x180053d1f  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x180053d24  jmp     loc_180053E3E
0x180053d29  mov     edx, [rcx+8]; cbAlloc
0x180053d2c  mov     rcx, [rcx+10h]; pidl
0x180053d30  call    IDListContainerIsConsistent
0x180053d35  test    eax, eax
0x180053d37  jz      loc_180053E40
0x180053d3d  mov     rcx, [rdi+10h]
0x180053d41  jmp     short loc_180053D1C
0x180053d43  mov     rcx, [rcx+8]
0x180053d47  lea     r8, [rbp+pstm]
0x180053d4b  mov     [rbp+pstm], 0
0x180053d53  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180053d5a  mov     rax, [rcx]
0x180053d5d  mov     rax, [rax]
0x180053d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d65  test    eax, eax
0x180053d67  js      loc_180053E40
0x180053d6d  mov     rcx, [rbp+pstm]; pstm
0x180053d71  lea     rdx, [rbp+pui]; pui
0x180053d75  mov     qword ptr [rbp+pui], 0
0x180053d7d  call    cs:__imp_IStream_Size
0x180053d83  mov     ebx, eax
0x180053d85  test    eax, eax
0x180053d87  js      short loc_180053DF3
0x180053d89  cmp     dword ptr [rbp+pui+4], 0
0x180053d8d  mov     ebx, 80070057h
0x180053d92  jnz     short loc_180053DF3
0x180053d94  mov     r8d, dword ptr [rbp+pui]; unsigned __int64
0x180053d98  lea     r9, [rbp+pv]; void **
0x180053d9c  mov     edx, 1; unsigned int
0x180053da1  mov     [rbp+pv], 0
0x180053da9  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180053dae  mov     ebx, eax
0x180053db0  test    eax, eax
0x180053db2  js      short loc_180053DF3
0x180053db4  mov     rdi, [rbp+pv]
0x180053db8  mov     r8d, dword ptr [rbp+pui]; cb
0x180053dbc  mov     rdx, rdi; pv
0x180053dbf  mov     rcx, [rbp+pstm]; pstm
0x180053dc3  call    cs:__imp_IStream_Read
0x180053dc9  mov     ebx, eax
0x180053dcb  test    eax, eax
0x180053dcd  js      short loc_180053DEA
0x180053dcf  mov     edx, dword ptr [rbp+pui]; cbAlloc
0x180053dd2  mov     rcx, rdi; pidl
0x180053dd5  mov     ebx, 80070057h
0x180053dda  call    IDListContainerIsConsistent
0x180053ddf  test    eax, eax
0x180053de1  jz      short loc_180053DEA
0x180053de3  mov     [rsi], rdi
0x180053de6  xor     edi, edi
0x180053de8  xor     ebx, ebx
0x180053dea  mov     rcx, rdi; pv
0x180053ded  call    cs:__imp_CoTaskMemFree
0x180053df3  mov     rcx, [rbp+pstm]
0x180053df7  mov     rax, [rcx]
0x180053dfa  mov     rax, [rax+10h]
0x180053dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e03  jmp     short loc_180053E40
0x180053e05  mov     rcx, [rcx+8]; pszName
0x180053e09  xor     r9d, r9d; sfgaoIn
0x180053e0c  mov     r8, rsi; ppidl
0x180053e0f  mov     [rsp+30h+psfgaoOut], 0; psfgaoOut
0x180053e18  xor     edx, edx; pbc
0x180053e1a  call    cs:__imp_SHParseDisplayName
0x180053e20  jmp     short loc_180053E3E
0x180053e22  cmp     qword ptr [rcx+8], 0FFFFh
0x180053e2a  jnb     short loc_180053E40
0x180053e2c  mov     edx, [rcx+8]
0x180053e2f  mov     r8, rsi; ppidl
0x180053e32  bts     edx, 0Fh; csidl
0x180053e36  xor     ecx, ecx; hwnd
0x180053e38  call    cs:__imp_SHGetSpecialFolderLocation
0x180053e3e  mov     ebx, eax
0x180053e40  mov     eax, ebx
0x180053e42  mov     rbx, [rsp+30h+arg_18]
0x180053e47  add     rsp, 30h
0x180053e4b  pop     rdi
0x180053e4c  pop     rsi
0x180053e4d  pop     rbp
0x180053e4e  retn
```
