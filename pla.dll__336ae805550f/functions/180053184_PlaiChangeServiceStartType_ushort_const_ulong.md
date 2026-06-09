# PlaiChangeServiceStartType(ushort const *,ulong)

- ea: `0x180053184`
- end: `0x18005351c`
- name: `?PlaiChangeServiceStartType@@YAJPEBGK@Z`
- size: `920`
- prototype: `int(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800a8040`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x180053184`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800531d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800532d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800533fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800531d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800532d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800533fa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800534ec`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800534f5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800534ec`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800534f5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800531bc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800531bc`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800532c4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800532c4`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800533e8`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800533e8`

## string_xrefs

- `0x180053267`: `PlaiChangeServiceStartType`
- `0x18005336c`: `PlaiChangeServiceStartType`
- `0x1800534a1`: `PlaiChangeServiceStartType`

## pseudocode

```c
__int64 __fastcall PlaiChangeServiceStartType(const unsigned __int16 *a1, DWORD a2)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  DWORD v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rdi
  DWORD v10; // eax
  __int64 v11; // rax
  DWORD LastError; // eax
  int v13; // eax
  __int64 v14; // rax
  int v16; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v17; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v18[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v19[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v20[64]; // [rsp+180h] [rbp+80h] BYREF

  v3 = OpenSCManagerW(0, 0, 1u);
  v4 = v3;
  if ( v3 )
  {
    v8 = OpenServiceW(v3, L"schedule", 2u);
    v9 = v8;
    if ( v8 )
    {
      if ( ChangeServiceConfigW(v8, 0xFFFFFFFF, a2, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      {
        v6 = 0;
      }
      else
      {
        LastError = GetLastError();
        v13 = PlaiHResultFromWin32(LastError);
        v6 = v13;
        if ( v13 < 0 )
        {
          v17 = 0;
          v16 = v13;
          if ( (_DWORD)xmmword_180169738 )
          {
            if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v20, 0x4000000000000800uLL);
              v14 = -1;
              do
                ++v14;
              while ( v20[v14] );
              EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v16, 4, byte_180147320, 1, &v17, 4);
            }
          }
        }
      }
      CloseServiceHandle(v9);
    }
    else
    {
      v10 = GetLastError();
      v6 = PlaiHResultFromWin32(v10);
      v17 = 0;
      v16 = v6;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v19, 0x4000000000000800uLL);
        v11 = -1;
        do
          ++v11;
        while ( v19[v11] );
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v16, 4, byte_180147320, 1, &v17, 4);
      }
    }
    CloseServiceHandle(v4);
  }
  else
  {
    v5 = GetLastError();
    v6 = PlaiHResultFromWin32(v5);
    v16 = 0;
    v17 = v6;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v18, 0x4000000000000800uLL);
      v7 = -1;
      do
        ++v7;
      while ( v18[v7] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v17, 4, byte_180147320, 1, &v16, 4);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180053184  push    rbp
