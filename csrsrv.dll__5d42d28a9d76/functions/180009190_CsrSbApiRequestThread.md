# CsrSbApiRequestThread

- ea: `0x180009190`
- end: `0x180009365`
- name: `CsrSbApiRequestThread`
- size: `469`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callees

- `0x180001140`
- `0x1800035c0`
- `0x1800090cc`
- `0x180009190`
- `0x180009370`
- `0x1800095b0`
- `0x18000a2b0`
- `0x18000ab61`
- `0x18000b010`

## import_xrefs

- `ntdll!NtClose` at `0x1800092c6`
- `ntdll!NtClose` at `0x1800092c6`
- `ntdll!NtDelayExecution` at `0x18000924d`
- `ntdll!NtDelayExecution` at `0x18000924d`
- `ntdll!NtAlpcCancelMessage` at `0x180009354`
- `ntdll!NtAlpcCancelMessage` at `0x180009354`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180009224`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180009224`

## string_xrefs

- `0x180009265`: `CsrSbApiRequestThread`
- `0x1800092fc`: `CsrSbApiRequestThread`

## pseudocode

```c
void __noreturn CsrSbApiRequestThread()
{
  _BYTE *v0; // rbx
  int v1; // eax
  __int16 v2; // dx
  HANDLE Handle[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v4; // [rsp+50h] [rbp-B0h]
  __int64 v5; // [rsp+60h] [rbp-A0h]
  _BYTE v6[4]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v7; // [rsp+74h] [rbp-8Ch]
  unsigned int v8; // [rsp+98h] [rbp-68h]
  int v9; // [rsp+9Ch] [rbp-64h]
  __int64 v10; // [rsp+1A8h] [rbp+A8h] BYREF
  LARGE_INTEGER Interval; // [rsp+1B0h] [rbp+B0h] BYREF

  memset_0(v6, 0, 0x120u);
  v0 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v5 = 0;
        v10 = 288;
        *(_OWORD *)Handle = 0;
        v4 = 0;
        LODWORD(Handle[0]) = 0x20000000;
        v1 = NtAlpcSendWaitReceivePort(CsrSbApiPort, v0 != 0 ? 0x10000 : 0, v0, 0, v6, &v10, Handle, 0);
        v0 = 0;
        if ( v1 != -1073741801 )
          break;
        Interval.QuadPart = -50000000;
        NtDelayExecution(0, &Interval);
      }
      if ( v1 >= 0 )
        break;
      CsrpLogFailure("CsrSbApiRequestThread");
    }
    v2 = v7;
    if ( (unsigned __int8)v7 == 1 )
      break;
    if ( (unsigned __int8)v7 == 3 )
    {
LABEL_15:
      if ( v8 < 4 )
      {
        ((void (__fastcall *)(_BYTE *))CsrServerSbApiDispatch[v8])(v6);
      }
      else
      {
        CsrpLogModuleFailureInt("CsrSbApiRequestThread", -1073741822);
        v8 = 4;
        v9 = -1073741822;
      }
      if ( !v0 )
      {
        v2 = v7;
        goto LABEL_20;
      }
    }
    else if ( (unsigned __int8)v7 == 5 )
    {
      if ( Handle[1] )
        NtClose(Handle[1]);
    }
    else if ( (unsigned __int8)v7 != 6 )
    {
      if ( (unsigned __int8)v7 == 10 )
      {
        CsrSbApiHandleConnectionRequest((__int64)v6);
      }
      else
      {
LABEL_20:
        if ( (v2 & 0x2000) != 0 )
          NtAlpcCancelMessage(CsrSbApiPort, 0, &Handle[1]);
      }
    }
  }
  v0 = v6;
  goto LABEL_15;
}

```

## disassembly

