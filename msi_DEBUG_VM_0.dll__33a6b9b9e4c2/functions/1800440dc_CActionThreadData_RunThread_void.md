# CActionThreadData::RunThread(void)

- ea: `0x1800440dc`
- end: `0x18004433d`
- name: `?RunThread@CActionThreadData@@QEAA?AW4iesEnum@@XZ`
- size: `609`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800437b8`
- `0x18009f870`
- `0x1801c5f70`
- `0x1801c60b4`

## callees

- `0x18003c7e0`
- `0x18003ca18`
- `0x1800440dc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18004422d`
- `KERNEL32!CloseHandle` at `0x18004422d`
- `KERNEL32!GetExitCodeThread` at `0x180044223`
- `KERNEL32!GetExitCodeThread` at `0x180044223`
- `KERNEL32!GetCurrentThreadId` at `0x180044109`
- `KERNEL32!GetCurrentThreadId` at `0x180044109`
- `KERNEL32!WaitForSingleObject` at `0x180044173`
- `KERNEL32!WaitForSingleObject` at `0x180044173`
- `KERNEL32!CreateThread` at `0x18004413a`
- `KERNEL32!CreateThread` at `0x18004413a`
- `USER32!MsgWaitForMultipleObjects` at `0x1800441fd`
- `USER32!MsgWaitForMultipleObjects` at `0x1800441fd`
- `USER32!PeekMessageW` at `0x1800441e1`
- `USER32!PeekMessageW` at `0x1800441e1`
- `USER32!TranslateMessage` at `0x1800441c0`
- `USER32!TranslateMessage` at `0x1800441c0`
- `USER32!DispatchMessageW` at `0x1800441ca`
- `USER32!DispatchMessageW` at `0x1800441ca`

## pseudocode

```c
__int64 __fastcall CActionThreadData::RunThread(__int64 a1)
{
  int v1; // esi
  int v3; // edi
  HANDLE Thread; // rax
  DWORD v5; // ecx
  DWORD v6; // ebx
  __int64 result; // rax
  DWORD v8; // ecx
  DWORD v9; // ecx
  DWORD v10; // ecx
  DWORD v11; // ecx
  DWORD v12; // ecx
  DWORD v13; // ecx
  MSG Msg; // [rsp+30h] [rbp-30h] BYREF
  DWORD ExitCode; // [rsp+80h] [rbp+20h] BYREF
  HANDLE hHandle; // [rsp+88h] [rbp+28h] BYREF

  v1 = *(_DWORD *)(a1 + 8);
  if ( (v1 & 0x80u) == 0 )
  {
    v3 = 0;
    if ( GetCurrentThreadId() == (_DWORD)qword_1803096A8 )
      *(_BYTE *)(a1 + 124) = 1;
  }
  else
  {
    v3 = 1;
  }
  Thread = CreateThread(0, 0xA000u, *(LPTHREAD_START_ROUTINE *)(a1 + 112), (LPVOID)a1, 0, (LPDWORD)(a1 + 36));
  *(_QWORD *)(a1 + 16) = Thread;
  hHandle = Thread;
  if ( !Thread )
    return 3;
  v5 = 0;
  ExitCode = 0;
  if ( !v3 )
  {
    if ( GetTestFlag(84) )
    {
      do
      {
        v6 = WaitForSingleObject(hHandle, 0x14u);
        MsiUIMessageContext::Invoke(&g_MessageContext, 167772160, &off_180305DB0);
      }
      while ( v6 == 258 );
    }
    else
    {
      ++HIDWORD(qword_1803096FC);
      while ( MsgWaitForMultipleObjects(1u, &hHandle, 0, 0xFFFFFFFF, 0x1CFFu) == 1 )
      {
        memset(&Msg, 0, sizeof(Msg));
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        {
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
      if ( HIDWORD(qword_1803096FC) )
        --HIDWORD(qword_1803096FC);
    }
    GetExitCodeThread(hHandle, &ExitCode);
    CloseHandle(hHandle);
    v5 = ExitCode;
  }
  if ( (v1 & 0x20000) != 0 )
    return v5;
  if ( v5 <= 0x643 )
  {
    if ( v5 != 1603 )
    {
      if ( !v5 )
        return 2 * (v3 ^ 1u) - 1;
      result = 7;
      v8 = v5 - 7;
      if ( v8 )
      {
        v9 = v8 - 227;
        if ( v9 && (v10 = v9 - 25) != 0 )
        {
          v11 = v10 - 895;
          if ( v11 && (v12 = v11 - 3) != 0 )
          {
            v13 = v12 - 444;
            if ( v13 )
            {
              if ( v13 == 1 )
                return 2;
              else
                return 3;
            }
            else
            {
              return 4294967290LL;
            }
          }
          else
          {
            return 4294967291LL;
          }
        }
        else
        {
          return 5;
        }
      }
      return result;
    }
    return 3;
  }
  switch ( v5 )
  {
    case 0x644u:
      return 4;
    case 0x649u:
      return 6;
    case 0x65Au:
      return 0;
    case 0x65Fu:
      return 4294967293LL;
    case 0xBC2u:
      return 4294967292LL;
    case 0xFFFFFFFE:
      return 4294967294LL;
  }
  result = 0xFFFFFFFFLL;
  if ( v5 != -1 )
    return 3;
  return result;
}

```

## disassembly

```asm
0x1800440dc  mov     [rsp-18h+arg_10], rbx
0x1800440e1  mov     [rsp-18h+arg_18], rsi
0x1800440e6  push    rbp
0x1800440e7  push    rdi
0x1800440e8  push    r14
0x1800440ea  mov     rbp, rsp
0x1800440ed  sub     rsp, 60h
0x1800440f1  mov     esi, [rcx+8]
0x1800440f4  mov     rbx, rcx
0x1800440f7  mov     r14d, 1
0x1800440fd  test    sil, sil
0x180044100  jns     short loc_180044107
0x180044102  mov     edi, r14d
0x180044105  jmp     short loc_18004411B
0x180044107  xor     edi, edi
0x180044109  call    cs:__imp_GetCurrentThreadId
0x18004410f  cmp     eax, dword ptr cs:qword_1803096A8
0x180044115  jnz     short loc_18004411B
0x180044117  mov     [rbx+7Ch], r14b
0x18004411b  mov     r8, [rbx+70h]; lpStartAddress
0x18004411f  lea     rax, [rbx+24h]
0x180044123  mov     [rsp+60h+lpThreadId], rax; lpThreadId
0x180044128  mov     r9, rbx; lpParameter
0x18004412b  mov     edx, 0A000h; dwStackSize
0x180044130  mov     [rsp+60h+dwCreationFlags], 0; dwCreationFlags
0x180044138  xor     ecx, ecx; lpThreadAttributes
0x18004413a  call    cs:__imp_CreateThread
0x180044140  mov     [rbx+10h], rax
0x180044144  mov     [rbp+hHandle], rax
0x180044148  test    rax, rax
0x18004414b  jz      loc_180044323
0x180044151  xor     ecx, ecx
0x180044153  mov     [rbp+ExitCode], ecx
0x180044156  test    edi, edi
0x180044158  jnz     loc_180044236
0x18004415e  lea     ecx, [rdi+54h]; int
0x180044161  call    ?GetTestFlag@@YA_NH@Z; GetTestFlag(int)
0x180044166  test    al, al
0x180044168  jz      short loc_18004419D
0x18004416a  mov     rcx, [rbp+hHandle]; hHandle
0x18004416e  mov     edx, 14h; dwMilliseconds
0x180044173  call    cs:__imp_WaitForSingleObject
0x180044179  lea     r8, off_180305DB0
0x180044180  mov     edx, 0A000000h
0x180044185  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; MsiUIMessageContext g_MessageContext
0x18004418c  mov     ebx, eax
0x18004418e  call    ?Invoke@MsiUIMessageContext@@QEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z; MsiUIMessageContext::Invoke(imtEnum,IMsiRecord *)
0x180044193  cmp     ebx, 102h
0x180044199  jz      short loc_18004416A
0x18004419b  jmp     short loc_18004421B
0x18004419d  add     dword ptr cs:qword_1803096FC+4, r14d
0x1800441a4  mov     ebx, 1CFFh
0x1800441a9  jmp     short loc_1800441EB
0x1800441ab  xorps   xmm0, xmm0
0x1800441ae  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x1800441b2  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x1800441b6  movups  xmmword ptr [rbp+Msg.time], xmm0
0x1800441ba  jmp     short loc_1800441D0
0x1800441bc  lea     rcx, [rbp+Msg]; lpMsg
0x1800441c0  call    cs:__imp_TranslateMessage
0x1800441c6  lea     rcx, [rbp+Msg]; lpMsg
0x1800441ca  call    cs:__imp_DispatchMessageW
0x1800441d0  xor     r9d, r9d; wMsgFilterMax
0x1800441d3  mov     [rsp+60h+dwCreationFlags], r14d; wRemoveMsg
0x1800441d8  xor     r8d, r8d; wMsgFilterMin
0x1800441db  lea     rcx, [rbp+Msg]; lpMsg
0x1800441df  xor     edx, edx; hWnd
0x1800441e1  call    cs:__imp_PeekMessageW
0x1800441e7  test    eax, eax
0x1800441e9  jnz     short loc_1800441BC
0x1800441eb  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800441ef  mov     [rsp+60h+dwCreationFlags], ebx; dwWakeMask
0x1800441f3  xor     r8d, r8d; fWaitAll
0x1800441f6  lea     rdx, [rbp+hHandle]; pHandles
0x1800441fa  mov     ecx, r14d; nCount
0x1800441fd  call    cs:__imp_MsgWaitForMultipleObjects
0x180044203  cmp     eax, r14d
0x180044206  jz      short loc_1800441AB
0x180044208  mov     eax, dword ptr cs:qword_1803096FC+4
0x18004420e  test    eax, eax
0x180044210  jz      short loc_18004421B
0x180044212  sub     eax, r14d
0x180044215  mov     dword ptr cs:qword_1803096FC+4, eax
0x18004421b  mov     rcx, [rbp+hHandle]; hThread
0x18004421f  lea     rdx, [rbp+ExitCode]; lpExitCode
0x180044223  call    cs:__imp_GetExitCodeThread
0x180044229  mov     rcx, [rbp+hHandle]; hObject
0x18004422d  call    cs:__imp_CloseHandle
0x180044233  mov     ecx, [rbp+ExitCode]
0x180044236  bt      esi, 11h
0x18004423a  jnb     short loc_180044243
0x18004423c  mov     eax, ecx
0x18004423e  jmp     loc_180044328
0x180044243  mov     eax, 643h
0x180044248  cmp     ecx, eax
0x18004424a  ja      short loc_1800442C1
0x18004424c  jz      loc_180044323
0x180044252  test    ecx, ecx
0x180044254  jz      short loc_1800442B5
0x180044256  mov     eax, 7
0x18004425b  sub     ecx, eax
0x18004425d  jz      loc_180044328
0x180044263  sub     ecx, 0E3h
0x180044269  jz      short loc_1800442AE
0x18004426b  sub     ecx, 19h
0x18004426e  jz      short loc_1800442AE
0x180044270  sub     ecx, 37Fh
0x180044276  jz      short loc_1800442A7
0x180044278  lea     edx, [rax-4]
0x18004427b  sub     ecx, edx
0x18004427d  jz      short loc_1800442A7
0x18004427f  sub     ecx, 1BCh
0x180044285  jz      short loc_18004429D
0x180044287  cmp     ecx, r14d
0x18004428a  jz      short loc_180044293
0x18004428c  mov     eax, edx
0x18004428e  jmp     loc_180044328
0x180044293  mov     eax, 2
0x180044298  jmp     loc_180044328
0x18004429d  mov     eax, 0FFFFFFFAh
0x1800442a2  jmp     loc_180044328
0x1800442a7  mov     eax, 0FFFFFFFBh
0x1800442ac  jmp     short loc_180044328
0x1800442ae  mov     eax, 5
0x1800442b3  jmp     short loc_180044328
0x1800442b5  xor     edi, r14d
0x1800442b8  lea     eax, ds:0FFFFFFFFFFFFFFFFh[rdi*2]
0x1800442bf  jmp     short loc_180044328
0x1800442c1  cmp     ecx, 644h
0x1800442c7  jz      short loc_18004431C
0x1800442c9  cmp     ecx, 649h
0x1800442cf  jz      short loc_180044315
0x1800442d1  cmp     ecx, 65Ah
0x1800442d7  jz      short loc_180044311
0x1800442d9  cmp     ecx, 65Fh
0x1800442df  jz      short loc_18004430A
0x1800442e1  cmp     ecx, 0BC2h
0x1800442e7  jz      short loc_180044303
0x1800442e9  cmp     ecx, 0FFFFFFFEh
0x1800442ec  jz      short loc_1800442FC
0x1800442ee  or      eax, 0FFFFFFFFh
0x1800442f1  cmp     ecx, 0FFFFFFFFh
0x1800442f4  lea     edx, [rax+4]
0x1800442f7  cmovnz  eax, edx
0x1800442fa  jmp     short loc_180044328
0x1800442fc  mov     eax, 0FFFFFFFEh
0x180044301  jmp     short loc_180044328
0x180044303  mov     eax, 0FFFFFFFCh
0x180044308  jmp     short loc_180044328
0x18004430a  mov     eax, 0FFFFFFFDh
0x18004430f  jmp     short loc_180044328
0x180044311  xor     eax, eax
0x180044313  jmp     short loc_180044328
0x180044315  mov     eax, 6
0x18004431a  jmp     short loc_180044328
0x18004431c  mov     eax, 4
0x180044321  jmp     short loc_180044328
0x180044323  mov     eax, 3
0x180044328  lea     r11, [rsp+60h+var_s0]
0x18004432d  mov     rbx, [r11+30h]
0x180044331  mov     rsi, [r11+38h]
0x180044335  mov     rsp, r11
0x180044338  pop     r14
0x18004433a  pop     rdi
0x18004433b  pop     rbp
0x18004433c  retn
```
