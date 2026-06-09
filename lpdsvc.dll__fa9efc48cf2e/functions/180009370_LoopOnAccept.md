# LoopOnAccept

- ea: `0x180009370`
- end: `0x1800097f8`
- name: `LoopOnAccept`
- size: `1160`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001ce0`
- `0x180002616`
- `0x180002e7c`
- `0x180002ea4`
- `0x180003d4c`
- `0x180009370`
- `0x18000a038`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180009611`
- `KERNEL32!CreateThread` at `0x180009611`
- `KERNEL32!ReleaseSemaphore` at `0x1800095d0`
- `KERNEL32!ReleaseSemaphore` at `0x1800095d0`
- `KERNEL32!LocalAlloc` at `0x1800094f8`
- `KERNEL32!LocalAlloc` at `0x1800094f8`
- `KERNEL32!EnterCriticalSection` at `0x18000954d`
- `KERNEL32!EnterCriticalSection` at `0x1800096ad`
- `KERNEL32!EnterCriticalSection` at `0x180009736`
- `KERNEL32!EnterCriticalSection` at `0x18000954d`
- `KERNEL32!EnterCriticalSection` at `0x1800096ad`
- `KERNEL32!EnterCriticalSection` at `0x180009736`
- `KERNEL32!GetLastError` at `0x18000971d`
- `KERNEL32!GetLastError` at `0x18000971d`
- `KERNEL32!CloseHandle` at `0x1800097b1`
- `KERNEL32!CloseHandle` at `0x1800097b1`
- `KERNEL32!LeaveCriticalSection` at `0x1800095e7`
- `KERNEL32!LeaveCriticalSection` at `0x180009700`
- `KERNEL32!LeaveCriticalSection` at `0x18000977b`
- `KERNEL32!LeaveCriticalSection` at `0x1800095e7`
- `KERNEL32!LeaveCriticalSection` at `0x180009700`
- `KERNEL32!LeaveCriticalSection` at `0x18000977b`
- `KERNEL32!LocalFree` at `0x180009789`
- `KERNEL32!LocalFree` at `0x180009789`
- `WS2_32!__imp_accept` at `0x180009448`
- `WS2_32!__imp_accept` at `0x180009448`
- `WS2_32!__imp_WSAGetLastError` at `0x180009457`
- `WS2_32!__imp_WSAGetLastError` at `0x180009457`

## pseudocode

