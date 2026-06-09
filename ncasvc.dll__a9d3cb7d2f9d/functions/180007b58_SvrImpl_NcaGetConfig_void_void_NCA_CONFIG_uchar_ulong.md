# SvrImpl_NcaGetConfig(void *,void *,NCA_CONFIG_,uchar *,ulong *)

- ea: `0x180007b58`
- end: `0x180007f09`
- name: `?SvrImpl_NcaGetConfig@@YAKPEAX0W4NCA_CONFIG_@@PEAEPEAK@Z`
- size: `945`
- prototype: `__int64 __fastcall(__int64, struct NCA_INTSERVER_ENGINE_HANDLE_ *, unsigned int, _DWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b530`

## callees

- `0x180003770`
- `0x1800043bc`
- `0x180004f04`
- `0x180004f34`
- `0x180006544`
- `0x1800065c8`
- `0x180006664`
- `0x18000673c`
- `0x180007088`
- `0x180007b58`
- `0x180019100`
- `0x180019784`
- `0x18001cc32`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d1c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007d61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007d61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007cff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007cff`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180007bee`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180007bee`

## string_xrefs

- `0x180007bc1`: `NcaGetConfig`
- `0x180007ee2`: `NcaGetConfig`

## pseudocode

```c
__int64 __fastcall SvrImpl_NcaGetConfig(
        __int64 a1,
        struct NCA_INTSERVER_ENGINE_HANDLE_ *a2,
        unsigned int a3,
        _DWORD *a4,
        unsigned int *a5)
{
  void *v6; // rbp
  PVOID v9; // rcx
  DWORD v10; // eax
  struct _tag_NCA_CANCELABLE_LOCK *v11; // rcx
  unsigned int IsEngineValid; // ebx
  unsigned int v13; // eax
  struct _tag_NCA_CANCELABLE_LOCK *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned int *v17; // rdi
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // edx
  unsigned int String; // eax
  unsigned int v23; // esi
  __int64 v24; // rsi
  PVOID v25; // rcx
  void *Src; // [rsp+70h] [rbp+8h] BYREF

  v6 = 0;
  Src = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v9, ApiActivityStart, L"NcaGetConfig");
  _InterlockedAdd(&dword_180028AE8, 1u);
  v10 = WaitForMultipleObjects(2u, &gNcaMain, 0, 0xFFFFFFFF);
  if ( v10 )
  {
    if ( v10 != 1 )
      goto LABEL_9;
    if ( a3 == 1 )
    {
      v13 = NcaHResultToWindowsError(2147500033LL);
      IsEngineValid = v13;
      v14 = (struct _tag_NCA_CANCELABLE_LOCK *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 63;
        v16 = v13;
LABEL_16:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, v16);
        goto LABEL_56;
      }
      goto LABEL_56;
    }
    v17 = a5;
    if ( !a5 )
    {
      IsEngineValid = 87;
      v14 = (struct _tag_NCA_CANCELABLE_LOCK *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_57;
      v18 = (unsigned int)((_DWORD)a5 + 64);
      goto LABEL_21;
    }
    if ( !a4 && *a5 )
    {
      IsEngineValid = 87;
      v14 = (struct _tag_NCA_CANCELABLE_LOCK *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_57;
      v18 = 65;
LABEL_21:
      WPP_SF_d(*((_QWORD *)v14 + 2), v18, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, 87);
      goto LABEL_57;
    }
    EnterCriticalSection(&gNcaApiSrvImpl);
    IsEngineValid = NcaApiSrvImplIsEngineValid(a2);
    LeaveCriticalSection(&gNcaApiSrvImpl);
    if ( IsEngineValid )
    {
      v14 = (struct _tag_NCA_CANCELABLE_LOCK *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 66;
        v16 = IsEngineValid;
        goto LABEL_16;
      }
LABEL_56:
      if ( IsEngineValid == 1115 )
        goto LABEL_58;
LABEL_57:
      NcaReleaseCancelableLock(v14);
      goto LABEL_58;
    }
    AcquireSRWLockShared(&SRWLock);
    if ( a3 == 7 || a3 == 2 )
    {
      String = NcaConfigMgrGetString(a3, (__int64)&Src);
      IsEngineValid = String;
      if ( String )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, String);
        v6 = Src;
        goto LABEL_55;
      }
      v6 = Src;
      v23 = 0;
      if ( !Src )
        goto LABEL_54;
      v24 = -1;
      do
        ++v24;
      while ( *((_WORD *)Src + v24) );
      v23 = 2 * v24 + 2;
      if ( *v17 >= v23 )
      {
LABEL_54:
        memcpy_0(a4, Src, v23);
        *v17 = v23;
        goto LABEL_55;
      }
      *v17 = v23;
      IsEngineValid = 234;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_55;
      v20 = 68;
    }
    else
    {
      if ( a3 - 3 > 3 && a3 != 8 )
      {
        IsEngineValid = 87;
LABEL_55:
        NcaExcludeShareLockLeave(1, &SRWLock);
        goto LABEL_56;
      }
      if ( *v17 >= 4 )
      {
        *a4 = NcaConfigMgrGetBool(a3);
        *v17 = v21;
        goto LABEL_55;
      }
      *v17 = 4;
      IsEngineValid = 234;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_55;
      v20 = 69;
    }
    WPP_SF_d(v19[2], v20, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, 234);
    goto LABEL_55;
  }
  NcaReleaseCancelableLock(v11);
