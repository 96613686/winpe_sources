# DialProgressDlg

- ea: `0x180007820`
- end: `0x180007b13`
- name: `DialProgressDlg`
- size: `755`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000e360`

## callees

- `0x180007820`
- `0x180008e14`
- `0x180008ffc`
- `0x18000a158`
- `0x180039124`
- `0x18003b57c`
- `0x18003b7ac`
- `0x180048b6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007890`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800078da`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800078da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000787e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000787e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180007a9c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180007a9c`
- `RASAPI32!DestroyEntryNode` at `0x1800079ed`
- `RASAPI32!DestroyEntryNode` at `0x1800079ed`
- `RASAPI32!ReadPhonebookFile` at `0x1800079bb`
- `RASAPI32!ReadPhonebookFile` at `0x1800079bb`
- `RASAPI32!ClosePhonebookFile` at `0x180007a24`
- `RASAPI32!ClosePhonebookFile` at `0x180007a24`
- `RASAPI32!WritePhonebookFile` at `0x180007af9`
- `RASAPI32!WritePhonebookFile` at `0x180007af9`
- `RASAPI32!DestroyLinkNode` at `0x180007ac2`
- `RASAPI32!DestroyLinkNode` at `0x180007ac2`
- `rtutils!TracePrintfExA` at `0x1800078b2`
- `rtutils!TracePrintfExA` at `0x1800078fe`
- `rtutils!TracePrintfExA` at `0x1800078b2`
- `rtutils!TracePrintfExA` at `0x1800078fe`

## string_xrefs

- `0x1800078a6`: `DialProgressDlg:CreateEvent failed: %d`

## pseudocode

```c
__int64 __fastcall DialProgressDlg(HWND a1)
{
  HWND v1; // rsi
  HWND v2; // rbx
  __int64 v3; // rsi
  __int64 v4; // rdi
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v7; // r8
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rsi
  __int64 v11; // rdx
  int v12; // ebp
  int v13; // ecx
  __int64 v14; // rsi
  __int64 v15; // r15
  const WCHAR *v16; // r12
  __int64 i; // r14
  __int64 v18; // rax
  __int128 v20; // [rsp+40h] [rbp-78h] BYREF
  __int128 v21; // [rsp+50h] [rbp-68h]
  __int128 v22; // [rsp+60h] [rbp-58h]
  __int64 v23; // [rsp+70h] [rbp-48h]

  v1 = a1 + 6;
  v2 = a1;
  if ( *((_DWORD *)a1 + 103) )
  {
    a1 = *(HWND *)(*(_QWORD *)v1 + 4LL);
    if ( a1 )
    {
      v3 = DpDialInit(a1);
      if ( v3 )
      {
        EventW = CreateEventW(0, 1, 0, 0);
        *(_QWORD *)(v3 + 144) = EventW;
        if ( EventW )
        {
          *(_DWORD *)(v3 + 152) = 0;
          DpDial(v3, 0);
          if ( !WaitForSingleObject(*(HANDLE *)(v3 + 144), 0xFFFFFFFF) )
          {
            v4 = *(unsigned int *)(v3 + 152);
            goto LABEL_12;
          }
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "\\DialProgressDlg: WaitForSingleObject failed");
        }
        else
        {
          LastError = GetLastError();
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "DialProgressDlg:CreateEvent failed: %d", LastError);
        }
      }
      v4 = 0;
LABEL_12:
      DpInfoFree((HGLOBAL)v3);
      goto LABEL_15;
    }
  }
  v4 = SHFusionDialogBoxParam(a1, 113, *(_QWORD *)(*(_QWORD *)v1 + 4LL), DpDlgProc);
  if ( v4 == -1 )
  {
    ErrorDlgUtil(*(HWND *)(*(_QWORD *)v1 + 4LL), 0x13Eu, 0x27Bu, (int)v2, 0x169u, 0xFAu);
    *(_DWORD *)(*(_QWORD *)v1 + 28LL) = 635;
    v4 = 0;
  }
