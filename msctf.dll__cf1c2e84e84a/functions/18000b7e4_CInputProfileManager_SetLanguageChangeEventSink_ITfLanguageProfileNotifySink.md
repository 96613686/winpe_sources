# CInputProfileManager::SetLanguageChangeEventSink(ITfLanguageProfileNotifySink *)

- ea: `0x18000b7e4`
- end: `0x18000ba1c`
- name: `?SetLanguageChangeEventSink@CInputProfileManager@@QEAAXPEAUITfLanguageProfileNotifySink@@@Z`
- size: `568`
- prototype: `void __fastcall(CInputProfileManager *__hidden this, struct ITfLanguageProfileNotifySink *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18000a184`
- `0x18000a4c4`

## callees

- `0x18000b7e4`
- `0x18000bc34`
- `0x18000be40`
- `0x1800139a4`
- `0x18003a930`
- `0x180040694`
- `0x18008c138`
- `0x1800a42a0`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b9e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b9e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b9da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b9da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b847`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b847`
- `USER32!MakeThreadTSFEventAware` at `0x18000b9c3`
- `USER32!MakeThreadTSFEventAware` at `0x18000b9c3`
- `USER32!SetWinEventHook` at `0x18000ba0a`
- `USER32!SetWinEventHook` at `0x18000ba0a`

## pseudocode

```c
void __fastcall CInputProfileManager::SetLanguageChangeEventSink(
        CInputProfileManager *this,
        struct ITfLanguageProfileNotifySink *a2)
{
  CInputProfileManager *v3; // rdi
  char v4; // r12
  __int64 v5; // rbx
  int v6; // edx
  _QWORD *v7; // r14
  HKL KeyboardLayout; // rax
  unsigned __int64 v9; // rdx
  void **v10; // rax
  DWORD v11; // ebp
  DWORD v12; // esi
  int v13; // r8d
  __int64 v14; // rax
  DWORD v15; // edx
  DWORD v16; // r9d
  _DWORD *v17; // rax
  _DWORD *v18; // r15
  __int64 v19; // r8
  int v20; // eax
  unsigned int v21; // r8d
  DWORD idThread; // ebx
  DWORD idProcess; // eax

  v3 = this;
  if ( !a2 || *((_QWORD *)this + 10) )
  {
    v4 = 0;
    if ( !a2 && !*((_QWORD *)this + 10) )
    {
LABEL_10:
      v9 = *((_QWORD *)v3 + 13);
      if ( v9 )
      {
        tagSYSTHREAD::UnadviseCiceroEvents(*((tagSYSTHREAD **)v3 + 9), v9);
        *((_QWORD *)v3 + 13) = 0;
      }
      goto LABEL_6;
    }
  }
  else
  {
    v4 = 1;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(CInputProfileManager *))(*(_QWORD *)this + 8LL))(this) )
    goto LABEL_10;
  if ( !*((_QWORD *)v3 + 13) )
  {
    v5 = *((_QWORD *)v3 + 9);
    *((_QWORD *)v3 + 13) = 0;
    v7 = LocalAlloc(0x40u, 0x18u);
    if ( v7 )
    {
      v10 = CVoidPtrArray::Append((CVoidPtrArray *)(v5 + 320), v6);
      if ( !v10 )
      {
        cicMemFree(v7);
        goto LABEL_6;
      }
      *v10 = v7;
      v11 = -2147483645;
      v12 = 0x80000000;
      *((_DWORD *)v7 + 3) = -2147483645;
      *((_DWORD *)v7 + 2) = 0x80000000;
      *((_DWORD *)v7 + 4) = 1;
      v13 = 0;
      *v7 = ((unsigned __int64)v3 + 64) & -(__int64)(v3 != 0);
      while ( v13 < *(_DWORD *)(v5 + 304) )
      {
        this = (CInputProfileManager *)(*(_DWORD *)(v5 + 308) * v13);
        v14 = *(_QWORD *)(v5 + 296);
        if ( *(_DWORD *)((char *)this + v14 + 16) == 1 )
        {
          v15 = *(_DWORD *)((char *)this + v14 + 12);
          if ( v12 <= v15 )
          {
            v16 = *(_DWORD *)((char *)this + v14 + 8);
            if ( v11 >= v16 )
            {
              ++*(_DWORD *)((char *)this + v14 + 20);
              if ( v12 >= v16 )
                v12 = v15 + 1;
              if ( v11 <= v15 )
                v11 = v16 - 1;
              if ( v12 >= v11 )
              {
                v12 = v11 + 1;
                break;
              }
            }
          }
        }
        ++v13;
      }
      if ( v12 <= v11 )
      {
        v17 = CVoidStructArray::Append((CVoidStructArray *)(v5 + 288), 1);
        v18 = v17;
        if ( !v17 )
        {
          tagSYSTHREAD::UnadviseCiceroEvents((tagSYSTHREAD *)v5, (unsigned __int64)v7);
          goto LABEL_6;
        }
        v17[5] = 1;
        v17[2] = v12;
        v17[3] = v11;
        v17[4] = 1;
        if ( (*(_DWORD *)(v5 + 192) & 0x100) != 0 )
        {
          v19 = 0;
          while ( v12 <= v11 )
          {
            v20 = TSFRangeFromEvent(v12, 0, v19);
            if ( !v20 )
            {
              LODWORD(v19) = 0;
              break;
            }
            v19 = v20 | v21;
            ++v12;
          }
          *((_DWORD *)v7 + 5) = v19;
          MakeThreadTSFEventAware((unsigned int)v19);
          *(_QWORD *)v18 = 0;
          v18[6] = *((_DWORD *)v7 + 5);
        }
        else
        {
          idThread = GetCurrentThreadId();
          idProcess = GetCurrentProcessId();
          *(_QWORD *)v18 = SetWinEventHook(v12, v11, g_hInst, WinEventProc, idProcess, idThread, 4u);
        }
      }
      *((_QWORD *)v3 + 13) = v7;
    }
  }
LABEL_6:
  if ( v4 )
  {
    KeyboardLayout = _Internal_GetKeyboardLayout((unsigned int)this);
    CInputProfileManager::OnActiveKeyboardLayoutChange(v3, KeyboardLayout);
  }
  *((_QWORD *)v3 + 11) = a2;
}

```

