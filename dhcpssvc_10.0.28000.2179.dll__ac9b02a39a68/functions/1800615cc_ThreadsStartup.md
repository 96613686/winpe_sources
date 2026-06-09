# ThreadsStartup

- ea: `0x1800615cc`
- end: `0x180061a98`
- name: `ThreadsStartup`
- size: `1228`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180024e18`

## callees

- `0x18000282c`
- `0x1800615cc`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18006175c`
- `KERNEL32!WaitForSingleObject` at `0x1800617d3`
- `KERNEL32!WaitForSingleObject` at `0x1800618af`
- `KERNEL32!WaitForSingleObject` at `0x180061989`
- `KERNEL32!WaitForSingleObject` at `0x180061a00`
- `KERNEL32!WaitForSingleObject` at `0x18006175c`
- `KERNEL32!WaitForSingleObject` at `0x1800617d3`
- `KERNEL32!WaitForSingleObject` at `0x1800618af`
- `KERNEL32!WaitForSingleObject` at `0x180061989`
- `KERNEL32!WaitForSingleObject` at `0x180061a00`
- `KERNEL32!GetLastError` at `0x1800616fc`
- `KERNEL32!GetLastError` at `0x18006176c`
- `KERNEL32!GetLastError` at `0x1800617e3`
- `KERNEL32!GetLastError` at `0x18006184f`
- `KERNEL32!GetLastError` at `0x1800618bf`
- `KERNEL32!GetLastError` at `0x18006192d`
- `KERNEL32!GetLastError` at `0x180061999`
- `KERNEL32!GetLastError` at `0x180061a10`
- `KERNEL32!GetLastError` at `0x1800616fc`
- `KERNEL32!GetLastError` at `0x18006176c`
- `KERNEL32!GetLastError` at `0x1800617e3`
- `KERNEL32!GetLastError` at `0x18006184f`
- `KERNEL32!GetLastError` at `0x1800618bf`
- `KERNEL32!GetLastError` at `0x18006192d`
- `KERNEL32!GetLastError` at `0x180061999`
- `KERNEL32!GetLastError` at `0x180061a10`
- `KERNEL32!CloseHandle` at `0x1800617ab`
- `KERNEL32!CloseHandle` at `0x180061822`
- `KERNEL32!CloseHandle` at `0x1800618fe`
- `KERNEL32!CloseHandle` at `0x1800619d8`
- `KERNEL32!CloseHandle` at `0x180061a4f`
- `KERNEL32!CloseHandle` at `0x1800617ab`
- `KERNEL32!CloseHandle` at `0x180061822`
- `KERNEL32!CloseHandle` at `0x1800618fe`
- `KERNEL32!CloseHandle` at `0x1800619d8`
- `KERNEL32!CloseHandle` at `0x180061a4f`
- `KERNEL32!CreateThread` at `0x18006162e`
- `KERNEL32!CreateThread` at `0x18006168b`
- `KERNEL32!CreateThread` at `0x1800616e0`
- `KERNEL32!CreateThread` at `0x18006162e`
- `KERNEL32!CreateThread` at `0x18006168b`
- `KERNEL32!CreateThread` at `0x1800616e0`

## pseudocode

