# STTABLE::Insert(STTABLE_ITEM *)

- ea: `0x180005e7c`
- end: `0x18000606c`
- name: `?Insert@STTABLE@@QEAAJPEAVSTTABLE_ITEM@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(STTABLE *__hidden this, struct STTABLE_ITEM *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005168`
- `0x1800057cc`

## callees

- `0x180005e7c`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006018`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006053`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006018`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006053`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f1b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005f3a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005f3a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006004`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000603c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006004`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000603c`

## pseudocode

```c
__int64 __fastcall STTABLE::Insert(STTABLE *this, struct STTABLE_ITEM *a2)
{
  __int64 (__fastcall *v2)(char *); // rax
  _DWORD *v3; // r15
  unsigned __int8 **v4; // rsi
  unsigned int v7; // r8d
  unsigned __int8 *v8; // rcx
  __int64 v9; // rbx
  __int64 *v10; // r14
  __int64 *i; // rbp
  unsigned int (__fastcall *v12)(char *, __int64); // rax
  unsigned int v13; // esi
  __int64 v14; // r8
  unsigned __int8 *v15; // rax
  __int64 v16; // r8
  int v17; // ecx
  int v18; // edx
  _QWORD *v19; // rax
  int v20; // eax
  int v21; // eax

  v2 = (__int64 (__fastcall *)(char *))*((_QWORD *)this + 22);
  v3 = (_DWORD *)((char *)a2 + 48);
  v4 = (unsigned __int8 **)((char *)a2 + 40);
  if ( v2 )
  {
    v7 = v2((char *)a2 + 32);
  }
  else
  {
    v7 = 0;
    (*v4)[*v3] = 0;
    (*v4)[*v3 + 1] = 0;
    v8 = *v4;
    if ( *v4 )
    {
      while ( *v8 )
        v7 += (char)*v8++ | 0x20;
    }
  }
  v9 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * (v7 % *((_DWORD *)this + 26)));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  _InterlockedIncrement((volatile signed __int32 *)this + 30);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 40));
  *(_DWORD *)(v9 + 28) = 1;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 32), 0) > 0 )
    WaitForSingleObject(*(HANDLE *)(v9 + 80), 0xFFFFFFFF);
  v10 = (__int64 *)(v9 + 8);
  *(_DWORD *)(v9 + 32) = -1;
  for ( i = *(__int64 **)(v9 + 8); i != v10; i = (__int64 *)*i )
  {
    v12 = *(unsigned int (__fastcall **)(char *, __int64))(v9 + 88);
    if ( v12 )
    {
      if ( v12((char *)a2 + 32, (__int64)(i + 3)) )
        goto LABEL_12;
    }
    else
    {
      *(_BYTE *)(*((unsigned int *)i + 10) + i[4]) = 0;
      *(_BYTE *)((unsigned int)(*((_DWORD *)i + 10) + 1) + i[4]) = 0;
      v14 = i[4];
      (*v4)[*v3] = 0;
      (*v4)[*v3 + 1] = 0;
      v15 = *v4;
      v16 = v14 - (_QWORD)*v4;
      do
      {
        v17 = v15[v16];
        v18 = *v15 - v17;
        if ( v18 )
          break;
        ++v15;
      }
      while ( v17 );
      if ( !v18 )
      {
LABEL_12:
        v13 = -2147024713;
        goto LABEL_20;
      }
    }
  }
  v13 = 0;
  _InterlockedIncrement((volatile signed __int32 *)a2 + 6);
  v19 = *(_QWORD **)(v9 + 16);
  *((_QWORD *)a2 + 1) = v10;
  *((_QWORD *)a2 + 2) = v19;
  *v19 = (char *)a2 + 8;
  *(_QWORD *)(v9 + 16) = (char *)a2 + 8;
