# APPLICATION_MANAGER::ReturnApplication(APPLICATION *,int,int)

- ea: `0x1800083d0`
- end: `0x1800086b4`
- name: `?ReturnApplication@APPLICATION_MANAGER@@QEAAJPEAVAPPLICATION@@HH@Z`
- size: `740`
- prototype: `__int64 __fastcall(APPLICATION_MANAGER *__hidden this, struct APPLICATION *, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180005068`
- `0x180006480`

## callees

- `0x180007180`
- `0x180008128`
- `0x1800083d0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008408`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008656`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008408`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008656`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008617`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008694`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008617`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008694`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800085af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800085af`

## pseudocode

```c
__int64 __fastcall APPLICATION_MANAGER::ReturnApplication(
        APPLICATION_MANAGER *this,
        struct APPLICATION *a2,
        int a3,
        int a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r12
  APPLICATION_MANAGER *v9; // rcx
  APPLICATION_MANAGER *v10; // rax
  APPLICATION_MANAGER *i; // rcx
  APPLICATION_MANAGER *v12; // rcx
  APPLICATION_MANAGER **v13; // rdx
  APPLICATION_MANAGER **v14; // rdx
  int v15; // ebp
  _QWORD *v16; // rax
  __int64 v17; // rdx
  BOOL v18; // ecx
  _QWORD *v19; // r8
  _QWORD *v20; // rdx
  __int64 v21; // r8
  APPLICATION_MANAGER *v22; // rsi
  APPLICATION_MANAGER **v23; // rbx
  APPLICATION_MANAGER *v24; // rax
  APPLICATION_MANAGER **v25; // r15
  APPLICATION_MANAGER *v26; // rax
  struct APPLICATION *v28; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v29; // [rsp+80h] [rbp+8h] BYREF
  int v30; // [rsp+98h] [rbp+20h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v28 = 0;
  v29 = 0;
  v30 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a4 )
  {
    v9 = (APPLICATION_MANAGER *)*((_QWORD *)this + 8);
    v10 = (struct APPLICATION *)((char *)a2 + 24);
    while ( v9 != (APPLICATION_MANAGER *)((char *)this + 64) )
    {
      if ( v9 == v10 )
      {
        --*((_DWORD *)this + 15);
        goto LABEL_13;
      }
      v9 = *(APPLICATION_MANAGER **)v9;
    }
    for ( i = (APPLICATION_MANAGER *)*((_QWORD *)this + 11);
          i != (APPLICATION_MANAGER *)((char *)this + 88);
          i = *(APPLICATION_MANAGER **)i )
    {
      if ( i == v10 )
      {
        --*((_DWORD *)this + 20);
        break;
      }
    }
LABEL_13:
    v12 = *(APPLICATION_MANAGER **)v10;
    if ( *(APPLICATION_MANAGER **)(*(_QWORD *)v10 + 8LL) != v10 )
      goto LABEL_40;
    v13 = (APPLICATION_MANAGER **)*((_QWORD *)a2 + 4);
    if ( *v13 != v10 )
      goto LABEL_40;
    *v13 = v12;
    *((_QWORD *)v12 + 1) = v13;
    v14 = (APPLICATION_MANAGER **)*((_QWORD *)this + 14);
    if ( *v14 != (APPLICATION_MANAGER *)((char *)this + 104) )
      goto LABEL_40;
    *(_QWORD *)v10 = (char *)this + 104;
    a2 = 0;
    *((_QWORD *)v10 + 1) = v14;
    *v14 = v10;
    *((_QWORD *)this + 14) = v10;
  }
  v15 = 0;
  if ( !*((_DWORD *)this + 36) )
  {
    if ( a2 )
    {
      v16 = (_QWORD *)((char *)a2 + 24);
      v17 = *((_QWORD *)a2 + 3);
      v18 = *((_DWORD *)a2 + 69) <= 1u;
      if ( *(struct APPLICATION **)(v17 + 8) != (struct APPLICATION *)((char *)a2 + 24) )
        goto LABEL_40;
      v19 = (_QWORD *)*((_QWORD *)a2 + 4);
      if ( (_QWORD *)*v19 != v16 )
        goto LABEL_40;
      *v19 = v17;
      *(_QWORD *)(v17 + 8) = v19;
      v20 = (_QWORD *)((char *)this + 88);
      --*((_DWORD *)this + 15);
      v21 = *((_QWORD *)this + 11);
      if ( *(APPLICATION_MANAGER **)(v21 + 8) != (APPLICATION_MANAGER *)((char *)this + 88) )
        goto LABEL_40;
      *v16 = v21;
      *((_QWORD *)a2 + 4) = v20;
      *(_QWORD *)(v21 + 8) = v16;
      *v20 = v16;
      ++*((_DWORD *)this + 20);
    }
    else
    {
      v18 = 1;
      if ( !a3 && *((_DWORD *)this + 127) )
      {
        *((_DWORD *)this + *((unsigned int *)this + 1130) + 130) = GetTickCount();
        *((_DWORD *)this + 1130) = (unsigned int)(*((_DWORD *)this + 1130) + 1) % *((_DWORD *)this + 127);
LABEL_24:
        v15 = 0;
        while ( 2 )
        {
          if ( *((_DWORD *)this + 15) < APPLICATION_MANAGER::QueryMaxApplications(this) && *((_DWORD *)this + 34) )
          {
            while ( 1 )
            {
              if ( !*((_DWORD *)this + 34) )
              {
                v15 = 0;
                goto LABEL_42;
              }
              v22 = (APPLICATION_MANAGER *)((char *)this + 120);
              v23 = (APPLICATION_MANAGER **)*((_QWORD *)this + 15);
              if ( v23[1] != (APPLICATION_MANAGER *)((char *)this + 120) )
                goto LABEL_40;
              v24 = *v23;
              if ( *((APPLICATION_MANAGER ***)*v23 + 1) != v23 )
                goto LABEL_40;
              *(_QWORD *)v22 = v24;
              v25 = v23 - 1;
              *((_QWORD *)v24 + 1) = v22;
              --*((_DWORD *)this + 34);
              _InterlockedDecrement(&APPLICATION_MANAGER::sm_lTotalQueueLength);
              if ( (*(int (__fastcall **)(APPLICATION_MANAGER **))*(v23 - 1))(v23 - 1) >= 0 )
                break;
              (*((void (__fastcall **)(APPLICATION_MANAGER **))*v25 + 2))(v23 - 1);
            }
            v15 = APPLICATION_MANAGER::AllocateApplication(this, &v28, &v29, a2, &v30);
            if ( v15 < 0 || !v30 )
            {
              LeaveCriticalSection(v4);
              (*((void (__fastcall **)(APPLICATION_MANAGER **, struct APPLICATION *, _QWORD, _QWORD))*v25 + 1))(
                v23 - 1,
                v28,
                (unsigned int)v15,
                v29);
              (*((void (__fastcall **)(APPLICATION_MANAGER **))*v25 + 2))(v23 - 1);
              v28 = 0;
              EnterCriticalSection(v4);
              continue;
            }
            v26 = *(APPLICATION_MANAGER **)v22;
            if ( *(APPLICATION_MANAGER **)(*(_QWORD *)v22 + 8LL) == v22 )
            {
              *v23 = v26;
              v23[1] = v22;
              *((_QWORD *)v26 + 1) = v23;
              *(_QWORD *)v22 = v23;
              ++*((_DWORD *)this + 34);
              _InterlockedIncrement(&APPLICATION_MANAGER::sm_lTotalQueueLength);
              goto LABEL_42;
            }
LABEL_40:
            __fastfail(3u);
          }
          goto LABEL_42;
        }
      }
    }
    if ( !v18 )
      goto LABEL_42;
    goto LABEL_24;
  }
LABEL_42:
  LeaveCriticalSection(v4);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800083d0  mov     rax, rsp
0x1800083d3  mov     [rax+10h], rbx
0x1800083d7  push    rbp
0x1800083d8  push    rsi
0x1800083d9  push    rdi
0x1800083da  push    r12
0x1800083dc  push    r13
0x1800083de  push    r14
0x1800083e0  push    r15
0x1800083e2  sub     rsp, 40h
0x1800083e6  xor     r15d, r15d
0x1800083e9  lea     r12, [rcx+10h]
0x1800083ed  mov     rdi, rcx
0x1800083f0  mov     [rax-48h], r15
0x1800083f4  mov     rcx, r12; lpCriticalSection
0x1800083f7  mov     [rax+8], r15d
0x1800083fb  mov     ebx, r9d
0x1800083fe  mov     [rax+20h], r15d
0x180008402  mov     esi, r8d
0x180008405  mov     r14, rdx
0x180008408  call    cs:__imp_EnterCriticalSection
0x18000840e  test    ebx, ebx
0x180008410  jz      short loc_18000848F
0x180008412  lea     rdx, [rdi+40h]
0x180008416  mov     rcx, [rdx]
0x180008419  lea     rax, [r14+18h]
0x18000841d  jmp     short loc_180008427
0x18000841f  cmp     rcx, rax
0x180008422  jz      short loc_180008435
0x180008424  mov     rcx, [rcx]
0x180008427  cmp     rcx, rdx
0x18000842a  jnz     short loc_18000841F
0x18000842c  lea     rdx, [rdi+58h]
0x180008430  mov     rcx, [rdx]
0x180008433  jmp     short loc_180008442
0x180008435  dec     dword ptr [rdi+3Ch]
0x180008438  jmp     short loc_18000844C
0x18000843a  cmp     rcx, rax
0x18000843d  jz      short loc_180008449
0x18000843f  mov     rcx, [rcx]
0x180008442  cmp     rcx, rdx
0x180008445  jnz     short loc_18000843A
0x180008447  jmp     short loc_18000844C
0x180008449  dec     dword ptr [rdi+50h]
0x18000844c  mov     rcx, [rax]
0x18000844f  cmp     [rcx+8], rax
0x180008453  jnz     loc_180008687
0x180008459  mov     rdx, [rax+8]
0x18000845d  cmp     [rdx], rax
0x180008460  jnz     loc_180008687
0x180008466  mov     [rdx], rcx
0x180008469  mov     [rcx+8], rdx
0x18000846d  lea     rcx, [rdi+68h]
0x180008471  mov     rdx, [rcx+8]
0x180008475  cmp     [rdx], rcx
0x180008478  jnz     loc_180008687
0x18000847e  mov     [rax], rcx
0x180008481  mov     r14, r15
0x180008484  mov     [rax+8], rdx
0x180008488  mov     [rdx], rax
0x18000848b  mov     [rcx+8], rax
0x18000848f  mov     ebp, r15d
0x180008492  cmp     [rdi+90h], r15d
0x180008499  jnz     loc_180008691
0x18000849f  test    r14, r14
0x1800084a2  jz      loc_180008595
0x1800084a8  cmp     dword ptr [r14+114h], 1
0x1800084b0  lea     rax, [r14+18h]
0x1800084b4  mov     rdx, [rax]
0x1800084b7  mov     ecx, r15d
0x1800084ba  setbe   cl
0x1800084bd  cmp     [rdx+8], rax
0x1800084c1  jnz     loc_180008687
0x1800084c7  mov     r8, [rax+8]
0x1800084cb  cmp     [r8], rax
0x1800084ce  jnz     loc_180008687
0x1800084d4  mov     [r8], rdx
0x1800084d7  mov     [rdx+8], r8
0x1800084db  lea     rdx, [rdi+58h]
0x1800084df  dec     dword ptr [rdi+3Ch]
0x1800084e2  mov     r8, [rdx]
0x1800084e5  cmp     [r8+8], rdx
0x1800084e9  jnz     loc_180008687
0x1800084ef  mov     [rax], r8
0x1800084f2  mov     [rax+8], rdx
0x1800084f6  mov     [r8+8], rax
0x1800084fa  mov     [rdx], rax
0x1800084fd  inc     dword ptr [rdi+50h]
0x180008500  test    ecx, ecx
0x180008502  jz      loc_180008691
0x180008508  mov     r13, r12
0x18000850b  mov     ebp, r15d
0x18000850e  mov     rcx, rdi; this
0x180008511  call    ?QueryMaxApplications@APPLICATION_MANAGER@@QEAAKXZ; APPLICATION_MANAGER::QueryMaxApplications(void)
0x180008516  cmp     [rdi+3Ch], eax
0x180008519  jnb     loc_180008691
0x18000851f  cmp     [rdi+88h], r15d
0x180008526  jz      loc_180008691
0x18000852c  cmp     [rdi+88h], r15d
0x180008533  jbe     loc_18000868E
0x180008539  lea     rsi, [rdi+78h]
0x18000853d  mov     rbx, [rsi]
0x180008540  cmp     [rbx+8], rsi
0x180008544  jnz     loc_180008687
0x18000854a  mov     rax, [rbx]
0x18000854d  cmp     [rax+8], rbx
0x180008551  jnz     loc_180008687
0x180008557  mov     [rsi], rax
0x18000855a  lea     r15, [rbx-8]
0x18000855e  mov     [rax+8], rsi
0x180008562  mov     rcx, r15
0x180008565  dec     dword ptr [rdi+88h]
0x18000856b  lock dec cs:?sm_lTotalQueueLength@APPLICATION_MANAGER@@0JA; long APPLICATION_MANAGER::sm_lTotalQueueLength
0x180008572  mov     rax, [r15]
0x180008575  mov     rax, [rax]
0x180008578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000857d  test    eax, eax
0x18000857f  jns     short loc_1800085DF
0x180008581  mov     rax, [r15]
0x180008584  mov     rcx, r15
0x180008587  mov     rax, [rax+10h]
0x18000858b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008590  xor     r15d, r15d
0x180008593  jmp     short loc_18000852C
0x180008595  mov     ecx, 1
0x18000859a  test    esi, esi
0x18000859c  jnz     loc_180008500
0x1800085a2  cmp     [rdi+1FCh], r15d
0x1800085a9  jz      loc_180008500
0x1800085af  call    cs:__imp_GetTickCount
0x1800085b5  mov     ecx, eax
0x1800085b7  xor     edx, edx
0x1800085b9  mov     eax, [rdi+11A8h]
0x1800085bf  mov     [rdi+rax*4+208h], ecx
0x1800085c6  mov     eax, [rdi+11A8h]
0x1800085cc  inc     eax
0x1800085ce  div     dword ptr [rdi+1FCh]
0x1800085d4  mov     [rdi+11A8h], edx
0x1800085da  jmp     loc_180008508
0x1800085df  lea     rax, [rsp+78h+arg_18]
0x1800085e7  mov     r9, r14; struct APPLICATION *
0x1800085ea  lea     r8, [rsp+78h+arg_0]; unsigned int *
0x1800085f2  mov     [rsp+78h+var_58], rax; int *
0x1800085f7  lea     rdx, [rsp+78h+var_48]; struct APPLICATION **
0x1800085fc  mov     rcx, rdi; this
0x1800085ff  call    ?AllocateApplication@APPLICATION_MANAGER@@AEAAJPEAPEAVAPPLICATION@@PEAIPEAV2@PEAH@Z; APPLICATION_MANAGER::AllocateApplication(APPLICATION * *,uint *,APPLICATION *,int *)
0x180008604  mov     ebp, eax
0x180008606  test    eax, eax
0x180008608  js      short loc_180008614
0x18000860a  cmp     [rsp+78h+arg_18], 0
0x180008612  jnz     short loc_180008661
0x180008614  mov     rcx, r13; lpCriticalSection
0x180008617  call    cs:__imp_LeaveCriticalSection
0x18000861d  mov     rcx, [r15]
0x180008620  mov     r8d, ebp
0x180008623  mov     r9d, [rsp+78h+arg_0]
0x18000862b  mov     rdx, [rsp+78h+var_48]
0x180008630  mov     rax, [rcx+8]
0x180008634  mov     rcx, r15
0x180008637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000863c  mov     rax, [r15]
0x18000863f  mov     rcx, r15
0x180008642  mov     rax, [rax+10h]
0x180008646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000864b  xor     r15d, r15d
0x18000864e  mov     rcx, r13; lpCriticalSection
0x180008651  mov     [rsp+78h+var_48], r15
0x180008656  call    cs:__imp_EnterCriticalSection
0x18000865c  jmp     loc_18000850E
0x180008661  mov     rax, [rsi]
0x180008664  cmp     [rax+8], rsi
0x180008668  jnz     short loc_180008687
0x18000866a  mov     [rbx], rax
0x18000866d  mov     [rbx+8], rsi
0x180008671  mov     [rax+8], rbx
0x180008675  mov     [rsi], rbx
0x180008678  inc     dword ptr [rdi+88h]
0x18000867e  lock inc cs:?sm_lTotalQueueLength@APPLICATION_MANAGER@@0JA; long APPLICATION_MANAGER::sm_lTotalQueueLength
0x180008685  jmp     short loc_180008691
0x180008687  mov     ecx, 3
0x18000868c  int     29h; Win8: RtlFailFast(ecx)
0x18000868e  mov     ebp, r15d
0x180008691  mov     rcx, r12; lpCriticalSection
0x180008694  call    cs:__imp_LeaveCriticalSection
0x18000869a  mov     rbx, [rsp+78h+arg_8]
0x1800086a2  mov     eax, ebp
0x1800086a4  add     rsp, 40h
0x1800086a8  pop     r15
0x1800086aa  pop     r14
0x1800086ac  pop     r13
0x1800086ae  pop     r12
0x1800086b0  pop     rdi
0x1800086b1  pop     rsi
0x1800086b2  pop     rbp
0x1800086b3  retn
```
