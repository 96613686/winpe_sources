# DasHostCreateAssociationContextFromOobBlob

- ea: `0x14000c350`
- end: `0x14000c62d`
- name: `DasHostCreateAssociationContextFromOobBlob`
- size: `733`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, const struct _GUID *, int, __int64, void *, HANDLE ExistingTokenHandle, unsigned int, void **, _QWORD *, _DWORD *, struct _DEVPROPERTY **)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x140008eec`
- `0x140008f88`
- `0x140009060`
- `0x140009090`
- `0x14000a8ac`
- `0x14000afa4`
- `0x14000bc74`
- `0x14000c350`
- `0x140019c5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000c412`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000c412`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000c47b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000c47b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c4aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c4aa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x14000c5cb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x14000c5cb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x14000c5c2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x14000c5c2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14000c46c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14000c46c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14000c45b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14000c45b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c5af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c5af`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000c3ad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000c3ad`

## pseudocode

```c
__int64 __fastcall DasHostCreateAssociationContextFromOobBlob(
        __int64 a1,
        struct _GUID *a2,
        const struct _GUID *a3,
        int a4,
        __int64 a5,
        void *a6,
        HANDLE ExistingTokenHandle,
        unsigned int a8,
        void **a9,
        _QWORD *a10,
        _DWORD *a11,
        struct _DEVPROPERTY **a12)
{
  struct _TP_WORK *v13; // rsi
  int v16; // edx
  signed int AssociationEntry; // ebx
  int v18; // r8d
  PVOID v19; // rdi
  HANDLE EventW; // rax
  signed int v21; // eax
  struct _TP_WORK *ThreadpoolWork; // rax
  DWORD v23; // eax
  signed int LastError; // eax
  _WORD *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rbx
  unsigned __int16 *v28; // rax
  struct _DEVPROPERTY *v29; // rcx
  void *v30; // rcx
  int v32; // [rsp+28h] [rbp-70h]
  PVOID pv; // [rsp+40h] [rbp-58h] BYREF

  pv = 0;
  v13 = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      (int)a3,
      23,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids);
  EventActivityIdControl(2u, a2);
  AssociationEntry = CreateAssociationEntry(
                       a2,
                       a8,
                       0,
                       a3,
                       0,
                       a6,
                       ExistingTokenHandle,
                       (struct _ASSOCIATION_ENTRY **)&pv);
  v19 = pv;
  if ( !AssociationEntry )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)v19 + 12) = EventW;
    if ( EventW
      && (*((_DWORD *)v19 + 26) = a4,
          *((_QWORD *)v19 + 14) = a5,
          ThreadpoolWork = CreateThreadpoolWork(InitFromOobCallback, v19, 0),
          (v13 = ThreadpoolWork) != 0) )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      v23 = WaitForSingleObject(*((HANDLE *)v19 + 12), 0xEA60u);
      switch ( v23 )
      {
        case 0u:
          goto LABEL_16;
        case 0x80u:
          AssociationEntry = -2147024161;
          goto LABEL_33;
        case 0x102u:
          AssociationEntry = -2147023436;
          goto LABEL_33;
      }
      if ( v23 != -1 )
      {
        AssociationEntry = -2147467259;
        goto LABEL_33;
      }
      LastError = GetLastError();
      AssociationEntry = LastError;
      if ( LastError > 0 )
        AssociationEntry = (unsigned __int16)LastError | 0x80070000;
      if ( !AssociationEntry )
      {
LABEL_16:
        AssociationEntry = *((_DWORD *)v19 + 16);
        if ( !AssociationEntry )
        {
          v25 = (_WORD *)*((_QWORD *)v19 + 9);
          if ( !v25 )
          {
            AssociationEntry = -2147024809;
            goto LABEL_33;
          }
          v16 = 768;
          v26 = 768;
          do
          {
            if ( !*v25 )
              break;
            ++v25;
            --v26;
          }
          while ( v26 );
          AssociationEntry = v26 == 0 ? 0x80070057 : 0;
          if ( v26 )
          {
            v27 = -(__int64)(v26 != 0) & (2 * (768 - v26));
            v28 = (unsigned __int16 *)DAF_user_alloc(v27 + 2);
            *a9 = v28;
            if ( v28 )
            {
              AssociationEntry = StringCbCopyW(v28, v27 + 2, *((unsigned __int16 **)v19 + 9));
              if ( AssociationEntry >= 0 )
              {
                v18 = (int)a12;
                if ( a12 )
                {
                  v29 = (struct _DEVPROPERTY *)*((_QWORD *)v19 + 16);
                  if ( v29 )
                  {
                    AssociationEntry = MidlCopyDevProperties(v29, *((_DWORD *)v19 + 30), a12);
                    if ( AssociationEntry )
                      goto LABEL_33;
                    *a11 = *((_DWORD *)v19 + 30);
                  }
                }
                *a10 = v19;
              }
            }
            else
            {
              AssociationEntry = -2147024882;
            }
          }
        }
      }
    }
    else
    {
      v21 = GetLastError();
      AssociationEntry = v21;
      if ( v21 > 0 )
        AssociationEntry = (unsigned __int16)v21 | 0x80070000;
    }
  }
LABEL_33:
  if ( v19 )
  {
    v30 = (void *)*((_QWORD *)v19 + 12);
    if ( v30 )
      CloseHandle(v30);
  }
  if ( v13 )
  {
    WaitForThreadpoolWorkCallbacks(v13, 1);
    CloseThreadpoolWork(v13);
  }
  if ( AssociationEntry < 0 )
  {
    if ( *a9 )
    {
      MIDL_user_free(*a9);
      *a9 = 0;
    }
    if ( v19 )
      RemoveAssociationEntry((struct _ASSOCIATION_ENTRY *)v19, v16, v18);
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v16,
      v18,
      24,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids,
      v32,
      AssociationEntry);
  return (unsigned int)AssociationEntry;
}

```

