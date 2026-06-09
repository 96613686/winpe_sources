# RealtimeProtection::DlpUserSidCache::GetPrimaryToken(ulong,PPID const &,void * *)

- ea: `0x1801d9120`
- end: `0x1801d936e`
- name: `?GetPrimaryToken@DlpUserSidCache@RealtimeProtection@@YAJKAEBUPPID@@PEAPEAX@Z`
- size: `590`
- prototype: `__int64 __fastcall(ULONG SessionId, unsigned int, const struct PPID *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009d7b0`

## callees

- `0x180028d80`
- `0x18007d570`
- `0x1800809d0`
- `0x1801019bc`
- `0x1801051e8`
- `0x180105f50`
- `0x18010cb40`
- `0x1801d9120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801d91d1`
- `KERNEL32!CloseHandle` at `0x1801d9209`
- `KERNEL32!CloseHandle` at `0x1801d9219`
- `KERNEL32!CloseHandle` at `0x1801d923f`
- `KERNEL32!CloseHandle` at `0x1801d92a6`
- `KERNEL32!CloseHandle` at `0x1801d92b6`
- `KERNEL32!CloseHandle` at `0x1801d92ef`
- `KERNEL32!CloseHandle` at `0x1801d92ff`
- `KERNEL32!CloseHandle` at `0x1801d91d1`
- `KERNEL32!CloseHandle` at `0x1801d9209`
- `KERNEL32!CloseHandle` at `0x1801d9219`
- `KERNEL32!CloseHandle` at `0x1801d923f`
- `KERNEL32!CloseHandle` at `0x1801d92a6`
- `KERNEL32!CloseHandle` at `0x1801d92b6`
- `KERNEL32!CloseHandle` at `0x1801d92ef`
- `KERNEL32!CloseHandle` at `0x1801d92ff`
- `WTSAPI32!WTSQueryUserToken` at `0x1801d9256`
- `WTSAPI32!WTSQueryUserToken` at `0x1801d9256`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpUserSidCache::GetPrimaryToken(
        ULONG SessionId,
        __int64 a2,
        const struct PPID *a3,
        void **a4)
{
  unsigned int v8; // r9d
  void **v9; // rsi
  HANDLE v10; // rax
  int LastFailure; // eax
  unsigned int v12; // esi
  HANDLE v13; // rax
  std::_Ref_count_base *v14[2]; // [rsp+20h] [rbp-48h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-30h] BYREF
  HANDLE v16; // [rsp+40h] [rbp-28h] BYREF

  *(_OWORD *)v14 = 0;
  std::atomic_load__anonymous_namespace_::UserSidCache_(v14);
  if ( v14[0] )
  {
    if ( a3 )
    {
      *(_QWORD *)a3 = 0;
      hObject = 0;
      v16 = 0;
      if ( (int)CommonUtil::UtilOpenProcess((CommonUtil *)&v16, (void **)*(unsigned int *)(a2 + 8), 0x400u) < 0 )
        goto LABEL_19;
      v9 = (void **)v16;
      if ( hObject )
        CloseHandle(hObject);
      if ( CommonUtil::UtilOpenProcessToken((CommonUtil *)&hObject, v9, (void *)0xE, v8) < 0 )
      {
LABEL_19:
        if ( hObject )
        {
          CloseHandle(hObject);
          hObject = 0;
        }
        if ( WTSQueryUserToken(SessionId, &hObject)
          || (LastFailure = HrGetLastFailure(), v12 = LastFailure, LastFailure >= 0) )
        {
          v13 = hObject;
          hObject = 0;
          *(_QWORD *)a3 = v13;
          if ( v16 )
          {
            CloseHandle(v16);
            if ( hObject )
              CloseHandle(hObject);
          }
          if ( v14[1] )
            std::_Ref_count_base::_Decref(v14[1]);
          return 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              WPP_3aa1f00f36e330821d5f037f1b346392_Traceguids,
              (unsigned int)LastFailure);
          if ( v16 )
            CloseHandle(v16);
          if ( hObject )
            CloseHandle(hObject);
          if ( v14[1] )
            std::_Ref_count_base::_Decref(v14[1]);
          return v12;
        }
      }
      else
      {
        v10 = hObject;
        hObject = 0;
        *(_QWORD *)a3 = v10;
        if ( v16 )
        {
          CloseHandle(v16);
          if ( hObject )
            CloseHandle(hObject);
        }
        if ( v14[1] )
          std::_Ref_count_base::_Decref(v14[1]);
        return 0;
      }
    }
    else
    {
      if ( v14[1] )
        std::_Ref_count_base::_Decref(v14[1]);
      return 2147942487LL;
    }
  }
  else
  {
    if ( v14[1] )
      std::_Ref_count_base::_Decref(v14[1]);
    return 2147483662LL;
  }
}

