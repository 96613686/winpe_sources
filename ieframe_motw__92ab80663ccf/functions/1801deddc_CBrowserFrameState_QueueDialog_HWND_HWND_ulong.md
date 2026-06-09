# CBrowserFrameState::QueueDialog(HWND__ *,HWND__ *,ulong)

- ea: `0x1801deddc`
- end: `0x1801df0e4`
- name: `?QueueDialog@CBrowserFrameState@@QEAAJPEAUHWND__@@0K@Z`
- size: `776`
- prototype: `__int64 __fastcall(CBrowserFrameState *__hidden this, HWND, HWND, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801ded00`

## callees

- `0x1801deb30`
- `0x1801deddc`
- `0x1801e0728`
- `0x1801e0c54`
- `0x1801e0f1c`
- `0x180421008`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801df0b2`
- `KERNEL32!CloseHandle` at `0x1801df0b2`
- `KERNEL32!GetCurrentThreadId` at `0x1801dee05`
- `KERNEL32!GetCurrentThreadId` at `0x1801dee39`
- `KERNEL32!GetCurrentThreadId` at `0x1801deea6`
- `KERNEL32!GetCurrentThreadId` at `0x1801df077`
- `KERNEL32!GetCurrentThreadId` at `0x1801dee05`
- `KERNEL32!GetCurrentThreadId` at `0x1801dee39`
- `KERNEL32!GetCurrentThreadId` at `0x1801deea6`
- `KERNEL32!GetCurrentThreadId` at `0x1801df077`
- `KERNEL32!LeaveCriticalSection` at `0x1801df041`
- `KERNEL32!LeaveCriticalSection` at `0x1801df041`
- `KERNEL32!EnterCriticalSection` at `0x1801defa7`
- `KERNEL32!EnterCriticalSection` at `0x1801defa7`
- `iertutil!__imp_DSA_Create` at `0x1801defc2`
- `iertutil!__imp_DSA_Create` at `0x1801defc2`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801df027`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801df027`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801deffc`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801deffc`
- `iertutil!__imp_DSA_InsertItem` at `0x1801defe3`
- `iertutil!__imp_DSA_InsertItem` at `0x1801defe3`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801deeb9`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801def8f`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801deeb9`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801def8f`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801deee8`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801deee8`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1801dee66`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1801dee66`

## pseudocode

```c
__int64 __fastcall CBrowserFrameState::QueueDialog(CBrowserFrameState *this, HWND a2, HWND a3, int a4)
{
  unsigned int v7; // edx
  int TrustSplitComponent; // edi
  int v9; // ebx
  unsigned int v10; // ecx
  int i; // r8d
  __int64 v12; // rbx
  _DWORD *v13; // rax
  CBrowserFrameState *v14; // rcx
  struct _DSA *v15; // rax
  int inserted; // eax
  int v17; // ebx
  struct CBrowserFrameState::TAB_DIALOG *ItemPtr; // rax
  DWORD CurrentThreadId; // eax
  int v20; // eax
  HANDLE hObject; // [rsp+30h] [rbp-50h] BYREF
  struct _IsoUntrustedComponent *v23; // [rsp+38h] [rbp-48h] BYREF
  HWND v24; // [rsp+40h] [rbp-40h] BYREF
  struct _IsoComponent *v25; // [rsp+48h] [rbp-38h] BYREF
  __int128 pitem; // [rsp+50h] [rbp-30h] BYREF
  __int128 v27; // [rsp+60h] [rbp-20h]
  __int64 v28; // [rsp+70h] [rbp-10h]
  HANDLE Handles; // [rsp+B8h] [rbp+38h] BYREF
  _DWORD *v30; // [rsp+C0h] [rbp+40h] BYREF
  int v31; // [rsp+C8h] [rbp+48h] BYREF

  DWORD2(v27) = a4;
  hObject = 0;
  v24 = 0;
  HIDWORD(v27) = GetCurrentThreadId();
  *(_QWORD *)&pitem = a2;
  *((_QWORD *)&pitem + 1) = a3;
  *(_QWORD *)&v27 = 0;
  if ( !dword_1806A733C )
  {
    EnterCriticalSection(&g_csDll);
    v15 = (struct _DSA *)*((_QWORD *)this + 9);
    if ( (v15 || (v15 = DSA_Create(40, 16), (*((_QWORD *)this + 9) = v15) != 0))
      && (inserted = DSA_InsertItem(v15, 0x7FFFFFFF, &pitem), v17 = inserted, inserted != -1) )
    {
      ItemPtr = (struct CBrowserFrameState::TAB_DIALOG *)DSA_GetItemPtr(*((HDSA *)this + 9), inserted);
      TrustSplitComponent = CBrowserFrameState::_QueueDialogCommon(this, ItemPtr, &v24, &hObject);
      if ( TrustSplitComponent < 0 )
        DSA_DeleteItem(*((HDSA *)this + 9), v17);
    }
    else
    {
      TrustSplitComponent = -2147024882;
    }
    LeaveCriticalSection(&g_csDll);
LABEL_31:
    if ( hObject )
    {
      Handles = hObject;
      TrustSplitComponent = _PumpWithMultipleEvents(&Handles, 1u, 0, 0);
      if ( TrustSplitComponent >= 0 )
      {
        v31 = 0;
        CurrentThreadId = GetCurrentThreadId();
        if ( (int)CBrowserFrameState::QueryDialogsDisabled(this, CurrentThreadId, &v31, (int *)&Handles, 0) >= 0 )
        {
          v20 = TrustSplitComponent;
          if ( v31 == 1 )
            v20 = -2147467260;
          TrustSplitComponent = v20;
        }
      }
      CloseHandle(hObject);
    }
    else if ( v24 )
    {
      return (unsigned int)CBrowserFrameState::_SetAssociatedWindowVisibility(v14, v24, 0);
    }
    return (unsigned int)TrustSplitComponent;
  }
  v25 = 0;
  v23 = 0;
  v31 = 0;
  if ( *((_DWORD *)this + 10) == GetCurrentThreadId() )
    v7 = 0;
  else
    v7 = 2;
  TrustSplitComponent = IsoGetTrustSplitComponent(*((_DWORD *)this + 5), v7, &v25, (unsigned int *)&v31, &v23);
  if ( TrustSplitComponent >= 0 )
  {
    if ( !*((_DWORD *)this + 6) )
    {
      if ( *((_DWORD *)v23 + 25) )
        *((_DWORD *)this + 6) = *((_DWORD *)v23 + 25);
      else
        TrustSplitComponent = CBrowserFrameState::_CreateSharedMemoryDialogs(
                                this,
                                (struct _IsoUntrustedComponent *)((char *)v23 + 64));
    }
    v9 = *((_DWORD *)this + 10);
    if ( v9 != GetCurrentThreadId() )
      IsoUnlockArtifact(v31);
    if ( TrustSplitComponent >= 0 )
    {
      v10 = *((_DWORD *)this + 6);
      if ( v10 )
      {
        v30 = 0;
        LODWORD(Handles) = 0;
        TrustSplitComponent = IsoLockSharedMemory(v10, (void **)&v30, (unsigned int *)&Handles);
        if ( TrustSplitComponent >= 0 )
        {
          if ( (unsigned int)Handles < 0x320 )
            return (unsigned int)-2147467260;
          TrustSplitComponent = -2147024882;
          for ( i = 0; i < 20; ++i )
          {
            v12 = 5LL * i;
            if ( !_InterlockedCompareExchange(&v30[10 * i + 7], SHIDWORD(v27), 0) )
            {
              v13 = v30;
              *(_OWORD *)&v30[10 * i] = pitem;
              *(_OWORD *)&v13[10 * i + 4] = v27;
              *(_QWORD *)&v13[10 * i + 8] = v28;
              v30[10 * i + 9] = i;
              TrustSplitComponent = CBrowserFrameState::_QueueDialogCommon(
                                      this,
                                      (struct CBrowserFrameState::TAB_DIALOG *)&v30[10 * i],
                                      &v24,
                                      &hObject);
              if ( TrustSplitComponent < 0 )
                v30[2 * v12 + 7] = 0;
              break;
            }
          }
          IsoUnlockArtifact(*((_DWORD *)this + 6));
          goto LABEL_31;
        }
      }
    }
  }
  return (unsigned int)TrustSplitComponent;
}

