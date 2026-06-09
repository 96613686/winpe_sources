# AddFlagValuesToPropertyList(ushort *,ulong,ulong *,ushort * *)

- ea: `0x18000f49c`
- end: `0x18000f737`
- name: `?AddFlagValuesToPropertyList@@YAJPEAGKPEAKPEAPEAG@Z`
- size: `667`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007d90`

## callees

- `0x18000f49c`
- `0x18003098e`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18000f593`
- `IisRTL!PuDbgPrintW` at `0x18000f5e9`
- `IisRTL!PuDbgPrintW` at `0x18000f702`
- `IisRTL!PuDbgPrintW` at `0x18000f593`
- `IisRTL!PuDbgPrintW` at `0x18000f5e9`
- `IisRTL!PuDbgPrintW` at `0x18000f702`

## string_xrefs

- `0x18000f571`: `inetsrv\iis\mb\metadata\readschema.cpp`
- `0x18000f5c4`: `inetsrv\iis\mb\metadata\readschema.cpp`
- `0x18000f6d8`: `inetsrv\iis\mb\metadata\readschema.cpp`

## pseudocode

```c
__int64 __fastcall AddFlagValuesToPropertyList(unsigned __int16 *a1, int a2, unsigned int *a3, unsigned __int16 **a4)
{
  unsigned __int16 *v7; // rdi
  int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // r14d
  unsigned __int16 *v11; // rsi
  int v12; // eax
  const void *v13; // rdx
  __int64 v14; // rcx
  size_t v15; // rbx
  unsigned __int16 *v16; // rdi
  size_t v17; // rbx
  __int64 v19; // [rsp+30h] [rbp-59h]
  int v20; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v21; // [rsp+48h] [rbp-41h] BYREF
  _DWORD v22[2]; // [rsp+50h] [rbp-39h] BYREF
  int v23; // [rsp+58h] [rbp-31h] BYREF
  __int64 v24; // [rsp+5Ch] [rbp-2Dh]
  unsigned __int16 *v25; // [rsp+68h] [rbp-21h] BYREF
  int *v26; // [rsp+70h] [rbp-19h]
  void *Src[2]; // [rsp+78h] [rbp-11h]
  __int128 v28; // [rsp+88h] [rbp-1h]

  v20 = a2;
  v22[0] = 0;
  v21 = 0;
  v23 = 2;
  v7 = 0;
  v24 = 1;
  v22[1] = 1;
  *(_OWORD *)Src = 0;
  v28 = 0;
  if ( a4 && *a4 )
    v7 = *a4;
  v25 = a1;
  v26 = &v20;
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _DWORD *, _QWORD, unsigned __int16 **, unsigned int *))(**((_QWORD **)g_pGlobalISTHelper + 2) + 56LL))(
         *((_QWORD *)g_pGlobalISTHelper + 2),
         0,
         2,
         v22,
         0,
         &v25,
         &v21);
  v9 = v8;
  if ( v8 == -2145318890 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v19) = v20;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\readschema.cpp",
        2185,
        "AddFlagValuesToPropertyList",
        L"[AddFlagValuesToPropertyList] No flags found for  %s:%d.\n",
        a1,
        v19);
    }
    return 0;
  }
  else if ( v8 >= 0 )
  {
    v10 = v21;
    v11 = 0;
    while ( 1 )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, int *, _QWORD, unsigned __int16 **))(**((_QWORD **)g_pGlobalISTHelper + 2) + 32LL))(
              *((_QWORD *)g_pGlobalISTHelper + 2),
              v10,
              3,
              &v23,
              0,
              &v25);
      v9 = v12;
      if ( v12 == -2145318890 )
      {
        v9 = 0;
LABEL_28:
        if ( a4 )
          *a4 = v7;
        return v9;
      }
      if ( v12 < 0 )
        break;
      if ( !v11 )
        v11 = v25;
      if ( v11 != v25 || v20 != *v26 )
        goto LABEL_28;
      v13 = Src[0];
      v14 = -1;
      do
        ++v14;
      while ( *((_WORD *)Src[0] + v14) );
      if ( a3 )
        *a3 += v14 + 1;
      if ( v7 )
      {
        v15 = (unsigned int)v14;
        memcpy_0(v7, v13, v15 * 2);
        v16 = &v7[v15];
        v17 = g_cchComma;
        memcpy_0(v16, L",", v17 * 2);
        v7 = &v16[v17];
      }
      ++v10;
    }
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v19) = v10;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\readschema.cpp",
        2219,
        "AddFlagValuesToPropertyList",
        L"[AddFlagValuesToPropertyList] GetColumnValues for %s index %i failed with hr = 0x%x.\n",
        L"TAGMETA",
        v19,
        v12);
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v19) = v8;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\readschema.cpp",
      2194,
      "AddFlagValuesToPropertyList",
      L"[AddFlagValuesToPropertyList] GetRowIndexBySearch for %s failed with hr = 0x%x.\n",
      L"TAGMETA",
      v19);
  }
  return v9;
}

```

