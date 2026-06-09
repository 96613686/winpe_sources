# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x1800130f4`
- end: `0x1800131d1`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `221`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, LCID lcid, int *)`
- caller_count: `10`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012fc0`
- `0x180012fe0`
- `0x180013000`
- `0x180013020`
- `0x180013040`
- `0x180013060`
- `0x180013080`
- `0x1800130a0`
- `0x1800130c0`
- `0x1800130e0`

## callees

- `0x1800130f4`
- `0x1800131d8`
- `0x18001f646`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetIDsOfNames(
        ATL::CComTypeInfoHolder *this,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        LCID lcid,
        int *a6)
{
  __int64 result; // rax
  __int64 v10; // r15
  __int64 v11; // rbp
  _WORD *v12; // r14
  __int64 v13; // rsi
  unsigned int v14; // ebx

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    result = 0;
  else
    result = ATL::CComTypeInfoHolder::GetTI(this, lcid);
  v10 = *((_QWORD *)this + 3);
  if ( v10 )
  {
    v11 = *((_QWORD *)this + 5);
    if ( v11 && a4 == 1 )
    {
      v12 = *a3;
      if ( *a3 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
      }
      else
      {
        LODWORD(v13) = 0;
      }
      v14 = *((_DWORD *)this + 12);
      while ( (--v14 & 0x80000000) == 0 )
      {
        if ( (_DWORD)v13 == *(_DWORD *)(v11 + 16LL * v14 + 8)
          && !memcmp_0(*(const void **)(v11 + 16LL * v14), v12, 2LL * *(int *)(v11 + 16LL * v14 + 8)) )
        {
          *a6 = *(_DWORD *)(v11 + 16LL * v14 + 12);
          return 0;
        }
      }
    }
    return (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, _QWORD, int *))(*(_QWORD *)v10 + 80LL))(
             v10,
             a3,
             a4,
             a6);
  }
  return result;
}

```

## disassembly

```asm
0x1800130f4  push    rbx
0x1800130f6  push    rbp
0x1800130f7  push    rsi
0x1800130f8  push    rdi
0x1800130f9  push    r12
0x1800130fb  push    r13
0x1800130fd  push    r14
0x1800130ff  push    r15
0x180013101  sub     rsp, 38h
0x180013105  xor     edx, edx
0x180013107  mov     r12d, r9d
0x18001310a  mov     r13, r8
0x18001310d  mov     rdi, rcx
0x180013110  cmp     [rcx+18h], rdx
0x180013114  jz      short loc_180013120
0x180013116  cmp     [rcx+28h], rdx
0x18001311a  jz      short loc_180013120
0x18001311c  mov     eax, edx
0x18001311e  jmp     short loc_18001312E
0x180013120  mov     edx, [rsp+78h+lcid]; lcid
0x180013127  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18001312c  xor     edx, edx
0x18001312e  mov     r15, [rdi+18h]
0x180013132  test    r15, r15
0x180013135  jz      short loc_1800131AE
0x180013137  mov     rbp, [rdi+28h]
0x18001313b  test    rbp, rbp
0x18001313e  jz      short loc_180013191
0x180013140  cmp     r12d, 1
0x180013144  jnz     short loc_180013191
0x180013146  mov     r14, [r13+0]
0x18001314a  test    r14, r14
0x18001314d  jnz     short loc_180013153
0x18001314f  mov     esi, edx
0x180013151  jmp     short loc_180013161
0x180013153  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180013157  inc     rsi
0x18001315a  cmp     [r14+rsi*2], dx
0x18001315f  jnz     short loc_180013157
0x180013161  mov     ebx, [rdi+30h]
0x180013164  jmp     short loc_18001318C
0x180013166  mov     edi, ebx
0x180013168  add     rdi, rdi
0x18001316b  cmp     esi, [rbp+rdi*8+8]
0x18001316f  jnz     short loc_18001318C
0x180013171  movsxd  r8, dword ptr [rbp+rdi*8+8]
0x180013176  mov     rdx, r14; Buf2
0x180013179  mov     rcx, [rbp+rdi*8+0]; Buf1
0x18001317e  add     r8, r8; Size
0x180013181  call    memcmp_0
0x180013186  xor     edx, edx
0x180013188  test    eax, eax
0x18001318a  jz      short loc_1800131BF
0x18001318c  sub     ebx, 1
0x18001318f  jns     short loc_180013166
0x180013191  mov     rax, [r15]
0x180013194  mov     r8d, r12d
0x180013197  mov     r9, [rsp+78h+arg_28]
0x18001319f  mov     rdx, r13
0x1800131a2  mov     rcx, r15
0x1800131a5  mov     rax, [rax+50h]
0x1800131a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131ae  add     rsp, 38h
0x1800131b2  pop     r15
0x1800131b4  pop     r14
0x1800131b6  pop     r13
0x1800131b8  pop     r12
0x1800131ba  pop     rdi
0x1800131bb  pop     rsi
0x1800131bc  pop     rbp
0x1800131bd  pop     rbx
0x1800131be  retn
0x1800131bf  mov     rax, [rsp+78h+arg_28]
0x1800131c7  mov     ecx, [rbp+rdi*8+0Ch]
0x1800131cb  mov     [rax], ecx
0x1800131cd  mov     eax, edx
0x1800131cf  jmp     short loc_1800131AE
```