```

## disassembly

```asm
0x1801deddc  push    rbp
0x1801dedde  push    rbx
0x1801deddf  push    rsi
0x1801dede0  push    rdi
0x1801dede1  push    r14
0x1801dede3  mov     rbp, rsp
0x1801dede6  sub     rsp, 80h
0x1801deded  xor     r14d, r14d
0x1801dedf0  mov     dword ptr [rbp+var_20+8], r9d
0x1801dedf4  mov     [rbp+hObject], r14
0x1801dedf8  mov     rdi, r8
0x1801dedfb  mov     [rbp+var_40], r14
0x1801dedff  mov     rbx, rdx
0x1801dee02  mov     rsi, rcx
0x1801dee05  call    cs:__imp_GetCurrentThreadId
0x1801dee0c  nop     dword ptr [rax+rax+00h]
0x1801dee11  cmp     cs:dword_1806A733C, r14d
0x1801dee18  mov     dword ptr [rbp+var_20+0Ch], eax
0x1801dee1b  mov     qword ptr [rbp+pitem], rbx
0x1801dee1f  mov     qword ptr [rbp+pitem+8], rdi
0x1801dee23  mov     qword ptr [rbp+var_20], r14
0x1801dee27  jz      loc_1801DEFA0
0x1801dee2d  mov     [rbp+var_38], r14
0x1801dee31  mov     [rbp+var_48], r14
0x1801dee35  mov     [rbp+arg_18], r14d
0x1801dee39  call    cs:__imp_GetCurrentThreadId
0x1801dee40  nop     dword ptr [rax+rax+00h]
0x1801dee45  mov     ecx, [rsi+14h]
0x1801dee48  lea     r9, [rbp+arg_18]
0x1801dee4c  cmp     [rsi+28h], eax
0x1801dee4f  lea     r8, [rbp+var_38]
0x1801dee53  lea     rax, [rbp+var_48]
0x1801dee57  mov     qword ptr [rsp+80h+var_60], rax
0x1801dee5c  jz      short loc_1801DEE64
0x1801dee5e  lea     edx, [r14+2]
0x1801dee62  jmp     short loc_1801DEE66
0x1801dee64  xor     edx, edx
0x1801dee66  call    cs:__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z; IsoGetTrustSplitComponent(ulong,ulong,_IsoComponent * *,ulong *,_IsoUntrustedComponent * *)
0x1801dee6d  nop     dword ptr [rax+rax+00h]
0x1801dee72  mov     edi, eax
0x1801dee74  test    eax, eax
0x1801dee76  js      loc_1801DF0D3
0x1801dee7c  cmp     [rsi+18h], r14d
0x1801dee80  jnz     short loc_1801DEEA3
0x1801dee82  mov     rdx, [rbp+var_48]
0x1801dee86  add     rdx, 40h ; '@'; struct FRAME_SHAREDMEMORY *
0x1801dee8a  mov     eax, [rdx+24h]
0x1801dee8d  test    eax, eax
0x1801dee8f  jz      short loc_1801DEE99
0x1801dee91  mov     eax, [rdx+24h]
0x1801dee94  mov     [rsi+18h], eax
0x1801dee97  jmp     short loc_1801DEEA3
0x1801dee99  mov     rcx, rsi; this
0x1801dee9c  call    ?_CreateSharedMemoryDialogs@CBrowserFrameState@@AEAAJPEAUFRAME_SHAREDMEMORY@@@Z; CBrowserFrameState::_CreateSharedMemoryDialogs(FRAME_SHAREDMEMORY *)
0x1801deea1  mov     edi, eax
0x1801deea3  mov     ebx, [rsi+28h]
0x1801deea6  call    cs:__imp_GetCurrentThreadId
0x1801deead  nop     dword ptr [rax+rax+00h]
0x1801deeb2  cmp     ebx, eax
0x1801deeb4  jz      short loc_1801DEEC5
0x1801deeb6  mov     ecx, [rbp+arg_18]
0x1801deeb9  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1801deec0  nop     dword ptr [rax+rax+00h]
0x1801deec5  test    edi, edi
0x1801deec7  js      loc_1801DF0D3
0x1801deecd  mov     ecx, [rsi+18h]
0x1801deed0  test    ecx, ecx
0x1801deed2  jz      loc_1801DF0D3
0x1801deed8  lea     r8, [rbp+Handles]
0x1801deedc  mov     [rbp+arg_10], r14
0x1801deee0  lea     rdx, [rbp+arg_10]
0x1801deee4  mov     dword ptr [rbp+Handles], r14d
0x1801deee8  call    cs:__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z; IsoLockSharedMemory(ulong,void * *,ulong *)
0x1801deeef  nop     dword ptr [rax+rax+00h]
0x1801deef4  mov     edi, eax
0x1801deef6  test    eax, eax
0x1801deef8  js      loc_1801DF0D3
0x1801deefe  cmp     dword ptr [rbp+Handles], 320h
0x1801def05  jnb     short loc_1801DEF11
0x1801def07  mov     edi, 80004004h
0x1801def0c  jmp     loc_1801DF0D3
0x1801def11  mov     edi, 8007000Eh
0x1801def16  mov     r8d, r14d
0x1801def19  cmp     r8d, 14h
0x1801def1d  jge     short loc_1801DEF8C
0x1801def1f  mov     rdx, [rbp+arg_10]
0x1801def23  mov     ecx, dword ptr [rbp+var_20+0Ch]
0x1801def26  movsxd  rax, r8d
0x1801def29  lea     rbx, [rax+rax*4]
0x1801def2d  xor     eax, eax
0x1801def2f  lock cmpxchg [rdx+rbx*8+1Ch], ecx
0x1801def35  jz      short loc_1801DEF3C
0x1801def37  inc     r8d
0x1801def3a  jmp     short loc_1801DEF19
0x1801def3c  mov     rax, [rbp+arg_10]
0x1801def40  lea     r9, [rbp+hObject]; void **
0x1801def44  movups  xmm0, [rbp+pitem]
0x1801def48  mov     rcx, rsi; this
0x1801def4b  movups  xmmword ptr [rax+rbx*8], xmm0
0x1801def4f  movups  xmm1, [rbp+var_20]
0x1801def53  movups  xmmword ptr [rax+rbx*8+10h], xmm1
0x1801def58  movsd   xmm0, [rbp+var_10]
0x1801def5d  movsd   qword ptr [rax+rbx*8+20h], xmm0
0x1801def63  mov     rax, [rbp+arg_10]
0x1801def67  mov     [rax+rbx*8+24h], r8d
0x1801def6c  lea     r8, [rbp+var_40]; HWND *
0x1801def70  mov     rax, [rbp+arg_10]
0x1801def74  lea     rdx, [rax+rbx*8]; struct CBrowserFrameState::TAB_DIALOG *
0x1801def78  call    ?_QueueDialogCommon@CBrowserFrameState@@AEAAJPEAUTAB_DIALOG@1@PEAPEAUHWND__@@PEAPEAX@Z; CBrowserFrameState::_QueueDialogCommon(CBrowserFrameState::TAB_DIALOG *,HWND__ * *,void * *)
0x1801def7d  mov     edi, eax
0x1801def7f  test    eax, eax
0x1801def81  jns     short loc_1801DEF8C
0x1801def83  mov     rax, [rbp+arg_10]
0x1801def87  mov     [rax+rbx*8+1Ch], r14d
0x1801def8c  mov     ecx, [rsi+18h]
0x1801def8f  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1801def96  nop     dword ptr [rax+rax+00h]
0x1801def9b  jmp     loc_1801DF04D
0x1801defa0  lea     rcx, g_csDll; lpCriticalSection
0x1801defa7  call    cs:__imp_EnterCriticalSection
0x1801defae  nop     dword ptr [rax+rax+00h]
0x1801defb3  mov     rax, [rsi+48h]
0x1801defb7  test    rax, rax
0x1801defba  jnz     short loc_1801DEFD7
0x1801defbc  lea     edx, [rax+10h]; cItemGrow
0x1801defbf  lea     ecx, [rax+28h]; cbItem
0x1801defc2  call    cs:__imp_DSA_Create
0x1801defc9  nop     dword ptr [rax+rax+00h]
0x1801defce  mov     [rsi+48h], rax
0x1801defd2  test    rax, rax
0x1801defd5  jz      short loc_1801DF035
0x1801defd7  lea     r8, [rbp+pitem]; pitem
0x1801defdb  mov     edx, 7FFFFFFFh; i
0x1801defe0  mov     rcx, rax; hdsa
0x1801defe3  call    cs:__imp_DSA_InsertItem
0x1801defea  nop     dword ptr [rax+rax+00h]
0x1801defef  mov     ebx, eax
0x1801deff1  cmp     eax, 0FFFFFFFFh
0x1801deff4  jz      short loc_1801DF035
0x1801deff6  mov     rcx, [rsi+48h]; hdsa
0x1801deffa  mov     edx, eax; i
0x1801deffc  call    cs:__imp_DSA_GetItemPtr
0x1801df003  nop     dword ptr [rax+rax+00h]
0x1801df008  lea     r9, [rbp+hObject]; void **
0x1801df00c  mov     rcx, rsi; this
0x1801df00f  mov     rdx, rax; struct CBrowserFrameState::TAB_DIALOG *
0x1801df012  lea     r8, [rbp+var_40]; HWND *
0x1801df016  call    ?_QueueDialogCommon@CBrowserFrameState@@AEAAJPEAUTAB_DIALOG@1@PEAPEAUHWND__@@PEAPEAX@Z; CBrowserFrameState::_QueueDialogCommon(CBrowserFrameState::TAB_DIALOG *,HWND__ * *,void * *)
0x1801df01b  mov     edi, eax
0x1801df01d  test    eax, eax
0x1801df01f  jns     short loc_1801DF03A
0x1801df021  mov     rcx, [rsi+48h]; hdsa
0x1801df025  mov     edx, ebx; i
0x1801df027  call    cs:__imp_DSA_DeleteItem
0x1801df02e  nop     dword ptr [rax+rax+00h]
0x1801df033  jmp     short loc_1801DF03A
0x1801df035  mov     edi, 8007000Eh
0x1801df03a  lea     rcx, g_csDll; lpCriticalSection
0x1801df041  call    cs:__imp_LeaveCriticalSection
0x1801df048  nop     dword ptr [rax+rax+00h]
0x1801df04d  mov     rax, [rbp+hObject]
0x1801df051  test    rax, rax
0x1801df054  jz      short loc_1801DF0C0
0x1801df056  xor     r9d, r9d; unsigned int
0x1801df059  mov     [rbp+Handles], rax
0x1801df05d  xor     r8d, r8d; HWND
0x1801df060  lea     rcx, [rbp+Handles]; lpHandles
0x1801df064  lea     edx, [r9+1]; nCount
0x1801df068  call    ?_PumpWithMultipleEvents@@YAJPEAPEAXKPEAUHWND__@@I@Z; _PumpWithMultipleEvents(void * *,ulong,HWND__ *,uint)
0x1801df06d  mov     edi, eax
0x1801df06f  test    eax, eax
0x1801df071  js      short loc_1801DF0AE
0x1801df073  mov     [rbp+arg_18], r14d
0x1801df077  call    cs:__imp_GetCurrentThreadId
0x1801df07e  nop     dword ptr [rax+rax+00h]
0x1801df083  lea     r9, [rbp+Handles]; int *
0x1801df087  mov     [rsp+80h+var_60], r14d; int
0x1801df08c  mov     edx, eax; unsigned int
0x1801df08e  lea     r8, [rbp+arg_18]; int *
0x1801df092  mov     rcx, rsi; this
0x1801df095  call    ?QueryDialogsDisabled@CBrowserFrameState@@UEAAJKPEAH0H@Z; CBrowserFrameState::QueryDialogsDisabled(ulong,int *,int *,int)
0x1801df09a  test    eax, eax
0x1801df09c  js      short loc_1801DF0AE
0x1801df09e  cmp     [rbp+arg_18], 1
0x1801df0a2  mov     eax, edi
0x1801df0a4  mov     edi, 80004004h
0x1801df0a9  cmovz   eax, edi
0x1801df0ac  mov     edi, eax
0x1801df0ae  mov     rcx, [rbp+hObject]; hObject
0x1801df0b2  call    cs:__imp_CloseHandle
0x1801df0b9  nop     dword ptr [rax+rax+00h]
0x1801df0be  jmp     short loc_1801DF0D3
0x1801df0c0  mov     rdx, [rbp+var_40]; HWND
0x1801df0c4  test    rdx, rdx
0x1801df0c7  jz      short loc_1801DF0D3
0x1801df0c9  xor     r8d, r8d; int
0x1801df0cc  call    ?_SetAssociatedWindowVisibility@CBrowserFrameState@@AEAAJPEAUHWND__@@H@Z; CBrowserFrameState::_SetAssociatedWindowVisibility(HWND__ *,int)
0x1801df0d1  mov     edi, eax
0x1801df0d3  mov     eax, edi
0x1801df0d5  add     rsp, 80h
0x1801df0dc  pop     r14
0x1801df0de  pop     rdi
0x1801df0df  pop     rsi
0x1801df0e0  pop     rbx
0x1801df0e1  pop     rbp
0x1801df0e2  retn
```
