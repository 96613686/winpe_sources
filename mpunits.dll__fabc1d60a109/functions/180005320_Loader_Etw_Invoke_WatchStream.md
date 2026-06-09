# Loader_Etw_Invoke_WatchStream

- ea: `0x180005320`
- end: `0x180005598`
- name: `Loader_Etw_Invoke_WatchStream`
- size: `632`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180005320`
- `0x180006ef8`
- `0x180007c80`
- `0x180008db0`
- `0x180008ea0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000541b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000541b`

## string_xrefs

- `0x180005410`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall Loader_Etw_Invoke_WatchStream(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 *a7)
{
  __int64 *v7; // rdi
  unsigned int v9; // ebx
  __int64 result; // rax
  char v11; // bl
  char v12; // r15
  __int64 v13; // r12
  HMODULE ModuleHandleA; // rax
  __int64 *v15; // rax
  __int64 *v16; // rsi
  void (__fastcall **v17)(__int64 *, __int64 **); // rax
  __int64 v18; // rax
  __int64 *v19; // [rsp+98h] [rbp+50h] BYREF

  v7 = a7;
  v19 = 0;
  if ( !*((_BYTE *)a7 + 88) )
  {
    v9 = 4;
    result = MI_ReportErrorDetails_MandatoryParameterMissing((__int64)L"UpstreamPipe");
    goto LABEL_6;
  }
  if ( !*((_BYTE *)a7 + 148) )
  {
    result = MI_ReportErrorDetails_MandatoryParameterMissing((__int64)L"Interval");
LABEL_5:
    v9 = 4;
    goto LABEL_6;
  }
  if ( *((_DWORD *)a7 + 28) )
  {
    v9 = 4;
    result = MI_ReportErrorDetails_InvalidParameter_CannotCoerceTimestampToInterval((__int64)L"interval");
    goto LABEL_6;
  }
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( *((_BYTE *)a7 + 153) )
    v11 = *((_BYTE *)a7 + 152);
  if ( *((_BYTE *)a7 + 156) )
    v12 = *((_BYTE *)a7 + 155);
  if ( *((_BYTE *)a7 + 104) )
    v13 = a7[12];
  if ( !v11 && !v12 )
  {
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    Intlstr_GetString_LoadString(ModuleHandleA, 2113);
    v9 = 4;
    result = MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
    goto LABEL_6;
  }
  v15 = (__int64 *)((__int64 (__fastcall *)(__int64))Observable_FromInstance)(a7[10]);
  v19 = v15;
  v16 = v15;
  a7 = 0;
  if ( v15 )
  {
    v17 = (void (__fastcall **)(__int64 *, __int64 **))*v15;
    if ( v17 )
    {
      (*v17)(v16, &a7);
      v16 = v19;
    }
  }
  if ( v11 )
  {
    result = ((__int64 (__fastcall *)(__int64 *, char *, __int64, __int64 **))WatchThroughput)(
               v16,
               (char *)v7 + 116,
               v13,
               &v19);
    v9 = result;
    if ( v16 )
    {
      result = *v16;
      if ( *v16 )
        result = (*(__int64 (__fastcall **)(__int64 *))(result + 16))(v16);
    }
    if ( v9 )
      goto LABEL_6;
    v16 = v19;
  }
  if ( !v12 )
  {
LABEL_39:
    v18 = *v7;
    a7 = v16;
    result = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **, __int64, int))(v18 + 80))(
               v7,
               0,
               &a7,
               15,
               0x40000000);
    v9 = result;
    if ( (_DWORD)result )
      goto LABEL_6;
    if ( a2 )
    {
      result = *a2;
      if ( *a2 )
      {
        result = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(result + 8))(a2, v7);
        v9 = result;
        goto LABEL_6;
      }
    }
    goto LABEL_5;
  }
  result = ((__int64 (__fastcall *)(__int64 *, char *, __int64, __int64 **))WatchInclusiveCpu)(
             v16,
             (char *)v7 + 116,
             v13,
             &v19);
  v9 = result;
  if ( v16 )
  {
    result = *v16;
    if ( *v16 )
      result = (*(__int64 (__fastcall **)(__int64 *))(result + 16))(v16);
  }
  if ( !v9 )
  {
    v16 = v19;
    goto LABEL_39;
  }
LABEL_6:
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
      return (*(__int64 (__fastcall **)(__int64 *, _QWORD))result)(a2, v9);
  }
  return result;
}

```

