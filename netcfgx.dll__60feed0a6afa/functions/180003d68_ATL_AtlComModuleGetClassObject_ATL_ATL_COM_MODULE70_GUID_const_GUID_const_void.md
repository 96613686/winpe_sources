# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180003d68`
- end: `0x180003e6e`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800044cc`

## callees

- `0x180003d68`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003e30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003e05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003e05`

## pseudocode

```c
__int64 __fastcall ATL::AtlComModuleGetClassObject(
        struct ATL::_ATL_COM_MODULE70 *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v8; // ebx
  __int64 *i; // rcx
  __int64 v10; // rsi
  _DWORD *v11; // rdx
  _QWORD *v12; // rdi

  if ( !ATL::_AtlComModule )
    return 2147549183LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  for ( i = off_18001A1F0[0]; i < off_18001A1F8; ++i )
  {
    v10 = *i;
    if ( *i )
    {
      if ( *(_QWORD *)(v10 + 16) )
      {
        v11 = *(_DWORD **)v10;
        if ( a2->Data1 == **(_DWORD **)v10
          && *(_DWORD *)&a2->Data2 == v11[1]
          && *(_DWORD *)a2->Data4 == v11[2]
          && *(_DWORD *)&a2->Data4[4] == v11[3] )
        {
          v12 = (_QWORD *)(v10 + 32);
          if ( !*(_QWORD *)(v10 + 32) )
          {
            EnterCriticalSection(&stru_18001A200);
            if ( !*v12 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                     *(_QWORD *)(v10 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v10 + 32);
            LeaveCriticalSection(&stru_18001A200);
          }
          if ( *v12 )
            v8 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v12)(*v12, a3, a4);
          break;
        }
      }
    }
  }
  if ( !*a4 && !v8 )
    return (unsigned int)-2147221231;
  return v8;
}

```

## disassembly

```asm
0x180003d68  push    rbx
0x180003d6a  push    rbp
0x180003d6b  push    rsi
0x180003d6c  push    rdi
0x180003d6d  push    r14
0x180003d6f  sub     rsp, 20h
0x180003d73  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180003d7a  mov     r14, r9
0x180003d7d  mov     r9, rdx
0x180003d80  mov     rbp, r8
0x180003d83  jnz     short loc_180003D8F
0x180003d85  mov     eax, 8000FFFFh
0x180003d8a  jmp     loc_180003E63
0x180003d8f  test    r14, r14
0x180003d92  jnz     short loc_180003D9E
0x180003d94  mov     eax, 80004003h
0x180003d99  jmp     loc_180003E63
0x180003d9e  mov     qword ptr [r14], 0
0x180003da5  xor     ebx, ebx
0x180003da7  mov     rcx, cs:off_18001A1F0
0x180003dae  mov     r8, cs:off_18001A1F8
0x180003db5  jmp     short loc_180003DEE
0x180003db7  mov     rsi, [rcx]
0x180003dba  test    rsi, rsi
0x180003dbd  jz      short loc_180003DEA
0x180003dbf  cmp     [rsi+10h], rbx
0x180003dc3  jz      short loc_180003DEA
0x180003dc5  mov     rdx, [rsi]
0x180003dc8  mov     eax, [rdx]
0x180003dca  cmp     [r9], eax
0x180003dcd  jnz     short loc_180003DEA
0x180003dcf  mov     eax, [rdx+4]
0x180003dd2  cmp     [r9+4], eax
0x180003dd6  jnz     short loc_180003DEA
0x180003dd8  mov     eax, [rdx+8]
0x180003ddb  cmp     [r9+8], eax
0x180003ddf  jnz     short loc_180003DEA
0x180003de1  mov     eax, [rdx+0Ch]
0x180003de4  cmp     [r9+0Ch], eax
0x180003de8  jz      short loc_180003DF5
0x180003dea  add     rcx, 8
0x180003dee  cmp     rcx, r8
0x180003df1  jb      short loc_180003DB7
0x180003df3  jmp     short loc_180003E51
0x180003df5  lea     rdi, [rsi+20h]
0x180003df9  cmp     [rdi], rbx
0x180003dfc  jnz     short loc_180003E36
0x180003dfe  lea     rcx, stru_18001A200; lpCriticalSection
0x180003e05  call    cs:__imp_EnterCriticalSection
0x180003e0b  cmp     [rdi], rbx
0x180003e0e  jnz     short loc_180003E29
0x180003e10  mov     rcx, [rsi+18h]
0x180003e14  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180003e1b  mov     rax, [rsi+10h]
0x180003e1f  mov     r8, rdi
0x180003e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e27  mov     ebx, eax
0x180003e29  lea     rcx, stru_18001A200; lpCriticalSection
0x180003e30  call    cs:__imp_LeaveCriticalSection
0x180003e36  mov     rcx, [rdi]
0x180003e39  test    rcx, rcx
0x180003e3c  jz      short loc_180003E51
0x180003e3e  mov     rax, [rcx]
0x180003e41  mov     r8, r14
0x180003e44  mov     rdx, rbp
0x180003e47  mov     rax, [rax]
0x180003e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e4f  mov     ebx, eax
0x180003e51  cmp     qword ptr [r14], 0
0x180003e55  jnz     short loc_180003E61
0x180003e57  test    ebx, ebx
0x180003e59  mov     eax, 80040111h
0x180003e5e  cmovz   ebx, eax
0x180003e61  mov     eax, ebx
0x180003e63  add     rsp, 20h
0x180003e67  pop     r14
0x180003e69  pop     rdi
0x180003e6a  pop     rsi
0x180003e6b  pop     rbp
0x180003e6c  pop     rbx
0x180003e6d  retn
```
