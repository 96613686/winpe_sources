# CVideoProcessor::SetOutputTargetRect(int,tagRECT const *)

- ea: `0x1800617a0`
- end: `0x180061961`
- name: `?SetOutputTargetRect@CVideoProcessor@@UEAAXHPEBUtagRECT@@@Z`
- size: `449`
- prototype: `void __fastcall(CVideoProcessor *__hidden this, int, const struct tagRECT *)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180035f10`
- `0x180061700`
- `0x180061d08`
- `0x18007ce70`

## callees

- `0x180022400`
- `0x1800617a0`
- `0x180061d08`
- `0x1800dd664`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061834`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061834`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CVideoProcessor::SetOutputTargetRect(CVideoProcessor *this, int a2, const struct tagRECT *a3)
{
  struct tagRECT *v6; // r14
  int v7; // r15d
  __int64 v8; // rbx
  __int64 v9; // [rsp+30h] [rbp-58h]
  void **pExceptionObject; // [rsp+48h] [rbp-40h] BYREF
  int v11; // [rsp+50h] [rbp-38h]
  __int128 v12; // [rsp+58h] [rbp-30h]
  __int16 v13; // [rsp+91h] [rbp+9h]
  char v14; // [rsp+93h] [rbp+Bh]

  try
  {
    if ( !*((_DWORD *)this + 140) )
      CVideoProcessor::InitState(this);
    if ( a2 )
    {
      if ( !a3 )
      {
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
          *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
          3145809,
          0);
        ThrowFailure(-2147024809);
      }
      if ( a3->left > a3->right || a3->top > a3->bottom )
      {
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 20) + 1248LL) + 32LL))(
          *(_QWORD *)(*((_QWORD *)this + 20) + 1248LL),
          3145809,
          0);
        pExceptionObject = &_com_error::`vftable';
        v11 = -2147024809;
        v12 = 0;
        throw (_com_error *)&pExceptionObject;
      }
    }
    *((_DWORD *)this + 76) = a2;
    v6 = (struct tagRECT *)((char *)this + 308);
    if ( a2 )
      *v6 = *a3;
    else
      *v6 = 0;
    v9 = *(_QWORD *)(*((_QWORD *)this + 20) + 1080LL);
    v7 = *(_DWORD *)(v9 + 3688);
    v8 = *(_QWORD *)(v9 + 3692);
    *(_DWORD *)(v9 + 3688) = GetCurrentThreadId();
    *(_BYTE *)(v9 + 3692) = 0;
    *(_WORD *)(v9 + 3693) = v13;
    *(_BYTE *)(v9 + 3695) = v14;
    *(_DWORD *)(v9 + 3696) = 0;
    (*(void (__fastcall **)(__int64, char *, _QWORD, char *))(v9 + 3104))(
      *(_QWORD *)(*((_QWORD *)this + 20) + 1080LL) + 40768LL,
      (char *)this + 600,
      *((unsigned int *)this + 76),
      (char *)this + 308);
    *(_DWORD *)(v9 + 3688) = v7;
    *(_QWORD *)(v9 + 3692) = v8;
  }
  catch ( _com_error )
  {
  }
}

```

## disassembly

