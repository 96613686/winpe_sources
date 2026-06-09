# RegistryKey::RegistryKey(HKEY__ *,wchar_t const *,ulong,bool)

- ea: `0x180030080`
- end: `0x1800300ba`
- name: `??0RegistryKey@@QEAA@PEAUHKEY__@@PEB_WK_N@Z`
- size: `58`
- prototype: `RegistryKey *__fastcall(RegistryKey *this, HKEY, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001b698`
- `0x180026a4c`

## callees

- `0x18002f158`
- `0x180030080`
- `0x180030128`

## string_xrefs

- `0x1800300a4`: `RegOpenKeyExW`

## pseudocode

```c
RegistryKey *__fastcall RegistryKey::RegistryKey(RegistryKey *this, HKEY a2, const wchar_t *a3, int a4)
{
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = a4;
  if ( (unsigned int)RegistryKey::Create(this, -2147483646, a3) )
    SystemError::Throw(L"RegOpenKeyExW");
  return this;
}

```

## disassembly

```asm
0x180030080  push    rbx
0x180030082  sub     rsp, 30h
0x180030086  mov     rdx, 0FFFFFFFF80000002h
0x18003008d  mov     qword ptr [rcx], 0
0x180030094  mov     rbx, rcx
0x180030097  mov     [rcx+8], r9d
0x18003009b  call    ?Create@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK_N@Z; RegistryKey::Create(HKEY__ *,wchar_t const *,ulong,bool)
0x1800300a0  test    eax, eax
0x1800300a2  jz      short loc_1800300B1
0x1800300a4  lea     rcx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800300ab  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
0x1800300b1  mov     rax, rbx
0x1800300b4  add     rsp, 30h
0x1800300b8  pop     rbx
0x1800300b9  retn
```
