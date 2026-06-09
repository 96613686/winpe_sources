# DpDialInit

- ea: `0x180008ffc`
- end: `0x180009338`
- name: `DpDialInit`
- size: `828`
- prototype: `va_list(HWND hWnd, ...)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180007820`
- `0x18000a268`

## callees

- `0x180008ffc`
- `0x18000a158`
- `0x18003c43c`
- `0x180048b6c`
- `0x18004d0d2`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180009061`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800090a3`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180009289`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180009061`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800090a3`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180009289`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000919a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000919a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009191`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009191`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009251`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000923b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000923b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800090fb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800090fb`
- `RASAPI32!GetOverridableParam` at `0x180009216`
- `RASAPI32!GetOverridableParam` at `0x180009216`
- `USER32!SetWindowLongPtrW` at `0x180009116`
- `USER32!SetWindowLongPtrW` at `0x1800091bb`
- `USER32!SetWindowLongPtrW` at `0x180009116`
- `USER32!SetWindowLongPtrW` at `0x1800091bb`
- `rtutils!TracePrintfExA` at `0x180009036`
- `rtutils!TracePrintfExA` at `0x1800090c7`
- `rtutils!TracePrintfExA` at `0x180009133`
- `rtutils!TracePrintfExA` at `0x180009274`
- `rtutils!TracePrintfExA` at `0x1800092ae`
- `rtutils!TracePrintfExA` at `0x180009036`
- `rtutils!TracePrintfExA` at `0x1800090c7`
- `rtutils!TracePrintfExA` at `0x180009133`
- `rtutils!TracePrintfExA` at `0x180009274`
- `rtutils!TracePrintfExA` at `0x1800092ae`

## string_xrefs

- `0x180009268`: `DpInit:CreateEvent failed: %d`

## pseudocode

```c
va_list DpDialInit(HWND hWnd, ...)
{
  va_list v1; // r15
  va_list v3; // rax
  va_list v4; // rbx
  DWORD v5; // r8d
  va_list v6; // r14
  struct _RTL_CRITICAL_SECTION *v7; // rax
  DWORD v8; // r8d
  __int64 v9; // r13
  void *v10; // r15
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  HGLOBAL v13; // rax
  HANDLE EventW; // rax
  DWORD LastError; // eax
  DWORD v16; // r14d
  int lpBuffer; // [rsp+20h] [rbp-48h]
  va_list Arguments; // [rsp+78h] [rbp+10h] BYREF
  va_list va; // [rsp+78h] [rbp+10h]
  va_list va1; // [rsp+80h] [rbp+18h] BYREF

  va_start(va1, hWnd);
  va_start(va, hWnd);
  Arguments = va_arg(va1, va_list);
  va_copy(v1, Arguments);
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DpDialInit");
  if ( !v1 || !*((_QWORD *)v1 + 55) )
  {
    v5 = 1003;
    goto LABEL_26;
  }
  v3 = (va_list)GlobalAlloc(0x40u, 0xA0u);
  v4 = v3;
  if ( v3 )
  {
    v6 = v3;
    va_copy(Arguments, v3);
    memset_0(v3, 0, 0xA0u);
    *(_DWORD *)v4 = -1061437218;
    *((_QWORD *)v4 + 1) = v1;
    *((_QWORD *)v4 + 2) = hWnd;
    v7 = (struct _RTL_CRITICAL_SECTION *)GlobalAlloc(0x40u, 0x28u);
    *((_QWORD *)v4 + 13) = v7;
    if ( v7 )
    {
      InitializeCriticalSection(v7);
      *((_DWORD *)v4 + 28) = 1;
      SetWindowLongPtrW(hWnd, 16, (LONG_PTR)v4);
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Context set");
      v9 = *((_QWORD *)v1 + 55);
      Arguments = 0;
      v10 = (void *)PszFromId(g_hinstDll, 0x209u);
      if ( v10 )
      {
        Arguments = *(va_list *)(v9 + 8);
        FormatMessageW(0x2500u, v10, 0, 0, (LPWSTR)v4 + 16, 1u, (va_list *)va);
        GlobalFree(v10);
      }
      *(_QWORD *)(*((_QWORD *)v4 + 1) + 2588LL) = v4;
      *((_QWORD *)v4 + 8) = SetWindowLongPtrW(*((HWND *)v4 + 2), -4, (LONG_PTR)DpWndProc);
      v11 = *(unsigned int *)(*(_QWORD *)(v9 + 32) + 16LL);
      *((_DWORD *)v4 + 22) = v11;
      v12 = 96 * v11;
      if ( v12 <= 0xFFFFFFFF )
      {
        v13 = GlobalAlloc(0x40u, (unsigned int)v12);
      }
      else
      {
        *((_DWORD *)v4 + 22) = 0;
        v13 = 0;
      }
      *((_QWORD *)v4 + 10) = v13;
      if ( v13 )
      {
        *((_DWORD *)v4 + 18) = GetOverridableParam(
                                 *(_QWORD *)(*((_QWORD *)v4 + 1) + 168LL),
                                 *(_QWORD *)(*((_QWORD *)v4 + 1) + 440LL),
                                 1);
        *(_DWORD *)(*((_QWORD *)v4 + 1) + 2584LL) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v4 + 1) + 24LL) + 24LL);
        EventW = CreateEventW(0, 1, 0, 0);
        *((_QWORD *)v4 + 16) = EventW;
        if ( EventW )
          return v6;
        LastError = GetLastError();
        v16 = LastError;
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "DpInit:CreateEvent failed: %d", LastError);
        v8 = v16;
LABEL_11:
        ErrorDlgUtil(hWnd, 0x13Eu, v8, lpBuffer, 0x169u, 0xFAu);
        DpInfoFree(v4);
        return 0;
      }
    }
    else if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(g_dwTraceId, 0xCu, "No memory for critical section");
    }
    v8 = 8;
    goto LABEL_11;
  }
  v5 = 8;
LABEL_26:
  ErrorDlgUtil(hWnd, 0x13Eu, v5, lpBuffer, 0x169u, 0xFAu);
  return 0;
}

```

