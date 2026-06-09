# CFLACSource::Start(IMFPresentationDescriptor *,_GUID const *,tagPROPVARIANT const *)

- ea: `0x180026fc0`
- end: `0x18002723d`
- name: `?Start@CFLACSource@@UEAAJPEAUIMFPresentationDescriptor@@PEBU_GUID@@PEBUtagPROPVARIANT@@@Z`
- size: `637`
- prototype: `int(CFLACSource *__hidden this, struct IMFPresentationDescriptor *, const struct _GUID *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18001e834`
- `0x180020398`
- `0x180020484`
- `0x180022648`
- `0x180023f30`
- `0x180026230`
- `0x1800266ac`
- `0x180026fc0`
- `0x1800273e8`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002720f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002720f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027056`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027056`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180027196`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180027196`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFLACSource::Start(
        CFLACSource *this,
        struct IMFPresentationDescriptor *a2,
        const struct _GUID *a3,
        const struct tagPROPVARIANT *a4)
{
  int v7; // r15d
  CFLACSource *v8; // rbx
  __int64 v9; // rax
  struct _RTL_CRITICAL_SECTION *v11; // r13
  __int64 QuadPart; // rsi
  int v13; // ecx
  __int64 v14; // rdx
  __int64 v15; // rax
  struct CSourceOp *v16; // rdi
  int v17; // ecx
  __int64 v18; // rdx
  HRESULT IsInitialized; // [rsp+90h] [rbp+40h]
  struct CSourceOp *v20; // [rsp+A8h] [rbp+58h] BYREF

  v7 = 0;
  v8 = (CFLACSource *)((char *)this - 80);
  v20 = 0;
  if ( a4 && a2 )
  {
    if ( a3 )
    {
      v9 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_NULL.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
        v9 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_NULL.Data4;
      if ( v9 )
        return MF::OriginateError((MF *)0xC00D36C5LL, (int)a2);
    }
    if ( a4->vt != 20 && a4->vt )
      return MF::OriginateError((MF *)0xC00D36C5LL, (int)a2);
    v11 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    QuadPart = a4->hVal.QuadPart;
    if ( a4->vt == 20 )
    {
      LOBYTE(v7) = *((_DWORD *)this + 36) != 2;
    }
    else if ( !a4->vt )
    {
      if ( *((_DWORD *)this + 36) == 2 )
      {
        QuadPart = 0;
        goto LABEL_15;
      }
      QuadPart = *((_QWORD *)this + 34);
    }
    if ( *((_DWORD *)this + 36) == 5 )
    {
      IsInitialized = -1072873851;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 40;
        goto LABEL_22;
      }
      goto LABEL_43;
    }
LABEL_15:
    IsInitialized = CFLACSource::IsInitialized(v8);
    if ( IsInitialized < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 41;
LABEL_22:
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, v8, v13);
      }
LABEL_43:
      LeaveCriticalSection(v11);
      return (unsigned int)IsInitialized;
    }
    IsInitialized = CFLACSource::ValidatePresentationDescriptor(v8, a2);
    if ( IsInitialized < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_43;
      v14 = 42;
      goto LABEL_22;
    }
    IsInitialized = CFLACSource::SeekStream(v8, QuadPart);
    if ( IsInitialized < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_43;
      v14 = 43;
      goto LABEL_22;
    }
    v15 = *((_QWORD *)v8 + 22);
    if ( v15 )
      *(_DWORD *)(v15 + 56) = 0;
    IsInitialized = CSourceOp::CreateStartOp(a2, &v20);
    v16 = v20;
    if ( IsInitialized >= 0 )
    {
      *((_DWORD *)v20 + 10) = v7;
      IsInitialized = PropVariantCopy((PROPVARIANT *)((char *)v16 + 16), a4);
      if ( IsInitialized >= 0 )
      {
        IsInitialized = OpQueue<CSourceOp>::QueueOperation(v8, v16);
        if ( IsInitialized >= 0 || !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_41;
        v18 = 46;
      }
      else
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_41;
        v18 = 45;
      }
    }
    else
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_41;
      v18 = 44;
    }
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, v8, v17);
LABEL_41:
    if ( v16 )
      (*(void (__fastcall **)(struct CSourceOp *))(*(_QWORD *)v16 + 16LL))(v16);
    goto LABEL_43;
  }
  return MF::OriginateError((MF *)0x80070057LL, (int)a2);
}

