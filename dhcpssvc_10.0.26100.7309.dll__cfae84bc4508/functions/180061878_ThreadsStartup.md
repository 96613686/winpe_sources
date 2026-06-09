# ThreadsStartup

- ea: `0x180061878`
- end: `0x180061d25`
- name: `ThreadsStartup`
- size: `1197`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800258dc`

## callees

- `0x180002854`
- `0x180061878`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800619fc`
- `KERNEL32!WaitForSingleObject` at `0x180061a70`
- `KERNEL32!WaitForSingleObject` at `0x180061b49`
- `KERNEL32!WaitForSingleObject` at `0x180061c1c`
- `KERNEL32!WaitForSingleObject` at `0x180061c90`
- `KERNEL32!WaitForSingleObject` at `0x1800619fc`
- `KERNEL32!WaitForSingleObject` at `0x180061a70`
- `KERNEL32!WaitForSingleObject` at `0x180061b49`
- `KERNEL32!WaitForSingleObject` at `0x180061c1c`
- `KERNEL32!WaitForSingleObject` at `0x180061c90`
- `KERNEL32!CreateThread` at `0x1800618d4`
- `KERNEL32!CreateThread` at `0x18006192e`
- `KERNEL32!CreateThread` at `0x180061980`
- `KERNEL32!CreateThread` at `0x1800618d4`
- `KERNEL32!CreateThread` at `0x18006192e`
- `KERNEL32!CreateThread` at `0x180061980`
- `KERNEL32!GetLastError` at `0x18006199c`
- `KERNEL32!GetLastError` at `0x180061a0c`
- `KERNEL32!GetLastError` at `0x180061a80`
- `KERNEL32!GetLastError` at `0x180061ae9`
- `KERNEL32!GetLastError` at `0x180061b59`
- `KERNEL32!GetLastError` at `0x180061bc0`
- `KERNEL32!GetLastError` at `0x180061c2c`
- `KERNEL32!GetLastError` at `0x180061ca0`
- `KERNEL32!GetLastError` at `0x18006199c`
- `KERNEL32!GetLastError` at `0x180061a0c`
- `KERNEL32!GetLastError` at `0x180061a80`
- `KERNEL32!GetLastError` at `0x180061ae9`
- `KERNEL32!GetLastError` at `0x180061b59`
- `KERNEL32!GetLastError` at `0x180061bc0`
- `KERNEL32!GetLastError` at `0x180061c2c`
- `KERNEL32!GetLastError` at `0x180061ca0`
- `KERNEL32!CloseHandle` at `0x180061a4b`
- `KERNEL32!CloseHandle` at `0x180061abf`
- `KERNEL32!CloseHandle` at `0x180061b98`
- `KERNEL32!CloseHandle` at `0x180061c6b`
- `KERNEL32!CloseHandle` at `0x180061cdf`
- `KERNEL32!CloseHandle` at `0x180061a4b`
- `KERNEL32!CloseHandle` at `0x180061abf`
- `KERNEL32!CloseHandle` at `0x180061b98`
- `KERNEL32!CloseHandle` at `0x180061c6b`
- `KERNEL32!CloseHandle` at `0x180061cdf`

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
  v0 = dword_1800FAF38;
  if ( (unsigned int)dword_1800FAF38 >= 0x14 )
  {
    v0 = 19;
    dword_1800FAF38 = 19;
  }
  v1 = 0;
  if ( v0 )
  {
    while ( 1 )
    {
      v2 = CreateThread(0, 0, ProcessingLoop, 0, 0, &ThreadId);
      if ( !v2 )
        break;
      v3 = dword_1800FB17C;
      ++v1;
      qword_1800FAF40[dword_1800FB17C] = (__int64)v2;
      v0 = dword_1800FAF38;
      dword_1800FB17C = v3 + 1;
      if ( v1 >= dword_1800FAF38 )
        goto LABEL_6;
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, LastError);
    v15 = dword_1800FAF38;
    for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
    {
      v17 = (void *)qword_1800FAF40[i];
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
        CloseHandle((HANDLE)qword_1800FAF40[i]);
        qword_1800FAF40[i] = 0;
        v15 = dword_1800FAF38;
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
      v6 = dword_1800FB178;
      ++v4;
      qword_1800FAFE0[dword_1800FB178] = (__int64)v5;
      dword_1800FB178 = v6 + 1;
      if ( v4 >= dword_1800FAF38 )
        goto LABEL_9;
    }
    v20 = GetLastError();
    v8 = v20;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, v20);
    for ( j = 0; (unsigned int)j < dword_1800FAF38; j = (unsigned int)(j + 1) )
    {
      v22 = (void *)qword_1800FAF40[j];
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
        CloseHandle((HANDLE)qword_1800FAF40[j]);
        qword_1800FAF40[j] = 0;
      }
      v24 = (void *)qword_1800FAFE0[j];
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
        CloseHandle((HANDLE)qword_1800FAFE0[j]);
        qword_1800FAFE0[j] = 0;
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
    for ( k = 0; (unsigned int)k < dword_1800FAF38; k = (unsigned int)(k + 1) )
    {
      v10 = (void *)qword_1800FAF40[k];
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
        CloseHandle((HANDLE)qword_1800FAF40[k]);
        qword_1800FAF40[k] = 0;
      }
      v12 = (void *)qword_1800FAFE0[k];
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
        CloseHandle((HANDLE)qword_1800FAFE0[k]);
        qword_1800FAFE0[k] = 0;
      }
    }
    return v8;
  }
  return 0;
}

