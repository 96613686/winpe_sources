# RegistryKey::RegistryKey(HKEY__ *,wchar_t const *,ulong,bool)

- ea: `0x180031294`
- end: `0x1800312cf`
- name: `??0RegistryKey@@QEAA@PEAUHKEY__@@PEB_WK_N@Z`
- size: `59`
- prototype: `RegistryKey *__fastcall(RegistryKey *__hidden this, HKEY, const wchar_t *, unsigned int, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001c0a8`
- `0x1800277a8`

## callees

- `0x180030288`
- `0x180031294`
- `0x180031348`

## string_xrefs

- `0x1800312b8`: `RegOpenKeyExW`

## pseudocode

```c
RegistryKey *__fastcall RegistryKey::RegistryKey(RegistryKey *this, HKEY a2, const wchar_t *a3, int a4)
{
  DWORD v6; // [rsp+20h] [rbp-18h]

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = a4;
  if ( (unsigned int)RegistryKey::Create(this, HKEY_LOCAL_MACHINE, a3, a4, v6) )
    SystemError::Throw(L"RegOpenKeyExW");
  return this;
}

```

## disassembly

```asm
0x180031294  push    rbx
0x180031296  sub     rsp, 30h
0x18003129a  mov     rdx, 0FFFFFFFF80000002h
0x1800312a1  mov     qword ptr [rcx], 0
0x1800312a8  mov     rbx, rcx
0x1800312ab  mov     [rcx+8], r9d
0x1800312af  call    ?Create@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK_N@Z; RegistryKey::Create(HKEY__ *,wchar_t const *,ulong,bool)
0x1800312b4  test    eax, eax
0x1800312b6  jz      short loc_1800312C5
0x1800312b8  lea     rcx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800312bf  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
0x1800312c5  mov     rax, rbx
0x1800312c8  add     rsp, 30h
0x1800312cc  pop     rbx
0x1800312cd  retn
```
