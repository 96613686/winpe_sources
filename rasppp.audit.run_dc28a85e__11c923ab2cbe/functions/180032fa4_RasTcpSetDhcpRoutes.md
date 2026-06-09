# RasTcpSetDhcpRoutes

- ea: `0x180032fa4`
- end: `0x1800332fd`
- name: `RasTcpSetDhcpRoutes`
- size: `857`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001dcb0`
- `0x18001f760`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002b0dc`
- `0x18003230c`
- `0x180032fa4`
- `0x180033304`
- `0x180034010`

## string_xrefs

- `0x180033252`: `RasTcpSetDhcpRoutes: invalid destination descriptor first byte %d`
- `0x180033280`: `RasTcpSetDhcpRoutes: invalid destination descriptor first byte %d`

## pseudocode

```c
unsigned __int64 __fastcall RasTcpSetDhcpRoutes(unsigned int *a1, DWORD a2, int a3)
{
  __int64 v3; // rdi
  unsigned __int8 *v4; // r12
  unsigned __int64 result; // rax
  unsigned int v7; // ecx
  unsigned __int8 v8; // r8
  DWORD v9; // r13d
  unsigned int v10; // ebx
  __int64 v11; // rdi
  int v12; // edx
  __int64 v13; // rsi
  unsigned __int8 *v14; // r12
  unsigned int v15; // edx
  char v16; // al
  __int64 v17; // rcx
  __int64 v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+28h] [rbp-D8h]
  __int64 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  __int64 v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  unsigned __int64 v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  int v31; // [rsp+88h] [rbp-78h]
  DWORD v32; // [rsp+8Ch] [rbp-74h]
  unsigned __int64 v33; // [rsp+90h] [rbp-70h]
  _DWORD v34[2]; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v35[4]; // [rsp+A0h] [rbp-60h]
  int v36; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v37[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v3 = *a1;
  v4 = (unsigned __int8 *)(a1 + 1);
  v31 = a3;
  v32 = a2;
  v28 = 0xFEFCF8F0E0C08000uLL;
  v36 = 0;
  LOBYTE(v29) = -1;
  memset_0(v37, 0, sizeof(v37));
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( qword_18004D648 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004D648,
        L"RasTcpSetDhcpRoutes Begin");
  }
  else
  {
    TraceHlp("RasTcpSetDhcpRoutes Begin");
  }
  result = (unsigned __int64)a1 + v3 + 1;
  v33 = result;
  while ( 1 )
  {
    if ( (unsigned __int64)v4 >= result )
      goto LABEL_24;
    v7 = *v4;
    v8 = 0;
    v9 = 0;
    v30 = 0;
    v35[0] = 0;
    v34[0] = 0;
    if ( (unsigned __int8)v7 > 0x20u )
      break;
    v10 = v7 >> 3;
    v11 = v7 >> 3;
    v12 = (int)v7 % 8;
    v13 = (int)v7 % 8;
    if ( v7 >> 3 )
    {
      LOBYTE(v12) = -1;
      memset_0(v34, v12, v10);
      v8 = v30;
      v9 = v34[0];
    }
    if ( (_DWORD)v13 )
    {
      ++v10;
      *((_BYTE *)v34 + v11) = *((_BYTE *)&v28 + v13);
      v9 = v34[0];
    }
    v14 = v4 + 1;
    v15 = 0;
    if ( v10 )
    {
      do
      {
        v16 = *v14++;
        v17 = v15++;
        *((_BYTE *)v35 + v17) = v16;
      }
      while ( (int)v15 < (int)v10 );
      v8 = v35[0];
      v30 = v35[0];
    }
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004D648 )
      {
        LODWORD(v27) = v14[3];
        LODWORD(v26) = v14[2];
        LODWORD(v25) = v14[1];
        LODWORD(v24) = *v14;
        LODWORD(v23) = HIBYTE(v34[0]);
        LOWORD(v36) = 0;
        LODWORD(v22) = BYTE2(v34[0]);
        LODWORD(v21) = BYTE1(v34[0]);
        LODWORD(v20) = (unsigned __int8)v9;
        LODWORD(v19) = HIBYTE(v35[0]);
        LODWORD(v18) = BYTE2(v35[0]);
        FormatRRASErrorString(
          &v36,
          L"RasTcpSetDhcpRoutes: Got route dest addr = %d.%d.%d.%d   subnet mask = %d.%d.%d.%d    route = %d.%d.%d.%d\n",
          v8,
          BYTE1(v35[0]),
          v18,
          v19,
          v20,
          v21,
          v22,
          v23,
          v24,
          v25,
          v26,
          v27,
          v28,
          v29);
        ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004D648, &v36);
      }
    }
    else
    {
      TraceHlp("RasTcpSetDhcpRoutes: Got route dest addr = %d.%d.%d.%d   subnet mask = %d.%d.%d.%d    route = %d.%d.%d.%d\n");
    }
    RasTcpSetRoute(v30, v32, v9, v32, v31);
    result = v33;
    v4 = v14 + 4;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( !qword_18004D640 )
      goto LABEL_25;
    LOWORD(v36) = 0;
    FormatRRASErrorString(&v36, L"RasTcpSetDhcpRoutes: invalid destination descriptor first byte %d", v7);
    result = ((__int64 (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(
               gIphlpEtwContext,
               qword_18004D640,
               &v36);
  }
  else
  {
    result = TraceHlp("RasTcpSetDhcpRoutes: invalid destination descriptor first byte %d");
  }
LABEL_24:
  if ( !gIsIphlpEtwTracingAvailable )
    return TraceHlp("RasTcpSetDhcpRoutes End");
LABEL_25:
  if ( qword_18004D648 )
    return ((__int64 (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
             gIphlpEtwContext,
             qword_18004D648,
             L"RasTcpSetDhcpRoutes End");
  if ( !gIsIphlpEtwTracingAvailable )
    return TraceHlp("RasTcpSetDhcpRoutes End");
  return result;
}

```

