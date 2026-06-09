# DwmpCreateSharedThumbnailVisual

- ea: `0x180001690`
- end: `0x18000199d`
- name: `DwmpCreateSharedThumbnailVisual`
- size: `781`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001684`
- `0x180001690`
- `0x18000352c`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000183a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000183a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800018d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800018d7`
- `win32u!NtDCompositionRegisterThumbnailVisual` at `0x18000188e`
- `win32u!NtDCompositionRegisterThumbnailVisual` at `0x18000188e`
- `USER32!GetWindowLongPtrW` at `0x180001945`
- `USER32!GetWindowLongPtrW` at `0x180001945`
- `USER32!IsTopLevelWindow` at `0x18000171d`
- `USER32!IsTopLevelWindow` at `0x180001734`
- `USER32!IsTopLevelWindow` at `0x18000171d`
- `USER32!IsTopLevelWindow` at `0x180001734`

## pseudocode

```c
__int64 __fastcall DwmpCreateSharedThumbnailVisual(
        HWND a1,
        HWND a2,
        int a3,
        unsigned int *a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7)
{
  int v11; // r9d
  unsigned int v12; // ebx
  signed int v13; // ecx
  __int64 v14; // rax
  __int64 (__fastcall **v15)(__int64, GUID *, __int64); // rdx
  __int64 v16; // r9
  int v17; // eax
  unsigned __int32 v18; // r15d
  unsigned int v19; // esi
  int v20; // eax
  __int64 v21; // rax
  unsigned int v23; // [rsp+20h] [rbp-58h]
  void *v24; // [rsp+28h] [rbp-50h]
  __int64 v25; // [rsp+50h] [rbp-28h] BYREF
  __int64 v26; // [rsp+58h] [rbp-20h] BYREF
  HANDLE hObject[3]; // [rsp+60h] [rbp-18h] BYREF

  v26 = 0;
  v25 = 0;
  hObject[0] = 0;
  if ( (a3 & 4) != 0 || (a3 & 8) != 0 || !(unsigned int)((__int64 (*)(void))IsTopLevelWindow)() )
    goto LABEL_2;
  if ( (a3 & 1) == 0 )
  {
    if ( (unsigned int)IsTopLevelWindow(a2) || (GetWindowLongPtrW(a2, -20) & 0x80000) != 0 )
      goto LABEL_11;
LABEL_2:
    v23 = 181;
LABEL_3:
    v11 = -2147024809;
    v12 = -2147024809;
LABEL_4:
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019230, 2u, v11, v23, v24);
    goto LABEL_5;
  }
  if ( a2 )
    goto LABEL_2;
LABEL_11:
  if ( a1 == a2 || (*a4 & 2) != 0 && ((int)a4[7] < (int)a4[5] || (int)a4[8] < (int)a4[6]) )
    goto LABEL_2;
  if ( (*a4 & 9) != 9 )
    goto LABEL_2;
  if ( !*(unsigned int *)((char *)a4 + 37) )
    goto LABEL_2;
  v13 = a4[1];
  if ( (int)a4[3] < v13 || (int)a4[4] < (int)a4[2] || v13 || a4[2] )
    goto LABEL_2;
  *a6 = 0;
  v14 = IID_PPV_ARGS_Helper<Windows::UI::Composition::Internal::ICompositorInternal>(&v26, *a5);
  v17 = (*v15)(v16, &GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0, v14);
  v12 = v17;
  if ( v17 < 0 )
  {
    v23 = 191;
    goto LABEL_34;
  }
  if ( !v26 )
  {
    v23 = 194;
    goto LABEL_3;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v26 + 216LL))(
          v26,
          &GUID_e8de1639_4331_4b26_bc5f_6a321d347a85,
          &v25);
  v12 = v17;
  if ( v17 < 0 )
  {
    v23 = 200;
    goto LABEL_34;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, __int64, HANDLE *))(*(_QWORD *)v26 + 224LL))(v26, v25, hObject);
  v12 = v17;
  if ( v17 < 0 )
  {
    v23 = 203;
LABEL_34:
    v11 = v17;
    goto LABEL_4;
  }
  v18 = _InterlockedIncrement(&dword_18001F990);
  hObject[1] = (HANDLE)__PAIR64__(GetCurrentProcessId(), v18);
  v19 = a3 | 4;
  if ( (*(_BYTE *)a4 & 0x10) != 0 && *(unsigned int *)((char *)a4 + 41) )
    v19 |= 8u;
  v20 = NtDCompositionRegisterThumbnailVisual(a1, a2, v19, *a4, a4 + 1);
  if ( v20 >= 0 )
  {
    v21 = v25;
    v25 = 0;
    *a6 = v21;
    *a7 = v18;
    goto LABEL_26;
  }
  v12 = v20 | 0x10000000;
  MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019230, 2u, v20 | 0x10000000, 0xE8u, a4 + 5);
LABEL_5:
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
LABEL_26:
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  return v12;
}

```

