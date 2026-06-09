# EventObjectCollection::AddItemToMap(ushort const *,IDispatch *)

- ea: `0x180006220`
- end: `0x18000652f`
- name: `?AddItemToMap@EventObjectCollection@@AEAAJPEBGPEAUIDispatch@@@Z`
- size: `783`
- prototype: `__int64 __fastcall(EventObjectCollection *this, const unsigned __int16 *, struct IDispatch *)`
- caller_count: `4`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180005cf0`
- `0x180020b40`
- `0x180028440`
- `0x180030080`

## callees

- `0x180003d54`
- `0x180006220`
- `0x180006540`
- `0x18000682c`
- `0x180012654`
- `0x180030720`
- `0x18003ecb0`
- `0x1800434ba`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800063fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000641e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800064af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800063fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000641e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800064af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000628a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000628a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800062bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006358`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800062bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006358`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000640c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000640c`

## string_xrefs

- `0x180006271`: `com\complus\src\events\Shared\UTSem.h`
- `0x1800064e7`: `com\complus\src\events\Shared\UTSem.h`

## pseudocode

```c
__int64 __fastcall EventObjectCollection::AddItemToMap(
        EventObjectCollection *this,
        const unsigned __int16 *a2,
        struct IDispatch *a3)
{
  char *v6; // rdi
  __int64 v7; // rax
  unsigned __int64 v8; // rsi
  _WORD *v9; // rax
  _WORD *v10; // r15
  _QWORD *v11; // r14
  int v12; // esi
  __int64 i; // rbx
  _WORD *v14; // rdx
  unsigned int v15; // r8d
  _QWORD *v16; // r9
  __int64 *v17; // r9
  signed __int32 j; // eax
  _QWORD *v19; // rdx
  __int64 v20; // rax
  _QWORD *v21; // rax
  _WORD *v22; // rax
  _WORD *v23; // rcx
  struct IDispatch *v25; // [rsp+A0h] [rbp+18h] BYREF
  void *v26; // [rsp+A8h] [rbp+20h] BYREF

  v25 = a3;
  v6 = (char *)this + 104;
  if ( this == (EventObjectCollection *)-104LL )
    InternalError(L"com\\complus\\src\\events\\Shared\\UTSem.h", 0x158u, 0x80001203, 0x10u);
  if ( !*((_DWORD *)v6 + 10) )
    InternalAssert(L"com\\complus\\src\\events\\Shared\\UTSem.h", 0x12Eu, 0x10u, L"m_fInitialized");
  EnterCriticalSection((LPCRITICAL_SECTION)v6);
  if ( a2 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
  }
  else
  {
    LODWORD(v7) = 0;
  }
  v8 = (unsigned int)(v7 + 1);
  v9 = CoTaskMemAlloc(saturated_mul(v8, 2u));
  v10 = v9;
  v26 = v9;
  if ( !v9 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
    return 2147942414LL;
  }
  memcpy_0(v9, a2, 2 * v8);
  v11 = (_QWORD *)((char *)this + 56);
  v12 = Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::allocAssocIfNecessary((char *)this + 56);
  if ( v12 >= 0 )
  {
    i = 0;
    v14 = v10;
    v15 = 19088743;
    while ( *v14 )
      v15 = (unsigned __int16)*v14++ + (v15 >> 27) + 32 * v15;
    if ( *v11 )
    {
      for ( i = *v11 + 8LL * (v15 % *((_DWORD *)this + 16)); *(_QWORD *)i; i = *(_QWORD *)i + 16LL )
      {
        v22 = v10;
        v23 = *(_WORD **)(*(_QWORD *)i + 32LL);
        if ( v23 == v10 )
        {
LABEL_28:
          *(_QWORD *)(*(_QWORD *)i + 32LL) = v10;
          *(_QWORD *)(*(_QWORD *)i + 40LL) = a3;
          goto LABEL_21;
        }
        if ( v23 && v10 )
        {
          while ( *v23 == *v22 )
          {
            if ( !*v23 )
              goto LABEL_28;
            ++v23;
            ++v22;
          }
        }
      }
    }
    v12 = 0;
    v16 = (_QWORD *)*((_QWORD *)this + 9);
    if ( v16 )
    {
      *((_QWORD *)this + 9) = v16[2];
      goto LABEL_16;
    }
    v16 = CoTaskMemAlloc(0x30u);
    if ( v16 )
    {
LABEL_16:
      Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::Assoc::Assoc(v16, &v26, &v25);
      for ( j = *((_DWORD *)v17 + 6);
            j != _InterlockedCompareExchange((volatile signed __int32 *)v17 + 6, j | 0x80000000, j);
            j = *((_DWORD *)v17 + 6) )
      {
        ;
      }
      v17[2] = *(_QWORD *)i;
      *(_QWORD *)i = v17;
      v19 = (_QWORD *)v17[1];
      v20 = *v17;
      *v19 = *v17;
      *(_QWORD *)(v20 + 8) = v19;
      v21 = (_QWORD *)*((_QWORD *)this + 11);
      *v21 = v17;
      v17[1] = (__int64)v21;
      *v17 = (__int64)this + 80;
      *((_QWORD *)this + 11) = v17;
      if ( ++*((_DWORD *)this + 17) > *((_DWORD *)this + 16) )
        v12 = Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow((char *)this + 56);
      goto LABEL_21;
    }
    v12 = -2147024882;
  }
LABEL_21:
  if ( v12 < 0 )
    CoTaskMemFree(v10);
  else
    ++*((_DWORD *)this + 24);
  LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180006220  mov     rax, rsp
0x180006223  mov     [rax+8], rbx
0x180006227  mov     [rax+10h], rsi
0x18000622b  mov     [rax+18h], r8
0x18000622f  push    rdi
0x180006230  push    r12
0x180006232  push    r13
0x180006234  push    r14
0x180006236  push    r15
0x180006238  sub     rsp, 60h
0x18000623c  mov     r12, r8
0x18000623f  mov     rbx, rdx
0x180006242  mov     r13, rcx
0x180006245  xor     r14d, r14d
0x180006248  mov     [rax-68h], r14d
0x18000624c  mov     [rsp+88h+var_40], 1
0x180006254  lea     rdi, [rcx+68h]
0x180006258  mov     [rsp+88h+var_38], rdi
0x18000625d  test    rdi, rdi
0x180006260  jnz     short loc_18000627D
0x180006262  mov     edx, 158h; unsigned int
0x180006267  lea     r9d, [r14+10h]; unsigned __int16
0x18000626b  mov     r8d, 80001203h; unsigned int
0x180006271  lea     rcx, aComComplusSrcE_4; "com\\complus\\src\\events\\Shared\\UTSe"...
0x180006278  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000627d  cmp     [rdi+28h], r14d
0x180006281  jz      loc_1800064D5
0x180006287  mov     rcx, rdi; lpCriticalSection
0x18000628a  call    cs:__imp_EnterCriticalSection
0x180006290  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006294  test    rbx, rbx
0x180006297  jz      loc_1800064F8
0x18000629d  mov     rax, rcx
0x1800062a0  inc     rax
0x1800062a3  cmp     [rbx+rax*2], r14w
0x1800062a8  jnz     short loc_1800062A0
0x1800062aa  lea     esi, [rax+1]
0x1800062ad  mov     eax, 2
0x1800062b2  mul     rsi
0x1800062b5  cmovb   rax, rcx
0x1800062b9  mov     rcx, rax; cb
0x1800062bc  call    cs:__imp_CoTaskMemAlloc
0x1800062c2  mov     r15, rax
0x1800062c5  mov     [rsp+88h+arg_18], rax
0x1800062cd  test    rax, rax
0x1800062d0  jz      loc_1800064AC
0x1800062d6  lea     r8, [rsi+rsi]; Size
0x1800062da  mov     rdx, rbx; Src
0x1800062dd  mov     rcx, rax; void *
0x1800062e0  call    memcpy_0
0x1800062e5  lea     r14, [r13+38h]
0x1800062e9  mov     rcx, r14
0x1800062ec  call    ?allocAssocIfNecessary@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@AEAAJXZ; Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::allocAssocIfNecessary(void)
0x1800062f1  mov     esi, eax
0x1800062f3  xor     r10d, r10d
0x1800062f6  test    eax, eax
0x1800062f8  js      loc_180006481
0x1800062fe  mov     ebx, r10d
0x180006301  mov     [rsp+88h+var_60], rbx
0x180006306  mov     rdx, r15
0x180006309  mov     [rsp+88h+var_58], rdx
0x18000630e  mov     r8d, 1234567h
0x180006314  cmp     [rdx], r10w
0x180006318  jz      short loc_180006338
0x18000631a  mov     ecx, r8d
0x18000631d  shr     ecx, 1Bh
0x180006320  shl     r8d, 5
0x180006324  add     r8d, ecx
0x180006327  movzx   eax, word ptr [rdx]
0x18000632a  add     r8d, eax
0x18000632d  add     rdx, 2
0x180006331  mov     [rsp+88h+var_58], rdx
0x180006336  jmp     short loc_180006314
0x180006338  mov     r9, [r14]
0x18000633b  test    r9, r9
0x18000633e  jnz     loc_18000642B
0x180006344  mov     esi, r10d
0x180006347  mov     r9, [r14+10h]
0x18000634b  test    r9, r9
0x18000634e  jnz     loc_18000646F
0x180006354  lea     ecx, [r9+30h]; cb
0x180006358  call    cs:__imp_CoTaskMemAlloc
0x18000635e  mov     r9, rax
0x180006361  test    rax, rax
0x180006364  jz      loc_18000647C
0x18000636a  lea     r8, [rsp+88h+arg_10]
0x180006372  lea     rdx, [rsp+88h+arg_18]
0x18000637a  mov     rcx, r9
0x18000637d  call    ??0Assoc@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@AEAA@AEBQEAGAEBQEAUIDispatch@@@Z; Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::Assoc::Assoc(ushort * const &,IDispatch * const &)
0x180006382  mov     eax, [r9+18h]
0x180006386  mov     ecx, eax
0x180006388  or      ecx, 80000000h
0x18000638e  lock cmpxchg [r9+18h], ecx
0x180006394  jz      short loc_18000639C
0x180006396  mov     eax, [r9+18h]
0x18000639a  jmp     short loc_180006386
0x18000639c  mov     rax, [rbx]
0x18000639f  mov     [r9+10h], rax
0x1800063a3  mov     [rbx], r9
0x1800063a6  lea     r8, [r14+18h]
0x1800063aa  mov     rdx, [r9+8]
0x1800063ae  mov     rax, [r9]
0x1800063b1  mov     [rdx], rax
0x1800063b4  mov     [rax+8], rdx
0x1800063b8  mov     rax, [r8+8]
0x1800063bc  mov     [rax], r9
0x1800063bf  mov     [r9+8], rax
0x1800063c3  mov     [r9], r8
0x1800063c6  mov     [r8+8], r9
0x1800063ca  mov     r12d, 1
0x1800063d0  add     [r14+0Ch], r12d
0x1800063d4  mov     eax, [r14+0Ch]
0x1800063d8  cmp     eax, [r14+8]
0x1800063dc  ja      loc_180006500
0x1800063e2  mov     [rsp+88h+var_68], esi
0x1800063e6  mov     eax, [rsp+88h+var_68]
0x1800063ea  test    eax, eax
0x1800063ec  js      short loc_180006409
0x1800063ee  add     [r13+60h], r12d
0x1800063f2  test    r12d, r12d
0x1800063f5  jz      loc_18000650F
0x1800063fb  mov     rcx, rdi; lpCriticalSection
0x1800063fe  call    cs:__imp_LeaveCriticalSection
0x180006404  jmp     loc_18000650F
0x180006409  mov     rcx, r15; pv
0x18000640c  call    cs:__imp_CoTaskMemFree
0x180006412  mov     ebx, [rsp+88h+var_68]
0x180006416  test    r12d, r12d
0x180006419  jz      short loc_180006424
0x18000641b  mov     rcx, rdi; lpCriticalSection
0x18000641e  call    cs:__imp_LeaveCriticalSection
0x180006424  mov     eax, ebx
0x180006426  jmp     loc_180006515
0x18000642b  xor     edx, edx
0x18000642d  mov     eax, r8d
0x180006430  div     dword ptr [r14+8]
0x180006434  lea     rbx, [r9+rdx*8]
0x180006438  mov     [rsp+88h+var_60], rbx
0x18000643d  mov     rcx, [rbx]
0x180006440  test    rcx, rcx
0x180006443  jz      loc_180006344
0x180006449  mov     rax, r15
0x18000644c  mov     [rsp+88h+var_48], rax
0x180006451  mov     rcx, [rcx+20h]
0x180006455  mov     [rsp+88h+var_50], rcx
0x18000645a  cmp     rcx, r15
0x18000645d  jnz     short loc_18000648C
0x18000645f  mov     rax, [rbx]
0x180006462  mov     [rax+20h], r15
0x180006466  mov     rax, [rbx]
0x180006469  mov     [rax+28h], r12
0x18000646d  jmp     short loc_180006481
0x18000646f  mov     rax, [r9+10h]
0x180006473  mov     [r14+10h], rax
0x180006477  jmp     loc_18000636A
0x18000647c  mov     esi, 8007000Eh
0x180006481  mov     r12d, 1
0x180006487  jmp     loc_1800063E2
0x18000648c  test    rcx, rcx
0x18000648f  jz      short loc_18000649E
0x180006491  test    rax, rax
0x180006494  jz      short loc_18000649E
0x180006496  movzx   edx, word ptr [rcx]
0x180006499  cmp     dx, [rax]
0x18000649c  jz      short loc_1800064BC
0x18000649e  mov     rbx, [rbx]
0x1800064a1  add     rbx, 10h
0x1800064a5  mov     [rsp+88h+var_60], rbx
0x1800064aa  jmp     short loc_18000643D
0x1800064ac  mov     rcx, rdi; lpCriticalSection
0x1800064af  call    cs:__imp_LeaveCriticalSection
0x1800064b5  mov     eax, 8007000Eh
0x1800064ba  jmp     short loc_180006515
0x1800064bc  test    dx, dx
0x1800064bf  jz      short loc_18000645F
0x1800064c1  add     rcx, 2
0x1800064c5  mov     [rsp+88h+var_50], rcx
0x1800064ca  add     rax, 2
0x1800064ce  mov     [rsp+88h+var_48], rax
0x1800064d3  jmp     short loc_180006496
0x1800064d5  mov     r8d, 10h; unsigned __int16
0x1800064db  lea     r9, aMFinitialized; "m_fInitialized"
0x1800064e2  mov     edx, 12Eh; unsigned int
0x1800064e7  lea     rcx, aComComplusSrcE_4; "com\\complus\\src\\events\\Shared\\UTSe"...
0x1800064ee  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x1800064f3  jmp     loc_180006287
0x1800064f8  mov     rax, r14
0x1800064fb  jmp     loc_1800062AA
0x180006500  mov     rcx, r14
0x180006503  call    ?grow@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@AEAAJXZ; Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow(void)
0x180006508  mov     esi, eax
0x18000650a  jmp     loc_1800063E2
0x18000650f  jmp     short $+2
0x180006511  mov     eax, [rsp+88h+var_68]
0x180006515  lea     r11, [rsp+88h+var_28]
0x18000651a  mov     rbx, [r11+30h]
0x18000651e  mov     rsi, [r11+38h]
0x180006522  mov     rsp, r11
0x180006525  pop     r15
0x180006527  pop     r14
0x180006529  pop     r13
0x18000652b  pop     r12
0x18000652d  pop     rdi
0x18000652e  retn
0x18004372c  push    rbp
0x18004372e  sub     rsp, 20h
0x180043732  mov     rbp, rdx
0x180043735  lea     rdx, [rbp+20h]; int *
0x180043739  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x18004373e  nop
0x18004373f  add     rsp, 20h
0x180043743  pop     rbp
0x180043744  retn
```
