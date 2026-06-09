# QosLineSignalExternalEvent

- ea: `0x14000a380`
- end: `0x14000a764`
- name: `QosLineSignalExternalEvent`
- size: `996`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140005c10`
- `0x140008290`
- `0x1400085c0`
- `0x140009b80`
- `0x140009fe0`

## callees

- `0x14000a380`
- `0x140013110`
- `0x140013150`
- `0x140013600`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x14000a601`
- `HAL!KeQueryPerformanceCounter` at `0x14000a601`

## pseudocode

```c
__int64 __fastcall QosLineSignalExternalEvent(__int64 a1, unsigned int a2)
{
  unsigned __int64 v3; // rsi
  __int64 v4; // rbx
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int32 v7; // r9d
  __int32 v8; // r10d
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r14
  __int64 v12; // rsi
  __int64 v13; // rbp
  __int64 v14; // r11
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  LARGE_INTEGER v20; // rax
  union _LARGE_INTEGER v21; // rcx
  LARGE_INTEGER v22; // r9
  __int64 v23; // rdx
  unsigned __int64 v24; // r8
  unsigned __int8 v25; // al
  unsigned __int8 v26; // al
  void (__fastcall *v27)(_QWORD *); // rax
  void (__fastcall *v28)(_QWORD *); // rax
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+20h] [rbp-E8h] BYREF
  _QWORD v30[10]; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD v31[10]; // [rsp+80h] [rbp-88h] BYREF

  v3 = *(_QWORD *)QosgTimerTable + ((unsigned __int64)a2 << 7);
  v4 = MEMORY[0xFFFFF78000000008];
  if ( MEMORY[0xFFFFF78000000008] != *(_QWORD *)(v3 + 8) )
  {
    PerformanceFrequency.QuadPart = 0;
    v20 = KeQueryPerformanceCounter(&PerformanceFrequency);
    v21 = PerformanceFrequency;
    v22 = v20;
    v23 = *(unsigned __int8 *)(v3 + 112);
    v24 = ((1000000 * HIDWORD(v20.QuadPart) / (unsigned __int64)PerformanceFrequency.QuadPart) << 32)
        + (1000000LL * v20.LowPart
         + ((1000000 * HIDWORD(v20.QuadPart) % (unsigned __int64)PerformanceFrequency.QuadPart) << 32))
        / PerformanceFrequency.QuadPart;
    if ( (_BYTE)v23 )
      v25 = v23 - 1;
    else
      v25 = 2;
    if ( (__int64)(*(_QWORD *)(v3 + 8LL * v25 + 64) - v24) > 0 )
    {
      *(_QWORD *)(v3 + 8 * v23 + 16) = *(_QWORD *)(v3 + 8LL * v25 + 16);
      *(_QWORD *)(v3 + 8 * v23 + 40) = *(_QWORD *)(v3 + 8LL * v25 + 40);
      *(_QWORD *)(v3 + 8 * v23 + 64) = *(_QWORD *)(v3 + 8LL * v25 + 64);
      v24 = *(_QWORD *)(v3 + 8LL * v25 + 64);
    }
    else
    {
      *(LARGE_INTEGER *)(v3 + 8 * v23 + 16) = v22;
      *(union _LARGE_INTEGER *)(v3 + 8 * v23 + 40) = v21;
      *(_QWORD *)(v3 + 8 * v23 + 64) = v24;
    }
    *(_QWORD *)(v3 + 8 * v23 + 88) = v4;
    v26 = *(_BYTE *)(v3 + 112) + 1;
    *(_QWORD *)v3 = v24;
    *(_QWORD *)(v3 + 8) = v4;
    *(_BYTE *)(v3 + 112) = v26 % 3u;
  }
  v5 = *(_QWORD *)v3;
  if ( (__int64)(*(_QWORD *)(a1 + 168) - *(_QWORD *)v3) <= 0 )
  {
    memset(v30, 0, sizeof(v30));
    v6 = *(unsigned int *)(a1 + 120);
    v7 = 0;
    v8 = 0;
    if ( (_DWORD)v6 )
    {
      v9 = *(_DWORD *)(a1 + 208);
      if ( (v9 & 4) != 0 )
      {
        v10 = *(unsigned int *)(a1 + 140);
        v7 = _InterlockedExchange((volatile __int32 *)(a1 + 132), 0);
        v8 = _InterlockedExchange((volatile __int32 *)(a1 + 136), 0);
        v11 = v10 + v7 - (__int64)v8;
        v12 = *(unsigned int *)(a1 + 120) - v11;
        v13 = 0;
        v14 = 3 * (v12 - *(int *)(a1 + 200)) / 200;
        v15 = v12 / 100;
        v16 = v12 / 100 + v14;
        if ( v16 + *(_QWORD *)(a1 + 184) > 0 )
          v13 = v16 + *(_QWORD *)(a1 + 184);
        if ( v13 >= *(unsigned int *)(a1 + 124) )
          v13 = *(unsigned int *)(a1 + 124);
      }
      else
      {
        v12 = *(unsigned int *)(a1 + 120);
        *(_DWORD *)(a1 + 208) = v9 | 4;
        v16 = v6;
        v14 = 0;
        v15 = v6;
        v13 = v6;
        LODWORD(v11) = 0;
      }
    }
    else
    {
      v16 = 0x7FFFFFFFFFFFFFFFLL;
      v12 = 0x7FFFFFFF;
      v14 = 0x7FFFFFFFFFFFFFFFLL;
      v15 = 0x7FFFFFFFFFFFFFFFLL;
      v13 = 0x7FFFFFFFFFFFFFFFLL;
      LODWORD(v11) = 0;
    }
    if ( **(_DWORD **)QosgEtwDispatchTable == 1 )
    {
      v27 = *(void (__fastcall **)(_QWORD *))(QosgEtwDispatchTable + 56);
      v30[6] = a1;
      v30[0] = v5;
      v30[7] = __PAIR64__(v8, v7);
      LODWORD(v30[8]) = v11;
      v30[1] = v12;
      v30[2] = v14;
      v30[3] = v15;
      v30[4] = v16;
      v30[5] = v13;
      v27(v30);
    }
    v17 = *(unsigned int *)(a1 + 116);
    *(_DWORD *)(a1 + 144) = *(_DWORD *)(a1 + 152);
    *(_DWORD *)(a1 + 148) = *(_DWORD *)(a1 + 156);
    *(_DWORD *)(a1 + 140) = v11;
    *(_QWORD *)(a1 + 184) = v13;
    *(_DWORD *)(a1 + 200) = v12;
    *(_QWORD *)(a1 + 168) = v5 + v17 - (v17 + v5) % v17;
    *(_QWORD *)(a1 + 152) = 0;
  }
  if ( *(_QWORD *)(a1 + 160) - v5 <= 0 )
  {
    memset(v31, 0, sizeof(v31));
    if ( **(_DWORD **)QosgEtwDispatchTable == 1 )
    {
      v31[2] = *(_QWORD *)(a1 + 144);
      LODWORD(v31[3]) = *(_DWORD *)(a1 + 184);
      v28 = *(void (__fastcall **)(_QWORD *))(QosgEtwDispatchTable + 16);
      v31[1] = a1;
      v31[0] = v5;
      v28(v31);
    }
    v18 = *(unsigned int *)(a1 + 116);
    *(_QWORD *)(a1 + 176) = *(_QWORD *)(a1 + 184);
    *(_QWORD *)(a1 + 160) = v5 + v18 - (v18 + v5) % v18;
  }
  return (unsigned int)_InterlockedExchange((volatile __int32 *)(a1 + 128), 0);
}

```

