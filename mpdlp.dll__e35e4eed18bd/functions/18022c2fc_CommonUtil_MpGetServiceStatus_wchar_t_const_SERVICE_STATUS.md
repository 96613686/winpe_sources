# CommonUtil::MpGetServiceStatus(wchar_t const *,_SERVICE_STATUS *)

- ea: `0x18022c2fc`
- end: `0x18022c46a`
- name: `?MpGetServiceStatus@CommonUtil@@YAJPEB_WPEAU_SERVICE_STATUS@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *this, LPSERVICE_STATUS lpServiceStatus, struct _SERVICE_STATUS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801cd0f0`

## callees

- `0x1800809d0`
- `0x180107940`
- `0x1801079a8`
- `0x180107b9c`
- `0x18010cb40`
- `0x18022c2fc`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x18022c38a`
- `ADVAPI32!CloseServiceHandle` at `0x18022c3f6`
- `ADVAPI32!CloseServiceHandle` at `0x18022c43a`
- `ADVAPI32!CloseServiceHandle` at `0x18022c449`
- `ADVAPI32!CloseServiceHandle` at `0x18022c38a`
- `ADVAPI32!CloseServiceHandle` at `0x18022c3f6`
- `ADVAPI32!CloseServiceHandle` at `0x18022c43a`
- `ADVAPI32!CloseServiceHandle` at `0x18022c449`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpGetServiceStatus(
        struct SC_HANDLE__ *this,
        LPSERVICE_STATUS lpServiceStatus,
        struct _SERVICE_STATUS *a3)
{
  int v6; // eax
  int ServiceStatus; // ebx
  struct SC_HANDLE__ *v8; // r8
  _QWORD *v9; // r10
  __int64 v10; // rdx
  SC_HANDLE hSCObject; // [rsp+20h] [rbp-20h] BYREF
  SC_HANDLE hService; // [rsp+28h] [rbp-18h] BYREF

  if ( !lpServiceStatus )
    return 2147942487LL;
  v6 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCObject, (struct SC_HANDLE__ **)1, 0, 0, 0);
  ServiceStatus = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids,
        (unsigned int)v6);
LABEL_7:
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    return (unsigned int)ServiceStatus;
  }
  hService = 0;
  ServiceStatus = CommonUtil::HrOpenService(
                    (CommonUtil *)&hService,
                    (struct SC_HANDLE__ **)hSCObject,
                    this,
                    (const wchar_t *)4,
                    (unsigned int)hSCObject);
  if ( ServiceStatus < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 70;
LABEL_14:
      WPP_SF_d(v9[2], v10, WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids, (unsigned int)ServiceStatus);
      goto LABEL_15;
    }
    goto LABEL_15;
  }
  ServiceStatus = CommonUtil::HrQueryServiceStatus(lpServiceStatus, hService, v8);
  if ( ServiceStatus < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 71;
      goto LABEL_14;
    }
LABEL_15:
    if ( hService )
      CloseServiceHandle(hService);
    goto LABEL_7;
  }
  if ( hService )
    CloseServiceHandle(hService);
  if ( hSCObject )
    CloseServiceHandle(hSCObject);
  return 0;
}

```

## disassembly

