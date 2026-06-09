# CVoiceEG::GetLevel(__int64,__int64 *,int)

- ea: `0x18000b4b0`
- end: `0x18000b701`
- name: `?GetLevel@CVoiceEG@@AEAAJ_JPEA_JH@Z`
- size: `593`
- prototype: `__int64 __fastcall(CVoiceEG *__hidden this, __int64, __int64 *, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b1d0`
- `0x18000b4b0`
- `0x18000b710`
- `0x18000c710`
- `0x18000d220`
- `0x18000d320`
- `0x18000e3b0`

## callees

- `0x18000b4b0`

## pseudocode

```c
__int64 __fastcall CVoiceEG::GetLevel(CVoiceEG *this, __int64 a2, __int64 *a3, int a4)
{
  __int64 v6; // rdx
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 result; // rax
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rbx
  __int64 v17; // r9
  __int64 v18; // rbx
  unsigned int v19; // r8d
  __int64 v20; // rdx
  __int64 v21; // rbp
  __int64 v22; // rbx
  int Level; // eax
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // [rsp+30h] [rbp+8h] BYREF

  v6 = *((_QWORD *)this + 8);
  if ( a2 > v6 )
  {
    LODWORD(v15) = 0;
    v21 = *((_QWORD *)this + 2);
    v22 = a2 - v6;
    v26 = 0;
    if ( v22 >= v21 )
    {
      *a3 = 0x7FFFFFFFFFFFFFFFLL;
    }
    else
    {
      Level = CVoiceEG::GetLevel(this, v6, &v26, a4);
      v24 = *((_QWORD *)this + 2);
      v15 = (v21 - v22) * Level / v24;
      if ( v22 >= (v24 >> 2) - 100 )
      {
        v25 = v24 - v22;
        if ( v22 < (v24 >> 1) - 100 )
          v25 = (v24 >> 1) - v22;
        *a3 = v25;
      }
      else
      {
        *a3 = (v24 >> 2) - v22;
      }
    }
    return (unsigned int)v15;
  }
  v8 = a2 - *((_QWORD *)this + 7);
  v9 = *((_QWORD *)this + 4);
  if ( v8 < v9 )
  {
    *a3 = v9 - v8;
    return 0;
  }
  v11 = *(_QWORD *)this;
  v12 = v8 - v9;
  if ( v12 < v11 )
  {
    if ( v11 )
    {
      *a3 = v11 - v12;
      v13 = 0;
      if ( 1000 * v12 / v11 >= 0 )
        v13 = 1000 * v12 / v11;
      v14 = v13;
      v15 = 1000;
      if ( v14 > 1000 )
      {
LABEL_12:
        if ( a4 )
          return (unsigned int)*((__int16 *)&CVoiceEG::m_snAttackTable + v15 / 5);
        return (unsigned int)v15;
      }
    }
    else
    {
      *a3 = -v12;
      v14 = 0;
    }
    v15 = v14;
    goto LABEL_12;
  }
  result = *((_QWORD *)this + 5);
  v16 = v12 - v11;
  if ( v16 < result )
  {
    LODWORD(v15) = 1000;
    *a3 = result - v16;
    if ( a4 )
      return (unsigned int)word_18001EA60;
    return (unsigned int)v15;
  }
  v17 = *((_QWORD *)this + 1);
  v18 = v16 - result;
  LODWORD(result) = *((__int16 *)this + 14);
  if ( v18 >= v17 )
  {
    *a3 = 44100;
    return (unsigned int)result;
  }
  else
  {
    v19 = 1000 - v18 * (1000 - (int)result) / v17;
    if ( v18 >= (v17 >> 2) - 100 )
    {
      v20 = v17 - v18;
      result = v19;
      if ( v18 < (v17 >> 1) - 100 )
        v20 = (v17 >> 1) - v18;
      *a3 = v20;
    }
    else
    {
      result = v19;
      *a3 = (v17 >> 2) - v18;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b4b0  mov     [rsp+arg_10], rbx
0x18000b4b5  mov     [rsp+arg_18], rsi
0x18000b4ba  push    rdi
0x18000b4bb  sub     rsp, 20h
0x18000b4bf  mov     rbx, rdx
0x18000b4c2  mov     rsi, r8
0x18000b4c5  mov     rdx, [rcx+40h]; __int64
0x18000b4c9  mov     rdi, rcx
0x18000b4cc  cmp     rbx, rdx
0x18000b4cf  jg      loc_18000B66D
0x18000b4d5  sub     rbx, [rcx+38h]
0x18000b4d9  mov     rax, [rcx+20h]
0x18000b4dd  cmp     rbx, rax
0x18000b4e0  jge     short loc_18000B4FE
0x18000b4e2  xor     r8d, r8d
0x18000b4e5  sub     rax, rbx
0x18000b4e8  mov     [rsi], rax
0x18000b4eb  mov     eax, r8d
0x18000b4ee  mov     rbx, [rsp+28h+arg_10]
0x18000b4f3  mov     rsi, [rsp+28h+arg_18]
0x18000b4f8  add     rsp, 20h
0x18000b4fc  pop     rdi
0x18000b4fd  retn
0x18000b4fe  mov     rcx, [rcx]
0x18000b501  sub     rbx, rax
0x18000b504  cmp     rbx, rcx
0x18000b507  jge     loc_18000B58F
0x18000b50d  test    rcx, rcx
0x18000b510  jz      short loc_18000B53E
0x18000b512  imul    rax, rbx, 3E8h
0x18000b519  cqo
0x18000b51b  idiv    rcx
0x18000b51e  sub     rcx, rbx
0x18000b521  mov     [r8], rcx
0x18000b524  xor     r8d, r8d
0x18000b527  test    rax, rax
0x18000b52a  cmovns  r8, rax
0x18000b52e  mov     rax, r8
0x18000b531  mov     r8d, 3E8h
0x18000b537  cmp     rax, r8
0x18000b53a  jle     short loc_18000B54A
0x18000b53c  jmp     short loc_18000B54D
0x18000b53e  sub     rcx, rbx
0x18000b541  mov     [r8], rcx
0x18000b544  xor     r8d, r8d
0x18000b547  mov     eax, r8d
0x18000b54a  mov     r8, rax
0x18000b54d  test    r9d, r9d
0x18000b550  jz      loc_18000B6EE
0x18000b556  mov     rax, 6666666666666667h
0x18000b560  imul    r8
0x18000b563  sar     rdx, 1
0x18000b566  mov     rax, rdx
0x18000b569  shr     rax, 3Fh
0x18000b56d  add     rdx, rax
0x18000b570  lea     rax, ?m_snAttackTable@CVoiceEG@@0PAFA; short near * CVoiceEG::m_snAttackTable
0x18000b577  movsx   r8, word ptr [rax+rdx*2]
0x18000b57c  mov     eax, r8d
0x18000b57f  mov     rbx, [rsp+28h+arg_10]
0x18000b584  mov     rsi, [rsp+28h+arg_18]
0x18000b589  add     rsp, 20h
0x18000b58d  pop     rdi
0x18000b58e  retn
0x18000b58f  mov     rax, [rdi+28h]
0x18000b593  sub     rbx, rcx
0x18000b596  cmp     rbx, rax
0x18000b599  jge     short loc_18000B5CB
0x18000b59b  sub     rax, rbx
0x18000b59e  mov     r8d, 3E8h
0x18000b5a4  mov     [rsi], rax
0x18000b5a7  test    r9d, r9d
0x18000b5aa  jz      loc_18000B6EE
0x18000b5b0  movsx   r8, cs:word_18001EA60
0x18000b5b8  mov     eax, r8d
0x18000b5bb  mov     rbx, [rsp+28h+arg_10]
0x18000b5c0  mov     rsi, [rsp+28h+arg_18]
0x18000b5c5  add     rsp, 20h
0x18000b5c9  pop     rdi
0x18000b5ca  retn
0x18000b5cb  mov     r9, [rdi+8]
0x18000b5cf  sub     rbx, rax
0x18000b5d2  movsx   rax, word ptr [rdi+1Ch]
0x18000b5d7  cmp     rbx, r9
0x18000b5da  jge     short loc_18000B650
0x18000b5dc  mov     ecx, eax
0x18000b5de  mov     r8d, 3E8h
0x18000b5e4  mov     eax, r8d
0x18000b5e7  sub     eax, ecx
0x18000b5e9  cdqe
0x18000b5eb  imul    rax, rbx
0x18000b5ef  cqo
0x18000b5f1  idiv    r9
0x18000b5f4  mov     rdx, r9
0x18000b5f7  sar     rdx, 2
0x18000b5fb  sub     r8, rax
0x18000b5fe  lea     rax, [rdx-64h]
0x18000b602  cmp     rbx, rax
0x18000b605  jge     short loc_18000B620
0x18000b607  sub     rdx, rbx
0x18000b60a  mov     eax, r8d
0x18000b60d  mov     [rsi], rdx
0x18000b610  mov     rbx, [rsp+28h+arg_10]
0x18000b615  mov     rsi, [rsp+28h+arg_18]
0x18000b61a  add     rsp, 20h
0x18000b61e  pop     rdi
0x18000b61f  retn
0x18000b620  mov     rcx, r9
0x18000b623  mov     rdx, r9
0x18000b626  sar     rcx, 1
0x18000b629  sub     rdx, rbx
0x18000b62c  lea     rax, [rcx-64h]
0x18000b630  sub     rcx, rbx
0x18000b633  cmp     rbx, rax
0x18000b636  mov     eax, r8d
0x18000b639  cmovl   rdx, rcx
0x18000b63d  mov     [rsi], rdx
0x18000b640  mov     rbx, [rsp+28h+arg_10]
0x18000b645  mov     rsi, [rsp+28h+arg_18]
0x18000b64a  add     rsp, 20h
0x18000b64e  pop     rdi
0x18000b64f  retn
0x18000b650  mov     r8, rax
0x18000b653  mov     qword ptr [rsi], 0AC44h
0x18000b65a  mov     eax, r8d
0x18000b65d  mov     rbx, [rsp+28h+arg_10]
0x18000b662  mov     rsi, [rsp+28h+arg_18]
0x18000b667  add     rsp, 20h
0x18000b66b  pop     rdi
0x18000b66c  retn
0x18000b66d  xor     r8d, r8d
0x18000b670  mov     [rsp+28h+arg_8], rbp
0x18000b675  mov     rbp, [rcx+10h]
0x18000b679  sub     rbx, rdx
0x18000b67c  mov     [rsp+28h+arg_0], r8
0x18000b681  cmp     rbx, rbp
0x18000b684  jge     short loc_18000B6DC
0x18000b686  lea     r8, [rsp+28h+arg_0]; __int64 *
0x18000b68b  call    ?GetLevel@CVoiceEG@@AEAAJ_JPEA_JH@Z; CVoiceEG::GetLevel(__int64,__int64 *,int)
0x18000b690  mov     r9, [rdi+10h]
0x18000b694  sub     rbp, rbx
0x18000b697  cdqe
0x18000b699  imul    rax, rbp
0x18000b69d  cqo
0x18000b69f  idiv    r9
0x18000b6a2  mov     rdx, r9
0x18000b6a5  sar     rdx, 2
0x18000b6a9  mov     r8, rax
0x18000b6ac  lea     rcx, [rdx-64h]
0x18000b6b0  cmp     rbx, rcx
0x18000b6b3  jge     short loc_18000B6BD
0x18000b6b5  sub     rdx, rbx
0x18000b6b8  mov     [rsi], rdx
0x18000b6bb  jmp     short loc_18000B6E9
0x18000b6bd  mov     rcx, r9
0x18000b6c0  mov     rdx, r9
0x18000b6c3  sar     rcx, 1
0x18000b6c6  sub     rdx, rbx
0x18000b6c9  lea     rax, [rcx-64h]
0x18000b6cd  sub     rcx, rbx
0x18000b6d0  cmp     rbx, rax
0x18000b6d3  cmovl   rdx, rcx
0x18000b6d7  mov     [rsi], rdx
0x18000b6da  jmp     short loc_18000B6E9
0x18000b6dc  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000b6e6  mov     [rsi], rax
0x18000b6e9  mov     rbp, [rsp+28h+arg_8]
0x18000b6ee  mov     rbx, [rsp+28h+arg_10]
0x18000b6f3  mov     eax, r8d
0x18000b6f6  mov     rsi, [rsp+28h+arg_18]
0x18000b6fb  add     rsp, 20h
0x18000b6ff  pop     rdi
0x18000b700  retn
```
