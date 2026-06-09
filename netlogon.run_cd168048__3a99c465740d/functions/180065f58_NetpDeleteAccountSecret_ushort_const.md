# NetpDeleteAccountSecret(ushort const *)

- ea: `0x180065f58`
- end: `0x18006605f`
- name: `?NetpDeleteAccountSecret@@YAJPEBG@Z`
- size: `263`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180065520`
- `0x180067760`

## callees

- `0x180065bec`
- `0x180065f58`

## import_xrefs

- `LSASRV!LsarClose` at `0x18006604a`
- `LSASRV!LsarClose` at `0x18006604a`
- `LSASRV!LsarDeleteObject` at `0x180066016`
- `LSASRV!LsarDeleteObject` at `0x180066016`
- `LSASRV!LsarOpenSecret` at `0x180065fec`
- `LSASRV!LsarOpenSecret` at `0x180065fec`
- `ntdll!RtlLeaveCriticalSection` at `0x180066001`
- `ntdll!RtlLeaveCriticalSection` at `0x180066001`
- `ntdll!RtlEnterCriticalSection` at `0x180065fc2`
- `ntdll!RtlEnterCriticalSection` at `0x180065fc2`
- `ntdll!RtlInitUnicodeString` at `0x180065faf`
- `ntdll!RtlInitUnicodeString` at `0x180065faf`
- `netutils!NetApiBufferFree` at `0x180066031`
- `netutils!NetApiBufferFree` at `0x180066031`

## pseudocode

```c
__int64 __fastcall NetpDeleteAccountSecret(const unsigned __int16 *a1)
{
  int v1; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  PCWSTR SourceString; // [rsp+58h] [rbp+10h] BYREF
  __int64 v5; // [rsp+60h] [rbp+18h] BYREF

  v5 = 0;
  SourceString = 0;
  v1 = NetpConcatenate(
         0,
         (unsigned __int16 **)&SourceString,
         3u,
         L"_SC_{262E99C9-6160-4871-ACEC-4E61736B6F21}_",
         a1,
         L"$",
         0,
         0);
  if ( v1 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    RtlEnterCriticalSection(&NlGlobalDomainCritSect);
    v1 = LsarOpenSecret(*((_QWORD *)NlGlobalDomainInfo + 49), &DestinationString, 983043, &v5);
    RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
    if ( v1 >= 0 )
      v1 = LsarDeleteObject(&v5);
  }
  if ( SourceString )
    NetApiBufferFree((LPVOID)SourceString);
  if ( v5 )
    LsarClose(&v5);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180065f58  mov     r11, rsp
0x180065f5b  push    rbx
0x180065f5c  sub     rsp, 40h
0x180065f60  lea     rax, asc_1800ACA94; "$"
0x180065f67  mov     qword ptr [r11+18h], 0
0x180065f6f  mov     [r11-20h], rax
0x180065f73  lea     r9, aSc262e99c96160; "_SC_{262E99C9-6160-4871-ACEC-4E61736B6F"...
0x180065f7a  mov     [r11-28h], rcx
0x180065f7e  lea     rdx, [r11+10h]; unsigned __int16 **
0x180065f82  xorps   xmm0, xmm0
0x180065f85  mov     qword ptr [r11+10h], 0
0x180065f8d  xor     ecx, ecx; int
0x180065f8f  mov     r8d, 3; unsigned __int16
0x180065f95  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x180065f9a  call    ?NetpConcatenate@@YAJHPEAPEAGGZZ; NetpConcatenate(int,ushort * *,ushort,...)
0x180065f9f  mov     ebx, eax
0x180065fa1  test    eax, eax
0x180065fa3  js      short loc_180066024
0x180065fa5  mov     rdx, [rsp+48h+SourceString]; SourceString
0x180065faa  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180065faf  call    cs:__imp_RtlInitUnicodeString
0x180065fb6  nop     dword ptr [rax+rax+00h]
0x180065fbb  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180065fc2  call    cs:__imp_RtlEnterCriticalSection
0x180065fc9  nop     dword ptr [rax+rax+00h]
0x180065fce  mov     rcx, cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA; _DOMAIN_INFO * NlGlobalDomainInfo
0x180065fd5  lea     r9, [rsp+48h+arg_10]
0x180065fda  mov     r8d, 0F0003h
0x180065fe0  lea     rdx, [rsp+48h+DestinationString]
0x180065fe5  mov     rcx, [rcx+188h]
0x180065fec  call    cs:__imp_LsarOpenSecret
0x180065ff3  nop     dword ptr [rax+rax+00h]
0x180065ff8  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180065fff  mov     ebx, eax
0x180066001  call    cs:__imp_RtlLeaveCriticalSection
0x180066008  nop     dword ptr [rax+rax+00h]
0x18006600d  test    ebx, ebx
0x18006600f  js      short loc_180066024
0x180066011  lea     rcx, [rsp+48h+arg_10]
0x180066016  call    cs:__imp_LsarDeleteObject
0x18006601d  nop     dword ptr [rax+rax+00h]
0x180066022  mov     ebx, eax
0x180066024  cmp     [rsp+48h+SourceString], 0
0x18006602a  jz      short loc_18006603D
0x18006602c  mov     rcx, [rsp+48h+SourceString]; Buffer
0x180066031  call    cs:__imp_NetApiBufferFree
0x180066038  nop     dword ptr [rax+rax+00h]
0x18006603d  cmp     [rsp+48h+arg_10], 0
0x180066043  jz      short loc_180066056
0x180066045  lea     rcx, [rsp+48h+arg_10]
0x18006604a  call    cs:__imp_LsarClose
0x180066051  nop     dword ptr [rax+rax+00h]
0x180066056  mov     eax, ebx
0x180066058  add     rsp, 40h
0x18006605c  pop     rbx
0x18006605d  retn
```
