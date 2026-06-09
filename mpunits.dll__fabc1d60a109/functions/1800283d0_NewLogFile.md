# NewLogFile

- ea: `0x1800283d0`
- end: `0x1800286c8`
- name: `NewLogFile`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180027f20`

## callees

- `0x180006e64`
- `0x1800077a0`
- `0x180007800`
- `0x180007920`
- `0x180007ad0`
- `0x18000af38`
- `0x1800283d0`
- `0x180028948`
- `0x180042c5c`
- `0x180043638`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800284ed`
- `msvcrt!swprintf_s` at `0x1800284ed`
- `msvcrt!malloc` at `0x18002846f`
- `msvcrt!malloc` at `0x18002846f`
- `msvcrt!_close` at `0x18002842c`
- `msvcrt!_close` at `0x18002842c`
- `msvcrt!free` at `0x18002862c`
- `msvcrt!free` at `0x180028698`
- `msvcrt!free` at `0x18002862c`
- `msvcrt!free` at `0x180028698`
- `msvcrt!wcscpy_s` at `0x18002848f`
- `msvcrt!wcscpy_s` at `0x18002848f`
- `msvcrt!wcscat_s` at `0x18002850e`
- `msvcrt!wcscat_s` at `0x180028524`
- `msvcrt!wcscat_s` at `0x18002853d`
- `msvcrt!wcscat_s` at `0x18002850e`
- `msvcrt!wcscat_s` at `0x180028524`
- `msvcrt!wcscat_s` at `0x18002853d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002863d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002863d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180028682`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180028682`

## string_xrefs

- `0x180028636`: `mpunits.dll`
- `0x18002857c`: `BinaryLogger.OpenLogFile`

## pseudocode

```c
__int64 __fastcall NewLogFile(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  errno_t v5; // edi
  wchar_t *v6; // rsi
  unsigned int v7; // r14d
  int v8; // eax
  rsize_t v9; // r15
  wchar_t *v10; // rax
  unsigned int v11; // r15d
  __int64 v12; // r15
  int v13; // eax
  __int128 v14; // xmm1
  void *v15; // rcx
  HMODULE ModuleHandleA; // rax
  void *v18; // rbx
  MI_Instance *extendedError; // [rsp+50h] [rbp-59h] BYREF
  void *v20; // [rsp+58h] [rbp-51h] BYREF
  __int128 v21; // [rsp+60h] [rbp-49h] BYREF
  __int128 v22; // [rsp+70h] [rbp-39h]
  int v23; // [rsp+80h] [rbp-29h]
  const wchar_t *v24; // [rsp+88h] [rbp-21h] BYREF
  wchar_t Buffer[20]; // [rsp+90h] [rbp-19h] BYREF

  v23 = 0;
  v2 = -1;
  extendedError = 0;
  v5 = 1;
  v6 = 0;
  v7 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  if ( *(_DWORD *)a2 != -1 )
  {
    v8 = _close(*(_DWORD *)a2);
    *(_DWORD *)a2 = -1;
    v5 = v8;
    if ( v8 )
      goto LABEL_16;
    trace_BinLogWriter_ClosedLogFile();
    v5 = 1;
  }
  if ( (unsigned int)CPU_GetLocalTimestamp(&v21) )
    goto LABEL_16;
  do
    ++v2;
  while ( *(_WORD *)(*(_QWORD *)(a2 + 96) + 2 * v2) );
  v9 = v2 + 24;
  v10 = (wchar_t *)malloc(2 * v9);
  v6 = v10;
  if ( !v10 )
    goto LABEL_16;
  *v10 = 0;
  v5 = wcscpy_s(v10, v9, *(const wchar_t **)(a2 + 96));
  if ( v5 )
    goto LABEL_16;
  if ( *(_QWORD *)(a2 + 64) )
    goto LABEL_13;
  if ( (unsigned int)swprintf_s(
                       Buffer,
                       0x12u,
                       L"%04d%02d%02d%02d%02d%02d%03d",
                       DWORD1(v21),
                       DWORD2(v21),
                       HIDWORD(v21),
                       (_DWORD)v22,
                       DWORD1(v22),
                       DWORD2(v22),
                       HIDWORD(v22) / 0x3E8) <= 0x12 )
  {
    v5 = wcscat_s(v6, v9, L"_");
    if ( !v5 )
    {
      v5 = wcscat_s(v6, v9, Buffer);
      if ( !v5 )
      {
LABEL_13:
        v5 = wcscat_s(v6, v9, L".bmil");
        if ( !v5 )
        {
          v7 = ((__int64 (__fastcall *)(void **))ExecutionContext_ImpersonateIdentity)(&v20);
          if ( v7 )
          {
            v5 = 5;
          }
          else
          {
            v12 = EnableErrorDetails();
            v7 = BinaryLogWriter_Core_NewFile((int *)a2, v6);
            if ( !v7 )
            {
              RevertErrorDetails(v12);
              v13 = v23;
              v14 = v22;
              v15 = v20;
              *(_OWORD *)(a2 + 124) = v21;
              *(_QWORD *)(a2 + 160) = a1;
              *(_OWORD *)(a2 + 140) = v14;
              *(_DWORD *)(a2 + 156) = v13;
              ExecutionContext_RevertIdentity(v15);
              free(v6);
              return 0;
            }
            CatchErrorDetails(v12, &extendedError);
            ExecutionContext_RevertIdentity(v20);
          }
        }
      }
    }
LABEL_16:
    v11 = 1;
    goto LABEL_17;
  }
  v11 = ++v5;
LABEL_17:
  if ( extendedError )
  {
    v24 = L"BinaryLogger.OpenLogFile";
    ((void (__fastcall *)(MI_Instance *, __int64, const wchar_t **))extendedError->ft->SetElementAt)(
      extendedError,
      3,
      &v24);
  }
  else
  {
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v18 = (void *)Intlstr_FormatString_FormatMessage(ModuleHandleA, 2126, v6);
    CreateOMIError_shared((int)v18, v5, (int)L"ERRNO", v11, (__int64)&OMI_Error_rtti, &extendedError);
    LocalFree(v18);
  }
  ReportErrorDetails(extendedError);
  extendedError = 0;
  free(v6);
  if ( !v7 )
    return v11;
  return v7;
}

