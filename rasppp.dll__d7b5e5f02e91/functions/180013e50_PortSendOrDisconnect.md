# PortSendOrDisconnect

- ea: `0x180013e50`
- end: `0x180013fc6`
- name: `PortSendOrDisconnect`
- size: `374`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `11`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800023c0`
- `0x18000442c`
- `0x18000d5e4`
- `0x18000d6b4`
- `0x18000d8b4`
- `0x18000dd20`
- `0x18000deb0`
- `0x18000dfac`
- `0x18000e1e0`
- `0x18000e298`
- `0x18000e358`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18001348c`
- `0x180013e50`
- `0x18002b0dc`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall PortSendOrDisconnect(__int64 a1, unsigned int a2)
{
  __int64 *v4; // rbx
  __int64 v5; // rdx
  int v6; // r15d
  unsigned int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // r8
  int v10; // eax
  unsigned int v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v13 = 0;
  v12 = 0;
  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  v4 = (__int64 *)(a1 + 16);
  if ( qword_18004DAB8 && (qword_18004DAB8(*v4, *(_QWORD *)(a1 + 40), a2, &v13, &v12), (v5 = v13) != 0) )
  {
    a2 = v12;
    v6 = 1;
  }
  else
  {
    v5 = *(_QWORD *)(a1 + 40);
    v6 = 0;
    v13 = v5;
    v12 = a2;
  }
  v7 = (*((__int64 (__fastcall **)(__int64, __int64, _QWORD))&xmmword_18004D460 + 1))(*v4, v5, a2);
  v8 = v7;
  if ( v7 )
  {
    if ( byte_18004DF33 < 0 )
    {
      v9 = *v4;
      LOWORD(v14) = 0;
      FormatRRASErrorString((wchar_t *)&v14, L"RasPortSend on port %d failed: %d", v9, v7);
      if ( byte_18004DF33 < 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasPppTraceError,
          (const wchar_t *)&v14);
    }
    *(_DWORD *)(a1 + 56) |= 0x8000u;
    v10 = *(_DWORD *)(a1 + 56);
    *(_DWORD *)(a1 + 1496) = v8;
    NotifyCaller(a1, (v10 & 4) != 0 ? 23 : 10, (unsigned int *)(a1 + 1496));
  }
  if ( v6 )
    ((void (__fastcall *)(__int64))qword_18004DAC0)(v13);
  return v8;
}

```

## disassembly

```asm
0x180013e50  mov     [rsp-8+arg_10], rbx
0x180013e55  push    rbp
0x180013e56  push    rsi
0x180013e57  push    rdi
0x180013e58  push    r14
0x180013e5a  push    r15
0x180013e5c  lea     rbp, [rsp-750h]
0x180013e64  sub     rsp, 850h
0x180013e6b  mov     rax, cs:__security_cookie
0x180013e72  xor     rax, rsp
0x180013e75  mov     [rbp+770h+var_30], rax
0x180013e7c  mov     r14d, edx
0x180013e7f  mov     [rsp+870h+var_838], 0
0x180013e88  mov     rsi, rcx
0x180013e8b  mov     [rsp+870h+var_840], 0
0x180013e93  xor     eax, eax
0x180013e95  lea     rcx, [rsp+870h+var_82C]; void *
0x180013e9a  xor     edx, edx; Val
0x180013e9c  mov     [rsp+870h+var_830], eax
0x180013ea0  mov     r8d, 7FCh; Size
0x180013ea6  call    memset_0
0x180013eab  mov     rax, cs:qword_18004DAB8
0x180013eb2  lea     rbx, [rsi+10h]
0x180013eb6  test    rax, rax
0x180013eb9  jz      short loc_180013EF0
0x180013ebb  mov     rdx, [rsi+28h]
0x180013ebf  lea     rcx, [rsp+870h+var_840]
0x180013ec4  mov     [rsp+870h+var_850], rcx
0x180013ec9  lea     r9, [rsp+870h+var_838]
0x180013ece  mov     rcx, [rbx]
0x180013ed1  mov     r8d, r14d
0x180013ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ed9  mov     rdx, [rsp+870h+var_838]
0x180013ede  test    rdx, rdx
0x180013ee1  jz      short loc_180013EF0
0x180013ee3  mov     r14d, [rsp+870h+var_840]
0x180013ee8  mov     r15d, 1
0x180013eee  jmp     short loc_180013F01
0x180013ef0  mov     rdx, [rsi+28h]
0x180013ef4  xor     r15d, r15d
0x180013ef7  mov     [rsp+870h+var_838], rdx
0x180013efc  mov     [rsp+870h+var_840], r14d
0x180013f01  mov     rcx, [rbx]
0x180013f04  mov     r8d, r14d
0x180013f07  mov     rax, qword ptr cs:xmmword_18004D460+8
0x180013f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f13  mov     edi, eax
0x180013f15  test    eax, eax
0x180013f17  jz      short loc_180013F87
0x180013f19  cmp     cs:byte_18004DF33, 0
0x180013f20  jge     short loc_180013F61
0x180013f22  mov     r8, [rbx]
0x180013f25  lea     rdx, aRasportsendOnP; "RasPortSend on port %d failed: %d"
0x180013f2c  xor     ecx, ecx
0x180013f2e  mov     r9d, eax
0x180013f31  mov     word ptr [rsp+870h+var_830], cx
0x180013f36  lea     rcx, [rsp+870h+var_830]
0x180013f3b  call    FormatRRASErrorString
0x180013f40  cmp     cs:byte_18004DF33, 0
0x180013f47  jge     short loc_180013F61
0x180013f49  lea     r8, [rsp+870h+var_830]
0x180013f4e  lea     rdx, RasPppTraceError
0x180013f55  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013f5c  call    McTemplateU0z_EventWriteTransfer
0x180013f61  bts     dword ptr [rsi+38h], 0Fh
0x180013f66  lea     r8, [rsi+5D8h]
0x180013f6d  mov     eax, [rsi+38h]
0x180013f70  mov     rcx, rsi
0x180013f73  and     al, 4
0x180013f75  mov     [r8], edi
0x180013f78  neg     al
0x180013f7a  sbb     edx, edx
0x180013f7c  and     edx, 0Dh
0x180013f7f  add     edx, 0Ah
0x180013f82  call    NotifyCaller
0x180013f87  test    r15d, r15d
0x180013f8a  jz      short loc_180013F9D
0x180013f8c  mov     rcx, [rsp+870h+var_838]
0x180013f91  mov     rax, cs:qword_18004DAC0
0x180013f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f9d  mov     eax, edi
0x180013f9f  mov     rcx, [rbp+770h+var_30]
0x180013fa6  xor     rcx, rsp; StackCookie
0x180013fa9  call    __security_check_cookie
0x180013fae  mov     rbx, [rsp+870h+arg_10]
0x180013fb6  add     rsp, 850h
0x180013fbd  pop     r15
0x180013fbf  pop     r14
0x180013fc1  pop     rdi
0x180013fc2  pop     rsi
0x180013fc3  pop     rbp
0x180013fc4  retn
```
