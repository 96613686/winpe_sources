# CLONE_WINDOWS_SERVICES::GetNextElement(CLONE_SOFTWARE_ELEMENT * *)

- ea: `0x180024300`
- end: `0x1800244c0`
- name: `?GetNextElement@CLONE_WINDOWS_SERVICES@@UEAAKPEAPEAVCLONE_SOFTWARE_ELEMENT@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(CLONE_WINDOWS_SERVICES *this, struct CLONE_SOFTWARE_ELEMENT **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180003308`
- `0x180023afc`
- `0x180024300`
- `0x180024548`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800243ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800243ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024408`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243ce`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002433f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002433f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800244aa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002c588`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800244aa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002c588`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x1800243c4`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x1800243c4`

## pseudocode

```c
__int64 __fastcall CLONE_WINDOWS_SERVICES::GetNextElement(
        CLONE_WINDOWS_SERVICES *this,
        struct CLONE_SOFTWARE_ELEMENT **a2)
{
  DWORD LastError; // ebx
  SC_HANDLE v5; // r14
  struct CLONE_SOFTWARE_ELEMENT *v6; // rdi
  int i; // r15d
  void *v8; // rcx
  HLOCAL v9; // rax
  struct CLONE_SOFTWARE_ELEMENT *v10; // rax
  DWORD cbBufSize; // [rsp+B8h] [rbp+10h] BYREF

  LastError = 0;
  v5 = 0;
  v6 = 0;
  cbBufSize = 0;
  *a2 = 0;
  if ( !*((_QWORD *)this + 1) )
  {
    v5 = OpenSCManagerW(0, 0, 0x80000000);
    if ( !v5 )
    {
      LastError = GetLastError();
      goto LABEL_20;
    }
    for ( i = 0; i < 5; ++i )
    {
      *((_DWORD *)this + 5) = 0;
      if ( EnumServicesStatusExW(
             v5,
             SC_ENUM_PROCESS_INFO,
             0x30u,
             3u,
             *((LPBYTE *)this + 1),
             cbBufSize,
             &cbBufSize,
             (LPDWORD)this + 5,
             0,
             0) )
      {
        break;
      }
      LastError = GetLastError();
      if ( LastError != 234 )
        goto LABEL_20;
      v8 = (void *)*((_QWORD *)this + 1);
      if ( v8 )
      {
        LocalFree(v8);
        *((_QWORD *)this + 1) = 0;
      }
      v9 = LocalAlloc(0x40u, cbBufSize);
      *((_QWORD *)this + 1) = v9;
      if ( !v9 )
        goto LABEL_11;
    }
  }
  if ( *((_DWORD *)this + 4) < *((_DWORD *)this + 5) )
  {
    v10 = (struct CLONE_SOFTWARE_ELEMENT *)operator new(0x10u);
    v6 = v10;
    if ( v10 )
    {
      *(_QWORD *)v10 = 0;
      *((_DWORD *)v10 + 2) = 0;
    }
    else
    {
      v6 = 0;
    }
    if ( v6 )
    {
      LastError = CLONE_SOFTWARE_ELEMENT::Initialize(
                    v6,
                    *(_QWORD *)(56LL * *((unsigned int *)this + 4) + *((_QWORD *)this + 1)),
                    2);
      if ( !LastError )
      {
        ++*((_DWORD *)this + 4);
        *a2 = v6;
        v6 = 0;
      }
    }
    else
    {
LABEL_11:
      LastError = 14;
    }
  }
LABEL_20:
  if ( v6 )
    CLONE_SOFTWARE_ELEMENT::`scalar deleting destructor'(v6, (unsigned int)a2);
  if ( v5 )
    CloseServiceHandle(v5);
  return LastError;
}

