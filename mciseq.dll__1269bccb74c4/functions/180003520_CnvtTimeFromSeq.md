# CnvtTimeFromSeq

- ea: `0x180003520`
- end: `0x1800036d8`
- name: `CnvtTimeFromSeq`
- size: `440`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180001810`
- `0x180001eec`
- `0x1800025fc`
- `0x1800038ac`

## callees

- `0x180003520`
- `0x180003878`
- `0x180005270`
- `0x180005ff0`

## pseudocode

```c
__int64 __fastcall CnvtTimeFromSeq(__int64 a1, unsigned int a2, _WORD *a3)
{
  unsigned int v3; // r9d
  __int64 v4; // r11
  unsigned int v6; // eax
  int v7; // ecx
  unsigned int v8; // edx
  unsigned int v9; // r10d
  unsigned int v10; // r8d
  int v11; // ecx
  int v12; // ecx
  unsigned int v13; // eax
  unsigned int v14; // r10d
  int v15; // edx
  unsigned int v16; // eax
  unsigned int v17; // r9d
  unsigned int v19; // [rsp+20h] [rbp-18h] BYREF

  v3 = (unsigned __int16)a3[1];
  v4 = a2;
  v19 = 0;
  v6 = 4 * a2;
  if ( *a3 )
    v6 = a2;
  v7 = *(_DWORD *)(a1 + 340);
  v8 = *(_DWORD *)(a1 + 344);
  v9 = v6 / v3;
  if ( !v7 )
  {
    if ( v8 == 16385 )
      return v9;
    midiSeqMessage(*(_QWORD *)(a1 + 256), 0xFu, v4, (__int64)&v19);
    if ( !*(_DWORD *)(a1 + 344) )
      return v19;
    v16 = ((__int64 (*)(void))FPSDisplay)();
    v17 = v19 * v16 / 0x3E8;
    LOBYTE(v19) = v17 / (3600 * v16);
    BYTE1(v19) = v17 % (3600 * v16) / (60 * v16);
    BYTE2(v19) = v17 % (60 * v16) / v16;
    v15 = v17 % v16;
LABEL_19:
    HIBYTE(v19) = v15;
    return v19;
  }
  v10 = 1;
  if ( v8 - 4 <= 1 || v8 == 7 || v8 == 6 )
  {
    v13 = FPSDisplay(v8);
    LOBYTE(v19) = v14 / (3600 * v13);
    BYTE1(v19) = v14 % (3600 * v13) / (60 * v13);
    BYTE2(v19) = v14 % (60 * v13) / v13;
    v15 = v14 % v13;
    goto LABEL_19;
  }
  v11 = v7 - 24;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      if ( (unsigned int)(v12 - 4) <= 1 )
        v10 = 30;
    }
    else
    {
      v10 = 25;
    }
  }
  else
  {
    v10 = 24;
  }
  return ((v10 >> 1) + 1000 * (_DWORD)v4) / (v10 * v3);
}

