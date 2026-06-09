# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,wchar_t * *,uint,ulong,long *)

- ea: `0x18000e994`
- end: `0x18000ea70`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEA_WIKPEAJ@Z`
- size: `220`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, const struct _GUID *, wchar_t **, unsigned int, LCID lcid, int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e900`
- `0x18000e920`
- `0x18000e940`
- `0x18000e960`
- `0x18000e980`

## callees

- `0x180004d20`
- `0x18000e994`
- `0x18000ea78`
- `0x18001e342`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetIDsOfNames(
        ATL::CComTypeInfoHolder *this,
        const struct _GUID *a2,
        const wchar_t **a3,
        unsigned int a4,
        LCID lcid,
        int *a6)
{
  __int64 *v9; // rbx
  __int64 result; // rax
  unsigned int v11; // r15d
  int v12; // edi
  __int64 v13; // r14

  v9 = (__int64 *)((char *)this + 40);
  if ( *((_QWORD *)this + 3) && *v9 )
    result = 0;
  else
    result = ATL::CComTypeInfoHolder::GetTI(this, lcid);
  if ( *((_QWORD *)this + 3) )
  {
    if ( *v9 && a4 == 1 )
    {
      if ( *a3 )
        v11 = mqwcslen(*a3);
      else
        v11 = 0;
      v12 = *((_DWORD *)this + 12);
      while ( --v12 >= 0 )
      {
        v13 = *v9;
        if ( v11 == *(_DWORD *)(*v9 + 16LL * v12 + 8)
          && !memcmp_0(*(const void **)(v13 + 16LL * v12), *a3, 2LL * *(int *)(v13 + 16LL * v12 + 8)) )
        {
          *a6 = *(_DWORD *)(v13 + 16LL * v12 + 12);
          return 0;
        }
      }
    }
    return (*(__int64 (__fastcall **)(_QWORD, const wchar_t **, _QWORD, int *))(**((_QWORD **)this + 3) + 80LL))(
             *((_QWORD *)this + 3),
             a3,
             a4,
             a6);
  }
  return result;
}

```

## disassembly

```asm
0x18000e994  push    rbx
0x18000e996  push    rbp
0x18000e997  push    rsi
0x18000e998  push    rdi
0x18000e999  push    r12
0x18000e99b  push    r13
0x18000e99d  push    r14
0x18000e99f  push    r15
0x18000e9a1  sub     rsp, 38h
0x18000e9a5  mov     r13d, r9d
0x18000e9a8  mov     r12, r8
0x18000e9ab  mov     rbp, rcx
0x18000e9ae  lea     rbx, [rcx+28h]
0x18000e9b2  cmp     qword ptr [rcx+18h], 0
0x18000e9b7  jz      short loc_18000E9C3
0x18000e9b9  cmp     qword ptr [rbx], 0
0x18000e9bd  jz      short loc_18000E9C3
0x18000e9bf  xor     eax, eax
0x18000e9c1  jmp     short loc_18000E9CF
0x18000e9c3  mov     edx, [rsp+78h+lcid]; lcid
0x18000e9ca  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000e9cf  cmp     qword ptr [rbp+18h], 0
0x18000e9d4  jz      loc_18000EA5F
0x18000e9da  cmp     qword ptr [rbx], 0
0x18000e9de  jz      short loc_18000EA41
0x18000e9e0  cmp     r13d, 1
0x18000e9e4  jnz     short loc_18000EA41
0x18000e9e6  mov     rcx, [r12]; wchar_t *
0x18000e9ea  test    rcx, rcx
0x18000e9ed  jnz     short loc_18000E9F4
0x18000e9ef  xor     r15d, r15d
0x18000e9f2  jmp     short loc_18000E9FC
0x18000e9f4  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000e9f9  mov     r15d, eax
0x18000e9fc  mov     edi, [rbp+30h]
0x18000e9ff  dec     edi
0x18000ea01  test    edi, edi
0x18000ea03  js      short loc_18000EA41
0x18000ea05  movsxd  rsi, edi
0x18000ea08  add     rsi, rsi
0x18000ea0b  mov     r14, [rbx]
0x18000ea0e  cmp     r15d, [r14+rsi*8+8]
0x18000ea13  jnz     short loc_18000E9FF
0x18000ea15  movsxd  r8, dword ptr [r14+rsi*8+8]
0x18000ea1a  add     r8, r8; Size
0x18000ea1d  mov     rdx, [r12]; Buf2
0x18000ea21  mov     rcx, [r14+rsi*8]; Buf1
0x18000ea25  call    memcmp_0
0x18000ea2a  test    eax, eax
0x18000ea2c  jnz     short loc_18000E9FF
0x18000ea2e  mov     ecx, [r14+rsi*8+0Ch]
0x18000ea33  mov     rax, [rsp+78h+arg_28]
0x18000ea3b  mov     [rax], ecx
0x18000ea3d  xor     eax, eax
0x18000ea3f  jmp     short loc_18000EA5F
0x18000ea41  mov     rcx, [rbp+18h]
0x18000ea45  mov     rax, [rcx]
0x18000ea48  mov     r9, [rsp+78h+arg_28]
0x18000ea50  mov     r8d, r13d
0x18000ea53  mov     rdx, r12
0x18000ea56  mov     rax, [rax+50h]
0x18000ea5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea5f  add     rsp, 38h
0x18000ea63  pop     r15
0x18000ea65  pop     r14
0x18000ea67  pop     r13
0x18000ea69  pop     r12
0x18000ea6b  pop     rdi
0x18000ea6c  pop     rsi
0x18000ea6d  pop     rbp
0x18000ea6e  pop     rbx
0x18000ea6f  retn
```
