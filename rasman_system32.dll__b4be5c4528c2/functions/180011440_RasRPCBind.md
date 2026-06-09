# RasRPCBind

- ea: `0x180011440`
- end: `0x18001157b`
- name: `RasRPCBind`
- size: `315`
- prototype: `__int64 __fastcall(wchar_t *String1, RPC_BINDING_HANDLE *Binding)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013f40`
- `0x180024290`

## callees

- `0x180011440`
- `0x180011d34`
- `0x180021ae4`
- `0x180021b14`

## pseudocode

```c
DWORD __fastcall RasRPCBind(wchar_t *String1, RPC_BINDING_HANDLE *Binding, __int64 a3, __int64 a4)
{
  DWORD result; // eax
  int v7; // ebx
  PVOID *v8; // rcx
  int v9; // [rsp+20h] [rbp-88h]
  int v10; // [rsp+28h] [rbp-80h]
  int v11; // [rsp+30h] [rbp-78h]
  int v12; // [rsp+38h] [rbp-70h]
  int v13; // [rsp+40h] [rbp-68h]
  int v14; // [rsp+50h] [rbp-58h]
  int v15; // [rsp+58h] [rbp-50h]
  RPC_SECURITY_QOS v16; // [rsp+70h] [rbp-38h] BYREF
  __int128 v17; // [rsp+80h] [rbp-28h]
  __int64 v18; // [rsp+90h] [rbp-18h]
  __int64 v19; // [rsp+98h] [rbp-10h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xAu, &WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids);
  }
  v18 = 0;
  v19 = 1;
  v17 = 0;
  *(_QWORD *)&v16.Version = 4;
  v16.IdentityTracking = 1;
  v16.ImpersonationType = 3;
  result = RpcConnect(String1, (__int64)Binding, a3, a4, v9, v10, v11, v12, v13, &v16, v14, v15, Binding);
  v7 = result;
  if ( !result )
    goto LABEL_3;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xBu, &WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids, result);
LABEL_3:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d((TRACEHANDLE)v8[2], 0xCu, &WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180011440  mov     [rsp+arg_0], rbx
0x180011445  mov     [rsp+arg_8], rsi
0x18001144a  push    rdi
0x18001144b  sub     rsp, 0A0h
0x180011452  mov     rbx, rdx
0x180011455  mov     rdi, rcx
0x180011458  mov     rcx, cs:WPP_GLOBAL_Control
0x18001145f  lea     rsi, WPP_GLOBAL_Control
0x180011466  cmp     rcx, rsi
0x180011469  jnz     loc_1800114F1
0x18001146f  xor     eax, eax
0x180011471  mov     [rsp+0A8h+Binding], rbx; Binding
0x180011476  mov     [rsp+0A8h+var_18], rax
0x18001147e  xorps   xmm0, xmm0
0x180011481  lea     rax, [rsp+0A8h+var_38]
0x180011486  mov     [rsp+0A8h+var_10], 1
0x180011492  mov     rcx, rdi; String1
0x180011495  mov     [rsp+0A8h+var_60], rax; RPC_SECURITY_QOS *
0x18001149a  movdqu  [rsp+0A8h+var_28], xmm0
0x1800114a3  mov     qword ptr [rsp+0A8h+var_38.Version], 4
0x1800114ac  mov     [rsp+0A8h+var_38.IdentityTracking], 1
0x1800114b4  mov     [rsp+0A8h+var_38.ImpersonationType], 3
0x1800114bc  call    RpcConnect
0x1800114c1  mov     ebx, eax
0x1800114c3  test    eax, eax
0x1800114c5  jnz     short loc_18001151F
0x1800114c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114ce  cmp     rcx, rsi
0x1800114d1  jz      short loc_1800114D9
0x1800114d3  test    byte ptr [rcx+1Ch], 40h
0x1800114d7  jnz     short loc_180011554
0x1800114d9  mov     eax, ebx
0x1800114db  lea     r11, [rsp+0A8h+var_8]
0x1800114e3  mov     rbx, [r11+10h]
0x1800114e7  mov     rsi, [r11+18h]
0x1800114eb  mov     rsp, r11
0x1800114ee  pop     rdi
0x1800114ef  retn
0x1800114f1  test    byte ptr [rcx+1Ch], 40h
0x1800114f5  jz      loc_18001146F
0x1800114fb  cmp     byte ptr [rcx+19h], 6
0x1800114ff  jb      loc_18001146F
0x180011505  mov     rcx, [rcx+10h]
0x180011509  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x180011510  mov     edx, 0Ah
0x180011515  call    WPP_SF_
0x18001151a  jmp     loc_18001146F
0x18001151f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011526  cmp     rcx, rsi
0x180011529  jz      short loc_1800114DB
0x18001152b  test    byte ptr [rcx+1Ch], 40h
0x18001152f  jz      short loc_1800114CE
0x180011531  cmp     byte ptr [rcx+19h], 2
0x180011535  jb      short loc_1800114CE
0x180011537  mov     rcx, [rcx+10h]
0x18001153b  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x180011542  mov     edx, 0Bh
0x180011547  mov     r9d, ebx
0x18001154a  call    WPP_SF_d
0x18001154f  jmp     loc_1800114C7
0x180011554  cmp     byte ptr [rcx+19h], 6
0x180011558  jb      loc_1800114D9
0x18001155e  mov     rcx, [rcx+10h]
0x180011562  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x180011569  mov     edx, 0Ch
0x18001156e  mov     r9d, ebx
0x180011571  call    WPP_SF_d
0x180011576  jmp     loc_1800114D9
```
