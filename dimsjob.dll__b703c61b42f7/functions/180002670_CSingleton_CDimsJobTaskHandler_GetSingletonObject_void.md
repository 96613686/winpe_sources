# CSingleton<CDimsJobTaskHandler>::GetSingletonObject(void)

- ea: `0x180002670`
- end: `0x180002770`
- name: `?GetSingletonObject@?$CSingleton@VCDimsJobTaskHandler@@@@SAPEAVCDimsJobTaskHandler@@XZ`
- size: `256`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1800025e0`

## callees

- `0x180002670`
- `0x180002780`
- `0x18000a360`
- `0x18000ab3c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002713`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800026b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800026b8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800026ff`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800026ff`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000269e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000269e`

## pseudocode

```c
__int64 CSingleton<CDimsJobTaskHandler>::GetSingletonObject()
{
  char *v0; // rdi
  __int64 v1; // rbx
  CDimsJobTaskHandler *v2; // rax
  struct CModule *v3; // rdx
  __int64 v4; // rbx
  signed int LastError; // ebx
  signed int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  char *v8; // [rsp+38h] [rbp+10h]

  v0 = (char *)&CSingleton<CDimsJobTaskHandler>::sm_rwlock + SHIDWORD((*CSingleton<CDimsJobTaskHandler>::sm_rwlock)[1]);
  v8 = v0;
  RtlAcquireSRWLockExclusive(&v0[*(int *)(*(_QWORD *)v0 + 4LL)]);
  v1 = CSingleton<CDimsJobTaskHandler>::sm_singleton;
  if ( !CSingleton<CDimsJobTaskHandler>::sm_singleton )
  {
    v2 = (CDimsJobTaskHandler *)LocalAlloc(0, 0x40u);
    v1 = (__int64)v2;
    if ( !v2 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_ea7d1c204d33352b702f4b4b9615bef9_Traceguids,
          (unsigned int)LastError);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      pExceptionObject = LastError;
      throw (CExcept *)&pExceptionObject;
    }
    CDimsJobTaskHandler::CDimsJobTaskHandler(v2, v3);
    *(_QWORD *)v1 = &CSingleton<CDimsJobTaskHandler>::`vftable';
    CSingleton<CDimsJobTaskHandler>::sm_singleton = v1;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(v1);
  v4 = CSingleton<CDimsJobTaskHandler>::sm_singleton;
  RtlReleaseSRWLockExclusive(&v0[*(int *)(*(_QWORD *)v0 + 4LL)]);
  return v4;
}

```

## disassembly

```asm
0x180002670  mov     [rsp+arg_10], rbx
0x180002675  push    rdi
0x180002676  sub     rsp, 20h
0x18000267a  mov     rax, cs:?sm_rwlock@?$CSingleton@VCDimsJobTaskHandler@@@@0U_CRwlock@@A; _CRwlock CSingleton<CDimsJobTaskHandler>::sm_rwlock
0x180002681  movsxd  rdi, dword ptr [rax+0Ch]
0x180002685  lea     rax, ?sm_rwlock@?$CSingleton@VCDimsJobTaskHandler@@@@0U_CRwlock@@A; _CRwlock CSingleton<CDimsJobTaskHandler>::sm_rwlock
0x18000268c  add     rdi, rax
0x18000268f  mov     [rsp+28h+arg_8], rdi
0x180002694  mov     rax, [rdi]
0x180002697  movsxd  rcx, dword ptr [rax+4]
0x18000269b  add     rcx, rdi
0x18000269e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800026a4  nop
0x1800026a5  mov     rbx, cs:?sm_singleton@?$CSingleton@VCDimsJobTaskHandler@@@@0PEAVCDimsJobTaskHandler@@EA; CDimsJobTaskHandler * CSingleton<CDimsJobTaskHandler>::sm_singleton
0x1800026ac  test    rbx, rbx
0x1800026af  jnz     short loc_1800026DF
0x1800026b1  mov     edx, 40h ; '@'; uBytes
0x1800026b6  xor     ecx, ecx; uFlags
0x1800026b8  call    cs:__imp_LocalAlloc
0x1800026be  mov     rbx, rax
0x1800026c1  test    rax, rax
0x1800026c4  jz      short loc_180002713
0x1800026c6  mov     rcx, rax; this
0x1800026c9  call    ??0CDimsJobTaskHandler@@IEAA@AEAVCModule@@@Z; CDimsJobTaskHandler::CDimsJobTaskHandler(CModule &)
0x1800026ce  lea     rax, ??_7?$CSingleton@VCDimsJobTaskHandler@@@@6B@; const CSingleton<CDimsJobTaskHandler>::`vftable'
0x1800026d5  mov     [rbx], rax
0x1800026d8  mov     cs:?sm_singleton@?$CSingleton@VCDimsJobTaskHandler@@@@0PEAVCDimsJobTaskHandler@@EA, rbx; CDimsJobTaskHandler * CSingleton<CDimsJobTaskHandler>::sm_singleton
0x1800026df  mov     rax, [rbx]
0x1800026e2  mov     rcx, rbx
0x1800026e5  mov     rax, [rax+8]
0x1800026e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ee  mov     rbx, cs:?sm_singleton@?$CSingleton@VCDimsJobTaskHandler@@@@0PEAVCDimsJobTaskHandler@@EA; CDimsJobTaskHandler * CSingleton<CDimsJobTaskHandler>::sm_singleton
0x1800026f5  mov     rcx, [rdi]
0x1800026f8  movsxd  rcx, dword ptr [rcx+4]
0x1800026fc  add     rcx, rdi
0x1800026ff  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002705  mov     rax, rbx
0x180002708  mov     rbx, [rsp+28h+arg_10]
0x18000270d  add     rsp, 20h
0x180002711  pop     rdi
0x180002712  retn
0x180002713  call    cs:__imp_GetLastError
0x180002719  nop
0x18000271a  mov     ebx, eax
0x18000271c  lea     rax, WPP_GLOBAL_Control
0x180002723  mov     rcx, cs:WPP_GLOBAL_Control
0x18000272a  cmp     rcx, rax
0x18000272d  jz      short loc_18000274D
0x18000272f  test    byte ptr [rcx+1Ch], 2
0x180002733  jz      short loc_18000274D
0x180002735  mov     edx, 0Ah
0x18000273a  mov     r9d, ebx
0x18000273d  lea     r8, WPP_ea7d1c204d33352b702f4b4b9615bef9_Traceguids
0x180002744  mov     rcx, [rcx+10h]
0x180002748  call    WPP_SF_D
0x18000274d  test    ebx, ebx
0x18000274f  jle     short loc_18000275A
0x180002751  movzx   ebx, bx
0x180002754  or      ebx, 80070000h
0x18000275a  mov     [rsp+28h+pExceptionObject], ebx
0x18000275e  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180002765  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000276a  call    _CxxThrowException_0
```