## disassembly

```asm
0x14000a380  push    rbx
0x14000a382  push    rdi
0x14000a383  push    r15
0x14000a385  sub     rsp, 0F0h
0x14000a38c  mov     rax, cs:__security_cookie
0x14000a393  xor     rax, rsp
0x14000a396  mov     [rsp+108h+var_38], rax
0x14000a39e  mov     rax, cs:QosgTimerTable
0x14000a3a5  mov     rbx, 0FFFFF78000000008h
0x14000a3af  mov     [rsp+108h+var_20], rsi
0x14000a3b7  xor     r15d, r15d
0x14000a3ba  mov     esi, edx
0x14000a3bc  mov     rdi, rcx
0x14000a3bf  shl     rsi, 7
0x14000a3c3  add     rsi, [rax]
0x14000a3c6  mov     rbx, [rbx]
0x14000a3c9  cmp     rbx, [rsi+8]
0x14000a3cd  jnz     loc_14000A5F7
0x14000a3d3  mov     rbx, [rsi]
0x14000a3d6  mov     rax, [rdi+0A8h]
0x14000a3dd  sub     rax, rbx
0x14000a3e0  test    rax, rax
0x14000a3e3  jg      loc_14000A52B
0x14000a3e9  mov     [rsp+108h+arg_10], rbp
0x14000a3f1  lea     rcx, [rsp+108h+var_D8]; void *
0x14000a3f6  xor     edx, edx; Val
0x14000a3f8  mov     [rsp+108h+var_28], r14
0x14000a400  mov     r8d, 50h ; 'P'; Size
0x14000a406  call    memset
0x14000a40b  mov     ecx, [rdi+78h]
0x14000a40e  mov     r9d, r15d
0x14000a411  mov     r10d, r15d
0x14000a414  test    ecx, ecx
0x14000a416  jz      loc_14000A5B7
0x14000a41c  mov     eax, [rdi+0D0h]
0x14000a422  test    al, 4
0x14000a424  jz      loc_14000A5D7
0x14000a42a  mov     edx, [rdi+8Ch]
0x14000a430  mov     rbp, 0A3D70A3D70A3D70Bh
0x14000a43a  xchg    r9d, [rdi+84h]
0x14000a441  xchg    r10d, [rdi+88h]
0x14000a448  mov     esi, [rdi+78h]
0x14000a44b  movsxd  rax, r10d
0x14000a44e  movsxd  r14, r9d
0x14000a451  sub     r14, rax
0x14000a454  movsxd  rax, dword ptr [rdi+0C8h]
0x14000a45b  add     r14, rdx
0x14000a45e  sub     rsi, r14
0x14000a461  mov     rcx, rsi
0x14000a464  sub     rcx, rax
0x14000a467  mov     rax, rbp
0x14000a46a  lea     r8, [rcx+rcx*2]
0x14000a46e  imul    r8
0x14000a471  mov     rax, rbp
0x14000a474  mov     rbp, r15
0x14000a477  lea     r11, [r8+rdx]
0x14000a47b  imul    rsi
0x14000a47e  sar     r11, 7
0x14000a482  add     rdx, rsi
0x14000a485  mov     rcx, r11
0x14000a488  shr     rcx, 3Fh
0x14000a48c  add     r11, rcx
0x14000a48f  sar     rdx, 6
0x14000a493  mov     rcx, [rdi+0B8h]
0x14000a49a  mov     rax, rdx
0x14000a49d  shr     rax, 3Fh
0x14000a4a1  add     rdx, rax
0x14000a4a4  mov     eax, [rdi+7Ch]
0x14000a4a7  lea     r8, [rdx+r11]
0x14000a4ab  add     rcx, r8
0x14000a4ae  test    rcx, rcx
0x14000a4b1  cmovg   rbp, rcx
0x14000a4b5  cmp     rbp, rax
0x14000a4b8  cmovge  rbp, rax
0x14000a4bc  mov     rcx, cs:QosgEtwDispatchTable
0x14000a4c3  mov     rax, [rcx]
0x14000a4c6  cmp     dword ptr [rax], 1
0x14000a4c9  jz      loc_14000A6D2
0x14000a4cf  mov     eax, [rdi+98h]
0x14000a4d5  xor     edx, edx
0x14000a4d7  mov     ecx, [rdi+74h]
0x14000a4da  mov     [rdi+90h], eax
0x14000a4e0  mov     eax, [rdi+9Ch]
0x14000a4e6  mov     [rdi+94h], eax
0x14000a4ec  lea     rax, [rcx+rbx]
0x14000a4f0  mov     [rdi+8Ch], r14d
0x14000a4f7  mov     r14, [rsp+108h+var_28]
0x14000a4ff  div     rcx
0x14000a502  mov     [rdi+0B8h], rbp
0x14000a509  mov     rbp, [rsp+108h+arg_10]
0x14000a511  sub     rcx, rdx
0x14000a514  add     rcx, rbx
0x14000a517  mov     [rdi+0C8h], esi
0x14000a51d  mov     [rdi+0A8h], rcx
0x14000a524  mov     [rdi+98h], r15
0x14000a52b  mov     rax, [rdi+0A0h]
0x14000a532  mov     rsi, [rsp+108h+var_20]
0x14000a53a  sub     rax, rbx
0x14000a53d  test    rax, rax
0x14000a540  jg      short loc_14000A591
0x14000a542  xor     edx, edx; Val
0x14000a544  lea     rcx, [rsp+108h+var_88]; void *
0x14000a54c  mov     r8d, 50h ; 'P'; Size
0x14000a552  call    memset
0x14000a557  mov     rcx, cs:QosgEtwDispatchTable
0x14000a55e  mov     rax, [rcx]
0x14000a561  cmp     dword ptr [rax], 1
0x14000a564  jz      loc_14000A717
0x14000a56a  mov     ecx, [rdi+74h]
0x14000a56d  xor     edx, edx
0x14000a56f  mov     rax, [rdi+0B8h]
0x14000a576  mov     [rdi+0B0h], rax
0x14000a57d  lea     rax, [rcx+rbx]
0x14000a581  div     rcx
0x14000a584  sub     rcx, rdx
0x14000a587  add     rcx, rbx
0x14000a58a  mov     [rdi+0A0h], rcx
0x14000a591  mov     eax, r15d
0x14000a594  xchg    eax, [rdi+80h]
0x14000a59a  mov     rcx, [rsp+108h+var_38]
0x14000a5a2  xor     rcx, rsp; StackCookie
0x14000a5a5  call    __security_check_cookie
0x14000a5aa  add     rsp, 0F0h
0x14000a5b1  pop     r15
0x14000a5b3  pop     rdi
0x14000a5b4  pop     rbx
0x14000a5b5  retn
0x14000a5b7  mov     r8, 7FFFFFFFFFFFFFFFh
0x14000a5c1  mov     esi, 7FFFFFFFh
0x14000a5c6  mov     r11, r8
0x14000a5c9  mov     rdx, r8
0x14000a5cc  mov     rbp, r8
0x14000a5cf  mov     r14, r15
0x14000a5d2  jmp     loc_14000A4BC
0x14000a5d7  or      eax, 4
0x14000a5da  mov     rsi, rcx
0x14000a5dd  mov     [rdi+0D0h], eax
0x14000a5e3  mov     r8, rcx
0x14000a5e6  mov     r11, r15
0x14000a5e9  mov     rdx, rcx
0x14000a5ec  mov     rbp, rcx
0x14000a5ef  mov     r14, r15
0x14000a5f2  jmp     loc_14000A4BC
0x14000a5f7  lea     rcx, [rsp+108h+PerformanceFrequency]; PerformanceFrequency
0x14000a5fc  mov     qword ptr [rsp+108h+PerformanceFrequency], r15
0x14000a601  call    cs:__imp_KeQueryPerformanceCounter
0x14000a608  nop     dword ptr [rax+rax+00h]
0x14000a60d  mov     rcx, qword ptr [rsp+108h+PerformanceFrequency]
0x14000a612  xor     edx, edx
0x14000a614  mov     r9, rax
0x14000a617  shr     rax, 20h
0x14000a61b  imul    r10, rax, 0F4240h
0x14000a622  mov     rax, r10
0x14000a625  div     rcx
0x14000a628  mov     rax, rdx
0x14000a62b  mov     edx, r9d
0x14000a62e  imul    r8, rdx, 0F4240h
0x14000a635  shl     rax, 20h
0x14000a639  xor     edx, edx
0x14000a63b  add     rax, r8
0x14000a63e  div     rcx
0x14000a641  xor     edx, edx
0x14000a643  mov     r8, rax
0x14000a646  mov     rax, r10
0x14000a649  div     rcx
0x14000a64c  movzx   edx, byte ptr [rsi+70h]
0x14000a650  shl     rax, 20h
0x14000a654  add     r8, rax
0x14000a657  test    dl, dl
0x14000a659  jz      short loc_14000A6A9
0x14000a65b  lea     eax, [rdx-1]
0x14000a65e  movzx   r10d, al
0x14000a662  mov     rax, [rsi+r10*8+40h]
0x14000a667  sub     rax, r8
0x14000a66a  test    rax, rax
0x14000a66d  jg      short loc_14000A6AD
0x14000a66f  mov     [rsi+rdx*8+10h], r9
0x14000a674  mov     [rsi+rdx*8+28h], rcx
0x14000a679  mov     [rsi+rdx*8+40h], r8
0x14000a67e  mov     [rsi+rdx*8+58h], rbx
0x14000a683  movzx   eax, byte ptr [rsi+70h]
0x14000a687  inc     al
0x14000a689  mov     [rsi], r8
0x14000a68c  movzx   ecx, al
0x14000a68f  mov     eax, 0AAAAAAABh
0x14000a694  mul     ecx
0x14000a696  mov     [rsi+8], rbx
0x14000a69a  shr     edx, 1
0x14000a69c  lea     eax, [rdx+rdx*2]
0x14000a69f  sub     ecx, eax
0x14000a6a1  mov     [rsi+70h], cl
0x14000a6a4  jmp     loc_14000A3D3
0x14000a6a9  mov     al, 2
0x14000a6ab  jmp     short loc_14000A65E
0x14000a6ad  mov     rax, [rsi+r10*8+10h]
0x14000a6b2  mov     [rsi+rdx*8+10h], rax
0x14000a6b7  mov     rax, [rsi+r10*8+28h]
0x14000a6bc  mov     [rsi+rdx*8+28h], rax
0x14000a6c1  mov     rax, [rsi+r10*8+40h]
0x14000a6c6  mov     [rsi+rdx*8+40h], rax
0x14000a6cb  mov     r8, [rsi+r10*8+40h]
0x14000a6d0  jmp     short loc_14000A67E
0x14000a6d2  mov     rax, [rcx+38h]
0x14000a6d6  lea     rcx, [rsp+108h+var_D8]
0x14000a6db  mov     [rsp+108h+var_A8], rdi
0x14000a6e0  mov     [rsp+108h+var_D8], rbx
0x14000a6e5  mov     [rsp+108h+var_A0], r9d
0x14000a6ea  mov     [rsp+108h+var_9C], r10d
0x14000a6ef  mov     [rsp+108h+var_98], r14d
0x14000a6f4  mov     [rsp+108h+var_D0], rsi
0x14000a6f9  mov     [rsp+108h+var_C8], r11
0x14000a6fe  mov     [rsp+108h+var_C0], rdx
0x14000a703  mov     [rsp+108h+var_B8], r8
0x14000a708  mov     [rsp+108h+var_B0], rbp
0x14000a70d  call    _guard_dispatch_icall
0x14000a712  jmp     loc_14000A4CF
0x14000a717  mov     eax, [rdi+90h]
0x14000a71d  mov     [rsp+108h+var_78], eax
0x14000a724  mov     eax, [rdi+94h]
0x14000a72a  mov     [rsp+108h+var_74], eax
0x14000a731  mov     eax, [rdi+0B8h]
0x14000a737  mov     [rsp+108h+var_70], eax
0x14000a73e  mov     rax, [rcx+10h]
0x14000a742  lea     rcx, [rsp+108h+var_88]
0x14000a74a  mov     [rsp+108h+var_80], rdi
0x14000a752  mov     [rsp+108h+var_88], rbx
0x14000a75a  call    _guard_dispatch_icall
0x14000a75f  jmp     loc_14000A56A
```
