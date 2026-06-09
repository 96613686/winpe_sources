# SetMsChapMppeKeys

- ea: `0x180003308`
- end: `0x1800034cb`
- name: `SetMsChapMppeKeys`
- size: `451`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, __int128 *, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003770`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x180003308`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x18000346c`: `RasCompressionSetInfo failed, Error=%d`

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
  v16 = (*((__int64 (__fastcall **)(__int64, __int64 *, __int64 *))&xmmword_18004C490 + 1))(a1, &v26, &v18);
  v17 = v16;
  if ( v16 && byte_18004CF33 < 0 )
  {
    LOWORD(v34) = 0;
    FormatRRASErrorString(&v34, L"RasCompressionSetInfo failed, Error=%d", v16);
    if ( byte_18004CF33 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v34);
  }
  return v17;
}

```

## disassembly

```asm
0x180003308  push    rbp
0x18000330a  push    rbx
0x18000330b  push    rsi
0x18000330c  push    rdi
0x18000330d  push    r14
0x18000330f  lea     rbp, [rsp-0A10h]
0x180003317  sub     rsp, 0B10h
0x18000331e  mov     rax, cs:__security_cookie
0x180003325  xor     rax, rsp
0x180003328  mov     [rbp+0A30h+var_30], rax
0x18000332f  mov     r14, r8
0x180003332  mov     rsi, rdx
0x180003335  mov     rbx, rcx
0x180003338  xor     edx, edx; Val
0x18000333a  mov     r8d, 170h; Size
0x180003340  lea     rcx, [rsp+0B30h+var_B10]; void *
0x180003345  mov     rdi, r9
0x180003348  call    memset_0
0x18000334d  xor     eax, eax
0x18000334f  lea     rcx, [rbp+0A30h+var_82C]; void *
0x180003356  xor     edx, edx; Val
0x180003358  mov     [rbp+0A30h+var_830], eax
0x18000335e  mov     r8d, 7FCh; Size
0x180003364  call    memset_0
0x180003369  cmp     dword ptr [rsi+4], 1Eh
0x18000336d  jnb     short loc_180003379
0x18000336f  mov     eax, 57h ; 'W'
0x180003374  jmp     loc_1800034AE
0x180003379  xor     edx, edx; Val
0x18000337b  lea     rcx, [rbp+0A30h+var_9A0]; void *
0x180003382  mov     r8d, 170h; Size
0x180003388  call    memset_0
0x18000338d  cmp     [rbp+0A30h+arg_20], 0C223h
0x180003397  mov     r8d, 4
0x18000339d  mov     rdx, [rsi+8]
0x1800033a1  mov     rcx, [r14]
0x1800033a4  movsd   xmm1, qword ptr [rdi+10h]
0x1800033a9  mov     [rbp+0A30h+var_960], 0FFh
0x1800033b0  mov     rax, [rdx+6]
0x1800033b4  mov     [rbp+0A30h+var_9A0], rax
0x1800033bb  movups  xmm0, xmmword ptr [rdx+0Eh]
0x1800033bf  mov     [rbp+0A30h+var_988], rcx
0x1800033c6  movsd   [rbp+0A30h+var_970], xmm1
0x1800033ce  movdqu  [rbp+0A30h+var_998], xmm0
0x1800033d6  mov     [rbp+0A30h+var_938], r8d
0x1800033dd  movaps  xmm0, xmmword ptr [rdi]
0x1800033e0  movaps  [rbp+0A30h+var_980], xmm0
0x1800033e7  mov     [rsp+0B30h+var_AD0], 0FFh
0x1800033ec  mov     rax, [rdx+6]
0x1800033f0  mov     [rsp+0B30h+var_B10], rax
0x1800033f5  lea     eax, [r8-2]
0x1800033f9  movups  xmm0, xmmword ptr [rdx+0Eh]
0x1800033fd  mov     [rsp+0B30h+var_AF8], rcx
0x180003402  movsd   [rsp+0B30h+var_AE0], xmm1
0x180003408  movdqu  [rsp+0B30h+var_B08], xmm0
0x18000340e  mov     [rbp+0A30h+var_AA8], r8d
0x180003412  movaps  xmm0, xmmword ptr [rdi]
0x180003415  movaps  [rsp+0B30h+var_AF0], xmm0
0x18000341a  mov     [rbp+0A30h+var_964], eax
0x180003420  mov     [rsp+0B30h+var_AD4], eax
0x180003424  jnz     short loc_180003440
0x180003426  cmp     [rbp+0A30h+arg_28], 80h
0x180003430  jnz     short loc_180003440
0x180003432  lea     eax, [r8-3]
0x180003436  mov     [rbp+0A30h+var_964], eax
0x18000343c  mov     [rsp+0B30h+var_AD4], eax
0x180003440  mov     rax, qword ptr cs:xmmword_18004C490+8
0x180003447  lea     r8, [rsp+0B30h+var_B10]
0x18000344c  lea     rdx, [rbp+0A30h+var_9A0]
0x180003453  mov     rcx, rbx
0x180003456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000345b  mov     ebx, eax
0x18000345d  test    eax, eax
0x18000345f  jz      short loc_1800034AC
0x180003461  cmp     cs:byte_18004CF33, 0
0x180003468  jge     short loc_1800034AC
0x18000346a  xor     ecx, ecx
0x18000346c  lea     rdx, aRascompression; "RasCompressionSetInfo failed, Error=%d"
0x180003473  mov     word ptr [rbp+0A30h+var_830], cx
0x18000347a  mov     r8d, eax
0x18000347d  lea     rcx, [rbp+0A30h+var_830]
0x180003484  call    FormatRRASErrorString
0x180003489  cmp     cs:byte_18004CF33, 0
0x180003490  jge     short loc_1800034AC
0x180003492  lea     r8, [rbp+0A30h+var_830]
0x180003499  lea     rdx, RasPppTraceError
0x1800034a0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800034a7  call    McTemplateU0z_EventWriteTransfer
0x1800034ac  mov     eax, ebx
0x1800034ae  mov     rcx, [rbp+0A30h+var_30]
0x1800034b5  xor     rcx, rsp; StackCookie
0x1800034b8  call    __security_check_cookie
0x1800034bd  add     rsp, 0B10h
0x1800034c4  pop     r14
0x1800034c6  pop     rdi
0x1800034c7  pop     rsi
0x1800034c8  pop     rbx
0x1800034c9  pop     rbp
0x1800034ca  retn
```
