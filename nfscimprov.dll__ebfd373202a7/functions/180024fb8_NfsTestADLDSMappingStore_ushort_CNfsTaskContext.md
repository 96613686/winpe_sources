# NfsTestADLDSMappingStore(ushort *,CNfsTaskContext *)

- ea: `0x180024fb8`
- end: `0x180025151`
- name: `?NfsTestADLDSMappingStore@@YAKPEAGPEAVCNfsTaskContext@@@Z`
- size: `409`
- prototype: `unsigned int __fastcall(PCWSTR SourceString, struct CNfsTaskContext *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x180013724`

## callees

- `0x180021ba4`
- `0x180024d88`
- `0x180024fb8`
- `0x180025158`
- `0x18002b368`
- `0x18002b4ac`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180025015`
- `ntdll!RtlInitUnicodeString` at `0x180025015`
- `KERNEL32!HeapFree` at `0x180025122`
- `KERNEL32!HeapFree` at `0x180025122`
- `KERNEL32!GetProcessHeap` at `0x180025114`
- `KERNEL32!GetProcessHeap` at `0x180025114`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180025045`
- `ADVAPI32!LsaNtStatusToWinError` at `0x180025045`

## pseudocode

```c
__int64 __fastcall NfsTestADLDSMappingStore(PCWSTR SourceString, struct CNfsTaskContext *a2)
{
  unsigned __int16 *v4; // rsi
  NTSTATUS v5; // eax
  ULONG v6; // eax
  const unsigned __int16 *v7; // rdx
  const unsigned __int16 *v8; // r9
  unsigned int v9; // ebx
  unsigned int LdapAttributeValue; // eax
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  LDAP *ld[68]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = 0;
  lpMem = 0;
  DestinationString = 0;
  memset_0(ld, 0, 0x218u);
  RtlInitUnicodeString(&DestinationString, SourceString);
  (**(void (__fastcall ***)(struct CNfsTaskContext *, __int64, PCWSTR))a2)(a2, 1073746016, SourceString);
  v5 = NfsConnectLdap(ld, &DestinationString, 0);
  v6 = LsaNtStatusToWinError(v5);
  v9 = v6;
  if ( v6 )
  {
    (*(void (__fastcall **)(struct CNfsTaskContext *, _QWORD, __int64, PCWSTR))(*(_QWORD *)a2 + 40LL))(
      a2,
      v6,
      3221229661LL,
      SourceString);
  }
  else
  {
    LdapAttributeValue = NfsGetLdapAttributeValue(
                           ld[0],
                           v7,
                           L"SchemaNamingContext",
                           v8,
                           (const unsigned __int16 **)&lpMem);
    v4 = (unsigned __int16 *)lpMem;
    v9 = LdapAttributeValue;
    if ( LdapAttributeValue )
      goto LABEL_8;
    v9 = NfsCheckForIdentitySchema(ld[0], (const unsigned __int16 *)lpMem, 1u);
    if ( !v9 )
      v9 = NfsCheckForIdentitySchema(ld[0], v4, 0);
    if ( v9 == 1168 )
      v9 = NfsTestDomainMappingStore(SourceString, 0);
    if ( v9 )
LABEL_8:
      (*(void (__fastcall **)(struct CNfsTaskContext *, _QWORD, __int64))(*(_QWORD *)a2 + 40LL))(a2, v9, 3221229662LL);
    NfsDisconnectLdap(ld);
    if ( !v9 )
      (**(void (__fastcall ***)(struct CNfsTaskContext *, __int64))a2)(a2, 1073746017);
  }
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  return v9;
}

```

## disassembly

