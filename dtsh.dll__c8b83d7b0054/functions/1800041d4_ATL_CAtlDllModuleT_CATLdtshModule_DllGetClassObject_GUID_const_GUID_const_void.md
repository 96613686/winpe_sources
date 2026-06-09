# ATL::CAtlDllModuleT<CATLdtshModule>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x1800041d4`
- end: `0x1800042da`
- name: `?DllGetClassObject@?$CAtlDllModuleT@VCATLdtshModule@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004400`

## callees

- `0x1800041d4`
- `0x180005010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180004271`
- `KERNEL32!EnterCriticalSection` at `0x180004271`
- `KERNEL32!LeaveCriticalSection` at `0x18000429c`
- `KERNEL32!LeaveCriticalSection` at `0x18000429c`

## pseudocode

```c
__int64 __fastcall ATL::CAtlDllModuleT<CATLdtshModule>::DllGetClassObject(
        __int64 a1,
        _DWORD *a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v7; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 *i; // rcx
  __int64 v9; // rsi
  _DWORD *v10; // rdx
  _QWORD *v11; // rdi

  if ( ATL::_AtlComModule )
  {
    if ( a4 )
    {
      *a4 = 0;
      v7 = 0;
      for ( i = off_180009060;
            i < (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_180009068;
            i = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)i + 8) )
      {
        v9 = *(_QWORD *)i;
        if ( *(_QWORD *)i )
        {
          if ( *(_QWORD *)(v9 + 16) )
          {
            v10 = *(_DWORD **)v9;
            if ( *a2 == **(_DWORD **)v9 && a2[1] == v10[1] && a2[2] == v10[2] && a2[3] == v10[3] )
            {
              v11 = (_QWORD *)(v9 + 32);
              if ( !*(_QWORD *)(v9 + 32) )
              {
                EnterCriticalSection(&CriticalSection);
                if ( !*v11 )
                  v7 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v9 + 16))(
                         *(_QWORD *)(v9 + 24),
                         &GUID_00000000_0000_0000_c000_000000000046,
                         v9 + 32);
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
0x1800041d4  push    rbx
0x1800041d6  push    rbp
0x1800041d7  push    rsi
0x1800041d8  push    rdi
0x1800041d9  push    r14
0x1800041db  sub     rsp, 20h
0x1800041df  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800041e6  mov     r14, r9
0x1800041e9  mov     r9, rdx
0x1800041ec  mov     rbp, r8
0x1800041ef  jnz     short loc_1800041FB
0x1800041f1  mov     ebx, 8000FFFFh
0x1800041f6  jmp     loc_1800042CD
0x1800041fb  test    r14, r14
0x1800041fe  jnz     short loc_18000420A
0x180004200  mov     ebx, 80004003h
0x180004205  jmp     loc_1800042CD
0x18000420a  mov     qword ptr [r14], 0
0x180004211  xor     ebx, ebx
0x180004213  mov     rcx, cs:off_180009060
0x18000421a  mov     r8, cs:off_180009068
0x180004221  jmp     short loc_18000425A
0x180004223  mov     rsi, [rcx]
0x180004226  test    rsi, rsi
0x180004229  jz      short loc_180004256
0x18000422b  cmp     [rsi+10h], rbx
0x18000422f  jz      short loc_180004256
0x180004231  mov     rdx, [rsi]
0x180004234  mov     eax, [rdx]
0x180004236  cmp     [r9], eax
0x180004239  jnz     short loc_180004256
0x18000423b  mov     eax, [rdx+4]
0x18000423e  cmp     [r9+4], eax
0x180004242  jnz     short loc_180004256
0x180004244  mov     eax, [rdx+8]
0x180004247  cmp     [r9+8], eax
0x18000424b  jnz     short loc_180004256
0x18000424d  mov     eax, [rdx+0Ch]
0x180004250  cmp     [r9+0Ch], eax
0x180004254  jz      short loc_180004261
0x180004256  add     rcx, 8
0x18000425a  cmp     rcx, r8
0x18000425d  jb      short loc_180004223
0x18000425f  jmp     short loc_1800042BD
0x180004261  lea     rdi, [rsi+20h]
0x180004265  cmp     [rdi], rbx
0x180004268  jnz     short loc_1800042A2
0x18000426a  lea     rcx, CriticalSection; lpCriticalSection
0x180004271  call    cs:__imp_EnterCriticalSection
0x180004277  cmp     [rdi], rbx
0x18000427a  jnz     short loc_180004295
0x18000427c  mov     rcx, [rsi+18h]
0x180004280  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180004287  mov     rax, [rsi+10h]
0x18000428b  mov     r8, rdi
0x18000428e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004293  mov     ebx, eax
0x180004295  lea     rcx, CriticalSection; lpCriticalSection
0x18000429c  call    cs:__imp_LeaveCriticalSection
0x1800042a2  mov     rcx, [rdi]
0x1800042a5  test    rcx, rcx
0x1800042a8  jz      short loc_1800042BD
0x1800042aa  mov     rax, [rcx]
0x1800042ad  mov     r8, r14
0x1800042b0  mov     rdx, rbp
0x1800042b3  mov     rax, [rax]
0x1800042b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042bb  mov     ebx, eax
0x1800042bd  cmp     qword ptr [r14], 0
0x1800042c1  jnz     short loc_1800042CD
0x1800042c3  test    ebx, ebx
0x1800042c5  mov     eax, 80040111h
0x1800042ca  cmovz   ebx, eax
0x1800042cd  mov     eax, ebx
0x1800042cf  add     rsp, 20h
0x1800042d3  pop     r14
0x1800042d5  pop     rdi
0x1800042d6  pop     rsi
0x1800042d7  pop     rbp
0x1800042d8  pop     rbx
0x1800042d9  retn
```
