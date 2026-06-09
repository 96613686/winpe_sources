# DafCreateAssociationContextFromOobBlob

- ea: `0x180008950`
- end: `0x180008a4e`
- name: `DafCreateAssociationContextFromOobBlob`
- size: `254`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, struct _DAC_CLIENT_CONTEXT **, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002284`
- `0x180002f10`
- `0x180008950`

## pseudocode

```c
__int64 __fastcall DafCreateAssociationContextFromOobBlob(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        _QWORD *a5,
        RPC_BINDING_HANDLE **a6,
        _DWORD *a7,
        _QWORD *a8)
{
  _DWORD v13[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v14; // [rsp+28h] [rbp-38h]
  int v15; // [rsp+30h] [rbp-30h]
  int v16; // [rsp+34h] [rbp-2Ch]
  __int64 v17; // [rsp+38h] [rbp-28h]
  int v18; // [rsp+40h] [rbp-20h]
  int v19; // [rsp+44h] [rbp-1Ch]
  _QWORD *v20; // [rsp+48h] [rbp-18h]
  _DWORD *v21; // [rsp+50h] [rbp-10h]
  _QWORD *v22; // [rsp+58h] [rbp-8h]

  v13[1] = 0;
  v16 = 0;
  v19 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids);
  if ( !a1 || !a2 || !a3 || (a4 & 0xFFFFFFD8) != 0 || !a5 || !a6 )
    return 2147942487LL;
  if ( a7 )
  {
    if ( !a8 )
      return 2147942487LL;
  }
  else if ( a8 )
  {
    return 2147942487LL;
  }
  *a5 = 0;
  *a6 = 0;
  v13[0] = 2;
  v14 = a1;
  v15 = a2;
  v17 = a3;
  v18 = a4;
  v20 = a5;
  v21 = a7;
  v22 = a8;
  if ( a7 )
  {
    if ( a8 )
    {
      *a7 = 0;
      *a8 = 0;
    }
  }
  return CreateContext((struct _DAC_CREATE_CONTEXT_PARAMS *)v13, a6);
}

```

## disassembly

```asm
0x180008950  push    rbp
0x180008952  push    rbx
0x180008953  push    rsi
0x180008954  push    rdi
0x180008955  push    r14
0x180008957  mov     rbp, rsp
0x18000895a  sub     rsp, 60h
0x18000895e  mov     r14d, r9d
0x180008961  mov     [rbp+var_3C], 0
0x180008968  mov     rbx, r8
0x18000896b  mov     [rbp+var_2C], 0
0x180008972  mov     edi, edx
0x180008974  mov     [rbp+var_1C], 0
0x18000897b  mov     rsi, rcx
0x18000897e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008985  lea     rax, WPP_GLOBAL_Control
0x18000898c  cmp     rcx, rax
0x18000898f  jz      short loc_1800089AC
0x180008991  cmp     byte ptr [rcx+19h], 4
0x180008995  jb      short loc_1800089AC
0x180008997  mov     rcx, [rcx+10h]
0x18000899b  lea     r8, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids
0x1800089a2  mov     edx, 0Ch
0x1800089a7  call    WPP_SF_s
0x1800089ac  test    rsi, rsi
0x1800089af  jz      short loc_1800089E7
0x1800089b1  test    edi, edi
0x1800089b3  jz      short loc_1800089E7
0x1800089b5  test    rbx, rbx
0x1800089b8  jz      short loc_1800089E7
0x1800089ba  test    r14d, 0FFFFFFD8h
0x1800089c1  jnz     short loc_1800089E7
0x1800089c3  mov     r8, [rbp+arg_20]
0x1800089c7  test    r8, r8
0x1800089ca  jz      short loc_1800089E7
0x1800089cc  mov     rdx, [rbp+arg_28]; struct _DAC_CLIENT_CONTEXT **
0x1800089d0  test    rdx, rdx
0x1800089d3  jz      short loc_1800089E7
0x1800089d5  mov     rcx, [rbp+arg_30]
0x1800089d9  mov     rax, [rbp+arg_38]
0x1800089dd  test    rcx, rcx
0x1800089e0  jz      short loc_1800089F7
0x1800089e2  test    rax, rax
0x1800089e5  jnz     short loc_1800089FC
0x1800089e7  mov     eax, 80070057h
0x1800089ec  add     rsp, 60h
0x1800089f0  pop     r14
0x1800089f2  pop     rdi
0x1800089f3  pop     rsi
0x1800089f4  pop     rbx
0x1800089f5  pop     rbp
0x1800089f6  retn
0x1800089f7  test    rax, rax
0x1800089fa  jnz     short loc_1800089E7
0x1800089fc  mov     qword ptr [r8], 0
0x180008a03  mov     qword ptr [rdx], 0
0x180008a0a  mov     [rbp+var_40], 2
0x180008a11  mov     [rbp+var_38], rsi
0x180008a15  mov     [rbp+var_30], edi
0x180008a18  mov     [rbp+var_28], rbx
0x180008a1c  mov     [rbp+var_20], r14d
0x180008a20  mov     [rbp+var_18], r8
0x180008a24  mov     [rbp+var_10], rcx
0x180008a28  mov     [rbp+var_8], rax
0x180008a2c  test    rcx, rcx
0x180008a2f  jz      short loc_180008A43
0x180008a31  test    rax, rax
0x180008a34  jz      short loc_180008A43
0x180008a36  mov     dword ptr [rcx], 0
0x180008a3c  mov     qword ptr [rax], 0
0x180008a43  lea     rcx, [rbp+var_40]; struct _DAC_CREATE_CONTEXT_PARAMS *
0x180008a47  call    ?CreateContext@@YAJPEAU_DAC_CREATE_CONTEXT_PARAMS@@PEAPEAU_DAC_CLIENT_CONTEXT@@@Z; CreateContext(_DAC_CREATE_CONTEXT_PARAMS *,_DAC_CLIENT_CONTEXT * *)
0x180008a4c  jmp     short loc_1800089EC
```
