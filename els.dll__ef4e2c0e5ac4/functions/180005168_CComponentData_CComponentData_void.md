# CComponentData::CComponentData(void)

- ea: `0x180005168`
- end: `0x18000526b`
- name: `??0CComponentData@@QEAA@XZ`
- size: `259`
- prototype: `CComponentData *__fastcall(CComponentData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004fb0`

## callees

- `0x180005168`
- `0x18001435c`

## pseudocode

```c
CComponentData *__fastcall CComponentData::CComponentData(CComponentData *this)
{
  *((_WORD *)this + 28) = 0;
  *(_QWORD *)this = &CComponentData::`vftable'{for `IPersistStream'};
  *((_QWORD *)this + 1) = &CComponentData::`vftable'{for `IComponentData'};
  *((_QWORD *)this + 2) = &CComponentData::`vftable'{for `IExtendPropertySheet'};
  *((_QWORD *)this + 3) = &CComponentData::`vftable'{for `IExtendContextMenu'};
  *((_QWORD *)this + 4) = &CComponentData::`vftable'{for `INamespacePrshtActions'};
  *((_QWORD *)this + 5) = &CComponentData::`vftable'{for `IExternalConnection'};
  *((_QWORD *)this + 6) = &CComponentData::`vftable'{for `ISnapinHelp'};
  if ( !CDll::s_cObjs )
    InitGlobals();
  _InterlockedAdd((volatile signed __int32 *)&CDll::s_cObjs, 1u);
  *((_DWORD *)this + 15) = 1;
  *((_DWORD *)this + 286) = 1;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 142) = 0;
  *((_QWORD *)this + 144) = 0;
  *((_QWORD *)this + 145) = 0;
  *((_QWORD *)this + 146) = 0;
  *((_QWORD *)this + 147) = 0;
  *((_QWORD *)this + 151) = 3;
  *((_QWORD *)this + 150) = 0;
  *((_DWORD *)this + 296) = 0;
  *((_WORD *)this + 44) = 0;
  *((_WORD *)this + 306) = 0;
  return this;
}

```

## disassembly

```asm
0x180005168  push    rbx
0x18000516a  sub     rsp, 20h
0x18000516e  xor     eax, eax
0x180005170  mov     rbx, rcx
0x180005173  mov     [rcx+38h], ax
0x180005177  lea     rax, ??_7CComponentData@@6BIPersistStream@@@; const CComponentData::`vftable'{for `IPersistStream'}
0x18000517e  mov     [rcx], rax
0x180005181  lea     rax, ??_7CComponentData@@6BIComponentData@@@; const CComponentData::`vftable'{for `IComponentData'}
0x180005188  mov     [rcx+8], rax
0x18000518c  lea     rax, ??_7CComponentData@@6BIExtendPropertySheet@@@; const CComponentData::`vftable'{for `IExtendPropertySheet'}
0x180005193  mov     [rcx+10h], rax
0x180005197  lea     rax, ??_7CComponentData@@6BIExtendContextMenu@@@; const CComponentData::`vftable'{for `IExtendContextMenu'}
0x18000519e  mov     [rcx+18h], rax
0x1800051a2  lea     rax, ??_7CComponentData@@6BINamespacePrshtActions@@@; const CComponentData::`vftable'{for `INamespacePrshtActions'}
0x1800051a9  mov     [rcx+20h], rax
0x1800051ad  lea     rax, ??_7CComponentData@@6BIExternalConnection@@@; const CComponentData::`vftable'{for `IExternalConnection'}
0x1800051b4  mov     [rcx+28h], rax
0x1800051b8  lea     rax, ??_7CComponentData@@6BISnapinHelp@@@; const CComponentData::`vftable'{for `ISnapinHelp'}
0x1800051bf  mov     [rcx+30h], rax
0x1800051c3  cmp     cs:?s_cObjs@CDll@@2KA, 0; ulong CDll::s_cObjs
0x1800051ca  jnz     short loc_1800051D1
0x1800051cc  call    ?InitGlobals@@YAXXZ; InitGlobals(void)
0x1800051d1  mov     eax, 1
0x1800051d6  lock add cs:?s_cObjs@CDll@@2KA, eax; ulong CDll::s_cObjs
0x1800051dd  mov     [rbx+3Ch], eax
0x1800051e0  mov     [rbx+478h], eax
0x1800051e6  xor     eax, eax
0x1800051e8  mov     qword ptr [rbx+40h], 0
0x1800051f0  mov     qword ptr [rbx+48h], 0
0x1800051f8  mov     qword ptr [rbx+50h], 0
0x180005200  mov     qword ptr [rbx+470h], 0
0x18000520b  mov     qword ptr [rbx+480h], 0
0x180005216  mov     qword ptr [rbx+488h], 0
0x180005221  mov     qword ptr [rbx+490h], 0
0x18000522c  mov     qword ptr [rbx+498h], 0
0x180005237  mov     qword ptr [rbx+4B8h], 3
0x180005242  mov     qword ptr [rbx+4B0h], 0
0x18000524d  mov     dword ptr [rbx+4A0h], 0
0x180005257  mov     [rbx+58h], ax
0x18000525b  mov     [rbx+264h], ax
0x180005262  mov     rax, rbx
0x180005265  add     rsp, 20h
0x180005269  pop     rbx
0x18000526a  retn
```
