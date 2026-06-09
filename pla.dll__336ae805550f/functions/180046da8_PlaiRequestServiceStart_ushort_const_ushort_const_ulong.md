# PlaiRequestServiceStart(ushort const *,ushort const *,ulong *)

- ea: `0x180046da8`
- end: `0x18004716f`
- name: `?PlaiRequestServiceStart@@YAJPEBG0PEAK@Z`
- size: `967`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800eb21c`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x180046da8`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046f69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046f69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047063`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180047023`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180047031`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180047023`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180047031`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180046df6`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180046df6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180046ec6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180046ec6`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180046f5b`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180046f5b`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18004700d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18004700d`

## string_xrefs

- `0x180046e9b`: `PlaiRequestServiceStart`
- `0x1800470f8`: `PlaiRequestServiceStart`

## pseudocode

```c
__int64 __fastcall PlaiRequestServiceStart(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned int *a3)
{
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // r14
  SC_HANDLE v7; // rdi
  DWORD v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  int *v11; // r9
  int *v12; // rax
  SC_HANDLE v13; // rax
  DWORD LastError; // eax
  __int64 v15; // rax
  DWORD v16; // eax
  __int64 v17; // rax
  DWORD v19; // eax
  int v20; // eax
  __int64 v21; // rax
  int v22; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v23; // [rsp+78h] [rbp-88h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v25[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v26[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v27[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v28[64]; // [rsp+220h] [rbp+120h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v5 = OpenSCManagerW(0, 0, 1u);
  v6 = v5;
  if ( v5 )
  {
    v13 = OpenServiceW(v5, a2, 0x90u);
    v7 = v13;
    if ( !v13 )
    {
      LastError = GetLastError();
      v9 = PlaiHResultFromWin32(LastError);
      v23 = 0;
      v22 = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_39;
      }
      PlaiWhoAmI(v26, 0x4000000000000800uLL);
      v15 = -1;
      do
        ++v15;
      while ( v26[v15] );
      goto LABEL_37;
    }
    if ( !StartServiceW(v13, 0, 0) )
    {
      v16 = GetLastError();
      v9 = PlaiHResultFromWin32(v16);
      if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147023840 )
      {
        v23 = 0;
        v22 = v9;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_39;
        }
        PlaiWhoAmI(v27, 0x4000000000000800uLL);
        v17 = -1;
        do
          ++v17;
        while ( v27[v17] );
        goto LABEL_37;
      }
    }
    if ( ControlService(v7, 4u, &ServiceStatus) )
    {
      v9 = 0;
    }
    else
    {
      v19 = GetLastError();
      v20 = PlaiHResultFromWin32(v19);
      v9 = v20;
      if ( v20 < 0 )
      {
        v23 = 0;
        v22 = v20;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_39;
        }
        PlaiWhoAmI(v28, 0x4000000000000800uLL);
        v21 = -1;
        do
          ++v21;
        while ( v28[v21] );
LABEL_37:
        v11 = &v22;
        v12 = (int *)&v23;
LABEL_38:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v11, 4, byte_180147320, 1, v12, 4);
        goto LABEL_39;
      }
    }
    *a3 = ServiceStatus.dwCurrentState;
LABEL_27:
    CloseServiceHandle(v7);
    goto LABEL_28;
  }
  v7 = 0;
  v8 = GetLastError();
  v9 = PlaiHResultFromWin32(v8);
  v22 = 0;
  v23 = v9;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v25, 0x4000000000000800uLL);
    v10 = -1;
    do
      ++v10;
    while ( v25[v10] );
    v11 = (int *)&v23;
    v12 = &v22;
    goto LABEL_38;
  }
LABEL_39:
  if ( v9 == -2147023834 || v9 == -2147023843 )
  {
    *a3 = 1;
    v9 = 0;
  }
  if ( v7 )
    goto LABEL_27;
LABEL_28:
  if ( v6 )
    CloseServiceHandle(v6);
  return v9;
}

```

