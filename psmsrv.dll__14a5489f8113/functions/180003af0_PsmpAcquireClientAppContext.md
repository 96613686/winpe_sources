# PsmpAcquireClientAppContext

- ea: `0x180003af0`
- end: `0x180003ebf`
- name: `PsmpAcquireClientAppContext`
- size: `975`
- prototype: `__int64 __fastcall(_QWORD *, void *, unsigned int, void *, void **, HANDLE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800039a8`

## callees

- `0x180003af0`
- `0x180003ec8`
- `0x180004170`
- `0x180008cc0`
- `0x180009b40`
- `0x180019bfc`
- `0x18001b7e0`
- `0x18001c10c`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x180003d5a`
- `ntdll!NtCreateEvent` at `0x180003d5a`
- `ntdll!NtDuplicateObject` at `0x180003d37`
- `ntdll!NtDuplicateObject` at `0x180003d96`
- `ntdll!NtDuplicateObject` at `0x180003d37`
- `ntdll!NtDuplicateObject` at `0x180003d96`
- `ntdll!NtClose` at `0x180003c03`
- `ntdll!NtClose` at `0x180003e19`
- `ntdll!NtClose` at `0x180003e86`
- `ntdll!NtClose` at `0x180003e91`
- `ntdll!NtClose` at `0x180003e9c`
- `ntdll!NtClose` at `0x180003ea7`
- `ntdll!NtClose` at `0x180003c03`
- `ntdll!NtClose` at `0x180003e19`
- `ntdll!NtClose` at `0x180003e86`
- `ntdll!NtClose` at `0x180003e91`
- `ntdll!NtClose` at `0x180003e9c`
- `ntdll!NtClose` at `0x180003ea7`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180003e5d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180003e5d`
- `ntdll!NtCreateSemaphore` at `0x180003cfb`
- `ntdll!NtCreateSemaphore` at `0x180003cfb`
- `ntdll!NtOpenProcessTokenEx` at `0x180003b90`
- `ntdll!NtOpenProcessTokenEx` at `0x180003b90`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003daa`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003daa`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003df8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003df8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003d0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003d14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003d6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003d73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003d0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003d14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003d6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003d73`
- `RPCRT4!RpcImpersonateClient` at `0x180003ccd`
- `RPCRT4!RpcImpersonateClient` at `0x180003ccd`
- `RPCRT4!RpcRevertToSelfEx` at `0x180003e27`
- `RPCRT4!RpcRevertToSelfEx` at `0x180003e27`
- `RPCRT4!I_RpcMapWin32Status` at `0x180003e3e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180003e3e`

## pseudocode

```c
__int64 __fastcall PsmpAcquireClientAppContext(_QWORD *a1, void *a2, unsigned int a3, void *a4, void **a5, HANDLE *a6)
{
  __int64 v9; // r14
  int v10; // r13d
  __int64 v11; // rdi
  NTSTATUS ClientApplicationInformation; // ebx
  unsigned __int8 v14; // al
  int ApplicationByManagerForUser; // eax
  int v16; // eax
  RPC_STATUS v17; // eax
  HANDLE CurrentProcess; // rbx
  HANDLE v19; // rax
  HANDLE v20; // rbx
  HANDLE v21; // rax
  void **v22; // rcx
  HANDLE *v23; // rcx
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  void *EventHandle; // [rsp+48h] [rbp-B8h] BYREF
  void *SemaphoreHandle; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v27; // [rsp+58h] [rbp-A8h] BYREF
  void *TargetHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-80h] BYREF
  void **v33; // [rsp+88h] [rbp-78h]
  HANDLE *v34; // [rsp+90h] [rbp-70h]
  _QWORD *v35; // [rsp+98h] [rbp-68h]
  int v36; // [rsp+A0h] [rbp-60h] BYREF
  char Sid2[68]; // [rsp+278h] [rbp+178h] BYREF
  unsigned __int8 v38; // [rsp+2BCh] [rbp+1BCh]

  v33 = a5;
  v35 = a1;
  v34 = a6;
  Handle = a4;
  memset_0(&v36, 0, 0x220u);
  v30 = 0;
  EventHandle = 0;
  v9 = 0;
  v27 = 0;
  v29 = 0;
  v10 = 0;
  SemaphoreHandle = 0;
  v11 = 0;
  TargetHandle = 0;
  TokenHandle = 0;
  ClientApplicationInformation = NtOpenProcessTokenEx(a4, 8u, 0, &TokenHandle);
  if ( ClientApplicationInformation >= 0 )
  {
    ClientApplicationInformation = PsmpQueryClientApplicationInformation(a4, 0);
    if ( ClientApplicationInformation >= 0 )
    {
      v14 = v38;
      if ( v38 )
      {
        if ( v38 != 4 || (v24 = 0, RtlGetDeviceFamilyInfoEnum(0, &v24, 0), v24 != 16) && v24 != 10 )
        {
          ClientApplicationInformation = -1073741637;
          goto LABEL_2;
        }
        v14 = v38;
      }
      ApplicationByManagerForUser = PsmpFindApplicationByManagerForUser(Sid2, v14, (__int64)&v30);
      v9 = v30;
      ClientApplicationInformation = ApplicationByManagerForUser;
      if ( ApplicationByManagerForUser >= 0 )
      {
        v16 = PsmpFindOrCreateClientProcessContext(v30, a3, &Handle, &v29);
        v11 = v29;
        ClientApplicationInformation = v16;
        if ( v16 >= 0 )
        {
          if ( *(_QWORD *)(v29 + 80) )
          {
LABEL_35:
            ClientApplicationInformation = -1073740008;
            goto LABEL_2;
          }
          v17 = RpcImpersonateClient(a2);
          if ( v17 )
          {
            ClientApplicationInformation = I_RpcMapWin32Status(v17);
          }
          else
          {
            v10 = 1;
            ClientApplicationInformation = NtCreateSemaphore(&SemaphoreHandle, 0x1F0003u, 0, 0, 2);
            if ( ClientApplicationInformation >= 0 )
            {
              CurrentProcess = GetCurrentProcess();
              v19 = GetCurrentProcess();
              ClientApplicationInformation = NtDuplicateObject(
                                               v19,
                                               SemaphoreHandle,
                                               CurrentProcess,
                                               &TargetHandle,
                                               0x1F0003u,
                                               0,
                                               0);
              if ( ClientApplicationInformation >= 0 )
              {
                ClientApplicationInformation = NtCreateEvent(&EventHandle, 0x1F0003u, 0, NotificationEvent, 0);
                if ( ClientApplicationInformation >= 0 )
                {
                  v20 = GetCurrentProcess();
                  v21 = GetCurrentProcess();
                  ClientApplicationInformation = NtDuplicateObject(v21, EventHandle, v20, &v27, 0x1F0003u, 0, 0);
                  if ( ClientApplicationInformation >= 0 )
                  {
                    RtlAcquireSRWLockExclusive(v11 + 8);
                    if ( !*(_QWORD *)(v11 + 80) )
                    {
                      v22 = v33;
                      *(_QWORD *)(v11 + 80) = SemaphoreHandle;
                      SemaphoreHandle = 0;
                      *v22 = TargetHandle;
                      v23 = v34;
                      TargetHandle = 0;
                      *(_QWORD *)(v11 + 88) = EventHandle;
                      *v23 = v27;
                      EventHandle = 0;
                      v27 = 0;
                    }
                    RtlReleaseSRWLockExclusive(v11 + 8);
                    if ( !EventHandle )
                    {
                      ClientApplicationInformation = 0;
                      *v35 = v11;
                      v11 = 0;
                      goto LABEL_2;
                    }
                    goto LABEL_35;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_2:
  if ( EventHandle )
    NtClose(EventHandle);
  if ( SemaphoreHandle )
    NtClose(SemaphoreHandle);
  if ( v27 )
    NtClose(v27);
  if ( TargetHandle )
    NtClose(TargetHandle);
  if ( v10 )
    RpcRevertToSelfEx(a2);
  if ( v9 )
    PsmpDereferenceApplicationEx(v9, 0);
  if ( v11 )
    PsmpDereferenceClientContext(v11);
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)ClientApplicationInformation;
}

```

## disassembly

```asm
0x180003af0  push    rbp
0x180003af2  push    rbx
0x180003af3  push    rsi
0x180003af4  push    rdi
0x180003af5  push    r12
0x180003af7  push    r13
0x180003af9  push    r14
0x180003afb  push    r15
0x180003afd  lea     rbp, [rsp-1D8h]
0x180003b05  sub     rsp, 2D8h
0x180003b0c  mov     rax, cs:__security_cookie
0x180003b13  xor     rax, rsp
0x180003b16  mov     [rbp+210h+var_50], rax
0x180003b1d  mov     rax, [rbp+210h+arg_20]
0x180003b24  mov     r15d, r8d
0x180003b27  mov     [rbp+210h+var_288], rax
0x180003b2b  mov     r12, rdx
0x180003b2e  mov     rax, [rbp+210h+arg_28]
0x180003b35  xor     edx, edx; Val
0x180003b37  mov     [rbp+210h+var_278], rcx
0x180003b3b  mov     r8d, 220h; Size
0x180003b41  lea     rcx, [rbp+210h+var_270]; void *
0x180003b45  mov     [rbp+210h+var_280], rax
0x180003b49  mov     rsi, r9
0x180003b4c  mov     [rbp+210h+Handle], r9
0x180003b50  call    memset_0
0x180003b55  xor     eax, eax
0x180003b57  lea     r9, [rsp+310h+TokenHandle]; TokenHandle
0x180003b5c  xor     r8d, r8d; HandleAttributes
0x180003b5f  mov     [rsp+310h+var_2A0], rax
0x180003b64  mov     rcx, rsi; ProcessHandle
0x180003b67  mov     [rsp+310h+EventHandle], rax
0x180003b6c  mov     r14d, eax
0x180003b6f  mov     [rsp+310h+var_2B8], rax
0x180003b74  lea     edx, [rax+8]; DesiredAccess
0x180003b77  mov     [rsp+310h+var_2A8], rax
0x180003b7c  mov     r13d, eax
0x180003b7f  mov     [rsp+310h+SemaphoreHandle], rax
0x180003b84  mov     edi, eax
0x180003b86  mov     [rsp+310h+TargetHandle], rax
0x180003b8b  mov     [rsp+310h+TokenHandle], rax
0x180003b90  call    cs:__imp_NtOpenProcessTokenEx
0x180003b96  mov     ebx, eax
0x180003b98  test    eax, eax
0x180003b9a  jns     loc_180003C3B
0x180003ba0  mov     rcx, [rsp+310h+EventHandle]; Handle
0x180003ba5  test    rcx, rcx
0x180003ba8  jnz     loc_180003E86
0x180003bae  mov     rcx, [rsp+310h+SemaphoreHandle]; Handle
0x180003bb3  test    rcx, rcx
0x180003bb6  jnz     loc_180003E91
0x180003bbc  mov     rcx, [rsp+310h+var_2B8]; Handle
0x180003bc1  test    rcx, rcx
0x180003bc4  jnz     loc_180003E9C
0x180003bca  mov     rcx, [rsp+310h+TargetHandle]; Handle
0x180003bcf  test    rcx, rcx
0x180003bd2  jnz     loc_180003EA7
0x180003bd8  test    r13d, r13d
0x180003bdb  jnz     loc_180003E24
0x180003be1  test    r14, r14
0x180003be4  jz      short loc_180003BF0
0x180003be6  xor     edx, edx
0x180003be8  mov     rcx, r14
0x180003beb  call    PsmpDereferenceApplicationEx
0x180003bf0  test    rdi, rdi
0x180003bf3  jnz     loc_180003EB2
0x180003bf9  mov     rcx, [rsp+310h+TokenHandle]; Handle
0x180003bfe  test    rcx, rcx
0x180003c01  jz      short loc_180003C09
0x180003c03  call    cs:__imp_NtClose
0x180003c09  mov     rsi, [rbp+210h+Handle]
0x180003c0d  test    rsi, rsi
0x180003c10  jnz     loc_180003E16
0x180003c16  mov     eax, ebx
0x180003c18  mov     rcx, [rbp+210h+var_50]
0x180003c1f  xor     rcx, rsp; StackCookie
0x180003c22  call    __security_check_cookie
0x180003c27  add     rsp, 2D8h
0x180003c2e  pop     r15
0x180003c30  pop     r14
0x180003c32  pop     r13
0x180003c34  pop     r12
0x180003c36  pop     rdi
0x180003c37  pop     rsi
0x180003c38  pop     rbx
0x180003c39  pop     rbp
0x180003c3a  retn
0x180003c3b  xor     r9d, r9d
0x180003c3e  lea     r8, [rbp+210h+var_270]
0x180003c42  xor     edx, edx; TokenHandle
0x180003c44  mov     rcx, rsi; ProcessHandle
0x180003c47  call    PsmpQueryClientApplicationInformation
0x180003c4c  xor     esi, esi
0x180003c4e  mov     ebx, eax
0x180003c50  test    eax, eax
0x180003c52  js      loc_180003BA0
0x180003c58  mov     al, [rbp+210h+var_54]
0x180003c5e  test    al, al
0x180003c60  jnz     loc_180003E4B
0x180003c66  mov     r9d, [rbp+210h+var_26C]
0x180003c6a  lea     rcx, [rsp+310h+var_2A0]
0x180003c6f  mov     edx, [rbp+210h+var_270]
0x180003c72  lea     r8, [rbp+210h+var_268]
0x180003c76  mov     qword ptr [rsp+310h+HandleAttributes], rcx; __int64
0x180003c7b  lea     rcx, [rbp+210h+Sid2]; Sid2
0x180003c82  movzx   eax, al
0x180003c85  mov     [rsp+310h+MaximumCount], eax; int
0x180003c89  call    PsmpFindApplicationByManagerForUser
0x180003c8e  mov     r14, [rsp+310h+var_2A0]
0x180003c93  mov     ebx, eax
0x180003c95  test    eax, eax
0x180003c97  js      loc_180003BA0
0x180003c9d  lea     r9, [rsp+310h+var_2A8]
0x180003ca2  mov     edx, r15d
0x180003ca5  lea     r8, [rbp+210h+Handle]
0x180003ca9  mov     rcx, r14
0x180003cac  call    PsmpFindOrCreateClientProcessContext
0x180003cb1  mov     rdi, [rsp+310h+var_2A8]
0x180003cb6  mov     ebx, eax
0x180003cb8  test    eax, eax
0x180003cba  js      loc_180003BA0
0x180003cc0  cmp     [rdi+50h], rsi
0x180003cc4  jnz     loc_180003E32
0x180003cca  mov     rcx, r12; BindingHandle
0x180003ccd  call    cs:__imp_RpcImpersonateClient
0x180003cd3  test    eax, eax
0x180003cd5  jnz     loc_180003E3C
0x180003cdb  mov     r15d, 1F0003h
0x180003ce1  mov     [rsp+310h+MaximumCount], 2; MaximumCount
0x180003ce9  mov     edx, r15d; DesiredAccess
0x180003cec  lea     rcx, [rsp+310h+SemaphoreHandle]; SemaphoreHandle
0x180003cf1  xor     r9d, r9d; InitialCount
0x180003cf4  lea     r13d, [rax+1]
0x180003cf8  xor     r8d, r8d; ObjectAttributes
0x180003cfb  call    cs:__imp_NtCreateSemaphore
0x180003d01  mov     ebx, eax
0x180003d03  test    eax, eax
0x180003d05  js      loc_180003BA0
0x180003d0b  call    cs:__imp_GetCurrentProcess
0x180003d11  mov     rbx, rax
0x180003d14  call    cs:__imp_GetCurrentProcess
0x180003d1a  mov     rdx, [rsp+310h+SemaphoreHandle]; SourceHandle
0x180003d1f  lea     r9, [rsp+310h+TargetHandle]; TargetHandle
0x180003d24  mov     [rsp+310h+Options], esi; Options
0x180003d28  mov     rcx, rax; SourceProcessHandle
0x180003d2b  mov     [rsp+310h+HandleAttributes], esi; HandleAttributes
0x180003d2f  mov     r8, rbx; TargetProcessHandle
0x180003d32  mov     [rsp+310h+MaximumCount], r15d; DesiredAccess
0x180003d37  call    cs:__imp_NtDuplicateObject
0x180003d3d  mov     ebx, eax
0x180003d3f  test    eax, eax
0x180003d41  js      loc_180003BA0
0x180003d47  xor     r9d, r9d; EventType
0x180003d4a  mov     byte ptr [rsp+310h+MaximumCount], sil; InitialState
0x180003d4f  xor     r8d, r8d; ObjectAttributes
0x180003d52  lea     rcx, [rsp+310h+EventHandle]; EventHandle
0x180003d57  mov     edx, r15d; DesiredAccess
0x180003d5a  call    cs:__imp_NtCreateEvent
0x180003d60  mov     ebx, eax
0x180003d62  test    eax, eax
0x180003d64  js      loc_180003BA0
0x180003d6a  call    cs:__imp_GetCurrentProcess
0x180003d70  mov     rbx, rax
0x180003d73  call    cs:__imp_GetCurrentProcess
0x180003d79  mov     rdx, [rsp+310h+EventHandle]; SourceHandle
0x180003d7e  lea     r9, [rsp+310h+var_2B8]; TargetHandle
0x180003d83  mov     [rsp+310h+Options], esi; Options
0x180003d87  mov     rcx, rax; SourceProcessHandle
0x180003d8a  mov     [rsp+310h+HandleAttributes], esi; HandleAttributes
0x180003d8e  mov     r8, rbx; TargetProcessHandle
0x180003d91  mov     [rsp+310h+MaximumCount], r15d; DesiredAccess
0x180003d96  call    cs:__imp_NtDuplicateObject
0x180003d9c  mov     ebx, eax
0x180003d9e  test    eax, eax
0x180003da0  js      loc_180003BA0
0x180003da6  lea     rcx, [rdi+8]
0x180003daa  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180003db0  cmp     [rdi+50h], rsi
0x180003db4  jnz     short loc_180003DF4
0x180003db6  mov     rax, [rsp+310h+SemaphoreHandle]
0x180003dbb  mov     rcx, [rbp+210h+var_288]
0x180003dbf  mov     [rdi+50h], rax
0x180003dc3  mov     rax, [rsp+310h+TargetHandle]
0x180003dc8  mov     [rsp+310h+SemaphoreHandle], rsi
0x180003dcd  mov     [rcx], rax
0x180003dd0  mov     rax, [rsp+310h+EventHandle]
0x180003dd5  mov     rcx, [rbp+210h+var_280]
0x180003dd9  mov     [rsp+310h+TargetHandle], rsi
0x180003dde  mov     [rdi+58h], rax
0x180003de2  mov     rax, [rsp+310h+var_2B8]
0x180003de7  mov     [rcx], rax
0x180003dea  mov     [rsp+310h+EventHandle], rsi
0x180003def  mov     [rsp+310h+var_2B8], rsi
0x180003df4  lea     rcx, [rdi+8]
0x180003df8  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180003dfe  cmp     [rsp+310h+EventHandle], rsi
0x180003e03  jnz     short loc_180003E32
0x180003e05  mov     rax, [rbp+210h+var_278]
0x180003e09  mov     ebx, esi
0x180003e0b  mov     [rax], rdi
0x180003e0e  mov     rdi, rsi
0x180003e11  jmp     loc_180003BA0
0x180003e16  mov     rcx, rsi; Handle
0x180003e19  call    cs:__imp_NtClose
0x180003e1f  jmp     loc_180003C16
0x180003e24  mov     rcx, r12; BindingHandle
0x180003e27  call    cs:__imp_RpcRevertToSelfEx
0x180003e2d  jmp     loc_180003BE1
0x180003e32  mov     ebx, 0C0000718h
0x180003e37  jmp     loc_180003BA0
0x180003e3c  mov     ecx, eax; Status
0x180003e3e  call    cs:__imp_I_RpcMapWin32Status
0x180003e44  mov     ebx, eax
0x180003e46  jmp     loc_180003BA0
0x180003e4b  cmp     al, 4
0x180003e4d  jnz     short loc_180003E71
0x180003e4f  xor     r8d, r8d
0x180003e52  mov     [rsp+310h+var_2D0], esi
0x180003e56  lea     rdx, [rsp+310h+var_2D0]
0x180003e5b  xor     ecx, ecx
0x180003e5d  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180003e63  cmp     [rsp+310h+var_2D0], 10h
0x180003e68  jz      short loc_180003E7B
0x180003e6a  cmp     [rsp+310h+var_2D0], 0Ah
0x180003e6f  jz      short loc_180003E7B
0x180003e71  mov     ebx, 0C00000BBh
0x180003e76  jmp     loc_180003BA0
0x180003e7b  mov     al, [rbp+210h+var_54]
0x180003e81  jmp     loc_180003C66
0x180003e86  call    cs:__imp_NtClose
0x180003e8c  jmp     loc_180003BAE
0x180003e91  call    cs:__imp_NtClose
0x180003e97  jmp     loc_180003BBC
0x180003e9c  call    cs:__imp_NtClose
0x180003ea2  jmp     loc_180003BCA
0x180003ea7  call    cs:__imp_NtClose
0x180003ead  jmp     loc_180003BD8
0x180003eb2  mov     rcx, rdi
0x180003eb5  call    PsmpDereferenceClientContext
0x180003eba  jmp     loc_180003BF9
```
