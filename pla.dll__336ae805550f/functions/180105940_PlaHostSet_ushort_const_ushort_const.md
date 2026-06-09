# PlaHostSet(ushort const *,ushort const *)

- ea: `0x180105940`
- end: `0x180105f3e`
- name: `?PlaHostSet@@YAJPEBG0@Z`
- size: `1534`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180051860`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x18009aef4`
- `0x1800e89cc`
- `0x180105940`
- `0x1801334e8`
- `0x18013aee0`

## import_xrefs

- `msvcrt!wcschr` at `0x180105cc0`
- `msvcrt!wcschr` at `0x180105cc0`
- `ntdll!EtwNotificationUnregister` at `0x180105f01`
- `ntdll!EtwNotificationUnregister` at `0x180105f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105c33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105dc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105c33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105dc4`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180105b67`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180105b67`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801059b2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801059b2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180105f0c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180105f0c`
- `USER32!DestroyWindow` at `0x180105ed5`
- `USER32!DestroyWindow` at `0x180105ed5`
- `USER32!CreateWindowExW` at `0x180105c21`
- `USER32!CreateWindowExW` at `0x180105c21`
- `USER32!PeekMessageW` at `0x180105d7d`
- `USER32!PeekMessageW` at `0x180105d7d`
- `USER32!MsgWaitForMultipleObjects` at `0x180105db1`
- `USER32!MsgWaitForMultipleObjects` at `0x180105db1`
- `USER32!DispatchMessageW` at `0x180105d95`
- `USER32!DispatchMessageW` at `0x180105d95`

## pseudocode

```c
__int64 __fastcall PlaHostSet(unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HWND Window; // r12
  HRESULT v5; // eax
  signed int v6; // ebx
  int v7; // r13d
  __int64 v8; // rdi
  __int64 v9; // rdi
  __int64 v10; // rdi
  HRESULT v11; // eax
  signed int LastError; // eax
  wchar_t *v13; // rax
  const unsigned __int16 *v14; // rdx
  int started; // eax
  DWORD v16; // eax
  signed int v17; // eax
  signed int v19; // [rsp+70h] [rbp-90h] BYREF
  HRESULT v20; // [rsp+78h] [rbp-88h] BYREF
  HANDLE pHandles; // [rsp+80h] [rbp-80h] BYREF
  LPCVOID lpMem; // [rsp+88h] [rbp-78h] BYREF
  LPCVOID v23; // [rsp+90h] [rbp-70h] BYREF
  LPCVOID v24; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v25; // [rsp+A0h] [rbp-60h] BYREF
  struct _ACL pDacl; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD pSecDesc[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v28; // [rsp+D0h] [rbp-30h]
  tagMSG Msg; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 v30[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v31[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v32[64]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v33[64]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v34[64]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v35[64]; // [rsp+390h] [rbp+290h] BYREF

  Window = 0;
  pHandles = 0;
  v24 = 0;
  pDacl = 0;
  v28 = 0;
  lpMem = 0;
  memset(&Msg, 0, sizeof(Msg));
  v23 = 0;
  v25 = 0;
  memset(pSecDesc, 0, sizeof(pSecDesc));
  v5 = CoInitializeEx(0, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 0;
    v19 = 0;
    v20 = v5;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v30, 0x4000000000000800uLL);
      v8 = -1;
      do
        ++v8;
      while ( v30[v8] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v20, 4, byte_180147320, 1, &v19, 4);
    }
    goto LABEL_60;
  }
  v7 = 1;
  v6 = PlaiCreateHostSecurityDescriptor(pSecDesc, &pDacl, (void **)&v23, (void **)&lpMem);
  if ( v6 < 0 )
  {
    v19 = v6;
    v20 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_54;
    }
    PlaiWhoAmI(v31, 0x4000000000000800uLL);
    v9 = -1;
    do
      ++v9;
    while ( v31[v9] );
    goto LABEL_53;
  }
  v10 = -1;
  v11 = CoInitializeSecurity(pSecDesc, -1, 0, 0, 6u, 3u, 0, 0x3020u, 0);
  v6 = v11;
  if ( v11 < 0 )
  {
    v19 = v11;
    v20 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_54;
    }
    PlaiWhoAmI(v32, 0x4000000000000800uLL);
    do
      ++v10;
    while ( v32[v10] );
    goto LABEL_53;
  }
  Window = CreateWindowExW(0, L"STATIC", L"PLAWnd", 0, 0x80000000, 0x80000000, 0x80000000, 0x80000000, 0, 0, 0, 0);
  if ( !Window )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v20 = 0;
    v19 = v6;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_54;
    }
    PlaiWhoAmI(v33, 0x4000000000000800uLL);
    do
      ++v10;
    while ( v33[v10] );
    goto LABEL_53;
  }
  v13 = wcschr(a2, 0x7Cu);
  if ( !v13 || (v14 = v13 + 1, *v13 = 0, v13 == (wchar_t *)-2LL) )
    v14 = a2;
  started = PlaStartDataCollectorSet(a1, (unsigned __int64)v14, (unsigned __int16 ***)&v24, &pHandles, &v25);
  v6 = started;
  if ( started >= 0 )
  {
    while ( 1 )
    {
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        if ( Msg.message == 16 )
          goto LABEL_54;
        DispatchMessageW(&Msg);
      }
      v16 = MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1CFFu);
      if ( !v16 )
        goto LABEL_54;
      if ( v16 == -1 )
      {
        v17 = GetLastError();
        v6 = v17;
        if ( v17 > 0 )
          v6 = (unsigned __int16)v17 | 0x80070000;
        v20 = 0;
        v19 = v6;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v35, 0x4000000000000800uLL);
          do
            ++v10;
          while ( v35[v10] );
          goto LABEL_53;
        }
        goto LABEL_54;
      }
    }
  }
  v20 = 0;
  v19 = started;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v34, 0x4000000000000800uLL);
    do
      ++v10;
    while ( v34[v10] );
