# OfflineFilesGetShareCachingMode

- ea: `0x180007880`
- end: `0x18000793b`
- name: `OfflineFilesGetShareCachingMode`
- size: `187`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180007880`
- `0x180007c9c`
- `0x1800091d4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800078c4`
- `ntdll!RtlInitUnicodeString` at `0x1800078c4`
- `ntdll!RtlNtStatusToDosError` at `0x1800078ec`
- `ntdll!RtlNtStatusToDosError` at `0x1800078ec`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1800078a2`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1800078a2`

## pseudocode

```c
__int64 __fastcall OfflineFilesGetShareCachingMode(PCWSTR SourceString, int *a2)
{
  ULONG v4; // ebx
  int v5; // r8d
  NTSTATUS PathShareCscCachingFlags; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  int v9; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 48;
  v4 = 50;
  if ( PathIsUNCEx(SourceString, 0) )
  {
    v9 = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, SourceString);
    PathShareCscCachingFlags = CscUmGetPathShareCscCachingFlags(&DestinationString, &v9);
    if ( PathShareCscCachingFlags < 0 )
    {
      v4 = RtlNtStatusToDosError(PathShareCscCachingFlags);
    }
    else
    {
      v4 = 0;
      *a2 = v9 & 0x30;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 2) != 0 )
    WPP_SF_SDd(*((_QWORD *)WPP_GLOBAL_Control + 22), *a2, v5, (_DWORD)SourceString, *a2, v4);
  return v4;
}

```

## disassembly

```asm
0x180007880  mov     [rsp+arg_0], rbx
0x180007885  mov     [rsp+arg_10], rsi
0x18000788a  push    rdi
0x18000788b  sub     rsp, 40h
0x18000788f  mov     rdi, rdx
0x180007892  mov     dword ptr [rdx], 30h ; '0'
0x180007898  xor     edx, edx; ppszServer
0x18000789a  mov     rsi, rcx
0x18000789d  mov     ebx, 32h ; '2'
0x1800078a2  call    cs:__imp_PathIsUNCEx
0x1800078a8  test    eax, eax
0x1800078aa  jz      short loc_1800078F4
0x1800078ac  xorps   xmm0, xmm0
0x1800078af  mov     [rsp+48h+arg_8], 0
0x1800078b7  mov     rdx, rsi; SourceString
0x1800078ba  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1800078bf  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1800078c4  call    cs:__imp_RtlInitUnicodeString
0x1800078ca  lea     rdx, [rsp+48h+arg_8]
0x1800078cf  lea     rcx, [rsp+48h+DestinationString]
0x1800078d4  call    CscUmGetPathShareCscCachingFlags
0x1800078d9  test    eax, eax
0x1800078db  js      short loc_1800078EA
0x1800078dd  mov     eax, [rsp+48h+arg_8]
0x1800078e1  xor     ebx, ebx
0x1800078e3  and     eax, 30h
0x1800078e6  mov     [rdi], eax
0x1800078e8  jmp     short loc_1800078F4
0x1800078ea  mov     ecx, eax; Status
0x1800078ec  call    cs:__imp_RtlNtStatusToDosError
0x1800078f2  mov     ebx, eax
0x1800078f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078fb  lea     rax, WPP_GLOBAL_Control
0x180007902  cmp     rcx, rax
0x180007905  jz      short loc_180007929
0x180007907  test    byte ptr [rcx+0BCh], 2
0x18000790e  jz      short loc_180007929
0x180007910  mov     edx, [rdi]
0x180007912  mov     r9, rsi
0x180007915  mov     rcx, [rcx+0B0h]
0x18000791c  mov     [rsp+48h+var_20], ebx
0x180007920  mov     [rsp+48h+var_28], edx
0x180007924  call    WPP_SF_SDd
0x180007929  mov     rsi, [rsp+48h+arg_10]
0x18000792e  mov     eax, ebx
0x180007930  mov     rbx, [rsp+48h+arg_0]
0x180007935  add     rsp, 40h
0x180007939  pop     rdi
0x18000793a  retn
```
