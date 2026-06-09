# CommonUtil::MpGetServiceStartType(wchar_t const *,ulong *)

- ea: `0x18022c148`
- end: `0x18022c2fb`
- name: `?MpGetServiceStartType@CommonUtil@@YAJPEB_WPEAK@Z`
- size: `435`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *this, const wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1801cd0f0`

## callees

- `0x1800809d0`
- `0x180107940`
- `0x1801079a8`
- `0x180107c90`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18022c148`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x18022c1db`
- `ADVAPI32!CloseServiceHandle` at `0x18022c246`
- `ADVAPI32!CloseServiceHandle` at `0x18022c2cb`
- `ADVAPI32!CloseServiceHandle` at `0x18022c2da`
- `ADVAPI32!CloseServiceHandle` at `0x18022c1db`
- `ADVAPI32!CloseServiceHandle` at `0x18022c246`
- `ADVAPI32!CloseServiceHandle` at `0x18022c2cb`
- `ADVAPI32!CloseServiceHandle` at `0x18022c2da`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpGetServiceStartType(struct SC_HANDLE__ *this, wchar_t *a2, unsigned int *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  struct SC_HANDLE__ *v9; // r8
  int ServiceConfig; // eax
  void *v11; // rcx
  SC_HANDLE hSCObject; // [rsp+20h] [rbp-20h] BYREF
  SC_HANDLE v13; // [rsp+28h] [rbp-18h] BYREF
  void *v14; // [rsp+30h] [rbp-10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  *(_DWORD *)a2 = -1;
  v6 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCObject, (struct SC_HANDLE__ **)1, 0, 0, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids,
        (unsigned int)v6);
LABEL_7:
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    return v7;
  }
  v13 = 0;
  v8 = CommonUtil::HrOpenService(
         (CommonUtil *)&v13,
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
        73,
        WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids,
        (unsigned int)v8);
LABEL_14:
    if ( v13 )
      CloseServiceHandle(v13);
    goto LABEL_7;
  }
  v14 = 0;
  ServiceConfig = CommonUtil::UtilQueryServiceConfig((CommonUtil *)&v14, (struct _QUERY_SERVICE_CONFIGW **)v13, v9);
  v7 = ServiceConfig;
  if ( ServiceConfig < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids,
        (unsigned int)ServiceConfig);
    if ( v14 )
      operator delete(v14, (const struct std::nothrow_t *)0x40);
    goto LABEL_14;
  }
  v11 = v14;
  *(_DWORD *)a2 = *((_DWORD *)v14 + 1);
  operator delete(v11, (const struct std::nothrow_t *)0x40);
  if ( v13 )
    CloseServiceHandle(v13);
  if ( hSCObject )
    CloseServiceHandle(hSCObject);
  return 0;
}

```

## disassembly

