# ChapInit

- ea: `0x18000f950`
- end: `0x18000faa4`
- name: `ChapInit`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180015da0`

## callees

- `0x180003bd0`
- `0x1800045c0`
- `0x180004690`
- `0x18000e240`
- `0x18000f950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa08`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18000fa91`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18000fa91`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x18000f9fe`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x18000f9fe`

## pseudocode

```c
__int64 __fastcall ChapInit(unsigned int a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  DWORD inited; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  DWORD nSize; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, a1);
  v4 = g_dwRefCount;
  if ( a1 )
  {
    if ( !g_dwRefCount )
    {
      DebuggingInit(1);
      if ( g_hLsa == (HANDLE)-1LL )
      {
        inited = InitLSA();
        if ( inited )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return inited;
          v7 = 11;
LABEL_9:
          WPP_SF_d(v6[2], v7, &WPP_d3ccaec7459834abcb1c6432c7781bd4_Traceguids, inited);
          return inited;
        }
      }
      nSize = 16;
      if ( !GetComputerNameA(szComputerName, &nSize) )
      {
        inited = GetLastError();
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return inited;
        v7 = 12;
        goto LABEL_9;
      }
      v4 = g_dwRefCount;
    }
    g_dwRefCount = v4 + 1;
  }
  else if ( g_dwRefCount )
  {
    --g_dwRefCount;
    if ( v4 == 1 )
    {
      DebuggingInit(0);
      if ( g_hLsa != (HANDLE)-1LL )
      {
        LsaDeregisterLogonProcess(g_hLsa);
        g_hLsa = (HANDLE)-1LL;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, a3, a1);
  return 0;
}

```

## disassembly

```asm
0x18000f950  mov     [rsp+arg_8], rbx
0x18000f955  mov     [rsp+arg_10], rsi
0x18000f95a  push    rdi
0x18000f95b  sub     rsp, 30h
0x18000f95f  mov     edi, ecx
0x18000f961  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f968  lea     rsi, WPP_GLOBAL_Control
0x18000f96f  cmp     rcx, rsi
0x18000f972  jz      short loc_18000F98F
0x18000f974  mov     eax, dword ptr cs:g_hLsa
0x18000f97a  mov     edx, 0Ah
0x18000f97f  mov     rcx, [rcx+10h]
0x18000f983  mov     r9d, edi
0x18000f986  mov     [rsp+38h+var_10], eax
0x18000f98a  call    WPP_SF_DDD
0x18000f98f  mov     eax, cs:g_dwRefCount
0x18000f995  test    edi, edi
0x18000f997  jz      loc_18000FA6B
0x18000f99d  test    eax, eax
0x18000f99f  jnz     loc_18000FA29
0x18000f9a5  lea     ecx, [rax+1]
0x18000f9a8  call    DebuggingInit
0x18000f9ad  cmp     cs:g_hLsa, 0FFFFFFFFFFFFFFFFh
0x18000f9b5  jnz     short loc_18000F9EA
0x18000f9b7  call    InitLSA
0x18000f9bc  mov     ebx, eax
0x18000f9be  test    eax, eax
0x18000f9c0  jz      short loc_18000F9EA
0x18000f9c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9c9  cmp     rcx, rsi
0x18000f9cc  jz      short loc_18000F9E6
0x18000f9ce  mov     edx, 0Bh
0x18000f9d3  mov     rcx, [rcx+10h]
0x18000f9d7  lea     r8, WPP_d3ccaec7459834abcb1c6432c7781bd4_Traceguids
0x18000f9de  mov     r9d, ebx
0x18000f9e1  call    WPP_SF_d
0x18000f9e6  mov     eax, ebx
0x18000f9e8  jmp     short loc_18000FA5B
0x18000f9ea  lea     rdx, [rsp+38h+nSize]; nSize
0x18000f9ef  mov     [rsp+38h+nSize], 10h
0x18000f9f7  lea     rcx, szComputerName; lpBuffer
0x18000f9fe  call    cs:__imp_GetComputerNameA
0x18000fa04  test    eax, eax
0x18000fa06  jnz     short loc_18000FA23
0x18000fa08  call    cs:__imp_GetLastError
0x18000fa0e  mov     ebx, eax
0x18000fa10  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa17  cmp     rcx, rsi
0x18000fa1a  jz      short loc_18000F9E6
0x18000fa1c  mov     edx, 0Ch
0x18000fa21  jmp     short loc_18000F9D3
0x18000fa23  mov     eax, cs:g_dwRefCount
0x18000fa29  inc     eax
0x18000fa2b  mov     cs:g_dwRefCount, eax
0x18000fa31  mov     rax, cs:g_hLsa
0x18000fa38  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa3f  cmp     rcx, rsi
0x18000fa42  jz      short loc_18000FA59
0x18000fa44  mov     rcx, [rcx+10h]
0x18000fa48  mov     edx, 0Dh
0x18000fa4d  mov     r9d, edi
0x18000fa50  mov     [rsp+38h+var_10], eax
0x18000fa54  call    WPP_SF_DDD
0x18000fa59  xor     eax, eax
0x18000fa5b  mov     rbx, [rsp+38h+arg_8]
0x18000fa60  mov     rsi, [rsp+38h+arg_10]
0x18000fa65  add     rsp, 30h
0x18000fa69  pop     rdi
0x18000fa6a  retn
0x18000fa6b  test    eax, eax
0x18000fa6d  jz      short loc_18000FA31
0x18000fa6f  add     eax, 0FFFFFFFFh
0x18000fa72  mov     cs:g_dwRefCount, eax
0x18000fa78  jnz     short loc_18000FA31
0x18000fa7a  xor     ecx, ecx
0x18000fa7c  call    DebuggingInit
0x18000fa81  mov     rax, cs:g_hLsa
0x18000fa88  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fa8c  jz      short loc_18000FA38
0x18000fa8e  mov     rcx, rax; LsaHandle
0x18000fa91  call    cs:__imp_LsaDeregisterLogonProcess
0x18000fa97  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fa9b  mov     cs:g_hLsa, rax
0x18000faa2  jmp     short loc_18000FA38
```
