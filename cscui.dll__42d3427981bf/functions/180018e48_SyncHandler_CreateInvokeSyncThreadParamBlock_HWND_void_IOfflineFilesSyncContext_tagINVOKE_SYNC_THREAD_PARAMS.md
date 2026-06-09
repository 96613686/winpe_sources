# SyncHandler_CreateInvokeSyncThreadParamBlock(HWND__ *,void *,IOfflineFilesSyncContext *,tagINVOKE_SYNC_THREAD_PARAMS * *)

- ea: `0x180018e48`
- end: `0x1800190d8`
- name: `?SyncHandler_CreateInvokeSyncThreadParamBlock@@YAJPEAUHWND__@@PEAXPEAUIOfflineFilesSyncContext@@PEAPEAUtagINVOKE_SYNC_THREAD_PARAMS@@@Z`
- size: `656`
- prototype: `int(HWND, void *, struct IOfflineFilesSyncContext *, struct tagINVOKE_SYNC_THREAD_PARAMS **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019254`

## callees

- `0x180005190`
- `0x180006430`
- `0x180008b40`
- `0x18001101c`
- `0x180018e48`
- `0x1800190e0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018f56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018f5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018f56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018f5f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180018f8a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180018f8a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180018ed4`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180018ed4`

## pseudocode

```c
__int64 __fastcall SyncHandler_CreateInvokeSyncThreadParamBlock(
        HWND a1,
        void *a2,
        struct IOfflineFilesSyncContext *a3,
        struct tagINVOKE_SYNC_THREAD_PARAMS **a4)
{
  HRESULT Error; // edi
  __int64 (__fastcall **v9)(struct IOfflineFilesSyncContext *, GUID *, _QWORD *); // rax
  struct tagINVOKE_SYNC_THREAD_PARAMS *v10; // rsi
  unsigned int *v11; // r8
  HANDLE CurrentProcess; // rbx
  HANDLE v13; // rax
  UstCommon::CImpersonator *v14; // rcx
  __int64 v15; // rdx
  _QWORD v17[2]; // [rsp+40h] [rbp-20h] BYREF
  struct tagINVOKE_SYNC_THREAD_PARAMS *lpMem; // [rsp+50h] [rbp-10h] BYREF
  LPSTREAM ppstm; // [rsp+A8h] [rbp+48h] BYREF

  *a4 = 0;
  lpMem = 0;
  Error = CscUtil_HeapAlloc(0x18u, 1, (void **)&lpMem, a4);
  if ( Error >= 0 )
  {
    v9 = *(__int64 (__fastcall ***)(struct IOfflineFilesSyncContext *, GUID *, _QWORD *))a3;
    v17[0] = 0;
    Error = (*v9)(a3, &GUID_00000109_0000_0000_c000_000000000046, v17);
    if ( Error >= 0 )
    {
      ppstm = 0;
      Error = CreateStreamOnHGlobal(0, 1, &ppstm);
      if ( Error < 0 )
      {
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            89,
            WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids,
            (unsigned int)Error);
        }
        goto LABEL_25;
      }
      v17[1] = 0;
      Error = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
      if ( Error < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
          goto LABEL_21;
        }
        v15 = 88;
      }
      else
      {
        Error = (*(__int64 (__fastcall **)(_QWORD, LPSTREAM, _QWORD))(*(_QWORD *)v17[0] + 48LL))(v17[0], ppstm, 0);
        if ( Error >= 0 )
        {
          v10 = lpMem;
          v11 = (unsigned int *)((char *)lpMem + 16);
          *((_DWORD *)lpMem + 4) = 0;
          Error = MarshalToGIT((struct IUnknown *)ppstm, &GUID_0000000c_0000_0000_c000_000000000046, v11);
          if ( Error < 0 )
          {
            if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                86,
                WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids,
                (unsigned int)Error);
            }
            SyncHandler_DestroyInvokeSyncThreadParamBlock(v10);
          }
          else
          {
            CurrentProcess = GetCurrentProcess();
            v13 = GetCurrentProcess();
            if ( DuplicateHandle(v13, a2, CurrentProcess, (LPHANDLE)v10 + 1, 0, 0, 2u) )
            {
              *(_QWORD *)v10 = a1;
              *a4 = v10;
            }
            else
            {
              Error = ResultFromLastError();
            }
          }
          goto LABEL_21;
        }
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
LABEL_21:
          (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
LABEL_25:
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17[0] + 16LL))(v17[0]);
          return (unsigned int)Error;
        }
        v15 = 87;
      }
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids, (unsigned int)Error);
      goto LABEL_21;
    }
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids,
        (unsigned int)Error);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180018e48  mov     [rsp-28h+arg_0], rbx
