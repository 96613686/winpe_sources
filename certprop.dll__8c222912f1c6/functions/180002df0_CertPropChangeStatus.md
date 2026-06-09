# CertPropChangeStatus

- ea: `0x180002df0`
- end: `0x180002ed8`
- name: `CertPropChangeStatus`
- size: `232`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000fe80`

## callees

- `0x180002df0`
- `0x180003070`
- `0x180004600`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180002e46`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180002e46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e72`

## pseudocode

```c
__int64 __fastcall CertPropChangeStatus(int a1, int a2)
{
  unsigned int Certs; // edi
  char *v5; // rbx
  __int64 v6; // rcx

  Certs = 0;
  EnterCriticalSection(&g_csSessionList);
  v5 = (char *)g_pSessionList;
  if ( g_pSessionList )
  {
    while ( a1 != *((_DWORD *)v5 + 2) )
    {
      v5 = *(char **)v5;
      if ( !v5 )
        goto LABEL_8;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 72));
    *((_DWORD *)v5 + 8) = a2;
    *((_DWORD *)v5 + 141) = a2;
    if ( a2 )
    {
      *((_DWORD *)v5 + 7) = g_fEnableRootCertProp;
      Certs = ReaderMonitorReadCerts((__int64)(v5 + 24));
      if ( Certs )
      {
        WppTraceIndent(v6, 2);
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
            WPP_pszIndent,
            Certs);
        }
      }
      SubmitThreadpoolWork(*((PTP_WORK *)v5 + 76));
    }
    else
    {
      *((_DWORD *)v5 + 7) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 72));
  }
LABEL_8:
  LeaveCriticalSection(&g_csSessionList);
  return Certs;
}

```

## disassembly

```asm
0x180002df0  push    rbx
0x180002df2  push    rbp
0x180002df3  push    rsi
0x180002df4  push    rdi
0x180002df5  sub     rsp, 38h
0x180002df9  mov     esi, ecx
0x180002dfb  mov     ebp, edx
0x180002dfd  lea     rcx, g_csSessionList; lpCriticalSection
0x180002e04  xor     edi, edi
0x180002e06  call    cs:__imp_EnterCriticalSection
0x180002e0c  mov     rbx, cs:g_pSessionList
0x180002e13  test    rbx, rbx
0x180002e16  jz      short loc_180002E56
0x180002e18  cmp     esi, [rbx+8]
0x180002e1b  jz      short loc_180002E6E
0x180002e1d  mov     rbx, [rbx]
0x180002e20  test    rbx, rbx
0x180002e23  jnz     short loc_180002E18
0x180002e25  jmp     short loc_180002E56
0x180002e27  mov     eax, cs:g_fEnableRootCertProp
0x180002e2d  lea     rcx, [rbx+18h]
0x180002e31  mov     [rbx+1Ch], eax
0x180002e34  call    ReaderMonitorReadCerts
0x180002e39  mov     edi, eax
0x180002e3b  test    eax, eax
0x180002e3d  jnz     short loc_180002E8A
0x180002e3f  mov     rcx, [rbx+260h]; pwk
0x180002e46  call    cs:__imp_SubmitThreadpoolWork
0x180002e4c  lea     rcx, [rbx+48h]; lpCriticalSection
0x180002e50  call    cs:__imp_LeaveCriticalSection
0x180002e56  lea     rcx, g_csSessionList; lpCriticalSection
0x180002e5d  call    cs:__imp_LeaveCriticalSection
0x180002e63  mov     eax, edi
0x180002e65  add     rsp, 38h
0x180002e69  pop     rdi
0x180002e6a  pop     rsi
0x180002e6b  pop     rbp
0x180002e6c  pop     rbx
0x180002e6d  retn
0x180002e6e  lea     rcx, [rbx+48h]; lpCriticalSection
0x180002e72  call    cs:__imp_EnterCriticalSection
0x180002e78  mov     [rbx+20h], ebp
0x180002e7b  mov     [rbx+234h], ebp
0x180002e81  test    ebp, ebp
0x180002e83  jnz     short loc_180002E27
0x180002e85  mov     [rbx+1Ch], edi
0x180002e88  jmp     short loc_180002E4C
0x180002e8a  mov     edx, 2
0x180002e8f  call    WppTraceIndent
0x180002e94  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e9b  lea     rax, WPP_GLOBAL_Control
0x180002ea2  cmp     rcx, rax
0x180002ea5  jz      short loc_180002E3F
0x180002ea7  test    byte ptr [rcx+1Ch], 1
0x180002eab  jz      short loc_180002E3F
0x180002ead  cmp     byte ptr [rcx+19h], 2
0x180002eb1  jb      short loc_180002E3F
0x180002eb3  mov     r9, cs:WPP_pszIndent
0x180002eba  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180002ec1  mov     rcx, [rcx+10h]
0x180002ec5  mov     edx, 33h ; '3'
0x180002eca  mov     [rsp+58h+var_38], edi
0x180002ece  call    WPP_SF_sD
0x180002ed3  jmp     loc_180002E3F
```
