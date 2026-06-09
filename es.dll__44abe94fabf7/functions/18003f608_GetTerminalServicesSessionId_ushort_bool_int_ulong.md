# GetTerminalServicesSessionId(ushort *,bool,int *,ulong *)

- ea: `0x18003f608`
- end: `0x18003f74d`
- name: `?GetTerminalServicesSessionId@@YAJPEAG_NPEAHPEAK@Z`
- size: `325`
- prototype: `__int64 __fastcall(unsigned __int16 *, bool, int *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001a838`
- `0x180029b50`

## callees

- `0x18003f1d4`
- `0x18003f378`
- `0x18003f608`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f649`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f649`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f725`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f725`
- `WTSAPI32!WTSFreeMemory` at `0x18003f734`
- `WTSAPI32!WTSFreeMemory` at `0x18003f734`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18003f6bd`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18003f6bd`

## pseudocode

```c
__int64 __fastcall GetTerminalServicesSessionId(unsigned __int16 *a1, char a2, int *a3, unsigned int *a4)
{
  unsigned __int16 *v8; // rax
  wchar_t *v9; // r14
  int DomainNameFromTextualSid; // ebx
  void *v11; // rdx
  void *v12; // rdx
  signed int LastError; // eax
  __int64 i; // rsi
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+30h] [rbp-10h] BYREF
  unsigned int SessionId; // [rsp+80h] [rbp+40h] BYREF
  DWORD pCount; // [rsp+88h] [rbp+48h] BYREF

  *a4 = -1;
  ppSessionInfo = 0;
  pCount = 0;
  *a3 = 0;
  v8 = (unsigned __int16 *)CoTaskMemAlloc(0x800u);
  v9 = v8;
  if ( !v8 )
  {
    DomainNameFromTextualSid = -2147024882;
    goto LABEL_20;
  }
  DomainNameFromTextualSid = GetDomainNameFromTextualSid(a1, v8);
  if ( DomainNameFromTextualSid >= 0 )
  {
    if ( a2 )
      goto LABEL_8;
    SessionId = -1;
    DomainNameFromTextualSid = CompareTerminalServicesSessionName(v9, v11, &SessionId, a3);
    if ( DomainNameFromTextualSid >= 0 )
    {
      if ( *a3 )
      {
        *a4 = SessionId;
        goto LABEL_19;
      }
LABEL_8:
      if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
      {
        for ( i = 0; (unsigned int)i < pCount; i = (unsigned int)(i + 1) )
        {
          SessionId = ppSessionInfo[i].SessionId;
          DomainNameFromTextualSid = CompareTerminalServicesSessionName(v9, v12, &SessionId, a3);
          if ( DomainNameFromTextualSid < 0 )
            goto LABEL_19;
          if ( *a3 )
          {
            *a4 = SessionId;
            break;
          }
        }
        if ( !*a3 )
          DomainNameFromTextualSid = -2147220976;
      }
      else
      {
        LastError = GetLastError();
        DomainNameFromTextualSid = LastError;
        if ( LastError > 0 )
          DomainNameFromTextualSid = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
LABEL_19:
  CoTaskMemFree(v9);
LABEL_20:
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  return (unsigned int)DomainNameFromTextualSid;
}

```

## disassembly