0x180018e4d  mov     [rsp-28h+arg_8], rsi
0x180018e52  push    rbp
0x180018e53  push    rdi
0x180018e54  push    r12
0x180018e56  push    r14
0x180018e58  push    r15
0x180018e5a  mov     rbp, rsp
0x180018e5d  sub     rsp, 60h
0x180018e61  mov     esi, 1
0x180018e66  mov     qword ptr [r9], 0
0x180018e6d  mov     rbx, r8
0x180018e70  mov     [rbp+lpMem], 0
0x180018e78  mov     r12, rdx
0x180018e7b  lea     r8, [rbp+lpMem]; void **
0x180018e7f  mov     r15, rcx
0x180018e82  mov     edx, esi; int
0x180018e84  lea     ecx, [rsi+17h]; dwBytes
0x180018e87  mov     r14, r9
0x180018e8a  call    ?CscUtil_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; CscUtil_HeapAlloc(unsigned __int64,int,void * *,void *)
0x180018e8f  mov     edi, eax
0x180018e91  test    eax, eax
0x180018e93  js      loc_1800190BD
0x180018e99  mov     rax, [rbx]
0x180018e9c  lea     r8, [rbp+var_20]
0x180018ea0  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x180018ea7  mov     [rbp+var_20], 0
0x180018eaf  mov     rcx, rbx
0x180018eb2  mov     rax, [rax]
0x180018eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018eba  mov     edi, eax
0x180018ebc  test    eax, eax
0x180018ebe  js      loc_18001908C
0x180018ec4  lea     r8, [rbp+ppstm]; ppstm
0x180018ec8  mov     [rbp+ppstm], 0
0x180018ed0  mov     edx, esi; fDeleteOnRelease
0x180018ed2  xor     ecx, ecx; hGlobal
0x180018ed4  call    cs:__imp_CreateStreamOnHGlobal
0x180018eda  mov     edi, eax
0x180018edc  test    eax, eax
0x180018ede  js      loc_180019049
0x180018ee4  mov     rcx, [rbp+ppstm]
0x180018ee8  xor     r9d, r9d
0x180018eeb  mov     [rbp+var_18], 0
0x180018ef3  xor     r8d, r8d
0x180018ef6  mov     rdx, [rbp+var_18]
0x180018efa  mov     rax, [rcx]
0x180018efd  mov     rax, [rax+28h]
0x180018f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f06  mov     edi, eax
0x180018f08  test    eax, eax
0x180018f0a  js      loc_180019006
0x180018f10  mov     rcx, [rbp+var_20]
0x180018f14  xor     r8d, r8d
0x180018f17  mov     rdx, [rbp+ppstm]
0x180018f1b  mov     rax, [rcx]
0x180018f1e  mov     rax, [rax+30h]
0x180018f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f27  mov     edi, eax
0x180018f29  test    eax, eax
0x180018f2b  js      loc_180018FE6
0x180018f31  mov     rsi, [rbp+lpMem]
0x180018f35  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046; struct _GUID *
0x180018f3c  lea     r8, [rsi+10h]; unsigned int *
0x180018f40  mov     dword ptr [r8], 0
0x180018f47  mov     rcx, [rbp+ppstm]; struct IUnknown *
0x180018f4b  call    ?MarshalToGIT@@YAJPEAUIUnknown@@AEBU_GUID@@PEAK@Z; MarshalToGIT(IUnknown *,_GUID const &,ulong *)
0x180018f50  mov     edi, eax
0x180018f52  test    eax, eax
0x180018f54  js      short loc_180018FAB
0x180018f56  call    cs:__imp_GetCurrentProcess
0x180018f5c  mov     rbx, rax
0x180018f5f  call    cs:__imp_GetCurrentProcess
0x180018f65  mov     [rsp+60h+dwOptions], 2; dwOptions
0x180018f6d  lea     r9, [rsi+8]; lpTargetHandle
0x180018f71  mov     rcx, rax; hSourceProcessHandle
0x180018f74  mov     [rsp+60h+bInheritHandle], 0; bInheritHandle
0x180018f7c  mov     r8, rbx; hTargetProcessHandle
0x180018f7f  mov     [rsp+60h+dwDesiredAccess], 0; dwDesiredAccess
0x180018f87  mov     rdx, r12; hSourceHandle
0x180018f8a  call    cs:__imp_DuplicateHandle
0x180018f90  test    eax, eax
0x180018f92  jnz     short loc_180018FA0
0x180018f94  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180018f99  mov     edi, eax
0x180018f9b  jmp     loc_180019037
0x180018fa0  mov     [rsi], r15
0x180018fa3  mov     [r14], rsi
0x180018fa6  jmp     loc_180019037
0x180018fab  mov     rcx, cs:WPP_GLOBAL_Control
0x180018fb2  lea     rax, WPP_GLOBAL_Control
0x180018fb9  cmp     rcx, rax
0x180018fbc  jz      short loc_180018FDC
0x180018fbe  test    byte ptr [rcx+1Ch], 2
0x180018fc2  jz      short loc_180018FDC
0x180018fc4  mov     rcx, [rcx+10h]
0x180018fc8  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x180018fcf  mov     edx, 56h ; 'V'
0x180018fd4  mov     r9d, edi
0x180018fd7  call    WPP_SF_d
0x180018fdc  mov     rcx, rsi; lpMem
0x180018fdf  call    ?SyncHandler_DestroyInvokeSyncThreadParamBlock@@YAXPEAUtagINVOKE_SYNC_THREAD_PARAMS@@@Z; SyncHandler_DestroyInvokeSyncThreadParamBlock(tagINVOKE_SYNC_THREAD_PARAMS *)
0x180018fe4  jmp     short loc_180019037
0x180018fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180018fed  lea     rax, WPP_GLOBAL_Control
0x180018ff4  cmp     rcx, rax
0x180018ff7  jz      short loc_180019037
0x180018ff9  test    byte ptr [rcx+1Ch], 2
0x180018ffd  jz      short loc_180019037
0x180018fff  mov     edx, 57h ; 'W'
0x180019004  jmp     short loc_180019024
0x180019006  mov     rcx, cs:WPP_GLOBAL_Control
0x18001900d  lea     rax, WPP_GLOBAL_Control
0x180019014  cmp     rcx, rax
0x180019017  jz      short loc_180019037
0x180019019  test    byte ptr [rcx+1Ch], 2
0x18001901d  jz      short loc_180019037
0x18001901f  mov     edx, 58h ; 'X'
0x180019024  mov     rcx, [rcx+10h]
0x180019028  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x18001902f  mov     r9d, edi
0x180019032  call    WPP_SF_d
0x180019037  mov     rcx, [rbp+ppstm]
0x18001903b  mov     rax, [rcx]
0x18001903e  mov     rax, [rax+10h]
0x180019042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019047  jmp     short loc_18001907A
0x180019049  mov     rcx, cs:WPP_GLOBAL_Control
0x180019050  lea     rax, WPP_GLOBAL_Control
0x180019057  cmp     rcx, rax
0x18001905a  jz      short loc_18001907A
0x18001905c  test    byte ptr [rcx+1Ch], 2
0x180019060  jz      short loc_18001907A
0x180019062  mov     rcx, [rcx+10h]
0x180019066  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x18001906d  mov     edx, 59h ; 'Y'
0x180019072  mov     r9d, edi
0x180019075  call    WPP_SF_d
0x18001907a  mov     rcx, [rbp+var_20]
0x18001907e  mov     rax, [rcx]
0x180019081  mov     rax, [rax+10h]
0x180019085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001908a  jmp     short loc_1800190BD
0x18001908c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019093  lea     rax, WPP_GLOBAL_Control
0x18001909a  cmp     rcx, rax
0x18001909d  jz      short loc_1800190BD
0x18001909f  test    byte ptr [rcx+1Ch], 2
0x1800190a3  jz      short loc_1800190BD
0x1800190a5  mov     rcx, [rcx+10h]
0x1800190a9  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x1800190b0  mov     edx, 5Ah ; 'Z'
0x1800190b5  mov     r9d, edi
0x1800190b8  call    WPP_SF_d
0x1800190bd  lea     r11, [rsp+60h+var_s0]
0x1800190c2  mov     eax, edi
0x1800190c4  mov     rbx, [r11+30h]
0x1800190c8  mov     rsi, [r11+38h]
0x1800190cc  mov     rsp, r11
0x1800190cf  pop     r15
0x1800190d1  pop     r14
0x1800190d3  pop     r12
0x1800190d5  pop     rdi
0x1800190d6  pop     rbp
0x1800190d7  retn
```
