# MI_ReportErrorDetails_OutOfMemory_OnceInit

- ea: `0x180007f40`
- end: `0x1800080b6`
- name: `MI_ReportErrorDetails_OutOfMemory_OnceInit`
- size: `374`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000175c`
- `0x180006ef8`
- `0x180007f40`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180007f7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180007f7f`
- `miutils!Instance_Construct` at `0x180007f5f`
- `miutils!Instance_Construct` at `0x180007f5f`

## string_xrefs

- `0x180007f78`: `mpunits.dll`

## pseudocode

```c
int __fastcall MI_ReportErrorDetails_OutOfMemory_OnceInit(__int64 a1, _QWORD *a2)
{
  HMODULE ModuleHandleA; // rax
  const char *v5; // [rsp+50h] [rbp+18h] BYREF

  if ( (unsigned int)Instance_Construct(&OMI_DebugError_rtti, &qword_18008E4B0) )
  {
    *a2 = 0;
    return -1;
  }
  else
  {
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    qword_18008E458 = Intlstr_GetString_LoadString(ModuleHandleA, 2042);
    v5 = (const char *)qword_18008E458;
    (*(void (__fastcall **)(__int64 *, __int64, const char **))(qword_18008E4B0 + 80))(&qword_18008E4B0, 4, &v5);
    dword_18008E5C0 = 27;
    v5 = L"MI";
    byte_18008E5C4 = 1;
    (*(void (__fastcall **)(__int64 *, __int64, const char **))(qword_18008E4B0 + 80))(&qword_18008E4B0, 16, &v5);
    byte_18008E5DA = 1;
    word_18008E5D8 = 29;
    xmmword_18008E478 = xmmword_18008E4B8;
    dword_18008E5A8 = 27;
    qword_18008E470 = (__int64)g_refCountedInstanceFT;
    xmmword_18008E488 = xmmword_18008E4C8;
    byte_18008E5AC = 1;
    xmmword_18008E498 = xmmword_18008E4D8;
    qword_18008E460 = 1;
    qword_18008E468 = (__int64)&qword_18008E4B0;
    qword_18008E4A8 = qword_18008E4E8;
    *a2 = &qword_18008E470;
    qword_18006E050 = (__int64)&qword_18008E470;
    return atexit(MI_ReportErrorDetails_OutOfMemory_OnceCleanUp);
  }
}

```

## disassembly

```asm
0x180007f40  mov     [rsp+arg_0], rbx
0x180007f45  push    r14
0x180007f47  sub     rsp, 30h
0x180007f4b  mov     rbx, rdx
0x180007f4e  lea     r14, qword_18008E4B0
0x180007f55  mov     rdx, r14
0x180007f58  lea     rcx, OMI_DebugError_rtti
0x180007f5f  call    cs:__imp_Instance_Construct
0x180007f65  test    eax, eax
0x180007f67  jz      short loc_180007F78
0x180007f69  mov     qword ptr [rbx], 0
0x180007f70  or      eax, 0FFFFFFFFh
0x180007f73  jmp     loc_1800080AA
0x180007f78  lea     rcx, ModuleName; "mpunits.dll"
0x180007f7f  call    cs:__imp_GetModuleHandleA
0x180007f85  mov     rcx, rax
0x180007f88  mov     edx, 7FAh
0x180007f8d  call    _Intlstr_GetString_LoadString
0x180007f92  mov     cs:qword_18008E458, rax
0x180007f99  lea     r8, [rsp+38h+arg_10]
0x180007f9e  mov     [rsp+38h+arg_10], rax
0x180007fa3  mov     r9d, 0Dh
0x180007fa9  mov     rax, cs:qword_18008E4B0
0x180007fb0  mov     rcx, r14
0x180007fb3  mov     [rsp+38h+var_18], 40000000h
0x180007fbb  lea     edx, [r9-9]
0x180007fbf  mov     rax, [rax+50h]
0x180007fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fc8  lea     rax, aMi; "MI"
0x180007fcf  mov     cs:dword_18008E5C0, 1Bh
0x180007fd9  mov     [rsp+38h+arg_10], rax
0x180007fde  lea     r8, [rsp+38h+arg_10]
0x180007fe3  mov     rax, cs:qword_18008E4B0
0x180007fea  mov     r9d, 0Dh
0x180007ff0  mov     cs:byte_18008E5C4, 1
0x180007ff7  mov     rcx, r14
0x180007ffa  mov     [rsp+38h+var_18], 40000000h
0x180008002  mov     rax, [rax+50h]
0x180008006  lea     edx, [r9+3]
0x18000800a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000800f  movups  xmm0, cs:xmmword_18008E4B8
0x180008016  mov     eax, 1Dh
0x18000801b  mov     cs:byte_18008E5DA, 1
0x180008022  movups  xmm1, cs:xmmword_18008E4C8
0x180008029  mov     cs:word_18008E5D8, ax
0x180008030  lea     rcx, MI_ReportErrorDetails_OutOfMemory_OnceCleanUp; void (__cdecl *)()
0x180008037  movups  cs:xmmword_18008E478, xmm0
0x18000803e  lea     rax, g_refCountedInstanceFT
0x180008045  mov     cs:dword_18008E5A8, 1Bh
0x18000804f  movups  xmm0, cs:xmmword_18008E4D8
0x180008056  mov     cs:qword_18008E470, rax
0x18000805d  lea     rax, qword_18008E470
0x180008064  movups  cs:xmmword_18008E488, xmm1
0x18000806b  mov     cs:byte_18008E5AC, 1
0x180008072  movsd   xmm1, cs:qword_18008E4E8
0x18000807a  movups  cs:xmmword_18008E498, xmm0
0x180008081  mov     cs:qword_18008E460, 1
0x18000808c  mov     cs:qword_18008E468, r14
0x180008093  movsd   cs:qword_18008E4A8, xmm1
0x18000809b  mov     [rbx], rax
0x18000809e  mov     cs:qword_18006E050, rax
0x1800080a5  call    atexit
0x1800080aa  mov     rbx, [rsp+38h+arg_0]
0x1800080af  add     rsp, 30h
0x1800080b3  pop     r14
0x1800080b5  retn
```
