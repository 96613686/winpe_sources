# DeActivateRasConfig

- ea: `0x18001b7c0`
- end: `0x18001b904`
- name: `DeActivateRasConfig`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001ebd0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001b7c0`
- `0x18001fd58`
- `0x18002a138`
- `0x18003153c`
- `0x180033010`

## string_xrefs

- `0x18001b818`: `DeActivateRasConfig`

## pseudocode

```c
__int64 __fastcall DeActivateRasConfig(_DWORD *a1)
{
  unsigned int v2; // edi
  __int64 v3; // rdx
  __int64 v4; // r8
  int *v5; // r9
  bool v6; // zf
  int v8; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v9[2044]; // [rsp+34h] [rbp-814h] BYREF

  v8 = 0;
  v2 = 0;
  memset_0(v9, 0, sizeof(v9));
  if ( a1[6] )
  {
    v3 = *((_QWORD *)&xmmword_18004C860 + 1);
    if ( *((_QWORD *)&xmmword_18004C860 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004C860 + 1),
        L"DeActivateRasConfig");
    if ( !*a1 )
      RasTcpAdjustMulticastRouteMetric((unsigned int)a1[36], 0);
    if ( a1[522] != 2 )
    {
      if ( a1[4] )
      {
        LOBYTE(v3) = 1;
        ((void (__fastcall *)(_QWORD, __int64, __int64))xmmword_18004C450)(
          0,
          v3,
          (a1[314] & 0xFFFFFF | 0x17000000LL) << 24);
      }
      if ( *((_QWORD *)&xmmword_18004C860 + 1) )
      {
        v4 = (unsigned int)a1[36];
        v5 = &dword_180039974;
        v6 = a1[4] == 0;
        LOWORD(v8) = 0;
        if ( v6 )
          v5 = (int *)"!";
        FormatRRASErrorString(&v8, L"HelperResetDefaultInterfaceNet(0x%x, %hsPrioritizeRemote)", v4, v5);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004C860 + 1),
          &v8);
      }
    }
    return (unsigned int)ResetNetBTConfigInfo((__int64)a1);
  }
  return v2;
}

```

## disassembly

```asm
0x18001b7c0  mov     [rsp+arg_8], rbx
0x18001b7c5  push    rdi
0x18001b7c6  sub     rsp, 840h
0x18001b7cd  mov     rax, cs:__security_cookie
0x18001b7d4  xor     rax, rsp
0x18001b7d7  mov     [rsp+848h+var_18], rax
0x18001b7df  mov     rbx, rcx
0x18001b7e2  xor     eax, eax
0x18001b7e4  lea     rcx, [rsp+848h+var_814]; void *
0x18001b7e9  mov     [rsp+848h+var_818], eax
0x18001b7ed  xor     edx, edx; Val
0x18001b7ef  mov     r8d, 7FCh; Size
0x18001b7f5  xor     edi, edi
0x18001b7f7  call    memset_0
0x18001b7fc  cmp     [rbx+18h], edi
0x18001b7ff  jz      loc_18001B8E1
0x18001b805  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001b80c  test    rdx, rdx
0x18001b80f  jz      short loc_18001B82B
0x18001b811  mov     rcx, cs:gRasIpcpEtwContext
0x18001b818  lea     r8, aDeactivaterasc; "DeActivateRasConfig"
0x18001b81f  mov     rax, cs:gRasIpcpTemplateFunc
0x18001b826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b82b  cmp     [rbx], edi
0x18001b82d  jnz     short loc_18001B83C
0x18001b82f  mov     ecx, [rbx+90h]
0x18001b835  xor     edx, edx
0x18001b837  call    RasTcpAdjustMulticastRouteMetric
0x18001b83c  cmp     dword ptr [rbx+828h], 2
0x18001b843  jz      loc_18001B8D7
0x18001b849  cmp     [rbx+10h], edi
0x18001b84c  jz      short loc_18001B87B
0x18001b84e  mov     r8d, [rbx+4E8h]
0x18001b855  mov     r9b, 1
0x18001b858  mov     rax, qword ptr cs:xmmword_18004C450
0x18001b85f  and     r8d, 0FFFFFFh
0x18001b866  or      r8, 17000000h
0x18001b86d  mov     dl, r9b
0x18001b870  shl     r8, 18h
0x18001b874  xor     ecx, ecx
0x18001b876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b87b  cmp     qword ptr cs:xmmword_18004C860+8, rdi
0x18001b882  jz      short loc_18001B8D7
0x18001b884  mov     r8d, [rbx+90h]
0x18001b88b  lea     r9, dword_180039974
0x18001b892  xor     eax, eax
0x18001b894  lea     rdx, aHelperresetdef; "HelperResetDefaultInterfaceNet(0x%x, %h"...
0x18001b89b  cmp     [rbx+10h], edi
0x18001b89e  lea     rcx, [rsp+848h+var_818]
0x18001b8a3  mov     word ptr [rsp+848h+var_818], ax
0x18001b8a8  lea     rax, asc_18003EEE0; "!"
0x18001b8af  cmovz   r9, rax
0x18001b8b3  call    FormatRRASErrorString
0x18001b8b8  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001b8bf  lea     r8, [rsp+848h+var_818]
0x18001b8c4  mov     rcx, cs:gRasIpcpEtwContext
0x18001b8cb  mov     rax, cs:gRasIpcpTemplateFunc
0x18001b8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8d7  mov     rcx, rbx
0x18001b8da  call    ResetNetBTConfigInfo
0x18001b8df  mov     edi, eax
0x18001b8e1  mov     eax, edi
0x18001b8e3  mov     rcx, [rsp+848h+var_18]
0x18001b8eb  xor     rcx, rsp; StackCookie
0x18001b8ee  call    __security_check_cookie
0x18001b8f3  mov     rbx, [rsp+848h+arg_8]
0x18001b8fb  add     rsp, 840h
0x18001b902  pop     rdi
0x18001b903  retn
```
