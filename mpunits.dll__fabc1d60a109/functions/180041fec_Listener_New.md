# Listener_New

- ea: `0x180041fec`
- end: `0x18004228a`
- name: `Listener_New`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180041dc0`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x180007ea0`
- `0x180041340`
- `0x180041fb0`
- `0x180041fec`
- `0x180045010`

## import_xrefs

- `msvcrt!free` at `0x180042262`
- `msvcrt!free` at `0x180042262`
- `msvcrt!wcscpy_s` at `0x18004205e`
- `msvcrt!wcscpy_s` at `0x18004207b`
- `msvcrt!wcscpy_s` at `0x18004209c`
- `msvcrt!wcscpy_s` at `0x18004205e`
- `msvcrt!wcscpy_s` at `0x18004207b`
- `msvcrt!wcscpy_s` at `0x18004209c`
- `msvcrt!_wcsdup` at `0x180042039`
- `msvcrt!_wcsdup` at `0x180042039`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800421f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800421f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180042259`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180042259`

## string_xrefs

- `0x1800421ec`: `mpunits.dll`
- `0x180042057`: `Win32_ComputerSystem`

## pseudocode

```c
__int64 __fastcall Listener_New(__int64 a1, __int64 a2, const wchar_t *a3, __int16 a4)
{
  const wchar_t *v6; // r13
  __int64 v8; // rax
  __int64 v9; // rbx
  wchar_t *v10; // rax
  errno_t v11; // esi
  __int64 v12; // rdi
  unsigned int v13; // r14d
  __int64 v14; // rax
  void *v16; // rdi
  HMODULE ModuleHandleA; // rax
  __int128 v18; // [rsp+30h] [rbp-18h] BYREF

  v6 = a3;
  v8 = CimBase_Create(424);
  v9 = v8;
  if ( v8 )
  {
    *(_QWORD *)(v8 + 56) = v8;
    *(_QWORD *)(v8 + 24) = a2;
    *(_WORD *)(v8 + 162) = a4;
    v10 = _wcsdup(v6);
    *(_QWORD *)(v9 + 48) = v10;
    if ( v10 )
    {
      v11 = wcscpy_s((wchar_t *)(v9 + 64), 0x15u, L"Win32_ComputerSystem");
      if ( !v11 )
      {
        v11 = wcscpy_s((wchar_t *)(v9 + 120), 0x15u, L"OMF_IndicationFilter");
        if ( !v11 )
        {
          v11 = wcscpy_s((wchar_t *)(v9 + 106), 7u, L"System");
          if ( !v11 )
          {
            if ( a1 && *(_QWORD *)a1 )
            {
              v12 = v9 + 168;
              if ( !(*(unsigned int (__fastcall **)(__int64, void *, __int64))(*(_QWORD *)a1 + 24LL))(
                      a1,
                      &OMF_ListenerDestination_rtti,
                      v9 + 168) )
              {
                *(_WORD *)(v9 + 360) = a4;
                *(_QWORD *)&v18 = v9 + 64;
                v13 = v11 + 13;
                *(_BYTE *)(v9 + 362) = 1;
                if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int128 *, _QWORD, errno_t))(*(_QWORD *)v12 + 80LL))(
                        v9 + 168,
                        (unsigned int)(v11 + 4),
                        &v18,
                        (unsigned int)(v11 + 13),
                        v11) )
                {
                  v14 = *(_QWORD *)v12;
                  *(_QWORD *)&v18 = v9 + 106;
                  if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int128 *, _QWORD, errno_t))(v14 + 80))(
                          v9 + 168,
                          (unsigned int)(v11 + 5),
                          &v18,
                          v13,
                          v11) )
                  {
                    *(_QWORD *)&v18 = v9 + 120;
                    if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int128 *, _QWORD, errno_t))(*(_QWORD *)v12 + 80LL))(
                            v9 + 168,
                            (unsigned int)(v11 + 6),
                            &v18,
                            v13,
                            v11) )
                    {
                      *(_QWORD *)(v9 + 16) = g_listenerft;
                      ((void (__fastcall *)(__int64))g_listenerft[0])(v9);
                      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v9 + 16) + 56LL))(a2, v9);
                      return v9;
                    }
                  }
                }
              }
            }
            else
            {
              v12 = v9 + 168;
            }
            if ( v12 && *(_QWORD *)v12 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
          }
          v6 = a3;
        }
      }
    }
    else
    {
      v11 = -1;
    }
    v16 = *(void **)(v9 + 48);
    if ( v16 )
    {
      if ( v11 )
      {
        v18 = 0;
        ModuleHandleA = GetModuleHandleA("mpunits.dll");
        *(_QWORD *)&v18 = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2128, v6);
        BYTE8(v18) = 1;
        MI_ReportErrorDetails_ForCustomError(v11, (int)L"ERRNO", 0, 0);
      }
      else
      {
        RaiseException(0xC0000025, 1u, 0, 0);
      }
      free(v16);
    }
    else
    {
      MI_ReportErrorDetails_OutOfMemory();
    }
    Listener_Delete(v9);
  }
  else
  {
    MI_ReportErrorDetails_OutOfMemory();
  }
  return 0;
}

```

