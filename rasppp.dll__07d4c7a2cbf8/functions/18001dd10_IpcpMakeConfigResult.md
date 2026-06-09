# IpcpMakeConfigResult

- ea: `0x18001dd10`
- end: `0x18001df14`
- name: `IpcpMakeConfigResult`
- size: `516`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18001dd10`
- `0x18001f06c`
- `0x18001faa4`
- `0x180032460`
- `0x180033010`

## string_xrefs

- `0x18001dd49`: `IPCP: IpcpMakeConfigResult for...`
- `0x18001dd89`: `Dumping Bytes IpcpMakeConfigResult`
- `0x18001ddd9`: `IPCP: ConfigResult...`
- `0x18001deb2`: `IPCP: ConfigResult...`
- `0x18001ddfc`: `DumpingBytes ConfigResult`
- `0x18001ded5`: `DumpingBytes ConfigResult`

## pseudocode

```c
__int64 __fastcall IpcpMakeConfigResult(
        __int64 a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 v9; // r9
  unsigned int v10; // ebp
  __int64 v11; // rdx
  __int64 v13; // rdx
  int v14; // [rsp+50h] [rbp+8h] BYREF

  v14 = 0;
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      L"IPCP: IpcpMakeConfigResult for...");
  if ( qword_18004C880 )
  {
    if ( a2 )
      v9 = a2[3] + (a2[2] << 8);
    else
      v9 = 0;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, unsigned __int8 *))gRasIpcpByteTemplateFunc)(
      gRasIpcpEtwContext,
      qword_18004C880,
      L"Dumping Bytes IpcpMakeConfigResult",
      v9,
      a2);
  }
  *(_DWORD *)(a1 + 92) = 0;
  v10 = RejectCheck(a1, (_DWORD)a2, (_DWORD)a3, a4, (__int64)&v14);
  if ( v10 )
  {
    v11 = xmmword_18004C860;
LABEL_10:
    if ( v11 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        v11,
        L"IPCP: ConfigResult...");
    if ( qword_18004C880 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, _QWORD, unsigned __int8 *))gRasIpcpByteTemplateFunc)(
        gRasIpcpEtwContext,
        qword_18004C880,
        L"DumpingBytes ConfigResult",
        (a3[2] << 8) + (unsigned int)a3[3],
        a3);
    return v10;
  }
  if ( v14 )
    return *(_DWORD *)(a1 + 24) != 0 ? 0x2DC : 0;
  v10 = NakCheck(a1, a2, (__int64)a3, a4, &v14, a5);
  if ( v10 )
  {
    v11 = *((_QWORD *)&xmmword_18004C860 + 1);
    goto LABEL_10;
  }
  if ( v14 )
    return *(_DWORD *)(a1 + 24) != 0 ? 0x2DC : 0;
  memcpy_0(a3, a2, a2[3] + ((unsigned __int64)a2[2] << 8));
  v13 = *((_QWORD *)&xmmword_18004C860 + 1);
  *a3 = 2;
  if ( v13 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      v13,
      L"IPCP: ConfigResult...");
  if ( qword_18004C880 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, _QWORD, unsigned __int8 *))gRasIpcpByteTemplateFunc)(
      gRasIpcpEtwContext,
      qword_18004C880,
      L"DumpingBytes ConfigResult",
      (a3[2] << 8) + (unsigned int)a3[3],
      a3);
  return 0;
}

