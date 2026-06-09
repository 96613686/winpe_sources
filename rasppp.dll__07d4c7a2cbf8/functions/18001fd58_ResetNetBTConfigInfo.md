# ResetNetBTConfigInfo

- ea: `0x18001fd58`
- end: `0x18001ff47`
- name: `ResetNetBTConfigInfo`
- size: `495`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001b074`
- `0x18001b7c0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001fd58`
- `0x18002a138`
- `0x18002cbd4`
- `0x18002d08c`
- `0x18002d904`
- `0x18002e92c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fef0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fef0`

## string_xrefs

- `0x18001fdba`: `IPCP: ResetNetBTConfigInfo ...`

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
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      L"IPCP: ResetNetBTConfigInfo ...");
    if ( *((_QWORD *)&xmmword_18004C860 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004C860 + 1),
        L"IPCP: LoadTcpipInfo...");
  }
  TcpipInfo = LoadTcpipInfo(v9, *(const wchar_t **)(a1 + 1248), 1);
  v3 = *((_QWORD *)&xmmword_18004C860 + 1);
  v4 = TcpipInfo;
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"IPCP: LoadTcpipInfo done(%d)", TcpipInfo);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      &v10);
    v3 = *((_QWORD *)&xmmword_18004C860 + 1);
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
    if ( *((_QWORD *)&xmmword_18004C860 + 1) )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"IPCP: SaveTcpipInfo done(%d)", v4);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004C860 + 1),
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
    v4 = ResetIpAddressOnInterface(*(unsigned int *)(a1 + 1256), *(unsigned int *)(a1 + 144));
    *(_DWORD *)(a1 + 88) = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18001fd58  mov     [rsp-8+arg_8], rbx
0x18001fd5d  mov     [rsp-8+arg_10], rdi
0x18001fd62  push    rbp
0x18001fd63  lea     rbp, [rsp-740h]
0x18001fd6b  sub     rsp, 840h
0x18001fd72  mov     rax, cs:__security_cookie
0x18001fd79  xor     rax, rsp
0x18001fd7c  mov     [rbp+740h+var_10], rax
0x18001fd83  mov     rbx, rcx
0x18001fd86  mov     [rsp+840h+var_820], 0
0x18001fd8f  xor     eax, eax
0x18001fd91  lea     rcx, [rsp+840h+var_80C]; void *
0x18001fd96  xor     edx, edx; Val
0x18001fd98  mov     [rsp+840h+var_810], eax
0x18001fd9c  mov     r8d, 7FCh; Size
0x18001fda2  call    memset_0
0x18001fda7  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001fdae  test    rdx, rdx
0x18001fdb1  jz      short loc_18001FDF3
0x18001fdb3  mov     rcx, cs:gRasIpcpEtwContext
0x18001fdba  lea     r8, aIpcpResetnetbt; "IPCP: ResetNetBTConfigInfo ..."
0x18001fdc1  mov     rax, cs:gRasIpcpTemplateFunc
0x18001fdc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdcd  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001fdd4  test    rdx, rdx
0x18001fdd7  jz      short loc_18001FDF3
0x18001fdd9  mov     rcx, cs:gRasIpcpEtwContext
0x18001fde0  lea     r8, aIpcpLoadtcpipi; "IPCP: LoadTcpipInfo..."
0x18001fde7  mov     rax, cs:gRasIpcpTemplateFunc
0x18001fdee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdf3  mov     rdx, [rbx+4E0h]
0x18001fdfa  lea     rcx, [rsp+840h+var_820]
0x18001fdff  mov     r8d, 1
0x18001fe05  call    LoadTcpipInfo
0x18001fe0a  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001fe11  mov     edi, eax
0x18001fe13  test    rdx, rdx
0x18001fe16  jz      short loc_18001FE59
0x18001fe18  xor     ecx, ecx
0x18001fe1a  lea     rdx, aIpcpLoadtcpipi_0; "IPCP: LoadTcpipInfo done(%d)"
0x18001fe21  mov     word ptr [rsp+840h+var_810], cx
0x18001fe26  mov     r8d, eax
0x18001fe29  lea     rcx, [rsp+840h+var_810]
0x18001fe2e  call    FormatRRASErrorString
0x18001fe33  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001fe3a  lea     r8, [rsp+840h+var_810]
0x18001fe3f  mov     rcx, cs:gRasIpcpEtwContext
0x18001fe46  mov     rax, cs:gRasIpcpTemplateFunc
0x18001fe4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe52  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001fe59  test    edi, edi
0x18001fe5b  jnz     short loc_18001FED5
0x18001fe5d  mov     rdi, [rsp+840h+var_820]
0x18001fe62  mov     dword ptr [rdi], 1
0x18001fe68  test    rdx, rdx
0x18001fe6b  jz      short loc_18001FE87
0x18001fe6d  mov     rcx, cs:gRasIpcpEtwContext
0x18001fe74  lea     r8, aIpcpSavetcpipi; "IPCP: SaveTcpipInfo..."
0x18001fe7b  mov     rax, cs:gRasIpcpTemplateFunc
0x18001fe82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe87  mov     rcx, rdi
0x18001fe8a  call    SaveTcpipInfo
0x18001fe8f  cmp     qword ptr cs:xmmword_18004C860+8, 0
0x18001fe97  mov     edi, eax
0x18001fe99  jz      short loc_18001FED5
0x18001fe9b  xor     eax, eax
0x18001fe9d  lea     rdx, aIpcpSavetcpipi_0; "IPCP: SaveTcpipInfo done(%d)"
0x18001fea4  mov     r8d, edi
0x18001fea7  mov     word ptr [rsp+840h+var_810], ax
0x18001feac  lea     rcx, [rsp+840h+var_810]
0x18001feb1  call    FormatRRASErrorString
0x18001feb6  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001febd  lea     r8, [rsp+840h+var_810]
0x18001fec2  mov     rcx, cs:gRasIpcpEtwContext
0x18001fec9  mov     rax, cs:gRasIpcpTemplateFunc
0x18001fed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fed5  lea     rcx, [rsp+840h+var_820]
0x18001feda  call    FreeTcpipInfo
0x18001fedf  mov     rcx, [rbx+0A0h]; hMem
0x18001fee6  mov     dword ptr [rbx+9Ch], 0
0x18001fef0  call    cs:__imp_LocalFree
0x18001fef6  cmp     dword ptr [rbx+58h], 0
0x18001fefa  mov     qword ptr [rbx+0A0h], 0
0x18001ff05  jz      short loc_18001FF21
0x18001ff07  mov     edx, [rbx+90h]
0x18001ff0d  mov     ecx, [rbx+4E8h]
0x18001ff13  call    ResetIpAddressOnInterface
0x18001ff18  mov     edi, eax
0x18001ff1a  mov     dword ptr [rbx+58h], 0
0x18001ff21  mov     eax, edi
0x18001ff23  mov     rcx, [rbp+740h+var_10]
0x18001ff2a  xor     rcx, rsp; StackCookie
0x18001ff2d  call    __security_check_cookie
0x18001ff32  lea     r11, [rsp+840h+var_s0]
0x18001ff3a  mov     rbx, [r11+18h]
0x18001ff3e  mov     rdi, [r11+20h]
0x18001ff42  mov     rsp, r11
0x18001ff45  pop     rbp
0x18001ff46  retn
```
