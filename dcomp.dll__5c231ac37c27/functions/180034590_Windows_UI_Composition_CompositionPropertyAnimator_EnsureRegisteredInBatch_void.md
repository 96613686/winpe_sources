# Windows::UI::Composition::CompositionPropertyAnimator::EnsureRegisteredInBatch(void)

- ea: `0x180034590`
- end: `0x1800348be`
- name: `?EnsureRegisteredInBatch@CompositionPropertyAnimator@Composition@UI@Windows@@MEAAXXZ`
- size: `814`
- prototype: `void __fastcall(Windows::UI::Composition::CompositionPropertyAnimator *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800343c0`
- `0x1800cccd0`

## callees

- `0x180034590`
- `0x1800348d0`
- `0x18009f34c`
- `0x1800ea11c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800345c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034616`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034631`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034675`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800346c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800346e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800347d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003485d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800345c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034616`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034631`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034675`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800346c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800346e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800347d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003485d`

## pseudocode

```c
void __fastcall Windows::UI::Composition::CompositionPropertyAnimator::EnsureRegisteredInBatch(
        Windows::UI::Composition::CompositionPropertyAnimator *this)
{
  __int64 v2; // rdi
  __int64 *v3; // r14
  DWORD CurrentThreadId; // eax
  DWORD v5; // ecx
  __int64 v6; // rdi
  __int64 i; // rax
  int v8; // ebx
  struct Windows::UI::Composition::CompositionBatch *v9; // rsi
  unsigned int v10; // ebx
  DWORD v11; // eax
  __int64 v12; // rcx
  struct Windows::UI::Composition::BatchSet *v13; // rax
  __int64 v14; // rdi
  __int64 *v15; // r14
  DWORD v16; // eax
  DWORD v17; // ecx
  __int64 v18; // rdi
  __int64 k; // rax
  int v20; // ebx
  struct Windows::UI::Composition::CompositionBatch *v21; // rsi
  unsigned int v22; // ebx
  DWORD v23; // eax
  __int64 v24; // rcx
  struct Windows::UI::Composition::BatchSet *v25; // rax
  DWORD v26; // r12d
  _DWORD *v27; // rax
  _DWORD *v28; // rdx
  unsigned int v29; // r8d
  __int64 j; // rcx
  __int64 v31; // rax
  DWORD v32; // r12d
  _DWORD *v33; // rax
  _DWORD *v34; // rdx
  unsigned int v35; // r8d
  __int64 m; // rcx
  __int64 v37; // rax
  struct Windows::UI::Composition::BatchSet *v38; // [rsp+60h] [rbp+40h] BYREF
  struct Windows::UI::Composition::CompositionBatch *v39; // [rsp+68h] [rbp+48h] BYREF

  if ( (*((_BYTE *)this + 168) & 2) == 0 )
  {
    v2 = *((_QWORD *)this + 3);
    v3 = (__int64 *)((char *)this + 216);
    CurrentThreadId = GetCurrentThreadId();
    v5 = CurrentThreadId;
    if ( *v3 || v3[1] )
      goto LABEL_65;
    v6 = v2 + 664;
    if ( CurrentThreadId == *(_DWORD *)(v6 + 64) )
    {
      *v3 = *(_QWORD *)(v6 + 16) | 1LL;
      *(_QWORD *)(v6 + 16) = v3;
    }
    for ( i = *(_QWORD *)(v6 + 32); i; i = *(_QWORD *)(i + 208) )
    {
      if ( *(_DWORD *)(i + 152) == v5 )
        ++*(_DWORD *)(i + 156);
    }
    v8 = *(_DWORD *)(v6 + 64);
    v9 = 0;
    v38 = 0;
    v39 = 0;
    if ( GetCurrentThreadId() == v8 )
    {
      if ( !*(_QWORD *)(v6 + 8) )
      {
        *(_QWORD *)(v6 + 8) = 0;
        v10 = 0;
        v11 = GetCurrentThreadId();
        v12 = *(_QWORD *)(v6 + 32);
        if ( v12 )
        {
          do
          {
            if ( *(_DWORD *)(v12 + 152) == v11 )
            {
              if ( !v9 )
                v9 = (struct Windows::UI::Composition::CompositionBatch *)v12;
              ++v10;
            }
            v12 = *(_QWORD *)(v12 + 208);
          }
          while ( v12 );
          if ( v10 > 1 )
          {
            *(_QWORD *)(v6 + 8) = 0;
            v26 = GetCurrentThreadId();
            v27 = DefaultHeap::Alloc(8LL * (v10 - 1) + 16);
            *(_QWORD *)(v6 + 8) = v27;
            v28 = v27;
            if ( !v27 )
              goto LABEL_65;
            *v27 = 1;
            v29 = 0;
            v27[1] = v10;
            for ( j = *(_QWORD *)(v6 + 32); j; j = *(_QWORD *)(j + 208) )
            {
              if ( *(_DWORD *)(j + 152) == v26 )
              {
                v31 = v29++;
                *(_QWORD *)&v28[2 * v31 + 2] = j;
              }
            }
          }
        }
      }
      v13 = *(struct Windows::UI::Composition::BatchSet **)(v6 + 8);
      if ( !v13 )
        goto LABEL_14;
      ++*(_DWORD *)v13;
    }
    else
    {
      Windows::UI::Composition::BatchController::CreateBatchSet(
        (Windows::UI::Composition::BatchController *)v6,
        &v38,
        &v39);
      v13 = v38;
      v9 = v39;
    }
    if ( v13 )
    {
      v3[1] = (unsigned __int64)v13 | 1;
LABEL_15:
      if ( (*((_BYTE *)this + 168) & 4) == 0 )
      {
LABEL_29:
        *((_BYTE *)this + 168) |= 2u;
        return;
      }
      v14 = *((_QWORD *)this + 3);
      v15 = (__int64 *)((char *)this + 232);
      v16 = GetCurrentThreadId();
      v17 = v16;
      if ( !*((_QWORD *)this + 29) && !*((_QWORD *)this + 30) )
      {
        v18 = v14 + 592;
        if ( v16 == *(_DWORD *)(v18 + 64) )
        {
          *v15 = *(_QWORD *)(v18 + 16) | 1LL;
          *(_QWORD *)(v18 + 16) = v15;
        }
        for ( k = *(_QWORD *)(v18 + 32); k; k = *(_QWORD *)(k + 208) )
        {
          if ( *(_DWORD *)(k + 152) == v17 )
            ++*(_DWORD *)(k + 156);
        }
        v20 = *(_DWORD *)(v18 + 64);
        v21 = 0;
        v38 = 0;
        v39 = 0;
        if ( GetCurrentThreadId() != v20 )
        {
          Windows::UI::Composition::BatchController::CreateBatchSet(
            (Windows::UI::Composition::BatchController *)v18,
            &v38,
            &v39);
          v25 = v38;
          v21 = v39;
          goto LABEL_27;
        }
        if ( *(_QWORD *)(v18 + 8) )
          goto LABEL_25;
        *(_QWORD *)(v18 + 8) = 0;
        v22 = 0;
        v23 = GetCurrentThreadId();
        v24 = *(_QWORD *)(v18 + 32);
        if ( !v24 )
          goto LABEL_25;
        do
        {
          if ( *(_DWORD *)(v24 + 152) == v23 )
          {
            if ( !v21 )
              v21 = (struct Windows::UI::Composition::CompositionBatch *)v24;
            ++v22;
          }
          v24 = *(_QWORD *)(v24 + 208);
        }
        while ( v24 );
        if ( v22 <= 1 )
        {
LABEL_25:
          v25 = *(struct Windows::UI::Composition::BatchSet **)(v18 + 8);
          if ( !v25 )
          {
LABEL_28:
            *((_QWORD *)this + 30) = v21;
            goto LABEL_29;
          }
          ++*(_DWORD *)v25;
LABEL_27:
          if ( v25 )
          {
            *((_QWORD *)this + 30) = (unsigned __int64)v25 | 1;
            goto LABEL_29;
          }
          goto LABEL_28;
        }
        *(_QWORD *)(v18 + 8) = 0;
        v32 = GetCurrentThreadId();
        v33 = DefaultHeap::Alloc(8LL * (v22 - 1) + 16);
        *(_QWORD *)(v18 + 8) = v33;
        v34 = v33;
        if ( v33 )
        {
          *v33 = 1;
          v35 = 0;
          v33[1] = v22;
          for ( m = *(_QWORD *)(v18 + 32); m; m = *(_QWORD *)(m + 208) )
          {
            if ( *(_DWORD *)(m + 152) == v32 )
            {
              v37 = v35++;
              *(_QWORD *)&v34[2 * v37 + 2] = m;
            }
          }
          goto LABEL_25;
        }
      }
LABEL_65:
      Microsoft::WRL2::FailFast::Do();
    }
LABEL_14:
    v3[1] = (__int64)v9;
    goto LABEL_15;
  }
}

```

