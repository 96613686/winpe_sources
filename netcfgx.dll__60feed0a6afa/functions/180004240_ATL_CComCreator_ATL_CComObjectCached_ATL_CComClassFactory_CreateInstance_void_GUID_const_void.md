# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004240`
- end: `0x18000436a`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001fec`
- `0x180004240`
- `0x18000465c`
- `0x180007d38`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004346`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004346`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // r15

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)MemAlloc(0x48u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *((_OWORD *)v8 + 1) = 0;
    *((_OWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 6) = 0;
    v8[56] = 0;
    *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    *((_QWORD *)v9 + 8) = a1;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 16));
    v10 = v9 + 56;
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactory::`vftable';
      if ( *v10 )
      {
        *v10 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      operator delete(v9, 0x48u);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004240  mov     [rsp+arg_10], r8
0x180004245  mov     [rsp+arg_8], rdx
0x18000424a  mov     [rsp+arg_0], rcx
0x18000424f  push    rbx
0x180004250  push    rsi
0x180004251  push    r12
0x180004253  push    r13
0x180004255  push    r14
0x180004257  push    r15
0x180004259  sub     rsp, 38h
0x18000425d  mov     r14, r8
0x180004260  mov     r12, rdx
0x180004263  mov     r15, rcx
0x180004266  test    r8, r8
0x180004269  jnz     short loc_180004275
0x18000426b  mov     eax, 80004003h
0x180004270  jmp     loc_18000435B
0x180004275  mov     qword ptr [r8], 0
0x18000427c  mov     esi, 8007000Eh
0x180004281  mov     [rsp+68h+arg_18], esi
0x180004288  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000428d  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180004292  mov     rbx, rax
0x180004295  mov     [rsp+68h+var_48], rax
0x18000429a  test    rax, rax
0x18000429d  jz      short loc_1800042C6
0x18000429f  mov     dword ptr [rax+8], 0
0x1800042a6  xorps   xmm0, xmm0
0x1800042a9  xor     eax, eax
0x1800042ab  movups  xmmword ptr [rbx+10h], xmm0
0x1800042af  movups  xmmword ptr [rbx+20h], xmm0
0x1800042b3  mov     [rbx+30h], rax
0x1800042b7  mov     [rbx+38h], al
0x1800042ba  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x1800042c1  mov     [rbx], rax
0x1800042c4  jmp     short loc_1800042C8
0x1800042c6  xor     ebx, ebx
0x1800042c8  mov     [rsp+68h+var_48], rbx
0x1800042cd  jmp     short loc_1800042ED
0x1800042cf  mov     r14, [rsp+68h+arg_10]
0x1800042d7  mov     r12, [rsp+68h+arg_8]
0x1800042dc  mov     r15, [rsp+68h+arg_0]
0x1800042e1  mov     esi, [rsp+68h+arg_18]
0x1800042e8  mov     rbx, [rsp+68h+var_48]
0x1800042ed  test    rbx, rbx
0x1800042f0  jz      short loc_180004359
0x1800042f2  mov     [rbx+40h], r15
0x1800042f6  lea     rcx, [rbx+10h]; this
0x1800042fa  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800042ff  mov     esi, eax
0x180004301  lea     r15, [rbx+38h]
0x180004305  test    eax, eax
0x180004307  js      short loc_180004327
0x180004309  mov     byte ptr [r15], 1
0x18000430d  mov     rax, [rbx]
0x180004310  mov     r8, r14
0x180004313  mov     rdx, r12
0x180004316  mov     rcx, rbx
0x180004319  mov     rax, [rax]
0x18000431c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004321  mov     esi, eax
0x180004323  test    eax, eax
0x180004325  jz      short loc_180004359
0x180004327  mov     dword ptr [rbx+8], 0C0000001h
0x18000432e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180004335  mov     [rbx], rax
0x180004338  cmp     byte ptr [r15], 0
0x18000433c  jz      short loc_18000434C
0x18000433e  mov     byte ptr [r15], 0
0x180004342  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004346  call    cs:__imp_DeleteCriticalSection
0x18000434c  mov     edx, 48h ; 'H'; unsigned __int64
0x180004351  mov     rcx, rbx; void *
0x180004354  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004359  mov     eax, esi
0x18000435b  add     rsp, 38h
0x18000435f  pop     r15
0x180004361  pop     r14
0x180004363  pop     r13
0x180004365  pop     r12
0x180004367  pop     rsi
0x180004368  pop     rbx
0x180004369  retn
```
