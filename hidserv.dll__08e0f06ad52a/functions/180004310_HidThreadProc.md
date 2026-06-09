# HidThreadProc

- ea: `0x180004310`
- end: `0x180004649`
- name: `HidThreadProc`
- size: `825`
- prototype: `__int64 __fastcall(unsigned __int16 *Parameter, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, installer_update`

## callees

- `0x1800025b8`
- `0x1800030d4`
- `0x180004310`
- `0x180005150`
- `0x1800053a0`
- `0x1800053e0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180004395`
- `KERNEL32!WaitForSingleObject` at `0x180004461`
- `KERNEL32!WaitForSingleObject` at `0x180004395`
- `KERNEL32!WaitForSingleObject` at `0x180004461`
- `KERNEL32!CloseHandle` at `0x1800045f3`
- `KERNEL32!CloseHandle` at `0x180004600`
- `KERNEL32!CloseHandle` at `0x1800045f3`
- `KERNEL32!CloseHandle` at `0x180004600`
- `KERNEL32!ReadFile` at `0x1800043c9`
- `KERNEL32!ReadFile` at `0x1800043c9`
- `KERNEL32!CancelIo` at `0x1800044ce`
- `KERNEL32!CancelIo` at `0x1800044ce`
- `KERNEL32!WaitForMultipleObjects` at `0x1800044eb`
- `KERNEL32!WaitForMultipleObjects` at `0x1800044eb`
- `KERNEL32!GetLastError` at `0x1800043d1`
- `KERNEL32!GetLastError` at `0x1800043d1`
- `USER32!PostMessageW` at `0x1800045db`
- `USER32!PostMessageW` at `0x1800045db`

## pseudocode

```c
__int64 __fastcall HidThreadProc(unsigned __int16 *Parameter, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rsi
  BOOL v6; // ebx
  DWORD LastError; // r9d
  unsigned __int16 *i; // rbx
  unsigned int v9; // edx
  DWORD v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  HANDLE Handles[11]; // [rsp+30h] [rbp-58h] BYREF
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+8h] BYREF

  v4 = *((_QWORD *)Parameter + 24);
  Handles[0] = *((HANDLE *)Parameter + 20);
  Handles[1] = *((HANDLE *)Parameter + 19);
  NumberOfBytesRead = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids, a4);
  }
  _InterlockedIncrement(&cThreadRef);
  WaitForSingleObject(*((HANDLE *)Parameter + 19), 0xFFFFFFFF);
  if ( !*((_DWORD *)Parameter + 42) )
    goto LABEL_17;
  while ( 1 )
  {
    v6 = ReadFile(
           *((HANDLE *)Parameter + 1),
           *((LPVOID *)Parameter + 23),
           Parameter[14],
           &NumberOfBytesRead,
           (LPOVERLAPPED)(Parameter + 60));
    LastError = GetLastError();
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids, Parameter);
      }
      goto LABEL_34;
    }
    if ( LastError != 997 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_Dqq(*((_QWORD *)WPP_GLOBAL_Control + 2));
      }
      goto LABEL_16;
    }
    do
    {
      v10 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( !v10 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v12 = 22;
LABEL_32:
          WPP_SF_q(v11[2], v12, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids, Parameter);
          goto LABEL_33;
        }
        goto LABEL_33;
      }
    }
    while ( *((_DWORD *)Parameter + 42) || !CancelIo(*((HANDLE *)Parameter + 1)) );
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v12 = 23;
      goto LABEL_32;
    }
LABEL_33:
    if ( !*((_DWORD *)Parameter + 42) )
      break;
LABEL_34:
    if ( !*((_DWORD *)Parameter + 42) )
      goto LABEL_16;
    UnpackReport(*((PCHAR *)Parameter + 23), *((_DWORD *)Parameter + 50), *((PHIDP_PREPARSED_DATA *)Parameter + 2));
    HidServReportDispatch(Parameter);
    if ( !*((_DWORD *)Parameter + 42) )
      goto LABEL_17;
  }
  if ( v10 != 1 )
LABEL_16:
    WaitForSingleObject(*((HANDLE *)Parameter + 19), 0xFFFFFFFF);
LABEL_17:
  if ( *(_BYTE *)v4 )
  {
    for ( i = *(unsigned __int16 **)(v4 + 32); *i; i += 2 )
    {
      v9 = 0;
      while ( *((_WORD *)PendingButtonList + 3 * v9) != *(_WORD *)(v4 + 6)
           || *((_WORD *)PendingButtonList + 3 * v9 + 1) != i[1]
           || *((_WORD *)PendingButtonList + 3 * v9 + 2) != *i )
      {
        if ( (int)++v9 >= 16 )
          goto LABEL_44;
      }
      *(_DWORD *)((char *)PendingButtonList + 6 * v9) = 0;
      *((_WORD *)PendingButtonList + 3 * v9 + 2) = 0;
LABEL_44:
      PostMessageW(
        hWndHidServ,
        0x813Au,
        *i | ((unsigned __int64)*(unsigned __int16 *)(v4 + 6) << 16),
        (unsigned __int64)i[1] << 16);
    }
  }
  CloseHandle(*((HANDLE *)Parameter + 1));
  CloseHandle(*((HANDLE *)Parameter + 20));
  _InterlockedDecrement(&cThreadRef);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids, v13);
  }
  return 0;
}

```

