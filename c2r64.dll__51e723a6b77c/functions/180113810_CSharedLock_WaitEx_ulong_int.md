# CSharedLock::WaitEx(ulong,int)

- ea: `0x180113810`
- end: `0x180113a24`
- name: `?WaitEx@CSharedLock@@QEAAKKH@Z`
- size: `532`
- prototype: `unsigned int __fastcall(CSharedLock *__hidden this, unsigned int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180112d60`
- `0x1801137f0`
- `0x180113800`

## callees

- `0x1800264b4`
- `0x18003e690`
- `0x180110a34`
- `0x180113810`
- `0x180113bd0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180113832`
- `KERNEL32!GetCurrentThreadId` at `0x180113832`
- `KERNEL32!GetTickCount` at `0x180113954`
- `KERNEL32!GetTickCount` at `0x180113961`
- `KERNEL32!GetTickCount` at `0x180113954`
- `KERNEL32!GetTickCount` at `0x180113961`

## pseudocode

```c
__int64 __fastcall CSharedLock::WaitEx(CSharedLock *this, unsigned int a2, unsigned int a3)
{
  DWORD CurrentThreadId; // r15d
  _DWORD *v7; // rcx
  DWORD v9; // r14d
  char v10; // bp
  signed __int32 *v11; // roff
  signed __int32 v12; // ecx
  signed __int32 v13; // eax
  int v14; // edx
  int v15; // edi
  char v16; // r9
  unsigned int v17; // edx
  _DWORD *v18; // rax
  DWORD TickCount; // eax
  unsigned __int32 *v20; // roff
  unsigned __int32 v21; // eax
  unsigned __int32 v22; // ett
  __int128 i; // [rsp+30h] [rbp-58h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  if ( CurrentThreadId == *(_DWORD *)(*((_QWORD *)this + 2) + 4LL)
    && (v7 = (_DWORD *)*((_QWORD *)this + 2), (*v7 & 0x7FF) == *((_DWORD *)this + 10)) )
  {
    ++*(_DWORD *)(*((_QWORD *)this + 2) + 8LL);
    if ( Microsoft_Office_ThreadpoolEnableBits < 0 )
      McTemplateU0pqq_EventWriteTransfer(
        (_DWORD)v7,
        (unsigned int)SharedLockAquire,
        (_DWORD)this,
        *(_DWORD *)(*((_QWORD *)this + 2) + 8LL),
        *(_DWORD *)(*((_QWORD *)this + 2) + 12LL));
    return 0;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    for ( i = 0; ; CSharedLock::WaitForLockEventWrapper(this, (struct CSharedLock::CWaitData *)&i) )
    {
      v11 = (signed __int32 *)*((_QWORD *)this + 2);
      _m_prefetchw(v11);
      v12 = *v11;
      do
      {
        v13 = v12;
        v14 = v12 & 0x7FF;
        if ( v14 == 2043 || (v15 = 0, (v12 & 0x7FF) == 0) )
        {
          v16 = 1;
          v15 = v14 == 2043;
          v17 = v12 ^ (*((_DWORD *)this + 10) ^ v12) & 0x7FF;
          v12 = v17;
          if ( v10 )
            v12 = v17 & 0x7FF | (((v17 >> 11) - 1) << 11);
        }
        else
        {
          v16 = 0;
          LODWORD(i) = v12 & 0x7FF;
          if ( !v10 )
            v12 += 2048;
        }
        v12 = _InterlockedCompareExchange(*((volatile signed __int32 **)this + 2), v12, v13);
      }
      while ( v13 != v12 );
      v18 = (_DWORD *)*((_QWORD *)this + 2);
      if ( v16 )
        break;
      if ( (*v18 & 0xFFFFF800) >= 0x28F5800 )
        MsoShipAssertTagProc(507556117);
      if ( a2 != -1 )
      {
        if ( v10 || (v9 = GetTickCount(), !a2) )
        {
          TickCount = GetTickCount();
          if ( TickCount - v9 >= a2 )
          {
            v20 = (unsigned __int32 *)*((_QWORD *)this + 2);
            _m_prefetchw(v20);
            v21 = *v20;
            do
            {
              v22 = v21;
              v21 = _InterlockedCompareExchange(
                      *((volatile signed __int32 **)this + 2),
                      v21 & 0x7FF | (((v21 >> 11) - 1) << 11),
                      v21);
            }
            while ( v22 != v21 );
            return 258;
          }
          a2 -= TickCount - v9;
          v9 = TickCount;
        }
      }
      *(_QWORD *)((char *)&i + 4) = __PAIR64__(a3, a2);
      v10 = 1;
    }
    v18[1] = CurrentThreadId;
    *(_DWORD *)(*((_QWORD *)this + 2) + 8LL) = 1;
    if ( Microsoft_Office_ThreadpoolEnableBits < 0 )
      McTemplateU0pqq_EventWriteTransfer(
        *(_DWORD *)(*((_QWORD *)this + 2) + 12LL),
        (unsigned int)SharedLockAquire,
        (_DWORD)this,
        *(_DWORD *)(*((_QWORD *)this + 2) + 8LL),
        *(_DWORD *)(*((_QWORD *)this + 2) + 12LL));
    return (unsigned int)(v15 << 7);
  }
}

```