```c
__int64 __fastcall LoopOnAccept(PVOID Parameter)
{
  int v1; // ebx
  char v2; // r12
  int v3; // r14d
  _QWORD *v4; // rcx
  SOCKET *v5; // r15
  SOCKET v6; // rcx
  SOCKET v7; // rbp
  unsigned int Error; // eax
  unsigned int v9; // ebx
  int v10; // ebx
  HLOCAL v11; // rax
  __int64 v12; // rdi
  HANDLE Thread; // rsi
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  __int64 *v17; // rbx
  __int64 *v18; // rcx
  __int64 v19; // rax
  int addrlen; // [rsp+30h] [rbp-C8h] BYREF
  DWORD ThreadId[3]; // [rsp+34h] [rbp-C4h] BYREF
  struct sockaddr addr; // [rsp+40h] [rbp-B8h] BYREF

  v1 = (int)Parameter;
  memset_0(&addr, 0, 0x80u);
  v2 = 0;
  addrlen = 0;
  v3 = 0;
  ThreadId[0] = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = (SOCKET *)&qword_180013110[4 * v1];
  addrlen = 128;
LABEL_5:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
    WPP_SF_(v4[2], 25, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
  while ( 1 )
  {
    v6 = *v5;
    addrlen = 128;
    v7 = accept(v6, &addr, &addrlen);
    if ( v7 != -1 )
    {
      v10 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
      v11 = LocalAlloc(0, 0x110u);
      v12 = (__int64)v11;
      if ( v11 )
      {
        memset_0(v11, 0, 0x110u);
        *(_QWORD *)(v12 + 8) = v7;
        *(_QWORD *)(v12 + 56) = v12 + 48;
        *(_QWORD *)(v12 + 48) = v12 + 48;
        *(_QWORD *)(v12 + 72) = v12 + 64;
        *(_QWORD *)(v12 + 64) = v12 + 64;
        *(_DWORD *)(v12 + 24) = 1;
        *(_DWORD *)(v12 + 16) = 0;
        *(_QWORD *)(v12 + 96) = -1;
        EnterCriticalSection(&csConnSemGLB);
        ++DWORD1(Common);
        if ( SHIDWORD(qword_180013710) >= (int)Common && (int)Common < dwMaxUsersGLB )
          v10 = 1;
        if ( SHIDWORD(qword_180013710) >= MaxQueueLength )
        {
          v10 = 0;
          v3 = 1;
          v2 = 0;
        }
        else
        {
          v3 = 0;
          *(_QWORD *)v12 = scConnHeadGLB;
          v2 = 1;
          ++HIDWORD(qword_180013710);
          scConnHeadGLB = v12;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
          ReleaseSemaphore(hWorkThreadSemaphore, 1, 0);
        }
        LeaveCriticalSection(&csConnSemGLB);
        if ( !v10 )
        {
          Thread = 0;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids,
              (unsigned int)dwMaxUsersGLB);
          goto LABEL_41;
        }
        Thread = CreateThread(0, 0, WorkerThread, 0, 0, ThreadId);
        if ( Thread
          || (v14 = WPP_GLOBAL_Control, WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control)
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        {
LABEL_41:
          EnterCriticalSection(&csConnSemGLB);
          if ( v10 && Thread )
          {
            v16 = Common + 1;
            LODWORD(Common) = Common + 1;
          }
          else
          {
            v16 = Common;
          }
          if ( SDWORD2(Common) < v16 )
            DWORD2(Common) = v16;
          if ( !v12 || v10 && !Thread || v3 )
            ++HIDWORD(Common);
          LeaveCriticalSection(&csConnSemGLB);
          if ( !v12 || v10 && !Thread || v3 )
          {
            GetLastError();
            if ( v2 )
            {
              v17 = 0;
              EnterCriticalSection(&csConnSemGLB);
              if ( v12 )
              {
                if ( !(_DWORD)Common )
                {
                  v17 = (__int64 *)scConnHeadGLB;
                  v18 = &scConnHeadGLB;
                  if ( scConnHeadGLB )
                  {
                    while ( 1 )
                    {
                      v19 = *v17;
                      if ( v17 == (__int64 *)v12 )
                        break;
                      v18 = v17;
                      v17 = (__int64 *)*v17;
                      if ( !v19 )
                        goto LABEL_65;
                    }
                    *v18 = v19;
                  }
                }
              }
LABEL_65:
              LeaveCriticalSection(&csConnSemGLB);
            }
            else
            {
              v17 = (__int64 *)v12;
            }
            if ( v17 )
            {
              LocalFree(v17);
              SureCloseSocket(v7);
            }
            LpdReportEvent(0xC0000FA4);
          }
          if ( Thread )
            CloseHandle(Thread);
          v4 = WPP_GLOBAL_Control;
          goto LABEL_5;
        }
        v15 = 30;
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        Thread = 0;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_41;
        v15 = 32;
      }
      WPP_SF_(v14[2], v15, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
      goto LABEL_41;
    }
    Error = WSAGetLastError();
    v9 = Error;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids, Error);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v9 == 10004 )
      return 0;
    if ( v4 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v4 + 28) & 2) != 0 )
      {
        WPP_SF_(v4[2], 27, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
        v4 = WPP_GLOBAL_Control;
      }
      goto LABEL_5;
    }
  }
}

```

## disassembly

