# NfsTestDomainMappingStore(ushort *,CNfsTaskContext *)

- ea: `0x180025158`
- end: `0x1800252cf`
- name: `?NfsTestDomainMappingStore@@YAKPEAGPEAVCNfsTaskContext@@@Z`
- size: `375`
- prototype: `unsigned int __fastcall(PCWSTR SourceString, struct CNfsTaskContext *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180013724`
- `0x180024fb8`

## callees

- `0x180021ba4`
- `0x180025158`
- `0x18002b368`
- `0x18002b4ac`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `msvcrt!wcstoul` at `0x18002521a`
- `msvcrt!wcstoul` at `0x18002521a`
- `ntdll!RtlInitUnicodeString` at `0x1800251a8`
- `ntdll!RtlInitUnicodeString` at `0x1800251a8`
- `KERNEL32!HeapFree` at `0x1800252a4`
- `KERNEL32!HeapFree` at `0x1800252a4`
- `KERNEL32!GetProcessHeap` at `0x180025296`
- `KERNEL32!GetProcessHeap` at `0x180025296`
- `ADVAPI32!LsaNtStatusToWinError` at `0x1800251dd`
- `ADVAPI32!LsaNtStatusToWinError` at `0x1800251dd`

## pseudocode

```c
__int64 __fastcall NfsTestDomainMappingStore(PCWSTR SourceString, struct CNfsTaskContext *a2)
{
  wchar_t *v4; // rsi
  NTSTATUS v5; // eax
  ULONG v6; // eax
  const unsigned __int16 *v7; // rdx
  const unsigned __int16 *v8; // r9
  unsigned int v9; // ebx
  unsigned int v10; // ebp
  unsigned int LdapAttributeValue; // eax
  HANDLE ProcessHeap; // rax
  wchar_t *String; // [rsp+30h] [rbp-268h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-260h] BYREF
  LDAP *ld[68]; // [rsp+50h] [rbp-248h] BYREF

  v4 = 0;
  String = 0;
  DestinationString = 0;
  memset_0(ld, 0, 0x218u);
  RtlInitUnicodeString(&DestinationString, SourceString);
  if ( a2 )
    (**(void (__fastcall ***)(struct CNfsTaskContext *, __int64, PCWSTR))a2)(a2, 1073746015, SourceString);
  v5 = NfsConnectLdap(ld, &DestinationString, 0);
  v6 = LsaNtStatusToWinError(v5);
  v9 = v6;
  if ( v6 )
  {
    if ( !a2 )
      goto LABEL_16;
    (*(void (__fastcall **)(struct CNfsTaskContext *, _QWORD, __int64, PCWSTR))(*(_QWORD *)a2 + 40LL))(
      a2,
      v6,
      3221229661LL,
      SourceString);
    goto LABEL_15;
  }
  v10 = 3;
  LdapAttributeValue = NfsGetLdapAttributeValue(
                         ld[0],
                         v7,
                         L"domainFunctionality",
                         v8,
                         (const unsigned __int16 **)&String);
  v4 = String;
  v9 = LdapAttributeValue;
  if ( !LdapAttributeValue )
    v10 = wcstoul(String, 0, 0);
  NfsDisconnectLdap(ld);
  if ( v9 )
  {
LABEL_9:
    if ( !a2 )
      goto LABEL_16;
LABEL_15:
    (*(void (__fastcall **)(struct CNfsTaskContext *, _QWORD, __int64))(*(_QWORD *)a2 + 40LL))(a2, v9, 3221229660LL);
    goto LABEL_16;
  }
  if ( v10 < 2 )
  {
    v9 = 50;
    goto LABEL_9;
  }
  if ( a2 )
    (**(void (__fastcall ***)(struct CNfsTaskContext *, __int64))a2)(a2, 1073746017);
LABEL_16:
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
0x180025158  mov     [rsp+arg_10], rbx
0x18002515d  push    rbp
0x18002515e  push    rsi
0x18002515f  push    rdi
0x180025160  sub     rsp, 280h
0x180025167  mov     rax, cs:__security_cookie
0x18002516e  xor     rax, rsp
0x180025171  mov     [rsp+298h+var_28], rax
0x180025179  mov     rdi, rdx
0x18002517c  mov     rbp, rcx
0x18002517f  xorps   xmm0, xmm0
0x180025182  lea     rcx, [rsp+298h+ld]; void *
0x180025187  xor     esi, esi
0x180025189  xor     edx, edx; Val
0x18002518b  mov     r8d, 218h; Size
0x180025191  mov     [rsp+298h+String], rsi
0x180025196  movups  xmmword ptr [rsp+298h+DestinationString.Length], xmm0
0x18002519b  call    memset_0
0x1800251a0  mov     rdx, rbp; SourceString
0x1800251a3  lea     rcx, [rsp+298h+DestinationString]; DestinationString
0x1800251a8  call    cs:__imp_RtlInitUnicodeString
0x1800251ae  test    rdi, rdi
0x1800251b1  jz      short loc_1800251C9
0x1800251b3  mov     rax, [rdi]
0x1800251b6  mov     r8, rbp
0x1800251b9  mov     edx, 4000105Fh
0x1800251be  mov     rcx, rdi
0x1800251c1  mov     rax, [rax]
0x1800251c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251c9  xor     r8d, r8d
0x1800251cc  lea     rdx, [rsp+298h+DestinationString]
0x1800251d1  lea     rcx, [rsp+298h+ld]
0x1800251d6  call    NfsConnectLdap
0x1800251db  mov     ecx, eax; Status
0x1800251dd  call    cs:__imp_LsaNtStatusToWinError
0x1800251e3  mov     ebx, eax
0x1800251e5  test    eax, eax
0x1800251e7  jnz     short loc_18002525B
0x1800251e9  mov     rcx, [rsp+298h+ld]; ld
0x1800251ee  lea     ebp, [rax+3]
0x1800251f1  lea     rax, [rsp+298h+String]
0x1800251f6  lea     r8, aDomainfunction; "domainFunctionality"
0x1800251fd  mov     [rsp+298h+var_278], rax; unsigned __int16 **
0x180025202  call    ?NfsGetLdapAttributeValue@@YAKPEAUldap@@PEBG11PEAPEBG@Z; NfsGetLdapAttributeValue(ldap *,ushort const *,ushort const *,ushort const *,ushort const * *)
0x180025207  mov     rsi, [rsp+298h+String]
0x18002520c  mov     ebx, eax
0x18002520e  test    eax, eax
0x180025210  jnz     short loc_180025222
0x180025212  xor     r8d, r8d; Radix
0x180025215  xor     edx, edx; EndPtr
0x180025217  mov     rcx, rsi; String
0x18002521a  call    cs:__imp_wcstoul
0x180025220  mov     ebp, eax
0x180025222  lea     rcx, [rsp+298h+ld]
0x180025227  call    NfsDisconnectLdap
0x18002522c  test    ebx, ebx
0x18002522e  jnz     short loc_18002523A
0x180025230  cmp     ebp, 2
0x180025233  jnb     short loc_180025241
0x180025235  mov     ebx, 32h ; '2'
0x18002523a  test    rdi, rdi
0x18002523d  jz      short loc_180025291
0x18002523f  jmp     short loc_18002527A
0x180025241  test    rdi, rdi
0x180025244  jz      short loc_180025291
0x180025246  mov     rax, [rdi]
0x180025249  mov     edx, 40001061h
0x18002524e  mov     rcx, rdi
0x180025251  mov     rax, [rax]
0x180025254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025259  jmp     short loc_180025291
0x18002525b  test    rdi, rdi
0x18002525e  jz      short loc_180025291
0x180025260  mov     rax, [rdi]
0x180025263  mov     r9, rbp
0x180025266  mov     r8d, 0C000105Dh
0x18002526c  mov     edx, ebx
0x18002526e  mov     rcx, rdi
0x180025271  mov     rax, [rax+28h]
0x180025275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002527a  mov     rax, [rdi]
0x18002527d  mov     r8d, 0C000105Ch
0x180025283  mov     edx, ebx
0x180025285  mov     rcx, rdi
0x180025288  mov     rax, [rax+28h]
0x18002528c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025291  test    rsi, rsi
0x180025294  jz      short loc_1800252AA
0x180025296  call    cs:__imp_GetProcessHeap
0x18002529c  mov     r8, rsi; lpMem
0x18002529f  xor     edx, edx; dwFlags
0x1800252a1  mov     rcx, rax; hHeap
0x1800252a4  call    cs:__imp_HeapFree
0x1800252aa  mov     eax, ebx
0x1800252ac  mov     rcx, [rsp+298h+var_28]
0x1800252b4  xor     rcx, rsp; StackCookie
0x1800252b7  call    __security_check_cookie
0x1800252bc  mov     rbx, [rsp+298h+arg_10]
0x1800252c4  add     rsp, 280h
0x1800252cb  pop     rdi
0x1800252cc  pop     rsi
0x1800252cd  pop     rbp
0x1800252ce  retn
```