```c
__int64 ThreadsStartup()
{
  int v0; // eax
  unsigned int v1; // ebx
  HANDLE v2; // rax
  int v3; // edx
  unsigned int v4; // ebx
  HANDLE v5; // rax
  int v6; // edx
  DWORD v7; // eax
  DWORD v8; // edi
  __int64 k; // r14
  void *v10; // rcx
  DWORD v11; // eax
  void *v12; // rcx
  DWORD v13; // eax
  DWORD LastError; // eax
  unsigned int v15; // eax
  __int64 i; // rsi
  void *v17; // rcx
  DWORD v18; // eax
  DWORD v20; // eax
  __int64 j; // r14
  void *v22; // rcx
  DWORD v23; // eax
  void *v24; // rcx
  DWORD v25; // eax
  DWORD ThreadId; // [rsp+50h] [rbp+8h] BYREF

  ThreadId = 0;
  v0 = dword_1800FCF28;
  if ( (unsigned int)dword_1800FCF28 >= 0x14 )
  {
    v0 = 19;
    dword_1800FCF28 = 19;
  }
  v1 = 0;
  if ( v0 )
  {
    while ( 1 )
    {
      v2 = CreateThread(0, 0, ProcessingLoop, 0, 0, &ThreadId);
      if ( !v2 )
        break;
      v3 = dword_1800FD148;
      ++v1;
      qword_1800FCF30[dword_1800FD148] = (__int64)v2;
      v0 = dword_1800FCF28;
      dword_1800FD148 = v3 + 1;
      if ( v1 >= dword_1800FCF28 )
        goto LABEL_6;
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, LastError);
    v15 = dword_1800FCF28;
    for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
    {
      v17 = (void *)qword_1800FCF30[i];
      if ( v17 )
      {
        if ( WaitForSingleObject(v17, 0xFFFFFFFF) )
        {
          v18 = GetLastError();
          v8 = v18;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v18);
          }
        }
        CloseHandle((HANDLE)qword_1800FCF30[i]);
        v15 = dword_1800FCF28;
        qword_1800FCF30[i] = 0;
      }
    }
    return v8;
  }
LABEL_6:
  v4 = 0;
  if ( v0 )
  {
    while ( 1 )
    {
      v5 = CreateThread(0, 0, QuarPacketLoop, 0, 0, &ThreadId);
      if ( !v5 )
        break;
      v6 = dword_1800FD14C;
      ++v4;
      qword_1800FCFD0[dword_1800FD14C] = (__int64)v5;
      dword_1800FD14C = v6 + 1;
      if ( v4 >= dword_1800FCF28 )
        goto LABEL_9;
    }
    v20 = GetLastError();
    v8 = v20;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v20);
    for ( j = 0; (unsigned int)j < dword_1800FCF28; j = (unsigned int)(j + 1) )
    {
      v22 = (void *)qword_1800FCF30[j];
      if ( v22 )
      {
        if ( WaitForSingleObject(v22, 0xFFFFFFFF) )
        {
          v23 = GetLastError();
          v8 = v23;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v23);
          }
        }
        CloseHandle((HANDLE)qword_1800FCF30[j]);
        qword_1800FCF30[j] = 0;
      }
      v24 = (void *)qword_1800FCFD0[j];
      if ( v24 )
      {
        if ( WaitForSingleObject(v24, 0xFFFFFFFF) )
        {
          v25 = GetLastError();
          v8 = v25;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v25);
          }
        }
        CloseHandle((HANDLE)qword_1800FCFD0[j]);
        qword_1800FCFD0[j] = 0;
      }
    }
    return v8;
  }
LABEL_9:
  hHandle = CreateThread(0, 0, MessageLoop, 0, 0, &ThreadId);
  if ( !hHandle )
  {
    v7 = GetLastError();
    v8 = v7;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v7);
    for ( k = 0; (unsigned int)k < dword_1800FCF28; k = (unsigned int)(k + 1) )
    {
      v10 = (void *)qword_1800FCF30[k];
      if ( v10 )
      {
        if ( WaitForSingleObject(v10, 0xFFFFFFFF) )
        {
          v11 = GetLastError();
          v8 = v11;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v11);
          }
        }
        CloseHandle((HANDLE)qword_1800FCF30[k]);
        qword_1800FCF30[k] = 0;
      }
      v12 = (void *)qword_1800FCFD0[k];
      if ( v12 )
      {
        if ( WaitForSingleObject(v12, 0xFFFFFFFF) )
        {
          v13 = GetLastError();
          v8 = v13;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v13);
          }
        }
        CloseHandle((HANDLE)qword_1800FCFD0[k]);
        qword_1800FCFD0[k] = 0;
      }
    }
    return v8;
  }
  return 0;
}

```

## disassembly

