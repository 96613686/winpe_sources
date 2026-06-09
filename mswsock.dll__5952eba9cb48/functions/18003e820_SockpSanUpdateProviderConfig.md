# SockpSanUpdateProviderConfig

- ea: `0x18003e820`
- end: `0x18003eb1e`
- name: `SockpSanUpdateProviderConfig`
- size: `766`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180042bc8`
- `0x180042c70`

## callees

- `0x1800222f0`
- `0x180038104`
- `0x18003e820`
- `0x18003eb24`
- `0x180042b50`
- `0x180053010`

## import_xrefs

- `ntdll!RtlQueryRegistryValuesEx` at `0x18003ea10`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18003ea10`
- `ntdll!NtOpenKey` at `0x18003e9a4`
- `ntdll!NtOpenKey` at `0x18003e9a4`
- `ntdll!NtClose` at `0x18003ea21`
- `ntdll!NtClose` at `0x18003ea21`
- `ntdll!RtlInitUnicodeString` at `0x18003e961`
- `ntdll!RtlInitUnicodeString` at `0x18003e961`
- `ntdll!RtlFreeHeap` at `0x18003eab8`
- `ntdll!RtlFreeHeap` at `0x18003eab8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003e88f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003e88f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ea79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ea79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ea41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ea41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e8c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e8c3`

## string_xrefs

- `0x18003e955`: `\Registry\Machine\System\CurrentControlSet\Services\Winsock\Parameters\TCP on SAN`

## pseudocode

```c
__int64 SockpSanUpdateProviderConfig()
{
  __m256i *p_P; // rbx
  int v1; // edi
  int v2; // r14d
  PVOID *i; // rsi
  PVOID *v4; // rax
  __m256i *v5; // rax
  __int64 v6; // rcx
  _QWORD *v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  void *KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall *v14)(int, int, int, int, __int64, int); // [rsp+80h] [rbp-80h] BYREF
  int v15; // [rsp+88h] [rbp-78h]
  __int64 v16; // [rsp+90h] [rbp-70h]
  __int64 v17; // [rsp+98h] [rbp-68h]
  int v18; // [rsp+A0h] [rbp-60h]
  __int64 v19; // [rsp+A8h] [rbp-58h]
  int v20; // [rsp+B0h] [rbp-50h]
  __int64 v21; // [rsp+B8h] [rbp-48h]
  int v22; // [rsp+C0h] [rbp-40h]
  __int64 v23; // [rsp+C8h] [rbp-38h]
  __int64 v24; // [rsp+D0h] [rbp-30h]
  int v25; // [rsp+D8h] [rbp-28h]
  __int64 v26; // [rsp+E0h] [rbp-20h]
  int v27; // [rsp+E8h] [rbp-18h]
  __m256i P; // [rsp+F0h] [rbp-10h] BYREF

  p_P = &P;
  memset(&P, 0, sizeof(P));
  KeyHandle = 0;
  v1 = 0;
  v2 = 4;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( SockSanEnabled == 2 && !WaitForSingleObject(SockSanSCAutostartEvent, 0) )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 66, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
    CloseHandle(SockSanSCAutostartEvent);
    SockSanSCAutostartEvent = (HANDLE)-1LL;
    SockSanEnabled = 1;
  }
  for ( i = (PVOID *)SockSanProviderList; i != &SockSanProviderList; i = (PVOID *)*i )
  {
    if ( v1 >= v2 )
    {
      v4 = i;
      do
      {
        v4 = (PVOID *)*v4;
        ++v2;
      }
      while ( v4 != &SockSanProviderList );
      v5 = (__m256i *)((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(
                        SockPrivateHeap,
                        0,
                        8LL * v2);
      p_P = v5;
      if ( !v5 )
        return 10055;
      *v5 = P;
    }
    v6 = v1++;
    p_P->m256i_i64[v6] = (__int64)i;
  }
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Winsock\\Parameters\\TCP on SAN");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    v14 = SockpSanProcessProvider;
    v17 = v1;
    v15 = 0;
    v16 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    RtlQueryRegistryValuesEx(0x40000000, KeyHandle, &v14, p_P, 0);
    NtClose(KeyHandle);
  }
  while ( v1 > 0 )
  {
    if ( p_P->m256i_i64[--v1] )
    {
      EnterCriticalSection(&SockSanProvListCritSec);
      v8 = (_QWORD *)p_P->m256i_i64[v1];
      v9 = *v8;
      if ( *(_QWORD **)(*v8 + 8LL) != v8 || (v10 = (_QWORD *)v8[1], (_QWORD *)*v10 != v8) )
        __fastfail(3u);
      *v10 = v9;
      *(_QWORD *)(v9 + 8) = v10;
      LeaveCriticalSection(&SockSanProvListCritSec);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(p_P->m256i_i64[v1] + 16), 0xFFFFFFFF) == 1 )
        SockSanFreeProvider((PVOID)p_P->m256i_i64[v1]);
    }
  }
  if ( p_P != &P )
    RtlFreeHeap(SockPrivateHeap, 0, p_P);
  if ( SockSanProviderList != &SockSanProviderList )
    return SockpSanUpdateSubnetMap();
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_(1025, 67, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
  return 10107;
}

```

