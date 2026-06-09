# IpcpMakeConfigResult

- ea: `0x18001e830`
- end: `0x18001ea35`
- name: `IpcpMakeConfigResult`
- size: `517`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18001e830`
- `0x18001fc1c`
- `0x18002066c`
- `0x180033a80`
- `0x180034010`

## string_xrefs

- `0x18001e869`: `IPCP: IpcpMakeConfigResult for...`
- `0x18001e8a9`: `Dumping Bytes IpcpMakeConfigResult`
- `0x18001e8f9`: `IPCP: ConfigResult...`
- `0x18001e9d2`: `IPCP: ConfigResult...`
- `0x18001e91c`: `DumpingBytes ConfigResult`
- `0x18001e9f5`: `DumpingBytes ConfigResult`

## pseudocode

```c
__int64 __fastcall IpcpMakeConfigResult(__int64 a1, unsigned __int8 *a2, _BYTE *a3, __int64 a4, unsigned int a5)
{
  unsigned int v6; // r14d
  __int64 v9; // r9
  unsigned int v10; // ebp
  __int64 v11; // rdx
  __int64 v13; // rdx
  int v14; // [rsp+50h] [rbp+8h] BYREF

  v14 = 0;
  v6 = a4;
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      L"IPCP: IpcpMakeConfigResult for...");
  if ( qword_18004D880 )
  {
    if ( a2 )
      v9 = a2[3] + (a2[2] << 8);
    else
      v9 = 0;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, unsigned __int8 *))gRasIpcpByteTemplateFunc)(
      gRasIpcpEtwContext,
      qword_18004D880,
      L"Dumping Bytes IpcpMakeConfigResult",
      v9,
      a2);
  }
  *(_DWORD *)(a1 + 92) = 0;
  v10 = RejectCheck(a1, a2, a3, a4, &v14);
  if ( v10 )
  {
    v11 = xmmword_18004D860;
LABEL_10:
    if ( v11 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        v11,
        L"IPCP: ConfigResult...");
    if ( qword_18004D880 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, _QWORD, _BYTE *))gRasIpcpByteTemplateFunc)(
        gRasIpcpEtwContext,
        qword_18004D880,
        L"DumpingBytes ConfigResult",
        ((unsigned __int8)a3[2] << 8) + (unsigned int)(unsigned __int8)a3[3],
        a3);
    return v10;
  }
  if ( v14 )
    return *(_DWORD *)(a1 + 24) != 0 ? 0x2DC : 0;
  v10 = NakCheck(a1, a2, (__int64)a3, v6, &v14, a5);
  if ( v10 )
  {
    v11 = *((_QWORD *)&xmmword_18004D860 + 1);
    goto LABEL_10;
  }
  if ( v14 )
    return *(_DWORD *)(a1 + 24) != 0 ? 0x2DC : 0;
  memcpy_0(a3, a2, a2[3] + ((unsigned __int64)a2[2] << 8));
  v13 = *((_QWORD *)&xmmword_18004D860 + 1);
  *a3 = 2;
  if ( v13 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      v13,
      L"IPCP: ConfigResult...");
  if ( qword_18004D880 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, _QWORD, _BYTE *))gRasIpcpByteTemplateFunc)(
      gRasIpcpEtwContext,
      qword_18004D880,
      L"DumpingBytes ConfigResult",
      ((unsigned __int8)a3[2] << 8) + (unsigned int)(unsigned __int8)a3[3],
      a3);
  return 0;
}

