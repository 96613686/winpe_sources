# SerializeClassDeclOfInstanceToBinary

- ea: `0x18002a160`
- end: `0x18002a407`
- name: `SerializeClassDeclOfInstanceToBinary`
- size: `679`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002a160`
- `0x18002a4bc`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x1800279b0`
- `0x18002a160`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002a1cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002a1e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002a3ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002a1cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002a1e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002a3ac`

## string_xrefs

- `0x18002a1bf`: `mpunits.dll`
- `0x18002a1db`: `mpunits.dll`
- `0x18002a3a1`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall SerializeClassDeclOfInstanceToBinary(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rax
  const wchar_t *v6; // rbx
  HMODULE ModuleHandleA; // rax
  const wchar_t *v8; // r8
  __int64 result; // rax
  unsigned __int8 v10; // cl
  __int64 v11; // rcx
  ULONGLONG v12; // rdx
  __int64 v13; // r9
  __int64 v14; // r8
  unsigned int v15; // ebx
  unsigned int v16; // r12d
  __int64 v17; // rax
  __int64 i; // r15
  HMODULE v19; // rax
  int v20; // [rsp+50h] [rbp-9h] BYREF
  const wchar_t *v21; // [rsp+58h] [rbp-1h] BYREF
  _OWORD v22[2]; // [rsp+60h] [rbp+7h] BYREF
  __int64 v23; // [rsp+80h] [rbp+27h]

  if ( !a3[1] )
  {
    v5 = *a3;
    v21 = 0;
    if ( !v5 || (*(unsigned int (__fastcall **)(_QWORD *, const wchar_t **))(v5 + 32))(a3, &v21) )
    {
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      v8 = L"UnknownClass";
    }
    else
    {
      v6 = v21;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      v8 = v6;
    }
    Intlstr_FormatString_FormatMessage(ModuleHandleA, 2104, v8);
    MI_ReportErrorDetails_ForCustomError(23, (int)L"BinaryLogger", 0, 0);
    return 4;
  }
  v10 = *(_BYTE *)(a1 + 81);
  *(_BYTE *)(a1 + 81) = v10 + 1;
  if ( v10 > 0xFu )
    return 7;
  v11 = a3[1];
  v12 = 0;
  v13 = a3[2];
  v14 = a3[3];
  if ( *(_QWORD *)(v11 + 96) != -1 )
    v12 = v11;
  result = BinaryLogWriter_OnSerializeClassDecl(v11, v12, v14, v13, (unsigned int *)a1);
  v15 = result;
  if ( !(_DWORD)result )
  {
    v23 = 0;
    v16 = 0;
    LODWORD(v21) = 0;
    v20 = 0;
    v17 = a3[1];
    memset(v22, 0, sizeof(v22));
    if ( *(_DWORD *)(v17 + 40) )
    {
      do
      {
        if ( !*a3 )
        {
          v15 = 4;
LABEL_28:
          v19 = GetModuleHandleA("mpunits.dll");
          Intlstr_FormatString_FormatMessage(v19, 2013, v16);
          MI_ReportErrorDetails_ForCustomError(20, (int)L"BinaryLogger", 0, 0);
          return v15;
        }
        v15 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, _OWORD *, const wchar_t **, int *))(*a3 + 96LL))(
                a3,
                v16,
                0,
                v22,
                &v21,
                &v20);
        if ( v15 )
          goto LABEL_28;
        if ( (v20 & 0x20000000) == 0 )
        {
          if ( (unsigned int)((_DWORD)v21 - 14) <= 1 )
          {
            result = SerializeClassDeclOfInstanceToBinary(
                       a1,
                       4,
                       *(_QWORD *)&v22[0],
                       BinaryLogWriter_OnSerializeClassDecl);
            v15 = result;
            if ( (_DWORD)result )
              return result;
          }
          else if ( (unsigned int)((_DWORD)v21 - 30) <= 1 )
          {
            for ( i = 0; (unsigned int)i < DWORD2(v22[0]); i = (unsigned int)(i + 1) )
            {
              result = SerializeClassDeclOfInstanceToBinary(
                         a1,
                         4,
                         *(_QWORD *)(*(_QWORD *)&v22[0] + 8 * i),
                         BinaryLogWriter_OnSerializeClassDecl);
              v15 = result;
              if ( (_DWORD)result )
                return result;
            }
          }
        }
        ++v16;
      }
      while ( v16 < *(_DWORD *)(a3[1] + 40LL) );
    }
    --*(_BYTE *)(a1 + 81);
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x18002a160  mov     [rsp-8+arg_8], rbx
0x18002a165  push    rbp
0x18002a166  push    rsi
0x18002a167  push    rdi
0x18002a168  push    r12
0x18002a16a  push    r15
0x18002a16c  lea     rbp, [rsp-37h]
0x18002a171  sub     rsp, 90h
0x18002a178  mov     rax, cs:__security_cookie
0x18002a17f  xor     rax, rsp
0x18002a182  mov     [rbp+57h+var_28], rax
0x18002a186  cmp     qword ptr [r8+8], 0
0x18002a18b  mov     rdi, r8
0x18002a18e  mov     rsi, rcx
0x18002a191  jnz     loc_18002A247
0x18002a197  mov     rax, [r8]
0x18002a19a  mov     [rbp+57h+var_58], 0
0x18002a1a2  test    rax, rax
0x18002a1a5  jz      short loc_18002A1D8
0x18002a1a7  mov     rax, [rax+20h]
0x18002a1ab  lea     rdx, [rbp+57h+var_58]
0x18002a1af  mov     rcx, r8
0x18002a1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1b7  test    eax, eax
0x18002a1b9  jnz     short loc_18002A1D8
0x18002a1bb  mov     rbx, [rbp+57h+var_58]
0x18002a1bf  lea     rcx, ModuleName; "mpunits.dll"
0x18002a1c6  xorps   xmm0, xmm0
0x18002a1c9  movups  [rbp+57h+var_70], xmm0
0x18002a1cd  call    cs:__imp_GetModuleHandleA
0x18002a1d3  mov     r8, rbx
0x18002a1d6  jmp     short loc_18002A1F3
0x18002a1d8  xorps   xmm0, xmm0
0x18002a1db  lea     rcx, ModuleName; "mpunits.dll"
0x18002a1e2  movups  [rbp+57h+var_70], xmm0
0x18002a1e6  call    cs:__imp_GetModuleHandleA
0x18002a1ec  lea     r8, aUnknownclass; "UnknownClass"
0x18002a1f3  mov     edx, 838h
0x18002a1f8  mov     rcx, rax
0x18002a1fb  call    _Intlstr_FormatString_FormatMessage
0x18002a200  mov     qword ptr [rbp+57h+var_70], rax
0x18002a204  lea     r9, [rbp+57h+var_70]
0x18002a208  mov     byte ptr [rbp+57h+var_70+8], 1
0x18002a20c  lea     rdx, aBinarylogger; "BinaryLogger"
0x18002a213  movaps  xmm0, [rbp+57h+var_70]
0x18002a217  mov     r8d, 5
0x18002a21d  mov     [rsp+0B0h+var_88], 0; __int64
0x18002a226  movdqa  [rbp+57h+var_70], xmm0
0x18002a22b  mov     [rsp+0B0h+var_90], 0; __int64
0x18002a234  lea     ecx, [r8+12h]; int
0x18002a238  call    MI_ReportErrorDetails_ForCustomError
0x18002a23d  mov     eax, 4
0x18002a242  jmp     loc_18002A376
0x18002a247  mov     cl, [rcx+51h]
0x18002a24a  lea     eax, [rcx+1]
0x18002a24d  mov     [rsi+51h], al
0x18002a250  cmp     cl, 0Fh
0x18002a253  jbe     short loc_18002A25F
0x18002a255  mov     eax, 7
0x18002a25a  jmp     loc_18002A376
0x18002a25f  mov     rcx, [r8+8]
0x18002a263  xor     edx, edx
0x18002a265  mov     r9, [r8+10h]
0x18002a269  mov     r8, [r8+18h]
0x18002a26d  mov     [rsp+0B0h+var_90], rsi
0x18002a272  cmp     qword ptr [rcx+60h], 0FFFFFFFFFFFFFFFFh
0x18002a277  cmovnz  rdx, rcx
0x18002a27b  call    BinaryLogWriter_OnSerializeClassDecl
0x18002a280  mov     ebx, eax
0x18002a282  test    eax, eax
0x18002a284  jnz     loc_18002A376
0x18002a28a  xor     eax, eax
0x18002a28c  xorps   xmm0, xmm0
0x18002a28f  mov     [rbp+57h+var_30], rax
0x18002a293  xor     r12d, r12d
0x18002a296  mov     dword ptr [rbp+57h+var_58], eax
0x18002a299  mov     [rbp+57h+var_60], eax
0x18002a29c  mov     rax, [rdi+8]
0x18002a2a0  movups  [rbp+57h+var_50], xmm0
0x18002a2a4  movups  [rbp+57h+var_40], xmm0
0x18002a2a8  cmp     [rax+28h], r12d
0x18002a2ac  jbe     loc_18002A371
0x18002a2b2  mov     rax, [rdi]
0x18002a2b5  test    rax, rax
0x18002a2b8  jz      loc_18002A399
0x18002a2be  mov     rax, [rax+60h]
0x18002a2c2  lea     rcx, [rbp+57h+var_60]
0x18002a2c6  mov     [rsp+0B0h+var_88], rcx
0x18002a2cb  lea     r9, [rbp+57h+var_50]
0x18002a2cf  lea     rcx, [rbp+57h+var_58]
0x18002a2d3  xor     r8d, r8d
0x18002a2d6  mov     [rsp+0B0h+var_90], rcx
0x18002a2db  mov     edx, r12d
0x18002a2de  mov     rcx, rdi
0x18002a2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2e6  mov     ebx, eax
0x18002a2e8  test    eax, eax
0x18002a2ea  jnz     loc_18002A39E
0x18002a2f0  test    [rbp+57h+var_60], 20000000h
0x18002a2f7  jnz     short loc_18002A360
0x18002a2f9  mov     ecx, dword ptr [rbp+57h+var_58]
0x18002a2fc  lea     eax, [rcx-0Eh]
0x18002a2ff  cmp     eax, 1
0x18002a302  jbe     short loc_18002A342
0x18002a304  lea     eax, [rcx-1Eh]
0x18002a307  cmp     eax, 1
0x18002a30a  ja      short loc_18002A360
0x18002a30c  xor     r15d, r15d
0x18002a30f  cmp     dword ptr [rbp+57h+var_50+8], r15d
0x18002a313  jbe     short loc_18002A360
0x18002a315  mov     r8, qword ptr [rbp+57h+var_50]
0x18002a319  lea     r9, BinaryLogWriter_OnSerializeClassDecl
0x18002a320  mov     edx, 4
0x18002a325  mov     rcx, rsi
0x18002a328  mov     r8, [r8+r15*8]
0x18002a32c  call    SerializeClassDeclOfInstanceToBinary
0x18002a331  mov     ebx, eax
0x18002a333  test    eax, eax
0x18002a335  jnz     short loc_18002A376
0x18002a337  inc     r15d
0x18002a33a  cmp     r15d, dword ptr [rbp+57h+var_50+8]
0x18002a33e  jb      short loc_18002A315
0x18002a340  jmp     short loc_18002A360
0x18002a342  mov     r8, qword ptr [rbp+57h+var_50]
0x18002a346  lea     r9, BinaryLogWriter_OnSerializeClassDecl
0x18002a34d  mov     edx, 4
0x18002a352  mov     rcx, rsi
0x18002a355  call    SerializeClassDeclOfInstanceToBinary
0x18002a35a  mov     ebx, eax
0x18002a35c  test    eax, eax
0x18002a35e  jnz     short loc_18002A376
0x18002a360  mov     rax, [rdi+8]
0x18002a364  inc     r12d
0x18002a367  cmp     r12d, [rax+28h]
0x18002a36b  jb      loc_18002A2B2
0x18002a371  dec     byte ptr [rsi+51h]
0x18002a374  mov     eax, ebx
0x18002a376  mov     rcx, [rbp+57h+var_28]
0x18002a37a  xor     rcx, rsp; StackCookie
0x18002a37d  call    __security_check_cookie
0x18002a382  mov     rbx, [rsp+0B0h+arg_8]
0x18002a38a  add     rsp, 90h
0x18002a391  pop     r15
0x18002a393  pop     r12
0x18002a395  pop     rdi
0x18002a396  pop     rsi
0x18002a397  pop     rbp
0x18002a398  retn
0x18002a399  mov     ebx, 4
0x18002a39e  xorps   xmm0, xmm0
0x18002a3a1  lea     rcx, ModuleName; "mpunits.dll"
0x18002a3a8  movups  [rbp+57h+var_70], xmm0
0x18002a3ac  call    cs:__imp_GetModuleHandleA
0x18002a3b2  mov     r9d, ebx
0x18002a3b5  mov     r8d, r12d
0x18002a3b8  mov     rcx, rax
0x18002a3bb  mov     edx, 7DDh
0x18002a3c0  call    _Intlstr_FormatString_FormatMessage
0x18002a3c5  mov     qword ptr [rbp+57h+var_70], rax
0x18002a3c9  lea     r9, [rbp+57h+var_70]
0x18002a3cd  mov     byte ptr [rbp+57h+var_70+8], 1
0x18002a3d1  lea     rdx, aBinarylogger; "BinaryLogger"
0x18002a3d8  movaps  xmm0, [rbp+57h+var_70]
0x18002a3dc  mov     r8d, 6
0x18002a3e2  mov     [rsp+0B0h+var_88], 0; __int64
0x18002a3eb  movdqa  [rbp+57h+var_70], xmm0
0x18002a3f0  mov     [rsp+0B0h+var_90], 0; __int64
0x18002a3f9  lea     ecx, [r8+0Eh]; int
0x18002a3fd  call    MI_ReportErrorDetails_ForCustomError
0x18002a402  jmp     loc_18002A374
```