```

## disassembly

```asm
0x180061878  mov     rax, rsp
0x18006187b  mov     [rax+10h], rbx
0x18006187f  mov     [rax+18h], rbp
0x180061883  mov     [rax+20h], rsi
0x180061887  push    rdi
0x180061888  push    r13
0x18006188a  push    r14
0x18006188c  sub     rsp, 30h
0x180061890  and     dword ptr [rax+8], 0
0x180061894  mov     eax, cs:dword_1800FAF38
0x18006189a  cmp     eax, 14h
0x18006189d  jb      short loc_1800618AA
0x18006189f  mov     eax, 13h
0x1800618a4  mov     cs:dword_1800FAF38, eax
0x1800618aa  xor     ebx, ebx
0x1800618ac  lea     r13, __ImageBase
0x1800618b3  test    eax, eax
0x1800618b5  jz      short loc_18006190B
0x1800618b7  lea     rax, [rsp+48h+ThreadId]
0x1800618bc  xor     r9d, r9d; lpParameter
0x1800618bf  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800618c4  lea     r8, ProcessingLoop; lpStartAddress
0x1800618cb  and     [rsp+48h+var_28], 0
0x1800618d0  xor     edx, edx; dwStackSize
0x1800618d2  xor     ecx, ecx; lpThreadAttributes
0x1800618d4  call    cs:__imp_CreateThread
0x1800618db  nop     dword ptr [rax+rax+00h]
0x1800618e0  test    rax, rax
0x1800618e3  jz      loc_180061AE9
0x1800618e9  mov     edx, cs:dword_1800FB17C
0x1800618ef  inc     ebx
0x1800618f1  mov     rva qword_1800FAF40[r13+rdx*8], rax
0x1800618f9  inc     edx
0x1800618fb  mov     eax, cs:dword_1800FAF38
0x180061901  mov     cs:dword_1800FB17C, edx
0x180061907  cmp     ebx, eax
0x180061909  jb      short loc_1800618B7
0x18006190b  xor     ebx, ebx
0x18006190d  test    eax, eax
0x18006190f  jz      short loc_180061963
0x180061911  lea     rax, [rsp+48h+ThreadId]
0x180061916  xor     r9d, r9d; lpParameter
0x180061919  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x18006191e  lea     r8, QuarPacketLoop; lpStartAddress
0x180061925  and     [rsp+48h+var_28], 0
0x18006192a  xor     edx, edx; dwStackSize
0x18006192c  xor     ecx, ecx; lpThreadAttributes
0x18006192e  call    cs:__imp_CreateThread
0x180061935  nop     dword ptr [rax+rax+00h]
0x18006193a  test    rax, rax
0x18006193d  jz      loc_180061BC0
0x180061943  mov     edx, cs:dword_1800FB178
0x180061949  inc     ebx
0x18006194b  mov     rva qword_1800FAFE0[r13+rdx*8], rax
0x180061953  inc     edx
0x180061955  cmp     ebx, cs:dword_1800FAF38
0x18006195b  mov     cs:dword_1800FB178, edx
0x180061961  jb      short loc_180061911
0x180061963  lea     rax, [rsp+48h+ThreadId]
0x180061968  xor     r9d, r9d; lpParameter
0x18006196b  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180061970  lea     r8, MessageLoop; lpStartAddress
0x180061977  and     [rsp+48h+var_28], 0
0x18006197c  xor     edx, edx; dwStackSize
0x18006197e  xor     ecx, ecx; lpThreadAttributes
0x180061980  call    cs:__imp_CreateThread
0x180061987  nop     dword ptr [rax+rax+00h]
0x18006198c  mov     cs:hHandle, rax
0x180061993  test    rax, rax
0x180061996  jnz     loc_180061D09
0x18006199c  call    cs:__imp_GetLastError
0x1800619a3  nop     dword ptr [rax+rax+00h]
0x1800619a8  mov     edi, eax
0x1800619aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800619b1  lea     rbp, WPP_GLOBAL_Control
0x1800619b8  mov     bl, 10h
0x1800619ba  cmp     rcx, rbp
0x1800619bd  jz      short loc_1800619DC
0x1800619bf  test    [rcx+1Ch], bl
0x1800619c2  jz      short loc_1800619DC
0x1800619c4  mov     rcx, [rcx+10h]
0x1800619c8  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x1800619cf  mov     edx, 3Ch ; '<'
0x1800619d4  mov     r9d, eax
0x1800619d7  call    WPP_SF_D
0x1800619dc  xor     r14d, r14d
0x1800619df  cmp     cs:dword_1800FAF38, r14d
0x1800619e6  jbe     loc_180061BB9
0x1800619ec  mov     rcx, rva qword_1800FAF40[r13+r14*8]; hHandle
0x1800619f4  test    rcx, rcx
0x1800619f7  jz      short loc_180061A60
0x1800619f9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800619fc  call    cs:__imp_WaitForSingleObject
0x180061a03  nop     dword ptr [rax+rax+00h]
0x180061a08  test    eax, eax
0x180061a0a  jz      short loc_180061A43
0x180061a0c  call    cs:__imp_GetLastError
0x180061a13  nop     dword ptr [rax+rax+00h]
0x180061a18  mov     edi, eax
0x180061a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180061a21  cmp     rcx, rbp
0x180061a24  jz      short loc_180061A43
0x180061a26  test    [rcx+1Ch], bl
0x180061a29  jz      short loc_180061A43
0x180061a2b  mov     rcx, [rcx+10h]
0x180061a2f  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180061a36  mov     edx, 3Dh ; '='
0x180061a3b  mov     r9d, eax
0x180061a3e  call    WPP_SF_D
0x180061a43  mov     rcx, rva qword_1800FAF40[r13+r14*8]; hObject
0x180061a4b  call    cs:__imp_CloseHandle
0x180061a52  nop     dword ptr [rax+rax+00h]
0x180061a57  and     rva qword_1800FAF40[r13+r14*8], 0
0x180061a60  mov     rcx, rva qword_1800FAFE0[r13+r14*8]; hHandle
0x180061a68  test    rcx, rcx
0x180061a6b  jz      short loc_180061AD4
0x180061a6d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180061a70  call    cs:__imp_WaitForSingleObject
0x180061a77  nop     dword ptr [rax+rax+00h]
0x180061a7c  test    eax, eax
0x180061a7e  jz      short loc_180061AB7
0x180061a80  call    cs:__imp_GetLastError
0x180061a87  nop     dword ptr [rax+rax+00h]
0x180061a8c  mov     edi, eax
0x180061a8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180061a95  cmp     rcx, rbp
0x180061a98  jz      short loc_180061AB7
0x180061a9a  test    [rcx+1Ch], bl
0x180061a9d  jz      short loc_180061AB7
0x180061a9f  mov     rcx, [rcx+10h]
0x180061aa3  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180061aaa  mov     edx, 3Eh ; '>'
0x180061aaf  mov     r9d, eax
0x180061ab2  call    WPP_SF_D
0x180061ab7  mov     rcx, rva qword_1800FAFE0[r13+r14*8]; hObject
0x180061abf  call    cs:__imp_CloseHandle
0x180061ac6  nop     dword ptr [rax+rax+00h]
0x180061acb  and     rva qword_1800FAFE0[r13+r14*8], 0
0x180061ad4  inc     r14d
0x180061ad7  cmp     r14d, cs:dword_1800FAF38
0x180061ade  jb      loc_1800619EC
0x180061ae4  jmp     loc_180061BB9
0x180061ae9  call    cs:__imp_GetLastError
0x180061af0  nop     dword ptr [rax+rax+00h]
0x180061af5  mov     edi, eax
0x180061af7  mov     rcx, cs:WPP_GLOBAL_Control
0x180061afe  lea     rbp, WPP_GLOBAL_Control
0x180061b05  mov     bl, 10h
0x180061b07  cmp     rcx, rbp
0x180061b0a  jz      short loc_180061B29
0x180061b0c  test    [rcx+1Ch], bl
0x180061b0f  jz      short loc_180061B29
0x180061b11  mov     rcx, [rcx+10h]
0x180061b15  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180061b1c  mov     edx, 37h ; '7'
0x180061b21  mov     r9d, eax
0x180061b24  call    WPP_SF_D
0x180061b29  mov     eax, cs:dword_1800FAF38
0x180061b2f  xor     esi, esi
0x180061b31  test    eax, eax
0x180061b33  jz      loc_180061BB9
0x180061b39  mov     rcx, rva qword_1800FAF40[r13+rsi*8]; hHandle
0x180061b41  test    rcx, rcx
0x180061b44  jz      short loc_180061BB3
0x180061b46  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180061b49  call    cs:__imp_WaitForSingleObject
0x180061b50  nop     dword ptr [rax+rax+00h]
0x180061b55  test    eax, eax
0x180061b57  jz      short loc_180061B90
0x180061b59  call    cs:__imp_GetLastError
0x180061b60  nop     dword ptr [rax+rax+00h]
0x180061b65  mov     edi, eax
0x180061b67  mov     rcx, cs:WPP_GLOBAL_Control
0x180061b6e  cmp     rcx, rbp
0x180061b71  jz      short loc_180061B90
0x180061b73  test    [rcx+1Ch], bl
0x180061b76  jz      short loc_180061B90
0x180061b78  mov     rcx, [rcx+10h]
0x180061b7c  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180061b83  mov     edx, 38h ; '8'
0x180061b88  mov     r9d, eax
0x180061b8b  call    WPP_SF_D
0x180061b90  mov     rcx, rva qword_1800FAF40[r13+rsi*8]; hObject
0x180061b98  call    cs:__imp_CloseHandle
0x180061b9f  nop     dword ptr [rax+rax+00h]
0x180061ba4  and     rva qword_1800FAF40[r13+rsi*8], 0
0x180061bad  mov     eax, cs:dword_1800FAF38
0x180061bb3  inc     esi
0x180061bb5  cmp     esi, eax
0x180061bb7  jb      short loc_180061B39
0x180061bb9  mov     eax, edi
0x180061bbb  jmp     loc_180061D0B
0x180061bc0  call    cs:__imp_GetLastError
0x180061bc7  nop     dword ptr [rax+rax+00h]
0x180061bcc  mov     edi, eax
0x180061bce  mov     rcx, cs:WPP_GLOBAL_Control
0x180061bd5  lea     rbp, WPP_GLOBAL_Control
0x180061bdc  mov     bl, 10h
0x180061bde  cmp     rcx, rbp
0x180061be1  jz      short loc_180061C00
0x180061be3  test    [rcx+1Ch], bl
0x180061be6  jz      short loc_180061C00
0x180061be8  mov     rcx, [rcx+10h]
0x180061bec  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180061bf3  mov     edx, 39h ; '9'
0x180061bf8  mov     r9d, eax
0x180061bfb  call    WPP_SF_D
0x180061c00  xor     r14d, r14d
0x180061c03  cmp     cs:dword_1800FAF38, r14d
0x180061c0a  jbe     short loc_180061BB9
0x180061c0c  mov     rcx, rva qword_1800FAF40[r13+r14*8]; hHandle
0x180061c14  test    rcx, rcx
0x180061c17  jz      short loc_180061C80
0x180061c19  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180061c1c  call    cs:__imp_WaitForSingleObject
0x180061c23  nop     dword ptr [rax+rax+00h]
0x180061c28  test    eax, eax
0x180061c2a  jz      short loc_180061C63
0x180061c2c  call    cs:__imp_GetLastError
0x180061c33  nop     dword ptr [rax+rax+00h]
0x180061c38  mov     edi, eax
0x180061c3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180061c41  cmp     rcx, rbp
0x180061c44  jz      short loc_180061C63
0x180061c46  test    [rcx+1Ch], bl
0x180061c49  jz      short loc_180061C63
0x180061c4b  mov     rcx, [rcx+10h]
0x180061c4f  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180061c56  mov     edx, 3Ah ; ':'
0x180061c5b  mov     r9d, eax
0x180061c5e  call    WPP_SF_D
0x180061c63  mov     rcx, rva qword_1800FAF40[r13+r14*8]; hObject
0x180061c6b  call    cs:__imp_CloseHandle
0x180061c72  nop     dword ptr [rax+rax+00h]
0x180061c77  and     rva qword_1800FAF40[r13+r14*8], 0
0x180061c80  mov     rcx, rva qword_1800FAFE0[r13+r14*8]; hHandle
0x180061c88  test    rcx, rcx
0x180061c8b  jz      short loc_180061CF4
0x180061c8d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180061c90  call    cs:__imp_WaitForSingleObject
0x180061c97  nop     dword ptr [rax+rax+00h]
0x180061c9c  test    eax, eax
0x180061c9e  jz      short loc_180061CD7
0x180061ca0  call    cs:__imp_GetLastError
0x180061ca7  nop     dword ptr [rax+rax+00h]
0x180061cac  mov     edi, eax
0x180061cae  mov     rcx, cs:WPP_GLOBAL_Control
0x180061cb5  cmp     rcx, rbp
0x180061cb8  jz      short loc_180061CD7
0x180061cba  test    [rcx+1Ch], bl
0x180061cbd  jz      short loc_180061CD7
0x180061cbf  mov     rcx, [rcx+10h]
0x180061cc3  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180061cca  mov     edx, 3Bh ; ';'
0x180061ccf  mov     r9d, eax
0x180061cd2  call    WPP_SF_D
0x180061cd7  mov     rcx, rva qword_1800FAFE0[r13+r14*8]; hObject
0x180061cdf  call    cs:__imp_CloseHandle
0x180061ce6  nop     dword ptr [rax+rax+00h]
0x180061ceb  and     rva qword_1800FAFE0[r13+r14*8], 0
0x180061cf4  inc     r14d
0x180061cf7  cmp     r14d, cs:dword_1800FAF38
0x180061cfe  jb      loc_180061C0C
0x180061d04  jmp     loc_180061BB9
0x180061d09  xor     eax, eax
0x180061d0b  mov     rbx, [rsp+48h+arg_8]
0x180061d10  mov     rbp, [rsp+48h+arg_10]
0x180061d15  mov     rsi, [rsp+48h+arg_18]
0x180061d1a  add     rsp, 30h
0x180061d1e  pop     r14
0x180061d20  pop     r13
0x180061d22  pop     rdi
0x180061d23  retn
```
