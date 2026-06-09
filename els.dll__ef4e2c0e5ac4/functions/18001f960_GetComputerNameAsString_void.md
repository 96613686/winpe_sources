# GetComputerNameAsString(void)

- ea: `0x18001f960`
- end: `0x18001f9c5`
- name: `?GetComputerNameAsString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008be0`
- `0x1800098e0`
- `0x18000e208`
- `0x18000eb2c`
- `0x180016cd4`

## callees

- `0x180001750`
- `0x1800222d0`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x18001f99c`
- `KERNEL32!GetComputerNameW` at `0x18001f99c`

## pseudocode

```c
__int64 __fastcall GetComputerNameAsString(__int64 a1)
{
  DWORD nSize[4]; // [rsp+20h] [rbp-48h] BYREF
  WCHAR Buffer[8]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v5; // [rsp+40h] [rbp-28h]

  nSize[1] = HIDWORD(a1);
  nSize[0] = 16;
  *(_OWORD *)Buffer = 0;
  v5 = 0;
  GetComputerNameW(Buffer, nSize);
  std::wstring::wstring(a1, Buffer);
  return a1;
}

```

## disassembly

```asm
0x18001f960  push    rbx
0x18001f962  sub     rsp, 60h
0x18001f966  mov     rax, cs:__security_cookie
0x18001f96d  xor     rax, rsp
0x18001f970  mov     [rsp+68h+var_18], rax
0x18001f975  mov     qword ptr [rsp+68h+nSize], rcx
0x18001f97a  lea     rdx, [rsp+68h+nSize]; nSize
0x18001f97f  xorps   xmm0, xmm0
0x18001f982  mov     [rsp+68h+nSize], 10h
0x18001f98a  mov     rbx, rcx
0x18001f98d  lea     rcx, [rsp+68h+Buffer]; lpBuffer
0x18001f992  movups  xmmword ptr [rsp+68h+Buffer], xmm0
0x18001f997  movups  [rsp+68h+var_28], xmm0
0x18001f99c  call    cs:__imp_GetComputerNameW
0x18001f9a2  lea     rdx, [rsp+68h+Buffer]
0x18001f9a7  mov     rcx, rbx
0x18001f9aa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001f9af  mov     rax, rbx
0x18001f9b2  mov     rcx, [rsp+68h+var_18]
0x18001f9b7  xor     rcx, rsp; StackCookie
0x18001f9ba  call    __security_check_cookie
0x18001f9bf  add     rsp, 60h
0x18001f9c3  pop     rbx
0x18001f9c4  retn
```
