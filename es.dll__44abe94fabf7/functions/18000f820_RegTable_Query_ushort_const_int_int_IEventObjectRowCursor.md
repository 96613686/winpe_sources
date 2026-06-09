# RegTable::Query(ushort const *,int,int *,IEventObjectRowCursor * *)

- ea: `0x18000f820`
- end: `0x18000f9cc`
- name: `?Query@RegTable@@UEAAJPEBGHPEAHPEAPEAUIEventObjectRowCursor@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(RegTable *__hidden this, const unsigned __int16 *, int, int *, struct IEventObjectRowCursor **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000f820`
- `0x18000fce0`
- `0x180010410`
- `0x180010454`
- `0x1800212d0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f957`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043e07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f957`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043e07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f8b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f8b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f94d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f94d`

## pseudocode

```c
__int64 __fastcall RegTable::Query(
        RegTable *this,
        const unsigned __int16 *a2,
        int a3,
        int *a4,
        struct IEventObjectRowCursor **a5)
{
  struct IEventObjectRowCursor **v7; // rdi
  int v8; // esi
  RegRowCursor *v9; // rax
  struct RegTable *v10; // rdx
  RegRowCursor *v11; // rax
  RegRowCursor *v12; // r14
  struct _RTL_CRITICAL_SECTION *v13; // r15
  struct IQueryPlan *v14; // rbx
  _DWORD v16[2]; // [rsp+30h] [rbp-78h] BYREF
  __int64 v17; // [rsp+38h] [rbp-70h]
  __int64 v18; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v19[3]; // [rsp+50h] [rbp-58h] BYREF
  bool v20; // [rsp+68h] [rbp-40h]
  __int64 v21; // [rsp+70h] [rbp-38h]
  __int64 v22; // [rsp+78h] [rbp-30h]
  struct IQueryPlan *v23; // [rsp+B8h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  v7 = a5;
  if ( !a5 )
    return 2147500035LL;
  *a5 = 0;
  v16[0] = *((_DWORD *)this + 136);
  v16[1] = 0;
  v17 = *((_QWORD *)this + 69);
  v23 = 0;
  v8 = QueryEngine::Compile((QueryEngine *)&v18, (const struct tagTableInfo *)v16, a2, &v23, a4);
  if ( v8 >= 0 )
  {
    v9 = (RegRowCursor *)CoTaskMemAlloc(0x50u);
    if ( v9 && (v11 = RegRowCursor::RegRowCursor(v9, v10), (v12 = v11) != 0) )
    {
      v19[0] = &TableQueryInterpreter::`vftable';
      v19[1] = this;
      v19[2] = v11;
      v20 = a3 != 0;
      v22 = 0;
      v21 = -(__int64)(*((_DWORD *)this + 147) != 0);
      v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 616);
      CSemExclusiveES::Lock((RegTable *)((char *)this + 616));
      v14 = v23;
      v8 = (*(__int64 (__fastcall **)(struct IQueryPlan *, _QWORD *))(*(_QWORD *)v23 + 24LL))(v23, v19);
      if ( v8 < 0 )
      {
        RegRowCursor::~RegRowCursor(v12);
        CoTaskMemFree(v12);
      }
      else
      {
        *v7 = v12;
      }
      LeaveCriticalSection(v13);
      (*(void (__fastcall **)(struct IQueryPlan *))(*(_QWORD *)v14 + 16LL))(v14);
      v19[0] = &TableQueryInterpreter::`vftable';
      if ( v22 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 104LL))(v22);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000f820  mov     r11, rsp
0x18000f823  mov     [r11+18h], rbx
0x18000f827  mov     [r11+20h], rsi
0x18000f82b  mov     [r11+8], rcx
0x18000f82f  push    rdi
0x18000f830  push    r12
0x18000f832  push    r13
0x18000f834  push    r14
0x18000f836  push    r15
0x18000f838  sub     rsp, 80h
0x18000f83f  mov     r15d, r8d
0x18000f842  mov     rbx, rcx
0x18000f845  test    rdx, rdx
0x18000f848  jz      loc_18000F9C5
0x18000f84e  test    r9, r9
0x18000f851  jz      loc_18000F9BE
0x18000f857  mov     rdi, [rsp+0A8h+arg_20]
0x18000f85f  test    rdi, rdi
0x18000f862  jz      loc_18000F9BE
0x18000f868  xor     r12d, r12d
0x18000f86b  mov     [rdi], r12
0x18000f86e  mov     eax, [rcx+220h]
0x18000f874  mov     [rsp+0A8h+var_78], eax
0x18000f878  xor     eax, eax
0x18000f87a  mov     [rsp+0A8h+var_74], eax
0x18000f87e  mov     rax, [rcx+228h]
0x18000f885  mov     [r11-70h], rax
0x18000f889  mov     [r11+10h], r12
0x18000f88d  mov     [rsp+0A8h+var_88], r9; int *
0x18000f892  lea     r9, [r11+10h]; struct IQueryPlan **
0x18000f896  mov     r8, rdx; unsigned __int16 *
0x18000f899  lea     rdx, [r11-78h]; struct tagTableInfo *
0x18000f89d  lea     rcx, [r11-68h]; this
0x18000f8a1  call    ?Compile@QueryEngine@@UEAAJPEBUtagTableInfo@@PEBGPEAPEAUIQueryPlan@@PEAH@Z; QueryEngine::Compile(tagTableInfo const *,ushort const *,IQueryPlan * *,int *)
0x18000f8a6  mov     esi, eax
0x18000f8a8  test    eax, eax
0x18000f8aa  js      loc_18000F998
0x18000f8b0  mov     ecx, 50h ; 'P'; cb
0x18000f8b5  call    cs:__imp_CoTaskMemAlloc
0x18000f8bb  test    rax, rax
0x18000f8be  jz      loc_18000F9B7
0x18000f8c4  mov     rcx, rax; this
0x18000f8c7  call    ??0RegRowCursor@@QEAA@AEAVRegTable@@@Z; RegRowCursor::RegRowCursor(RegTable &)
0x18000f8cc  mov     r14, rax
0x18000f8cf  test    rax, rax
0x18000f8d2  jz      loc_18000F9B7
0x18000f8d8  lea     r13, ??_7TableQueryInterpreter@@6B@; const TableQueryInterpreter::`vftable'
0x18000f8df  mov     [rsp+0A8h+var_58], r13
0x18000f8e4  mov     [rsp+0A8h+var_50], rbx
0x18000f8e9  mov     [rsp+0A8h+var_48], rax
0x18000f8ee  test    r15d, r15d
0x18000f8f1  setnz   [rsp+0A8h+var_40]
0x18000f8f6  mov     [rsp+0A8h+var_30], r12
0x18000f8fb  mov     ecx, [rbx+24Ch]
0x18000f901  neg     ecx
0x18000f903  sbb     rdx, rdx
0x18000f906  mov     [rsp+0A8h+var_38], rdx
0x18000f90b  lea     r15, [rbx+268h]
0x18000f912  mov     rcx, r15; this
0x18000f915  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x18000f91a  nop
0x18000f91b  mov     rbx, [rsp+0A8h+arg_8]
0x18000f923  mov     rax, [rbx]
0x18000f926  lea     rdx, [rsp+0A8h+var_58]
0x18000f92b  mov     rcx, rbx
0x18000f92e  mov     rax, [rax+18h]
0x18000f932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f937  mov     esi, eax
0x18000f939  test    eax, eax
0x18000f93b  js      short loc_18000F942
0x18000f93d  mov     [rdi], r14
0x18000f940  jmp     short loc_18000F954
0x18000f942  mov     rcx, r14; this
0x18000f945  call    ??1RegRowCursor@@QEAA@XZ; RegRowCursor::~RegRowCursor(void)
0x18000f94a  mov     rcx, r14; pv
0x18000f94d  call    cs:__imp_CoTaskMemFree
0x18000f953  nop
0x18000f954  mov     rcx, r15; lpCriticalSection
0x18000f957  call    cs:__imp_LeaveCriticalSection
0x18000f95d  mov     rax, [rbx]
0x18000f960  mov     rcx, rbx
0x18000f963  mov     rax, [rax+10h]
0x18000f967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f96c  mov     [rsp+0A8h+var_58], r13
0x18000f971  mov     rcx, [rsp+0A8h+var_30]
0x18000f976  test    rcx, rcx
0x18000f979  jz      short loc_18000F998
0x18000f97b  mov     rax, [rcx]
0x18000f97e  mov     rax, [rax+68h]
0x18000f982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f987  mov     rcx, [rsp+0A8h+var_30]
0x18000f98c  mov     rax, [rcx]
0x18000f98f  mov     rax, [rax+10h]
0x18000f993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f998  mov     eax, esi
0x18000f99a  lea     r11, [rsp+0A8h+var_28]
0x18000f9a2  mov     rbx, [r11+40h]
0x18000f9a6  mov     rsi, [r11+48h]
0x18000f9aa  mov     rsp, r11
0x18000f9ad  pop     r15
0x18000f9af  pop     r14
0x18000f9b1  pop     r13
0x18000f9b3  pop     r12
0x18000f9b5  pop     rdi
0x18000f9b6  retn
0x18000f9b7  mov     esi, 8007000Eh
0x18000f9bc  jmp     short loc_18000F998
0x18000f9be  mov     eax, 80004003h
0x18000f9c3  jmp     short loc_18000F99A
0x18000f9c5  mov     eax, 80070057h
0x18000f9ca  jmp     short loc_18000F99A
0x180043df0  push    rbp
0x180043df2  sub     rsp, 30h
0x180043df6  mov     rbp, rdx
0x180043df9  mov     rcx, [rbp+0B0h]
0x180043e00  add     rcx, 268h; lpCriticalSection
0x180043e07  call    cs:__imp_LeaveCriticalSection
0x180043e0d  mov     rcx, [rbp+0B8h]
0x180043e14  mov     rax, [rcx]
0x180043e17  mov     rax, [rax+10h]
0x180043e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e20  nop
0x180043e21  add     rsp, 30h
0x180043e25  pop     rbp
0x180043e26  retn
```