```asm
0x1800617a0  mov     [rsp+arg_8], rbx
0x1800617a5  mov     [rsp+arg_10], rsi
0x1800617aa  push    rdi
0x1800617ab  push    r14
0x1800617ad  push    r15
0x1800617af  sub     rsp, 70h
0x1800617b3  mov     rbx, r8
0x1800617b6  mov     esi, edx
0x1800617b8  mov     rdi, rcx
0x1800617bb  cmp     dword ptr [rcx+230h], 0
0x1800617c2  jz      loc_180061921
0x1800617c8  test    esi, esi
0x1800617ca  jz      short loc_1800617EC
0x1800617cc  test    rbx, rbx
0x1800617cf  jz      loc_18006192B
0x1800617d5  mov     eax, [rbx+8]
0x1800617d8  cmp     [rbx], eax
0x1800617da  jg      loc_1800618D0
0x1800617e0  mov     eax, [rbx+0Ch]
0x1800617e3  cmp     [rbx+4], eax
0x1800617e6  jg      loc_1800618D0
0x1800617ec  mov     [rdi+130h], esi
0x1800617f2  lea     r14, [rdi+134h]
0x1800617f9  test    esi, esi
0x1800617fb  jz      loc_1800618C4
0x180061801  movups  xmm0, xmmword ptr [rbx]
0x180061804  movdqu  xmmword ptr [r14], xmm0
0x180061809  mov     rax, [rdi+0A0h]
0x180061810  mov     rsi, [rax+438h]
0x180061817  mov     [rsp+88h+var_58], rsi
0x18006181c  mov     r15d, [rsi+0E68h]
0x180061823  mov     [rsp+88h+var_50], r15d
0x180061828  mov     rbx, [rsi+0E6Ch]
0x18006182f  mov     [rsp+88h+var_4C], rbx
0x180061834  call    cs:__imp_GetCurrentThreadId
0x18006183a  mov     [rsi+0E68h], eax
0x180061840  mov     byte ptr [rsi+0E6Ch], 0
0x180061847  movzx   eax, [rsp+88h+arg_1]
0x18006184f  mov     [rsi+0E6Dh], ax
0x180061856  mov     al, [rsp+88h+arg_3]
0x18006185d  mov     [rsi+0E6Fh], al
0x180061863  mov     dword ptr [rsi+0E70h], 0
0x18006186d  mov     rax, [rdi+0A0h]
0x180061874  mov     rcx, [rax+438h]
0x18006187b  add     rcx, 9F40h
0x180061882  lea     rdx, [rdi+258h]
0x180061889  mov     r9, r14
0x18006188c  mov     r8d, [rdi+130h]
0x180061893  mov     rax, [rsi+0C20h]
0x18006189a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006189f  nop
0x1800618a0  mov     [rsi+0E68h], r15d
0x1800618a7  mov     [rsi+0E6Ch], rbx
0x1800618ae  lea     r11, [rsp+88h+var_18]
0x1800618b3  mov     rbx, [r11+28h]
0x1800618b7  mov     rsi, [r11+30h]
0x1800618bb  mov     rsp, r11
0x1800618be  pop     r15
0x1800618c0  pop     r14
0x1800618c2  pop     rdi
0x1800618c3  retn
0x1800618c4  xorps   xmm0, xmm0
0x1800618c7  movups  xmmword ptr [r14], xmm0
0x1800618cb  jmp     loc_180061809
0x1800618d0  mov     rax, [rdi+0A0h]
0x1800618d7  mov     rcx, [rax+4E0h]
0x1800618de  mov     rax, [rcx]
0x1800618e1  xor     r8d, r8d
0x1800618e4  mov     edx, 300051h
0x1800618e9  mov     rax, [rax+20h]
0x1800618ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800618f2  nop
0x1800618f3  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x1800618fa  mov     [rsp+88h+pExceptionObject], rax
0x1800618ff  mov     [rsp+88h+var_38], 80070057h
0x180061907  xorps   xmm0, xmm0
0x18006190a  movdqu  [rsp+88h+var_30], xmm0
0x180061910  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180061917  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18006191c  call    _CxxThrowException_0
0x180061921  call    ?InitState@CVideoProcessor@@QEAAXXZ; CVideoProcessor::InitState(void)
0x180061926  jmp     loc_1800617C8
0x18006192b  mov     rax, [rdi+0A0h]
0x180061932  mov     rcx, [rax+4E0h]
0x180061939  mov     rax, [rcx]
0x18006193c  xor     r8d, r8d
0x18006193f  mov     edx, 300051h
0x180061944  mov     rax, [rax+20h]
0x180061948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006194d  mov     ecx, 80070057h; int
0x180061952  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180061957  jmp     loc_1800617D5
0x18006195c  jmp     loc_1800618AE
```
