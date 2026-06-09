# APPLICATION_MANAGER::Recycle(int,int)

- ea: `0x180008164`
- end: `0x1800083c8`
- name: `?Recycle@APPLICATION_MANAGER@@AEAAXHH@Z`
- size: `612`
- prototype: `void __fastcall(APPLICATION_MANAGER *__hidden this, int, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180008100`
- `0x1800086bc`
- `0x180008be8`

## callees

- `0x180001008`
- `0x180001048`
- `0x180005030`
- `0x180005f4c`
- `0x180006480`
- `0x180006c5c`
- `0x180008164`
- `0x180008d90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008190`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800082d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008399`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008190`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800082d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008399`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000828c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008318`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008352`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000828c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008318`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008352`

## pseudocode

```c
void __fastcall APPLICATION_MANAGER::Recycle(APPLICATION_MANAGER *this, int a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r14
  DWORD v7; // edi
  APPLICATION_MANAGER *v8; // rcx
  APPLICATION_MANAGER *v9; // r9
  APPLICATION_MANAGER *v10; // rax
  APPLICATION_MANAGER **v11; // r8
  __int64 v12; // rax
  APPLICATION_MANAGER *v13; // rcx
  APPLICATION_MANAGER *v14; // r9
  APPLICATION_MANAGER *v15; // rax
  APPLICATION_MANAGER **v16; // r8
  __int64 v17; // rax
  int v18; // r12d
  void **v19; // rsi
  __int64 v20; // r13
  int v21; // edx
  _QWORD *v22; // r15
  void **v23; // rbx
  DWORD v24; // eax
  APPLICATION_MANAGER *v25; // rcx
  APPLICATION *v26; // rbx
  _QWORD *v27; // rbx
  __int64 v28; // rax
  _QWORD v29[3]; // [rsp+30h] [rbp-18h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v29[1] = v29;
  v29[0] = v29;
  if ( a2 == 1 )
  {
    v8 = (APPLICATION_MANAGER *)*((_QWORD *)this + 8);
    if ( v8 != (APPLICATION_MANAGER *)((char *)this + 64) )
    {
      do
      {
        v9 = *(APPLICATION_MANAGER **)v8;
        if ( !*((_DWORD *)v8 + 20) )
        {
          v10 = *(APPLICATION_MANAGER **)v8;
          if ( *(APPLICATION_MANAGER **)(*(_QWORD *)v8 + 8LL) != v8
            || (v11 = (APPLICATION_MANAGER **)*((_QWORD *)v8 + 1), *v11 != v8)
            || (*v11 = v10,
                *((_QWORD *)v10 + 1) = v11,
                v12 = v29[0],
                --*((_DWORD *)this + 15),
                *(_QWORD **)(v12 + 8) != v29) )
          {
LABEL_33:
            __fastfail(3u);
          }
          *(_QWORD *)v8 = v12;
          *((_QWORD *)v8 + 1) = v29;
          ++v7;
          *(_QWORD *)(v12 + 8) = v8;
          v29[0] = v8;
        }
        v8 = v9;
      }
      while ( v9 != (APPLICATION_MANAGER *)((char *)this + 64) );
    }
  }
  if ( a3 == 1 )
  {
    v13 = (APPLICATION_MANAGER *)*((_QWORD *)this + 11);
    if ( v13 != (APPLICATION_MANAGER *)((char *)this + 88) )
    {
      do
      {
        v14 = *(APPLICATION_MANAGER **)v13;
        if ( !*((_DWORD *)v13 + 20) )
        {
          v15 = *(APPLICATION_MANAGER **)v13;
          if ( *(APPLICATION_MANAGER **)(*(_QWORD *)v13 + 8LL) != v13 )
            goto LABEL_33;
          v16 = (APPLICATION_MANAGER **)*((_QWORD *)v13 + 1);
          if ( *v16 != v13 )
            goto LABEL_33;
          *v16 = v15;
          *((_QWORD *)v15 + 1) = v16;
          v17 = v29[0];
          --*((_DWORD *)this + 20);
          if ( *(_QWORD **)(v17 + 8) != v29 )
            goto LABEL_33;
          *(_QWORD *)v13 = v17;
          *((_QWORD *)v13 + 1) = v29;
          ++v7;
          *(_QWORD *)(v17 + 8) = v13;
          v29[0] = v13;
        }
        v13 = v14;
      }
      while ( v14 != (APPLICATION_MANAGER *)((char *)this + 88) );
    }
  }
  LeaveCriticalSection(v3);
  v18 = *((_DWORD *)this + 117);
  if ( v18 )
  {
    if ( v7 )
    {
      v19 = (void **)operator new(saturated_mul(v7, 8u));
      if ( v19 )
      {
        v20 = 0;
        EnterCriticalSection(v3);
        v22 = (_QWORD *)v29[0];
        while ( v22 != v29 )
        {
          v23 = &v19[v20];
          APPLICATION::SendSignalBeforeTerminate((APPLICATION *)(v22 - 3), v21, v23);
          v24 = v7 - 1;
          v22 = (_QWORD *)*v22;
          if ( *v23 != (void *)-1LL )
            v24 = v7;
          v7 = v24;
          if ( *v23 != (void *)-1LL )
            v20 = (unsigned int)(v20 + 1);
        }
        LeaveCriticalSection(v3);
        if ( v7 )
          APPLICATION_MANAGER::WaitForAllObjects(v25, v7, v19, 1000 * v18);
        operator delete(v19);
      }
    }
  }
  while ( 1 )
  {
    EnterCriticalSection(v3);
    v27 = (_QWORD *)v29[0];
    v28 = *(_QWORD *)v29[0];
    if ( *(_QWORD **)(v29[0] + 8LL) != v29 || *(_QWORD *)(v28 + 8) != v29[0] )
      goto LABEL_33;
    v29[0] = *(_QWORD *)v29[0];
    *(_QWORD *)(v28 + 8) = v29;
    LeaveCriticalSection(v3);
    if ( v27 == v29 )
      break;
    v26 = (APPLICATION *)(v27 - 3);
    APPLICATION::RealShutdown(v26, 0x800704E7, 0x30D48u, 1, 0);
    APPLICATION::Kill(v26);
    APPLICATION::DereferenceApplication(v26);
  }
}

