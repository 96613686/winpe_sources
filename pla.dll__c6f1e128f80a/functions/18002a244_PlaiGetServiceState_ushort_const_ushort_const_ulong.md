# PlaiGetServiceState(ushort const *,ushort const *,ulong *)

- ea: `0x18002a244`
- end: `0x18002a5c2`
- name: `?PlaiGetServiceState@@YAJPEBG0PEAK@Z`
- size: `894`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800e23b4`
- `0x1800eb21c`
- `0x1800ee324`
- `0x1800fed14`
- `0x180130e30`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002a244`
- `0x18002b3a0`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4dd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a4a2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a4ab`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a4a2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002a4ab`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002a290`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002a290`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002a396`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002a396`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002a48c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002a48c`

## string_xrefs

- `0x18002a342`: `PlaiGetServiceState`
- `0x18002a446`: `PlaiGetServiceState`
- `0x18002a580`: `PlaiGetServiceState`

## pseudocode

```c
__int64 __fastcall PlaiGetServiceState(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned int *a3)
{
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // r14
  DWORD v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rax
  SC_HANDLE v10; // rax
  SC_HANDLE v11; // rdi
  DWORD LastError; // eax
  __int64 v13; // rax
  DWORD v15; // eax
  int v16; // eax
  __int64 v17; // rax
  int v18; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v19; // [rsp+78h] [rbp-88h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v21[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v22[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v23[64]; // [rsp+1A0h] [rbp+A0h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v5 = OpenSCManagerW(a1, 0, 1u);
  v6 = v5;
  if ( v5 )
  {
    v10 = OpenServiceW(v5, a2, 4u);
    v11 = v10;
    if ( !v10 )
    {
      LastError = GetLastError();
      v8 = PlaiHResultFromWin32(LastError);
      v19 = 0;
      v18 = v8;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v22, 0x4000000000000800uLL);
        v13 = -1;
        do
          ++v13;
        while ( v22[v13] );
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v18,
          4,
          qword_180147320,
          1,
          &v19,
          4,
          "PlaiGetServiceState",
          20);
      }
      goto LABEL_19;
    }
    if ( QueryServiceStatus(v10, &ServiceStatus) )
    {
      v8 = 0;
    }
    else
    {
      v15 = GetLastError();
      v16 = PlaiHResultFromWin32(v15);
      v8 = v16;
      if ( v16 < 0 )
      {
        v19 = 0;
        v18 = v16;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v23, 0x4000000000000800uLL);
          v17 = -1;
          do
            ++v17;
          while ( v23[v17] );
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_ERROR,
            5,
            &v18,
            4,
            qword_180147320,
            1,
            &v19,
            4,
            "PlaiGetServiceState",
            20);
        }
        goto LABEL_18;
      }
    }
    *a3 = ServiceStatus.dwCurrentState;
LABEL_18:
    CloseServiceHandle(v11);
LABEL_19:
    CloseServiceHandle(v6);
    return v8;
  }
  v7 = GetLastError();
  v8 = PlaiHResultFromWin32(v7);
  v18 = 0;
  v19 = v8;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v21, 0x4000000000000800uLL);
    v9 = -1;
    do
      ++v9;
    while ( v21[v9] );
    EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v19, 4, qword_180147320, 1, &v18, 4, "PlaiGetServiceState", 20);
  }
  return v8;
}