## disassembly

```asm
0x14000c350  push    rbx
0x14000c352  push    rbp
0x14000c353  push    rsi
0x14000c354  push    rdi
0x14000c355  push    r12
0x14000c357  push    r13
0x14000c359  push    r14
0x14000c35b  push    r15
0x14000c35d  sub     rsp, 58h
0x14000c361  xor     r15d, r15d
0x14000c364  mov     ebp, r9d
0x14000c367  mov     [rsp+98h+pv], r15
0x14000c36c  mov     esi, r15d
0x14000c36f  mov     rdi, r8
0x14000c372  mov     rbx, rdx
0x14000c375  lea     r12, WPP_RECORDER_INITIALIZED
0x14000c37c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000c383  lea     r13, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000c38a  jz      short loc_14000C3A5
0x14000c38c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c393  lea     r9d, [r15+17h]; int
0x14000c397  mov     [rsp+98h+MessageGuid], r13; MessageGuid
0x14000c39c  mov     rcx, [rcx+28h]; int
0x14000c3a0  call    WPP_RECORDER_SF_s
0x14000c3a5  mov     rdx, rbx; ActivityId
0x14000c3a8  mov     ecx, 2; ControlCode
0x14000c3ad  call    cs:__imp_EventActivityIdControl
0x14000c3b3  mov     edx, [rsp+98h+arg_38]; unsigned int
0x14000c3ba  lea     rax, [rsp+98h+pv]
0x14000c3bf  mov     [rsp+98h+var_60], rax; struct _ASSOCIATION_ENTRY **
0x14000c3c4  mov     r9, rdi; struct _GUID *
0x14000c3c7  mov     rax, [rsp+98h+arg_30]
0x14000c3cf  xor     r8d, r8d; unsigned __int16 *
0x14000c3d2  mov     [rsp+98h+ExistingTokenHandle], rax; ExistingTokenHandle
0x14000c3d7  mov     rcx, rbx; struct _GUID *
0x14000c3da  mov     rax, [rsp+98h+arg_28]
0x14000c3e2  mov     [rsp+98h+var_70], rax; int
0x14000c3e7  mov     [rsp+98h+MessageGuid], r15; unsigned __int16 *
0x14000c3ec  call    ?CreateAssociationEntry@@YAJPEBU_GUID@@KPEBG01PEAX2PEAPEAU_ASSOCIATION_ENTRY@@@Z; CreateAssociationEntry(_GUID const *,ulong,ushort const *,_GUID const *,ushort const *,void *,void *,_ASSOCIATION_ENTRY * *)
0x14000c3f1  mov     r14, [rsp+98h+arg_40]
0x14000c3f9  mov     ebx, eax
0x14000c3fb  mov     rdi, [rsp+98h+pv]
0x14000c400  test    eax, eax
0x14000c402  jnz     loc_14000C5A1
0x14000c408  xor     r9d, r9d; lpName
0x14000c40b  xor     r8d, r8d; bInitialState
0x14000c40e  xor     edx, edx; bManualReset
0x14000c410  xor     ecx, ecx; lpEventAttributes
0x14000c412  call    cs:__imp_CreateEventW
0x14000c418  mov     [rdi+60h], rax
0x14000c41c  test    rax, rax
0x14000c41f  jnz     short loc_14000C43F
0x14000c421  call    cs:__imp_GetLastError
0x14000c427  mov     ebx, eax
0x14000c429  test    eax, eax
0x14000c42b  jle     loc_14000C5A1
0x14000c431  movzx   ebx, ax
0x14000c434  or      ebx, 80070000h
0x14000c43a  jmp     loc_14000C5A1
0x14000c43f  mov     rax, [rsp+98h+arg_20]
0x14000c447  lea     rcx, ?InitFromOobCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14000c44e  mov     [rdi+68h], ebp
0x14000c451  xor     r8d, r8d; pcbe
0x14000c454  mov     rdx, rdi; pv
0x14000c457  mov     [rdi+70h], rax
0x14000c45b  call    cs:__imp_CreateThreadpoolWork
0x14000c461  mov     rsi, rax
0x14000c464  test    rax, rax
0x14000c467  jz      short loc_14000C421
0x14000c469  mov     rcx, rax; pwk
0x14000c46c  call    cs:__imp_SubmitThreadpoolWork
0x14000c472  mov     rcx, [rdi+60h]; hHandle
0x14000c476  mov     edx, 0EA60h; dwMilliseconds
0x14000c47b  call    cs:__imp_WaitForSingleObject
0x14000c481  test    eax, eax
0x14000c483  jz      short loc_14000C4C7
0x14000c485  cmp     eax, 80h
0x14000c48a  jz      loc_14000C53E
0x14000c490  cmp     eax, 102h
0x14000c495  jz      loc_14000C537
0x14000c49b  cmp     eax, 0FFFFFFFFh
0x14000c49e  jz      short loc_14000C4AA
0x14000c4a0  mov     ebx, 80004005h
0x14000c4a5  jmp     loc_14000C5A1
0x14000c4aa  call    cs:__imp_GetLastError
0x14000c4b0  mov     ebx, eax
0x14000c4b2  test    eax, eax
0x14000c4b4  jle     short loc_14000C4BF
0x14000c4b6  movzx   ebx, ax
0x14000c4b9  or      ebx, 80070000h
0x14000c4bf  test    ebx, ebx
0x14000c4c1  jnz     loc_14000C5A1
0x14000c4c7  mov     ebx, [rdi+40h]
0x14000c4ca  test    ebx, ebx
0x14000c4cc  jnz     loc_14000C5A1
0x14000c4d2  mov     rax, [rdi+48h]
0x14000c4d6  test    rax, rax
0x14000c4d9  jz      loc_14000C59C
0x14000c4df  mov     edx, 300h
0x14000c4e4  mov     ecx, edx
0x14000c4e6  cmp     [rax], r15w
0x14000c4ea  jz      short loc_14000C4F6
0x14000c4ec  add     rax, 2
0x14000c4f0  sub     rcx, 1
0x14000c4f4  jnz     short loc_14000C4E6
0x14000c4f6  mov     rax, rcx
0x14000c4f9  neg     rax
0x14000c4fc  sbb     ebx, ebx
0x14000c4fe  not     ebx
0x14000c500  and     ebx, 80070057h
0x14000c506  test    rcx, rcx
0x14000c509  jz      loc_14000C5A1
0x14000c50f  sub     rdx, rcx
0x14000c512  neg     rcx
0x14000c515  sbb     rax, rax
0x14000c518  lea     rbx, [rdx+rdx]
0x14000c51c  and     rbx, rax
0x14000c51f  lea     rcx, [rbx+2]
0x14000c523  call    DAF_user_alloc
0x14000c528  mov     [r14], rax
0x14000c52b  test    rax, rax
0x14000c52e  jnz     short loc_14000C545
0x14000c530  mov     ebx, 8007000Eh
0x14000c535  jmp     short loc_14000C5A1
0x14000c537  mov     ebx, 800705B4h
0x14000c53c  jmp     short loc_14000C5A1
0x14000c53e  mov     ebx, 800702DFh
0x14000c543  jmp     short loc_14000C5A1
0x14000c545  mov     r8, [rdi+48h]; unsigned __int16 *
0x14000c549  lea     rdx, [rbx+2]; unsigned __int64
0x14000c54d  mov     rcx, rax; unsigned __int16 *
0x14000c550  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14000c555  mov     ebx, eax
0x14000c557  test    eax, eax
0x14000c559  js      short loc_14000C5A1
0x14000c55b  mov     r8, [rsp+98h+arg_58]; struct _DEVPROPERTY **
0x14000c563  test    r8, r8
0x14000c566  jz      short loc_14000C58F
0x14000c568  mov     rcx, [rdi+80h]; struct _DEVPROPERTY *
0x14000c56f  test    rcx, rcx
0x14000c572  jz      short loc_14000C58F
0x14000c574  mov     edx, [rdi+78h]; unsigned int
0x14000c577  call    ?MidlCopyDevProperties@@YAJPEAU_DEVPROPERTY@@KPEAPEAU1@@Z; MidlCopyDevProperties(_DEVPROPERTY *,ulong,_DEVPROPERTY * *)
0x14000c57c  mov     ebx, eax
0x14000c57e  test    eax, eax
0x14000c580  jnz     short loc_14000C5A1
0x14000c582  mov     rax, [rsp+98h+arg_50]
0x14000c58a  mov     ecx, [rdi+78h]
0x14000c58d  mov     [rax], ecx
0x14000c58f  mov     rax, [rsp+98h+arg_48]
0x14000c597  mov     [rax], rdi
0x14000c59a  jmp     short loc_14000C5A1
0x14000c59c  mov     ebx, 80070057h
0x14000c5a1  test    rdi, rdi
0x14000c5a4  jz      short loc_14000C5B5
0x14000c5a6  mov     rcx, [rdi+60h]; hObject
0x14000c5aa  test    rcx, rcx
0x14000c5ad  jz      short loc_14000C5B5
0x14000c5af  call    cs:__imp_CloseHandle
0x14000c5b5  test    rsi, rsi
0x14000c5b8  jz      short loc_14000C5D1
0x14000c5ba  mov     edx, 1; fCancelPendingCallbacks
0x14000c5bf  mov     rcx, rsi; pwk
0x14000c5c2  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x14000c5c8  mov     rcx, rsi; pwk
0x14000c5cb  call    cs:__imp_CloseThreadpoolWork
0x14000c5d1  test    ebx, ebx
0x14000c5d3  jns     short loc_14000C5F2
0x14000c5d5  mov     rcx, [r14]; void *
0x14000c5d8  test    rcx, rcx
0x14000c5db  jz      short loc_14000C5E5
0x14000c5dd  call    MIDL_user_free
0x14000c5e2  mov     [r14], r15
0x14000c5e5  test    rdi, rdi
0x14000c5e8  jz      short loc_14000C5F2
0x14000c5ea  mov     rcx, rdi; lpMem
0x14000c5ed  call    ?RemoveAssociationEntry@@YAJPEAU_ASSOCIATION_ENTRY@@@Z; RemoveAssociationEntry(_ASSOCIATION_ENTRY *)
0x14000c5f2  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000c5f9  jz      short loc_14000C61A
0x14000c5fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c602  mov     r9d, 18h; int
0x14000c608  mov     dword ptr [rsp+98h+ExistingTokenHandle], ebx; char
0x14000c60c  mov     [rsp+98h+MessageGuid], r13; MessageGuid
0x14000c611  mov     rcx, [rcx+28h]; int
0x14000c615  call    WPP_RECORDER_SF_sd
0x14000c61a  mov     eax, ebx
0x14000c61c  add     rsp, 58h
0x14000c620  pop     r15
0x14000c622  pop     r14
0x14000c624  pop     r13
0x14000c626  pop     r12
0x14000c628  pop     rdi
0x14000c629  pop     rsi
0x14000c62a  pop     rbp
0x14000c62b  pop     rbx
0x14000c62c  retn
```
