# CWmiAsyncCancelMonitor::CreateInstance(CWmiAsyncCancelMonitor * *)

- ea: `0x1800160d8`
- end: `0x1800161b1`
- name: `?CreateInstance@CWmiAsyncCancelMonitor@@SAJPEAPEAV1@@Z`
- size: `217`
- prototype: `static int(struct CWmiAsyncCancelMonitor **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180026338`

## callees

- `0x180002d80`
- `0x180008810`
- `0x180009864`
- `0x18000b390`
- `0x1800160d8`
- `0x180016280`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001612e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001612e`

## pseudocode

```c
__int64 __fastcall CWmiAsyncCancelMonitor::CreateInstance(struct CWmiAsyncCancelMonitor **a1)
{
  int Error; // edi
  char *v3; // rax
  char *v4; // rbx
  UstVarLib *v5; // rcx
  __int64 v7; // rdx
  void **v8; // r9
  SIZE_T dwBytes; // [rsp+38h] [rbp+10h] BYREF

  Error = -2147024882;
  v3 = (char *)operator new(0x50u);
  v4 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 2) = 1;
    *((_QWORD *)v3 + 2) = 0;
    *(_QWORD *)v3 = &CWmiAsyncCancelMonitor::`vftable';
    *((_DWORD *)v3 + 6) = 0;
    *((_DWORD *)v3 + 18) = 0;
    if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v3 + 32), 0) )
    {
      *((_DWORD *)v4 + 18) = 1;
      *((_QWORD *)v4 + 2) = 0;
      dwBytes = 0;
      Error = ULongLongMult(5u, 0x18u, &dwBytes);
      if ( Error >= 0 )
        Error = UstVarLib::CscUtil_HeapAlloc(dwBytes, v7, (_QWORD *)v4 + 2, v8);
      if ( Error < 0 )
        goto LABEL_5;
      *((_DWORD *)v4 + 6) = 5;
    }
    else
    {
      Error = UstVarLib::ResultFromLastError(v5);
      if ( Error < 0 )
      {
LABEL_5:
        CRefCounted::ReleaseReference((CRefCounted *)v4);
        return (unsigned int)Error;
      }
    }
    *a1 = (struct CWmiAsyncCancelMonitor *)v4;
    _InterlockedIncrement((volatile signed __int32 *)v4 + 2);
    goto LABEL_5;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800160d8  mov     [rsp+arg_0], rbx
0x1800160dd  mov     [rsp+arg_10], rsi
0x1800160e2  push    rdi; void *
0x1800160e3  sub     rsp, 20h
0x1800160e7  mov     rsi, rcx
0x1800160ea  mov     edi, 8007000Eh
0x1800160ef  mov     ecx, 50h ; 'P'; Size
0x1800160f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800160f9  mov     rbx, rax
0x1800160fc  test    rax, rax
0x1800160ff  jz      short loc_180016152
0x180016101  mov     dword ptr [rax+8], 1
0x180016108  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001610c  lea     rax, ??_7CWmiAsyncCancelMonitor@@6B@; const CWmiAsyncCancelMonitor::`vftable'
0x180016113  mov     qword ptr [rbx+10h], 0
0x18001611b  xor     edx, edx; dwSpinCount
0x18001611d  mov     [rbx], rax
0x180016120  mov     dword ptr [rbx+18h], 0
0x180016127  mov     dword ptr [rbx+48h], 0
0x18001612e  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180016134  test    eax, eax
0x180016136  jnz     short loc_180016164
0x180016138  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x18001613d  mov     edi, eax
0x18001613f  test    eax, eax
0x180016141  js      short loc_18001614A
0x180016143  mov     [rsi], rbx
0x180016146  lock inc dword ptr [rbx+8]
0x18001614a  mov     rcx, rbx; this
0x18001614d  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x180016152  mov     rbx, [rsp+28h+arg_0]
0x180016157  mov     eax, edi
0x180016159  mov     rsi, [rsp+28h+arg_10]
0x18001615e  add     rsp, 20h
0x180016162  pop     rdi
0x180016163  retn
0x180016164  mov     edx, 18h; unsigned __int64
0x180016169  mov     dword ptr [rbx+48h], 1
0x180016170  lea     r8, [rsp+28h+dwBytes]; unsigned __int64 *
0x180016175  mov     qword ptr [rbx+10h], 0
0x18001617d  mov     [rsp+28h+dwBytes], 0
0x180016186  lea     ecx, [rdx-13h]; unsigned __int64
0x180016189  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001618e  mov     edi, eax
0x180016190  test    eax, eax
0x180016192  js      short loc_1800161A4
0x180016194  mov     rcx, [rsp+28h+dwBytes]; dwBytes
0x180016199  lea     r8, [rbx+10h]; int
0x18001619d  call    ?CscUtil_HeapAlloc@UstVarLib@@YAJ_KHPEAPEAXPEAX@Z; UstVarLib::CscUtil_HeapAlloc(unsigned __int64,int,void * *,void *)
0x1800161a2  mov     edi, eax
0x1800161a4  test    edi, edi
0x1800161a6  js      short loc_18001614A
0x1800161a8  mov     dword ptr [rbx+18h], 5
0x1800161af  jmp     short loc_180016143
```
