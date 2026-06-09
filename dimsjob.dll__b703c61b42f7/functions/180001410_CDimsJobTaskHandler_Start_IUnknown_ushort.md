# CDimsJobTaskHandler::Start(IUnknown *,ushort *)

- ea: `0x180001410`
- end: `0x180001768`
- name: `?Start@CDimsJobTaskHandler@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `856`
- prototype: `__int64 __fastcall(CDimsJobTaskHandler *this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001190`
- `0x180001410`
- `0x180001770`
- `0x1800018f0`
- `0x180001b20`
- `0x1800022c0`
- `0x180003260`
- `0x18000a338`
- `0x18000a360`
- `0x18000a650`
- `0x18000aac8`
- `0x18000ad30`
- `0x18000c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000148a`
- `msvcrt!_wcsicmp` at `0x18000148a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000167c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000167c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001517`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001701`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001517`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001701`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800014fb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800014fb`

## pseudocode

```c
__int64 __fastcall CDimsJobTaskHandler::Start(CDimsJobTaskHandler *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  const wchar_t *v3; // r14
  unsigned int v6; // ebx
  unsigned int i; // r15d
  unsigned int v8; // eax
  char *v9; // rdi
  int v10; // ebx
  __int64; // rax
  CDims *v12; // rax
  unsigned int v13; // r8d
  unsigned int v14; // r9d
  CDims *v15; // r14
  CDims *v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  CExcept *v21; // rbx
  char *v22; // [rsp+30h] [rbp-78h] BYREF
  unsigned int v23; // [rsp+38h] [rbp-70h] BYREF
  CExcept *v24; // [rsp+40h] [rbp-68h] BYREF
  char *v25; // [rsp+48h] [rbp-60h]
  void *v26; // [rsp+50h] [rbp-58h] BYREF
  int v27; // [rsp+58h] [rbp-50h]
  int v28; // [rsp+5Ch] [rbp-4Ch]

  v3 = a3;
  v23 = 2;
  if ( !a2 )
    goto LABEL_22;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a3);
  v6 = 0;
  if ( v3 )
  {
    for ( i = 0; i < 5; ++i )
    {
      if ( !_wcsicmp(v3, (&off_18000D010)[2 * i]) )
      {
        v6 = *((_DWORD *)&off_18000D010 + 4 * i + 2);
        break;
      }
    }
  }
  RetrieveLogLevel((HKEY)((v6 == 256) - 0x7FFFFFFFLL), (int *)&v23);
  v8 = v23;
  *((_DWORD *)this + 14) = v23;
  if ( v8 > 3 )
    LogReport(DM_LOG_INFO_STARTED, 0, 0);
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids);
    if ( *((_DWORD *)this + 14) > 2u )
    {
      if ( v3 )
      {
        v17 = -1;
        do
          ++v17;
        while ( v3[v17] );
        v18 = 2 * v17 + 2;
      }
      else
      {
        v18 = 14;
        v3 = L"<NULL>";
      }
      v26 = (void *)v3;
      v27 = v18;
      v28 = 0;
      LogReport(DM_LOG_WARNING_BADPARAM, 1, &v26);
      LocalFree(0);
       = 2147942487LL;
      goto LABEL_58;
    }
LABEL_22:
     = 2147942487LL;
    goto LABEL_58;
  }
  v9 = (char *)this + *(int *)(*((_QWORD *)this + 2) + 12LL) + 16;
  v25 = v9;
  v22 = v9;
  RtlAcquireSRWLockExclusive(&v9[*(int *)(*(_QWORD *)v9 + 4LL)]);
  if ( *((_QWORD *)this + 6) )
    goto LABEL_15;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v12 = (CDims *)CAllocator::Allocate(0xE8u);
    v26 = v12;
    if ( v12 )
      v15 = CDims::CDims(v12, v6 == 256, v13, v14, v23);
    else
      v15 = 0;
    v16 = (CDims *)*((_QWORD *)this + 6);
    if ( v16 != v15 )
    {
      if ( v16 )
        _CObjectReleaser<CDims>::Free(v16);
      *((_QWORD *)this + 6) = v15;
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &CExcept `RTTI Type Descriptor', &v24) )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        v21 = v24;
      }
      else
      {
        v21 = v24;
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids,
          *(unsigned int *)v24);
      }
      LODWORD(v22) = *(_DWORD *)v21;
      __eh34_try_continuation(0, &CExcept `RTTI Type Descriptor', &loc_1800016F2);
      RtlReleaseSRWLockExclusive(&v25[*(int *)(*(_QWORD *)v25 + 4LL)]);
       = (unsigned int)v22;
LABEL_58:
      ;
    }
  }
