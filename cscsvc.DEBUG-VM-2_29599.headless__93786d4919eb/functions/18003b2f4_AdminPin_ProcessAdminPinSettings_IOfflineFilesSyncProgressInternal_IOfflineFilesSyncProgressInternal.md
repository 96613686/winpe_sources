# AdminPin_ProcessAdminPinSettings(IOfflineFilesSyncProgressInternal *,IOfflineFilesSyncProgressInternal *)

- ea: `0x18003b2f4`
- end: `0x18003b56c`
- name: `?AdminPin_ProcessAdminPinSettings@@YAJPEAUIOfflineFilesSyncProgressInternal@@0@Z`
- size: `632`
- prototype: `__int64 __fastcall(struct IOfflineFilesSyncProgressInternal *, struct IOfflineFilesSyncProgressInternal *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180061a00`

## callees

- `0x18000d640`
- `0x18002a8ac`
- `0x18002f10c`
- `0x180036394`
- `0x18003af88`
- `0x18003b130`
- `0x18003b2f4`
- `0x18003b574`
- `0x18003b89c`
- `0x18003baa0`
- `0x18003c410`
- `0x18003c460`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b4b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b4b6`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18003b3a0`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18003b3a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003b397`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003b397`

## pseudocode

```c
__int64 __fastcall AdminPin_ProcessAdminPinSettings(
        struct IOfflineFilesSyncProgressInternal *a1,
        struct IOfflineFilesSyncProgressInternal *a2)
{
  int PinAndUnpinLists; // ebx
  CObjectMonitor *v5; // rcx
  HANDLE CurrentThread; // rax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  void *v10; // rdx
  void *v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r9
  void *lpMem[2]; // [rsp+20h] [rbp-30h] BYREF
  int v16; // [rsp+30h] [rbp-20h]
  void *v17[2]; // [rsp+38h] [rbp-18h] BYREF
  int v18; // [rsp+48h] [rbp-8h]
  unsigned int ThreadPriority; // [rsp+90h] [rbp+40h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_a1ce3912c7ac35ae7cdf5f45266f18c1_Traceguids);
  }
  ThreadPriority = 0;
  PinAndUnpinLists = AdminPin_QuerySetting(L"DisableAdminPinning", &ThreadPriority);
  if ( PinAndUnpinLists >= 0 && ThreadPriority )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
      return (unsigned int)PinAndUnpinLists;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_a1ce3912c7ac35ae7cdf5f45266f18c1_Traceguids);
LABEL_33:
      v5 = WPP_GLOBAL_Control;
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  if ( ThreadPriority == 0x7FFFFFFF && (PinAndUnpinLists = ResultFromLastError(), PinAndUnpinLists < 0)
    || (PinAndUnpinLists = CThreadPriority::_Set((CThreadPriority *)&ThreadPriority, -1), PinAndUnpinLists < 0) )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 59;
      v13 = (unsigned int)PinAndUnpinLists;
      goto LABEL_29;
    }
  }
  else
  {
    hObject = 0;
    v7 = CscSec_OpenThreadTokenForAccessCheckAndImpersonation(&hObject);
    PinAndUnpinLists = v7;
    if ( v7 >= 0 )
    {
      v17[0] = 0;
      v18 = 4;
      v16 = 4;
      v17[1] = 0;
      lpMem[0] = 0;
      lpMem[1] = 0;
      PinAndUnpinLists = AdminPin_LoadPinAndUnpinLists(hObject);
      if ( PinAndUnpinLists >= 0 )
      {
        v8 = AdminPin_ProcessUnpinList(lpMem, a2);
        if ( v8 < 0
          && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            WPP_a1ce3912c7ac35ae7cdf5f45266f18c1_Traceguids,
            (unsigned int)v8);
        }
        v9 = AdminPin_ProcessPinList(v17, a1);
        PinAndUnpinLists = v9;
        if ( v9 < 0
          && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            WPP_a1ce3912c7ac35ae7cdf5f45266f18c1_Traceguids,
            (unsigned int)v9);
        }
      }
      AdminPin_DestroyDPAContents(v17);
      AdminPin_DestroyDPAContents(lpMem);
      CloseHandle(hObject);
      CscUtil_HeapFree(lpMem[0], v10);
      CscUtil_HeapFree(v17[0], v11);
      goto LABEL_30;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 58;
      v13 = (unsigned int)v7;
LABEL_29:
      WPP_SF_d(*((_QWORD *)v5 + 2), v12, WPP_a1ce3912c7ac35ae7cdf5f45266f18c1_Traceguids, v13);
LABEL_30:
      v5 = WPP_GLOBAL_Control;
    }
  }
  if ( ThreadPriority != 0x7FFFFFFF )
  {
    CThreadPriority::_Set((CThreadPriority *)&ThreadPriority, ThreadPriority);
    goto LABEL_33;
  }
LABEL_34:
  if ( v5 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x2000000) != 0 )
    WPP_SF_d(*((_QWORD *)v5 + 2), 61, WPP_a1ce3912c7ac35ae7cdf5f45266f18c1_Traceguids, (unsigned int)PinAndUnpinLists);
  return (unsigned int)PinAndUnpinLists;
}

```

