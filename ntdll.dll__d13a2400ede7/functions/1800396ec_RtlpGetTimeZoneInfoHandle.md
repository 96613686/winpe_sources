# RtlpGetTimeZoneInfoHandle

- ea: `0x1800396ec`
- end: `0x1800397d8`
- name: `RtlpGetTimeZoneInfoHandle`
- size: `236`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, registry_config`

## callers

- `0x180037cfc`
- `0x1801227fc`

## callees

- `0x180016bc0`
- `0x180038ed4`
- `0x1800396ec`
- `0x180162810`

## string_xrefs

- `0x18003976a`: `TargetNtPath`

## pseudocode

```c
__int64 __fastcall RtlpGetTimeZoneInfoHandle(char a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v6; // [rsp+40h] [rbp-238h] BYREF
  _BYTE v7[528]; // [rsp+50h] [rbp-228h] BYREF

  if ( dword_1801C661C == 2 )
    goto LABEL_2;
  result = RtlGetPersistedStateLocation(
             (wchar_t *)L"TimeZoneInformationSettings",
             L"TargetNtPath",
             0,
             0,
             v7,
             0x208u,
             (unsigned int *)&v6);
  if ( (int)result >= 0 )
  {
    dword_1801C661C = 1;
    LOBYTE(a3) = a1;
    result = RtlpGetRegistryHandle(0, v7, a3, a2);
    if ( (_DWORD)result == -1073741772 )
      goto LABEL_2;
  }
  else if ( (_DWORD)result == -1073741772 )
  {
    dword_1801C661C = 2;
LABEL_2:
    LOBYTE(a3) = a1;
    return RtlpGetRegistryHandle(2, L"TimeZoneInformation", a3, a2);
  }
  return result;
}

```

## disassembly

```asm
0x1800396ec  mov     [rsp+arg_0], rbx
0x1800396f1  push    rdi
0x1800396f2  sub     rsp, 270h
0x1800396f9  mov     rax, cs:__security_cookie
0x180039700  xor     rax, rsp
0x180039703  mov     [rsp+278h+var_18], rax
0x18003970b  mov     eax, cs:dword_1801C661C
0x180039711  mov     rdi, rdx
0x180039714  mov     bl, cl
0x180039716  cmp     eax, 2
0x180039719  jnz     short loc_18003975D
0x18003971b  cmp     eax, 1
0x18003971e  jz      loc_1800397B6
0x180039724  mov     r9, rdi
0x180039727  lea     rdx, aTimezoneinform; "TimeZoneInformation"
0x18003972e  mov     r8b, bl
0x180039731  mov     ecx, 2
0x180039736  call    RtlpGetRegistryHandle
0x18003973b  mov     rcx, [rsp+278h+var_18]
0x180039743  xor     rcx, rsp; StackCookie
0x180039746  call    __security_check_cookie
0x18003974b  mov     rbx, [rsp+278h+arg_0]
0x180039753  add     rsp, 270h
0x18003975a  pop     rdi
0x18003975b  retn
0x18003975d  lea     rax, [rsp+278h+var_238]
0x180039762  xor     r9d, r9d
0x180039765  mov     [rsp+278h+var_248], rax; __int64
0x18003976a  lea     rdx, aTargetntpath; "TargetNtPath"
0x180039771  lea     rax, [rsp+278h+var_228]
0x180039776  mov     [rsp+278h+var_250], 208h; int
0x18003977e  xor     r8d, r8d
0x180039781  mov     [rsp+278h+var_258], rax; void *
0x180039786  lea     rcx, aTimezoneinform_0; "TimeZoneInformationSettings"
0x18003978d  call    RtlGetPersistedStateLocation
0x180039792  test    eax, eax
0x180039794  jns     short loc_1800397AC
0x180039796  cmp     eax, 0C0000034h
0x18003979b  jnz     short loc_18003973B
0x18003979d  mov     cs:dword_1801C661C, 2
0x1800397a7  jmp     loc_180039724
0x1800397ac  mov     cs:dword_1801C661C, 1
0x1800397b6  mov     r9, rdi
0x1800397b9  lea     rdx, [rsp+278h+var_228]
0x1800397be  mov     r8b, bl
0x1800397c1  xor     ecx, ecx
0x1800397c3  call    RtlpGetRegistryHandle
0x1800397c8  cmp     eax, 0C0000034h
0x1800397cd  jnz     loc_18003973B
0x1800397d3  jmp     loc_180039724
```