```asm
0x180024fb8  mov     [rsp-8+arg_10], rbx
0x180024fbd  mov     [rsp-8+arg_18], rsi
0x180024fc2  push    rbp
0x180024fc3  push    rdi
0x180024fc4  push    r14
0x180024fc6  lea     rbp, [rsp-180h]
0x180024fce  sub     rsp, 280h
0x180024fd5  mov     rax, cs:__security_cookie
0x180024fdc  xor     rax, rsp
0x180024fdf  mov     [rbp+190h+var_20], rax
0x180024fe6  mov     rdi, rdx
0x180024fe9  mov     r14, rcx
0x180024fec  xorps   xmm0, xmm0
0x180024fef  lea     rcx, [rsp+290h+ld]; void *
0x180024ff4  xor     esi, esi
0x180024ff6  xor     edx, edx; Val
0x180024ff8  mov     r8d, 218h; Size
0x180024ffe  mov     [rsp+290h+lpMem], rsi
0x180025003  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x180025008  call    memset_0
0x18002500d  mov     rdx, r14; SourceString
0x180025010  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x180025015  call    cs:__imp_RtlInitUnicodeString
0x18002501b  mov     rax, [rdi]
0x18002501e  mov     r8, r14
0x180025021  mov     edx, 40001060h
0x180025026  mov     rcx, rdi
0x180025029  mov     rax, [rax]
0x18002502c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025031  xor     r8d, r8d
0x180025034  lea     rdx, [rsp+290h+DestinationString]
0x180025039  lea     rcx, [rsp+290h+ld]
0x18002503e  call    NfsConnectLdap
0x180025043  mov     ecx, eax; Status
0x180025045  call    cs:__imp_LsaNtStatusToWinError
0x18002504b  mov     ebx, eax
0x18002504d  test    eax, eax
0x18002504f  jnz     loc_1800250F5
0x180025055  mov     rcx, [rsp+290h+ld]; ld
0x18002505a  lea     rax, [rsp+290h+lpMem]
0x18002505f  lea     r8, aSchemanamingco; "SchemaNamingContext"
0x180025066  mov     [rsp+290h+var_270], rax; unsigned __int16 **
0x18002506b  call    ?NfsGetLdapAttributeValue@@YAKPEAUldap@@PEBG11PEAPEBG@Z; NfsGetLdapAttributeValue(ldap *,ushort const *,ushort const *,ushort const *,ushort const * *)
0x180025070  mov     rsi, [rsp+290h+lpMem]
0x180025075  mov     ebx, eax
0x180025077  test    eax, eax
0x180025079  jnz     short loc_1800250BB
0x18002507b  mov     rcx, [rsp+290h+ld]; ld
0x180025080  mov     r8b, 1; unsigned __int8
0x180025083  mov     rdx, rsi; unsigned __int16 *
0x180025086  call    ?NfsCheckForIdentitySchema@@YAKPEAUldap@@PEBGE@Z; NfsCheckForIdentitySchema(ldap *,ushort const *,uchar)
0x18002508b  mov     ebx, eax
0x18002508d  test    eax, eax
0x18002508f  jnz     short loc_1800250A3
0x180025091  mov     rcx, [rsp+290h+ld]; ld
0x180025096  xor     r8d, r8d; unsigned __int8
0x180025099  mov     rdx, rsi; unsigned __int16 *
0x18002509c  call    ?NfsCheckForIdentitySchema@@YAKPEAUldap@@PEBGE@Z; NfsCheckForIdentitySchema(ldap *,ushort const *,uchar)
0x1800250a1  mov     ebx, eax
0x1800250a3  cmp     ebx, 490h
0x1800250a9  jnz     short loc_1800250B7
0x1800250ab  xor     edx, edx; struct CNfsTaskContext *
0x1800250ad  mov     rcx, r14; SourceString
0x1800250b0  call    ?NfsTestDomainMappingStore@@YAKPEAGPEAVCNfsTaskContext@@@Z; NfsTestDomainMappingStore(ushort *,CNfsTaskContext *)
0x1800250b5  mov     ebx, eax
0x1800250b7  test    ebx, ebx
0x1800250b9  jz      short loc_1800250D2
0x1800250bb  mov     rax, [rdi]
0x1800250be  mov     r8d, 0C000105Eh
0x1800250c4  mov     edx, ebx
0x1800250c6  mov     rcx, rdi
0x1800250c9  mov     rax, [rax+28h]
0x1800250cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250d2  lea     rcx, [rsp+290h+ld]
0x1800250d7  call    NfsDisconnectLdap
0x1800250dc  test    ebx, ebx
0x1800250de  jnz     short loc_18002510F
0x1800250e0  mov     rax, [rdi]
0x1800250e3  mov     edx, 40001061h
0x1800250e8  mov     rcx, rdi
0x1800250eb  mov     rax, [rax]
0x1800250ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250f3  jmp     short loc_18002510F
0x1800250f5  mov     rax, [rdi]
0x1800250f8  mov     r9, r14
0x1800250fb  mov     r8d, 0C000105Dh
0x180025101  mov     edx, ebx
0x180025103  mov     rcx, rdi
0x180025106  mov     rax, [rax+28h]
0x18002510a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002510f  test    rsi, rsi
0x180025112  jz      short loc_180025128
0x180025114  call    cs:__imp_GetProcessHeap
0x18002511a  mov     r8, rsi; lpMem
0x18002511d  xor     edx, edx; dwFlags
0x18002511f  mov     rcx, rax; hHeap
0x180025122  call    cs:__imp_HeapFree
0x180025128  mov     eax, ebx
0x18002512a  mov     rcx, [rbp+190h+var_20]
0x180025131  xor     rcx, rsp; StackCookie
0x180025134  call    __security_check_cookie
0x180025139  lea     r11, [rsp+290h+var_10]
0x180025141  mov     rbx, [r11+30h]
0x180025145  mov     rsi, [r11+38h]
0x180025149  mov     rsp, r11
0x18002514c  pop     r14
0x18002514e  pop     rdi
0x18002514f  pop     rbp
0x180025150  retn
```
