# DwmpCreateSharedMultiWindowVisual

- ea: `0x180001060`
- end: `0x180001236`
- name: `DwmpCreateSharedMultiWindowVisual`
- size: `470`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001060`
- `0x180001520`
- `0x180001684`
- `0x18000352c`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001138`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001138`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800011de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800011de`
- `win32u!NtDCompositionRegisterVirtualDesktopVisual` at `0x180001157`
- `win32u!NtDCompositionRegisterVirtualDesktopVisual` at `0x180001157`

## pseudocode

```c
__int64 __fastcall DwmpCreateSharedMultiWindowVisual(HWND a1, _QWORD *a2, _QWORD *a3, _QWORD *a4)
{
  __int64 v8; // rax
  __int64 (__fastcall **v9)(_QWORD *, GUID *, __int64); // rdx
  int v10; // eax
  unsigned int v11; // ebx
  unsigned __int32 v12; // edi
  int v13; // eax
  unsigned int v15; // [rsp+20h] [rbp-38h]
  void *v16; // [rsp+28h] [rbp-30h]
  __int64 v17; // [rsp+30h] [rbp-28h] BYREF
  __int64 v18; // [rsp+38h] [rbp-20h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int64 v20; // [rsp+48h] [rbp-10h] BYREF

  v18 = 0;
  v17 = 0;
  hObject = 0;
  if ( !IsHwndInProcess(a1) )
  {
    v11 = -2147024809;
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019388, 2u, -2147024809, 0x116u, v16);
    goto LABEL_15;
  }
  *a3 = 0;
  v8 = IID_PPV_ARGS_Helper<Windows::UI::Composition::Internal::ICompositorInternal>(&v18, *a2);
  v10 = (*v9)(a2, &GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0, v8);
  v11 = v10;
  if ( v10 < 0 )
  {
    v15 = 288;
LABEL_14:
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019388, 2u, v10, v15, v16);
    goto LABEL_15;
  }
  if ( !v18 )
  {
    v11 = -2147024809;
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019388, 2u, -2147024809, 0x123u, v16);
    goto LABEL_15;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v18 + 216LL))(
          v18,
          &GUID_e8de1639_4331_4b26_bc5f_6a321d347a85,
          &v17);
  v11 = v10;
  if ( v10 < 0 )
  {
    v15 = 297;
    goto LABEL_14;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, __int64, HANDLE *))(*(_QWORD *)v18 + 224LL))(v18, v17, &hObject);
  v11 = v10;
  if ( v10 < 0 )
  {
    v15 = 300;
    goto LABEL_14;
  }
  v12 = _InterlockedIncrement(&dword_18001F990);
  v20 = __PAIR64__(GetCurrentProcessId(), v12);
  v13 = NtDCompositionRegisterVirtualDesktopVisual(a1, &v20, hObject);
  if ( v13 >= 0 )
  {
    *a3 = v17;
    *a4 = v12;
    v17 = 0;
    goto LABEL_8;
  }
  v11 = v13 | 0x10000000;
  MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019388, 2u, v13 | 0x10000000, 0x137u, v16);
LABEL_15:
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
LABEL_8:
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( hObject )
    CloseHandle(hObject);
  return v11;
}

```

## disassembly

