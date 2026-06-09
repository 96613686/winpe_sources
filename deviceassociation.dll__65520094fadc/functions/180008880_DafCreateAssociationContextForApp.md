# DafCreateAssociationContextForApp

- ea: `0x180008880`
- end: `0x18000893f`
- name: `DafCreateAssociationContextForApp`
- size: `191`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, struct _DAC_CLIENT_CONTEXT **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008850`

## callees

- `0x180002284`
- `0x180002f10`
- `0x180008880`

## pseudocode

```c
__int64 __fastcall DafCreateAssociationContextForApp(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        RPC_BINDING_HANDLE **a6)
{
  _DWORD v11[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v12; // [rsp+28h] [rbp-60h]
  __int64 v13; // [rsp+30h] [rbp-58h]
  int v14; // [rsp+38h] [rbp-50h]
  int v15; // [rsp+3Ch] [rbp-4Ch]
  __int64 v16; // [rsp+40h] [rbp-48h]
  __int64 v17; // [rsp+48h] [rbp-40h]
  __int128 v18; // [rsp+50h] [rbp-38h]

  v11[1] = 0;
  v18 = 0;
  v17 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids);
  if ( !a2 || !a6 || (a3 & 0xFFFFFF80) != 0 )
    return 2147942487LL;
  v16 = a5;
  *a6 = 0;
  v11[0] = 1;
  v15 = a4;
  v14 = a3;
  v12 = a1;
  v13 = a2;
  return CreateContext((struct _DAC_CREATE_CONTEXT_PARAMS *)v11, a6);
}

```

## disassembly

```asm
0x180008880  push    rbx
0x180008882  push    rbp
0x180008883  push    rsi
0x180008884  push    rdi
0x180008885  sub     rsp, 68h
0x180008889  xorps   xmm0, xmm0
0x18000888c  mov     [rsp+88h+var_64], 0
0x180008894  movdqa  [rsp+88h+var_38], xmm0
0x18000889a  mov     esi, r9d
0x18000889d  mov     edi, r8d
0x1800088a0  mov     [rsp+88h+var_40], 0
0x1800088a9  mov     rbx, rdx
0x1800088ac  mov     rbp, rcx
0x1800088af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088b6  lea     rax, WPP_GLOBAL_Control
0x1800088bd  cmp     rcx, rax
0x1800088c0  jz      short loc_1800088DD
0x1800088c2  cmp     byte ptr [rcx+19h], 4
0x1800088c6  jb      short loc_1800088DD
0x1800088c8  mov     rcx, [rcx+10h]
0x1800088cc  lea     r8, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids
0x1800088d3  mov     edx, 0Ah
0x1800088d8  call    WPP_SF_s
0x1800088dd  test    rbx, rbx
0x1800088e0  jz      short loc_180008931
0x1800088e2  mov     rdx, [rsp+88h+arg_28]; struct _DAC_CLIENT_CONTEXT **
0x1800088ea  test    rdx, rdx
0x1800088ed  jz      short loc_180008931
0x1800088ef  test    edi, 0FFFFFF80h
0x1800088f5  jnz     short loc_180008931
0x1800088f7  mov     rax, [rsp+88h+arg_20]
0x1800088ff  lea     rcx, [rsp+88h+var_68]; struct _DAC_CREATE_CONTEXT_PARAMS *
0x180008904  mov     [rsp+88h+var_48], rax
0x180008909  mov     qword ptr [rdx], 0
0x180008910  mov     [rsp+88h+var_68], 1
0x180008918  mov     [rsp+88h+var_4C], esi
0x18000891c  mov     [rsp+88h+var_50], edi
0x180008920  mov     [rsp+88h+var_60], rbp
0x180008925  mov     [rsp+88h+var_58], rbx
0x18000892a  call    ?CreateContext@@YAJPEAU_DAC_CREATE_CONTEXT_PARAMS@@PEAPEAU_DAC_CLIENT_CONTEXT@@@Z; CreateContext(_DAC_CREATE_CONTEXT_PARAMS *,_DAC_CLIENT_CONTEXT * *)
0x18000892f  jmp     short loc_180008936
0x180008931  mov     eax, 80070057h
0x180008936  add     rsp, 68h
0x18000893a  pop     rdi
0x18000893b  pop     rsi
0x18000893c  pop     rbp
0x18000893d  pop     rbx
0x18000893e  retn
```
