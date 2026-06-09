# CILogStorage::OpenLogStream(char *,ulong,void * *)

- ea: `0x1800047b0`
- end: `0x1800049f1`
- name: `?OpenLogStream@CILogStorage@@UEAAJPEADKPEAPEAX@Z`
- size: `577`
- prototype: `__int64 __fastcall(struct CLogMgr **this, char *, int, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800012c0`
- `0x1800042b4`
- `0x1800045f4`
- `0x1800047b0`
- `0x180006248`
- `0x180008248`
- `0x18000c918`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800048e7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800048e7`

## pseudocode

```c
__int64 __fastcall CILogStorage::OpenLogStream(struct CLogMgr **this, char *a2, int a3, void **a4)
{
  struct _STRMTBL *v8; // rdi
  __int64 result; // rax
  CLogStream *v10; // rbx
  struct _STRMTBL *v11; // rax
  unsigned int v12; // edi
  void *v13; // rcx
  struct CLogMgr *v14; // rdx
  int v15; // r9d
  int v16; // r8d
  struct CLogMgr *v17; // rcx
  struct _STRMTBL *v18[5]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v19; // [rsp+58h] [rbp+10h] BYREF

  v18[0] = 0;
  v19 = 0;
  if ( !a2 || !a4 )
    return 2147942487LL;
  CILogStorage::FindStream((CILogStorage *)this, a2, v18, &v19);
  v8 = v18[0];
  if ( !v18[0] )
  {
    if ( a3 == 2 )
    {
      result = CILogStorage::AddStream((CILogStorage *)this, a2, v18, &v19);
      if ( (_DWORD)result )
        return result;
      v8 = v18[0];
      goto LABEL_7;
    }
    return 2147942487LL;
  }
LABEL_7:
  v10 = *(CLogStream **)((char *)v8 + 20);
  if ( !v10 )
  {
    v11 = (struct _STRMTBL *)operator new(0x260u);
    v18[0] = v11;
    if ( v11 )
      v10 = CLogStream::CLogStream(v11, this[1], v19);
    else
      v10 = 0;
    *(_QWORD *)((char *)v8 + 20) = v10;
    if ( !v10 )
      return 2147942414LL;
    (*(void (__fastcall **)(CLogStream *))(*(_QWORD *)v10 + 8LL))(v10);
  }
  if ( a3 == 1 )
  {
    v12 = (**(__int64 (__fastcall ***)(CLogStream *, GUID *, void **))v10)(v10, &IID_ILogRead, a4);
    if ( !v12 && *((_DWORD *)v10 + 150) == -1 && *((_DWORD *)v10 + 151) == -1 )
    {
      CLogMgr::CrashShutDown(this[1]);
      v13 = (void *)*((_QWORD *)this[1] + 73);
      if ( v13 )
      {
        if ( WaitForSingleObject(v13, 0x1388u) )
          v12 = -2147467259;
      }
      v14 = this[1];
      *((_DWORD *)v10 + 150) = *(_DWORD *)(*((_QWORD *)v14 + 50) + 24LL);
      *((_DWORD *)v10 + 151) = *(_DWORD *)(*((_QWORD *)v14 + 50) + 28LL);
      *(_DWORD *)(*((_QWORD *)v14 + 50) + 24LL) = *(_DWORD *)(*((_QWORD *)v14 + 50) + 48LL);
      *(_DWORD *)(*((_QWORD *)v14 + 50) + 28LL) = *(_DWORD *)(*((_QWORD *)v14 + 50) + 52LL);
      **((_DWORD **)v14 + 49) = *(_DWORD *)(*((_QWORD *)v14 + 50) + 52LL);
    }
  }
  else if ( a3 == 2 )
  {
    v12 = (**(__int64 (__fastcall ***)(CLogStream *, GUID *, void **))v10)(v10, &IID_ILogWrite, a4);
    if ( !v12 )
    {
      v15 = *((_DWORD *)v10 + 150);
      if ( v15 != -1 )
      {
        v16 = *((_DWORD *)v10 + 151);
        if ( v16 != -1 )
        {
          v17 = this[1];
          *(_DWORD *)(*((_QWORD *)v17 + 50) + 24LL) = v15;
          *(_DWORD *)(*((_QWORD *)v17 + 50) + 28LL) = v16;
          **((_DWORD **)v17 + 49) = v16;
        }
      }
    }
    *((_DWORD *)v10 + 150) = -1;
    *((_DWORD *)v10 + 151) = -1;
    CLogMgr::_StartFlushThread(this[1]);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v12;
}

```

## disassembly

```asm
0x1800047b0  mov     rax, rsp
0x1800047b3  mov     [rax+8], rbx
0x1800047b7  mov     [rax+18h], rbp
0x1800047bb  push    rsi
0x1800047bc  push    rdi
0x1800047bd  push    r14
0x1800047bf  sub     rsp, 30h
0x1800047c3  mov     r14, r9
0x1800047c6  mov     ebp, r8d
0x1800047c9  mov     rbx, rdx
0x1800047cc  mov     rsi, rcx
0x1800047cf  mov     qword ptr [rax-28h], 0
0x1800047d7  mov     dword ptr [rax+10h], 0
0x1800047de  test    rdx, rdx
0x1800047e1  jz      loc_1800049D9
0x1800047e7  test    r9, r9
0x1800047ea  jz      loc_1800049D9
0x1800047f0  lea     r9, [rax+10h]; unsigned int *
0x1800047f4  lea     r8, [rax-28h]; struct _STRMTBL **
0x1800047f8  call    ?FindStream@CILogStorage@@AEAAJPEADPEAPEAU_STRMTBL@@PEAK@Z; CILogStorage::FindStream(char *,_STRMTBL * *,ulong *)
0x1800047fd  mov     rdi, [rsp+48h+var_28]
0x180004802  test    rdi, rdi
0x180004805  jnz     short loc_180004832
0x180004807  cmp     ebp, 2
0x18000480a  jnz     loc_1800049D9
0x180004810  lea     r9, [rsp+48h+arg_8]; unsigned int *
0x180004815  lea     r8, [rsp+48h+var_28]; struct _STRMTBL **
0x18000481a  mov     rdx, rbx; char *
0x18000481d  mov     rcx, rsi; this
0x180004820  call    ?AddStream@CILogStorage@@AEAAJPEADPEAPEAU_STRMTBL@@PEAK@Z; CILogStorage::AddStream(char *,_STRMTBL * *,ulong *)
0x180004825  test    eax, eax
0x180004827  jnz     loc_1800049DE
0x18000482d  mov     rdi, [rsp+48h+var_28]
0x180004832  mov     rbx, [rdi+14h]
0x180004836  test    rbx, rbx
0x180004839  jnz     short loc_180004883
0x18000483b  mov     ecx, 260h; Size
0x180004840  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004845  mov     [rsp+48h+var_28], rax
0x18000484a  test    rax, rax
0x18000484d  jz      short loc_180004865
0x18000484f  mov     r8d, [rsp+48h+arg_8]; unsigned int
0x180004854  mov     rdx, [rsi+8]; struct CLogMgr *
0x180004858  mov     rcx, rax; this
0x18000485b  call    ??0CLogStream@@QEAA@PEAVCLogMgr@@K@Z; CLogStream::CLogStream(CLogMgr *,ulong)
0x180004860  mov     rbx, rax
0x180004863  jmp     short loc_180004867
0x180004865  xor     ebx, ebx
0x180004867  mov     [rdi+14h], rbx
0x18000486b  test    rbx, rbx
0x18000486e  jz      loc_18000494D
0x180004874  mov     rax, [rbx]
0x180004877  mov     rcx, rbx
0x18000487a  mov     rax, [rax+8]
0x18000487e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004883  cmp     ebp, 1
0x180004886  jnz     loc_180004957
0x18000488c  mov     rax, [rbx]
0x18000488f  mov     r8, r14
0x180004892  lea     rdx, IID_ILogRead
0x180004899  mov     rcx, rbx
0x18000489c  mov     rax, [rax]
0x18000489f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048a4  mov     edi, eax
0x1800048a6  test    eax, eax
0x1800048a8  jnz     loc_1800049D5
0x1800048ae  or      edx, 0FFFFFFFFh
0x1800048b1  cmp     [rbx+258h], edx
0x1800048b7  jnz     loc_1800049D5
0x1800048bd  cmp     [rbx+25Ch], edx
0x1800048c3  jnz     loc_1800049D5
0x1800048c9  mov     rcx, [rsi+8]; this
0x1800048cd  call    ?CrashShutDown@CLogMgr@@QEAAJXZ; CLogMgr::CrashShutDown(void)
0x1800048d2  mov     rax, [rsi+8]
0x1800048d6  mov     rcx, [rax+248h]; hHandle
0x1800048dd  test    rcx, rcx
0x1800048e0  jz      short loc_1800048F7
0x1800048e2  mov     edx, 1388h; dwMilliseconds
0x1800048e7  call    cs:__imp_WaitForSingleObject
0x1800048ed  mov     ecx, 80004005h
0x1800048f2  test    eax, eax
0x1800048f4  cmovnz  edi, ecx
0x1800048f7  mov     rdx, [rsi+8]
0x1800048fb  mov     rax, [rdx+190h]
0x180004902  mov     ecx, [rax+18h]
0x180004905  mov     [rbx+258h], ecx
0x18000490b  mov     rax, [rdx+190h]
0x180004912  mov     ecx, [rax+1Ch]
0x180004915  mov     [rbx+25Ch], ecx
0x18000491b  mov     rcx, [rdx+190h]
0x180004922  mov     eax, [rcx+30h]
0x180004925  mov     [rcx+18h], eax
0x180004928  mov     rcx, [rdx+190h]
0x18000492f  mov     eax, [rcx+34h]
0x180004932  mov     [rcx+1Ch], eax
0x180004935  mov     rax, [rdx+190h]
0x18000493c  mov     rcx, [rdx+188h]
0x180004943  mov     eax, [rax+34h]
0x180004946  mov     [rcx], eax
0x180004948  jmp     loc_1800049D5
0x18000494d  mov     eax, 8007000Eh
0x180004952  jmp     loc_1800049DE
0x180004957  cmp     ebp, 2
0x18000495a  jnz     short loc_1800049D0
0x18000495c  mov     rax, [rbx]
0x18000495f  mov     r8, r14
0x180004962  lea     rdx, IID_ILogWrite
0x180004969  mov     rcx, rbx
0x18000496c  mov     rax, [rax]
0x18000496f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004974  mov     edi, eax
0x180004976  or      edx, 0FFFFFFFFh
0x180004979  test    eax, eax
0x18000497b  jnz     short loc_1800049B9
0x18000497d  mov     r9d, [rbx+258h]
0x180004984  cmp     r9d, edx
0x180004987  jz      short loc_1800049B9
0x180004989  mov     r8d, [rbx+25Ch]
0x180004990  cmp     r8d, edx
0x180004993  jz      short loc_1800049B9
0x180004995  mov     rcx, [rsi+8]
0x180004999  mov     rax, [rcx+190h]
0x1800049a0  mov     [rax+18h], r9d
0x1800049a4  mov     rax, [rcx+190h]
0x1800049ab  mov     [rax+1Ch], r8d
0x1800049af  mov     rax, [rcx+188h]
0x1800049b6  mov     [rax], r8d
0x1800049b9  mov     [rbx+258h], edx
0x1800049bf  mov     [rbx+25Ch], edx
0x1800049c5  mov     rcx, [rsi+8]; this
0x1800049c9  call    ?_StartFlushThread@CLogMgr@@AEAAXXZ; CLogMgr::_StartFlushThread(void)
0x1800049ce  jmp     short loc_1800049D5
0x1800049d0  mov     edi, 80070057h
0x1800049d5  mov     eax, edi
0x1800049d7  jmp     short loc_1800049DE
0x1800049d9  mov     eax, 80070057h
0x1800049de  mov     rbx, [rsp+48h+arg_0]
0x1800049e3  mov     rbp, [rsp+48h+arg_10]
0x1800049e8  add     rsp, 30h
0x1800049ec  pop     r14
0x1800049ee  pop     rdi
0x1800049ef  pop     rsi
0x1800049f0  retn
```
