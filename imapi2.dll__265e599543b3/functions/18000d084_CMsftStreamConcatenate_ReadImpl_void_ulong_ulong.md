# CMsftStreamConcatenate::ReadImpl(void *,ulong,ulong *)

- ea: `0x18000d084`
- end: `0x18000d348`
- name: `?ReadImpl@CMsftStreamConcatenate@@QEAAJPEAXKPEAK@Z`
- size: `708`
- prototype: `__int64 __fastcall(CMsftStreamConcatenate *this, char *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180012c40`

## callees

- `0x18000d084`
- `0x180013dac`
- `0x180014134`
- `0x1800141d8`
- `0x180014250`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall CMsftStreamConcatenate::ReadImpl(
        CMsftStreamConcatenate *this,
        char *a2,
        unsigned int a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r12
  char *v5; // r10
  unsigned int v6; // edx
  int v7; // ebx
  __int64 v8; // rdi
  __int64 v9; // r13
  unsigned int v10; // r9d
  unsigned __int64 v12; // r15
  __int64 v13; // rcx
  unsigned int v14; // r8d
  __int64 v15; // rax
  int updated; // eax
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rax
  unsigned int v19; // ebp
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned int v22; // r9d
  char *v23; // r10
  unsigned int v25; // [rsp+50h] [rbp-58h]
  unsigned int v26; // [rsp+B0h] [rbp+8h] BYREF
  char *v27; // [rsp+B8h] [rbp+10h]
  unsigned int v28; // [rsp+C0h] [rbp+18h]
  unsigned int *v29; // [rsp+C8h] [rbp+20h]

  v29 = a4;
  v28 = a3;
  v27 = a2;
  v4 = *((_QWORD *)this + 5);
  v5 = a2;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v25 = 0;
  v9 = 0;
  v10 = a3;
  v12 = v4;
  if ( *((_DWORD *)this + 16) )
  {
    v13 = *((_QWORD *)this + 10);
    do
    {
      if ( v12 < *(_QWORD *)(v13 + 8 * v8) )
        goto LABEL_6;
      v12 -= *(_QWORD *)(v13 + 8 * v8);
      v9 += *(_QWORD *)(v13 + 8 * v8);
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < *((_DWORD *)this + 16) );
  }
  while ( v7 >= 0 )
  {
LABEL_6:
    if ( !v10 )
    {
      *((_QWORD *)this + 5) = v4;
      break;
    }
    v14 = *((_DWORD *)this + 16);
    if ( (unsigned int)v8 >= v14 )
    {
LABEL_34:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 508) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 505) >= 3u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 62),
          21,
          &WPP_47ba174de9f13fae433aca4eb423b804_Traceguids,
          (unsigned int)v8,
          v14);
        v6 = v25;
      }
      v7 = -2147418113;
      break;
    }
    v15 = v9 + *(_QWORD *)(*((_QWORD *)this + 10) + 8 * v8);
    if ( v4 == v15 )
    {
      v8 = (unsigned int)(v8 + 1);
      if ( (unsigned int)v8 >= v14 )
        goto LABEL_34;
      v12 = 0;
      v9 = v15;
    }
    if ( v12 != *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v8) )
    {
      updated = CMsftStreamConcatenate::UpdateStreamOffset(this, v8, v12);
      v10 = v28;
      v7 = updated;
      v6 = v25;
      v5 = v27;
    }
    if ( v7 < 0 )
      break;
    _mm_lfence();
    v17 = *(_QWORD *)(*((_QWORD *)this + 10) + 8 * v8) - *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v8);
    v18 = v10;
    if ( v10 >= v17 )
      v18 = *(_QWORD *)(*((_QWORD *)this + 10) + 8 * v8) - *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v8);
    if ( v18 >= 0xFFFF8000 )
    {
      v19 = -32768;
    }
    else
    {
      v19 = v10;
      if ( v10 >= v17 )
        v19 = *(_DWORD *)(*((_QWORD *)this + 10) + 8 * v8) - *(_DWORD *)(*((_QWORD *)this + 11) + 8 * v8);
    }
    v20 = *((_QWORD *)this + 9);
    v26 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, unsigned int *))(**(_QWORD **)(v20 + 8 * v8) + 24LL))(
           *(_QWORD *)(v20 + 8 * v8),
           v5,
           v19,
           &v26);
    if ( v7 >= 0 )
    {
      v21 = v26;
      if ( v26 != v19 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 508) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 505) >= 3u )
        {
          WPP_SF_dDdDdD(
            *((_QWORD *)WPP_GLOBAL_Control + 62),
            23,
            &WPP_47ba174de9f13fae433aca4eb423b804_Traceguids,
            v19,
            v19,
            v8,
            v8,
            v26,
            v26);
          v21 = v26;
        }
        v7 = -2147467259;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 508) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 505) >= 3u )
      {
        WPP_SF_dDdDd(
          *((_QWORD *)WPP_GLOBAL_Control + 62),
          22,
          &WPP_47ba174de9f13fae433aca4eb423b804_Traceguids,
          v19,
          v19,
          v8,
          v8,
          v7);
      }
      v21 = 0;
      v26 = 0;
    }
    v22 = v28;
    v23 = v27;
    *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v8) += v21;
    v6 = v26 + v25;
    v10 = v22 - v26;
    v4 += v26;
    v25 += v26;
    v5 = &v23[v26];
    v28 = v10;
    v27 = v5;
  }
  *v29 = v6;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d084  mov     [rsp+arg_18], r9
