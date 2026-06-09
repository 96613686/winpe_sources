# CVideoProcessor::SetStreamSourceRect(uint,int,tagRECT const *)

- ea: `0x180063000`
- end: `0x18006322d`
- name: `?SetStreamSourceRect@CVideoProcessor@@UEAAXIHPEBUtagRECT@@@Z`
- size: `557`
- prototype: `void __fastcall(CVideoProcessor *__hidden this, unsigned int, int, const struct tagRECT *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180035f10`
- `0x180061d08`
- `0x180062f60`

## callees

- `0x180022400`
- `0x180061d08`
- `0x180063000`
- `0x1800dd664`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800630ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800630ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CVideoProcessor::SetStreamSourceRect(
        CVideoProcessor *this,
        unsigned int a2,
        unsigned int a3,
        const struct tagRECT *a4)
{
  __int64 v6; // r12
  __int64 v8; // r14
  __int64 v9; // rax
  int v10; // r13d
  __int64 v11; // rbx
  __int64 v12; // [rsp+30h] [rbp-68h]
  void **pExceptionObject; // [rsp+48h] [rbp-50h] BYREF
  int v14; // [rsp+50h] [rbp-48h]
  __int128 v15; // [rsp+58h] [rbp-40h]
  __int16 v16; // [rsp+A1h] [rbp+9h]
  char v17; // [rsp+A3h] [rbp+Bh]

  try
  {
    v6 = a2;
    if ( !*((_DWORD *)this + 140) )
      CVideoProcessor::InitState(this);
    if ( (unsigned int)v6 >= *((_DWORD *)this + 74) )
    {
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
        *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
        3145840,
        v6);
      ThrowFailure(-2147024809);
    }
    if ( a3 )
    {
      if ( !a4 )
      {
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
          *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
          3145839,
          0);
        ThrowFailure(-2147024809);
      }
      if ( a4->left > a4->right || a4->top > a4->bottom )
      {
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
          *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
          3145841,
          0);
        pExceptionObject = &_com_error::`vftable';
        v14 = -2147024809;
        v15 = 0;
        throw (_com_error *)&pExceptionObject;
      }
    }
    v8 = 1324 * v6;
    *(_DWORD *)(*((_QWORD *)this + 52) + 1324 * v6 + 24) = a3;
    v9 = *((_QWORD *)this + 52);
    if ( a3 )
      *(struct tagRECT *)(v9 + v8 + 28) = *a4;
    else
      *(_OWORD *)(v9 + v8 + 28) = 0;
    v12 = *(_QWORD *)(*((_QWORD *)this + 20) + 1080LL);
    v10 = *(_DWORD *)(v12 + 3688);
    v11 = *(_QWORD *)(v12 + 3692);
    *(_DWORD *)(v12 + 3688) = GetCurrentThreadId();
    *(_BYTE *)(v12 + 3692) = 0;
    *(_WORD *)(v12 + 3693) = v16;
    *(_BYTE *)(v12 + 3695) = v17;
    *(_DWORD *)(v12 + 3696) = 0;
    (*(void (__fastcall **)(__int64, char *, _QWORD, _QWORD, __int64))(v12 + 3192))(
      *(_QWORD *)(*((_QWORD *)this + 20) + 1080LL) + 40768LL,
      (char *)this + 600,
      (unsigned int)v6,
      a3,
      v8 + *((_QWORD *)this + 52) + 28LL);
    *(_DWORD *)(v12 + 3688) = v10;
    *(_QWORD *)(v12 + 3692) = v11;
  }
  catch ( _com_error )
  {
  }
}

```

## disassembly

```asm
0x180063000  mov     [rsp+arg_8], rbx
0x180063005  mov     [rsp+arg_10], rsi
0x18006300a  push    rdi
0x18006300b  push    r12
0x18006300d  push    r13
0x18006300f  push    r14
0x180063011  push    r15
0x180063013  sub     rsp, 70h
0x180063017  mov     rbx, r9
0x18006301a  mov     r15d, r8d
0x18006301d  mov     r12d, edx
0x180063020  mov     rdi, rcx
0x180063023  cmp     dword ptr [rcx+230h], 0
0x18006302a  jz      loc_1800631BC
0x180063030  cmp     r12d, [rdi+128h]
0x180063037  jnb     loc_1800631C6
0x18006303d  test    r15d, r15d
0x180063040  jz      short loc_180063062
0x180063042  test    rbx, rbx
0x180063045  jz      loc_1800631F7
0x18006304b  mov     eax, [rbx+8]
0x18006304e  cmp     [rbx], eax
0x180063050  jg      loc_18006316B
0x180063056  mov     eax, [rbx+0Ch]
0x180063059  cmp     [rbx+4], eax
0x18006305c  jg      loc_18006316B
0x180063062  imul    r14, r12, 52Ch
0x180063069  mov     rax, [rdi+1A0h]
0x180063070  mov     [rax+r14+18h], r15d
0x180063075  mov     rax, [rdi+1A0h]
0x18006307c  test    r15d, r15d
0x18006307f  jz      loc_18006315D
0x180063085  movups  xmm0, xmmword ptr [rbx]
0x180063088  movdqu  xmmword ptr [rax+r14+1Ch], xmm0
0x18006308f  mov     rax, [rdi+0A0h]
0x180063096  mov     rsi, [rax+438h]
0x18006309d  mov     [rsp+98h+var_68], rsi
0x1800630a2  mov     r13d, [rsi+0E68h]
0x1800630a9  mov     [rsp+98h+var_60], r13d
0x1800630ae  mov     rbx, [rsi+0E6Ch]
0x1800630b5  mov     [rsp+98h+var_5C], rbx
0x1800630ba  call    cs:__imp_GetCurrentThreadId
0x1800630c0  mov     [rsi+0E68h], eax
0x1800630c6  mov     byte ptr [rsi+0E6Ch], 0
0x1800630cd  movzx   eax, [rsp+98h+arg_1]
0x1800630d5  mov     [rsi+0E6Dh], ax
0x1800630dc  mov     al, [rsp+98h+arg_3]
0x1800630e3  mov     [rsi+0E6Fh], al
0x1800630e9  mov     dword ptr [rsi+0E70h], 0
0x1800630f3  mov     rax, [rdi+0A0h]
0x1800630fa  mov     rcx, [rax+438h]
0x180063101  add     rcx, 9F40h
0x180063108  mov     r8, [rdi+1A0h]
0x18006310f  add     r8, 1Ch
0x180063113  add     r8, r14
0x180063116  lea     rdx, [rdi+258h]
0x18006311d  mov     [rsp+98h+var_78], r8
0x180063122  mov     r9d, r15d
0x180063125  mov     r8d, r12d
0x180063128  mov     rax, [rsi+0C78h]
0x18006312f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063134  nop
0x180063135  mov     [rsi+0E68h], r13d
0x18006313c  mov     [rsi+0E6Ch], rbx
0x180063143  lea     r11, [rsp+98h+var_28]
0x180063148  mov     rbx, [r11+38h]
0x18006314c  mov     rsi, [r11+40h]
0x180063150  mov     rsp, r11
0x180063153  pop     r15
0x180063155  pop     r14
0x180063157  pop     r13
0x180063159  pop     r12
0x18006315b  pop     rdi
0x18006315c  retn
0x18006315d  xorps   xmm0, xmm0
0x180063160  movups  xmmword ptr [rax+r14+1Ch], xmm0
0x180063166  jmp     loc_18006308F
0x18006316b  mov     rax, [rdi+0A0h]
0x180063172  mov     rcx, [rax+4E0h]
0x180063179  mov     rax, [rcx]
0x18006317c  xor     r8d, r8d
0x18006317f  mov     edx, 300071h
0x180063184  mov     rax, [rax+20h]
0x180063188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006318d  nop
0x18006318e  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180063195  mov     [rsp+98h+pExceptionObject], rax
0x18006319a  mov     [rsp+98h+var_48], 80070057h
0x1800631a2  xorps   xmm0, xmm0
0x1800631a5  movdqu  [rsp+98h+var_40], xmm0
0x1800631ab  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x1800631b2  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800631b7  call    _CxxThrowException_0
0x1800631bc  call    ?InitState@CVideoProcessor@@QEAAXXZ; CVideoProcessor::InitState(void)
0x1800631c1  jmp     loc_180063030
0x1800631c6  mov     rax, [rdi+0A0h]
0x1800631cd  mov     rcx, [rax+4E0h]
0x1800631d4  mov     rax, [rcx]
0x1800631d7  mov     r8, r12
0x1800631da  mov     edx, 300070h
0x1800631df  mov     rax, [rax+20h]
0x1800631e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631e8  mov     ecx, 80070057h; int
0x1800631ed  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800631f2  jmp     loc_18006303D
0x1800631f7  mov     rax, [rdi+0A0h]
0x1800631fe  mov     rcx, [rax+4E0h]
0x180063205  mov     rax, [rcx]
0x180063208  xor     r8d, r8d
0x18006320b  mov     edx, 30006Fh
0x180063210  mov     rax, [rax+20h]
0x180063214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063219  mov     ecx, 80070057h; int
0x18006321e  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180063223  jmp     loc_18006304B
0x180063228  jmp     loc_180063143
```
