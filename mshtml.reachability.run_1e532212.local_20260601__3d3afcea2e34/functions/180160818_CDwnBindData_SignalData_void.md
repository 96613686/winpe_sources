# CDwnBindData::SignalData(void)

- ea: `0x180160818`
- end: `0x180160b95`
- name: `?SignalData@CDwnBindData@@AEAAXXZ`
- size: `893`
- prototype: `void __fastcall(CDwnBindData *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18015ea98`
- `0x180161610`
- `0x1801649d0`
- `0x180164bc0`
- `0x18072c480`

## callees

- `0x180157fdc`
- `0x18015c1c8`
- `0x180160818`
- `0x180160b9c`
- `0x180626970`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180160a98`
- `msvcrt!memcpy_s` at `0x180160a98`
- `KERNEL32!GetCurrentThreadId` at `0x18016090e`
- `KERNEL32!GetCurrentThreadId` at `0x18016090e`
- `KERNEL32!LeaveCriticalSection` at `0x180160895`
- `KERNEL32!LeaveCriticalSection` at `0x180160895`
- `KERNEL32!EnterCriticalSection` at `0x180160872`
- `KERNEL32!EnterCriticalSection` at `0x180160872`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180160944`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180160953`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180160963`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180160973`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180160a42`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180160a52`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180160944`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180160953`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180160963`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180160973`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180160a42`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180160a52`

## pseudocode

```c
void __fastcall CDwnBindData::SignalData(CDwnBindData *this)
{
  __int16 v2; // bp
  __int64 v3; // rdi
  __int16 v4; // si
  bool v5; // zf
  DWORD CurrentThreadId; // eax
  __int128 v7; // xmm6
  __int128 v8; // xmm7
  char v9; // r15
  struct IE_GLOBAL_THREAD_STATE *v10; // rax
  int v11; // ebp
  const void *v12; // r8
  CDwnBindData *v13; // rcx
  _BYTE v14[8]; // [rsp+20h] [rbp-78h] BYREF
  __int64 Destination; // [rsp+28h] [rbp-70h] BYREF
  int v16; // [rsp+30h] [rbp-68h]

  if ( *((_BYTE *)this + 792) && *((_QWORD *)this + 50) )
    CDwnBindData::BufferData(this);
  v2 = 32;
  _InterlockedIncrement((volatile signed __int32 *)this + 5);
  while ( 1 )
  {
    v3 = 0;
    LOBYTE(v4) = 0;
    EnterCriticalSection(&g_csDwnBindSig);
    *((_WORD *)this + 218) |= v2;
    if ( *((_QWORD *)this + 56) )
    {
      v5 = ((unsigned __int16)v2 | *((_WORD *)this + 219)) == 0;
      *((_WORD *)this + 219) |= v2;
      if ( !v5 && !*((_DWORD *)this + 110) )
      {
        v4 = *((_WORD *)this + 219);
        *((_WORD *)this + 219) = 0;
        CurrentThreadId = GetCurrentThreadId();
        v3 = *((_QWORD *)this + 56);
        *((_DWORD *)this + 110) = CurrentThreadId;
        _InterlockedIncrement((volatile signed __int32 *)(v3 + 20));
      }
    }
    LeaveCriticalSection(&g_csDwnBindSig);
    if ( !v3 )
      break;
    if ( !*((_BYTE *)this + 792) && *((_QWORD *)this + 50) && (v4 & 0x20) != 0 )
      CDwnBindData::BufferData(this);
    v7 = *(_OWORD *)((char *)this + 1080);
    v8 = *(_OWORD *)GlobalThreadState();
    v9 = *((_BYTE *)GlobalThreadState() + 16);
    *(_OWORD *)GlobalThreadState() = v7;
    v10 = GlobalThreadState();
    v14[0] = 0;
    *((_BYTE *)v10 + 16) = 1;
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v3 + 24LL))(v3, v14);
    if ( !v14[0] )
    {
      if ( (v4 & 1) != 0 )
      {
        v12 = (const void *)(*(_QWORD *)(v3 + 40) + 424LL);
        Destination = 0;
        v16 = 0;
        memcpy_s(&Destination, 0xCu, v12, 0xCu);
        v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 40LL))(v3, &Destination);
        if ( v11 )
          goto LABEL_21;
      }
      if ( (v4 & 2) != 0
        && (v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 48LL))(
                    v3,
                    *(_QWORD *)(*(_QWORD *)(v3 + 40) + 512LL),
                    *(_QWORD *)(*(_QWORD *)(v3 + 40) + 528LL))) != 0
        || (v4 & 8) != 0
        && (CDwnBindData::AddToPrivacyList(*(CDwnBindData **)(v3 + 40)),
            (v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 56LL))(v3)) != 0)
        || (v4 & 0x10) != 0
        && (v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 64LL))(
                    v3,
                    *(_QWORD *)(*(_QWORD *)(v3 + 40) + 456LL))) != 0 )
      {
LABEL_21:
        if ( v11 >= 0 )
          goto LABEL_22;
        if ( !*(_DWORD *)(v3 + 92) )
        {
          v13 = *(CDwnBindData **)(v3 + 40);
          *(_DWORD *)(v3 + 92) = 1;
          CDwnBindData::Disconnect(v13);
          CDwnBindData::Terminate(*(CDwnBindData **)(v3 + 40), v11);
        }
        goto LABEL_23;
      }
      if ( (v4 & 0x20) != 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 72LL))(v3);
        goto LABEL_21;
      }