```asm
0x180001060  push    rbp
0x180001062  push    rbx
0x180001063  push    rsi
0x180001064  push    rdi
0x180001065  push    r14
0x180001067  push    r15
0x180001069  mov     rbp, rsp
0x18000106c  sub     rsp, 58h
0x180001070  mov     r15, r9
0x180001073  mov     [rbp+var_20], 0
0x18000107b  mov     rsi, r8
0x18000107e  mov     [rbp+var_28], 0
0x180001086  mov     rbx, rdx
0x180001089  mov     [rbp+hObject], 0
0x180001091  mov     r14, rcx
0x180001094  call    ?IsHwndInProcess@@YA_NPEAUHWND__@@@Z; IsHwndInProcess(HWND__ *)
0x180001099  test    al, al
0x18000109b  jz      loc_1800011E6
0x1800010a1  mov     qword ptr [rsi], 0
0x1800010a8  lea     rcx, [rbp+var_20]
0x1800010ac  mov     rdx, [rbx]
0x1800010af  call    ??$IID_PPV_ARGS_Helper@UICompositorInternal@Internal@Composition@UI@Windows@@@@YAPEAPEAXPEAPEAUICompositorInternal@Internal@Composition@UI@Windows@@@Z; IID_PPV_ARGS_Helper<Windows::UI::Composition::Internal::ICompositorInternal>(Windows::UI::Composition::Internal::ICompositorInternal * *)
0x1800010b4  mov     r8, rax
0x1800010b7  mov     rcx, rbx
0x1800010ba  mov     rax, [rdx]
0x1800010bd  lea     rdx, _GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0
0x1800010c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010c9  mov     ebx, eax
0x1800010cb  test    eax, eax
0x1800010cd  js      loc_1800011A6
0x1800010d3  mov     rcx, [rbp+var_20]
0x1800010d7  test    rcx, rcx
0x1800010da  jz      loc_1800011F9
0x1800010e0  mov     rax, [rcx]
0x1800010e3  lea     r8, [rbp+var_28]
0x1800010e7  lea     rdx, _GUID_e8de1639_4331_4b26_bc5f_6a321d347a85
0x1800010ee  mov     rax, [rax+0D8h]
0x1800010f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010fa  mov     ebx, eax
0x1800010fc  test    eax, eax
0x1800010fe  js      loc_180001229
0x180001104  mov     rcx, [rbp+var_20]
0x180001108  lea     r8, [rbp+hObject]
0x18000110c  mov     rdx, [rbp+var_28]
0x180001110  mov     rax, [rcx]
0x180001113  mov     rax, [rax+0E0h]
0x18000111a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000111f  mov     ebx, eax
0x180001121  test    eax, eax
0x180001123  js      loc_18000121F
0x180001129  mov     edi, 1
0x18000112e  lock xadd cs:dword_18001F990, edi
0x180001136  inc     edi
0x180001138  call    cs:__imp_GetCurrentProcessId
0x18000113e  mov     r8, [rbp+hObject]
0x180001142  lea     rdx, [rbp+var_10]
0x180001146  mov     dword ptr [rbp+var_10+4], eax
0x180001149  mov     rcx, r14
0x18000114c  mov     dword ptr [rbp+var_10], edi
0x18000114f  mov     rax, [rbp+var_10]
0x180001153  mov     [rbp+var_10], rax
0x180001157  call    cs:__imp_NtDCompositionRegisterVirtualDesktopVisual
0x18000115d  test    eax, eax
0x18000115f  js      loc_18000120C
0x180001165  mov     rax, [rbp+var_28]
0x180001169  mov     [rsi], rax
0x18000116c  mov     eax, edi
0x18000116e  mov     [r15], rax
0x180001171  mov     [rbp+var_28], 0
0x180001179  mov     rcx, [rbp+var_20]
0x18000117d  test    rcx, rcx
0x180001180  jz      short loc_18000118E
0x180001182  mov     rax, [rcx]
0x180001185  mov     rax, [rax+10h]
0x180001189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000118e  mov     rcx, [rbp+hObject]; hObject
0x180001192  test    rcx, rcx
0x180001195  jnz     short loc_1800011DE
0x180001197  mov     eax, ebx
0x180001199  add     rsp, 58h
0x18000119d  pop     r15
0x18000119f  pop     r14
0x1800011a1  pop     rdi
0x1800011a2  pop     rsi
0x1800011a3  pop     rbx
0x1800011a4  pop     rbp
0x1800011a5  retn
0x1800011a6  mov     [rsp+58h+var_38], 120h; unsigned int
0x1800011ae  mov     r9d, eax; int
0x1800011b1  mov     r8d, 2; unsigned int
0x1800011b7  lea     rdx, qword_180019388; int *
0x1800011be  lea     ecx, [r8+2]; unsigned int
0x1800011c2  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800011c7  mov     rcx, [rbp+var_28]
0x1800011cb  test    rcx, rcx
0x1800011ce  jz      short loc_180001179
0x1800011d0  mov     rax, [rcx]
0x1800011d3  mov     rax, [rax+10h]
0x1800011d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011dc  jmp     short loc_180001179
0x1800011de  call    cs:__imp_CloseHandle
0x1800011e4  jmp     short loc_180001197
0x1800011e6  mov     r9d, 80070057h
0x1800011ec  mov     [rsp+58h+var_38], 116h
0x1800011f4  mov     ebx, r9d
0x1800011f7  jmp     short loc_1800011B1
0x1800011f9  mov     r9d, 80070057h
0x1800011ff  mov     [rsp+58h+var_38], 123h
0x180001207  mov     ebx, r9d
0x18000120a  jmp     short loc_1800011B1
0x18000120c  mov     ebx, eax
0x18000120e  mov     [rsp+58h+var_38], 137h
0x180001216  bts     ebx, 1Ch
0x18000121a  mov     r9d, ebx
0x18000121d  jmp     short loc_1800011B1
0x18000121f  mov     [rsp+58h+var_38], 12Ch
0x180001227  jmp     short loc_1800011AE
0x180001229  mov     [rsp+58h+var_38], 129h
0x180001231  jmp     loc_1800011AE
```
