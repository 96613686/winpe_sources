# NdfTelemetryProviderSingleton::AddRepairGuid(_GUID const &)

- ea: `0x1800185b0`
- end: `0x180018658`
- name: `?AddRepairGuid@NdfTelemetryProviderSingleton@@QEAAXAEBU_GUID@@@Z`
- size: `168`
- prototype: `void __fastcall(NdfTelemetryProviderSingleton *this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018ae4`

## callees

- `0x18001786c`
- `0x1800185b0`
- `0x18001d530`
- `0x18001de64`
- `0x18002c802`
- `0x18002c840`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800185fd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800185fd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018639`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018639`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800185ec`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800185ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NdfTelemetryProviderSingleton::AddRepairGuid(
        NdfTelemetryProviderSingleton *this,
        const struct _GUID *a2)
{
  __int64 v3; // rax
  _QWORD v4[4]; // [rsp+20h] [rbp-88h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-68h] BYREF

  memset_0(sz, 0, sizeof(sz));
  if ( StringFromGUID2(a2, sz, 40) > 0 )
  {
    AcquireSRWLockExclusive(&stru_180041D08);
    v3 = std::wstring::wstring(v4, sz);
    std::vector<std::wstring>::push_back((char *)&xmmword_180041D80 + 8, v3);
    std::wstring::_Tidy(v4, 1, 0);
    ReleaseSRWLockExclusive(&stru_180041D08);
  }
}

```

## disassembly

```asm
0x1800185b0  push    rbx
0x1800185b2  sub     rsp, 0A0h
0x1800185b9  mov     rax, cs:__security_cookie
0x1800185c0  xor     rax, rsp
0x1800185c3  mov     [rsp+0A8h+var_18], rax
0x1800185cb  mov     rbx, rdx
0x1800185ce  xor     edx, edx; Val
0x1800185d0  lea     r8d, [rdx+50h]; Size
0x1800185d4  lea     rcx, [rsp+0A8h+sz]; void *
0x1800185d9  call    memset_0
0x1800185de  mov     r8d, 28h ; '('; cchMax
0x1800185e4  lea     rdx, [rsp+0A8h+sz]; lpsz
0x1800185e9  mov     rcx, rbx; rguid
0x1800185ec  call    cs:__imp_StringFromGUID2
0x1800185f2  test    eax, eax
0x1800185f4  jle     short loc_18001863F
0x1800185f6  lea     rcx, stru_180041D08; SRWLock
0x1800185fd  call    cs:__imp_AcquireSRWLockExclusive
0x180018603  lea     rdx, [rsp+0A8h+sz]
0x180018608  lea     rcx, [rsp+0A8h+var_88]
0x18001860d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180018612  nop
0x180018613  mov     rdx, rax
0x180018616  lea     rcx, xmmword_180041D80+8
0x18001861d  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x180018622  nop
0x180018623  xor     r8d, r8d
0x180018626  mov     dl, 1
0x180018628  lea     rcx, [rsp+0A8h+var_88]
0x18001862d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018632  lea     rcx, stru_180041D08; SRWLock
0x180018639  call    cs:__imp_ReleaseSRWLockExclusive
0x18001863f  mov     rcx, [rsp+0A8h+var_18]
0x180018647  xor     rcx, rsp; StackCookie
0x18001864a  call    __security_check_cookie
0x18001864f  add     rsp, 0A0h
0x180018656  pop     rbx
0x180018657  retn
```