```

## disassembly

```asm
0x180003520  mov     [rsp+arg_10], rbx
0x180003525  push    rdi
0x180003526  sub     rsp, 30h
0x18000352a  mov     rax, cs:__security_cookie
0x180003531  xor     rax, rsp
0x180003534  mov     [rsp+38h+var_10], rax
0x180003539  movzx   r9d, word ptr [r8+2]
0x18000353e  xor     edi, edi
0x180003540  mov     r11d, edx
0x180003543  mov     rbx, rcx
0x180003546  xor     edx, edx
0x180003548  mov     [rsp+38h+var_18], edi
0x18000354c  lea     eax, ds:0[r11*4]
0x180003554  cmp     [r8], di
0x180003558  jz      short loc_18000355D
0x18000355a  mov     eax, r11d
0x18000355d  mov     ecx, [rcx+154h]
0x180003563  div     r9d
0x180003566  mov     edx, [rbx+158h]
0x18000356c  mov     r10d, eax
0x18000356f  test    ecx, ecx
0x180003571  jz      short loc_1800035D4
0x180003573  lea     eax, [rdx-4]
0x180003576  mov     r8d, 1
0x18000357c  cmp     eax, r8d
0x18000357f  jbe     short loc_1800035ED
0x180003581  cmp     edx, 7
0x180003584  jz      short loc_1800035ED
0x180003586  cmp     edx, 6
0x180003589  jz      short loc_1800035ED
0x18000358b  sub     ecx, 18h
0x18000358e  jz      short loc_1800035AF
0x180003590  sub     ecx, r8d
0x180003593  jz      short loc_1800035A7
0x180003595  sub     ecx, 4
0x180003598  jz      short loc_18000359F
0x18000359a  cmp     ecx, r8d
0x18000359d  jnz     short loc_1800035B5
0x18000359f  mov     r8d, 1Eh
0x1800035a5  jmp     short loc_1800035B5
0x1800035a7  mov     r8d, 19h
0x1800035ad  jmp     short loc_1800035B5
0x1800035af  mov     r8d, 18h
0x1800035b5  imul    eax, r11d, 3E8h
0x1800035bc  mov     ecx, r8d
0x1800035bf  shr     ecx, 1
0x1800035c1  xor     edx, edx
0x1800035c3  imul    r9d, r8d
0x1800035c7  add     eax, ecx
0x1800035c9  div     r9d
0x1800035cc  mov     r10d, eax
0x1800035cf  jmp     loc_1800036BD
0x1800035d4  cmp     edx, 4001h
0x1800035da  jnz     short loc_180003636
0x1800035dc  lea     eax, [rdx-4]
0x1800035df  cmp     eax, 2
0x1800035e2  jbe     short loc_1800035ED
0x1800035e4  cmp     edx, 7
0x1800035e7  jnz     loc_1800036BD
0x1800035ed  mov     ecx, edx
0x1800035ef  call    FPSDisplay
0x1800035f4  imul    ecx, eax, 0E10h
0x1800035fa  mov     r9d, eax
0x1800035fd  xor     edx, edx
0x1800035ff  imul    r8d, r9d, 3Ch ; '<'
0x180003603  mov     eax, r10d
0x180003606  div     ecx
0x180003608  mov     ecx, edx
0x18000360a  mov     byte ptr [rsp+38h+var_18], al
0x18000360e  xor     edx, edx
0x180003610  mov     eax, ecx
0x180003612  div     r8d
0x180003615  xor     edx, edx
0x180003617  mov     byte ptr [rsp+38h+var_18+1], al
0x18000361b  mov     eax, r10d
0x18000361e  div     r8d
0x180003621  mov     eax, edx
0x180003623  xor     edx, edx
0x180003625  div     r9d
0x180003628  xor     edx, edx
0x18000362a  mov     byte ptr [rsp+38h+var_18+2], al
0x18000362e  mov     eax, r10d
0x180003631  div     r9d
0x180003634  jmp     short loc_1800036B4
0x180003636  mov     rcx, [rbx+100h]; dwUser
0x18000363d  lea     r9, [rsp+38h+var_18]
0x180003642  mov     r8, r11
0x180003645  mov     edx, 0Fh
0x18000364a  call    midiSeqMessage
0x18000364f  mov     ecx, [rbx+158h]
0x180003655  test    ecx, ecx
0x180003657  jz      short loc_1800036B8
0x180003659  call    FPSDisplay
0x18000365e  mov     r10d, eax
0x180003661  mov     ecx, eax
0x180003663  imul    ecx, [rsp+38h+var_18]
0x180003668  mov     eax, 10624DD3h
0x18000366d  imul    r8d, r10d, 3Ch ; '<'
0x180003671  mul     ecx
0x180003673  imul    ecx, r10d, 0E10h
0x18000367a  mov     r9d, edx
0x18000367d  xor     edx, edx
0x18000367f  shr     r9d, 6
0x180003683  mov     eax, r9d
0x180003686  div     ecx
0x180003688  mov     ecx, edx
0x18000368a  mov     byte ptr [rsp+38h+var_18], al
0x18000368e  xor     edx, edx
0x180003690  mov     eax, ecx
0x180003692  div     r8d
0x180003695  xor     edx, edx
0x180003697  mov     byte ptr [rsp+38h+var_18+1], al
0x18000369b  mov     eax, r9d
0x18000369e  div     r8d
0x1800036a1  mov     eax, edx
0x1800036a3  xor     edx, edx
0x1800036a5  div     r10d
0x1800036a8  xor     edx, edx
0x1800036aa  mov     byte ptr [rsp+38h+var_18+2], al
0x1800036ae  mov     eax, r9d
0x1800036b1  div     r10d
0x1800036b4  mov     byte ptr [rsp+38h+var_18+3], dl
0x1800036b8  mov     r10d, [rsp+38h+var_18]
0x1800036bd  mov     eax, r10d
0x1800036c0  mov     rcx, [rsp+38h+var_10]
0x1800036c5  xor     rcx, rsp; StackCookie
0x1800036c8  call    __security_check_cookie
0x1800036cd  mov     rbx, [rsp+38h+arg_10]
0x1800036d2  add     rsp, 30h
0x1800036d6  pop     rdi
0x1800036d7  retn
```
