# DrvCreateDeviceBitmap

- ea: `0x140001230`
- end: `0x1400015ce`
- name: `DrvCreateDeviceBitmap`
- size: `926`
- prototype: `FN_DrvCreateDeviceBitmap`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140001230`
- `0x140002470`
- `0x140015490`
- `0x140015bbc`
- `0x14001bff8`
- `0x14001cb60`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400014f8`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400014f8`
- `ntoskrnl!DbgPrint` at `0x140001453`
- `ntoskrnl!DbgPrint` at `0x140001453`
- `ntoskrnl!KdDebuggerEnabled` at `0x140001440`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14000128f`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400012aa`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400012c4`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14000128f`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400012aa`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400012c4`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14000158c`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14000158c`
- `watchdog!WdLogSingleEntry1` at `0x140001519`
- `watchdog!WdLogSingleEntry1` at `0x140001519`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000147b`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000147b`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400013df`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400013df`
- `watchdog!WdLogSingleEntry0` at `0x1400013c8`
- `watchdog!WdLogSingleEntry0` at `0x140001464`
- `watchdog!WdLogSingleEntry0` at `0x140001575`
- `watchdog!WdLogSingleEntry0` at `0x1400013c8`
- `watchdog!WdLogSingleEntry0` at `0x140001464`
- `watchdog!WdLogSingleEntry0` at `0x140001575`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140001530`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140001530`
- `WIN32K!W32GetSessionState` at `0x14000124a`
- `WIN32K!W32GetSessionState` at `0x1400012ef`
- `WIN32K!W32GetSessionState` at `0x14000124a`
- `WIN32K!W32GetSessionState` at `0x1400012ef`

## pseudocode

```c
HBITMAP __stdcall DrvCreateDeviceBitmap(DHPDEV dhpdev, SIZEL sizl, ULONG iFormat)
{
  __int64 v3; // rdi
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // ebx
  _QWORD *v9; // rax
  __int64 v10; // rax
  CddBitmapHw *v11; // rax
  CddBitmapHw *v12; // rax
  CddBitmapSw *v13; // rax
  CddBitmap *v14; // rdi
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  _QWORD *v18; // rax
  int v19; // r8d
  DHPDEV v20; // rsi
  __int64 v21; // rdx
  __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rdx
  _QWORD *v27; // rax
  __int64 v28; // [rsp+60h] [rbp-28h] BYREF
  int v29; // [rsp+68h] [rbp-20h]
  LONG cy; // [rsp+9Ch] [rbp+14h]

  cy = sizl.cy;
  v3 = iFormat;
  v6 = *(_QWORD *)(((__int64 (__fastcall *)(_QWORD, _QWORD))W32GetSessionState)(dhpdev, sizl) + 72);
  if ( !*(_DWORD *)(v6 + 3404) || *((_BYTE *)dhpdev + 2716) || sizl.cx * cy < 4096 )
    return 0;
  if ( (_DWORD)v3 != 6 )
  {
    v8 = 2262;
    *(_QWORD *)(WdLogNewEntry5_WdTrace() + 24) = v3;
LABEL_6:
    WdLogGlobalForLineNumber = v8;
    v9 = (_QWORD *)WdLogNewEntry5_WdTrace();
LABEL_32:
    v9[3] = gCddImageInfo;
    v9[4] = (unsigned int)dword_14003E570;
    v9[5] = 215857758;
    WdLogGlobalForLineNumber = v8;
    return 0;
  }
  if ( *((_DWORD *)dhpdev + 279) != 32 )
  {
    v10 = WdLogNewEntry5_WdTrace();
    v8 = 2268;
    *(_QWORD *)(v10 + 24) = dhpdev;
    *(_QWORD *)(v10 + 32) = *((unsigned int *)dhpdev + 279);
    goto LABEL_6;
  }
  if ( ((_DWORD)dhpdev[686] & 0x40) == 0 || *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v7, v6) + 72) + 3396LL) )
  {
    if ( ((_DWORD)dhpdev[686] & 0x800) == 0 )
    {
LABEL_31:
      WdLogSingleEntry0(6);
      v8 = 2294;
      WdLogGlobalForLineNumber = 2294;
      v9 = (_QWORD *)WdLogNewEntry5_WdLowResource();
      goto LABEL_32;
    }
    v13 = (CddBitmapSw *)operator new(0x3B8u);
    if ( v13 )
    {
      v12 = CddBitmapSw::CddBitmapSw(v13, (struct CDDPDEV *)dhpdev);
      goto LABEL_16;
    }
  }
  else
  {
    v11 = (CddBitmapHw *)operator new(0x4B0u);
    if ( v11 )
    {
      v12 = CddBitmapHw::CddBitmapHw(v11, (struct CDDPDEV *)dhpdev);
LABEL_16:
      v14 = v12;
      goto LABEL_18;
    }
  }
  v14 = 0;
