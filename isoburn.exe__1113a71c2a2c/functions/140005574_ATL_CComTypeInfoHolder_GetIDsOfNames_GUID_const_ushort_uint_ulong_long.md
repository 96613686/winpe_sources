# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x140005574`
- end: `0x140005651`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `221`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, LCID lcid, int *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005500`
- `0x140005520`
- `0x140005540`
- `0x140005560`

## callees

- `0x140005574`
- `0x1400058e4`
- `0x14000f734`
- `0x140010010`

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
0x140005574  push    rbx
0x140005576  push    rbp
0x140005577  push    rsi
0x140005578  push    rdi
0x140005579  push    r12
0x14000557b  push    r13
0x14000557d  push    r14
0x14000557f  push    r15
0x140005581  sub     rsp, 38h
0x140005585  xor     edx, edx
0x140005587  mov     r12d, r9d
0x14000558a  mov     r13, r8
0x14000558d  mov     rdi, rcx
0x140005590  cmp     [rcx+18h], rdx
0x140005594  jz      short loc_1400055A0
0x140005596  cmp     [rcx+28h], rdx
0x14000559a  jz      short loc_1400055A0
0x14000559c  mov     eax, edx
0x14000559e  jmp     short loc_1400055AE
0x1400055a0  mov     edx, [rsp+78h+lcid]; lcid
0x1400055a7  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1400055ac  xor     edx, edx
0x1400055ae  mov     r15, [rdi+18h]
0x1400055b2  test    r15, r15
0x1400055b5  jz      short loc_14000562E
0x1400055b7  mov     rbp, [rdi+28h]
0x1400055bb  test    rbp, rbp
0x1400055be  jz      short loc_140005611
0x1400055c0  cmp     r12d, 1
0x1400055c4  jnz     short loc_140005611
0x1400055c6  mov     r14, [r13+0]
0x1400055ca  test    r14, r14
0x1400055cd  jnz     short loc_1400055D3
0x1400055cf  mov     esi, edx
0x1400055d1  jmp     short loc_1400055E1
0x1400055d3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400055d7  inc     rsi
0x1400055da  cmp     [r14+rsi*2], dx
0x1400055df  jnz     short loc_1400055D7
0x1400055e1  mov     ebx, [rdi+30h]
0x1400055e4  jmp     short loc_14000560C
0x1400055e6  mov     edi, ebx
0x1400055e8  add     rdi, rdi
0x1400055eb  cmp     esi, [rbp+rdi*8+8]
0x1400055ef  jnz     short loc_14000560C
0x1400055f1  movsxd  r8, dword ptr [rbp+rdi*8+8]
0x1400055f6  mov     rdx, r14; Buf2
0x1400055f9  mov     rcx, [rbp+rdi*8+0]; Buf1
0x1400055fe  add     r8, r8; Size
0x140005601  call    memcmp_0
0x140005606  xor     edx, edx
0x140005608  test    eax, eax
0x14000560a  jz      short loc_14000563F
0x14000560c  sub     ebx, 1
0x14000560f  jns     short loc_1400055E6
0x140005611  mov     rax, [r15]
0x140005614  mov     r8d, r12d
0x140005617  mov     r9, [rsp+78h+arg_28]
0x14000561f  mov     rdx, r13
0x140005622  mov     rcx, r15
0x140005625  mov     rax, [rax+50h]
0x140005629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000562e  add     rsp, 38h
0x140005632  pop     r15
0x140005634  pop     r14
0x140005636  pop     r13
0x140005638  pop     r12
0x14000563a  pop     rdi
0x14000563b  pop     rsi
0x14000563c  pop     rbp
0x14000563d  pop     rbx
0x14000563e  retn
0x14000563f  mov     rax, [rsp+78h+arg_28]
0x140005647  mov     ecx, [rbp+rdi*8+0Ch]
0x14000564b  mov     [rax], ecx
0x14000564d  mov     eax, edx
0x14000564f  jmp     short loc_14000562E
```
