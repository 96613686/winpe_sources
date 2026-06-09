# STTABLE::GetItem(STBUFF *,STTABLE_ITEM * *)

- ea: `0x1800053b0`
- end: `0x18000558f`
- name: `?GetItem@STTABLE@@QEAAJPEAVSTBUFF@@PEAPEAVSTTABLE_ITEM@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(STTABLE *__hidden this, struct STBUFF *, struct STTABLE_ITEM **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005168`
- `0x1800057cc`

## callees

- `0x1800053b0`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005448`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005460`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005528`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000556b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005448`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005460`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005528`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000556b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000543b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005452`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000543b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005452`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005514`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005554`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005514`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005554`

## pseudocode

```c
__int64 __fastcall STTABLE::GetItem(STTABLE *this, struct STBUFF *a2, struct STTABLE_ITEM **a3)
{
  __int64 (__fastcall *v3)(struct STBUFF *); // rax
  _DWORD *v4; // r14
  unsigned __int8 **v5; // rsi
  unsigned int v8; // r8d
  unsigned __int8 *v9; // rcx
  __int64 v10; // rdi
  _QWORD *i; // r12
  unsigned int (__fastcall *v12)(struct STBUFF *, _QWORD *); // rax
  volatile signed __int32 *v13; // rbp
  int v14; // esi
  __int64 v15; // r8
  unsigned __int8 *v16; // rax
  __int64 v17; // r8
  int v18; // ecx
  int v19; // edx
  int v20; // eax
  struct STTABLE_ITEM *v21; // rdi
  int v22; // eax

  v3 = (__int64 (__fastcall *)(struct STBUFF *))*((_QWORD *)this + 22);
  v4 = (_DWORD *)((char *)a2 + 16);
  v5 = (unsigned __int8 **)((char *)a2 + 8);
  if ( v3 )
  {
    v8 = v3(a2);
  }
  else
  {
    v8 = 0;
    (*v5)[*v4] = 0;
    (*v5)[*v4 + 1] = 0;
    v9 = *v5;
    if ( *v5 )
    {
      while ( *v9 )
        v8 += (char)*v9++ | 0x20;
    }
  }
  v10 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * (v8 % *((_DWORD *)this + 26)));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  _InterlockedIncrement((volatile signed __int32 *)this + 30);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 40));
  _InterlockedIncrement((volatile signed __int32 *)(v10 + 32));
  LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 40));
  for ( i = *(_QWORD **)(v10 + 8); i != (_QWORD *)(v10 + 8); i = (_QWORD *)*i )
  {
    v12 = *(unsigned int (__fastcall **)(struct STBUFF *, _QWORD *))(v10 + 88);
    v13 = (volatile signed __int32 *)(i - 1);
    if ( v12 )
    {
      if ( v12(a2, i + 3) )
        goto LABEL_10;
    }
    else
    {
      *(_BYTE *)(*((unsigned int *)i + 10) + i[4]) = 0;
      *(_BYTE *)((unsigned int)(*((_DWORD *)i + 10) + 1) + i[4]) = 0;
      v15 = i[4];
      (*v5)[*v4] = 0;
      (*v5)[*v4 + 1] = 0;
      v16 = *v5;
      v17 = v15 - (_QWORD)*v5;
      do
      {
        v18 = v16[v17];
        v19 = *v16 - v18;
        if ( v19 )
          break;
        ++v16;
      }
      while ( v18 );
      if ( !v19 )
      {
LABEL_10:
        v14 = 0;
        _InterlockedIncrement(v13 + 6);
        goto LABEL_18;
      }
    }
  }
  v13 = 0;
  v14 = -2147024894;
LABEL_18:
  v20 = _InterlockedDecrement((volatile signed __int32 *)(v10 + 32));
  if ( v20 < 0 )
  {
    *(_QWORD *)(v10 + 28) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 40));
  }
  else if ( *(_DWORD *)(v10 + 28) && !v20 )
  {
    SetEvent(*(HANDLE *)(v10 + 80));
  }
  v21 = 0;
  if ( v14 >= 0 )
    v21 = (struct STTABLE_ITEM *)v13;
  v22 = _InterlockedDecrement((volatile signed __int32 *)this + 30);
  if ( v22 < 0 )
  {
    *(_QWORD *)((char *)this + 116) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  }
  else if ( *((_DWORD *)this + 29) && !v22 )
  {
    SetEvent(*((HANDLE *)this + 21));
  }
  *a3 = v21;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800053b0  mov     [rsp+arg_10], r8
0x1800053b5  push    rbx
0x1800053b6  push    rbp
0x1800053b7  push    rsi
0x1800053b8  push    rdi
0x1800053b9  push    r12
0x1800053bb  push    r13
0x1800053bd  push    r14
0x1800053bf  push    r15
0x1800053c1  sub     rsp, 28h
0x1800053c5  mov     rax, [rcx+0B0h]
0x1800053cc  lea     r14, [rdx+10h]
0x1800053d0  lea     rsi, [rdx+8]
0x1800053d4  mov     r15, rdx
0x1800053d7  mov     rbx, rcx
0x1800053da  test    rax, rax
0x1800053dd  jz      short loc_1800053EC
0x1800053df  mov     rcx, rdx
0x1800053e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053e7  mov     r8d, eax
0x1800053ea  jmp     short loc_180005421
0x1800053ec  mov     ecx, [r14]
0x1800053ef  xor     r8d, r8d
0x1800053f2  mov     rax, [rsi]
0x1800053f5  mov     byte ptr [rcx+rax], 0
0x1800053f9  mov     ecx, [r14]
0x1800053fc  mov     rax, [rsi]
0x1800053ff  inc     ecx
0x180005401  mov     byte ptr [rcx+rax], 0
0x180005405  mov     rcx, [rsi]
0x180005408  test    rcx, rcx
0x18000540b  jz      short loc_180005421
0x18000540d  jmp     short loc_18000541B
0x18000540f  movsx   eax, al
0x180005412  or      eax, 20h
0x180005415  add     r8d, eax
0x180005418  inc     rcx
0x18000541b  mov     al, [rcx]
0x18000541d  test    al, al
0x18000541f  jnz     short loc_18000540F
0x180005421  xor     edx, edx
0x180005423  lea     rbp, [rbx+80h]
0x18000542a  mov     eax, r8d
0x18000542d  mov     rcx, rbp; lpCriticalSection
0x180005430  div     dword ptr [rbx+68h]
0x180005433  mov     rax, [rbx+10h]
0x180005437  mov     rdi, [rax+rdx*8]
0x18000543b  call    cs:__imp_EnterCriticalSection
0x180005441  lock inc dword ptr [rbx+78h]
0x180005445  mov     rcx, rbp; lpCriticalSection
0x180005448  call    cs:__imp_LeaveCriticalSection
0x18000544e  lea     rcx, [rdi+28h]; lpCriticalSection
0x180005452  call    cs:__imp_EnterCriticalSection
0x180005458  lock inc dword ptr [rdi+20h]
0x18000545c  lea     rcx, [rdi+28h]; lpCriticalSection
0x180005460  call    cs:__imp_LeaveCriticalSection
0x180005466  lea     r13, [rdi+8]
0x18000546a  mov     r12, [r13+0]
0x18000546e  jmp     short loc_1800054E9
0x180005470  mov     rax, [rdi+58h]
0x180005474  lea     rbp, [r12-8]
0x180005479  lea     rdx, [rbp+20h]
0x18000547d  test    rax, rax
0x180005480  jz      short loc_180005496
0x180005482  mov     rcx, r15
0x180005485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000548a  test    eax, eax
0x18000548c  jz      short loc_1800054E5
0x18000548e  xor     esi, esi
0x180005490  lock inc dword ptr [rbp+18h]
0x180005494  jmp     short loc_1800054F5
0x180005496  mov     ecx, [rdx+10h]
0x180005499  mov     rax, [rdx+8]
0x18000549d  mov     byte ptr [rcx+rax], 0
0x1800054a1  mov     ecx, [rdx+10h]
0x1800054a4  mov     rax, [rdx+8]
0x1800054a8  inc     ecx
0x1800054aa  mov     byte ptr [rcx+rax], 0
0x1800054ae  mov     ecx, [r14]
0x1800054b1  mov     rax, [rsi]
0x1800054b4  mov     r8, [rdx+8]
0x1800054b8  mov     byte ptr [rcx+rax], 0
0x1800054bc  mov     ecx, [r14]
0x1800054bf  mov     rax, [rsi]
0x1800054c2  inc     ecx
0x1800054c4  mov     byte ptr [rcx+rax], 0
0x1800054c8  mov     rax, [rsi]
0x1800054cb  sub     r8, rax
0x1800054ce  movzx   edx, byte ptr [rax]
0x1800054d1  movzx   ecx, byte ptr [rax+r8]
0x1800054d6  sub     edx, ecx
0x1800054d8  jnz     short loc_1800054E1
0x1800054da  inc     rax
0x1800054dd  test    ecx, ecx
0x1800054df  jnz     short loc_1800054CE
0x1800054e1  test    edx, edx
0x1800054e3  jz      short loc_18000548E
0x1800054e5  mov     r12, [r12]
0x1800054e9  cmp     r12, r13
0x1800054ec  jnz     short loc_180005470
0x1800054ee  xor     ebp, ebp
0x1800054f0  mov     esi, 80070002h
0x1800054f5  or      r14d, 0FFFFFFFFh
0x1800054f9  mov     eax, r14d
0x1800054fc  lock xadd [rdi+20h], eax
0x180005501  add     eax, r14d
0x180005504  js      short loc_18000551C
0x180005506  cmp     dword ptr [rdi+1Ch], 0
0x18000550a  jz      short loc_18000552E
0x18000550c  test    eax, eax
0x18000550e  jnz     short loc_18000552E
0x180005510  mov     rcx, [rdi+50h]; hEvent
0x180005514  call    cs:__imp_SetEvent
0x18000551a  jmp     short loc_18000552E
0x18000551c  lea     rcx, [rdi+28h]; lpCriticalSection
0x180005520  mov     qword ptr [rdi+1Ch], 0
0x180005528  call    cs:__imp_LeaveCriticalSection
0x18000552e  xor     edi, edi
0x180005530  mov     eax, r14d
0x180005533  test    esi, esi
0x180005535  cmovns  rdi, rbp
0x180005539  lock xadd [rbx+78h], eax
0x18000553e  add     eax, r14d
0x180005541  js      short loc_18000555C
0x180005543  cmp     dword ptr [rbx+74h], 0
0x180005547  jz      short loc_180005571
0x180005549  test    eax, eax
0x18000554b  jnz     short loc_180005571
0x18000554d  mov     rcx, [rbx+0A8h]; hEvent
0x180005554  call    cs:__imp_SetEvent
0x18000555a  jmp     short loc_180005571
0x18000555c  lea     rcx, [rbx+80h]; lpCriticalSection
0x180005563  mov     qword ptr [rbx+74h], 0
0x18000556b  call    cs:__imp_LeaveCriticalSection
0x180005571  mov     rax, [rsp+68h+arg_10]
0x180005579  mov     [rax], rdi
0x18000557c  mov     eax, esi
0x18000557e  add     rsp, 28h
0x180005582  pop     r15
0x180005584  pop     r14
0x180005586  pop     r13
0x180005588  pop     r12
0x18000558a  pop     rdi
0x18000558b  pop     rsi
0x18000558c  pop     rbp
0x18000558d  pop     rbx
0x18000558e  retn
```