## disassembly

```asm
0x18003b2f4  mov     [rsp-28h+arg_0], rbx
0x18003b2f9  push    rbp
0x18003b2fa  push    rsi
0x18003b2fb  push    rdi
0x18003b2fc  push    r12
0x18003b2fe  push    r15
0x18003b300  mov     rbp, rsp
0x18003b303  sub     rsp, 50h
0x18003b307  mov     rdi, rdx
0x18003b30a  mov     rsi, rcx
0x18003b30d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b314  lea     r15, WPP_GLOBAL_Control
0x18003b31b  lea     r12, WPP_a1ce3912c7ac35ae7cdf5f45266f18c1_Traceguids
0x18003b322  cmp     rcx, r15
0x18003b325  jz      short loc_18003B341
0x18003b327  test    dword ptr [rcx+1Ch], 2000000h
0x18003b32e  jz      short loc_18003B341
0x18003b330  mov     rcx, [rcx+10h]
0x18003b334  mov     edx, 37h ; '7'
0x18003b339  mov     r8, r12
0x18003b33c  call    WPP_SF_
0x18003b341  lea     rdx, [rbp+arg_10]; unsigned int *
0x18003b345  mov     [rbp+arg_10], 0
0x18003b34c  lea     rcx, REGSTR_VAL_DISABLEADMINPINNING; "DisableAdminPinning"
0x18003b353  call    ?AdminPin_QuerySetting@@YAJPEBGPEAK@Z; AdminPin_QuerySetting(ushort const *,ulong *)
0x18003b358  mov     ebx, eax
0x18003b35a  test    eax, eax
0x18003b35c  js      short loc_18003B397
0x18003b35e  cmp     [rbp+arg_10], 0
0x18003b362  jz      short loc_18003B397
0x18003b364  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b36b  cmp     rcx, r15
0x18003b36e  jz      loc_18003B556
0x18003b374  test    dword ptr [rcx+1Ch], 2000000h
0x18003b37b  jz      loc_18003B534
0x18003b381  mov     rcx, [rcx+10h]
0x18003b385  mov     edx, 3Ch ; '<'
0x18003b38a  mov     r8, r12
0x18003b38d  call    WPP_SF_
0x18003b392  jmp     loc_18003B52D
0x18003b397  call    cs:__imp_GetCurrentThread
0x18003b39d  mov     rcx, rax; hThread
0x18003b3a0  call    cs:__imp_GetThreadPriority
0x18003b3a6  mov     [rbp+arg_10], eax
0x18003b3a9  cmp     eax, 7FFFFFFFh
0x18003b3ae  jnz     short loc_18003B3BF
0x18003b3b0  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18003b3b5  mov     ebx, eax
0x18003b3b7  test    eax, eax
0x18003b3b9  js      loc_18003B4EC
0x18003b3bf  or      edx, 0FFFFFFFFh; int
0x18003b3c2  lea     rcx, [rbp+arg_10]; this
0x18003b3c6  call    ?_Set@CThreadPriority@@AEAAJH@Z; CThreadPriority::_Set(int)
0x18003b3cb  mov     ebx, eax
0x18003b3cd  test    eax, eax
0x18003b3cf  js      loc_18003B4EC
0x18003b3d5  lea     rcx, [rbp+hObject]; TokenHandle
0x18003b3d9  mov     [rbp+hObject], 0
0x18003b3e1  call    ?CscSec_OpenThreadTokenForAccessCheckAndImpersonation@@YAJPEAPEAX@Z; CscSec_OpenThreadTokenForAccessCheckAndImpersonation(void * *)
0x18003b3e6  mov     ebx, eax
0x18003b3e8  test    eax, eax
0x18003b3ea  js      loc_18003B4D0
0x18003b3f0  mov     rcx, [rbp+hObject]; hToken
0x18003b3f4  lea     r8, [rbp+lpMem]
0x18003b3f8  mov     eax, 4
0x18003b3fd  mov     [rbp+var_18], 0
0x18003b405  lea     rdx, [rbp+var_18]
0x18003b409  mov     [rbp+var_8], eax
0x18003b40c  mov     [rbp+var_20], eax
0x18003b40f  mov     [rbp+var_10], 0
0x18003b417  mov     [rbp+lpMem], 0
0x18003b41f  mov     [rbp+var_28], 0
0x18003b427  call    ?AdminPin_LoadPinAndUnpinLists@@YAJPEAXAEAV?$CDpa@UtagADMINPIN_ITEM_INFO@@@@1@Z; AdminPin_LoadPinAndUnpinLists(void *,CDpa<tagADMINPIN_ITEM_INFO> &,CDpa<tagADMINPIN_ITEM_INFO> &)
0x18003b42c  mov     ebx, eax
0x18003b42e  test    eax, eax
0x18003b430  js      short loc_18003B4A0
0x18003b432  mov     rdx, rdi
0x18003b435  lea     rcx, [rbp+lpMem]
0x18003b439  call    ?AdminPin_ProcessUnpinList@@YAJAEAV?$CDpa@UtagADMINPIN_ITEM_INFO@@@@PEAUIOfflineFilesSyncProgressInternal@@@Z; AdminPin_ProcessUnpinList(CDpa<tagADMINPIN_ITEM_INFO> &,IOfflineFilesSyncProgressInternal *)
0x18003b43e  test    eax, eax
0x18003b440  jns     short loc_18003B468
0x18003b442  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b449  cmp     rcx, r15
0x18003b44c  jz      short loc_18003B468
0x18003b44e  test    byte ptr [rcx+1Ch], 2
0x18003b452  jz      short loc_18003B468
0x18003b454  mov     rcx, [rcx+10h]
0x18003b458  mov     edx, 38h ; '8'
0x18003b45d  mov     r9d, eax
0x18003b460  mov     r8, r12
0x18003b463  call    WPP_SF_d
0x18003b468  mov     rdx, rsi
0x18003b46b  lea     rcx, [rbp+var_18]
0x18003b46f  call    ?AdminPin_ProcessPinList@@YAJAEAV?$CDpa@UtagADMINPIN_ITEM_INFO@@@@PEAUIOfflineFilesSyncProgressInternal@@@Z; AdminPin_ProcessPinList(CDpa<tagADMINPIN_ITEM_INFO> &,IOfflineFilesSyncProgressInternal *)
0x18003b474  mov     ebx, eax
0x18003b476  test    eax, eax
0x18003b478  jns     short loc_18003B4A0
0x18003b47a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b481  cmp     rcx, r15
0x18003b484  jz      short loc_18003B4A0
0x18003b486  test    byte ptr [rcx+1Ch], 2
0x18003b48a  jz      short loc_18003B4A0
0x18003b48c  mov     rcx, [rcx+10h]
0x18003b490  mov     edx, 39h ; '9'
0x18003b495  mov     r9d, eax
0x18003b498  mov     r8, r12
0x18003b49b  call    WPP_SF_d
0x18003b4a0  lea     rcx, [rbp+var_18]
0x18003b4a4  call    ?AdminPin_DestroyDPAContents@@YAXAEAV?$CDpa@UtagADMINPIN_ITEM_INFO@@@@@Z; AdminPin_DestroyDPAContents(CDpa<tagADMINPIN_ITEM_INFO> &)
0x18003b4a9  lea     rcx, [rbp+lpMem]
0x18003b4ad  call    ?AdminPin_DestroyDPAContents@@YAXAEAV?$CDpa@UtagADMINPIN_ITEM_INFO@@@@@Z; AdminPin_DestroyDPAContents(CDpa<tagADMINPIN_ITEM_INFO> &)
0x18003b4b2  mov     rcx, [rbp+hObject]; hObject
0x18003b4b6  call    cs:__imp_CloseHandle
0x18003b4bc  mov     rcx, [rbp+lpMem]; lpMem
0x18003b4c0  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18003b4c5  mov     rcx, [rbp+var_18]; lpMem
0x18003b4c9  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18003b4ce  jmp     short loc_18003B512
0x18003b4d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b4d7  cmp     rcx, r15
0x18003b4da  jz      short loc_18003B519
0x18003b4dc  test    byte ptr [rcx+1Ch], 2
0x18003b4e0  jz      short loc_18003B519
0x18003b4e2  mov     edx, 3Ah ; ':'
0x18003b4e7  mov     r9d, eax
0x18003b4ea  jmp     short loc_18003B506
0x18003b4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b4f3  cmp     rcx, r15
0x18003b4f6  jz      short loc_18003B519
0x18003b4f8  test    byte ptr [rcx+1Ch], 2
0x18003b4fc  jz      short loc_18003B519
0x18003b4fe  mov     edx, 3Bh ; ';'
0x18003b503  mov     r9d, ebx
0x18003b506  mov     rcx, [rcx+10h]
0x18003b50a  mov     r8, r12
0x18003b50d  call    WPP_SF_d
0x18003b512  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b519  mov     edx, [rbp+arg_10]; int
0x18003b51c  cmp     edx, 7FFFFFFFh
0x18003b522  jz      short loc_18003B534
0x18003b524  lea     rcx, [rbp+arg_10]; this
0x18003b528  call    ?_Set@CThreadPriority@@AEAAJH@Z; CThreadPriority::_Set(int)
0x18003b52d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b534  cmp     rcx, r15
0x18003b537  jz      short loc_18003B556
0x18003b539  test    dword ptr [rcx+1Ch], 2000000h
0x18003b540  jz      short loc_18003B556
0x18003b542  mov     rcx, [rcx+10h]
0x18003b546  mov     edx, 3Dh ; '='
0x18003b54b  mov     r9d, ebx
0x18003b54e  mov     r8, r12
0x18003b551  call    WPP_SF_d
0x18003b556  mov     eax, ebx
0x18003b558  mov     rbx, [rsp+50h+arg_0]
0x18003b560  add     rsp, 50h
0x18003b564  pop     r15
0x18003b566  pop     r12
0x18003b568  pop     rdi
0x18003b569  pop     rsi
0x18003b56a  pop     rbp
0x18003b56b  retn
```