## disassembly

```asm
0x180032fa4  mov     [rsp-8+arg_10], rbx
0x180032fa9  push    rbp
0x180032faa  push    rsi
0x180032fab  push    rdi
0x180032fac  push    r12
0x180032fae  push    r13
0x180032fb0  push    r14
0x180032fb2  push    r15
0x180032fb4  lea     rbp, [rsp-7C0h]
0x180032fbc  sub     rsp, 8C0h
0x180032fc3  mov     rax, cs:__security_cookie
0x180032fca  xor     rax, rsp
0x180032fcd  mov     [rbp+7F0h+var_40], rax
0x180032fd4  mov     edi, [rcx]
0x180032fd6  lea     r12, [rcx+4]
0x180032fda  mov     [rbp+7F0h+var_868], r8d
0x180032fde  mov     rbx, rcx
0x180032fe1  mov     [rbp+7F0h+var_864], edx
0x180032fe4  lea     rcx, [rbp+7F0h+var_83C]; void *
0x180032fe8  xor     r14d, r14d
0x180032feb  mov     [rsp+8F0h+var_880], 0E0C08000h
0x180032ff3  xor     edx, edx; Val
0x180032ff5  mov     [rbp+7F0h+var_840], r14d
0x180032ff9  mov     r8d, 7FCh; Size
0x180032fff  mov     [rsp+8F0h+var_87C], 0FEFCF8F0h
0x180033007  mov     byte ptr [rsp+8F0h+var_878], 0FFh
0x18003300c  call    memset_0
0x180033011  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x180033018  jz      short loc_180033042
0x18003301a  mov     rdx, cs:qword_18004D648
0x180033021  test    rdx, rdx
0x180033024  jz      short loc_18003304E
0x180033026  mov     rcx, cs:gIphlpEtwContext
0x18003302d  lea     r8, aRastcpsetdhcpr; "RasTcpSetDhcpRoutes Begin"
0x180033034  mov     rax, cs:gIphlpTemplateFunc
0x18003303b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033040  jmp     short loc_18003304E
0x180033042  lea     rcx, aRastcpsetdhcpr_0; "RasTcpSetDhcpRoutes Begin"
0x180033049  call    TraceHlp
0x18003304e  lea     rax, [rdi+1]
0x180033052  add     rax, rbx
0x180033055  mov     [rbp+7F0h+var_860], rax
0x180033059  cmp     r12, rax
0x18003305c  jnb     loc_18003328C
0x180033062  movzx   ecx, byte ptr [r12]
0x180033067  xor     r8d, r8d
0x18003306a  xor     r13d, r13d
0x18003306d  mov     [rbp+7F0h+var_870], r8
0x180033071  mov     [rbp+7F0h+var_850], r8d
0x180033075  mov     [rbp+7F0h+var_858], r13d
0x180033079  cmp     cl, 20h ; ' '
0x18003307c  ja      loc_180033234
0x180033082  mov     eax, ecx
0x180033084  mov     ebx, ecx
0x180033086  cdq
0x180033087  shr     ebx, 3
0x18003308a  lea     ecx, [r8+8]
0x18003308e  mov     edi, ebx
0x180033090  idiv    ecx
0x180033092  movsxd  rsi, edx
0x180033095  test    ebx, ebx
0x180033097  jz      short loc_1800330AF
0x180033099  mov     r8d, ebx; Size
0x18003309c  lea     rcx, [rbp+7F0h+var_858]; void *
0x1800330a0  mov     dl, 0FFh; Val
0x1800330a2  call    memset_0
0x1800330a7  mov     r8, [rbp+7F0h+var_870]
0x1800330ab  mov     r13d, [rbp+7F0h+var_858]
0x1800330af  test    esi, esi
0x1800330b1  jz      short loc_1800330C1
0x1800330b3  mov     cl, byte ptr [rsp+rsi+8F0h+var_880]
0x1800330b7  inc     ebx
0x1800330b9  mov     byte ptr [rbp+rdi+7F0h+var_858], cl
0x1800330bd  mov     r13d, [rbp+7F0h+var_858]
0x1800330c1  inc     r12
0x1800330c4  mov     edx, r14d
0x1800330c7  test    ebx, ebx
0x1800330c9  jz      short loc_1800330E6
0x1800330cb  mov     al, [r12]
0x1800330cf  inc     r12
0x1800330d2  mov     ecx, edx
0x1800330d4  inc     edx
0x1800330d6  mov     byte ptr [rbp+rcx+7F0h+var_850], al
0x1800330da  cmp     edx, ebx
0x1800330dc  jl      short loc_1800330CB
0x1800330de  mov     r8d, [rbp+7F0h+var_850]
0x1800330e2  mov     [rbp+7F0h+var_870], r8
0x1800330e6  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x1800330ed  jz      loc_18003319B
0x1800330f3  cmp     cs:qword_18004D648, r14
0x1800330fa  jz      loc_18003320E
0x180033100  movzx   r10d, byte ptr [r12+3]
0x180033106  movzx   r11d, byte ptr [r12+2]
0x18003310c  movzx   ebx, byte ptr [r12+1]
0x180033112  movzx   edi, byte ptr [r12]
0x180033117  movzx   ecx, byte ptr [rbp+7F0h+var_850+3]
0x18003311b  movzx   edx, byte ptr [rbp+7F0h+var_850+2]
0x18003311f  movzx   esi, byte ptr [rbp+7F0h+var_858+3]
0x180033123  movzx   r15d, byte ptr [rbp+7F0h+var_858+1]
0x180033128  movzx   r9d, byte ptr [rbp+7F0h+var_850+1]
0x18003312d  mov     dword ptr [rsp+8F0h+var_888], r10d
0x180033132  mov     dword ptr [rsp+8F0h+var_890], r11d
0x180033137  mov     dword ptr [rsp+8F0h+var_898], ebx
0x18003313b  mov     dword ptr [rsp+8F0h+var_8A0], edi
0x18003313f  mov     dword ptr [rsp+8F0h+var_8A8], esi
0x180033143  mov     word ptr [rbp+7F0h+var_840], r14w
0x180033148  movzx   r14d, byte ptr [rbp+7F0h+var_858+2]
0x18003314d  mov     dword ptr [rsp+8F0h+var_8B0], r14d
0x180033152  mov     dword ptr [rsp+8F0h+var_8B8], r15d
0x180033157  movzx   eax, r13b
0x18003315b  mov     dword ptr [rsp+8F0h+var_8C0], eax
0x18003315f  mov     dword ptr [rsp+8F0h+var_8C8], ecx
0x180033163  lea     rcx, [rbp+7F0h+var_840]
0x180033167  mov     dword ptr [rsp+8F0h+var_8D0], edx
0x18003316b  lea     rdx, aRastcpsetdhcpr_4; "RasTcpSetDhcpRoutes: Got route dest add"...
0x180033172  movzx   r8d, r8b
0x180033176  call    FormatRRASErrorString
0x18003317b  mov     rdx, cs:qword_18004D648
0x180033182  lea     r8, [rbp+7F0h+var_840]
0x180033186  mov     rcx, cs:gIphlpEtwContext
0x18003318d  mov     rax, cs:gIphlpTemplateFunc
0x180033194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033199  jmp     short loc_18003320B
0x18003319b  movzx   ecx, byte ptr [r12+3]
0x1800331a1  movzx   r11d, byte ptr [r12+2]
0x1800331a7  movzx   ebx, byte ptr [r12+1]
0x1800331ad  movzx   edi, byte ptr [r12]
0x1800331b2  movzx   r10d, byte ptr [rbp+7F0h+var_850+3]
0x1800331b7  movzx   esi, byte ptr [rbp+7F0h+var_858+3]
0x1800331bb  movzx   r14d, byte ptr [rbp+7F0h+var_858+2]
0x1800331c0  movzx   r15d, byte ptr [rbp+7F0h+var_858+1]
0x1800331c5  movzx   r9d, byte ptr [rbp+7F0h+var_850+2]
0x1800331ca  movzx   r8d, byte ptr [rbp+7F0h+var_850+1]
0x1800331cf  movzx   edx, byte ptr [rbp+7F0h+var_870]
0x1800331d3  mov     dword ptr [rsp+8F0h+var_890], ecx
0x1800331d7  lea     rcx, aRastcpsetdhcpr_6; "RasTcpSetDhcpRoutes: Got route dest add"...
0x1800331de  mov     dword ptr [rsp+8F0h+var_898], r11d
0x1800331e3  mov     dword ptr [rsp+8F0h+var_8A0], ebx
0x1800331e7  mov     dword ptr [rsp+8F0h+var_8A8], edi
0x1800331eb  mov     dword ptr [rsp+8F0h+var_8B0], esi
0x1800331ef  mov     dword ptr [rsp+8F0h+var_8B8], r14d
0x1800331f4  movzx   eax, r13b
0x1800331f8  mov     dword ptr [rsp+8F0h+var_8C0], r15d
0x1800331fd  mov     dword ptr [rsp+8F0h+var_8C8], eax
0x180033201  mov     dword ptr [rsp+8F0h+var_8D0], r10d
0x180033206  call    TraceHlp
0x18003320b  xor     r14d, r14d
0x18003320e  mov     r9d, [rbp+7F0h+var_864]
0x180033212  mov     r8d, r13d
0x180033215  mov     eax, [rbp+7F0h+var_868]
0x180033218  mov     edx, r9d
0x18003321b  mov     ecx, dword ptr [rbp+7F0h+var_870]
0x18003321e  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x180033222  call    RasTcpSetRoute
0x180033227  mov     rax, [rbp+7F0h+var_860]
0x18003322b  add     r12, 4
0x18003322f  jmp     loc_180033059
0x180033234  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18003323b  jz      short loc_18003327E
0x18003323d  cmp     cs:qword_18004D640, r14
0x180033244  jz      short loc_180033295
0x180033246  mov     r8d, ecx
0x180033249  mov     word ptr [rbp+7F0h+var_840], r14w
0x18003324e  lea     rcx, [rbp+7F0h+var_840]
0x180033252  lea     rdx, aRastcpsetdhcpr_5; "RasTcpSetDhcpRoutes: invalid destinatio"...
0x180033259  call    FormatRRASErrorString
0x18003325e  mov     rdx, cs:qword_18004D640
0x180033265  lea     r8, [rbp+7F0h+var_840]
0x180033269  mov     rcx, cs:gIphlpEtwContext
0x180033270  mov     rax, cs:gIphlpTemplateFunc
0x180033277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003327c  jmp     short loc_18003328C
0x18003327e  mov     edx, ecx
0x180033280  lea     rcx, aRastcpsetdhcpr_2; "RasTcpSetDhcpRoutes: invalid destinatio"...
0x180033287  call    TraceHlp
0x18003328c  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x180033293  jz      short loc_1800332C6
0x180033295  mov     rdx, cs:qword_18004D648
0x18003329c  test    rdx, rdx
0x18003329f  jz      short loc_1800332BD
0x1800332a1  mov     rcx, cs:gIphlpEtwContext
0x1800332a8  lea     r8, aRastcpsetdhcpr_1; "RasTcpSetDhcpRoutes End"
0x1800332af  mov     rax, cs:gIphlpTemplateFunc
0x1800332b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332bb  jmp     short loc_1800332D2
0x1800332bd  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x1800332c4  jnz     short loc_1800332D2
0x1800332c6  lea     rcx, aRastcpsetdhcpr_3; "RasTcpSetDhcpRoutes End"
0x1800332cd  call    TraceHlp
0x1800332d2  mov     rcx, [rbp+7F0h+var_40]
0x1800332d9  xor     rcx, rsp; StackCookie
0x1800332dc  call    __security_check_cookie
0x1800332e1  mov     rbx, [rsp+8F0h+arg_10]
0x1800332e9  add     rsp, 8C0h
0x1800332f0  pop     r15
0x1800332f2  pop     r14
0x1800332f4  pop     r13
0x1800332f6  pop     r12
0x1800332f8  pop     rdi
0x1800332f9  pop     rsi
0x1800332fa  pop     rbp
0x1800332fb  retn
```
