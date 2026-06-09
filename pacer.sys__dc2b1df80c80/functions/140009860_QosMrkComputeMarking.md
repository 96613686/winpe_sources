# QosMrkComputeMarking

- ea: `0x140009860`
- end: `0x140009b46`
- name: `QosMrkComputeMarking`
- size: `742`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140009350`

## callees

- `0x140004fe0`
- `0x140007ef0`
- `0x140009860`
- `0x140013110`
- `0x140013150`
- `0x140013600`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400099e2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400099e2`

## pseudocode

```c
__int64 __fastcall QosMrkComputeMarking(__int64 a1, _BYTE *a2, __int64 a3, char a4, unsigned __int8 *a5, _BYTE *a6)
{
  __int64 *v10; // r12
  __int16 v11; // r13
  unsigned __int8 j; // dl
  __int64 v13; // rcx
  __int64 result; // rax
  __int64 v15; // r8
  unsigned __int8 v16; // dl
  ULONG CurrentProcessorNumber; // eax
  __int64 v18; // r8
  unsigned __int64 CurrentTime; // r10
  unsigned __int64 v20; // rax
  __int64 v21; // r10
  __int64 **v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rax
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  bool v28; // zf
  unsigned __int8 v29; // cl
  unsigned __int8 i; // al
  unsigned __int8 v31; // [rsp+20h] [rbp-A8h]
  __int64 v32; // [rsp+28h] [rbp-A0h]
  _QWORD v33[10]; // [rsp+30h] [rbp-98h] BYREF

  memset(v33, 0, sizeof(v33));
  if ( (a4 & 1) == 0 )
  {
    if ( *(_QWORD *)(a1 + 152) == -1 )
    {
      v10 = (__int64 *)(a1 + 56);
      LOBYTE(v11) = *(_BYTE *)(a1 + 82);
      *a5 = *(_BYTE *)(a1 + 80);
      j = *(_BYTE *)(a1 + 84);
      v13 = *(_QWORD *)(a1 + 56);
LABEL_4:
      result = *(unsigned __int8 *)(a1 + 86);
      *a6 = result;
      *v10 = v13;
      goto LABEL_5;
    }
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    LOBYTE(v18) = 1;
    CurrentTime = QosTimerGetCurrentTime(CurrentProcessorNumber, 0, v18);
    v20 = *(_QWORD *)(a1 + 48);
    if ( CurrentTime > v20 )
    {
      QosUtilComputeTokenSpec(a1 + 56, CurrentTime - v20);
      *(_QWORD *)(a1 + 48) = v21;
    }
    v22 = *(__int64 ***)(a3 + 8);
    v10 = (__int64 *)(a1 + 56);
    v23 = *(_QWORD *)(a1 + 56);
    v32 = v23;
    if ( v22 )
    {
      do
      {
        v24 = *((unsigned int *)v22 + 6);
        v22 = (__int64 **)*v22;
        v23 -= v24;
      }
      while ( v22 );
      v32 = v23;
    }
    v25 = *(_DWORD *)(a1 + 40);
    if ( v25 )
    {
      v26 = v25 - 1;
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( v27 )
        {
          v28 = v27 == 1;
          v13 = v32;
          if ( v28 )
          {
            LOBYTE(v11) = *(_BYTE *)(a1 + 82);
            *a5 = *(_BYTE *)(a1 + 80);
            j = *(_BYTE *)(a1 + 84);
          }
          else
          {
            LOBYTE(v11) = 0;
            *a5 = 0;
            j = 0;
          }
        }
        else
        {
          v13 = v32;
          LOBYTE(v11) = *(_BYTE *)(a1 + 82);
          *a5 = *(_BYTE *)(a1 + 80);
          j = *(_BYTE *)(a1 + 84);
          if ( v32 < 0 )
            v13 = *v10;
        }
        goto LABEL_4;
      }
    }
    else if ( v23 < 0 )
    {
      v15 = QosgEtwDispatchTable;
      v16 = *(_BYTE *)(a1 + 81);
      v11 = *(unsigned __int8 *)(a1 + 83);
      *a5 = v16;
      v31 = *(_BYTE *)(a1 + 85);
      if ( **(_DWORD **)v15 == 1 )
      {
        WORD2(v33[1]) = *(unsigned __int8 *)(a1 + 85);
        LOWORD(v33[1]) = v16 >> 2;
        v33[0] = a3;
        WORD1(v33[1]) = v11;
        (*(void (__fastcall **)(_QWORD *))(v15 + 48))(v33);
        j = v31;
      }
      else
      {
        j = *(_BYTE *)(a1 + 85);
      }
      goto LABEL_14;
    }
    LOBYTE(v11) = *(_BYTE *)(a1 + 82);
    *a5 = *(_BYTE *)(a1 + 80);
    j = *(_BYTE *)(a1 + 84);
LABEL_14:
    v13 = v32;
    goto LABEL_4;
  }
  LOBYTE(v11) = *(_BYTE *)(a1 + 82);
  *a5 = *(_BYTE *)(a1 + 80);
  result = *(unsigned __int8 *)(a1 + 86);
  j = *(_BYTE *)(a1 + 84);
  *a6 = result;
LABEL_5:
  if ( !*(_BYTE *)(a1 + 87) )
  {
    result = *(unsigned int *)(a3 + 176);
    *(_DWORD *)(a3 + 176) = result ^ ((unsigned __int8)result ^ (unsigned __int8)v11) & 7;
  }
  if ( (a4 & 2) != 0 )
  {
    if ( *a2 )
    {
      v29 = *a5 >> 2;
      for ( i = 0; i < a2[17]; ++i )
      {
        if ( v29 == a2[2 * i + 18] )
        {
          j = a2[2 * i + 19];
          goto LABEL_9;
        }
      }
      for ( j = 0; j < 8u; ++j )
      {
        if ( v29 >= a2[2 * j + 1] && v29 <= a2[2 * j + 2] )
          goto LABEL_9;
      }
      j = 0;
    }
LABEL_9:
    result = *(unsigned int *)(a3 + 176);
    *(_DWORD *)(a3 + 176) = result ^ (result ^ (j << 16)) & 0xF0000;
  }
  return result;
}

```

