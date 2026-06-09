# ResetNetBTConfigInfo

- ea: `0x180020920`
- end: `0x180020b16`
- name: `ResetNetBTConfigInfo`
- size: `502`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001bab4`
- `0x18001c1bc`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180020920`
- `0x18002b0dc`
- `0x18002dd20`
- `0x18002e2a4`
- `0x18002ebd0`
- `0x18002fce0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020ab8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020ab8`

## string_xrefs

- `0x180020982`: `IPCP: ResetNetBTConfigInfo ...`

## pseudocode

```c
__int64 __fastcall ResetNetBTConfigInfo(__int64 a1)
{
  unsigned int TcpipInfo; // eax
  __int64 v3; // rdx
  unsigned int v4; // edi
  __int64 v5; // rdi
  void *v6; // rcx
  bool v7; // zf
  __int64 v9[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v11[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v9[0] = 0;
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      L"IPCP: ResetNetBTConfigInfo ...");
    if ( *((_QWORD *)&xmmword_18004D860 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004D860 + 1),
        L"IPCP: LoadTcpipInfo...");
  }
  TcpipInfo = LoadTcpipInfo(v9, *(const wchar_t **)(a1 + 1248), 1);
  v3 = *((_QWORD *)&xmmword_18004D860 + 1);
  v4 = TcpipInfo;
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString((wchar_t *)&v10, L"IPCP: LoadTcpipInfo done(%d)", TcpipInfo);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      &v10);
    v3 = *((_QWORD *)&xmmword_18004D860 + 1);
  }
  if ( !v4 )
  {
    v5 = v9[0];
    *(_DWORD *)v9[0] = 1;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        v3,
        L"IPCP: SaveTcpipInfo...");
    v4 = SaveTcpipInfo(v5);
    if ( *((_QWORD *)&xmmword_18004D860 + 1) )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString((wchar_t *)&v10, L"IPCP: SaveTcpipInfo done(%d)", v4);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004D860 + 1),
        &v10);
    }
  }
  FreeTcpipInfo(v9);
  v6 = *(void **)(a1 + 160);
  *(_DWORD *)(a1 + 156) = 0;
  LocalFree(v6);
  v7 = *(_DWORD *)(a1 + 88) == 0;
  *(_QWORD *)(a1 + 160) = 0;
  if ( !v7 )
  {
    v4 = ResetIpAddressOnInterface(*(_DWORD *)(a1 + 1256), *(_DWORD *)(a1 + 144));
    *(_DWORD *)(a1 + 88) = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180020920  mov     [rsp-8+arg_8], rbx
0x180020925  mov     [rsp-8+arg_10], rdi
0x18002092a  push    rbp
0x18002092b  lea     rbp, [rsp-740h]
0x180020933  sub     rsp, 840h
0x18002093a  mov     rax, cs:__security_cookie
0x180020941  xor     rax, rsp
0x180020944  mov     [rbp+740h+var_10], rax
0x18002094b  mov     rbx, rcx
0x18002094e  mov     [rsp+840h+var_820], 0
0x180020957  xor     eax, eax
0x180020959  lea     rcx, [rsp+840h+var_80C]; void *
0x18002095e  xor     edx, edx; Val
0x180020960  mov     [rsp+840h+var_810], eax
0x180020964  mov     r8d, 7FCh; Size
0x18002096a  call    memset_0
0x18002096f  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x180020976  test    rdx, rdx
0x180020979  jz      short loc_1800209BB
0x18002097b  mov     rcx, cs:gRasIpcpEtwContext
0x180020982  lea     r8, aIpcpResetnetbt; "IPCP: ResetNetBTConfigInfo ..."
0x180020989  mov     rax, cs:gRasIpcpTemplateFunc
0x180020990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020995  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18002099c  test    rdx, rdx
0x18002099f  jz      short loc_1800209BB
0x1800209a1  mov     rcx, cs:gRasIpcpEtwContext
0x1800209a8  lea     r8, aIpcpLoadtcpipi; "IPCP: LoadTcpipInfo..."
0x1800209af  mov     rax, cs:gRasIpcpTemplateFunc
0x1800209b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209bb  mov     rdx, [rbx+4E0h]
0x1800209c2  lea     rcx, [rsp+840h+var_820]
0x1800209c7  mov     r8d, 1
0x1800209cd  call    LoadTcpipInfo
0x1800209d2  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x1800209d9  mov     edi, eax
0x1800209db  test    rdx, rdx
0x1800209de  jz      short loc_180020A21
0x1800209e0  xor     ecx, ecx
0x1800209e2  lea     rdx, aIpcpLoadtcpipi_0; "IPCP: LoadTcpipInfo done(%d)"
0x1800209e9  mov     word ptr [rsp+840h+var_810], cx
0x1800209ee  mov     r8d, eax
0x1800209f1  lea     rcx, [rsp+840h+var_810]
0x1800209f6  call    FormatRRASErrorString
0x1800209fb  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x180020a02  lea     r8, [rsp+840h+var_810]
0x180020a07  mov     rcx, cs:gRasIpcpEtwContext
0x180020a0e  mov     rax, cs:gRasIpcpTemplateFunc
0x180020a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a1a  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x180020a21  test    edi, edi
0x180020a23  jnz     short loc_180020A9D
0x180020a25  mov     rdi, [rsp+840h+var_820]
0x180020a2a  mov     dword ptr [rdi], 1
0x180020a30  test    rdx, rdx
0x180020a33  jz      short loc_180020A4F
0x180020a35  mov     rcx, cs:gRasIpcpEtwContext
0x180020a3c  lea     r8, aIpcpSavetcpipi; "IPCP: SaveTcpipInfo..."
0x180020a43  mov     rax, cs:gRasIpcpTemplateFunc
0x180020a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a4f  mov     rcx, rdi
0x180020a52  call    SaveTcpipInfo
0x180020a57  cmp     qword ptr cs:xmmword_18004D860+8, 0
0x180020a5f  mov     edi, eax
0x180020a61  jz      short loc_180020A9D
0x180020a63  xor     eax, eax
0x180020a65  lea     rdx, aIpcpSavetcpipi_0; "IPCP: SaveTcpipInfo done(%d)"
0x180020a6c  mov     r8d, edi
0x180020a6f  mov     word ptr [rsp+840h+var_810], ax
0x180020a74  lea     rcx, [rsp+840h+var_810]
0x180020a79  call    FormatRRASErrorString
0x180020a7e  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x180020a85  lea     r8, [rsp+840h+var_810]
0x180020a8a  mov     rcx, cs:gRasIpcpEtwContext
0x180020a91  mov     rax, cs:gRasIpcpTemplateFunc
0x180020a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a9d  lea     rcx, [rsp+840h+var_820]
0x180020aa2  call    FreeTcpipInfo
0x180020aa7  mov     rcx, [rbx+0A0h]; hMem
0x180020aae  mov     dword ptr [rbx+9Ch], 0
0x180020ab8  call    cs:__imp_LocalFree
0x180020abf  nop     dword ptr [rax+rax+00h]
0x180020ac4  cmp     dword ptr [rbx+58h], 0
0x180020ac8  mov     qword ptr [rbx+0A0h], 0
0x180020ad3  jz      short loc_180020AEF
0x180020ad5  mov     edx, [rbx+90h]
0x180020adb  mov     ecx, [rbx+4E8h]
0x180020ae1  call    ResetIpAddressOnInterface
0x180020ae6  mov     edi, eax
0x180020ae8  mov     dword ptr [rbx+58h], 0
0x180020aef  mov     eax, edi
0x180020af1  mov     rcx, [rbp+740h+var_10]
0x180020af8  xor     rcx, rsp; StackCookie
0x180020afb  call    __security_check_cookie
0x180020b00  lea     r11, [rsp+840h+var_s0]
0x180020b08  mov     rbx, [r11+18h]
0x180020b0c  mov     rdi, [r11+20h]
0x180020b10  mov     rsp, r11
0x180020b13  pop     rbp
0x180020b14  retn
```
