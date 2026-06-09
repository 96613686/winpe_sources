# CLocationWriter::GetGroupEnum(ushort *,eMBProperty_Group *,ushort * *)

- ea: `0x180006e98`
- end: `0x180007047`
- name: `?GetGroupEnum@CLocationWriter@@AEAAJPEAGPEAW4eMBProperty_Group@@PEAPEAG@Z`
- size: `431`
- prototype: `__int64 __fastcall(CLocationWriter *__hidden this, unsigned __int16 *, enum eMBProperty_Group *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006dc4`

## callees

- `0x180006e98`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x180006fb2`
- `IisRTL!PuDbgPrintW` at `0x180006fb2`

## string_xrefs

- `0x180006f9f`: `CLocationWriter::GetGroupEnum`
- `0x180006fa6`: `inetsrv\iis\mb\xmlwriter\locationwriter.cpp`

## pseudocode

```c
__int64 __fastcall CLocationWriter::GetGroupEnum(
        CLocationWriter *this,
        unsigned __int16 *a2,
        enum eMBProperty_Group *a3,
        unsigned __int16 **a4)
{
  _QWORD *v5; // rcx
  __int64 v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned __int16 *v12; // rax
  __int64 v14; // [rsp+28h] [rbp-71h]
  __int64 v15; // [rsp+28h] [rbp-71h]
  unsigned int v16; // [rsp+40h] [rbp-59h] BYREF
  int v17; // [rsp+44h] [rbp-55h] BYREF
  _DWORD v18[2]; // [rsp+48h] [rbp-51h] BYREF
  _DWORD v19[4]; // [rsp+50h] [rbp-49h] BYREF
  __int128 v20; // [rsp+60h] [rbp-39h] BYREF
  __int128 v21; // [rsp+70h] [rbp-29h]
  __int128 v22; // [rsp+80h] [rbp-19h]
  __int128 v23; // [rsp+90h] [rbp-9h] BYREF
  __int128 v24; // [rsp+A0h] [rbp+7h]
  __int128 v25; // [rsp+B0h] [rbp+17h]

  v16 = 0;
  v19[0] = 0;
  v20 = 0;
  v19[1] = 1;
  v5 = (_QWORD *)*((_QWORD *)this + 4);
  v21 = 0;
  v19[2] = 2;
  v18[0] = 4;
  v18[1] = 2;
  v23 = 0;
  v17 = 8;
  v24 = 0;
  v25 = 0;
  v22 = 0;
  v8 = v5[28];
  *(_QWORD *)&v21 = a2;
  *(_QWORD *)&v20 = v8;
  *((_QWORD *)&v20 + 1) = &v17;
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _DWORD *, _QWORD, __int128 *, unsigned int *))(*(_QWORD *)*v5 + 56LL))(
         *v5,
         0,
         3,
         v19,
         0,
         &v20,
         &v16);
  v10 = v9;
  if ( v9 == -2145318890 )
    goto LABEL_2;
  if ( v9 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _DWORD *, _QWORD, __int128 *))(***((_QWORD ***)this + 4)
                                                                                           + 32LL))(
            **((_QWORD **)this + 4),
            v16,
            2,
            v18,
            0,
            &v23);
    v10 = v11;
    if ( v11 == -2145318890 )
    {
LABEL_2:
      *(_DWORD *)a3 = 66;
      return 0;
    }
    if ( v11 >= 0 )
    {
      v12 = (unsigned __int16 *)v24;
      *(_DWORD *)a3 = *(_DWORD *)v25;
      *a4 = v12;
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v15) = v11;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\xmlwriter\\locationwriter.cpp",
        938,
        "CLocationWriter::GetGroupEnum",
        L"\nGetColumnValues failed with hr = 0x%x\n",
        v15);
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v14) = v9;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\xmlwriter\\locationwriter.cpp",
      916,
      "CLocationWriter::GetGroupEnum",
      L"\nGetRowIndexBySearch failed with hr = 0x%x\n",
      v14);
  }
  return v10;
}

