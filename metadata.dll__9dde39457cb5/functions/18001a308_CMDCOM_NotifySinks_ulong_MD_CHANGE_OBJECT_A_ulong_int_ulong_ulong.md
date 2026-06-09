# CMDCOM::NotifySinks(ulong,_MD_CHANGE_OBJECT_A *,ulong,int,ulong,ulong)

- ea: `0x18001a308`
- end: `0x18001a57e`
- name: `?NotifySinks@CMDCOM@@AEAAJKPEAU_MD_CHANGE_OBJECT_A@@KHKK@Z`
- size: `630`
- prototype: `__int64 __fastcall(CMDCOM *__hidden this, unsigned int, struct _MD_CHANGE_OBJECT_A *, unsigned int, int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001a584`
- `0x18001a93c`
- `0x18001a9b0`

## callees

- `0x180008a08`
- `0x18001a308`
- `0x180028270`
- `0x180031010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001a37b`
- `KERNEL32!LeaveCriticalSection` at `0x18001a37b`
- `KERNEL32!EnterCriticalSection` at `0x18001a348`
- `KERNEL32!EnterCriticalSection` at `0x18001a348`
- `IisRTL!ScheduleWorkItem` at `0x18001a36e`
- `IisRTL!ScheduleWorkItem` at `0x18001a36e`

## pseudocode

```c
__int64 __fastcall CMDCOM::NotifySinks(
        CMDCOM *this,
        unsigned int a2,
        struct _MD_CHANGE_OBJECT_A *a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        unsigned int a7)
{
  unsigned int v8; // r12d
  int v10; // esi
  COConnectionPoint *v11; // r15
  int v12; // eax
  int (__fastcall ****v13)(_QWORD, GUID *, __int64 *); // r14
  unsigned int v14; // edi
  unsigned int v15; // ebx
  struct _MD_CHANGE_OBJECT_A *v16; // rsi
  unsigned int v17; // r15d
  struct _MD_CHANGE_OBJECT_A *v18; // rsi
  unsigned int v19; // r15d
  unsigned int i; // ebx
  int (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v23; // [rsp+30h] [rbp-20h] BYREF
  void *Block; // [rsp+38h] [rbp-18h] BYREF
  COConnectionPoint *v25; // [rsp+40h] [rbp-10h]
  __int64 v26; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v27; // [rsp+98h] [rbp+48h]
  struct _MD_CHANGE_OBJECT_A *v28; // [rsp+A0h] [rbp+50h]

  v28 = a3;
  v27 = a2;
  Block = 0;
  v8 = 0;
  a7 = 0;
  v23 = 0;
  v26 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  if ( *((_DWORD *)this + 13) )
  {
    ++*((_DWORD *)this + 16);
    if ( !*((_DWORD *)this + 14) )
      *((_DWORD *)this + 14) = ScheduleWorkItem(
                                 (void (*)(void *))CMDCOM::MetabaseLazyFlush,
                                 this,
                                 *((_DWORD *)this + 15),
                                 0);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  v10 = a5;
  v11 = *(COConnectionPoint **)((char *)this + (a5 != 0 ? 8 : 0) + 32);
  v25 = v11;
  if ( v11 )
  {
    (*(void (__fastcall **)(COConnectionPoint *))(*(_QWORD *)v11 + 8LL))(v11);
    v12 = COConnectionPoint::InternalEnumSinks(v11, (struct tagCONNECTDATA **)&Block, &a7);
    v13 = (int (__fastcall ****)(_QWORD, GUID *, __int64 *))Block;
    v8 = v12;
    v14 = a7;
    if ( v12 >= 0 && a7 )
    {
      v15 = 0;
      if ( v10 )
      {
        v16 = v28;
        v17 = v27;
        do
        {
          if ( (**v13[2 * v15])(v13[2 * v15], &IID_IMDCOMSINK_W, &v26) >= 0 )
          {
            if ( a6 )
            {
              if ( a6 == 1 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 32LL))(v26);
              }
              else if ( a6 == 2 )
              {
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 40LL))(v26, 0);
              }
            }
            else
            {
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD, struct _MD_CHANGE_OBJECT_A *))(*(_QWORD *)v26 + 24LL))(
                v26,
                v17,
                a4,
                v16);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
            v26 = 0;
          }
          ++v15;
        }
        while ( v15 < v14 );
      }
      else
      {
        v18 = v28;
        v19 = v27;
        do
        {
          if ( (**v13[2 * v15])(v13[2 * v15], &IID_IMDCOMSINK_A, &v23) >= 0 )
          {
            if ( a6 )
            {
              if ( a6 == 1 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 32LL))(v23);
            }
            else
            {
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD, struct _MD_CHANGE_OBJECT_A *))(*(_QWORD *)v23 + 24LL))(
                v23,
                v19,
                a4,
                v18);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            v23 = 0;
          }
          ++v15;
        }
        while ( v15 < v14 );
      }
      v11 = v25;
    }
    if ( v13 )
    {
      for ( i = 0; i < v14; ++i )
      {
        v21 = v13[2 * i];
        if ( v21 )
        {
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v21)[2])(v21);
          v13[2 * i] = 0;
        }
      }
      operator delete(v13);
    }
    (*(void (__fastcall **)(COConnectionPoint *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return v8;
}

```

