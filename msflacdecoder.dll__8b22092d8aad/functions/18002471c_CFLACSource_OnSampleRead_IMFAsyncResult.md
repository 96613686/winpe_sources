# CFLACSource::OnSampleRead(IMFAsyncResult *)

- ea: `0x18002471c`
- end: `0x180024a01`
- name: `?OnSampleRead@CFLACSource@@QEAAJPEAUIMFAsyncResult@@@Z`
- size: `741`
- prototype: `__int64 __fastcall(CFLACSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180023f10`

## callees

- `0x180020398`
- `0x180020484`
- `0x1800230b8`
- `0x1800234fc`
- `0x180023d6c`
- `0x18002471c`
- `0x180024c60`
- `0x18002513c`
- `0x180027338`
- `0x180027bf0`
- `0x180027da0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002488b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002488b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800249eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800249eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024761`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024761`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFLACSource::OnSampleRead(CFLACSource *this, struct IMFAsyncResult *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  int v5; // ecx
  __int64 v6; // rdx
  HANDLE EventW; // rax
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int inited; // [rsp+70h] [rbp+20h]
  unsigned int v13; // [rsp+80h] [rbp+30h] BYREF
  _DWORD *v14; // [rsp+88h] [rbp+38h] BYREF

  v13 = 0;
  v14 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 184);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  if ( *((_DWORD *)this + 56) == 5 )
  {
    inited = -1072873851;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_36;
    v6 = 122;
    goto LABEL_4;
  }
  ((void (__fastcall *)(struct IMFAsyncResult *, _DWORD **))a2->lpVtbl->GetState)(a2, &v14);
  inited = (*(__int64 (__fastcall **)(_QWORD, struct IMFAsyncResult *, unsigned int *))(**((_QWORD **)this + 39) + 88LL))(
             *((_QWORD *)this + 39),
             a2,
             &v13);
  if ( inited < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_36;
    v6 = 123;
    goto LABEL_4;
  }
  if ( v14 && v14[6] != *((_DWORD *)this + 70) )
  {
LABEL_36:
    if ( inited >= 0 )
      goto LABEL_38;
    goto LABEL_37;
  }
  if ( !v13 )
  {
    if ( (*((_BYTE *)this + 390) & 1) != 0 )
    {
      inited = CFLACSource::EndOfStream(this);
      goto LABEL_36;
    }
    inited = -1072875836;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v6 = 124;
LABEL_4:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, this, v5);
      goto LABEL_36;
    }
    goto LABEL_37;
  }
  CBuffReader::MoveEnd((CFLACSource *)((char *)this + 328), v13);
  if ( (*((_BYTE *)this + 390) & 1) != 0 )
  {
    inited = CFLACSource::ParseSampleData(this);
    if ( inited < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_36;
      v6 = 129;
      goto LABEL_4;
    }
    goto LABEL_34;
  }
  if ( *((_QWORD *)this + 50) || (EventW = CreateEventW(0, 1, 0, 0), (*((_QWORD *)this + 50) = EventW) != 0) )
  {
    v8 = CFLACSource::ParseStreamMetadata(this);
    inited = v8;
    if ( v8 == -1072863856 )
    {
      inited = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD, char *, _QWORD))(**((_QWORD **)this + 39)
                                                                                           + 80LL))(
                 *((_QWORD *)this + 39),
                 *((_QWORD *)this + 41)
               + *((unsigned int *)this + 86)
               + (unsigned __int64)(unsigned int)(*((_DWORD *)this + 87) - *((_DWORD *)this + 86)),
                 *((unsigned int *)this + 72),
                 (char *)this + 152,
                 *((_QWORD *)this + 33));
      if ( inited < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_36;
        v6 = 126;
        goto LABEL_4;
      }
      goto LABEL_34;
    }
    if ( v8 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          127,
          &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids,
          this,
          inited);
      goto LABEL_36;
    }
    inited = CFLACSource::InitStream(this);
    if ( inited < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_36;
      v6 = 128;
      goto LABEL_4;
    }
LABEL_34:
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
      WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 27), v9, v10, *((_QWORD *)this + 44));
    goto LABEL_36;
  }
  inited = -2147024882;
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v6 = 125;
    goto LABEL_4;
  }
LABEL_37:
  CFLACSource::StreamingError(this, inited);
LABEL_38:
  if ( v14 )
  {
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  LeaveCriticalSection(v4);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18002471c  mov     [rsp-18h+arg_8], rbx
0x180024721  push    rbp
0x180024722  push    rsi
0x180024723  push    rdi
0x180024724  mov     rbp, rsp
0x180024727  sub     rsp, 50h
0x18002472b  mov     rsi, rdx
0x18002472e  mov     rbx, rcx
0x180024731  mov     [rbp+arg_0], 0
0x180024738  mov     [rbp+var_18], rcx
0x18002473c  lea     rax, [rbp+arg_0]
0x180024740  mov     [rbp+var_10], rax
0x180024744  mov     [rbp+arg_10], 0
0x18002474b  mov     [rbp+arg_18], 0
0x180024753  lea     rdi, [rcx+0B8h]
0x18002475a  mov     [rbp+var_20], rdi
0x18002475e  mov     rcx, rdi; lpCriticalSection
0x180024761  call    cs:__imp_EnterCriticalSection
0x180024767  nop
0x180024768  cmp     dword ptr [rbx+0E0h], 5
0x18002476f  jnz     short loc_1800247AE
0x180024771  mov     ecx, 0C00D3E85h
0x180024776  mov     [rbp+arg_0], ecx
0x180024779  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002477e  cmp     al, 1
0x180024780  jb      loc_1800249B7
0x180024786  mov     edx, 7Ah ; 'z'
0x18002478b  mov     dword ptr [rsp+50h+var_30], ecx
0x18002478f  mov     r9, rbx
0x180024792  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x180024799  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247a0  mov     rcx, [rcx+10h]
0x1800247a4  call    WPP_SF_qd
0x1800247a9  jmp     loc_1800249B7
0x1800247ae  mov     [rbp+arg_0], 0
0x1800247b5  mov     rax, [rsi]
0x1800247b8  lea     rdx, [rbp+arg_18]
0x1800247bc  mov     rcx, rsi
0x1800247bf  mov     rax, [rax+18h]
0x1800247c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247c8  mov     rcx, [rbx+138h]
0x1800247cf  mov     rax, [rcx]
0x1800247d2  lea     r8, [rbp+arg_10]
0x1800247d6  mov     rdx, rsi
0x1800247d9  mov     rax, [rax+58h]
0x1800247dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247e2  mov     ecx, eax
0x1800247e4  mov     [rbp+arg_0], eax
0x1800247e7  test    eax, eax
0x1800247e9  jns     short loc_1800247FF
0x1800247eb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800247f0  cmp     al, 1
0x1800247f2  jb      loc_1800249B7
0x1800247f8  mov     edx, 7Bh ; '{'
0x1800247fd  jmp     short loc_18002478B
0x1800247ff  mov     rcx, [rbp+arg_18]
0x180024803  test    rcx, rcx
0x180024806  jz      short loc_180024817
0x180024808  mov     eax, [rbx+118h]
0x18002480e  cmp     [rcx+18h], eax
0x180024811  jnz     loc_1800249B7
0x180024817  mov     edx, [rbp+arg_10]; unsigned int
0x18002481a  test    edx, edx
0x18002481c  jnz     short loc_180024856
0x18002481e  test    byte ptr [rbx+186h], 1
0x180024825  jnz     short loc_180024846
0x180024827  mov     ecx, 0C00D36C4h
0x18002482c  mov     [rbp+arg_0], ecx
0x18002482f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024834  cmp     al, 1
0x180024836  jb      loc_1800249BD
0x18002483c  mov     edx, 7Ch ; '|'
0x180024841  jmp     loc_18002478B
0x180024846  mov     rcx, rbx; this
0x180024849  call    ?EndOfStream@CFLACSource@@AEAAJXZ; CFLACSource::EndOfStream(void)
0x18002484e  mov     [rbp+arg_0], eax
0x180024851  jmp     loc_1800249B7
0x180024856  lea     rsi, [rbx+148h]
0x18002485d  mov     rcx, rsi; this
0x180024860  call    ?MoveEnd@CBuffReader@@QEAAJK@Z; CBuffReader::MoveEnd(ulong)
0x180024865  mov     [rbp+arg_0], eax
0x180024868  test    byte ptr [rbx+186h], 1
0x18002486f  jnz     loc_180024970
0x180024875  cmp     qword ptr [rbx+190h], 0
0x18002487d  jnz     short loc_1800248BC
0x18002487f  xor     r9d, r9d; lpName
0x180024882  xor     r8d, r8d; bInitialState
0x180024885  lea     edx, [r9+1]; bManualReset
0x180024889  xor     ecx, ecx; lpEventAttributes
0x18002488b  call    cs:__imp_CreateEventW
0x180024891  mov     [rbx+190h], rax
0x180024898  test    rax, rax
0x18002489b  jnz     short loc_1800248BC
0x18002489d  mov     ecx, 8007000Eh
0x1800248a2  mov     [rbp+arg_0], ecx
0x1800248a5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800248aa  cmp     al, 1
0x1800248ac  jb      loc_1800249BD
0x1800248b2  mov     edx, 7Dh ; '}'
0x1800248b7  jmp     loc_18002478B
0x1800248bc  mov     rcx, rbx; this
0x1800248bf  call    ?ParseStreamMetadata@CFLACSource@@AEAAJXZ; CFLACSource::ParseStreamMetadata(void)
0x1800248c4  mov     [rbp+arg_0], eax
0x1800248c7  cmp     eax, 0C00D6590h
0x1800248cc  jnz     short loc_18002492E
0x1800248ce  mov     rcx, [rbx+138h]
0x1800248d5  mov     r8d, [rsi+10h]
0x1800248d9  mov     r10, [rcx]
0x1800248dc  lea     r9, [rbx+98h]
0x1800248e3  mov     edx, [rbx+15Ch]
0x1800248e9  sub     edx, r8d
0x1800248ec  add     rdx, r8
0x1800248ef  add     rdx, [rsi]
0x1800248f2  mov     r8, [rbx+108h]
0x1800248f9  mov     [rsp+50h+var_30], r8
0x1800248fe  mov     r8d, [rbx+120h]
0x180024905  mov     rax, [r10+50h]
0x180024909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002490e  mov     ecx, eax
0x180024910  mov     [rbp+arg_0], eax
0x180024913  test    eax, eax
0x180024915  jns     short loc_180024994
0x180024917  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002491c  cmp     al, 1
0x18002491e  jb      loc_1800249B7
0x180024924  mov     edx, 7Eh ; '~'
0x180024929  jmp     loc_18002478B
0x18002492e  test    eax, eax
0x180024930  jns     short loc_18002494C
0x180024932  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024937  cmp     al, 1
0x180024939  jb      short loc_1800249B7
0x18002493b  mov     edx, 7Fh
0x180024940  mov     eax, [rbp+arg_0]
0x180024943  mov     dword ptr [rsp+50h+var_30], eax
0x180024947  jmp     loc_18002478F
0x18002494c  mov     rcx, rbx; this
0x18002494f  call    ?InitStream@CFLACSource@@AEAAJXZ; CFLACSource::InitStream(void)
0x180024954  mov     ecx, eax
0x180024956  mov     [rbp+arg_0], eax
0x180024959  test    eax, eax
0x18002495b  jns     short loc_180024994
0x18002495d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024962  cmp     al, 1
0x180024964  jb      short loc_1800249B7
0x180024966  mov     edx, 80h
0x18002496b  jmp     loc_18002478B
0x180024970  mov     rcx, rbx; this
0x180024973  call    ?ParseSampleData@CFLACSource@@AEAAJXZ; CFLACSource::ParseSampleData(void)
0x180024978  mov     ecx, eax
0x18002497a  mov     [rbp+arg_0], eax
0x18002497d  test    eax, eax
0x18002497f  jns     short loc_180024994
0x180024981  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024986  cmp     al, 1
0x180024988  jb      short loc_1800249B7
0x18002498a  mov     edx, 81h
0x18002498f  jmp     loc_18002478B
0x180024994  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180024999  cmp     al, 8
0x18002499b  jb      short loc_1800249B7
0x18002499d  mov     r9, [rbx+160h]
0x1800249a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249ab  mov     rcx, [rcx+0D8h]
0x1800249b2  call    WPP_SF_i
0x1800249b7  cmp     [rbp+arg_0], 0
0x1800249bb  jge     short loc_1800249C8
0x1800249bd  mov     edx, [rbp+arg_0]; int
0x1800249c0  mov     rcx, rbx; this
0x1800249c3  call    ?StreamingError@CFLACSource@@AEAAXJ@Z; CFLACSource::StreamingError(long)
0x1800249c8  mov     rcx, [rbp+arg_18]
0x1800249cc  test    rcx, rcx
0x1800249cf  jz      short loc_1800249E5
0x1800249d1  mov     rax, [rcx]
0x1800249d4  mov     rax, [rax+10h]
0x1800249d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249dd  mov     [rbp+arg_18], 0
0x1800249e5  mov     ebx, [rbp+arg_0]
0x1800249e8  mov     rcx, rdi; lpCriticalSection
0x1800249eb  call    cs:__imp_LeaveCriticalSection
0x1800249f1  nop
0x1800249f2  mov     eax, ebx
0x1800249f4  mov     rbx, [rsp+50h+arg_8]
0x1800249f9  add     rsp, 50h
0x1800249fd  pop     rdi
0x1800249fe  pop     rsi
0x1800249ff  pop     rbp
0x180024a00  retn
```
