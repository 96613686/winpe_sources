# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPersistDSO>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180019660`
- end: `0x180019703`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCPersistDSO@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001dd4`
- `0x18000ca08`
- `0x18000ca34`
- `0x180018bc8`
- `0x180018eb0`
- `0x180019660`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPersistDSO>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  unsigned __int8 *v6; // rax
  int *v7; // rsi
  int *v8; // rcx

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      return (unsigned int)-2147221232;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v5 = -2147024882;
  v6 = MMMAlloc(0x1380u, a2);
  if ( v6 )
    v7 = (int *)ATL::CComObject<CPersistDSO>::CComObject<CPersistDSO>(v6);
  else
    v7 = 0;
  if ( v7 )
  {
    ATL::SafeIncrementReferenceMultiThread(v7 + 12);
    ATL::SafeDecrementReferenceMultiThread(v8);
    v5 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, a2, a3);
    if ( v5 )
      ATL::CComObject<CPersistDSO>::`scalar deleting destructor'(v7);
  }
  return v5;
}

```

## disassembly

```asm
0x180019660  push    rbx
0x180019662  push    rbp
0x180019663  push    rsi
0x180019664  push    rdi
0x180019665  sub     rsp, 28h
0x180019669  mov     rdi, r8
0x18001966c  mov     rbp, rdx
0x18001966f  test    rcx, rcx
0x180019672  jnz     short loc_1800196E6
0x180019674  test    r8, r8
0x180019677  jnz     short loc_180019680
0x180019679  mov     ebx, 80004003h
0x18001967e  jmp     short loc_1800196F7
0x180019680  mov     qword ptr [r8], 0
0x180019687  mov     ebx, 8007000Eh
0x18001968c  mov     ecx, 1380h; unsigned int
0x180019691  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180019696  mov     [rsp+48h+arg_0], rax
0x18001969b  test    rax, rax
0x18001969e  jz      short loc_1800196AD
0x1800196a0  mov     rcx, rax
0x1800196a3  call    ??0?$CComObject@VCPersistDSO@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CPersistDSO>::CComObject<CPersistDSO>(void *)
0x1800196a8  mov     rsi, rax
0x1800196ab  jmp     short loc_1800196AF
0x1800196ad  xor     esi, esi
0x1800196af  test    rsi, rsi
0x1800196b2  jz      short loc_1800196F7
0x1800196b4  lea     rcx, [rsi+30h]; int *
0x1800196b8  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPEAJ@Z; ATL::SafeIncrementReferenceMultiThread(long *)
0x1800196bd  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPEAJ@Z; ATL::SafeDecrementReferenceMultiThread(long *)
0x1800196c2  mov     rcx, [rsi]
0x1800196c5  mov     rax, [rcx]
0x1800196c8  mov     r8, rdi
0x1800196cb  mov     rdx, rbp
0x1800196ce  mov     rcx, rsi
0x1800196d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196d6  mov     ebx, eax
0x1800196d8  test    eax, eax
0x1800196da  jz      short loc_1800196F7
0x1800196dc  mov     rcx, rsi; void *
0x1800196df  call    ??_G?$CComObject@VCPersistDSO@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CPersistDSO>::`scalar deleting destructor'(uint)
0x1800196e4  jmp     short loc_1800196F7
0x1800196e6  test    rdi, rdi
0x1800196e9  jz      short loc_180019679
0x1800196eb  mov     qword ptr [r8], 0
0x1800196f2  mov     ebx, 80040110h
0x1800196f7  mov     eax, ebx
0x1800196f9  add     rsp, 28h
0x1800196fd  pop     rdi
0x1800196fe  pop     rsi
0x1800196ff  pop     rbp
0x180019700  pop     rbx
0x180019701  retn
```
