# ATL::CAtlModule::Term(void)

- ea: `0x1800076d8`
- end: `0x18000778a`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `178`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006928`

## callees

- `0x180001bc4`
- `0x1800076d8`
- `0x180039010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007771`
- `KERNEL32!DeleteCriticalSection` at `0x180007771`
- `KERNEL32!RaiseException` at `0x180007718`
- `KERNEL32!RaiseException` at `0x180007718`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v2; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v2 & -(__int64)(this != 0);
      if ( !v3 )
      {
        RaiseException(0xC0000005, 1u, 0, 0);
        __debugbreak();
      }
      v4 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
      if ( v4 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v4)(v4[1]);
          v5 = (_QWORD *)v4[2];
          operator delete(v4);
          v4 = v5;
        }
        while ( v5 );
      }
      *(_QWORD *)(v3 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v6 = *((_QWORD *)this + 8);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x1800076d8  push    rbx
0x1800076da  push    rsi
0x1800076db  push    rdi
0x1800076dc  push    r14
0x1800076de  push    r15
0x1800076e0  sub     rsp, 20h
0x1800076e4  mov     rdi, rcx
0x1800076e7  lea     r14, [rcx+8]
0x1800076eb  cmp     dword ptr [r14], 0
0x1800076ef  jz      loc_18000777E
0x1800076f5  cmp     qword ptr [rcx+10h], 0
0x1800076fa  jz      short loc_180007758
0x1800076fc  mov     rax, rcx
0x1800076ff  neg     rax
0x180007702  sbb     rsi, rsi
0x180007705  and     rsi, r14
0x180007708  jnz     short loc_18000771F
0x18000770a  xor     r9d, r9d; lpArguments
0x18000770d  xor     r8d, r8d; nNumberOfArguments
0x180007710  lea     edx, [rsi+1]; dwExceptionFlags
0x180007713  mov     ecx, 0C0000005h; dwExceptionCode
0x180007718  call    cs:__imp_RaiseException
0x18000771e  int     3; Trap to Debugger
0x18000771f  mov     r15, [rsi+8]
0x180007723  test    r15, r15
0x180007726  jz      short loc_180007748
0x180007728  mov     rcx, [r15+8]
0x18000772c  mov     rax, [r15]
0x18000772f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007734  mov     rbx, [r15+10h]
0x180007738  mov     rcx, r15; Block
0x18000773b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007740  mov     r15, rbx
0x180007743  test    rbx, rbx
0x180007746  jnz     short loc_180007728
0x180007748  mov     qword ptr [rsi+8], 0
0x180007750  mov     qword ptr [rdi+10h], 0
0x180007758  mov     rcx, [rdi+40h]
0x18000775c  test    rcx, rcx
0x18000775f  jz      short loc_18000776D
0x180007761  mov     rax, [rcx]
0x180007764  mov     rax, [rax+10h]
0x180007768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000776d  lea     rcx, [rdi+18h]; lpCriticalSection
0x180007771  call    cs:__imp_DeleteCriticalSection
0x180007777  mov     dword ptr [r14], 0
0x18000777e  add     rsp, 20h
0x180007782  pop     r15
0x180007784  pop     r14
0x180007786  pop     rdi
0x180007787  pop     rsi
0x180007788  pop     rbx
0x180007789  retn
```
