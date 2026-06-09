# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x1800081a0`
- end: `0x1800082a6`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009ad0`

## callees

- `0x1800081a0`
- `0x180019010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180008268`
- `KERNEL32!LeaveCriticalSection` at `0x180008268`
- `KERNEL32!EnterCriticalSection` at `0x18000823d`
- `KERNEL32!EnterCriticalSection` at `0x18000823d`

## pseudocode

```c
__int64 __fastcall ATL::AtlComModuleGetClassObject(
        struct ATL::_ATL_COM_MODULE70 *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v8; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **i; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v10; // rsi
  _DWORD *v11; // rdx
  _QWORD *v12; // rdi

  if ( !ATL::_AtlComModule )
    return 2147549183LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  for ( i = off_1800213E0; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800213E8; ++i )
  {
    v10 = *i;
    if ( *i )
    {
      if ( *((_QWORD *)v10 + 2) )
      {
        v11 = *(_DWORD **)v10;
        if ( a2->Data1 == **(_DWORD **)v10
          && *(_DWORD *)&a2->Data2 == v11[1]
          && *(_DWORD *)a2->Data4 == v11[2]
          && *(_DWORD *)&a2->Data4[4] == v11[3] )
        {
          v12 = (_QWORD *)((char *)v10 + 32);
          if ( !*((_QWORD *)v10 + 4) )
          {
            EnterCriticalSection(&CriticalSection);
            if ( !*v12 )
              v8 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v10 + 2))(
                     *((_QWORD *)v10 + 3),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     (__int64)v10 + 32);
            LeaveCriticalSection(&CriticalSection);
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
0x1800081a0  push    rbx
0x1800081a2  push    rbp
0x1800081a3  push    rsi
0x1800081a4  push    rdi
0x1800081a5  push    r14
0x1800081a7  sub     rsp, 20h
0x1800081ab  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800081b2  mov     r14, r9
0x1800081b5  mov     r9, rdx
0x1800081b8  mov     rbp, r8
0x1800081bb  jnz     short loc_1800081C7
0x1800081bd  mov     eax, 8000FFFFh
0x1800081c2  jmp     loc_18000829B
0x1800081c7  test    r14, r14
0x1800081ca  jnz     short loc_1800081D6
0x1800081cc  mov     eax, 80004003h
0x1800081d1  jmp     loc_18000829B
0x1800081d6  mov     qword ptr [r14], 0
0x1800081dd  xor     ebx, ebx
0x1800081df  mov     rcx, cs:off_1800213E0
0x1800081e6  mov     r8, cs:off_1800213E8
0x1800081ed  jmp     short loc_180008226
0x1800081ef  mov     rsi, [rcx]
0x1800081f2  test    rsi, rsi
0x1800081f5  jz      short loc_180008222
0x1800081f7  cmp     [rsi+10h], rbx
0x1800081fb  jz      short loc_180008222
0x1800081fd  mov     rdx, [rsi]
0x180008200  mov     eax, [rdx]
0x180008202  cmp     [r9], eax
0x180008205  jnz     short loc_180008222
0x180008207  mov     eax, [rdx+4]
0x18000820a  cmp     [r9+4], eax
0x18000820e  jnz     short loc_180008222
0x180008210  mov     eax, [rdx+8]
0x180008213  cmp     [r9+8], eax
0x180008217  jnz     short loc_180008222
0x180008219  mov     eax, [rdx+0Ch]
0x18000821c  cmp     [r9+0Ch], eax
0x180008220  jz      short loc_18000822D
0x180008222  add     rcx, 8
0x180008226  cmp     rcx, r8
0x180008229  jb      short loc_1800081EF
0x18000822b  jmp     short loc_180008289
0x18000822d  lea     rdi, [rsi+20h]
0x180008231  cmp     [rdi], rbx
0x180008234  jnz     short loc_18000826E
0x180008236  lea     rcx, CriticalSection; lpCriticalSection
0x18000823d  call    cs:__imp_EnterCriticalSection
0x180008243  cmp     [rdi], rbx
0x180008246  jnz     short loc_180008261
0x180008248  mov     rcx, [rsi+18h]
0x18000824c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180008253  mov     rax, [rsi+10h]
0x180008257  mov     r8, rdi
0x18000825a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000825f  mov     ebx, eax
0x180008261  lea     rcx, CriticalSection; lpCriticalSection
0x180008268  call    cs:__imp_LeaveCriticalSection
0x18000826e  mov     rcx, [rdi]
0x180008271  test    rcx, rcx
0x180008274  jz      short loc_180008289
0x180008276  mov     rax, [rcx]
0x180008279  mov     r8, r14
0x18000827c  mov     rdx, rbp
0x18000827f  mov     rax, [rax]
0x180008282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008287  mov     ebx, eax
0x180008289  cmp     qword ptr [r14], 0
0x18000828d  jnz     short loc_180008299
0x18000828f  test    ebx, ebx
0x180008291  mov     eax, 80040111h
0x180008296  cmovz   ebx, eax
0x180008299  mov     eax, ebx
0x18000829b  add     rsp, 20h
0x18000829f  pop     r14
0x1800082a1  pop     rdi
0x1800082a2  pop     rsi
0x1800082a3  pop     rbp
0x1800082a4  pop     rbx
0x1800082a5  retn
```
