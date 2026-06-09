# CDwnBindData::Signal(ushort)

- ea: `0x18015b408`
- end: `0x18015b77b`
- name: `?Signal@CDwnBindData@@AEAAXG@Z`
- size: `883`
- prototype: `void __fastcall(CDwnBindData *__hidden this, unsigned __int16)`
- caller_count: `8`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18015ad1c`
- `0x18015b784`
- `0x1801621d0`
- `0x1801649d0`
- `0x180164bc0`
- `0x1801667b8`
- `0x1803ff520`
- `0x180412a00`

## callees

- `0x180157fdc`
- `0x18015b408`
- `0x18015c1c8`
- `0x180160b9c`
- `0x180626970`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18015b67d`
- `msvcrt!memcpy_s` at `0x18015b67d`
- `KERNEL32!GetCurrentThreadId` at `0x18015b4f9`
- `KERNEL32!GetCurrentThreadId` at `0x18015b4f9`
- `KERNEL32!LeaveCriticalSection` at `0x18015b480`
- `KERNEL32!LeaveCriticalSection` at `0x18015b480`
- `KERNEL32!EnterCriticalSection` at `0x18015b443`
- `KERNEL32!EnterCriticalSection` at `0x18015b443`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18015b52f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18015b53e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18015b54e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18015b55e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18015b627`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18015b637`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18015b52f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18015b53e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18015b54e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18015b55e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18015b627`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18015b637`

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
0x18015b408  push    rbx
0x18015b40a  push    rbp
0x18015b40b  push    rsi
0x18015b40c  push    rdi
0x18015b40d  push    r14
0x18015b40f  push    r15
0x18015b411  sub     rsp, 68h
0x18015b415  movaps  [rsp+98h+var_48], xmm6
0x18015b41a  movaps  [rsp+98h+var_58], xmm7
0x18015b41f  mov     rax, cs:__security_cookie
0x18015b426  xor     rax, rsp
0x18015b429  mov     [rsp+98h+var_60], rax
0x18015b42e  movzx   ebp, dx
0x18015b431  mov     rdi, rcx
0x18015b434  lock inc dword ptr [rcx+14h]
0x18015b438  lea     rcx, ?g_csDwnBindSig@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x18015b43f  xor     ebx, ebx
0x18015b441  xor     esi, esi
0x18015b443  call    cs:__imp_EnterCriticalSection
0x18015b44a  nop     dword ptr [rax+rax+00h]
0x18015b44f  movzx   ecx, word ptr [rdi+1B4h]
0x18015b456  movzx   edx, cx
0x18015b459  and     dx, 40h
0x18015b45d  not     dx
0x18015b460  and     dx, bp
0x18015b463  movzx   eax, dx
0x18015b466  or      ax, cx
0x18015b469  mov     [rdi+1B4h], ax
0x18015b470  cmp     [rdi+1C0h], rbx
0x18015b477  jnz     short loc_18015B4D8
0x18015b479  lea     rcx, ?g_csDwnBindSig@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x18015b480  call    cs:__imp_LeaveCriticalSection
0x18015b487  nop     dword ptr [rax+rax+00h]
0x18015b48c  test    rbx, rbx
0x18015b48f  jnz     loc_18015B51B
0x18015b495  or      eax, 0FFFFFFFFh
0x18015b498  lock xadd [rdi+14h], eax
0x18015b49d  cmp     eax, 1
0x18015b4a0  jnz     short loc_18015B4B3
0x18015b4a2  mov     rax, [rdi]
0x18015b4a5  lea     edx, [rbx+1]
0x18015b4a8  mov     rcx, rdi
0x18015b4ab  mov     rax, [rax]
0x18015b4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b4b3  mov     rcx, [rsp+98h+var_60]
0x18015b4b8  xor     rcx, rsp; StackCookie
0x18015b4bb  call    __security_check_cookie
0x18015b4c0  movaps  xmm6, [rsp+98h+var_48]
0x18015b4c5  movaps  xmm7, [rsp+98h+var_58]
0x18015b4ca  add     rsp, 68h
0x18015b4ce  pop     r15
0x18015b4d0  pop     r14
0x18015b4d2  pop     rdi
0x18015b4d3  pop     rsi
0x18015b4d4  pop     rbp
0x18015b4d5  pop     rbx
0x18015b4d6  retn
0x18015b4d8  or      [rdi+1B6h], dx
0x18015b4df  jz      short loc_18015B479
0x18015b4e1  mov     eax, [rdi+1B8h]
0x18015b4e7  test    eax, eax
0x18015b4e9  jnz     short loc_18015B479
0x18015b4eb  movzx   esi, word ptr [rdi+1B6h]
0x18015b4f2  mov     [rdi+1B6h], ax
0x18015b4f9  call    cs:__imp_GetCurrentThreadId
0x18015b500  nop     dword ptr [rax+rax+00h]
0x18015b505  mov     rbx, [rdi+1C0h]
0x18015b50c  mov     [rdi+1B8h], eax
0x18015b512  lock inc dword ptr [rbx+14h]
0x18015b516  jmp     loc_18015B479
0x18015b51b  cmp     byte ptr [rdi+318h], 0
0x18015b522  jz      loc_18015B6AC
0x18015b528  movups  xmm6, xmmword ptr [rdi+438h]
0x18015b52f  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18015b536  nop     dword ptr [rax+rax+00h]
0x18015b53b  movups  xmm7, xmmword ptr [rax]
0x18015b53e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18015b545  nop     dword ptr [rax+rax+00h]
0x18015b54a  mov     r15b, [rax+10h]
0x18015b54e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18015b555  nop     dword ptr [rax+rax+00h]
0x18015b55a  movdqu  xmmword ptr [rax], xmm6
0x18015b55e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18015b565  nop     dword ptr [rax+rax+00h]
0x18015b56a  lea     rdx, [rsp+98h+var_78]
0x18015b56f  mov     [rsp+98h+var_78], 0
0x18015b574  mov     rcx, rbx
0x18015b577  mov     byte ptr [rax+10h], 1
0x18015b57b  mov     rax, [rbx]
0x18015b57e  mov     rax, [rax+18h]
0x18015b582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b587  cmp     [rsp+98h+var_78], 0
0x18015b58c  jnz     short loc_18015B607
0x18015b58e  movzx   r14d, si
0x18015b592  test    sil, 1
0x18015b596  jnz     loc_18015B658
0x18015b59c  test    sil, 2
0x18015b5a0  jnz     loc_18015B721
0x18015b5a6  test    sil, 8
0x18015b5aa  jnz     loc_18015B6D1
0x18015b5b0  test    sil, 10h
0x18015b5b4  jnz     loc_18015B6F8
0x18015b5ba  test    sil, 20h
0x18015b5be  jz      short loc_18015B5D9
0x18015b5c0  mov     rax, [rbx]
0x18015b5c3  mov     rcx, rbx
0x18015b5c6  mov     rax, [rax+48h]
0x18015b5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b5cf  mov     ebp, eax
0x18015b5d1  test    ebp, ebp
0x18015b5d3  js      loc_18015B751
0x18015b5d9  test    r14b, 40h
0x18015b5dd  jz      short loc_18015B5F8
0x18015b5df  mov     rax, [rbx]
0x18015b5e2  mov     rcx, rbx
0x18015b5e5  mov     rdx, [rbx+28h]
0x18015b5e9  mov     rax, [rax+50h]
0x18015b5ed  mov     edx, [rdx+2F4h]
0x18015b5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b5f8  mov     rax, [rbx]
0x18015b5fb  mov     rcx, rbx
0x18015b5fe  mov     rax, [rax+20h]
0x18015b602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b607  or      eax, 0FFFFFFFFh
0x18015b60a  lock xadd [rbx+14h], eax
0x18015b60f  cmp     eax, 1
0x18015b612  jnz     short loc_18015B627
0x18015b614  mov     rax, [rbx]
0x18015b617  mov     edx, 1
0x18015b61c  mov     rcx, rbx
0x18015b61f  mov     rax, [rax]
0x18015b622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b627  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18015b62e  nop     dword ptr [rax+rax+00h]
0x18015b633  movdqu  xmmword ptr [rax], xmm7
0x18015b637  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18015b63e  nop     dword ptr [rax+rax+00h]
0x18015b643  xor     ebp, ebp
0x18015b645  mov     [rax+10h], r15b
0x18015b649  mov     dword ptr [rdi+1B8h], 0
0x18015b653  jmp     loc_18015B438
0x18015b658  mov     r8, [rbx+28h]
0x18015b65c  lea     rcx, [rsp+98h+Destination]; Destination
0x18015b661  xor     eax, eax
0x18015b663  add     r8, 1A8h; Source
0x18015b66a  mov     [rsp+98h+Destination], rax
0x18015b66f  mov     [rsp+98h+var_68], eax
0x18015b673  mov     eax, 0Ch
0x18015b678  mov     r9d, eax; SourceSize
0x18015b67b  mov     edx, eax; DestinationSize
0x18015b67d  call    cs:__imp_memcpy_s
0x18015b684  nop     dword ptr [rax+rax+00h]
0x18015b689  mov     rax, [rbx]
0x18015b68c  lea     rdx, [rsp+98h+Destination]
0x18015b691  mov     rcx, rbx
0x18015b694  mov     rax, [rax+28h]
0x18015b698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b69d  mov     ebp, eax
0x18015b69f  test    eax, eax
0x18015b6a1  jz      loc_18015B59C
0x18015b6a7  jmp     loc_18015B5D1
0x18015b6ac  cmp     qword ptr [rdi+190h], 0
0x18015b6b4  jz      loc_18015B528
0x18015b6ba  test    sil, 20h
0x18015b6be  jz      loc_18015B528
0x18015b6c4  mov     rcx, rdi; this
0x18015b6c7  call    ?BufferData@CDwnBindData@@AEAAXXZ; CDwnBindData::BufferData(void)
0x18015b6cc  jmp     loc_18015B528
0x18015b6d1  mov     rcx, [rbx+28h]; this
0x18015b6d5  call    ?AddToPrivacyList@CDwnBindData@@QEAAXXZ; CDwnBindData::AddToPrivacyList(void)
0x18015b6da  mov     rax, [rbx]
0x18015b6dd  mov     rcx, rbx
0x18015b6e0  mov     rax, [rax+38h]
0x18015b6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b6e9  mov     ebp, eax
0x18015b6eb  test    eax, eax
0x18015b6ed  jz      loc_18015B5B0
0x18015b6f3  jmp     loc_18015B5D1
0x18015b6f8  mov     rax, [rbx]
0x18015b6fb  mov     rcx, rbx
0x18015b6fe  mov     rdx, [rbx+28h]
0x18015b702  mov     rax, [rax+40h]
0x18015b706  mov     rdx, [rdx+1C8h]
0x18015b70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b712  mov     ebp, eax
0x18015b714  test    eax, eax
0x18015b716  jz      loc_18015B5BA
0x18015b71c  jmp     loc_18015B5D1
0x18015b721  mov     rdx, [rbx+28h]
0x18015b725  mov     rcx, rbx
0x18015b728  mov     rax, [rbx]
0x18015b72b  mov     r8, [rdx+210h]
0x18015b732  mov     rdx, [rdx+200h]
0x18015b739  mov     rax, [rax+30h]
0x18015b73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b742  mov     ebp, eax
0x18015b744  test    eax, eax
0x18015b746  jnz     loc_18015B5D1
0x18015b74c  jmp     loc_18015B5A6
0x18015b751  cmp     dword ptr [rbx+5Ch], 0
0x18015b755  jnz     loc_18015B5DF
0x18015b75b  mov     rcx, [rbx+28h]; this
0x18015b75f  mov     dword ptr [rbx+5Ch], 1
0x18015b766  call    ?Disconnect@CDwnBindData@@QEAAXXZ; CDwnBindData::Disconnect(void)
0x18015b76b  mov     rcx, [rbx+28h]; this
0x18015b76f  mov     edx, ebp; int
0x18015b771  call    ?Terminate@CDwnBindData@@QEAAXJ@Z; CDwnBindData::Terminate(long)
0x18015b776  jmp     loc_18015B5DF
```
