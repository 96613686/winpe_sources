# PRCreateLocalToken(_UNICODE_STRING *,_UNICODE_STRING *,void * *)

- ea: `0x180037a5c`
- end: `0x180037ba1`
- name: `?PRCreateLocalToken@@YAKPEAU_UNICODE_STRING@@0PEAPEAX@Z`
- size: `325`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180037e98`
- `0x180038a00`

## callees

- `0x180007f10`
- `0x180037a5c`
- `0x18003e010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180037ad3`
- `ntdll!RtlNtStatusToDosError` at `0x180037b44`
- `ntdll!RtlNtStatusToDosError` at `0x180037ad3`
- `ntdll!RtlNtStatusToDosError` at `0x180037b44`

## string_xrefs

- `0x180037b56`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PRCreateLocalToken(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2, void **a3)
{
  NTSTATUS v5; // eax
  unsigned int v6; // edi
  ULONG v7; // eax
  __int64 v8; // r9
  ULONG v9; // ebx
  NTSTATUS v10; // eax
  int v12; // [rsp+68h] [rbp+17h] BYREF
  __int64 v13; // [rsp+70h] [rbp+1Fh] BYREF
  __int64 v14; // [rsp+78h] [rbp+27h] BYREF
  __int128 v15; // [rsp+80h] [rbp+2Fh] BYREF
  unsigned int v16; // [rsp+D0h] [rbp+7Fh] BYREF

  v12 = 0;
  v14 = 0;
  v13 = 0;
  v16 = 0;
  v15 = 0;
  v5 = (*((__int64 (__fastcall **)(struct _UNICODE_STRING *, _QWORD, _QWORD, __int64 *, unsigned int *, _QWORD))g_pDPAPILsasrvIfTable
        + 5))(
         a1,
         0,
         0,
         &v13,
         &v16,
         0);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v9 = 0;
    *((_QWORD *)&v15 + 1) = 0;
    v10 = (*((__int64 (__fastcall **)(__int64, _QWORD, __int64, struct _TOKEN_SOURCE *, int, struct _UNICODE_STRING *, void **, __int64 *, __int128 *, int *))g_pDPAPILsasrvIfTable
           + 6))(
            v13,
            v16,
            2,
            &DPAPITokenSource,
            3,
            a2,
            a3,
            &v14,
            &v15,
            &v12);
    v6 = v10;
    if ( v10 >= 0 )
      goto LABEL_6;
    v7 = RtlNtStatusToDosError(v10);
    v8 = 1200;
  }
  else
  {
    v7 = RtlNtStatusToDosError(v5);
    v8 = 1175;
  }
  v9 = v7;
  DebugTraceError(v6, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v8);
LABEL_6:
  if ( v13 )
    (*((void (**)(void))g_pDPAPILsasrvIfTable + 3))();
  return v9;
}

```

## disassembly

```asm
0x180037a5c  mov     r11, rsp
0x180037a5f  mov     [r11+8], rbx
0x180037a63  mov     [r11+10h], rsi
0x180037a67  push    rbp
0x180037a68  push    rdi
0x180037a69  push    r14
0x180037a6b  lea     rbp, [r11-5Fh]
0x180037a6f  sub     rsp, 90h
0x180037a76  mov     rax, cs:?g_pDPAPILsasrvIfTable@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pDPAPILsasrvIfTable
0x180037a7d  lea     r9, [rbp+57h+var_38]
0x180037a81  mov     r14, rdx
0x180037a84  mov     qword ptr [r11-80h], 0
0x180037a8c  lea     rdx, [rbp+57h+arg_18]
0x180037a90  mov     [rbp+57h+var_40], 0
0x180037a97  xorps   xmm0, xmm0
0x180037a9a  mov     [rbp+57h+var_30], 0
0x180037aa2  mov     rsi, r8
0x180037aa5  mov     [rbp+57h+var_38], 0
0x180037aad  mov     [rbp+57h+arg_18], 0
0x180037ab4  xor     r8d, r8d
0x180037ab7  movups  [rbp+57h+var_28], xmm0
0x180037abb  mov     rax, [rax+28h]
0x180037abf  mov     [rsp+0A0h+var_80], rdx
0x180037ac4  xor     edx, edx
0x180037ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037acb  mov     edi, eax
0x180037acd  test    eax, eax
0x180037acf  jns     short loc_180037AE7
0x180037ad1  mov     ecx, eax; Status
0x180037ad3  call    cs:__imp_RtlNtStatusToDosError
0x180037ada  nop     dword ptr [rax+rax+00h]
0x180037adf  mov     r9d, 497h
0x180037ae5  jmp     short loc_180037B56
0x180037ae7  mov     rax, cs:?g_pDPAPILsasrvIfTable@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pDPAPILsasrvIfTable
0x180037aee  lea     rcx, [rbp+57h+var_40]
0x180037af2  mov     edx, [rbp+57h+arg_18]
0x180037af5  lea     r9, ?DPAPITokenSource@@3U_TOKEN_SOURCE@@A; _TOKEN_SOURCE DPAPITokenSource
0x180037afc  mov     [rsp+0A0h+var_58], rcx
0x180037b01  xor     ebx, ebx
0x180037b03  lea     rcx, [rbp+57h+var_28]
0x180037b07  mov     qword ptr [rbp+57h+var_28+8], rbx
0x180037b0b  mov     rax, [rax+30h]
0x180037b0f  mov     [rsp+0A0h+var_60], rcx
0x180037b14  lea     rcx, [rbp+57h+var_30]
0x180037b18  mov     [rsp+0A0h+var_68], rcx
0x180037b1d  lea     r8d, [rbx+2]
0x180037b21  mov     rcx, [rbp+57h+var_38]
0x180037b25  mov     [rsp+0A0h+var_70], rsi
0x180037b2a  mov     [rsp+0A0h+var_78], r14
0x180037b2f  mov     dword ptr [rsp+0A0h+var_80], 3
0x180037b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b3c  mov     edi, eax
0x180037b3e  test    eax, eax
0x180037b40  jns     short loc_180037B6D
0x180037b42  mov     ecx, eax; Status
0x180037b44  call    cs:__imp_RtlNtStatusToDosError
0x180037b4b  nop     dword ptr [rax+rax+00h]
0x180037b50  mov     r9d, 4B0h
0x180037b56  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180037b5d  mov     ecx, edi
0x180037b5f  lea     rdx, aStatus; "Status"
0x180037b66  mov     ebx, eax
0x180037b68  call    DebugTraceError
0x180037b6d  mov     rcx, [rbp+57h+var_38]
0x180037b71  test    rcx, rcx
0x180037b74  jz      short loc_180037B86
0x180037b76  mov     rax, cs:?g_pDPAPILsasrvIfTable@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pDPAPILsasrvIfTable
0x180037b7d  mov     rax, [rax+18h]
0x180037b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b86  lea     r11, [rsp+0A0h+var_10]
0x180037b8e  mov     eax, ebx
0x180037b90  mov     rbx, [r11+20h]
0x180037b94  mov     rsi, [r11+28h]
0x180037b98  mov     rsp, r11
0x180037b9b  pop     r14
0x180037b9d  pop     rdi
0x180037b9e  pop     rbp
0x180037b9f  retn
```