## disassembly

```asm
0x18001a308  mov     [rsp-38h+arg_18], rbx
0x18001a30d  mov     [rsp-38h+arg_10], r8
0x18001a312  mov     [rsp-38h+arg_8], edx
0x18001a316  push    rbp
0x18001a317  push    rsi
0x18001a318  push    rdi
0x18001a319  push    r12
0x18001a31b  push    r13
0x18001a31d  push    r14
0x18001a31f  push    r15
0x18001a321  mov     rbp, rsp
0x18001a324  sub     rsp, 50h
0x18001a328  xor     r14d, r14d
0x18001a32b  mov     rbx, rcx
0x18001a32e  add     rcx, 50h ; 'P'; lpCriticalSection
0x18001a332  mov     [rbp+Block], r14
0x18001a336  mov     r12d, r14d
0x18001a339  mov     [rbp+arg_30], r14d
0x18001a33d  mov     [rbp+var_20], r14
0x18001a341  mov     r13d, r9d
0x18001a344  mov     [rbp+arg_0], r14
0x18001a348  call    cs:__imp_EnterCriticalSection
0x18001a34e  cmp     [rbx+34h], r14d
0x18001a352  jz      short loc_18001A377
0x18001a354  inc     dword ptr [rbx+40h]
0x18001a357  cmp     [rbx+38h], r14d
0x18001a35b  jnz     short loc_18001A377
0x18001a35d  mov     r8d, [rbx+3Ch]
0x18001a361  lea     rcx, ?MetabaseLazyFlush@CMDCOM@@CAXPEAX@Z; CMDCOM::MetabaseLazyFlush(void *)
0x18001a368  xor     r9d, r9d
0x18001a36b  mov     rdx, rbx
0x18001a36e  call    cs:__imp_?ScheduleWorkItem@@YAKP6AXPEAX@Z0KH@Z; ScheduleWorkItem(void (*)(void *),void *,ulong,int)
0x18001a374  mov     [rbx+38h], eax
0x18001a377  lea     rcx, [rbx+50h]; lpCriticalSection
0x18001a37b  call    cs:__imp_LeaveCriticalSection
0x18001a381  mov     esi, [rbp+arg_20]
0x18001a384  mov     eax, esi
0x18001a386  neg     eax
0x18001a388  sbb     rcx, rcx
0x18001a38b  and     ecx, 8
0x18001a38e  mov     r15, [rcx+rbx+20h]
0x18001a393  mov     [rbp+var_10], r15
0x18001a397  test    r15, r15
0x18001a39a  jz      loc_18001A563
0x18001a3a0  mov     rax, [r15]
0x18001a3a3  mov     rcx, r15
0x18001a3a6  mov     rax, [rax+8]
0x18001a3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3af  lea     r8, [rbp+arg_30]; unsigned int *
0x18001a3b3  mov     rcx, r15; this
0x18001a3b6  lea     rdx, [rbp+Block]; struct tagCONNECTDATA **
0x18001a3ba  call    ?InternalEnumSinks@COConnectionPoint@@QEAAJPEAPEAUtagCONNECTDATA@@PEAK@Z; COConnectionPoint::InternalEnumSinks(tagCONNECTDATA * *,ulong *)
0x18001a3bf  mov     r14, [rbp+Block]
0x18001a3c3  mov     r12d, eax
0x18001a3c6  mov     edi, [rbp+arg_30]
0x18001a3c9  test    eax, eax
0x18001a3cb  js      loc_18001A519
0x18001a3d1  test    edi, edi
0x18001a3d3  jz      loc_18001A519
0x18001a3d9  xor     ebx, ebx
0x18001a3db  test    esi, esi
0x18001a3dd  jz      loc_18001A48D
0x18001a3e3  test    edi, edi
0x18001a3e5  jz      loc_18001A519
0x18001a3eb  mov     rsi, [rbp+arg_10]
0x18001a3ef  mov     r15d, [rbp+arg_8]
0x18001a3f3  mov     eax, ebx
0x18001a3f5  lea     r8, [rbp+arg_0]
0x18001a3f9  add     rax, rax
0x18001a3fc  lea     rdx, IID_IMDCOMSINK_W
0x18001a403  mov     rcx, [r14+rax*8]
0x18001a407  mov     rax, [rcx]
0x18001a40a  mov     rax, [rax]
0x18001a40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a412  test    eax, eax
0x18001a414  js      short loc_18001A47E
0x18001a416  mov     eax, [rbp+arg_28]
0x18001a419  test    eax, eax
0x18001a41b  jz      short loc_18001A44D
0x18001a41d  sub     eax, 1
0x18001a420  jz      short loc_18001A43B
0x18001a422  cmp     eax, 1
0x18001a425  jnz     short loc_18001A466
0x18001a427  mov     rcx, [rbp+arg_0]
0x18001a42b  xor     edx, edx
0x18001a42d  mov     rax, [rcx]
0x18001a430  mov     rax, [rax+28h]
0x18001a434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a439  jmp     short loc_18001A466
0x18001a43b  mov     rcx, [rbp+arg_0]
0x18001a43f  mov     rax, [rcx]
0x18001a442  mov     rax, [rax+20h]
0x18001a446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a44b  jmp     short loc_18001A466
0x18001a44d  mov     rcx, [rbp+arg_0]
0x18001a451  mov     r9, rsi
0x18001a454  mov     r8d, r13d
0x18001a457  mov     edx, r15d
0x18001a45a  mov     rax, [rcx]
0x18001a45d  mov     rax, [rax+18h]
0x18001a461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a466  mov     rcx, [rbp+arg_0]
0x18001a46a  mov     rax, [rcx]
0x18001a46d  mov     rax, [rax+10h]
0x18001a471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a476  mov     [rbp+arg_0], 0
0x18001a47e  inc     ebx
0x18001a480  cmp     ebx, edi
0x18001a482  jb      loc_18001A3F3
0x18001a488  jmp     loc_18001A515
0x18001a48d  test    edi, edi
0x18001a48f  jz      loc_18001A519
0x18001a495  mov     rsi, [rbp+arg_10]
0x18001a499  mov     r15d, [rbp+arg_8]
0x18001a49d  mov     eax, ebx
0x18001a49f  lea     r8, [rbp+var_20]
0x18001a4a3  add     rax, rax
0x18001a4a6  lea     rdx, IID_IMDCOMSINK_A
0x18001a4ad  mov     rcx, [r14+rax*8]
0x18001a4b1  mov     rax, [rcx]
0x18001a4b4  mov     rax, [rax]
0x18001a4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4bc  test    eax, eax
0x18001a4be  js      short loc_18001A50F
0x18001a4c0  mov     eax, [rbp+arg_28]
0x18001a4c3  test    eax, eax
0x18001a4c5  jz      short loc_18001A4DE
0x18001a4c7  cmp     eax, 1
0x18001a4ca  jnz     short loc_18001A4F7
0x18001a4cc  mov     rcx, [rbp+var_20]
0x18001a4d0  mov     rax, [rcx]
0x18001a4d3  mov     rax, [rax+20h]
0x18001a4d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4dc  jmp     short loc_18001A4F7
0x18001a4de  mov     rcx, [rbp+var_20]
0x18001a4e2  mov     r9, rsi
0x18001a4e5  mov     r8d, r13d
0x18001a4e8  mov     edx, r15d
0x18001a4eb  mov     rax, [rcx]
0x18001a4ee  mov     rax, [rax+18h]
0x18001a4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4f7  mov     rcx, [rbp+var_20]
0x18001a4fb  mov     rax, [rcx]
0x18001a4fe  mov     rax, [rax+10h]
0x18001a502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a507  mov     [rbp+var_20], 0
0x18001a50f  inc     ebx
0x18001a511  cmp     ebx, edi
0x18001a513  jb      short loc_18001A49D
0x18001a515  mov     r15, [rbp+var_10]
0x18001a519  test    r14, r14
0x18001a51c  jz      short loc_18001A554
0x18001a51e  xor     ebx, ebx
0x18001a520  test    edi, edi
0x18001a522  jz      short loc_18001A54C
0x18001a524  mov     esi, ebx
0x18001a526  add     rsi, rsi
0x18001a529  mov     rcx, [r14+rsi*8]
0x18001a52d  test    rcx, rcx
0x18001a530  jz      short loc_18001A546
0x18001a532  mov     rax, [rcx]
0x18001a535  mov     rax, [rax+10h]
0x18001a539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a53e  mov     qword ptr [r14+rsi*8], 0
0x18001a546  inc     ebx
0x18001a548  cmp     ebx, edi
0x18001a54a  jb      short loc_18001A524
0x18001a54c  mov     rcx, r14; Block
0x18001a54f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a554  mov     rax, [r15]
0x18001a557  mov     rcx, r15
0x18001a55a  mov     rax, [rax+10h]
0x18001a55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a563  mov     rbx, [rsp+50h+arg_18]
0x18001a56b  mov     eax, r12d
0x18001a56e  add     rsp, 50h
0x18001a572  pop     r15
0x18001a574  pop     r14
0x18001a576  pop     r13
0x18001a578  pop     r12
0x18001a57a  pop     rdi
0x18001a57b  pop     rsi
0x18001a57c  pop     rbp
0x18001a57d  retn
```
