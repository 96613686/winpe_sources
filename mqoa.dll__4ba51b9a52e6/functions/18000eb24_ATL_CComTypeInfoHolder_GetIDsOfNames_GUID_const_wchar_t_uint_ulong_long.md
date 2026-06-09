# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,wchar_t * *,uint,ulong,long *)

- ea: `0x18000eb24`
- end: `0x18000ebe8`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEA_WIKPEAJ@Z`
- size: `196`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, const struct _GUID *, wchar_t **, unsigned int, LCID lcid, int *)`
- caller_count: `15`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e990`
- `0x18000e9b0`
- `0x18000e9d0`
- `0x18000e9f0`
- `0x18000ea10`
- `0x18000ea30`
- `0x18000ea50`
- `0x18000ea70`
- `0x18000ea90`
- `0x18000eab0`
- `0x18000ead0`
- `0x18000eaf0`
- `0x18000eb10`
- `0x180022ba0`
- `0x180025e70`

## callees

- `0x18000eb24`
- `0x18000ec10`
- `0x180012e60`
- `0x180027366`
- `0x180029010`

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
  __int64 result; // rax
  __int64 v10; // r14
  __int64 v11; // rsi
  int v12; // eax
  int v13; // ebx
  int v14; // r12d

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
      v12 = ocslen(*a3);
      v13 = *((_DWORD *)this + 12);
      v14 = v12;
      while ( --v13 >= 0 )
      {
        if ( v14 == *(_DWORD *)(v11 + 16LL * v13 + 8)
          && !memcmp_0(*(const void **)(v11 + 16LL * v13), *a3, 2LL * *(int *)(v11 + 16LL * v13 + 8)) )
        {
          *a6 = *(_DWORD *)(v11 + 16LL * v13 + 12);
          return 0;
        }
      }
    }
    return (*(__int64 (__fastcall **)(__int64, const wchar_t **, _QWORD, int *))(*(_QWORD *)v10 + 80LL))(
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
0x18000eb24  push    rbx
0x18000eb26  push    rbp
0x18000eb27  push    rsi
0x18000eb28  push    rdi
0x18000eb29  push    r12
0x18000eb2b  push    r14
0x18000eb2d  push    r15
0x18000eb2f  sub     rsp, 30h
0x18000eb33  cmp     qword ptr [rcx+18h], 0
0x18000eb38  mov     ebp, r9d
0x18000eb3b  mov     r15, r8
0x18000eb3e  mov     rdi, rcx
0x18000eb41  jz      short loc_18000EB4E
0x18000eb43  cmp     qword ptr [rcx+28h], 0
0x18000eb48  jz      short loc_18000EB4E
0x18000eb4a  xor     eax, eax
0x18000eb4c  jmp     short loc_18000EB5A
0x18000eb4e  mov     edx, [rsp+68h+lcid]; lcid
0x18000eb55  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000eb5a  mov     r14, [rdi+18h]
0x18000eb5e  test    r14, r14
0x18000eb61  jz      short loc_18000EBD9
0x18000eb63  mov     rsi, [rdi+28h]
0x18000eb67  test    rsi, rsi
0x18000eb6a  jz      short loc_18000EBBC
0x18000eb6c  cmp     ebp, 1
0x18000eb6f  jnz     short loc_18000EBBC
0x18000eb71  mov     rcx, [r15]; wchar_t *
0x18000eb74  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x18000eb79  mov     ebx, [rdi+30h]
0x18000eb7c  mov     r12d, eax
0x18000eb7f  dec     ebx
0x18000eb81  test    ebx, ebx
0x18000eb83  js      short loc_18000EBBC
0x18000eb85  movsxd  rdi, ebx
0x18000eb88  add     rdi, rdi
0x18000eb8b  cmp     r12d, [rsi+rdi*8+8]
0x18000eb90  jnz     short loc_18000EB7F
0x18000eb92  movsxd  r8, dword ptr [rsi+rdi*8+8]
0x18000eb97  mov     rdx, [r15]; Buf2
0x18000eb9a  add     r8, r8; Size
0x18000eb9d  mov     rcx, [rsi+rdi*8]; Buf1
0x18000eba1  call    memcmp_0
0x18000eba6  test    eax, eax
0x18000eba8  jnz     short loc_18000EB7F
0x18000ebaa  mov     rax, [rsp+68h+arg_28]
0x18000ebb2  mov     ecx, [rsi+rdi*8+0Ch]
0x18000ebb6  mov     [rax], ecx
0x18000ebb8  xor     eax, eax
0x18000ebba  jmp     short loc_18000EBD9
0x18000ebbc  mov     rax, [r14]
0x18000ebbf  mov     r8d, ebp
0x18000ebc2  mov     r9, [rsp+68h+arg_28]
0x18000ebca  mov     rdx, r15
0x18000ebcd  mov     rcx, r14
0x18000ebd0  mov     rax, [rax+50h]
0x18000ebd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebd9  add     rsp, 30h
0x18000ebdd  pop     r15
0x18000ebdf  pop     r14
0x18000ebe1  pop     r12
0x18000ebe3  pop     rdi
0x18000ebe4  pop     rsi
0x18000ebe5  pop     rbp
0x18000ebe6  pop     rbx
0x18000ebe7  retn
```
