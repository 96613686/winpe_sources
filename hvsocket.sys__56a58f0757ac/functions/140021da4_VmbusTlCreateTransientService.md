# VmbusTlCreateTransientService

- ea: `0x140021da4`
- end: `0x140021eb8`
- name: `VmbusTlCreateTransientService`
- size: `276`
- prototype: `__int64 __fastcall(__int64, _OWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14001e1c0`
- `0x14001e5ac`

## callees

- `0x14000a154`
- `0x14000a234`
- `0x140021cb4`
- `0x140021da4`

## string_xrefs

- `0x140021dfb`: `VmbusTlCreateTransientService`

## pseudocode

```c
__int64 __fastcall VmbusTlCreateTransientService(__int64 a1, _OWORD *a2, _QWORD *a3)
{
  bool v3; // zf
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rsi
  _QWORD *v12; // rdx
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_BYTE *)(a1 + 393) == 0;
  v14 = 0;
  if ( v3 )
  {
    v8 = VmbusTlCreateService(&v14);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v11 = v14;
      *(_OWORD *)(v14 + 112) = *a2;
      *(_BYTE *)(v11 + 128) = 1;
      *(_DWORD *)(v11 + 156) = 1;
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceServiceMessage(v9, (__int64)a2, a1 + 232, v10);
      v12 = *(_QWORD **)(a1 + 368);
      if ( *v12 != a1 + 360 )
        __fastfail(3u);
      *a3 = v11;
      *(_QWORD *)(v11 + 96) = a1 + 360;
      *(_QWORD *)(v11 + 104) = v12;
      *v12 = v11 + 96;
      *(_QWORD *)(a1 + 368) = v11 + 96;
    }
    else if ( (unsigned int)dword_140013058 > 2 )
    {
      HvsocketTraceServiceError(
        (const int *)"VmbusTlCreateTransientService",
        505,
        (unsigned int)v8,
        (__int64)a2,
        a1 + 232);
    }
  }
  else
  {
    v7 = -1073741811;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceServiceError((const int *)"VmbusTlCreateTransientService", 497, 3221225485LL, (__int64)a2, a1 + 232);
  }
  return v7;
}

```

## disassembly

```asm
0x140021da4  mov     r11, rsp
0x140021da7  mov     [r11+10h], rbx
0x140021dab  mov     [r11+18h], rbp
0x140021daf  push    rsi
0x140021db0  push    rdi
0x140021db1  push    r14
0x140021db3  sub     rsp, 30h
0x140021db7  cmp     byte ptr [rcx+189h], 0
0x140021dbe  mov     r14, r8
0x140021dc1  mov     rbp, rdx
0x140021dc4  mov     qword ptr [r11+8], 0
0x140021dcc  mov     rdi, rcx
0x140021dcf  jz      short loc_140021E0C
0x140021dd1  mov     eax, cs:dword_140013058
0x140021dd7  mov     ebx, 0C000000Dh
0x140021ddc  cmp     eax, 2
0x140021ddf  jbe     loc_140021EA2
0x140021de5  lea     rax, [rcx+0E8h]
0x140021dec  mov     r8d, ebx
0x140021def  mov     [r11-28h], rax
0x140021df3  mov     edx, 1F1h
0x140021df8  mov     r9, rbp
0x140021dfb  lea     rcx, aVmbustlcreatet; "VmbusTlCreateTransientService"
0x140021e02  call    HvsocketTraceServiceError
0x140021e07  jmp     loc_140021EA2
0x140021e0c  lea     rcx, [rsp+48h+arg_0]
0x140021e11  call    VmbusTlCreateService
0x140021e16  mov     ebx, eax
0x140021e18  test    eax, eax
0x140021e1a  jns     short loc_140021E3D
0x140021e1c  mov     ecx, cs:dword_140013058
0x140021e22  cmp     ecx, 2
0x140021e25  jbe     short loc_140021EA2
0x140021e27  lea     rcx, [rdi+0E8h]
0x140021e2e  mov     r8d, eax
0x140021e31  mov     [rsp+48h+var_28], rcx
0x140021e36  mov     edx, 1F9h
0x140021e3b  jmp     short loc_140021DF8
0x140021e3d  mov     rsi, [rsp+48h+arg_0]
0x140021e42  movups  xmm0, xmmword ptr [rbp+0]
0x140021e46  movdqu  xmmword ptr [rsi+70h], xmm0
0x140021e4b  mov     byte ptr [rsi+80h], 1
0x140021e52  mov     dword ptr [rsi+9Ch], 1
0x140021e5c  mov     eax, cs:dword_140013058
0x140021e62  cmp     eax, 2
0x140021e65  jbe     short loc_140021E76
0x140021e67  lea     r8, [rdi+0E8h]
0x140021e6e  mov     rdx, rbp
0x140021e71  call    HvsocketTraceServiceMessage
0x140021e76  lea     rcx, [rdi+168h]
0x140021e7d  mov     rdx, [rcx+8]
0x140021e81  cmp     [rdx], rcx
0x140021e84  jz      short loc_140021E8D
0x140021e86  mov     ecx, 3
0x140021e8b  int     29h; Win8: RtlFailFast(ecx)
0x140021e8d  lea     rax, [rsi+60h]
0x140021e91  mov     [r14], rsi
0x140021e94  mov     [rax], rcx
0x140021e97  mov     [rax+8], rdx
0x140021e9b  mov     [rdx], rax
0x140021e9e  mov     [rcx+8], rax
0x140021ea2  mov     rbp, [rsp+48h+arg_10]
0x140021ea7  mov     eax, ebx
0x140021ea9  mov     rbx, [rsp+48h+arg_8]
0x140021eae  add     rsp, 30h
0x140021eb2  pop     r14
0x140021eb4  pop     rdi
0x140021eb5  pop     rsi
0x140021eb6  retn
```
