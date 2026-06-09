# Loader_Collector_Invoke_ReceiveCollectorEvent

- ea: `0x180005a10`
- end: `0x180005c70`
- name: `Loader_Collector_Invoke_ReceiveCollectorEvent`
- size: `608`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18000416c`
- `0x180005a10`
- `0x180006e64`
- `0x180007c80`
- `0x180008ea0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180005ac3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180005b3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180005ac3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180005b3f`

## string_xrefs

- `0x180005ab8`: `mpunits.dll`
- `0x180005b34`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall Loader_Collector_Invoke_ReceiveCollectorEvent(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 *a7)
{
  __int64 v7; // rbx
  __int64 v9; // rdi
  int v10; // r14d
  __int64 v11; // r15
  int v12; // r12d
  __int64 v13; // r9
  __int64 v14; // r13
  HMODULE ModuleHandleA; // rax
  unsigned int v16; // edi
  __int64 result; // rax
  HMODULE v18; // rax
  __int64 *v19; // [rsp+D8h] [rbp+57h] BYREF

  v7 = (__int64)a7;
  v19 = 0;
  if ( !*((_BYTE *)a7 + 88) || !a7[10] )
  {
    v16 = 4;
    result = MI_ReportErrorDetails_MandatoryParameterMissing(L"BindingID");
    goto LABEL_23;
  }
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( *((_BYTE *)a7 + 128) )
  {
    v14 = a7[14];
    LODWORD(a7) = *((_DWORD *)a7 + 30);
  }
  else
  {
    v14 = 0;
    LODWORD(a7) = 0;
  }
  if ( *(_BYTE *)(v7 + 152) )
  {
    v9 = *(_QWORD *)(v7 + 136);
    v10 = *(_DWORD *)(v7 + 144);
  }
  if ( *(_BYTE *)(v7 + 176) )
  {
    v11 = *(_QWORD *)(v7 + 160);
    v12 = *(_DWORD *)(v7 + 168);
  }
  if ( *(_BYTE *)(v7 + 252) )
  {
    if ( !*(_DWORD *)(v7 + 216) )
    {
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      Intlstr_FormatString_FormatMessage(ModuleHandleA, 2108, L"Expires");
LABEL_13:
      v16 = 4;
      result = MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
      goto LABEL_23;
    }
    if ( !(unsigned __int8)Timestamp_IsValid(v7 + 220) )
    {
      v18 = GetModuleHandleA("mpunits.dll");
      Intlstr_FormatString_FormatMessage(v18, 2135, L"Expires");
      goto LABEL_13;
    }
  }
  result = Collector(
             *(_QWORD *)(v7 + 80),
             *(_QWORD *)(v7 + 96),
             v14,
             (int)a7,
             v9,
             v10,
             v11,
             v12,
             0,
             *(_QWORD *)(v7 + 200),
             v13,
             (__int64)&v19);
  v16 = result;
  if ( !(_DWORD)result )
  {
    a7 = v19;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 **, __int64, int))(*(_QWORD *)v7 + 80LL))(
               v7,
               0,
               &a7,
               15,
               0x40000000);
    v16 = result;
    if ( !(_DWORD)result )
    {
      if ( a2 && (result = *a2) != 0 )
      {
        result = (*(__int64 (__fastcall **)(__int64 *, __int64))(result + 8))(a2, v7);
        v16 = result;
      }
      else
      {
        v16 = 4;
      }
    }
  }
LABEL_23:
  if ( v19 )
  {
    result = *v19;
    if ( *v19 )
      result = (*(__int64 (**)(void))(result + 16))();
  }
  if ( a2 )
  {
    result = *a2;
    if ( *a2 )
      return (*(__int64 (__fastcall **)(__int64 *, _QWORD))result)(a2, v16);
  }
  return result;
}

```

## disassembly