0x18000d089  mov     [rsp+arg_10], r8d
0x18000d08e  mov     [rsp+arg_8], rdx
0x18000d093  push    rbx
0x18000d094  push    rbp
0x18000d095  push    rsi
0x18000d096  push    rdi
0x18000d097  push    r12
0x18000d099  push    r13
0x18000d09b  push    r14
0x18000d09d  push    r15
0x18000d09f  sub     rsp, 68h
0x18000d0a3  mov     r12, [rcx+28h]
0x18000d0a7  mov     r10, rdx
0x18000d0aa  xor     edx, edx
0x18000d0ac  xor     ebx, ebx
0x18000d0ae  xor     edi, edi
0x18000d0b0  mov     [rsp+0A8h+var_58], edx
0x18000d0b4  xor     r13d, r13d
0x18000d0b7  mov     r9d, r8d
0x18000d0ba  mov     rsi, rcx
0x18000d0bd  mov     r15, r12
0x18000d0c0  mov     r11d, 0FFFF8000h
0x18000d0c6  cmp     [rcx+40h], edx
0x18000d0c9  jbe     short loc_18000D0E4
0x18000d0cb  mov     rcx, [rcx+50h]
0x18000d0cf  cmp     r15, [rcx+rdi*8]
0x18000d0d3  jb      short loc_18000D0EC
0x18000d0d5  sub     r15, [rcx+rdi*8]
0x18000d0d9  add     r13, [rcx+rdi*8]
0x18000d0dd  inc     edi
0x18000d0df  cmp     edi, [rsi+40h]
0x18000d0e2  jb      short loc_18000D0CF
0x18000d0e4  test    ebx, ebx
0x18000d0e6  js      loc_18000D32B
0x18000d0ec  test    r9d, r9d
0x18000d0ef  jz      loc_18000D327
0x18000d0f5  mov     r8d, [rsi+40h]
0x18000d0f9  cmp     edi, r8d
0x18000d0fc  jnb     loc_18000D2D7
0x18000d102  mov     rax, [rsi+50h]
0x18000d106  mov     rax, [rax+rdi*8]
0x18000d10a  add     rax, r13
0x18000d10d  cmp     r12, rax
0x18000d110  jnz     short loc_18000D123
0x18000d112  inc     edi
0x18000d114  cmp     edi, r8d
0x18000d117  jnb     loc_18000D2D7
0x18000d11d  xor     r15d, r15d
0x18000d120  mov     r13, rax
0x18000d123  mov     rax, [rsi+58h]
0x18000d127  cmp     r15, [rax+rdi*8]
0x18000d12b  jz      short loc_18000D156
0x18000d12d  mov     r8, r15; unsigned __int64
0x18000d130  mov     edx, edi; unsigned int
0x18000d132  mov     rcx, rsi; this
0x18000d135  call    ?UpdateStreamOffset@CMsftStreamConcatenate@@AEAAJK_K@Z; CMsftStreamConcatenate::UpdateStreamOffset(ulong,unsigned __int64)
0x18000d13a  mov     r9d, [rsp+0A8h+arg_10]
0x18000d142  mov     ebx, eax
0x18000d144  mov     edx, [rsp+0A8h+var_58]
0x18000d148  mov     r11d, 0FFFF8000h
0x18000d14e  mov     r10, [rsp+0A8h+arg_8]
0x18000d156  test    ebx, ebx
0x18000d158  js      loc_18000D32B
0x18000d15e  lfence
0x18000d161  mov     rcx, [rsi+50h]
0x18000d165  mov     rax, [rsi+58h]
0x18000d169  mov     rdx, [rcx+rdi*8]
0x18000d16d  sub     rdx, [rax+rdi*8]
0x18000d171  mov     ecx, r9d
0x18000d174  cmp     rcx, rdx
0x18000d177  mov     eax, r9d
0x18000d17a  cmovnb  rax, rdx
0x18000d17e  cmp     rax, r11
0x18000d181  jnb     short loc_18000D18E
0x18000d183  cmp     rcx, rdx
0x18000d186  mov     ebp, r9d
0x18000d189  cmovnb  ebp, edx
0x18000d18c  jmp     short loc_18000D191
0x18000d18e  mov     ebp, r11d
0x18000d191  mov     rax, [rsi+48h]
0x18000d195  lea     r9, [rsp+0A8h+arg_0]
0x18000d19d  mov     [rsp+0A8h+arg_0], 0
0x18000d1a8  mov     r8d, ebp
0x18000d1ab  mov     rdx, r10
0x18000d1ae  mov     rcx, [rax+rdi*8]
0x18000d1b2  mov     rax, [rcx]
0x18000d1b5  mov     rax, [rax+18h]
0x18000d1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1be  mov     ebx, eax
0x18000d1c0  test    eax, eax
0x18000d1c2  jns     short loc_18000D21F
0x18000d1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1cb  lea     rax, WPP_GLOBAL_Control
0x18000d1d2  cmp     rcx, rax
0x18000d1d5  jz      short loc_18000D214
0x18000d1d7  test    byte ptr [rcx+1FCh], 4
0x18000d1de  jz      short loc_18000D214
0x18000d1e0  cmp     byte ptr [rcx+1F9h], 3
0x18000d1e7  jb      short loc_18000D214
0x18000d1e9  mov     rcx, [rcx+1F0h]
0x18000d1f0  lea     r8, WPP_47ba174de9f13fae433aca4eb423b804_Traceguids
0x18000d1f7  mov     [rsp+0A8h+var_70], ebx
0x18000d1fb  mov     edx, 16h
0x18000d200  mov     [rsp+0A8h+var_78], edi
0x18000d204  mov     r9d, ebp
0x18000d207  mov     [rsp+0A8h+var_80], edi
0x18000d20b  mov     [rsp+0A8h+var_88], ebp
0x18000d20f  call    WPP_SF_dDdDd
0x18000d214  xor     eax, eax
0x18000d216  mov     [rsp+0A8h+arg_0], eax
0x18000d21d  jmp     short loc_18000D28A
0x18000d21f  mov     eax, [rsp+0A8h+arg_0]
0x18000d226  cmp     eax, ebp
0x18000d228  jz      short loc_18000D28A
0x18000d22a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d231  lea     rdx, WPP_GLOBAL_Control
0x18000d238  cmp     rcx, rdx
0x18000d23b  jz      short loc_18000D285
0x18000d23d  test    byte ptr [rcx+1FCh], 4
0x18000d244  jz      short loc_18000D285
0x18000d246  cmp     byte ptr [rcx+1F9h], 3
0x18000d24d  jb      short loc_18000D285
0x18000d24f  mov     rcx, [rcx+1F0h]
0x18000d256  lea     r8, WPP_47ba174de9f13fae433aca4eb423b804_Traceguids
0x18000d25d  mov     [rsp+0A8h+var_68], eax
0x18000d261  mov     edx, 17h
0x18000d266  mov     [rsp+0A8h+var_70], eax
0x18000d26a  mov     r9d, ebp
0x18000d26d  mov     [rsp+0A8h+var_78], edi
0x18000d271  mov     [rsp+0A8h+var_80], edi
0x18000d275  mov     [rsp+0A8h+var_88], ebp
0x18000d279  call    WPP_SF_dDdDdD
0x18000d27e  mov     eax, [rsp+0A8h+arg_0]
0x18000d285  mov     ebx, 80004005h
0x18000d28a  mov     edx, [rsp+0A8h+var_58]
0x18000d28e  mov     r11d, 0FFFF8000h
0x18000d294  mov     r9d, [rsp+0A8h+arg_10]
0x18000d29c  mov     r10, [rsp+0A8h+arg_8]
0x18000d2a4  mov     rcx, [rsi+58h]
0x18000d2a8  add     [rcx+rdi*8], rax
0x18000d2ac  mov     eax, [rsp+0A8h+arg_0]
0x18000d2b3  add     edx, eax
0x18000d2b5  sub     r9d, eax
0x18000d2b8  add     r12, rax
0x18000d2bb  mov     [rsp+0A8h+var_58], edx
0x18000d2bf  add     r10, rax
0x18000d2c2  mov     [rsp+0A8h+arg_10], r9d
0x18000d2ca  mov     [rsp+0A8h+arg_8], r10
0x18000d2d2  jmp     loc_18000D0E4
0x18000d2d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2de  lea     rax, WPP_GLOBAL_Control
0x18000d2e5  cmp     rcx, rax
0x18000d2e8  jz      short loc_18000D320
0x18000d2ea  test    byte ptr [rcx+1FCh], 4
0x18000d2f1  jz      short loc_18000D320
0x18000d2f3  cmp     byte ptr [rcx+1F9h], 3
0x18000d2fa  jb      short loc_18000D320
0x18000d2fc  mov     rcx, [rcx+1F0h]
0x18000d303  mov     edx, 15h
0x18000d308  mov     [rsp+0A8h+var_88], r8d
0x18000d30d  mov     r9d, edi
0x18000d310  lea     r8, WPP_47ba174de9f13fae433aca4eb423b804_Traceguids
0x18000d317  call    WPP_SF_Dd
0x18000d31c  mov     edx, [rsp+0A8h+var_58]
0x18000d320  mov     ebx, 8000FFFFh
0x18000d325  jmp     short loc_18000D32B
0x18000d327  mov     [rsi+28h], r12
0x18000d32b  mov     rax, [rsp+0A8h+arg_18]
0x18000d333  mov     [rax], edx
0x18000d335  mov     eax, ebx
0x18000d337  add     rsp, 68h
0x18000d33b  pop     r15
0x18000d33d  pop     r14
0x18000d33f  pop     r13
0x18000d341  pop     r12
0x18000d343  pop     rdi
0x18000d344  pop     rsi
0x18000d345  pop     rbp
0x18000d346  pop     rbx
0x18000d347  retn
```