## disassembly

```asm
0x180046da8  mov     [rsp-8+arg_0], rbx
0x180046dad  push    rbp
0x180046dae  push    rsi
0x180046daf  push    rdi
0x180046db0  push    r12
0x180046db2  push    r13
0x180046db4  push    r14
0x180046db6  push    r15
0x180046db8  lea     rbp, [rsp-1B0h]
0x180046dc0  sub     rsp, 2B0h
0x180046dc7  mov     rax, cs:__security_cookie
0x180046dce  xor     rax, rsp
0x180046dd1  mov     [rbp+1E0h+var_40], rax
0x180046dd8  xorps   xmm0, xmm0
0x180046ddb  mov     r15, r8
0x180046dde  mov     rbx, rdx
0x180046de1  mov     r13d, 1
0x180046de7  movups  xmmword ptr [rbp+1E0h+ServiceStatus.dwServiceType], xmm0
0x180046deb  mov     r8d, r13d; dwDesiredAccess
0x180046dee  xor     edx, edx; lpDatabaseName
0x180046df0  xor     ecx, ecx; lpMachineName
0x180046df2  movups  xmmword ptr [rbp+1E0h+ServiceStatus.dwWin32ExitCode], xmm0
0x180046df6  call    cs:__imp_OpenSCManagerW
0x180046dfc  xor     r12d, r12d
0x180046dff  mov     r14, rax
0x180046e02  test    rax, rax
0x180046e05  jnz     loc_180046EBA
0x180046e0b  mov     edi, r12d
0x180046e0e  call    cs:__imp_GetLastError
0x180046e14  mov     ecx, eax; unsigned int
0x180046e16  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180046e1b  cmp     dword ptr cs:xmmword_180169738, r12d
0x180046e22  mov     ebx, eax
0x180046e24  mov     [rsp+2E0h+var_270], r12d
0x180046e29  mov     [rsp+2E0h+var_268], eax
0x180046e2d  jz      loc_18004714B
0x180046e33  mov     rdx, 4000000000000800h; unsigned __int64
0x180046e3d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180046e44  jz      loc_18004714B
0x180046e4a  mov     rax, cs:qword_180169748
0x180046e51  and     rax, rdx
0x180046e54  cmp     cs:qword_180169748, rax
0x180046e5b  jnz     loc_18004714B
0x180046e61  lea     rcx, [rbp+1E0h+var_240]; unsigned __int16 *
0x180046e65  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180046e6a  lea     rcx, [rbp+1E0h+var_240]
0x180046e6e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180046e72  inc     rax
0x180046e75  cmp     [rcx+rax*2], r12w
0x180046e7a  jnz     short loc_180046E72
0x180046e7c  lea     ecx, [rax+rax]
0x180046e7f  mov     esi, 4
0x180046e84  lea     rax, [rbp+1E0h+var_240]
0x180046e88  add     rcx, 2
0x180046e8c  mov     [rsp+2E0h+var_280], rcx
0x180046e91  lea     r9, [rsp+2E0h+var_268]
0x180046e96  mov     [rsp+2E0h+var_288], rax
0x180046e9b  lea     rax, aPlairequestser; "PlaiRequestServiceStart"
0x180046ea2  mov     [rsp+2E0h+var_290], 18h
0x180046eab  mov     [rsp+2E0h+var_298], rax
0x180046eb0  lea     rax, [rsp+2E0h+var_270]
0x180046eb5  jmp     loc_180047112
0x180046eba  mov     r8d, 90h; dwDesiredAccess
0x180046ec0  mov     rdx, rbx; lpServiceName
0x180046ec3  mov     rcx, r14; hSCManager
0x180046ec6  call    cs:__imp_OpenServiceW
0x180046ecc  mov     rdi, rax
0x180046ecf  test    rax, rax
0x180046ed2  jnz     short loc_180046F53
0x180046ed4  call    cs:__imp_GetLastError
0x180046eda  mov     ecx, eax; unsigned int
0x180046edc  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180046ee1  cmp     dword ptr cs:xmmword_180169738, r12d
0x180046ee8  mov     ebx, eax
0x180046eea  mov     [rsp+2E0h+var_268], r12d
0x180046eef  mov     [rsp+2E0h+var_270], eax
0x180046ef3  jz      loc_18004714B
0x180046ef9  mov     rdx, 4000000000000800h; unsigned __int64
0x180046f03  test    qword ptr cs:xmmword_180169738+8, rdx
0x180046f0a  jz      loc_18004714B
0x180046f10  mov     rax, cs:qword_180169748
0x180046f17  and     rax, rdx
0x180046f1a  cmp     cs:qword_180169748, rax
0x180046f21  jnz     loc_18004714B
0x180046f27  lea     rcx, [rbp+1E0h+var_1C0]; unsigned __int16 *
0x180046f2b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180046f30  lea     rcx, [rbp+1E0h+var_1C0]
0x180046f34  or      rax, 0FFFFFFFFFFFFFFFFh
0x180046f38  inc     rax
0x180046f3b  cmp     [rcx+rax*2], r12w
0x180046f40  jnz     short loc_180046F38
0x180046f42  lea     ecx, [rax+rax]
0x180046f45  lea     rax, [rbp+1E0h+var_1C0]
0x180046f49  mov     esi, 4
0x180046f4e  jmp     loc_1800470E5
0x180046f53  xor     r8d, r8d; lpServiceArgVectors
0x180046f56  xor     edx, edx; dwNumServiceArgs
0x180046f58  mov     rcx, rdi; hService
0x180046f5b  call    cs:__imp_StartServiceW
0x180046f61  test    eax, eax
0x180046f63  jnz     loc_180046FFF
0x180046f69  call    cs:__imp_GetLastError
0x180046f6f  mov     ecx, eax; unsigned int
0x180046f71  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180046f76  mov     ecx, 80000000h
0x180046f7b  mov     ebx, eax
0x180046f7d  add     eax, ecx
0x180046f7f  test    ecx, eax
0x180046f81  jnz     short loc_180046FFF
0x180046f83  cmp     ebx, 80070420h
0x180046f89  jz      short loc_180046FFF
0x180046f8b  cmp     dword ptr cs:xmmword_180169738, r12d
0x180046f92  mov     [rsp+2E0h+var_268], r12d
0x180046f97  mov     [rsp+2E0h+var_270], ebx
0x180046f9b  jz      loc_18004714B
0x180046fa1  mov     rdx, 4000000000000800h; unsigned __int64
0x180046fab  test    qword ptr cs:xmmword_180169738+8, rdx
0x180046fb2  jz      loc_18004714B
0x180046fb8  mov     rax, cs:qword_180169748
0x180046fbf  and     rax, rdx
0x180046fc2  cmp     cs:qword_180169748, rax
0x180046fc9  jnz     loc_18004714B
0x180046fcf  lea     rcx, [rbp+1E0h+var_140]; unsigned __int16 *
0x180046fd6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180046fdb  lea     rcx, [rbp+1E0h+var_140]
0x180046fe2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180046fe6  inc     rax
0x180046fe9  cmp     [rcx+rax*2], r12w
0x180046fee  jnz     short loc_180046FE6
0x180046ff0  lea     ecx, [rax+rax]
0x180046ff3  lea     rax, [rbp+1E0h+var_140]
0x180046ffa  jmp     loc_180046F49
0x180046fff  mov     esi, 4
0x180047004  lea     r8, [rbp+1E0h+ServiceStatus]; lpServiceStatus
0x180047008  mov     edx, esi; dwControl
0x18004700a  mov     rcx, rdi; hService
0x18004700d  call    cs:__imp_ControlService
0x180047013  test    eax, eax
0x180047015  jz      short loc_180047063
0x180047017  mov     ebx, r12d
0x18004701a  mov     ecx, [rbp+1E0h+ServiceStatus.dwCurrentState]
0x18004701d  mov     [r15], ecx
0x180047020  mov     rcx, rdi; hSCObject
0x180047023  call    cs:__imp_CloseServiceHandle
0x180047029  test    r14, r14
0x18004702c  jz      short loc_180047037
0x18004702e  mov     rcx, r14; hSCObject
0x180047031  call    cs:__imp_CloseServiceHandle
0x180047037  mov     eax, ebx
0x180047039  mov     rcx, [rbp+1E0h+var_40]
0x180047040  xor     rcx, rsp; StackCookie
0x180047043  call    __security_check_cookie
0x180047048  mov     rbx, [rsp+2E0h+arg_0]
0x180047050  add     rsp, 2B0h
0x180047057  pop     r15
0x180047059  pop     r14
0x18004705b  pop     r13
0x18004705d  pop     r12
0x18004705f  pop     rdi
0x180047060  pop     rsi
0x180047061  pop     rbp
0x180047062  retn
0x180047063  call    cs:__imp_GetLastError
0x180047069  mov     ecx, eax; unsigned int
0x18004706b  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180047070  mov     ebx, eax
0x180047072  test    eax, eax
0x180047074  jns     short loc_18004701A
0x180047076  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004707d  mov     [rsp+2E0h+var_268], r12d
0x180047082  mov     [rsp+2E0h+var_270], eax
0x180047086  jz      loc_18004714B
0x18004708c  mov     rdx, 4000000000000800h; unsigned __int64
0x180047096  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004709d  jz      loc_18004714B
0x1800470a3  mov     rax, cs:qword_180169748
0x1800470aa  and     rax, rdx
0x1800470ad  cmp     cs:qword_180169748, rax
0x1800470b4  jnz     loc_18004714B
0x1800470ba  lea     rcx, [rbp+1E0h+var_C0]; unsigned __int16 *
0x1800470c1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800470c6  lea     rcx, [rbp+1E0h+var_C0]
0x1800470cd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800470d1  inc     rax
0x1800470d4  cmp     [rcx+rax*2], r12w
0x1800470d9  jnz     short loc_1800470D1
0x1800470db  lea     ecx, [rax+rax]
0x1800470de  lea     rax, [rbp+1E0h+var_C0]
0x1800470e5  add     rcx, 2
0x1800470e9  lea     r9, [rsp+2E0h+var_270]
0x1800470ee  mov     [rsp+2E0h+var_280], rcx
0x1800470f3  mov     [rsp+2E0h+var_288], rax
0x1800470f8  lea     rax, aPlairequestser; "PlaiRequestServiceStart"
0x1800470ff  mov     [rsp+2E0h+var_290], 18h
0x180047108  mov     [rsp+2E0h+var_298], rax
0x18004710d  lea     rax, [rsp+2E0h+var_268]
0x180047112  mov     [rsp+2E0h+var_2A0], rsi
0x180047117  lea     rdx, PLA_EVENT_ERROR
0x18004711e  mov     [rsp+2E0h+var_2A8], rax
0x180047123  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004712a  lea     rax, byte_180147320
0x180047131  mov     [rsp+2E0h+var_2B0], r13
0x180047136  mov     [rsp+2E0h+var_2B8], rax
0x18004713b  mov     r8d, 5
0x180047141  mov     [rsp+2E0h+var_2C0], rsi
0x180047146  call    EventingWriteEvent
0x18004714b  cmp     ebx, 80070426h
0x180047151  jz      short loc_18004715B
0x180047153  cmp     ebx, 8007041Dh
0x180047159  jnz     short loc_180047161
0x18004715b  mov     [r15], r13d
0x18004715e  mov     ebx, r12d
0x180047161  test    rdi, rdi
0x180047164  jnz     loc_180047020
0x18004716a  jmp     loc_180047029
```
