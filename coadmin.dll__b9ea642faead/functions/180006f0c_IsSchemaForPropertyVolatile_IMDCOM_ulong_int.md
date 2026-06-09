# IsSchemaForPropertyVolatile(IMDCOM *,ulong,int *)

- ea: `0x180006f0c`
- end: `0x18000705f`
- name: `?IsSchemaForPropertyVolatile@@YAJPEAUIMDCOM@@KPEAH@Z`
- size: `339`
- prototype: `__int64 __fastcall(struct IMDCOM *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cec`

## callees

- `0x180006f0c`
- `0x180010010`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180006fd1`
- `IisRTL!PuDbgPrint` at `0x180007004`
- `IisRTL!PuDbgPrint` at `0x18000704a`
- `IisRTL!PuDbgPrint` at `0x180006fd1`
- `IisRTL!PuDbgPrint` at `0x180007004`
- `IisRTL!PuDbgPrint` at `0x18000704a`

## string_xrefs

- `0x180006fbf`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180006ff2`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180007043`: `inetsrv\iis\mb\coadmin\comobj.cxx`

## pseudocode

```c
__int64 __fastcall IsSchemaForPropertyVolatile(struct IMDCOM *a1, int a2, int *a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  int v6; // eax
  __int128 v8; // [rsp+30h] [rbp-29h] BYREF
  __int128 v9; // [rsp+40h] [rbp-19h]
  __int64 v10; // [rsp+50h] [rbp-9h]
  _OWORD v11[2]; // [rsp+58h] [rbp-1h] BYREF
  __int128 v12; // [rsp+78h] [rbp+1Fh]
  __int64 v13; // [rsp+88h] [rbp+2Fh]
  int v14; // [rsp+C0h] [rbp+67h] BYREF

  v10 = 0;
  v14 = 0;
  v13 = 0;
  v8 = 0;
  v9 = 0;
  memset(v11, 0, sizeof(v11));
  v12 = 0;
  if ( !a1 || !a3 )
  {
    v4 = -2147024809;
LABEL_7:
    if ( (g_dwDebugFlags & 8) != 0 )
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", 4865, &word_1800127E6, "*%08x\n", v4);
    return v4;
  }
  *a3 = 0;
  LODWORD(v8) = a2;
  *((_QWORD *)&v9 + 1) = v11;
  v5 = *(_QWORD *)a1;
  HIDWORD(v8) = 3;
  LODWORD(v9) = 56;
  v6 = (*(__int64 (__fastcall **)(struct IMDCOM *, _QWORD, const wchar_t *, __int128 *, int *))(v5 + 168))(
         a1,
         0,
         L"/SCHEMA/PROPERTIES/TYPES",
         &v8,
         &v14);
  v4 = v6;
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 4) != 0 )
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", 4856, &word_1800127E6, "*%08x\n", v6);
    goto LABEL_7;
  }
  if ( (v12 & 0x10) != 0 )
    *a3 = 1;
  v4 = 0;
  if ( (g_dwDebugFlags & 1) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", 4865, &word_1800127E6, "\n");
  return v4;
}

```

## disassembly

```asm
0x180006f0c  push    rbp
0x180006f0e  push    rbx
0x180006f0f  push    rdi
0x180006f10  push    r15
0x180006f12  lea     rbp, [rsp-3Fh]
0x180006f17  sub     rsp, 98h
0x180006f1e  xorps   xmm0, xmm0
0x180006f21  lea     r15, a08x; "*%08x\n"
0x180006f28  xor     eax, eax
0x180006f2a  mov     rdi, r8
0x180006f2d  mov     [rbp+57h+var_60], rax
0x180006f31  mov     [rbp+57h+arg_0], eax
0x180006f34  mov     [rbp+57h+var_28], rax
0x180006f38  movups  [rbp+57h+var_80], xmm0
0x180006f3c  movups  [rbp+57h+var_70], xmm0
0x180006f40  movups  [rbp+57h+var_58], xmm0
0x180006f44  movups  [rbp+57h+var_48], xmm0
0x180006f48  movups  [rbp+57h+var_38], xmm0
0x180006f4c  test    rcx, rcx
0x180006f4f  jnz     short loc_180006F58
0x180006f51  mov     ebx, 80070057h
0x180006f56  jmp     short loc_180006FD7
0x180006f58  test    rdi, rdi
0x180006f5b  jz      short loc_180006F51
0x180006f5d  mov     [r8], eax
0x180006f60  lea     r9, [rbp+57h+var_80]
0x180006f64  mov     dword ptr [rbp+57h+var_80], edx
0x180006f67  lea     rax, [rbp+57h+var_58]
0x180006f6b  mov     qword ptr [rbp+57h+var_70+8], rax
0x180006f6f  lea     rdx, [rbp+57h+arg_0]
0x180006f73  mov     rax, [rcx]
0x180006f76  lea     r8, aSchemaProperti; "/SCHEMA/PROPERTIES/TYPES"
0x180006f7d  mov     [rsp+0B0h+var_90], rdx
0x180006f82  xor     edx, edx
0x180006f84  mov     dword ptr [rbp+57h+var_80+0Ch], 3
0x180006f8b  mov     dword ptr [rbp+57h+var_70], 38h ; '8'
0x180006f92  mov     rax, [rax+0A8h]
0x180006f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f9e  mov     ebx, eax
0x180006fa0  test    eax, eax
0x180006fa2  jns     short loc_18000700C
0x180006fa4  test    byte ptr cs:g_dwDebugFlags, 4
0x180006fab  jz      short loc_180006FD7
0x180006fad  mov     rcx, cs:g_pDebug
0x180006fb4  lea     r9, word_1800127E6
0x180006fbb  mov     [rsp+0B0h+var_88], eax
0x180006fbf  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180006fc6  mov     r8d, 12F8h
0x180006fcc  mov     [rsp+0B0h+var_90], r15
0x180006fd1  call    cs:__imp_PuDbgPrint
0x180006fd7  test    byte ptr cs:g_dwDebugFlags, 8
0x180006fde  jz      short loc_180007050
0x180006fe0  mov     rcx, cs:g_pDebug
0x180006fe7  lea     r9, word_1800127E6
0x180006fee  mov     [rsp+0B0h+var_88], ebx
0x180006ff2  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180006ff9  mov     r8d, 1301h
0x180006fff  mov     [rsp+0B0h+var_90], r15
0x180007004  call    cs:__imp_PuDbgPrint
0x18000700a  jmp     short loc_180007050
0x18000700c  test    byte ptr [rbp+57h+var_38], 10h
0x180007010  jz      short loc_180007018
0x180007012  mov     dword ptr [rdi], 1
0x180007018  xor     ebx, ebx
0x18000701a  test    byte ptr cs:g_dwDebugFlags, 1
0x180007021  jz      short loc_180007050
0x180007023  mov     rcx, cs:g_pDebug
0x18000702a  lea     rax, asc_1800127E4; "\n"
0x180007031  lea     r9, word_1800127E6
0x180007038  mov     [rsp+0B0h+var_90], rax
0x18000703d  mov     r8d, 1301h
0x180007043  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x18000704a  call    cs:__imp_PuDbgPrint
0x180007050  mov     eax, ebx
0x180007052  add     rsp, 98h
0x180007059  pop     r15
0x18000705b  pop     rdi
0x18000705c  pop     rbx
0x18000705d  pop     rbp
0x18000705e  retn
```
