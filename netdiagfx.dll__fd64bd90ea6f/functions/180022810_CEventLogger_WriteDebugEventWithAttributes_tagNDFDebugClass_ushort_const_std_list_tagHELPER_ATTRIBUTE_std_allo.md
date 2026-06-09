# CEventLogger::WriteDebugEventWithAttributes(tagNDFDebugClass,ushort const *,std::list<tagHELPER_ATTRIBUTE,std::allocator<tagHELPER_ATTRIBUTE>> *)

- ea: `0x180022810`
- end: `0x1800228ae`
- name: `?WriteDebugEventWithAttributes@CEventLogger@@UEAAJW4tagNDFDebugClass@@PEBGPEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@@Z`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056bc`
- `0x180011b70`
- `0x180022810`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022879`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022879`

## pseudocode

```c
__int64 __fastcall CEventLogger::WriteDebugEventWithAttributes(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  _OWORD *v9; // rbx
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64, _OWORD *, int); // r14
  int v11; // eax
  unsigned int v12; // edi

  if ( !a3 )
    return 2147942487LL;
  v9 = 0;
  if ( a4 )
    v9 = ListToArray<tagHELPER_ATTRIBUTE>(a4);
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _OWORD *, int))(*(_QWORD *)a1 + 120LL);
  if ( v9 )
  {
    v11 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*(_QWORD *)(a4 + 8));
    v12 = v10(a1, a2, a3, v9, v11);
    CoTaskMemFree(v9);
  }
  else
  {
    return (unsigned int)v10(a1, a2, a3, 0, 0);
  }
  return v12;
}

```

## disassembly

```asm
0x180022810  push    rbx
0x180022812  push    rbp
0x180022813  push    rsi
0x180022814  push    rdi
0x180022815  push    r14
0x180022817  push    r15
0x180022819  sub     rsp, 38h
0x18002281d  mov     rdi, r9
0x180022820  mov     rbp, r8
0x180022823  mov     r15d, edx
0x180022826  mov     rsi, rcx
0x180022829  test    r8, r8
0x18002282c  jnz     short loc_180022835
0x18002282e  mov     eax, 80070057h
0x180022833  jmp     short loc_1800228A1
0x180022835  xor     ebx, ebx
0x180022837  test    rdi, rdi
0x18002283a  jz      short loc_180022847
0x18002283c  mov     rcx, rdi
0x18002283f  call    ??$ListToArray@UtagHELPER_ATTRIBUTE@@@@YAPEAUtagHELPER_ATTRIBUTE@@PEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@@Z; ListToArray<tagHELPER_ATTRIBUTE>(std::list<tagHELPER_ATTRIBUTE> *)
0x180022844  mov     rbx, rax
0x180022847  mov     rcx, [rsi]
0x18002284a  mov     r14, [rcx+78h]
0x18002284e  test    rbx, rbx
0x180022851  jz      short loc_180022881
0x180022853  mov     rcx, [rdi+8]
0x180022857  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18002285c  mov     [rsp+68h+var_48], eax
0x180022860  mov     r9, rbx
0x180022863  mov     rax, r14
0x180022866  mov     r8, rbp
0x180022869  mov     edx, r15d
0x18002286c  mov     rcx, rsi
0x18002286f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022874  mov     rcx, rbx; pv
0x180022877  mov     edi, eax
0x180022879  call    cs:__imp_CoTaskMemFree
0x18002287f  jmp     short loc_18002289F
0x180022881  xor     r9d, r9d
0x180022884  mov     [rsp+68h+var_48], 0
0x18002288c  mov     r8, rbp
0x18002288f  mov     edx, r15d
0x180022892  mov     rcx, rsi
0x180022895  mov     rax, r14
0x180022898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002289d  mov     edi, eax
0x18002289f  mov     eax, edi
0x1800228a1  add     rsp, 38h
0x1800228a5  pop     r15
0x1800228a7  pop     r14
0x1800228a9  pop     rdi
0x1800228aa  pop     rsi
0x1800228ab  pop     rbp
0x1800228ac  pop     rbx
0x1800228ad  retn
```
