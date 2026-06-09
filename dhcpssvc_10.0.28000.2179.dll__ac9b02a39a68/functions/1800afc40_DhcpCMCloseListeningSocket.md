# DhcpCMCloseListeningSocket

- ea: `0x1800afc40`
- end: `0x1800aff94`
- name: `DhcpCMCloseListeningSocket`
- size: `852`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800af4e4`
- `0x1800b0bb4`

## callees

- `0x18001c45c`
- `0x1800afc40`
- `0x1800b3c9c`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x1800afce4`
- `WS2_32!WSACloseEvent` at `0x1800afd2e`
- `WS2_32!WSACloseEvent` at `0x1800afd85`
- `WS2_32!WSACloseEvent` at `0x1800afce4`
- `WS2_32!WSACloseEvent` at `0x1800afd2e`
- `WS2_32!WSACloseEvent` at `0x1800afd85`
- `WS2_32!__imp_closesocket` at `0x1800afcc7`
- `WS2_32!__imp_closesocket` at `0x1800afcc7`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afcf4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afd3e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afd95`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afcf4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afd3e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afd95`
- `KERNEL32!EnterCriticalSection` at `0x1800afdda`
- `KERNEL32!EnterCriticalSection` at `0x1800afdda`
- `KERNEL32!LeaveCriticalSection` at `0x1800afdff`
- `KERNEL32!LeaveCriticalSection` at `0x1800afdff`
- `KERNEL32!HeapFree` at `0x1800aff68`
- `KERNEL32!HeapFree` at `0x1800aff68`

## string_xrefs

- `0x1800afd06`: `WSACloseEvent`
- `0x1800afd50`: `WSACloseEvent`
- `0x1800afda7`: `WSACloseEvent`

## pseudocode

```c
__int64 __fastcall DhcpCMCloseListeningSocket(__int64 a1, _DWORD *a2, _DWORD *a3, _DWORD *a4, _DWORD *a5, int a6)
{
  unsigned int Error; // edi
  unsigned int *v8; // rbx
  __int64 v9; // rsi
  STRSAFE_LPCWSTR *v12; // r13
  char *v13; // rbp
  void *v15; // rcx
  void *v16; // rcx
  HANDLE v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // xmm1_8
  __int64 v20; // rcx
  __int64 v21; // r9
  __int64 v22; // r8
  unsigned int v23; // edx
  __int64 v24; // r11
  __int64 v25; // r10
  __int64 v26; // rax
  unsigned int v27; // eax

  Error = 0;
  v8 = 0;
  v9 = 0;
  v12 = (STRSAFE_LPCWSTR *)a1;
  if ( !gNumListeningSockets )
    return Error;
  while ( 1 )
  {
    v13 = (char *)&gListeningSockets + 24 * v9;
    if ( *(_DWORD *)v13 == *(_DWORD *)(a1 + 16) )
      break;
    v9 = (unsigned int)(v9 + 1);
    if ( (unsigned int)v9 >= gNumListeningSockets )
      return Error;
  }
  if ( LODWORD(qword_1800FD360[3 * v9])-- == 1 )
  {
    v8 = (unsigned int *)*((_QWORD *)&gListeningSockets + 3 * v9 + 1);
    closesocket(*((_QWORD *)v8 + 1));
    v15 = (void *)*((_QWORD *)v8 + 5);
    *((_QWORD *)v8 + 1) = -1;
    if ( v15 )
    {
      if ( !WSACloseEvent(v15) )
      {
        Error = WSAGetLastError();
        DhcpPrintFOErrorEx(Error, "DhcpCMCloseListeningSocket", "WSACloseEvent", 2275);
      }
      *((_QWORD *)v8 + 5) = 0;
    }
    v16 = (void *)*((_QWORD *)v8 + 6);
    if ( v16 )
    {
      if ( !WSACloseEvent(v16) )
      {
        Error = WSAGetLastError();
        DhcpPrintFOErrorEx(Error, "DhcpCMCloseListeningSocket", "WSACloseEvent", 2278);
      }
      *((_QWORD *)v8 + 6) = 0;
    }
    v17 = gSocketEventArray[*v8];
    if ( v17 )
    {
      if ( !WSACloseEvent(v17) )
      {
        Error = WSAGetLastError();
        DhcpPrintFOErrorEx(Error, "DhcpCMCloseListeningSocket", "WSACloseEvent", 2281);
      }
      gSocketEventArray[*v8] = 0;
    }
    EnterCriticalSection(&gSocketLock);
    **((_DWORD **)v8 + 2) = 0;
    *((_QWORD *)v8 + 2) = 0;
    LeaveCriticalSection(&gSocketLock);
    v18 = (unsigned int)(gNumListeningSockets - 1);
    if ( (unsigned int)v9 < (unsigned int)v18 )
    {
      do
      {
        v9 = (unsigned int)(v9 + 1);
        v19 = qword_1800FD360[3 * v9];
        *(_OWORD *)v13 = *(__int128 *)((char *)&gListeningSockets + 24 * v9);
        *((_QWORD *)v13 + 2) = v19;
        v13 += 24;
      }
      while ( (unsigned int)v9 < (unsigned int)v18 );
      v12 = (STRSAFE_LPCWSTR *)a1;
    }
    gNumListeningSockets = v18;
    *((_QWORD *)&gListeningSockets + 3 * v18 + 1) = 0;
    v20 = 3 * v18;
    LODWORD(qword_1800FD360[v20]) = 0;
    *((_DWORD *)&gListeningSockets + 2 * v20) = 0;
    v21 = *v8;
    if ( a3 )
      *a3 = v21;
    if ( a4 )
      *a4 = v8[1];
    v22 = gSocketEventTotal - 1;
    if ( (_DWORD)v21 != (_DWORD)v22 )
    {
      v23 = v21;
      if ( (unsigned int)v21 < (unsigned int)v22 )
      {
        v24 = (unsigned int)(v21 + 1);
        v25 = v21;
        do
        {
          gSocketEventArray[v25++] = gSocketEventArray[v24];
          *(_DWORD *)gSocketArray[v24] = v23++;
          v26 = gSocketArray[v24];
          v24 = (unsigned int)(v24 + 1);
          *(_QWORD *)((char *)&unk_1801003B8 + v25 * 8) = v26;
        }
        while ( v23 < (unsigned int)v22 );
      }
    }
    gSocketEventTotal = v22;
    gSocketArray[v22] = 0;
    if ( a5 )
    {
      if ( a2 && (_DWORD)v21 == *a2 )
      {
        *a5 = 1;
        goto LABEL_35;
      }
      *a5 = 0;
    }
    if ( a2 )
    {
LABEL_35:
      if ( (unsigned int)v21 < *a2 )
        --*a2;
    }
  }
  if ( a6 == 1 )
  {
    v27 = DhcpCMUpdateListeningRelName(*v12);
    if ( v27 )
      Error = v27;
  }
  if ( v8 )
    HeapFree(gDhcpHeap, 0, v8);
  return Error;
}

```