## disassembly

```asm
0x180004310  mov     r11, rsp
0x180004313  push    rbx
0x180004314  push    rbp
0x180004315  push    rsi
0x180004316  push    rdi
0x180004317  push    r12
0x180004319  push    r13
0x18000431b  push    r14
0x18000431d  push    r15
0x18000431f  sub     rsp, 48h
0x180004323  mov     rax, [rcx+0A0h]
0x18000432a  xor     r14d, r14d
0x18000432d  mov     rsi, [rcx+0C0h]
0x180004334  mov     rdi, rcx
0x180004337  mov     [r11-58h], rax
0x18000433b  mov     rax, [rcx+98h]
0x180004342  mov     [r11-50h], rax
0x180004346  mov     [r11+8], r14d
0x18000434a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004351  lea     r12, WPP_GLOBAL_Control
0x180004358  lea     r13, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids
0x18000435f  cmp     rcx, r12
0x180004362  jz      short loc_180004380
0x180004364  test    byte ptr [rcx+1Ch], 4
0x180004368  jz      short loc_180004380
0x18000436a  cmp     byte ptr [rcx+19h], 5
0x18000436e  jb      short loc_180004380
0x180004370  mov     rcx, [rcx+10h]
0x180004374  lea     edx, [r14+14h]
0x180004378  mov     r8, r13
0x18000437b  call    WPP_SF_
0x180004380  lock inc cs:cThreadRef
0x180004387  mov     rcx, [rdi+98h]; hHandle
0x18000438e  or      r15d, 0FFFFFFFFh
0x180004392  mov     edx, r15d; dwMilliseconds
0x180004395  call    cs:__imp_WaitForSingleObject
0x18000439b  cmp     [rdi+0A8h], r14d
0x1800043a2  jz      loc_180004467
0x1800043a8  lea     rbp, [rdi+78h]
0x1800043ac  movzx   r8d, word ptr [rdi+1Ch]; nNumberOfBytesToRead
0x1800043b1  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800043b9  mov     rdx, [rdi+0B8h]; lpBuffer
0x1800043c0  mov     rcx, [rdi+8]; hFile
0x1800043c4  mov     [rsp+88h+lpOverlapped], rbp; lpOverlapped
0x1800043c9  call    cs:__imp_ReadFile
0x1800043cf  mov     ebx, eax
0x1800043d1  call    cs:__imp_GetLastError
0x1800043d7  mov     r9d, eax
0x1800043da  test    ebx, ebx
0x1800043dc  jz      short loc_18000441B
0x1800043de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043e5  cmp     rcx, r12
0x1800043e8  jz      loc_18000452C
0x1800043ee  test    byte ptr [rcx+1Ch], 4
0x1800043f2  jz      loc_18000452C
0x1800043f8  cmp     byte ptr [rcx+19h], 5
0x1800043fc  jb      loc_18000452C
0x180004402  mov     rcx, [rcx+10h]
0x180004406  mov     edx, 15h
0x18000440b  mov     r9, rdi
0x18000440e  mov     r8, r13
0x180004411  call    WPP_SF_q
0x180004416  jmp     loc_18000452C
0x18000441b  cmp     r9d, 3E5h
0x180004422  jz      loc_1800044DC
0x180004428  mov     rcx, cs:WPP_GLOBAL_Control
0x18000442f  cmp     rcx, r12
0x180004432  jz      short loc_180004457
0x180004434  test    byte ptr [rcx+1Ch], 4
0x180004438  jz      short loc_180004457
0x18000443a  cmp     byte ptr [rcx+19h], 3
0x18000443e  jb      short loc_180004457
0x180004440  mov     rax, [rdi+8]
0x180004444  mov     rcx, [rcx+10h]
0x180004448  mov     [rsp+88h+var_60], rax
0x18000444d  mov     [rsp+88h+lpOverlapped], rdi
0x180004452  call    WPP_SF_Dqq
0x180004457  mov     rcx, [rdi+98h]; hHandle
0x18000445e  mov     edx, r15d; dwMilliseconds
0x180004461  call    cs:__imp_WaitForSingleObject
0x180004467  cmp     [rsi], r14b
0x18000446a  jz      loc_1800045EF
0x180004470  mov     rbx, [rsi+20h]
0x180004474  cmp     [rbx], r14w
0x180004478  jz      loc_1800045EF
0x18000447e  lea     r15, PendingButtonList
0x180004485  movzx   r8d, word ptr [rsi+6]
0x18000448a  mov     edx, r14d
0x18000448d  mov     eax, edx
0x18000448f  lea     rcx, [rax+rax*2]
0x180004493  cmp     [r15+rcx*2], r8w
0x180004498  jnz     short loc_1800044B5
0x18000449a  movzx   eax, word ptr [rbx+2]
0x18000449e  cmp     [r15+rcx*2+2], ax
0x1800044a4  jnz     short loc_1800044B5
0x1800044a6  movzx   eax, word ptr [rbx]
0x1800044a9  cmp     [r15+rcx*2+4], ax
0x1800044af  jz      loc_1800045AD
0x1800044b5  inc     edx
0x1800044b7  cmp     edx, 10h
0x1800044ba  jl      short loc_18000448D
0x1800044bc  jmp     loc_1800045B7
0x1800044c1  cmp     [rdi+0A8h], r14d
0x1800044c8  jnz     short loc_1800044DC
0x1800044ca  mov     rcx, [rdi+8]; hFile
0x1800044ce  call    cs:__imp_CancelIo
0x1800044d4  test    eax, eax
0x1800044d6  jnz     loc_18000457D
0x1800044dc  xor     r8d, r8d; bWaitAll
0x1800044df  lea     rdx, [rsp+88h+Handles]; lpHandles
0x1800044e4  mov     r9d, r15d; dwMilliseconds
0x1800044e7  lea     ecx, [r8+2]; nCount
0x1800044eb  call    cs:__imp_WaitForMultipleObjects
0x1800044f1  mov     ebx, eax
0x1800044f3  test    eax, eax
0x1800044f5  jnz     short loc_1800044C1
0x1800044f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044fe  cmp     rcx, r12
0x180004501  jz      short loc_180004523
0x180004503  test    byte ptr [rcx+1Ch], 4
0x180004507  jz      short loc_180004523
0x180004509  cmp     byte ptr [rcx+19h], 4
0x18000450d  jb      short loc_180004523
0x18000450f  mov     edx, 16h
0x180004514  mov     rcx, [rcx+10h]
0x180004518  mov     r9, rdi
0x18000451b  mov     r8, r13
0x18000451e  call    WPP_SF_q
0x180004523  cmp     [rdi+0A8h], r14d
0x18000452a  jz      short loc_18000459F
0x18000452c  cmp     [rdi+0A8h], r14d
0x180004533  jz      loc_180004457
0x180004539  mov     rax, [rdi+10h]
0x18000453d  mov     r9, [rdi+0C0h]
0x180004544  movzx   edx, word ptr [rdi+1Ch]
0x180004548  mov     rcx, [rdi+0B8h]; Report
0x18000454f  mov     [rsp+88h+var_60], rax; PHIDP_PREPARSED_DATA
0x180004554  mov     eax, [rdi+0C8h]
0x18000455a  mov     dword ptr [rsp+88h+lpOverlapped], eax; int
0x18000455e  call    UnpackReport
0x180004563  mov     rcx, rdi
0x180004566  call    HidServReportDispatch
0x18000456b  cmp     [rdi+0A8h], r14d
0x180004572  jnz     loc_1800043AC
0x180004578  jmp     loc_180004467
0x18000457d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004584  cmp     rcx, r12
0x180004587  jz      short loc_180004523
0x180004589  test    byte ptr [rcx+1Ch], 4
0x18000458d  jz      short loc_180004523
0x18000458f  cmp     byte ptr [rcx+19h], 4
0x180004593  jb      short loc_180004523
0x180004595  mov     edx, 17h
0x18000459a  jmp     loc_180004514
0x18000459f  cmp     ebx, 1
0x1800045a2  jz      loc_180004467
0x1800045a8  jmp     loc_180004457
0x1800045ad  mov     [r15+rcx*2], r14d
0x1800045b1  mov     [r15+rcx*2+4], r14w
0x1800045b7  movzx   r8d, word ptr [rsi+6]
0x1800045bc  mov     edx, 813Ah; Msg
0x1800045c1  movzx   r9d, word ptr [rbx+2]
0x1800045c6  movzx   eax, word ptr [rbx]
0x1800045c9  mov     rcx, cs:hWndHidServ; hWnd
0x1800045d0  shl     r8, 10h
0x1800045d4  or      r8, rax; wParam
0x1800045d7  shl     r9, 10h; lParam
0x1800045db  call    cs:__imp_PostMessageW
0x1800045e1  add     rbx, 4
0x1800045e5  cmp     [rbx], r14w
0x1800045e9  jnz     loc_180004485
0x1800045ef  mov     rcx, [rdi+8]; hObject
0x1800045f3  call    cs:__imp_CloseHandle
0x1800045f9  mov     rcx, [rdi+0A0h]; hObject
0x180004600  call    cs:__imp_CloseHandle
0x180004606  lock dec cs:cThreadRef
0x18000460d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004614  cmp     rcx, r12
0x180004617  jz      short loc_180004636
0x180004619  test    byte ptr [rcx+1Ch], 4
0x18000461d  jz      short loc_180004636
0x18000461f  cmp     byte ptr [rcx+19h], 5
0x180004623  jb      short loc_180004636
0x180004625  mov     rcx, [rcx+10h]
0x180004629  mov     edx, 19h
0x18000462e  mov     r8, r13
0x180004631  call    WPP_SF_
0x180004636  xor     eax, eax
0x180004638  add     rsp, 48h
0x18000463c  pop     r15
0x18000463e  pop     r14
0x180004640  pop     r13
0x180004642  pop     r12
0x180004644  pop     rdi
0x180004645  pop     rsi
0x180004646  pop     rbp
0x180004647  pop     rbx
0x180004648  retn
```