## disassembly

```asm
0x18000f49c  push    rbp
0x18000f49e  push    rbx
0x18000f49f  push    rsi
0x18000f4a0  push    rdi
0x18000f4a1  push    r12
0x18000f4a3  push    r13
0x18000f4a5  push    r14
0x18000f4a7  push    r15
0x18000f4a9  lea     rbp, [rsp-1Fh]
0x18000f4ae  sub     rsp, 0A8h
0x18000f4b5  mov     rax, cs:__security_cookie
0x18000f4bc  xor     rax, rsp
0x18000f4bf  mov     [rbp+57h+var_48], rax
0x18000f4c3  xor     r13d, r13d
0x18000f4c6  mov     [rbp+57h+var_A0], edx
0x18000f4c9  mov     [rbp+57h+var_90], r13d
0x18000f4cd  mov     r12, r8
0x18000f4d0  mov     [rbp+57h+var_98], r13d
0x18000f4d4  mov     r8d, 2
0x18000f4da  mov     [rbp+57h+var_88], r8d
0x18000f4de  xorps   xmm0, xmm0
0x18000f4e1  xorps   xmm1, xmm1
0x18000f4e4  mov     r15, r9
0x18000f4e7  mov     rsi, rcx
0x18000f4ea  mov     edi, r13d
0x18000f4ed  lea     eax, [r8-1]
0x18000f4f1  mov     [rbp+57h+var_84], rax
0x18000f4f5  mov     [rbp+57h+var_8C], eax
0x18000f4f8  movdqu  xmmword ptr [rbp+57h+Src], xmm0
0x18000f4fd  movdqu  [rbp+57h+var_58], xmm1
0x18000f502  test    r9, r9
0x18000f505  jz      short loc_18000F50E
0x18000f507  cmp     [r9], r13
0x18000f50a  cmovnz  rdi, [r9]
0x18000f50e  mov     [rbp+57h+var_78], rsi
0x18000f512  lea     rax, [rbp+57h+var_A0]
0x18000f516  mov     [rbp+57h+var_70], rax
0x18000f51a  lea     rdx, [rbp+57h+var_98]
0x18000f51e  mov     rax, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x18000f525  lea     r9, [rbp+57h+var_90]
0x18000f529  mov     [rsp+0E0h+var_B0], rdx
0x18000f52e  lea     rdx, [rbp+57h+var_78]
0x18000f532  mov     [rsp+0E0h+var_B8], rdx
0x18000f537  xor     edx, edx
0x18000f539  mov     [rsp+0E0h+var_C0], r13
0x18000f53e  mov     rcx, [rax+10h]
0x18000f542  mov     rax, [rcx]
0x18000f545  mov     rax, [rax+38h]
0x18000f549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f54e  mov     ebx, eax
0x18000f550  cmp     eax, 80210816h
0x18000f555  jnz     short loc_18000F5A1
0x18000f557  test    byte ptr cs:g_dwDebugFlags, 3
0x18000f55e  jz      short loc_18000F599
0x18000f560  mov     eax, [rbp+57h+var_A0]
0x18000f563  lea     r9, aAddflagvaluest_2; "AddFlagValuesToPropertyList"
0x18000f56a  mov     rcx, cs:g_pDebug
0x18000f571  lea     rdx, aInetsrvIisMbMe_0; "inetsrv\\iis\\mb\\metadata\\readschema."...
0x18000f578  mov     dword ptr [rsp+0E0h+var_B0], eax
0x18000f57c  mov     r8d, 889h
0x18000f582  lea     rax, aAddflagvaluest; "[AddFlagValuesToPropertyList] No flags "...
0x18000f589  mov     [rsp+0E0h+var_B8], rsi
0x18000f58e  mov     [rsp+0E0h+var_C0], rax
0x18000f593  call    cs:__imp_PuDbgPrintW
0x18000f599  mov     ebx, r13d
0x18000f59c  jmp     loc_18000F715
0x18000f5a1  test    eax, eax
0x18000f5a3  jns     short loc_18000F5F4
0x18000f5a5  test    byte ptr cs:g_dwDebugFlags, 3
0x18000f5ac  jz      loc_18000F715
0x18000f5b2  mov     rcx, cs:g_pDebug
0x18000f5b9  lea     r9, aAddflagvaluest_2; "AddFlagValuesToPropertyList"
0x18000f5c0  mov     dword ptr [rsp+0E0h+var_B0], eax
0x18000f5c4  lea     rdx, aInetsrvIisMbMe_0; "inetsrv\\iis\\mb\\metadata\\readschema."...
0x18000f5cb  lea     rax, aTagmeta; "TAGMETA"
0x18000f5d2  mov     r8d, 892h
0x18000f5d8  mov     [rsp+0E0h+var_B8], rax
0x18000f5dd  lea     rax, aAddflagvaluest_0; "[AddFlagValuesToPropertyList] GetRowInd"...
0x18000f5e4  mov     [rsp+0E0h+var_C0], rax
0x18000f5e9  call    cs:__imp_PuDbgPrintW
0x18000f5ef  jmp     loc_18000F715
0x18000f5f4  mov     r14d, [rbp+57h+var_98]
0x18000f5f8  mov     rsi, r13
0x18000f5fb  mov     rax, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x18000f602  lea     rdx, [rbp+57h+var_78]
0x18000f606  mov     [rsp+0E0h+var_B8], rdx
0x18000f60b  lea     r9, [rbp+57h+var_88]
0x18000f60f  mov     r8d, 3
0x18000f615  mov     [rsp+0E0h+var_C0], r13
0x18000f61a  mov     edx, r14d
0x18000f61d  mov     rcx, [rax+10h]
0x18000f621  mov     rax, [rcx]
0x18000f624  mov     rax, [rax+20h]
0x18000f628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f62d  mov     ebx, eax
0x18000f62f  cmp     eax, 80210816h
0x18000f634  jz      loc_18000F70A
0x18000f63a  test    eax, eax
0x18000f63c  js      short loc_18000F6BD
0x18000f63e  test    rsi, rsi
0x18000f641  cmovz   rsi, [rbp+57h+var_78]
0x18000f646  cmp     rsi, [rbp+57h+var_78]
0x18000f64a  jnz     loc_18000F70D
0x18000f650  mov     rax, [rbp+57h+var_70]
0x18000f654  mov     ecx, [rax]
0x18000f656  cmp     [rbp+57h+var_A0], ecx
0x18000f659  jnz     loc_18000F70D
0x18000f65f  mov     rdx, [rbp+57h+Src]; Src
0x18000f663  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000f667  inc     rcx
0x18000f66a  cmp     [rdx+rcx*2], r13w
0x18000f66f  jnz     short loc_18000F667
0x18000f671  test    r12, r12
0x18000f674  jz      short loc_18000F67D
0x18000f676  lea     eax, [rcx+1]
0x18000f679  add     [r12], eax
0x18000f67d  test    rdi, rdi
0x18000f680  jz      short loc_18000F6B5
0x18000f682  mov     eax, ecx
0x18000f684  mov     rcx, rdi; void *
0x18000f687  lea     rbx, [rax+rax]
0x18000f68b  mov     r8, rbx; Size
0x18000f68e  call    memcpy_0
0x18000f693  mov     eax, cs:?g_cchComma@@3KA; ulong g_cchComma
0x18000f699  lea     rdx, asc_180033CF0; ","
0x18000f6a0  add     rdi, rbx
0x18000f6a3  mov     rcx, rdi; void *
0x18000f6a6  lea     rbx, [rax+rax]
0x18000f6aa  mov     r8, rbx; Size
0x18000f6ad  call    memcpy_0
0x18000f6b2  add     rdi, rbx
0x18000f6b5  inc     r14d
0x18000f6b8  jmp     loc_18000F5FB
0x18000f6bd  test    byte ptr cs:g_dwDebugFlags, 3
0x18000f6c4  jz      short loc_18000F715
0x18000f6c6  mov     rcx, cs:g_pDebug
0x18000f6cd  lea     r9, aAddflagvaluest_2; "AddFlagValuesToPropertyList"
0x18000f6d4  mov     [rsp+0E0h+var_A8], eax
0x18000f6d8  lea     rdx, aInetsrvIisMbMe_0; "inetsrv\\iis\\mb\\metadata\\readschema."...
0x18000f6df  lea     rax, aTagmeta; "TAGMETA"
0x18000f6e6  mov     dword ptr [rsp+0E0h+var_B0], r14d
0x18000f6eb  mov     [rsp+0E0h+var_B8], rax
0x18000f6f0  mov     r8d, 8ABh
0x18000f6f6  lea     rax, aAddflagvaluest_1; "[AddFlagValuesToPropertyList] GetColumn"...
0x18000f6fd  mov     [rsp+0E0h+var_C0], rax
0x18000f702  call    cs:__imp_PuDbgPrintW
0x18000f708  jmp     short loc_18000F715
0x18000f70a  mov     ebx, r13d
0x18000f70d  test    r15, r15
0x18000f710  jz      short loc_18000F715
0x18000f712  mov     [r15], rdi
0x18000f715  mov     eax, ebx
0x18000f717  mov     rcx, [rbp+57h+var_48]
0x18000f71b  xor     rcx, rsp; StackCookie
0x18000f71e  call    __security_check_cookie
0x18000f723  add     rsp, 0A8h
0x18000f72a  pop     r15
0x18000f72c  pop     r14
0x18000f72e  pop     r13
0x18000f730  pop     r12
0x18000f732  pop     rdi
0x18000f733  pop     rsi
0x18000f734  pop     rbx
0x18000f735  pop     rbp
0x18000f736  retn
```
