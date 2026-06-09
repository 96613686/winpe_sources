# CommonUtil::MpGetServiceBinary(wchar_t const *,wchar_t * *)

- ea: `0x18022bf28`
- end: `0x18022c146`
- name: `?MpGetServiceBinary@CommonUtil@@YAJPEB_WPEAPEA_W@Z`
- size: `542`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *this, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1801cd0f0`

## callees

- `0x1800809d0`
- `0x180100c34`
- `0x180107940`
- `0x1801079a8`
- `0x180107c90`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18022bf28`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x18022bfbc`
- `ADVAPI32!CloseServiceHandle` at `0x18022c027`
- `ADVAPI32!CloseServiceHandle` at `0x18022c113`
- `ADVAPI32!CloseServiceHandle` at `0x18022c122`
- `ADVAPI32!CloseServiceHandle` at `0x18022bfbc`
- `ADVAPI32!CloseServiceHandle` at `0x18022c027`
- `ADVAPI32!CloseServiceHandle` at `0x18022c113`
- `ADVAPI32!CloseServiceHandle` at `0x18022c122`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpGetServiceBinary(struct SC_HANDLE__ *this, wchar_t *a2, wchar_t **a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  struct SC_HANDLE__ *v9; // r8
  int ServiceConfig; // eax
  const wchar_t *v11; // r8
  int v12; // eax
  const struct std::nothrow_t *v13; // rdx
  void *v14; // rcx
  SC_HANDLE hSCObject; // [rsp+20h] [rbp-30h] BYREF
  SC_HANDLE v16; // [rsp+28h] [rbp-28h] BYREF
  void *v17; // [rsp+30h] [rbp-20h] BYREF
  void *v18; // [rsp+38h] [rbp-18h] BYREF

  if ( !a2 )
    return 2147942487LL;
  *(_QWORD *)a2 = 0;
  v6 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCObject, (struct SC_HANDLE__ **)1, 0, 0, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids,
        (unsigned int)v6);
LABEL_7:
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    return v7;
  }
  v16 = 0;
  v8 = CommonUtil::HrOpenService(
         (CommonUtil *)&v16,
         (struct SC_HANDLE__ **)hSCObject,
         this,
         (const wchar_t *)1,
         (unsigned int)hSCObject);
  v7 = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids,
        (unsigned int)v8);
LABEL_14:
    if ( v16 )
      CloseServiceHandle(v16);
    goto LABEL_7;
  }
  v17 = 0;
  ServiceConfig = CommonUtil::UtilQueryServiceConfig((CommonUtil *)&v17, (struct _QUERY_SERVICE_CONFIGW **)v16, v9);
  v7 = ServiceConfig;
  if ( ServiceConfig < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids,
        (unsigned int)ServiceConfig);
LABEL_20:
    if ( v17 )
      operator delete(v17, (const struct std::nothrow_t *)0x40);
    goto LABEL_14;
  }
  v18 = 0;
  v12 = CommonUtil::HrDuplicateStringW((CommonUtil *)&v18, *((wchar_t ***)v17 + 2), v11);
  v7 = v12;
  if ( v12 < 0 )
  {
    v13 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids,
        (unsigned int)v12);
    if ( v18 )
      operator delete(v18, v13);
    goto LABEL_20;
  }
  v14 = v17;
  *(_QWORD *)a2 = v18;
  if ( v14 )
    operator delete(v14, (const struct std::nothrow_t *)0x40);
  if ( v16 )
    CloseServiceHandle(v16);
  if ( hSCObject )
    CloseServiceHandle(hSCObject);
  return 0;
}

```

## disassembly

