# ATL::CComAggObject<CExtractIcon>::Release(void)

- ea: `0x180005aa0`
- end: `0x180005b1b`
- name: `?Release@?$CComAggObject@VCExtractIcon@@@ATL@@UEAAKXZ`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005aa0`
- `0x18000931c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005b01`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005b01`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CExtractIcon>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi
  CStr *v4; // rcx

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
        *(_QWORD *)a1 = &ATL::CComAggObject<CExtractIcon>::`vftable';
        v4 = (CStr *)(a1 + 10);
        _InterlockedDecrement(&dword_180012EE8);
        *(_QWORD *)v4 = &CStr::`vftable';
        CStr::Empty(v4);
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
0x180005aa0  mov     [rsp+arg_0], rbx
0x180005aa5  push    rdi
0x180005aa6  sub     rsp, 20h
0x180005aaa  mov     edi, [rcx+8]
0x180005aad  mov     rbx, rcx
0x180005ab0  cmp     edi, 7FFFFFFFh
0x180005ab6  jnz     short loc_180005ABF
0x180005ab8  mov     edi, 7FFFFFFEh
0x180005abd  jmp     short loc_180005B0E
0x180005abf  sub     edi, 1
0x180005ac2  mov     [rcx+8], edi
0x180005ac5  jnz     short loc_180005B0E
0x180005ac7  lock inc cs:dword_180012EE8
0x180005ace  test    rbx, rbx
0x180005ad1  jz      short loc_180005B07
0x180005ad3  mov     dword ptr [rcx+8], 1
0x180005ada  lea     rax, ??_7?$CComAggObject@VCExtractIcon@@@ATL@@6B@; const ATL::CComAggObject<CExtractIcon>::`vftable'
0x180005ae1  mov     [rcx], rax
0x180005ae4  add     rcx, 28h ; '('; this
0x180005ae8  lock dec cs:dword_180012EE8
0x180005aef  lea     rax, ??_7CStr@@6B@; const CStr::`vftable'
0x180005af6  mov     [rcx], rax
0x180005af9  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180005afe  mov     rcx, rbx
0x180005b01  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005b07  lock dec cs:dword_180012EE8
0x180005b0e  mov     rbx, [rsp+28h+arg_0]
0x180005b13  mov     eax, edi
0x180005b15  add     rsp, 20h
0x180005b19  pop     rdi
0x180005b1a  retn
```
