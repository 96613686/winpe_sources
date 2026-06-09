# SetMsChapMppeKeys

- ea: `0x18000339c`
- end: `0x180003560`
- name: `SetMsChapMppeKeys`
- size: `452`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, __int128 *, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000380c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000339c`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x180003500`: `RasCompressionSetInfo failed, Error=%d`

## pseudocode

```c
__int64 __fastcall SetMsChapMppeKeys(__int64 a1, __int64 a2, __int64 *a3, __int128 *a4, int a5, int a6)
{
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // xmm1_8
  __int128 v14; // xmm0
  __int128 v15; // xmm0
  unsigned int v16; // eax
  unsigned int v17; // ebx
  __int64 v18; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v19; // [rsp+28h] [rbp-D8h]
  __int64 v20; // [rsp+38h] [rbp-C8h]
  __int128 v21; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+50h] [rbp-B0h]
  int v23; // [rsp+5Ch] [rbp-A4h]
  char v24; // [rsp+60h] [rbp-A0h]
  int v25; // [rsp+88h] [rbp-78h]
  __int64 v26; // [rsp+190h] [rbp+90h] BYREF
  __int128 v27; // [rsp+198h] [rbp+98h]
  __int64 v28; // [rsp+1A8h] [rbp+A8h]
  __int128 v29; // [rsp+1B0h] [rbp+B0h]
  __int64 v30; // [rsp+1C0h] [rbp+C0h]
  int v31; // [rsp+1CCh] [rbp+CCh]
  char v32; // [rsp+1D0h] [rbp+D0h]
  int v33; // [rsp+1F8h] [rbp+F8h]
  int v34; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v35[2044]; // [rsp+304h] [rbp+204h] BYREF

  memset_0(&v18, 0, 0x170u);
  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  if ( *(_DWORD *)(a2 + 4) < 0x1Eu )
    return 87;
  memset_0(&v26, 0, 0x170u);
  v11 = *(_QWORD *)(a2 + 8);
  v12 = *a3;
  v13 = *((_QWORD *)a4 + 2);
  v32 = -1;
  v26 = *(_QWORD *)(v11 + 6);
  v14 = *(_OWORD *)(v11 + 14);
  v28 = v12;
  v30 = v13;
  v27 = v14;
  v33 = 4;
  v29 = *a4;
  v24 = -1;
  v18 = *(_QWORD *)(v11 + 6);
  v15 = *(_OWORD *)(v11 + 14);
  v20 = v12;
  v22 = v13;
  v19 = v15;
  v25 = 4;
  v21 = *a4;
  v31 = 2;
  v23 = 2;
  if ( a5 == 49699 && a6 == 128 )
  {
    v31 = 1;
    v23 = 1;
  }
  v16 = (*((__int64 (__fastcall **)(__int64, __int64 *, __int64 *))&xmmword_18004D490 + 1))(a1, &v26, &v18);
  v17 = v16;
  if ( v16 && byte_18004DF33 < 0 )
  {
    LOWORD(v34) = 0;
    FormatRRASErrorString((wchar_t *)&v34, L"RasCompressionSetInfo failed, Error=%d", v16);
    if ( byte_18004DF33 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasPppTraceError,
        (const wchar_t *)&v34);
  }
  return v17;
}

```

## disassembly

