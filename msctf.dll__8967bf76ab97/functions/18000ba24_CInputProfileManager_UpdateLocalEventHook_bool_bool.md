# CInputProfileManager::UpdateLocalEventHook(bool,bool)

- ea: `0x18000ba24`
- end: `0x18000bc2b`
- name: `?UpdateLocalEventHook@CInputProfileManager@@QEAAX_N0@Z`
- size: `519`
- prototype: `void __fastcall(CInputProfileManager *__hidden this, bool, bool)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18000b570`
- `0x18000b77c`
- `0x18000c720`

## callees

- `0x18000ba24`
- `0x18000bc34`
- `0x18000be40`
- `0x1800139a4`
- `0x18003a930`
- `0x180040694`
- `0x18008c138`
- `0x1800a42a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bbf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bbf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bbe8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bbe8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ba6a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ba6a`
- `USER32!MakeThreadTSFEventAware` at `0x18000bbd2`
- `USER32!MakeThreadTSFEventAware` at `0x18000bbd2`
- `USER32!SetWinEventHook` at `0x18000bc19`
- `USER32!SetWinEventHook` at `0x18000bc19`

## pseudocode

```c
void __fastcall CInputProfileManager::UpdateLocalEventHook(CInputProfileManager *this, char a2, char a3)
{
  unsigned __int64 v3; // rax
  CInputProfileManager *v5; // rbp
  __int64 v6; // rbx
  unsigned __int64 v7; // r15
  _QWORD *v8; // rsi
  HKL KeyboardLayout; // rax
  void **v10; // rax
  DWORD v11; // edi
  DWORD v12; // r14d
  __int64 v13; // rdx
  __int64 v14; // rax
  DWORD v15; // r9d
  DWORD v16; // r8d
  DWORD v17; // eax
  DWORD v18; // eax
  _DWORD *v19; // rax
  _DWORD *v20; // r15
  __int64 v21; // r8
  int v22; // eax
  unsigned int v23; // r8d
  int v24; // r9d
  DWORD idThread; // ebx
  DWORD idProcess; // eax

  v3 = *((_QWORD *)this + 13);
  v5 = this;
  if ( a2 )
  {
    if ( v3 )
      goto LABEL_4;
    v6 = *((_QWORD *)this + 9);
    *((_QWORD *)this + 13) = 0;
    v7 = ((unsigned __int64)this + 64) & -(__int64)(this != 0);
    v8 = LocalAlloc(0x40u, 0x18u);
    if ( !v8 )
      goto LABEL_4;
    v10 = CVoidPtrArray::Append((CVoidPtrArray *)(v6 + 320));
    if ( !v10 )
    {
      cicMemFree(v8);
      goto LABEL_4;
    }
    *v10 = v8;
    v11 = 0x80000000;
    v12 = -2147483645;
    *((_DWORD *)v8 + 2) = 0x80000000;
    *((_DWORD *)v8 + 3) = -2147483645;
    *((_DWORD *)v8 + 4) = 1;
    LODWORD(this) = 0;
    *v8 = v7;
    while ( (int)this < *(_DWORD *)(v6 + 304) )
    {
      v13 = *(_DWORD *)(v6 + 308) * (int)this;
      v14 = *(_QWORD *)(v6 + 296);
      if ( *(_DWORD *)(v13 + v14 + 16) == 1 )
      {
        v15 = *(_DWORD *)(v13 + v14 + 12);
        if ( v11 <= v15 )
        {
          v16 = *(_DWORD *)(v13 + v14 + 8);
          if ( v12 >= v16 )
          {
            ++*(_DWORD *)(v13 + v14 + 20);
            v17 = v15 + 1;
            if ( v11 < v16 )
              v17 = v11;
            v11 = v17;
            v18 = v16 - 1;
            if ( v12 > v15 )
              v18 = v12;
            v12 = v18;
            if ( v11 >= v18 )
            {
              v11 = v18 + 1;
              break;
            }
          }
        }
      }
      LODWORD(this) = (_DWORD)this + 1;
    }
    if ( v11 <= v12 )
    {
      v19 = CVoidStructArray::Append((CVoidStructArray *)(v6 + 288), 1);
      v20 = v19;
      if ( !v19 )
      {
        tagSYSTHREAD::UnadviseCiceroEvents((tagSYSTHREAD *)v6, (unsigned __int64)v8);
        goto LABEL_4;
      }
      v19[2] = v11;
      v19[5] = 1;
      v19[4] = 1;
      v19[3] = v12;
      if ( (*(_DWORD *)(v6 + 192) & 0x100) != 0 )
      {
        v21 = 0;
        while ( v11 <= v12 )
        {
          v22 = TSFRangeFromEvent(v11, 0, v21);
          if ( !v22 )
          {
            LODWORD(v21) = 0;
            break;
          }
          v21 = v22 | v23;
          v11 += v24;
        }
        *((_DWORD *)v8 + 5) = v21;
        MakeThreadTSFEventAware((unsigned int)v21);
        *(_QWORD *)v20 = 0;
        v20[6] = *((_DWORD *)v8 + 5);
      }
      else
      {
        idThread = GetCurrentThreadId();
        idProcess = GetCurrentProcessId();
        *(_QWORD *)v20 = SetWinEventHook(v11, v12, g_hInst, WinEventProc, idProcess, idThread, 4u);
      }
    }
    *((_QWORD *)v5 + 13) = v8;
  }
  else if ( v3 )
  {
    tagSYSTHREAD::UnadviseCiceroEvents(*((tagSYSTHREAD **)this + 9), v3);
    *((_QWORD *)v5 + 13) = 0;
  }
LABEL_4:
  if ( a3 )
  {
    KeyboardLayout = _Internal_GetKeyboardLayout((unsigned int)this);
    CInputProfileManager::OnActiveKeyboardLayoutChange((CInputLanguage **)v5, KeyboardLayout);
  }
}

```

