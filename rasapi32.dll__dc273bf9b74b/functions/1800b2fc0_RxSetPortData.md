# RxSetPortData

- ea: `0x1800b2fc0`
- end: `0x1800b3249`
- name: `RxSetPortData`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800b90d4`

## callees

- `0x1800024f8`
- `0x1800b2fc0`
- `0x1800b4080`
- `0x1800ded50`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x1800b3011`
- `rtutils!TracePrintfExA` at `0x1800b3072`
- `rtutils!TracePrintfExA` at `0x1800b30a1`
- `rtutils!TracePrintfExA` at `0x1800b30ec`
- `rtutils!TracePrintfExA` at `0x1800b312b`
- `rtutils!TracePrintfExA` at `0x1800b3172`
- `rtutils!TracePrintfExA` at `0x1800b31a1`
- `rtutils!TracePrintfExA` at `0x1800b31e2`
- `rtutils!TracePrintfExA` at `0x1800b3011`
- `rtutils!TracePrintfExA` at `0x1800b3072`
- `rtutils!TracePrintfExA` at `0x1800b30a1`
- `rtutils!TracePrintfExA` at `0x1800b30ec`
- `rtutils!TracePrintfExA` at `0x1800b312b`
- `rtutils!TracePrintfExA` at `0x1800b3172`
- `rtutils!TracePrintfExA` at `0x1800b31a1`
- `rtutils!TracePrintfExA` at `0x1800b31e2`
- `rasman!RasPortSetInfo` at `0x1800b31c2`
- `rasman!RasPortSetInfo` at `0x1800b31c2`

## string_xrefs

- `0x1800b3068`: `RxSetPortData: StringCchCopyA Failed when SPF_DATABITS is set`
- `0x1800b3168`: `RxSetPortData: StringCchCopyA Failed when SPF_PARITY is set`
- `0x1800b30e2`: `RxSetPortData: StringCchCopyA Failed when SPF_STOPBITS is set`

## pseudocode

