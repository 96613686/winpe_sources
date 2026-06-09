# ATL::CComObject<CMSDiscRecorderObj>::CreateInstance(ATL::CComObject<CMSDiscRecorderObj> * *)

- ea: `0x18000aaa4`
- end: `0x18000ab89`
- name: `?CreateInstance@?$CComObject@VCMSDiscRecorderObj@@@ATL@@SAJPEAPEAV12@@Z`
- size: `229`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ab90`

## callees

- `0x18000115c`
- `0x180002f5c`
- `0x18000aaa4`
- `0x18000e850`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSDiscRecorderObj>::CreateInstance(CMSDiscRecorderObj **a1)
{
  CMSDiscRecorderObj *v3; // rax
  CMSDiscRecorderObj *v4; // rbx
  ATL::CAtlModule *v5; // rcx
  volatile signed __int32 *v6; // rsi
  signed __int32 v7; // eax
  int v8; // eax
  int v9; // ecx
  unsigned int v10; // edi
  signed __int32 v11; // eax

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = (CMSDiscRecorderObj *)operator new(0xE8u);
  v4 = v3;
  if ( v3 )
  {
    CMSDiscRecorderObj::CMSDiscRecorderObj(v3);
    v5 = ATL::_pAtlModule;
    *(_QWORD *)v4 = &ATL::CComObject<CMSDiscRecorderObj>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v4 + 1) = &ATL::CComObject<CMSDiscRecorderObj>::`vftable'{for `IDiscRecorder'};
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)v5 + 8LL))(v5);
    v6 = (volatile signed __int32 *)((char *)v4 + 16);
    do
    {
      if ( *v6 == 0x7FFFFFFF )
        break;
      v7 = *v6;
    }
    while ( v7 != _InterlockedCompareExchange(v6, v7 + 1, v7) );
    v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)((char *)v4 + 24));
    if ( v8 >= 0 )
      *((_BYTE *)v4 + 64) = 1;
    v9 = 0;
    if ( v8 < 0 )
      v9 = v8;
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    do
    {
      if ( *v6 == 0x7FFFFFFF )
        break;
      v11 = *v6;
    }
    while ( v11 != _InterlockedCompareExchange(v6, v11 - 1, v11) );
    if ( !v10 )
      goto LABEL_20;
    (*(void (__fastcall **)(CMSDiscRecorderObj *, __int64))(*(_QWORD *)v4 + 32LL))(v4, 1);
  }
  else
  {
    v10 = -2147024882;
  }
  v4 = 0;
LABEL_20:
  *a1 = v4;
  return v10;
}

```

## disassembly

```asm
0x18000aaa4  push    rbx
0x18000aaa6  push    rbp
0x18000aaa7  push    rsi
0x18000aaa8  push    rdi
0x18000aaa9  push    r14
0x18000aaab  sub     rsp, 20h
0x18000aaaf  mov     r14, rcx
0x18000aab2  test    rcx, rcx
0x18000aab5  jnz     short loc_18000AAC1
0x18000aab7  mov     eax, 80004003h
0x18000aabc  jmp     loc_18000AB7E
0x18000aac1  mov     qword ptr [rcx], 0
0x18000aac8  mov     ecx, 0E8h; Size
0x18000aacd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aad2  mov     rbx, rax
0x18000aad5  test    rax, rax
0x18000aad8  jz      loc_18000AB72
0x18000aade  mov     rcx, rax; this
0x18000aae1  call    ??0CMSDiscRecorderObj@@QEAA@XZ; CMSDiscRecorderObj::CMSDiscRecorderObj(void)
0x18000aae6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000aaed  lea     rax, ??_7?$CComObject@VCMSDiscRecorderObj@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSDiscRecorderObj>::`vftable'{for `ISupportErrorInfo'}
0x18000aaf4  mov     [rbx], rax
0x18000aaf7  lea     rax, ??_7?$CComObject@VCMSDiscRecorderObj@@@ATL@@6BIDiscRecorder@@@; const ATL::CComObject<CMSDiscRecorderObj>::`vftable'{for `IDiscRecorder'}
0x18000aafe  mov     [rbx+8], rax
0x18000ab02  mov     rax, [rcx]
0x18000ab05  mov     rax, [rax+8]
0x18000ab09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab0e  lea     rsi, [rbx+10h]
0x18000ab12  mov     ebp, 7FFFFFFFh
0x18000ab17  jmp     short loc_18000AB22
0x18000ab19  lea     ecx, [rax+1]
0x18000ab1c  lock cmpxchg [rsi], ecx
0x18000ab20  jz      short loc_18000AB28
0x18000ab22  mov     eax, [rsi]
0x18000ab24  cmp     eax, ebp
0x18000ab26  jnz     short loc_18000AB19
0x18000ab28  lea     rcx, [rsi+8]; this
0x18000ab2c  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000ab31  test    eax, eax
0x18000ab33  js      short loc_18000AB39
0x18000ab35  mov     byte ptr [rsi+30h], 1
0x18000ab39  xor     ecx, ecx
0x18000ab3b  test    eax, eax
0x18000ab3d  cmovs   ecx, eax
0x18000ab40  xor     edi, edi
0x18000ab42  test    ecx, ecx
0x18000ab44  cmovs   edi, ecx
0x18000ab47  jmp     short loc_18000AB52
0x18000ab49  lea     ecx, [rax-1]
0x18000ab4c  lock cmpxchg [rsi], ecx
0x18000ab50  jz      short loc_18000AB58
0x18000ab52  mov     eax, [rsi]
0x18000ab54  cmp     eax, ebp
0x18000ab56  jnz     short loc_18000AB49
0x18000ab58  test    edi, edi
0x18000ab5a  jz      short loc_18000AB79
0x18000ab5c  mov     rax, [rbx]
0x18000ab5f  mov     edx, 1
0x18000ab64  mov     rcx, rbx
0x18000ab67  mov     rax, [rax+20h]
0x18000ab6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab70  jmp     short loc_18000AB77
0x18000ab72  mov     edi, 8007000Eh
0x18000ab77  xor     ebx, ebx
0x18000ab79  mov     [r14], rbx
0x18000ab7c  mov     eax, edi
0x18000ab7e  add     rsp, 20h
0x18000ab82  pop     r14
0x18000ab84  pop     rdi
0x18000ab85  pop     rsi
0x18000ab86  pop     rbp
0x18000ab87  pop     rbx
0x18000ab88  retn
```
