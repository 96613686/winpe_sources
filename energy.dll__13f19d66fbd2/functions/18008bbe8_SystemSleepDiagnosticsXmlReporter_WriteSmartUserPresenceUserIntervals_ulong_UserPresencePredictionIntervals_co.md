# SystemSleepDiagnosticsXmlReporter::WriteSmartUserPresenceUserIntervals(ulong,UserPresencePredictionIntervals const &)

- ea: `0x18008bbe8`
- end: `0x18008bcbc`
- name: `?WriteSmartUserPresenceUserIntervals@SystemSleepDiagnosticsXmlReporter@@IEAAKKAEBUUserPresencePredictionIntervals@@@Z`
- size: `212`
- prototype: `unsigned int __fastcall(SystemSleepDiagnosticsXmlReporter *__hidden this, unsigned int, const struct UserPresencePredictionIntervals *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18008b8d4`

## callees

- `0x180009b5c`
- `0x18000f730`
- `0x18001107c`
- `0x180088940`
- `0x18008bb00`
- `0x18008bbe8`
- `0x1800902d0`

## string_xrefs

- `0x18008bc45`: `</UserSid>\n`
- `0x18008bc1c`: `<UserSid>`

## pseudocode

```c
__int64 __fastcall SystemSleepDiagnosticsXmlReporter::WriteSmartUserPresenceUserIntervals(
        SystemSleepDiagnosticsXmlReporter *this,
        __int64 a2,
        const struct UserPresencePredictionInterval **a3)
{
  unsigned int v5; // esi
  __int64 v6; // rax
  unsigned int v7; // edx
  const struct UserPresencePredictionInterval *i; // rbx
  _BYTE v10[72]; // [rsp+20h] [rbp-48h] BYREF

  if ( *((_DWORD *)this + 2) == 6 )
  {
    v5 = 0;
    XmlReporter::WriteTabbedRawString(this, 5u, L"<UserIntervals>\n");
    XmlReporter::WriteTabbedRawString(this, 6u, L"<UserSid>");
    v6 = ConvertSidToStlString((__int64)v10, a3);
    XmlReporter::WriteStlString(this, v6);
    XmlReporter::WriteRawString(this, L"</UserSid>\n");
    XmlReporter::WriteTabbedRawString(this, 6u, L"<Flags>");
    XmlReporter::WriteHexInteger(this, *((unsigned int *)a3 + 17));
    XmlReporter::WriteRawString(this, L"</Flags>\n");
    for ( i = a3[9]; i != a3[10]; i = (const struct UserPresencePredictionInterval *)((char *)i + 24) )
    {
      v5 = SystemSleepDiagnosticsXmlReporter::WriteSmartUserPresenceInterval(this, v7, i);
      if ( v5 )
        return v5;
    }
    XmlReporter::WriteTabbedRawString(this, 5u, L"</UserIntervals>\n");
  }
  else
  {
    return 1627;
  }
  return v5;
}

```

## disassembly

```asm
0x18008bbe8  push    rbx
0x18008bbea  push    rbp
0x18008bbeb  push    rsi
0x18008bbec  push    rdi
0x18008bbed  sub     rsp, 48h
0x18008bbf1  mov     ebx, 6
0x18008bbf6  mov     rbp, r8
0x18008bbf9  mov     rdi, rcx
0x18008bbfc  cmp     [rcx+8], ebx
0x18008bbff  jz      short loc_18008BC0B
0x18008bc01  mov     esi, 65Bh
0x18008bc06  jmp     loc_18008BCB1
0x18008bc0b  xor     esi, esi
0x18008bc0d  lea     r8, aUserintervals_0; "<UserIntervals>\n"
0x18008bc14  lea     edx, [rsi+5]; unsigned int
0x18008bc17  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x18008bc1c  lea     r8, aUsersid_0; "<UserSid>"
0x18008bc23  mov     edx, ebx; unsigned int
0x18008bc25  mov     rcx, rdi; this
0x18008bc28  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x18008bc2d  mov     rdx, rbp
0x18008bc30  lea     rcx, [rsp+68h+var_48]
0x18008bc35  call    ?ConvertSidToStlString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; ConvertSidToStlString(void *)
0x18008bc3a  mov     rdx, rax
0x18008bc3d  mov     rcx, rdi
0x18008bc40  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x18008bc45  lea     rdx, aUsersid_1; "</UserSid>\n"
0x18008bc4c  mov     rcx, rdi; this
0x18008bc4f  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008bc54  lea     r8, aFlags_1; "<Flags>"
0x18008bc5b  mov     edx, ebx; unsigned int
0x18008bc5d  mov     rcx, rdi; this
0x18008bc60  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x18008bc65  mov     edx, [rbp+44h]; unsigned __int64
0x18008bc68  mov     rcx, rdi; this
0x18008bc6b  call    ?WriteHexInteger@XmlReporter@@IEAAK_K@Z; XmlReporter::WriteHexInteger(unsigned __int64)
0x18008bc70  lea     rdx, aFlags_0; "</Flags>\n"
0x18008bc77  mov     rcx, rdi; this
0x18008bc7a  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18008bc7f  mov     rbx, [rbp+48h]
0x18008bc83  mov     rcx, rdi; this
0x18008bc86  cmp     rbx, [rbp+50h]
0x18008bc8a  jz      short loc_18008BCA0
0x18008bc8c  mov     r8, rbx; struct UserPresencePredictionInterval *
0x18008bc8f  call    ?WriteSmartUserPresenceInterval@SystemSleepDiagnosticsXmlReporter@@IEAAKKAEBUUserPresencePredictionInterval@@@Z; SystemSleepDiagnosticsXmlReporter::WriteSmartUserPresenceInterval(ulong,UserPresencePredictionInterval const &)
0x18008bc94  mov     esi, eax
0x18008bc96  test    eax, eax
0x18008bc98  jnz     short loc_18008BCB1
0x18008bc9a  add     rbx, 18h
0x18008bc9e  jmp     short loc_18008BC83
0x18008bca0  lea     r8, aUserintervals; "</UserIntervals>\n"
0x18008bca7  mov     edx, 5; unsigned int
0x18008bcac  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x18008bcb1  mov     eax, esi
0x18008bcb3  add     rsp, 48h
0x18008bcb7  pop     rdi
0x18008bcb8  pop     rsi
0x18008bcb9  pop     rbp
0x18008bcba  pop     rbx
0x18008bcbb  retn
```