```asm
0x18022c2fc  mov     [rsp-18h+arg_10], rbx
0x18022c301  push    rbp
0x18022c302  push    rsi
0x18022c303  push    rdi
0x18022c304  mov     rbp, rsp
0x18022c307  sub     rsp, 40h
0x18022c30b  mov     rax, cs:__security_cookie
0x18022c312  xor     rax, rsp
0x18022c315  mov     [rbp+var_10], rax
0x18022c319  mov     rdi, rdx
0x18022c31c  mov     rsi, rcx
0x18022c31f  test    rdx, rdx
0x18022c322  jnz     short loc_18022C32E
0x18022c324  mov     eax, 80070057h
0x18022c329  jmp     loc_18022C451
0x18022c32e  xor     r9d, r9d; wchar_t *
0x18022c331  mov     [rbp+hSCObject], 0
0x18022c339  xor     r8d, r8d; unsigned int
0x18022c33c  lea     rcx, [rbp+hSCObject]; this
0x18022c340  lea     edx, [r9+1]; struct SC_HANDLE__ **
0x18022c344  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEB_W1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,wchar_t const *,wchar_t const *)
0x18022c349  mov     ebx, eax
0x18022c34b  test    eax, eax
0x18022c34d  jns     short loc_18022C397
0x18022c34f  mov     r10, cs:WPP_GLOBAL_Control
0x18022c356  lea     rcx, WPP_GLOBAL_Control
0x18022c35d  cmp     r10, rcx
0x18022c360  jz      short loc_18022C381
0x18022c362  test    byte ptr [r10+1Ch], 1
0x18022c367  jz      short loc_18022C381
0x18022c369  mov     rcx, [r10+10h]
0x18022c36d  lea     r8, WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids
0x18022c374  mov     edx, 45h ; 'E'
0x18022c379  mov     r9d, eax
0x18022c37c  call    WPP_SF_d
0x18022c381  mov     rcx, [rbp+hSCObject]; hSCObject
0x18022c385  test    rcx, rcx
0x18022c388  jz      short loc_18022C390
0x18022c38a  call    cs:__imp_CloseServiceHandle
0x18022c390  mov     eax, ebx
0x18022c392  jmp     loc_18022C451
0x18022c397  mov     rdx, [rbp+hSCObject]; struct SC_HANDLE__ **
0x18022c39b  lea     rcx, [rbp+hService]; this
0x18022c39f  mov     r9d, 4; wchar_t *
0x18022c3a5  mov     [rbp+hService], 0
0x18022c3ad  mov     r8, rsi; struct SC_HANDLE__ *
0x18022c3b0  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEB_WK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,wchar_t const *,ulong)
0x18022c3b5  mov     ebx, eax
0x18022c3b7  test    eax, eax
0x18022c3b9  jns     short loc_18022C3FE
0x18022c3bb  mov     r10, cs:WPP_GLOBAL_Control
0x18022c3c2  lea     rcx, WPP_GLOBAL_Control
0x18022c3c9  cmp     r10, rcx
0x18022c3cc  jz      short loc_18022C3ED
0x18022c3ce  test    byte ptr [r10+1Ch], 1
0x18022c3d3  jz      short loc_18022C3ED
0x18022c3d5  mov     edx, 46h ; 'F'
0x18022c3da  mov     rcx, [r10+10h]
0x18022c3de  lea     r8, WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids
0x18022c3e5  mov     r9d, ebx
0x18022c3e8  call    WPP_SF_d
0x18022c3ed  mov     rcx, [rbp+hService]; hSCObject
0x18022c3f1  test    rcx, rcx
0x18022c3f4  jz      short loc_18022C381
0x18022c3f6  call    cs:__imp_CloseServiceHandle
0x18022c3fc  jmp     short loc_18022C381
0x18022c3fe  mov     rdx, [rbp+hService]; hService
0x18022c402  mov     rcx, rdi; lpServiceStatus
0x18022c405  call    ?HrQueryServiceStatus@CommonUtil@@YAJPEAU_SERVICE_STATUS@@PEAUSC_HANDLE__@@@Z; CommonUtil::HrQueryServiceStatus(_SERVICE_STATUS *,SC_HANDLE__ *)
0x18022c40a  mov     ebx, eax
0x18022c40c  test    eax, eax
0x18022c40e  jns     short loc_18022C431
0x18022c410  mov     r10, cs:WPP_GLOBAL_Control
0x18022c417  lea     rcx, WPP_GLOBAL_Control
0x18022c41e  cmp     r10, rcx
0x18022c421  jz      short loc_18022C3ED
0x18022c423  test    byte ptr [r10+1Ch], 1
0x18022c428  jz      short loc_18022C3ED
0x18022c42a  mov     edx, 47h ; 'G'
0x18022c42f  jmp     short loc_18022C3DA
0x18022c431  mov     rcx, [rbp+hService]; hSCObject
0x18022c435  test    rcx, rcx
0x18022c438  jz      short loc_18022C440
0x18022c43a  call    cs:__imp_CloseServiceHandle
0x18022c440  mov     rcx, [rbp+hSCObject]; hSCObject
0x18022c444  test    rcx, rcx
0x18022c447  jz      short loc_18022C44F
0x18022c449  call    cs:__imp_CloseServiceHandle
0x18022c44f  xor     eax, eax
0x18022c451  mov     rcx, [rbp+var_10]
0x18022c455  xor     rcx, rsp; StackCookie
0x18022c458  call    __security_check_cookie
0x18022c45d  mov     rbx, [rsp+40h+arg_10]
0x18022c462  add     rsp, 40h
0x18022c466  pop     rdi
0x18022c467  pop     rsi
0x18022c468  pop     rbp
0x18022c469  retn
```