## disassembly

```asm
0x180001690  push    rbp
0x180001692  push    rbx
0x180001693  push    rsi
0x180001694  push    rdi
0x180001695  push    r12
0x180001697  push    r13
0x180001699  push    r14
0x18000169b  push    r15
0x18000169d  mov     rbp, rsp
0x1800016a0  sub     rsp, 78h
0x1800016a4  mov     r15d, 4
0x1800016aa  mov     [rbp+var_20], 0
0x1800016b2  mov     [rbp+var_28], 0
0x1800016ba  mov     rdi, r9
0x1800016bd  mov     [rbp+hObject], 0
0x1800016c5  mov     esi, r8d
0x1800016c8  mov     r12, rdx
0x1800016cb  mov     r13, rcx
0x1800016ce  test    r15b, r8b
0x1800016d1  jz      short loc_180001717
0x1800016d3  mov     [rsp+78h+var_58], 0B5h; unsigned int
0x1800016db  mov     r9d, 80070057h; int
0x1800016e1  mov     ebx, r9d
0x1800016e4  mov     ecx, r15d; unsigned int
0x1800016e7  mov     r8d, 2; unsigned int
0x1800016ed  lea     rdx, qword_180019230; int *
0x1800016f4  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800016f9  mov     rcx, [rbp+var_28]
0x1800016fd  test    rcx, rcx
0x180001700  jz      loc_1800018B9
0x180001706  mov     rax, [rcx]
0x180001709  mov     rax, [rax+10h]
0x18000170d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001712  jmp     loc_1800018B9
0x180001717  test    sil, 8
0x18000171b  jnz     short loc_1800016D3
0x18000171d  call    cs:__imp_IsTopLevelWindow
0x180001723  test    eax, eax
0x180001725  jz      short loc_1800016D3
0x180001727  test    sil, 1
0x18000172b  jnz     loc_18000192F
0x180001731  mov     rcx, r12
0x180001734  call    cs:__imp_IsTopLevelWindow
0x18000173a  test    eax, eax
0x18000173c  jz      loc_18000193D
0x180001742  cmp     r13, r12
0x180001745  jz      short loc_1800016D3
0x180001747  mov     ecx, [rdi]
0x180001749  test    cl, 2
0x18000174c  jnz     loc_180001912
0x180001752  and     ecx, 9
0x180001755  cmp     cl, 9
0x180001758  jnz     loc_1800016D3
0x18000175e  cmp     dword ptr [rdi+25h], 0
0x180001762  jz      loc_1800016D3
0x180001768  lea     r14, [rdi+4]
0x18000176c  mov     ecx, [r14]
0x18000176f  cmp     [r14+8], ecx
0x180001773  jl      loc_1800016D3
0x180001779  mov     eax, [r14+4]
0x18000177d  cmp     [r14+0Ch], eax
0x180001781  jl      loc_1800016D3
0x180001787  test    ecx, ecx
0x180001789  jnz     loc_1800016D3
0x18000178f  cmp     [rdi+8], ecx
0x180001792  jnz     loc_1800016D3
0x180001798  mov     rax, [rbp+arg_28]
0x18000179c  lea     rcx, [rbp+var_20]
0x1800017a0  mov     r9, [rbp+arg_20]
0x1800017a4  mov     qword ptr [rax], 0
0x1800017ab  mov     rdx, [r9]
0x1800017ae  call    ??$IID_PPV_ARGS_Helper@UICompositorInternal@Internal@Composition@UI@Windows@@@@YAPEAPEAXPEAPEAUICompositorInternal@Internal@Composition@UI@Windows@@@Z; IID_PPV_ARGS_Helper<Windows::UI::Composition::Internal::ICompositorInternal>(Windows::UI::Composition::Internal::ICompositorInternal * *)
0x1800017b3  mov     r8, rax
0x1800017b6  mov     rcx, r9
0x1800017b9  mov     rax, [rdx]
0x1800017bc  lea     rdx, _GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0
0x1800017c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017c8  mov     ebx, eax
0x1800017ca  test    eax, eax
0x1800017cc  js      loc_180001990
0x1800017d2  mov     rcx, [rbp+var_20]
0x1800017d6  test    rcx, rcx
0x1800017d9  jz      loc_18000195B
0x1800017df  mov     rax, [rcx]
0x1800017e2  lea     r8, [rbp+var_28]
0x1800017e6  lea     rdx, _GUID_e8de1639_4331_4b26_bc5f_6a321d347a85
0x1800017ed  mov     rax, [rax+0D8h]
0x1800017f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017f9  mov     ebx, eax
0x1800017fb  test    eax, eax
0x1800017fd  js      loc_180001983
0x180001803  mov     rcx, [rbp+var_20]
0x180001807  lea     r8, [rbp+hObject]
0x18000180b  mov     rdx, [rbp+var_28]
0x18000180f  mov     rax, [rcx]
0x180001812  mov     rax, [rax+0E0h]
0x180001819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000181e  mov     ebx, eax
0x180001820  test    eax, eax
0x180001822  js      loc_180001902
0x180001828  mov     r15d, 1
0x18000182e  lock xadd cs:dword_18001F990, r15d
0x180001837  inc     r15d
0x18000183a  call    cs:__imp_GetCurrentProcessId
0x180001840  mov     dword ptr [rbp+var_10], r15d
0x180001844  or      esi, 4
0x180001847  test    byte ptr [rdi], 10h
0x18000184a  mov     dword ptr [rbp+var_10+4], eax
0x18000184d  mov     rax, [rbp+var_10]
0x180001851  mov     [rbp+var_10], rax
0x180001855  jnz     loc_1800018F0
0x18000185b  mov     rax, [rbp+hObject]
0x18000185f  lea     rcx, [rdi+14h]
0x180001863  mov     r9d, [rdi]
0x180001866  mov     r8d, esi
0x180001869  mov     [rsp+78h+var_38], rax
0x18000186e  mov     rdx, r12
0x180001871  lea     rax, [rbp+var_10]
0x180001875  mov     [rsp+78h+var_40], rax
0x18000187a  mov     al, [rdi+24h]
0x18000187d  mov     [rsp+78h+var_48], al
0x180001881  mov     [rsp+78h+var_50], rcx
0x180001886  mov     rcx, r13
0x180001889  mov     qword ptr [rsp+78h+var_58], r14
0x18000188e  call    cs:__imp_NtDCompositionRegisterThumbnailVisual
0x180001894  test    eax, eax
0x180001896  js      loc_180001968
0x18000189c  mov     rax, [rbp+var_28]
0x1800018a0  mov     rcx, [rbp+arg_28]
0x1800018a4  mov     [rbp+var_28], 0
0x1800018ac  mov     [rcx], rax
0x1800018af  mov     rax, [rbp+arg_30]
0x1800018b3  mov     ecx, r15d
0x1800018b6  mov     [rax], rcx
0x1800018b9  mov     rcx, [rbp+var_20]
0x1800018bd  test    rcx, rcx
0x1800018c0  jz      short loc_1800018CE
0x1800018c2  mov     rax, [rcx]
0x1800018c5  mov     rax, [rax+10h]
0x1800018c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018ce  mov     rcx, [rbp+hObject]; hObject
0x1800018d2  test    rcx, rcx
0x1800018d5  jz      short loc_1800018DD
0x1800018d7  call    cs:__imp_CloseHandle
0x1800018dd  mov     eax, ebx
0x1800018df  add     rsp, 78h
0x1800018e3  pop     r15
0x1800018e5  pop     r14
0x1800018e7  pop     r13
0x1800018e9  pop     r12
0x1800018eb  pop     rdi
0x1800018ec  pop     rsi
0x1800018ed  pop     rbx
0x1800018ee  pop     rbp
0x1800018ef  retn
0x1800018f0  cmp     dword ptr [rdi+29h], 0
0x1800018f4  jz      loc_18000185B
0x1800018fa  or      esi, 8
0x1800018fd  jmp     loc_18000185B
0x180001902  mov     [rsp+78h+var_58], 0CBh
0x18000190a  mov     r9d, eax
0x18000190d  jmp     loc_1800016E4
0x180001912  mov     eax, [rdi+14h]
0x180001915  cmp     [rdi+1Ch], eax
0x180001918  jl      loc_1800016D3
0x18000191e  mov     eax, [rdi+18h]
0x180001921  cmp     [rdi+20h], eax
0x180001924  jl      loc_1800016D3
0x18000192a  jmp     loc_180001752
0x18000192f  test    r12, r12
0x180001932  jnz     loc_1800016D3
0x180001938  jmp     loc_180001742
0x18000193d  mov     edx, 0FFFFFFECh; nIndex
0x180001942  mov     rcx, r12; hWnd
0x180001945  call    cs:__imp_GetWindowLongPtrW
0x18000194b  bt      rax, 13h
0x180001950  jnb     loc_1800016D3
0x180001956  jmp     loc_180001742
0x18000195b  mov     [rsp+78h+var_58], 0C2h
0x180001963  jmp     loc_1800016DB
0x180001968  mov     ebx, eax
0x18000196a  mov     [rsp+78h+var_58], 0E8h
0x180001972  bts     ebx, 1Ch
0x180001976  mov     ecx, 4
0x18000197b  mov     r9d, ebx
0x18000197e  jmp     loc_1800016E7
0x180001983  mov     [rsp+78h+var_58], 0C8h
0x18000198b  jmp     loc_18000190A
0x180001990  mov     [rsp+78h+var_58], 0BFh
0x180001998  jmp     loc_18000190A
```