```asm
0x18022c148  mov     [rsp-18h+arg_10], rbx
0x18022c14d  push    rbp
0x18022c14e  push    rsi
0x18022c14f  push    rdi
0x18022c150  mov     rbp, rsp
0x18022c153  sub     rsp, 40h
0x18022c157  mov     rax, cs:__security_cookie
0x18022c15e  xor     rax, rsp
0x18022c161  mov     [rbp+var_8], rax
0x18022c165  mov     rdi, rdx
0x18022c168  mov     rsi, rcx
0x18022c16b  test    rdx, rdx
0x18022c16e  jnz     short loc_18022C17A
0x18022c170  mov     eax, 80070057h
0x18022c175  jmp     loc_18022C2E2
0x18022c17a  xor     r9d, r9d; wchar_t *
0x18022c17d  mov     dword ptr [rdx], 0FFFFFFFFh
0x18022c183  xor     r8d, r8d; unsigned int
0x18022c186  mov     [rbp+hSCObject], 0
0x18022c18e  lea     rcx, [rbp+hSCObject]; this
0x18022c192  lea     edx, [r9+1]; struct SC_HANDLE__ **
0x18022c196  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEB_W1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,wchar_t const *,wchar_t const *)
0x18022c19b  mov     ebx, eax
0x18022c19d  test    eax, eax
0x18022c19f  jns     short loc_18022C1E8
0x18022c1a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18022c1a8  lea     rdx, WPP_GLOBAL_Control
0x18022c1af  cmp     rcx, rdx
0x18022c1b2  jz      short loc_18022C1D2
0x18022c1b4  test    byte ptr [rcx+1Ch], 1
0x18022c1b8  jz      short loc_18022C1D2
0x18022c1ba  mov     rcx, [rcx+10h]
0x18022c1be  lea     r8, WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids
0x18022c1c5  mov     edx, 48h ; 'H'
0x18022c1ca  mov     r9d, eax
0x18022c1cd  call    WPP_SF_d
0x18022c1d2  mov     rcx, [rbp+hSCObject]; hSCObject
0x18022c1d6  test    rcx, rcx
0x18022c1d9  jz      short loc_18022C1E1
0x18022c1db  call    cs:__imp_CloseServiceHandle
0x18022c1e1  mov     eax, ebx
0x18022c1e3  jmp     loc_18022C2E2
0x18022c1e8  mov     rdx, [rbp+hSCObject]; struct SC_HANDLE__ **
0x18022c1ec  lea     rcx, [rbp+var_18]; this
0x18022c1f0  mov     r9d, 1; wchar_t *
0x18022c1f6  mov     [rbp+var_18], 0
0x18022c1fe  mov     r8, rsi; struct SC_HANDLE__ *
0x18022c201  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEB_WK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,wchar_t const *,ulong)
0x18022c206  mov     ebx, eax
0x18022c208  test    eax, eax
0x18022c20a  jns     short loc_18022C24E
0x18022c20c  mov     rcx, cs:WPP_GLOBAL_Control
0x18022c213  lea     rdx, WPP_GLOBAL_Control
0x18022c21a  cmp     rcx, rdx
0x18022c21d  jz      short loc_18022C23D
0x18022c21f  test    byte ptr [rcx+1Ch], 1
0x18022c223  jz      short loc_18022C23D
0x18022c225  mov     rcx, [rcx+10h]
0x18022c229  lea     r8, WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids
0x18022c230  mov     edx, 49h ; 'I'
0x18022c235  mov     r9d, eax
0x18022c238  call    WPP_SF_d
0x18022c23d  mov     rcx, [rbp+var_18]; hSCObject
0x18022c241  test    rcx, rcx
0x18022c244  jz      short loc_18022C1D2
0x18022c246  call    cs:__imp_CloseServiceHandle
0x18022c24c  jmp     short loc_18022C1D2
0x18022c24e  mov     rdx, [rbp+var_18]; struct _QUERY_SERVICE_CONFIGW **
0x18022c252  lea     rcx, [rbp+var_10]; this
0x18022c256  mov     [rbp+var_10], 0
0x18022c25e  call    ?UtilQueryServiceConfig@CommonUtil@@YAJPEAPEAU_QUERY_SERVICE_CONFIGW@@PEAUSC_HANDLE__@@@Z; CommonUtil::UtilQueryServiceConfig(_QUERY_SERVICE_CONFIGW * *,SC_HANDLE__ *)
0x18022c263  mov     ebx, eax
0x18022c265  test    eax, eax
0x18022c267  jns     short loc_18022C2AF
0x18022c269  mov     rcx, cs:WPP_GLOBAL_Control
0x18022c270  lea     rdx, WPP_GLOBAL_Control
0x18022c277  cmp     rcx, rdx
0x18022c27a  jz      short loc_18022C29A
0x18022c27c  test    byte ptr [rcx+1Ch], 1
0x18022c280  jz      short loc_18022C29A
0x18022c282  mov     rcx, [rcx+10h]
0x18022c286  lea     r8, WPP_7aad8978a6743ebf70f1dcb2e6512991_Traceguids
0x18022c28d  mov     edx, 4Ah ; 'J'
0x18022c292  mov     r9d, eax
0x18022c295  call    WPP_SF_d
0x18022c29a  mov     rcx, [rbp+var_10]; void *
0x18022c29e  test    rcx, rcx
0x18022c2a1  jz      short loc_18022C23D
0x18022c2a3  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x18022c2a8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18022c2ad  jmp     short loc_18022C23D
0x18022c2af  mov     rcx, [rbp+var_10]; void *
0x18022c2b3  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x18022c2b8  mov     eax, [rcx+4]
0x18022c2bb  mov     [rdi], eax
0x18022c2bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18022c2c2  mov     rcx, [rbp+var_18]; hSCObject
0x18022c2c6  test    rcx, rcx
0x18022c2c9  jz      short loc_18022C2D1
0x18022c2cb  call    cs:__imp_CloseServiceHandle
0x18022c2d1  mov     rcx, [rbp+hSCObject]; hSCObject
0x18022c2d5  test    rcx, rcx
0x18022c2d8  jz      short loc_18022C2E0
0x18022c2da  call    cs:__imp_CloseServiceHandle
0x18022c2e0  xor     eax, eax
0x18022c2e2  mov     rcx, [rbp+var_8]
0x18022c2e6  xor     rcx, rsp; StackCookie
0x18022c2e9  call    __security_check_cookie
0x18022c2ee  mov     rbx, [rsp+40h+arg_10]
0x18022c2f3  add     rsp, 40h
0x18022c2f7  pop     rdi
0x18022c2f8  pop     rsi
0x18022c2f9  pop     rbp
0x18022c2fa  retn
```
