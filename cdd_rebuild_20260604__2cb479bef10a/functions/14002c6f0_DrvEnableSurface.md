# DrvEnableSurface

- ea: `0x14002c6f0`
- end: `0x14002cd78`
- name: `DrvEnableSurface`
- size: `1672`
- prototype: `FN_DrvEnableSurface`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x140008714`
- `0x14000874c`
- `0x140018d9c`
- `0x14001cc58`
- `0x14002a218`
- `0x14002b5f0`
- `0x14002c6f0`
- `0x140033134`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogSingleEntry4` at `0x14002c7b0`
- `watchdog!WdLogSingleEntry4` at `0x14002c7b0`
- `watchdog!WdLogSingleEntry5` at `0x14002c9e8`
- `watchdog!WdLogSingleEntry5` at `0x14002ca51`
- `watchdog!WdLogSingleEntry5` at `0x14002caa6`
- `watchdog!WdLogSingleEntry5` at `0x14002cb2b`
- `watchdog!WdLogSingleEntry5` at `0x14002cba9`
- `watchdog!WdLogSingleEntry5` at `0x14002cc1d`
- `watchdog!WdLogSingleEntry5` at `0x14002cc4a`
- `watchdog!WdLogSingleEntry5` at `0x14002ccbb`
- `watchdog!WdLogSingleEntry5` at `0x14002c9e8`
- `watchdog!WdLogSingleEntry5` at `0x14002ca51`
- `watchdog!WdLogSingleEntry5` at `0x14002caa6`
- `watchdog!WdLogSingleEntry5` at `0x14002cb2b`
- `watchdog!WdLogSingleEntry5` at `0x14002cba9`
- `watchdog!WdLogSingleEntry5` at `0x14002cc1d`
- `watchdog!WdLogSingleEntry5` at `0x14002cc4a`
- `watchdog!WdLogSingleEntry5` at `0x14002ccbb`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002c7c7`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002cb44`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002cbc0`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002cc61`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002ccd2`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002c7c7`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002cb44`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002cbc0`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002cc61`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002ccd2`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14002c9ff`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14002c9ff`
- `watchdog!WdLogSingleEntry1` at `0x14002c71c`
- `watchdog!WdLogSingleEntry1` at `0x14002cd05`
- `watchdog!WdLogSingleEntry1` at `0x14002c71c`
- `watchdog!WdLogSingleEntry1` at `0x14002cd05`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002ca68`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002cd1c`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002ca68`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002cd1c`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002c85c`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002c8aa`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002c85c`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002c8aa`
- `watchdog!WdLogSingleEntry0` at `0x14002c845`
- `watchdog!WdLogSingleEntry0` at `0x14002c893`
- `watchdog!WdLogSingleEntry0` at `0x14002c845`
- `watchdog!WdLogSingleEntry0` at `0x14002c893`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002c733`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002cabd`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002c733`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002cabd`
- `WIN32K!EngAssociateSurface` at `0x14002c971`
- `WIN32K!EngAssociateSurface` at `0x14002c971`
- `WIN32K!EngLockSurface` at `0x14002c94f`
- `WIN32K!EngLockSurface` at `0x14002c94f`
- `WIN32K!EngCreateBitmap` at `0x14002c934`
- `WIN32K!EngCreateBitmap` at `0x14002c934`
- `WIN32K!EngCreateDeviceSurface` at `0x14002c8ef`
- `WIN32K!EngCreateDeviceSurface` at `0x14002c8ef`
- `WIN32K!EngDeleteSurface` at `0x14002cbee`
- `WIN32K!EngDeleteSurface` at `0x14002cc8f`
- `WIN32K!EngDeleteSurface` at `0x14002cbee`
- `WIN32K!EngDeleteSurface` at `0x14002cc8f`
- `WIN32K!EngUnlockSurface` at `0x14002cb73`
- `WIN32K!EngUnlockSurface` at `0x14002cb73`

## pseudocode

