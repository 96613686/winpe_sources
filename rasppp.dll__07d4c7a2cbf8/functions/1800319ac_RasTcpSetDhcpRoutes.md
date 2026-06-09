# RasTcpSetDhcpRoutes

- ea: `0x1800319ac`
- end: `0x180031d04`
- name: `RasTcpSetDhcpRoutes`
- size: `856`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001d1d0`
- `0x18001ebd0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002a138`
- `0x180030da4`
- `0x1800319ac`
- `0x180031d0c`
- `0x180033010`

## string_xrefs

- `0x180031c5a`: `RasTcpSetDhcpRoutes: invalid destination descriptor first byte %d`
- `0x180031c88`: `RasTcpSetDhcpRoutes: invalid destination descriptor first byte %d`

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
    if ( qword_18004C648 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C648,
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
      if ( qword_18004C648 )
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
        ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004C648, &v36);
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
    if ( !qword_18004C640 )
      goto LABEL_25;
    LOWORD(v36) = 0;
    FormatRRASErrorString(&v36, L"RasTcpSetDhcpRoutes: invalid destination descriptor first byte %d", v7);
    result = ((__int64 (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(
               gIphlpEtwContext,
               qword_18004C640,
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
  if ( qword_18004C648 )
    return ((__int64 (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(
             gIphlpEtwContext,
             qword_18004C648,
             L"RasTcpSetDhcpRoutes End");
  if ( !gIsIphlpEtwTracingAvailable )
    return TraceHlp("RasTcpSetDhcpRoutes End");
  return result;
}

```

## disassembly