```

## disassembly

```asm
0x180006e98  push    rbp
0x180006e9a  push    rbx
0x180006e9b  push    rsi
0x180006e9c  push    rdi
0x180006e9d  push    r14
0x180006e9f  lea     rbp, [rsp-37h]
0x180006ea4  sub     rsp, 0D0h
0x180006eab  mov     rax, cs:__security_cookie
0x180006eb2  xor     rax, rsp
0x180006eb5  mov     [rbp+57h+var_30], rax
0x180006eb9  xorps   xmm0, xmm0
0x180006ebc  mov     [rbp+57h+var_B0], 0
0x180006ec3  xorps   xmm1, xmm1
0x180006ec6  mov     [rbp+57h+var_A0], 0
0x180006ecd  movups  [rbp+57h+var_90], xmm1
0x180006ed1  mov     [rbp+57h+var_9C], 1
0x180006ed8  mov     r14, rcx
0x180006edb  mov     rcx, [rcx+20h]
0x180006edf  mov     rsi, r9
0x180006ee2  movups  [rbp+57h+var_80], xmm1
0x180006ee6  mov     [rbp+57h+var_98], 2
0x180006eed  lea     r9, [rbp+57h+var_A0]
0x180006ef1  mov     [rbp+57h+var_A8], 4
0x180006ef8  mov     rdi, r8
0x180006efb  mov     [rbp+57h+var_A4], 2
0x180006f02  movups  [rbp+57h+var_60], xmm0
0x180006f06  mov     [rbp+57h+var_AC], 8
0x180006f0d  movups  [rbp+57h+var_50], xmm0
0x180006f11  movups  [rbp+57h+var_40], xmm0
0x180006f15  movups  [rbp+57h+var_70], xmm1
0x180006f19  mov     rax, [rcx+0E0h]
0x180006f20  mov     qword ptr [rbp+57h+var_80], rdx
0x180006f24  lea     rdx, [rbp+57h+var_B0]
0x180006f28  mov     qword ptr [rbp+57h+var_90], rax
0x180006f2c  lea     rax, [rbp+57h+var_AC]
0x180006f30  mov     [rsp+0F0h+var_C0], rdx
0x180006f35  lea     rdx, [rbp+57h+var_90]
0x180006f39  mov     qword ptr [rbp+57h+var_90+8], rax
0x180006f3d  mov     rcx, [rcx]
0x180006f40  mov     [rsp+0F0h+var_C8], rdx
0x180006f45  xor     edx, edx
0x180006f47  mov     [rsp+0F0h+var_D0], 0
0x180006f50  mov     rax, [rcx]
0x180006f53  lea     r8d, [rdx+3]
0x180006f57  mov     rax, [rax+38h]
0x180006f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f60  mov     ebx, eax
0x180006f62  cmp     eax, 80210816h
0x180006f67  jnz     short loc_180006F76
0x180006f69  mov     dword ptr [rdi], 42h ; 'B'
0x180006f6f  xor     ebx, ebx
0x180006f71  jmp     loc_18000702B
0x180006f76  test    eax, eax
0x180006f78  jns     short loc_180006FBA
0x180006f7a  test    byte ptr cs:g_dwDebugFlags, 3
0x180006f81  jz      loc_18000702B
0x180006f87  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180006f8b  mov     r8d, 394h
0x180006f91  lea     rax, aGetrowindexbys; "\nGetRowIndexBySearch failed with hr = "...
0x180006f98  mov     rcx, cs:g_pDebug
0x180006f9f  lea     r9, aClocationwrite; "CLocationWriter::GetGroupEnum"
0x180006fa6  lea     rdx, aInetsrvIisMbXm; "inetsrv\\iis\\mb\\xmlwriter\\locationwr"...
0x180006fad  mov     [rsp+0F0h+var_D0], rax
0x180006fb2  call    cs:__imp_PuDbgPrintW
0x180006fb8  jmp     short loc_18000702B
0x180006fba  mov     rax, [r14+20h]
0x180006fbe  lea     rdx, [rbp+57h+var_60]
0x180006fc2  mov     [rsp+0F0h+var_C8], rdx
0x180006fc7  lea     r9, [rbp+57h+var_A8]
0x180006fcb  mov     edx, [rbp+57h+var_B0]
0x180006fce  mov     r8d, 2
0x180006fd4  mov     [rsp+0F0h+var_D0], 0
0x180006fdd  mov     rcx, [rax]
0x180006fe0  mov     rax, [rcx]
0x180006fe3  mov     rax, [rax+20h]
0x180006fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fec  mov     ebx, eax
0x180006fee  cmp     eax, 80210816h
0x180006ff3  jz      loc_180006F69
0x180006ff9  test    eax, eax
0x180006ffb  jns     short loc_18000701C
0x180006ffd  test    byte ptr cs:g_dwDebugFlags, 3
0x180007004  jz      short loc_18000702B
0x180007006  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18000700a  mov     r8d, 3AAh
0x180007010  lea     rax, aGetcolumnvalue; "\nGetColumnValues failed with hr = 0x%x"...
0x180007017  jmp     loc_180006F98
0x18000701c  mov     rax, qword ptr [rbp+57h+var_40]
0x180007020  mov     ecx, [rax]
0x180007022  mov     rax, qword ptr [rbp+57h+var_50]
0x180007026  mov     [rdi], ecx
0x180007028  mov     [rsi], rax
0x18000702b  mov     eax, ebx
0x18000702d  mov     rcx, [rbp+57h+var_30]
0x180007031  xor     rcx, rsp; StackCookie
0x180007034  call    __security_check_cookie
0x180007039  add     rsp, 0D0h
0x180007040  pop     r14
0x180007042  pop     rdi
0x180007043  pop     rsi
0x180007044  pop     rbx
0x180007045  pop     rbp
0x180007046  retn
```
