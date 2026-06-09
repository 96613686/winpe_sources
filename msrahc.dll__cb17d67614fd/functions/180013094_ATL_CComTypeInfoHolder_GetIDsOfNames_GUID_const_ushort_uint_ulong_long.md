# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180013094`
- end: `0x180013167`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `211`
- prototype: `int __fastcall(ATL::CComTypeInfoHolder *this, const struct _GUID *, const unsigned __int16 **, unsigned int, unsigned int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013170`

## callees

- `0x18000c504`
- `0x180013094`
- `0x18001317c`
- `0x18001a596`
- `0x18001c010`

## pseudocode

```c
int __fastcall ATL::CComTypeInfoHolder::GetIDsOfNames(
        ATL::CComTypeInfoHolder *this,
        const struct _GUID *a2,
        const unsigned __int16 **a3,
        unsigned int a4,
        unsigned int a5,
        int *a6)
{
  struct ITypeInfo *v6; // rdi
  __int64 v9; // rbx
  int result; // eax
  int v11; // eax
  int v12; // ebp
  int v13; // r12d

  v6 = qword_1800270F8;
  if ( !qword_1800270F8 || (v9 = qword_180027108, result = 0, !qword_180027108) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(this, a5);
    v9 = qword_180027108;
    v6 = qword_1800270F8;
  }
  if ( v6 )
  {
    if ( v9 && a4 == 1 )
    {
      v11 = ocslen(*a3);
      v12 = dword_180027110;
      v13 = v11;
      while ( --v12 >= 0 )
      {
        if ( v13 == *(_DWORD *)(v9 + 16LL * v12 + 8)
          && !memcmp_0(*(const void **)(v9 + 16LL * v12), *a3, 2LL * *(int *)(v9 + 16LL * v12 + 8)) )
        {
          *a6 = *(_DWORD *)(v9 + 16LL * v12 + 12);
          return 0;
        }
      }
    }
    return ((__int64 (__fastcall *)(struct ITypeInfo *, const unsigned __int16 **, _QWORD, int *))v6->lpVtbl->GetIDsOfNames)(
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
0x180013094  push    rbx
0x180013096  push    rbp
0x180013097  push    rsi
0x180013098  push    rdi
0x180013099  push    r12
0x18001309b  push    r14
0x18001309d  push    r15
0x18001309f  sub     rsp, 30h
0x1800130a3  mov     rdi, cs:qword_1800270F8
0x1800130aa  mov     r14d, r9d
0x1800130ad  mov     r15, r8
0x1800130b0  test    rdi, rdi
0x1800130b3  jz      short loc_1800130C3
0x1800130b5  mov     rbx, cs:qword_180027108
0x1800130bc  xor     eax, eax
0x1800130be  test    rbx, rbx
0x1800130c1  jnz     short loc_1800130DD
0x1800130c3  mov     edx, [rsp+68h+arg_20]; unsigned int
0x1800130ca  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800130cf  mov     rbx, cs:qword_180027108
0x1800130d6  mov     rdi, cs:qword_1800270F8
0x1800130dd  test    rdi, rdi
0x1800130e0  jz      short loc_180013158
0x1800130e2  test    rbx, rbx
0x1800130e5  jz      short loc_18001313B
0x1800130e7  cmp     r14d, 1
0x1800130eb  jnz     short loc_18001313B
0x1800130ed  mov     rcx, [r15]; unsigned __int16 *
0x1800130f0  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x1800130f5  mov     ebp, cs:dword_180027110
0x1800130fb  mov     r12d, eax
0x1800130fe  dec     ebp
0x180013100  test    ebp, ebp
0x180013102  js      short loc_18001313B
0x180013104  movsxd  rsi, ebp
0x180013107  add     rsi, rsi
0x18001310a  cmp     r12d, [rbx+rsi*8+8]
0x18001310f  jnz     short loc_1800130FE
0x180013111  movsxd  r8, dword ptr [rbx+rsi*8+8]
0x180013116  mov     rdx, [r15]; Buf2
0x180013119  add     r8, r8; Size
0x18001311c  mov     rcx, [rbx+rsi*8]; Buf1
0x180013120  call    memcmp_0
0x180013125  test    eax, eax
0x180013127  jnz     short loc_1800130FE
0x180013129  mov     rax, [rsp+68h+arg_28]
0x180013131  mov     ecx, [rbx+rsi*8+0Ch]
0x180013135  mov     [rax], ecx
0x180013137  xor     eax, eax
0x180013139  jmp     short loc_180013158
0x18001313b  mov     rax, [rdi]
0x18001313e  mov     r8d, r14d
0x180013141  mov     r9, [rsp+68h+arg_28]
0x180013149  mov     rdx, r15
0x18001314c  mov     rcx, rdi
0x18001314f  mov     rax, [rax+50h]
0x180013153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013158  add     rsp, 30h
0x18001315c  pop     r15
0x18001315e  pop     r14
0x180013160  pop     r12
0x180013162  pop     rdi
0x180013163  pop     rsi
0x180013164  pop     rbp
0x180013165  pop     rbx
0x180013166  retn
```