```asm
0x180005a10  push    rbp
0x180005a12  push    rbx
0x180005a13  push    rsi
0x180005a14  push    rdi
0x180005a15  push    r12
0x180005a17  push    r13
0x180005a19  push    r14
0x180005a1b  push    r15
0x180005a1d  lea     rbp, [rsp-7]
0x180005a22  sub     rsp, 88h
0x180005a29  mov     rbx, [rbp+3Fh+arg_30]
0x180005a2d  xor     ecx, ecx
0x180005a2f  mov     rsi, rdx
0x180005a32  mov     [rbp+3Fh+arg_8], rcx
0x180005a36  cmp     [rbx+58h], cl
0x180005a39  jz      loc_180005C17
0x180005a3f  cmp     [rbx+50h], rcx
0x180005a43  jz      loc_180005C17
0x180005a49  mov     edi, ecx
0x180005a4b  mov     r14d, ecx
0x180005a4e  mov     r15d, ecx
0x180005a51  mov     r12d, ecx
0x180005a54  mov     r9d, ecx
0x180005a57  cmp     [rbx+80h], cl
0x180005a5d  jz      short loc_180005A6B
0x180005a5f  mov     eax, [rbx+78h]
0x180005a62  mov     r13, [rbx+70h]
0x180005a66  mov     dword ptr [rbp+3Fh+arg_30], eax
0x180005a69  jmp     short loc_180005A71
0x180005a6b  mov     r13, rcx
0x180005a6e  mov     dword ptr [rbp+3Fh+arg_30], ecx
0x180005a71  cmp     [rbx+98h], cl
0x180005a77  jz      short loc_180005A87
0x180005a79  mov     rdi, [rbx+88h]
0x180005a80  mov     r14d, [rbx+90h]
0x180005a87  cmp     [rbx+0B0h], cl
0x180005a8d  jz      short loc_180005A9D
0x180005a8f  mov     r15, [rbx+0A0h]
0x180005a96  mov     r12d, [rbx+0A8h]
0x180005a9d  cmp     [rbx+0FCh], cl
0x180005aa3  jz      loc_180005B65
0x180005aa9  lea     r9, [rbx+0D8h]
0x180005ab0  cmp     [r9], ecx
0x180005ab3  jnz     short loc_180005B21
0x180005ab5  xorps   xmm0, xmm0
0x180005ab8  lea     rcx, ModuleName; "mpunits.dll"
0x180005abf  movups  [rbp+3Fh+var_50], xmm0
0x180005ac3  call    cs:__imp_GetModuleHandleA
0x180005ac9  lea     r8, aExpires; "Expires"
0x180005ad0  mov     edx, 83Ch
0x180005ad5  mov     rcx, rax
0x180005ad8  call    _Intlstr_FormatString_FormatMessage
0x180005add  mov     qword ptr [rbp+3Fh+var_50], rax
0x180005ae1  lea     r9, [rbp+3Fh+var_50]
0x180005ae5  mov     byte ptr [rbp+3Fh+var_50+8], 1
0x180005ae9  lea     rdx, aMi; "MI"
0x180005af0  movaps  xmm0, [rbp+3Fh+var_50]
0x180005af4  mov     r8d, 5
0x180005afa  mov     [rsp+0C0h+var_98], 0; __int64
0x180005b03  movdqa  [rbp+3Fh+var_50], xmm0
0x180005b08  mov     [rsp+0C0h+var_A0], 0; __int64
0x180005b11  lea     edi, [r8-1]
0x180005b15  mov     ecx, edi; int
0x180005b17  call    MI_ReportErrorDetails_ForCustomError
0x180005b1c  jmp     loc_180005C28
0x180005b21  lea     rcx, [rbx+0DCh]
0x180005b28  call    Timestamp_IsValid
0x180005b2d  test    al, al
0x180005b2f  jnz     short loc_180005B65
0x180005b31  xorps   xmm0, xmm0
0x180005b34  lea     rcx, ModuleName; "mpunits.dll"
0x180005b3b  movups  [rbp+3Fh+var_50], xmm0
0x180005b3f  call    cs:__imp_GetModuleHandleA
0x180005b45  lea     r9, aReceiveCollect; "Receive-CollectorEvent"
0x180005b4c  mov     edx, 857h
0x180005b51  mov     rcx, rax
0x180005b54  lea     r8, aExpires; "Expires"
0x180005b5b  call    _Intlstr_FormatString_FormatMessage
0x180005b60  jmp     loc_180005ADD
0x180005b65  mov     rdx, [rbx+0C8h]
0x180005b6c  lea     rcx, [rbp+3Fh+arg_8]
0x180005b70  mov     rax, cs:off_180047BA0
0x180005b77  mov     r8, r13
0x180005b7a  mov     [rsp+0C0h+var_68], rcx
0x180005b7f  mov     rcx, [rbx+50h]
0x180005b83  mov     [rsp+0C0h+var_70], r9
0x180005b88  mov     r9d, dword ptr [rbp+3Fh+arg_30]
0x180005b8c  mov     rax, [rax+58h]
0x180005b90  mov     [rsp+0C0h+var_78], rdx
0x180005b95  mov     rdx, [rbx+60h]
0x180005b99  mov     [rsp+0C0h+var_80], 0
0x180005ba2  mov     [rsp+0C0h+var_88], r12d
0x180005ba7  mov     [rsp+0C0h+var_90], r15
0x180005bac  mov     dword ptr [rsp+0C0h+var_98], r14d
0x180005bb1  mov     [rsp+0C0h+var_A0], rdi
0x180005bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bbb  mov     edi, eax
0x180005bbd  test    eax, eax
0x180005bbf  jnz     short loc_180005C28
0x180005bc1  mov     rax, [rbp+3Fh+arg_8]
0x180005bc5  lea     r9d, [rdi+0Fh]
0x180005bc9  mov     [rbp+3Fh+arg_30], rax
0x180005bcd  lea     r8, [rbp+3Fh+arg_30]
0x180005bd1  mov     rax, [rbx]
0x180005bd4  xor     edx, edx
0x180005bd6  mov     rcx, rbx
0x180005bd9  mov     dword ptr [rsp+0C0h+var_A0], 40000000h
0x180005be1  mov     rax, [rax+50h]
0x180005be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bea  mov     edi, eax
0x180005bec  test    eax, eax
0x180005bee  jnz     short loc_180005C28
0x180005bf0  test    rsi, rsi
0x180005bf3  jz      short loc_180005C10
0x180005bf5  mov     rax, [rsi]
0x180005bf8  test    rax, rax
0x180005bfb  jz      short loc_180005C10
0x180005bfd  mov     rax, [rax+8]
0x180005c01  mov     rdx, rbx
0x180005c04  mov     rcx, rsi
0x180005c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c0c  mov     edi, eax
0x180005c0e  jmp     short loc_180005C28
0x180005c10  mov     edi, 4
0x180005c15  jmp     short loc_180005C28
0x180005c17  lea     rcx, aBindingid; "BindingID"
0x180005c1e  mov     edi, 4
0x180005c23  call    MI_ReportErrorDetails_MandatoryParameterMissing
0x180005c28  mov     rcx, [rbp+3Fh+arg_8]
0x180005c2c  test    rcx, rcx
0x180005c2f  jz      short loc_180005C42
0x180005c31  mov     rax, [rcx]
0x180005c34  test    rax, rax
0x180005c37  jz      short loc_180005C42
0x180005c39  mov     rax, [rax+10h]
0x180005c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c42  test    rsi, rsi
0x180005c45  jz      short loc_180005C5C
0x180005c47  mov     rax, [rsi]
0x180005c4a  test    rax, rax
0x180005c4d  jz      short loc_180005C5C
0x180005c4f  mov     rax, [rax]
0x180005c52  mov     edx, edi
0x180005c54  mov     rcx, rsi
0x180005c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c5c  add     rsp, 88h
0x180005c63  pop     r15
0x180005c65  pop     r14
0x180005c67  pop     r13
0x180005c69  pop     r12
0x180005c6b  pop     rdi
0x180005c6c  pop     rsi
0x180005c6d  pop     rbx
0x180005c6e  pop     rbp
0x180005c6f  retn
```
