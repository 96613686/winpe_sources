# CSecurityLogHelper::LogSecurityEvent(ushort,ulong,ushort,_AUDIT_PARAM *)

- ea: `0x1800154e0`
- end: `0x18001569a`
- name: `?LogSecurityEvent@CSecurityLogHelper@@QEAAJGKGPEAU_AUDIT_PARAM@@@Z`
- size: `442`
- prototype: `signed int __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned __int16, unsigned int, unsigned __int16, struct _AUDIT_PARAM *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800150c0`

## callees

- `0x180015304`
- `0x1800154e0`
- `0x1800181a2`
- `0x1800181e0`

## import_xrefs

- `AUTHZ!AuthziInitializeAuditParamsFromArray` at `0x1800155b2`
- `AUTHZ!AuthziInitializeAuditParamsFromArray` at `0x1800155b2`
- `AUTHZ!AuthziLogAuditEvent` at `0x18001564f`
- `AUTHZ!AuthziLogAuditEvent` at `0x18001564f`
- `AUTHZ!AuthziInitializeAuditEvent` at `0x180015637`
- `AUTHZ!AuthziInitializeAuditEvent` at `0x180015637`
- `AUTHZ!AuthzFreeAuditEvent` at `0x180015673`
- `AUTHZ!AuthzFreeAuditEvent` at `0x180015673`
- `KERNEL32!GetLastError` at `0x1800155bc`
- `KERNEL32!GetLastError` at `0x180015659`
- `KERNEL32!GetLastError` at `0x1800155bc`
- `KERNEL32!GetLastError` at `0x180015659`

## pseudocode