```

## disassembly

```asm
0x18001e830  mov     [rsp+arg_8], rbx
0x18001e835  mov     [rsp+arg_10], rbp
0x18001e83a  push    rsi
0x18001e83b  push    rdi
0x18001e83c  push    r14
0x18001e83e  sub     rsp, 30h
0x18001e842  mov     rbx, rdx
0x18001e845  mov     [rsp+48h+arg_0], 0
0x18001e84d  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001e854  mov     r14d, r9d
0x18001e857  mov     rdi, r8
0x18001e85a  mov     rsi, rcx
0x18001e85d  test    rdx, rdx
0x18001e860  jz      short loc_18001E87C
0x18001e862  mov     rcx, cs:gRasIpcpEtwContext
0x18001e869  lea     r8, aIpcpIpcpmakeco; "IPCP: IpcpMakeConfigResult for..."
0x18001e870  mov     rax, cs:gRasIpcpTemplateFunc
0x18001e877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e87c  mov     rdx, cs:qword_18004D880
0x18001e883  test    rdx, rdx
0x18001e886  jz      short loc_18001E8C1
0x18001e888  test    rbx, rbx
0x18001e88b  jz      short loc_18001E89F
0x18001e88d  movzx   r9d, byte ptr [rbx+2]
0x18001e892  movzx   eax, byte ptr [rbx+3]
0x18001e896  shl     r9d, 8
0x18001e89a  add     r9d, eax
0x18001e89d  jmp     short loc_18001E8A2
0x18001e89f  xor     r9d, r9d
0x18001e8a2  mov     rcx, cs:gRasIpcpEtwContext
0x18001e8a9  lea     r8, aDumpingBytesIp; "Dumping Bytes IpcpMakeConfigResult"
0x18001e8b0  mov     rax, cs:gRasIpcpByteTemplateFunc
0x18001e8b7  mov     [rsp+48h+var_28], rbx
0x18001e8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8c1  lea     rax, [rsp+48h+arg_0]
0x18001e8c6  mov     dword ptr [rsi+5Ch], 0
0x18001e8cd  mov     r8, rdi
0x18001e8d0  mov     [rsp+48h+var_28], rax
0x18001e8d5  mov     rdx, rbx
0x18001e8d8  mov     rcx, rsi
0x18001e8db  call    RejectCheck
0x18001e8e0  mov     ebp, eax
0x18001e8e2  test    eax, eax
0x18001e8e4  jz      short loc_18001E94D
0x18001e8e6  mov     rdx, qword ptr cs:xmmword_18004D860
0x18001e8ed  test    rdx, rdx
0x18001e8f0  jz      short loc_18001E90C
0x18001e8f2  mov     rcx, cs:gRasIpcpEtwContext
0x18001e8f9  lea     r8, aIpcpConfigresu; "IPCP: ConfigResult..."
0x18001e900  mov     rax, cs:gRasIpcpTemplateFunc
0x18001e907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e90c  mov     rdx, cs:qword_18004D880
0x18001e913  test    rdx, rdx
0x18001e916  jz      short loc_18001E946
0x18001e918  movzx   eax, byte ptr [rdi+2]
0x18001e91c  lea     r8, aDumpingbytesCo; "DumpingBytes ConfigResult"
0x18001e923  movzx   r9d, byte ptr [rdi+3]
0x18001e928  mov     rcx, cs:gRasIpcpEtwContext
0x18001e92f  shl     eax, 8
0x18001e932  add     r9d, eax
0x18001e935  mov     [rsp+48h+var_28], rdi
0x18001e93a  mov     rax, cs:gRasIpcpByteTemplateFunc
0x18001e941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e946  mov     eax, ebp
0x18001e948  jmp     loc_18001EA21
0x18001e94d  cmp     [rsp+48h+arg_0], 0
0x18001e952  jz      short loc_18001E965
0x18001e954  mov     eax, [rsi+18h]
0x18001e957  neg     eax
0x18001e959  sbb     eax, eax
0x18001e95b  and     eax, 2DCh
0x18001e960  jmp     loc_18001EA21
0x18001e965  mov     eax, [rsp+48h+arg_20]
0x18001e969  mov     r9d, r14d
0x18001e96c  mov     [rsp+48h+var_20], eax
0x18001e970  mov     r8, rdi
0x18001e973  lea     rax, [rsp+48h+arg_0]
0x18001e978  mov     rdx, rbx
0x18001e97b  mov     rcx, rsi
0x18001e97e  mov     [rsp+48h+var_28], rax
0x18001e983  call    NakCheck
0x18001e988  mov     ebp, eax
0x18001e98a  test    eax, eax
0x18001e98c  jz      short loc_18001E99A
0x18001e98e  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001e995  jmp     loc_18001E8ED
0x18001e99a  cmp     [rsp+48h+arg_0], 0
0x18001e99f  jnz     short loc_18001E954
0x18001e9a1  movzx   r8d, byte ptr [rbx+2]
0x18001e9a6  mov     rdx, rbx; Src
0x18001e9a9  movzx   eax, byte ptr [rbx+3]
0x18001e9ad  mov     rcx, rdi; void *
0x18001e9b0  shl     r8, 8
0x18001e9b4  add     r8, rax; Size
0x18001e9b7  call    memcpy_0
0x18001e9bc  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001e9c3  mov     byte ptr [rdi], 2
0x18001e9c6  test    rdx, rdx
0x18001e9c9  jz      short loc_18001E9E5
0x18001e9cb  mov     rcx, cs:gRasIpcpEtwContext
0x18001e9d2  lea     r8, aIpcpConfigresu; "IPCP: ConfigResult..."
0x18001e9d9  mov     rax, cs:gRasIpcpTemplateFunc
0x18001e9e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9e5  mov     rdx, cs:qword_18004D880
0x18001e9ec  test    rdx, rdx
0x18001e9ef  jz      short loc_18001EA1F
0x18001e9f1  movzx   eax, byte ptr [rdi+2]
0x18001e9f5  lea     r8, aDumpingbytesCo; "DumpingBytes ConfigResult"
0x18001e9fc  movzx   r9d, byte ptr [rdi+3]
0x18001ea01  mov     rcx, cs:gRasIpcpEtwContext
0x18001ea08  shl     eax, 8
0x18001ea0b  add     r9d, eax
0x18001ea0e  mov     [rsp+48h+var_28], rdi
0x18001ea13  mov     rax, cs:gRasIpcpByteTemplateFunc
0x18001ea1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea1f  xor     eax, eax
0x18001ea21  mov     rbx, [rsp+48h+arg_8]
0x18001ea26  mov     rbp, [rsp+48h+arg_10]
0x18001ea2b  add     rsp, 30h
0x18001ea2f  pop     r14
0x18001ea31  pop     rdi
0x18001ea32  pop     rsi
0x18001ea33  retn
```