LABEL_15:
  if ( v4 )
  {
    v7 = *((_QWORD *)v2 + 55);
    v8 = (_QWORD *)*((_QWORD *)v2 + 4);
    v9 = *((_QWORD *)v2 + 21);
    v23 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    if ( !(unsigned int)ReadPhonebookFile(*v8, v9, *(_QWORD *)(v7 + 8), 1) )
    {
      v10 = *(_QWORD *)v21;
      if ( *(_QWORD *)v21 )
      {
        DtlRemoveNode(*(_QWORD *)(*((_QWORD *)v2 + 4) + 16LL), *((_QWORD *)v2 + 54));
        DestroyEntryNode(*((_QWORD *)v2 + 54));
        DtlRemoveNode(v21, v10);
        DtlAddNodeLast(*(_QWORD *)(*((_QWORD *)v2 + 4) + 16LL), v11);
        *((_QWORD *)v2 + 54) = v10;
        *((_QWORD *)v2 + 55) = *(_QWORD *)(v10 + 16);
      }
      ClosePhonebookFile(&v20);
    }
  }
  v12 = 0;
  if ( *((_DWORD *)v2 + 104) )
  {
    *(_DWORD *)(*((_QWORD *)v2 + 55) + 176LL) = 0;
    v12 = 1;
  }
  v13 = *((_DWORD *)v2 + 105);
  if ( v13 )
  {
    v12 = 1;
    *(_DWORD *)(*((_QWORD *)v2 + 55) + 236LL) |= v13;
  }
  if ( *((_QWORD *)v2 + 53) )
  {
    v14 = **(_QWORD **)(*((_QWORD *)v2 + 55) + 32LL);
    if ( v14 )
    {
      do
      {
        v15 = *(_QWORD *)(v14 + 8);
        v16 = **(const WCHAR ***)(v14 + 16);
        for ( i = **((_QWORD **)v2 + 53); i; i = *(_QWORD *)(i + 8) )
        {
          if ( !lstrcmpW(*(LPCWSTR *)(i + 16), v16) )
          {
            v18 = DtlRemoveNode(*(_QWORD *)(*((_QWORD *)v2 + 55) + 32LL), v14);
            DestroyLinkNode(v18);
            v12 = 1;
            break;
          }
        }
        v14 = v15;
      }
      while ( v15 );
    }
  }
  if ( v12 )
  {
    *(_DWORD *)(*((_QWORD *)v2 + 55) + 532LL) = 1;
    WritePhonebookFile(*((_QWORD *)v2 + 4), 0);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007820  push    rbx
0x180007822  push    rbp
0x180007823  push    rsi
0x180007824  push    rdi
0x180007825  push    r12
0x180007827  push    r14
0x180007829  push    r15
0x18000782b  sub     rsp, 80h
0x180007832  cmp     dword ptr [rcx+19Ch], 0
0x180007839  lea     rsi, [rcx+18h]
0x18000783d  mov     rbx, rcx
0x180007840  mov     r14d, 1
0x180007846  jz      loc_180007919
0x18000784c  mov     rax, [rsi]
0x18000784f  mov     rcx, [rax+4]; hWnd
0x180007853  test    rcx, rcx
0x180007856  jz      loc_180007919
0x18000785c  mov     rdx, rbx
0x18000785f  call    DpDialInit
0x180007864  mov     rsi, rax
0x180007867  test    rax, rax
0x18000786a  jnz     short loc_180007873
0x18000786c  xor     edi, edi
0x18000786e  jmp     loc_18000790F
0x180007873  xor     r9d, r9d; lpName
0x180007876  xor     r8d, r8d; bInitialState
0x180007879  mov     edx, r14d; bManualReset
0x18000787c  xor     ecx, ecx; lpEventAttributes
0x18000787e  call    cs:__imp_CreateEventW
0x180007884  mov     [rsi+90h], rax
0x18000788b  test    rax, rax
0x18000788e  jnz     short loc_1800078BA
0x180007890  call    cs:__imp_GetLastError
0x180007896  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000789c  or      edi, 0FFFFFFFFh
0x18000789f  cmp     ecx, edi
0x1800078a1  jz      short loc_18000786C
0x1800078a3  mov     r9d, eax
0x1800078a6  lea     r8, aDialprogressdl; "DialProgressDlg:CreateEvent failed: %d"
0x1800078ad  mov     edx, 0Ch; dwFlags
0x1800078b2  call    cs:__imp_TracePrintfExA
0x1800078b8  jmp     short loc_18000786C
0x1800078ba  xor     edx, edx
0x1800078bc  mov     dword ptr [rsi+98h], 0
0x1800078c6  mov     rcx, rsi
0x1800078c9  call    DpDial
0x1800078ce  mov     rcx, [rsi+90h]; hHandle
0x1800078d5  or      edi, 0FFFFFFFFh
0x1800078d8  mov     edx, edi; dwMilliseconds
0x1800078da  call    cs:__imp_WaitForSingleObject
0x1800078e0  test    eax, eax
0x1800078e2  jz      short loc_180007909
0x1800078e4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800078ea  cmp     ecx, edi
0x1800078ec  jz      loc_18000786C
0x1800078f2  lea     r8, aDialprogressdl_0; "\\DialProgressDlg: WaitForSingleObject "...
0x1800078f9  mov     edx, 0Ch; dwFlags
0x1800078fe  call    cs:__imp_TracePrintfExA
0x180007904  jmp     loc_18000786C
0x180007909  mov     edi, [rsi+98h]
0x18000790f  mov     rcx, rsi; hMem
0x180007912  call    DpInfoFree
0x180007917  jmp     short loc_180007973
0x180007919  mov     r8, [rsi]
0x18000791c  lea     r9, DpDlgProc
0x180007923  mov     edx, 71h ; 'q'
0x180007928  mov     qword ptr [rsp+0B8h+var_98], rbx; int
0x18000792d  mov     r8, [r8+4]
0x180007931  call    SHFusionDialogBoxParam
0x180007936  mov     rdi, rax
0x180007939  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000793d  jnz     short loc_180007973
0x18000793f  mov     rcx, [rsi]
0x180007942  mov     edi, 27Bh
0x180007947  mov     [rsp+0B8h+var_88], 0FAh; UINT
0x18000794f  xor     r9d, r9d
0x180007952  mov     r8d, edi; dwMessageId
0x180007955  mov     [rsp+0B8h+var_90], 169h; UINT
0x18000795d  mov     edx, 13Eh; uID
0x180007962  mov     rcx, [rcx+4]; hWnd
0x180007966  call    ErrorDlgUtil
0x18000796b  mov     rax, [rsi]
0x18000796e  mov     [rax+1Ch], edi
0x180007971  xor     edi, edi
0x180007973  test    rdi, rdi
0x180007976  jz      loc_180007A2A
0x18000797c  mov     r8, [rbx+1B8h]
0x180007983  xorps   xmm0, xmm0
0x180007986  mov     rcx, [rbx+20h]
0x18000798a  xor     eax, eax
0x18000798c  mov     rdx, [rbx+0A8h]
0x180007993  mov     r9d, r14d
0x180007996  mov     [rsp+0B8h+var_48], rax
0x18000799b  lea     rax, [rsp+0B8h+var_78]
0x1800079a0  movups  [rsp+0B8h+var_78], xmm0
0x1800079a5  mov     qword ptr [rsp+0B8h+var_98], rax
0x1800079aa  movups  [rsp+0B8h+var_68], xmm0
0x1800079af  movups  [rsp+0B8h+var_58], xmm0
0x1800079b4  mov     r8, [r8+8]
0x1800079b8  mov     rcx, [rcx]
0x1800079bb  call    cs:__imp_ReadPhonebookFile
0x1800079c1  test    eax, eax
0x1800079c3  jnz     short loc_180007A2A
0x1800079c5  mov     rax, qword ptr [rsp+0B8h+var_68]
0x1800079ca  mov     rsi, [rax]
0x1800079cd  test    rsi, rsi
0x1800079d0  jz      short loc_180007A1F
0x1800079d2  mov     rcx, [rbx+20h]
0x1800079d6  mov     rdx, [rbx+1B0h]
0x1800079dd  mov     rcx, [rcx+10h]
0x1800079e1  call    DtlRemoveNode
0x1800079e6  mov     rcx, [rbx+1B0h]
0x1800079ed  call    cs:__imp_DestroyEntryNode
0x1800079f3  mov     rcx, qword ptr [rsp+0B8h+var_68]
0x1800079f8  mov     rdx, rsi
0x1800079fb  call    DtlRemoveNode
0x180007a00  mov     rcx, [rbx+20h]
0x180007a04  mov     rcx, [rcx+10h]
0x180007a08  call    DtlAddNodeLast
0x180007a0d  mov     [rbx+1B0h], rsi
0x180007a14  mov     rax, [rsi+10h]
0x180007a18  mov     [rbx+1B8h], rax
0x180007a1f  lea     rcx, [rsp+0B8h+var_78]
0x180007a24  call    cs:__imp_ClosePhonebookFile
0x180007a2a  xor     ebp, ebp
0x180007a2c  cmp     [rbx+1A0h], ebp
0x180007a32  jz      short loc_180007A44
0x180007a34  mov     rax, [rbx+1B8h]
0x180007a3b  mov     [rax+0B0h], ebp
0x180007a41  mov     ebp, r14d
0x180007a44  mov     ecx, [rbx+1A4h]
0x180007a4a  test    ecx, ecx
0x180007a4c  jz      short loc_180007A5E
0x180007a4e  mov     rax, [rbx+1B8h]
0x180007a55  mov     ebp, r14d
0x180007a58  or      [rax+0ECh], ecx
0x180007a5e  cmp     qword ptr [rbx+1A8h], 0
0x180007a66  jz      short loc_180007AE1
0x180007a68  mov     rax, [rbx+1B8h]
0x180007a6f  mov     rcx, [rax+20h]
0x180007a73  mov     rsi, [rcx]
0x180007a76  test    rsi, rsi
0x180007a79  jz      short loc_180007AE1
0x180007a7b  mov     rax, [rsi+10h]
0x180007a7f  mov     r15, [rsi+8]
0x180007a83  mov     r12, [rax]
0x180007a86  mov     rax, [rbx+1A8h]
0x180007a8d  mov     r14, [rax]
0x180007a90  test    r14, r14
0x180007a93  jz      short loc_180007AD3
0x180007a95  mov     rcx, [r14+10h]; lpString1
0x180007a99  mov     rdx, r12; lpString2
0x180007a9c  call    cs:__imp_lstrcmpW
0x180007aa2  test    eax, eax
0x180007aa4  jz      short loc_180007AAC
0x180007aa6  mov     r14, [r14+8]
0x180007aaa  jmp     short loc_180007A90
0x180007aac  mov     rcx, [rbx+1B8h]
0x180007ab3  mov     rdx, rsi
0x180007ab6  mov     rcx, [rcx+20h]
0x180007aba  call    DtlRemoveNode
0x180007abf  mov     rcx, rax
0x180007ac2  call    cs:__imp_DestroyLinkNode
0x180007ac8  mov     r14d, 1
0x180007ace  mov     ebp, r14d
0x180007ad1  jmp     short loc_180007AD9
0x180007ad3  mov     r14d, 1
0x180007ad9  mov     rsi, r15
0x180007adc  test    r15, r15
0x180007adf  jnz     short loc_180007A7B
0x180007ae1  test    ebp, ebp
0x180007ae3  jz      short loc_180007AFF
0x180007ae5  mov     rax, [rbx+1B8h]
0x180007aec  xor     edx, edx
0x180007aee  mov     [rax+214h], r14d
0x180007af5  mov     rcx, [rbx+20h]
0x180007af9  call    cs:__imp_WritePhonebookFile
0x180007aff  mov     eax, edi
0x180007b01  add     rsp, 80h
0x180007b08  pop     r15
0x180007b0a  pop     r14
0x180007b0c  pop     r12
0x180007b0e  pop     rdi
0x180007b0f  pop     rsi
0x180007b10  pop     rbp
0x180007b11  pop     rbx
0x180007b12  retn
```