## disassembly

```asm
0x180008ffc  mov     [rsp+arg_18], rbx
0x180009001  mov     [rsp+hWnd], rcx
0x180009006  push    rdi
0x180009007  push    r12
0x180009009  push    r13
0x18000900b  push    r14
0x18000900d  push    r15
0x18000900f  sub     rsp, 40h
0x180009013  mov     r15, rdx
0x180009016  mov     rdi, rcx
0x180009019  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000901f  mov     r13d, 0FFFFFFFFh
0x180009025  cmp     ecx, r13d
0x180009028  jz      short loc_18000903C
0x18000902a  lea     r8, aDpdialinit; "DpDialInit"
0x180009031  mov     edx, 0Ch; dwFlags
0x180009036  call    cs:__imp_TracePrintfExA
0x18000903c  test    r15, r15
0x18000903f  jz      loc_1800092FA
0x180009045  cmp     qword ptr [r15+1B8h], 0
0x18000904d  jz      loc_1800092FA
0x180009053  mov     r12d, 0A0h
0x180009059  mov     edx, r12d; dwBytes
0x18000905c  lea     ecx, [r12-60h]; uFlags
0x180009061  call    cs:__imp_GlobalAlloc
0x180009067  mov     rbx, rax
0x18000906a  test    rax, rax
0x18000906d  jnz     short loc_180009078
0x18000906f  lea     r8d, [rax+8]
0x180009073  jmp     loc_180009300
0x180009078  mov     r14, rbx
0x18000907b  mov     [rsp+68h+arg_8], rbx
0x180009080  mov     r8, r12; Size
0x180009083  xor     edx, edx; Val
0x180009085  mov     rcx, rbx; void *
0x180009088  call    memset_0
0x18000908d  mov     dword ptr [rbx], 0C0BBC0DEh
0x180009093  mov     [rbx+8], r15
0x180009097  mov     [rbx+10h], rdi
0x18000909b  mov     edx, 28h ; '('; dwBytes
0x1800090a0  lea     ecx, [rdx+18h]; uFlags
0x1800090a3  call    cs:__imp_GlobalAlloc
0x1800090a9  mov     [rbx+68h], rax
0x1800090ad  test    rax, rax
0x1800090b0  jnz     short loc_1800090F8
0x1800090b2  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800090b8  cmp     ecx, r13d
0x1800090bb  jz      short loc_1800090CD
0x1800090bd  lea     r8, aNoMemoryForCri; "No memory for critical section"
0x1800090c4  lea     edx, [rax+0Ch]; dwFlags
0x1800090c7  call    cs:__imp_TracePrintfExA
0x1800090cd  mov     r8d, 8; dwMessageId
0x1800090d3  mov     dword ptr [rsp+68h+Arguments], 0FAh; UINT
0x1800090db  mov     edx, 13Eh; uID
0x1800090e0  xor     r9d, r9d
0x1800090e3  mov     [rsp+68h+nSize], 169h; UINT
0x1800090eb  mov     rcx, rdi; hWnd
0x1800090ee  call    ErrorDlgUtil
0x1800090f3  jmp     loc_1800092EA
0x1800090f8  mov     rcx, rax; lpCriticalSection
0x1800090fb  call    cs:__imp_InitializeCriticalSection
0x180009101  mov     r12d, 1
0x180009107  mov     [rbx+70h], r12d
0x18000910b  mov     r8, rbx; dwNewLong
0x18000910e  mov     edx, 10h; nIndex
0x180009113  mov     rcx, rdi; hWnd
0x180009116  call    cs:__imp_SetWindowLongPtrW
0x18000911c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180009122  cmp     ecx, r13d
0x180009125  jz      short loc_180009139
0x180009127  lea     r8, aContextSet; "Context set"
0x18000912e  mov     edx, 0Ch; dwFlags
0x180009133  call    cs:__imp_TracePrintfExA
0x180009139  mov     r13, [r15+1B8h]
0x180009140  mov     [rsp+68h+arg_8], 0
0x180009149  mov     edx, 209h; uID
0x18000914e  mov     rcx, cs:g_hinstDll; hInstance
0x180009155  call    PszFromId
0x18000915a  mov     r15, rax
0x18000915d  test    rax, rax
0x180009160  jz      short loc_1800091A0
0x180009162  mov     rcx, [r13+8]
0x180009166  mov     [rsp+68h+arg_8], rcx
0x18000916b  lea     rcx, [rbx+20h]
0x18000916f  lea     rax, [rsp+68h+arg_8]
0x180009174  mov     [rsp+68h+Arguments], rax; Arguments
0x180009179  mov     [rsp+68h+nSize], r12d; nSize
0x18000917e  mov     [rsp+68h+lpBuffer], rcx; lpBuffer
0x180009183  xor     r9d, r9d; dwLanguageId
0x180009186  xor     r8d, r8d; dwMessageId
0x180009189  mov     rdx, r15; lpSource
0x18000918c  mov     ecx, 2500h; dwFlags
0x180009191  call    cs:__imp_FormatMessageW
0x180009197  mov     rcx, r15; hMem
0x18000919a  call    cs:__imp_GlobalFree
0x1800091a0  mov     rax, [rbx+8]
0x1800091a4  mov     [rax+0A1Ch], rbx
0x1800091ab  lea     r8, DpWndProc; dwNewLong
0x1800091b2  mov     edx, 0FFFFFFFCh; nIndex
0x1800091b7  mov     rcx, [rbx+10h]; hWnd
0x1800091bb  call    cs:__imp_SetWindowLongPtrW
0x1800091c1  mov     [rbx+40h], rax
0x1800091c5  mov     rax, [r13+20h]
0x1800091c9  mov     ecx, [rax+10h]
0x1800091cc  mov     [rbx+58h], ecx
0x1800091cf  lea     rcx, [rcx+rcx*2]
0x1800091d3  shl     rcx, 5
0x1800091d7  mov     r15d, 0FFFFFFFFh
0x1800091dd  cmp     rcx, r15
0x1800091e0  mov     eax, ecx
0x1800091e2  jbe     loc_180009282
0x1800091e8  mov     eax, r15d
0x1800091eb  mov     dword ptr [rbx+58h], 0
0x1800091f2  xor     eax, eax
0x1800091f4  mov     [rbx+50h], rax
0x1800091f8  test    rax, rax
0x1800091fb  jz      loc_1800090CD
0x180009201  mov     rcx, [rbx+8]
0x180009205  mov     r8d, r12d
0x180009208  mov     rdx, [rcx+1B8h]
0x18000920f  mov     rcx, [rcx+0A8h]
0x180009216  call    cs:__imp_GetOverridableParam
0x18000921c  mov     [rbx+48h], eax
0x18000921f  mov     rdx, [rbx+8]
0x180009223  mov     rax, [rdx+18h]
0x180009227  mov     ecx, [rax+18h]
0x18000922a  mov     [rdx+0A18h], ecx
0x180009230  xor     r9d, r9d; lpName
0x180009233  xor     r8d, r8d; bInitialState
0x180009236  mov     edx, r12d; bManualReset
0x180009239  xor     ecx, ecx; lpEventAttributes
0x18000923b  call    cs:__imp_CreateEventW
0x180009241  mov     [rbx+80h], rax
0x180009248  test    rax, rax
0x18000924b  jnz     loc_1800092E5
0x180009251  call    cs:__imp_GetLastError
0x180009257  mov     r14d, eax
0x18000925a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180009260  cmp     ecx, r15d
0x180009263  jz      short loc_18000927A
0x180009265  mov     r9d, eax
0x180009268  lea     r8, aDpinitCreateev; "DpInit:CreateEvent failed: %d"
0x18000926f  mov     edx, 0Ch; dwFlags
0x180009274  call    cs:__imp_TracePrintfExA
0x18000927a  mov     r8d, r14d
0x18000927d  jmp     loc_1800090D3
0x180009282  mov     edx, eax; dwBytes
0x180009284  mov     ecx, 40h ; '@'; uFlags
0x180009289  call    cs:__imp_GlobalAlloc
0x18000928f  jmp     loc_1800091F4
0x180009294  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000929a  cmp     ecx, 0FFFFFFFFh
0x18000929d  jz      short loc_1800092B4
0x18000929f  mov     r9d, eax
0x1800092a2  lea     r8, aInitializecrit; "InitializeCriticalSection() raise:0x%x"
0x1800092a9  mov     edx, 0Ch; dwFlags
0x1800092ae  call    cs:__imp_TracePrintfExA
0x1800092b4  mov     dword ptr [rsp+68h+Arguments], 0FAh; UINT
0x1800092bc  mov     [rsp+68h+nSize], 169h; UINT
0x1800092c4  xor     r9d, r9d
0x1800092c7  mov     edx, 13Eh; uID
0x1800092cc  lea     r8d, [r9+8]; dwMessageId
0x1800092d0  mov     rcx, [rsp+68h+hWnd]; hWnd
0x1800092d5  call    ErrorDlgUtil
0x1800092da  xor     r12d, r12d
0x1800092dd  mov     r14, [rsp+68h+arg_8]
0x1800092e2  mov     rbx, r14
0x1800092e5  test    r12d, r12d
0x1800092e8  jnz     short loc_1800092F5
0x1800092ea  mov     rcx, rbx; hMem
0x1800092ed  call    DpInfoFree
0x1800092f2  xor     r14d, r14d
0x1800092f5  mov     rax, r14
0x1800092f8  jmp     short loc_180009322
0x1800092fa  mov     r8d, 3EBh; dwMessageId
0x180009300  mov     dword ptr [rsp+68h+Arguments], 0FAh; UINT
0x180009308  mov     [rsp+68h+nSize], 169h; UINT
0x180009310  xor     r9d, r9d
0x180009313  mov     edx, 13Eh; uID
0x180009318  mov     rcx, rdi; hWnd
0x18000931b  call    ErrorDlgUtil
0x180009320  xor     eax, eax
0x180009322  mov     rbx, [rsp+68h+arg_18]
0x18000932a  add     rsp, 40h
0x18000932e  pop     r15
0x180009330  pop     r14
0x180009332  pop     r13
0x180009334  pop     r12
0x180009336  pop     rdi
0x180009337  retn
```
