# CCorSvcMgr::IsRunningAtHigherThanMediumIL(int *)

- ea: `0x18002225c`
- end: `0x180022344`
- name: `?IsRunningAtHigherThanMediumIL@CCorSvcMgr@@AEAAJPEAH@Z`
- size: `232`
- prototype: `__int64 __fastcall(CCorSvcMgr *__hidden this, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002142c`

## callees

- `0x18002225c`
- `0x180039e9c`

## import_xrefs

- `ADVAPI32!GetSidSubAuthorityCount` at `0x1800222d3`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x1800222d3`
- `ADVAPI32!GetSidSubAuthority` at `0x1800222e2`
- `ADVAPI32!GetSidSubAuthority` at `0x1800222e2`
- `KERNEL32!GetCurrentProcess` at `0x18002229b`
- `KERNEL32!GetCurrentProcess` at `0x18002229b`
- `KERNEL32!HeapFree` at `0x180022325`
- `KERNEL32!HeapFree` at `0x180022325`
- `KERNEL32!GetProcessHeap` at `0x180022310`
- `KERNEL32!GetProcessHeap` at `0x180022310`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CCorSvcMgr::IsRunningAtHigherThanMediumIL(CCorSvcMgr *this, int *a2)
{
  HANDLE CurrentProcess; // rax
  int MandatoryLabelFromProcess; // edi
  int v5; // eax
  PSID v6; // rbx
  PUCHAR SidSubAuthorityCount; // rax
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+28h] [rbp-18h] BYREF
  int v12; // [rsp+30h] [rbp-10h]

  *a2 = 0;
  v12 = 0;
  lpMem = 0;
  CurrentProcess = GetCurrentProcess();
  MandatoryLabelFromProcess = SecurityUtil::GetMandatoryLabelFromProcess(CurrentProcess, (unsigned __int8 **)&lpMem);
  v5 = v12;
  if ( lpMem )
    v5 = 1;
  v12 = v5;
  if ( MandatoryLabelFromProcess >= 0 )
  {
    v6 = *(PSID *)lpMem;
    SidSubAuthorityCount = GetSidSubAuthorityCount(*(PSID *)lpMem);
    if ( *GetSidSubAuthority(v6, (unsigned int)*SidSubAuthorityCount - 1) > 0x2000 )
      *a2 = 1;
    MandatoryLabelFromProcess = 0;
  }
  if ( v12 )
  {
    v8 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v8);
    }
    v12 = 0;
  }
  return (unsigned int)MandatoryLabelFromProcess;
}

```

## disassembly

```asm
0x18002225c  mov     [rsp-18h+arg_0], rbx
0x180022261  mov     [rsp-18h+arg_10], rsi
0x180022266  push    rbp
0x180022267  push    rdi
0x180022268  push    r15
0x18002226a  mov     rbp, rsp
0x18002226d  sub     rsp, 40h
0x180022271  mov     rsi, rdx
0x180022274  and     [rbp+var_20], 0
0x180022278  and     dword ptr [rdx], 0
0x18002227b  and     [rbp+lpMem], 0
0x180022280  and     [rbp+var_10], 0
0x180022284  lea     rax, [rbp+lpMem]
0x180022288  mov     [rbp+arg_8], rax
0x18002228c  and     [rbp+lpMem], 0
0x180022291  mov     r15d, 1
0x180022297  mov     [rbp+var_20], r15d
0x18002229b  call    cs:__imp_GetCurrentProcess
0x1800222a1  mov     rcx, rax; void *
0x1800222a4  lea     rdx, [rbp+lpMem]; unsigned __int8 **
0x1800222a8  call    ?GetMandatoryLabelFromProcess@SecurityUtil@@SAJPEAXPEAPEAE@Z; SecurityUtil::GetMandatoryLabelFromProcess(void *,uchar * *)
0x1800222ad  mov     edi, eax
0x1800222af  mov     eax, r15d
0x1800222b2  and     eax, 0FFFFFFFEh
0x1800222b5  mov     [rbp+var_20], eax
0x1800222b8  mov     eax, [rbp+var_10]
0x1800222bb  mov     rbx, [rbp+lpMem]
0x1800222bf  test    rbx, rbx
0x1800222c2  cmovnz  eax, r15d
0x1800222c6  mov     [rbp+var_10], eax
0x1800222c9  test    edi, edi
0x1800222cb  js      short loc_1800222F5
0x1800222cd  mov     rbx, [rbx]
0x1800222d0  mov     rcx, rbx; pSid
0x1800222d3  call    cs:__imp_GetSidSubAuthorityCount
0x1800222d9  movzx   edx, byte ptr [rax]
0x1800222dc  sub     edx, r15d; nSubAuthority
0x1800222df  mov     rcx, rbx; pSid
0x1800222e2  call    cs:__imp_GetSidSubAuthority
0x1800222e8  cmp     dword ptr [rax], 2000h
0x1800222ee  jbe     short loc_1800222F3
0x1800222f0  mov     [rsi], r15d
0x1800222f3  xor     edi, edi
0x1800222f5  cmp     [rbp+var_10], 0
0x1800222f9  jz      short loc_18002232F
0x1800222fb  mov     rbx, [rbp+lpMem]
0x1800222ff  test    rbx, rbx
0x180022302  jz      short loc_18002232B
0x180022304  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002230b  test    rax, rax
0x18002230e  jnz     short loc_18002231D
0x180022310  call    cs:__imp_GetProcessHeap
0x180022316  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002231d  mov     r8, rbx; lpMem
0x180022320  xor     edx, edx; dwFlags
0x180022322  mov     rcx, rax; hHeap
0x180022325  call    cs:__imp_HeapFree
0x18002232b  and     [rbp+var_10], 0
0x18002232f  mov     eax, edi
0x180022331  mov     rbx, [rsp+40h+arg_0]
0x180022336  mov     rsi, [rsp+40h+arg_10]
0x18002233b  add     rsp, 40h
0x18002233f  pop     r15
0x180022341  pop     rdi
0x180022342  pop     rbp
0x180022343  retn
```
