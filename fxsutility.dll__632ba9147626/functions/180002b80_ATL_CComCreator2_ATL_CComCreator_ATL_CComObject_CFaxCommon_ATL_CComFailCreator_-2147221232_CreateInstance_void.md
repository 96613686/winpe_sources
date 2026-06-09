# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CFaxCommon>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002b80`
- end: `0x180002c40`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCFaxCommon@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001284`
- `0x1800012d0`
- `0x180002b80`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CFaxCommon>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  _QWORD *v6; // rax
  _DWORD *v7; // rdi

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      return (unsigned int)-2147221232;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v5 = -2147024882;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 2) = 0;
    *v6 = &ATL::CComObject<CFaxCommon>::`vftable';
    _InterlockedIncrement(&dword_18001EB58);
    v5 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v6)(v6, a2, a3);
    if ( v5 )
    {
      *(_QWORD *)v7 = &ATL::CComObject<CFaxCommon>::`vftable';
      v7[2] = 1;
      _InterlockedDecrement(&dword_18001EB58);
      operator delete(v7);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180002b80  mov     [rsp+arg_8], rbx
0x180002b85  mov     [rsp+arg_10], rbp
0x180002b8a  push    rsi
0x180002b8b  push    rdi
0x180002b8c  push    r15
0x180002b8e  sub     rsp, 20h
0x180002b92  mov     rsi, r8
0x180002b95  mov     rbp, rdx
0x180002b98  test    rcx, rcx
0x180002b9b  jnz     short loc_180002C13
0x180002b9d  test    r8, r8
0x180002ba0  jz      short loc_180002C18
0x180002ba2  mov     [r8], rcx
0x180002ba5  mov     ebx, 8007000Eh
0x180002baa  mov     ecx, 10h; Size
0x180002baf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002bb4  mov     [rsp+38h+arg_0], rax
0x180002bb9  mov     rdi, rax
0x180002bbc  test    rax, rax
0x180002bbf  jz      short loc_180002C2B
0x180002bc1  lea     r15, ??_7?$CComObject@VCFaxCommon@@@ATL@@6B@; const ATL::CComObject<CFaxCommon>::`vftable'
0x180002bc8  mov     dword ptr [rax+8], 0
0x180002bcf  mov     [rax], r15
0x180002bd2  lock inc cs:dword_18001EB58
0x180002bd9  test    rax, rax
0x180002bdc  jz      short loc_180002C2B
0x180002bde  mov     rax, [rax]
0x180002be1  mov     r8, rsi
0x180002be4  mov     rdx, rbp
0x180002be7  mov     rcx, rdi
0x180002bea  mov     rax, [rax]
0x180002bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf2  mov     ebx, eax
0x180002bf4  test    eax, eax
0x180002bf6  jz      short loc_180002C2B
0x180002bf8  mov     [rdi], r15
0x180002bfb  mov     rcx, rdi; Block
0x180002bfe  mov     dword ptr [rdi+8], 1
0x180002c05  lock dec cs:dword_18001EB58
0x180002c0c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002c11  jmp     short loc_180002C2B
0x180002c13  test    rsi, rsi
0x180002c16  jnz     short loc_180002C1F
0x180002c18  mov     ebx, 80004003h
0x180002c1d  jmp     short loc_180002C2B
0x180002c1f  mov     qword ptr [r8], 0
0x180002c26  mov     ebx, 80040110h
0x180002c2b  mov     rbp, [rsp+38h+arg_10]
0x180002c30  mov     eax, ebx
0x180002c32  mov     rbx, [rsp+38h+arg_8]
0x180002c37  add     rsp, 20h
0x180002c3b  pop     r15
0x180002c3d  pop     rdi
0x180002c3e  pop     rsi
0x180002c3f  retn
```