```

## disassembly

```asm
0x1801d9120  push    rsi
0x1801d9122  push    rdi
0x1801d9123  push    r14
0x1801d9125  sub     rsp, 50h
0x1801d9129  mov     rax, cs:__security_cookie
0x1801d9130  xor     rax, rsp
0x1801d9133  mov     [rsp+68h+var_20], rax
0x1801d9138  mov     rdi, r8
0x1801d913b  mov     rsi, rdx
0x1801d913e  mov     r14d, ecx
0x1801d9141  xorps   xmm0, xmm0
0x1801d9144  movups  xmmword ptr [rsp+68h+var_48], xmm0
0x1801d9149  lea     rcx, [rsp+68h+var_48]
0x1801d914e  call    std__atomic_load__anonymous_namespace___UserSidCache_
0x1801d9153  cmp     [rsp+68h+var_48], 0
0x1801d9159  jnz     short loc_1801D9174
0x1801d915b  mov     rcx, [rsp+68h+var_48+8]; this
0x1801d9160  test    rcx, rcx
0x1801d9163  jz      short loc_1801D916A
0x1801d9165  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801d916a  mov     eax, 8000000Eh
0x1801d916f  jmp     loc_1801D9358
0x1801d9174  test    rdi, rdi
0x1801d9177  jnz     short loc_1801D9192
0x1801d9179  mov     rcx, [rsp+68h+var_48+8]; this
0x1801d917e  test    rcx, rcx
0x1801d9181  jz      short loc_1801D9188
0x1801d9183  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801d9188  mov     eax, 80070057h
0x1801d918d  jmp     loc_1801D9358
0x1801d9192  mov     qword ptr [rdi], 0
0x1801d9199  mov     [rsp+68h+hObject], 0
0x1801d91a2  mov     [rsp+68h+var_28], 0
0x1801d91ab  mov     r8d, 400h; unsigned int
0x1801d91b1  mov     edx, [rsi+8]; void **
0x1801d91b4  lea     rcx, [rsp+68h+var_28]; this
0x1801d91b9  call    ?UtilOpenProcess@CommonUtil@@YAJPEAPEAXKK@Z; CommonUtil::UtilOpenProcess(void * *,ulong,ulong)
0x1801d91be  test    eax, eax
0x1801d91c0  js      short loc_1801D9235
0x1801d91c2  mov     rsi, [rsp+68h+var_28]
0x1801d91c7  mov     rcx, [rsp+68h+hObject]; hObject
0x1801d91cc  test    rcx, rcx
0x1801d91cf  jz      short loc_1801D91D7
0x1801d91d1  call    cs:__imp_CloseHandle
0x1801d91d7  mov     r8d, 0Eh; void *
0x1801d91dd  mov     rdx, rsi; void **
0x1801d91e0  lea     rcx, [rsp+68h+hObject]; this
0x1801d91e5  call    ?UtilOpenProcessToken@CommonUtil@@YAJPEAPEAXPEAXK@Z; CommonUtil::UtilOpenProcessToken(void * *,void *,ulong)
0x1801d91ea  test    eax, eax
0x1801d91ec  js      short loc_1801D9235
0x1801d91ee  mov     rax, [rsp+68h+hObject]
0x1801d91f3  mov     [rsp+68h+hObject], 0
0x1801d91fc  mov     [rdi], rax
0x1801d91ff  mov     rcx, [rsp+68h+var_28]; hObject
0x1801d9204  test    rcx, rcx
0x1801d9207  jz      short loc_1801D921F
0x1801d9209  call    cs:__imp_CloseHandle
0x1801d920f  mov     rcx, [rsp+68h+hObject]; hObject
0x1801d9214  test    rcx, rcx
0x1801d9217  jz      short loc_1801D921F
0x1801d9219  call    cs:__imp_CloseHandle
0x1801d921f  mov     rcx, [rsp+68h+var_48+8]; this
0x1801d9224  test    rcx, rcx
0x1801d9227  jz      short loc_1801D922E
0x1801d9229  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801d922e  xor     eax, eax
0x1801d9230  jmp     loc_1801D9358
0x1801d9235  mov     rcx, [rsp+68h+hObject]; hObject
0x1801d923a  test    rcx, rcx
0x1801d923d  jz      short loc_1801D924E
0x1801d923f  call    cs:__imp_CloseHandle
0x1801d9245  mov     [rsp+68h+hObject], 0
0x1801d924e  lea     rdx, [rsp+68h+hObject]; phToken
0x1801d9253  mov     ecx, r14d; SessionId
0x1801d9256  call    cs:__imp_WTSQueryUserToken
0x1801d925c  test    eax, eax
0x1801d925e  jnz     short loc_1801D92D2
0x1801d9260  call    HrGetLastFailure
0x1801d9265  mov     esi, eax
0x1801d9267  test    eax, eax
0x1801d9269  jns     short loc_1801D92D2
0x1801d926b  lea     rdx, WPP_GLOBAL_Control
0x1801d9272  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d9279  cmp     rcx, rdx
0x1801d927c  jz      short loc_1801D929C
0x1801d927e  test    byte ptr [rcx+1Ch], 1
0x1801d9282  jz      short loc_1801D929C
0x1801d9284  mov     edx, 11h
0x1801d9289  mov     r9d, eax
0x1801d928c  lea     r8, WPP_3aa1f00f36e330821d5f037f1b346392_Traceguids
0x1801d9293  mov     rcx, [rcx+10h]
0x1801d9297  call    WPP_SF_d
0x1801d929c  mov     rcx, [rsp+68h+var_28]; hObject
0x1801d92a1  test    rcx, rcx
0x1801d92a4  jz      short loc_1801D92AC
0x1801d92a6  call    cs:__imp_CloseHandle
0x1801d92ac  mov     rcx, [rsp+68h+hObject]; hObject
0x1801d92b1  test    rcx, rcx
0x1801d92b4  jz      short loc_1801D92BC
0x1801d92b6  call    cs:__imp_CloseHandle
0x1801d92bc  mov     rcx, [rsp+68h+var_48+8]; this
0x1801d92c1  test    rcx, rcx
0x1801d92c4  jz      short loc_1801D92CB
0x1801d92c6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801d92cb  mov     eax, esi
0x1801d92cd  jmp     loc_1801D9358
0x1801d92d2  mov     rax, [rsp+68h+hObject]
0x1801d92d7  mov     [rsp+68h+hObject], 0
0x1801d92e0  mov     [rdi], rax
0x1801d92e3  xor     edi, edi
0x1801d92e5  mov     rcx, [rsp+68h+var_28]; hObject
0x1801d92ea  test    rcx, rcx
0x1801d92ed  jz      short loc_1801D9306
0x1801d92ef  call    cs:__imp_CloseHandle
0x1801d92f5  mov     rcx, [rsp+68h+hObject]; hObject
0x1801d92fa  test    rcx, rcx
0x1801d92fd  jz      short loc_1801D9306
0x1801d92ff  call    cs:__imp_CloseHandle
0x1801d9305  nop
0x1801d9306  jmp     short loc_1801D9347
0x1801d9308  mov     edi, dword ptr [rsp+68h+hObject]
0x1801d930c  jmp     short loc_1801D9316
0x1801d930e  mov     edi, dword ptr [rsp+68h+hObject]
0x1801d9312  test    edi, edi
0x1801d9314  jns     short loc_1801D9347
0x1801d9316  lea     rdx, WPP_GLOBAL_Control
0x1801d931d  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d9324  cmp     rcx, rdx
0x1801d9327  jz      short loc_1801D9347
0x1801d9329  test    byte ptr [rcx+1Ch], 1
0x1801d932d  jz      short loc_1801D9347
0x1801d932f  mov     edx, 12h
0x1801d9334  mov     r9d, edi
0x1801d9337  lea     r8, WPP_3aa1f00f36e330821d5f037f1b346392_Traceguids
0x1801d933e  mov     rcx, [rcx+10h]
0x1801d9342  call    WPP_SF_d
0x1801d9347  mov     rcx, [rsp+68h+var_48+8]; this
0x1801d934c  test    rcx, rcx
0x1801d934f  jz      short loc_1801D9356
0x1801d9351  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801d9356  mov     eax, edi
0x1801d9358  mov     rcx, [rsp+68h+var_20]
0x1801d935d  xor     rcx, rsp; StackCookie
0x1801d9360  call    __security_check_cookie
0x1801d9365  add     rsp, 50h
0x1801d9369  pop     r14
0x1801d936b  pop     rdi
0x1801d936c  pop     rsi
0x1801d936d  retn
```