```

## disassembly

```asm
0x1800283d0  push    rbp
0x1800283d2  push    rbx
0x1800283d3  push    rsi
0x1800283d4  push    rdi
0x1800283d5  push    r12
0x1800283d7  push    r13
0x1800283d9  push    r14
0x1800283db  push    r15
0x1800283dd  lea     rbp, [rsp-1Fh]
0x1800283e2  sub     rsp, 0C8h
0x1800283e9  mov     rax, cs:__security_cookie
0x1800283f0  xor     rax, rsp
0x1800283f3  mov     [rbp+57h+var_48], rax
0x1800283f7  xor     r13d, r13d
0x1800283fa  xor     eax, eax
0x1800283fc  xorps   xmm0, xmm0
0x1800283ff  mov     [rbp+57h+var_80], eax
0x180028402  or      r15, 0FFFFFFFFFFFFFFFFh
0x180028406  mov     [rbp+57h+var_B0], r13
0x18002840a  mov     rbx, rdx
0x18002840d  mov     r12, rcx
0x180028410  lea     edi, [rax+1]
0x180028413  mov     esi, r13d
0x180028416  mov     r14d, r13d
0x180028419  mov     [rbp+57h+var_A8], r13
0x18002841d  movups  [rbp+57h+var_A0], xmm0
0x180028421  movups  [rbp+57h+var_90], xmm0
0x180028425  cmp     [rdx], r15d
0x180028428  jz      short loc_180028448
0x18002842a  mov     ecx, [rdx]; FileHandle
0x18002842c  call    cs:__imp__close
0x180028432  mov     [rbx], r15d
0x180028435  mov     edi, eax
0x180028437  test    eax, eax
0x180028439  jnz     loc_180028569
0x18002843f  call    trace_BinLogWriter_ClosedLogFile
0x180028444  lea     edi, [r13+1]
0x180028448  lea     rcx, [rbp+57h+var_A0]
0x18002844c  call    CPU_GetLocalTimestamp
0x180028451  test    eax, eax
0x180028453  jnz     loc_180028569
0x180028459  mov     rax, [rbx+60h]
0x18002845d  inc     r15
0x180028460  cmp     [rax+r15*2], r13w
0x180028465  jnz     short loc_18002845D
0x180028467  add     r15, 18h
0x18002846b  lea     rcx, [r15+r15]; Size
0x18002846f  call    cs:__imp_malloc
0x180028475  mov     rsi, rax
0x180028478  test    rax, rax
0x18002847b  jz      loc_180028569
0x180028481  mov     [rax], r13w
0x180028485  mov     rdx, r15; SizeInWords
0x180028488  mov     r8, [rbx+60h]; Source
0x18002848c  mov     rcx, rax; Destination
0x18002848f  call    cs:__imp_wcscpy_s
0x180028495  mov     edi, eax
0x180028497  test    eax, eax
0x180028499  jnz     loc_180028569
0x18002849f  cmp     [rbx+40h], r13
0x1800284a3  jnz     loc_180028530
0x1800284a9  mov     r9d, dword ptr [rbp+57h+var_A0+4]
0x1800284ad  lea     r8, a04d02d02d02d02; "%04d%02d%02d%02d%02d%02d%03d"
0x1800284b4  mov     eax, 10624DD3h
0x1800284b9  lea     rcx, [rbp+57h+Buffer]; Buffer
0x1800284bd  mul     dword ptr [rbp+57h+var_90+0Ch]
0x1800284c0  mov     eax, dword ptr [rbp+57h+var_90+8]
0x1800284c3  shr     edx, 6
0x1800284c6  mov     [rsp+100h+var_B8], edx
0x1800284ca  lea     edx, [rdi+12h]; BufferCount
0x1800284cd  mov     [rsp+100h+var_C0], eax
0x1800284d1  mov     eax, dword ptr [rbp+57h+var_90+4]
0x1800284d4  mov     [rsp+100h+var_C8], eax
0x1800284d8  mov     eax, dword ptr [rbp+57h+var_90]
0x1800284db  mov     [rsp+100h+var_D0], eax
0x1800284df  mov     eax, dword ptr [rbp+57h+var_A0+0Ch]
0x1800284e2  mov     dword ptr [rsp+100h+extendedError], eax
0x1800284e6  mov     eax, dword ptr [rbp+57h+var_A0+8]
0x1800284e9  mov     dword ptr [rsp+100h+var_E0], eax
0x1800284ed  call    cs:__imp_swprintf_s
0x1800284f3  cmp     eax, 12h
0x1800284f6  jbe     short loc_180028501
0x1800284f8  lea     r15d, [rdi+1]
0x1800284fc  mov     edi, r15d
0x1800284ff  jmp     short loc_18002856F
0x180028501  lea     r8, asc_18005E61C; "_"
0x180028508  mov     rdx, r15; SizeInWords
0x18002850b  mov     rcx, rsi; Destination
0x18002850e  call    cs:__imp_wcscat_s
0x180028514  mov     edi, eax
0x180028516  test    eax, eax
0x180028518  jnz     short loc_180028569
0x18002851a  lea     r8, [rbp+57h+Buffer]; Source
0x18002851e  mov     rdx, r15; SizeInWords
0x180028521  mov     rcx, rsi; Destination
0x180028524  call    cs:__imp_wcscat_s
0x18002852a  mov     edi, eax
0x18002852c  test    eax, eax
0x18002852e  jnz     short loc_180028569
0x180028530  lea     r8, aBmil; ".bmil"
0x180028537  mov     rdx, r15; SizeInWords
0x18002853a  mov     rcx, rsi; Destination
0x18002853d  call    cs:__imp_wcscat_s
0x180028543  mov     edi, eax
0x180028545  test    eax, eax
0x180028547  jnz     short loc_180028569
0x180028549  mov     rax, cs:off_180047C30
0x180028550  lea     rcx, [rbp+57h+var_A8]
0x180028554  mov     rax, [rax+50h]
0x180028558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002855d  mov     r14d, eax
0x180028560  test    eax, eax
0x180028562  jz      short loc_1800285AE
0x180028564  mov     edi, 5
0x180028569  mov     r15d, 1
0x18002856f  mov     rcx, [rbp+57h+var_B0]
0x180028573  test    rcx, rcx
0x180028576  jz      loc_180028636
0x18002857c  lea     rax, aBinaryloggerOp; "BinaryLogger.OpenLogFile"
0x180028583  mov     dword ptr [rsp+100h+var_E0], 40000000h
0x18002858b  mov     [rbp+57h+var_78], rax
0x18002858f  lea     r8, [rbp+57h+var_78]
0x180028593  mov     rax, [rcx]
0x180028596  mov     r9d, 0Dh
0x18002859c  mov     rax, [rax+50h]
0x1800285a0  lea     edx, [r9-0Ah]
0x1800285a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285a9  jmp     loc_180028688
0x1800285ae  call    EnableErrorDetails
0x1800285b3  mov     rdx, rsi; FileName
0x1800285b6  mov     rcx, rbx; FileHandle
0x1800285b9  mov     r15, rax
0x1800285bc  call    BinaryLogWriter_Core_NewFile
0x1800285c1  mov     r14d, eax
0x1800285c4  mov     rcx, r15
0x1800285c7  test    eax, eax
0x1800285c9  jz      short loc_1800285ED
0x1800285cb  lea     rdx, [rbp+57h+var_B0]
0x1800285cf  call    CatchErrorDetails
0x1800285d4  mov     rax, cs:off_180047C30
0x1800285db  mov     rcx, [rbp+57h+var_A8]
0x1800285df  mov     rax, [rax+58h]
0x1800285e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285e8  jmp     loc_180028569
0x1800285ed  call    RevertErrorDetails
0x1800285f2  movups  xmm0, [rbp+57h+var_A0]
0x1800285f6  mov     eax, [rbp+57h+var_80]
0x1800285f9  movups  xmm1, [rbp+57h+var_90]
0x1800285fd  mov     rcx, [rbp+57h+var_A8]
0x180028601  movups  xmmword ptr [rbx+7Ch], xmm0
0x180028605  mov     [rbx+0A0h], r12
0x18002860c  movups  xmmword ptr [rbx+8Ch], xmm1
0x180028613  mov     [rbx+9Ch], eax
0x180028619  mov     rax, cs:off_180047C30
0x180028620  mov     rax, [rax+58h]
0x180028624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028629  mov     rcx, rsi; Block
0x18002862c  call    cs:__imp_free
0x180028632  xor     eax, eax
0x180028634  jmp     short loc_1800286A8
0x180028636  lea     rcx, ModuleName; "mpunits.dll"
0x18002863d  call    cs:__imp_GetModuleHandleA
0x180028643  mov     r8, rsi
0x180028646  mov     edx, 84Eh
0x18002864b  mov     rcx, rax
0x18002864e  call    _Intlstr_FormatString_FormatMessage
0x180028653  mov     rbx, rax
0x180028656  lea     r8, aErrno; "ERRNO"
0x18002865d  lea     rax, [rbp+57h+var_B0]
0x180028661  mov     r9d, r15d; int
0x180028664  mov     [rsp+100h+extendedError], rax; extendedError
0x180028669  mov     edx, edi; int
0x18002866b  lea     rax, OMI_Error_rtti
0x180028672  mov     rcx, rbx; int
0x180028675  mov     [rsp+100h+var_E0], rax; __int64
0x18002867a  call    CreateOMIError_shared
0x18002867f  mov     rcx, rbx; hMem
0x180028682  call    cs:__imp_LocalFree
0x180028688  mov     rcx, [rbp+57h+var_B0]; lpTlsValue
0x18002868c  call    ReportErrorDetails
0x180028691  mov     rcx, rsi; Block
0x180028694  mov     [rbp+57h+var_B0], r13
0x180028698  call    cs:__imp_free
0x18002869e  test    r14d, r14d
0x1800286a1  cmovz   r14d, r15d
0x1800286a5  mov     eax, r14d
0x1800286a8  mov     rcx, [rbp+57h+var_48]
0x1800286ac  xor     rcx, rsp; StackCookie
0x1800286af  call    __security_check_cookie
0x1800286b4  add     rsp, 0C8h
0x1800286bb  pop     r15
0x1800286bd  pop     r14
0x1800286bf  pop     r13
0x1800286c1  pop     r12
0x1800286c3  pop     rdi
0x1800286c4  pop     rsi
0x1800286c5  pop     rbx
0x1800286c6  pop     rbp
0x1800286c7  retn
```