```asm
0x180009190  mov     [rsp-8+arg_0], rbx
0x180009195  push    rbp
0x180009196  lea     rbp, [rsp-90h]
0x18000919e  sub     rsp, 190h
0x1800091a5  xor     edx, edx; Val
0x1800091a7  lea     rcx, [rsp+190h+var_120]; void *
0x1800091ac  mov     r8d, 120h; Size
0x1800091b2  call    memset_0
0x1800091b7  xor     ebx, ebx
0x1800091b9  mov     rcx, cs:CsrSbApiPort
0x1800091c0  xor     eax, eax
0x1800091c2  mov     [rsp+190h+var_130], rax
0x1800091c7  xorps   xmm0, xmm0
0x1800091ca  sub     rax, rbx
0x1800091cd  mov     [rsp+190h+var_158], 0
0x1800091d6  neg     rax
0x1800091d9  mov     [rbp+90h+arg_8], 120h
0x1800091e4  lea     rax, [rsp+190h+Handle]
0x1800091e9  mov     r8, rbx
0x1800091ec  mov     [rsp+190h+var_160], rax
0x1800091f1  sbb     edx, edx
0x1800091f3  lea     rax, [rbp+90h+arg_8]
0x1800091fa  and     edx, 10000h
0x180009200  mov     [rsp+190h+var_168], rax
0x180009205  xor     r9d, r9d
0x180009208  lea     rax, [rsp+190h+var_120]
0x18000920d  movups  xmmword ptr [rsp+190h+Handle], xmm0
0x180009212  mov     qword ptr [rsp+190h+var_170], rax
0x180009217  movups  [rsp+190h+var_140], xmm0
0x18000921c  mov     dword ptr [rsp+190h+Handle], 20000000h
0x180009224  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18000922b  nop     dword ptr [rax+rax+00h]
0x180009230  xor     ebx, ebx
0x180009232  cmp     eax, 0C0000017h
0x180009237  jnz     short loc_18000925E
0x180009239  lea     rdx, [rbp+90h+Interval]; Interval
0x180009240  mov     qword ptr [rbp+90h+Interval], 0FFFFFFFFFD050F80h
0x18000924b  xor     ecx, ecx; Alertable
0x18000924d  call    cs:__imp_NtDelayExecution
0x180009254  nop     dword ptr [rax+rax+00h]
0x180009259  jmp     loc_1800091B9
0x18000925e  test    eax, eax
0x180009260  jns     short loc_18000927B
0x180009262  mov     r8d, eax
0x180009265  lea     rcx, aCsrsbapireques; "CsrSbApiRequestThread"
0x18000926c  mov     edx, 74h ; 't'
0x180009271  call    CsrpLogFailure
0x180009276  jmp     loc_1800091B9
0x18000927b  movzx   edx, [rsp+190h+var_11C]
0x180009280  mov     ecx, edx
0x180009282  and     ecx, 0FFFF00FFh
0x180009288  sub     ecx, 1
0x18000928b  jz      short loc_1800092D7
0x18000928d  sub     ecx, 2
0x180009290  jz      short loc_1800092DC
0x180009292  sub     ecx, 2
0x180009295  jz      short loc_1800092B8
0x180009297  sub     ecx, 1
0x18000929a  jz      loc_1800091B9
0x1800092a0  cmp     ecx, 4
0x1800092a3  jnz     loc_18000933B
0x1800092a9  lea     rcx, [rsp+190h+var_120]
0x1800092ae  call    CsrSbApiHandleConnectionRequest
0x1800092b3  jmp     loc_1800091B9
0x1800092b8  mov     rcx, [rsp+190h+Handle+8]; Handle
0x1800092bd  test    rcx, rcx
0x1800092c0  jz      loc_1800091B9
0x1800092c6  call    cs:__imp_NtClose
0x1800092cd  nop     dword ptr [rax+rax+00h]
0x1800092d2  jmp     loc_1800091B9
0x1800092d7  lea     rbx, [rsp+190h+var_120]
0x1800092dc  movsxd  rax, [rbp+90h+var_F8]
0x1800092e0  cmp     eax, 4
0x1800092e3  jb      short loc_180009318
0x1800092e5  mov     r9d, eax
0x1800092e8  mov     [rsp+190h+var_170], 0C0000002h; int
0x1800092f0  lea     r8, qword_18000C660
0x1800092f7  mov     edx, 8Eh
0x1800092fc  lea     rcx, aCsrsbapireques; "CsrSbApiRequestThread"
0x180009303  call    CsrpLogModuleFailureInt
0x180009308  mov     [rbp+90h+var_F8], 4
0x18000930f  mov     [rbp+90h+var_F4], 0C0000002h
0x180009316  jmp     short loc_18000932D
0x180009318  lea     rdx, CsrServerSbApiDispatch
0x18000931f  mov     rax, ds:(CsrServerSbApiDispatch - 18000C038h)[rdx+rax*8]
0x180009323  lea     rcx, [rsp+190h+var_120]
0x180009328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000932d  test    rbx, rbx
0x180009330  jnz     loc_1800091B9
0x180009336  movzx   edx, [rsp+190h+var_11C]
0x18000933b  bt      dx, 0Dh
0x180009340  jnb     loc_1800091B9
0x180009346  mov     rcx, cs:CsrSbApiPort
0x18000934d  lea     r8, [rsp+190h+Handle+8]
0x180009352  xor     edx, edx
0x180009354  call    cs:__imp_NtAlpcCancelMessage
0x18000935b  nop     dword ptr [rax+rax+00h]
0x180009360  jmp     loc_1800091B9
```
