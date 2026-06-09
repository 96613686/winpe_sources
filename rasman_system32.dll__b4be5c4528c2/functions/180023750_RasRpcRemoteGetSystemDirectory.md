# RasRpcRemoteGetSystemDirectory

- ea: `0x180023750`
- end: `0x180023840`
- name: `RasRpcRemoteGetSystemDirectory`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180021b14`
- `0x180021fd4`
- `0x180023750`
- `0x18002464c`

## pseudocode

```c
__int64 __fastcall RasRpcRemoteGetSystemDirectory(__int64 a1)
{
  PVOID *v2; // rcx
  unsigned int SystemDirectory; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r9

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids, a1);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 || *(_DWORD *)(a1 + 8) )
  {
    v4 = 87;
    if ( v2 == &WPP_GLOBAL_Control )
      return v4;
    if ( (*((_BYTE *)v2 + 28) & 0x40) == 0 || *((_BYTE *)v2 + 25) < 2u )
      goto LABEL_18;
    v5 = 36;
    v6 = 87;
    goto LABEL_16;
  }
  SystemDirectory = RemoteGetSystemDirectory(a1);
  v4 = SystemDirectory;
  if ( !SystemDirectory )
  {
LABEL_17:
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = 37;
    v6 = SystemDirectory;
LABEL_16:
    WPP_SF_d(v2[2], v5, &WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids, v6);
    goto LABEL_17;
  }
LABEL_18:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 38, &WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180023750  mov     [rsp+arg_0], rbx
0x180023755  push    rsi
0x180023756  sub     rsp, 20h
0x18002375a  mov     rbx, rcx
0x18002375d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023764  lea     rsi, WPP_GLOBAL_Control
0x18002376b  cmp     rcx, rsi
0x18002376e  jz      short loc_18002379B
0x180023770  test    byte ptr [rcx+1Ch], 40h
0x180023774  jz      short loc_18002379B
0x180023776  cmp     byte ptr [rcx+19h], 6
0x18002377a  jb      short loc_18002379B
0x18002377c  mov     rcx, [rcx+10h]
0x180023780  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x180023787  mov     edx, 23h ; '#'
0x18002378c  mov     r9, rbx
0x18002378f  call    WPP_SF_q
0x180023794  mov     rcx, cs:WPP_GLOBAL_Control
0x18002379b  test    rbx, rbx
0x18002379e  jz      short loc_1800237D6
0x1800237a0  cmp     dword ptr [rbx+8], 0
0x1800237a4  jnz     short loc_1800237D6
0x1800237a6  mov     rcx, rbx
0x1800237a9  call    RemoteGetSystemDirectory
0x1800237ae  mov     ebx, eax
0x1800237b0  test    eax, eax
0x1800237b2  jz      short loc_180023802
0x1800237b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800237bb  cmp     rcx, rsi
0x1800237be  jz      short loc_180023832
0x1800237c0  test    byte ptr [rcx+1Ch], 40h
0x1800237c4  jz      short loc_180023809
0x1800237c6  cmp     byte ptr [rcx+19h], 2
0x1800237ca  jb      short loc_180023809
0x1800237cc  mov     edx, 25h ; '%'
0x1800237d1  mov     r9d, eax
0x1800237d4  jmp     short loc_1800237F2
0x1800237d6  mov     ebx, 57h ; 'W'
0x1800237db  cmp     rcx, rsi
0x1800237de  jz      short loc_180023832
0x1800237e0  test    byte ptr [rcx+1Ch], 40h
0x1800237e4  jz      short loc_180023809
0x1800237e6  cmp     byte ptr [rcx+19h], 2
0x1800237ea  jb      short loc_180023809
0x1800237ec  lea     edx, [rbx-33h]
0x1800237ef  mov     r9d, ebx
0x1800237f2  mov     rcx, [rcx+10h]
0x1800237f6  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x1800237fd  call    WPP_SF_d
0x180023802  mov     rcx, cs:WPP_GLOBAL_Control
0x180023809  cmp     rcx, rsi
0x18002380c  jz      short loc_180023832
0x18002380e  test    byte ptr [rcx+1Ch], 40h
0x180023812  jz      short loc_180023832
0x180023814  cmp     byte ptr [rcx+19h], 6
0x180023818  jb      short loc_180023832
0x18002381a  mov     rcx, [rcx+10h]
0x18002381e  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x180023825  mov     edx, 26h ; '&'
0x18002382a  mov     r9d, ebx
0x18002382d  call    WPP_SF_d
0x180023832  mov     eax, ebx
0x180023834  mov     rbx, [rsp+28h+arg_0]
0x180023839  add     rsp, 20h
0x18002383d  pop     rsi
0x18002383e  retn
```
