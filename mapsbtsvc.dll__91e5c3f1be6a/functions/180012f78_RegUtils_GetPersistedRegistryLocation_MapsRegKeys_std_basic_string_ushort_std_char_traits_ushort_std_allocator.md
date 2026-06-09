# RegUtils::GetPersistedRegistryLocation(MapsRegKeys,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180012f78`
- end: `0x180013005`
- name: `?GetPersistedRegistryLocation@RegUtils@@SAJW4MapsRegKeys@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000cfec`

## callees

- `0x180001e70`
- `0x1800028e8`
- `0x180012f18`
- `0x180012f78`
- `0x1800130e8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180012fc9`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180012fc9`

## string_xrefs

- `0x180012fc0`: `RegUtils::GetPersistedRegistryLocation`

## pseudocode

```c
__int64 __fastcall RegUtils::GetPersistedRegistryLocation(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  int PersistedRegistryLocation; // eax
  unsigned int v5; // ebx
  _BYTE v7[528]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(v7, 0, 0x208u);
  PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(v3, v7);
  if ( PersistedRegistryLocation >= 0 )
  {
    v5 = 0;
    std::wstring::assign(a2, v7);
  }
  else
  {
    return (unsigned int)ZTraceReportPropagationNoThis(
                           PersistedRegistryLocation,
                           "RegUtils::GetPersistedRegistryLocation",
                           788);
  }
  return v5;
}

```

## disassembly

```asm
0x180012f78  mov     [rsp+arg_0], rbx
0x180012f7d  push    rdi
0x180012f7e  sub     rsp, 240h
0x180012f85  mov     rax, cs:__security_cookie
0x180012f8c  xor     rax, rsp
0x180012f8f  mov     [rsp+248h+var_18], rax
0x180012f97  mov     rdi, rdx
0x180012f9a  lea     rcx, [rsp+248h+var_228]; void *
0x180012f9f  xor     edx, edx; Val
0x180012fa1  mov     r8d, 208h; Size
0x180012fa7  call    memset_0
0x180012fac  lea     rdx, [rsp+248h+var_228]
0x180012fb1  call    ?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)
0x180012fb6  test    eax, eax
0x180012fb8  jns     short loc_180012FD3
0x180012fba  mov     r8d, 314h
0x180012fc0  lea     rdx, aRegutilsGetper; "RegUtils::GetPersistedRegistryLocation"
0x180012fc7  mov     ecx, eax
0x180012fc9  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180012fcf  mov     ebx, eax
0x180012fd1  jmp     short loc_180012FE2
0x180012fd3  xor     ebx, ebx
0x180012fd5  lea     rdx, [rsp+248h+var_228]
0x180012fda  mov     rcx, rdi
0x180012fdd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180012fe2  mov     eax, ebx
0x180012fe4  mov     rcx, [rsp+248h+var_18]
0x180012fec  xor     rcx, rsp; StackCookie
0x180012fef  call    __security_check_cookie
0x180012ff4  mov     rbx, [rsp+248h+arg_0]
0x180012ffc  add     rsp, 240h
0x180013003  pop     rdi
0x180013004  retn
```