```c
HSURF __stdcall DrvEnableSurface(DHPDEV dhpdev)
{
  _QWORD *v2; // rax
  __int64 v3; // rcx
  int v4; // r8d
  unsigned int v5; // ebp
  int v6; // edi
  int v7; // edi
  _QWORD *v8; // rax
  __int64 v9; // r14
  __int64 v10; // r15
  int v11; // eax
  LONG v12; // ebp
  ULONG v13; // edi
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  HSURF DeviceSurface; // rax
  HSURF v17; // rsi
  HBITMAP Bitmap; // rax
  HSURF v19; // rbp
  SURFOBJ *v20; // rdi
  void *v21; // rax
  int v22; // eax
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // rax
  int v26; // edi
  _QWORD *v27; // rax
  _QWORD *v28; // rax
  _BYTE v30[16]; // [rsp+30h] [rbp-38h] BYREF
  SIZEL sizl; // [rsp+70h] [rbp+8h]

  WdLogSingleEntry1(4, dhpdev);
  WdLogGlobalForLineNumber = 1827;
  v2 = (_QWORD *)WdLogNewEntry5_WdEvent();
  v3 = (unsigned int)dword_14003E570;
  v2[3] = gCddImageInfo;
  v2[4] = v3;
  v2[5] = 215857758;
  WdLogGlobalForLineNumber = 1827;
  CDDDEVLOCK::CDDDEVLOCK((CDDDEVLOCK *)v30, *((HSEMAPHORE *)dhpdev + 365), v4);
  v5 = *((_DWORD *)dhpdev + 279);
  v6 = *((_DWORD *)dhpdev + 199);
  if ( !(unsigned int)AllocPointerSurface((struct _POINTER_INFO *)(dhpdev + 280)) )
  {
    WdLogSingleEntry4(
      6,
      dhpdev,
      *((unsigned int *)dhpdev + 196),
      *((unsigned int *)dhpdev + 300),
      *((unsigned int *)dhpdev + 301));
    v7 = 1840;
    WdLogGlobalForLineNumber = 1840;
    v8 = (_QWORD *)WdLogNewEntry5_WdLowResource();
LABEL_3:
    v8[3] = gCddImageInfo;
    v8[4] = (unsigned int)dword_14003E570;
LABEL_32:
    v8[5] = 215857758;
    WdLogGlobalForLineNumber = v7;
    goto LABEL_33;
  }
  v9 = *((int *)dhpdev + 199);
  v10 = *((int *)dhpdev + 200);
  v11 = *((_DWORD *)dhpdev + 279);
  sizl = *(SIZEL *)(dhpdev + 199);
  v12 = (v6 * (v5 >> 3) + 3) & 0xFFFFFFFC;
  if ( v11 == 8 )
  {
    v13 = 3;
  }
  else if ( v11 == 16 )
  {
    v13 = 4;
  }
  else
  {
    v13 = (v11 != 24) + 5;
  }
  if ( *((_QWORD *)dhpdev + 319) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1866;
    v14 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v14[3] = gCddImageInfo;
    v14[4] = (unsigned int)dword_14003E570;
    v14[5] = 215857758;
    WdLogGlobalForLineNumber = 1866;
  }
  if ( *((_QWORD *)dhpdev + 2) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1867;
    v15 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v15[3] = gCddImageInfo;
    v15[4] = (unsigned int)dword_14003E570;
    v15[5] = 215857758;
    WdLogGlobalForLineNumber = 1867;
  }
  *((_QWORD *)dhpdev + 320) = (unsigned int)(*((_DWORD *)dhpdev + 200) * v12);
  DeviceSurface = EngCreateDeviceSurface(0, sizl, v13);
  v17 = DeviceSurface;
  if ( !DeviceSurface )
  {
    WdLogSingleEntry5(6, dhpdev, *((unsigned int *)dhpdev + 196), v9, v10, v13);
    v7 = 1985;
    WdLogGlobalForLineNumber = 1985;
    v8 = (_QWORD *)WdLogNewEntry5_WdLowResource();
    v8[3] = gCddImageInfo;
    v8[4] = (unsigned int)dword_14003E570;
    goto LABEL_32;
  }
  if ( !CddModifySurface((struct CDDPDEV *)dhpdev, DeviceSurface) )
  {
    WdLogSingleEntry5(6, dhpdev, v17, v9, v10, v13);
    v26 = 1977;
    goto LABEL_29;
  }
  Bitmap = EngCreateBitmap(sizl, v12, v13, 1u, (PVOID)0xDEADBEEFLL);
  v19 = (HSURF)Bitmap;
  if ( !Bitmap )
  {
    WdLogSingleEntry5(6, dhpdev, *((unsigned int *)dhpdev + 196), v9, v10, v13);
    v26 = 1971;
LABEL_29:
    WdLogGlobalForLineNumber = v26;
    v27 = (_QWORD *)WdLogNewEntry5_WdLowResource();
    v27[3] = gCddImageInfo;
    v27[4] = (unsigned int)dword_14003E570;
    v27[5] = 215857758;
    WdLogGlobalForLineNumber = v26;
    goto LABEL_30;
  }
  v20 = EngLockSurface((HSURF)Bitmap);
  if ( !v20 )
  {
    WdLogSingleEntry5(
      6,
      v19,
      dhpdev,
      *((unsigned int *)dhpdev + 196),
      *((unsigned int *)dhpdev + 199),
      *((unsigned int *)dhpdev + 200));
    WdLogGlobalForLineNumber = 1963;
    v25 = (_QWORD *)WdLogNewEntry5_WdLowResource();
    v25[3] = gCddImageInfo;
    v25[4] = (unsigned int)dword_14003E570;
    v25[5] = 215857758;
    WdLogGlobalForLineNumber = 1963;
    goto LABEL_26;
  }
  if ( !EngAssociateSurface(v19, *((HDEV *)dhpdev + 1), 0) )
  {
    WdLogSingleEntry5(
      6,
      v19,
      dhpdev,
      *((unsigned int *)dhpdev + 196),
      *((unsigned int *)dhpdev + 199),
      *((unsigned int *)dhpdev + 200));
    WdLogGlobalForLineNumber = 1955;
    v24 = (_QWORD *)WdLogNewEntry5_WdLowResource();
    v24[3] = gCddImageInfo;
    v24[4] = (unsigned int)dword_14003E570;
    v24[5] = 215857758;
    WdLogGlobalForLineNumber = 1955;
    EngUnlockSurface(v20);
LABEL_26:
    EngDeleteSurface(v19);
LABEL_30:
    EngDeleteSurface(v17);
LABEL_33:
    WdLogSingleEntry1(2, dhpdev);
    WdLogGlobalForLineNumber = 1990;
    v28 = (_QWORD *)WdLogNewEntry5_WdError();
    v28[3] = gCddImageInfo;
    v28[4] = (unsigned int)dword_14003E570;
    v28[5] = 215857758;
    WdLogGlobalForLineNumber = 1990;
    vDisableSURF((struct CDDPDEV *)dhpdev);
    v17 = 0;
    goto LABEL_34;
  }
  v21 = (void *)*((_QWORD *)dhpdev + 319);
  *((_QWORD *)dhpdev + 349) = v20;
  *((_QWORD *)dhpdev + 2) = v17;
  v20->pvBits = v21;
  *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 56LL) = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL);
  v22 = DrvAssertModeInternal(dhpdev, 1, 1);
  if ( v22 < 0 )
  {
    WdLogSingleEntry5(
      3,
      dhpdev,
      *((unsigned int *)dhpdev + 196),
      *((unsigned int *)dhpdev + 199),
      *((unsigned int *)dhpdev + 200),
      v22);
    v7 = 1931;
    WdLogGlobalForLineNumber = 1931;
    v8 = (_QWORD *)WdLogNewEntry5_WdWarning();
    goto LABEL_3;
  }
  if ( *((_DWORD *)dhpdev + 279) == 8 && !(unsigned int)bInit256ColorPalette((struct CDDPDEV *)dhpdev) )
  {
    WdLogSingleEntry5(
      2,
      dhpdev,
      *((unsigned int *)dhpdev + 196),
      *((unsigned int *)dhpdev + 199),
      *((unsigned int *)dhpdev + 200),
      *((unsigned int *)dhpdev + 247));
    v7 = 1939;
    WdLogGlobalForLineNumber = 1939;
    v8 = (_QWORD *)WdLogNewEntry5_WdError();
    goto LABEL_3;
  }
  WdLogSingleEntry5(
    4,
    dhpdev,
    *((unsigned int *)dhpdev + 196),
    *((unsigned int *)dhpdev + 199),
    *((unsigned int *)dhpdev + 200),
    *((int *)dhpdev + 258));
  WdLogGlobalForLineNumber = 1945;
  v23 = (_QWORD *)WdLogNewEntry5_WdEvent();
  v23[3] = gCddImageInfo;
  v23[4] = (unsigned int)dword_14003E570;
  v23[5] = 215857758;
  WdLogGlobalForLineNumber = 1945;
  (*((void (__fastcall **)(HSURF, _QWORD))dhpdev + 84))(v17, *((_QWORD *)dhpdev + 308));
LABEL_34:
  CDDDEVLOCK::vUnlock((CDDDEVLOCK *)v30);
  return v17;
}

```