```c
__int64 __fastcall RxSetPortData(__int64 a1, __int64 a2)
{
  int v4; // esi
  char *v5; // rbx
  int v6; // eax
  HRESULT v7; // eax
  DWORD v8; // ecx
  int v9; // r9d
  HRESULT v10; // eax
  DWORD v11; // ecx
  int v12; // r9d
  HRESULT v13; // eax
  DWORD v14; // ecx
  int v15; // r9d
  int v16; // ebx
  int v17; // eax
  int v19; // [rsp+20h] [rbp-89h] BYREF
  char pszDest[32]; // [rsp+28h] [rbp-81h] BYREF
  int v21; // [rsp+48h] [rbp-61h]
  char v22; // [rsp+4Ch] [rbp-5Dh]
  int v23; // [rsp+50h] [rbp-59h]
  char v24; // [rsp+60h] [rbp-49h] BYREF

  if ( g_dwRasscrptTraceId != -1 )
    TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RxSetPortData");
  if ( !a1 || !a2 )
    return 2147500037LL;
  v4 = *(_DWORD *)(a2 + 16);
  v19 = 0;
  if ( (v4 & 1) != 0 )
  {
    v7 = StringCchCopyA(pszDest, 0x20u, "WordSize");
    v8 = g_dwRasscrptTraceId;
    if ( v7 && g_dwRasscrptTraceId != -1 )
    {
      TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RxSetPortData: StringCchCopyA Failed when SPF_DATABITS is set");
      v8 = g_dwRasscrptTraceId;
    }
    v9 = *(unsigned __int8 *)(a2 + 20);
    v23 = v9;
    v21 = 0;
    v22 = 0;
    if ( v8 != -1 )
      TracePrintfExA(v8, 0xCu, "GetDatabits==%d", v9);
    v5 = &v24;
    v6 = ++v19;
  }
  else
  {
    v5 = pszDest;
    v6 = 0;
  }
  if ( (v4 & 4) != 0 )
  {
    v10 = StringCchCopyA(v5, 0x20u, "StopBits");
    v11 = g_dwRasscrptTraceId;
    if ( v10 && g_dwRasscrptTraceId != -1 )
    {
      TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RxSetPortData: StringCchCopyA Failed when SPF_STOPBITS is set");
      v11 = g_dwRasscrptTraceId;
    }
    v12 = *(unsigned __int8 *)(a2 + 22);
    *((_DWORD *)v5 + 8) = 0;
    v5[36] = 0;
    *((_DWORD *)v5 + 10) = v12;
    if ( v12 == 1 )
    {
      *((_DWORD *)v5 + 10) = 0;
      v12 = 0;
    }
    if ( v11 != -1 )
      TracePrintfExA(v11, 0xCu, "GetStopbits==%d", v12);
    v6 = ++v19;
    v5 += 56;
  }
  if ( (v4 & 2) != 0 )
  {
    v13 = StringCchCopyA(v5, 0x20u, "Parity");
    v14 = g_dwRasscrptTraceId;
    if ( v13 && g_dwRasscrptTraceId != -1 )
    {
      TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RxSetPortData: StringCchCopyA Failed when SPF_PARITY is set");
      v14 = g_dwRasscrptTraceId;
    }
    v15 = *(unsigned __int8 *)(a2 + 21);
    *((_DWORD *)v5 + 10) = v15;
    *((_DWORD *)v5 + 8) = 0;
    v5[36] = 0;
    if ( v14 != -1 )
      TracePrintfExA(v14, 0xCu, "GetParity==%d", v15);
    v6 = ++v19;
  }
  if ( v6 )
  {
    v17 = RasPortSetInfo(*(_QWORD *)(a1 + 40), &v19);
    v16 = v17;
    if ( g_dwRasscrptTraceId != -1 )
      TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RasPortSetInfo==%d", v17);
    if ( v16 )
      Stxerr_Add(
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 112) + 1072LL) + 88LL),
        "set port",
        *(unsigned int *)(a2 + 8),
        2147500037LL);
  }
  else
  {
    v16 = 0;
  }
  return v16 != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x1800b2fc0  mov     [rsp-8+arg_8], rbx
0x1800b2fc5  mov     [rsp-8+arg_10], rsi
0x1800b2fca  push    rbp
0x1800b2fcb  push    rdi
0x1800b2fcc  push    r12
0x1800b2fce  push    r13
0x1800b2fd0  push    r14
0x1800b2fd2  lea     rbp, [rsp-37h]
0x1800b2fd7  sub     rsp, 0E0h
0x1800b2fde  mov     rax, cs:__security_cookie
0x1800b2fe5  xor     rax, rsp
0x1800b2fe8  mov     [rbp+57h+var_30], rax
0x1800b2fec  mov     r14, rcx
0x1800b2fef  or      r12d, 0FFFFFFFFh
0x1800b2ff3  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b2ff9  mov     rdi, rdx
0x1800b2ffc  mov     r13d, 0Ch
0x1800b3002  cmp     ecx, r12d
0x1800b3005  jz      short loc_1800B3017
0x1800b3007  lea     r8, aRxsetportdata; "RxSetPortData"
0x1800b300e  mov     edx, r13d; dwFlags
0x1800b3011  call    cs:__imp_TracePrintfExA
0x1800b3017  test    r14, r14
0x1800b301a  jz      loc_1800B321C
0x1800b3020  test    rdi, rdi
0x1800b3023  jz      loc_1800B321C
0x1800b3029  mov     esi, [rdi+10h]
0x1800b302c  mov     [rsp+100h+var_E0], 0
0x1800b3034  test    sil, 1
0x1800b3038  jnz     short loc_1800B3043
0x1800b303a  lea     rbx, [rsp+100h+pszDest]
0x1800b303f  xor     eax, eax
0x1800b3041  jmp     short loc_1800B30B5
0x1800b3043  lea     r8, aWordsize; "WordSize"
0x1800b304a  mov     edx, 20h ; ' '; cchDest
0x1800b304f  lea     rcx, [rsp+100h+pszDest]; pszDest
0x1800b3054  call    StringCchCopyA
0x1800b3059  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b305f  test    eax, eax
0x1800b3061  jz      short loc_1800B307E
0x1800b3063  cmp     ecx, r12d
0x1800b3066  jz      short loc_1800B307E
0x1800b3068  lea     r8, aRxsetportdataS_0; "RxSetPortData: StringCchCopyA Failed wh"...
0x1800b306f  mov     edx, r13d; dwFlags
0x1800b3072  call    cs:__imp_TracePrintfExA
0x1800b3078  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b307e  movzx   r9d, byte ptr [rdi+14h]
0x1800b3083  mov     [rbp+57h+var_B0], r9d
0x1800b3087  mov     [rbp+57h+var_B8], 0
0x1800b308e  mov     [rbp+57h+var_B4], 0
0x1800b3092  cmp     ecx, r12d
0x1800b3095  jz      short loc_1800B30A7
0x1800b3097  lea     r8, aGetdatabitsD; "GetDatabits==%d"
0x1800b309e  mov     edx, r13d; dwFlags
0x1800b30a1  call    cs:__imp_TracePrintfExA
0x1800b30a7  mov     eax, [rsp+100h+var_E0]
0x1800b30ab  lea     rbx, [rbp+57h+var_A0]
0x1800b30af  inc     eax
0x1800b30b1  mov     [rsp+100h+var_E0], eax
0x1800b30b5  test    sil, 4
0x1800b30b9  jz      loc_1800B313F
0x1800b30bf  lea     r8, aStopbits_0; "StopBits"
0x1800b30c6  mov     edx, 20h ; ' '; cchDest
0x1800b30cb  mov     rcx, rbx; pszDest
0x1800b30ce  call    StringCchCopyA
0x1800b30d3  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b30d9  test    eax, eax
0x1800b30db  jz      short loc_1800B30F8
0x1800b30dd  cmp     ecx, r12d
0x1800b30e0  jz      short loc_1800B30F8
0x1800b30e2  lea     r8, aRxsetportdataS; "RxSetPortData: StringCchCopyA Failed wh"...
0x1800b30e9  mov     edx, r13d; dwFlags
0x1800b30ec  call    cs:__imp_TracePrintfExA
0x1800b30f2  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b30f8  movzx   r9d, byte ptr [rdi+16h]
0x1800b30fd  mov     dword ptr [rbx+20h], 0
0x1800b3104  mov     byte ptr [rbx+24h], 0
0x1800b3108  mov     [rbx+28h], r9d
0x1800b310c  cmp     r9d, 1
0x1800b3110  jnz     short loc_1800B311C
0x1800b3112  mov     dword ptr [rbx+28h], 0
0x1800b3119  xor     r9d, r9d
0x1800b311c  cmp     ecx, r12d
0x1800b311f  jz      short loc_1800B3131
0x1800b3121  lea     r8, aGetstopbitsD; "GetStopbits==%d"
0x1800b3128  mov     edx, r13d; dwFlags
0x1800b312b  call    cs:__imp_TracePrintfExA
0x1800b3131  mov     eax, [rsp+100h+var_E0]
0x1800b3135  inc     eax
0x1800b3137  mov     [rsp+100h+var_E0], eax
0x1800b313b  add     rbx, 38h ; '8'
0x1800b313f  test    sil, 2
0x1800b3143  jz      short loc_1800B31B1
0x1800b3145  lea     r8, aParity_0; "Parity"
0x1800b314c  mov     edx, 20h ; ' '; cchDest
0x1800b3151  mov     rcx, rbx; pszDest
0x1800b3154  call    StringCchCopyA
0x1800b3159  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b315f  test    eax, eax
0x1800b3161  jz      short loc_1800B317E
0x1800b3163  cmp     ecx, r12d
0x1800b3166  jz      short loc_1800B317E
0x1800b3168  lea     r8, aRxsetportdataS_1; "RxSetPortData: StringCchCopyA Failed wh"...
0x1800b316f  mov     edx, r13d; dwFlags
0x1800b3172  call    cs:__imp_TracePrintfExA
0x1800b3178  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b317e  movzx   r9d, byte ptr [rdi+15h]
0x1800b3183  mov     [rbx+28h], r9d
0x1800b3187  mov     dword ptr [rbx+20h], 0
0x1800b318e  mov     byte ptr [rbx+24h], 0
0x1800b3192  cmp     ecx, r12d
0x1800b3195  jz      short loc_1800B31A7
0x1800b3197  lea     r8, aGetparityD; "GetParity==%d"
0x1800b319e  mov     edx, r13d; dwFlags
0x1800b31a1  call    cs:__imp_TracePrintfExA
0x1800b31a7  mov     eax, [rsp+100h+var_E0]
0x1800b31ab  inc     eax
0x1800b31ad  mov     [rsp+100h+var_E0], eax
0x1800b31b1  test    eax, eax
0x1800b31b3  jnz     short loc_1800B31B9
0x1800b31b5  xor     ebx, ebx
0x1800b31b7  jmp     short loc_1800B3211
0x1800b31b9  mov     rcx, [r14+28h]
0x1800b31bd  lea     rdx, [rsp+100h+var_E0]
0x1800b31c2  call    cs:__imp_RasPortSetInfo
0x1800b31c8  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b31ce  mov     ebx, eax
0x1800b31d0  cmp     ecx, r12d
0x1800b31d3  jz      short loc_1800B31E8
0x1800b31d5  mov     r9d, eax
0x1800b31d8  lea     r8, aRasportsetinfo_1; "RasPortSetInfo==%d"
0x1800b31df  mov     edx, r13d; dwFlags
0x1800b31e2  call    cs:__imp_TracePrintfExA
0x1800b31e8  test    ebx, ebx
0x1800b31ea  jz      short loc_1800B3211
0x1800b31ec  mov     rax, [r14+70h]
0x1800b31f0  lea     rdx, aSetPort; "set port"
0x1800b31f7  mov     r8d, [rdi+8]
0x1800b31fb  mov     r9d, 80004005h
0x1800b3201  mov     rcx, [rax+430h]
0x1800b3208  mov     rcx, [rcx+58h]
0x1800b320c  call    Stxerr_Add
0x1800b3211  neg     ebx
0x1800b3213  sbb     eax, eax
0x1800b3215  and     eax, 80004005h
0x1800b321a  jmp     short loc_1800B3221
0x1800b321c  mov     eax, 80004005h
0x1800b3221  mov     rcx, [rbp+57h+var_30]
0x1800b3225  xor     rcx, rsp; StackCookie
0x1800b3228  call    __security_check_cookie
0x1800b322d  lea     r11, [rsp+100h+var_20]
0x1800b3235  mov     rbx, [r11+38h]
0x1800b3239  mov     rsi, [r11+40h]
0x1800b323d  mov     rsp, r11
0x1800b3240  pop     r14
0x1800b3242  pop     r13
0x1800b3244  pop     r12
0x1800b3246  pop     rdi
0x1800b3247  pop     rbp
0x1800b3248  retn
```