## disassembly

```asm
0x1800afc40  mov     rax, rsp
0x1800afc43  mov     [rax+10h], rbx
0x1800afc47  mov     [rax+18h], rbp
0x1800afc4b  mov     [rax+20h], rsi
0x1800afc4f  mov     [rax+8], rcx
0x1800afc53  push    rdi
0x1800afc54  push    r12
0x1800afc56  push    r13
0x1800afc58  push    r14
0x1800afc5a  push    r15
0x1800afc5c  sub     rsp, 30h
0x1800afc60  mov     r14, rdx
0x1800afc63  xor     edi, edi
0x1800afc65  mov     edx, cs:gNumListeningSockets
0x1800afc6b  xor     ebx, ebx
0x1800afc6d  xor     esi, esi
0x1800afc6f  mov     r15, r9
0x1800afc72  mov     r12, r8
0x1800afc75  mov     r13, rcx
0x1800afc78  test    edx, edx
0x1800afc7a  jz      loc_1800AFF74
0x1800afc80  mov     r10d, [rcx+10h]
0x1800afc84  lea     r8, __ImageBase
0x1800afc8b  lea     rcx, [rsi+rsi*2]
0x1800afc8f  lea     rbp, rva gListeningSockets[r8]
0x1800afc96  lea     rbp, [rbp+rcx*8+0]
0x1800afc9b  cmp     [rbp+0], r10d
0x1800afc9f  jz      short loc_1800AFCAC
0x1800afca1  inc     esi
0x1800afca3  cmp     esi, edx
0x1800afca5  jb      short loc_1800AFC8B
0x1800afca7  jmp     loc_1800AFF74
0x1800afcac  add     dword ptr rva qword_1800FD360[r8+rcx*8], 0FFFFFFFFh
0x1800afcb5  jnz     loc_1800AFF3D
0x1800afcbb  mov     rbx, qword ptr (rva gListeningSockets+8)[r8+rcx*8]
0x1800afcc3  mov     rcx, [rbx+8]; s
0x1800afcc7  call    cs:__imp_closesocket
0x1800afcce  nop     dword ptr [rax+rax+00h]
0x1800afcd3  mov     rcx, [rbx+28h]; hEvent
0x1800afcd7  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800afcdf  test    rcx, rcx
0x1800afce2  jz      short loc_1800AFD25
0x1800afce4  call    cs:__imp_WSACloseEvent
0x1800afceb  nop     dword ptr [rax+rax+00h]
0x1800afcf0  test    eax, eax
0x1800afcf2  jnz     short loc_1800AFD1D
0x1800afcf4  call    cs:__imp_WSAGetLastError
0x1800afcfb  nop     dword ptr [rax+rax+00h]
0x1800afd00  mov     r9d, 8E3h
0x1800afd06  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800afd0d  mov     ecx, eax
0x1800afd0f  lea     rdx, aDhcpcmcloselis; "DhcpCMCloseListeningSocket"
0x1800afd16  mov     edi, eax
0x1800afd18  call    DhcpPrintFOErrorEx
0x1800afd1d  mov     qword ptr [rbx+28h], 0
0x1800afd25  mov     rcx, [rbx+30h]; hEvent
0x1800afd29  test    rcx, rcx
0x1800afd2c  jz      short loc_1800AFD6F
0x1800afd2e  call    cs:__imp_WSACloseEvent
0x1800afd35  nop     dword ptr [rax+rax+00h]
0x1800afd3a  test    eax, eax
0x1800afd3c  jnz     short loc_1800AFD67
0x1800afd3e  call    cs:__imp_WSAGetLastError
0x1800afd45  nop     dword ptr [rax+rax+00h]
0x1800afd4a  mov     r9d, 8E6h
0x1800afd50  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800afd57  mov     ecx, eax
0x1800afd59  lea     rdx, aDhcpcmcloselis; "DhcpCMCloseListeningSocket"
0x1800afd60  mov     edi, eax
0x1800afd62  call    DhcpPrintFOErrorEx
0x1800afd67  mov     qword ptr [rbx+30h], 0
0x1800afd6f  mov     eax, [rbx]
0x1800afd71  lea     rcx, __ImageBase
0x1800afd78  mov     rcx, rva gSocketEventArray[rcx+rax*8]; hEvent
0x1800afd80  test    rcx, rcx
0x1800afd83  jz      short loc_1800AFDD3
0x1800afd85  call    cs:__imp_WSACloseEvent
0x1800afd8c  nop     dword ptr [rax+rax+00h]
0x1800afd91  test    eax, eax
0x1800afd93  jnz     short loc_1800AFDBE
0x1800afd95  call    cs:__imp_WSAGetLastError
0x1800afd9c  nop     dword ptr [rax+rax+00h]
0x1800afda1  mov     r9d, 8E9h
0x1800afda7  lea     r8, aWsacloseevent; "WSACloseEvent"
0x1800afdae  mov     ecx, eax
0x1800afdb0  lea     rdx, aDhcpcmcloselis; "DhcpCMCloseListeningSocket"
0x1800afdb7  mov     edi, eax
0x1800afdb9  call    DhcpPrintFOErrorEx
0x1800afdbe  mov     eax, [rbx]
0x1800afdc0  lea     rcx, __ImageBase
0x1800afdc7  mov     rva gSocketEventArray[rcx+rax*8], 0
0x1800afdd3  lea     rcx, gSocketLock; lpCriticalSection
0x1800afdda  call    cs:__imp_EnterCriticalSection
0x1800afde1  nop     dword ptr [rax+rax+00h]
0x1800afde6  mov     rax, [rbx+10h]
0x1800afdea  lea     rcx, gSocketLock; lpCriticalSection
0x1800afdf1  mov     dword ptr [rax], 0
0x1800afdf7  mov     qword ptr [rbx+10h], 0
0x1800afdff  call    cs:__imp_LeaveCriticalSection
0x1800afe06  nop     dword ptr [rax+rax+00h]
0x1800afe0b  mov     edx, cs:gNumListeningSockets
0x1800afe11  dec     edx
0x1800afe13  cmp     esi, edx
0x1800afe15  jnb     short loc_1800AFE4D
0x1800afe17  lea     r13, __ImageBase
0x1800afe1e  inc     esi
0x1800afe20  lea     rcx, [rsi+rsi*2]
0x1800afe24  movsd   xmm1, rva qword_1800FD360[r13+rcx*8]
0x1800afe2e  movups  xmm0, rva gListeningSockets[r13+rcx*8]
0x1800afe37  movups  xmmword ptr [rbp+0], xmm0
0x1800afe3b  movsd   qword ptr [rbp+10h], xmm1
0x1800afe40  lea     rbp, [rbp+18h]
0x1800afe44  cmp     esi, edx
0x1800afe46  jb      short loc_1800AFE1E
0x1800afe48  mov     r13, [rsp+58h+arg_0]
0x1800afe4d  mov     cs:gNumListeningSockets, edx
0x1800afe53  lea     rsi, __ImageBase
0x1800afe5a  lea     rcx, [rdx+rdx*2]
0x1800afe5e  mov     qword ptr (rva gListeningSockets+8)[rsi+rcx*8], 0
0x1800afe6a  lea     rcx, [rdx+rdx*2]
0x1800afe6e  mov     dword ptr rva qword_1800FD360[rsi+rcx*8], 0
0x1800afe79  mov     dword ptr rva gListeningSockets[rsi+rcx*8], 0
0x1800afe84  mov     r9d, [rbx]
0x1800afe87  test    r12, r12
0x1800afe8a  jz      short loc_1800AFE90
0x1800afe8c  mov     [r12], r9d
0x1800afe90  test    r15, r15
0x1800afe93  jz      short loc_1800AFE9B
0x1800afe95  mov     eax, [rbx+4]
0x1800afe98  mov     [r15], eax
0x1800afe9b  mov     r8d, cs:gSocketEventTotal
0x1800afea2  dec     r8d
0x1800afea5  cmp     r9d, r8d
0x1800afea8  jz      short loc_1800AFEF3
0x1800afeaa  mov     rdx, r9
0x1800afead  jnb     short loc_1800AFEF3
0x1800afeaf  lea     r11d, [r9+1]
0x1800afeb3  lea     r10, ds:0[r9*8]
0x1800afebb  mov     rax, rva gSocketEventArray[rsi+r11*8]
0x1800afec3  mov     [r10+rsi+100BE0h], rax
0x1800afecb  lea     r10, [r10+8]
0x1800afecf  mov     rax, rva gSocketArray[rsi+r11*8]
0x1800afed7  mov     [rax], edx
0x1800afed9  inc     edx
0x1800afedb  mov     rax, rva gSocketArray[rsi+r11*8]
0x1800afee3  inc     r11d
0x1800afee6  mov     [r10+rsi+1003B8h], rax
0x1800afeee  cmp     edx, r8d
0x1800afef1  jb      short loc_1800AFEBB
0x1800afef3  mov     rax, [rsp+58h+arg_20]
0x1800afefb  mov     cs:gSocketEventTotal, r8d
0x1800aff02  mov     rva gSocketArray[rsi+r8*8], 0
0x1800aff0e  test    rax, rax
0x1800aff11  jz      short loc_1800AFF2B
0x1800aff13  test    r14, r14
0x1800aff16  jz      short loc_1800AFF25
0x1800aff18  cmp     r9d, [r14]
0x1800aff1b  jnz     short loc_1800AFF25
0x1800aff1d  mov     dword ptr [rax], 1
0x1800aff23  jmp     short loc_1800AFF30
0x1800aff25  mov     dword ptr [rax], 0
0x1800aff2b  test    r14, r14
0x1800aff2e  jz      short loc_1800AFF3D
0x1800aff30  mov     eax, [r14]
0x1800aff33  cmp     r9d, eax
0x1800aff36  jnb     short loc_1800AFF3D
0x1800aff38  dec     eax
0x1800aff3a  mov     [r14], eax
0x1800aff3d  cmp     [rsp+58h+arg_28], 1
0x1800aff45  jnz     short loc_1800AFF57
0x1800aff47  mov     rcx, [r13+0]; pszSrc
0x1800aff4b  xor     edx, edx
0x1800aff4d  call    DhcpCMUpdateListeningRelName
0x1800aff52  test    eax, eax
0x1800aff54  cmovnz  edi, eax
0x1800aff57  test    rbx, rbx
0x1800aff5a  jz      short loc_1800AFF74
0x1800aff5c  mov     rcx, cs:gDhcpHeap; hHeap
0x1800aff63  mov     r8, rbx; lpMem
0x1800aff66  xor     edx, edx; dwFlags
0x1800aff68  call    cs:__imp_HeapFree
0x1800aff6f  nop     dword ptr [rax+rax+00h]
0x1800aff74  mov     rbx, [rsp+58h+arg_8]
0x1800aff79  mov     eax, edi
0x1800aff7b  mov     rbp, [rsp+58h+arg_10]
0x1800aff80  mov     rsi, [rsp+58h+arg_18]
0x1800aff85  add     rsp, 30h
0x1800aff89  pop     r15
0x1800aff8b  pop     r14
0x1800aff8d  pop     r13
0x1800aff8f  pop     r12
0x1800aff91  pop     rdi
0x1800aff92  retn
```
