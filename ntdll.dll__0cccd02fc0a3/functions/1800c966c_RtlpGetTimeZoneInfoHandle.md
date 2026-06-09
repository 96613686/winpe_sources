# RtlpGetTimeZoneInfoHandle

- ea: `0x1800c966c`
- end: `0x1800c9758`
- name: `RtlpGetTimeZoneInfoHandle`
- size: `236`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, registry_config`

## callers

- `0x1800c93e0`
- `0x180121d0c`

## callees

- `0x180016bc0`
- `0x1800c966c`
- `0x1800ca7e4`
- `0x180162000`

## string_xrefs

- `0x1800c96ea`: `TargetNtPath`

## pseudocode

```c
__int64 __fastcall RtlpGetTimeZoneInfoHandle(char a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v6; // [rsp+40h] [rbp-238h] BYREF
  _BYTE v7[528]; // [rsp+50h] [rbp-228h] BYREF

  if ( dword_1801C669C == 2 )
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
    dword_1801C669C = 1;
    LOBYTE(a3) = a1;
    result = RtlpGetRegistryHandle(0, v7, a3, a2);
    if ( (_DWORD)result == -1073741772 )
      goto LABEL_2;
  }
  else if ( (_DWORD)result == -1073741772 )
  {
    dword_1801C669C = 2;
LABEL_2:
    LOBYTE(a3) = a1;
    return RtlpGetRegistryHandle(2, L"TimeZoneInformation", a3, a2);
  }
  return result;
}

```

## disassembly

```asm
0x1800c966c  mov     [rsp+arg_0], rbx
0x1800c9671  push    rdi
0x1800c9672  sub     rsp, 270h
0x1800c9679  mov     rax, cs:__security_cookie
0x1800c9680  xor     rax, rsp
0x1800c9683  mov     [rsp+278h+var_18], rax
0x1800c968b  mov     eax, cs:dword_1801C669C
0x1800c9691  mov     rdi, rdx
0x1800c9694  mov     bl, cl
0x1800c9696  cmp     eax, 2
0x1800c9699  jnz     short loc_1800C96DD
0x1800c969b  cmp     eax, 1
0x1800c969e  jz      loc_1800C9736
0x1800c96a4  mov     r9, rdi
0x1800c96a7  lea     rdx, aTimezoneinform; "TimeZoneInformation"
0x1800c96ae  mov     r8b, bl
0x1800c96b1  mov     ecx, 2
0x1800c96b6  call    RtlpGetRegistryHandle
0x1800c96bb  mov     rcx, [rsp+278h+var_18]
0x1800c96c3  xor     rcx, rsp; StackCookie
0x1800c96c6  call    __security_check_cookie
0x1800c96cb  mov     rbx, [rsp+278h+arg_0]
0x1800c96d3  add     rsp, 270h
0x1800c96da  pop     rdi
0x1800c96db  retn
0x1800c96dd  lea     rax, [rsp+278h+var_238]
0x1800c96e2  xor     r9d, r9d
0x1800c96e5  mov     [rsp+278h+var_248], rax; __int64
0x1800c96ea  lea     rdx, aTargetntpath; "TargetNtPath"
0x1800c96f1  lea     rax, [rsp+278h+var_228]
0x1800c96f6  mov     [rsp+278h+var_250], 208h; int
0x1800c96fe  xor     r8d, r8d
0x1800c9701  mov     [rsp+278h+var_258], rax; void *
0x1800c9706  lea     rcx, aTimezoneinform_0; "TimeZoneInformationSettings"
0x1800c970d  call    RtlGetPersistedStateLocation
0x1800c9712  test    eax, eax
0x1800c9714  jns     short loc_1800C972C
0x1800c9716  cmp     eax, 0C0000034h
0x1800c971b  jnz     short loc_1800C96BB
0x1800c971d  mov     cs:dword_1801C669C, 2
0x1800c9727  jmp     loc_1800C96A4
0x1800c972c  mov     cs:dword_1801C669C, 1
0x1800c9736  mov     r9, rdi
0x1800c9739  lea     rdx, [rsp+278h+var_228]
0x1800c973e  mov     r8b, bl
0x1800c9741  xor     ecx, ecx
0x1800c9743  call    RtlpGetRegistryHandle
0x1800c9748  cmp     eax, 0C0000034h
0x1800c974d  jnz     loc_1800C96BB
0x1800c9753  jmp     loc_1800C96A4
```
