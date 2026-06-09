# CDwnBindData::Signal(ushort)

- ea: `0x1804e4004`
- end: `0x1804e4336`
- name: `?Signal@CDwnBindData@@AEAAXG@Z`
- size: `818`
- prototype: `void __fastcall(CDwnBindData *__hidden this, unsigned __int16)`
- caller_count: `8`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1804e3010`
- `0x1804e394c`
- `0x1804e58d0`
- `0x1804e63b0`
- `0x1804e95a0`
- `0x1804e9790`
- `0x1804eb38c`
- `0x18064c5c0`

## callees

- `0x180496b0c`
- `0x1804e192c`
- `0x1804e4004`
- `0x1804e44e0`
- `0x18062947c`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1804e423e`
- `msvcrt!memcpy_s` at `0x1804e423e`
- `KERNEL32!GetCurrentThreadId` at `0x1804e40e4`
- `KERNEL32!GetCurrentThreadId` at `0x1804e40e4`
- `KERNEL32!LeaveCriticalSection` at `0x1804e4076`
- `KERNEL32!LeaveCriticalSection` at `0x1804e4076`
- `KERNEL32!EnterCriticalSection` at `0x1804e403f`
- `KERNEL32!EnterCriticalSection` at `0x1804e403f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e4114`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e411d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e4127`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e4131`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e41f4`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e41fe`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e4114`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e411d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e4127`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e4131`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e41f4`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e41fe`

## pseudocode

```c
void __fastcall CDwnBindData::Signal(CDwnBindData *this, __int16 a2)
{
  __int64 v4; // rbx
  __int16 v5; // si
  unsigned __int16 v6; // dx
  bool v7; // zf
  DWORD CurrentThreadId; // eax
  __int128 v9; // xmm6
  __int128 v10; // xmm7
  char v11; // r15
  struct IE_GLOBAL_THREAD_STATE *v12; // rax
  int v13; // ebp
  const void *v14; // r8
  CDwnBindData *v15; // rcx
  _BYTE v16[8]; // [rsp+20h] [rbp-78h] BYREF
  __int64 Destination; // [rsp+28h] [rbp-70h] BYREF
  int v18; // [rsp+30h] [rbp-68h]

  _InterlockedIncrement((volatile signed __int32 *)this + 5);
  while ( 1 )
  {
    v4 = 0;
    LOBYTE(v5) = 0;
    EnterCriticalSection(&g_csDwnBindSig);
    v6 = a2 & ~(*((_WORD *)this + 218) & 0x40);
    *((_WORD *)this + 218) |= v6;
    if ( *((_QWORD *)this + 56) )
    {
      v7 = (v6 | *((_WORD *)this + 219)) == 0;
      *((_WORD *)this + 219) |= v6;
      if ( !v7 && !*((_DWORD *)this + 110) )
      {
        v5 = *((_WORD *)this + 219);
        *((_WORD *)this + 219) = 0;
        CurrentThreadId = GetCurrentThreadId();
        v4 = *((_QWORD *)this + 56);
        *((_DWORD *)this + 110) = CurrentThreadId;
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 20));
      }
    }
    LeaveCriticalSection(&g_csDwnBindSig);
    if ( !v4 )
      break;
    if ( !*((_BYTE *)this + 792) && *((_QWORD *)this + 50) && (v5 & 0x20) != 0 )
      CDwnBindData::BufferData(this);
    v9 = *(_OWORD *)((char *)this + 1080);
    v10 = *(_OWORD *)GlobalThreadState();
    v11 = *((_BYTE *)GlobalThreadState() + 16);
    *(_OWORD *)GlobalThreadState() = v9;
    v12 = GlobalThreadState();
    v16[0] = 0;
    *((_BYTE *)v12 + 16) = 1;
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v4 + 24LL))(v4, v16);
    if ( !v16[0] )
    {
      if ( (v5 & 1) != 0 )
      {
        v14 = (const void *)(*(_QWORD *)(v4 + 40) + 424LL);
        Destination = 0;
        v18 = 0;
        memcpy_s(&Destination, 0xCu, v14, 0xCu);
        v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 40LL))(v4, &Destination);
        if ( v13 )
          goto LABEL_18;
      }
      if ( (v5 & 2) != 0
        && (v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v4 + 48LL))(
                    v4,
                    *(_QWORD *)(*(_QWORD *)(v4 + 40) + 512LL),
                    *(_QWORD *)(*(_QWORD *)(v4 + 40) + 528LL))) != 0
        || (v5 & 8) != 0
        && (CDwnBindData::AddToPrivacyList(*(CDwnBindData **)(v4 + 40)),
            (v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 56LL))(v4)) != 0)
        || (v5 & 0x10) != 0
        && (v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 64LL))(
                    v4,
                    *(_QWORD *)(*(_QWORD *)(v4 + 40) + 456LL))) != 0 )
      {
LABEL_18:
        if ( v13 >= 0 )
          goto LABEL_19;
        if ( !*(_DWORD *)(v4 + 92) )
        {
          v15 = *(CDwnBindData **)(v4 + 40);
          *(_DWORD *)(v4 + 92) = 1;
          CDwnBindData::Disconnect(v15);
          CDwnBindData::Terminate(*(CDwnBindData **)(v4 + 40), v13);
        }
        goto LABEL_20;
      }
      if ( (v5 & 0x20) != 0 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4);
        goto LABEL_18;
      }