```asm
0x1800319ac  mov     [rsp-8+arg_10], rbx
0x1800319b1  push    rbp
0x1800319b2  push    rsi
0x1800319b3  push    rdi
0x1800319b4  push    r12
0x1800319b6  push    r13
0x1800319b8  push    r14
0x1800319ba  push    r15
0x1800319bc  lea     rbp, [rsp-7C0h]
0x1800319c4  sub     rsp, 8C0h
0x1800319cb  mov     rax, cs:__security_cookie
0x1800319d2  xor     rax, rsp
0x1800319d5  mov     [rbp+7F0h+var_40], rax
0x1800319dc  mov     edi, [rcx]
0x1800319de  lea     r12, [rcx+4]
0x1800319e2  mov     [rbp+7F0h+var_868], r8d
0x1800319e6  mov     rbx, rcx
0x1800319e9  mov     [rbp+7F0h+var_864], edx
0x1800319ec  lea     rcx, [rbp+7F0h+var_83C]; void *
0x1800319f0  xor     r14d, r14d
0x1800319f3  mov     [rsp+8F0h+var_880], 0E0C08000h
0x1800319fb  xor     edx, edx; Val
0x1800319fd  mov     [rbp+7F0h+var_840], r14d
0x180031a01  mov     r8d, 7FCh; Size
0x180031a07  mov     [rsp+8F0h+var_87C], 0FEFCF8F0h
0x180031a0f  mov     byte ptr [rsp+8F0h+var_878], 0FFh
0x180031a14  call    memset_0
0x180031a19  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x180031a20  jz      short loc_180031A4A
0x180031a22  mov     rdx, cs:qword_18004C648
0x180031a29  test    rdx, rdx
0x180031a2c  jz      short loc_180031A56
0x180031a2e  mov     rcx, cs:gIphlpEtwContext
0x180031a35  lea     r8, aRastcpsetdhcpr; "RasTcpSetDhcpRoutes Begin"
0x180031a3c  mov     rax, cs:gIphlpTemplateFunc
0x180031a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a48  jmp     short loc_180031A56
0x180031a4a  lea     rcx, aRastcpsetdhcpr_0; "RasTcpSetDhcpRoutes Begin"
0x180031a51  call    TraceHlp
0x180031a56  lea     rax, [rdi+1]
0x180031a5a  add     rax, rbx
0x180031a5d  mov     [rbp+7F0h+var_860], rax
0x180031a61  cmp     r12, rax
0x180031a64  jnb     loc_180031C94
0x180031a6a  movzx   ecx, byte ptr [r12]
0x180031a6f  xor     r8d, r8d
0x180031a72  xor     r13d, r13d
0x180031a75  mov     [rbp+7F0h+var_870], r8
0x180031a79  mov     [rbp+7F0h+var_850], r8d
0x180031a7d  mov     [rbp+7F0h+var_858], r13d
0x180031a81  cmp     cl, 20h ; ' '
0x180031a84  ja      loc_180031C3C
0x180031a8a  mov     eax, ecx
0x180031a8c  mov     ebx, ecx
0x180031a8e  cdq
0x180031a8f  shr     ebx, 3
0x180031a92  lea     ecx, [r8+8]
0x180031a96  mov     edi, ebx
0x180031a98  idiv    ecx
0x180031a9a  movsxd  rsi, edx
0x180031a9d  test    ebx, ebx
0x180031a9f  jz      short loc_180031AB7
0x180031aa1  mov     r8d, ebx; Size
0x180031aa4  lea     rcx, [rbp+7F0h+var_858]; void *
0x180031aa8  mov     dl, 0FFh; Val
0x180031aaa  call    memset_0
0x180031aaf  mov     r8, [rbp+7F0h+var_870]
0x180031ab3  mov     r13d, [rbp+7F0h+var_858]
0x180031ab7  test    esi, esi
0x180031ab9  jz      short loc_180031AC9
0x180031abb  mov     cl, byte ptr [rsp+rsi+8F0h+var_880]
0x180031abf  inc     ebx
0x180031ac1  mov     byte ptr [rbp+rdi+7F0h+var_858], cl
0x180031ac5  mov     r13d, [rbp+7F0h+var_858]
0x180031ac9  inc     r12
0x180031acc  mov     edx, r14d
0x180031acf  test    ebx, ebx
0x180031ad1  jz      short loc_180031AEE
0x180031ad3  mov     al, [r12]
0x180031ad7  inc     r12
0x180031ada  mov     ecx, edx
0x180031adc  inc     edx
0x180031ade  mov     byte ptr [rbp+rcx+7F0h+var_850], al
0x180031ae2  cmp     edx, ebx
0x180031ae4  jl      short loc_180031AD3
0x180031ae6  mov     r8d, [rbp+7F0h+var_850]
0x180031aea  mov     [rbp+7F0h+var_870], r8
0x180031aee  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x180031af5  jz      loc_180031BA3
0x180031afb  cmp     cs:qword_18004C648, r14
0x180031b02  jz      loc_180031C16
0x180031b08  movzx   r10d, byte ptr [r12+3]
0x180031b0e  movzx   r11d, byte ptr [r12+2]
0x180031b14  movzx   ebx, byte ptr [r12+1]
0x180031b1a  movzx   edi, byte ptr [r12]
0x180031b1f  movzx   ecx, byte ptr [rbp+7F0h+var_850+3]
0x180031b23  movzx   edx, byte ptr [rbp+7F0h+var_850+2]
0x180031b27  movzx   esi, byte ptr [rbp+7F0h+var_858+3]
0x180031b2b  movzx   r15d, byte ptr [rbp+7F0h+var_858+1]
0x180031b30  movzx   r9d, byte ptr [rbp+7F0h+var_850+1]
0x180031b35  mov     dword ptr [rsp+8F0h+var_888], r10d
0x180031b3a  mov     dword ptr [rsp+8F0h+var_890], r11d
0x180031b3f  mov     dword ptr [rsp+8F0h+var_898], ebx
0x180031b43  mov     dword ptr [rsp+8F0h+var_8A0], edi
0x180031b47  mov     dword ptr [rsp+8F0h+var_8A8], esi
0x180031b4b  mov     word ptr [rbp+7F0h+var_840], r14w
0x180031b50  movzx   r14d, byte ptr [rbp+7F0h+var_858+2]
0x180031b55  mov     dword ptr [rsp+8F0h+var_8B0], r14d
0x180031b5a  mov     dword ptr [rsp+8F0h+var_8B8], r15d
0x180031b5f  movzx   eax, r13b
0x180031b63  mov     dword ptr [rsp+8F0h+var_8C0], eax
0x180031b67  mov     dword ptr [rsp+8F0h+var_8C8], ecx
0x180031b6b  lea     rcx, [rbp+7F0h+var_840]
0x180031b6f  mov     dword ptr [rsp+8F0h+var_8D0], edx
0x180031b73  lea     rdx, aRastcpsetdhcpr_4; "RasTcpSetDhcpRoutes: Got route dest add"...
0x180031b7a  movzx   r8d, r8b
0x180031b7e  call    FormatRRASErrorString
0x180031b83  mov     rdx, cs:qword_18004C648
0x180031b8a  lea     r8, [rbp+7F0h+var_840]
0x180031b8e  mov     rcx, cs:gIphlpEtwContext
0x180031b95  mov     rax, cs:gIphlpTemplateFunc
0x180031b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ba1  jmp     short loc_180031C13
0x180031ba3  movzx   ecx, byte ptr [r12+3]
0x180031ba9  movzx   r11d, byte ptr [r12+2]
0x180031baf  movzx   ebx, byte ptr [r12+1]
0x180031bb5  movzx   edi, byte ptr [r12]
0x180031bba  movzx   r10d, byte ptr [rbp+7F0h+var_850+3]
0x180031bbf  movzx   esi, byte ptr [rbp+7F0h+var_858+3]
0x180031bc3  movzx   r14d, byte ptr [rbp+7F0h+var_858+2]
0x180031bc8  movzx   r15d, byte ptr [rbp+7F0h+var_858+1]
0x180031bcd  movzx   r9d, byte ptr [rbp+7F0h+var_850+2]
0x180031bd2  movzx   r8d, byte ptr [rbp+7F0h+var_850+1]
0x180031bd7  movzx   edx, byte ptr [rbp+7F0h+var_870]
0x180031bdb  mov     dword ptr [rsp+8F0h+var_890], ecx
0x180031bdf  lea     rcx, aRastcpsetdhcpr_6; "RasTcpSetDhcpRoutes: Got route dest add"...
0x180031be6  mov     dword ptr [rsp+8F0h+var_898], r11d
0x180031beb  mov     dword ptr [rsp+8F0h+var_8A0], ebx
0x180031bef  mov     dword ptr [rsp+8F0h+var_8A8], edi
0x180031bf3  mov     dword ptr [rsp+8F0h+var_8B0], esi
0x180031bf7  mov     dword ptr [rsp+8F0h+var_8B8], r14d
0x180031bfc  movzx   eax, r13b
0x180031c00  mov     dword ptr [rsp+8F0h+var_8C0], r15d
0x180031c05  mov     dword ptr [rsp+8F0h+var_8C8], eax
0x180031c09  mov     dword ptr [rsp+8F0h+var_8D0], r10d
0x180031c0e  call    TraceHlp
0x180031c13  xor     r14d, r14d
0x180031c16  mov     r9d, [rbp+7F0h+var_864]
0x180031c1a  mov     r8d, r13d
0x180031c1d  mov     eax, [rbp+7F0h+var_868]
0x180031c20  mov     edx, r9d
0x180031c23  mov     ecx, dword ptr [rbp+7F0h+var_870]
0x180031c26  mov     dword ptr [rsp+8F0h+var_8D0], eax
0x180031c2a  call    RasTcpSetRoute
0x180031c2f  mov     rax, [rbp+7F0h+var_860]
0x180031c33  add     r12, 4
0x180031c37  jmp     loc_180031A61
0x180031c3c  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x180031c43  jz      short loc_180031C86
0x180031c45  cmp     cs:qword_18004C640, r14
0x180031c4c  jz      short loc_180031C9D
0x180031c4e  mov     r8d, ecx
0x180031c51  mov     word ptr [rbp+7F0h+var_840], r14w
0x180031c56  lea     rcx, [rbp+7F0h+var_840]
0x180031c5a  lea     rdx, aRastcpsetdhcpr_5; "RasTcpSetDhcpRoutes: invalid destinatio"...
0x180031c61  call    FormatRRASErrorString
0x180031c66  mov     rdx, cs:qword_18004C640
0x180031c6d  lea     r8, [rbp+7F0h+var_840]
0x180031c71  mov     rcx, cs:gIphlpEtwContext
0x180031c78  mov     rax, cs:gIphlpTemplateFunc
0x180031c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c84  jmp     short loc_180031C94
0x180031c86  mov     edx, ecx
0x180031c88  lea     rcx, aRastcpsetdhcpr_2; "RasTcpSetDhcpRoutes: invalid destinatio"...
0x180031c8f  call    TraceHlp
0x180031c94  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x180031c9b  jz      short loc_180031CCE
0x180031c9d  mov     rdx, cs:qword_18004C648
0x180031ca4  test    rdx, rdx
0x180031ca7  jz      short loc_180031CC5
0x180031ca9  mov     rcx, cs:gIphlpEtwContext
0x180031cb0  lea     r8, aRastcpsetdhcpr_1; "RasTcpSetDhcpRoutes End"
0x180031cb7  mov     rax, cs:gIphlpTemplateFunc
0x180031cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031cc3  jmp     short loc_180031CDA
0x180031cc5  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x180031ccc  jnz     short loc_180031CDA
0x180031cce  lea     rcx, aRastcpsetdhcpr_3; "RasTcpSetDhcpRoutes End"
0x180031cd5  call    TraceHlp
0x180031cda  mov     rcx, [rbp+7F0h+var_40]
0x180031ce1  xor     rcx, rsp; StackCookie
0x180031ce4  call    __security_check_cookie
0x180031ce9  mov     rbx, [rsp+8F0h+arg_10]
0x180031cf1  add     rsp, 8C0h
0x180031cf8  pop     r15
0x180031cfa  pop     r14
0x180031cfc  pop     r13
0x180031cfe  pop     r12
0x180031d00  pop     rdi
0x180031d01  pop     rsi
0x180031d02  pop     rbp
0x180031d03  retn
```