## disassembly

```asm
0x18000ba24  push    rbx
0x18000ba26  push    rbp
0x18000ba27  push    rsi
0x18000ba28  push    rdi
0x18000ba29  push    r12
0x18000ba2b  push    r14
0x18000ba2d  push    r15
0x18000ba2f  sub     rsp, 40h
0x18000ba33  mov     rax, [rcx+68h]
0x18000ba37  mov     r12b, r8b
0x18000ba3a  mov     rbp, rcx
0x18000ba3d  test    dl, dl
0x18000ba3f  jz      short loc_18000BA9C
0x18000ba41  test    rax, rax
0x18000ba44  jnz     short loc_18000BA78
0x18000ba46  mov     rbx, [rcx+48h]
0x18000ba4a  lea     rdx, [rcx+40h]
0x18000ba4e  mov     rax, rcx
0x18000ba51  mov     qword ptr [rcx+68h], 0
0x18000ba59  neg     rax
0x18000ba5c  sbb     r15, r15
0x18000ba5f  and     r15, rdx
0x18000ba62  mov     edx, 18h; uBytes
0x18000ba67  lea     ecx, [rdx+28h]; uFlags
0x18000ba6a  call    cs:__imp_LocalAlloc
0x18000ba70  mov     rsi, rax
0x18000ba73  test    rax, rax
0x18000ba76  jnz     short loc_18000BAB7
0x18000ba78  test    r12b, r12b
0x18000ba7b  jz      short loc_18000BA8D
0x18000ba7d  call    ?_Internal_GetKeyboardLayout@@YAPEAUHKL__@@K@Z; _Internal_GetKeyboardLayout(ulong)
0x18000ba82  mov     rdx, rax; HKL
0x18000ba85  mov     rcx, rbp; this
0x18000ba88  call    ?OnActiveKeyboardLayoutChange@CInputProfileManager@@QEAAXPEAUHKL__@@@Z; CInputProfileManager::OnActiveKeyboardLayoutChange(HKL__ *)
0x18000ba8d  add     rsp, 40h
0x18000ba91  pop     r15
0x18000ba93  pop     r14
0x18000ba95  pop     r12
0x18000ba97  pop     rdi
0x18000ba98  pop     rsi
0x18000ba99  pop     rbp
0x18000ba9a  pop     rbx
0x18000ba9b  retn
0x18000ba9c  test    rax, rax
0x18000ba9f  jz      short loc_18000BA78
0x18000baa1  mov     rcx, [rcx+48h]; this
0x18000baa5  mov     rdx, rax; unsigned __int64
0x18000baa8  call    ?UnadviseCiceroEvents@tagSYSTHREAD@@QEAAX_K@Z; tagSYSTHREAD::UnadviseCiceroEvents(unsigned __int64)
0x18000baad  mov     qword ptr [rbp+68h], 0
0x18000bab5  jmp     short loc_18000BA78
0x18000bab7  lea     rcx, [rbx+140h]; this
0x18000babe  call    ?Append@CVoidPtrArray@@QEAAPEAPEAXH@Z; CVoidPtrArray::Append(int)
0x18000bac3  test    rax, rax
0x18000bac6  jnz     short loc_18000BAD2
0x18000bac8  mov     rcx, rsi
0x18000bacb  call    cicMemFree
0x18000bad0  jmp     short loc_18000BA78
0x18000bad2  mov     [rax], rsi
0x18000bad5  mov     edi, 80000000h
0x18000bada  mov     r14d, 80000003h
0x18000bae0  mov     [rsi+8], edi
0x18000bae3  mov     r10d, 1
0x18000bae9  mov     [rsi+0Ch], r14d
0x18000baed  mov     [rsi+10h], r10d
0x18000baf1  xor     ecx, ecx
0x18000baf3  mov     [rsi], r15
0x18000baf6  cmp     ecx, [rbx+130h]
0x18000bafc  jge     short loc_18000BB52
0x18000bafe  mov     eax, ecx
0x18000bb00  imul    eax, [rbx+134h]
0x18000bb07  movsxd  rdx, eax
0x18000bb0a  mov     rax, [rbx+128h]
0x18000bb11  cmp     [rdx+rax+10h], r10d
0x18000bb16  jnz     short loc_18000BB82
0x18000bb18  mov     r9d, [rdx+rax+0Ch]
0x18000bb1d  cmp     edi, r9d
0x18000bb20  ja      short loc_18000BB82
0x18000bb22  mov     r8d, [rdx+rax+8]
0x18000bb27  cmp     r14d, r8d
0x18000bb2a  jb      short loc_18000BB82
0x18000bb2c  add     [rdx+rax+14h], r10d
0x18000bb31  lea     eax, [r9+1]
0x18000bb35  cmp     edi, r8d
0x18000bb38  cmovb   eax, edi
0x18000bb3b  cmp     r14d, r9d
0x18000bb3e  mov     edi, eax
0x18000bb40  lea     eax, [r8-1]
0x18000bb44  cmova   eax, r14d
0x18000bb48  mov     r14d, eax
0x18000bb4b  cmp     edi, eax
0x18000bb4d  jb      short loc_18000BB82
0x18000bb4f  lea     edi, [rax+1]
0x18000bb52  cmp     edi, r14d
0x18000bb55  ja      loc_18000BC22
0x18000bb5b  lea     rcx, [rbx+120h]; this
0x18000bb62  mov     edx, r10d; int
0x18000bb65  call    ?Append@CVoidStructArray@@QEAAPEAXH@Z; CVoidStructArray::Append(int)
0x18000bb6a  mov     r15, rax
0x18000bb6d  test    rax, rax
0x18000bb70  jnz     short loc_18000BB8A
0x18000bb72  mov     rdx, rsi; unsigned __int64
0x18000bb75  mov     rcx, rbx; this
0x18000bb78  call    ?UnadviseCiceroEvents@tagSYSTHREAD@@QEAAX_K@Z; tagSYSTHREAD::UnadviseCiceroEvents(unsigned __int64)
0x18000bb7d  jmp     loc_18000BA78
0x18000bb82  add     ecx, r10d
0x18000bb85  jmp     loc_18000BAF6
0x18000bb8a  mov     r9d, 1
0x18000bb90  mov     [rax+8], edi
0x18000bb93  mov     [rax+14h], r9d
0x18000bb97  mov     [rax+10h], r9d
0x18000bb9b  mov     [rax+0Ch], r14d
0x18000bb9f  test    dword ptr [rbx+0C0h], 100h
0x18000bba9  jz      short loc_18000BBE8
0x18000bbab  xor     r8d, r8d
0x18000bbae  cmp     edi, r14d
0x18000bbb1  ja      short loc_18000BBCB
0x18000bbb3  xor     edx, edx
0x18000bbb5  mov     ecx, edi
0x18000bbb7  call    ?TSFRangeFromEvent@@YAKKW4TSFLocality@@@Z; TSFRangeFromEvent(ulong,TSFLocality)
0x18000bbbc  test    eax, eax
0x18000bbbe  jz      short loc_18000BBC8
0x18000bbc0  or      r8d, eax
0x18000bbc3  add     edi, r9d
0x18000bbc6  jmp     short loc_18000BBAE
0x18000bbc8  xor     r8d, r8d
0x18000bbcb  mov     ecx, r8d
0x18000bbce  mov     [rsi+14h], r8d
0x18000bbd2  call    cs:__imp_MakeThreadTSFEventAware
0x18000bbd8  mov     qword ptr [r15], 0
0x18000bbdf  mov     eax, [rsi+14h]
0x18000bbe2  mov     [r15+18h], eax
0x18000bbe6  jmp     short loc_18000BC22
0x18000bbe8  call    cs:__imp_GetCurrentThreadId
0x18000bbee  mov     ebx, eax
0x18000bbf0  call    cs:__imp_GetCurrentProcessId
0x18000bbf6  mov     r8, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hmodWinEventProc
0x18000bbfd  lea     r9, ?WinEventProc@@YAXPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJKK@Z; pfnWinEventProc
0x18000bc04  mov     [rsp+78h+dwFlags], 4; dwFlags
0x18000bc0c  mov     edx, r14d; eventMax
0x18000bc0f  mov     [rsp+78h+idThread], ebx; idThread
0x18000bc13  mov     ecx, edi; eventMin
0x18000bc15  mov     [rsp+78h+idProcess], eax; idProcess
0x18000bc19  call    cs:__imp_SetWinEventHook
0x18000bc1f  mov     [r15], rax
0x18000bc22  mov     [rbp+68h], rsi
0x18000bc26  jmp     loc_18000BA78
```
