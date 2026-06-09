# GenFreeProcessObject(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_LIST_ENTRY *)

- ea: `0x18001a010`
- end: `0x18001a3e7`
- name: `?GenFreeProcessObject@@YAXPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_LIST_ENTRY@@@Z`
- size: `983`
- prototype: `void __fastcall(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *, struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000f8e8`
- `0x18001ad48`

## callees

- `0x18001a010`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001a061`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001a061`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001a078`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001a078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a2f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a2f5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a2ff`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a2ff`

## pseudocode

```c
void __fastcall GenFreeProcessObject(struct _MINIDUMP_STATE *a1, struct _INTERNAL_PROCESS *a2, struct _LIST_ENTRY *a3)
{
  _QWORD *v3; // rsi
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v8; // rcx
  struct _LIST_ENTRY *v9; // r14
  HMODULE Blink; // rcx
  FARPROC ProcAddress; // rax
  struct _INTERNAL_PROCESS *v12; // r15
  _QWORD *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  struct _INTERNAL_PROCESS *v17; // rbx
  char *v18; // rdx
  struct _INTERNAL_PROCESS *v19; // r14
  char *v20; // rbx
  struct _INTERNAL_PROCESS *v21; // rbx
  char *v22; // r15
  _QWORD *v23; // rdx
  _QWORD *v24; // rdx
  struct _INTERNAL_PROCESS *v25; // rbx
  struct _INTERNAL_PROCESS *v26; // r15
  void *v27; // rcx
  _QWORD *v28; // rbx

  v3 = (_QWORD *)((char *)a1 + 32);
  if ( a3 )
  {
    while ( 1 )
    {
      Flink = a3->Flink;
      if ( a3->Flink == a3 )
        break;
      if ( Flink->Blink != a3 || (v8 = Flink->Flink, Flink->Flink->Blink != Flink) )
        __fastfail(3u);
      a3->Flink = v8;
      v9 = Flink - 1;
      v8->Blink = a3;
      Blink = (HMODULE)Flink[-1].Blink;
      if ( Blink )
      {
        ProcAddress = GetProcAddress(Blink, "FreeDumpStreams");
        if ( ProcAddress )
          ((void (__fastcall *)(struct _LIST_ENTRY *))ProcAddress)(v9->Flink);
        FreeLibrary((HMODULE)v9->Blink);
        v9->Blink = 0;
        (*(void (__fastcall **)(_QWORD, struct _LIST_ENTRY *))(**((_QWORD **)a1 + 4) + 24LL))(*((_QWORD *)a1 + 4), v9);
      }
    }
  }
  v12 = (struct _INTERNAL_PROCESS *)*((_QWORD *)a2 + 15);
  if ( v12 != (struct _INTERNAL_PROCESS *)((char *)a2 + 120) )
  {
    v3 = (_QWORD *)((char *)a1 + 32);
    do
    {
      v13 = (_QWORD *)((char *)v12 - 144);
      v14 = *((_QWORD *)v12 - 3);
      v12 = *(struct _INTERNAL_PROCESS **)v12;
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v3 + 24LL))(*v3, v14);
      v15 = v13[10];
      v13[15] = 0;
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v3 + 24LL))(*v3, v15);
      v16 = v13[12];
      v13[10] = 0;
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v3 + 24LL))(*v3, v16);
      v13[12] = 0;
      (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v3 + 24LL))(*v3, v13);
    }
    while ( v12 != (struct _INTERNAL_PROCESS *)((char *)a2 + 120) );
  }
  v17 = (struct _INTERNAL_PROCESS *)*((_QWORD *)a2 + 17);
  if ( v17 != (struct _INTERNAL_PROCESS *)((char *)a2 + 136) )
  {
    v3 = (_QWORD *)((char *)a1 + 32);
    do
    {
      v18 = (char *)v17 - 744;
      v17 = *(struct _INTERNAL_PROCESS **)v17;
      (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v3 + 24LL))(*v3, v18);
    }
    while ( v17 != (struct _INTERNAL_PROCESS *)((char *)a2 + 136) );
  }
  v19 = (struct _INTERNAL_PROCESS *)*((_QWORD *)a2 + 13);
  if ( v19 != (struct _INTERNAL_PROCESS *)((char *)a2 + 104) )
  {
    v3 = (_QWORD *)((char *)a1 + 32);
    do
    {
      v20 = (char *)v19 - 184;
      v19 = *(struct _INTERNAL_PROCESS **)v19;
      if ( *((_QWORD *)v20 + 1) )
      {
        if ( *((_DWORD *)v20 + 6) != -1
          && *(_DWORD *)v20 != (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 2) + 160LL))(*((_QWORD *)a1 + 2)) )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)a1 + 2) + 176LL))(
            *((_QWORD *)a1 + 2),
            *((_QWORD *)v20 + 1),
            v20 + 224);
          *((_DWORD *)v20 + 6) = -1;
        }
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 2) + 152LL))(
          *((_QWORD *)a1 + 2),
          *((_QWORD *)v20 + 1));
        *((_QWORD *)v20 + 1) = 0;
      }
      if ( *((_QWORD *)v20 + 25) )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 24LL))(*v3);
      if ( *((_QWORD *)v20 + 26) )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 24LL))(*v3);
      (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v3 + 24LL))(*v3, v20);
    }
    while ( v19 != (struct _INTERNAL_PROCESS *)((char *)a2 + 104) );
  }
  v21 = (struct _INTERNAL_PROCESS *)*((_QWORD *)a2 + 19);
  while ( v21 != (struct _INTERNAL_PROCESS *)((char *)a2 + 152) )
  {
    v22 = (char *)v21 - 48;
    v21 = *(struct _INTERNAL_PROCESS **)v21;
    if ( *((_QWORD *)v22 + 5) )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 24LL))(*v3);
    (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v3 + 24LL))(*v3, v22);
  }
  while ( 1 )
  {
    v23 = (_QWORD *)*((_QWORD *)a2 + 943);
    if ( !v23 )
      break;
    *((_QWORD *)a2 + 943) = *v23;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)a2 + 941) + 32LL) + 24LL))(*(_QWORD *)(*((_QWORD *)a2 + 941) + 32LL));
  }
  *((_QWORD *)a2 + 944) = 0;
  while ( 1 )
  {
    v24 = (_QWORD *)*((_QWORD *)a2 + 947);
    if ( !v24 )
      break;
    *((_QWORD *)a2 + 947) = *v24;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)a2 + 945) + 32LL) + 24LL))(*(_QWORD *)(*((_QWORD *)a2 + 945) + 32LL));
  }
  *((_QWORD *)a2 + 948) = 0;
  v25 = (struct _INTERNAL_PROCESS *)*((_QWORD *)a2 + 949);
  while ( v25 != (struct _INTERNAL_PROCESS *)((char *)a2 + 7592) )
  {
    v26 = v25;
    v25 = *(struct _INTERNAL_PROCESS **)v25;
    v27 = (void *)*((_QWORD *)v26 + 5);
    if ( v27 )
    {
      CloseHandle(v27);
      DeleteFileW(*((LPCWSTR *)v26 + 4));
    }
    (*(void (__fastcall **)(_QWORD, struct _INTERNAL_PROCESS *))(*(_QWORD *)*v3 + 24LL))(*v3, v26);
  }
  while ( 1 )
  {
    v28 = (_QWORD *)*((_QWORD *)a2 + 9148);
    if ( !v28 )
      break;
    *((_QWORD *)a2 + 9148) = *v28;
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v3 + 24LL))(*v3, v28[1]);
    (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v3 + 24LL))(*v3, v28);
  }
  if ( *((_QWORD *)a2 + 9143) )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 24LL))(*v3);
  if ( *((_QWORD *)a2 + 9145) )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 24LL))(*v3);
  if ( *((_QWORD *)a2 + 9146) )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 24LL))(*v3);
  if ( *((_QWORD *)a2 + 9149) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 2) + 544LL))(*((_QWORD *)a1 + 2));
  (*(void (__fastcall **)(_QWORD, struct _INTERNAL_PROCESS *))(*(_QWORD *)*v3 + 24LL))(*v3, a2);
}