## disassembly

```asm
0x180041fec  mov     [rsp-40h+arg_10], r8
0x180041ff1  push    rbp
0x180041ff2  push    rbx
0x180041ff3  push    rsi
0x180041ff4  push    rdi
0x180041ff5  push    r12
0x180041ff7  push    r13
0x180041ff9  push    r14
0x180041ffb  push    r15
0x180041ffd  mov     rbp, rsp
0x180042000  sub     rsp, 48h
0x180042004  mov     r14, rcx
0x180042007  mov     r12d, r9d
0x18004200a  mov     ecx, 1A8h
0x18004200f  mov     r13, r8
0x180042012  mov     r15, rdx
0x180042015  call    CimBase_Create
0x18004201a  mov     rbx, rax
0x18004201d  test    rax, rax
0x180042020  jz      loc_180042272
0x180042026  mov     rcx, r13; String
0x180042029  mov     [rax+38h], rax
0x18004202d  mov     [rax+18h], r15
0x180042031  mov     [rax+0A2h], r12w
0x180042039  call    cs:__imp__wcsdup
0x18004203f  mov     [rbx+30h], rax
0x180042043  test    rax, rax
0x180042046  jz      loc_1800421E0
0x18004204c  mov     edi, 15h
0x180042051  lea     rcx, [rbx+40h]; Destination
0x180042055  mov     edx, edi; SizeInWords
0x180042057  lea     r8, aWin32Computers; "Win32_ComputerSystem"
0x18004205e  call    cs:__imp_wcscpy_s
0x180042064  mov     esi, eax
0x180042066  test    eax, eax
0x180042068  jnz     loc_1800421CD
0x18004206e  lea     rcx, [rbx+78h]; Destination
0x180042072  mov     edx, edi; SizeInWords
0x180042074  lea     r8, aOmfIndicationf; "OMF_IndicationFilter"
0x18004207b  call    cs:__imp_wcscpy_s
0x180042081  mov     esi, eax
0x180042083  test    eax, eax
0x180042085  jnz     loc_1800421CD
0x18004208b  lea     r13, [rbx+6Ah]
0x18004208f  mov     rcx, r13; Destination
0x180042092  lea     r8, aSystem; "System"
0x180042099  lea     edx, [rdi-0Eh]; SizeInWords
0x18004209c  call    cs:__imp_wcscpy_s
0x1800420a2  mov     esi, eax
0x1800420a4  test    eax, eax
0x1800420a6  jnz     loc_1800421C9
0x1800420ac  test    r14, r14
0x1800420af  jz      loc_1800421A9
0x1800420b5  mov     rax, [r14]
0x1800420b8  test    rax, rax
0x1800420bb  jz      loc_1800421A9
0x1800420c1  mov     rax, [rax+18h]
0x1800420c5  lea     rdi, [rbx+0A8h]
0x1800420cc  mov     r8, rdi
0x1800420cf  lea     rdx, OMF_ListenerDestination_rtti
0x1800420d6  mov     rcx, r14
0x1800420d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800420de  test    eax, eax
0x1800420e0  jnz     loc_1800421B0
0x1800420e6  mov     [rdi+0C0h], r12w
0x1800420ee  lea     rax, [rbx+40h]
0x1800420f2  mov     qword ptr [rbp+var_18], rax
0x1800420f6  lea     r14d, [rsi+0Dh]
0x1800420fa  mov     byte ptr [rdi+0C2h], 1
0x180042101  lea     r8, [rbp+var_18]
0x180042105  mov     rax, [rdi]
0x180042108  lea     edx, [rsi+4]
0x18004210b  mov     r9d, r14d
0x18004210e  mov     dword ptr [rsp+48h+var_28], esi
0x180042112  mov     rcx, rdi
0x180042115  mov     rax, [rax+50h]
0x180042119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004211e  test    eax, eax
0x180042120  jnz     loc_1800421B0
0x180042126  mov     rax, [rdi]
0x180042129  lea     r8, [rbp+var_18]
0x18004212d  mov     qword ptr [rbp+var_18], r13
0x180042131  lea     edx, [rsi+5]
0x180042134  mov     r9d, r14d
0x180042137  mov     dword ptr [rsp+48h+var_28], esi
0x18004213b  mov     rcx, rdi
0x18004213e  mov     rax, [rax+50h]
0x180042142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042147  test    eax, eax
0x180042149  jnz     short loc_1800421B0
0x18004214b  lea     rax, [rbx+78h]
0x18004214f  mov     dword ptr [rsp+48h+var_28], esi
0x180042153  mov     qword ptr [rbp+var_18], rax
0x180042157  lea     r8, [rbp+var_18]
0x18004215b  mov     rax, [rdi]
0x18004215e  lea     edx, [rsi+6]
0x180042161  mov     r9d, r14d
0x180042164  mov     rcx, rdi
0x180042167  mov     rax, [rax+50h]
0x18004216b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042170  test    eax, eax
0x180042172  jnz     short loc_1800421B0
0x180042174  lea     rax, g_listenerft
0x18004217b  mov     rcx, rbx
0x18004217e  mov     [rbx+10h], rax
0x180042182  mov     rax, cs:g_listenerft
0x180042189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004218e  mov     rax, [rbx+10h]
0x180042192  mov     rdx, rbx
0x180042195  mov     rcx, r15
0x180042198  mov     rax, [rax+38h]
0x18004219c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421a1  mov     rax, rbx
0x1800421a4  jmp     loc_180042279
0x1800421a9  lea     rdi, [rbx+0A8h]
0x1800421b0  test    rdi, rdi
0x1800421b3  jz      short loc_1800421C9
0x1800421b5  mov     rax, [rdi]
0x1800421b8  test    rax, rax
0x1800421bb  jz      short loc_1800421C9
0x1800421bd  mov     rax, [rax+8]
0x1800421c1  mov     rcx, rdi
0x1800421c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421c9  mov     r13, [rbp+arg_10]
0x1800421cd  mov     rdi, [rbx+30h]
0x1800421d1  test    rdi, rdi
0x1800421d4  jnz     short loc_1800421E5
0x1800421d6  call    MI_ReportErrorDetails_OutOfMemory
0x1800421db  jmp     loc_180042268
0x1800421e0  or      esi, 0FFFFFFFFh
0x1800421e3  jmp     short loc_1800421CD
0x1800421e5  test    esi, esi
0x1800421e7  jz      short loc_18004224A
0x1800421e9  xorps   xmm0, xmm0
0x1800421ec  lea     rcx, ModuleName; "mpunits.dll"
0x1800421f3  movups  [rbp+var_18], xmm0
0x1800421f7  call    cs:__imp_GetModuleHandleA
0x1800421fd  mov     r8, r13
0x180042200  mov     edx, 850h
0x180042205  mov     rcx, rax
0x180042208  call    _Intlstr_FormatString_FormatMessage
0x18004220d  mov     qword ptr [rbp+var_18], rax
0x180042211  lea     r9, [rbp+var_18]
0x180042215  mov     byte ptr [rbp+var_18+8], 1
0x180042219  lea     rdx, aErrno; "ERRNO"
0x180042220  movaps  xmm0, [rbp+var_18]
0x180042224  mov     r8d, 6
0x18004222a  mov     [rsp+48h+var_20], 0; __int64
0x180042233  mov     ecx, esi; int
0x180042235  movdqa  [rbp+var_18], xmm0
0x18004223a  mov     [rsp+48h+var_28], 0; __int64
0x180042243  call    MI_ReportErrorDetails_ForCustomError
0x180042248  jmp     short loc_18004225F
0x18004224a  xor     r9d, r9d; lpArguments
0x18004224d  xor     r8d, r8d; nNumberOfArguments
0x180042250  mov     ecx, 0C0000025h; dwExceptionCode
0x180042255  lea     edx, [r9+1]; dwExceptionFlags
0x180042259  call    cs:__imp_RaiseException
0x18004225f  mov     rcx, rdi; Block
0x180042262  call    cs:__imp_free
0x180042268  mov     rcx, rbx
0x18004226b  call    Listener_Delete
0x180042270  jmp     short loc_180042277
0x180042272  call    MI_ReportErrorDetails_OutOfMemory
0x180042277  xor     eax, eax
0x180042279  add     rsp, 48h
0x18004227d  pop     r15
0x18004227f  pop     r14
0x180042281  pop     r13
0x180042283  pop     r12
0x180042285  pop     rdi
0x180042286  pop     rsi
0x180042287  pop     rbx
0x180042288  pop     rbp
0x180042289  retn
```
