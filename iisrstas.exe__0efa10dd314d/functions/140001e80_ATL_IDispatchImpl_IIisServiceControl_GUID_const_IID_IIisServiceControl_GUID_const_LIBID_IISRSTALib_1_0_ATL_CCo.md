# ATL::IDispatchImpl<IIisServiceControl,&_GUID const IID_IIisServiceControl,&_GUID const LIBID_IISRSTALib,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x140001e80`
- end: `0x140001f6c`
- name: `?GetIDsOfNames@?$IDispatchImpl@UIIisServiceControl@@$1?IID_IIisServiceControl@@3U_GUID@@B$1?LIBID_IISRSTALib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140001e80`
- `0x1400020ec`
- `0x140005476`
- `0x140006010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IIisServiceControl,&_GUID const IID_IIisServiceControl,&_GUID const LIBID_IISRSTALib,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(
        struct ITypeInfo *a1,
        __int64 a2,
        const void **a3,
        unsigned int a4,
        LCID a5,
        _DWORD *a6)
{
  struct ITypeInfo *v6; // r14
  __int64 v9; // rbx
  __int64 result; // rax
  _WORD *v11; // r15
  __int64 v12; // rsi
  unsigned int v13; // ebp

  v6 = qword_14000A0A8;
  if ( !qword_14000A0A8 || (v9 = qword_14000A0B8, result = 0, !qword_14000A0B8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(a1, a5);
    v9 = qword_14000A0B8;
    v6 = qword_14000A0A8;
  }
  if ( v6 )
  {
    if ( v9 && a4 == 1 )
    {
      v11 = *a3;
      if ( *a3 )
      {
        v12 = -1;
        do
          ++v12;
        while ( v11[v12] );
      }
      else
      {
        LODWORD(v12) = 0;
      }
      v13 = dword_14000A0C0;
      while ( (--v13 & 0x80000000) == 0 )
      {
        if ( (_DWORD)v12 == *(_DWORD *)(v9 + 16LL * v13 + 8)
          && !memcmp_0(*(const void **)(v9 + 16LL * v13), v11, 2LL * *(int *)(v9 + 16LL * v13 + 8)) )
        {
          *a6 = *(_DWORD *)(v9 + 16LL * v13 + 12);
          return 0;
        }
      }
    }
    return ((__int64 (__fastcall *)(struct ITypeInfo *, const void **, _QWORD, _DWORD *))v6->lpVtbl->GetIDsOfNames)(
             v6,
             a3,
             a4,
             a6);
  }
  return result;
}

```

## disassembly

```asm
0x140001e80  push    rbx
0x140001e82  push    rbp
0x140001e83  push    rsi
0x140001e84  push    rdi
0x140001e85  push    r12
0x140001e87  push    r13
0x140001e89  push    r14
0x140001e8b  push    r15
0x140001e8d  sub     rsp, 38h
0x140001e91  mov     r14, cs:qword_14000A0A8
0x140001e98  xor     edx, edx
0x140001e9a  mov     r12d, r9d
0x140001e9d  mov     r13, r8
0x140001ea0  test    r14, r14
0x140001ea3  jz      short loc_140001EB3
0x140001ea5  mov     rbx, cs:qword_14000A0B8
0x140001eac  mov     eax, edx
0x140001eae  test    rbx, rbx
0x140001eb1  jnz     short loc_140001ECF
0x140001eb3  mov     edx, [rsp+78h+arg_20]; unsigned int
0x140001eba  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x140001ebf  mov     rbx, cs:qword_14000A0B8
0x140001ec6  xor     edx, edx
0x140001ec8  mov     r14, cs:qword_14000A0A8
0x140001ecf  test    r14, r14
0x140001ed2  jz      short loc_140001F49
0x140001ed4  test    rbx, rbx
0x140001ed7  jz      short loc_140001F2C
0x140001ed9  cmp     r12d, 1
0x140001edd  jnz     short loc_140001F2C
0x140001edf  mov     r15, [r13+0]
0x140001ee3  test    r15, r15
0x140001ee6  jnz     short loc_140001EEC
0x140001ee8  mov     esi, edx
0x140001eea  jmp     short loc_140001EFA
0x140001eec  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140001ef0  inc     rsi
0x140001ef3  cmp     [r15+rsi*2], dx
0x140001ef8  jnz     short loc_140001EF0
0x140001efa  mov     ebp, cs:dword_14000A0C0
0x140001f00  jmp     short loc_140001F27
0x140001f02  mov     edi, ebp
0x140001f04  add     rdi, rdi
0x140001f07  cmp     esi, [rbx+rdi*8+8]
0x140001f0b  jnz     short loc_140001F27
0x140001f0d  movsxd  r8, dword ptr [rbx+rdi*8+8]
0x140001f12  mov     rdx, r15; Buf2
0x140001f15  mov     rcx, [rbx+rdi*8]; Buf1
0x140001f19  add     r8, r8; Size
0x140001f1c  call    memcmp_0
0x140001f21  xor     edx, edx
0x140001f23  test    eax, eax
0x140001f25  jz      short loc_140001F5A
0x140001f27  sub     ebp, 1
0x140001f2a  jns     short loc_140001F02
0x140001f2c  mov     rax, [r14]
0x140001f2f  mov     r8d, r12d
0x140001f32  mov     r9, [rsp+78h+arg_28]
0x140001f3a  mov     rdx, r13
0x140001f3d  mov     rcx, r14
0x140001f40  mov     rax, [rax+50h]
0x140001f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001f49  add     rsp, 38h
0x140001f4d  pop     r15
0x140001f4f  pop     r14
0x140001f51  pop     r13
0x140001f53  pop     r12
0x140001f55  pop     rdi
0x140001f56  pop     rsi
0x140001f57  pop     rbp
0x140001f58  pop     rbx
0x140001f59  retn
0x140001f5a  mov     rax, [rsp+78h+arg_28]
0x140001f62  mov     ecx, [rbx+rdi*8+0Ch]
0x140001f66  mov     [rax], ecx
0x140001f68  mov     eax, edx
0x140001f6a  jmp     short loc_140001F49
```
