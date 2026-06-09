# CFontAgent::RemoveResource(void)

- ea: `0x180008288`
- end: `0x1800082ff`
- name: `?RemoveResource@CFontAgent@@QEAAJXZ`
- size: `119`
- prototype: `__int64 __fastcall(CFontAgent *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001ea2c`
- `0x18001eda8`

## callees

- `0x180008288`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082cf`
- `GDI32!RemoveFontResourceW` at `0x1800082c5`
- `GDI32!RemoveFontResourceW` at `0x1800082c5`

## pseudocode

```c
__int64 __fastcall CFontAgent::RemoveResource(CFontAgent *this)
{
  int v1; // ebx
  signed int LastError; // eax
  WCHAR FileName[520]; // [rsp+20h] [rbp-428h] BYREF

  v1 = (*(__int64 (__fastcall **)(CFontAgent *, WCHAR *, __int64))(*(_QWORD *)this + 96LL))(this, FileName, 520);
  if ( v1 >= 0 && !RemoveFontResourceW(FileName) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180008288  push    rbx
0x18000828a  sub     rsp, 440h
0x180008291  mov     rax, cs:__security_cookie
0x180008298  xor     rax, rsp
0x18000829b  mov     [rsp+448h+var_18], rax
0x1800082a3  mov     rax, [rcx]
0x1800082a6  lea     rdx, [rsp+448h+FileName]
0x1800082ab  mov     r8d, 208h
0x1800082b1  mov     rax, [rax+60h]
0x1800082b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082ba  mov     ebx, eax
0x1800082bc  test    eax, eax
0x1800082be  js      short loc_1800082E4
0x1800082c0  lea     rcx, [rsp+448h+FileName]; lpFileName
0x1800082c5  call    cs:__imp_RemoveFontResourceW
0x1800082cb  test    eax, eax
0x1800082cd  jnz     short loc_1800082E4
0x1800082cf  call    cs:__imp_GetLastError
0x1800082d5  mov     ebx, eax
0x1800082d7  test    eax, eax
0x1800082d9  jle     short loc_1800082E4
0x1800082db  movzx   ebx, ax
0x1800082de  or      ebx, 80070000h
0x1800082e4  mov     eax, ebx
0x1800082e6  mov     rcx, [rsp+448h+var_18]
0x1800082ee  xor     rcx, rsp; StackCookie
0x1800082f1  call    __security_check_cookie
0x1800082f6  add     rsp, 440h
0x1800082fd  pop     rbx
0x1800082fe  retn
```