LABEL_18:
  if ( !v14 )
    goto LABEL_31;
  ++*((_DWORD *)v14 + 46);
  _InterlockedIncrement((volatile signed __int32 *)dhpdev + 1807);
  v15 = (*(__int64 (__fastcall **)(CddBitmap *, SIZEL, __int64))(*(_QWORD *)v14 + 40LL))(v14, sizl, 6);
  if ( v15 < 0 )
  {
    WdLogSingleEntry1(4, v15);
    WdLogGlobalForLineNumber = 2319;
    v27 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v27[3] = gCddImageInfo;
    v27[4] = (unsigned int)dword_14003E570;
    v27[5] = 215857758;
    WdLogGlobalForLineNumber = 2319;
    (*(void (__fastcall **)(CddBitmap *))(*(_QWORD *)v14 + 48LL))(v14);
    return 0;
  }
  WdLogSingleEntry0(1);
  WdLogGlobalForLineNumber = 2308;
  v18 = (_QWORD *)WdLogNewEntry5_WdAssertion(v17, v16);
  v18[3] = gCddImageInfo;
  v18[4] = (unsigned int)dword_14003E570;
  v18[5] = 215857758;
  WdLogGlobalForLineNumber = 2308;
  CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v28, *((struct CDDMUTEX **)dhpdev + 907), v19);
  v20 = dhpdev + 1810;
  if ( *(struct _KTHREAD **)(*(_QWORD *)(*((_QWORD *)v14 + 1) + 7256LL) + 8LL) != KeGetCurrentThread()
    && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("CddBitmap::InsertToCddBitmapList is called without taking pCddBitmapListMutex");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 100;
    v23 = (_QWORD *)WdLogNewEntry5_WdError(v22, v21);
    v23[3] = gCddImageInfo;
    v23[4] = (unsigned int)dword_14003E570;
    v23[5] = 215857758;
    WdLogGlobalForLineNumber = 100;
    __debugbreak();
  }
  v24 = *(_QWORD *)v20;
  if ( *(DHPDEV *)(*(_QWORD *)v20 + 8LL) != v20 )
    __fastfail(3u);
  *((_QWORD *)v14 + 18) = v24;
  *((_QWORD *)v14 + 19) = v20;
  *(_QWORD *)(v24 + 8) = (char *)v14 + 144;
  *(_QWORD *)v20 = (char *)v14 + 144;
  v25 = *((_QWORD *)v14 + 1);
  if ( (*(_DWORD *)(v25 + 2744) & 0x40) == 0 )
    CddBitmap::InsertToCddBitmapOnCloseProcessList(v14, (struct _LIST_ENTRY *)(v25 + 7144));
  if ( v29 )
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v28);
  return 0;
}

