# ATL::CComObject<CPersistStreamInit>::CreateInstance(ATL::CComObject<CPersistStreamInit> * *)

- ea: `0x18001425c`
- end: `0x18001430e`
- name: `?CreateInstance@?$CComObject@VCPersistStreamInit@@@ATL@@SAJPEAPEAV12@@Z`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014bd0`

## callees

- `0x180001dd4`
- `0x18000a3d4`
- `0x18001425c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CPersistStreamInit>::CreateInstance(unsigned __int8 **a1, unsigned int a2)
{
  __int64 result; // rax
  unsigned __int8 *v4; // rax
  unsigned __int8 *v5; // rbx
  unsigned int v6; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v4 = MMMAlloc(0x2058u, a2);
  try
  {
    v5 = v4;
    if ( v4 )
    {
      ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>((_DWORD *)v4 + 2);
      *((_QWORD *)v5 + 3) = 0;
      *((_QWORD *)v5 + 4) = 0;
      *((_QWORD *)v5 + 5) = 0;
      *((_QWORD *)v5 + 6) = 0;
      *((_QWORD *)v5 + 7) = 0;
      *((_DWORD *)v5 + 2068) = 0;
      v5[64] = 1;
      *(_QWORD *)v5 = &ATL::CComObject<CPersistStreamInit>::`vftable';
      _InterlockedIncrement(&dword_1800464E8);
    }
    else
    {
      v5 = 0;
    }
    result = v5 == 0 ? 0x8007000E : 0;
    *a1 = v5;
  }
  catch ( long v6 )
  {
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18001425c  mov     [rsp+arg_8], rbx
0x180014261  push    rdi
0x180014262  sub     rsp, 30h
0x180014266  mov     rdi, rcx
0x180014269  test    rcx, rcx
0x18001426c  jnz     short loc_180014278
0x18001426e  mov     eax, 80004003h
0x180014273  jmp     loc_180014302
0x180014278  mov     qword ptr [rcx], 0
0x18001427f  mov     ecx, 2058h; unsigned int
0x180014284  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180014289  mov     rbx, rax
0x18001428c  mov     [rsp+38h+arg_0], rax
0x180014291  test    rax, rax
0x180014294  jz      short loc_1800142E8
0x180014296  lea     rcx, [rax+8]
0x18001429a  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x18001429f  mov     qword ptr [rbx+18h], 0
0x1800142a7  mov     qword ptr [rbx+20h], 0
0x1800142af  mov     qword ptr [rbx+28h], 0
0x1800142b7  mov     qword ptr [rbx+30h], 0
0x1800142bf  mov     qword ptr [rbx+38h], 0
0x1800142c7  mov     dword ptr [rbx+2050h], 0
0x1800142d1  mov     byte ptr [rbx+40h], 1
0x1800142d5  lea     rax, ??_7?$CComObject@VCPersistStreamInit@@@ATL@@6B@; const ATL::CComObject<CPersistStreamInit>::`vftable'
0x1800142dc  mov     [rbx], rax
0x1800142df  lock inc cs:dword_1800464E8
0x1800142e6  jmp     short loc_1800142EA
0x1800142e8  xor     ebx, ebx
0x1800142ea  mov     rax, rbx
0x1800142ed  neg     rax
0x1800142f0  sbb     eax, eax
0x1800142f2  not     eax
0x1800142f4  and     eax, 8007000Eh
0x1800142f9  mov     [rdi], rbx
0x1800142fc  jmp     short loc_180014302
0x1800142fe  mov     eax, [rsp+38h+var_18]
0x180014302  mov     rbx, [rsp+38h+arg_8]
0x180014307  add     rsp, 30h
0x18001430b  pop     rdi
0x18001430c  retn
```