## disassembly

```asm
0x180113810  push    rbx
0x180113812  push    rsi
0x180113813  push    r12
0x180113815  push    r15
0x180113817  sub     rsp, 68h
0x18011381b  mov     rax, cs:__security_cookie
0x180113822  xor     rax, rsp
0x180113825  mov     [rsp+88h+var_48], rax
0x18011382a  mov     r12d, r8d
0x18011382d  mov     esi, edx
0x18011382f  mov     rbx, rcx
0x180113832  call    cs:__imp_GetCurrentThreadId
0x180113838  mov     rcx, [rbx+10h]
0x18011383c  mov     r15d, eax
0x18011383f  mov     r8d, [rcx+4]
0x180113843  cmp     eax, r8d
0x180113846  jnz     short loc_180113894
0x180113848  mov     rcx, [rbx+10h]
0x18011384c  mov     r9d, [rbx+28h]
0x180113850  mov     edx, [rcx]
0x180113852  and     edx, 7FFh
0x180113858  cmp     edx, r9d
0x18011385b  jnz     short loc_180113894
0x18011385d  mov     rax, [rbx+10h]
0x180113861  inc     dword ptr [rax+8]
0x180113864  cmp     cs:Microsoft_Office_ThreadpoolEnableBits, 0
0x18011386b  jge     short loc_18011388C
0x18011386d  mov     r9, [rbx+10h]
0x180113871  lea     rdx, SharedLockAquire
0x180113878  mov     r8, rbx
0x18011387b  mov     eax, [r9+0Ch]
0x18011387f  mov     r9d, [r9+8]
0x180113883  mov     [rsp+88h+var_68], eax
0x180113887  call    McTemplateU0pqq_EventWriteTransfer
0x18011388c  xor     eax, eax
0x18011388e  jmp     loc_180113A0C
0x180113894  mov     [rsp+88h+var_28], rbp
0x180113899  xorps   xmm0, xmm0
0x18011389c  mov     [rsp+88h+var_30], rdi
0x1801138a1  mov     [rsp+88h+var_38], r14
0x1801138a6  xor     r14d, r14d
0x1801138a9  xor     bpl, bpl
0x1801138ac  movups  [rsp+88h+var_58], xmm0
0x1801138b1  mov     rcx, [rbx+10h]
0x1801138b5  prefetchw byte ptr [rcx]
0x1801138b8  mov     ecx, [rcx]
0x1801138ba  mov     edx, ecx
0x1801138bc  mov     eax, ecx
0x1801138be  and     edx, 7FFh
0x1801138c4  cmp     edx, 7FBh
0x1801138ca  jz      short loc_1801138E6
0x1801138cc  xor     edi, edi
0x1801138ce  test    edx, edx
0x1801138d0  jz      short loc_1801138E6
0x1801138d2  xor     r9b, r9b
0x1801138d5  mov     dword ptr [rsp+88h+var_58], edx
0x1801138d9  test    bpl, bpl
0x1801138dc  jnz     short loc_180113919
0x1801138de  add     ecx, 800h
0x1801138e4  jmp     short loc_180113919
0x1801138e6  xor     edi, edi
0x1801138e8  mov     r9b, 1
0x1801138eb  cmp     edx, 7FBh
0x1801138f1  mov     edx, ecx
0x1801138f3  setz    dil
0x1801138f7  xor     edx, [rbx+28h]
0x1801138fa  and     edx, 7FFh
0x180113900  xor     edx, ecx
0x180113902  mov     ecx, edx
0x180113904  test    bpl, bpl
0x180113907  jz      short loc_180113919
0x180113909  shr     ecx, 0Bh
0x18011390c  and     edx, 7FFh
0x180113912  dec     ecx
0x180113914  shl     ecx, 0Bh
0x180113917  or      ecx, edx
0x180113919  mov     rdx, [rbx+10h]
0x18011391d  lock cmpxchg [rdx], ecx
0x180113921  mov     ecx, eax
0x180113923  jnz     short loc_1801138BA
0x180113925  mov     rax, [rbx+10h]
0x180113929  test    r9b, r9b
0x18011392c  jnz     loc_1801139C1
0x180113932  mov     eax, [rax]
0x180113934  and     eax, 0FFFFF800h
0x180113939  cmp     eax, 28F5800h
0x18011393e  jb      short loc_18011394A
0x180113940  mov     ecx, 1E40B115h
0x180113945  call    MsoShipAssertTagProc
0x18011394a  cmp     esi, 0FFFFFFFFh
0x18011394d  jz      short loc_180113975
0x18011394f  test    bpl, bpl
0x180113952  jnz     short loc_180113961
0x180113954  call    cs:__imp_GetTickCount
0x18011395a  mov     r14d, eax
0x18011395d  test    esi, esi
0x18011395f  jnz     short loc_180113975
0x180113961  call    cs:__imp_GetTickCount
0x180113967  mov     ecx, eax
0x180113969  sub     ecx, r14d
0x18011396c  cmp     ecx, esi
0x18011396e  jnb     short loc_180113993
0x180113970  sub     esi, ecx
0x180113972  mov     r14d, eax
0x180113975  lea     rdx, [rsp+88h+var_58]; struct CSharedLock::CWaitData *
0x18011397a  mov     dword ptr [rsp+88h+var_58+8], r12d
0x18011397f  mov     rcx, rbx; this
0x180113982  mov     dword ptr [rsp+88h+var_58+4], esi
0x180113986  mov     bpl, 1
0x180113989  call    ?WaitForLockEventWrapper@CSharedLock@@IEAAXPEAUCWaitData@1@@Z; CSharedLock::WaitForLockEventWrapper(CSharedLock::CWaitData *)
0x18011398e  jmp     loc_1801138B1
0x180113993  mov     rax, [rbx+10h]
0x180113997  prefetchw byte ptr [rax]
0x18011399a  mov     eax, [rax]
0x18011399c  mov     edx, eax
0x18011399e  mov     ecx, eax
0x1801139a0  shr     ecx, 0Bh
0x1801139a3  and     edx, 7FFh
0x1801139a9  dec     ecx
0x1801139ab  shl     ecx, 0Bh
0x1801139ae  or      ecx, edx
0x1801139b0  mov     rdx, [rbx+10h]
0x1801139b4  lock cmpxchg [rdx], ecx
0x1801139b8  jnz     short loc_18011399C
0x1801139ba  mov     eax, 102h
0x1801139bf  jmp     short loc_1801139FD
0x1801139c1  mov     [rax+4], r15d
0x1801139c5  mov     rax, [rbx+10h]
0x1801139c9  mov     dword ptr [rax+8], 1
0x1801139d0  cmp     cs:Microsoft_Office_ThreadpoolEnableBits, 0
0x1801139d7  jge     short loc_1801139F8
0x1801139d9  mov     r9, [rbx+10h]
0x1801139dd  lea     rdx, SharedLockAquire
0x1801139e4  mov     r8, rbx
0x1801139e7  mov     ecx, [r9+0Ch]
0x1801139eb  mov     r9d, [r9+8]
0x1801139ef  mov     [rsp+88h+var_68], ecx
0x1801139f3  call    McTemplateU0pqq_EventWriteTransfer
0x1801139f8  shl     edi, 7
0x1801139fb  mov     eax, edi
0x1801139fd  mov     rdi, [rsp+88h+var_30]
0x180113a02  mov     rbp, [rsp+88h+var_28]
0x180113a07  mov     r14, [rsp+88h+var_38]
0x180113a0c  mov     rcx, [rsp+88h+var_48]
0x180113a11  xor     rcx, rsp; StackCookie
0x180113a14  call    __security_check_cookie
0x180113a19  add     rsp, 68h
0x180113a1d  pop     r15
0x180113a1f  pop     r12
0x180113a21  pop     rsi
0x180113a22  pop     rbx
0x180113a23  retn
```