```

## disassembly

```asm
0x140001230  mov     [rsp+arg_10], rbx
0x140001235  mov     [rsp+arg_8], rdx
0x14000123a  push    rbp
0x14000123b  push    rsi
0x14000123c  push    rdi
0x14000123d  sub     rsp, 70h
0x140001241  mov     edi, r8d
0x140001244  mov     rbx, rdx
0x140001247  mov     rsi, rcx
0x14000124a  call    cs:__imp_W32GetSessionState
0x140001251  nop     dword ptr [rax+rax+00h]
0x140001256  xor     ebp, ebp
0x140001258  mov     rdx, [rax+48h]
0x14000125c  cmp     [rdx+0D4Ch], ebp
0x140001262  jz      loc_1400015BB
0x140001268  cmp     [rsi+0A9Ch], bpl
0x14000126f  jnz     loc_1400015BB
0x140001275  mov     eax, dword ptr [rsp+88h+arg_8+4]
0x14000127c  imul    eax, ebx
0x14000127f  cmp     eax, 1000h
0x140001284  jl      loc_1400015BB
0x14000128a  cmp     edi, 6
0x14000128d  jz      short loc_1400012BB
0x14000128f  call    cs:__imp_WdLogNewEntry5_WdTrace
0x140001296  nop     dword ptr [rax+rax+00h]
0x14000129b  mov     ebx, 8D6h
0x1400012a0  mov     [rax+18h], rdi
0x1400012a4  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400012aa  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400012b1  nop     dword ptr [rax+rax+00h]
0x1400012b6  jmp     loc_140001598
0x1400012bb  cmp     dword ptr [rsi+45Ch], 20h ; ' '
0x1400012c2  jz      short loc_1400012E5
0x1400012c4  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400012cb  nop     dword ptr [rax+rax+00h]
0x1400012d0  mov     ebx, 8DCh
0x1400012d5  mov     [rax+18h], rsi
0x1400012d9  mov     ecx, [rsi+45Ch]
0x1400012df  mov     [rax+20h], rcx
0x1400012e3  jmp     short loc_1400012A4
0x1400012e5  mov     eax, [rsi+0AB8h]
0x1400012eb  test    al, 40h
0x1400012ed  jz      short loc_140001323
0x1400012ef  call    cs:__imp_W32GetSessionState
0x1400012f6  nop     dword ptr [rax+rax+00h]
0x1400012fb  mov     rcx, [rax+48h]
0x1400012ff  cmp     [rcx+0D44h], ebp
0x140001305  jnz     short loc_140001323
0x140001307  mov     ecx, 4B0h; cjMemSize
0x14000130c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001311  test    rax, rax
0x140001314  jz      short loc_140001352
0x140001316  mov     rdx, rsi; struct CDDPDEV *
0x140001319  mov     rcx, rax; this
0x14000131c  call    ??0CddBitmapHw@@QEAA@PEAUCDDPDEV@@@Z; CddBitmapHw::CddBitmapHw(CDDPDEV *)
0x140001321  jmp     short loc_14000134D
0x140001323  test    dword ptr [rsi+0AB8h], 800h
0x14000132d  jz      loc_140001570
0x140001333  mov     ecx, 3B8h; cjMemSize
0x140001338  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000133d  test    rax, rax
0x140001340  jz      short loc_140001352
0x140001342  mov     rdx, rsi; struct CDDPDEV *
0x140001345  mov     rcx, rax; this
0x140001348  call    ??0CddBitmapSw@@QEAA@PEAUCDDPDEV@@@Z; CddBitmapSw::CddBitmapSw(CDDPDEV *)
0x14000134d  mov     rdi, rax
0x140001350  jmp     short loc_140001355
0x140001352  mov     rdi, rbp
0x140001355  test    rdi, rdi
0x140001358  jz      loc_140001570
0x14000135e  inc     dword ptr [rdi+0B8h]
0x140001364  lock inc dword ptr [rsi+1C3Ch]
0x14000136b  mov     [rsp+88h+arg_0], rbp
0x140001373  lea     rcx, [rsp+88h+arg_0]
0x14000137b  mov     rax, [rdi]
0x14000137e  xor     r9d, r9d
0x140001381  mov     [rsp+88h+var_40], rcx
0x140001386  mov     rdx, rbx
0x140001389  mov     [rsp+88h+var_48], rbp
0x14000138e  mov     rcx, rdi
0x140001391  mov     [rsp+88h+var_50], ebp
0x140001395  mov     rax, [rax+28h]
0x140001399  lea     r8d, [r9+6]
0x14000139d  mov     [rsp+88h+var_58], bpl
0x1400013a2  mov     [rsp+88h+var_60], bpl
0x1400013a7  mov     [rsp+88h+var_68], bpl
0x1400013ac  call    _guard_dispatch_icall
0x1400013b1  test    eax, eax
0x1400013b3  js      loc_140001511
0x1400013b9  cmp     [rsp+88h+arg_0], rbp
0x1400013c1  jnz     short loc_14000140E
0x1400013c3  mov     ecx, 1
0x1400013c8  call    cs:__imp_WdLogSingleEntry0
0x1400013cf  nop     dword ptr [rax+rax+00h]
0x1400013d4  mov     ebx, 904h
0x1400013d9  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400013df  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400013e6  nop     dword ptr [rax+rax+00h]
0x1400013eb  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400013f2  mov     [rax+18h], rcx
0x1400013f6  mov     ecx, cs:dword_14003E570
0x1400013fc  mov     [rax+20h], rcx
0x140001400  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140001408  mov     cs:WdLogGlobalForLineNumber, ebx
0x14000140e  mov     rdx, [rsi+1C58h]; struct CDDMUTEX *
0x140001415  lea     rcx, [rsp+88h+var_28]; this
0x14000141a  call    ??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z; CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)
0x14000141f  mov     rdx, gs:188h
0x140001428  add     rsi, 1C48h
0x14000142f  mov     rax, [rdi+8]
0x140001433  mov     rcx, [rax+1C58h]
0x14000143a  cmp     [rcx+8], rdx
0x14000143e  jz      short loc_1400014AB
0x140001440  mov     rax, cs:KdDebuggerEnabled
0x140001447  cmp     [rax], bpl
0x14000144a  jz      short loc_1400014AB
0x14000144c  lea     rcx, Format; "CddBitmap::InsertToCddBitmapList is cal"...
0x140001453  call    cs:__imp_DbgPrint
0x14000145a  nop     dword ptr [rax+rax+00h]
0x14000145f  mov     ecx, 2
0x140001464  call    cs:__imp_WdLogSingleEntry0
0x14000146b  nop     dword ptr [rax+rax+00h]
0x140001470  mov     ebx, 64h ; 'd'
0x140001475  mov     cs:WdLogGlobalForLineNumber, ebx
0x14000147b  call    cs:__imp_WdLogNewEntry5_WdError
0x140001482  nop     dword ptr [rax+rax+00h]
0x140001487  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000148e  mov     [rax+18h], rcx
0x140001492  mov     ecx, cs:dword_14003E570
0x140001498  mov     [rax+20h], rcx
0x14000149c  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400014a4  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400014aa  int     3; Trap to Debugger
0x1400014ab  mov     rcx, [rsi]
0x1400014ae  cmp     [rcx+8], rsi
0x1400014b2  jz      short loc_1400014BB
0x1400014b4  mov     ecx, 3
0x1400014b9  int     29h; Win8: RtlFailFast(ecx)
0x1400014bb  lea     rax, [rdi+90h]
0x1400014c2  mov     [rax], rcx
0x1400014c5  mov     [rax+8], rsi
0x1400014c9  mov     [rcx+8], rax
0x1400014cd  mov     [rsi], rax
0x1400014d0  mov     rdx, [rdi+8]
0x1400014d4  mov     eax, [rdx+0AB8h]
0x1400014da  test    al, 40h
0x1400014dc  jnz     short loc_1400014ED
0x1400014de  add     rdx, 1BE8h; struct _LIST_ENTRY *
0x1400014e5  mov     rcx, rdi; this
0x1400014e8  call    ?InsertToCddBitmapOnCloseProcessList@CddBitmap@@QEAAXPEAU_LIST_ENTRY@@@Z; CddBitmap::InsertToCddBitmapOnCloseProcessList(_LIST_ENTRY *)
0x1400014ed  cmp     [rsp+88h+var_20], ebp
0x1400014f1  jz      short loc_140001504
0x1400014f3  mov     rcx, [rsp+88h+var_28]
0x1400014f8  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x1400014ff  nop     dword ptr [rax+rax+00h]
0x140001504  mov     rax, [rsp+88h+arg_0]
0x14000150c  jmp     loc_1400015BD
0x140001511  movsxd  rdx, eax
0x140001514  mov     ecx, 4
0x140001519  call    cs:__imp_WdLogSingleEntry1
0x140001520  nop     dword ptr [rax+rax+00h]
0x140001525  mov     ebx, 90Fh
0x14000152a  mov     cs:WdLogGlobalForLineNumber, ebx
0x140001530  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140001537  nop     dword ptr [rax+rax+00h]
0x14000153c  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140001543  mov     [rax+18h], rcx
0x140001547  mov     ecx, cs:dword_14003E570
0x14000154d  mov     [rax+20h], rcx
0x140001551  mov     rcx, rdi
0x140001554  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000155c  mov     cs:WdLogGlobalForLineNumber, ebx
0x140001562  mov     rax, [rdi]
0x140001565  mov     rax, [rax+30h]
0x140001569  call    _guard_dispatch_icall
0x14000156e  jmp     short loc_1400015BB
0x140001570  mov     ecx, 6
0x140001575  call    cs:__imp_WdLogSingleEntry0
0x14000157c  nop     dword ptr [rax+rax+00h]
0x140001581  mov     ebx, 8F6h
0x140001586  mov     cs:WdLogGlobalForLineNumber, ebx
0x14000158c  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x140001593  nop     dword ptr [rax+rax+00h]
0x140001598  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000159f  mov     [rax+18h], rcx
0x1400015a3  mov     ecx, cs:dword_14003E570
0x1400015a9  mov     [rax+20h], rcx
0x1400015ad  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400015b5  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400015bb  xor     eax, eax
0x1400015bd  mov     rbx, [rsp+88h+arg_10]
0x1400015c5  add     rsp, 70h
0x1400015c9  pop     rdi
0x1400015ca  pop     rsi
0x1400015cb  pop     rbp
0x1400015cc  retn
```