## disassembly

```asm
0x18000b7e4  push    rbx
0x18000b7e6  push    rbp
0x18000b7e7  push    rsi
0x18000b7e8  push    rdi
0x18000b7e9  push    r12
0x18000b7eb  push    r13
0x18000b7ed  push    r14
0x18000b7ef  push    r15
0x18000b7f1  sub     rsp, 48h
0x18000b7f5  mov     r13, rdx
0x18000b7f8  mov     rdi, rcx
0x18000b7fb  test    rdx, rdx
0x18000b7fe  jnz     loc_18000B8A2
0x18000b804  xor     r12b, r12b
0x18000b807  test    r13, r13
0x18000b80a  jz      short loc_18000B87F
0x18000b80c  mov     rax, [rcx]
0x18000b80f  mov     rax, [rax+8]
0x18000b813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b818  test    al, al
0x18000b81a  jz      short loc_18000B886
0x18000b81c  cmp     qword ptr [rdi+68h], 0
0x18000b821  jnz     short loc_18000B855
0x18000b823  mov     rbx, [rdi+48h]
0x18000b827  lea     rcx, [rdi+40h]
0x18000b82b  mov     edx, 18h; uBytes
0x18000b830  mov     qword ptr [rdi+68h], 0
0x18000b838  mov     rax, rdi
0x18000b83b  neg     rax
0x18000b83e  sbb     r15, r15
0x18000b841  and     r15, rcx
0x18000b844  lea     ecx, [rdx+28h]; uFlags
0x18000b847  call    cs:__imp_LocalAlloc
0x18000b84d  mov     r14, rax
0x18000b850  test    rax, rax
0x18000b853  jnz     short loc_18000B8B5
0x18000b855  test    r12b, r12b
0x18000b858  jz      short loc_18000B86A
0x18000b85a  call    ?_Internal_GetKeyboardLayout@@YAPEAUHKL__@@K@Z; _Internal_GetKeyboardLayout(ulong)
0x18000b85f  mov     rdx, rax; HKL
0x18000b862  mov     rcx, rdi; this
0x18000b865  call    ?OnActiveKeyboardLayoutChange@CInputProfileManager@@QEAAXPEAUHKL__@@@Z; CInputProfileManager::OnActiveKeyboardLayoutChange(HKL__ *)
0x18000b86a  mov     [rdi+58h], r13
0x18000b86e  add     rsp, 48h
0x18000b872  pop     r15
0x18000b874  pop     r14
0x18000b876  pop     r13
0x18000b878  pop     r12
0x18000b87a  pop     rdi
0x18000b87b  pop     rsi
0x18000b87c  pop     rbp
0x18000b87d  pop     rbx
0x18000b87e  retn
0x18000b87f  cmp     qword ptr [rcx+50h], 0
0x18000b884  jnz     short loc_18000B80C
0x18000b886  mov     rdx, [rdi+68h]; unsigned __int64
0x18000b88a  test    rdx, rdx
0x18000b88d  jz      short loc_18000B855
0x18000b88f  mov     rcx, [rdi+48h]; this
0x18000b893  call    ?UnadviseCiceroEvents@tagSYSTHREAD@@QEAAX_K@Z; tagSYSTHREAD::UnadviseCiceroEvents(unsigned __int64)
0x18000b898  mov     qword ptr [rdi+68h], 0
0x18000b8a0  jmp     short loc_18000B855
0x18000b8a2  cmp     qword ptr [rcx+50h], 0
0x18000b8a7  jnz     loc_18000B804
0x18000b8ad  mov     r12b, 1
0x18000b8b0  jmp     loc_18000B80C
0x18000b8b5  lea     rcx, [rbx+140h]; this
0x18000b8bc  call    ?Append@CVoidPtrArray@@QEAAPEAPEAXH@Z; CVoidPtrArray::Append(int)
0x18000b8c1  test    rax, rax
0x18000b8c4  jnz     short loc_18000B8D0
0x18000b8c6  mov     rcx, r14
0x18000b8c9  call    cicMemFree
0x18000b8ce  jmp     short loc_18000B855
0x18000b8d0  mov     [rax], r14
0x18000b8d3  mov     ebp, 80000003h
0x18000b8d8  mov     esi, 80000000h
0x18000b8dd  mov     [r14+0Ch], ebp
0x18000b8e1  mov     r10d, 1
0x18000b8e7  mov     [r14+8], esi
0x18000b8eb  mov     [r14+10h], r10d
0x18000b8ef  xor     r8d, r8d
0x18000b8f2  mov     [r14], r15
0x18000b8f5  cmp     r8d, [rbx+130h]
0x18000b8fc  jge     short loc_18000B947
0x18000b8fe  mov     eax, r8d
0x18000b901  imul    eax, [rbx+134h]
0x18000b908  movsxd  rcx, eax
0x18000b90b  mov     rax, [rbx+128h]
0x18000b912  cmp     [rcx+rax+10h], r10d
0x18000b917  jnz     short loc_18000B976
0x18000b919  mov     edx, [rcx+rax+0Ch]
0x18000b91d  cmp     esi, edx
0x18000b91f  ja      short loc_18000B976
0x18000b921  mov     r9d, [rcx+rax+8]
0x18000b926  cmp     ebp, r9d
0x18000b929  jb      short loc_18000B976
0x18000b92b  add     [rcx+rax+14h], r10d
0x18000b930  cmp     esi, r9d
0x18000b933  jb      short loc_18000B938
0x18000b935  lea     esi, [rdx+1]
0x18000b938  cmp     ebp, edx
0x18000b93a  ja      short loc_18000B940
0x18000b93c  lea     ebp, [r9-1]
0x18000b940  cmp     esi, ebp
0x18000b942  jb      short loc_18000B976
0x18000b944  lea     esi, [rbp+1]
0x18000b947  cmp     esi, ebp
0x18000b949  ja      loc_18000BA13
0x18000b94f  lea     rcx, [rbx+120h]; this
0x18000b956  mov     edx, r10d; int
0x18000b959  call    ?Append@CVoidStructArray@@QEAAPEAXH@Z; CVoidStructArray::Append(int)
0x18000b95e  mov     r15, rax
0x18000b961  test    rax, rax
0x18000b964  jnz     short loc_18000B97E
0x18000b966  mov     rdx, r14; unsigned __int64
0x18000b969  mov     rcx, rbx; this
0x18000b96c  call    ?UnadviseCiceroEvents@tagSYSTHREAD@@QEAAX_K@Z; tagSYSTHREAD::UnadviseCiceroEvents(unsigned __int64)
0x18000b971  jmp     loc_18000B855
0x18000b976  add     r8d, r10d
0x18000b979  jmp     loc_18000B8F5
0x18000b97e  mov     dword ptr [rax+14h], 1
0x18000b985  mov     [rax+8], esi
0x18000b988  mov     [rax+0Ch], ebp
0x18000b98b  mov     dword ptr [rax+10h], 1
0x18000b992  test    dword ptr [rbx+0C0h], 100h
0x18000b99c  jz      short loc_18000B9DA
0x18000b99e  xor     r8d, r8d
0x18000b9a1  cmp     esi, ebp
0x18000b9a3  ja      short loc_18000B9BC
0x18000b9a5  xor     edx, edx
0x18000b9a7  mov     ecx, esi
0x18000b9a9  call    ?TSFRangeFromEvent@@YAKKW4TSFLocality@@@Z; TSFRangeFromEvent(ulong,TSFLocality)
0x18000b9ae  test    eax, eax
0x18000b9b0  jz      short loc_18000B9B9
0x18000b9b2  or      r8d, eax
0x18000b9b5  inc     esi
0x18000b9b7  jmp     short loc_18000B9A1
0x18000b9b9  xor     r8d, r8d
0x18000b9bc  mov     ecx, r8d
0x18000b9bf  mov     [r14+14h], r8d
0x18000b9c3  call    cs:__imp_MakeThreadTSFEventAware
0x18000b9c9  mov     qword ptr [r15], 0
0x18000b9d0  mov     eax, [r14+14h]
0x18000b9d4  mov     [r15+18h], eax
0x18000b9d8  jmp     short loc_18000BA13
0x18000b9da  call    cs:__imp_GetCurrentThreadId
0x18000b9e0  mov     ebx, eax
0x18000b9e2  call    cs:__imp_GetCurrentProcessId
0x18000b9e8  mov     r8, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hmodWinEventProc
0x18000b9ef  lea     r9, ?WinEventProc@@YAXPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJKK@Z; pfnWinEventProc
0x18000b9f6  mov     [rsp+88h+dwFlags], 4; dwFlags
0x18000b9fe  mov     edx, ebp; eventMax
0x18000ba00  mov     [rsp+88h+idThread], ebx; idThread
0x18000ba04  mov     ecx, esi; eventMin
0x18000ba06  mov     [rsp+88h+idProcess], eax; idProcess
0x18000ba0a  call    cs:__imp_SetWinEventHook
0x18000ba10  mov     [r15], rax
0x18000ba13  mov     [rdi+68h], r14
0x18000ba17  jmp     loc_18000B855
```
