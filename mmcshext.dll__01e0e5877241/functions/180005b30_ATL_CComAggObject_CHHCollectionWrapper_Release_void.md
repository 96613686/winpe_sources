# ATL::CComAggObject<CHHCollectionWrapper>::Release(void)

- ea: `0x180005b30`
- end: `0x180005ba2`
- name: `?Release@?$CComAggObject@VCHHCollectionWrapper@@@ATL@@UEAAKXZ`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180005b30`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005b88`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005b88`
- `hhsetup!??1CCollection@@QEAA@XZ` at `0x180005b7f`
- `hhsetup!??1CCollection@@QEAA@XZ` at `0x180005b7f`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CHHCollectionWrapper>::Release(_DWORD *a1)
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
        *(_QWORD *)a1 = &ATL::CComAggObject<CHHCollectionWrapper>::`vftable';
        _InterlockedDecrement(&dword_180012EE8);
        CCollection::~CCollection((CCollection *)(a1 + 8));
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
0x180005b30  mov     [rsp+arg_0], rbx
0x180005b35  push    rdi
0x180005b36  sub     rsp, 20h
0x180005b3a  mov     edi, [rcx+8]
0x180005b3d  mov     rbx, rcx
0x180005b40  cmp     edi, 7FFFFFFFh
0x180005b46  jnz     short loc_180005B4F
0x180005b48  mov     edi, 7FFFFFFEh
0x180005b4d  jmp     short loc_180005B95
0x180005b4f  sub     edi, 1
0x180005b52  mov     [rcx+8], edi
0x180005b55  jnz     short loc_180005B95
0x180005b57  lock inc cs:dword_180012EE8
0x180005b5e  test    rbx, rbx
0x180005b61  jz      short loc_180005B8E
0x180005b63  mov     dword ptr [rcx+8], 1
0x180005b6a  lea     rax, ??_7?$CComAggObject@VCHHCollectionWrapper@@@ATL@@6B@; const ATL::CComAggObject<CHHCollectionWrapper>::`vftable'
0x180005b71  mov     [rcx], rax
0x180005b74  add     rcx, 20h ; ' '
0x180005b78  lock dec cs:dword_180012EE8
0x180005b7f  call    cs:__imp_??1CCollection@@QEAA@XZ; CCollection::~CCollection(void)
0x180005b85  mov     rcx, rbx
0x180005b88  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005b8e  lock dec cs:dword_180012EE8
0x180005b95  mov     rbx, [rsp+28h+arg_0]
0x180005b9a  mov     eax, edi
0x180005b9c  add     rsp, 20h
0x180005ba0  pop     rdi
0x180005ba1  retn
```
