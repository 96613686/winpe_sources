# CFontRegistry::OpenKey(CFontRegValue const &,ulong,HKEY__ * *)

- ea: `0x180025e80`
- end: `0x180025f29`
- name: `?OpenKey@CFontRegistry@@SAJAEBVCFontRegValue@@KPEAPEAUHKEY__@@@Z`
- size: `169`
- prototype: `static int(const struct CFontRegValue *, unsigned int, HKEY *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180025b58`
- `0x180025bdc`
- `0x180025cd4`
- `0x180025da8`

## callees

- `0x180025e80`
- `0x18003104a`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025efc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025efc`

## pseudocode

```c
LSTATUS __fastcall CFontRegistry::OpenKey(const struct CFontRegValue *a1, REGSAM a2, HKEY *a3)
{
  const WCHAR *v6; // rax
  LSTATUS result; // eax
  WCHAR Class[264]; // [rsp+50h] [rbp-238h] BYREF

  memset_0(Class, 0, 0x208u);
  v6 = (const WCHAR *)(*(__int64 (__fastcall **)(const struct CFontRegValue *))(*(_QWORD *)a1 + 32LL))(a1);
  result = RegCreateKeyExW((HKEY)((*((_DWORD *)a1 + 2) != 0) - 0x7FFFFFFFLL), v6, 0, Class, 0, a2, 0, a3, 0);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180025e80  push    rbx
0x180025e82  push    rsi
0x180025e83  push    rdi
0x180025e84  sub     rsp, 270h
0x180025e8b  mov     rax, cs:__security_cookie
0x180025e92  xor     rax, rsp
0x180025e95  mov     [rsp+288h+var_28], rax
0x180025e9d  mov     rdi, r8
0x180025ea0  mov     esi, edx
0x180025ea2  mov     rbx, rcx
0x180025ea5  xor     edx, edx; Val
0x180025ea7  mov     r8d, 208h; Size
0x180025ead  lea     rcx, [rsp+288h+Class]; void *
0x180025eb2  call    memset_0
0x180025eb7  mov     rax, [rbx]
0x180025eba  mov     rcx, rbx
0x180025ebd  mov     rax, [rax+20h]
0x180025ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ec6  mov     ecx, [rbx+8]
0x180025ec9  lea     r9, [rsp+288h+Class]; lpClass
0x180025ece  neg     ecx
0x180025ed0  mov     rdx, rax; lpSubKey
0x180025ed3  sbb     rcx, rcx
0x180025ed6  xor     ebx, ebx
0x180025ed8  mov     [rsp+288h+lpdwDisposition], rbx; lpdwDisposition
0x180025edd  neg     rcx
0x180025ee0  mov     [rsp+288h+phkResult], rdi; phkResult
0x180025ee5  add     rcx, 0FFFFFFFF80000001h; hKey
0x180025eec  mov     [rsp+288h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180025ef1  xor     r8d, r8d; Reserved
0x180025ef4  mov     [rsp+288h+samDesired], esi; samDesired
0x180025ef8  mov     [rsp+288h+dwOptions], ebx; dwOptions
0x180025efc  call    cs:__imp_RegCreateKeyExW
0x180025f02  test    eax, eax
0x180025f04  jle     short loc_180025F0E
0x180025f06  movzx   eax, ax
0x180025f09  or      eax, 80070000h
0x180025f0e  mov     rcx, [rsp+288h+var_28]
0x180025f16  xor     rcx, rsp; StackCookie
0x180025f19  call    __security_check_cookie
0x180025f1e  add     rsp, 270h
0x180025f25  pop     rdi
0x180025f26  pop     rsi
0x180025f27  pop     rbx
0x180025f28  retn
```
