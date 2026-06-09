# CATUtils::SessionKeyString(void)

- ea: `0x14001caa4`
- end: `0x14001cb51`
- name: `?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ`
- size: `173`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001b51c`
- `0x14001cc50`
- `0x14001eb30`
- `0x140020374`
- `0x140024ba4`
- `0x1400252a8`

## callees

- `0x1400045f4`
- `0x14001c508`
- `0x14001caa4`
- `0x140025d70`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14001cae3`
- `KERNEL32!GetCurrentProcessId` at `0x14001cae3`
- `KERNEL32!ProcessIdToSessionId` at `0x14001caf0`
- `KERNEL32!ProcessIdToSessionId` at `0x14001caf0`
- `msvcrt!_ltow_s` at `0x14001cb0b`
- `msvcrt!_ltow_s` at `0x14001cb0b`

## string_xrefs

- `0x14001cacf`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\Session`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CATUtils::SessionKeyString(__int64 a1)
{
  DWORD CurrentProcessId; // eax
  __int64 v3; // r8
  DWORD pSessionId[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h]
  wchar_t Buffer[12]; // [rsp+30h] [rbp-28h] BYREF

  v6 = a1;
  pSessionId[0] = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    a1,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\Session");
  pSessionId[1] = 1;
  CurrentProcessId = GetCurrentProcessId();
  if ( ProcessIdToSessionId(CurrentProcessId, pSessionId) && !_ltow_s(pSessionId[0], Buffer, 0xCu, 10) )
  {
    v3 = -1;
    do
      ++v3;
    while ( Buffer[v3] );
    ATL::CSimpleStringT<unsigned short,0>::Append(a1, Buffer, v3);
  }
  return a1;
}

```

## disassembly

```asm
0x14001caa4  mov     [rsp+arg_8], rbx
0x14001caa9  push    rdi
0x14001caaa  sub     rsp, 50h
0x14001caae  mov     rax, cs:__security_cookie
0x14001cab5  xor     rax, rsp
0x14001cab8  mov     [rsp+58h+var_10], rax
0x14001cabd  mov     rbx, rcx
0x14001cac0  mov     [rsp+58h+var_30], rcx
0x14001cac5  xor     edi, edi
0x14001cac7  mov     [rsp+58h+var_34], edi
0x14001cacb  mov     [rsp+58h+pSessionId], edi
0x14001cacf  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001cad6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001cadb  mov     [rsp+58h+var_34], 1
0x14001cae3  call    cs:__imp_GetCurrentProcessId
0x14001cae9  mov     ecx, eax; dwProcessId
0x14001caeb  lea     rdx, [rsp+58h+pSessionId]; pSessionId
0x14001caf0  call    cs:__imp_ProcessIdToSessionId
0x14001caf6  test    eax, eax
0x14001caf8  jz      short loc_14001CB35
0x14001cafa  lea     r9d, [rdi+0Ah]; Radix
0x14001cafe  lea     r8d, [rdi+0Ch]; BufferCount
0x14001cb02  lea     rdx, [rsp+58h+Buffer]; Buffer
0x14001cb07  mov     ecx, [rsp+58h+pSessionId]; Value
0x14001cb0b  call    cs:__imp__ltow_s
0x14001cb11  test    eax, eax
0x14001cb13  jnz     short loc_14001CB35
0x14001cb15  lea     rax, [rsp+58h+Buffer]
0x14001cb1a  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001cb1e  inc     r8
0x14001cb21  cmp     [rax+r8*2], di
0x14001cb26  jnz     short loc_14001CB1E
0x14001cb28  lea     rdx, [rsp+58h+Buffer]
0x14001cb2d  mov     rcx, rbx
0x14001cb30  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001cb35  mov     rax, rbx
0x14001cb38  mov     rcx, [rsp+58h+var_10]
0x14001cb3d  xor     rcx, rsp; StackCookie
0x14001cb40  call    __security_check_cookie
0x14001cb45  mov     rbx, [rsp+58h+arg_8]
0x14001cb4a  add     rsp, 50h
0x14001cb4e  pop     rdi
0x14001cb4f  retn
```
