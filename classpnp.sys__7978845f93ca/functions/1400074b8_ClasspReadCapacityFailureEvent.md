# ClasspReadCapacityFailureEvent

- ea: `0x1400074b8`
- end: `0x14000761e`
- name: `ClasspReadCapacityFailureEvent`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140001130`

## callees

- `0x140007230`
- `0x1400074b8`
- `0x140007630`
- `0x14003e430`

## pseudocode

```c
void __fastcall ClasspReadCapacityFailureEvent(__int64 a1, __int64 a2, __int64 a3, char a4, char a5, char a6)
{
  __int64 v6; // r11
  char v7; // r15
  __int64 v9; // rax
  const char *v10; // r9
  unsigned int *v11; // r10
  const char *v12; // rbx
  const char *v13; // rdi
  const char *v14; // rsi
  __int128 *v15; // rbp
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // r10
  __int64 v24; // rdx
  __int128 v25; // [rsp+70h] [rbp-58h] BYREF

  v6 = *(_QWORD *)(a2 + 64);
  v7 = a3;
  v25 = 0;
  if ( v6 )
  {
    v9 = *(_QWORD *)(v6 + 1168);
    v10 = 0;
    v11 = *(unsigned int **)(v6 + 520);
    v12 = 0;
    v13 = 0;
    v14 = 0;
    v15 = (__int128 *)(v9 + 4);
    if ( !v9 )
      v15 = &v25;
    if ( v11 )
    {
      v16 = v11[3];
      if ( (_DWORD)v16 && (unsigned int)ClasspGetMaxUsableBufferLengthFromOffset(*(_QWORD *)(v6 + 520), v16, v11[1]) )
        v10 = (char *)v11 + v24;
      v17 = v11[4];
      if ( (_DWORD)v17 && (unsigned int)ClasspGetMaxUsableBufferLengthFromOffset(v11, v17, v11[1]) )
        v12 = (char *)v11 + v18;
      v19 = v11[5];
      if ( (_DWORD)v19 && (unsigned int)ClasspGetMaxUsableBufferLengthFromOffset(v11, v19, v11[1]) )
        v13 = (char *)v11 + v20;
      v21 = v11[6];
      if ( (_DWORD)v21 && (unsigned int)ClasspGetMaxUsableBufferLengthFromOffset(v11, v21, v11[1]) )
        v14 = (const char *)(v23 + v22);
    }
    if ( SBYTE3(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) < 0 )
      McTemplateK0jqsssstqqd_EtwWriteTransfer(
        a1,
        (const EVENT_DESCRIPTOR *)EventReadCapacityFailed,
        a3,
        (__int64)v15,
        *(_DWORD *)(v6 + 588),
        v10,
        v12,
        v13,
        v14,
        v7,
        a4,
        a5,
        a6);
  }
}

