# RasRPCBind

- ea: `0x180010cc0`
- end: `0x180010df6`
- name: `RasRPCBind`
- size: `310`
- prototype: `__int64 __fastcall(wchar_t *String1, RPC_BINDING_HANDLE *Binding)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013700`
- `0x180023618`

## callees

- `0x180010cc0`
- `0x180011574`
- `0x180020fd8`
- `0x180021000`

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
0x180010cc0  mov     [rsp+arg_0], rbx
0x180010cc5  mov     [rsp+arg_8], rsi
0x180010cca  push    rdi
0x180010ccb  sub     rsp, 0A0h
0x180010cd2  mov     rbx, rdx
0x180010cd5  mov     rdi, rcx
0x180010cd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cdf  lea     rsi, WPP_GLOBAL_Control
0x180010ce6  cmp     rcx, rsi
0x180010ce9  jnz     loc_180010D70
0x180010cef  xor     eax, eax
0x180010cf1  mov     [rsp+0A8h+Binding], rbx; Binding
0x180010cf6  mov     [rsp+0A8h+var_18], rax
0x180010cfe  xorps   xmm0, xmm0
0x180010d01  lea     rax, [rsp+0A8h+var_38]
0x180010d06  mov     [rsp+0A8h+var_10], 1
0x180010d12  mov     rcx, rdi; String1
0x180010d15  mov     [rsp+0A8h+var_60], rax; RPC_SECURITY_QOS *
0x180010d1a  movdqu  [rsp+0A8h+var_28], xmm0
0x180010d23  mov     qword ptr [rsp+0A8h+var_38.Version], 4
0x180010d2c  mov     [rsp+0A8h+var_38.IdentityTracking], 1
0x180010d34  mov     [rsp+0A8h+var_38.ImpersonationType], 3
0x180010d3c  call    RpcConnect
0x180010d41  mov     ebx, eax
0x180010d43  test    eax, eax
0x180010d45  jnz     short loc_180010D9E
0x180010d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d4e  cmp     rcx, rsi
0x180010d51  jz      short loc_180010D59
0x180010d53  test    byte ptr [rcx+1Ch], 40h
0x180010d57  jnz     short loc_180010DD3
0x180010d59  mov     eax, ebx
0x180010d5b  lea     r11, [rsp+0A8h+var_8]
0x180010d63  mov     rbx, [r11+10h]
0x180010d67  mov     rsi, [r11+18h]
0x180010d6b  mov     rsp, r11
0x180010d6e  pop     rdi
0x180010d6f  retn
0x180010d70  test    byte ptr [rcx+1Ch], 40h
0x180010d74  jz      loc_180010CEF
0x180010d7a  cmp     byte ptr [rcx+19h], 6
0x180010d7e  jb      loc_180010CEF
0x180010d84  mov     rcx, [rcx+10h]
0x180010d88  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x180010d8f  mov     edx, 0Ah
0x180010d94  call    WPP_SF_
0x180010d99  jmp     loc_180010CEF
0x180010d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010da5  cmp     rcx, rsi
0x180010da8  jz      short loc_180010D5B
0x180010daa  test    byte ptr [rcx+1Ch], 40h
0x180010dae  jz      short loc_180010D4E
0x180010db0  cmp     byte ptr [rcx+19h], 2
0x180010db4  jb      short loc_180010D4E
0x180010db6  mov     rcx, [rcx+10h]
0x180010dba  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x180010dc1  mov     edx, 0Bh
0x180010dc6  mov     r9d, ebx
0x180010dc9  call    WPP_SF_d
0x180010dce  jmp     loc_180010D47
0x180010dd3  cmp     byte ptr [rcx+19h], 6
0x180010dd7  jb      short loc_180010D59
0x180010dd9  mov     rcx, [rcx+10h]
0x180010ddd  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x180010de4  mov     edx, 0Ch
0x180010de9  mov     r9d, ebx
0x180010dec  call    WPP_SF_d
0x180010df1  jmp     loc_180010D59
```
