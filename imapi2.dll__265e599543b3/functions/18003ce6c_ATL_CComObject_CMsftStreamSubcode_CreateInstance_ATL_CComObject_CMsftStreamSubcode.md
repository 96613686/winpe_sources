# ATL::CComObject<CMsftStreamSubcode>::CreateInstance(ATL::CComObject<CMsftStreamSubcode> * *)

- ea: `0x18003ce6c`
- end: `0x18003cf26`
- name: `?CreateInstance@?$CComObject@VCMsftStreamSubcode@@@ATL@@SAJPEAPEAV12@@Z`
- size: `186`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003cf30`

## callees

- `0x180005fa4`
- `0x18000ea44`
- `0x18000ee90`
- `0x18000fdd4`
- `0x18003c0d8`
- `0x18003ce6c`
- `0x18003fc84`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMsftStreamSubcode>::CreateInstance(volatile int **a1)
{
  CMsftStreamSubcode *v3; // rax
  volatile int *v4; // rbx
  int v5; // eax
  unsigned int v6; // edi

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = (CMsftStreamSubcode *)operator new(0xB8u);
  v4 = (volatile int *)v3;
  if ( !v3 )
  {
    v6 = -2147024882;
    goto LABEL_12;
  }
  CMsftStreamSubcode::CMsftStreamSubcode(v3);
  *(_QWORD *)v4 = &ATL::CComObject<CMsftStreamSubcode>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  ATL::SafeIncrementReferenceMultiThread(v4 + 2);
  v5 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v4 + 4));
  if ( v5 >= 0 )
    v5 = CMsftStreamSubcode::FinalConstruct((CMsftStreamSubcode *)v4);
  v6 = 0;
  if ( v5 < 0 )
    v6 = v5;
  ATL::SafeDecrementReferenceMultiThread(v4 + 2);
  if ( v6 )
  {
    (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v4 + 112LL))(v4, 1);
LABEL_12:
    v4 = 0;
    goto LABEL_13;
  }
  v6 = 0;
LABEL_13:
  *a1 = v4;
  return v6;
}

```

## disassembly

```asm
0x18003ce6c  push    rbx
0x18003ce6e  push    rbp
0x18003ce6f  push    rsi
0x18003ce70  push    rdi
0x18003ce71  sub     rsp, 28h
0x18003ce75  mov     rsi, rcx
0x18003ce78  test    rcx, rcx
0x18003ce7b  jnz     short loc_18003CE87
0x18003ce7d  mov     eax, 80004003h
0x18003ce82  jmp     loc_18003CF1D
0x18003ce87  mov     qword ptr [rcx], 0
0x18003ce8e  mov     ecx, 0B8h; Size
0x18003ce93  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ce98  mov     rbx, rax
0x18003ce9b  test    rax, rax
0x18003ce9e  jz      short loc_18003CF11
0x18003cea0  mov     rcx, rax; this
0x18003cea3  call    ??0CMsftStreamSubcode@@QEAA@XZ; CMsftStreamSubcode::CMsftStreamSubcode(void)
0x18003cea8  lea     rcx, ??_7?$CComObject@VCMsftStreamSubcode@@@ATL@@6B@; const ATL::CComObject<CMsftStreamSubcode>::`vftable'
0x18003ceaf  mov     [rbx], rcx
0x18003ceb2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18003ceb9  mov     rax, [rcx]
0x18003cebc  mov     rax, [rax+8]
0x18003cec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cec5  lea     rcx, [rbx+8]; volatile int *
0x18003cec9  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18003cece  lea     rcx, [rbx+10h]; this
0x18003ced2  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18003ced7  test    eax, eax
0x18003ced9  js      short loc_18003CEE3
0x18003cedb  mov     rcx, rbx; this
0x18003cede  call    ?FinalConstruct@CMsftStreamSubcode@@QEAAJXZ; CMsftStreamSubcode::FinalConstruct(void)
0x18003cee3  xor     edi, edi
0x18003cee5  lea     rcx, [rbx+8]; volatile int *
0x18003cee9  test    eax, eax
0x18003ceeb  cmovs   edi, eax
0x18003ceee  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18003cef3  test    edi, edi
0x18003cef5  jz      short loc_18003CF0D
0x18003cef7  mov     rax, [rbx]
0x18003cefa  mov     edx, 1
0x18003ceff  mov     rcx, rbx
0x18003cf02  mov     rax, [rax+70h]
0x18003cf06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf0b  jmp     short loc_18003CF16
0x18003cf0d  xor     edi, edi
0x18003cf0f  jmp     short loc_18003CF18
0x18003cf11  mov     edi, 8007000Eh
0x18003cf16  xor     ebx, ebx
0x18003cf18  mov     [rsi], rbx
0x18003cf1b  mov     eax, edi
0x18003cf1d  add     rsp, 28h
0x18003cf21  pop     rdi
0x18003cf22  pop     rsi
0x18003cf23  pop     rbp
0x18003cf24  pop     rbx
0x18003cf25  retn
```
