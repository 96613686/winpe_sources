# CMfObject::ChangeData(void *,int)

- ea: `0x18009f1f4`
- end: `0x18009f338`
- name: `?ChangeData@CMfObject@@AEAAJPEAXH@Z`
- size: `324`
- prototype: `HRESULT __fastcall(CMfObject *this, void *hMfp, int fDelete)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18009fff0`

## callees

- `0x18009f1f4`
- `0x1800aca50`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x18009f24d`
- `KERNELBASE!GlobalFree` at `0x18009f30a`
- `KERNELBASE!GlobalFree` at `0x18009f24d`
- `KERNELBASE!GlobalFree` at `0x18009f30a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18009f2e3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18009f2e3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009f231`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009f231`
- `GDI32!DeleteMetaFile` at `0x18009f2be`
- `GDI32!DeleteMetaFile` at `0x18009f2f6`
- `GDI32!DeleteMetaFile` at `0x18009f2be`
- `GDI32!DeleteMetaFile` at `0x18009f2f6`
- `GDI32!CopyMetaFileW` at `0x18009f269`
- `GDI32!CopyMetaFileW` at `0x18009f269`
- `GDI32!GetMetaFileBitsEx` at `0x18009f29b`
- `GDI32!GetMetaFileBitsEx` at `0x18009f29b`

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
0x18009f1f4  mov     rax, rsp
0x18009f1f7  mov     [rax+8], rbx
0x18009f1fb  mov     [rax+10h], rbp
0x18009f1ff  mov     [rax+18h], rsi
0x18009f203  mov     [rax+20h], rdi
0x18009f207  push    r12
0x18009f209  push    r14
0x18009f20b  push    r15
0x18009f20d  sub     rsp, 20h
0x18009f211  mov     r15, this
0x18009f214  mov     r14d, fDelete
0x18009f217  mov     ecx, 3; cfFormat
0x18009f21c  mov     rdi, hMfp
0x18009f21f  call    ?VerifyStructFromHGlobal@@YAJGPEAX@Z; VerifyStructFromHGlobal(ushort,void *)
0x18009f224  mov     ebx, eax
0x18009f226  test    eax, eax
0x18009f228  js      loc_18009F318
0x18009f22e  mov     this, rdi; hMem
0x18009f231  call    cs:__imp_GlobalLock
0x18009f238  nop     dword ptr [rax+rax+00h]
0x18009f23d  mov     rsi, rax
0x18009f240  test    rax, rax
0x18009f243  jnz     short loc_18009F25B
0x18009f245  test    r14d, r14d
0x18009f248  jz      short loc_18009F27D
0x18009f24a  mov     this, rdi; hMem
0x18009f24d  call    cs:__imp_GlobalFree
0x18009f254  nop     dword ptr [rax+rax+00h]
0x18009f259  jmp     short loc_18009F27D
0x18009f25b  mov     rbp, [rax+10h]
0x18009f25f  test    r14d, r14d
0x18009f262  jnz     short loc_18009F287
0x18009f264  xor     edx, edx; LPCWSTR
0x18009f266  mov     this, rbp; HMETAFILE
0x18009f269  call    cs:__imp_CopyMetaFileW
0x18009f270  nop     dword ptr [rax+rax+00h]
0x18009f275  mov     rbp, rax
0x18009f278  test    rax, rax
0x18009f27b  jnz     short loc_18009F287
0x18009f27d  mov     eax, 8007000Eh
0x18009f282  jmp     loc_18009F318
0x18009f287  cmp     dword ptr [rsi], 8
0x18009f28a  jz      short loc_18009F293
0x18009f28c  mov     ebx, 80004005h
0x18009f291  jmp     short loc_18009F2E0
0x18009f293  xor     fDelete, fDelete; lpData
0x18009f296  xor     edx, edx; cbBuffer
0x18009f298  mov     this, rbp; hMF
0x18009f29b  call    cs:__imp_GetMetaFileBitsEx
0x18009f2a2  nop     dword ptr [rax+rax+00h]
0x18009f2a7  mov     r12d, eax
0x18009f2aa  test    eax, eax
0x18009f2ac  jnz     short loc_18009F2B5
0x18009f2ae  mov     ebx, 80040007h
0x18009f2b3  jmp     short loc_18009F2E0
0x18009f2b5  mov     this, [r15+10h]; hmf
0x18009f2b9  test    this, this
0x18009f2bc  jz      short loc_18009F2CA
0x18009f2be  call    cs:__imp_DeleteMetaFile
0x18009f2c5  nop     dword ptr [rax+rax+00h]
0x18009f2ca  mov     [r15+10h], rbp
0x18009f2ce  mov     [r15+5Ch], r12d
0x18009f2d2  mov     eax, [rsi+4]
0x18009f2d5  mov     [r15+60h], eax
0x18009f2d9  mov     eax, [rsi+8]
0x18009f2dc  mov     [r15+64h], eax
0x18009f2e0  mov     this, rdi; hMem
0x18009f2e3  call    cs:__imp_GlobalUnlock
0x18009f2ea  nop     dword ptr [rax+rax+00h]
0x18009f2ef  test    ebx, ebx
0x18009f2f1  jz      short loc_18009F302
0x18009f2f3  mov     this, rbp; hmf
0x18009f2f6  call    cs:__imp_DeleteMetaFile
0x18009f2fd  nop     dword ptr [rax+rax+00h]
0x18009f302  test    r14d, r14d
0x18009f305  jz      short loc_18009F316
0x18009f307  mov     this, rdi; hMem
0x18009f30a  call    cs:__imp_GlobalFree
0x18009f311  nop     dword ptr [rax+rax+00h]
0x18009f316  mov     eax, ebx
0x18009f318  mov     rbx, [rsp+38h+arg_0]
0x18009f31d  mov     rbp, [rsp+38h+arg_8]
0x18009f322  mov     rsi, [rsp+38h+arg_10]
0x18009f327  mov     rdi, [rsp+38h+arg_18]
0x18009f32c  add     rsp, 20h
0x18009f330  pop     r15
0x18009f332  pop     r14
0x18009f334  pop     r12
0x18009f336  retn
```
