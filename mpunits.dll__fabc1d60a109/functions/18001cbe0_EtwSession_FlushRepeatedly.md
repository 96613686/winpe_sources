# EtwSession_FlushRepeatedly

- ea: `0x18001cbe0`
- end: `0x18001cd34`
- name: `EtwSession_FlushRepeatedly`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x180019770`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18000b2a8`
- `0x18001cbe0`
- `0x180033d80`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001cc7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001cc7b`

## string_xrefs

- `0x18001cc70`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall EtwSession_FlushRepeatedly(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // edi
  HMODULE ModuleHandleA; // rax
  __int64 v6; // [rsp+30h] [rbp-19h] BYREF
  __int128 v7; // [rsp+40h] [rbp-9h]
  __int128 v8; // [rsp+50h] [rbp+7h] BYREF
  __int128 v9; // [rsp+60h] [rbp+17h]
  __int64 v10; // [rsp+70h] [rbp+27h]
  __int128 v11; // [rsp+78h] [rbp+2Fh] BYREF
  int v12; // [rsp+88h] [rbp+3Fh]
  __int64 v13; // [rsp+8Ch] [rbp+43h]
  int v14; // [rsp+94h] [rbp+4Bh]

  v6 = 0;
  v13 = 0;
  v14 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 50000;
  v8 = 0;
  v9 = 0;
  if ( _InterlockedExchange64((volatile __int64 *)(a1 + 24), 1) != 1 )
  {
    v2 = RxcInterval(&v11, 0, 0, &v6);
    v3 = v2;
    if ( v2 )
    {
      *(_QWORD *)(a1 + 24) = 0;
      trace_ETW_ThreadStartFail(v2);
      v7 = 0;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      *(_QWORD *)&v7 = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2037, v3);
      BYTE8(v7) = 1;
      MI_ReportErrorDetails_ForCustomError(6, (int)L"ETW Normalizer", 0, 0);
      return v3;
    }
    *(_QWORD *)&v8 = a1;
    *((_QWORD *)&v8 + 1) = EtwSession_FlushThread;
    v9 = 0u;
    v10 = 0;
    *(_QWORD *)(a1 + 16) = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(v6 + 32))(v6, &v8, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18001cbe0  mov     [rsp-8+arg_8], rbx
0x18001cbe5  mov     [rsp-8+arg_10], rdi
0x18001cbea  push    rbp
0x18001cbeb  lea     rbp, [rsp-57h]
0x18001cbf0  sub     rsp, 0A0h
0x18001cbf7  mov     rax, cs:__security_cookie
0x18001cbfe  xor     rax, rsp
0x18001cc01  mov     [rbp+57h+var_8], rax
0x18001cc05  xor     eax, eax
0x18001cc07  mov     [rbp+57h+var_70], 0
0x18001cc0f  xorps   xmm0, xmm0
0x18001cc12  mov     [rbp+57h+var_14], rax
0x18001cc16  mov     [rbp+57h+var_C], eax
0x18001cc19  mov     rbx, rcx
0x18001cc1c  mov     [rbp+57h+var_30], rax
0x18001cc20  mov     eax, 1
0x18001cc25  movups  [rbp+57h+var_28], xmm0
0x18001cc29  mov     [rbp+57h+var_18], 0C350h
0x18001cc30  movups  [rbp+57h+var_50], xmm0
0x18001cc34  movups  [rbp+57h+var_40], xmm0
0x18001cc38  xchg    rax, [rcx+18h]
0x18001cc3c  cmp     rax, 1
0x18001cc40  jz      loc_18001CD11
0x18001cc46  lea     r9, [rbp+57h+var_70]
0x18001cc4a  xor     r8d, r8d
0x18001cc4d  xor     edx, edx
0x18001cc4f  lea     rcx, [rbp+57h+var_28]
0x18001cc53  call    RxcInterval
0x18001cc58  mov     edi, eax
0x18001cc5a  test    eax, eax
0x18001cc5c  jz      short loc_18001CCD2
0x18001cc5e  mov     ecx, eax
0x18001cc60  mov     qword ptr [rbx+18h], 0
0x18001cc68  call    trace_ETW_ThreadStartFail
0x18001cc6d  xorps   xmm0, xmm0
0x18001cc70  lea     rcx, ModuleName; "mpunits.dll"
0x18001cc77  movups  [rbp+57h+var_60], xmm0
0x18001cc7b  call    cs:__imp_GetModuleHandleA
0x18001cc81  mov     r8d, edi
0x18001cc84  mov     edx, 7F5h
0x18001cc89  mov     rcx, rax
0x18001cc8c  call    _Intlstr_FormatString_FormatMessage
0x18001cc91  mov     qword ptr [rbp+57h+var_60], rax
0x18001cc95  lea     r9, [rbp+57h+var_60]
0x18001cc99  mov     byte ptr [rbp+57h+var_60+8], 1
0x18001cc9d  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x18001cca4  movaps  xmm0, [rbp+57h+var_60]
0x18001cca8  mov     r8d, 15h
0x18001ccae  mov     [rsp+0A0h+var_78], 0; __int64
0x18001ccb7  movdqa  [rbp+57h+var_60], xmm0
0x18001ccbc  mov     [rsp+0A0h+var_80], 0; __int64
0x18001ccc5  lea     ecx, [r8-0Fh]; int
0x18001ccc9  call    MI_ReportErrorDetails_ForCustomError
0x18001ccce  mov     eax, edi
0x18001ccd0  jmp     short loc_18001CD13
0x18001ccd2  mov     rcx, [rbp+57h+var_70]
0x18001ccd6  lea     rax, EtwSession_FlushThread
0x18001ccdd  mov     qword ptr [rbp+57h+var_50], rbx
0x18001cce1  lea     rdx, [rbp+57h+var_50]
0x18001cce5  mov     qword ptr [rbp+57h+var_50+8], rax
0x18001cce9  xor     r8d, r8d
0x18001ccec  mov     qword ptr [rbp+57h+var_40+8], 0
0x18001ccf4  mov     qword ptr [rbp+57h+var_40], 0
0x18001ccfc  mov     [rbp+57h+var_30], 0
0x18001cd04  mov     rax, [rcx+20h]
0x18001cd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd0d  mov     [rbx+10h], rax
0x18001cd11  xor     eax, eax
0x18001cd13  mov     rcx, [rbp+57h+var_8]
0x18001cd17  xor     rcx, rsp; StackCookie
0x18001cd1a  call    __security_check_cookie
0x18001cd1f  lea     r11, [rsp+0A0h+var_s0]
0x18001cd27  mov     rbx, [r11+18h]
0x18001cd2b  mov     rdi, [r11+20h]
0x18001cd2f  mov     rsp, r11
0x18001cd32  pop     rbp
0x18001cd33  retn
```