## disassembly

```asm
0x140009860  mov     r11, rsp
0x140009863  push    rbp
0x140009864  push    rsi
0x140009865  push    r15
0x140009867  sub     rsp, 0B0h
0x14000986e  mov     rax, cs:__security_cookie
0x140009875  xor     rax, rsp
0x140009878  mov     [rsp+0C8h+var_48], rax
0x140009880  mov     r15, [rsp+0C8h+arg_20]
0x140009888  mov     rsi, r8
0x14000988b  mov     [r11+10h], rbx
0x14000988f  mov     rbp, rdx
0x140009892  mov     [r11-20h], rdi
0x140009896  mov     rbx, rcx
0x140009899  mov     [r11-30h], r13
0x14000989d  lea     rcx, [rsp+0C8h+var_98]; void *
0x1400098a2  mov     [r11-38h], r14
0x1400098a6  xor     edx, edx; Val
0x1400098a8  mov     r14, [rsp+0C8h+arg_28]
0x1400098b0  mov     r8d, 50h ; 'P'; Size
0x1400098b6  movzx   edi, r9w
0x1400098ba  call    memset
0x1400098bf  test    dil, 1
0x1400098c3  jnz     loc_140009990
0x1400098c9  cmp     qword ptr [rbx+98h], 0FFFFFFFFFFFFFFFFh
0x1400098d1  mov     [rsp+0C8h+var_28], r12
0x1400098d9  jnz     loc_1400099E0
0x1400098df  movzx   eax, byte ptr [rbx+50h]
0x1400098e3  lea     r12, [rbx+38h]
0x1400098e7  movzx   r13d, byte ptr [rbx+52h]
0x1400098ec  mov     [r15], al
0x1400098ef  movzx   edx, byte ptr [rbx+54h]
0x1400098f3  mov     rcx, [r12]
0x1400098f7  movzx   eax, byte ptr [rbx+56h]
0x1400098fb  mov     [r14], al
0x1400098fe  mov     [r12], rcx
0x140009902  mov     r12, [rsp+0C8h+var_28]
0x14000990a  cmp     byte ptr [rbx+57h], 0
0x14000990e  mov     rbx, [rsp+0C8h+arg_8]
0x140009916  mov     r14, [rsp+0C8h+var_38]
0x14000991e  jnz     short loc_140009937
0x140009920  mov     eax, [rsi+0B0h]
0x140009926  movzx   ecx, r13b
0x14000992a  xor     ecx, eax
0x14000992c  and     ecx, 7
0x14000992f  xor     ecx, eax
0x140009931  mov     [rsi+0B0h], ecx
0x140009937  mov     r13, [rsp+0C8h+var_30]
0x14000993f  test    dil, 2
0x140009943  mov     rdi, [rsp+0C8h+var_20]
0x14000994b  jz      short loc_140009973
0x14000994d  cmp     byte ptr [rbp+0], 0
0x140009951  jnz     loc_140009AF7
0x140009957  mov     eax, [rsi+0B0h]
0x14000995d  movzx   ecx, dl
0x140009960  shl     ecx, 10h
0x140009963  xor     ecx, eax
0x140009965  and     ecx, 0F0000h
0x14000996b  xor     ecx, eax
0x14000996d  mov     [rsi+0B0h], ecx
0x140009973  mov     rcx, [rsp+0C8h+var_48]
0x14000997b  xor     rcx, rsp; StackCookie
0x14000997e  call    __security_check_cookie
0x140009983  add     rsp, 0B0h
0x14000998a  pop     r15
0x14000998c  pop     rsi
0x14000998d  pop     rbp
0x14000998e  retn
0x140009990  movzx   eax, byte ptr [rbx+50h]
0x140009994  movzx   r13d, byte ptr [rbx+52h]
0x140009999  mov     [r15], al
0x14000999c  movzx   eax, byte ptr [rbx+56h]
0x1400099a0  movzx   edx, byte ptr [rbx+54h]
0x1400099a4  mov     [r14], al
0x1400099a7  jmp     loc_14000990A
0x1400099ac  mov     r8, cs:QosgEtwDispatchTable
0x1400099b3  movzx   edx, byte ptr [rbx+51h]
0x1400099b7  movzx   r13d, byte ptr [rbx+53h]
0x1400099bc  mov     [r15], dl
0x1400099bf  mov     rax, [r8]
0x1400099c2  movzx   ecx, byte ptr [rbx+55h]
0x1400099c6  mov     [rsp+0C8h+var_A8], cl
0x1400099ca  cmp     dword ptr [rax], 1
0x1400099cd  jz      loc_140009AC4
0x1400099d3  movzx   edx, cl
0x1400099d6  mov     rcx, [rsp+0C8h+var_A0]
0x1400099db  jmp     loc_1400098F7
0x1400099e0  xor     ecx, ecx; ProcNumber
0x1400099e2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400099e9  nop     dword ptr [rax+rax+00h]
0x1400099ee  mov     r8b, 1
0x1400099f1  xor     edx, edx
0x1400099f3  mov     ecx, eax
0x1400099f5  call    QosTimerGetCurrentTime
0x1400099fa  mov     r10, rax
0x1400099fd  mov     rax, [rbx+30h]
0x140009a01  cmp     r10, rax
0x140009a04  jbe     short loc_140009A19
0x140009a06  mov     rdx, r10
0x140009a09  lea     rcx, [rbx+38h]
0x140009a0d  sub     rdx, rax
0x140009a10  call    QosUtilComputeTokenSpec
0x140009a15  mov     [rbx+30h], r10
0x140009a19  mov     rcx, [rsi+8]
0x140009a1d  lea     r12, [rbx+38h]
0x140009a21  mov     rdx, [r12]
0x140009a25  mov     [rsp+0C8h+var_A0], rdx
0x140009a2a  test    rcx, rcx
0x140009a2d  jz      short loc_140009A42
0x140009a2f  mov     eax, [rcx+18h]
0x140009a32  mov     rcx, [rcx]
0x140009a35  sub     rdx, rax
0x140009a38  test    rcx, rcx
0x140009a3b  jnz     short loc_140009A2F
0x140009a3d  mov     [rsp+0C8h+var_A0], rdx
0x140009a42  mov     ecx, [rbx+28h]
0x140009a45  test    ecx, ecx
0x140009a47  jz      short loc_140009AA6
0x140009a49  sub     ecx, 1
0x140009a4c  jz      short loc_140009AAF
0x140009a4e  sub     ecx, 1
0x140009a51  jz      short loc_140009A7F
0x140009a53  cmp     ecx, 1
0x140009a56  mov     rcx, [rsp+0C8h+var_A0]
0x140009a5b  jz      short loc_140009A6A
0x140009a5d  xor     r13b, r13b
0x140009a60  mov     [r15], r13b
0x140009a63  xor     dl, dl
0x140009a65  jmp     loc_1400098F7
0x140009a6a  movzx   eax, byte ptr [rbx+50h]
0x140009a6e  movzx   r13d, byte ptr [rbx+52h]
0x140009a73  mov     [r15], al
0x140009a76  movzx   edx, byte ptr [rbx+54h]
0x140009a7a  jmp     loc_1400098F7
0x140009a7f  movzx   eax, byte ptr [rbx+50h]
0x140009a83  mov     rcx, [rsp+0C8h+var_A0]
0x140009a88  movzx   r13d, byte ptr [rbx+52h]
0x140009a8d  mov     [r15], al
0x140009a90  movzx   edx, byte ptr [rbx+54h]
0x140009a94  test    rcx, rcx
0x140009a97  jns     loc_1400098F7
0x140009a9d  mov     rcx, [r12]
0x140009aa1  jmp     loc_1400098F7
0x140009aa6  test    rdx, rdx
0x140009aa9  js      loc_1400099AC
0x140009aaf  movzx   eax, byte ptr [rbx+50h]
0x140009ab3  movzx   r13d, byte ptr [rbx+52h]
0x140009ab8  mov     [r15], al
0x140009abb  movzx   edx, byte ptr [rbx+54h]
0x140009abf  jmp     loc_1400099D6
0x140009ac4  mov     [rsp+0C8h+var_8C], cx
0x140009ac9  lea     rcx, [rsp+0C8h+var_98]
0x140009ace  shr     dl, 2
0x140009ad1  movzx   eax, dl
0x140009ad4  mov     [rsp+0C8h+var_90], ax
0x140009ad9  mov     [rsp+0C8h+var_98], rsi
0x140009ade  mov     [rsp+0C8h+var_8E], r13w
0x140009ae4  mov     rax, [r8+30h]
0x140009ae8  call    _guard_dispatch_icall
0x140009aed  movzx   edx, [rsp+0C8h+var_A8]
0x140009af2  jmp     loc_1400099D6
0x140009af7  movzx   ecx, byte ptr [r15]
0x140009afb  movzx   r8d, byte ptr [rbp+11h]
0x140009b00  shr     cl, 2
0x140009b03  xor     al, al
0x140009b05  cmp     al, r8b
0x140009b08  jnb     short loc_140009B21
0x140009b0a  movzx   edx, al
0x140009b0d  cmp     cl, [rbp+rdx*2+12h]
0x140009b11  jz      short loc_140009B17
0x140009b13  inc     al
0x140009b15  jmp     short loc_140009B05
0x140009b17  movzx   edx, byte ptr [rbp+rdx*2+13h]
0x140009b1c  jmp     loc_140009957
0x140009b21  xor     dl, dl
0x140009b23  cmp     dl, 8
0x140009b26  jnb     short loc_140009B3F
0x140009b28  movzx   eax, dl
0x140009b2b  cmp     cl, [rbp+rax*2+1]
0x140009b2f  jb      short loc_140009B3B
0x140009b31  cmp     cl, [rbp+rax*2+2]
0x140009b35  jbe     loc_140009957
0x140009b3b  inc     dl
0x140009b3d  jmp     short loc_140009B23
0x140009b3f  xor     dl, dl
0x140009b41  jmp     loc_140009957
```
