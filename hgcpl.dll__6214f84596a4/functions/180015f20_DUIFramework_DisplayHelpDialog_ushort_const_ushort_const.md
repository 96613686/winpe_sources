# DUIFramework_DisplayHelpDialog(ushort const *,ushort const *)

- ea: `0x180015f20`
- end: `0x180016025`
- name: `?DUIFramework_DisplayHelpDialog@@YAJPEBG0@Z`
- size: `261`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b080`

## callees

- `0x180006338`
- `0x1800063c4`
- `0x180015f20`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015f9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015f9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015fef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015fef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015f73`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015f73`
- `USER32!SetCursor` at `0x180015f44`
- `USER32!SetCursor` at `0x180016010`
- `USER32!SetCursor` at `0x180015f44`
- `USER32!SetCursor` at `0x180016010`
- `USER32!LoadCursorW` at `0x180015f3b`
- `USER32!LoadCursorW` at `0x180015f3b`

## pseudocode

```c
__int64 __fastcall DUIFramework_DisplayHelpDialog(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  HCURSOR CursorW; // rax
  HCURSOR v4; // r14
  HRESULT v5; // ebx
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdi
  LPVOID ppv; // [rsp+78h] [rbp+10h] BYREF

  ppv = a2;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v4 = SetCursor(CursorW);
  ppv = 0;
  v5 = CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         1u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &ppv);
  if ( v5 >= 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a1[v6] );
    v7 = v6 + 22;
    v8 = (unsigned __int16 *)LocalAlloc(0, 2 * (v6 + 22));
    v9 = v8;
    if ( v8 )
    {
      v5 = StringCchCopyW(v8, v7, L"mshelp://windows/?id=");
      if ( v5 >= 0 )
      {
        v5 = StringCchCatW(v9, v7, a1);
        if ( v5 >= 0 )
          v5 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, v9);
      }
      LocalFree(v9);
    }
    else
    {
      v5 = -2147024882;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  SetCursor(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180015f20  mov     [rsp+arg_8], rdx
0x180015f25  push    rbx
0x180015f26  push    rbp
0x180015f27  push    rsi
0x180015f28  push    rdi
0x180015f29  push    r14
0x180015f2b  push    r15
0x180015f2d  sub     rsp, 38h
0x180015f31  mov     rbp, rcx
0x180015f34  mov     edx, 7F02h; lpCursorName
0x180015f39  xor     ecx, ecx; hInstance
0x180015f3b  call    cs:__imp_LoadCursorW
0x180015f41  mov     rcx, rax; hCursor
0x180015f44  call    cs:__imp_SetCursor
0x180015f4a  xor     r15d, r15d
0x180015f4d  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x180015f54  mov     r14, rax
0x180015f57  mov     [rsp+68h+arg_8], r15
0x180015f5c  lea     rax, [rsp+68h+arg_8]
0x180015f61  xor     edx, edx; pUnkOuter
0x180015f63  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x180015f6a  mov     [rsp+68h+ppv], rax; ppv
0x180015f6f  lea     r8d, [r15+1]; dwClsContext
0x180015f73  call    cs:__imp_CoCreateInstance
0x180015f79  mov     ebx, eax
0x180015f7b  test    eax, eax
0x180015f7d  js      loc_18001600D
0x180015f83  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015f87  inc     rax
0x180015f8a  cmp     [rbp+rax*2+0], r15w
0x180015f90  jnz     short loc_180015F87
0x180015f92  lea     rsi, [rax+16h]
0x180015f96  xor     ecx, ecx; uFlags
0x180015f98  lea     rdx, [rsi+rsi]; uBytes
0x180015f9c  call    cs:__imp_LocalAlloc
0x180015fa2  mov     rdi, rax
0x180015fa5  test    rax, rax
0x180015fa8  jz      short loc_180015FF7
0x180015faa  lea     r8, aMshelpWindowsI; "mshelp://windows/?id="
0x180015fb1  mov     rdx, rsi; unsigned __int64
0x180015fb4  mov     rcx, rax; unsigned __int16 *
0x180015fb7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015fbc  mov     ebx, eax
0x180015fbe  test    eax, eax
0x180015fc0  js      short loc_180015FEC
0x180015fc2  mov     r8, rbp; unsigned __int16 *
0x180015fc5  mov     rdx, rsi; unsigned __int64
0x180015fc8  mov     rcx, rdi; unsigned __int16 *
0x180015fcb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015fd0  mov     ebx, eax
0x180015fd2  test    eax, eax
0x180015fd4  js      short loc_180015FEC
0x180015fd6  mov     rcx, [rsp+68h+arg_8]
0x180015fdb  mov     rdx, rdi
0x180015fde  mov     rax, [rcx]
0x180015fe1  mov     rax, [rax+18h]
0x180015fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fea  mov     ebx, eax
0x180015fec  mov     rcx, rdi; hMem
0x180015fef  call    cs:__imp_LocalFree
0x180015ff5  jmp     short loc_180015FFC
0x180015ff7  mov     ebx, 8007000Eh
0x180015ffc  mov     rcx, [rsp+68h+arg_8]
0x180016001  mov     rax, [rcx]
0x180016004  mov     rax, [rax+10h]
0x180016008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001600d  mov     rcx, r14; hCursor
0x180016010  call    cs:__imp_SetCursor
0x180016016  mov     eax, ebx
0x180016018  add     rsp, 38h
0x18001601c  pop     r15
0x18001601e  pop     r14
0x180016020  pop     rdi
0x180016021  pop     rsi
0x180016022  pop     rbp
0x180016023  pop     rbx
0x180016024  retn
```