## disassembly

```asm
0x180005320  push    rbp
0x180005322  push    rbx
0x180005323  push    rsi
0x180005324  push    rdi
0x180005325  push    r12
0x180005327  push    r13
0x180005329  push    r14
0x18000532b  push    r15
0x18000532d  mov     rbp, rsp
0x180005330  sub     rsp, 48h
0x180005334  mov     rdi, [rbp+arg_30]
0x180005338  xor     r13d, r13d
0x18000533b  mov     r14, rdx
0x18000533e  mov     [rbp+arg_8], r13
0x180005342  cmp     [rdi+58h], r13b
0x180005346  jnz     short loc_18000535A
0x180005348  lea     rcx, aUpstreampipe_0; "UpstreamPipe"
0x18000534f  lea     ebx, [r13+4]
0x180005353  call    MI_ReportErrorDetails_MandatoryParameterMissing
0x180005358  jmp     short loc_180005374
0x18000535a  cmp     [rdi+94h], r13b
0x180005361  jnz     short loc_1800053B9
0x180005363  lea     rcx, aInterval_0; "Interval"
0x18000536a  call    MI_ReportErrorDetails_MandatoryParameterMissing
0x18000536f  mov     ebx, 4
0x180005374  mov     rcx, [rbp+arg_8]
0x180005378  test    rcx, rcx
0x18000537b  jz      short loc_18000538E
0x18000537d  mov     rax, [rcx]
0x180005380  test    rax, rax
0x180005383  jz      short loc_18000538E
0x180005385  mov     rax, [rax+10h]
0x180005389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000538e  test    r14, r14
0x180005391  jz      short loc_1800053A8
0x180005393  mov     rax, [r14]
0x180005396  test    rax, rax
0x180005399  jz      short loc_1800053A8
0x18000539b  mov     rax, [rax]
0x18000539e  mov     edx, ebx
0x1800053a0  mov     rcx, r14
0x1800053a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053a8  add     rsp, 48h
0x1800053ac  pop     r15
0x1800053ae  pop     r14
0x1800053b0  pop     r13
0x1800053b2  pop     r12
0x1800053b4  pop     rdi
0x1800053b5  pop     rsi
0x1800053b6  pop     rbx
0x1800053b7  pop     rbp
0x1800053b8  retn
0x1800053b9  cmp     [rdi+70h], r13d
0x1800053bd  jz      short loc_1800053D2
0x1800053bf  lea     rcx, aInterval; "interval"
0x1800053c6  mov     ebx, 4
0x1800053cb  call    MI_ReportErrorDetails_InvalidParameter_CannotCoerceTimestampToInterval
0x1800053d0  jmp     short loc_180005374
0x1800053d2  mov     bl, r13b
0x1800053d5  mov     r15b, r13b
0x1800053d8  mov     r12, r13
0x1800053db  cmp     [rdi+99h], r13b
0x1800053e2  jz      short loc_1800053EA
0x1800053e4  mov     bl, [rdi+98h]
0x1800053ea  cmp     [rdi+9Ch], r13b
0x1800053f1  jz      short loc_1800053FA
0x1800053f3  mov     r15b, [rdi+9Bh]
0x1800053fa  cmp     [rdi+68h], r13b
0x1800053fe  jz      short loc_180005404
0x180005400  mov     r12, [rdi+60h]
0x180005404  test    bl, bl
0x180005406  jnz     short loc_18000546A
0x180005408  test    r15b, r15b
0x18000540b  jnz     short loc_18000546A
0x18000540d  xorps   xmm0, xmm0
0x180005410  lea     rcx, ModuleName; "mpunits.dll"
0x180005417  movups  [rbp+var_18], xmm0
0x18000541b  call    cs:__imp_GetModuleHandleA
0x180005421  mov     rcx, rax
0x180005424  mov     edx, 841h
0x180005429  call    _Intlstr_GetString_LoadString
0x18000542e  mov     qword ptr [rbp+var_18], rax
0x180005432  lea     r9, [rbp+var_18]
0x180005436  mov     byte ptr [rbp+var_18+8], r13b
0x18000543a  lea     rdx, aMi; "MI"
0x180005441  movaps  xmm0, [rbp+var_18]
0x180005445  mov     r8d, 5
0x18000544b  mov     [rsp+48h+var_20], r13; __int64
0x180005450  movdqa  [rbp+var_18], xmm0
0x180005455  mov     [rsp+48h+var_28], r13; __int64
0x18000545a  lea     ebx, [r8-1]
0x18000545e  mov     ecx, ebx; int
0x180005460  call    MI_ReportErrorDetails_ForCustomError
0x180005465  jmp     loc_180005374
0x18000546a  mov     rax, cs:off_180047B90
0x180005471  mov     rcx, [rdi+50h]
0x180005475  mov     rax, [rax+8]
0x180005479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000547e  mov     [rbp+arg_8], rax
0x180005482  mov     rsi, rax
0x180005485  mov     [rbp+arg_30], r13
0x180005489  test    rax, rax
0x18000548c  jz      short loc_1800054A9
0x18000548e  mov     rax, [rax]
0x180005491  test    rax, rax
0x180005494  jz      short loc_1800054A9
0x180005496  mov     rax, [rax]
0x180005499  lea     rdx, [rbp+arg_30]
0x18000549d  mov     rcx, rsi
0x1800054a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054a5  mov     rsi, [rbp+arg_8]
0x1800054a9  test    bl, bl
0x1800054ab  jz      short loc_1800054F2
0x1800054ad  mov     rax, cs:off_180047BA0
0x1800054b4  lea     r9, [rbp+arg_8]
0x1800054b8  mov     r8, r12
0x1800054bb  lea     rdx, [rdi+74h]
0x1800054bf  mov     rcx, rsi
0x1800054c2  mov     rax, [rax+48h]
0x1800054c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054cb  mov     ebx, eax
0x1800054cd  test    rsi, rsi
0x1800054d0  jz      short loc_1800054E6
0x1800054d2  mov     rax, [rsi]
0x1800054d5  test    rax, rax
0x1800054d8  jz      short loc_1800054E6
0x1800054da  mov     rax, [rax+10h]
0x1800054de  mov     rcx, rsi
0x1800054e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054e6  test    ebx, ebx
0x1800054e8  jnz     loc_180005374
0x1800054ee  mov     rsi, [rbp+arg_8]
0x1800054f2  test    r15b, r15b
0x1800054f5  jz      short loc_18000553C
0x1800054f7  mov     rax, cs:off_180047BA0
0x1800054fe  lea     r9, [rbp+arg_8]
0x180005502  mov     r8, r12
0x180005505  lea     rdx, [rdi+74h]
0x180005509  mov     rcx, rsi
0x18000550c  mov     rax, [rax+50h]
0x180005510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005515  mov     ebx, eax
0x180005517  test    rsi, rsi
0x18000551a  jz      short loc_180005530
0x18000551c  mov     rax, [rsi]
0x18000551f  test    rax, rax
0x180005522  jz      short loc_180005530
0x180005524  mov     rax, [rax+10h]
0x180005528  mov     rcx, rsi
0x18000552b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005530  test    ebx, ebx
0x180005532  jnz     loc_180005374
0x180005538  mov     rsi, [rbp+arg_8]
0x18000553c  mov     rax, [rdi]
0x18000553f  lea     r8, [rbp+arg_30]
0x180005543  mov     [rbp+arg_30], rsi
0x180005547  mov     r9d, 0Fh
0x18000554d  xor     edx, edx
0x18000554f  mov     dword ptr [rsp+48h+var_28], 40000000h
0x180005557  mov     rcx, rdi
0x18000555a  mov     rax, [rax+50h]
0x18000555e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005563  mov     ebx, eax
0x180005565  test    eax, eax
0x180005567  jnz     loc_180005374
0x18000556d  test    r14, r14
0x180005570  jz      loc_18000536F
0x180005576  mov     rax, [r14]
0x180005579  test    rax, rax
0x18000557c  jz      loc_18000536F
0x180005582  mov     rax, [rax+8]
0x180005586  mov     rdx, rdi
0x180005589  mov     rcx, r14
0x18000558c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005591  mov     ebx, eax
0x180005593  jmp     loc_180005374
```
