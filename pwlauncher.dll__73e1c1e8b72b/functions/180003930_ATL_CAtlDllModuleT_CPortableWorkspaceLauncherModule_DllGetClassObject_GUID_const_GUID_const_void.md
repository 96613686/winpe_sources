# ATL::CAtlDllModuleT<CPortableWorkspaceLauncherModule>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180003930`
- end: `0x180003a36`
- name: `?DllGetClassObject@?$CAtlDllModuleT@VCPortableWorkspaceLauncherModule@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005080`

## callees

- `0x180003930`
- `0x180011010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800039cd`
- `KERNEL32!EnterCriticalSection` at `0x1800039cd`
- `KERNEL32!LeaveCriticalSection` at `0x1800039f8`
- `KERNEL32!LeaveCriticalSection` at `0x1800039f8`

## pseudocode

```c
__int64 __fastcall ATL::CAtlDllModuleT<CPortableWorkspaceLauncherModule>::DllGetClassObject(
        __int64 a1,
        _DWORD *a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v7; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **i; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v9; // rsi
  _DWORD *v10; // rdx
  _QWORD *v11; // rdi

  if ( ATL::_AtlComModule )
  {
    if ( a4 )
    {
      *a4 = 0;
      v7 = 0;
      for ( i = off_1800190E0; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800190E8; ++i )
      {
        v9 = *i;
        if ( *i )
        {
          if ( *((_QWORD *)v9 + 2) )
          {
            v10 = *(_DWORD **)v9;
            if ( *a2 == **(_DWORD **)v9 && a2[1] == v10[1] && a2[2] == v10[2] && a2[3] == v10[3] )
            {
              v11 = (_QWORD *)((char *)v9 + 32);
              if ( !*((_QWORD *)v9 + 4) )
              {
                EnterCriticalSection(&CriticalSection);
                if ( !*v11 )
                  v7 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v9 + 2))(
                         *((_QWORD *)v9 + 3),
                         &GUID_00000000_0000_0000_c000_000000000046,
                         (__int64)v9 + 32);
                LeaveCriticalSection(&CriticalSection);
              }
              if ( *v11 )
                v7 = (**(__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))*v11)(*v11, a3, a4);
              break;
            }
          }
        }
      }
      if ( !*a4 && !v7 )
        return (unsigned int)-2147221231;
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return v7;
}

```

## disassembly

```asm
0x180003930  push    rbx
0x180003932  push    rbp
0x180003933  push    rsi
0x180003934  push    rdi
0x180003935  push    r14
0x180003937  sub     rsp, 20h
0x18000393b  mov     r14, r9
0x18000393e  mov     rbp, r8
0x180003941  mov     r9, rdx
0x180003944  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000394b  jnz     short loc_180003957
0x18000394d  mov     ebx, 8000FFFFh
0x180003952  jmp     loc_180003A29
0x180003957  test    r14, r14
0x18000395a  jnz     short loc_180003966
0x18000395c  mov     ebx, 80004003h
0x180003961  jmp     loc_180003A29
0x180003966  mov     qword ptr [r14], 0
0x18000396d  xor     ebx, ebx
0x18000396f  mov     rcx, cs:off_1800190E0
0x180003976  mov     r8, cs:off_1800190E8
0x18000397d  jmp     short loc_1800039B6
0x18000397f  mov     rsi, [rcx]
0x180003982  test    rsi, rsi
0x180003985  jz      short loc_1800039B2
0x180003987  cmp     [rsi+10h], rbx
0x18000398b  jz      short loc_1800039B2
0x18000398d  mov     rdx, [rsi]
0x180003990  mov     eax, [rdx]
0x180003992  cmp     [r9], eax
0x180003995  jnz     short loc_1800039B2
0x180003997  mov     eax, [rdx+4]
0x18000399a  cmp     [r9+4], eax
0x18000399e  jnz     short loc_1800039B2
0x1800039a0  mov     eax, [rdx+8]
0x1800039a3  cmp     [r9+8], eax
0x1800039a7  jnz     short loc_1800039B2
0x1800039a9  mov     eax, [rdx+0Ch]
0x1800039ac  cmp     [r9+0Ch], eax
0x1800039b0  jz      short loc_1800039BD
0x1800039b2  add     rcx, 8
0x1800039b6  cmp     rcx, r8
0x1800039b9  jb      short loc_18000397F
0x1800039bb  jmp     short loc_180003A19
0x1800039bd  lea     rdi, [rsi+20h]
0x1800039c1  cmp     [rdi], rbx
0x1800039c4  jnz     short loc_1800039FE
0x1800039c6  lea     rcx, CriticalSection; lpCriticalSection
0x1800039cd  call    cs:__imp_EnterCriticalSection
0x1800039d3  cmp     [rdi], rbx
0x1800039d6  jnz     short loc_1800039F1
0x1800039d8  mov     r8, rdi
0x1800039db  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800039e2  mov     rcx, [rsi+18h]
0x1800039e6  mov     rax, [rsi+10h]
0x1800039ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ef  mov     ebx, eax
0x1800039f1  lea     rcx, CriticalSection; lpCriticalSection
0x1800039f8  call    cs:__imp_LeaveCriticalSection
0x1800039fe  mov     rcx, [rdi]
0x180003a01  test    rcx, rcx
0x180003a04  jz      short loc_180003A19
0x180003a06  mov     rax, [rcx]
0x180003a09  mov     r8, r14
0x180003a0c  mov     rdx, rbp
0x180003a0f  mov     rax, [rax]
0x180003a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a17  mov     ebx, eax
0x180003a19  cmp     qword ptr [r14], 0
0x180003a1d  jnz     short loc_180003A29
0x180003a1f  mov     eax, 80040111h
0x180003a24  test    ebx, ebx
0x180003a26  cmovz   ebx, eax
0x180003a29  mov     eax, ebx
0x180003a2b  add     rsp, 20h
0x180003a2f  pop     r14
0x180003a31  pop     rdi
0x180003a32  pop     rsi
0x180003a33  pop     rbp
0x180003a34  pop     rbx
0x180003a35  retn
```