```asm
0x18003f608  mov     [rsp-28h+arg_0], rbx
0x18003f60d  push    rbp
0x18003f60e  push    rsi
0x18003f60f  push    rdi
0x18003f610  push    r14
0x18003f612  push    r15
0x18003f614  mov     rbp, rsp
0x18003f617  sub     rsp, 40h
0x18003f61b  mov     rbx, rcx
0x18003f61e  mov     dword ptr [r9], 0FFFFFFFFh
0x18003f625  mov     ecx, 800h; cb
0x18003f62a  mov     [rbp+ppSessionInfo], 0
0x18003f632  mov     r15, r9
0x18003f635  mov     [rbp+arg_18], 0
0x18003f63c  mov     rdi, r8
0x18003f63f  mov     dword ptr [r8], 0
0x18003f646  mov     sil, dl
0x18003f649  call    cs:__imp_CoTaskMemAlloc
0x18003f64f  mov     r14, rax
0x18003f652  test    rax, rax
0x18003f655  jnz     short loc_18003F661
0x18003f657  mov     ebx, 8007000Eh
0x18003f65c  jmp     loc_18003F72B
0x18003f661  mov     rdx, r14; unsigned __int16 *
0x18003f664  mov     rcx, rbx; unsigned __int16 *
0x18003f667  call    ?GetDomainNameFromTextualSid@@YAJPEAG0K@Z; GetDomainNameFromTextualSid(ushort *,ushort *,ulong)
0x18003f66c  mov     ebx, eax
0x18003f66e  test    eax, eax
0x18003f670  js      loc_18003F722
0x18003f676  test    sil, sil
0x18003f679  jnz     short loc_18003F6A8
0x18003f67b  mov     r9, rdi; int *
0x18003f67e  mov     [rbp+arg_10], 0FFFFFFFFh
0x18003f685  lea     r8, [rbp+arg_10]; unsigned int *
0x18003f689  mov     rcx, r14; String2
0x18003f68c  call    ?CompareTerminalServicesSessionName@@YAJPEAGPEAXPEAKPEAH@Z; CompareTerminalServicesSessionName(ushort *,void *,ulong *,int *)
0x18003f691  mov     ebx, eax
0x18003f693  test    eax, eax
0x18003f695  js      loc_18003F722
0x18003f69b  cmp     dword ptr [rdi], 0
0x18003f69e  jz      short loc_18003F6A8
0x18003f6a0  mov     eax, [rbp+arg_10]
0x18003f6a3  mov     [r15], eax
0x18003f6a6  jmp     short loc_18003F722
0x18003f6a8  xor     edx, edx; Reserved
0x18003f6aa  lea     rax, [rbp+arg_18]
0x18003f6ae  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x18003f6b2  mov     [rsp+40h+pCount], rax; pCount
0x18003f6b7  xor     ecx, ecx; hServer
0x18003f6b9  lea     r8d, [rdx+1]; Version
0x18003f6bd  call    cs:__imp_WTSEnumerateSessionsW
0x18003f6c3  test    eax, eax
0x18003f6c5  jnz     short loc_18003F6DE
0x18003f6c7  call    cs:__imp_GetLastError
0x18003f6cd  mov     ebx, eax
0x18003f6cf  test    eax, eax
0x18003f6d1  jle     short loc_18003F722
0x18003f6d3  movzx   ebx, ax
0x18003f6d6  or      ebx, 80070000h
0x18003f6dc  jmp     short loc_18003F722
0x18003f6de  xor     esi, esi
0x18003f6e0  cmp     esi, [rbp+arg_18]
0x18003f6e3  jnb     short loc_18003F717
0x18003f6e5  mov     rax, [rbp+ppSessionInfo]
0x18003f6e9  lea     rcx, [rsi+rsi*2]
0x18003f6ed  mov     r9, rdi; int *
0x18003f6f0  lea     r8, [rbp+arg_10]; unsigned int *
0x18003f6f4  mov     ecx, [rax+rcx*8]
0x18003f6f7  mov     [rbp+arg_10], ecx
0x18003f6fa  mov     rcx, r14; String2
0x18003f6fd  call    ?CompareTerminalServicesSessionName@@YAJPEAGPEAXPEAKPEAH@Z; CompareTerminalServicesSessionName(ushort *,void *,ulong *,int *)
0x18003f702  mov     ebx, eax
0x18003f704  test    eax, eax
0x18003f706  js      short loc_18003F722
0x18003f708  cmp     dword ptr [rdi], 0
0x18003f70b  jnz     short loc_18003F711
0x18003f70d  inc     esi
0x18003f70f  jmp     short loc_18003F6E0
0x18003f711  mov     eax, [rbp+arg_10]
0x18003f714  mov     [r15], eax
0x18003f717  cmp     dword ptr [rdi], 0
0x18003f71a  mov     eax, 80040210h
0x18003f71f  cmovz   ebx, eax
0x18003f722  mov     rcx, r14; pv
0x18003f725  call    cs:__imp_CoTaskMemFree
0x18003f72b  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x18003f72f  test    rcx, rcx
0x18003f732  jz      short loc_18003F73A
0x18003f734  call    cs:__imp_WTSFreeMemory
0x18003f73a  mov     eax, ebx
0x18003f73c  mov     rbx, [rsp+40h+arg_0]
0x18003f741  add     rsp, 40h
0x18003f745  pop     r15
0x18003f747  pop     r14
0x18003f749  pop     rdi
0x18003f74a  pop     rsi
0x18003f74b  pop     rbp
0x18003f74c  retn
```