```

## disassembly

```asm
0x18002a244  mov     [rsp-8+arg_18], rbx
0x18002a249  push    rbp
0x18002a24a  push    rsi
0x18002a24b  push    rdi
0x18002a24c  push    r12
0x18002a24e  push    r13
0x18002a250  push    r14
0x18002a252  push    r15
0x18002a254  lea     rbp, [rsp-130h]
0x18002a25c  sub     rsp, 230h
0x18002a263  mov     rax, cs:__security_cookie
0x18002a26a  xor     rax, rsp
0x18002a26d  mov     [rbp+160h+var_40], rax
0x18002a274  xorps   xmm0, xmm0
0x18002a277  mov     r15, r8
0x18002a27a  mov     rbx, rdx
0x18002a27d  mov     r13d, 1
0x18002a283  movups  xmmword ptr [rbp+160h+ServiceStatus.dwServiceType], xmm0
0x18002a287  mov     r8d, r13d; dwDesiredAccess
0x18002a28a  xor     edx, edx; lpDatabaseName
0x18002a28c  movups  xmmword ptr [rbp+160h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002a290  call    cs:__imp_OpenSCManagerW
0x18002a296  xor     r12d, r12d
0x18002a299  mov     r14, rax
0x18002a29c  test    rax, rax
0x18002a29f  jnz     loc_18002A388
0x18002a2a5  call    cs:__imp_GetLastError
0x18002a2ab  mov     ecx, eax; unsigned int
0x18002a2ad  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18002a2b2  cmp     dword ptr cs:xmmword_180169738, r12d
0x18002a2b9  mov     ebx, eax
0x18002a2bb  mov     [rsp+260h+var_1F0], r12d
0x18002a2c0  mov     [rsp+260h+var_1E8], eax
0x18002a2c4  jz      loc_18002A4B1
0x18002a2ca  mov     rdx, 4000000000000800h; unsigned __int64
0x18002a2d4  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002a2db  jz      loc_18002A4B1
0x18002a2e1  mov     rax, cs:qword_180169748
0x18002a2e8  and     rax, rdx
0x18002a2eb  cmp     cs:qword_180169748, rax
0x18002a2f2  jnz     loc_18002A4B1
0x18002a2f8  lea     rcx, [rbp+160h+var_1C0]; unsigned __int16 *
0x18002a2fc  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002a301  lea     rcx, [rbp+160h+var_1C0]
0x18002a305  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a309  inc     rax
0x18002a30c  cmp     [rcx+rax*2], r12w
0x18002a311  jnz     short loc_18002A309
0x18002a313  lea     ecx, [rax+rax]
0x18002a316  mov     esi, 4
0x18002a31b  add     rcx, 2
0x18002a31f  lea     rax, [rbp+160h+var_1C0]
0x18002a323  mov     [rsp+260h+var_200], rcx
0x18002a328  lea     r9, [rsp+260h+var_1E8]
0x18002a32d  mov     [rsp+260h+var_208], rax
0x18002a332  lea     rdx, PLA_EVENT_ERROR
0x18002a339  mov     [rsp+260h+var_210], 14h
0x18002a342  lea     rax, aPlaigetservice; "PlaiGetServiceState"
0x18002a349  mov     [rsp+260h+var_218], rax
0x18002a34e  lea     r8d, [rsi+1]
0x18002a352  mov     [rsp+260h+var_220], rsi
0x18002a357  lea     rax, [rsp+260h+var_1F0]
0x18002a35c  mov     [rsp+260h+var_228], rax
0x18002a361  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18002a368  lea     rax, qword_180147320
0x18002a36f  mov     [rsp+260h+var_230], r13
0x18002a374  mov     [rsp+260h+var_238], rax
0x18002a379  mov     [rsp+260h+var_240], rsi
0x18002a37e  call    EventingWriteEvent
0x18002a383  jmp     loc_18002A4B1
0x18002a388  mov     esi, 4
0x18002a38d  mov     rdx, rbx; lpServiceName
0x18002a390  mov     r8d, esi; dwDesiredAccess
0x18002a393  mov     rcx, r14; hSCManager
0x18002a396  call    cs:__imp_OpenServiceW
0x18002a39c  mov     rdi, rax
0x18002a39f  test    rax, rax
0x18002a3a2  jnz     loc_18002A485
0x18002a3a8  call    cs:__imp_GetLastError
0x18002a3ae  mov     ecx, eax; unsigned int
0x18002a3b0  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18002a3b5  cmp     dword ptr cs:xmmword_180169738, r12d
0x18002a3bc  mov     ebx, eax
0x18002a3be  mov     [rsp+260h+var_1E8], r12d
0x18002a3c3  mov     [rsp+260h+var_1F0], eax
0x18002a3c7  jz      loc_18002A4A8
0x18002a3cd  mov     rdx, 4000000000000800h; unsigned __int64
0x18002a3d7  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002a3de  jz      loc_18002A4A8
0x18002a3e4  mov     rax, cs:qword_180169748
0x18002a3eb  and     rax, rdx
0x18002a3ee  cmp     cs:qword_180169748, rax
0x18002a3f5  jnz     loc_18002A4A8
0x18002a3fb  lea     rcx, [rbp+160h+var_140]; unsigned __int16 *
0x18002a3ff  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002a404  lea     rcx, [rbp+160h+var_140]
0x18002a408  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a40c  inc     rax
0x18002a40f  cmp     [rcx+rax*2], r12w
0x18002a414  jnz     short loc_18002A40C
0x18002a416  lea     ecx, [rax+rax]
0x18002a419  mov     r8d, 5
0x18002a41f  add     rcx, 2
0x18002a423  lea     rax, [rbp+160h+var_140]
0x18002a427  mov     [rsp+260h+var_200], rcx
0x18002a42c  lea     r9, [rsp+260h+var_1F0]
0x18002a431  mov     [rsp+260h+var_208], rax
0x18002a436  lea     rdx, PLA_EVENT_ERROR
0x18002a43d  mov     [rsp+260h+var_210], 14h
0x18002a446  lea     rax, aPlaigetservice; "PlaiGetServiceState"
0x18002a44d  mov     [rsp+260h+var_218], rax
0x18002a452  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18002a459  mov     [rsp+260h+var_220], rsi
0x18002a45e  lea     rax, [rsp+260h+var_1E8]
0x18002a463  mov     [rsp+260h+var_228], rax
0x18002a468  lea     rax, qword_180147320
0x18002a46f  mov     [rsp+260h+var_230], r13
0x18002a474  mov     [rsp+260h+var_238], rax
0x18002a479  mov     [rsp+260h+var_240], rsi
0x18002a47e  call    EventingWriteEvent
0x18002a483  jmp     short loc_18002A4A8
0x18002a485  lea     rdx, [rbp+160h+ServiceStatus]; lpServiceStatus
0x18002a489  mov     rcx, rdi; hService
0x18002a48c  call    cs:__imp_QueryServiceStatus
0x18002a492  test    eax, eax
0x18002a494  jz      short loc_18002A4DD
0x18002a496  mov     ebx, r12d
0x18002a499  mov     ecx, [rbp+160h+ServiceStatus.dwCurrentState]
0x18002a49c  mov     [r15], ecx
0x18002a49f  mov     rcx, rdi; hSCObject
0x18002a4a2  call    cs:__imp_CloseServiceHandle
0x18002a4a8  mov     rcx, r14; hSCObject
0x18002a4ab  call    cs:__imp_CloseServiceHandle
0x18002a4b1  mov     eax, ebx
0x18002a4b3  mov     rcx, [rbp+160h+var_40]
0x18002a4ba  xor     rcx, rsp; StackCookie
0x18002a4bd  call    __security_check_cookie
0x18002a4c2  mov     rbx, [rsp+260h+arg_18]
0x18002a4ca  add     rsp, 230h
0x18002a4d1  pop     r15
0x18002a4d3  pop     r14
0x18002a4d5  pop     r13
0x18002a4d7  pop     r12
0x18002a4d9  pop     rdi
0x18002a4da  pop     rsi
0x18002a4db  pop     rbp
0x18002a4dc  retn
0x18002a4dd  call    cs:__imp_GetLastError
0x18002a4e3  mov     ecx, eax; unsigned int
0x18002a4e5  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18002a4ea  mov     ebx, eax
0x18002a4ec  test    eax, eax
0x18002a4ee  jns     short loc_18002A499
0x18002a4f0  cmp     dword ptr cs:xmmword_180169738, r12d
0x18002a4f7  mov     [rsp+260h+var_1E8], r12d
0x18002a4fc  mov     [rsp+260h+var_1F0], eax
0x18002a500  jz      short loc_18002A49F
0x18002a502  mov     rdx, 4000000000000800h; unsigned __int64
0x18002a50c  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002a513  jz      short loc_18002A49F
0x18002a515  mov     rax, cs:qword_180169748
0x18002a51c  and     rax, rdx
0x18002a51f  cmp     cs:qword_180169748, rax
0x18002a526  jnz     loc_18002A49F
0x18002a52c  lea     rcx, [rbp+160h+var_C0]; unsigned __int16 *
0x18002a533  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002a538  lea     rcx, [rbp+160h+var_C0]
0x18002a53f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a543  inc     rax
0x18002a546  cmp     [rcx+rax*2], r12w
0x18002a54b  jnz     short loc_18002A543
0x18002a54d  lea     ecx, [rax+rax]
0x18002a550  mov     r8d, 5
0x18002a556  add     rcx, 2
0x18002a55a  lea     rax, [rbp+160h+var_C0]
0x18002a561  mov     [rsp+260h+var_200], rcx
0x18002a566  lea     r9, [rsp+260h+var_1F0]
0x18002a56b  mov     [rsp+260h+var_208], rax
0x18002a570  lea     rdx, PLA_EVENT_ERROR
0x18002a577  mov     [rsp+260h+var_210], 14h
0x18002a580  lea     rax, aPlaigetservice; "PlaiGetServiceState"
0x18002a587  mov     [rsp+260h+var_218], rax
0x18002a58c  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18002a593  mov     [rsp+260h+var_220], rsi
0x18002a598  lea     rax, [rsp+260h+var_1E8]
0x18002a59d  mov     [rsp+260h+var_228], rax
0x18002a5a2  lea     rax, qword_180147320
0x18002a5a9  mov     [rsp+260h+var_230], r13
0x18002a5ae  mov     [rsp+260h+var_238], rax
0x18002a5b3  mov     [rsp+260h+var_240], rsi
0x18002a5b8  call    EventingWriteEvent
0x18002a5bd  jmp     loc_18002A49F
```