```

## disassembly

```asm
0x18001a010  push    rbx
0x18001a012  push    rbp
0x18001a013  push    rsi
0x18001a014  push    rdi
0x18001a015  push    r14
0x18001a017  push    r15
0x18001a019  sub     rsp, 28h
0x18001a01d  lea     rsi, [rcx+20h]
0x18001a021  mov     rbx, r8
0x18001a024  mov     rdi, rdx
0x18001a027  mov     rbp, rcx
0x18001a02a  test    r8, r8
0x18001a02d  jz      short loc_18001A0A2
0x18001a02f  mov     rax, [rbx]
0x18001a032  cmp     rax, rbx
0x18001a035  jz      short loc_18001A0A2
0x18001a037  cmp     [rax+8], rbx
0x18001a03b  jnz     short loc_18001A09B
0x18001a03d  mov     rcx, [rax]
0x18001a040  cmp     [rcx+8], rax
0x18001a044  jnz     short loc_18001A09B
0x18001a046  mov     [rbx], rcx
0x18001a049  lea     r14, [rax-10h]
0x18001a04d  mov     [rcx+8], rbx
0x18001a051  mov     rcx, [r14+8]; hModule
0x18001a055  test    rcx, rcx
0x18001a058  jz      short loc_18001A02F
0x18001a05a  lea     rdx, aFreedumpstream; "FreeDumpStreams"
0x18001a061  call    cs:__imp_GetProcAddress
0x18001a067  test    rax, rax
0x18001a06a  jz      short loc_18001A074
0x18001a06c  mov     rcx, [r14]
0x18001a06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a074  mov     rcx, [r14+8]; hLibModule
0x18001a078  call    cs:__imp_FreeLibrary
0x18001a07e  mov     qword ptr [r14+8], 0
0x18001a086  mov     rdx, r14
0x18001a089  mov     rcx, [rbp+20h]
0x18001a08d  mov     rax, [rcx]
0x18001a090  mov     rax, [rax+18h]
0x18001a094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a099  jmp     short loc_18001A02F
0x18001a09b  mov     ecx, 3
0x18001a0a0  int     29h; Win8: RtlFailFast(ecx)
0x18001a0a2  lea     r14, [rdi+78h]
0x18001a0a6  mov     r15, [r14]
0x18001a0a9  cmp     r15, r14
0x18001a0ac  jz      short loc_18001A124
0x18001a0ae  lea     rsi, [rbp+20h]
0x18001a0b2  mov     rcx, [rsi]
0x18001a0b5  lea     rbx, [r15-90h]
0x18001a0bc  mov     rdx, [rbx+78h]
0x18001a0c0  mov     r15, [r15]
0x18001a0c3  mov     rax, [rcx]
0x18001a0c6  mov     rax, [rax+18h]
0x18001a0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0cf  mov     rdx, [rbx+50h]
0x18001a0d3  mov     qword ptr [rbx+78h], 0
0x18001a0db  mov     rcx, [rsi]
0x18001a0de  mov     rax, [rcx]
0x18001a0e1  mov     rax, [rax+18h]
0x18001a0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0ea  mov     rdx, [rbx+60h]
0x18001a0ee  mov     qword ptr [rbx+50h], 0
0x18001a0f6  mov     rcx, [rsi]
0x18001a0f9  mov     rax, [rcx]
0x18001a0fc  mov     rax, [rax+18h]
0x18001a100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a105  mov     qword ptr [rbx+60h], 0
0x18001a10d  mov     rdx, rbx
0x18001a110  mov     rcx, [rsi]
0x18001a113  mov     rax, [rcx]
0x18001a116  mov     rax, [rax+18h]
0x18001a11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a11f  cmp     r15, r14
0x18001a122  jnz     short loc_18001A0B2
0x18001a124  lea     r14, [rdi+88h]
0x18001a12b  mov     rbx, [r14]
0x18001a12e  cmp     rbx, r14
0x18001a131  jz      short loc_18001A155
0x18001a133  lea     rsi, [rbp+20h]
0x18001a137  mov     rcx, [rsi]
0x18001a13a  lea     rdx, [rbx-2E8h]
0x18001a141  mov     rbx, [rbx]
0x18001a144  mov     rax, [rcx]
0x18001a147  mov     rax, [rax+18h]
0x18001a14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a150  cmp     rbx, r14
0x18001a153  jnz     short loc_18001A137
0x18001a155  lea     r15, [rdi+68h]
0x18001a159  mov     r14, [r15]
0x18001a15c  cmp     r14, r15
0x18001a15f  jz      loc_18001A22C
0x18001a165  lea     rsi, [rbp+20h]
0x18001a169  lea     rbx, [r14-0B8h]
0x18001a170  mov     r14, [r14]
0x18001a173  cmp     qword ptr [rbx+8], 0
0x18001a178  jz      short loc_18001A1DB
0x18001a17a  cmp     dword ptr [rbx+18h], 0FFFFFFFFh
0x18001a17e  jz      short loc_18001A1BC
0x18001a180  mov     rcx, [rbp+10h]
0x18001a184  mov     rax, [rcx]
0x18001a187  mov     rax, [rax+0A0h]
0x18001a18e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a193  cmp     [rbx], eax
0x18001a195  jz      short loc_18001A1BC
0x18001a197  mov     rcx, [rbp+10h]
0x18001a19b  lea     r8, [rbx+0E0h]
0x18001a1a2  mov     rdx, [rbx+8]
0x18001a1a6  mov     rax, [rcx]
0x18001a1a9  mov     rax, [rax+0B0h]
0x18001a1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1b5  mov     dword ptr [rbx+18h], 0FFFFFFFFh
0x18001a1bc  mov     rcx, [rbp+10h]
0x18001a1c0  mov     rdx, [rbx+8]
0x18001a1c4  mov     rax, [rcx]
0x18001a1c7  mov     rax, [rax+98h]
0x18001a1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1d3  mov     qword ptr [rbx+8], 0
0x18001a1db  mov     rdx, [rbx+0C8h]
0x18001a1e2  test    rdx, rdx
0x18001a1e5  jz      short loc_18001A1F6
0x18001a1e7  mov     rcx, [rsi]
0x18001a1ea  mov     rax, [rcx]
0x18001a1ed  mov     rax, [rax+18h]
0x18001a1f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1f6  mov     rdx, [rbx+0D0h]
0x18001a1fd  test    rdx, rdx
0x18001a200  jz      short loc_18001A211
0x18001a202  mov     rcx, [rsi]
0x18001a205  mov     rax, [rcx]
0x18001a208  mov     rax, [rax+18h]
0x18001a20c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a211  mov     rcx, [rsi]
0x18001a214  mov     rdx, rbx
0x18001a217  mov     rax, [rcx]
0x18001a21a  mov     rax, [rax+18h]
0x18001a21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a223  cmp     r14, r15
0x18001a226  jnz     loc_18001A169
0x18001a22c  lea     r14, [rdi+98h]
0x18001a233  mov     rbx, [r14]
0x18001a236  jmp     short loc_18001A269
0x18001a238  lea     r15, [rbx-30h]
0x18001a23c  mov     rbx, [rbx]
0x18001a23f  mov     rdx, [r15+28h]
0x18001a243  test    rdx, rdx
0x18001a246  jz      short loc_18001A257
0x18001a248  mov     rcx, [rsi]
0x18001a24b  mov     rax, [rcx]
0x18001a24e  mov     rax, [rax+18h]
0x18001a252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a257  mov     rcx, [rsi]
0x18001a25a  mov     rdx, r15
0x18001a25d  mov     rax, [rcx]
0x18001a260  mov     rax, [rax+18h]
0x18001a264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a269  cmp     rbx, r14
0x18001a26c  jnz     short loc_18001A238
0x18001a26e  jmp     short loc_18001A291
0x18001a270  mov     rax, [rdx]
0x18001a273  mov     [rdi+1D78h], rax
0x18001a27a  mov     rax, [rdi+1D68h]
0x18001a281  mov     rcx, [rax+20h]
0x18001a285  mov     rax, [rcx]
0x18001a288  mov     rax, [rax+18h]
0x18001a28c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a291  mov     rdx, [rdi+1D78h]
0x18001a298  test    rdx, rdx
0x18001a29b  jnz     short loc_18001A270
0x18001a29d  mov     [rdi+1D80h], rdx
0x18001a2a4  jmp     short loc_18001A2C7
0x18001a2a6  mov     rax, [rdx]
0x18001a2a9  mov     [rdi+1D98h], rax
0x18001a2b0  mov     rax, [rdi+1D88h]
0x18001a2b7  mov     rcx, [rax+20h]
0x18001a2bb  mov     rax, [rcx]
0x18001a2be  mov     rax, [rax+18h]
0x18001a2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2c7  mov     rdx, [rdi+1D98h]
0x18001a2ce  test    rdx, rdx
0x18001a2d1  jnz     short loc_18001A2A6
0x18001a2d3  lea     r14, [rdi+1DA8h]
0x18001a2da  mov     [rdi+1DA0h], rdx
0x18001a2e1  mov     rbx, [r14]
0x18001a2e4  jmp     short loc_18001A317
0x18001a2e6  mov     r15, rbx
0x18001a2e9  mov     rbx, [rbx]
0x18001a2ec  mov     rcx, [r15+28h]; hObject
0x18001a2f0  test    rcx, rcx
0x18001a2f3  jz      short loc_18001A305
0x18001a2f5  call    cs:__imp_CloseHandle
0x18001a2fb  mov     rcx, [r15+20h]; lpFileName
0x18001a2ff  call    cs:__imp_DeleteFileW
0x18001a305  mov     rcx, [rsi]
0x18001a308  mov     rdx, r15
0x18001a30b  mov     rax, [rcx]
0x18001a30e  mov     rax, [rax+18h]
0x18001a312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a317  cmp     rbx, r14
0x18001a31a  jnz     short loc_18001A2E6
0x18001a31c  jmp     short loc_18001A34D
0x18001a31e  mov     rax, [rbx]
0x18001a321  mov     [rdi+11DE0h], rax
0x18001a328  mov     rcx, [rsi]
0x18001a32b  mov     rdx, [rbx+8]
0x18001a32f  mov     rax, [rcx]
0x18001a332  mov     rax, [rax+18h]
0x18001a336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a33b  mov     rcx, [rsi]
0x18001a33e  mov     rdx, rbx
0x18001a341  mov     rax, [rcx]
0x18001a344  mov     rax, [rax+18h]
0x18001a348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a34d  mov     rbx, [rdi+11DE0h]
0x18001a354  test    rbx, rbx
0x18001a357  jnz     short loc_18001A31E
0x18001a359  mov     rdx, [rdi+11DB8h]
0x18001a360  test    rdx, rdx
0x18001a363  jz      short loc_18001A374
0x18001a365  mov     rcx, [rsi]
0x18001a368  mov     rax, [rcx]
0x18001a36b  mov     rax, [rax+18h]
0x18001a36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a374  mov     rdx, [rdi+11DC8h]
0x18001a37b  test    rdx, rdx
0x18001a37e  jz      short loc_18001A38F
0x18001a380  mov     rcx, [rsi]
0x18001a383  mov     rax, [rcx]
0x18001a386  mov     rax, [rax+18h]
0x18001a38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a38f  mov     rdx, [rdi+11DD0h]
0x18001a396  test    rdx, rdx
0x18001a399  jz      short loc_18001A3AA
0x18001a39b  mov     rcx, [rsi]
0x18001a39e  mov     rax, [rcx]
0x18001a3a1  mov     rax, [rax+18h]
0x18001a3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3aa  mov     rdx, [rdi+11DE8h]
0x18001a3b1  test    rdx, rdx
0x18001a3b4  jz      short loc_18001A3C9
0x18001a3b6  mov     rcx, [rbp+10h]
0x18001a3ba  mov     rax, [rcx]
0x18001a3bd  mov     rax, [rax+220h]
0x18001a3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3c9  mov     rcx, [rsi]
0x18001a3cc  mov     rdx, rdi
0x18001a3cf  mov     rax, [rcx]
0x18001a3d2  mov     rax, [rax+18h]
0x18001a3d6  add     rsp, 28h
0x18001a3da  pop     r15
0x18001a3dc  pop     r14
0x18001a3de  pop     rdi
0x18001a3df  pop     rsi
0x18001a3e0  pop     rbp
0x18001a3e1  pop     rbx
0x18001a3e2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
