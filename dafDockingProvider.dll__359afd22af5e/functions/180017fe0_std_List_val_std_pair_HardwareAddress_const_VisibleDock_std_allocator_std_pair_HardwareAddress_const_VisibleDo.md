# std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>::_Buynode<std::pair<HardwareAddress const,VisibleDock>>(std::_List_nod<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>::_Node *,std::_List_nod<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>::_Node *,std::pair<HardwareAddress const,VisibleDock> &&)

- ea: `0x180017fe0`
- end: `0x180018099`
- name: `??$_Buynode@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@QEAAPEAU_Node@?$_List_nod@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@1@PEAU231@0$$QEAU?$pair@$$CBVHardwareAddress@@VVisibleDock@@@1@@Z`
- size: `185`
- prototype: `_QWORD *__fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180018540`

## callees

- `0x180001484`
- `0x1800020bd`
- `0x18001117c`
- `0x180017fe0`
- `0x18001821c`

## pseudocode

```c
_QWORD *__fastcall std::_List_val<std::pair<HardwareAddress const,VisibleDock>>::_Buynode<std::pair<HardwareAddress const,VisibleDock>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v7; // rax
  const char *v8; // rdx
  _QWORD *v9; // rbx
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

  v7 = operator new(0x4A8u);
  v9 = v7;
  if ( !v7 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, v8);
    throw (std::bad_alloc *)pExceptionObject;
  }
  *v7 = a2;
  v7[1] = a3;
  *((_DWORD *)v7 + 6) = *(_DWORD *)(a4 + 8);
  *((_WORD *)v7 + 14) = *(_WORD *)(a4 + 12);
  v7[2] = *((unsigned __int8 *)v7 + 29)
        | ((*((unsigned __int8 *)v7 + 28)
          | ((*((unsigned __int8 *)v7 + 27)
            | ((*((unsigned __int8 *)v7 + 26)
              | ((((unsigned __int64)*((unsigned __int8 *)v7 + 24) << 8) | *((unsigned __int8 *)v7 + 25)) << 8)) << 8)) << 8)) << 8);
  VisibleDock::VisibleDock((VisibleDock *)(v7 + 4), (const struct VisibleDock *)(a4 + 16));
  return v9;
}

```

## disassembly

```asm
0x180017fe0  mov     [rsp+arg_0], rcx
0x180017fe5  push    rbx
0x180017fe6  push    rsi
0x180017fe7  push    rdi
0x180017fe8  push    r14
0x180017fea  sub     rsp, 48h
0x180017fee  mov     rdi, r9
0x180017ff1  mov     rsi, r8
0x180017ff4  mov     r14, rdx
0x180017ff7  mov     ecx, 4A8h; Size
0x180017ffc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018001  mov     rbx, rax
0x180018004  mov     [rsp+68h+arg_0], rax
0x180018009  test    rax, rax
0x18001800c  jz      short loc_18001807D
0x18001800e  mov     [rax], r14
0x180018011  mov     [rax+8], rsi
0x180018015  mov     ecx, [rdi+8]
0x180018018  mov     [rax+18h], ecx
0x18001801b  movzx   eax, word ptr [rdi+0Ch]
0x18001801f  mov     [rbx+1Ch], ax
0x180018023  movzx   ecx, byte ptr [rbx+19h]
0x180018027  movzx   eax, byte ptr [rbx+18h]
0x18001802b  shl     rax, 8
0x18001802f  or      rcx, rax
0x180018032  shl     rcx, 8
0x180018036  movzx   eax, byte ptr [rbx+1Ah]
0x18001803a  or      rcx, rax
0x18001803d  shl     rcx, 8
0x180018041  movzx   eax, byte ptr [rbx+1Bh]
0x180018045  or      rcx, rax
0x180018048  shl     rcx, 8
0x18001804c  movzx   eax, byte ptr [rbx+1Ch]
0x180018050  or      rcx, rax
0x180018053  shl     rcx, 8
0x180018057  movzx   eax, byte ptr [rbx+1Dh]
0x18001805b  or      rcx, rax
0x18001805e  mov     [rbx+10h], rcx
0x180018062  lea     rdx, [rdi+10h]; struct VisibleDock *
0x180018066  lea     rcx, [rbx+20h]; this
0x18001806a  call    ??0VisibleDock@@QEAA@AEBV0@@Z; VisibleDock::VisibleDock(VisibleDock const &)
0x18001806f  nop
0x180018070  mov     rax, rbx
0x180018073  add     rsp, 48h
0x180018077  pop     r14
0x180018079  pop     rdi
0x18001807a  pop     rsi
0x18001807b  pop     rbx
0x18001807c  retn
0x18001807d  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180018082  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x180018087  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001808e  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180018093  call    _CxxThrowException_0
```