```c
signed int __fastcall CSecurityLogHelper::LogSecurityEvent(
        LPCRITICAL_SECTION lpCriticalSection,
        unsigned __int16 a2,
        unsigned int a3,
        unsigned __int16 a4,
        struct _AUDIT_PARAM *a5)
{
  __int64 v6; // rdx
  unsigned int DebugInfo; // r8d
  signed int result; // eax
  unsigned int v12; // ebx
  PRTL_CRITICAL_SECTION_DEBUG v13; // rdx
  PRTL_CRITICAL_SECTION_DEBUG v14; // rdx
  signed int LastError; // eax
  struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *v16; // [rsp+60h] [rbp-A0h] BYREF
  AUTHZ_AUDIT_EVENT_HANDLE hAuditEvent; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v18[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v19[1024]; // [rsp+90h] [rbp-70h] BYREF

  v6 = 0;
  v16 = 0;
  DebugInfo = (unsigned int)lpCriticalSection[14].DebugInfo;
  if ( DebugInfo )
  {
    while ( *((_WORD *)&lpCriticalSection[1].LockCount + 8 * v6) != a2 )
    {
      v6 = (unsigned int)(v6 + 1);
      if ( (unsigned int)v6 >= DebugInfo )
        goto LABEL_4;
    }
    v12 = 0;
    v16 = (struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *)*((_QWORD *)&lpCriticalSection[1].OwningThread + 2 * (unsigned int)v6);
  }
  else
  {
LABEL_4:
    result = CSecurityLogHelper::InitEventType(lpCriticalSection, a2, a4, &v16);
    v12 = result;
    if ( result < 0 )
      return result;
  }
  v18[0] = 0;
  v18[1] = 0;
  memset_0(v19, 0, sizeof(v19));
  v13 = lpCriticalSection[1].DebugInfo;
  v18[2] = v19;
  if ( (unsigned int)AuthziInitializeAuditParamsFromArray(a3, v13, a4, a5, v18)
    && (v14 = lpCriticalSection[1].DebugInfo,
        hAuditEvent = 0,
        (unsigned int)AuthziInitializeAuditEvent(
                        0,
                        v14,
                        v16,
                        v18,
                        0,
                        -1,
                        &dword_18001C7CC,
                        &dword_18001C7CC,
                        &dword_18001C7CC,
                        &dword_18001C7CC,
                        &hAuditEvent)) )
  {
    if ( !(unsigned int)AuthziLogAuditEvent(0, hAuditEvent, 0) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
    }
    AuthzFreeAuditEvent(hAuditEvent);
    return v12;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800154e0  push    rbp
0x1800154e2  push    rbx
0x1800154e3  push    rsi
0x1800154e4  push    rdi
0x1800154e5  push    r14
0x1800154e7  push    r15
0x1800154e9  lea     rbp, [rsp-3A8h]
0x1800154f1  sub     rsp, 4A8h
0x1800154f8  mov     rax, cs:__security_cookie
0x1800154ff  xor     rax, rsp
0x180015502  mov     [rbp+3D0h+var_40], rax
0x180015509  mov     r15, [rbp+3D0h+arg_20]
0x180015510  movzx   r10d, dx
0x180015514  xor     edx, edx
0x180015516  mov     [rsp+4D0h+var_470], 0
0x18001551f  mov     r14d, r8d
0x180015522  movzx   esi, r9w
0x180015526  mov     r8d, [rcx+230h]
0x18001552d  mov     rdi, rcx
0x180015530  test    r8d, r8d
0x180015533  jz      short loc_180015550
0x180015535  lea     rax, [rdx+3]
0x180015539  mov     ecx, edx
0x18001553b  add     rax, rax
0x18001553e  cmp     [rdi+rax*8], r10w
0x180015543  jz      loc_1800155D7
0x180015549  inc     edx
0x18001554b  cmp     edx, r8d
0x18001554e  jb      short loc_180015535
0x180015550  lea     r9, [rsp+4D0h+var_470]; struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ **
0x180015555  movzx   r8d, si; unsigned __int16
0x180015559  movzx   edx, r10w; unsigned __int16
0x18001555d  mov     rcx, rdi; lpCriticalSection
0x180015560  call    ?InitEventType@CSecurityLogHelper@@AEAAJGGAEAPEAUAUTHZ_AUDIT_EVENT_TYPE_HANDLE__@@@Z; CSecurityLogHelper::InitEventType(ushort,ushort,AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ * &)
0x180015565  mov     ebx, eax
0x180015567  test    eax, eax
0x180015569  js      loc_18001567B
0x18001556f  xor     edx, edx; Val
0x180015571  mov     [rsp+4D0h+var_460], 0
0x18001557a  mov     r8d, 400h; Size
0x180015580  mov     [rsp+4D0h+var_458], 0
0x180015589  lea     rcx, [rbp+3D0h+var_440]; void *
0x18001558d  call    memset_0
0x180015592  mov     rdx, [rdi+28h]
0x180015596  lea     rax, [rbp+3D0h+var_440]
0x18001559a  mov     [rbp+3D0h+var_450], rax
0x18001559e  mov     r9, r15
0x1800155a1  lea     rax, [rsp+4D0h+var_460]
0x1800155a6  movzx   r8d, si
0x1800155aa  mov     ecx, r14d
0x1800155ad  mov     [rsp+4D0h+var_4B0], rax
0x1800155b2  call    cs:__imp_AuthziInitializeAuditParamsFromArray
0x1800155b8  test    eax, eax
0x1800155ba  jnz     short loc_1800155E8
0x1800155bc  call    cs:__imp_GetLastError
0x1800155c2  test    eax, eax
0x1800155c4  jle     loc_18001567B
0x1800155ca  movzx   eax, ax
0x1800155cd  or      eax, 80070000h
0x1800155d2  jmp     loc_18001567B
0x1800155d7  xor     ebx, ebx
0x1800155d9  add     rcx, rcx
0x1800155dc  mov     rax, [rdi+rcx*8+38h]
0x1800155e1  mov     [rsp+4D0h+var_470], rax
0x1800155e6  jmp     short loc_18001556F
0x1800155e8  mov     r8, [rsp+4D0h+var_470]
0x1800155ed  lea     rax, [rsp+4D0h+hAuditEvent]
0x1800155f2  mov     rdx, [rdi+28h]
0x1800155f6  lea     r9, [rsp+4D0h+var_460]
0x1800155fb  mov     [rsp+4D0h+var_480], rax
0x180015600  xor     ecx, ecx
0x180015602  lea     rax, dword_18001C7CC
0x180015609  mov     [rsp+4D0h+hAuditEvent], 0
0x180015612  mov     [rsp+4D0h+var_488], rax
0x180015617  mov     [rsp+4D0h+var_490], rax
0x18001561c  mov     [rsp+4D0h+var_498], rax
0x180015621  mov     [rsp+4D0h+var_4A0], rax
0x180015626  mov     [rsp+4D0h+var_4A8], 0FFFFFFFFh
0x18001562e  mov     [rsp+4D0h+var_4B0], 0
0x180015637  call    cs:__imp_AuthziInitializeAuditEvent
0x18001563d  test    eax, eax
0x18001563f  jz      loc_1800155BC
0x180015645  mov     rdx, [rsp+4D0h+hAuditEvent]
0x18001564a  xor     r8d, r8d
0x18001564d  xor     ecx, ecx
0x18001564f  call    cs:__imp_AuthziLogAuditEvent
0x180015655  test    eax, eax
0x180015657  jnz     short loc_18001566E
0x180015659  call    cs:__imp_GetLastError
0x18001565f  mov     ebx, eax
0x180015661  test    eax, eax
0x180015663  jle     short loc_18001566E
0x180015665  movzx   ebx, ax
0x180015668  or      ebx, 80070000h
0x18001566e  mov     rcx, [rsp+4D0h+hAuditEvent]; hAuditEvent
0x180015673  call    cs:__imp_AuthzFreeAuditEvent
0x180015679  mov     eax, ebx
0x18001567b  mov     rcx, [rbp+3D0h+var_40]
0x180015682  xor     rcx, rsp; StackCookie
0x180015685  call    __security_check_cookie
0x18001568a  add     rsp, 4A8h
0x180015691  pop     r15
0x180015693  pop     r14
0x180015695  pop     rdi
0x180015696  pop     rsi
0x180015697  pop     rbx
0x180015698  pop     rbp
0x180015699  retn
```