```

## disassembly

```asm
0x1400074b8  push    rbx
0x1400074ba  push    rbp
0x1400074bb  push    rsi
0x1400074bc  push    rdi
0x1400074bd  push    r14
0x1400074bf  push    r15
0x1400074c1  sub     rsp, 98h
0x1400074c8  mov     rax, cs:__security_cookie
0x1400074cf  xor     rax, rsp
0x1400074d2  mov     [rsp+0C8h+var_48], rax
0x1400074da  mov     r11, [rdx+40h]
0x1400074de  xorps   xmm0, xmm0
0x1400074e1  movzx   r15d, r8b
0x1400074e5  mov     r14d, r9d
0x1400074e8  movups  [rsp+0C8h+var_58], xmm0
0x1400074ed  test    r11, r11
0x1400074f0  jz      loc_1400075D6
0x1400074f6  mov     rax, [r11+490h]
0x1400074fd  xor     r9d, r9d
0x140007500  mov     r10, [r11+208h]
0x140007507  xor     ebx, ebx
0x140007509  xor     edi, edi
0x14000750b  xor     esi, esi
0x14000750d  lea     rbp, [rax+4]
0x140007511  test    rax, rax
0x140007514  jz      loc_140007614
0x14000751a  test    r10, r10
0x14000751d  jz      short loc_14000757F
0x14000751f  mov     edx, [r10+0Ch]
0x140007523  test    edx, edx
0x140007525  jnz     loc_1400075F7
0x14000752b  mov     edx, [r10+10h]
0x14000752f  test    edx, edx
0x140007531  jz      short loc_140007547
0x140007533  mov     r8d, [r10+4]
0x140007537  mov     rcx, r10
0x14000753a  call    ClasspGetMaxUsableBufferLengthFromOffset
0x14000753f  test    eax, eax
0x140007541  jz      short loc_140007547
0x140007543  lea     rbx, [r10+rdx]
0x140007547  mov     edx, [r10+14h]
0x14000754b  test    edx, edx
0x14000754d  jz      short loc_140007563
0x14000754f  mov     r8d, [r10+4]
0x140007553  mov     rcx, r10
0x140007556  call    ClasspGetMaxUsableBufferLengthFromOffset
0x14000755b  test    eax, eax
0x14000755d  jz      short loc_140007563
0x14000755f  lea     rdi, [r10+rdx]
0x140007563  mov     edx, [r10+18h]
0x140007567  test    edx, edx
0x140007569  jz      short loc_14000757F
0x14000756b  mov     r8d, [r10+4]
0x14000756f  mov     rcx, r10
0x140007572  call    ClasspGetMaxUsableBufferLengthFromOffset
0x140007577  test    eax, eax
0x140007579  jz      short loc_14000757F
0x14000757b  lea     rsi, [r10+rdx]
0x14000757f  cmp     byte ptr cs:WPP_MAIN_CB.Queue+3Bh, 0
0x140007586  jge     short loc_1400075D6
0x140007588  mov     eax, [rsp+0C8h+arg_28]
0x14000758f  lea     rdx, EventReadCapacityFailed
0x140007596  mov     [rsp+0C8h+var_68], eax
0x14000759a  mov     eax, dword ptr [rsp+0C8h+arg_20]
0x1400075a1  mov     [rsp+0C8h+var_70], eax
0x1400075a5  mov     eax, [r11+24Ch]
0x1400075ac  mov     [rsp+0C8h+var_78], r14d
0x1400075b1  mov     [rsp+0C8h+var_80], r15d
0x1400075b6  mov     [rsp+0C8h+var_88], rsi
0x1400075bb  mov     [rsp+0C8h+var_90], rdi
0x1400075c0  mov     [rsp+0C8h+var_98], rbx
0x1400075c5  mov     [rsp+0C8h+var_A0], r9
0x1400075ca  mov     r9, rbp
0x1400075cd  mov     [rsp+0C8h+var_A8], eax
0x1400075d1  call    McTemplateK0jqsssstqqd_EtwWriteTransfer
0x1400075d6  mov     rcx, [rsp+0C8h+var_48]
0x1400075de  xor     rcx, rsp; StackCookie
0x1400075e1  call    __security_check_cookie
0x1400075e6  add     rsp, 98h
0x1400075ed  pop     r15
0x1400075ef  pop     r14
0x1400075f1  pop     rdi
0x1400075f2  pop     rsi
0x1400075f3  pop     rbp
0x1400075f4  pop     rbx
0x1400075f5  retn
0x1400075f7  mov     r8d, [r10+4]
0x1400075fb  mov     rcx, r10
0x1400075fe  call    ClasspGetMaxUsableBufferLengthFromOffset
0x140007603  test    eax, eax
0x140007605  jz      loc_14000752B
0x14000760b  lea     r9, [r10+rdx]
0x14000760f  jmp     loc_14000752B
0x140007614  lea     rbp, [rsp+0C8h+var_58]
0x140007619  jmp     loc_14000751A
```
