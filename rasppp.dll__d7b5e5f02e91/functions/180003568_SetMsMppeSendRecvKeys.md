# SetMsMppeSendRecvKeys

- ea: `0x180003568`
- end: `0x1800036ef`
- name: `SetMsMppeSendRecvKeys`
- size: `391`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000380c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180003568`
- `0x18002b0dc`
- `0x180033a80`
- `0x180034010`

## string_xrefs

- `0x180003683`: `RasCompressionSetInfo failed, Error=%d`

## pseudocode

```c
__int64 __fastcall SetMsMppeSendRecvKeys(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  bool v7; // cc
  __int64 v8; // rdx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  _BYTE v12[60]; // [rsp+20h] [rbp-E0h] BYREF
  int v13; // [rsp+5Ch] [rbp-A4h]
  char v14; // [rsp+60h] [rbp-A0h]
  int v15; // [rsp+88h] [rbp-78h]
  unsigned int v16; // [rsp+8Ch] [rbp-74h]
  _BYTE v17[256]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v18[60]; // [rsp+190h] [rbp+90h] BYREF
  int v19; // [rsp+1CCh] [rbp+CCh]
  char v20; // [rsp+1D0h] [rbp+D0h]
  int v21; // [rsp+1F8h] [rbp+F8h]
  unsigned int v22; // [rsp+1FCh] [rbp+FCh]
  _BYTE v23[256]; // [rsp+200h] [rbp+100h] BYREF
  int v24; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v25[2044]; // [rsp+304h] [rbp+204h] BYREF

  memset_0(v12, 0, 0x170u);
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  if ( *(_DWORD *)(a2 + 4) <= 8u )
    return 87;
  memset_0(v18, 0, 0x170u);
  v6 = *(_QWORD *)(a2 + 8);
  v20 = -1;
  v22 = *(unsigned __int8 *)(v6 + 8);
  memcpy_0(v23, (const void *)(v6 + 9), v22);
  v7 = *(_DWORD *)(a3 + 4) <= 8u;
  v21 = 4;
  v19 = 3;
  if ( v7 )
    return 87;
  v8 = *(_QWORD *)(a3 + 8);
  v14 = -1;
  v16 = *(unsigned __int8 *)(v8 + 8);
  memcpy_0(v17, (const void *)(v8 + 9), v16);
  v15 = 4;
  v13 = 3;
  v9 = (*((__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *))&xmmword_18004D490 + 1))(a1, v18, v12);
  v10 = v9;
  if ( v9 && byte_18004DF33 < 0 )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString((wchar_t *)&v24, L"RasCompressionSetInfo failed, Error=%d", v9);
    if ( byte_18004DF33 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasPppTraceError,
        (const wchar_t *)&v24);
  }
  return v10;
}

```

## disassembly

```asm
0x180003568  mov     [rsp-8+arg_18], rbx
0x18000356d  push    rbp
0x18000356e  push    rsi
0x18000356f  push    rdi
0x180003570  lea     rbp, [rsp-0A10h]
0x180003578  sub     rsp, 0B10h
0x18000357f  mov     rax, cs:__security_cookie
0x180003586  xor     rax, rsp
0x180003589  mov     [rbp+0A20h+var_20], rax
0x180003590  mov     rbx, r8
0x180003593  mov     rdi, rdx
0x180003596  mov     rsi, rcx
0x180003599  xor     edx, edx; Val
0x18000359b  mov     r8d, 170h; Size
0x1800035a1  lea     rcx, [rsp+0B20h+var_B00]; void *
0x1800035a6  call    memset_0
0x1800035ab  xor     eax, eax
0x1800035ad  lea     rcx, [rbp+0A20h+var_81C]; void *
0x1800035b4  xor     edx, edx; Val
0x1800035b6  mov     [rbp+0A20h+var_820], eax
0x1800035bc  mov     r8d, 7FCh; Size
0x1800035c2  call    memset_0
0x1800035c7  cmp     dword ptr [rdi+4], 8
0x1800035cb  jbe     loc_1800036C7
0x1800035d1  xor     edx, edx; Val
0x1800035d3  lea     rcx, [rbp+0A20h+var_990]; void *
0x1800035da  mov     r8d, 170h; Size
0x1800035e0  call    memset_0
0x1800035e5  mov     rdx, [rdi+8]
0x1800035e9  lea     rcx, [rbp+0A20h+var_920]; void *
0x1800035f0  mov     [rbp+0A20h+var_950], 0FFh
0x1800035f7  movzx   eax, byte ptr [rdx+8]
0x1800035fb  add     rdx, 9; Src
0x1800035ff  mov     r8d, eax; Size
0x180003602  mov     [rbp+0A20h+var_924], eax
0x180003608  call    memcpy_0
0x18000360d  cmp     dword ptr [rbx+4], 8
0x180003611  mov     edi, 4
0x180003616  mov     [rbp+0A20h+var_928], edi
0x18000361c  mov     [rbp+0A20h+var_954], 3
0x180003626  jbe     loc_1800036C7
0x18000362c  mov     rdx, [rbx+8]
0x180003630  lea     rcx, [rbp+0A20h+var_A90]; void *
0x180003634  mov     [rsp+0B20h+var_AC0], 0FFh
0x180003639  movzx   eax, byte ptr [rdx+8]
0x18000363d  add     rdx, 9; Src
0x180003641  mov     r8d, eax; Size
0x180003644  mov     [rbp+0A20h+var_A94], eax
0x180003647  call    memcpy_0
0x18000364c  mov     rax, qword ptr cs:xmmword_18004D490+8
0x180003653  lea     r8, [rsp+0B20h+var_B00]
0x180003658  lea     rdx, [rbp+0A20h+var_990]
0x18000365f  mov     [rbp+0A20h+var_A98], edi
0x180003662  mov     rcx, rsi
0x180003665  mov     [rsp+0B20h+var_AC4], 3
0x18000366d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003672  mov     ebx, eax
0x180003674  test    eax, eax
0x180003676  jz      short loc_1800036C3
0x180003678  cmp     cs:byte_18004DF33, 0
0x18000367f  jge     short loc_1800036C3
0x180003681  xor     ecx, ecx
0x180003683  lea     rdx, aRascompression; "RasCompressionSetInfo failed, Error=%d"
0x18000368a  mov     word ptr [rbp+0A20h+var_820], cx
0x180003691  mov     r8d, eax
0x180003694  lea     rcx, [rbp+0A20h+var_820]
0x18000369b  call    FormatRRASErrorString
0x1800036a0  cmp     cs:byte_18004DF33, 0
0x1800036a7  jge     short loc_1800036C3
0x1800036a9  lea     r8, [rbp+0A20h+var_820]
0x1800036b0  lea     rdx, RasPppTraceError
0x1800036b7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800036be  call    McTemplateU0z_EventWriteTransfer
0x1800036c3  mov     eax, ebx
0x1800036c5  jmp     short loc_1800036CC
0x1800036c7  mov     eax, 57h ; 'W'
0x1800036cc  mov     rcx, [rbp+0A20h+var_20]
0x1800036d3  xor     rcx, rsp; StackCookie
0x1800036d6  call    __security_check_cookie
0x1800036db  mov     rbx, [rsp+0B20h+arg_18]
0x1800036e3  add     rsp, 0B10h
0x1800036ea  pop     rdi
0x1800036eb  pop     rsi
0x1800036ec  pop     rbp
0x1800036ed  retn
```