## disassembly

```asm
0x18003e820  push    rbp
0x18003e822  push    rbx
0x18003e823  push    rsi
0x18003e824  push    rdi
0x18003e825  push    r13
0x18003e827  push    r14
0x18003e829  push    r15
0x18003e82b  lea     rbp, [rsp-20h]
0x18003e830  sub     rsp, 120h
0x18003e837  mov     rax, cs:__security_cookie
0x18003e83e  xor     rax, rsp
0x18003e841  mov     [rbp+50h+var_40], rax
0x18003e845  xor     r15d, r15d
0x18003e848  lea     rbx, [rbp+50h+P]
0x18003e84c  xorps   xmm0, xmm0
0x18003e84f  mov     qword ptr [rbp+50h+P], r15
0x18003e853  xor     eax, eax
0x18003e855  mov     [rsp+150h+KeyHandle], r15
0x18003e85a  cmp     cs:SockSanEnabled, 2
0x18003e861  mov     edi, r15d
0x18003e864  movups  xmmword ptr [rsp+150h+ObjectAttributes.ObjectName], xmm0
0x18003e869  lea     r14d, [r15+4]
0x18003e86d  mov     [rbp+50h+var_48], rax
0x18003e871  movups  [rbp+50h+P+8], xmm0
0x18003e875  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x18003e87a  movups  xmmword ptr [rsp+150h+ObjectAttributes.Length], xmm0
0x18003e87f  movups  xmmword ptr [rsp+150h+ObjectAttributes+1Ch], xmm0
0x18003e884  jnz     short loc_18003E8E4
0x18003e886  mov     rcx, cs:SockSanSCAutostartEvent; hHandle
0x18003e88d  xor     edx, edx; dwMilliseconds
0x18003e88f  call    cs:__imp_WaitForSingleObject
0x18003e896  nop     dword ptr [rax+rax+00h]
0x18003e89b  test    eax, eax
0x18003e89d  jnz     short loc_18003E8E4
0x18003e89f  test    byte ptr cs:xmmword_180063D60, 2
0x18003e8a6  jz      short loc_18003E8BC
0x18003e8a8  lea     edx, [rax+42h]
0x18003e8ab  mov     ecx, 401h
0x18003e8b0  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x18003e8b7  call    WPP_SF_
0x18003e8bc  mov     rcx, cs:SockSanSCAutostartEvent; hObject
0x18003e8c3  call    cs:__imp_CloseHandle
0x18003e8ca  nop     dword ptr [rax+rax+00h]
0x18003e8cf  mov     cs:SockSanSCAutostartEvent, 0FFFFFFFFFFFFFFFFh
0x18003e8da  mov     cs:SockSanEnabled, 1
0x18003e8e4  mov     rsi, cs:SockSanProviderList
0x18003e8eb  lea     r13, SockSanProviderList
0x18003e8f2  cmp     rsi, r13
0x18003e8f5  jz      short loc_18003E955
0x18003e8f7  cmp     edi, r14d
0x18003e8fa  jl      short loc_18003E93D
0x18003e8fc  mov     rax, rsi
0x18003e8ff  mov     rax, [rax]
0x18003e902  inc     r14d
0x18003e905  cmp     rax, r13
0x18003e908  jnz     short loc_18003E8FF
0x18003e90a  mov     rcx, cs:SockPrivateHeap
0x18003e911  xor     edx, edx
0x18003e913  mov     rax, cs:SockAllocateHeapRoutine
0x18003e91a  movsxd  r8, r14d
0x18003e91d  shl     r8, 3
0x18003e921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e926  mov     rbx, rax
0x18003e929  test    rax, rax
0x18003e92c  jz      short loc_18003E94B
0x18003e92e  movups  xmm0, [rbp+50h+P]
0x18003e932  movups  xmmword ptr [rax], xmm0
0x18003e935  movups  xmm1, xmmword ptr [rbp+0]
0x18003e939  movups  xmmword ptr [rax+10h], xmm1
0x18003e93d  movsxd  rcx, edi
0x18003e940  inc     edi
0x18003e942  mov     [rbx+rcx*8], rsi
0x18003e946  mov     rsi, [rsi]
0x18003e949  jmp     short loc_18003E8F2
0x18003e94b  mov     eax, 2747h
0x18003e950  jmp     loc_18003EAFF
0x18003e955  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x18003e95c  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x18003e961  call    cs:__imp_RtlInitUnicodeString
0x18003e968  nop     dword ptr [rax+rax+00h]
0x18003e96d  lea     rax, [rsp+150h+DestinationString]
0x18003e972  mov     [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x18003e97a  xorps   xmm0, xmm0
0x18003e97d  mov     [rsp+150h+ObjectAttributes.ObjectName], rax
0x18003e982  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x18003e987  mov     [rsp+150h+ObjectAttributes.RootDirectory], r15
0x18003e98c  mov     edx, 20019h; DesiredAccess
0x18003e991  mov     [rsp+150h+ObjectAttributes.Attributes], 40h ; '@'
0x18003e999  lea     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x18003e99e  movdqu  xmmword ptr [rsp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003e9a4  call    cs:__imp_NtOpenKey
0x18003e9ab  nop     dword ptr [rax+rax+00h]
0x18003e9b0  test    eax, eax
0x18003e9b2  js      loc_18003EA9F
0x18003e9b8  mov     rdx, [rsp+150h+KeyHandle]
0x18003e9bd  lea     rax, SockpSanProcessProvider
0x18003e9c4  mov     [rbp+50h+var_D0], rax
0x18003e9c8  lea     r8, [rbp+50h+var_D0]
0x18003e9cc  movsxd  rax, edi
0x18003e9cf  mov     r9, rbx
0x18003e9d2  mov     ecx, 40000000h
0x18003e9d7  mov     [rbp+50h+var_B8], rax
0x18003e9db  mov     [rbp+50h+var_C8], r15d
0x18003e9df  mov     [rbp+50h+var_C0], r15
0x18003e9e3  mov     [rbp+50h+var_B0], r15d
0x18003e9e7  mov     [rbp+50h+var_A8], r15
0x18003e9eb  mov     [rbp+50h+var_A0], r15d
0x18003e9ef  mov     [rbp+50h+var_98], r15
0x18003e9f3  mov     [rbp+50h+var_90], r15d
0x18003e9f7  mov     [rbp+50h+var_88], r15
0x18003e9fb  mov     [rbp+50h+var_80], r15
0x18003e9ff  mov     [rbp+50h+var_78], r15d
0x18003ea03  mov     [rbp+50h+var_70], r15
0x18003ea07  mov     [rbp+50h+var_68], r15d
0x18003ea0b  mov     [rsp+150h+var_130], r15
0x18003ea10  call    cs:__imp_RtlQueryRegistryValuesEx
0x18003ea17  nop     dword ptr [rax+rax+00h]
0x18003ea1c  mov     rcx, [rsp+150h+KeyHandle]; Handle
0x18003ea21  call    cs:__imp_NtClose
0x18003ea28  nop     dword ptr [rax+rax+00h]
0x18003ea2d  jmp     short loc_18003EA9F
0x18003ea2f  dec     edi
0x18003ea31  movsxd  rsi, edi
0x18003ea34  cmp     [rbx+rsi*8], r15
0x18003ea38  jz      short loc_18003EA9F
0x18003ea3a  lea     rcx, SockSanProvListCritSec; lpCriticalSection
0x18003ea41  call    cs:__imp_EnterCriticalSection
0x18003ea48  nop     dword ptr [rax+rax+00h]
0x18003ea4d  mov     rax, [rbx+rsi*8]
0x18003ea51  mov     rdx, [rax]
0x18003ea54  cmp     [rdx+8], rax
0x18003ea58  jnz     loc_18003EAF3
0x18003ea5e  mov     rcx, [rax+8]
0x18003ea62  cmp     [rcx], rax
0x18003ea65  jnz     loc_18003EAF3
0x18003ea6b  mov     [rcx], rdx
0x18003ea6e  mov     [rdx+8], rcx
0x18003ea72  lea     rcx, SockSanProvListCritSec; lpCriticalSection
0x18003ea79  call    cs:__imp_LeaveCriticalSection
0x18003ea80  nop     dword ptr [rax+rax+00h]
0x18003ea85  mov     rcx, [rbx+rsi*8]
0x18003ea89  or      eax, 0FFFFFFFFh
0x18003ea8c  lock xadd [rcx+10h], eax
0x18003ea91  cmp     eax, 1
0x18003ea94  jnz     short loc_18003EA9F
0x18003ea96  mov     rcx, [rbx+rsi*8]; CompletionContext
0x18003ea9a  call    SockSanFreeProvider
0x18003ea9f  test    edi, edi
0x18003eaa1  jg      short loc_18003EA2F
0x18003eaa3  lea     rax, [rbp+50h+P]
0x18003eaa7  cmp     rbx, rax
0x18003eaaa  jz      short loc_18003EAC4
0x18003eaac  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18003eab3  mov     r8, rbx; P
0x18003eab6  xor     edx, edx; Flags
0x18003eab8  call    cs:__imp_RtlFreeHeap
0x18003eabf  nop     dword ptr [rax+rax+00h]
0x18003eac4  cmp     cs:SockSanProviderList, r13
0x18003eacb  jnz     short loc_18003EAFA
0x18003eacd  test    byte ptr cs:xmmword_180063D60, 2
0x18003ead4  jz      short loc_18003EAEC
0x18003ead6  mov     edx, 43h ; 'C'
0x18003eadb  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x18003eae2  mov     ecx, 401h
0x18003eae7  call    WPP_SF_
0x18003eaec  mov     eax, 277Bh
0x18003eaf1  jmp     short loc_18003EAFF
0x18003eaf3  mov     ecx, 3
0x18003eaf8  int     29h; Win8: RtlFailFast(ecx)
0x18003eafa  call    SockpSanUpdateSubnetMap
0x18003eaff  mov     rcx, [rbp+50h+var_40]
0x18003eb03  xor     rcx, rsp; StackCookie
0x18003eb06  call    __security_check_cookie
0x18003eb0b  add     rsp, 120h
0x18003eb12  pop     r15
0x18003eb14  pop     r14
0x18003eb16  pop     r13
0x18003eb18  pop     rdi
0x18003eb19  pop     rsi
0x18003eb1a  pop     rbx
0x18003eb1b  pop     rbp
0x18003eb1c  retn
```
