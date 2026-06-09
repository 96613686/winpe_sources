# CMfObject::ChangeData(void *,int)

- ea: `0x18009c5e8`
- end: `0x18009c6da`
- name: `?ChangeData@CMfObject@@AEAAJPEAXH@Z`
- size: `242`
- prototype: `HRESULT __fastcall(CMfObject *this, void *hMfp, int fDelete)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18009d280`

## callees

- `0x18009c5e8`
- `0x1800a5b68`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x18009c62d`
- `KERNELBASE!GlobalFree` at `0x18009c6c3`
- `KERNELBASE!GlobalFree` at `0x18009c62d`
- `KERNELBASE!GlobalFree` at `0x18009c6c3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18009c6a8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18009c6a8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009c617`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009c617`
- `GDI32!DeleteMetaFile` at `0x18009c689`
- `GDI32!DeleteMetaFile` at `0x18009c6b5`
- `GDI32!DeleteMetaFile` at `0x18009c689`
- `GDI32!DeleteMetaFile` at `0x18009c6b5`
- `GDI32!CopyMetaFileW` at `0x18009c643`
- `GDI32!CopyMetaFileW` at `0x18009c643`
- `GDI32!GetMetaFileBitsEx` at `0x18009c66c`
- `GDI32!GetMetaFileBitsEx` at `0x18009c66c`

## pseudocode

```c
HRESULT __fastcall CMfObject::ChangeData(CMfObject *this, void *hMfp, int fDelete)
{
  HRESULT result; // eax
  HRESULT v7; // ebx
  LPVOID v8; // rax
  _DWORD *v9; // rsi
  HMETAFILE__ *v10; // rbp
  UINT MetaFileBits; // r12d
  HMETAFILE__ *m_hPres; // rcx

  result = VerifyStructFromHGlobal(3u, hMfp);
  v7 = result;
  if ( result >= 0 )
  {
    v8 = GlobalLock(hMfp);
    v9 = v8;
    if ( !v8 )
    {
      if ( fDelete )
        GlobalFree(hMfp);
      return -2147024882;
    }
    v10 = (HMETAFILE__ *)*((_QWORD *)v8 + 2);
    if ( !fDelete )
    {
      v10 = CopyMetaFileW(*((HMETAFILE *)v8 + 2), 0);
      if ( !v10 )
        return -2147024882;
    }
    if ( *v9 == 8 )
    {
      MetaFileBits = GetMetaFileBitsEx(v10, 0, 0);
      if ( MetaFileBits )
      {
        m_hPres = this->m_hPres;
        if ( m_hPres )
          DeleteMetaFile(m_hPres);
        this->m_hPres = v10;
        this->m_dwSize = MetaFileBits;
        this->m_lWidth = v9[1];
        this->m_lHeight = v9[2];
      }
      else
      {
        v7 = -2147221497;
      }
    }
    else
    {
      v7 = -2147467259;
    }
    GlobalUnlock(hMfp);
    if ( v7 )
      DeleteMetaFile(v10);
    if ( fDelete )
      GlobalFree(hMfp);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18009c5e8  push    rbx
0x18009c5ea  push    rbp
0x18009c5eb  push    rsi
0x18009c5ec  push    rdi
0x18009c5ed  push    r12
0x18009c5ef  push    r14
0x18009c5f1  push    r15
0x18009c5f3  sub     rsp, 20h
0x18009c5f7  mov     r15, this
0x18009c5fa  mov     r14d, fDelete
0x18009c5fd  mov     ecx, 3; cfFormat
0x18009c602  mov     rdi, hMfp
0x18009c605  call    ?VerifyStructFromHGlobal@@YAJGPEAX@Z; VerifyStructFromHGlobal(ushort,void *)
0x18009c60a  mov     ebx, eax
0x18009c60c  test    eax, eax
0x18009c60e  js      loc_18009C6CB
0x18009c614  mov     this, rdi; hMem
0x18009c617  call    cs:__imp_GlobalLock
0x18009c61d  mov     rsi, rax
0x18009c620  test    rax, rax
0x18009c623  jnz     short loc_18009C635
0x18009c625  test    r14d, r14d
0x18009c628  jz      short loc_18009C651
0x18009c62a  mov     this, rdi; hMem
0x18009c62d  call    cs:__imp_GlobalFree
0x18009c633  jmp     short loc_18009C651
0x18009c635  mov     rbp, [rax+10h]
0x18009c639  test    r14d, r14d
0x18009c63c  jnz     short loc_18009C658
0x18009c63e  xor     edx, edx; LPCWSTR
0x18009c640  mov     this, rbp; HMETAFILE
0x18009c643  call    cs:__imp_CopyMetaFileW
0x18009c649  mov     rbp, rax
0x18009c64c  test    rax, rax
0x18009c64f  jnz     short loc_18009C658
0x18009c651  mov     eax, 8007000Eh
0x18009c656  jmp     short loc_18009C6CB
0x18009c658  cmp     dword ptr [rsi], 8
0x18009c65b  jz      short loc_18009C664
0x18009c65d  mov     ebx, 80004005h
0x18009c662  jmp     short loc_18009C6A5
0x18009c664  xor     fDelete, fDelete; lpData
0x18009c667  xor     edx, edx; cbBuffer
0x18009c669  mov     this, rbp; hMF
0x18009c66c  call    cs:__imp_GetMetaFileBitsEx
0x18009c672  mov     r12d, eax
0x18009c675  test    eax, eax
0x18009c677  jnz     short loc_18009C680
0x18009c679  mov     ebx, 80040007h
0x18009c67e  jmp     short loc_18009C6A5
0x18009c680  mov     this, [r15+10h]; hmf
0x18009c684  test    this, this
0x18009c687  jz      short loc_18009C68F
0x18009c689  call    cs:__imp_DeleteMetaFile
0x18009c68f  mov     [r15+10h], rbp
0x18009c693  mov     [r15+5Ch], r12d
0x18009c697  mov     eax, [rsi+4]
0x18009c69a  mov     [r15+60h], eax
0x18009c69e  mov     eax, [rsi+8]
0x18009c6a1  mov     [r15+64h], eax
0x18009c6a5  mov     this, rdi; hMem
0x18009c6a8  call    cs:__imp_GlobalUnlock
0x18009c6ae  test    ebx, ebx
0x18009c6b0  jz      short loc_18009C6BB
0x18009c6b2  mov     this, rbp; hmf
0x18009c6b5  call    cs:__imp_DeleteMetaFile
0x18009c6bb  test    r14d, r14d
0x18009c6be  jz      short loc_18009C6C9
0x18009c6c0  mov     this, rdi; hMem
0x18009c6c3  call    cs:__imp_GlobalFree
0x18009c6c9  mov     eax, ebx
0x18009c6cb  add     rsp, 20h
0x18009c6cf  pop     r15
0x18009c6d1  pop     r14
0x18009c6d3  pop     r12
0x18009c6d5  pop     rdi
0x18009c6d6  pop     rsi
0x18009c6d7  pop     rbp
0x18009c6d8  pop     rbx
0x18009c6d9  retn
```
