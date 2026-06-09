# CRegKey::CRegKey(HKEY__ *,ushort const *,ulong)

- ea: `0x18000408c`
- end: `0x180004124`
- name: `??0CRegKey@@QEAA@PEAUHKEY__@@PEBGK@Z`
- size: `152`
- prototype: `CRegKey *__fastcall(PHKEY phkResult, HKEY, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003fd0`

## callees

- `0x18000408c`
- `0x18000a360`
- `0x18000ab3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800040b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800040b6`

## pseudocode

```c
CRegKey *__fastcall CRegKey::CRegKey(PHKEY phkResult, HKEY a2, const unsigned __int16 *a3, int a4)
{
  int v5; // ebx
  int pExceptionObject; // [rsp+58h] [rbp+20h] BYREF

  pExceptionObject = a4;
  v5 = RegOpenKeyExW(HKEY_CLASSES_ROOT, a3, 0, 0x20006u, phkResult);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_1eba886745fe349fd97ae921e3b476bf_Traceguids,
        (unsigned int)v5);
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    pExceptionObject = v5;
    throw (CExcept *)&pExceptionObject;
  }
  return (CRegKey *)phkResult;
}

```

## disassembly

```asm
0x18000408c  mov     [rsp+arg_0], rbx
0x180004091  mov     [rsp+pExceptionObject], r9d
0x180004096  push    rdi
0x180004097  sub     rsp, 30h
0x18000409b  mov     rdx, r8; lpSubKey
0x18000409e  mov     [rsp+38h+phkResult], rcx; phkResult
0x1800040a3  mov     rdi, rcx
0x1800040a6  xor     r8d, r8d; ulOptions
0x1800040a9  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800040b0  mov     r9d, 20006h; samDesired
0x1800040b6  call    cs:__imp_RegOpenKeyExW
0x1800040bc  mov     ebx, eax
0x1800040be  test    eax, eax
0x1800040c0  jz      short loc_180004116
0x1800040c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040c9  lea     rax, WPP_GLOBAL_Control
0x1800040d0  cmp     rcx, rax
0x1800040d3  jz      short loc_1800040F3
0x1800040d5  test    byte ptr [rcx+1Ch], 2
0x1800040d9  jz      short loc_1800040F3
0x1800040db  mov     rcx, [rcx+10h]
0x1800040df  lea     r8, WPP_1eba886745fe349fd97ae921e3b476bf_Traceguids
0x1800040e6  mov     edx, 0Bh
0x1800040eb  mov     r9d, ebx
0x1800040ee  call    WPP_SF_D
0x1800040f3  test    ebx, ebx
0x1800040f5  jle     short loc_180004100
0x1800040f7  movzx   ebx, bx
0x1800040fa  or      ebx, 80070000h
0x180004100  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180004107  mov     [rsp+38h+pExceptionObject], ebx
0x18000410b  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180004110  call    _CxxThrowException_0
0x180004116  mov     rbx, [rsp+38h+arg_0]
0x18000411b  mov     rax, rdi
0x18000411e  add     rsp, 30h
0x180004122  pop     rdi
0x180004123  retn
```