LABEL_22:
      if ( (v4 & 0x40) != 0 )
LABEL_23:
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 80LL))(
          v3,
          *(unsigned int *)(*(_QWORD *)(v3 + 40) + 756LL));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 32LL))(v3);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 20), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
    *(_OWORD *)GlobalThreadState() = v8;
    v2 = 0;
    *((_BYTE *)GlobalThreadState() + 16) = v9;
    *((_DWORD *)this + 110) = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 5, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(CDwnBindData *, __int64))this)(this, 1);
}

```

## disassembly

```asm
0x180160818  push    rbx
0x18016081a  push    rbp
0x18016081b  push    rsi
0x18016081c  push    rdi
0x18016081d  push    r14
0x18016081f  push    r15
0x180160821  sub     rsp, 68h
0x180160825  movaps  [rsp+98h+var_48], xmm6
0x18016082a  movaps  [rsp+98h+var_58], xmm7
0x18016082f  mov     rax, cs:__security_cookie
0x180160836  xor     rax, rsp
0x180160839  mov     [rsp+98h+var_60], rax
0x18016083e  cmp     byte ptr [rcx+318h], 0
0x180160845  mov     rbx, rcx
0x180160848  jz      short loc_180160859
0x18016084a  cmp     qword ptr [rcx+190h], 0
0x180160852  jz      short loc_180160859
0x180160854  call    ?BufferData@CDwnBindData@@AEAAXXZ; CDwnBindData::BufferData(void)
0x180160859  mov     r14d, 20h ; ' '
0x18016085f  movzx   ebp, r14w
0x180160863  lock inc dword ptr [rbx+14h]
0x180160867  lea     rcx, ?g_csDwnBindSig@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x18016086e  xor     edi, edi
0x180160870  xor     esi, esi
0x180160872  call    cs:__imp_EnterCriticalSection
0x180160879  nop     dword ptr [rax+rax+00h]
0x18016087e  or      [rbx+1B4h], bp
0x180160885  cmp     [rbx+1C0h], rsi
0x18016088c  jnz     short loc_1801608ED
0x18016088e  lea     rcx, ?g_csDwnBindSig@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x180160895  call    cs:__imp_LeaveCriticalSection
0x18016089c  nop     dword ptr [rax+rax+00h]
0x1801608a1  test    rdi, rdi
0x1801608a4  jnz     loc_180160930
0x1801608aa  or      eax, 0FFFFFFFFh
0x1801608ad  lock xadd [rbx+14h], eax
0x1801608b2  cmp     eax, 1
0x1801608b5  jnz     short loc_1801608C8
0x1801608b7  mov     rax, [rbx]
0x1801608ba  lea     edx, [rdi+1]
0x1801608bd  mov     rcx, rbx
0x1801608c0  mov     rax, [rax]
0x1801608c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801608c8  mov     rcx, [rsp+98h+var_60]
0x1801608cd  xor     rcx, rsp; StackCookie
0x1801608d0  call    __security_check_cookie
0x1801608d5  movaps  xmm6, [rsp+98h+var_48]
0x1801608da  movaps  xmm7, [rsp+98h+var_58]
0x1801608df  add     rsp, 68h
0x1801608e3  pop     r15
0x1801608e5  pop     r14
0x1801608e7  pop     rdi
0x1801608e8  pop     rsi
0x1801608e9  pop     rbp
0x1801608ea  pop     rbx
0x1801608eb  retn
0x1801608ed  or      [rbx+1B6h], bp
0x1801608f4  jz      short loc_18016088E
0x1801608f6  mov     eax, [rbx+1B8h]
0x1801608fc  test    eax, eax
0x1801608fe  jnz     short loc_18016088E
0x180160900  movzx   esi, word ptr [rbx+1B6h]
0x180160907  mov     [rbx+1B6h], ax
0x18016090e  call    cs:__imp_GetCurrentThreadId
0x180160915  nop     dword ptr [rax+rax+00h]
0x18016091a  mov     rdi, [rbx+1C0h]
0x180160921  mov     [rbx+1B8h], eax
0x180160927  lock inc dword ptr [rdi+14h]
0x18016092b  jmp     loc_18016088E
0x180160930  cmp     byte ptr [rbx+318h], 0
0x180160937  jz      loc_180160AC7
0x18016093d  movups  xmm6, xmmword ptr [rbx+438h]
0x180160944  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18016094b  nop     dword ptr [rax+rax+00h]
0x180160950  movups  xmm7, xmmword ptr [rax]
0x180160953  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18016095a  nop     dword ptr [rax+rax+00h]
0x18016095f  mov     r15b, [rax+10h]
0x180160963  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18016096a  nop     dword ptr [rax+rax+00h]
0x18016096f  movdqu  xmmword ptr [rax], xmm6
0x180160973  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18016097a  nop     dword ptr [rax+rax+00h]
0x18016097f  lea     rdx, [rsp+98h+var_78]
0x180160984  mov     [rsp+98h+var_78], 0
0x180160989  mov     rcx, rdi
0x18016098c  mov     byte ptr [rax+10h], 1
0x180160990  mov     rax, [rdi]
0x180160993  mov     rax, [rax+18h]
0x180160997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016099c  cmp     [rsp+98h+var_78], 0
0x1801609a1  jnz     short loc_180160A22
0x1801609a3  movzx   r14d, si
0x1801609a7  test    sil, 1
0x1801609ab  jnz     loc_180160A73
0x1801609b1  test    sil, 2
0x1801609b5  jnz     loc_180160B3B
0x1801609bb  test    sil, 8
0x1801609bf  jnz     loc_180160AEB
0x1801609c5  test    sil, 10h
0x1801609c9  jnz     loc_180160B12
0x1801609cf  test    sil, 20h
0x1801609d3  jz      short loc_1801609EE
0x1801609d5  mov     rax, [rdi]
0x1801609d8  mov     rcx, rdi
0x1801609db  mov     rax, [rax+48h]
0x1801609df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801609e4  mov     ebp, eax
0x1801609e6  test    ebp, ebp
0x1801609e8  js      loc_180160B6B
0x1801609ee  test    r14b, 40h
0x1801609f2  jz      short loc_180160A0D
0x1801609f4  mov     rax, [rdi]
0x1801609f7  mov     rcx, rdi
0x1801609fa  mov     rdx, [rdi+28h]
0x1801609fe  mov     rax, [rax+50h]
0x180160a02  mov     edx, [rdx+2F4h]
0x180160a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160a0d  mov     rax, [rdi]
0x180160a10  mov     rcx, rdi
0x180160a13  mov     rax, [rax+20h]
0x180160a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160a1c  mov     r14d, 20h ; ' '
0x180160a22  or      eax, 0FFFFFFFFh
0x180160a25  lock xadd [rdi+14h], eax
0x180160a2a  cmp     eax, 1
0x180160a2d  jnz     short loc_180160A42
0x180160a2f  mov     rax, [rdi]
0x180160a32  mov     edx, 1
0x180160a37  mov     rcx, rdi
0x180160a3a  mov     rax, [rax]
0x180160a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160a42  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180160a49  nop     dword ptr [rax+rax+00h]
0x180160a4e  movdqu  xmmword ptr [rax], xmm7
0x180160a52  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180160a59  nop     dword ptr [rax+rax+00h]
0x180160a5e  xor     ebp, ebp
0x180160a60  mov     [rax+10h], r15b
0x180160a64  mov     dword ptr [rbx+1B8h], 0
0x180160a6e  jmp     loc_180160867
0x180160a73  mov     r8, [rdi+28h]
0x180160a77  lea     rcx, [rsp+98h+Destination]; Destination
0x180160a7c  xor     eax, eax
0x180160a7e  add     r8, 1A8h; Source
0x180160a85  mov     [rsp+98h+Destination], rax
0x180160a8a  mov     [rsp+98h+var_68], eax
0x180160a8e  mov     eax, 0Ch
0x180160a93  mov     r9d, eax; SourceSize
0x180160a96  mov     edx, eax; DestinationSize
0x180160a98  call    cs:__imp_memcpy_s
0x180160a9f  nop     dword ptr [rax+rax+00h]
0x180160aa4  mov     rax, [rdi]
0x180160aa7  lea     rdx, [rsp+98h+Destination]
0x180160aac  mov     rcx, rdi
0x180160aaf  mov     rax, [rax+28h]
0x180160ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160ab8  mov     ebp, eax
0x180160aba  test    eax, eax
0x180160abc  jz      loc_1801609B1
0x180160ac2  jmp     loc_1801609E6
0x180160ac7  cmp     qword ptr [rbx+190h], 0
0x180160acf  jz      loc_18016093D
0x180160ad5  test    r14b, sil
0x180160ad8  jz      loc_18016093D
0x180160ade  mov     rcx, rbx; this
0x180160ae1  call    ?BufferData@CDwnBindData@@AEAAXXZ; CDwnBindData::BufferData(void)
0x180160ae6  jmp     loc_18016093D
0x180160aeb  mov     rcx, [rdi+28h]; this
0x180160aef  call    ?AddToPrivacyList@CDwnBindData@@QEAAXXZ; CDwnBindData::AddToPrivacyList(void)
0x180160af4  mov     rax, [rdi]
0x180160af7  mov     rcx, rdi
0x180160afa  mov     rax, [rax+38h]
0x180160afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160b03  mov     ebp, eax
0x180160b05  test    eax, eax
0x180160b07  jz      loc_1801609C5
0x180160b0d  jmp     loc_1801609E6
0x180160b12  mov     rax, [rdi]
0x180160b15  mov     rcx, rdi
0x180160b18  mov     rdx, [rdi+28h]
0x180160b1c  mov     rax, [rax+40h]
0x180160b20  mov     rdx, [rdx+1C8h]
0x180160b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160b2c  mov     ebp, eax
0x180160b2e  test    eax, eax
0x180160b30  jz      loc_1801609CF
0x180160b36  jmp     loc_1801609E6
0x180160b3b  mov     rdx, [rdi+28h]
0x180160b3f  mov     rcx, rdi
0x180160b42  mov     rax, [rdi]
0x180160b45  mov     r8, [rdx+210h]
0x180160b4c  mov     rdx, [rdx+200h]
0x180160b53  mov     rax, [rax+30h]
0x180160b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160b5c  mov     ebp, eax
0x180160b5e  test    eax, eax
0x180160b60  jnz     loc_1801609E6
0x180160b66  jmp     loc_1801609BB
0x180160b6b  cmp     dword ptr [rdi+5Ch], 0
0x180160b6f  jnz     loc_1801609F4
0x180160b75  mov     rcx, [rdi+28h]; this
0x180160b79  mov     dword ptr [rdi+5Ch], 1
0x180160b80  call    ?Disconnect@CDwnBindData@@QEAAXXZ; CDwnBindData::Disconnect(void)
0x180160b85  mov     rcx, [rdi+28h]; this
0x180160b89  mov     edx, ebp; int
0x180160b8b  call    ?Terminate@CDwnBindData@@QEAAXJ@Z; CDwnBindData::Terminate(long)
0x180160b90  jmp     loc_1801609F4
```