```asm
0x18000339c  push    rbp
0x18000339e  push    rbx
0x18000339f  push    rsi
0x1800033a0  push    rdi
0x1800033a1  push    r14
0x1800033a3  lea     rbp, [rsp-0A10h]
0x1800033ab  sub     rsp, 0B10h
0x1800033b2  mov     rax, cs:__security_cookie
0x1800033b9  xor     rax, rsp
0x1800033bc  mov     [rbp+0A30h+var_30], rax
0x1800033c3  mov     r14, r8
0x1800033c6  mov     rsi, rdx
0x1800033c9  mov     rbx, rcx
0x1800033cc  xor     edx, edx; Val
0x1800033ce  mov     r8d, 170h; Size
0x1800033d4  lea     rcx, [rsp+0B30h+var_B10]; void *
0x1800033d9  mov     rdi, r9
0x1800033dc  call    memset_0
0x1800033e1  xor     eax, eax
0x1800033e3  lea     rcx, [rbp+0A30h+var_82C]; void *
0x1800033ea  xor     edx, edx; Val
0x1800033ec  mov     [rbp+0A30h+var_830], eax
0x1800033f2  mov     r8d, 7FCh; Size
0x1800033f8  call    memset_0
0x1800033fd  cmp     dword ptr [rsi+4], 1Eh
0x180003401  jnb     short loc_18000340D
0x180003403  mov     eax, 57h ; 'W'
0x180003408  jmp     loc_180003542
0x18000340d  xor     edx, edx; Val
0x18000340f  lea     rcx, [rbp+0A30h+var_9A0]; void *
0x180003416  mov     r8d, 170h; Size
0x18000341c  call    memset_0
0x180003421  cmp     [rbp+0A30h+arg_20], 0C223h
0x18000342b  mov     r8d, 4
0x180003431  mov     rdx, [rsi+8]
0x180003435  mov     rcx, [r14]
0x180003438  movsd   xmm1, qword ptr [rdi+10h]
0x18000343d  mov     [rbp+0A30h+var_960], 0FFh
0x180003444  mov     rax, [rdx+6]
0x180003448  mov     [rbp+0A30h+var_9A0], rax
0x18000344f  movups  xmm0, xmmword ptr [rdx+0Eh]
0x180003453  mov     [rbp+0A30h+var_988], rcx
0x18000345a  movsd   [rbp+0A30h+var_970], xmm1
0x180003462  movdqu  [rbp+0A30h+var_998], xmm0
0x18000346a  mov     [rbp+0A30h+var_938], r8d
0x180003471  movaps  xmm0, xmmword ptr [rdi]
0x180003474  movaps  [rbp+0A30h+var_980], xmm0
0x18000347b  mov     [rsp+0B30h+var_AD0], 0FFh
0x180003480  mov     rax, [rdx+6]
0x180003484  mov     [rsp+0B30h+var_B10], rax
0x180003489  lea     eax, [r8-2]
0x18000348d  movups  xmm0, xmmword ptr [rdx+0Eh]
0x180003491  mov     [rsp+0B30h+var_AF8], rcx
0x180003496  movsd   [rsp+0B30h+var_AE0], xmm1
0x18000349c  movdqu  [rsp+0B30h+var_B08], xmm0
0x1800034a2  mov     [rbp+0A30h+var_AA8], r8d
0x1800034a6  movaps  xmm0, xmmword ptr [rdi]
0x1800034a9  movaps  [rsp+0B30h+var_AF0], xmm0
0x1800034ae  mov     [rbp+0A30h+var_964], eax
0x1800034b4  mov     [rsp+0B30h+var_AD4], eax
0x1800034b8  jnz     short loc_1800034D4
0x1800034ba  cmp     [rbp+0A30h+arg_28], 80h
0x1800034c4  jnz     short loc_1800034D4
0x1800034c6  lea     eax, [r8-3]
0x1800034ca  mov     [rbp+0A30h+var_964], eax
0x1800034d0  mov     [rsp+0B30h+var_AD4], eax
0x1800034d4  mov     rax, qword ptr cs:xmmword_18004D490+8
0x1800034db  lea     r8, [rsp+0B30h+var_B10]
0x1800034e0  lea     rdx, [rbp+0A30h+var_9A0]
0x1800034e7  mov     rcx, rbx
0x1800034ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ef  mov     ebx, eax
0x1800034f1  test    eax, eax
0x1800034f3  jz      short loc_180003540
0x1800034f5  cmp     cs:byte_18004DF33, 0
0x1800034fc  jge     short loc_180003540
0x1800034fe  xor     ecx, ecx
0x180003500  lea     rdx, aRascompression; "RasCompressionSetInfo failed, Error=%d"
0x180003507  mov     word ptr [rbp+0A30h+var_830], cx
0x18000350e  mov     r8d, eax
0x180003511  lea     rcx, [rbp+0A30h+var_830]
0x180003518  call    FormatRRASErrorString
0x18000351d  cmp     cs:byte_18004DF33, 0
0x180003524  jge     short loc_180003540
0x180003526  lea     r8, [rbp+0A30h+var_830]
0x18000352d  lea     rdx, RasPppTraceError
0x180003534  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000353b  call    McTemplateU0z_EventWriteTransfer
0x180003540  mov     eax, ebx
0x180003542  mov     rcx, [rbp+0A30h+var_30]
0x180003549  xor     rcx, rsp; StackCookie
0x18000354c  call    __security_check_cookie
0x180003551  add     rsp, 0B10h
0x180003558  pop     r14
0x18000355a  pop     rdi
0x18000355b  pop     rsi
0x18000355c  pop     rbx
0x18000355d  pop     rbp
0x18000355e  retn
```
