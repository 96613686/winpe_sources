# GenericCache_FetchContext

- ea: `0x18003dbe0`
- end: `0x18003dcf8`
- name: `GenericCache_FetchContext`
- size: `280`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003e7d0`
- `0x18003e8f0`
- `0x18003e980`
- `0x18003ecc0`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18003dbe0`
- `0x18003f000`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003dc9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003dc9e`

## string_xrefs

- `0x18003dc90`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall GenericCache_FetchContext(__int64 a1, unsigned __int16 *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // r9
  unsigned __int16 v9; // dx
  unsigned __int16 *v10; // r8
  unsigned __int16 v11; // cx
  unsigned int v12; // edi
  __int64 v13; // rbx
  HMODULE ModuleHandleA; // rax
  __int128 v16; // [rsp+30h] [rbp-29h] BYREF
  __int128 v17; // [rsp+40h] [rbp-19h]
  __int64 v18; // [rsp+50h] [rbp-9h] BYREF
  __int128 v19; // [rsp+58h] [rbp-1h]
  unsigned __int128 v20; // [rsp+68h] [rbp+Fh]
  __int128 v21; // [rsp+78h] [rbp+1Fh]
  __int64 v22; // [rsp+88h] [rbp+2Fh]

  v18 = 0;
  v20 = __PAIR128__((unsigned __int64)a2, 0);
  v19 = 0;
  v22 = 0;
  v21 = 0;
  v8 = 2166136261LL;
  v16 = 0;
  v9 = *a2;
  if ( v9 )
  {
    v10 = a2;
    do
    {
      v11 = v9 + 32;
      ++v10;
      if ( (unsigned __int16)(v9 - 65) > 0x19u )
        v11 = v9;
      v9 = *v10;
      v8 = 16777619 * (v8 ^ v11);
    }
    while ( *v10 );
  }
  *(_QWORD *)&v20 = v8;
  *(_QWORD *)&v16 = a4;
  *((_QWORD *)&v16 + 1) = a3;
  v12 = ThreadSafeHashMap_Fetch(
          a1,
          (__int64)&v18,
          (__int64 (__fastcall *)(__int64, _QWORD *))FetchContextAdapter,
          (__int64)&v16);
  if ( v12 == 6 )
  {
    v13 = *(_QWORD *)(a1 + 128);
    v17 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&v17 = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2134, v13);
    BYTE8(v17) = 1;
    MI_ReportErrorDetails_ForCustomError(6, (int)L"MI", 0, 0);
  }
  return v12;
}

```

## disassembly

```asm
0x18003dbe0  push    rbp
0x18003dbe2  push    rbx
0x18003dbe3  push    rsi
0x18003dbe4  push    rdi
0x18003dbe5  push    r14
0x18003dbe7  lea     rbp, [rsp-37h]
0x18003dbec  sub     rsp, 90h
0x18003dbf3  xorps   xmm1, xmm1
0x18003dbf6  xor     r14d, r14d
0x18003dbf9  xorps   xmm0, xmm0
0x18003dbfc  mov     [rbp+57h+var_60], r14
0x18003dc00  xor     eax, eax
0x18003dc02  mov     rsi, rdx
0x18003dc05  movups  [rbp+57h+var_48], xmm1
0x18003dc09  mov     qword ptr [rbp+57h+var_48+8], rdx
0x18003dc0d  mov     r10, r9
0x18003dc10  movups  [rbp+57h+var_58], xmm0
0x18003dc14  mov     [rbp+57h+var_28], rax
0x18003dc18  mov     r11, r8
0x18003dc1b  movups  [rbp+57h+var_38], xmm1
0x18003dc1f  mov     rbx, rcx
0x18003dc22  mov     r9d, 811C9DC5h
0x18003dc28  movups  [rbp+57h+var_80], xmm0
0x18003dc2c  movzx   edx, word ptr [rdx]
0x18003dc2f  test    dx, dx
0x18003dc32  jz      short loc_18003DC5F
0x18003dc34  mov     r8, rsi
0x18003dc37  lea     eax, [rdx-41h]
0x18003dc3a  cmp     ax, 19h
0x18003dc3e  lea     ecx, [rdx+20h]
0x18003dc41  lea     r8, [r8+2]
0x18003dc45  cmova   cx, dx
0x18003dc49  movzx   edx, word ptr [r8]
0x18003dc4d  movzx   eax, cx
0x18003dc50  xor     rax, r9
0x18003dc53  imul    r9, rax, 1000193h
0x18003dc5a  test    dx, dx
0x18003dc5d  jnz     short loc_18003DC37
0x18003dc5f  mov     qword ptr [rbp+57h+var_48], r9
0x18003dc63  lea     r8, FetchContextAdapter
0x18003dc6a  lea     r9, [rbp+57h+var_80]
0x18003dc6e  mov     qword ptr [rbp+57h+var_80], r10
0x18003dc72  lea     rdx, [rbp+57h+var_60]
0x18003dc76  mov     qword ptr [rbp+57h+var_80+8], r11
0x18003dc7a  mov     rcx, rbx
0x18003dc7d  call    ThreadSafeHashMap_Fetch
0x18003dc82  mov     edi, eax
0x18003dc84  cmp     eax, 6
0x18003dc87  jnz     short loc_18003DCE8
0x18003dc89  mov     rbx, [rbx+80h]
0x18003dc90  lea     rcx, ModuleName; "mpunits.dll"
0x18003dc97  xorps   xmm0, xmm0
0x18003dc9a  movups  [rbp+57h+var_70], xmm0
0x18003dc9e  call    cs:__imp_GetModuleHandleA
0x18003dca4  mov     r9, rsi
0x18003dca7  mov     r8, rbx
0x18003dcaa  mov     rcx, rax
0x18003dcad  mov     edx, 856h
0x18003dcb2  call    _Intlstr_FormatString_FormatMessage
0x18003dcb7  mov     qword ptr [rbp+57h+var_70], rax
0x18003dcbb  lea     r9, [rbp+57h+var_70]
0x18003dcbf  mov     byte ptr [rbp+57h+var_70+8], 1
0x18003dcc3  lea     r8d, [rdi+7]
0x18003dcc7  movaps  xmm0, [rbp+57h+var_70]
0x18003dccb  lea     rdx, aMi; "MI"
0x18003dcd2  mov     [rsp+0B0h+var_88], r14; __int64
0x18003dcd7  mov     ecx, edi; int
0x18003dcd9  movdqa  [rbp+57h+var_70], xmm0
0x18003dcde  mov     [rsp+0B0h+var_90], r14; __int64
0x18003dce3  call    MI_ReportErrorDetails_ForCustomError
0x18003dce8  mov     eax, edi
0x18003dcea  add     rsp, 90h
0x18003dcf1  pop     r14
0x18003dcf3  pop     rdi
0x18003dcf4  pop     rsi
0x18003dcf5  pop     rbx
0x18003dcf6  pop     rbp
0x18003dcf7  retn
```
