# SetMsMppeSendRecvKeys

- ea: `0x1800034d4`
- end: `0x18000365a`
- name: `SetMsMppeSendRecvKeys`
- size: `390`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180003770`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800034d4`
- `0x18002a138`
- `0x180032460`
- `0x180033010`

## string_xrefs

- `0x1800035ef`: `RasCompressionSetInfo failed, Error=%d`

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
  v9 = (*((__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *))&xmmword_18004C490 + 1))(a1, v18, v12);
  v10 = v9;
  if ( v9 && byte_18004CF33 < 0 )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"RasCompressionSetInfo failed, Error=%d", v9);
    if ( byte_18004CF33 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v24);
  }
  return v10;
}

```

## disassembly

```asm
0x1800034d4  mov     [rsp-8+arg_18], rbx
0x1800034d9  push    rbp
0x1800034da  push    rsi
0x1800034db  push    rdi
0x1800034dc  lea     rbp, [rsp-0A10h]
0x1800034e4  sub     rsp, 0B10h
0x1800034eb  mov     rax, cs:__security_cookie
0x1800034f2  xor     rax, rsp
0x1800034f5  mov     [rbp+0A20h+var_20], rax
0x1800034fc  mov     rbx, r8
0x1800034ff  mov     rdi, rdx
0x180003502  mov     rsi, rcx
0x180003505  xor     edx, edx; Val
0x180003507  mov     r8d, 170h; Size
0x18000350d  lea     rcx, [rsp+0B20h+var_B00]; void *
0x180003512  call    memset_0
0x180003517  xor     eax, eax
0x180003519  lea     rcx, [rbp+0A20h+var_81C]; void *
0x180003520  xor     edx, edx; Val
0x180003522  mov     [rbp+0A20h+var_820], eax
0x180003528  mov     r8d, 7FCh; Size
0x18000352e  call    memset_0
0x180003533  cmp     dword ptr [rdi+4], 8
0x180003537  jbe     loc_180003633
0x18000353d  xor     edx, edx; Val
0x18000353f  lea     rcx, [rbp+0A20h+var_990]; void *
0x180003546  mov     r8d, 170h; Size
0x18000354c  call    memset_0
0x180003551  mov     rdx, [rdi+8]
0x180003555  lea     rcx, [rbp+0A20h+var_920]; void *
0x18000355c  mov     [rbp+0A20h+var_950], 0FFh
0x180003563  movzx   eax, byte ptr [rdx+8]
0x180003567  add     rdx, 9; Src
0x18000356b  mov     r8d, eax; Size
0x18000356e  mov     [rbp+0A20h+var_924], eax
0x180003574  call    memcpy_0
0x180003579  cmp     dword ptr [rbx+4], 8
0x18000357d  mov     edi, 4
0x180003582  mov     [rbp+0A20h+var_928], edi
0x180003588  mov     [rbp+0A20h+var_954], 3
0x180003592  jbe     loc_180003633
0x180003598  mov     rdx, [rbx+8]
0x18000359c  lea     rcx, [rbp+0A20h+var_A90]; void *
0x1800035a0  mov     [rsp+0B20h+var_AC0], 0FFh
0x1800035a5  movzx   eax, byte ptr [rdx+8]
0x1800035a9  add     rdx, 9; Src
0x1800035ad  mov     r8d, eax; Size
0x1800035b0  mov     [rbp+0A20h+var_A94], eax
0x1800035b3  call    memcpy_0
0x1800035b8  mov     rax, qword ptr cs:xmmword_18004C490+8
0x1800035bf  lea     r8, [rsp+0B20h+var_B00]
0x1800035c4  lea     rdx, [rbp+0A20h+var_990]
0x1800035cb  mov     [rbp+0A20h+var_A98], edi
0x1800035ce  mov     rcx, rsi
0x1800035d1  mov     [rsp+0B20h+var_AC4], 3
0x1800035d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035de  mov     ebx, eax
0x1800035e0  test    eax, eax
0x1800035e2  jz      short loc_18000362F
0x1800035e4  cmp     cs:byte_18004CF33, 0
0x1800035eb  jge     short loc_18000362F
0x1800035ed  xor     ecx, ecx
0x1800035ef  lea     rdx, aRascompression; "RasCompressionSetInfo failed, Error=%d"
0x1800035f6  mov     word ptr [rbp+0A20h+var_820], cx
0x1800035fd  mov     r8d, eax
0x180003600  lea     rcx, [rbp+0A20h+var_820]
0x180003607  call    FormatRRASErrorString
0x18000360c  cmp     cs:byte_18004CF33, 0
0x180003613  jge     short loc_18000362F
0x180003615  lea     r8, [rbp+0A20h+var_820]
0x18000361c  lea     rdx, RasPppTraceError
0x180003623  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000362a  call    McTemplateU0z_EventWriteTransfer
0x18000362f  mov     eax, ebx
0x180003631  jmp     short loc_180003638
0x180003633  mov     eax, 57h ; 'W'
0x180003638  mov     rcx, [rbp+0A20h+var_20]
0x18000363f  xor     rcx, rsp; StackCookie
0x180003642  call    __security_check_cookie
0x180003647  mov     rbx, [rsp+0B20h+arg_18]
0x18000364f  add     rsp, 0B10h
0x180003656  pop     rdi
0x180003657  pop     rsi
0x180003658  pop     rbp
0x180003659  retn
```