0x180053186  push    rbx
0x180053187  push    rsi
0x180053188  push    rdi
0x180053189  push    r14
0x18005318b  push    r15
0x18005318d  lea     rbp, [rsp-118h]
0x180053195  sub     rsp, 218h
0x18005319c  mov     rax, cs:__security_cookie
0x1800531a3  xor     rax, rsp
0x1800531a6  mov     [rbp+140h+var_40], rax
0x1800531ad  mov     ebx, edx
0x1800531af  mov     r15d, 1
0x1800531b5  mov     r8d, r15d; dwDesiredAccess
0x1800531b8  xor     edx, edx; lpDatabaseName
0x1800531ba  xor     ecx, ecx; lpMachineName
0x1800531bc  call    cs:__imp_OpenSCManagerW
0x1800531c2  xor     r14d, r14d
0x1800531c5  mov     rsi, rax
0x1800531c8  test    rax, rax
0x1800531cb  jnz     loc_1800532B4
0x1800531d1  call    cs:__imp_GetLastError
0x1800531d7  mov     ecx, eax; unsigned int
0x1800531d9  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800531de  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800531e5  mov     ebx, eax
0x1800531e7  mov     [rsp+240h+var_1D0], r14d
0x1800531ec  mov     [rsp+240h+var_1C8], eax
0x1800531f0  jz      loc_1800534FB
0x1800531f6  mov     rdx, 4000000000000800h; unsigned __int64
0x180053200  test    qword ptr cs:xmmword_180169738+8, rdx
0x180053207  jz      loc_1800534FB
0x18005320d  mov     rax, cs:qword_180169748
0x180053214  and     rax, rdx
0x180053217  cmp     cs:qword_180169748, rax
0x18005321e  jnz     loc_1800534FB
0x180053224  lea     rcx, [rbp+140h+var_1C0]; unsigned __int16 *
0x180053228  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005322d  lea     rcx, [rbp+140h+var_1C0]
0x180053231  or      rax, 0FFFFFFFFFFFFFFFFh
0x180053235  inc     rax
0x180053238  cmp     [rcx+rax*2], r14w
0x18005323d  jnz     short loc_180053235
0x18005323f  lea     ecx, [rax+rax]
0x180053242  add     rcx, 2
0x180053246  lea     rax, [rbp+140h+var_1C0]
0x18005324a  mov     [rsp+240h+var_1E0], rcx
0x18005324f  lea     r9, [rsp+240h+var_1C8]
0x180053254  mov     [rsp+240h+var_1E8], rax
0x180053259  lea     rcx, [rsp+240h+var_1D0]
0x18005325e  mov     [rsp+240h+lpDisplayName], 1Bh
0x180053267  lea     rax, aPlaichangeserv; "PlaiChangeServiceStartType"
0x18005326e  mov     [rsp+240h+lpPassword], rax
0x180053273  lea     rdx, PLA_EVENT_ERROR
0x18005327a  mov     eax, 4
0x18005327f  mov     [rsp+240h+lpServiceStartName], rax
0x180053284  mov     [rsp+240h+lpDependencies], rcx
0x180053289  lea     rcx, byte_180147320
0x180053290  mov     [rsp+240h+lpdwTagId], r15
0x180053295  mov     [rsp+240h+lpLoadOrderGroup], rcx
0x18005329a  lea     r8d, [rax+1]
0x18005329e  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800532a5  mov     [rsp+240h+lpBinaryPathName], rax
0x1800532aa  call    EventingWriteEvent
0x1800532af  jmp     loc_1800534FB
0x1800532b4  mov     r8d, 2; dwDesiredAccess
0x1800532ba  lea     rdx, ServiceName; "schedule"
0x1800532c1  mov     rcx, rsi; hSCManager
0x1800532c4  call    cs:__imp_OpenServiceW
0x1800532ca  mov     rdi, rax
0x1800532cd  test    rax, rax
0x1800532d0  jnz     loc_1800533B9
0x1800532d6  call    cs:__imp_GetLastError
0x1800532dc  mov     ecx, eax; unsigned int
0x1800532de  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800532e3  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800532ea  mov     ebx, eax
0x1800532ec  mov     [rsp+240h+var_1C8], r14d
0x1800532f1  mov     [rsp+240h+var_1D0], eax
0x1800532f5  jz      loc_1800534F2
0x1800532fb  mov     rdx, 4000000000000800h; unsigned __int64
0x180053305  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005330c  jz      loc_1800534F2
0x180053312  mov     rax, cs:qword_180169748
0x180053319  and     rax, rdx
0x18005331c  cmp     cs:qword_180169748, rax
0x180053323  jnz     loc_1800534F2
0x180053329  lea     rcx, [rbp+140h+var_140]; unsigned __int16 *
0x18005332d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180053332  lea     rcx, [rbp+140h+var_140]
0x180053336  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005333a  inc     rax
0x18005333d  cmp     [rcx+rax*2], r14w
0x180053342  jnz     short loc_18005333A
0x180053344  lea     ecx, [rax+rax]
0x180053347  add     rcx, 2
0x18005334b  lea     rax, [rbp+140h+var_140]
0x18005334f  mov     [rsp+240h+var_1E0], rcx
0x180053354  lea     r9, [rsp+240h+var_1D0]
0x180053359  mov     [rsp+240h+var_1E8], rax
0x18005335e  lea     rcx, [rsp+240h+var_1C8]
0x180053363  mov     [rsp+240h+lpDisplayName], 1Bh
0x18005336c  lea     rax, aPlaichangeserv; "PlaiChangeServiceStartType"
0x180053373  mov     [rsp+240h+lpPassword], rax
0x180053378  lea     rdx, PLA_EVENT_ERROR
0x18005337f  mov     eax, 4
0x180053384  mov     [rsp+240h+lpServiceStartName], rax
0x180053389  mov     [rsp+240h+lpDependencies], rcx
0x18005338e  lea     rcx, byte_180147320
0x180053395  mov     [rsp+240h+lpdwTagId], r15
0x18005339a  mov     [rsp+240h+lpLoadOrderGroup], rcx
0x18005339f  lea     r8d, [rax+1]
0x1800533a3  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800533aa  mov     [rsp+240h+lpBinaryPathName], rax
0x1800533af  call    EventingWriteEvent
0x1800533b4  jmp     loc_1800534F2
0x1800533b9  mov     [rsp+240h+lpDisplayName], r14; lpDisplayName
0x1800533be  or      edx, 0FFFFFFFFh; dwServiceType
0x1800533c1  mov     [rsp+240h+lpPassword], r14; lpPassword
0x1800533c6  mov     r9d, edx; dwErrorControl
0x1800533c9  mov     [rsp+240h+lpServiceStartName], r14; lpServiceStartName
0x1800533ce  mov     r8d, ebx; dwStartType
0x1800533d1  mov     [rsp+240h+lpDependencies], r14; lpDependencies
0x1800533d6  mov     rcx, rdi; hService
0x1800533d9  mov     [rsp+240h+lpdwTagId], r14; lpdwTagId
0x1800533de  mov     [rsp+240h+lpLoadOrderGroup], r14; lpLoadOrderGroup
0x1800533e3  mov     [rsp+240h+lpBinaryPathName], r14; lpBinaryPathName
0x1800533e8  call    cs:__imp_ChangeServiceConfigW
0x1800533ee  test    eax, eax
0x1800533f0  jz      short loc_1800533FA
0x1800533f2  mov     ebx, r14d
0x1800533f5  jmp     loc_1800534E9
0x1800533fa  call    cs:__imp_GetLastError
0x180053400  mov     ecx, eax; unsigned int
0x180053402  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180053407  mov     ebx, eax
0x180053409  test    eax, eax
0x18005340b  jns     loc_1800534E9
0x180053411  cmp     dword ptr cs:xmmword_180169738, r14d
0x180053418  mov     [rsp+240h+var_1C8], r14d
0x18005341d  mov     [rsp+240h+var_1D0], eax
0x180053421  jz      loc_1800534E9
0x180053427  mov     rdx, 4000000000000800h; unsigned __int64
0x180053431  test    qword ptr cs:xmmword_180169738+8, rdx
0x180053438  jz      loc_1800534E9
0x18005343e  mov     rax, cs:qword_180169748
0x180053445  and     rax, rdx
0x180053448  cmp     cs:qword_180169748, rax
0x18005344f  jnz     loc_1800534E9
0x180053455  lea     rcx, [rbp+140h+var_C0]; unsigned __int16 *
0x18005345c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180053461  lea     rcx, [rbp+140h+var_C0]
0x180053468  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005346c  inc     rax
0x18005346f  cmp     [rcx+rax*2], r14w
0x180053474  jnz     short loc_18005346C
0x180053476  lea     ecx, [rax+rax]
0x180053479  add     rcx, 2
0x18005347d  lea     rax, [rbp+140h+var_C0]
0x180053484  mov     [rsp+240h+var_1E0], rcx
0x180053489  lea     r9, [rsp+240h+var_1D0]
0x18005348e  mov     [rsp+240h+var_1E8], rax
0x180053493  lea     rcx, [rsp+240h+var_1C8]
0x180053498  mov     [rsp+240h+lpDisplayName], 1Bh
0x1800534a1  lea     rax, aPlaichangeserv; "PlaiChangeServiceStartType"
0x1800534a8  mov     [rsp+240h+lpPassword], rax
0x1800534ad  lea     rdx, PLA_EVENT_ERROR
0x1800534b4  mov     eax, 4
0x1800534b9  mov     [rsp+240h+lpServiceStartName], rax
0x1800534be  mov     [rsp+240h+lpDependencies], rcx
0x1800534c3  lea     rcx, byte_180147320
0x1800534ca  mov     [rsp+240h+lpdwTagId], r15
0x1800534cf  mov     [rsp+240h+lpLoadOrderGroup], rcx
0x1800534d4  lea     r8d, [rax+1]
0x1800534d8  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800534df  mov     [rsp+240h+lpBinaryPathName], rax
0x1800534e4  call    EventingWriteEvent
0x1800534e9  mov     rcx, rdi; hSCObject
0x1800534ec  call    cs:__imp_CloseServiceHandle
0x1800534f2  mov     rcx, rsi; hSCObject
0x1800534f5  call    cs:__imp_CloseServiceHandle
0x1800534fb  mov     eax, ebx
0x1800534fd  mov     rcx, [rbp+140h+var_40]
0x180053504  xor     rcx, rsp; StackCookie
0x180053507  call    __security_check_cookie
0x18005350c  add     rsp, 218h
0x180053513  pop     r15
0x180053515  pop     r14
0x180053517  pop     rdi
0x180053518  pop     rsi
0x180053519  pop     rbx
0x18005351a  pop     rbp
0x18005351b  retn
```
