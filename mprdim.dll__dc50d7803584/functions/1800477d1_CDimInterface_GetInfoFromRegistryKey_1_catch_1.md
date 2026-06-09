# _CDimInterface::GetInfoFromRegistryKey_::_1_::catch$1

- ea: `0x1800477d1`
- end: `0x1800478e4`
- name: `_CDimInterface::GetInfoFromRegistryKey_::_1_::catch$1`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000df70`
- `0x180045d40`
- `0x1800477d1`
- `0x180048010`

## import_xrefs

- `rtutils!RouterLogEventW` at `0x1800478cb`
- `rtutils!RouterLogEventW` at `0x1800478cb`

## string_xrefs

- `0x180047827`: `Cannot access Registry value for Error: %d.`

## pseudocode

```c
__int64 __fastcall CDimInterface::GetInfoFromRegistryKey_::_1_::catch_1(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  int v5; // r9d

  *(_DWORD *)(a2 + 96) = 8;
  v3 = *(_QWORD *)(a2 + 144);
  *(_QWORD *)(a2 + 144) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 280LL))(v3);
  if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
  {
    *(_WORD *)(a2 + 208) = 0;
    *(_WORD *)(a2 + 168) = 0;
    FormatRRASErrorString(a2 + 208, L"Cannot access Registry value for Error: %d.", a2 + 96);
    if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 280LL))(v3);
      v5 = v3 + 3104;
      if ( v3 == -3104 )
        v5 = a2 + 152;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDimParamTraceAdminError,
        a2 + 208,
        v5,
        v4,
        a2 + 168);
    }
  }
  if ( dword_180070F40 )
    RouterLogEventW(hLogHandle, 1u, 0x4E83u, 1u, (LPWSTR *)(a2 + 144), *(_DWORD *)(a2 + 96));
  return 0;
}

```

## disassembly

```asm
0x1800477d1  mov     [rsp+arg_8], rdx
0x1800477d6  push    rbx
0x1800477d7  push    rbp
0x1800477d8  sub     rsp, 68h
0x1800477dc  mov     rbp, rdx
0x1800477df  mov     dword ptr [rbp+60h], 8
0x1800477e6  mov     rbx, [rbp+90h]
0x1800477ed  mov     rax, [rbx]
0x1800477f0  mov     rcx, rbx
0x1800477f3  mov     rax, [rax+118h]
0x1800477fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477ff  mov     [rbp+90h], rax
0x180047806  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x18004780d  jz      loc_18004789A
0x180047813  xor     eax, eax
0x180047815  mov     [rbp+0D0h], ax
0x18004781c  mov     [rbp+0A8h], ax
0x180047823  lea     r8, [rbp+60h]
0x180047827  lea     rdx, aCannotAccessRe_0; "Cannot access Registry value for Error:"...
0x18004782e  lea     rcx, [rbp+0D0h]
0x180047835  call    FormatRRASErrorString
0x18004783a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x180047841  jz      short loc_18004789A
0x180047843  mov     rax, [rbx]
0x180047846  mov     rcx, rbx
0x180047849  mov     rax, [rax+118h]
0x180047850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047855  lea     rcx, [rbx+0C20h]
0x18004785c  test    rcx, rcx
0x18004785f  lea     r9, [rbx+0C20h]
0x180047866  jnz     short loc_18004786F
0x180047868  lea     r9, [rbp+98h]
0x18004786f  lea     rcx, [rbp+0A8h]
0x180047876  mov     qword ptr [rsp+78h+dwErrorCode], rcx
0x18004787b  mov     [rsp+78h+plpszSubStringArray], rax
0x180047880  lea     r8, [rbp+0D0h]
0x180047887  lea     rdx, RasDimParamTraceAdminError
0x18004788e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180047895  call    McTemplateU0zjzz_EventWriteTransfer
0x18004789a  cmp     cs:dword_180070F40, 0
0x1800478a1  jbe     short loc_1800478D2
0x1800478a3  mov     eax, [rbp+60h]
0x1800478a6  mov     [rsp+78h+dwErrorCode], eax; dwErrorCode
0x1800478aa  lea     rax, [rbp+90h]
0x1800478b1  mov     [rsp+78h+plpszSubStringArray], rax; plpszSubStringArray
0x1800478b6  mov     edx, 1; dwEventType
0x1800478bb  mov     r9d, edx; dwSubStringCount
0x1800478be  mov     r8d, 4E83h; dwMessageId
0x1800478c4  mov     rcx, cs:hLogHandle; hLogHandle
0x1800478cb  call    cs:__imp_RouterLogEventW
0x1800478d1  nop
0x1800478d2  mov     rax, 0
0x1800478dc  add     rsp, 68h
0x1800478e0  pop     rbp
0x1800478e1  pop     rbx
0x1800478e2  retn
```
