# CComponentData::~CComponentData(void)

- ea: `0x1800052a8`
- end: `0x180005323`
- name: `??1CComponentData@@QEAA@XZ`
- size: `123`
- prototype: `void __fastcall(CComponentData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006c20`

## callees

- `0x1800052a8`
- `0x180008a00`
- `0x180014128`

## pseudocode

```c
void __fastcall CComponentData::~CComponentData(CComponentData *this, __int64 a2)
{
  *(_QWORD *)this = &CComponentData::`vftable'{for `IPersistStream'};
  LOBYTE(a2) = 1;
  *((_QWORD *)this + 1) = &CComponentData::`vftable'{for `IComponentData'};
  *((_QWORD *)this + 2) = &CComponentData::`vftable'{for `IExtendPropertySheet'};
  *((_QWORD *)this + 3) = &CComponentData::`vftable'{for `IExtendContextMenu'};
  *((_QWORD *)this + 4) = &CComponentData::`vftable'{for `INamespacePrshtActions'};
  *((_QWORD *)this + 5) = &CComponentData::`vftable'{for `IExternalConnection'};
  *((_QWORD *)this + 6) = &CComponentData::`vftable'{for `ISnapinHelp'};
  std::basic_string<unsigned long>::_Tidy((char *)this + 1184, a2, 0);
  if ( CDll::s_cObjs == 1 )
    FreeGlobals();
  _InterlockedDecrement((volatile signed __int32 *)&CDll::s_cObjs);
}

```

## disassembly

```asm
0x1800052a8  sub     rsp, 28h
0x1800052ac  lea     rax, ??_7CComponentData@@6BIPersistStream@@@; const CComponentData::`vftable'{for `IPersistStream'}
0x1800052b3  xor     r8d, r8d
0x1800052b6  mov     [rcx], rax
0x1800052b9  mov     dl, 1
0x1800052bb  lea     rax, ??_7CComponentData@@6BIComponentData@@@; const CComponentData::`vftable'{for `IComponentData'}
0x1800052c2  mov     [rcx+8], rax
0x1800052c6  lea     rax, ??_7CComponentData@@6BIExtendPropertySheet@@@; const CComponentData::`vftable'{for `IExtendPropertySheet'}
0x1800052cd  mov     [rcx+10h], rax
0x1800052d1  lea     rax, ??_7CComponentData@@6BIExtendContextMenu@@@; const CComponentData::`vftable'{for `IExtendContextMenu'}
0x1800052d8  mov     [rcx+18h], rax
0x1800052dc  lea     rax, ??_7CComponentData@@6BINamespacePrshtActions@@@; const CComponentData::`vftable'{for `INamespacePrshtActions'}
0x1800052e3  mov     [rcx+20h], rax
0x1800052e7  lea     rax, ??_7CComponentData@@6BIExternalConnection@@@; const CComponentData::`vftable'{for `IExternalConnection'}
0x1800052ee  mov     [rcx+28h], rax
0x1800052f2  lea     rax, ??_7CComponentData@@6BISnapinHelp@@@; const CComponentData::`vftable'{for `ISnapinHelp'}
0x1800052f9  mov     [rcx+30h], rax
0x1800052fd  add     rcx, 4A0h
0x180005304  call    ?_Tidy@?$basic_string@KU?$char_traits@K@std@@V?$allocator@K@2@@std@@QEAAX_N_K@Z; std::basic_string<ulong>::_Tidy(bool,unsigned __int64)
0x180005309  cmp     cs:?s_cObjs@CDll@@2KA, 1; ulong CDll::s_cObjs
0x180005310  jnz     short loc_180005317
0x180005312  call    ?FreeGlobals@@YAXXZ; FreeGlobals(void)
0x180005317  lock dec cs:?s_cObjs@CDll@@2KA; ulong CDll::s_cObjs
0x18000531e  add     rsp, 28h
0x180005322  retn
```
