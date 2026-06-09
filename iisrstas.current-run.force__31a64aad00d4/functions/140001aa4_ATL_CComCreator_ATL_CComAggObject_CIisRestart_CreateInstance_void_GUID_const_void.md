# ATL::CComCreator<ATL::CComAggObject<CIisRestart>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140001aa4`
- end: `0x140001b92`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCIisRestart@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140001a90`

## callees

- `0x140001014`
- `0x140001054`
- `0x140001aa4`
- `0x14000232c`
- `0x1400029d8`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140001b73`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140001b73`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CIisRestart>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v7; // esi
  char *v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  _BYTE *v10; // rdi
  CExeModule *v11; // rcx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x58u);
  v9 = (struct _RTL_CRITICAL_SECTION *)v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<CIisRestart>::`vftable';
    *(_OWORD *)(v8 + 40) = 0;
    *(_OWORD *)(v8 + 56) = 0;
    *((_QWORD *)v8 + 9) = 0;
    v8[80] = 0;
    *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CIisRestart>::`vftable';
    *((_QWORD *)v8 + 4) = a1;
    _InterlockedIncrement(&dword_14000A798);
    v10 = v8 + 80;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 40));
    if ( v7 < 0
      || (*v10 = 1,
          (v7 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, _QWORD *))v9->DebugInfo->Type)(
                  v9,
                  a2,
                  a3)) != 0) )
    {
      v9->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CIisRestart>::`vftable';
      v9->LockCount = 1;
      CExeModule::Unlock(v11);
      if ( *v10 )
      {
        *v10 = 0;
        DeleteCriticalSection(v9 + 1);
      }
      operator delete(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140001aa4  push    rbx
0x140001aa6  push    rbp
0x140001aa7  push    rsi
0x140001aa8  push    rdi
0x140001aa9  push    r13
0x140001aab  push    r14
0x140001aad  push    r15
0x140001aaf  sub     rsp, 20h
0x140001ab3  mov     r14, r8
0x140001ab6  mov     r15, rdx
0x140001ab9  mov     rdi, rcx
0x140001abc  test    r8, r8
0x140001abf  jnz     short loc_140001ACB
0x140001ac1  mov     eax, 80004003h
0x140001ac6  jmp     loc_140001B83
0x140001acb  mov     ecx, 58h ; 'X'; Size
0x140001ad0  mov     qword ptr [r8], 0
0x140001ad7  mov     esi, 8007000Eh
0x140001adc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001ae1  mov     rbx, rax
0x140001ae4  test    rax, rax
0x140001ae7  jz      loc_140001B81
0x140001aed  mov     dword ptr [rax+8], 0
0x140001af4  lea     r13, ??_7?$CComAggObject@VCIisRestart@@@ATL@@6B@; const ATL::CComAggObject<CIisRestart>::`vftable'
0x140001afb  mov     [rax], r13
0x140001afe  xorps   xmm0, xmm0
0x140001b01  movups  xmmword ptr [rbx+28h], xmm0
0x140001b05  xor     eax, eax
0x140001b07  movups  xmmword ptr [rbx+38h], xmm0
0x140001b0b  mov     [rbx+48h], rax
0x140001b0f  mov     [rbx+50h], al
0x140001b12  lea     rax, ??_7?$CComContainedObject@VCIisRestart@@@ATL@@6B@; const ATL::CComContainedObject<CIisRestart>::`vftable'
0x140001b19  mov     [rbx+18h], rax
0x140001b1d  mov     [rbx+20h], rdi
0x140001b21  lock inc cs:dword_14000A798
0x140001b28  lea     rcx, [rbx+28h]; this
0x140001b2c  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140001b31  lea     rdi, [rbx+50h]
0x140001b35  mov     esi, eax
0x140001b37  test    eax, eax
0x140001b39  js      short loc_140001B58
0x140001b3b  mov     byte ptr [rdi], 1
0x140001b3e  mov     r8, r14
0x140001b41  mov     rax, [rbx]
0x140001b44  mov     rdx, r15
0x140001b47  mov     rcx, rbx
0x140001b4a  mov     rax, [rax]
0x140001b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001b52  mov     esi, eax
0x140001b54  test    eax, eax
0x140001b56  jz      short loc_140001B81
0x140001b58  mov     [rbx], r13
0x140001b5b  mov     dword ptr [rbx+8], 1
0x140001b62  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x140001b67  cmp     byte ptr [rdi], 0
0x140001b6a  jz      short loc_140001B79
0x140001b6c  lea     rcx, [rbx+28h]; lpCriticalSection
0x140001b70  mov     byte ptr [rdi], 0
0x140001b73  call    cs:__imp_DeleteCriticalSection
0x140001b79  mov     rcx, rbx; Block
0x140001b7c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001b81  mov     eax, esi
0x140001b83  add     rsp, 20h
0x140001b87  pop     r15
0x140001b89  pop     r14
0x140001b8b  pop     r13
0x140001b8d  pop     rdi
0x140001b8e  pop     rsi
0x140001b8f  pop     rbp
0x140001b90  pop     rbx
0x140001b91  retn
```