LABEL_53:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v19, 4, byte_180147320, 1, &v20, 4);
  }
LABEL_54:
  if ( lpMem )
    PlaiFree(lpMem, 1);
  if ( v23 )
    PlaiFree(v23, 1);
  if ( Window )
    DestroyWindow(Window);
LABEL_60:
  if ( v24 )
  {
    if ( v6 < 0 )
      PlaStopDataCollectorSet(v24);
    else
      v6 = PlaStopDataCollectorSet(v24);
  }
  if ( v25 )
    EtwNotificationUnregister(v25, 0);
  if ( v7 )
    CoUninitialize();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180105940  mov     [rsp-8+arg_10], rbx
0x180105945  push    rbp
0x180105946  push    rsi
0x180105947  push    rdi
0x180105948  push    r12
0x18010594a  push    r13
0x18010594c  push    r14
0x18010594e  push    r15
0x180105950  lea     rbp, [rsp-320h]
0x180105958  sub     rsp, 420h
0x18010595f  mov     rax, cs:__security_cookie
0x180105966  xor     rax, rsp
0x180105969  mov     [rbp+350h+var_40], rax
0x180105970  xorps   xmm0, xmm0
0x180105973  xor     r12d, r12d
0x180105976  mov     r14, rdx
0x180105979  mov     [rbp+350h+pHandles], r12
0x18010597d  mov     r15, rcx
0x180105980  mov     [rbp+350h+var_3B8], r12
0x180105984  xor     eax, eax
0x180105986  mov     qword ptr [rbp+350h+pDacl.AclRevision], r12
0x18010598a  xor     edx, edx; dwCoInit
0x18010598c  mov     [rbp+350h+var_380], rax
0x180105990  xor     ecx, ecx; pvReserved
0x180105992  mov     [rbp+350h+lpMem], r12
0x180105996  movups  xmmword ptr [rbp+350h+Msg.hwnd], xmm0
0x18010599a  mov     [rbp+350h+var_3C0], r12
0x18010599e  movups  xmmword ptr [rbp+350h+Msg.wParam], xmm0
0x1801059a2  mov     [rbp+350h+var_3B0], r12
0x1801059a6  movups  xmmword ptr [rbp+350h+Msg.time], xmm0
0x1801059aa  movups  [rbp+350h+pSecDesc], xmm0
0x1801059ae  movups  [rbp+350h+var_390], xmm0
0x1801059b2  call    cs:__imp_CoInitializeEx
0x1801059b8  mov     ebx, eax
0x1801059ba  test    eax, eax
0x1801059bc  jns     loc_180105A9C
0x1801059c2  cmp     dword ptr cs:xmmword_180169738, r12d
0x1801059c9  mov     r13d, r12d
0x1801059cc  mov     [rsp+450h+var_3E0], r12d
0x1801059d1  mov     [rsp+450h+var_3D8], eax
0x1801059d5  jz      loc_180105EDB
0x1801059db  mov     rdx, 4000000000000800h; unsigned __int64
0x1801059e5  test    qword ptr cs:xmmword_180169738+8, rdx
0x1801059ec  jz      loc_180105EDB
0x1801059f2  mov     rax, cs:qword_180169748
0x1801059f9  and     rax, rdx
0x1801059fc  cmp     cs:qword_180169748, rax
0x180105a03  jnz     loc_180105EDB
0x180105a09  lea     rcx, [rbp+350h+var_340]; unsigned __int16 *
0x180105a0d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180105a12  lea     rax, [rbp+350h+var_340]
0x180105a16  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180105a1a  inc     rdi
0x180105a1d  cmp     [rax+rdi*2], r12w
0x180105a22  jnz     short loc_180105A1A
0x180105a24  lea     rax, [rbp+350h+var_340]
0x180105a28  lea     ecx, [rdi+rdi]
0x180105a2b  add     rcx, 2
0x180105a2f  lea     r9, [rsp+450h+var_3D8]
0x180105a34  mov     [rsp+450h+var_3F0], rcx
0x180105a39  lea     rdx, PLA_EVENT_ERROR
0x180105a40  mov     [rsp+450h+lpParam], rax
0x180105a45  lea     rcx, [rsp+450h+var_3E0]
0x180105a4a  mov     [rsp+450h+hInstance], 0Bh
0x180105a53  lea     rax, aPlahostset; "PlaHostSet"
0x180105a5a  mov     [rsp+450h+hMenu], rax
0x180105a5f  mov     eax, 4
0x180105a64  mov     [rsp+450h+pReserved3], rax
0x180105a69  mov     qword ptr [rsp+450h+dwCapabilities], rcx
0x180105a6e  lea     rcx, byte_180147320
0x180105a75  lea     esi, [rax-3]
0x180105a78  mov     [rsp+450h+pAuthList], rsi
0x180105a7d  lea     r8d, [rax+1]
0x180105a81  mov     qword ptr [rsp+450h+dwImpLevel], rcx
0x180105a86  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180105a8d  mov     qword ptr [rsp+450h+dwAuthnLevel], rax
0x180105a92  call    EventingWriteEvent
0x180105a97  jmp     loc_180105EDB
0x180105a9c  mov     esi, 1
0x180105aa1  lea     r9, [rbp+350h+lpMem]; void **
0x180105aa5  lea     r8, [rbp+350h+var_3C0]; void **
0x180105aa9  mov     r13d, esi
0x180105aac  lea     rdx, [rbp+350h+pDacl]; pDacl
0x180105ab0  lea     rcx, [rbp+350h+pSecDesc]; pSecurityDescriptor
0x180105ab4  call    ?PlaiCreateHostSecurityDescriptor@@YAJPEAXPEAU_ACL@@PEAPEAX2@Z; PlaiCreateHostSecurityDescriptor(void *,_ACL *,void * *,void * *)
0x180105ab9  mov     ebx, eax
0x180105abb  xor     eax, eax
0x180105abd  test    ebx, ebx
0x180105abf  jns     short loc_180105B35
0x180105ac1  xor     r14d, r14d
0x180105ac4  mov     [rsp+450h+var_3E0], ebx
0x180105ac8  cmp     dword ptr cs:xmmword_180169738, r14d
0x180105acf  mov     [rsp+450h+var_3D8], r14d
0x180105ad4  jz      loc_180105EAD
0x180105ada  mov     rdx, 4000000000000800h; unsigned __int64
0x180105ae4  test    qword ptr cs:xmmword_180169738+8, rdx
0x180105aeb  jz      loc_180105EAD
0x180105af1  mov     rax, cs:qword_180169748
0x180105af8  and     rax, rdx
0x180105afb  cmp     cs:qword_180169748, rax
0x180105b02  jnz     loc_180105EAD
0x180105b08  lea     rcx, [rbp+350h+var_2C0]; unsigned __int16 *
0x180105b0f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180105b14  lea     rax, [rbp+350h+var_2C0]
0x180105b1b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180105b1f  inc     rdi
0x180105b22  cmp     [rax+rdi*2], r14w
0x180105b27  jnz     short loc_180105B1F
0x180105b29  lea     rax, [rbp+350h+var_2C0]
0x180105b30  jmp     loc_180105E41
0x180105b35  mov     [rsp+450h+pReserved3], rax; pReserved3
0x180105b3a  lea     rcx, [rbp+350h+pSecDesc]; pSecDesc
0x180105b3e  mov     [rsp+450h+dwCapabilities], 3020h; dwCapabilities
0x180105b46  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180105b4a  mov     [rsp+450h+pAuthList], rax; pAuthList
0x180105b4f  xor     r9d, r9d; pReserved1
0x180105b52  mov     [rsp+450h+dwImpLevel], 3; dwImpLevel
0x180105b5a  xor     r8d, r8d; asAuthSvc
0x180105b5d  mov     edx, edi; cAuthSvc
0x180105b5f  mov     [rsp+450h+dwAuthnLevel], 6; dwAuthnLevel
0x180105b67  call    cs:__imp_CoInitializeSecurity
0x180105b6d  mov     ebx, eax
0x180105b6f  test    eax, eax
0x180105b71  jns     short loc_180105BE3
0x180105b73  xor     r14d, r14d
0x180105b76  mov     [rsp+450h+var_3E0], eax
0x180105b7a  cmp     dword ptr cs:xmmword_180169738, r14d
0x180105b81  mov     [rsp+450h+var_3D8], r14d
0x180105b86  jz      loc_180105EAD
0x180105b8c  mov     rdx, 4000000000000800h; unsigned __int64
0x180105b96  test    qword ptr cs:xmmword_180169738+8, rdx
0x180105b9d  jz      loc_180105EAD
0x180105ba3  mov     rax, cs:qword_180169748
0x180105baa  and     rax, rdx
0x180105bad  cmp     cs:qword_180169748, rax
0x180105bb4  jnz     loc_180105EAD
0x180105bba  lea     rcx, [rbp+350h+var_240]; unsigned __int16 *
0x180105bc1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180105bc6  lea     rax, [rbp+350h+var_240]
0x180105bcd  inc     rdi
0x180105bd0  cmp     [rax+rdi*2], r14w
0x180105bd5  jnz     short loc_180105BCD
0x180105bd7  lea     rax, [rbp+350h+var_240]
0x180105bde  jmp     loc_180105E41
0x180105be3  mov     eax, 80000000h
0x180105be8  lea     r8, WindowName; "PLAWnd"
0x180105bef  xor     ebx, ebx
0x180105bf1  lea     rdx, ClassName; "STATIC"
0x180105bf8  mov     [rsp+450h+lpParam], rbx; lpParam
0x180105bfd  xor     r9d, r9d; dwStyle
0x180105c00  mov     [rsp+450h+hInstance], rbx; hInstance
0x180105c05  xor     ecx, ecx; dwExStyle
0x180105c07  mov     [rsp+450h+hMenu], rbx; hMenu
0x180105c0c  mov     [rsp+450h+pReserved3], rbx; hWndParent
0x180105c11  mov     [rsp+450h+dwCapabilities], eax; nHeight
0x180105c15  mov     dword ptr [rsp+450h+pAuthList], eax; nWidth
0x180105c19  mov     [rsp+450h+dwImpLevel], eax; Y
0x180105c1d  mov     [rsp+450h+dwAuthnLevel], eax; X
0x180105c21  call    cs:__imp_CreateWindowExW
0x180105c27  mov     r12, rax
0x180105c2a  test    rax, rax
0x180105c2d  jnz     loc_180105CB8
0x180105c33  call    cs:__imp_GetLastError
0x180105c39  xor     r14d, r14d
0x180105c3c  mov     ebx, eax
0x180105c3e  test    eax, eax
0x180105c40  jle     short loc_180105C4B
0x180105c42  movzx   ebx, ax
0x180105c45  or      ebx, 80070000h
0x180105c4b  cmp     dword ptr cs:xmmword_180169738, r14d
0x180105c52  mov     [rsp+450h+var_3D8], r14d
0x180105c57  mov     [rsp+450h+var_3E0], ebx
0x180105c5b  jz      loc_180105EAD
0x180105c61  mov     rdx, 4000000000000800h; unsigned __int64
0x180105c6b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180105c72  jz      loc_180105EAD
0x180105c78  mov     rax, cs:qword_180169748
0x180105c7f  and     rax, rdx
0x180105c82  cmp     cs:qword_180169748, rax
0x180105c89  jnz     loc_180105EAD
0x180105c8f  lea     rcx, [rbp+350h+var_1C0]; unsigned __int16 *
0x180105c96  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180105c9b  lea     rax, [rbp+350h+var_1C0]
0x180105ca2  inc     rdi
0x180105ca5  cmp     [rax+rdi*2], r14w
0x180105caa  jnz     short loc_180105CA2
0x180105cac  lea     rax, [rbp+350h+var_1C0]
0x180105cb3  jmp     loc_180105E41
0x180105cb8  mov     edx, 7Ch ; '|'; Ch
0x180105cbd  mov     rcx, r14; Str
0x180105cc0  call    cs:__imp_wcschr
0x180105cc6  test    rax, rax
0x180105cc9  jz      short loc_180105CD7
0x180105ccb  lea     rdx, [rax+2]
0x180105ccf  mov     [rax], bx
0x180105cd2  test    rdx, rdx
0x180105cd5  jnz     short loc_180105CDA
0x180105cd7  mov     rdx, r14; unsigned __int16 *
0x180105cda  lea     rax, [rbp+350h+var_3B0]
0x180105cde  mov     rcx, r15; unsigned __int16 *
0x180105ce1  lea     r9, [rbp+350h+pHandles]; void **
0x180105ce5  mov     qword ptr [rsp+450h+dwAuthnLevel], rax; unsigned __int64 *
0x180105cea  lea     r8, [rbp+350h+var_3B8]; void **
0x180105cee  call    ?PlaStartDataCollectorSet@@YAJPEBG0PEAPEAX1PEA_K@Z; PlaStartDataCollectorSet(ushort const *,ushort const *,void * *,void * *,unsigned __int64 *)
0x180105cf3  xor     r14d, r14d
0x180105cf6  mov     ebx, eax
0x180105cf8  test    eax, eax
0x180105cfa  jns     short loc_180105D69
0x180105cfc  cmp     dword ptr cs:xmmword_180169738, r14d
0x180105d03  mov     [rsp+450h+var_3D8], r14d
0x180105d08  mov     [rsp+450h+var_3E0], eax
0x180105d0c  jz      loc_180105EAD
0x180105d12  mov     rdx, 4000000000000800h; unsigned __int64
0x180105d1c  test    qword ptr cs:xmmword_180169738+8, rdx
0x180105d23  jz      loc_180105EAD
0x180105d29  mov     rax, cs:qword_180169748
0x180105d30  and     rax, rdx
0x180105d33  cmp     cs:qword_180169748, rax
0x180105d3a  jnz     loc_180105EAD
0x180105d40  lea     rcx, [rbp+350h+var_140]; unsigned __int16 *
0x180105d47  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180105d4c  lea     rax, [rbp+350h+var_140]
0x180105d53  inc     rdi
0x180105d56  cmp     [rax+rdi*2], r14w
0x180105d5b  jnz     short loc_180105D53
0x180105d5d  lea     rax, [rbp+350h+var_140]
0x180105d64  jmp     loc_180105E41
0x180105d69  or      r15d, 0FFFFFFFFh
0x180105d6d  xor     r9d, r9d; wMsgFilterMax
0x180105d70  mov     [rsp+450h+dwAuthnLevel], esi; wRemoveMsg
0x180105d74  xor     r8d, r8d; wMsgFilterMin
0x180105d77  lea     rcx, [rbp+350h+Msg]; lpMsg
0x180105d7b  xor     edx, edx; hWnd
0x180105d7d  call    cs:__imp_PeekMessageW
0x180105d83  test    eax, eax
0x180105d85  jz      short loc_180105D9D
0x180105d87  cmp     [rbp+350h+Msg.message], 10h
0x180105d8b  jz      loc_180105EAD
0x180105d91  lea     rcx, [rbp+350h+Msg]; lpMsg
0x180105d95  call    cs:__imp_DispatchMessageW
0x180105d9b  jmp     short loc_180105D6D
0x180105d9d  mov     r9d, r15d; dwMilliseconds
0x180105da0  mov     [rsp+450h+dwAuthnLevel], 1CFFh; dwWakeMask
0x180105da8  xor     r8d, r8d; fWaitAll
0x180105dab  lea     rdx, [rbp+350h+pHandles]; pHandles
0x180105daf  mov     ecx, esi; nCount
0x180105db1  call    cs:__imp_MsgWaitForMultipleObjects
0x180105db7  test    eax, eax
0x180105db9  jz      loc_180105EAD
0x180105dbf  cmp     eax, r15d
0x180105dc2  jnz     short loc_180105D6D
0x180105dc4  call    cs:__imp_GetLastError
0x180105dca  mov     ebx, eax
0x180105dcc  test    eax, eax
0x180105dce  jle     short loc_180105DD9
0x180105dd0  movzx   ebx, ax
0x180105dd3  or      ebx, 80070000h
0x180105dd9  cmp     dword ptr cs:xmmword_180169738, r14d
0x180105de0  mov     [rsp+450h+var_3D8], r14d
0x180105de5  mov     [rsp+450h+var_3E0], ebx
0x180105de9  jz      loc_180105EAD
0x180105def  mov     rdx, 4000000000000800h; unsigned __int64
0x180105df9  test    qword ptr cs:xmmword_180169738+8, rdx
0x180105e00  jz      loc_180105EAD
0x180105e06  mov     rax, cs:qword_180169748
0x180105e0d  and     rax, rdx
0x180105e10  cmp     cs:qword_180169748, rax
0x180105e17  jnz     loc_180105EAD
0x180105e1d  lea     rcx, [rbp+350h+var_C0]; unsigned __int16 *
0x180105e24  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180105e29  lea     rax, [rbp+350h+var_C0]
0x180105e30  inc     rdi
0x180105e33  cmp     [rax+rdi*2], r14w
0x180105e38  jnz     short loc_180105E30
0x180105e3a  lea     rax, [rbp+350h+var_C0]
0x180105e41  lea     ecx, [rdi+rdi]
0x180105e44  add     rcx, 2
0x180105e48  lea     r9, [rsp+450h+var_3E0]
0x180105e4d  mov     [rsp+450h+var_3F0], rcx
0x180105e52  lea     rdx, PLA_EVENT_ERROR
0x180105e59  mov     [rsp+450h+lpParam], rax
0x180105e5e  lea     rcx, [rsp+450h+var_3D8]
0x180105e63  mov     [rsp+450h+hInstance], 0Bh
0x180105e6c  lea     rax, aPlahostset; "PlaHostSet"
0x180105e73  mov     [rsp+450h+hMenu], rax
0x180105e78  mov     eax, 4
0x180105e7d  mov     [rsp+450h+pReserved3], rax
0x180105e82  mov     qword ptr [rsp+450h+dwCapabilities], rcx
0x180105e87  lea     rcx, byte_180147320
0x180105e8e  mov     [rsp+450h+pAuthList], rsi
0x180105e93  mov     qword ptr [rsp+450h+dwImpLevel], rcx
0x180105e98  lea     r8d, [rax+1]
0x180105e9c  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180105ea3  mov     qword ptr [rsp+450h+dwAuthnLevel], rax
0x180105ea8  call    EventingWriteEvent
0x180105ead  mov     rcx, [rbp+350h+lpMem]; lpMem
0x180105eb1  test    rcx, rcx
0x180105eb4  jz      short loc_180105EBD
0x180105eb6  mov     edx, esi; int
0x180105eb8  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
  ... truncated ...
```