LABEL_19:
      if ( (v5 & 0x40) != 0 )
LABEL_20:
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 80LL))(
          v4,
          *(unsigned int *)(*(_QWORD *)(v4 + 40) + 756LL));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 32LL))(v4);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 20), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
    *(_OWORD *)GlobalThreadState() = v10;
    a2 = 0;
    *((_BYTE *)GlobalThreadState() + 16) = v11;
    *((_DWORD *)this + 110) = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 5, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(CDwnBindData *, __int64))this)(this, 1);
}

```

## disassembly

```asm
0x1804e4004  push    rbx
0x1804e4006  push    rbp
0x1804e4007  push    rsi
0x1804e4008  push    rdi
0x1804e4009  push    r14
0x1804e400b  push    r15
0x1804e400d  sub     rsp, 68h
0x1804e4011  movaps  [rsp+98h+var_48], xmm6
0x1804e4016  movaps  [rsp+98h+var_58], xmm7
0x1804e401b  mov     rax, cs:__security_cookie
0x1804e4022  xor     rax, rsp
0x1804e4025  mov     [rsp+98h+var_60], rax
0x1804e402a  movzx   ebp, dx
0x1804e402d  mov     rdi, rcx
0x1804e4030  lock inc dword ptr [rcx+14h]
0x1804e4034  lea     rcx, ?g_csDwnBindSig@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x1804e403b  xor     ebx, ebx
0x1804e403d  xor     esi, esi
0x1804e403f  call    cs:__imp_EnterCriticalSection
0x1804e4045  movzx   ecx, word ptr [rdi+1B4h]
0x1804e404c  movzx   edx, cx
0x1804e404f  and     dx, 40h
0x1804e4053  not     dx
0x1804e4056  and     dx, bp
0x1804e4059  movzx   eax, dx
0x1804e405c  or      ax, cx
0x1804e405f  mov     [rdi+1B4h], ax
0x1804e4066  cmp     [rdi+1C0h], rbx
0x1804e406d  jnz     short loc_1804E40C3
0x1804e406f  lea     rcx, ?g_csDwnBindSig@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x1804e4076  call    cs:__imp_LeaveCriticalSection
0x1804e407c  test    rbx, rbx
0x1804e407f  jnz     short loc_1804E4100
0x1804e4081  or      eax, 0FFFFFFFFh
0x1804e4084  lock xadd [rdi+14h], eax
0x1804e4089  cmp     eax, 1
0x1804e408c  jnz     short loc_1804E409F
0x1804e408e  mov     rax, [rdi]
0x1804e4091  lea     edx, [rbx+1]
0x1804e4094  mov     rcx, rdi
0x1804e4097  mov     rax, [rax]
0x1804e409a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e409f  mov     rcx, [rsp+98h+var_60]
0x1804e40a4  xor     rcx, rsp; StackCookie
0x1804e40a7  call    __security_check_cookie
0x1804e40ac  movaps  xmm6, [rsp+98h+var_48]
0x1804e40b1  movaps  xmm7, [rsp+98h+var_58]
0x1804e40b6  add     rsp, 68h
0x1804e40ba  pop     r15
0x1804e40bc  pop     r14
0x1804e40be  pop     rdi
0x1804e40bf  pop     rsi
0x1804e40c0  pop     rbp
0x1804e40c1  pop     rbx
0x1804e40c2  retn
0x1804e40c3  or      [rdi+1B6h], dx
0x1804e40ca  jz      short loc_1804E406F
0x1804e40cc  mov     eax, [rdi+1B8h]
0x1804e40d2  test    eax, eax
0x1804e40d4  jnz     short loc_1804E406F
0x1804e40d6  movzx   esi, word ptr [rdi+1B6h]
0x1804e40dd  mov     [rdi+1B6h], ax
0x1804e40e4  call    cs:__imp_GetCurrentThreadId
0x1804e40ea  mov     rbx, [rdi+1C0h]
0x1804e40f1  mov     [rdi+1B8h], eax
0x1804e40f7  lock inc dword ptr [rbx+14h]
0x1804e40fb  jmp     loc_1804E406F
0x1804e4100  cmp     byte ptr [rdi+318h], 0
0x1804e4107  jz      loc_1804E4267
0x1804e410d  movups  xmm6, xmmword ptr [rdi+438h]
0x1804e4114  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1804e411a  movups  xmm7, xmmword ptr [rax]
0x1804e411d  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1804e4123  mov     r15b, [rax+10h]
0x1804e4127  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1804e412d  movdqu  xmmword ptr [rax], xmm6
0x1804e4131  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1804e4137  lea     rdx, [rsp+98h+var_78]
0x1804e413c  mov     [rsp+98h+var_78], 0
0x1804e4141  mov     rcx, rbx
0x1804e4144  mov     byte ptr [rax+10h], 1
0x1804e4148  mov     rax, [rbx]
0x1804e414b  mov     rax, [rax+18h]
0x1804e414f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e4154  cmp     [rsp+98h+var_78], 0
0x1804e4159  jnz     short loc_1804E41D4
0x1804e415b  movzx   r14d, si
0x1804e415f  test    sil, 1
0x1804e4163  jnz     loc_1804E4219
0x1804e4169  test    sil, 2
0x1804e416d  jnz     loc_1804E42DC
0x1804e4173  test    sil, 8
0x1804e4177  jnz     loc_1804E428C
0x1804e417d  test    sil, 10h
0x1804e4181  jnz     loc_1804E42B3
0x1804e4187  test    sil, 20h
0x1804e418b  jz      short loc_1804E41A6
0x1804e418d  mov     rax, [rbx]
0x1804e4190  mov     rcx, rbx
0x1804e4193  mov     rax, [rax+48h]
0x1804e4197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e419c  mov     ebp, eax
0x1804e419e  test    ebp, ebp
0x1804e41a0  js      loc_1804E430C
0x1804e41a6  test    r14b, 40h
0x1804e41aa  jz      short loc_1804E41C5
0x1804e41ac  mov     rax, [rbx]
0x1804e41af  mov     rcx, rbx
0x1804e41b2  mov     rdx, [rbx+28h]
0x1804e41b6  mov     rax, [rax+50h]
0x1804e41ba  mov     edx, [rdx+2F4h]
0x1804e41c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e41c5  mov     rax, [rbx]
0x1804e41c8  mov     rcx, rbx
0x1804e41cb  mov     rax, [rax+20h]
0x1804e41cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e41d4  or      eax, 0FFFFFFFFh
0x1804e41d7  lock xadd [rbx+14h], eax
0x1804e41dc  cmp     eax, 1
0x1804e41df  jnz     short loc_1804E41F4
0x1804e41e1  mov     rax, [rbx]
0x1804e41e4  mov     edx, 1
0x1804e41e9  mov     rcx, rbx
0x1804e41ec  mov     rax, [rax]
0x1804e41ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e41f4  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1804e41fa  movdqu  xmmword ptr [rax], xmm7
0x1804e41fe  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1804e4204  xor     ebp, ebp
0x1804e4206  mov     [rax+10h], r15b
0x1804e420a  mov     dword ptr [rdi+1B8h], 0
0x1804e4214  jmp     loc_1804E4034
0x1804e4219  mov     r8, [rbx+28h]
0x1804e421d  lea     rcx, [rsp+98h+Destination]; Destination
0x1804e4222  xor     eax, eax
0x1804e4224  add     r8, 1A8h; Source
0x1804e422b  mov     [rsp+98h+Destination], rax
0x1804e4230  mov     [rsp+98h+var_68], eax
0x1804e4234  mov     eax, 0Ch
0x1804e4239  mov     r9d, eax; SourceSize
0x1804e423c  mov     edx, eax; DestinationSize
0x1804e423e  call    cs:__imp_memcpy_s
0x1804e4244  mov     rax, [rbx]
0x1804e4247  lea     rdx, [rsp+98h+Destination]
0x1804e424c  mov     rcx, rbx
0x1804e424f  mov     rax, [rax+28h]
0x1804e4253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e4258  mov     ebp, eax
0x1804e425a  test    eax, eax
0x1804e425c  jz      loc_1804E4169
0x1804e4262  jmp     loc_1804E419E
0x1804e4267  cmp     qword ptr [rdi+190h], 0
0x1804e426f  jz      loc_1804E410D
0x1804e4275  test    sil, 20h
0x1804e4279  jz      loc_1804E410D
0x1804e427f  mov     rcx, rdi; this
0x1804e4282  call    ?BufferData@CDwnBindData@@AEAAXXZ; CDwnBindData::BufferData(void)
0x1804e4287  jmp     loc_1804E410D
0x1804e428c  mov     rcx, [rbx+28h]; this
0x1804e4290  call    ?AddToPrivacyList@CDwnBindData@@QEAAXXZ; CDwnBindData::AddToPrivacyList(void)
0x1804e4295  mov     rax, [rbx]
0x1804e4298  mov     rcx, rbx
0x1804e429b  mov     rax, [rax+38h]
0x1804e429f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e42a4  mov     ebp, eax
0x1804e42a6  test    eax, eax
0x1804e42a8  jz      loc_1804E417D
0x1804e42ae  jmp     loc_1804E419E
0x1804e42b3  mov     rax, [rbx]
0x1804e42b6  mov     rcx, rbx
0x1804e42b9  mov     rdx, [rbx+28h]
0x1804e42bd  mov     rax, [rax+40h]
0x1804e42c1  mov     rdx, [rdx+1C8h]
0x1804e42c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e42cd  mov     ebp, eax
0x1804e42cf  test    eax, eax
0x1804e42d1  jz      loc_1804E4187
0x1804e42d7  jmp     loc_1804E419E
0x1804e42dc  mov     rdx, [rbx+28h]
0x1804e42e0  mov     rcx, rbx
0x1804e42e3  mov     rax, [rbx]
0x1804e42e6  mov     r8, [rdx+210h]
0x1804e42ed  mov     rdx, [rdx+200h]
0x1804e42f4  mov     rax, [rax+30h]
0x1804e42f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e42fd  mov     ebp, eax
0x1804e42ff  test    eax, eax
0x1804e4301  jnz     loc_1804E419E
0x1804e4307  jmp     loc_1804E4173
0x1804e430c  cmp     dword ptr [rbx+5Ch], 0
0x1804e4310  jnz     loc_1804E41AC
0x1804e4316  mov     rcx, [rbx+28h]; this
0x1804e431a  mov     dword ptr [rbx+5Ch], 1
0x1804e4321  call    ?Disconnect@CDwnBindData@@QEAAXXZ; CDwnBindData::Disconnect(void)
0x1804e4326  mov     rcx, [rbx+28h]; this
0x1804e432a  mov     edx, ebp; int
0x1804e432c  call    ?Terminate@CDwnBindData@@QEAAXJ@Z; CDwnBindData::Terminate(long)
0x1804e4331  jmp     loc_1804E41AC
```