```

## disassembly

```asm
0x180026fc0  mov     [rsp-38h+arg_8], rbx
0x180026fc5  push    rbp
0x180026fc6  push    rsi
0x180026fc7  push    rdi
0x180026fc8  push    r12
0x180026fca  push    r13
0x180026fcc  push    r14
0x180026fce  push    r15
0x180026fd0  mov     rbp, rsp
0x180026fd3  sub     rsp, 50h
0x180026fd7  mov     r14, r9
0x180026fda  mov     r12, rdx
0x180026fdd  mov     rdi, rcx
0x180026fe0  xor     r15d, r15d
0x180026fe3  mov     [rbp+arg_0], r15d
0x180026fe7  lea     rbx, [rcx-50h]
0x180026feb  mov     [rbp+var_18], rbx
0x180026fef  lea     rax, [rbp+arg_0]
0x180026ff3  mov     [rbp+var_10], rax
0x180026ff7  mov     [rbp+arg_18], r15
0x180026ffb  test    r9, r9
0x180026ffe  jz      loc_18002721A
0x180027004  test    rdx, rdx
0x180027007  jz      loc_18002721A
0x18002700d  test    r8, r8
0x180027010  jz      short loc_18002703E
0x180027012  mov     rax, [r8]
0x180027015  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18002701c  jnz     short loc_180027029
0x18002701e  mov     rax, [r8+8]
0x180027022  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180027029  test    rax, rax
0x18002702c  jz      short loc_18002703E
0x18002702e  mov     ecx, 0C00D36C5h; this
0x180027033  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x180027038  nop
0x180027039  jmp     loc_180027225
0x18002703e  cmp     word ptr [r9], 14h
0x180027043  jz      short loc_18002704B
0x180027045  cmp     [r9], r15w
0x180027049  jnz     short loc_18002702E
0x18002704b  lea     r13, [rcx+68h]
0x18002704f  mov     [rbp+var_20], r13
0x180027053  mov     rcx, r13; lpCriticalSection
0x180027056  call    cs:__imp_EnterCriticalSection
0x18002705c  nop
0x18002705d  mov     rsi, [r14+8]
0x180027061  cmp     word ptr [r14], 14h
0x180027066  jnz     short loc_180027078
0x180027068  cmp     dword ptr [rdi+90h], 2
0x18002706f  setnz   r15b
0x180027073  xor     r8d, r8d
0x180027076  jmp     short loc_1800270BD
0x180027078  xor     r8d, r8d
0x18002707b  cmp     [r14], r8w
0x18002707f  jnz     short loc_1800270BD
0x180027081  cmp     dword ptr [rdi+90h], 2
0x180027088  jnz     short loc_1800270B6
0x18002708a  mov     esi, r8d
0x18002708d  mov     [rbp+arg_0], r8d
0x180027091  mov     rcx, rbx; this
0x180027094  call    ?IsInitialized@CFLACSource@@AEBAJXZ; CFLACSource::IsInitialized(void)
0x180027099  mov     ecx, eax
0x18002709b  mov     [rbp+arg_0], eax
0x18002709e  test    eax, eax
0x1800270a0  jns     short loc_180027103
0x1800270a2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800270a7  cmp     al, 1
0x1800270a9  jb      loc_180027209
0x1800270af  mov     edx, 29h ; ')'
0x1800270b4  jmp     short loc_1800270E0
0x1800270b6  mov     rsi, [rdi+110h]
0x1800270bd  cmp     dword ptr [rdi+90h], 5
0x1800270c4  jnz     short loc_18002708D
0x1800270c6  mov     ecx, 0C00D3E85h
0x1800270cb  mov     [rbp+arg_0], ecx
0x1800270ce  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800270d3  cmp     al, 1
0x1800270d5  jb      loc_180027209
0x1800270db  mov     edx, 28h ; '('
0x1800270e0  mov     [rsp+50h+var_30], ecx
0x1800270e4  mov     r9, rbx
0x1800270e7  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x1800270ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800270f5  mov     rcx, [rcx+10h]
0x1800270f9  call    WPP_SF_qd
0x1800270fe  jmp     loc_180027209
0x180027103  mov     rdx, r12; struct IMFPresentationDescriptor *
0x180027106  mov     rcx, rbx; this
0x180027109  call    ?ValidatePresentationDescriptor@CFLACSource@@AEAAJPEAUIMFPresentationDescriptor@@@Z; CFLACSource::ValidatePresentationDescriptor(IMFPresentationDescriptor *)
0x18002710e  mov     ecx, eax
0x180027110  mov     [rbp+arg_0], eax
0x180027113  test    eax, eax
0x180027115  jns     short loc_18002712B
0x180027117  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002711c  cmp     al, 1
0x18002711e  jb      loc_180027209
0x180027124  mov     edx, 2Ah ; '*'
0x180027129  jmp     short loc_1800270E0
0x18002712b  mov     rdx, rsi; __int64
0x18002712e  mov     rcx, rbx; this
0x180027131  call    ?SeekStream@CFLACSource@@AEAAJ_J@Z; CFLACSource::SeekStream(__int64)
0x180027136  mov     ecx, eax
0x180027138  mov     [rbp+arg_0], eax
0x18002713b  xor     esi, esi
0x18002713d  test    eax, eax
0x18002713f  jns     short loc_180027153
0x180027141  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180027146  cmp     al, 1
0x180027148  jb      loc_180027209
0x18002714e  lea     edx, [rsi+2Bh]
0x180027151  jmp     short loc_1800270E0
0x180027153  mov     rax, [rbx+0B0h]
0x18002715a  test    rax, rax
0x18002715d  jz      short loc_180027162
0x18002715f  mov     [rax+38h], esi
0x180027162  lea     rdx, [rbp+arg_18]; struct CSourceOp **
0x180027166  mov     rcx, r12; struct IMFPresentationDescriptor *
0x180027169  call    ?CreateStartOp@CSourceOp@@SAJPEAUIMFPresentationDescriptor@@PEAPEAV1@@Z; CSourceOp::CreateStartOp(IMFPresentationDescriptor *,CSourceOp * *)
0x18002716e  mov     ecx, eax
0x180027170  mov     [rbp+arg_0], eax
0x180027173  mov     rdi, [rbp+arg_18]
0x180027177  test    eax, eax
0x180027179  jns     short loc_18002718B
0x18002717b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180027180  cmp     al, 1
0x180027182  jb      short loc_1800271F5
0x180027184  mov     edx, 2Ch ; ','
0x180027189  jmp     short loc_1800271D7
0x18002718b  mov     [rdi+28h], r15d
0x18002718f  lea     rcx, [rdi+10h]; pvarDest
0x180027193  mov     rdx, r14; pvarSrc
0x180027196  call    cs:__imp_PropVariantCopy
0x18002719c  mov     ecx, eax
0x18002719e  mov     [rbp+arg_0], eax
0x1800271a1  test    eax, eax
0x1800271a3  jns     short loc_1800271B5
0x1800271a5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800271aa  cmp     al, 1
0x1800271ac  jb      short loc_1800271F5
0x1800271ae  mov     edx, 2Dh ; '-'
0x1800271b3  jmp     short loc_1800271D7
0x1800271b5  mov     rdx, rdi
0x1800271b8  mov     rcx, rbx
0x1800271bb  call    ?QueueOperation@?$OpQueue@VCSourceOp@@@@QEAAJPEAVCSourceOp@@@Z; OpQueue<CSourceOp>::QueueOperation(CSourceOp *)
0x1800271c0  mov     ecx, eax
0x1800271c2  mov     [rbp+arg_0], eax
0x1800271c5  test    eax, eax
0x1800271c7  jns     short loc_1800271F5
0x1800271c9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800271ce  cmp     al, 1
0x1800271d0  jb      short loc_1800271F5
0x1800271d2  mov     edx, 2Eh ; '.'
0x1800271d7  mov     [rsp+50h+var_30], ecx
0x1800271db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271e2  mov     r9, rbx
0x1800271e5  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x1800271ec  mov     rcx, [rcx+10h]
0x1800271f0  call    WPP_SF_qd
0x1800271f5  test    rdi, rdi
0x1800271f8  jz      short loc_180027209
0x1800271fa  mov     rax, [rdi]
0x1800271fd  mov     rcx, rdi
0x180027200  mov     rax, [rax+10h]
0x180027204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027209  mov     ebx, [rbp+arg_0]
0x18002720c  mov     rcx, r13; lpCriticalSection
0x18002720f  call    cs:__imp_LeaveCriticalSection
0x180027215  nop
0x180027216  mov     eax, ebx
0x180027218  jmp     short loc_180027225
0x18002721a  mov     ecx, 80070057h; this
0x18002721f  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x180027224  nop
0x180027225  mov     rbx, [rsp+50h+arg_8]
0x18002722d  add     rsp, 50h
0x180027231  pop     r15
0x180027233  pop     r14
0x180027235  pop     r13
0x180027237  pop     r12
0x180027239  pop     rdi
0x18002723a  pop     rsi
0x18002723b  pop     rbp
0x18002723c  retn
```