```asm
0x1800615cc  mov     rax, rsp
0x1800615cf  mov     [rax+10h], rbx
0x1800615d3  mov     [rax+18h], rbp
0x1800615d7  mov     [rax+20h], rsi
0x1800615db  push    rdi
0x1800615dc  push    r13
0x1800615de  push    r14
0x1800615e0  sub     rsp, 30h
0x1800615e4  mov     dword ptr [rax+8], 0
0x1800615eb  mov     eax, cs:dword_1800FCF28
0x1800615f1  cmp     eax, 14h
0x1800615f4  jb      short loc_180061601
0x1800615f6  mov     eax, 13h
0x1800615fb  mov     cs:dword_1800FCF28, eax
0x180061601  xor     ebx, ebx
0x180061603  lea     r13, __ImageBase
0x18006160a  test    eax, eax
0x18006160c  jz      short loc_180061665
0x18006160e  lea     rax, [rsp+48h+ThreadId]
0x180061613  xor     r9d, r9d; lpParameter
0x180061616  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x18006161b  lea     r8, ProcessingLoop; lpStartAddress
0x180061622  xor     edx, edx; dwStackSize
0x180061624  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x18006162c  xor     ecx, ecx; lpThreadAttributes
0x18006162e  call    cs:__imp_CreateThread
0x180061635  nop     dword ptr [rax+rax+00h]
0x18006163a  test    rax, rax
0x18006163d  jz      loc_18006184F
0x180061643  mov     edx, cs:dword_1800FD148
0x180061649  inc     ebx
0x18006164b  mov     rva qword_1800FCF30[r13+rdx*8], rax
0x180061653  inc     edx
0x180061655  mov     eax, cs:dword_1800FCF28
0x18006165b  mov     cs:dword_1800FD148, edx
0x180061661  cmp     ebx, eax
0x180061663  jb      short loc_18006160E
0x180061665  xor     ebx, ebx
0x180061667  test    eax, eax
0x180061669  jz      short loc_1800616C0
0x18006166b  lea     rax, [rsp+48h+ThreadId]
0x180061670  xor     r9d, r9d; lpParameter
0x180061673  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180061678  lea     r8, QuarPacketLoop; lpStartAddress
0x18006167f  xor     edx, edx; dwStackSize
0x180061681  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x180061689  xor     ecx, ecx; lpThreadAttributes
0x18006168b  call    cs:__imp_CreateThread
0x180061692  nop     dword ptr [rax+rax+00h]
0x180061697  test    rax, rax
0x18006169a  jz      loc_18006192D
0x1800616a0  mov     edx, cs:dword_1800FD14C
0x1800616a6  inc     ebx
0x1800616a8  mov     rva qword_1800FCFD0[r13+rdx*8], rax
0x1800616b0  inc     edx
0x1800616b2  cmp     ebx, cs:dword_1800FCF28
0x1800616b8  mov     cs:dword_1800FD14C, edx
0x1800616be  jb      short loc_18006166B
0x1800616c0  lea     rax, [rsp+48h+ThreadId]
0x1800616c5  xor     r9d, r9d; lpParameter
0x1800616c8  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800616cd  lea     r8, MessageLoop; lpStartAddress
0x1800616d4  xor     edx, edx; dwStackSize
0x1800616d6  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800616de  xor     ecx, ecx; lpThreadAttributes
0x1800616e0  call    cs:__imp_CreateThread
0x1800616e7  nop     dword ptr [rax+rax+00h]
0x1800616ec  mov     cs:hHandle, rax
0x1800616f3  test    rax, rax
0x1800616f6  jnz     loc_180061A7C
0x1800616fc  call    cs:__imp_GetLastError
0x180061703  nop     dword ptr [rax+rax+00h]
0x180061708  mov     edi, eax
0x18006170a  mov     rcx, cs:WPP_GLOBAL_Control
0x180061711  lea     rbp, WPP_GLOBAL_Control
0x180061718  mov     bl, 10h
0x18006171a  cmp     rcx, rbp
0x18006171d  jz      short loc_18006173C
0x18006171f  test    [rcx+1Ch], bl
0x180061722  jz      short loc_18006173C
0x180061724  mov     rcx, [rcx+10h]
0x180061728  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x18006172f  mov     edx, 3Ch ; '<'
0x180061734  mov     r9d, eax
0x180061737  call    WPP_SF_D
0x18006173c  xor     r14d, r14d
0x18006173f  cmp     cs:dword_1800FCF28, r14d
0x180061746  jbe     loc_180061926
0x18006174c  mov     rcx, rva qword_1800FCF30[r13+r14*8]; hHandle
0x180061754  test    rcx, rcx
0x180061757  jz      short loc_1800617C3
0x180061759  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18006175c  call    cs:__imp_WaitForSingleObject
0x180061763  nop     dword ptr [rax+rax+00h]
0x180061768  test    eax, eax
0x18006176a  jz      short loc_1800617A3
0x18006176c  call    cs:__imp_GetLastError
0x180061773  nop     dword ptr [rax+rax+00h]
0x180061778  mov     edi, eax
0x18006177a  mov     rcx, cs:WPP_GLOBAL_Control
0x180061781  cmp     rcx, rbp
0x180061784  jz      short loc_1800617A3
0x180061786  test    [rcx+1Ch], bl
0x180061789  jz      short loc_1800617A3
0x18006178b  mov     rcx, [rcx+10h]
0x18006178f  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180061796  mov     edx, 3Dh ; '='
0x18006179b  mov     r9d, eax
0x18006179e  call    WPP_SF_D
0x1800617a3  mov     rcx, rva qword_1800FCF30[r13+r14*8]; hObject
0x1800617ab  call    cs:__imp_CloseHandle
0x1800617b2  nop     dword ptr [rax+rax+00h]
0x1800617b7  mov     rva qword_1800FCF30[r13+r14*8], 0
0x1800617c3  mov     rcx, rva qword_1800FCFD0[r13+r14*8]; hHandle
0x1800617cb  test    rcx, rcx
0x1800617ce  jz      short loc_18006183A
0x1800617d0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800617d3  call    cs:__imp_WaitForSingleObject
0x1800617da  nop     dword ptr [rax+rax+00h]
0x1800617df  test    eax, eax
0x1800617e1  jz      short loc_18006181A
0x1800617e3  call    cs:__imp_GetLastError
0x1800617ea  nop     dword ptr [rax+rax+00h]
0x1800617ef  mov     edi, eax
0x1800617f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800617f8  cmp     rcx, rbp
0x1800617fb  jz      short loc_18006181A
0x1800617fd  test    [rcx+1Ch], bl
0x180061800  jz      short loc_18006181A
0x180061802  mov     rcx, [rcx+10h]
0x180061806  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x18006180d  mov     edx, 3Eh ; '>'
0x180061812  mov     r9d, eax
0x180061815  call    WPP_SF_D
0x18006181a  mov     rcx, rva qword_1800FCFD0[r13+r14*8]; hObject
0x180061822  call    cs:__imp_CloseHandle
0x180061829  nop     dword ptr [rax+rax+00h]
0x18006182e  mov     rva qword_1800FCFD0[r13+r14*8], 0
0x18006183a  inc     r14d
0x18006183d  cmp     r14d, cs:dword_1800FCF28
0x180061844  jb      loc_18006174C
0x18006184a  jmp     loc_180061926
0x18006184f  call    cs:__imp_GetLastError
0x180061856  nop     dword ptr [rax+rax+00h]
0x18006185b  mov     edi, eax
0x18006185d  mov     rcx, cs:WPP_GLOBAL_Control
0x180061864  lea     rbp, WPP_GLOBAL_Control
0x18006186b  mov     bl, 10h
0x18006186d  cmp     rcx, rbp
0x180061870  jz      short loc_18006188F
0x180061872  test    [rcx+1Ch], bl
0x180061875  jz      short loc_18006188F
0x180061877  mov     rcx, [rcx+10h]
0x18006187b  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180061882  mov     edx, 37h ; '7'
0x180061887  mov     r9d, eax
0x18006188a  call    WPP_SF_D
0x18006188f  mov     eax, cs:dword_1800FCF28
0x180061895  xor     esi, esi
0x180061897  test    eax, eax
0x180061899  jz      loc_180061926
0x18006189f  mov     rcx, rva qword_1800FCF30[r13+rsi*8]; hHandle
0x1800618a7  test    rcx, rcx
0x1800618aa  jz      short loc_18006191C
0x1800618ac  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800618af  call    cs:__imp_WaitForSingleObject
0x1800618b6  nop     dword ptr [rax+rax+00h]
0x1800618bb  test    eax, eax
0x1800618bd  jz      short loc_1800618F6
0x1800618bf  call    cs:__imp_GetLastError
0x1800618c6  nop     dword ptr [rax+rax+00h]
0x1800618cb  mov     edi, eax
0x1800618cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800618d4  cmp     rcx, rbp
0x1800618d7  jz      short loc_1800618F6
0x1800618d9  test    [rcx+1Ch], bl
0x1800618dc  jz      short loc_1800618F6
0x1800618de  mov     rcx, [rcx+10h]
0x1800618e2  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x1800618e9  mov     edx, 38h ; '8'
0x1800618ee  mov     r9d, eax
0x1800618f1  call    WPP_SF_D
0x1800618f6  mov     rcx, rva qword_1800FCF30[r13+rsi*8]; hObject
0x1800618fe  call    cs:__imp_CloseHandle
0x180061905  nop     dword ptr [rax+rax+00h]
0x18006190a  mov     eax, cs:dword_1800FCF28
0x180061910  mov     rva qword_1800FCF30[r13+rsi*8], 0
0x18006191c  inc     esi
0x18006191e  cmp     esi, eax
0x180061920  jb      loc_18006189F
0x180061926  mov     eax, edi
0x180061928  jmp     loc_180061A7E
0x18006192d  call    cs:__imp_GetLastError
0x180061934  nop     dword ptr [rax+rax+00h]
0x180061939  mov     edi, eax
0x18006193b  mov     rcx, cs:WPP_GLOBAL_Control
0x180061942  lea     rbp, WPP_GLOBAL_Control
0x180061949  mov     bl, 10h
0x18006194b  cmp     rcx, rbp
0x18006194e  jz      short loc_18006196D
0x180061950  test    [rcx+1Ch], bl
0x180061953  jz      short loc_18006196D
0x180061955  mov     rcx, [rcx+10h]
0x180061959  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180061960  mov     edx, 39h ; '9'
0x180061965  mov     r9d, eax
0x180061968  call    WPP_SF_D
0x18006196d  xor     r14d, r14d
0x180061970  cmp     cs:dword_1800FCF28, r14d
0x180061977  jbe     short loc_180061926
0x180061979  mov     rcx, rva qword_1800FCF30[r13+r14*8]; hHandle
0x180061981  test    rcx, rcx
0x180061984  jz      short loc_1800619F0
0x180061986  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180061989  call    cs:__imp_WaitForSingleObject
0x180061990  nop     dword ptr [rax+rax+00h]
0x180061995  test    eax, eax
0x180061997  jz      short loc_1800619D0
0x180061999  call    cs:__imp_GetLastError
0x1800619a0  nop     dword ptr [rax+rax+00h]
0x1800619a5  mov     edi, eax
0x1800619a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800619ae  cmp     rcx, rbp
0x1800619b1  jz      short loc_1800619D0
0x1800619b3  test    [rcx+1Ch], bl
0x1800619b6  jz      short loc_1800619D0
0x1800619b8  mov     rcx, [rcx+10h]
0x1800619bc  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x1800619c3  mov     edx, 3Ah ; ':'
0x1800619c8  mov     r9d, eax
0x1800619cb  call    WPP_SF_D
0x1800619d0  mov     rcx, rva qword_1800FCF30[r13+r14*8]; hObject
0x1800619d8  call    cs:__imp_CloseHandle
0x1800619df  nop     dword ptr [rax+rax+00h]
0x1800619e4  mov     rva qword_1800FCF30[r13+r14*8], 0
0x1800619f0  mov     rcx, rva qword_1800FCFD0[r13+r14*8]; hHandle
0x1800619f8  test    rcx, rcx
0x1800619fb  jz      short loc_180061A67
0x1800619fd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180061a00  call    cs:__imp_WaitForSingleObject
0x180061a07  nop     dword ptr [rax+rax+00h]
0x180061a0c  test    eax, eax
0x180061a0e  jz      short loc_180061A47
0x180061a10  call    cs:__imp_GetLastError
0x180061a17  nop     dword ptr [rax+rax+00h]
0x180061a1c  mov     edi, eax
0x180061a1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180061a25  cmp     rcx, rbp
0x180061a28  jz      short loc_180061A47
0x180061a2a  test    [rcx+1Ch], bl
0x180061a2d  jz      short loc_180061A47
0x180061a2f  mov     rcx, [rcx+10h]
0x180061a33  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180061a3a  mov     edx, 3Bh ; ';'
0x180061a3f  mov     r9d, eax
0x180061a42  call    WPP_SF_D
0x180061a47  mov     rcx, rva qword_1800FCFD0[r13+r14*8]; hObject
0x180061a4f  call    cs:__imp_CloseHandle
0x180061a56  nop     dword ptr [rax+rax+00h]
0x180061a5b  mov     rva qword_1800FCFD0[r13+r14*8], 0
0x180061a67  inc     r14d
0x180061a6a  cmp     r14d, cs:dword_1800FCF28
0x180061a71  jb      loc_180061979
0x180061a77  jmp     loc_180061926
0x180061a7c  xor     eax, eax
0x180061a7e  mov     rbx, [rsp+48h+arg_8]
0x180061a83  mov     rbp, [rsp+48h+arg_10]
0x180061a88  mov     rsi, [rsp+48h+arg_18]
0x180061a8d  add     rsp, 30h
0x180061a91  pop     r14
0x180061a93  pop     r13
0x180061a95  pop     rdi
0x180061a96  retn
```
