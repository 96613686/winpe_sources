# RasRpcRemoteRasDeleteEntry

- ea: `0x1800238c0`
- end: `0x1800239d2`
- name: `RasRpcRemoteRasDeleteEntry`
- size: `274`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180021b14`
- `0x1800238c0`
- `0x180023a60`
- `0x180024764`

## pseudocode

```c
__int64 __fastcall RasRpcRemoteRasDeleteEntry(__int64 a1, const char *a2, const char *a3)
{
  PVOID *v6; // rcx
  const char *v7; // rdx
  const char *v8; // rax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // eax

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v7 = a3;
    v8 = a2;
    if ( !a3 )
      v7 = L"<NULL>";
    if ( !a2 )
      v8 = L"<NULL>";
    WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v8, (__int64)v7);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v12 = RemoteRasDeleteEntry(a1, a2, a3);
    v9 = v12;
    if ( !v12 )
    {
LABEL_20:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_21;
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_21;
    v10 = 41;
    v11 = v12;
LABEL_19:
    WPP_SF_d(v6[2], v10, &WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids, v11);
    goto LABEL_20;
  }
  v9 = 87;
  if ( v6 == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 2u )
  {
    v10 = 40;
    v11 = 87;
    goto LABEL_19;
  }
LABEL_21:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_d(v6[2], 42, &WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1800238c0  push    rbx
0x1800238c2  push    rsi
0x1800238c3  push    rdi
0x1800238c4  push    r14
0x1800238c6  sub     rsp, 38h
0x1800238ca  mov     rdi, r8
0x1800238cd  mov     rsi, rdx
0x1800238d0  mov     rbx, rcx
0x1800238d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238da  lea     r14, WPP_GLOBAL_Control
0x1800238e1  cmp     rcx, r14
0x1800238e4  jz      short loc_18002392A
0x1800238e6  test    byte ptr [rcx+1Ch], 40h
0x1800238ea  jz      short loc_18002392A
0x1800238ec  cmp     byte ptr [rcx+19h], 6
0x1800238f0  jb      short loc_18002392A
0x1800238f2  mov     rcx, [rcx+10h]; LoggerHandle
0x1800238f6  lea     r8, aNull_2; "<NULL>"
0x1800238fd  test    rdi, rdi
0x180023900  mov     rdx, rdi
0x180023903  mov     rax, rsi
0x180023906  mov     r9, rbx
0x180023909  cmovz   rdx, r8
0x18002390d  test    rsi, rsi
0x180023910  mov     [rsp+58h+var_30], rdx; __int64
0x180023915  cmovz   rax, r8
0x180023919  mov     [rsp+58h+var_38], rax; __int64
0x18002391e  call    WPP_SF_qSS
0x180023923  mov     rcx, cs:WPP_GLOBAL_Control
0x18002392a  test    rbx, rbx
0x18002392d  jnz     short loc_180023951
0x18002392f  mov     ebx, 57h ; 'W'
0x180023934  cmp     rcx, r14
0x180023937  jz      loc_1800239C5
0x18002393d  test    byte ptr [rcx+1Ch], 40h
0x180023941  jz      short loc_18002399C
0x180023943  cmp     byte ptr [rcx+19h], 2
0x180023947  jb      short loc_18002399C
0x180023949  lea     edx, [rbx-2Fh]
0x18002394c  mov     r9d, ebx
0x18002394f  jmp     short loc_180023985
0x180023951  mov     r8, rdi
0x180023954  mov     rdx, rsi
0x180023957  mov     rcx, rbx
0x18002395a  call    RemoteRasDeleteEntry
0x18002395f  mov     ebx, eax
0x180023961  test    eax, eax
0x180023963  jz      short loc_180023995
0x180023965  mov     rcx, cs:WPP_GLOBAL_Control
0x18002396c  cmp     rcx, r14
0x18002396f  jz      short loc_1800239C5
0x180023971  test    byte ptr [rcx+1Ch], 40h
0x180023975  jz      short loc_18002399C
0x180023977  cmp     byte ptr [rcx+19h], 2
0x18002397b  jb      short loc_18002399C
0x18002397d  mov     edx, 29h ; ')'
0x180023982  mov     r9d, eax
0x180023985  mov     rcx, [rcx+10h]
0x180023989  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x180023990  call    WPP_SF_d
0x180023995  mov     rcx, cs:WPP_GLOBAL_Control
0x18002399c  cmp     rcx, r14
0x18002399f  jz      short loc_1800239C5
0x1800239a1  test    byte ptr [rcx+1Ch], 40h
0x1800239a5  jz      short loc_1800239C5
0x1800239a7  cmp     byte ptr [rcx+19h], 6
0x1800239ab  jb      short loc_1800239C5
0x1800239ad  mov     rcx, [rcx+10h]
0x1800239b1  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x1800239b8  mov     edx, 2Ah ; '*'
0x1800239bd  mov     r9d, ebx
0x1800239c0  call    WPP_SF_d
0x1800239c5  mov     eax, ebx
0x1800239c7  add     rsp, 38h
0x1800239cb  pop     r14
0x1800239cd  pop     rdi
0x1800239ce  pop     rsi
0x1800239cf  pop     rbx
0x1800239d0  retn
```
