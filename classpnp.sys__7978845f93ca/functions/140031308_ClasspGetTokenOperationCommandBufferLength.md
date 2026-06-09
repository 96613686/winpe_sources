# ClasspGetTokenOperationCommandBufferLength

- ea: `0x140031308`
- end: `0x1400314dd`
- name: `ClasspGetTokenOperationCommandBufferLength`
- size: `469`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140059cb4`
- `0x14005a300`

## callees

- `0x140001e40`
- `0x14001fc38`
- `0x140026f8c`
- `0x140031308`

## pseudocode

```c
__int64 __fastcall ClasspGetTokenOperationCommandBufferLength(
        __int64 a1,
        int a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  _QWORD *v5; // rbx
  __int64 v9; // r15
  __int64 v10; // rcx
  unsigned int v11; // r10d
  __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  bool v14; // zf
  unsigned int v15; // edi
  unsigned int v16; // esi
  _QWORD *v17; // rax
  __int64 v18; // rdx
  unsigned int v19; // ecx
  unsigned int v20; // eax
  __int64 v21; // r11
  unsigned int v22; // edx
  unsigned int v23; // ecx
  _QWORD *v24; // rax
  __int64 v25; // rdx
  unsigned int v26; // ecx
  unsigned int v27; // eax
  __int64 v28; // r11

  v5 = *(_QWORD **)(a1 + 64);
  v9 = v5[143];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 120, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, a1);
  }
  v10 = 16;
  v11 = 0xFFFF;
  if ( a2 != 16 )
    v10 = 536;
  v12 = *(unsigned __int16 *)(v5[144] + 132LL);
  if ( (_WORD)v12 )
  {
    v13 = v10 + 16 * v12;
    if ( v13 < 0xFFFF )
      v11 = v13;
  }
  v14 = a2 == 16;
  v15 = 805;
  v16 = v11;
  if ( !v14 )
    v15 = 287;
  v17 = (_QWORD *)v5[3];
  if ( v11 <= v15 )
    v16 = v15;
  v18 = v17[144];
  if ( (*(_DWORD *)(v17[143] + 664LL) & 0x40) == 0
    && (*(_DWORD *)(v18 + 16) & 1) != 0
    && (v19 = *(_DWORD *)(v18 + 64)) != 0 )
  {
    v20 = ClasspCalculateTransferLengthInBytes(v19, *(_DWORD *)(v5[3] + 572LL));
    v22 = *(_DWORD *)(v21 + 8);
    if ( v20 < v22 )
      v22 = v20;
  }
  else
  {
    v22 = *(_DWORD *)(v17[66] + 8LL);
  }
  v23 = *(_DWORD *)(v9 + 652);
  if ( v23 >= v22 )
  {
    v24 = (_QWORD *)v5[3];
    v25 = v24[144];
    if ( (*(_DWORD *)(v24[143] + 664LL) & 0x40) == 0
      && (*(_DWORD *)(v25 + 16) & 1) != 0
      && (v26 = *(_DWORD *)(v25 + 64)) != 0 )
    {
      v27 = ClasspCalculateTransferLengthInBytes(v26, *(_DWORD *)(v5[3] + 572LL));
      v23 = *(_DWORD *)(v28 + 8);
      if ( v27 < v23 )
        v23 = v27;
    }
    else
    {
      v23 = *(_DWORD *)(v24[66] + 8LL);
    }
  }
  if ( v16 < v23 )
    v23 = v16;
  *a3 = v23;
  if ( a4 )
    *a4 = v11;
  if ( a5 )
    *a5 = v15;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qDDD(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140031308  push    rbx
0x14003130a  push    rbp
0x14003130b  push    rsi
0x14003130c  push    rdi
0x14003130d  push    r12
0x14003130f  push    r13
0x140031311  push    r14
0x140031313  push    r15
0x140031315  sub     rsp, 48h
0x140031319  mov     rbx, [rcx+40h]
0x14003131d  mov     r14, r9
0x140031320  mov     r12, r8
0x140031323  mov     esi, edx
0x140031325  mov     rbp, rcx
0x140031328  mov     r15, [rbx+478h]
0x14003132f  mov     rcx, cs:WPP_GLOBAL_Control
0x140031336  lea     rax, WPP_GLOBAL_Control
0x14003133d  cmp     rcx, rax
0x140031340  jz      short loc_140031367
0x140031342  mov     eax, [rcx+2Ch]
0x140031345  test    al, 10h
0x140031347  jz      short loc_140031367
0x140031349  cmp     byte ptr [rcx+29h], 5
0x14003134d  jb      short loc_140031367
0x14003134f  mov     rcx, [rcx+18h]
0x140031353  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14003135a  mov     edx, 78h ; 'x'
0x14003135f  mov     r9, rbp
0x140031362  call    WPP_SF_q
0x140031367  mov     ecx, 10h
0x14003136c  mov     eax, 218h
0x140031371  cmp     esi, ecx
0x140031373  mov     r10d, 0FFFFh
0x140031379  cmovnz  ecx, eax
0x14003137c  mov     rax, [rbx+480h]
0x140031383  movzx   edx, word ptr [rax+84h]
0x14003138a  test    dx, dx
0x14003138d  jz      short loc_14003139E
0x14003138f  shl     rdx, 4
0x140031393  add     rdx, rcx
0x140031396  cmp     rdx, r10
0x140031399  jnb     short loc_14003139E
0x14003139b  mov     r10d, edx
0x14003139e  cmp     esi, 10h
0x1400313a1  mov     eax, 11Fh
0x1400313a6  mov     edi, 325h
0x1400313ab  mov     esi, r10d
0x1400313ae  cmovnz  edi, eax
0x1400313b1  mov     rax, [rbx+18h]
0x1400313b5  cmp     r10d, edi
0x1400313b8  cmovbe  esi, edi
0x1400313bb  mov     r11, [rax+210h]
0x1400313c2  mov     rdx, [rax+480h]
0x1400313c9  mov     rax, [rax+478h]
0x1400313d0  mov     ecx, [rax+298h]
0x1400313d6  test    cl, 40h
0x1400313d9  jnz     short loc_140031403
0x1400313db  mov     eax, [rdx+10h]
0x1400313de  test    al, 1
0x1400313e0  jz      short loc_140031403
0x1400313e2  mov     ecx, [rdx+40h]
0x1400313e5  test    ecx, ecx
0x1400313e7  jz      short loc_140031403
0x1400313e9  mov     rdx, [rbx+18h]
0x1400313ed  mov     edx, [rdx+23Ch]
0x1400313f3  call    ClasspCalculateTransferLengthInBytes
0x1400313f8  mov     edx, [r11+8]
0x1400313fc  cmp     eax, edx
0x1400313fe  cmovb   edx, eax
0x140031401  jmp     short loc_140031407
0x140031403  mov     edx, [r11+8]
0x140031407  mov     ecx, [r15+28Ch]
0x14003140e  cmp     ecx, edx
0x140031410  jb      short loc_140031462
0x140031412  mov     rax, [rbx+18h]
0x140031416  mov     r11, [rax+210h]
0x14003141d  mov     rdx, [rax+480h]
0x140031424  mov     rax, [rax+478h]
0x14003142b  mov     ecx, [rax+298h]
0x140031431  test    cl, 40h
0x140031434  jnz     short loc_14003145E
0x140031436  mov     eax, [rdx+10h]
0x140031439  test    al, 1
0x14003143b  jz      short loc_14003145E
0x14003143d  mov     ecx, [rdx+40h]
0x140031440  test    ecx, ecx
0x140031442  jz      short loc_14003145E
0x140031444  mov     rdx, [rbx+18h]
0x140031448  mov     edx, [rdx+23Ch]
0x14003144e  call    ClasspCalculateTransferLengthInBytes
0x140031453  mov     ecx, [r11+8]
0x140031457  cmp     eax, ecx
0x140031459  cmovb   ecx, eax
0x14003145c  jmp     short loc_140031462
0x14003145e  mov     ecx, [r11+8]
0x140031462  cmp     esi, ecx
0x140031464  cmovb   ecx, esi
0x140031467  mov     [r12], ecx
0x14003146b  test    r14, r14
0x14003146e  jz      short loc_140031473
0x140031470  mov     [r14], r10d
0x140031473  mov     rax, [rsp+88h+arg_20]
0x14003147b  test    rax, rax
0x14003147e  jz      short loc_140031482
0x140031480  mov     [rax], edi
0x140031482  mov     r11, cs:WPP_GLOBAL_Control
0x140031489  lea     rax, WPP_GLOBAL_Control
0x140031490  cmp     r11, rax
0x140031493  jz      short loc_1400314C9
0x140031495  mov     eax, [r11+2Ch]
0x140031499  test    al, 10h
0x14003149b  jz      short loc_1400314C9
0x14003149d  cmp     byte ptr [r11+29h], 5
0x1400314a2  jb      short loc_1400314C9
0x1400314a4  mov     [rsp+88h+var_58], edi
0x1400314a8  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x1400314af  mov     [rsp+88h+var_60], r10d
0x1400314b4  mov     edx, 79h ; 'y'
0x1400314b9  mov     [rsp+88h+var_68], ecx
0x1400314bd  mov     r9, rbp
0x1400314c0  mov     rcx, [r11+18h]
0x1400314c4  call    WPP_SF_qDDD
0x1400314c9  xor     eax, eax
0x1400314cb  add     rsp, 48h
0x1400314cf  pop     r15
0x1400314d1  pop     r14
0x1400314d3  pop     r13
0x1400314d5  pop     r12
0x1400314d7  pop     rdi
0x1400314d8  pop     rsi
0x1400314d9  pop     rbp
0x1400314da  pop     rbx
0x1400314db  retn
```