```

## disassembly

```asm
0x18001dd10  mov     [rsp+arg_8], rbx
0x18001dd15  mov     [rsp+arg_10], rbp
0x18001dd1a  push    rsi
0x18001dd1b  push    rdi
0x18001dd1c  push    r14
0x18001dd1e  sub     rsp, 30h
0x18001dd22  mov     rbx, rdx
0x18001dd25  mov     [rsp+48h+arg_0], 0
0x18001dd2d  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001dd34  mov     r14d, r9d
0x18001dd37  mov     rdi, r8
0x18001dd3a  mov     rsi, rcx
0x18001dd3d  test    rdx, rdx
0x18001dd40  jz      short loc_18001DD5C
0x18001dd42  mov     rcx, cs:gRasIpcpEtwContext
0x18001dd49  lea     r8, aIpcpIpcpmakeco; "IPCP: IpcpMakeConfigResult for..."
0x18001dd50  mov     rax, cs:gRasIpcpTemplateFunc
0x18001dd57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd5c  mov     rdx, cs:qword_18004C880
0x18001dd63  test    rdx, rdx
0x18001dd66  jz      short loc_18001DDA1
0x18001dd68  test    rbx, rbx
0x18001dd6b  jz      short loc_18001DD7F
0x18001dd6d  movzx   r9d, byte ptr [rbx+2]
0x18001dd72  movzx   eax, byte ptr [rbx+3]
0x18001dd76  shl     r9d, 8
0x18001dd7a  add     r9d, eax
0x18001dd7d  jmp     short loc_18001DD82
0x18001dd7f  xor     r9d, r9d
0x18001dd82  mov     rcx, cs:gRasIpcpEtwContext
0x18001dd89  lea     r8, aDumpingBytesIp; "Dumping Bytes IpcpMakeConfigResult"
0x18001dd90  mov     rax, cs:gRasIpcpByteTemplateFunc
0x18001dd97  mov     [rsp+48h+var_28], rbx
0x18001dd9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dda1  lea     rax, [rsp+48h+arg_0]
0x18001dda6  mov     dword ptr [rsi+5Ch], 0
0x18001ddad  mov     r8, rdi
0x18001ddb0  mov     [rsp+48h+var_28], rax
0x18001ddb5  mov     rdx, rbx
0x18001ddb8  mov     rcx, rsi
0x18001ddbb  call    RejectCheck
0x18001ddc0  mov     ebp, eax
0x18001ddc2  test    eax, eax
0x18001ddc4  jz      short loc_18001DE2D
0x18001ddc6  mov     rdx, qword ptr cs:xmmword_18004C860
0x18001ddcd  test    rdx, rdx
0x18001ddd0  jz      short loc_18001DDEC
0x18001ddd2  mov     rcx, cs:gRasIpcpEtwContext
0x18001ddd9  lea     r8, aIpcpConfigresu; "IPCP: ConfigResult..."
0x18001dde0  mov     rax, cs:gRasIpcpTemplateFunc
0x18001dde7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddec  mov     rdx, cs:qword_18004C880
0x18001ddf3  test    rdx, rdx
0x18001ddf6  jz      short loc_18001DE26
0x18001ddf8  movzx   eax, byte ptr [rdi+2]
0x18001ddfc  lea     r8, aDumpingbytesCo; "DumpingBytes ConfigResult"
0x18001de03  movzx   r9d, byte ptr [rdi+3]
0x18001de08  mov     rcx, cs:gRasIpcpEtwContext
0x18001de0f  shl     eax, 8
0x18001de12  add     r9d, eax
0x18001de15  mov     [rsp+48h+var_28], rdi
0x18001de1a  mov     rax, cs:gRasIpcpByteTemplateFunc
0x18001de21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de26  mov     eax, ebp
0x18001de28  jmp     loc_18001DF01
0x18001de2d  cmp     [rsp+48h+arg_0], 0
0x18001de32  jz      short loc_18001DE45
0x18001de34  mov     eax, [rsi+18h]
0x18001de37  neg     eax
0x18001de39  sbb     eax, eax
0x18001de3b  and     eax, 2DCh
0x18001de40  jmp     loc_18001DF01
0x18001de45  mov     eax, [rsp+48h+arg_20]
0x18001de49  mov     r9d, r14d
0x18001de4c  mov     [rsp+48h+var_20], eax
0x18001de50  mov     r8, rdi
0x18001de53  lea     rax, [rsp+48h+arg_0]
0x18001de58  mov     rdx, rbx
0x18001de5b  mov     rcx, rsi
0x18001de5e  mov     [rsp+48h+var_28], rax
0x18001de63  call    NakCheck
0x18001de68  mov     ebp, eax
0x18001de6a  test    eax, eax
0x18001de6c  jz      short loc_18001DE7A
0x18001de6e  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001de75  jmp     loc_18001DDCD
0x18001de7a  cmp     [rsp+48h+arg_0], 0
0x18001de7f  jnz     short loc_18001DE34
0x18001de81  movzx   r8d, byte ptr [rbx+2]
0x18001de86  mov     rdx, rbx; Src
0x18001de89  movzx   eax, byte ptr [rbx+3]
0x18001de8d  mov     rcx, rdi; void *
0x18001de90  shl     r8, 8
0x18001de94  add     r8, rax; Size
0x18001de97  call    memcpy_0
0x18001de9c  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001dea3  mov     byte ptr [rdi], 2
0x18001dea6  test    rdx, rdx
0x18001dea9  jz      short loc_18001DEC5
0x18001deab  mov     rcx, cs:gRasIpcpEtwContext
0x18001deb2  lea     r8, aIpcpConfigresu; "IPCP: ConfigResult..."
0x18001deb9  mov     rax, cs:gRasIpcpTemplateFunc
0x18001dec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dec5  mov     rdx, cs:qword_18004C880
0x18001decc  test    rdx, rdx
0x18001decf  jz      short loc_18001DEFF
0x18001ded1  movzx   eax, byte ptr [rdi+2]
0x18001ded5  lea     r8, aDumpingbytesCo; "DumpingBytes ConfigResult"
0x18001dedc  movzx   r9d, byte ptr [rdi+3]
0x18001dee1  mov     rcx, cs:gRasIpcpEtwContext
0x18001dee8  shl     eax, 8
0x18001deeb  add     r9d, eax
0x18001deee  mov     [rsp+48h+var_28], rdi
0x18001def3  mov     rax, cs:gRasIpcpByteTemplateFunc
0x18001defa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001deff  xor     eax, eax
0x18001df01  mov     rbx, [rsp+48h+arg_8]
0x18001df06  mov     rbp, [rsp+48h+arg_10]
0x18001df0b  add     rsp, 30h
0x18001df0f  pop     r14
0x18001df11  pop     rdi
0x18001df12  pop     rsi
0x18001df13  retn
```
