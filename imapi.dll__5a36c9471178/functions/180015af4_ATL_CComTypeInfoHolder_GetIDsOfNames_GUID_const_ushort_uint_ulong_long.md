# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180015af4`
- end: `0x180015bd1`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `221`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, LCID lcid, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015ac0`
- `0x180015ae0`

## callees

- `0x180015af4`
- `0x180015bd8`
- `0x1800184b6`
- `0x180019010`

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
0x180015af4  push    rbx
0x180015af6  push    rbp
0x180015af7  push    rsi
0x180015af8  push    rdi
0x180015af9  push    r12
0x180015afb  push    r13
0x180015afd  push    r14
0x180015aff  push    r15
0x180015b01  sub     rsp, 38h
0x180015b05  xor     edx, edx
0x180015b07  mov     r12d, r9d
0x180015b0a  mov     r13, r8
0x180015b0d  mov     rdi, rcx
0x180015b10  cmp     [rcx+18h], rdx
0x180015b14  jz      short loc_180015B20
0x180015b16  cmp     [rcx+28h], rdx
0x180015b1a  jz      short loc_180015B20
0x180015b1c  mov     eax, edx
0x180015b1e  jmp     short loc_180015B2E
0x180015b20  mov     edx, [rsp+78h+lcid]; lcid
0x180015b27  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180015b2c  xor     edx, edx
0x180015b2e  mov     r15, [rdi+18h]
0x180015b32  test    r15, r15
0x180015b35  jz      short loc_180015BAE
0x180015b37  mov     rbp, [rdi+28h]
0x180015b3b  test    rbp, rbp
0x180015b3e  jz      short loc_180015B91
0x180015b40  cmp     r12d, 1
0x180015b44  jnz     short loc_180015B91
0x180015b46  mov     r14, [r13+0]
0x180015b4a  test    r14, r14
0x180015b4d  jnz     short loc_180015B53
0x180015b4f  mov     esi, edx
0x180015b51  jmp     short loc_180015B61
0x180015b53  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180015b57  inc     rsi
0x180015b5a  cmp     [r14+rsi*2], dx
0x180015b5f  jnz     short loc_180015B57
0x180015b61  mov     ebx, [rdi+30h]
0x180015b64  jmp     short loc_180015B8C
0x180015b66  mov     edi, ebx
0x180015b68  add     rdi, rdi
0x180015b6b  cmp     esi, [rbp+rdi*8+8]
0x180015b6f  jnz     short loc_180015B8C
0x180015b71  movsxd  r8, dword ptr [rbp+rdi*8+8]
0x180015b76  mov     rdx, r14; Buf2
0x180015b79  mov     rcx, [rbp+rdi*8+0]; Buf1
0x180015b7e  add     r8, r8; Size
0x180015b81  call    memcmp_0
0x180015b86  xor     edx, edx
0x180015b88  test    eax, eax
0x180015b8a  jz      short loc_180015BBF
0x180015b8c  sub     ebx, 1
0x180015b8f  jns     short loc_180015B66
0x180015b91  mov     rax, [r15]
0x180015b94  mov     r8d, r12d
0x180015b97  mov     r9, [rsp+78h+arg_28]
0x180015b9f  mov     rdx, r13
0x180015ba2  mov     rcx, r15
0x180015ba5  mov     rax, [rax+50h]
0x180015ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bae  add     rsp, 38h
0x180015bb2  pop     r15
0x180015bb4  pop     r14
0x180015bb6  pop     r13
0x180015bb8  pop     r12
0x180015bba  pop     rdi
0x180015bbb  pop     rsi
0x180015bbc  pop     rbp
0x180015bbd  pop     rbx
0x180015bbe  retn
0x180015bbf  mov     rax, [rsp+78h+arg_28]
0x180015bc7  mov     ecx, [rbp+rdi*8+0Ch]
0x180015bcb  mov     [rax], ecx
0x180015bcd  mov     eax, edx
0x180015bcf  jmp     short loc_180015BAE
```