```asm
0x180009370  mov     [rsp+arg_8], rbx
0x180009375  mov     [rsp+arg_10], rbp
0x18000937a  push    rsi
0x18000937b  push    rdi
0x18000937c  push    r12
0x18000937e  push    r14
0x180009380  push    r15
0x180009382  sub     rsp, 0D0h
0x180009389  mov     rax, cs:__security_cookie
0x180009390  xor     rax, rsp
0x180009393  mov     [rsp+0F8h+var_38], rax
0x18000939b  mov     rbx, rcx
0x18000939e  xor     edx, edx; Val
0x1800093a0  lea     rcx, [rsp+0F8h+addr]; void *
0x1800093a5  mov     r8d, 80h; Size
0x1800093ab  call    memset_0
0x1800093b0  xor     r12b, r12b
0x1800093b3  mov     [rsp+0F8h+addrlen], 0
0x1800093bb  xor     r14d, r14d
0x1800093be  mov     [rsp+0F8h+ThreadId], 0
0x1800093c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093cd  lea     rsi, WPP_GLOBAL_Control
0x1800093d4  cmp     rcx, rsi
0x1800093d7  jz      short loc_1800093FA
0x1800093d9  test    byte ptr [rcx+1Ch], 1
0x1800093dd  jz      short loc_1800093FA
0x1800093df  mov     rcx, [rcx+10h]
0x1800093e3  lea     edx, [r14+18h]
0x1800093e7  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x1800093ee  call    WPP_SF_
0x1800093f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093fa  movsxd  r15, ebx
0x1800093fd  lea     rax, qword_180013110
0x180009404  shl     r15, 5
0x180009408  add     r15, rax
0x18000940b  mov     [rsp+0F8h+addrlen], 80h
0x180009413  cmp     rcx, rsi
0x180009416  jz      short loc_180009433
0x180009418  test    byte ptr [rcx+1Ch], 2
0x18000941c  jz      short loc_180009433
0x18000941e  mov     rcx, [rcx+10h]
0x180009422  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x180009429  mov     edx, 19h
0x18000942e  call    WPP_SF_
0x180009433  mov     rcx, [r15]; s
0x180009436  lea     r8, [rsp+0F8h+addrlen]; addrlen
0x18000943b  lea     rdx, [rsp+0F8h+addr]; addr
0x180009440  mov     [rsp+0F8h+addrlen], 80h
0x180009448  call    cs:__imp_accept
0x18000944e  mov     rbp, rax
0x180009451  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009455  jnz     short loc_1800094CA
0x180009457  call    cs:__imp_WSAGetLastError
0x18000945d  mov     ebx, eax
0x18000945f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009466  cmp     rcx, rsi
0x180009469  jz      short loc_18000948E
0x18000946b  test    byte ptr [rcx+1Ch], 8
0x18000946f  jz      short loc_18000948E
0x180009471  mov     rcx, [rcx+10h]
0x180009475  lea     edx, [rbp+1Bh]
0x180009478  mov     r9d, eax
0x18000947b  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x180009482  call    WPP_SF_d
0x180009487  mov     rcx, cs:WPP_GLOBAL_Control
0x18000948e  cmp     ebx, 2714h
0x180009494  jz      loc_1800097CA
0x18000949a  cmp     rcx, rsi
0x18000949d  jz      short loc_180009433
0x18000949f  test    byte ptr [rcx+1Ch], 2
0x1800094a3  jz      loc_180009413
0x1800094a9  mov     rcx, [rcx+10h]
0x1800094ad  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x1800094b4  mov     edx, 1Bh
0x1800094b9  call    WPP_SF_
0x1800094be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094c5  jmp     loc_180009413
0x1800094ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094d1  xor     ebx, ebx
0x1800094d3  cmp     rcx, rsi
0x1800094d6  jz      short loc_1800094F1
0x1800094d8  test    byte ptr [rcx+1Ch], 2
0x1800094dc  jz      short loc_1800094F1
0x1800094de  mov     rcx, [rcx+10h]
0x1800094e2  lea     edx, [rbx+1Ch]
0x1800094e5  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x1800094ec  call    WPP_SF_
0x1800094f1  mov     edx, 110h; uBytes
0x1800094f6  xor     ecx, ecx; uFlags
0x1800094f8  call    cs:__imp_LocalAlloc
0x1800094fe  mov     rdi, rax
0x180009501  test    rax, rax
0x180009504  jz      loc_180009678
0x18000950a  xor     edx, edx; Val
0x18000950c  mov     r8d, 110h; Size
0x180009512  mov     rcx, rax; void *
0x180009515  call    memset_0
0x18000951a  lea     rcx, [rdi+30h]
0x18000951e  mov     [rdi+8], rbp
0x180009522  mov     [rdi+38h], rcx
0x180009526  mov     [rcx], rcx
0x180009529  lea     rcx, [rdi+40h]
0x18000952d  mov     [rdi+48h], rcx
0x180009531  mov     [rcx], rcx
0x180009534  lea     rcx, csConnSemGLB; lpCriticalSection
0x18000953b  mov     dword ptr [rdi+18h], 1
0x180009542  mov     [rdi+10h], ebx
0x180009545  mov     qword ptr [rdi+60h], 0FFFFFFFFFFFFFFFFh
0x18000954d  call    cs:__imp_EnterCriticalSection
0x180009553  mov     eax, dword ptr cs:qword_180013710+4
0x180009559  mov     edx, 1
0x18000955e  add     dword ptr cs:Common+4, edx
0x180009564  mov     ecx, dword ptr cs:Common
0x18000956a  cmp     eax, ecx
0x18000956c  jl      short loc_180009577
0x18000956e  cmp     ecx, cs:dwMaxUsersGLB
0x180009574  cmovl   ebx, edx
0x180009577  cmp     eax, cs:MaxQueueLength
0x18000957d  jge     short loc_1800095D8
0x18000957f  mov     rax, cs:scConnHeadGLB
0x180009586  xor     r14d, r14d
0x180009589  mov     [rdi], rax
0x18000958c  mov     r12b, dl
0x18000958f  add     dword ptr cs:qword_180013710+4, edx
0x180009595  mov     cs:scConnHeadGLB, rdi
0x18000959c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095a3  cmp     rcx, rsi
0x1800095a6  jz      short loc_1800095C6
0x1800095a8  test    byte ptr [rcx+1Ch], 2
0x1800095ac  jz      short loc_1800095C6
0x1800095ae  mov     rcx, [rcx+10h]
0x1800095b2  lea     edx, [r14+1Dh]
0x1800095b6  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x1800095bd  call    WPP_SF_
0x1800095c2  lea     edx, [r14+1]; lReleaseCount
0x1800095c6  mov     rcx, cs:hWorkThreadSemaphore; hSemaphore
0x1800095cd  xor     r8d, r8d; lpPreviousCount
0x1800095d0  call    cs:__imp_ReleaseSemaphore
0x1800095d6  jmp     short loc_1800095E0
0x1800095d8  xor     ebx, ebx
0x1800095da  mov     r14d, edx
0x1800095dd  xor     r12b, r12b
0x1800095e0  lea     rcx, csConnSemGLB; lpCriticalSection
0x1800095e7  call    cs:__imp_LeaveCriticalSection
0x1800095ed  test    ebx, ebx
0x1800095ef  jz      short loc_180009641
0x1800095f1  lea     rax, [rsp+0F8h+ThreadId]
0x1800095f6  xor     r9d, r9d; lpParameter
0x1800095f9  mov     [rsp+0F8h+lpThreadId], rax; lpThreadId
0x1800095fe  lea     r8, WorkerThread; lpStartAddress
0x180009605  xor     edx, edx; dwStackSize
0x180009607  mov     [rsp+0F8h+dwCreationFlags], 0; dwCreationFlags
0x18000960f  xor     ecx, ecx; lpThreadAttributes
0x180009611  call    cs:__imp_CreateThread
0x180009617  mov     rsi, rax
0x18000961a  test    rax, rax
0x18000961d  jnz     loc_1800096A6
0x180009623  mov     rcx, cs:WPP_GLOBAL_Control
0x18000962a  lea     rax, WPP_GLOBAL_Control
0x180009631  cmp     rcx, rax
0x180009634  jz      short loc_1800096A6
0x180009636  test    byte ptr [rcx+1Ch], 8
0x18000963a  jz      short loc_1800096A6
0x18000963c  lea     edx, [rsi+1Eh]
0x18000963f  jmp     short loc_180009696
0x180009641  xor     esi, esi
0x180009643  mov     rcx, cs:WPP_GLOBAL_Control
0x18000964a  lea     rax, WPP_GLOBAL_Control
0x180009651  cmp     rcx, rax
0x180009654  jz      short loc_1800096A6
0x180009656  test    byte ptr [rcx+1Ch], 2
0x18000965a  jz      short loc_1800096A6
0x18000965c  mov     r9d, cs:dwMaxUsersGLB
0x180009663  lea     edx, [rsi+1Fh]
0x180009666  mov     rcx, [rcx+10h]
0x18000966a  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x180009671  call    WPP_SF_d
0x180009676  jmp     short loc_1800096A6
0x180009678  mov     rcx, cs:WPP_GLOBAL_Control
0x18000967f  lea     rax, WPP_GLOBAL_Control
0x180009686  xor     esi, esi
0x180009688  cmp     rcx, rax
0x18000968b  jz      short loc_1800096A6
0x18000968d  test    byte ptr [rcx+1Ch], 8
0x180009691  jz      short loc_1800096A6
0x180009693  lea     edx, [rsi+20h]
0x180009696  mov     rcx, [rcx+10h]
0x18000969a  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x1800096a1  call    WPP_SF_
0x1800096a6  lea     rcx, csConnSemGLB; lpCriticalSection
0x1800096ad  call    cs:__imp_EnterCriticalSection
0x1800096b3  test    ebx, ebx
0x1800096b5  jz      short loc_1800096CC
0x1800096b7  test    rsi, rsi
0x1800096ba  jz      short loc_1800096CC
0x1800096bc  mov     eax, dword ptr cs:Common
0x1800096c2  inc     eax
0x1800096c4  mov     dword ptr cs:Common, eax
0x1800096ca  jmp     short loc_1800096D2
0x1800096cc  mov     eax, dword ptr cs:Common
0x1800096d2  cmp     dword ptr cs:Common+8, eax
0x1800096d8  jge     short loc_1800096E0
0x1800096da  mov     dword ptr cs:Common+8, eax
0x1800096e0  test    rdi, rdi
0x1800096e3  jz      short loc_1800096F3
0x1800096e5  test    ebx, ebx
0x1800096e7  jz      short loc_1800096EE
0x1800096e9  test    rsi, rsi
0x1800096ec  jz      short loc_1800096F3
0x1800096ee  test    r14d, r14d
0x1800096f1  jz      short loc_1800096F9
0x1800096f3  inc     dword ptr cs:Common+0Ch
0x1800096f9  lea     rcx, csConnSemGLB; lpCriticalSection
0x180009700  call    cs:__imp_LeaveCriticalSection
0x180009706  test    rdi, rdi
0x180009709  jz      short loc_18000971D
0x18000970b  test    ebx, ebx
0x18000970d  jz      short loc_180009714
0x18000970f  test    rsi, rsi
0x180009712  jz      short loc_18000971D
0x180009714  test    r14d, r14d
0x180009717  jz      loc_1800097A9
0x18000971d  call    cs:__imp_GetLastError
0x180009723  test    r12b, r12b
0x180009726  jnz     short loc_18000972D
0x180009728  mov     rbx, rdi
0x18000972b  jmp     short loc_180009781
0x18000972d  lea     rcx, csConnSemGLB; lpCriticalSection
0x180009734  xor     ebx, ebx
0x180009736  call    cs:__imp_EnterCriticalSection
0x18000973c  test    rdi, rdi
0x18000973f  jz      short loc_180009774
0x180009741  cmp     dword ptr cs:Common, ebx
0x180009747  jnz     short loc_180009774
0x180009749  mov     rbx, cs:scConnHeadGLB
0x180009750  lea     rcx, scConnHeadGLB
0x180009757  test    rbx, rbx
0x18000975a  jz      short loc_180009774
0x18000975c  mov     rax, [rbx]
0x18000975f  cmp     rbx, rdi
0x180009762  jz      short loc_180009771
0x180009764  mov     rcx, rbx
0x180009767  mov     rbx, rax
0x18000976a  test    rax, rax
0x18000976d  jnz     short loc_18000975C
0x18000976f  jmp     short loc_180009774
0x180009771  mov     [rcx], rax
0x180009774  lea     rcx, csConnSemGLB; lpCriticalSection
0x18000977b  call    cs:__imp_LeaveCriticalSection
0x180009781  test    rbx, rbx
0x180009784  jz      short loc_180009797
0x180009786  mov     rcx, rbx; hMem
0x180009789  call    cs:__imp_LocalFree
0x18000978f  mov     rcx, rbp; s
0x180009792  call    SureCloseSocket
0x180009797  xor     edx, edx
0x180009799  xor     r9d, r9d
0x18000979c  xor     r8d, r8d
0x18000979f  mov     ecx, 0C0000FA4h; dwEventID
0x1800097a4  call    LpdReportEvent
0x1800097a9  test    rsi, rsi
0x1800097ac  jz      short loc_1800097B7
0x1800097ae  mov     rcx, rsi; hObject
0x1800097b1  call    cs:__imp_CloseHandle
0x1800097b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097be  lea     rsi, WPP_GLOBAL_Control
0x1800097c5  jmp     loc_180009413
0x1800097ca  xor     eax, eax
0x1800097cc  mov     rcx, [rsp+0F8h+var_38]
0x1800097d4  xor     rcx, rsp; StackCookie
0x1800097d7  call    __security_check_cookie
0x1800097dc  lea     r11, [rsp+0F8h+var_28]
0x1800097e4  mov     rbx, [r11+38h]
0x1800097e8  mov     rbp, [r11+40h]
0x1800097ec  mov     rsp, r11
0x1800097ef  pop     r15
0x1800097f1  pop     r14
0x1800097f3  pop     r12
0x1800097f5  pop     rdi
0x1800097f6  pop     rsi
0x1800097f7  retn
```
