# PlaiQueryServiceStartType(ushort const *,ulong *)

- ea: `0x1800a3bcc`
- end: `0x1800a402a`
- name: `?PlaiQueryServiceStartType@@YAJPEBGPEAK@Z`
- size: `1118`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800a8040`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x18002b3a0`
- `0x1800a3bcc`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3c1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3e6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3c1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3e6a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a3fe4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a3fed`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a3fe4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800a3fed`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800a3c0b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800a3c0b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800a3d17`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800a3d17`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800a3e5c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800a3e5c`

## string_xrefs

- `0x1800a3cb5`: `PlaiQueryServiceStartType`
- `0x1800a3dc1`: `PlaiQueryServiceStartType`
- `0x1800a3fa3`: `PlaiQueryServiceStartType`

## pseudocode

```c
__int64 __fastcall PlaiQueryServiceStartType(const unsigned __int16 *a1, unsigned int *a2)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // r15
  DWORD v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  struct _QUERY_SERVICE_CONFIGW *v8; // rdi
  SC_HANDLE v9; // r14
  DWORD v10; // eax
  __int64 v11; // rax
  struct _QUERY_SERVICE_CONFIGW *v12; // rax
  DWORD LastError; // eax
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v20; // [rsp+78h] [rbp-88h] BYREF
  DWORD pcbBytesNeeded[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v22[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v23[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v24[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v25[64]; // [rsp+210h] [rbp+110h] BYREF

  pcbBytesNeeded[0] = 0;
  v3 = OpenSCManagerW(0, 0, 1u);
  v4 = v3;
  if ( v3 )
  {
    v8 = 0;
    v9 = OpenServiceW(v3, L"schedule", 1u);
    if ( v9 )
    {
      pcbBytesNeeded[0] = 1088;
      while ( 1 )
      {
        if ( v8 )
          PlaiFree(v8, 1);
        v12 = (struct _QUERY_SERVICE_CONFIGW *)PlaiAlloc(pcbBytesNeeded[0], 1, 0, byte_180147320, v18);
        v8 = v12;
        if ( !v12 )
          break;
        if ( QueryServiceConfigW(v9, v12, pcbBytesNeeded[0], pcbBytesNeeded) )
        {
          v6 = 0;
          goto LABEL_29;
        }
        LastError = GetLastError();
        v14 = PlaiHResultFromWin32(LastError);
        v6 = v14;
        if ( v14 != -2147024774 )
        {
          if ( v14 < 0 )
          {
            v20 = 0;
            v19 = v14;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v24, 0x4000000000000800uLL);
              v15 = -1;
              do
                ++v15;
              while ( v24[v15] );
              goto LABEL_35;
            }
            goto LABEL_36;
          }
LABEL_29:
          *a2 = v8->dwStartType;
          goto LABEL_36;
        }
      }
      v6 = -2147024882;
      v19 = -2147024882;
      v20 = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v25, 0x4000000000000800uLL);
        v16 = -1;
        do
          ++v16;
        while ( v25[v16] );
LABEL_35:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v19, 4, byte_180147320, 1, &v20, 4);
      }
LABEL_36:
      CloseServiceHandle(v9);
    }
    else
    {
      v10 = GetLastError();
      v6 = PlaiHResultFromWin32(v10);
      v20 = 0;
      v19 = v6;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v23, 0x4000000000000800uLL);
        v11 = -1;
        do
          ++v11;
        while ( v23[v11] );
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v19, 4, byte_180147320, 1, &v20, 4);
      }
    }
    CloseServiceHandle(v4);
    if ( v8 )
      PlaiFree(v8, 1);
  }
  else
  {
    v5 = GetLastError();
    v6 = PlaiHResultFromWin32(v5);
    v19 = 0;
    v20 = v6;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v22, 0x4000000000000800uLL);
      v7 = -1;
      do
        ++v7;
      while ( v22[v7] );
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v20, 4, byte_180147320, 1, &v19, 4);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800a3bcc  push    rbp
0x1800a3bce  push    rbx
0x1800a3bcf  push    rsi
0x1800a3bd0  push    rdi
0x1800a3bd1  push    r12
0x1800a3bd3  push    r13
0x1800a3bd5  push    r14
0x1800a3bd7  push    r15
0x1800a3bd9  lea     rbp, [rsp-1A8h]
0x1800a3be1  sub     rsp, 2A8h
0x1800a3be8  mov     rax, cs:__security_cookie
0x1800a3bef  xor     rax, rsp
0x1800a3bf2  mov     [rbp+1E0h+var_50], rax
0x1800a3bf9  xor     r13d, r13d
0x1800a3bfc  mov     r12, rdx
0x1800a3bff  xor     edx, edx; lpDatabaseName
0x1800a3c01  mov     [rbp+1E0h+pcbBytesNeeded], r13d
0x1800a3c05  xor     ecx, ecx; lpMachineName
0x1800a3c07  lea     r8d, [r13+1]; dwDesiredAccess
0x1800a3c0b  call    cs:__imp_OpenSCManagerW
0x1800a3c11  mov     r15, rax
0x1800a3c14  test    rax, rax
0x1800a3c17  jnz     loc_1800A3D04
0x1800a3c1d  call    cs:__imp_GetLastError
0x1800a3c23  mov     ecx, eax; unsigned int
0x1800a3c25  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800a3c2a  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800a3c31  mov     ebx, eax
0x1800a3c33  mov     [rsp+2E0h+var_270], r13d
0x1800a3c38  mov     [rsp+2E0h+var_268], eax
0x1800a3c3c  jz      loc_1800A4005
0x1800a3c42  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a3c4c  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a3c53  jz      loc_1800A4005
0x1800a3c59  mov     rax, cs:qword_180169748
0x1800a3c60  and     rax, rdx
0x1800a3c63  cmp     cs:qword_180169748, rax
0x1800a3c6a  jnz     loc_1800A4005
0x1800a3c70  lea     rcx, [rbp+1E0h+var_250]; unsigned __int16 *
0x1800a3c74  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a3c79  lea     rcx, [rbp+1E0h+var_250]
0x1800a3c7d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a3c81  inc     rax
0x1800a3c84  cmp     [rcx+rax*2], r13w
0x1800a3c89  jnz     short loc_1800A3C81
0x1800a3c8b  lea     ecx, [rax+rax]
0x1800a3c8e  add     rcx, 2
0x1800a3c92  lea     rax, [rbp+1E0h+var_250]
0x1800a3c96  mov     [rsp+2E0h+var_280], rcx
0x1800a3c9b  lea     rsi, byte_180147320
0x1800a3ca2  mov     [rsp+2E0h+var_288], rax
0x1800a3ca7  lea     rcx, [rsp+2E0h+var_270]
0x1800a3cac  mov     [rsp+2E0h+var_290], 1Ah
0x1800a3cb5  lea     rax, aPlaiqueryservi; "PlaiQueryServiceStartType"
0x1800a3cbc  mov     [rsp+2E0h+var_298], rax
0x1800a3cc1  lea     r9, [rsp+2E0h+var_268]
0x1800a3cc6  mov     eax, 4
0x1800a3ccb  lea     rdx, PLA_EVENT_ERROR
0x1800a3cd2  mov     [rsp+2E0h+var_2A0], rax
0x1800a3cd7  mov     [rsp+2E0h+var_2A8], rcx
0x1800a3cdc  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800a3ce3  mov     [rsp+2E0h+var_2B0], 1
0x1800a3cec  mov     [rsp+2E0h+var_2B8], rsi
0x1800a3cf1  lea     r8d, [rax+1]
0x1800a3cf5  mov     [rsp+2E0h+var_2C0], rax
0x1800a3cfa  call    EventingWriteEvent
0x1800a3cff  jmp     loc_1800A4005
0x1800a3d04  mov     r8d, 1; dwDesiredAccess
0x1800a3d0a  lea     rdx, ServiceName; "schedule"
0x1800a3d11  mov     rcx, r15; hSCManager
0x1800a3d14  mov     rdi, r13
0x1800a3d17  call    cs:__imp_OpenServiceW
0x1800a3d1d  mov     r14, rax
0x1800a3d20  test    rax, rax
0x1800a3d23  jnz     loc_1800A3E10
0x1800a3d29  call    cs:__imp_GetLastError
0x1800a3d2f  mov     ecx, eax; unsigned int
0x1800a3d31  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800a3d36  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800a3d3d  mov     ebx, eax
0x1800a3d3f  mov     [rsp+2E0h+var_268], r13d
0x1800a3d44  mov     [rsp+2E0h+var_270], eax
0x1800a3d48  jz      loc_1800A3FEA
0x1800a3d4e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a3d58  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a3d5f  jz      loc_1800A3FEA
0x1800a3d65  mov     rax, cs:qword_180169748
0x1800a3d6c  and     rax, rdx
0x1800a3d6f  cmp     cs:qword_180169748, rax
0x1800a3d76  jnz     loc_1800A3FEA
0x1800a3d7c  lea     rcx, [rbp+1E0h+var_1D0]; unsigned __int16 *
0x1800a3d80  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a3d85  lea     rcx, [rbp+1E0h+var_1D0]
0x1800a3d89  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a3d8d  inc     rax
0x1800a3d90  cmp     [rcx+rax*2], r13w
0x1800a3d95  jnz     short loc_1800A3D8D
0x1800a3d97  lea     ecx, [rax+rax]
0x1800a3d9a  add     rcx, 2
0x1800a3d9e  lea     rax, [rbp+1E0h+var_1D0]
0x1800a3da2  mov     [rsp+2E0h+var_280], rcx
0x1800a3da7  lea     rsi, byte_180147320
0x1800a3dae  mov     [rsp+2E0h+var_288], rax
0x1800a3db3  lea     rcx, [rsp+2E0h+var_268]
0x1800a3db8  mov     [rsp+2E0h+var_290], 1Ah
0x1800a3dc1  lea     rax, aPlaiqueryservi; "PlaiQueryServiceStartType"
0x1800a3dc8  mov     [rsp+2E0h+var_298], rax
0x1800a3dcd  lea     r9, [rsp+2E0h+var_270]
0x1800a3dd2  mov     eax, 4
0x1800a3dd7  lea     rdx, PLA_EVENT_ERROR
0x1800a3dde  mov     [rsp+2E0h+var_2A0], rax
0x1800a3de3  mov     [rsp+2E0h+var_2A8], rcx
0x1800a3de8  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800a3def  mov     [rsp+2E0h+var_2B0], 1
0x1800a3df8  mov     [rsp+2E0h+var_2B8], rsi
0x1800a3dfd  lea     r8d, [rax+1]
0x1800a3e01  mov     [rsp+2E0h+var_2C0], rax
0x1800a3e06  call    EventingWriteEvent
0x1800a3e0b  jmp     loc_1800A3FEA
0x1800a3e10  mov     [rbp+1E0h+pcbBytesNeeded], 440h
0x1800a3e17  lea     rsi, byte_180147320
0x1800a3e1e  test    rdi, rdi
0x1800a3e21  jz      short loc_1800A3E30
0x1800a3e23  mov     edx, 1; int
0x1800a3e28  mov     rcx, rdi; lpMem
0x1800a3e2b  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x1800a3e30  mov     ecx, [rbp+1E0h+pcbBytesNeeded]; dwBytes
0x1800a3e33  xor     r8d, r8d; int
0x1800a3e36  mov     r9, rsi; char *
0x1800a3e39  lea     edx, [r8+1]; int
0x1800a3e3d  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800a3e42  mov     rdi, rax
0x1800a3e45  test    rax, rax
0x1800a3e48  jz      loc_1800A3F07
0x1800a3e4e  mov     r8d, [rbp+1E0h+pcbBytesNeeded]; cbBufSize
0x1800a3e52  lea     r9, [rbp+1E0h+pcbBytesNeeded]; pcbBytesNeeded
0x1800a3e56  mov     rdx, rax; lpServiceConfig
0x1800a3e59  mov     rcx, r14; hService
0x1800a3e5c  call    cs:__imp_QueryServiceConfigW
0x1800a3e62  test    eax, eax
0x1800a3e64  jnz     loc_1800A3EF8
0x1800a3e6a  call    cs:__imp_GetLastError
0x1800a3e70  mov     ecx, eax; unsigned int
0x1800a3e72  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800a3e77  mov     ebx, eax
0x1800a3e79  cmp     eax, 8007007Ah
0x1800a3e7e  jz      short loc_1800A3E1E
0x1800a3e80  test    eax, eax
0x1800a3e82  jns     short loc_1800A3EFB
0x1800a3e84  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800a3e8b  mov     [rsp+2E0h+var_268], r13d
0x1800a3e90  mov     [rsp+2E0h+var_270], eax
0x1800a3e94  jz      loc_1800A3FE1
0x1800a3e9a  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a3ea4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a3eab  jz      loc_1800A3FE1
0x1800a3eb1  mov     rax, cs:qword_180169748
0x1800a3eb8  and     rax, rdx
0x1800a3ebb  cmp     cs:qword_180169748, rax
0x1800a3ec2  jnz     loc_1800A3FE1
0x1800a3ec8  lea     rcx, [rbp+1E0h+var_150]; unsigned __int16 *
0x1800a3ecf  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a3ed4  lea     rcx, [rbp+1E0h+var_150]
0x1800a3edb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a3edf  inc     rax
0x1800a3ee2  cmp     [rcx+rax*2], r13w
0x1800a3ee7  jnz     short loc_1800A3EDF
0x1800a3ee9  lea     ecx, [rax+rax]
0x1800a3eec  lea     rax, [rbp+1E0h+var_150]
0x1800a3ef3  jmp     loc_1800A3F7B
0x1800a3ef8  mov     ebx, r13d
0x1800a3efb  mov     eax, [rdi+4]
0x1800a3efe  mov     [r12], eax
0x1800a3f02  jmp     loc_1800A3FE1
0x1800a3f07  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800a3f0e  mov     ebx, 8007000Eh
0x1800a3f13  mov     [rsp+2E0h+var_270], ebx
0x1800a3f17  mov     [rsp+2E0h+var_268], r13d
0x1800a3f1c  jz      loc_1800A3FE1
0x1800a3f22  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a3f2c  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a3f33  jz      loc_1800A3FE1
0x1800a3f39  mov     rax, cs:qword_180169748
0x1800a3f40  and     rax, rdx
0x1800a3f43  cmp     cs:qword_180169748, rax
0x1800a3f4a  jnz     loc_1800A3FE1
0x1800a3f50  lea     rcx, [rbp+1E0h+var_D0]; unsigned __int16 *
0x1800a3f57  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a3f5c  lea     rcx, [rbp+1E0h+var_D0]
0x1800a3f63  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a3f67  inc     rax
0x1800a3f6a  cmp     [rcx+rax*2], r13w
0x1800a3f6f  jnz     short loc_1800A3F67
0x1800a3f71  lea     ecx, [rax+rax]
0x1800a3f74  lea     rax, [rbp+1E0h+var_D0]
0x1800a3f7b  add     rcx, 2
0x1800a3f7f  lea     r9, [rsp+2E0h+var_270]
0x1800a3f84  mov     [rsp+2E0h+var_280], rcx
0x1800a3f89  lea     rdx, PLA_EVENT_ERROR
0x1800a3f90  mov     [rsp+2E0h+var_288], rax
0x1800a3f95  lea     rcx, [rsp+2E0h+var_268]
0x1800a3f9a  mov     [rsp+2E0h+var_290], 1Ah
0x1800a3fa3  lea     rax, aPlaiqueryservi; "PlaiQueryServiceStartType"
0x1800a3faa  mov     [rsp+2E0h+var_298], rax
0x1800a3faf  mov     eax, 4
0x1800a3fb4  mov     [rsp+2E0h+var_2A0], rax
0x1800a3fb9  mov     [rsp+2E0h+var_2A8], rcx
0x1800a3fbe  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800a3fc5  mov     [rsp+2E0h+var_2B0], 1
0x1800a3fce  mov     [rsp+2E0h+var_2B8], rsi
0x1800a3fd3  lea     r8d, [rax+1]
0x1800a3fd7  mov     [rsp+2E0h+var_2C0], rax
0x1800a3fdc  call    EventingWriteEvent
0x1800a3fe1  mov     rcx, r14; hSCObject
0x1800a3fe4  call    cs:__imp_CloseServiceHandle
0x1800a3fea  mov     rcx, r15; hSCObject
0x1800a3fed  call    cs:__imp_CloseServiceHandle
0x1800a3ff3  test    rdi, rdi
0x1800a3ff6  jz      short loc_1800A4005
0x1800a3ff8  mov     edx, 1; int
0x1800a3ffd  mov     rcx, rdi; lpMem
0x1800a4000  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x1800a4005  mov     eax, ebx
0x1800a4007  mov     rcx, [rbp+1E0h+var_50]
0x1800a400e  xor     rcx, rsp; StackCookie
0x1800a4011  call    __security_check_cookie
0x1800a4016  add     rsp, 2A8h
0x1800a401d  pop     r15
0x1800a401f  pop     r14
0x1800a4021  pop     r13
0x1800a4023  pop     r12
0x1800a4025  pop     rdi
0x1800a4026  pop     rsi
0x1800a4027  pop     rbx
0x1800a4028  pop     rbp
0x1800a4029  retn
```
