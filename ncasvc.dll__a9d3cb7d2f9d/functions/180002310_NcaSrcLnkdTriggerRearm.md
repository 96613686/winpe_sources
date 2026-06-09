# NcaSrcLnkdTriggerRearm

- ea: `0x180002310`
- end: `0x18000249c`
- name: `NcaSrcLnkdTriggerRearm`
- size: `396`
- prototype: `void __fastcall(__int64)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x180001400`
- `0x1800030b0`
- `0x180005180`
- `0x180005c20`
- `0x180010350`
- `0x180010710`
- `0x180010aa0`
- `0x180012fe0`
- `0x1800134c0`
- `0x180013b40`
- `0x180013f60`
- `0x1800147d0`
- `0x1800155e0`

## callees

- `0x180002310`
- `0x180004f04`
- `0x180004f34`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180002433`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180002433`

## pseudocode

```c
void __fastcall NcaSrcLnkdTriggerRearm(__int64 a1)
{
  PVOID *v2; // rcx
  __int64 v3; // rbx
  unsigned int v4; // ebx
  __int64 v5; // rdx
  struct _TP_WAIT *v6; // rax
  void *v7; // rdx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v2 == &WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)v2 + 28) & 1) == 0 )
      goto LABEL_30;
    WPP_SF_d(v2[2], 37, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, 87);
    goto LABEL_29;
  }
  v3 = *(_QWORD *)(a1 + 24);
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
  {
    WPP_SF_(v2[2], 19, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    v6 = *(struct _TP_WAIT **)v3;
    if ( *(_QWORD *)v3 )
    {
      v7 = *(void **)(v3 + 8);
      if ( v7 )
      {
        v4 = 0;
        SetThreadpoolWait(v6, v7, 0);
        goto LABEL_25;
      }
      if ( v2 == &WPP_GLOBAL_Control )
        return;
      v4 = 87;
      if ( (*((_BYTE *)v2 + 28) & 1) != 0 )
      {
        v5 = 22;
        goto LABEL_15;
      }
    }
    else
    {
      if ( v2 == &WPP_GLOBAL_Control )
        return;
      v4 = 87;
      if ( (*((_BYTE *)v2 + 28) & 1) != 0 )
      {
        v5 = 21;
        goto LABEL_15;
      }
    }
  }
  else
  {
    if ( v2 == &WPP_GLOBAL_Control )
      return;
    v4 = 87;
    if ( (*((_BYTE *)v2 + 28) & 1) != 0 )
    {
      v5 = 20;
LABEL_15:
      WPP_SF_d(v2[2], v5, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, 87);
LABEL_25:
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v2 == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)v2 + 28) & 8) != 0 )
  {
    WPP_SF_d(v2[2], 23, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, v4);
LABEL_29:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_30:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_(v2[2], 38, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids);
}

```

## disassembly

```asm
0x180002310  mov     [rsp+arg_0], rbx
0x180002315  push    rdi
0x180002316  sub     rsp, 20h
0x18000231a  mov     rbx, rcx
0x18000231d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002324  lea     rdi, WPP_GLOBAL_Control
0x18000232b  cmp     rcx, rdi
0x18000232e  jz      short loc_180002352
0x180002330  test    byte ptr [rcx+1Ch], 8
0x180002334  jz      short loc_180002352
0x180002336  mov     rcx, [rcx+10h]
0x18000233a  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x180002341  mov     edx, 24h ; '$'
0x180002346  call    WPP_SF_
0x18000234b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002352  test    rbx, rbx
0x180002355  jnz     short loc_18000238A
0x180002357  cmp     rcx, rdi
0x18000235a  jz      loc_180002490
0x180002360  test    byte ptr [rcx+1Ch], 1
0x180002364  jz      loc_180002470
0x18000236a  mov     rcx, [rcx+10h]
0x18000236e  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x180002375  mov     edx, 25h ; '%'
0x18000237a  mov     r9d, 57h ; 'W'
0x180002380  call    WPP_SF_d
0x180002385  jmp     loc_180002469
0x18000238a  mov     rbx, [rbx+18h]
0x18000238e  cmp     rcx, rdi
0x180002391  jz      short loc_1800023B5
0x180002393  test    byte ptr [rcx+1Ch], 8
0x180002397  jz      short loc_1800023B5
0x180002399  mov     rcx, [rcx+10h]
0x18000239d  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x1800023a4  mov     edx, 13h
0x1800023a9  call    WPP_SF_
0x1800023ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023b5  test    rbx, rbx
0x1800023b8  jnz     short loc_1800023E8
0x1800023ba  cmp     rcx, rdi
0x1800023bd  jz      loc_180002490
0x1800023c3  test    byte ptr [rcx+1Ch], 1
0x1800023c7  mov     ebx, 57h ; 'W'
0x1800023cc  jz      short loc_180002446
0x1800023ce  mov     edx, 14h
0x1800023d3  mov     rcx, [rcx+10h]
0x1800023d7  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x1800023de  mov     r9d, ebx
0x1800023e1  call    WPP_SF_d
0x1800023e6  jmp     short loc_18000243F
0x1800023e8  mov     rax, [rbx]
0x1800023eb  test    rax, rax
0x1800023ee  jnz     short loc_18000240B
0x1800023f0  cmp     rcx, rdi
0x1800023f3  jz      loc_180002490
0x1800023f9  test    byte ptr [rcx+1Ch], 1
0x1800023fd  mov     ebx, 57h ; 'W'
0x180002402  jz      short loc_180002446
0x180002404  mov     edx, 15h
0x180002409  jmp     short loc_1800023D3
0x18000240b  mov     rdx, [rbx+8]; h
0x18000240f  test    rdx, rdx
0x180002412  jnz     short loc_18000242B
0x180002414  cmp     rcx, rdi
0x180002417  jz      short loc_180002490
0x180002419  test    byte ptr [rcx+1Ch], 1
0x18000241d  mov     ebx, 57h ; 'W'
0x180002422  jz      short loc_180002446
0x180002424  mov     edx, 16h
0x180002429  jmp     short loc_1800023D3
0x18000242b  xor     ebx, ebx
0x18000242d  xor     r8d, r8d; pftTimeout
0x180002430  mov     rcx, rax; pwa
0x180002433  call    cs:__imp_SetThreadpoolWait
0x18000243a  nop     dword ptr [rax+rax+00h]
0x18000243f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002446  cmp     rcx, rdi
0x180002449  jz      short loc_180002490
0x18000244b  test    byte ptr [rcx+1Ch], 8
0x18000244f  jz      short loc_180002470
0x180002451  mov     rcx, [rcx+10h]
0x180002455  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000245c  mov     edx, 17h
0x180002461  mov     r9d, ebx
0x180002464  call    WPP_SF_d
0x180002469  mov     rcx, cs:WPP_GLOBAL_Control
0x180002470  cmp     rcx, rdi
0x180002473  jz      short loc_180002490
0x180002475  test    byte ptr [rcx+1Ch], 8
0x180002479  jz      short loc_180002490
0x18000247b  mov     rcx, [rcx+10h]
0x18000247f  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x180002486  mov     edx, 26h ; '&'
0x18000248b  call    WPP_SF_
0x180002490  mov     rbx, [rsp+28h+arg_0]
0x180002495  add     rsp, 20h
0x180002499  pop     rdi
0x18000249a  retn
```
