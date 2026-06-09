# CTVOAgent::CompleteActiveRetrieval(_TVO_ACTIVE_ENTRY *,ulong,int,void *)

- ea: `0x180017270`
- end: `0x18001744b`
- name: `?CompleteActiveRetrieval@CTVOAgent@@QEAAXPEAU_TVO_ACTIVE_ENTRY@@KHPEAX@Z`
- size: `475`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, _QWORD *hMem, int, int, CRL_CONTEXT *pCrlContext)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180007cc0`

## callees

- `0x18000a990`
- `0x18000eb80`
- `0x180017270`
- `0x180026546`

## import_xrefs

- `CRYPT32!I_CertDiagControl` at `0x1800173d6`
- `CRYPT32!I_CertDiagControl` at `0x1800173d6`
- `CRYPT32!CertDuplicateCRLContext` at `0x1800173ef`
- `CRYPT32!CertDuplicateCRLContext` at `0x1800173ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800172a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800172a2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017374`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017374`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800172cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800172cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001737f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001738a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001737f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001738a`

## pseudocode

```c
void __fastcall CTVOAgent::CompleteActiveRetrieval(
        LPCRITICAL_SECTION lpCriticalSection,
        _QWORD *hMem,
        int a3,
        int a4,
        CRL_CONTEXT *pCrlContext)
{
  _QWORD *v9; // rcx
  HLOCAL *v10; // rax
  _QWORD *v11; // rdi
  _QWORD *v12; // rsi
  void *v13; // rcx
  void *v14; // rcx
  __int64 v15; // rax
  __int32 v16; // r15d
  __int64 v17; // rax
  _QWORD v18[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( !hMem )
  {
    ++dword_180032960;
    return;
  }
  ++dword_180032964;
  EnterCriticalSection(lpCriticalSection);
  v9 = (_QWORD *)*hMem;
  if ( *(_QWORD **)(*hMem + 8LL) != hMem || (v10 = (HLOCAL *)hMem[1], *v10 != hMem) )
LABEL_27:
    __fastfail(3u);
  *v10 = v9;
  v9[1] = v10;
  LeaveCriticalSection(lpCriticalSection);
  v11 = hMem + 2;
  while ( 1 )
  {
    v12 = (_QWORD *)*v11;
    if ( (_QWORD *)*v11 == v11 )
      break;
    if ( (_QWORD *)v12[1] != v11 )
      goto LABEL_27;
    v15 = *v12;
    if ( *(_QWORD **)(*v12 + 8LL) != v12 )
      goto LABEL_27;
    *v11 = v15;
    *(_QWORD *)(v15 + 8) = v11;
    *((_DWORD *)v12 + 42) = a3;
    if ( a4 )
    {
      if ( memcmp_0(v12 + 15, hMem + 15, 0x20u) )
      {
        ++dword_18003296C;
        v16 = -1;
        goto LABEL_16;
      }
    }
    else if ( pCrlContext && !ObjectContextIsValidForSubject((const char *)2, pCrlContext, (void *)v12[7], 0) )
    {
      ++dword_18003296C;
      v16 = -1;
      goto LABEL_16;
    }
    v16 = 1;
    if ( a3 )
    {
      v17 = hMem[20];
      if ( v17 && v12[20] )
      {
        v18[1] = v12[20];
        v18[0] = v17;
        I_CertDiagControl(26, v18, 0);
      }
    }
    else if ( pCrlContext )
    {
      v12[22] = CertDuplicateCRLContext(pCrlContext);
    }
LABEL_16:
    _InterlockedExchange((volatile __int32 *)v12 + 46, v16);
    ++dword_180032968;
    SetEvent((HANDLE)v12[4]);
  }
  v13 = (void *)hMem[4];
  if ( v13 )
    CloseHandle(v13);
  v14 = (void *)hMem[5];
  if ( v14 )
    CloseHandle(v14);
  operator delete(hMem);
}

```

## disassembly

```asm
0x180017270  mov     [rsp+arg_10], rbx
0x180017275  push    rbp
0x180017276  push    rdi
0x180017277  push    r14
0x180017279  sub     rsp, 30h
0x18001727d  mov     r14d, r9d
0x180017280  mov     ebp, r8d
0x180017283  mov     rbx, rdx
0x180017286  mov     rdi, rcx
0x180017289  test    rdx, rdx
0x18001728c  jz      loc_180017401
0x180017292  inc     cs:dword_180032964
0x180017298  mov     [rsp+48h+arg_0], rsi
0x18001729d  mov     [rsp+48h+arg_8], r15
0x1800172a2  call    cs:__imp_EnterCriticalSection
0x1800172a8  mov     rcx, [rbx]
0x1800172ab  cmp     [rcx+8], rbx
0x1800172af  jnz     loc_180017444
0x1800172b5  mov     rax, [rbx+8]
0x1800172b9  cmp     [rax], rbx
0x1800172bc  jnz     loc_180017444
0x1800172c2  mov     [rax], rcx
0x1800172c5  mov     [rcx+8], rax
0x1800172c9  mov     rcx, rdi; lpCriticalSection
0x1800172cc  call    cs:__imp_LeaveCriticalSection
0x1800172d2  lea     rdi, [rbx+10h]
0x1800172d6  mov     rsi, [rdi]
0x1800172d9  cmp     rsi, rdi
0x1800172dc  jnz     short loc_180017317
0x1800172de  mov     rcx, [rbx+20h]; hObject
0x1800172e2  test    rcx, rcx
0x1800172e5  jnz     loc_18001738A
0x1800172eb  mov     rcx, [rbx+28h]; hObject
0x1800172ef  test    rcx, rcx
0x1800172f2  jnz     loc_18001737F
0x1800172f8  mov     rcx, rbx; hMem
0x1800172fb  mov     rsi, [rsp+48h+arg_0]
0x180017300  mov     r15, [rsp+48h+arg_8]
0x180017305  mov     rbx, [rsp+48h+arg_10]
0x18001730a  add     rsp, 30h
0x18001730e  pop     r14
0x180017310  pop     rdi
0x180017311  pop     rbp
0x180017312  jmp     ??3@YAXPEAX@Z; operator delete(void *)
0x180017317  cmp     [rsi+8], rdi
0x18001731b  jnz     loc_180017444
0x180017321  mov     rax, [rsi]
0x180017324  cmp     [rax+8], rsi
0x180017328  jnz     loc_180017444
0x18001732e  mov     [rdi], rax
0x180017331  mov     [rax+8], rdi
0x180017335  mov     [rsi+0A8h], ebp
0x18001733b  test    r14d, r14d
0x18001733e  jz      short loc_180017395
0x180017340  lea     rdx, [rbx+78h]; Buf2
0x180017344  mov     r8d, 20h ; ' '; Size
0x18001734a  lea     rcx, [rsi+78h]; Buf1
0x18001734e  call    memcmp_0
0x180017353  test    eax, eax
0x180017355  jz      short loc_18001739D
0x180017357  inc     cs:dword_18003296C
0x18001735d  mov     r15d, 0FFFFFFFFh
0x180017363  xchg    r15d, [rsi+0B8h]
0x18001736a  inc     cs:dword_180032968
0x180017370  mov     rcx, [rsi+20h]; hEvent
0x180017374  call    cs:__imp_SetEvent
0x18001737a  jmp     loc_1800172D6
0x18001737f  call    cs:__imp_CloseHandle
0x180017385  jmp     loc_1800172F8
0x18001738a  call    cs:__imp_CloseHandle
0x180017390  jmp     loc_1800172EB
0x180017395  cmp     [rsp+48h+pCrlContext], 0
0x18001739b  jnz     short loc_180017415
0x18001739d  mov     r15d, 1
0x1800173a3  test    ebp, ebp
0x1800173a5  jz      short loc_1800173DE
0x1800173a7  mov     rax, [rbx+0A0h]
0x1800173ae  test    rax, rax
0x1800173b1  jz      short loc_180017363
0x1800173b3  mov     rcx, [rsi+0A0h]
0x1800173ba  test    rcx, rcx
0x1800173bd  jz      short loc_180017363
0x1800173bf  mov     [rsp+48h+var_20], rcx
0x1800173c4  lea     rdx, [rsp+48h+var_28]
0x1800173c9  mov     ecx, 1Ah
0x1800173ce  mov     [rsp+48h+var_28], rax
0x1800173d3  xor     r8d, r8d
0x1800173d6  call    cs:__imp_I_CertDiagControl
0x1800173dc  jmp     short loc_180017363
0x1800173de  cmp     [rsp+48h+pCrlContext], 0
0x1800173e4  jz      loc_180017363
0x1800173ea  mov     rcx, [rsp+48h+pCrlContext]; pCrlContext
0x1800173ef  call    cs:__imp_CertDuplicateCRLContext
0x1800173f5  mov     [rsi+0B0h], rax
0x1800173fc  jmp     loc_180017363
0x180017401  inc     cs:dword_180032960
0x180017407  mov     rbx, [rsp+48h+arg_10]
0x18001740c  add     rsp, 30h
0x180017410  pop     r14
0x180017412  pop     rdi
0x180017413  pop     rbp
0x180017414  retn
0x180017415  mov     r8, [rsi+38h]; void *
0x180017419  xor     r9d, r9d; struct _CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *
0x18001741c  mov     rdx, [rsp+48h+pCrlContext]; void *
0x180017421  mov     ecx, 2; char *
0x180017426  call    ?ObjectContextIsValidForSubject@@YAHPEBDPEAX1PEAU_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO@@@Z; ObjectContextIsValidForSubject(char const *,void *,void *,_CRYPT_GET_TIME_VALID_OBJECT_EXTRA_INFO *)
0x18001742b  test    eax, eax
0x18001742d  jnz     loc_18001739D
0x180017433  inc     cs:dword_18003296C
0x180017439  mov     r15d, 0FFFFFFFFh
0x18001743f  jmp     loc_180017363
0x180017444  mov     ecx, 3
0x180017449  int     29h; Win8: RtlFailFast(ecx)
```
