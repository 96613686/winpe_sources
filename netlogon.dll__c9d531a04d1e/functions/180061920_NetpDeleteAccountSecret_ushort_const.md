# NetpDeleteAccountSecret(ushort const *)

- ea: `0x180061920`
- end: `0x1800619fc`
- name: `?NetpDeleteAccountSecret@@YAJPEBG@Z`
- size: `220`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180060fa4`
- `0x180062ee0`

## callees

- `0x1800615f0`
- `0x180061920`

## import_xrefs

- `LSASRV!LsarClose` at `0x1800619ee`
- `LSASRV!LsarClose` at `0x1800619ee`
- `LSASRV!LsarDeleteObject` at `0x1800619c6`
- `LSASRV!LsarDeleteObject` at `0x1800619c6`
- `LSASRV!LsarOpenSecret` at `0x1800619a8`
- `LSASRV!LsarOpenSecret` at `0x1800619a8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800619b7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800619b7`
- `ntdll!RtlEnterCriticalSection` at `0x180061984`
- `ntdll!RtlEnterCriticalSection` at `0x180061984`
- `ntdll!RtlInitUnicodeString` at `0x180061977`
- `ntdll!RtlInitUnicodeString` at `0x180061977`
- `netutils!NetApiBufferFree` at `0x1800619db`
- `netutils!NetApiBufferFree` at `0x1800619db`

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
0x180061920  mov     r11, rsp
0x180061923  push    rbx
0x180061924  sub     rsp, 40h
0x180061928  lea     rax, asc_1800A5A84; "$"
0x18006192f  mov     qword ptr [r11+18h], 0
0x180061937  mov     [r11-20h], rax
0x18006193b  lea     r9, aSc262e99c96160; "_SC_{262E99C9-6160-4871-ACEC-4E61736B6F"...
0x180061942  mov     [r11-28h], rcx
0x180061946  lea     rdx, [r11+10h]; unsigned __int16 **
0x18006194a  xorps   xmm0, xmm0
0x18006194d  mov     qword ptr [r11+10h], 0
0x180061955  xor     ecx, ecx; int
0x180061957  mov     r8d, 3; unsigned __int16
0x18006195d  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x180061962  call    ?NetpConcatenate@@YAJHPEAPEAGGZZ; NetpConcatenate(int,ushort * *,ushort,...)
0x180061967  mov     ebx, eax
0x180061969  test    eax, eax
0x18006196b  js      short loc_1800619CE
0x18006196d  mov     rdx, [rsp+48h+SourceString]; SourceString
0x180061972  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180061977  call    cs:__imp_RtlInitUnicodeString
0x18006197d  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180061984  call    cs:__imp_RtlEnterCriticalSection
0x18006198a  mov     rcx, cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA; _DOMAIN_INFO * NlGlobalDomainInfo
0x180061991  lea     r9, [rsp+48h+arg_10]
0x180061996  mov     r8d, 0F0003h
0x18006199c  lea     rdx, [rsp+48h+DestinationString]
0x1800619a1  mov     rcx, [rcx+188h]
0x1800619a8  call    cs:__imp_LsarOpenSecret
0x1800619ae  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800619b5  mov     ebx, eax
0x1800619b7  call    cs:__imp_RtlLeaveCriticalSection
0x1800619bd  test    ebx, ebx
0x1800619bf  js      short loc_1800619CE
0x1800619c1  lea     rcx, [rsp+48h+arg_10]
0x1800619c6  call    cs:__imp_LsarDeleteObject
0x1800619cc  mov     ebx, eax
0x1800619ce  cmp     [rsp+48h+SourceString], 0
0x1800619d4  jz      short loc_1800619E1
0x1800619d6  mov     rcx, [rsp+48h+SourceString]; Buffer
0x1800619db  call    cs:__imp_NetApiBufferFree
0x1800619e1  cmp     [rsp+48h+arg_10], 0
0x1800619e7  jz      short loc_1800619F4
0x1800619e9  lea     rcx, [rsp+48h+arg_10]
0x1800619ee  call    cs:__imp_LsarClose
0x1800619f4  mov     eax, ebx
0x1800619f6  add     rsp, 40h
0x1800619fa  pop     rbx
0x1800619fb  retn
```
