# CBrowserFrameState::QueueDialog(HWND__ *,HWND__ *,ulong)

- ea: `0x1801c7a08`
- end: `0x1801c7cb5`
- name: `?QueueDialog@CBrowserFrameState@@QEAAJPEAUHWND__@@0K@Z`
- size: `685`
- prototype: `__int64 __fastcall(CBrowserFrameState *__hidden this, HWND, HWND, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801c7940`

## callees

- `0x1801c77a0`
- `0x1801c7a08`
- `0x1801c9024`
- `0x1801c94b8`
- `0x1801c9730`
- `0x1803eb828`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801c7c8a`
- `KERNEL32!CloseHandle` at `0x1801c7c8a`
- `KERNEL32!GetCurrentThreadId` at `0x1801c7a31`
- `KERNEL32!GetCurrentThreadId` at `0x1801c7a5f`
- `KERNEL32!GetCurrentThreadId` at `0x1801c7ac0`
- `KERNEL32!GetCurrentThreadId` at `0x1801c7c55`
- `KERNEL32!GetCurrentThreadId` at `0x1801c7a31`
- `KERNEL32!GetCurrentThreadId` at `0x1801c7a5f`
- `KERNEL32!GetCurrentThreadId` at `0x1801c7ac0`
- `KERNEL32!GetCurrentThreadId` at `0x1801c7c55`
- `KERNEL32!LeaveCriticalSection` at `0x1801c7c25`
- `KERNEL32!LeaveCriticalSection` at `0x1801c7c25`
- `KERNEL32!EnterCriticalSection` at `0x1801c7ba9`
- `KERNEL32!EnterCriticalSection` at `0x1801c7ba9`
- `iertutil!__imp_DSA_Create` at `0x1801c7bbe`
- `iertutil!__imp_DSA_Create` at `0x1801c7bbe`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801c7c11`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801c7c11`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801c7bec`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801c7bec`
- `iertutil!__imp_DSA_InsertItem` at `0x1801c7bd9`
- `iertutil!__imp_DSA_InsertItem` at `0x1801c7bd9`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801c7acd`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801c7b97`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801c7acd`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801c7b97`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801c7af6`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801c7af6`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1801c7a86`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1801c7a86`

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
  if ( !dword_180663314 )
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
0x1801c7a08  push    rbp
0x1801c7a0a  push    rbx
0x1801c7a0b  push    rsi
0x1801c7a0c  push    rdi
0x1801c7a0d  push    r14
0x1801c7a0f  mov     rbp, rsp
0x1801c7a12  sub     rsp, 80h
0x1801c7a19  xor     r14d, r14d
0x1801c7a1c  mov     dword ptr [rbp+var_20+8], r9d
0x1801c7a20  mov     [rbp+hObject], r14
0x1801c7a24  mov     rdi, r8
0x1801c7a27  mov     [rbp+var_40], r14
0x1801c7a2b  mov     rbx, rdx
0x1801c7a2e  mov     rsi, rcx
0x1801c7a31  call    cs:__imp_GetCurrentThreadId
0x1801c7a37  cmp     cs:dword_180663314, r14d
0x1801c7a3e  mov     dword ptr [rbp+var_20+0Ch], eax
0x1801c7a41  mov     qword ptr [rbp+pitem], rbx
0x1801c7a45  mov     qword ptr [rbp+pitem+8], rdi
0x1801c7a49  mov     qword ptr [rbp+var_20], r14
0x1801c7a4d  jz      loc_1801C7BA2
0x1801c7a53  mov     [rbp+var_38], r14
0x1801c7a57  mov     [rbp+var_48], r14
0x1801c7a5b  mov     [rbp+arg_18], r14d
0x1801c7a5f  call    cs:__imp_GetCurrentThreadId
0x1801c7a65  mov     ecx, [rsi+14h]
0x1801c7a68  lea     r9, [rbp+arg_18]
0x1801c7a6c  cmp     [rsi+28h], eax
0x1801c7a6f  lea     r8, [rbp+var_38]
0x1801c7a73  lea     rax, [rbp+var_48]
0x1801c7a77  mov     qword ptr [rsp+80h+var_60], rax
0x1801c7a7c  jz      short loc_1801C7A84
0x1801c7a7e  lea     edx, [r14+2]
0x1801c7a82  jmp     short loc_1801C7A86
0x1801c7a84  xor     edx, edx
0x1801c7a86  call    cs:__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z; IsoGetTrustSplitComponent(ulong,ulong,_IsoComponent * *,ulong *,_IsoUntrustedComponent * *)
0x1801c7a8c  mov     edi, eax
0x1801c7a8e  test    eax, eax
0x1801c7a90  js      loc_1801C7CA5
0x1801c7a96  cmp     [rsi+18h], r14d
0x1801c7a9a  jnz     short loc_1801C7ABD
0x1801c7a9c  mov     rdx, [rbp+var_48]
0x1801c7aa0  add     rdx, 40h ; '@'; struct FRAME_SHAREDMEMORY *
0x1801c7aa4  mov     eax, [rdx+24h]
0x1801c7aa7  test    eax, eax
0x1801c7aa9  jz      short loc_1801C7AB3
0x1801c7aab  mov     eax, [rdx+24h]
0x1801c7aae  mov     [rsi+18h], eax
0x1801c7ab1  jmp     short loc_1801C7ABD
0x1801c7ab3  mov     rcx, rsi; this
0x1801c7ab6  call    ?_CreateSharedMemoryDialogs@CBrowserFrameState@@AEAAJPEAUFRAME_SHAREDMEMORY@@@Z; CBrowserFrameState::_CreateSharedMemoryDialogs(FRAME_SHAREDMEMORY *)
0x1801c7abb  mov     edi, eax
0x1801c7abd  mov     ebx, [rsi+28h]
0x1801c7ac0  call    cs:__imp_GetCurrentThreadId
0x1801c7ac6  cmp     ebx, eax
0x1801c7ac8  jz      short loc_1801C7AD3
0x1801c7aca  mov     ecx, [rbp+arg_18]
0x1801c7acd  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1801c7ad3  test    edi, edi
0x1801c7ad5  js      loc_1801C7CA5
0x1801c7adb  mov     ecx, [rsi+18h]
0x1801c7ade  test    ecx, ecx
0x1801c7ae0  jz      loc_1801C7CA5
0x1801c7ae6  lea     r8, [rbp+Handles]
0x1801c7aea  mov     [rbp+arg_10], r14
0x1801c7aee  lea     rdx, [rbp+arg_10]
0x1801c7af2  mov     dword ptr [rbp+Handles], r14d
0x1801c7af6  call    cs:__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z; IsoLockSharedMemory(ulong,void * *,ulong *)
0x1801c7afc  mov     edi, eax
0x1801c7afe  test    eax, eax
0x1801c7b00  js      loc_1801C7CA5
0x1801c7b06  cmp     dword ptr [rbp+Handles], 320h
0x1801c7b0d  jnb     short loc_1801C7B19
0x1801c7b0f  mov     edi, 80004004h
0x1801c7b14  jmp     loc_1801C7CA5
0x1801c7b19  mov     edi, 8007000Eh
0x1801c7b1e  mov     r8d, r14d
0x1801c7b21  cmp     r8d, 14h
0x1801c7b25  jge     short loc_1801C7B94
0x1801c7b27  mov     rdx, [rbp+arg_10]
0x1801c7b2b  mov     ecx, dword ptr [rbp+var_20+0Ch]
0x1801c7b2e  movsxd  rax, r8d
0x1801c7b31  lea     rbx, [rax+rax*4]
0x1801c7b35  xor     eax, eax
0x1801c7b37  lock cmpxchg [rdx+rbx*8+1Ch], ecx
0x1801c7b3d  jz      short loc_1801C7B44
0x1801c7b3f  inc     r8d
0x1801c7b42  jmp     short loc_1801C7B21
0x1801c7b44  mov     rax, [rbp+arg_10]
0x1801c7b48  lea     r9, [rbp+hObject]; void **
0x1801c7b4c  movups  xmm0, [rbp+pitem]
0x1801c7b50  mov     rcx, rsi; this
0x1801c7b53  movups  xmmword ptr [rax+rbx*8], xmm0
0x1801c7b57  movups  xmm1, [rbp+var_20]
0x1801c7b5b  movups  xmmword ptr [rax+rbx*8+10h], xmm1
0x1801c7b60  movsd   xmm0, [rbp+var_10]
0x1801c7b65  movsd   qword ptr [rax+rbx*8+20h], xmm0
0x1801c7b6b  mov     rax, [rbp+arg_10]
0x1801c7b6f  mov     [rax+rbx*8+24h], r8d
0x1801c7b74  lea     r8, [rbp+var_40]; HWND *
0x1801c7b78  mov     rax, [rbp+arg_10]
0x1801c7b7c  lea     rdx, [rax+rbx*8]; struct CBrowserFrameState::TAB_DIALOG *
0x1801c7b80  call    ?_QueueDialogCommon@CBrowserFrameState@@AEAAJPEAUTAB_DIALOG@1@PEAPEAUHWND__@@PEAPEAX@Z; CBrowserFrameState::_QueueDialogCommon(CBrowserFrameState::TAB_DIALOG *,HWND__ * *,void * *)
0x1801c7b85  mov     edi, eax
0x1801c7b87  test    eax, eax
0x1801c7b89  jns     short loc_1801C7B94
0x1801c7b8b  mov     rax, [rbp+arg_10]
0x1801c7b8f  mov     [rax+rbx*8+1Ch], r14d
0x1801c7b94  mov     ecx, [rsi+18h]
0x1801c7b97  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1801c7b9d  jmp     loc_1801C7C2B
0x1801c7ba2  lea     rcx, g_csDll; lpCriticalSection
0x1801c7ba9  call    cs:__imp_EnterCriticalSection
0x1801c7baf  mov     rax, [rsi+48h]
0x1801c7bb3  test    rax, rax
0x1801c7bb6  jnz     short loc_1801C7BCD
0x1801c7bb8  lea     edx, [rax+10h]; cItemGrow
0x1801c7bbb  lea     ecx, [rax+28h]; cbItem
0x1801c7bbe  call    cs:__imp_DSA_Create
0x1801c7bc4  mov     [rsi+48h], rax
0x1801c7bc8  test    rax, rax
0x1801c7bcb  jz      short loc_1801C7C19
0x1801c7bcd  lea     r8, [rbp+pitem]; pitem
0x1801c7bd1  mov     edx, 7FFFFFFFh; i
0x1801c7bd6  mov     rcx, rax; hdsa
0x1801c7bd9  call    cs:__imp_DSA_InsertItem
0x1801c7bdf  mov     ebx, eax
0x1801c7be1  cmp     eax, 0FFFFFFFFh
0x1801c7be4  jz      short loc_1801C7C19
0x1801c7be6  mov     rcx, [rsi+48h]; hdsa
0x1801c7bea  mov     edx, eax; i
0x1801c7bec  call    cs:__imp_DSA_GetItemPtr
0x1801c7bf2  lea     r9, [rbp+hObject]; void **
0x1801c7bf6  mov     rcx, rsi; this
0x1801c7bf9  mov     rdx, rax; struct CBrowserFrameState::TAB_DIALOG *
0x1801c7bfc  lea     r8, [rbp+var_40]; HWND *
0x1801c7c00  call    ?_QueueDialogCommon@CBrowserFrameState@@AEAAJPEAUTAB_DIALOG@1@PEAPEAUHWND__@@PEAPEAX@Z; CBrowserFrameState::_QueueDialogCommon(CBrowserFrameState::TAB_DIALOG *,HWND__ * *,void * *)
0x1801c7c05  mov     edi, eax
0x1801c7c07  test    eax, eax
0x1801c7c09  jns     short loc_1801C7C1E
0x1801c7c0b  mov     rcx, [rsi+48h]; hdsa
0x1801c7c0f  mov     edx, ebx; i
0x1801c7c11  call    cs:__imp_DSA_DeleteItem
0x1801c7c17  jmp     short loc_1801C7C1E
0x1801c7c19  mov     edi, 8007000Eh
0x1801c7c1e  lea     rcx, g_csDll; lpCriticalSection
0x1801c7c25  call    cs:__imp_LeaveCriticalSection
0x1801c7c2b  mov     rax, [rbp+hObject]
0x1801c7c2f  test    rax, rax
0x1801c7c32  jz      short loc_1801C7C92
0x1801c7c34  xor     r9d, r9d; unsigned int
0x1801c7c37  mov     [rbp+Handles], rax
0x1801c7c3b  xor     r8d, r8d; HWND
0x1801c7c3e  lea     rcx, [rbp+Handles]; lpHandles
0x1801c7c42  lea     edx, [r9+1]; nCount
0x1801c7c46  call    ?_PumpWithMultipleEvents@@YAJPEAPEAXKPEAUHWND__@@I@Z; _PumpWithMultipleEvents(void * *,ulong,HWND__ *,uint)
0x1801c7c4b  mov     edi, eax
0x1801c7c4d  test    eax, eax
0x1801c7c4f  js      short loc_1801C7C86
0x1801c7c51  mov     [rbp+arg_18], r14d
0x1801c7c55  call    cs:__imp_GetCurrentThreadId
0x1801c7c5b  lea     r9, [rbp+Handles]; int *
0x1801c7c5f  mov     [rsp+80h+var_60], r14d; int
0x1801c7c64  mov     edx, eax; unsigned int
0x1801c7c66  lea     r8, [rbp+arg_18]; int *
0x1801c7c6a  mov     rcx, rsi; this
0x1801c7c6d  call    ?QueryDialogsDisabled@CBrowserFrameState@@UEAAJKPEAH0H@Z; CBrowserFrameState::QueryDialogsDisabled(ulong,int *,int *,int)
0x1801c7c72  test    eax, eax
0x1801c7c74  js      short loc_1801C7C86
0x1801c7c76  cmp     [rbp+arg_18], 1
0x1801c7c7a  mov     eax, edi
0x1801c7c7c  mov     edi, 80004004h
0x1801c7c81  cmovz   eax, edi
0x1801c7c84  mov     edi, eax
0x1801c7c86  mov     rcx, [rbp+hObject]; hObject
0x1801c7c8a  call    cs:__imp_CloseHandle
0x1801c7c90  jmp     short loc_1801C7CA5
0x1801c7c92  mov     rdx, [rbp+var_40]; HWND
0x1801c7c96  test    rdx, rdx
0x1801c7c99  jz      short loc_1801C7CA5
0x1801c7c9b  xor     r8d, r8d; int
0x1801c7c9e  call    ?_SetAssociatedWindowVisibility@CBrowserFrameState@@AEAAJPEAUHWND__@@H@Z; CBrowserFrameState::_SetAssociatedWindowVisibility(HWND__ *,int)
0x1801c7ca3  mov     edi, eax
0x1801c7ca5  mov     eax, edi
0x1801c7ca7  add     rsp, 80h
0x1801c7cae  pop     r14
0x1801c7cb0  pop     rdi
0x1801c7cb1  pop     rsi
0x1801c7cb2  pop     rbx
0x1801c7cb3  pop     rbp
0x1801c7cb4  retn
```
