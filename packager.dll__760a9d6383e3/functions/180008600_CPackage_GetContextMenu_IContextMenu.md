# CPackage::GetContextMenu(IContextMenu * *)

- ea: `0x180008600`
- end: `0x180008745`
- name: `?GetContextMenu@CPackage@@IEAAJPEAPEAUIContextMenu@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct IContextMenu **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800050b0`
- `0x180005470`

## callees

- `0x1800079ac`
- `0x180008600`
- `0x18000e010`

## import_xrefs

- `SHELL32!SHBindToParent` at `0x1800086b7`
- `SHELL32!SHBindToParent` at `0x1800086b7`
- `SHELL32!__imp_ILFree` at `0x180008728`
- `SHELL32!__imp_ILFree` at `0x180008728`
- `SHELL32!__imp_SHSimpleIDListFromPath` at `0x18000867f`
- `SHELL32!__imp_SHSimpleIDListFromPath` at `0x18000867f`

## pseudocode

```c
__int64 __fastcall CPackage::GetContextMenu(CPackage *this, struct IContextMenu **a2)
{
  _QWORD *v2; // rsi
  __int64 v4; // rcx
  HRESULT TempFileName; // ebx
  const WCHAR *v7; // rcx
  const ITEMIDLIST *v8; // rax
  ITEMIDLIST *v9; // rdi
  void *ppv; // [rsp+60h] [rbp+8h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+70h] [rbp+18h] BYREF

  v2 = (_QWORD *)((char *)this + 232);
  v4 = *((_QWORD *)this + 29);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    TempFileName = 0;
    *a2 = (struct IContextMenu *)*v2;
  }
  else
  {
    if ( *((_DWORD *)this + 26) == 3 )
    {
      TempFileName = CPackage::CreateTempFileName(this);
      if ( TempFileName < 0 )
        return (unsigned int)TempFileName;
    }
    else
    {
      TempFileName = -2147467259;
      if ( *((_DWORD *)this + 26) != 1 )
        return (unsigned int)TempFileName;
    }
    if ( *((_DWORD *)this + 26) == 3 )
      v7 = *(const WCHAR **)(*((_QWORD *)this + 14) + 592LL);
    else
      v7 = (const WCHAR *)(*((_QWORD *)this + 15) + 4LL);
    v8 = SHSimpleIDListFromPath(v7);
    v9 = (ITEMIDLIST *)v8;
    if ( v8 )
    {
      ppv = 0;
      ppidlLast = 0;
      TempFileName = SHBindToParent(v8, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
      if ( TempFileName >= 0 )
      {
        TempFileName = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, LPCITEMIDLIST *, GUID *, _QWORD, _QWORD *))(*(_QWORD *)ppv + 80LL))(
                         ppv,
                         0,
                         1,
                         &ppidlLast,
                         &IID_IContextMenu,
                         0,
                         v2);
        if ( TempFileName >= 0 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 8LL))(*v2);
          *a2 = (struct IContextMenu *)*v2;
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      ILFree(v9);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)TempFileName;
}

```

## disassembly

```asm
0x180008600  mov     [rsp+arg_8], rbx
0x180008605  push    rsi
0x180008606  push    rdi
0x180008607  push    r14
0x180008609  sub     rsp, 40h
0x18000860d  lea     rsi, [rcx+0E8h]
0x180008614  mov     rdi, rcx
0x180008617  mov     rcx, [rsi]
0x18000861a  mov     r14, rdx
0x18000861d  test    rcx, rcx
0x180008620  jz      short loc_18000863B
0x180008622  mov     rax, [rcx]
0x180008625  mov     rax, [rax+8]
0x180008629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000862e  mov     rax, [rsi]
0x180008631  xor     ebx, ebx
0x180008633  mov     [r14], rax
0x180008636  jmp     loc_180008735
0x18000863b  cmp     dword ptr [rdi+68h], 3
0x18000863f  jz      short loc_180008652
0x180008641  cmp     dword ptr [rdi+68h], 1
0x180008645  mov     ebx, 80004005h
0x18000864a  jnz     loc_180008735
0x180008650  jmp     short loc_180008664
0x180008652  mov     rcx, rdi; this
0x180008655  call    ?CreateTempFileName@CPackage@@IEAAJXZ; CPackage::CreateTempFileName(void)
0x18000865a  mov     ebx, eax
0x18000865c  test    eax, eax
0x18000865e  js      loc_180008735
0x180008664  cmp     dword ptr [rdi+68h], 3
0x180008668  jnz     short loc_180008677
0x18000866a  mov     rax, [rdi+70h]
0x18000866e  mov     rcx, [rax+250h]
0x180008675  jmp     short loc_18000867F
0x180008677  mov     rcx, [rdi+78h]
0x18000867b  add     rcx, 4; pszPath
0x18000867f  call    cs:__imp_SHSimpleIDListFromPath
0x180008685  mov     rdi, rax
0x180008688  test    rax, rax
0x18000868b  jz      loc_180008730
0x180008691  lea     r9, [rsp+58h+ppidlLast]; ppidlLast
0x180008696  mov     [rsp+58h+ppv], 0
0x18000869f  lea     r8, [rsp+58h+ppv]; ppv
0x1800086a4  mov     [rsp+58h+ppidlLast], 0
0x1800086ad  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x1800086b4  mov     rcx, rax; pidl
0x1800086b7  call    cs:__imp_SHBindToParent
0x1800086bd  mov     ebx, eax
0x1800086bf  test    eax, eax
0x1800086c1  js      short loc_180008725
0x1800086c3  mov     rcx, [rsp+58h+ppv]
0x1800086c8  lea     rdx, IID_IContextMenu
0x1800086cf  mov     [rsp+58h+var_28], rsi
0x1800086d4  lea     r9, [rsp+58h+ppidlLast]
0x1800086d9  mov     [rsp+58h+var_30], 0
0x1800086e2  mov     [rsp+58h+var_38], rdx
0x1800086e7  xor     edx, edx
0x1800086e9  mov     rax, [rcx]
0x1800086ec  lea     r8d, [rdx+1]
0x1800086f0  mov     rax, [rax+50h]
0x1800086f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086f9  mov     ebx, eax
0x1800086fb  test    eax, eax
0x1800086fd  js      short loc_180008714
0x1800086ff  mov     rcx, [rsi]
0x180008702  mov     rax, [rcx]
0x180008705  mov     rax, [rax+8]
0x180008709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000870e  mov     rax, [rsi]
0x180008711  mov     [r14], rax
0x180008714  mov     rcx, [rsp+58h+ppv]
0x180008719  mov     rax, [rcx]
0x18000871c  mov     rax, [rax+10h]
0x180008720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008725  mov     rcx, rdi; pidl
0x180008728  call    cs:__imp_ILFree
0x18000872e  jmp     short loc_180008735
0x180008730  mov     ebx, 8007000Eh
0x180008735  mov     eax, ebx
0x180008737  mov     rbx, [rsp+58h+arg_8]
0x18000873c  add     rsp, 40h
0x180008740  pop     r14
0x180008742  pop     rdi
0x180008743  pop     rsi
0x180008744  retn
```