```

## disassembly

```asm
0x180008164  push    rbp
0x180008166  push    rbx
0x180008167  push    rsi
0x180008168  push    rdi
0x180008169  push    r12
0x18000816b  push    r13
0x18000816d  push    r14
0x18000816f  push    r15
0x180008171  mov     rbp, rsp
0x180008174  sub     rsp, 48h
0x180008178  lea     r14, [rcx+10h]
0x18000817c  mov     rsi, rcx
0x18000817f  xorps   xmm0, xmm0
0x180008182  mov     rcx, r14; lpCriticalSection
0x180008185  mov     r15d, r8d
0x180008188  mov     ebx, edx
0x18000818a  xor     edi, edi
0x18000818c  movups  [rbp+var_18], xmm0
0x180008190  call    cs:__imp_EnterCriticalSection
0x180008196  lea     rax, [rbp+var_18]
0x18000819a  or      r10d, 0FFFFFFFFh
0x18000819e  mov     qword ptr [rbp+var_18+8], rax
0x1800081a2  lea     rax, [rbp+var_18]
0x1800081a6  mov     qword ptr [rbp+var_18], rax
0x1800081aa  cmp     ebx, 1
0x1800081ad  jnz     short loc_180008219
0x1800081af  lea     rdx, [rsi+40h]
0x1800081b3  mov     rcx, [rdx]
0x1800081b6  cmp     rcx, rdx
0x1800081b9  jz      short loc_180008219
0x1800081bb  mov     eax, [rcx+50h]
0x1800081be  mov     r9, [rcx]
0x1800081c1  test    eax, eax
0x1800081c3  jnz     short loc_180008211
0x1800081c5  mov     rax, [rcx]
0x1800081c8  cmp     [rax+8], rcx
0x1800081cc  jnz     loc_1800083B0
0x1800081d2  mov     r8, [rcx+8]
0x1800081d6  cmp     [r8], rcx
0x1800081d9  jnz     loc_1800083B0
0x1800081df  mov     [r8], rax
0x1800081e2  mov     [rax+8], r8
0x1800081e6  lea     r8, [rbp+var_18]
0x1800081ea  mov     rax, qword ptr [rbp+var_18]
0x1800081ee  add     [rsi+3Ch], r10d
0x1800081f2  cmp     [rax+8], r8
0x1800081f6  jnz     loc_1800083B0
0x1800081fc  mov     [rcx], rax
0x1800081ff  lea     r8, [rbp+var_18]
0x180008203  mov     [rcx+8], r8
0x180008207  inc     edi
0x180008209  mov     [rax+8], rcx
0x18000820d  mov     qword ptr [rbp+var_18], rcx
0x180008211  mov     rcx, r9
0x180008214  cmp     r9, rdx
0x180008217  jnz     short loc_1800081BB
0x180008219  cmp     r15d, 1
0x18000821d  jnz     short loc_180008289
0x18000821f  lea     rdx, [rsi+58h]
0x180008223  mov     rcx, [rdx]
0x180008226  cmp     rcx, rdx
0x180008229  jz      short loc_180008289
0x18000822b  mov     eax, [rcx+50h]
0x18000822e  mov     r9, [rcx]
0x180008231  test    eax, eax
0x180008233  jnz     short loc_180008281
0x180008235  mov     rax, [rcx]
0x180008238  cmp     [rax+8], rcx
0x18000823c  jnz     loc_1800083B0
0x180008242  mov     r8, [rcx+8]
0x180008246  cmp     [r8], rcx
0x180008249  jnz     loc_1800083B0
0x18000824f  mov     [r8], rax
0x180008252  mov     [rax+8], r8
0x180008256  lea     r8, [rbp+var_18]
0x18000825a  mov     rax, qword ptr [rbp+var_18]
0x18000825e  add     [rsi+50h], r10d
0x180008262  cmp     [rax+8], r8
0x180008266  jnz     loc_1800083B0
0x18000826c  mov     [rcx], rax
0x18000826f  lea     r8, [rbp+var_18]
0x180008273  mov     [rcx+8], r8
0x180008277  inc     edi
0x180008279  mov     [rax+8], rcx
0x18000827d  mov     qword ptr [rbp+var_18], rcx
0x180008281  mov     rcx, r9
0x180008284  cmp     r9, rdx
0x180008287  jnz     short loc_18000822B
0x180008289  mov     rcx, r14; lpCriticalSection
0x18000828c  call    cs:__imp_LeaveCriticalSection
0x180008292  mov     r12d, [rsi+1D4h]
0x180008299  test    r12d, r12d
0x18000829c  jz      loc_180008396
0x1800082a2  test    edi, edi
0x1800082a4  jz      loc_180008396
0x1800082aa  mov     ecx, edi
0x1800082ac  mov     eax, 8
0x1800082b1  mul     rcx
0x1800082b4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800082bb  cmovb   rax, rcx
0x1800082bf  mov     rcx, rax; Size
0x1800082c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800082c7  mov     rsi, rax
0x1800082ca  test    rax, rax
0x1800082cd  jz      loc_180008396
0x1800082d3  xor     r13d, r13d
0x1800082d6  mov     rcx, r14; lpCriticalSection
0x1800082d9  call    cs:__imp_EnterCriticalSection
0x1800082df  mov     r15, qword ptr [rbp+var_18]
0x1800082e3  jmp     short loc_18000830C
0x1800082e5  lea     rbx, [rsi+r13*8]
0x1800082e9  mov     r8, rbx; void **
0x1800082ec  lea     rcx, [r15-18h]; this
0x1800082f0  call    ?SendSignalBeforeTerminate@APPLICATION@@QEAAXHPEAPEAX@Z; APPLICATION::SendSignalBeforeTerminate(int,void * *)
0x1800082f5  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800082f9  lea     eax, [rdi-1]
0x1800082fc  mov     r15, [r15]
0x1800082ff  cmovnz  eax, edi
0x180008302  mov     edi, eax
0x180008304  lea     eax, [r13+1]
0x180008308  cmovnz  r13d, eax
0x18000830c  lea     rax, [rbp+var_18]
0x180008310  cmp     r15, rax
0x180008313  jnz     short loc_1800082E5
0x180008315  mov     rcx, r14; lpCriticalSection
0x180008318  call    cs:__imp_LeaveCriticalSection
0x18000831e  test    edi, edi
0x180008320  jz      short loc_180008333
0x180008322  imul    r9d, r12d, 3E8h; unsigned int
0x180008329  mov     r8, rsi; void **
0x18000832c  mov     edx, edi; unsigned int
0x18000832e  call    ?WaitForAllObjects@APPLICATION_MANAGER@@AEAAXKPEAPEAXK@Z; APPLICATION_MANAGER::WaitForAllObjects(ulong,void * *,ulong)
0x180008333  mov     rcx, rsi; Block
0x180008336  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000833b  jmp     short loc_180008396
0x18000833d  cmp     [rax+8], rbx
0x180008341  jnz     short loc_1800083B0
0x180008343  lea     rcx, [rbp+var_18]
0x180008347  mov     qword ptr [rbp+var_18], rax
0x18000834b  mov     [rax+8], rcx
0x18000834f  mov     rcx, r14; lpCriticalSection
0x180008352  call    cs:__imp_LeaveCriticalSection
0x180008358  lea     rax, [rbp+var_18]
0x18000835c  cmp     rbx, rax
0x18000835f  jz      short loc_1800083B7
0x180008361  add     rbx, 0FFFFFFFFFFFFFFE8h
0x180008365  mov     [rsp+48h+var_28], 0; int
0x18000836d  mov     rcx, rbx; this
0x180008370  mov     edx, 800704E7h; int
0x180008375  mov     r9d, 1; int
0x18000837b  mov     r8d, 30D48h; unsigned int
0x180008381  call    ?RealShutdown@APPLICATION@@QEAAXJIHH@Z; APPLICATION::RealShutdown(long,uint,int,int)
0x180008386  mov     rcx, rbx; this
0x180008389  call    ?Kill@APPLICATION@@QEAAXXZ; APPLICATION::Kill(void)
0x18000838e  mov     rcx, rbx; this
0x180008391  call    ?DereferenceApplication@APPLICATION@@QEAAXXZ; APPLICATION::DereferenceApplication(void)
0x180008396  mov     rcx, r14; lpCriticalSection
0x180008399  call    cs:__imp_EnterCriticalSection
0x18000839f  mov     rbx, qword ptr [rbp+var_18]
0x1800083a3  lea     rcx, [rbp+var_18]
0x1800083a7  mov     rax, [rbx]
0x1800083aa  cmp     [rbx+8], rcx
0x1800083ae  jz      short loc_18000833D
0x1800083b0  mov     ecx, 3
0x1800083b5  int     29h; Win8: RtlFailFast(ecx)
0x1800083b7  add     rsp, 48h
0x1800083bb  pop     r15
0x1800083bd  pop     r14
0x1800083bf  pop     r13
0x1800083c1  pop     r12
0x1800083c3  pop     rdi
0x1800083c4  pop     rsi
0x1800083c5  pop     rbx
0x1800083c6  pop     rbp
0x1800083c7  retn
```
