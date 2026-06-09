# I_ScPnPCreateThreadpoolWait

- ea: `0x18000e4ac`
- end: `0x18000e5ea`
- name: `I_ScPnPCreateThreadpoolWait`
- size: `318`
- prototype: `__int64 __fastcall(__int64, __int64, void *, struct _TP_CALLBACK_ENVIRON_V3 *, struct _TP_WAIT **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006a40`
- `0x18000ec48`

## callees

- `0x180004600`
- `0x18000e4ac`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000e57c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000e57c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000e596`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000e596`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000e51a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000e51a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e530`

## pseudocode

```c
__int64 __fastcall I_ScPnPCreateThreadpoolWait(
        __int64 a1,
        __int64 a2,
        void *a3,
        struct _TP_CALLBACK_ENVIRON_V3 *a4,
        struct _TP_WAIT **a5)
{
  struct _TP_WAIT *ThreadpoolWait; // rax
  __int64 v8; // rcx
  DWORD LastError; // eax
  DWORD v10; // ebx
  struct _TP_WAIT *v11; // rcx

  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids, WPP_pszIndent);
  }
  ThreadpoolWait = *a5;
  if ( *a5 || (ThreadpoolWait = CreateThreadpoolWait(I_ScPnPHandleReaderAction, 0, a4), (*a5 = ThreadpoolWait) != 0) )
  {
    v10 = 0;
    SetThreadpoolWait(ThreadpoolWait, a3, 0);
  }
  else
  {
    WppTraceIndent(v8, 2);
    LastError = GetLastError();
    v10 = LastError;
    v11 = (struct _TP_WAIT *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
        WPP_pszIndent,
        LastError);
    }
    if ( v10 )
    {
      v11 = *a5;
      if ( *a5 )
      {
        CloseThreadpoolWait(v11);
        *a5 = 0;
      }
    }
  }
  WppTraceIndent(v11, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
      WPP_pszIndent,
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x18000e4ac  push    rbx
0x18000e4ae  push    rsi
0x18000e4af  push    rdi
0x18000e4b0  push    r15
0x18000e4b2  sub     rsp, 38h
0x18000e4b6  xor     edx, edx
0x18000e4b8  mov     rbx, r9
0x18000e4bb  mov     rsi, r8
0x18000e4be  call    WppTraceIndent
0x18000e4c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4ca  lea     r15, WPP_GLOBAL_Control
0x18000e4d1  cmp     rcx, r15
0x18000e4d4  jz      short loc_18000E4FE
0x18000e4d6  test    byte ptr [rcx+1Ch], 2
0x18000e4da  jz      short loc_18000E4FE
0x18000e4dc  cmp     byte ptr [rcx+19h], 5
0x18000e4e0  jb      short loc_18000E4FE
0x18000e4e2  mov     r9, cs:WPP_pszIndent
0x18000e4e9  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000e4f0  mov     rcx, [rcx+10h]
0x18000e4f4  mov     edx, 32h ; '2'
0x18000e4f9  call    WPP_SF_s
0x18000e4fe  mov     rdi, [rsp+58h+arg_20]
0x18000e506  mov     rax, [rdi]
0x18000e509  test    rax, rax
0x18000e50c  jnz     short loc_18000E58B
0x18000e50e  mov     r8, rbx; pcbe
0x18000e511  lea     rcx, I_ScPnPHandleReaderAction; pfnwa
0x18000e518  xor     edx, edx; pv
0x18000e51a  call    cs:__imp_CreateThreadpoolWait
0x18000e520  mov     [rdi], rax
0x18000e523  test    rax, rax
0x18000e526  jnz     short loc_18000E58B
0x18000e528  lea     edx, [rax+2]
0x18000e52b  call    WppTraceIndent
0x18000e530  call    cs:__imp_GetLastError
0x18000e536  mov     ebx, eax
0x18000e538  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e53f  cmp     rcx, r15
0x18000e542  jz      short loc_18000E570
0x18000e544  test    byte ptr [rcx+1Ch], 1
0x18000e548  jz      short loc_18000E570
0x18000e54a  cmp     byte ptr [rcx+19h], 2
0x18000e54e  jb      short loc_18000E570
0x18000e550  mov     r9, cs:WPP_pszIndent
0x18000e557  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000e55e  mov     rcx, [rcx+10h]
0x18000e562  mov     edx, 33h ; '3'
0x18000e567  mov     [rsp+58h+var_38], eax
0x18000e56b  call    WPP_SF_sD
0x18000e570  test    ebx, ebx
0x18000e572  jz      short loc_18000E59C
0x18000e574  mov     rcx, [rdi]; pwa
0x18000e577  test    rcx, rcx
0x18000e57a  jz      short loc_18000E59C
0x18000e57c  call    cs:__imp_CloseThreadpoolWait
0x18000e582  mov     qword ptr [rdi], 0
0x18000e589  jmp     short loc_18000E59C
0x18000e58b  xor     ebx, ebx
0x18000e58d  xor     r8d, r8d; pftTimeout
0x18000e590  mov     rdx, rsi; h
0x18000e593  mov     rcx, rax; pwa
0x18000e596  call    cs:__imp_SetThreadpoolWait
0x18000e59c  mov     edx, 1
0x18000e5a1  call    WppTraceIndent
0x18000e5a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5ad  cmp     rcx, r15
0x18000e5b0  jz      short loc_18000E5DE
0x18000e5b2  test    byte ptr [rcx+1Ch], 2
0x18000e5b6  jz      short loc_18000E5DE
0x18000e5b8  cmp     byte ptr [rcx+19h], 5
0x18000e5bc  jb      short loc_18000E5DE
0x18000e5be  mov     r9, cs:WPP_pszIndent
0x18000e5c5  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000e5cc  mov     rcx, [rcx+10h]
0x18000e5d0  mov     edx, 34h ; '4'
0x18000e5d5  mov     [rsp+58h+var_38], ebx
0x18000e5d9  call    WPP_SF_sD
0x18000e5de  mov     eax, ebx
0x18000e5e0  add     rsp, 38h
0x18000e5e4  pop     r15
0x18000e5e6  pop     rdi
0x18000e5e7  pop     rsi
0x18000e5e8  pop     rbx
0x18000e5e9  retn
```
