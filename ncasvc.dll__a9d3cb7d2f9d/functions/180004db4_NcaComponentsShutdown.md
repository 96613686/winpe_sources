# NcaComponentsShutdown

- ea: `0x180004db4`
- end: `0x180004e4e`
- name: `NcaComponentsShutdown`
- size: `154`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004984`
- `0x180004cec`

## callees

- `0x180004db4`
- `0x180004f04`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall NcaComponentsShutdown(int a1, __int64 a2)
{
  PVOID *v4; // rcx
  __int64 result; // rax
  int v6; // ebx

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    result = WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v6 = a1 - 1;
  if ( v6 >= 0 )
  {
    do
      result = (*(__int64 (**)(void))(a2 + 16LL * (unsigned int)v6-- + 8))();
    while ( v6 >= 0 );
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    return WPP_SF_(v4[2], 46, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180004db4  mov     [rsp+arg_0], rbx
0x180004db9  mov     [rsp+arg_8], rsi
0x180004dbe  push    rdi
0x180004dbf  sub     rsp, 20h
0x180004dc3  mov     rdi, rdx
0x180004dc6  mov     ebx, ecx
0x180004dc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dcf  lea     rsi, WPP_GLOBAL_Control
0x180004dd6  cmp     rcx, rsi
0x180004dd9  jz      short loc_180004DFD
0x180004ddb  test    byte ptr [rcx+1Ch], 8
0x180004ddf  jz      short loc_180004DFD
0x180004de1  mov     rcx, [rcx+10h]
0x180004de5  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180004dec  mov     edx, 2Dh ; '-'
0x180004df1  call    WPP_SF_
0x180004df6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dfd  sub     ebx, 1
0x180004e00  js      short loc_180004E1D
0x180004e02  mov     eax, ebx
0x180004e04  add     rax, rax
0x180004e07  mov     rax, [rdi+rax*8+8]
0x180004e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e11  sub     ebx, 1
0x180004e14  jns     short loc_180004E02
0x180004e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e1d  cmp     rcx, rsi
0x180004e20  jz      short loc_180004E3D
0x180004e22  test    byte ptr [rcx+1Ch], 8
0x180004e26  jz      short loc_180004E3D
0x180004e28  mov     rcx, [rcx+10h]
0x180004e2c  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180004e33  mov     edx, 2Eh ; '.'
0x180004e38  call    WPP_SF_
0x180004e3d  mov     rbx, [rsp+28h+arg_0]
0x180004e42  mov     rsi, [rsp+28h+arg_8]
0x180004e47  add     rsp, 20h
0x180004e4b  pop     rdi
0x180004e4c  retn
```