LABEL_20:
  v20 = _InterlockedDecrement((volatile signed __int32 *)(v9 + 32));
  if ( v20 < 0 )
  {
    *(_QWORD *)(v9 + 28) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 40));
  }
  else if ( *(_DWORD *)(v9 + 28) && !v20 )
  {
    SetEvent(*(HANDLE *)(v9 + 80));
  }
  v21 = _InterlockedDecrement((volatile signed __int32 *)this + 30);
  if ( v21 < 0 )
  {
    *(_QWORD *)((char *)this + 116) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  }
  else if ( *((_DWORD *)this + 29) && !v21 )
  {
    SetEvent(*((HANDLE *)this + 21));
  }
  return v13;
}

```

## disassembly

```asm
0x180005e7c  push    rbx
0x180005e7e  push    rbp
0x180005e7f  push    rsi
0x180005e80  push    rdi
0x180005e81  push    r12
0x180005e83  push    r13
0x180005e85  push    r14
0x180005e87  push    r15
0x180005e89  sub     rsp, 28h
0x180005e8d  mov     rax, [rcx+0B0h]
0x180005e94  lea     r15, [rdx+30h]
0x180005e98  lea     rsi, [rdx+28h]
0x180005e9c  mov     r12, rdx
0x180005e9f  mov     rdi, rcx
0x180005ea2  test    rax, rax
0x180005ea5  jz      short loc_180005EB5
0x180005ea7  lea     rcx, [rdx+20h]
0x180005eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eb0  mov     r8d, eax
0x180005eb3  jmp     short loc_180005EEA
0x180005eb5  mov     ecx, [r15]
0x180005eb8  xor     r8d, r8d
0x180005ebb  mov     rax, [rsi]
0x180005ebe  mov     byte ptr [rcx+rax], 0
0x180005ec2  mov     ecx, [r15]
0x180005ec5  mov     rax, [rsi]
0x180005ec8  inc     ecx
0x180005eca  mov     byte ptr [rcx+rax], 0
0x180005ece  mov     rcx, [rsi]
0x180005ed1  test    rcx, rcx
0x180005ed4  jz      short loc_180005EEA
0x180005ed6  jmp     short loc_180005EE4
0x180005ed8  movsx   eax, al
0x180005edb  or      eax, 20h
0x180005ede  add     r8d, eax
0x180005ee1  inc     rcx
0x180005ee4  mov     al, [rcx]
0x180005ee6  test    al, al
0x180005ee8  jnz     short loc_180005ED8
0x180005eea  xor     edx, edx
0x180005eec  lea     rbp, [rdi+80h]
0x180005ef3  mov     eax, r8d
0x180005ef6  mov     rcx, rbp; lpCriticalSection
0x180005ef9  div     dword ptr [rdi+68h]
0x180005efc  mov     rax, [rdi+10h]
0x180005f00  mov     rbx, [rax+rdx*8]
0x180005f04  call    cs:__imp_EnterCriticalSection
0x180005f0a  lock inc dword ptr [rdi+78h]
0x180005f0e  mov     rcx, rbp; lpCriticalSection
0x180005f11  call    cs:__imp_LeaveCriticalSection
0x180005f17  lea     rcx, [rbx+28h]; lpCriticalSection
0x180005f1b  call    cs:__imp_EnterCriticalSection
0x180005f21  xor     eax, eax
0x180005f23  mov     dword ptr [rbx+1Ch], 1
0x180005f2a  lock xadd [rbx+20h], eax
0x180005f2f  test    eax, eax
0x180005f31  jle     short loc_180005F40
0x180005f33  mov     rcx, [rbx+50h]; hHandle
0x180005f37  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005f3a  call    cs:__imp_WaitForSingleObject
0x180005f40  lea     r14, [rbx+8]
0x180005f44  mov     dword ptr [rbx+20h], 0FFFFFFFFh
0x180005f4b  mov     rbp, [r14]
0x180005f4e  jmp     short loc_180005FC5
0x180005f50  mov     rax, [rbx+58h]
0x180005f54  lea     rdx, [rbp+18h]
0x180005f58  test    rax, rax
0x180005f5b  jz      short loc_180005F72
0x180005f5d  lea     rcx, [r12+20h]
0x180005f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f67  test    eax, eax
0x180005f69  jz      short loc_180005FC1
0x180005f6b  mov     esi, 800700B7h
0x180005f70  jmp     short loc_180005FE9
0x180005f72  mov     ecx, [rdx+10h]
0x180005f75  mov     rax, [rdx+8]
0x180005f79  mov     byte ptr [rcx+rax], 0
0x180005f7d  mov     ecx, [rdx+10h]
0x180005f80  mov     rax, [rdx+8]
0x180005f84  inc     ecx
0x180005f86  mov     byte ptr [rcx+rax], 0
0x180005f8a  mov     ecx, [r15]
0x180005f8d  mov     rax, [rsi]
0x180005f90  mov     r8, [rdx+8]
0x180005f94  mov     byte ptr [rcx+rax], 0
0x180005f98  mov     ecx, [r15]
0x180005f9b  mov     rax, [rsi]
0x180005f9e  inc     ecx
0x180005fa0  mov     byte ptr [rcx+rax], 0
0x180005fa4  mov     rax, [rsi]
0x180005fa7  sub     r8, rax
0x180005faa  movzx   edx, byte ptr [rax]
0x180005fad  movzx   ecx, byte ptr [rax+r8]
0x180005fb2  sub     edx, ecx
0x180005fb4  jnz     short loc_180005FBD
0x180005fb6  inc     rax
0x180005fb9  test    ecx, ecx
0x180005fbb  jnz     short loc_180005FAA
0x180005fbd  test    edx, edx
0x180005fbf  jz      short loc_180005F6B
0x180005fc1  mov     rbp, [rbp+0]
0x180005fc5  cmp     rbp, r14
0x180005fc8  jnz     short loc_180005F50
0x180005fca  xor     esi, esi
0x180005fcc  lock inc dword ptr [r12+18h]
0x180005fd2  mov     rax, [r14+8]
0x180005fd6  lea     rcx, [r12+8]
0x180005fdb  mov     [rcx], r14
0x180005fde  mov     [rcx+8], rax
0x180005fe2  mov     [rax], rcx
0x180005fe5  mov     [r14+8], rcx
0x180005fe9  or      eax, 0FFFFFFFFh
0x180005fec  lock xadd [rbx+20h], eax
0x180005ff1  sub     eax, 1
0x180005ff4  js      short loc_18000600C
0x180005ff6  cmp     dword ptr [rbx+1Ch], 0
0x180005ffa  jz      short loc_18000601E
0x180005ffc  test    eax, eax
0x180005ffe  jnz     short loc_18000601E
0x180006000  mov     rcx, [rbx+50h]; hEvent
0x180006004  call    cs:__imp_SetEvent
0x18000600a  jmp     short loc_18000601E
0x18000600c  lea     rcx, [rbx+28h]; lpCriticalSection
0x180006010  mov     qword ptr [rbx+1Ch], 0
0x180006018  call    cs:__imp_LeaveCriticalSection
0x18000601e  or      eax, 0FFFFFFFFh
0x180006021  lock xadd [rdi+78h], eax
0x180006026  sub     eax, 1
0x180006029  js      short loc_180006044
0x18000602b  cmp     dword ptr [rdi+74h], 0
0x18000602f  jz      short loc_180006059
0x180006031  test    eax, eax
0x180006033  jnz     short loc_180006059
0x180006035  mov     rcx, [rdi+0A8h]; hEvent
0x18000603c  call    cs:__imp_SetEvent
0x180006042  jmp     short loc_180006059
0x180006044  lea     rcx, [rdi+80h]; lpCriticalSection
0x18000604b  mov     qword ptr [rdi+74h], 0
0x180006053  call    cs:__imp_LeaveCriticalSection
0x180006059  mov     eax, esi
0x18000605b  add     rsp, 28h
0x18000605f  pop     r15
0x180006061  pop     r14
0x180006063  pop     r13
0x180006065  pop     r12
0x180006067  pop     rdi
0x180006068  pop     rsi
0x180006069  pop     rbp
0x18000606a  pop     rbx
0x18000606b  retn
```
