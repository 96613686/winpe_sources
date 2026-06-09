# ATL::CComObject<CHHCollectionWrapper>::Release(void)

- ea: `0x180005ca0`
- end: `0x180005d12`
- name: `?Release@?$CComObject@VCHHCollectionWrapper@@@ATL@@UEAAKXZ`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180005ca0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005cf8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005cf8`
- `hhsetup!??1CCollection@@QEAA@XZ` at `0x180005cef`
- `hhsetup!??1CCollection@@QEAA@XZ` at `0x180005cef`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CHHCollectionWrapper>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi

  v1 = a1[2];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[2] = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_180012EE8);
      if ( a1 )
      {
        a1[2] = 1;
        *(_QWORD *)a1 = &ATL::CComObject<CHHCollectionWrapper>::`vftable';
        _InterlockedDecrement(&dword_180012EE8);
        CCollection::~CCollection((CCollection *)(a1 + 4));
        operator delete(a1);
      }
      _InterlockedDecrement(&dword_180012EE8);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180005ca0  mov     [rsp+arg_0], rbx
0x180005ca5  push    rdi
0x180005ca6  sub     rsp, 20h
0x180005caa  mov     edi, [rcx+8]
0x180005cad  mov     rbx, rcx
0x180005cb0  cmp     edi, 7FFFFFFFh
0x180005cb6  jnz     short loc_180005CBF
0x180005cb8  mov     edi, 7FFFFFFEh
0x180005cbd  jmp     short loc_180005D05
0x180005cbf  sub     edi, 1
0x180005cc2  mov     [rcx+8], edi
0x180005cc5  jnz     short loc_180005D05
0x180005cc7  lock inc cs:dword_180012EE8
0x180005cce  test    rbx, rbx
0x180005cd1  jz      short loc_180005CFE
0x180005cd3  mov     dword ptr [rcx+8], 1
0x180005cda  lea     rax, ??_7?$CComObject@VCHHCollectionWrapper@@@ATL@@6B@; const ATL::CComObject<CHHCollectionWrapper>::`vftable'
0x180005ce1  mov     [rcx], rax
0x180005ce4  add     rcx, 10h
0x180005ce8  lock dec cs:dword_180012EE8
0x180005cef  call    cs:__imp_??1CCollection@@QEAA@XZ; CCollection::~CCollection(void)
0x180005cf5  mov     rcx, rbx
0x180005cf8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005cfe  lock dec cs:dword_180012EE8
0x180005d05  mov     rbx, [rsp+28h+arg_0]
0x180005d0a  mov     eax, edi
0x180005d0c  add     rsp, 20h
0x180005d10  pop     rdi
0x180005d11  retn
```
