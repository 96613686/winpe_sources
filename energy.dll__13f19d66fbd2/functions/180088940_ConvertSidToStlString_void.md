# ConvertSidToStlString(void *)

- ea: `0x180088940`
- end: `0x180088a08`
- name: `?ConvertSidToStlString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180088e20`
- `0x18008bbe8`

## callees

- `0x180008d2c`
- `0x18000b6f0`
- `0x18001cf30`
- `0x180020454`
- `0x18003bce0`
- `0x18004ca90`
- `0x180088940`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800889c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800889c9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180088983`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180088983`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConvertSidToStlString(__int64 a1, void *a2)
{
  __int64 v4; // rax
  LPWSTR StringSid; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v7[4]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v8[32]; // [rsp+50h] [rbp-38h] BYREF

  std::wstring::wstring(v7);
  StringSid = 0;
  if ( ConvertSidToStringSidW(a2, &StringSid) )
  {
    v4 = std::wstring::wstring((__int64)v8, (__int64)StringSid);
    std::wstring::operator=(v7, v4);
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v8);
    LocalFree(StringSid);
    std::wstring::wstring(a1, (__int64)v7);
  }
  else
  {
    std::wstring::wstring(a1, (__int64)&qword_18009CA18);
  }
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v7);
  return a1;
}

```

## disassembly

```asm
0x180088940  mov     [rsp+arg_10], rbx
0x180088945  push    rdi
0x180088946  sub     rsp, 80h
0x18008894d  mov     rax, cs:__security_cookie
0x180088954  xor     rax, rsp
0x180088957  mov     [rsp+88h+var_18], rax
0x18008895c  mov     rbx, rdx
0x18008895f  mov     rdi, rcx
0x180088962  mov     [rsp+88h+StringSid], rcx
0x180088967  lea     rcx, [rsp+88h+var_58]; void *
0x18008896c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180088971  nop
0x180088972  mov     [rsp+88h+StringSid], 0
0x18008897b  lea     rdx, [rsp+88h+StringSid]; StringSid
0x180088980  mov     rcx, rbx; Sid
0x180088983  call    cs:__imp_ConvertSidToStringSidW
0x180088989  test    eax, eax
0x18008898b  jnz     short loc_18008899E
0x18008898d  lea     rdx, qword_18009CA18
0x180088994  mov     rcx, rdi
0x180088997  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008899c  jmp     short loc_1800889DD
0x18008899e  mov     rdx, [rsp+88h+StringSid]
0x1800889a3  lea     rcx, [rsp+88h+var_38]
0x1800889a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800889ad  mov     rdx, rax
0x1800889b0  lea     rcx, [rsp+88h+var_58]
0x1800889b5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800889ba  lea     rcx, [rsp+88h+var_38]; void *
0x1800889bf  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x1800889c4  mov     rcx, [rsp+88h+StringSid]; hMem
0x1800889c9  call    cs:__imp_LocalFree
0x1800889cf  lea     rdx, [rsp+88h+var_58]
0x1800889d4  mov     rcx, rdi
0x1800889d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800889dc  nop
0x1800889dd  lea     rcx, [rsp+88h+var_58]; void *
0x1800889e2  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x1800889e7  mov     rax, rdi
0x1800889ea  mov     rcx, [rsp+88h+var_18]
0x1800889ef  xor     rcx, rsp; StackCookie
0x1800889f2  call    __security_check_cookie
0x1800889f7  mov     rbx, [rsp+88h+arg_10]
0x1800889ff  add     rsp, 80h
0x180088a06  pop     rdi
0x180088a07  retn
```
