# NTEventLog::Initialize(void)

- ea: `0x180015100`
- end: `0x1800151f7`
- name: `?Initialize@NTEventLog@@UEAAJXZ`
- size: `247`
- prototype: `signed int __fastcall(NTEventLog *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180012be0`

## callees

- `0x180015100`
- `0x1800172b8`

## import_xrefs

- `AUTHZ!AuthzInitializeResourceManager` at `0x180015184`
- `AUTHZ!AuthzInitializeResourceManager` at `0x180015184`
- `ntdll!RtlAdjustPrivilege` at `0x18001512c`
- `ntdll!RtlAdjustPrivilege` at `0x18001512c`
- `ntdll!RtlNtStatusToDosError` at `0x18001513d`
- `ntdll!RtlNtStatusToDosError` at `0x18001513d`
- `ADVAPI32!DeregisterEventSource` at `0x1800151dc`
- `ADVAPI32!DeregisterEventSource` at `0x1800151dc`
- `ADVAPI32!RegisterEventSourceW` at `0x1800151aa`
- `ADVAPI32!RegisterEventSourceW` at `0x1800151aa`
- `KERNEL32!SetLastError` at `0x180015145`
- `KERNEL32!SetLastError` at `0x180015145`
- `KERNEL32!GetLastError` at `0x18001514b`
- `KERNEL32!GetLastError` at `0x18001518e`
- `KERNEL32!GetLastError` at `0x1800151b9`
- `KERNEL32!GetLastError` at `0x18001514b`
- `KERNEL32!GetLastError` at `0x18001518e`
- `KERNEL32!GetLastError` at `0x1800151b9`

## pseudocode

```c
signed int __fastcall NTEventLog::Initialize(NTEventLog *this)
{
  int v2; // eax
  ULONG v3; // eax
  signed int result; // eax
  bool v5; // sf
  bool v6; // sf
  HANDLE v7; // rax
  HRESULT v8; // edi
  unsigned __int8 OldValue; // [rsp+48h] [rbp+10h] BYREF

  OldValue = 0;
  *(__m128i *)((char *)this + 88) = _mm_load_si128((const __m128i *)&_xmm);
  v2 = RtlAdjustPrivilege(0x15u, 1u, 0, &OldValue);
  if ( v2 >= 0 )
    goto LABEL_8;
  v3 = RtlNtStatusToDosError(v2);
  SetLastError(v3);
  result = GetLastError();
  v5 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v5 = result < 0;
  }
  if ( !v5 )
  {
LABEL_8:
    if ( AuthzInitializeResourceManager(0, 0, 0, 0, L"NPS", (PAUTHZ_RESOURCE_MANAGER_HANDLE)this + 18) )
      goto LABEL_9;
    result = GetLastError();
    v6 = result < 0;
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v6 = result < 0;
    }
    if ( !v6 )
    {
LABEL_9:
      v7 = RegisterEventSourceW(0, L"NPS");
      *((_QWORD *)this + 10) = v7;
      if ( v7 )
      {
        v8 = Auditor::Initialize(this);
        if ( v8 < 0 )
        {
          DeregisterEventSource(*((HANDLE *)this + 10));
          *((_QWORD *)this + 10) = 0;
        }
        return v8;
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015100  mov     [rsp+arg_0], rbx
0x180015105  push    rdi
0x180015106  sub     rsp, 30h
0x18001510a  movdqa  xmm0, cs:__xmm@00000001000000010000000100000001
0x180015112  lea     r9, [rsp+38h+OldValue]; OldValue
0x180015117  xor     r8d, r8d; ForThread
0x18001511a  mov     [rsp+38h+OldValue], 0
0x18001511f  mov     rbx, rcx
0x180015122  mov     dl, 1; NewValue
0x180015124  movups  xmmword ptr [rcx+58h], xmm0
0x180015128  lea     ecx, [r8+15h]; Privilege
0x18001512c  call    cs:__imp_RtlAdjustPrivilege
0x180015132  mov     edi, 80070000h
0x180015137  test    eax, eax
0x180015139  jns     short loc_180015162
0x18001513b  mov     ecx, eax; Status
0x18001513d  call    cs:__imp_RtlNtStatusToDosError
0x180015143  mov     ecx, eax; dwErrCode
0x180015145  call    cs:__imp_SetLastError
0x18001514b  call    cs:__imp_GetLastError
0x180015151  test    eax, eax
0x180015153  jle     short loc_18001515C
0x180015155  movzx   eax, ax
0x180015158  or      eax, edi
0x18001515a  test    eax, eax
0x18001515c  js      loc_1800151EC
0x180015162  lea     rax, [rbx+90h]
0x180015169  xor     r9d, r9d; pfnFreeDynamicGroups
0x18001516c  mov     [rsp+38h+phAuthzResourceManager], rax; phAuthzResourceManager
0x180015171  xor     r8d, r8d; pfnComputeDynamicGroups
0x180015174  lea     rax, szResourceManagerName; "NPS"
0x18001517b  xor     edx, edx; pfnDynamicAccessCheck
0x18001517d  xor     ecx, ecx; Flags
0x18001517f  mov     [rsp+38h+szResourceManagerName], rax; szResourceManagerName
0x180015184  call    cs:__imp_AuthzInitializeResourceManager
0x18001518a  test    eax, eax
0x18001518c  jnz     short loc_1800151A1
0x18001518e  call    cs:__imp_GetLastError
0x180015194  test    eax, eax
0x180015196  jle     short loc_18001519F
0x180015198  movzx   eax, ax
0x18001519b  or      eax, edi
0x18001519d  test    eax, eax
0x18001519f  js      short loc_1800151EC
0x1800151a1  lea     rdx, SourceName; "NPS"
0x1800151a8  xor     ecx, ecx; lpUNCServerName
0x1800151aa  call    cs:__imp_RegisterEventSourceW
0x1800151b0  mov     [rbx+50h], rax
0x1800151b4  test    rax, rax
0x1800151b7  jnz     short loc_1800151CA
0x1800151b9  call    cs:__imp_GetLastError
0x1800151bf  test    eax, eax
0x1800151c1  jle     short loc_1800151EC
0x1800151c3  movzx   eax, ax
0x1800151c6  or      eax, edi
0x1800151c8  jmp     short loc_1800151EC
0x1800151ca  mov     rcx, rbx; this
0x1800151cd  call    ?Initialize@Auditor@@UEAAJXZ; Auditor::Initialize(void)
0x1800151d2  mov     edi, eax
0x1800151d4  test    eax, eax
0x1800151d6  jns     short loc_1800151EA
0x1800151d8  mov     rcx, [rbx+50h]; hEventLog
0x1800151dc  call    cs:__imp_DeregisterEventSource
0x1800151e2  mov     qword ptr [rbx+50h], 0
0x1800151ea  mov     eax, edi
0x1800151ec  mov     rbx, [rsp+38h+arg_0]
0x1800151f1  add     rsp, 30h
0x1800151f5  pop     rdi
0x1800151f6  retn
```
