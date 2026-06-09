# DeActivateRasConfig

- ea: `0x18001c1bc`
- end: `0x18001c301`
- name: `DeActivateRasConfig`
- size: `325`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001f760`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001c1bc`
- `0x180020920`
- `0x18002b0dc`
- `0x180032b1c`
- `0x180034010`

## string_xrefs

- `0x18001c214`: `DeActivateRasConfig`

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
    v3 = *((_QWORD *)&xmmword_18004D860 + 1);
    if ( *((_QWORD *)&xmmword_18004D860 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004D860 + 1),
        L"DeActivateRasConfig");
    if ( !*a1 )
      RasTcpAdjustMulticastRouteMetric(a1[36], 0);
    if ( a1[522] != 2 )
    {
      if ( a1[4] )
      {
        LOBYTE(v3) = 1;
        ((void (__fastcall *)(_QWORD, __int64, __int64))xmmword_18004D450)(
          0,
          v3,
          (a1[314] & 0xFFFFFF | 0x17000000LL) << 24);
      }
      if ( *((_QWORD *)&xmmword_18004D860 + 1) )
      {
        v4 = (unsigned int)a1[36];
        v5 = &dword_18003A974;
        v6 = a1[4] == 0;
        LOWORD(v8) = 0;
        if ( v6 )
          v5 = (int *)"!";
        FormatRRASErrorString((wchar_t *)&v8, L"HelperResetDefaultInterfaceNet(0x%x, %hsPrioritizeRemote)", v4, v5);
        ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          *((_QWORD *)&xmmword_18004D860 + 1),
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
0x18001c1bc  mov     [rsp+arg_8], rbx
0x18001c1c1  push    rdi
0x18001c1c2  sub     rsp, 840h
0x18001c1c9  mov     rax, cs:__security_cookie
0x18001c1d0  xor     rax, rsp
0x18001c1d3  mov     [rsp+848h+var_18], rax
0x18001c1db  mov     rbx, rcx
0x18001c1de  xor     eax, eax
0x18001c1e0  lea     rcx, [rsp+848h+var_814]; void *
0x18001c1e5  mov     [rsp+848h+var_818], eax
0x18001c1e9  xor     edx, edx; Val
0x18001c1eb  mov     r8d, 7FCh; Size
0x18001c1f1  xor     edi, edi
0x18001c1f3  call    memset_0
0x18001c1f8  cmp     [rbx+18h], edi
0x18001c1fb  jz      loc_18001C2DD
0x18001c201  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001c208  test    rdx, rdx
0x18001c20b  jz      short loc_18001C227
0x18001c20d  mov     rcx, cs:gRasIpcpEtwContext
0x18001c214  lea     r8, aDeactivaterasc; "DeActivateRasConfig"
0x18001c21b  mov     rax, cs:gRasIpcpTemplateFunc
0x18001c222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c227  cmp     [rbx], edi
0x18001c229  jnz     short loc_18001C238
0x18001c22b  mov     ecx, [rbx+90h]
0x18001c231  xor     edx, edx
0x18001c233  call    RasTcpAdjustMulticastRouteMetric
0x18001c238  cmp     dword ptr [rbx+828h], 2
0x18001c23f  jz      loc_18001C2D3
0x18001c245  cmp     [rbx+10h], edi
0x18001c248  jz      short loc_18001C277
0x18001c24a  mov     r8d, [rbx+4E8h]
0x18001c251  mov     r9b, 1
0x18001c254  mov     rax, qword ptr cs:xmmword_18004D450
0x18001c25b  and     r8d, 0FFFFFFh
0x18001c262  or      r8, 17000000h
0x18001c269  mov     dl, r9b
0x18001c26c  shl     r8, 18h
0x18001c270  xor     ecx, ecx
0x18001c272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c277  cmp     qword ptr cs:xmmword_18004D860+8, rdi
0x18001c27e  jz      short loc_18001C2D3
0x18001c280  mov     r8d, [rbx+90h]
0x18001c287  lea     r9, dword_18003A974
0x18001c28e  xor     eax, eax
0x18001c290  lea     rdx, aHelperresetdef; "HelperResetDefaultInterfaceNet(0x%x, %h"...
0x18001c297  cmp     [rbx+10h], edi
0x18001c29a  lea     rcx, [rsp+848h+var_818]
0x18001c29f  mov     word ptr [rsp+848h+var_818], ax
0x18001c2a4  lea     rax, asc_18003FEE0; "!"
0x18001c2ab  cmovz   r9, rax
0x18001c2af  call    FormatRRASErrorString
0x18001c2b4  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001c2bb  lea     r8, [rsp+848h+var_818]
0x18001c2c0  mov     rcx, cs:gRasIpcpEtwContext
0x18001c2c7  mov     rax, cs:gRasIpcpTemplateFunc
0x18001c2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2d3  mov     rcx, rbx
0x18001c2d6  call    ResetNetBTConfigInfo
0x18001c2db  mov     edi, eax
0x18001c2dd  mov     eax, edi
0x18001c2df  mov     rcx, [rsp+848h+var_18]
0x18001c2e7  xor     rcx, rsp; StackCookie
0x18001c2ea  call    __security_check_cookie
0x18001c2ef  mov     rbx, [rsp+848h+arg_8]
0x18001c2f7  add     rsp, 840h
0x18001c2fe  pop     rdi
0x18001c2ff  retn
```
