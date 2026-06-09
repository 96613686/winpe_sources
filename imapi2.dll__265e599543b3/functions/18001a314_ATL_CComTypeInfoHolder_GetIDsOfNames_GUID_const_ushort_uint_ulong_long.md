# ATL::CComTypeInfoHolder::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x18001a314`
- end: `0x18001a3d8`
- name: `?GetIDsOfNames@CComTypeInfoHolder@ATL@@QEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `196`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, const struct _GUID *, unsigned __int16 **, unsigned int, LCID lcid, int *)`
- caller_count: `17`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001a280`
- `0x18001a2a0`
- `0x18001a2c0`
- `0x18001a2e0`
- `0x18001a300`
- `0x180026df0`
- `0x1800287e0`
- `0x180029ad0`
- `0x18002e570`
- `0x18002e590`
- `0x180033830`
- `0x180033850`
- `0x180037f50`
- `0x180037f70`
- `0x18003da10`
- `0x18003da30`
- `0x180044240`

## callees

- `0x1800140d4`
- `0x18001a314`
- `0x18001b910`
- `0x180049826`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetIDsOfNames(
        ATL::CComTypeInfoHolder *this,
        const struct _GUID *a2,
        const unsigned __int16 **a3,
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
    return (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **, _QWORD, int *))(*(_QWORD *)v10 + 80LL))(
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
0x18001a314  push    rbx
0x18001a316  push    rbp
0x18001a317  push    rsi
0x18001a318  push    rdi
0x18001a319  push    r12
0x18001a31b  push    r14
0x18001a31d  push    r15
0x18001a31f  sub     rsp, 30h
0x18001a323  cmp     qword ptr [rcx+18h], 0
0x18001a328  mov     ebp, r9d
0x18001a32b  mov     r15, r8
0x18001a32e  mov     rdi, rcx
0x18001a331  jz      short loc_18001A33E
0x18001a333  cmp     qword ptr [rcx+28h], 0
0x18001a338  jz      short loc_18001A33E
0x18001a33a  xor     eax, eax
0x18001a33c  jmp     short loc_18001A34A
0x18001a33e  mov     edx, [rsp+68h+lcid]; lcid
0x18001a345  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18001a34a  mov     r14, [rdi+18h]
0x18001a34e  test    r14, r14
0x18001a351  jz      short loc_18001A3C9
0x18001a353  mov     rsi, [rdi+28h]
0x18001a357  test    rsi, rsi
0x18001a35a  jz      short loc_18001A3AC
0x18001a35c  cmp     ebp, 1
0x18001a35f  jnz     short loc_18001A3AC
0x18001a361  mov     rcx, [r15]; unsigned __int16 *
0x18001a364  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x18001a369  mov     ebx, [rdi+30h]
0x18001a36c  mov     r12d, eax
0x18001a36f  dec     ebx
0x18001a371  test    ebx, ebx
0x18001a373  js      short loc_18001A3AC
0x18001a375  movsxd  rdi, ebx
0x18001a378  add     rdi, rdi
0x18001a37b  cmp     r12d, [rsi+rdi*8+8]
0x18001a380  jnz     short loc_18001A36F
0x18001a382  movsxd  r8, dword ptr [rsi+rdi*8+8]
0x18001a387  mov     rdx, [r15]; Buf2
0x18001a38a  add     r8, r8; Size
0x18001a38d  mov     rcx, [rsi+rdi*8]; Buf1
0x18001a391  call    memcmp_0
0x18001a396  test    eax, eax
0x18001a398  jnz     short loc_18001A36F
0x18001a39a  mov     rax, [rsp+68h+arg_28]
0x18001a3a2  mov     ecx, [rsi+rdi*8+0Ch]
0x18001a3a6  mov     [rax], ecx
0x18001a3a8  xor     eax, eax
0x18001a3aa  jmp     short loc_18001A3C9
0x18001a3ac  mov     rax, [r14]
0x18001a3af  mov     r8d, ebp
0x18001a3b2  mov     r9, [rsp+68h+arg_28]
0x18001a3ba  mov     rdx, r15
0x18001a3bd  mov     rcx, r14
0x18001a3c0  mov     rax, [rax+50h]
0x18001a3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3c9  add     rsp, 30h
0x18001a3cd  pop     r15
0x18001a3cf  pop     r14
0x18001a3d1  pop     r12
0x18001a3d3  pop     rdi
0x18001a3d4  pop     rsi
0x18001a3d5  pop     rbp
0x18001a3d6  pop     rbx
0x18001a3d7  retn
```