## disassembly

```asm
0x14002c6f0  mov     [rsp+arg_8], rbx
0x14002c6f5  mov     [rsp+arg_10], rbp
0x14002c6fa  push    rsi
0x14002c6fb  push    rdi
0x14002c6fc  push    r13
0x14002c6fe  push    r14
0x14002c700  push    r15
0x14002c702  sub     rsp, 40h
0x14002c706  mov     rbx, rcx
0x14002c709  mov     qword ptr [rsp+68h+sizl.cx], 0
0x14002c712  mov     rdx, rcx
0x14002c715  mov     esi, 4
0x14002c71a  mov     ecx, esi
0x14002c71c  call    cs:__imp_WdLogSingleEntry1
0x14002c723  nop     dword ptr [rax+rax+00h]
0x14002c728  mov     edi, 723h
0x14002c72d  mov     cs:WdLogGlobalForLineNumber, edi
0x14002c733  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14002c73a  nop     dword ptr [rax+rax+00h]
0x14002c73f  mov     rdx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002c746  mov     r13d, 0CDDBA5Eh
0x14002c74c  mov     ecx, cs:dword_14003E570
0x14002c752  mov     [rax+18h], rdx
0x14002c756  mov     [rax+20h], rcx
0x14002c75a  lea     rcx, [rsp+68h+var_38]; this
0x14002c75f  mov     [rax+28h], r13
0x14002c763  mov     cs:WdLogGlobalForLineNumber, edi
0x14002c769  mov     rdx, [rbx+0B68h]; HSEMAPHORE
0x14002c770  call    ??0CDDDEVLOCK@@QEAA@PEAUHSEMAPHORE__@@H@Z; CDDDEVLOCK::CDDDEVLOCK(HSEMAPHORE__ *,int)
0x14002c775  mov     ebp, [rbx+45Ch]
0x14002c77b  lea     rcx, [rbx+460h]; struct _POINTER_INFO *
0x14002c782  mov     edi, [rbx+31Ch]
0x14002c788  call    ?AllocPointerSurface@@YAHPEAU_POINTER_INFO@@@Z; AllocPointerSurface(_POINTER_INFO *)
0x14002c78d  test    eax, eax
0x14002c78f  jnz     short loc_14002C7ED
0x14002c791  mov     eax, [rbx+4B4h]
0x14002c797  lea     ecx, [rsi+2]
0x14002c79a  mov     r9d, [rbx+4B0h]
0x14002c7a1  mov     rdx, rbx
0x14002c7a4  mov     r8d, [rbx+310h]
0x14002c7ab  mov     [rsp+68h+pvBits], rax
0x14002c7b0  call    cs:__imp_WdLogSingleEntry4
0x14002c7b7  nop     dword ptr [rax+rax+00h]
0x14002c7bc  mov     edi, 730h
0x14002c7c1  mov     cs:WdLogGlobalForLineNumber, edi
0x14002c7c7  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14002c7ce  nop     dword ptr [rax+rax+00h]
0x14002c7d3  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002c7da  mov     [rax+18h], rcx
0x14002c7de  mov     ecx, cs:dword_14003E570
0x14002c7e4  mov     [rax+20h], rcx
0x14002c7e8  jmp     loc_14002CCF3
0x14002c7ed  movsxd  r14, dword ptr [rbx+31Ch]
0x14002c7f4  movsxd  r15, dword ptr [rbx+320h]
0x14002c7fb  mov     eax, [rbx+45Ch]
0x14002c801  shr     ebp, 3
0x14002c804  imul    ebp, edi
0x14002c807  mov     [rsp+68h+sizl.cx], r14d
0x14002c80c  mov     [rsp+68h+sizl.cy], r15d
0x14002c811  add     ebp, 3
0x14002c814  and     ebp, 0FFFFFFFCh
0x14002c817  cmp     eax, 8
0x14002c81a  jnz     short loc_14002C821
0x14002c81c  lea     edi, [rax-5]
0x14002c81f  jmp     short loc_14002C836
0x14002c821  cmp     eax, 10h
0x14002c824  jnz     short loc_14002C82A
0x14002c826  mov     edi, esi
0x14002c828  jmp     short loc_14002C836
0x14002c82a  xor     edi, edi
0x14002c82c  cmp     eax, 18h
0x14002c82f  setnz   dil
0x14002c833  add     edi, 5
0x14002c836  cmp     qword ptr [rbx+9F8h], 0
0x14002c83e  jz      short loc_14002C887
0x14002c840  mov     ecx, 1
0x14002c845  call    cs:__imp_WdLogSingleEntry0
0x14002c84c  nop     dword ptr [rax+rax+00h]
0x14002c851  mov     esi, 74Ah
0x14002c856  mov     cs:WdLogGlobalForLineNumber, esi
0x14002c85c  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002c863  nop     dword ptr [rax+rax+00h]
0x14002c868  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002c86f  mov     [rax+18h], rcx
0x14002c873  mov     ecx, cs:dword_14003E570
0x14002c879  mov     [rax+20h], rcx
0x14002c87d  mov     [rax+28h], r13
0x14002c881  mov     cs:WdLogGlobalForLineNumber, esi
0x14002c887  cmp     qword ptr [rbx+10h], 0
0x14002c88c  jz      short loc_14002C8D5
0x14002c88e  mov     ecx, 1
0x14002c893  call    cs:__imp_WdLogSingleEntry0
0x14002c89a  nop     dword ptr [rax+rax+00h]
0x14002c89f  mov     esi, 74Bh
0x14002c8a4  mov     cs:WdLogGlobalForLineNumber, esi
0x14002c8aa  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002c8b1  nop     dword ptr [rax+rax+00h]
0x14002c8b6  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002c8bd  mov     [rax+18h], rcx
0x14002c8c1  mov     ecx, cs:dword_14003E570
0x14002c8c7  mov     [rax+20h], rcx
0x14002c8cb  mov     [rax+28h], r13
0x14002c8cf  mov     cs:WdLogGlobalForLineNumber, esi
0x14002c8d5  mov     rdx, qword ptr [rsp+68h+sizl.cx]; sizl
0x14002c8da  mov     eax, ebp
0x14002c8dc  imul    eax, [rbx+320h]
0x14002c8e3  mov     r8d, edi; iFormatCompat
0x14002c8e6  xor     ecx, ecx; dhsurf
0x14002c8e8  mov     [rbx+0A00h], rax
0x14002c8ef  call    cs:__imp_EngCreateDeviceSurface
0x14002c8f6  nop     dword ptr [rax+rax+00h]
0x14002c8fb  mov     rsi, rax
0x14002c8fe  test    rax, rax
0x14002c901  jz      loc_14002CC9D
0x14002c907  mov     rdx, rax; HSURF
0x14002c90a  mov     rcx, rbx; struct CDDPDEV *
0x14002c90d  call    ?CddModifySurface@@YAHPEAUCDDPDEV@@PEAUHSURF__@@@Z; CddModifySurface(CDDPDEV *,HSURF__ *)
0x14002c912  test    eax, eax
0x14002c914  jz      loc_14002CC30
0x14002c91a  mov     rcx, qword ptr [rsp+68h+sizl.cx]; sizl
0x14002c91f  mov     eax, 0DEADBEEFh
0x14002c924  mov     r9d, 1; fl
0x14002c92a  mov     [rsp+68h+pvBits], rax; pvBits
0x14002c92f  mov     r8d, edi; iFormat
0x14002c932  mov     edx, ebp; lWidth
0x14002c934  call    cs:__imp_EngCreateBitmap
0x14002c93b  nop     dword ptr [rax+rax+00h]
0x14002c940  mov     rbp, rax
0x14002c943  test    rax, rax
0x14002c946  jz      loc_14002CBFF
0x14002c94c  mov     rcx, rax; hsurf
0x14002c94f  call    cs:__imp_EngLockSurface
0x14002c956  nop     dword ptr [rax+rax+00h]
0x14002c95b  mov     rdi, rax
0x14002c95e  test    rax, rax
0x14002c961  jz      loc_14002CB81
0x14002c967  mov     rdx, [rbx+8]; hdev
0x14002c96b  xor     r8d, r8d; flHooks
0x14002c96e  mov     rcx, rbp; hsurf
0x14002c971  call    cs:__imp_EngAssociateSurface
0x14002c978  nop     dword ptr [rax+rax+00h]
0x14002c97d  test    eax, eax
0x14002c97f  jz      loc_14002CB03
0x14002c985  mov     rax, [rbx+9F8h]
0x14002c98c  mov     [rbx+0AE8h], rdi
0x14002c993  mov     [rbx+10h], rsi
0x14002c997  mov     [rdi+30h], rax
0x14002c99b  mov     rcx, [rbx+0AE8h]
0x14002c9a2  mov     rax, [rcx+30h]
0x14002c9a6  mov     [rcx+38h], rax
0x14002c9aa  mov     eax, 1
0x14002c9af  mov     r8d, eax; int
0x14002c9b2  mov     edx, eax; int
0x14002c9b4  mov     rcx, rbx; struct DHPDEV__ *
0x14002c9b7  call    ?DrvAssertModeInternal@@YAJPEAUDHPDEV__@@HH@Z; DrvAssertModeInternal(DHPDEV__ *,int,int)
0x14002c9bc  test    eax, eax
0x14002c9be  jns     short loc_14002CA10
0x14002c9c0  mov     edx, [rbx+320h]
0x14002c9c6  mov     ecx, 3
0x14002c9cb  mov     r9d, [rbx+31Ch]
0x14002c9d2  mov     r8d, [rbx+310h]
0x14002c9d9  cdqe
0x14002c9db  mov     [rsp+68h+var_40], rax
0x14002c9e0  mov     [rsp+68h+pvBits], rdx
0x14002c9e5  mov     rdx, rbx
0x14002c9e8  call    cs:__imp_WdLogSingleEntry5
0x14002c9ef  nop     dword ptr [rax+rax+00h]
0x14002c9f4  mov     edi, 78Bh
0x14002c9f9  mov     cs:WdLogGlobalForLineNumber, edi
0x14002c9ff  call    cs:__imp_WdLogNewEntry5_WdWarning
0x14002ca06  nop     dword ptr [rax+rax+00h]
0x14002ca0b  jmp     loc_14002C7D3
0x14002ca10  cmp     dword ptr [rbx+45Ch], 8
0x14002ca17  jnz     short loc_14002CA79
0x14002ca19  mov     rcx, rbx; struct CDDPDEV *
0x14002ca1c  call    ?bInit256ColorPalette@@YAHPEAUCDDPDEV@@@Z; bInit256ColorPalette(CDDPDEV *)
0x14002ca21  test    eax, eax
0x14002ca23  jnz     short loc_14002CA79
0x14002ca25  mov     ecx, [rbx+320h]
0x14002ca2b  mov     rdx, rbx
0x14002ca2e  mov     eax, [rbx+3DCh]
0x14002ca34  mov     r9d, [rbx+31Ch]
0x14002ca3b  mov     r8d, [rbx+310h]
0x14002ca42  mov     [rsp+68h+var_40], rax
0x14002ca47  mov     [rsp+68h+pvBits], rcx
0x14002ca4c  mov     ecx, 2
0x14002ca51  call    cs:__imp_WdLogSingleEntry5
0x14002ca58  nop     dword ptr [rax+rax+00h]
0x14002ca5d  mov     edi, 793h
0x14002ca62  mov     cs:WdLogGlobalForLineNumber, edi
0x14002ca68  call    cs:__imp_WdLogNewEntry5_WdError
0x14002ca6f  nop     dword ptr [rax+rax+00h]
0x14002ca74  jmp     loc_14002C7D3
0x14002ca79  mov     edx, [rbx+320h]
0x14002ca7f  mov     ecx, 4
0x14002ca84  movsxd  rax, dword ptr [rbx+408h]
0x14002ca8b  mov     r9d, [rbx+31Ch]
0x14002ca92  mov     r8d, [rbx+310h]
0x14002ca99  mov     [rsp+68h+var_40], rax
0x14002ca9e  mov     [rsp+68h+pvBits], rdx
0x14002caa3  mov     rdx, rbx
0x14002caa6  call    cs:__imp_WdLogSingleEntry5
0x14002caad  nop     dword ptr [rax+rax+00h]
0x14002cab2  mov     edi, 799h
0x14002cab7  mov     cs:WdLogGlobalForLineNumber, edi
0x14002cabd  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14002cac4  nop     dword ptr [rax+rax+00h]
0x14002cac9  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002cad0  mov     [rax+18h], rcx
0x14002cad4  mov     ecx, cs:dword_14003E570
0x14002cada  mov     [rax+20h], rcx
0x14002cade  mov     rcx, rsi
0x14002cae1  mov     [rax+28h], r13
0x14002cae5  mov     cs:WdLogGlobalForLineNumber, edi
0x14002caeb  mov     rax, [rbx+2A0h]
0x14002caf2  mov     rdx, [rbx+9A0h]
0x14002caf9  call    _guard_dispatch_icall
0x14002cafe  jmp     loc_14002CD51
0x14002cb03  mov     ecx, [rbx+31Ch]
0x14002cb09  mov     r8, rbx
0x14002cb0c  mov     eax, [rbx+320h]
0x14002cb12  mov     rdx, rbp
0x14002cb15  mov     r9d, [rbx+310h]
0x14002cb1c  mov     [rsp+68h+var_40], rax
0x14002cb21  mov     [rsp+68h+pvBits], rcx
0x14002cb26  mov     ecx, 6
0x14002cb2b  call    cs:__imp_WdLogSingleEntry5
0x14002cb32  nop     dword ptr [rax+rax+00h]
0x14002cb37  mov     r14d, 7A3h
0x14002cb3d  mov     cs:WdLogGlobalForLineNumber, r14d
0x14002cb44  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14002cb4b  nop     dword ptr [rax+rax+00h]
0x14002cb50  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002cb57  mov     [rax+18h], rcx
0x14002cb5b  mov     ecx, cs:dword_14003E570
0x14002cb61  mov     [rax+20h], rcx
0x14002cb65  mov     rcx, rdi; pso
0x14002cb68  mov     [rax+28h], r13
0x14002cb6c  mov     cs:WdLogGlobalForLineNumber, r14d
0x14002cb73  call    cs:__imp_EngUnlockSurface
0x14002cb7a  nop     dword ptr [rax+rax+00h]
0x14002cb7f  jmp     short loc_14002CBEB
0x14002cb81  mov     ecx, [rbx+31Ch]
0x14002cb87  mov     r8, rbx
0x14002cb8a  mov     eax, [rbx+320h]
0x14002cb90  mov     rdx, rbp
0x14002cb93  mov     r9d, [rbx+310h]
0x14002cb9a  mov     [rsp+68h+var_40], rax
0x14002cb9f  mov     [rsp+68h+pvBits], rcx
0x14002cba4  mov     ecx, 6
0x14002cba9  call    cs:__imp_WdLogSingleEntry5
0x14002cbb0  nop     dword ptr [rax+rax+00h]
0x14002cbb5  mov     edi, 7ABh
0x14002cbba  mov     cs:WdLogGlobalForLineNumber, edi
0x14002cbc0  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14002cbc7  nop     dword ptr [rax+rax+00h]
0x14002cbcc  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002cbd3  mov     [rax+18h], rcx
0x14002cbd7  mov     ecx, cs:dword_14003E570
0x14002cbdd  mov     [rax+20h], rcx
0x14002cbe1  mov     [rax+28h], r13
0x14002cbe5  mov     cs:WdLogGlobalForLineNumber, edi
0x14002cbeb  mov     rcx, rbp; hsurf
0x14002cbee  call    cs:__imp_EngDeleteSurface
0x14002cbf5  nop     dword ptr [rax+rax+00h]
0x14002cbfa  jmp     loc_14002CC8C
0x14002cbff  mov     r8d, [rbx+310h]
0x14002cc06  mov     r9, r14
0x14002cc09  mov     eax, edi
0x14002cc0b  mov     rdx, rbx
0x14002cc0e  mov     [rsp+68h+var_40], rax
0x14002cc13  mov     ecx, 6
0x14002cc18  mov     [rsp+68h+pvBits], r15
0x14002cc1d  call    cs:__imp_WdLogSingleEntry5
0x14002cc24  nop     dword ptr [rax+rax+00h]
0x14002cc29  mov     edi, 7B3h
0x14002cc2e  jmp     short loc_14002CC5B
0x14002cc30  mov     eax, edi
0x14002cc32  mov     r9, r14
0x14002cc35  mov     [rsp+68h+var_40], rax
0x14002cc3a  mov     r8, rsi
0x14002cc3d  mov     rdx, rbx
0x14002cc40  mov     [rsp+68h+pvBits], r15
0x14002cc45  mov     ecx, 6
0x14002cc4a  call    cs:__imp_WdLogSingleEntry5
0x14002cc51  nop     dword ptr [rax+rax+00h]
0x14002cc56  mov     edi, 7B9h
0x14002cc5b  mov     cs:WdLogGlobalForLineNumber, edi
0x14002cc61  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14002cc68  nop     dword ptr [rax+rax+00h]
0x14002cc6d  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002cc74  mov     [rax+18h], rcx
0x14002cc78  mov     ecx, cs:dword_14003E570
0x14002cc7e  mov     [rax+20h], rcx
0x14002cc82  mov     [rax+28h], r13
0x14002cc86  mov     cs:WdLogGlobalForLineNumber, edi
0x14002cc8c  mov     rcx, rsi; hsurf
0x14002cc8f  call    cs:__imp_EngDeleteSurface
0x14002cc96  nop     dword ptr [rax+rax+00h]
0x14002cc9b  jmp     short loc_14002CCFD
  ... truncated ...
```