```

## disassembly

```asm
0x180024300  mov     rax, rsp
0x180024303  push    rbx
0x180024304  push    rsi
0x180024305  push    rdi
0x180024306  push    r12
0x180024308  push    r14
0x18002430a  push    r15
0x18002430c  sub     rsp, 78h
0x180024310  mov     r12, rdx
0x180024313  mov     rsi, rcx
0x180024316  xor     ebx, ebx
0x180024318  xor     r14d, r14d
0x18002431b  mov     [rax-48h], r14
0x18002431f  xor     edi, edi
0x180024321  mov     [rax-50h], rdi
0x180024325  mov     [rax+10h], ebx
0x180024328  mov     [rdx], rbx
0x18002432b  cmp     [rcx+8], rdi
0x18002432f  jnz     loc_18002442A
0x180024335  xor     edx, edx; lpDatabaseName
0x180024337  xor     ecx, ecx; lpMachineName
0x180024339  mov     r8d, 80000000h; dwDesiredAccess
0x18002433f  call    cs:__imp_OpenSCManagerW
0x180024345  mov     r14, rax
0x180024348  mov     [rsp+0A8h+var_48], rax
0x18002434d  test    rax, rax
0x180024350  jnz     short loc_180024363
0x180024352  call    cs:__imp_GetLastError
0x180024358  mov     ebx, eax
0x18002435a  mov     [rsp+0A8h+var_58], eax
0x18002435e  jmp     loc_180024495
0x180024363  xor     r15d, r15d
0x180024366  mov     [rsp+0A8h+var_54], r15d
0x18002436b  cmp     r15d, 5
0x18002436f  jge     loc_18002442A
0x180024375  lea     rax, [rsi+14h]
0x180024379  mov     dword ptr [rax], 0
0x18002437f  mov     [rsp+0A8h+pszGroupName], 0; pszGroupName
0x180024388  mov     [rsp+0A8h+lpResumeHandle], 0; lpResumeHandle
0x180024391  mov     [rsp+0A8h+lpServicesReturned], rax; lpServicesReturned
0x180024396  lea     rax, [rsp+0A8h+arg_8]
0x18002439e  mov     [rsp+0A8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800243a3  mov     eax, [rsp+0A8h+arg_8]
0x1800243aa  mov     [rsp+0A8h+cbBufSize], eax; cbBufSize
0x1800243ae  mov     rax, [rsi+8]
0x1800243b2  mov     [rsp+0A8h+lpServices], rax; lpServices
0x1800243b7  xor     edx, edx; InfoLevel
0x1800243b9  lea     r9d, [rdx+3]; dwServiceState
0x1800243bd  lea     r8d, [rdx+30h]; dwServiceType
0x1800243c1  mov     rcx, r14; hSCManager
0x1800243c4  call    cs:__imp_EnumServicesStatusExW
0x1800243ca  test    eax, eax
0x1800243cc  jnz     short loc_18002442A
0x1800243ce  call    cs:__imp_GetLastError
0x1800243d4  mov     ebx, eax
0x1800243d6  mov     [rsp+0A8h+var_58], eax
0x1800243da  cmp     eax, 0EAh
0x1800243df  jnz     loc_180024495
0x1800243e5  mov     rcx, [rsi+8]; hMem
0x1800243e9  test    rcx, rcx
0x1800243ec  jz      short loc_1800243FC
0x1800243ee  call    cs:__imp_LocalFree
0x1800243f4  mov     qword ptr [rsi+8], 0
0x1800243fc  mov     edx, [rsp+0A8h+arg_8]; uBytes
0x180024403  mov     ecx, 40h ; '@'; uFlags
0x180024408  call    cs:__imp_LocalAlloc
0x18002440e  mov     [rsi+8], rax
0x180024412  test    rax, rax
0x180024415  jnz     short loc_180024422
0x180024417  mov     ebx, 0Eh
0x18002441c  mov     [rsp+0A8h+var_58], ebx
0x180024420  jmp     short loc_180024495
0x180024422  inc     r15d
0x180024425  jmp     loc_180024366
0x18002442a  mov     eax, [rsi+14h]
0x18002442d  cmp     [rsi+10h], eax
0x180024430  jnb     short loc_180024495
0x180024432  mov     ecx, 10h; Size
0x180024437  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002443c  mov     rdi, rax
0x18002443f  test    rax, rax
0x180024442  jz      short loc_180024454
0x180024444  mov     qword ptr [rax], 0
0x18002444b  mov     dword ptr [rax+8], 0
0x180024452  jmp     short loc_180024456
0x180024454  xor     edi, edi
0x180024456  mov     [rsp+0A8h+var_50], rdi
0x18002445b  test    rdi, rdi
0x18002445e  jz      short loc_180024417
0x180024460  mov     eax, [rsi+10h]
0x180024463  imul    rcx, rax, 38h ; '8'
0x180024467  mov     rdx, [rsi+8]
0x18002446b  mov     r8d, 2
0x180024471  mov     rdx, [rcx+rdx]
0x180024475  mov     rcx, rdi
0x180024478  call    ?Initialize@CLONE_SOFTWARE_ELEMENT@@QEAAKPEBGW4CLONE_SOFTWARE_TYPE@@@Z; CLONE_SOFTWARE_ELEMENT::Initialize(ushort const *,CLONE_SOFTWARE_TYPE)
0x18002447d  mov     ebx, eax
0x18002447f  mov     [rsp+0A8h+var_58], eax
0x180024483  test    eax, eax
0x180024485  jnz     short loc_180024495
0x180024487  inc     dword ptr [rsi+10h]
0x18002448a  mov     [r12], rdi
0x18002448e  xor     edi, edi
0x180024490  mov     [rsp+0A8h+var_50], rdi
0x180024495  test    rdi, rdi
0x180024498  jz      short loc_1800244A2
0x18002449a  mov     rcx, rdi; this
0x18002449d  call    ??_GCLONE_SOFTWARE_ELEMENT@@QEAAPEAXI@Z; CLONE_SOFTWARE_ELEMENT::`scalar deleting destructor'(uint)
0x1800244a2  test    r14, r14
0x1800244a5  jz      short loc_1800244B0
0x1800244a7  mov     rcx, r14; hSCObject
0x1800244aa  call    cs:__imp_CloseServiceHandle
0x1800244b0  mov     eax, ebx
0x1800244b2  add     rsp, 78h
0x1800244b6  pop     r15
0x1800244b8  pop     r14
0x1800244ba  pop     r12
0x1800244bc  pop     rdi
0x1800244bd  pop     rsi
0x1800244be  pop     rbx
0x1800244bf  retn
0x18002c567  push    rbp
0x18002c569  sub     rsp, 50h
0x18002c56d  mov     rbp, rdx
0x18002c570  mov     rcx, [rbp+58h]; this
0x18002c574  test    rcx, rcx
0x18002c577  jz      short loc_18002C57F
0x18002c579  call    ??_GCLONE_SOFTWARE_ELEMENT@@QEAAPEAXI@Z; CLONE_SOFTWARE_ELEMENT::`scalar deleting destructor'(uint)
0x18002c57e  nop
0x18002c57f  mov     rcx, [rbp+60h]; hSCObject
0x18002c583  test    rcx, rcx
0x18002c586  jz      short loc_18002C58F
0x18002c588  call    cs:__imp_CloseServiceHandle
0x18002c58e  nop
0x18002c58f  add     rsp, 50h
0x18002c593  pop     rbp
0x18002c594  retn
```