LABEL_15:
  RtlReleaseSRWLockExclusive(&v9[*(int *)(*(_QWORD *)v9 + 4LL)]);
  CDims::RefreshPolicyAndStartWatchers(*((CDims **)this + 6));
  (***((void (__fastcall ****)(_QWORD, _QWORD))this + 6))(*((_QWORD *)this + 6), v6);
  v22 = 0;
  v10 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char **))a2->lpVtbl->QueryInterface)(
          a2,
          &IID_ITaskHandlerStatus,
          &v22);
  if ( v10 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v20 = 19;
  }
  else
  {
    v10 = (*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v22 + 32LL))(v22, 0);
    if ( v10 >= 0 )
    {
      if ( v22 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 16LL))(v22);
       = 0;
      goto LABEL_58;
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_43:
      CAutoResource<ITaskHandlerStatus *,_CComObjectReleaser<ITaskHandlerStatus>,0>::~CAutoResource<ITaskHandlerStatus *,_CComObjectReleaser<ITaskHandlerStatus>,0>((__int64 *)&v22);
       = (unsigned int)v10;
      goto LABEL_58;
    }
    v20 = 20;
  }
  WPP_SF_D(v19[2], v20, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids, (unsigned int)v10);
  goto LABEL_43;
}

```

## disassembly

```asm
0x180001410  push    rbx
0x180001412  push    rsi
0x180001413  push    rdi
0x180001414  push    r12
0x180001416  push    r13
0x180001418  push    r14
0x18000141a  push    r15
0x18000141c  sub     rsp, 70h
0x180001420  mov     rax, cs:__security_cookie
0x180001427  xor     rax, rsp
0x18000142a  mov     [rsp+0A8h+var_48], rax
0x18000142f  mov     r14, r8
0x180001432  mov     r12, rdx
0x180001435  mov     rsi, rcx
0x180001438  mov     [rsp+0A8h+var_70], 2
0x180001440  test    rdx, rdx
0x180001443  jz      loc_1800015CE
0x180001449  lea     r13, WPP_GLOBAL_Control
0x180001450  mov     rcx, cs:WPP_GLOBAL_Control
0x180001457  cmp     rcx, r13
0x18000145a  jz      short loc_180001466
0x18000145c  test    byte ptr [rcx+1Ch], 10h
0x180001460  jnz     loc_18000168C
0x180001466  xor     ebx, ebx
0x180001468  test    r14, r14
0x18000146b  jz      short loc_1800014A4
0x18000146d  xor     r15d, r15d
0x180001470  lea     rax, off_18000D010; "SYSTEM"
0x180001477  cmp     r15d, 5
0x18000147b  jnb     short loc_1800014A4
0x18000147d  mov     edi, r15d
0x180001480  add     rdi, rdi
0x180001483  mov     rdx, [rax+rdi*8]; String2
0x180001487  mov     rcx, r14; String1
0x18000148a  call    cs:__imp__wcsicmp
0x180001490  test    eax, eax
0x180001492  jz      short loc_180001499
0x180001494  inc     r15d
0x180001497  jmp     short loc_180001470
0x180001499  lea     rbx, off_18000D010; "SYSTEM"
0x1800014a0  mov     ebx, [rbx+rdi*8+8]
0x1800014a4  xor     ecx, ecx
0x1800014a6  cmp     ebx, 100h
0x1800014ac  setz    cl
0x1800014af  add     rcx, 0FFFFFFFF80000001h
0x1800014b6  lea     rdx, [rsp+0A8h+var_70]
0x1800014bb  call    _RetrieveLogLevel
0x1800014c0  mov     eax, [rsp+0A8h+var_70]
0x1800014c4  mov     [rsi+38h], eax
0x1800014c7  cmp     eax, 3
0x1800014ca  ja      loc_18000169D
0x1800014d0  test    ebx, ebx
0x1800014d2  jz      loc_1800015B8
0x1800014d8  mov     rax, [rsi+10h]
0x1800014dc  movsxd  rdi, dword ptr [rax+0Ch]
0x1800014e0  add     rdi, 10h
0x1800014e4  add     rdi, rsi
0x1800014e7  mov     [rsp+0A8h+var_60], rdi
0x1800014ec  mov     [rsp+0A8h+var_78], rdi
0x1800014f1  mov     rax, [rdi]
0x1800014f4  movsxd  rcx, dword ptr [rax+4]
0x1800014f8  add     rcx, rdi
0x1800014fb  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001501  nop
0x180001502  cmp     qword ptr [rsi+30h], 0
0x180001507  jz      loc_1800015D5
0x18000150d  mov     rax, [rdi]
0x180001510  movsxd  rcx, dword ptr [rax+4]
0x180001514  add     rcx, rdi
0x180001517  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000151d  mov     rcx, [rsi+30h]; this
0x180001521  call    ?RefreshPolicyAndStartWatchers@CDims@@QEAAXXZ; CDims::RefreshPolicyAndStartWatchers(void)
0x180001526  mov     rcx, [rsi+30h]
0x18000152a  mov     rax, [rcx]
0x18000152d  mov     edx, ebx
0x18000152f  mov     rax, [rax]
0x180001532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001537  mov     [rsp+0A8h+var_78], 0
0x180001540  mov     rax, [r12]
0x180001544  lea     r8, [rsp+0A8h+var_78]
0x180001549  lea     rdx, IID_ITaskHandlerStatus
0x180001550  mov     rcx, r12
0x180001553  mov     rax, [rax]
0x180001556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000155b  mov     ebx, eax
0x18000155d  test    eax, eax
0x18000155f  js      loc_180001710
0x180001565  mov     rcx, [rsp+0A8h+var_78]
0x18000156a  mov     rax, [rcx]
0x18000156d  xor     edx, edx
0x18000156f  mov     rax, [rax+20h]
0x180001573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001578  mov     ebx, eax
0x18000157a  test    eax, eax
0x18000157c  js      loc_180001753
0x180001582  mov     rcx, [rsp+0A8h+var_78]
0x180001587  test    rcx, rcx
0x18000158a  jz      short loc_180001599
0x18000158c  mov     rax, [rcx]
0x18000158f  mov     rax, [rax+10h]
0x180001593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001598  nop
0x180001599  xor     eax, eax
0x18000159b  mov     rcx, [rsp+0A8h+var_48]
0x1800015a0  xor     rcx, rsp; StackCookie
0x1800015a3  call    __security_check_cookie
0x1800015a8  add     rsp, 70h
0x1800015ac  pop     r15
0x1800015ae  pop     r14
0x1800015b0  pop     r13
0x1800015b2  pop     r12
0x1800015b4  pop     rdi
0x1800015b5  pop     rsi
0x1800015b6  pop     rbx
0x1800015b7  retn
0x1800015b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800015bf  cmp     rcx, r13
0x1800015c2  jnz     loc_1800016B3
0x1800015c8  cmp     dword ptr [rsi+38h], 2
0x1800015cc  ja      short loc_180001625
0x1800015ce  mov     eax, 80070057h
0x1800015d3  jmp     short loc_18000159B
0x1800015d5  mov     ecx, 0E8h; uBytes
0x1800015da  call    ?Allocate@CAllocator@@SAPEAX_K@Z; CAllocator::Allocate(unsigned __int64)
0x1800015df  mov     [rsp+0A8h+var_58], rax
0x1800015e4  test    rax, rax
0x1800015e7  jnz     short loc_180001607
0x1800015e9  xor     r14d, r14d
0x1800015ec  mov     rcx, [rsi+30h]; hMem
0x1800015f0  cmp     rcx, r14
0x1800015f3  jz      short loc_180001602
0x1800015f5  test    rcx, rcx
0x1800015f8  jnz     loc_1800016E8
0x1800015fe  mov     [rsi+30h], r14
0x180001602  jmp     loc_18000150D
0x180001607  cmp     ebx, 100h
0x18000160d  setz    dl; bool
0x180001610  mov     ecx, [rsp+0A8h+var_70]
0x180001614  mov     [rsp+0A8h+var_88], ecx; unsigned int
0x180001618  mov     rcx, rax; this
0x18000161b  call    ??0CDims@@QEAA@_NKKK@Z; CDims::CDims(bool,ulong,ulong,ulong)
0x180001620  mov     r14, rax
0x180001623  jmp     short loc_1800015EC
0x180001625  test    r14, r14
0x180001628  jz      loc_1800016D7
0x18000162e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001635  nop     word ptr [rax+rax+00000000h]
0x180001640  lea     rax, [rax+1]
0x180001644  cmp     word ptr [r14+rax*2], 0
0x18000164a  jnz     short loc_180001640
0x18000164c  lea     eax, ds:2[rax*2]
0x180001653  mov     [rsp+0A8h+var_58], r14
0x180001658  mov     [rsp+0A8h+var_50], eax
0x18000165c  mov     [rsp+0A8h+var_4C], 0
0x180001664  lea     r8, [rsp+0A8h+var_58]
0x180001669  mov     edx, 1
0x18000166e  lea     rcx, DM_LOG_WARNING_BADPARAM
0x180001675  call    _LogReport
0x18000167a  xor     ecx, ecx; hMem
0x18000167c  call    cs:__imp_LocalFree
0x180001682  mov     eax, 80070057h
0x180001687  jmp     loc_18000159B
0x18000168c  mov     r9, r14
0x18000168f  mov     rcx, [rcx+10h]
0x180001693  call    WPP_SF_S
0x180001698  jmp     loc_180001466
0x18000169d  xor     r8d, r8d
0x1800016a0  xor     edx, edx
0x1800016a2  lea     rcx, DM_LOG_INFO_STARTED
0x1800016a9  call    _LogReport
0x1800016ae  jmp     loc_1800014D0
0x1800016b3  test    byte ptr [rcx+1Ch], 2
0x1800016b7  jz      loc_1800015C8
0x1800016bd  mov     edx, 11h
0x1800016c2  lea     r8, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids
0x1800016c9  mov     rcx, [rcx+10h]
0x1800016cd  call    WPP_SF_
0x1800016d2  jmp     loc_1800015C8
0x1800016d7  mov     eax, 0Eh
0x1800016dc  lea     r14, aNull_0; "<NULL>"
0x1800016e3  jmp     loc_180001653
0x1800016e8  call    ?Free@?$_CObjectReleaser@VCDims@@@@SAXPEAVCDims@@@Z; _CObjectReleaser<CDims>::Free(CDims *)
0x1800016ed  jmp     loc_1800015FE
0x1800016f2  mov     rdx, [rsp+0A8h+var_60]
0x1800016f7  mov     rax, [rdx]
0x1800016fa  movsxd  rcx, dword ptr [rax+4]
0x1800016fe  add     rcx, rdx
0x180001701  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001707  mov     eax, dword ptr [rsp+0A8h+var_78]
0x18000170b  jmp     loc_18000159B
0x180001710  mov     rcx, cs:WPP_GLOBAL_Control
0x180001717  cmp     rcx, r13
0x18000171a  jz      short loc_180001742
0x18000171c  test    byte ptr [rcx+1Ch], 2
0x180001720  jz      short loc_180001742
0x180001722  mov     edx, 13h
0x180001727  jmp     short loc_18000172E
0x180001729  mov     edx, 14h
0x18000172e  mov     r9d, ebx
0x180001731  lea     r8, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids
0x180001738  mov     rcx, [rcx+10h]
0x18000173c  call    WPP_SF_D
0x180001741  nop
0x180001742  lea     rcx, [rsp+0A8h+var_78]
0x180001747  call    ??1?$CAutoResource@PEAUITaskHandlerStatus@@U?$_CComObjectReleaser@UITaskHandlerStatus@@@@$0A@@@QEAA@XZ; CAutoResource<ITaskHandlerStatus *,_CComObjectReleaser<ITaskHandlerStatus>,0>::~CAutoResource<ITaskHandlerStatus *,_CComObjectReleaser<ITaskHandlerStatus>,0>(void)
0x18000174c  mov     eax, ebx
0x18000174e  jmp     loc_18000159B
0x180001753  mov     rcx, cs:WPP_GLOBAL_Control
0x18000175a  cmp     rcx, r13
0x18000175d  jz      short loc_180001742
0x18000175f  test    byte ptr [rcx+1Ch], 2
0x180001763  jz      short loc_180001742
0x180001765  jmp     short loc_180001729
```
