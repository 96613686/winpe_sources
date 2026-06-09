# UserProfileServiceAddWorkItem(ulong (*)(void *),void *,void *,ulong)

- ea: `0x18001cc58`
- end: `0x18001cd63`
- name: `?UserProfileServiceAddWorkItem@@YAJP6AKPEAX@Z00K@Z`
- size: `267`
- prototype: `int(unsigned int (*)(void *), void *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001b250`

## callees

- `0x1800061c8`
- `0x18001cc58`
- `0x18001cd6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cd46`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001cd15`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001cd15`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001ccca`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001ccca`

## pseudocode

```c
__int64 __fastcall UserProfileServiceAddWorkItem(unsigned int (*a1)(void *), void *a2, void *a3)
{
  LPCRITICAL_SECTION v3; // rbp
  signed int WorkItemInfo; // ebx
  PVOID v8; // rdi
  signed int LastError; // eax
  signed int v11; // eax
  PVOID pv; // [rsp+30h] [rbp-48h] BYREF

  v3 = g_pUPSvc;
  if ( !g_pUPSvc )
    return 2147500037LL;
  pv = 0;
  WorkItemInfo = _CreateWorkItemInfo((struct WorkItemInfo **)&pv);
  if ( WorkItemInfo >= 0 )
  {
    v8 = pv;
    *((_DWORD *)pv + 6) = 16;
    *(_QWORD *)v8 = a1;
    *((_QWORD *)v8 + 1) = a2;
    *((_QWORD *)v8 + 2) = 0;
    if ( !a3 || DuplicateTokenEx(a3, 0xCu, 0, SecurityImpersonation, TokenImpersonation, (PHANDLE)v8 + 2) )
      goto LABEL_18;
    LastError = GetLastError();
    WorkItemInfo = LastError;
    if ( LastError > 0 )
      WorkItemInfo = (unsigned __int16)LastError | 0x80070000;
    if ( WorkItemInfo >= 0 )
    {
LABEL_18:
      if ( TrySubmitThreadpoolCallback(
             (PTP_SIMPLE_CALLBACK)_WorkItemWrapper,
             v8,
             (PTP_CALLBACK_ENVIRON)&v3[1].LockSemaphore) )
      {
        v8 = 0;
      }
      else
      {
        v11 = GetLastError();
        WorkItemInfo = v11;
        if ( v11 > 0 )
          WorkItemInfo = (unsigned __int16)v11 | 0x80070000;
      }
    }
    _DestroyWorkItemInfo((struct WorkItemInfo *)v8);
  }
  return (unsigned int)WorkItemInfo;
}

```

## disassembly

```asm
0x18001cc58  push    rbx
0x18001cc5a  push    rbp
0x18001cc5b  push    rsi
0x18001cc5c  push    rdi
0x18001cc5d  push    r14
0x18001cc5f  push    r15
0x18001cc61  sub     rsp, 48h
0x18001cc65  mov     rbp, cs:?g_pUPSvc@@3PEAVCUserProfileService@@EA; CUserProfileService * g_pUPSvc
0x18001cc6c  mov     rsi, r8
0x18001cc6f  mov     r14, rdx
0x18001cc72  mov     r15, rcx
0x18001cc75  test    rbp, rbp
0x18001cc78  jz      short loc_18001CCF4
0x18001cc7a  lea     rcx, [rsp+78h+pv]; struct WorkItemInfo **
0x18001cc7f  mov     [rsp+78h+pv], 0
0x18001cc88  call    ?_CreateWorkItemInfo@@YAJPEAPEAUWorkItemInfo@@@Z; _CreateWorkItemInfo(WorkItemInfo * *)
0x18001cc8d  mov     ebx, eax
0x18001cc8f  test    eax, eax
0x18001cc91  js      short loc_18001CCE4
0x18001cc93  mov     rdi, [rsp+78h+pv]
0x18001cc98  mov     dword ptr [rdi+18h], 10h
0x18001cc9f  lea     rax, [rdi+10h]
0x18001cca3  mov     [rdi], r15
0x18001cca6  mov     [rdi+8], r14
0x18001ccaa  mov     r14d, 80070000h
0x18001ccb0  mov     qword ptr [rax], 0
0x18001ccb7  test    rsi, rsi
0x18001ccba  jnz     short loc_18001CCFB
0x18001ccbc  lea     r8, [rbp+40h]; pcbe
0x18001ccc0  mov     rdx, rdi; pv
0x18001ccc3  lea     rcx, ?_WorkItemWrapper@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001ccca  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001ccd1  nop     dword ptr [rax+rax+00h]
0x18001ccd6  test    eax, eax
0x18001ccd8  jz      short loc_18001CD46
0x18001ccda  xor     edi, edi
0x18001ccdc  mov     rcx, rdi; lpMem
0x18001ccdf  call    ?_DestroyWorkItemInfo@@YAXPEAUWorkItemInfo@@@Z; _DestroyWorkItemInfo(WorkItemInfo *)
0x18001cce4  mov     eax, ebx
0x18001cce6  add     rsp, 48h
0x18001ccea  pop     r15
0x18001ccec  pop     r14
0x18001ccee  pop     rdi
0x18001ccef  pop     rsi
0x18001ccf0  pop     rbp
0x18001ccf1  pop     rbx
0x18001ccf2  retn
0x18001ccf4  mov     eax, 80004005h
0x18001ccf9  jmp     short loc_18001CCE6
0x18001ccfb  mov     r9d, 2; ImpersonationLevel
0x18001cd01  mov     [rsp+78h+phNewToken], rax; phNewToken
0x18001cd06  xor     r8d, r8d; lpTokenAttributes
0x18001cd09  mov     [rsp+78h+TokenType], r9d; TokenType
0x18001cd0e  mov     rcx, rsi; hExistingToken
0x18001cd11  lea     edx, [r9+0Ah]; dwDesiredAccess
0x18001cd15  call    cs:__imp_DuplicateTokenEx
0x18001cd1c  nop     dword ptr [rax+rax+00h]
0x18001cd21  test    eax, eax
0x18001cd23  jnz     short loc_18001CCBC
0x18001cd25  call    cs:__imp_GetLastError
0x18001cd2c  nop     dword ptr [rax+rax+00h]
0x18001cd31  mov     ebx, eax
0x18001cd33  test    eax, eax
0x18001cd35  jle     short loc_18001CD3D
0x18001cd37  movzx   ebx, ax
0x18001cd3a  or      ebx, r14d
0x18001cd3d  test    ebx, ebx
0x18001cd3f  js      short loc_18001CCDC
0x18001cd41  jmp     loc_18001CCBC
0x18001cd46  call    cs:__imp_GetLastError
0x18001cd4d  nop     dword ptr [rax+rax+00h]
0x18001cd52  mov     ebx, eax
0x18001cd54  test    eax, eax
0x18001cd56  jle     short loc_18001CCDC
0x18001cd58  movzx   ebx, ax
0x18001cd5b  or      ebx, r14d
0x18001cd5e  jmp     loc_18001CCDC
```
