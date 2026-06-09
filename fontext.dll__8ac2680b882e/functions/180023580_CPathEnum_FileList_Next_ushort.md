# CPathEnum_FileList::Next(ushort * *)

- ea: `0x180023580`
- end: `0x18002367e`
- name: `?Next@CPathEnum_FileList@@UEAAJPEAPEAG@Z`
- size: `254`
- prototype: `int(CPathEnum_FileList *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180006624`
- `0x180007980`
- `0x1800127b8`
- `0x180023580`
- `0x180031070`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x18002361d`
- `SHLWAPI!SHStrDupW` at `0x18002361d`
- `SHLWAPI!PathCombineW` at `0x1800235e3`
- `SHLWAPI!PathCombineW` at `0x1800235e3`

## pseudocode

```c
__int64 __fastcall CPathEnum_FileList::Next(CPathEnum_FileList *this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rsi
  const WCHAR *v5; // rdx
  unsigned int v6; // edi
  const WCHAR *v7; // r8
  DWORD nLength[4]; // [rsp+20h] [rbp-248h] BYREF
  WCHAR pszDest[264]; // [rsp+30h] [rbp-238h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    v4 = (unsigned __int16 *)((char *)this + 12);
    v5 = (const WCHAR *)*((_QWORD *)this + 68);
    *((_WORD *)this + 6) = 0;
    v6 = 1;
    if ( v5 )
    {
      v7 = (const WCHAR *)*((_QWORD *)this + 67);
      if ( v7 )
      {
        PathCombineW(pszDest, v5, v7);
        nLength[0] = 260;
        if ( (int)GetRemotePath(pszDest, v4, nLength) < 0 )
          StringCchCopyW(v4, 0x104u, pszDest);
        v6 = SHStrDupW(v4, a2);
      }
    }
    if ( !CDblNulStrIter::Next((CPathEnum_FileList *)((char *)this + 560), (const unsigned __int16 **)this + 67) )
    {
      *((_QWORD *)this + 68) = 0;
      *((_QWORD *)this + 67) = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180023580  mov     [rsp+arg_10], rbx
0x180023585  push    rsi
0x180023586  push    rdi
0x180023587  push    r14
0x180023589  sub     rsp, 250h
0x180023590  mov     rax, cs:__security_cookie
0x180023597  xor     rax, rsp
0x18002359a  mov     [rsp+268h+var_28], rax
0x1800235a2  mov     r14, rdx
0x1800235a5  mov     rbx, rcx
0x1800235a8  test    rdx, rdx
0x1800235ab  jz      loc_180023653
0x1800235b1  mov     qword ptr [rdx], 0
0x1800235b8  lea     rsi, [rcx+0Ch]
0x1800235bc  mov     rdx, [rcx+220h]; pszDir
0x1800235c3  xor     eax, eax
0x1800235c5  mov     [rsi], ax
0x1800235c8  mov     edi, 1
0x1800235cd  test    rdx, rdx
0x1800235d0  jz      short loc_180023625
0x1800235d2  mov     r8, [rcx+218h]; pszFile
0x1800235d9  test    r8, r8
0x1800235dc  jz      short loc_180023625
0x1800235de  lea     rcx, [rsp+268h+pszDest]; pszDest
0x1800235e3  call    cs:__imp_PathCombineW
0x1800235e9  mov     edi, 104h
0x1800235ee  lea     r8, [rsp+268h+nLength]; lpnLength
0x1800235f3  mov     rdx, rsi; unsigned __int16 *
0x1800235f6  mov     [rsp+268h+nLength], edi
0x1800235fa  lea     rcx, [rsp+268h+pszDest]; unsigned __int16 *
0x1800235ff  call    ?GetRemotePath@@YAJPEBGPEAGPEAK@Z; GetRemotePath(ushort const *,ushort *,ulong *)
0x180023604  test    eax, eax
0x180023606  jns     short loc_180023617
0x180023608  lea     r8, [rsp+268h+pszDest]; unsigned __int16 *
0x18002360d  mov     edx, edi; unsigned __int64
0x18002360f  mov     rcx, rsi; unsigned __int16 *
0x180023612  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023617  mov     rdx, r14; ppwsz
0x18002361a  mov     rcx, rsi; psz
0x18002361d  call    cs:__imp_SHStrDupW
0x180023623  mov     edi, eax
0x180023625  lea     rsi, [rbx+218h]
0x18002362c  mov     rdx, rsi; unsigned __int16 **
0x18002362f  lea     rcx, [rbx+230h]; this
0x180023636  call    ?Next@CDblNulStrIter@@QEAA_NPEAPEBG@Z; CDblNulStrIter::Next(ushort const * *)
0x18002363b  test    al, al
0x18002363d  jnz     short loc_180023658
0x18002363f  mov     qword ptr [rbx+220h], 0
0x18002364a  mov     qword ptr [rsi], 0
0x180023651  jmp     short loc_180023658
0x180023653  mov     edi, 80070057h
0x180023658  mov     eax, edi
0x18002365a  mov     rcx, [rsp+268h+var_28]
0x180023662  xor     rcx, rsp; StackCookie
0x180023665  call    __security_check_cookie
0x18002366a  mov     rbx, [rsp+268h+arg_10]
0x180023672  add     rsp, 250h
0x180023679  pop     r14
0x18002367b  pop     rdi
0x18002367c  pop     rsi
0x18002367d  retn
```
