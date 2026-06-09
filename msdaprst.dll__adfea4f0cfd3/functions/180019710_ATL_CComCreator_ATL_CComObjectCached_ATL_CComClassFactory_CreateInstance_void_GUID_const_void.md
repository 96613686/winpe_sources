# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180019710`
- end: `0x1800197b2`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001dd4`
- `0x18000a3d4`
- `0x180018ed8`
- `0x180019710`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // esi
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = MMMAlloc(0x20u, a2);
  v9 = v8;
  if ( v8 )
  {
    ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>((_DWORD *)v8 + 2);
    *(_QWORD *)v9 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    *((_QWORD *)v9 + 3) = a1;
    v7 = (**(__int64 (__fastcall ***)(unsigned __int8 *, __int64, _QWORD *))v9)(v9, a2, a3);
    if ( v7 )
      ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x180019710  mov     [rsp+arg_0], rbx
0x180019715  mov     [rsp+arg_8], rbp
0x18001971a  push    rsi
0x18001971b  push    rdi
0x18001971c  push    r14
0x18001971e  sub     rsp, 20h
0x180019722  mov     rdi, r8
0x180019725  mov     rbp, rdx
0x180019728  mov     r14, rcx
0x18001972b  test    r8, r8
0x18001972e  jnz     short loc_180019737
0x180019730  mov     eax, 80004003h
0x180019735  jmp     short loc_18001979E
0x180019737  mov     qword ptr [r8], 0
0x18001973e  mov     esi, 8007000Eh
0x180019743  mov     ecx, 20h ; ' '; unsigned int
0x180019748  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18001974d  mov     rbx, rax
0x180019750  mov     [rsp+38h+arg_10], rax
0x180019755  test    rax, rax
0x180019758  jz      short loc_18001976F
0x18001975a  lea     rcx, [rax+8]
0x18001975e  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x180019763  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18001976a  mov     [rbx], rax
0x18001976d  jmp     short loc_180019771
0x18001976f  xor     ebx, ebx
0x180019771  test    rbx, rbx
0x180019774  jz      short loc_18001979C
0x180019776  mov     [rbx+18h], r14
0x18001977a  mov     rax, [rbx]
0x18001977d  mov     r8, rdi
0x180019780  mov     rdx, rbp
0x180019783  mov     rcx, rbx
0x180019786  mov     rax, [rax]
0x180019789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001978e  mov     esi, eax
0x180019790  test    eax, eax
0x180019792  jz      short loc_18001979C
0x180019794  mov     rcx, rbx; void *
0x180019797  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x18001979c  mov     eax, esi
0x18001979e  mov     rbx, [rsp+38h+arg_0]
0x1800197a3  mov     rbp, [rsp+38h+arg_8]
0x1800197a8  add     rsp, 20h
0x1800197ac  pop     r14
0x1800197ae  pop     rdi
0x1800197af  pop     rsi
0x1800197b0  retn
```