```asm
0x18022bf28  mov     [rsp-18h+arg_10], rbx
0x18022bf2d  push    rbp
0x18022bf2e  push    rsi
0x18022bf2f  push    rdi
0x18022bf30  mov     rbp, rsp
0x18022bf33  sub     rsp, 50h
0x18022bf37  mov     rax, cs:__security_cookie
0x18022bf3e  xor     rax, rsp
0x18022bf41  mov     [rbp+var_10], rax
0x18022bf45  mov     rdi, rdx
0x18022bf48  mov     rsi, rcx
0x18022bf4b  test    rdx, rdx
0x18022bf4e  jnz     short loc_18022BF5A
0x18022bf50  mov     eax, 80070057h
0x18022bf55  jmp     loc_18022C12A
0x18022bf5a  xor     r9d, r9d; wchar_t *
0x18022bf5d  mov     qword ptr [rdx], 0
0x18022bf64  xor     r8d, r8d; unsigned int
0x18022bf67  mov     [rbp+hSCObject], 0
0x18022bf6f  lea     rcx, [rbp+hSCObject]; this
0x18022bf73  lea     edx, [r9+1]; struct SC_HANDLE__ **
0x18022bf77  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEB_W1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,wchar_t const *,wchar_t const *)
0x18022bf7c  mov     ebx, eax
0x18022bf7e  test    eax, eax
0x18022bf80  jns     short loc_18022BFC9
0x18022bf82  mov     rcx, cs:WPP_GLOBAL_Control
0x18022bf89  lea     rdx, WPP_GLOBAL_Control
0x18022bf90  cmp     rcx, rdx
0x18022bf93  jz      short loc_18022BFB3
0x18022bf95  test    byte ptr [rcx+1Ch], 1
0x18022bf99  jz      short loc_18022BFB3
0x18022bf9b  mov     rcx, [rcx+10h]
0x18022bf9f  lea     r8, WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids
0x18022bfa6  mov     edx, 41h ; 'A'
0x18022bfab  mov     r9d, eax
0x18022bfae  call    WPP_SF_d
0x18022bfb3  mov     rcx, [rbp+hSCObject]; hSCObject
0x18022bfb7  test    rcx, rcx
0x18022bfba  jz      short loc_18022BFC2
0x18022bfbc  call    cs:__imp_CloseServiceHandle
0x18022bfc2  mov     eax, ebx
0x18022bfc4  jmp     loc_18022C12A
0x18022bfc9  mov     rdx, [rbp+hSCObject]; struct SC_HANDLE__ **
0x18022bfcd  lea     rcx, [rbp+var_28]; this
0x18022bfd1  mov     r9d, 1; wchar_t *
0x18022bfd7  mov     [rbp+var_28], 0
0x18022bfdf  mov     r8, rsi; struct SC_HANDLE__ *
0x18022bfe2  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEB_WK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,wchar_t const *,ulong)
0x18022bfe7  mov     ebx, eax
0x18022bfe9  test    eax, eax
0x18022bfeb  jns     short loc_18022C02F
0x18022bfed  mov     rcx, cs:WPP_GLOBAL_Control
0x18022bff4  lea     rdx, WPP_GLOBAL_Control
0x18022bffb  cmp     rcx, rdx
0x18022bffe  jz      short loc_18022C01E
0x18022c000  test    byte ptr [rcx+1Ch], 1
0x18022c004  jz      short loc_18022C01E
0x18022c006  mov     rcx, [rcx+10h]
0x18022c00a  lea     r8, WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids
0x18022c011  mov     edx, 42h ; 'B'
0x18022c016  mov     r9d, eax
0x18022c019  call    WPP_SF_d
0x18022c01e  mov     rcx, [rbp+var_28]; hSCObject
0x18022c022  test    rcx, rcx
0x18022c025  jz      short loc_18022BFB3
0x18022c027  call    cs:__imp_CloseServiceHandle
0x18022c02d  jmp     short loc_18022BFB3
0x18022c02f  mov     rdx, [rbp+var_28]; struct _QUERY_SERVICE_CONFIGW **
0x18022c033  lea     rcx, [rbp+var_20]; this
0x18022c037  mov     [rbp+var_20], 0
0x18022c03f  call    ?UtilQueryServiceConfig@CommonUtil@@YAJPEAPEAU_QUERY_SERVICE_CONFIGW@@PEAUSC_HANDLE__@@@Z; CommonUtil::UtilQueryServiceConfig(_QUERY_SERVICE_CONFIGW * *,SC_HANDLE__ *)
0x18022c044  mov     ebx, eax
0x18022c046  test    eax, eax
0x18022c048  jns     short loc_18022C090
0x18022c04a  mov     rcx, cs:WPP_GLOBAL_Control
0x18022c051  lea     rdx, WPP_GLOBAL_Control
0x18022c058  cmp     rcx, rdx
0x18022c05b  jz      short loc_18022C07B
0x18022c05d  test    byte ptr [rcx+1Ch], 1
0x18022c061  jz      short loc_18022C07B
0x18022c063  mov     rcx, [rcx+10h]
0x18022c067  lea     r8, WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids
0x18022c06e  mov     edx, 43h ; 'C'
0x18022c073  mov     r9d, eax
0x18022c076  call    WPP_SF_d
0x18022c07b  mov     rcx, [rbp+var_20]; void *
0x18022c07f  test    rcx, rcx
0x18022c082  jz      short loc_18022C01E
0x18022c084  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x18022c089  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18022c08e  jmp     short loc_18022C01E
0x18022c090  mov     rdx, [rbp+var_20]
0x18022c094  lea     rcx, [rbp+var_18]; this
0x18022c098  mov     [rbp+var_18], 0
0x18022c0a0  mov     rdx, [rdx+10h]; wchar_t **
0x18022c0a4  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::HrDuplicateStringW(wchar_t * *,wchar_t const *)
0x18022c0a9  mov     ebx, eax
0x18022c0ab  test    eax, eax
0x18022c0ad  jns     short loc_18022C0F0
0x18022c0af  mov     rcx, cs:WPP_GLOBAL_Control
0x18022c0b6  lea     rdx, WPP_GLOBAL_Control
0x18022c0bd  cmp     rcx, rdx
0x18022c0c0  jz      short loc_18022C0E0
0x18022c0c2  test    byte ptr [rcx+1Ch], 1
0x18022c0c6  jz      short loc_18022C0E0
0x18022c0c8  mov     rcx, [rcx+10h]
0x18022c0cc  lea     r8, WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids
0x18022c0d3  mov     edx, 44h ; 'D'
0x18022c0d8  mov     r9d, eax
0x18022c0db  call    WPP_SF_d
0x18022c0e0  mov     rcx, [rbp+var_18]; void *
0x18022c0e4  test    rcx, rcx
0x18022c0e7  jz      short loc_18022C07B
0x18022c0e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18022c0ee  jmp     short loc_18022C07B
0x18022c0f0  mov     rcx, [rbp+var_20]; void *
0x18022c0f4  mov     rax, [rbp+var_18]
0x18022c0f8  mov     [rdi], rax
0x18022c0fb  test    rcx, rcx
0x18022c0fe  jz      short loc_18022C10A
0x18022c100  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x18022c105  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18022c10a  mov     rcx, [rbp+var_28]; hSCObject
0x18022c10e  test    rcx, rcx
0x18022c111  jz      short loc_18022C119
0x18022c113  call    cs:__imp_CloseServiceHandle
0x18022c119  mov     rcx, [rbp+hSCObject]; hSCObject
0x18022c11d  test    rcx, rcx
0x18022c120  jz      short loc_18022C128
0x18022c122  call    cs:__imp_CloseServiceHandle
0x18022c128  xor     eax, eax
0x18022c12a  mov     rcx, [rbp+var_10]
0x18022c12e  xor     rcx, rsp; StackCookie
0x18022c131  call    __security_check_cookie
0x18022c136  mov     rbx, [rsp+50h+arg_10]
0x18022c13e  add     rsp, 50h
0x18022c142  pop     rdi
0x18022c143  pop     rsi
0x18022c144  pop     rbp
0x18022c145  retn
```