## disassembly

```asm
0x180034590  mov     [rsp-38h+arg_10], rbx
0x180034595  push    rbp
0x180034596  push    rsi
0x180034597  push    rdi
0x180034598  push    r12
0x18003459a  push    r13
0x18003459c  push    r14
0x18003459e  push    r15
0x1800345a0  mov     rbp, rsp
0x1800345a3  sub     rsp, 20h
0x1800345a7  test    byte ptr [rcx+0A8h], 2
0x1800345ae  mov     r15, rcx
0x1800345b1  jnz     loc_180034710
0x1800345b7  mov     rdi, [rcx+18h]
0x1800345bb  lea     r14, [rcx+0D8h]
0x1800345c2  call    cs:__imp_GetCurrentThreadId
0x1800345c8  xor     r13d, r13d
0x1800345cb  mov     ecx, eax
0x1800345cd  cmp     [r14], r13
0x1800345d0  jnz     loc_1800348B8
0x1800345d6  cmp     [r14+8], r13
0x1800345da  jnz     loc_1800348B8
0x1800345e0  add     rdi, 298h
0x1800345e7  cmp     eax, [rdi+40h]
0x1800345ea  jnz     short loc_1800345FB
0x1800345ec  mov     rax, [rdi+10h]
0x1800345f0  or      rax, 1
0x1800345f4  mov     [r14], rax
0x1800345f7  mov     [rdi+10h], r14
0x1800345fb  mov     rax, [rdi+20h]
0x1800345ff  test    rax, rax
0x180034602  jnz     loc_180034725
0x180034608  mov     ebx, [rdi+40h]
0x18003460b  mov     rsi, r13
0x18003460e  mov     [rbp+arg_0], r13
0x180034612  mov     [rbp+arg_8], r13
0x180034616  call    cs:__imp_GetCurrentThreadId
0x18003461c  cmp     eax, ebx
0x18003461e  jnz     loc_180034770
0x180034624  cmp     [rdi+8], r13
0x180034628  jnz     short loc_180034644
0x18003462a  mov     [rdi+8], r13
0x18003462e  mov     ebx, r13d
0x180034631  call    cs:__imp_GetCurrentThreadId
0x180034637  mov     rcx, [rdi+20h]
0x18003463b  test    rcx, rcx
0x18003463e  jnz     loc_1800347AA
0x180034644  mov     rax, [rdi+8]
0x180034648  test    rax, rax
0x18003464b  jz      short loc_180034658
0x18003464d  inc     dword ptr [rax]
0x18003464f  test    rax, rax
0x180034652  jnz     loc_180034759
0x180034658  mov     [r14+8], rsi
0x18003465c  test    byte ptr [r15+0A8h], 4
0x180034664  jz      loc_180034708
0x18003466a  mov     rdi, [r15+18h]
0x18003466e  lea     r14, [r15+0E8h]
0x180034675  call    cs:__imp_GetCurrentThreadId
0x18003467b  mov     ecx, eax
0x18003467d  cmp     [r14], r13
0x180034680  jnz     loc_1800348B8
0x180034686  cmp     [r14+8], r13
0x18003468a  jnz     loc_1800348B8
0x180034690  add     rdi, 250h
0x180034697  cmp     eax, [rdi+40h]
0x18003469a  jnz     short loc_1800346AB
0x18003469c  mov     rax, [rdi+10h]
0x1800346a0  or      rax, 1
0x1800346a4  mov     [r14], rax
0x1800346a7  mov     [rdi+10h], r14
0x1800346ab  mov     rax, [rdi+20h]
0x1800346af  test    rax, rax
0x1800346b2  jnz     loc_18003473F
0x1800346b8  mov     ebx, [rdi+40h]
0x1800346bb  mov     rsi, r13
0x1800346be  mov     [rbp+arg_0], r13
0x1800346c2  mov     [rbp+arg_8], r13
0x1800346c6  call    cs:__imp_GetCurrentThreadId
0x1800346cc  cmp     eax, ebx
0x1800346ce  jnz     loc_18003478D
0x1800346d4  cmp     [rdi+8], r13
0x1800346d8  jnz     short loc_1800346F4
0x1800346da  mov     [rdi+8], r13
0x1800346de  mov     ebx, r13d
0x1800346e1  call    cs:__imp_GetCurrentThreadId
0x1800346e7  mov     rcx, [rdi+20h]
0x1800346eb  test    rcx, rcx
0x1800346ee  jnz     loc_180034833
0x1800346f4  mov     rax, [rdi+8]
0x1800346f8  test    rax, rax
0x1800346fb  jz      short loc_180034704
0x1800346fd  inc     dword ptr [rax]
0x1800346ff  test    rax, rax
0x180034702  jnz     short loc_180034766
0x180034704  mov     [r14+8], rsi
0x180034708  or      byte ptr [r15+0A8h], 2
0x180034710  mov     rbx, [rsp+20h+arg_10]
0x180034715  add     rsp, 20h
0x180034719  pop     r15
0x18003471b  pop     r14
0x18003471d  pop     r13
0x18003471f  pop     r12
0x180034721  pop     rdi
0x180034722  pop     rsi
0x180034723  pop     rbp
0x180034724  retn
0x180034725  cmp     [rax+98h], ecx
0x18003472b  jnz     short loc_180034733
0x18003472d  inc     dword ptr [rax+9Ch]
0x180034733  mov     rax, [rax+0D0h]
0x18003473a  jmp     loc_1800345FF
0x18003473f  cmp     [rax+98h], ecx
0x180034745  jnz     short loc_18003474D
0x180034747  inc     dword ptr [rax+9Ch]
0x18003474d  mov     rax, [rax+0D0h]
0x180034754  jmp     loc_1800346AF
0x180034759  or      rax, 1
0x18003475d  mov     [r14+8], rax
0x180034761  jmp     loc_18003465C
0x180034766  or      rax, 1
0x18003476a  mov     [r14+8], rax
0x18003476e  jmp     short loc_180034708
0x180034770  lea     r8, [rbp+arg_8]; struct Windows::UI::Composition::CompositionBatch **
0x180034774  mov     rcx, rdi; this
0x180034777  lea     rdx, [rbp+arg_0]; struct Windows::UI::Composition::BatchSet **
0x18003477b  call    ?CreateBatchSet@BatchController@Composition@UI@Windows@@AEAAXPEAPEAUBatchSet@234@PEAPEAVCompositionBatch@234@@Z; Windows::UI::Composition::BatchController::CreateBatchSet(Windows::UI::Composition::BatchSet * *,Windows::UI::Composition::CompositionBatch * *)
0x180034780  mov     rax, [rbp+arg_0]
0x180034784  mov     rsi, [rbp+arg_8]
0x180034788  jmp     loc_18003464F
0x18003478d  lea     r8, [rbp+arg_8]; struct Windows::UI::Composition::CompositionBatch **
0x180034791  mov     rcx, rdi; this
0x180034794  lea     rdx, [rbp+arg_0]; struct Windows::UI::Composition::BatchSet **
0x180034798  call    ?CreateBatchSet@BatchController@Composition@UI@Windows@@AEAAXPEAPEAUBatchSet@234@PEAPEAVCompositionBatch@234@@Z; Windows::UI::Composition::BatchController::CreateBatchSet(Windows::UI::Composition::BatchSet * *,Windows::UI::Composition::CompositionBatch * *)
0x18003479d  mov     rax, [rbp+arg_0]
0x1800347a1  mov     rsi, [rbp+arg_8]
0x1800347a5  jmp     loc_1800346FF
0x1800347aa  cmp     [rcx+98h], eax
0x1800347b0  jnz     short loc_1800347BB
0x1800347b2  test    rsi, rsi
0x1800347b5  cmovz   rsi, rcx
0x1800347b9  inc     ebx
0x1800347bb  mov     rcx, [rcx+0D0h]
0x1800347c2  test    rcx, rcx
0x1800347c5  jnz     short loc_1800347AA
0x1800347c7  cmp     ebx, 1
0x1800347ca  jbe     loc_180034644
0x1800347d0  mov     [rdi+8], r13
0x1800347d4  call    cs:__imp_GetCurrentThreadId
0x1800347da  lea     ecx, [rbx-1]
0x1800347dd  mov     r12d, eax
0x1800347e0  lea     rcx, ds:10h[rcx*8]; unsigned __int64
0x1800347e8  call    ?Alloc@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::Alloc(unsigned __int64)
0x1800347ed  mov     [rdi+8], rax
0x1800347f1  mov     rdx, rax
0x1800347f4  test    rax, rax
0x1800347f7  jz      loc_1800348B8
0x1800347fd  mov     dword ptr [rax], 1
0x180034803  mov     r8d, r13d
0x180034806  mov     [rax+4], ebx
0x180034809  mov     rcx, [rdi+20h]
0x18003480d  test    rcx, rcx
0x180034810  jz      loc_180034644
0x180034816  cmp     [rcx+98h], r12d
0x18003481d  jnz     short loc_18003482A
0x18003481f  mov     eax, r8d
0x180034822  inc     r8d
0x180034825  mov     [rdx+rax*8+8], rcx
0x18003482a  mov     rcx, [rcx+0D0h]
0x180034831  jmp     short loc_18003480D
0x180034833  cmp     [rcx+98h], eax
0x180034839  jnz     short loc_180034844
0x18003483b  test    rsi, rsi
0x18003483e  cmovz   rsi, rcx
0x180034842  inc     ebx
0x180034844  mov     rcx, [rcx+0D0h]
0x18003484b  test    rcx, rcx
0x18003484e  jnz     short loc_180034833
0x180034850  cmp     ebx, 1
0x180034853  jbe     loc_1800346F4
0x180034859  mov     [rdi+8], r13
0x18003485d  call    cs:__imp_GetCurrentThreadId
0x180034863  lea     ecx, [rbx-1]
0x180034866  mov     r12d, eax
0x180034869  lea     rcx, ds:10h[rcx*8]; unsigned __int64
0x180034871  call    ?Alloc@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::Alloc(unsigned __int64)
0x180034876  mov     [rdi+8], rax
0x18003487a  mov     rdx, rax
0x18003487d  test    rax, rax
0x180034880  jz      short loc_1800348B8
0x180034882  mov     dword ptr [rax], 1
0x180034888  mov     r8d, r13d
0x18003488b  mov     [rax+4], ebx
0x18003488e  mov     rcx, [rdi+20h]
0x180034892  test    rcx, rcx
0x180034895  jz      loc_1800346F4
0x18003489b  cmp     [rcx+98h], r12d
0x1800348a2  jnz     short loc_1800348AF
0x1800348a4  mov     eax, r8d
0x1800348a7  inc     r8d
0x1800348aa  mov     [rdx+rax*8+8], rcx
0x1800348af  mov     rcx, [rcx+0D0h]
0x1800348b6  jmp     short loc_180034892
0x1800348b8  call    ?Do@FailFast@WRL2@Microsoft@@SAXXZ; Microsoft::WRL2::FailFast::Do(void)
```