LABEL_9:
  IsEngineValid = 1115;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, 1115);
LABEL_58:
  NcaFree(v6);
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, IsEngineValid);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0zx_EventWriteTransfer(v25, ApiActivityEnd, L"NcaGetConfig", IsEngineValid);
  return IsEngineValid;
}

```

## disassembly

```asm
0x180007b58  mov     [rsp+Src], rcx
0x180007b5d  push    rbx
0x180007b5e  push    rbp
0x180007b5f  push    rsi
0x180007b60  push    rdi
0x180007b61  push    r12
0x180007b63  push    r13
0x180007b65  push    r14
0x180007b67  push    r15
0x180007b69  sub     rsp, 28h
0x180007b6d  xor     r12d, r12d
0x180007b70  mov     r14, r9
0x180007b73  mov     ebp, r12d
0x180007b76  mov     [rsp+68h+Src], r12
0x180007b7b  mov     esi, r8d
0x180007b7e  mov     rbx, rdx
0x180007b81  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b88  lea     r13, WPP_GLOBAL_Control
0x180007b8f  lea     rdi, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x180007b96  cmp     rcx, r13
0x180007b99  jz      short loc_180007BB2
0x180007b9b  test    byte ptr [rcx+1Ch], 8
0x180007b9f  jz      short loc_180007BB2
0x180007ba1  mov     rcx, [rcx+10h]
0x180007ba5  lea     edx, [r12+3Dh]
0x180007baa  mov     r8, rdi
0x180007bad  call    WPP_SF_
0x180007bb2  mov     r15d, 1
0x180007bb8  test    cs:Microsoft_Windows_NcasvcEnableBits, r15b
0x180007bbf  jz      short loc_180007BD4
0x180007bc1  lea     r8, aNcagetconfig; "NcaGetConfig"
0x180007bc8  lea     rdx, ApiActivityStart
0x180007bcf  call    McTemplateU0z_EventWriteTransfer
0x180007bd4  lock add cs:dword_180028AE8, r15d
0x180007bdc  xor     r8d, r8d; bWaitAll
0x180007bdf  lea     rdx, ?gNcaMain@@3UNCA_MAIN_COMPONENT_@@A; lpHandles
0x180007be6  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180007bea  lea     ecx, [r8+2]; nCount
0x180007bee  call    cs:__imp_WaitForMultipleObjects
0x180007bf5  nop     dword ptr [rax+rax+00h]
0x180007bfa  test    eax, eax
0x180007bfc  jnz     short loc_180007C05
0x180007bfe  call    ?NcaReleaseCancelableLock@@YAXPEAU_tag_NCA_CANCELABLE_LOCK@@@Z; NcaReleaseCancelableLock(_tag_NCA_CANCELABLE_LOCK *)
0x180007c03  jmp     short loc_180007C0A
0x180007c05  cmp     eax, r15d
0x180007c08  jz      short loc_180007C42
0x180007c0a  mov     ebx, 45Bh
0x180007c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c16  cmp     rcx, r13
0x180007c19  jz      loc_180007EA4
0x180007c1f  test    [rcx+1Ch], r15b
0x180007c23  jz      loc_180007EA4
0x180007c29  mov     rcx, [rcx+10h]
0x180007c2d  mov     edx, 3Eh ; '>'
0x180007c32  mov     r9d, ebx
0x180007c35  mov     r8, rdi
0x180007c38  call    WPP_SF_d
0x180007c3d  jmp     loc_180007EA4
0x180007c42  cmp     esi, r15d
0x180007c45  jnz     short loc_180007C86
0x180007c47  mov     ecx, 80004001h
0x180007c4c  call    NcaHResultToWindowsError
0x180007c51  mov     ebx, eax
0x180007c53  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c5a  cmp     rcx, r13
0x180007c5d  jz      loc_180007E97
0x180007c63  test    [rcx+1Ch], r15b
0x180007c67  jz      loc_180007E97
0x180007c6d  mov     edx, 3Fh ; '?'
0x180007c72  mov     r9d, eax
0x180007c75  mov     r8, rdi
0x180007c78  mov     rcx, [rcx+10h]
0x180007c7c  call    WPP_SF_d
0x180007c81  jmp     loc_180007E97
0x180007c86  mov     rdi, [rsp+68h+arg_20]
0x180007c8e  test    rdi, rdi
0x180007c91  jnz     short loc_180007CCB
0x180007c93  lea     ebx, [rdi+57h]
0x180007c96  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c9d  cmp     rcx, r13
0x180007ca0  jz      loc_180007E9F
0x180007ca6  test    [rcx+1Ch], r15b
0x180007caa  jz      loc_180007E9F
0x180007cb0  lea     edx, [rdi+40h]
0x180007cb3  mov     rcx, [rcx+10h]
0x180007cb7  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x180007cbe  mov     r9d, ebx
0x180007cc1  call    WPP_SF_d
0x180007cc6  jmp     loc_180007E9F
0x180007ccb  test    r14, r14
0x180007cce  jnz     short loc_180007CF8
0x180007cd0  cmp     [rdi], r12d
0x180007cd3  jz      short loc_180007CF8
0x180007cd5  lea     ebx, [r14+57h]
0x180007cd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ce0  cmp     rcx, r13
0x180007ce3  jz      loc_180007E9F
0x180007ce9  test    [rcx+1Ch], r15b
0x180007ced  jz      loc_180007E9F
0x180007cf3  lea     edx, [rbx-16h]
0x180007cf6  jmp     short loc_180007CB3
0x180007cf8  lea     rcx, ?gNcaApiSrvImpl@@3UNCA_API_SRV_IMPL_COMPONENT_@@A; lpCriticalSection
0x180007cff  call    cs:__imp_EnterCriticalSection
0x180007d06  nop     dword ptr [rax+rax+00h]
0x180007d0b  mov     rcx, rbx; struct NCA_INTSERVER_ENGINE_HANDLE_ *
0x180007d0e  call    ?NcaApiSrvImplIsEngineValid@@YAKPEAUNCA_INTSERVER_ENGINE_HANDLE_@@@Z; NcaApiSrvImplIsEngineValid(NCA_INTSERVER_ENGINE_HANDLE_ *)
0x180007d13  lea     rcx, ?gNcaApiSrvImpl@@3UNCA_API_SRV_IMPL_COMPONENT_@@A; lpCriticalSection
0x180007d1a  mov     ebx, eax
0x180007d1c  call    cs:__imp_LeaveCriticalSection
0x180007d23  nop     dword ptr [rax+rax+00h]
0x180007d28  test    ebx, ebx
0x180007d2a  jz      short loc_180007D5A
0x180007d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d33  cmp     rcx, r13
0x180007d36  jz      loc_180007E97
0x180007d3c  test    [rcx+1Ch], r15b
0x180007d40  jz      loc_180007E97
0x180007d46  mov     edx, 42h ; 'B'
0x180007d4b  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x180007d52  mov     r9d, ebx
0x180007d55  jmp     loc_180007C78
0x180007d5a  lea     rcx, SRWLock; SRWLock
0x180007d61  call    cs:__imp_AcquireSRWLockShared
0x180007d68  nop     dword ptr [rax+rax+00h]
0x180007d6d  cmp     esi, 7
0x180007d70  jz      short loc_180007DE7
0x180007d72  cmp     esi, 2
0x180007d75  jz      short loc_180007DE7
0x180007d77  lea     eax, [rsi-3]
0x180007d7a  cmp     eax, 3
0x180007d7d  jbe     short loc_180007D8E
0x180007d7f  cmp     esi, 8
0x180007d82  jz      short loc_180007D8E
0x180007d84  mov     ebx, 57h ; 'W'
0x180007d89  jmp     loc_180007E88
0x180007d8e  mov     edx, 4
0x180007d93  cmp     [rdi], edx
0x180007d95  jnb     short loc_180007DD6
0x180007d97  mov     r9d, 0EAh
0x180007d9d  mov     [rdi], edx
0x180007d9f  mov     ebx, r9d
0x180007da2  mov     rcx, cs:WPP_GLOBAL_Control
0x180007da9  cmp     rcx, r13
0x180007dac  jz      loc_180007E88
0x180007db2  test    [rcx+1Ch], r15b
0x180007db6  jz      loc_180007E88
0x180007dbc  mov     edx, 45h ; 'E'
0x180007dc1  mov     rcx, [rcx+10h]
0x180007dc5  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x180007dcc  call    WPP_SF_d
0x180007dd1  jmp     loc_180007E88
0x180007dd6  mov     ecx, esi
0x180007dd8  call    NcaConfigMgrGetBool
0x180007ddd  mov     [r14], eax
0x180007de0  mov     [rdi], edx
0x180007de2  jmp     loc_180007E88
0x180007de7  lea     rdx, [rsp+68h+Src]
0x180007dec  mov     ecx, esi
0x180007dee  call    NcaConfigMgrGetString
0x180007df3  mov     ebx, eax
0x180007df5  test    eax, eax
0x180007df7  jz      short loc_180007E2A
0x180007df9  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e00  cmp     rcx, r13
0x180007e03  jz      short loc_180007E23
0x180007e05  test    [rcx+1Ch], r15b
0x180007e09  jz      short loc_180007E23
0x180007e0b  mov     rcx, [rcx+10h]
0x180007e0f  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x180007e16  mov     edx, 43h ; 'C'
0x180007e1b  mov     r9d, eax
0x180007e1e  call    WPP_SF_d
0x180007e23  mov     rbp, [rsp+68h+Src]
0x180007e28  jmp     short loc_180007E88
0x180007e2a  mov     rbp, [rsp+68h+Src]
0x180007e2f  mov     esi, r12d
0x180007e32  test    rbp, rbp
0x180007e35  jz      short loc_180007E78
0x180007e37  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007e3b  inc     rsi
0x180007e3e  cmp     [rbp+rsi*2+0], r12w
0x180007e44  jnz     short loc_180007E3B
0x180007e46  lea     esi, ds:2[rsi*2]
0x180007e4d  cmp     [rdi], esi
0x180007e4f  jnb     short loc_180007E78
0x180007e51  mov     r9d, 0EAh
0x180007e57  mov     [rdi], esi
0x180007e59  mov     ebx, r9d
0x180007e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e63  cmp     rcx, r13
0x180007e66  jz      short loc_180007E88
0x180007e68  test    [rcx+1Ch], r15b
0x180007e6c  jz      short loc_180007E88
0x180007e6e  mov     edx, 44h ; 'D'
0x180007e73  jmp     loc_180007DC1
0x180007e78  mov     r8d, esi; Size
0x180007e7b  mov     rdx, rbp; Src
0x180007e7e  mov     rcx, r14; void *
0x180007e81  call    memcpy_0
0x180007e86  mov     [rdi], esi
0x180007e88  lea     rdx, SRWLock
0x180007e8f  mov     ecx, r15d
0x180007e92  call    NcaExcludeShareLockLeave
0x180007e97  cmp     ebx, 45Bh
0x180007e9d  jz      short loc_180007EA4
0x180007e9f  call    ?NcaReleaseCancelableLock@@YAXPEAU_tag_NCA_CANCELABLE_LOCK@@@Z; NcaReleaseCancelableLock(_tag_NCA_CANCELABLE_LOCK *)
0x180007ea4  mov     rcx, rbp; lpMem
0x180007ea7  call    NcaFree
0x180007eac  mov     rcx, cs:WPP_GLOBAL_Control
0x180007eb3  cmp     rcx, r13
0x180007eb6  jz      short loc_180007ED6
0x180007eb8  test    byte ptr [rcx+1Ch], 8
0x180007ebc  jz      short loc_180007ED6
0x180007ebe  mov     rcx, [rcx+10h]
0x180007ec2  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x180007ec9  mov     edx, 46h ; 'F'
0x180007ece  mov     r9d, ebx
0x180007ed1  call    WPP_SF_d
0x180007ed6  test    cs:Microsoft_Windows_NcasvcEnableBits, r15b
0x180007edd  jz      short loc_180007EF5
0x180007edf  mov     r9d, ebx
0x180007ee2  lea     r8, aNcagetconfig; "NcaGetConfig"
0x180007ee9  lea     rdx, ApiActivityEnd
0x180007ef0  call    McTemplateU0zx_EventWriteTransfer
0x180007ef5  mov     eax, ebx
0x180007ef7  add     rsp, 28h
0x180007efb  pop     r15
0x180007efd  pop     r14
0x180007eff  pop     r13
0x180007f01  pop     r12
0x180007f03  pop     rdi
0x180007f04  pop     rsi
0x180007f05  pop     rbp
0x180007f06  pop     rbx
0x180007f07  retn
```
