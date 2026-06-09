# CVideoProcessor::SetStreamDestRect(uint,int,tagRECT const *)

- ea: `0x180062d40`
- end: `0x180062f50`
- name: `?SetStreamDestRect@CVideoProcessor@@UEAAXIHPEBUtagRECT@@@Z`
- size: `528`
- prototype: `void __fastcall(CVideoProcessor *__hidden this, unsigned int, int, const struct tagRECT *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180035f10`
- `0x180061d08`
- `0x180062ca0`

## callees

- `0x180022400`
- `0x180061d08`
- `0x180062d40`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062df9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062df9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVideoProcessor::SetStreamDestRect(
        CVideoProcessor *this,
        unsigned int a2,
        unsigned int a3,
        const struct tagRECT *a4)
{
  __int64 v6; // r12
  __int64 v8; // rsi
  __int64 v9; // rax
  int v10; // r13d
  __int64 v11; // rbx
  __int64 v12; // [rsp+30h] [rbp-48h]
  __int16 v13; // [rsp+81h] [rbp+9h]
  char v14; // [rsp+83h] [rbp+Bh]

  try
  {
    v6 = a2;
    if ( !*((_DWORD *)this + 140) )
      CVideoProcessor::InitState(this);
    if ( (unsigned int)v6 >= *((_DWORD *)this + 74) )
    {
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
        *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
        3145843,
        v6);
      ThrowFailure(-2147024809);
    }
    if ( a3 )
    {
      if ( !a4 )
      {
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
          *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
          3145842,
          0);
        ThrowFailure(-2147024809);
      }
      if ( a4->left > a4->right || a4->top > a4->bottom )
      {
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
          *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
          3145844,
          0);
        ThrowFailure(-2147024809);
      }
    }
    v8 = 1324 * v6;
    *(_DWORD *)(*((_QWORD *)this + 52) + 1324 * v6 + 44) = a3;
    v9 = *((_QWORD *)this + 52);
    if ( a3 )
      *(struct tagRECT *)(v9 + v8 + 48) = *a4;
    else
      *(_OWORD *)(v9 + v8 + 48) = 0;
    v12 = *(_QWORD *)(*((_QWORD *)this + 20) + 1080LL);
    v10 = *(_DWORD *)(v12 + 3688);
    v11 = *(_QWORD *)(v12 + 3692);
    *(_DWORD *)(v12 + 3688) = GetCurrentThreadId();
    *(_BYTE *)(v12 + 3692) = 0;
    *(_WORD *)(v12 + 3693) = v13;
    *(_BYTE *)(v12 + 3695) = v14;
    *(_DWORD *)(v12 + 3696) = 0;
    (*(void (__fastcall **)(__int64, char *, _QWORD, _QWORD, __int64))(v12 + 3200))(
      *(_QWORD *)(*((_QWORD *)this + 20) + 1080LL) + 40768LL,
      (char *)this + 600,
      (unsigned int)v6,
      a3,
      v8 + *((_QWORD *)this + 52) + 48LL);
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
0x180062d40  mov     [rsp+arg_8], rbx
0x180062d45  mov     [rsp+arg_10], rsi
0x180062d4a  push    rdi
0x180062d4b  push    r12
0x180062d4d  push    r13
0x180062d4f  push    r14
0x180062d51  push    r15
0x180062d53  sub     rsp, 50h
0x180062d57  mov     rbx, r9
0x180062d5a  mov     r15d, r8d
0x180062d5d  mov     r12d, edx
0x180062d60  mov     rdi, rcx
0x180062d63  cmp     dword ptr [rcx+230h], 0
0x180062d6a  jz      loc_180062EAE
0x180062d70  cmp     r12d, [rdi+128h]
0x180062d77  jnb     loc_180062EB8
0x180062d7d  test    r15d, r15d
0x180062d80  jz      short loc_180062DA2
0x180062d82  test    rbx, rbx
0x180062d85  jz      loc_180062EE9
0x180062d8b  mov     eax, [rbx+8]
0x180062d8e  cmp     [rbx], eax
0x180062d90  jg      loc_180062F1A
0x180062d96  mov     eax, [rbx+0Ch]
0x180062d99  cmp     [rbx+4], eax
0x180062d9c  jg      loc_180062F1A
0x180062da2  imul    rsi, r12, 52Ch
0x180062da9  mov     rax, [rdi+1A0h]
0x180062db0  mov     [rax+rsi+2Ch], r15d
0x180062db5  mov     rax, [rdi+1A0h]
0x180062dbc  test    r15d, r15d
0x180062dbf  jz      loc_180062EA1
0x180062dc5  movups  xmm0, xmmword ptr [rbx]
0x180062dc8  movdqu  xmmword ptr [rax+rsi+30h], xmm0
0x180062dce  mov     rax, [rdi+0A0h]
0x180062dd5  mov     r14, [rax+438h]
0x180062ddc  mov     [rsp+78h+var_48], r14
0x180062de1  mov     r13d, [r14+0E68h]
0x180062de8  mov     [rsp+78h+var_40], r13d
0x180062ded  mov     rbx, [r14+0E6Ch]
0x180062df4  mov     [rsp+78h+var_3C], rbx
0x180062df9  call    cs:__imp_GetCurrentThreadId
0x180062dff  mov     [r14+0E68h], eax
0x180062e06  mov     byte ptr [r14+0E6Ch], 0
0x180062e0e  movzx   eax, [rsp+78h+arg_1]
0x180062e16  mov     [r14+0E6Dh], ax
0x180062e1e  mov     al, [rsp+78h+arg_3]
0x180062e25  mov     [r14+0E6Fh], al
0x180062e2c  mov     dword ptr [r14+0E70h], 0
0x180062e37  mov     rax, [rdi+0A0h]
0x180062e3e  mov     rcx, [rax+438h]
0x180062e45  add     rcx, 9F40h
0x180062e4c  mov     r8, [rdi+1A0h]
0x180062e53  add     r8, 30h ; '0'
0x180062e57  add     r8, rsi
0x180062e5a  lea     rdx, [rdi+258h]
0x180062e61  mov     [rsp+78h+var_58], r8
0x180062e66  mov     r9d, r15d
0x180062e69  mov     r8d, r12d
0x180062e6c  mov     rax, [r14+0C80h]
0x180062e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e78  nop
0x180062e79  mov     [r14+0E68h], r13d
0x180062e80  mov     [r14+0E6Ch], rbx
0x180062e87  lea     r11, [rsp+78h+var_28]
0x180062e8c  mov     rbx, [r11+38h]
0x180062e90  mov     rsi, [r11+40h]
0x180062e94  mov     rsp, r11
0x180062e97  pop     r15
0x180062e99  pop     r14
0x180062e9b  pop     r13
0x180062e9d  pop     r12
0x180062e9f  pop     rdi
0x180062ea0  retn
0x180062ea1  xorps   xmm0, xmm0
0x180062ea4  movups  xmmword ptr [rax+rsi+30h], xmm0
0x180062ea9  jmp     loc_180062DCE
0x180062eae  call    ?InitState@CVideoProcessor@@QEAAXXZ; CVideoProcessor::InitState(void)
0x180062eb3  jmp     loc_180062D70
0x180062eb8  mov     rax, [rdi+0A0h]
0x180062ebf  mov     rcx, [rax+4E0h]
0x180062ec6  mov     rax, [rcx]
0x180062ec9  mov     r8, r12
0x180062ecc  mov     edx, 300073h
0x180062ed1  mov     rax, [rax+20h]
0x180062ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062eda  mov     ecx, 80070057h; int
0x180062edf  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180062ee4  jmp     loc_180062D7D
0x180062ee9  mov     rax, [rdi+0A0h]
0x180062ef0  mov     rcx, [rax+4E0h]
0x180062ef7  mov     rax, [rcx]
0x180062efa  xor     r8d, r8d
0x180062efd  mov     edx, 300072h
0x180062f02  mov     rax, [rax+20h]
0x180062f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062f0b  mov     ecx, 80070057h; int
0x180062f10  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180062f15  jmp     loc_180062D8B
0x180062f1a  mov     rax, [rdi+0A0h]
0x180062f21  mov     rcx, [rax+4E0h]
0x180062f28  mov     rax, [rcx]
0x180062f2b  xor     r8d, r8d
0x180062f2e  mov     edx, 300074h
0x180062f33  mov     rax, [rax+20h]
0x180062f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062f3c  mov     ecx, 80070057h; int
0x180062f41  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180062f46  jmp     loc_180062DA2
0x180062f4b  jmp     loc_180062E87
```
