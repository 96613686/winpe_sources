# EapProvPlugin_TestForAuthenticatingWlanInterfaces(ulong *)

- ea: `0x18001fa94`
- end: `0x18001fb47`
- name: `?EapProvPlugin_TestForAuthenticatingWlanInterfaces@@YAKPEAK@Z`
- size: `179`
- prototype: `unsigned int __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180010460`

## callees

- `0x180003bd0`
- `0x180006a20`
- `0x18001fa94`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall EapProvPlugin_TestForAuthenticatingWlanInterfaces(unsigned int *a1)
{
  bool v1; // zf
  unsigned int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // r9
  __int64 v7; // rdx

  v1 = g_hEapProvPluginDll == 0;
  *a1 = 0;
  if ( v1 || !xmmword_180033988 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids);
    return 0;
  }
  else
  {
    v3 = xmmword_180033988();
    v4 = v3;
    if ( v3 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v7 = 31;
        v6 = v3;
        goto LABEL_8;
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v6 = *a1;
        v7 = 30;
LABEL_8:
        WPP_SF_d(v5[2], v7, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, v6);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001fa94  mov     [rsp+arg_0], rbx
0x18001fa99  push    rdi
0x18001fa9a  sub     rsp, 20h
0x18001fa9e  cmp     cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hEapProvPluginDll
0x18001faa6  mov     rdi, rcx
0x18001faa9  mov     dword ptr [rcx], 0
0x18001faaf  jz      short loc_18001FB10
0x18001fab1  mov     rax, qword ptr cs:xmmword_180033988
0x18001fab8  test    rax, rax
0x18001fabb  jz      short loc_18001FB10
0x18001fabd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fac2  mov     ebx, eax
0x18001fac4  test    eax, eax
0x18001fac6  jnz     short loc_18001FAE3
0x18001fac8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001facf  lea     rdx, WPP_GLOBAL_Control
0x18001fad6  cmp     rcx, rdx
0x18001fad9  jz      short loc_18001FB3A
0x18001fadb  mov     r9d, [rdi]
0x18001fade  lea     edx, [rax+1Eh]
0x18001fae1  jmp     short loc_18001FAFE
0x18001fae3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001faea  lea     rdx, WPP_GLOBAL_Control
0x18001faf1  cmp     rcx, rdx
0x18001faf4  jz      short loc_18001FB3A
0x18001faf6  mov     edx, 1Fh
0x18001fafb  mov     r9d, eax
0x18001fafe  mov     rcx, [rcx+10h]
0x18001fb02  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18001fb09  call    WPP_SF_d
0x18001fb0e  jmp     short loc_18001FB3A
0x18001fb10  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb17  lea     rdx, WPP_GLOBAL_Control
0x18001fb1e  cmp     rcx, rdx
0x18001fb21  jz      short loc_18001FB38
0x18001fb23  mov     rcx, [rcx+10h]
0x18001fb27  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18001fb2e  mov     edx, 1Dh
0x18001fb33  call    WPP_SF_
0x18001fb38  xor     ebx, ebx
0x18001fb3a  mov     eax, ebx
0x18001fb3c  mov     rbx, [rsp+28h+arg_0]
0x18001fb41  add     rsp, 20h
0x18001fb45  pop     rdi
0x18001fb46  retn
```
