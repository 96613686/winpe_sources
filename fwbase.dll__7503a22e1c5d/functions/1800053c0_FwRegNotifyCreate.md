# FwRegNotifyCreate

- ea: `0x1800053c0`
- end: `0x180005556`
- name: `FwRegNotifyCreate`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800050c0`

## callees

- `0x1800045f0`
- `0x180004750`
- `0x1800047e0`
- `0x1800053c0`
- `0x180006030`
- `0x1800068e4`
- `0x1800130bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000547c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000547c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054d8`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800054a8`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800054a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000541d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000541d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000540c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000540c`

## string_xrefs

- `0x1800054d1`: `FwRegNotifyCreate`
- `0x180005507`: `FwRegNotifyCreate`
- `0x18000553a`: `FwRegNotifyCreate`
- `0x18000554a`: `CreateEventW`

## pseudocode

```c
__int64 __fastcall FwRegNotifyCreate(__int64 a1, void *a2, int a3, int a4, int a5, __int64 a6, __int64 a7, _QWORD *a8)
{
  DWORD LastError; // esi
  HANDLE ProcessHeap; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rdi
  int v16; // eax
  unsigned int v17; // esi
  HANDLE EventW; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  const char *v21; // rbp

  LastError = 8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids, a2);
  *a8 = 0;
  ProcessHeap = GetProcessHeap();
  v14 = HeapAlloc(ProcessHeap, 8u, 0x48u);
  v15 = v14;
  if ( !v14 )
  {
    v21 = "FwAlloc";
LABEL_12:
    v17 = FwReportErrorAsWinError("FwRegNotifyCreate", v21, LastError);
    if ( (v17 & 0x80000000) == 0 )
      return v17;
LABEL_15:
    FwRegNotifyDestroy(v15);
    return v17;
  }
  *v14 = a1;
  v16 = FwStringCopy(a2);
  v17 = v16;
  if ( v16 < 0 )
  {
LABEL_14:
    FwReportReturnError("FwRegNotifyCreate", (unsigned int)v16);
    goto LABEL_15;
  }
  *((_DWORD *)v15 + 7) = a5;
  v15[4] = a6;
  v15[5] = a7;
  *((_DWORD *)v15 + 4) = a3;
  *((_DWORD *)v15 + 5) = a4;
  EventW = CreateEventW(0, 0, 0, 0);
  v15[7] = EventW;
  if ( !EventW )
  {
    v21 = "CreateEventW";
    goto LABEL_11;
  }
  v19 = RegisterWaitForSingleObjectEx(EventW, FwRegNotifyOnChange, v15, 0xFFFFFFFFLL, 128);
  v15[8] = v19;
  if ( !v19 )
  {
    v21 = "RegisterWaitForSingleObjectEx";
LABEL_11:
    LastError = GetLastError();
    goto LABEL_12;
  }
  v16 = FwExecuteInPersistentThread(v20, v15);
  v17 = v16;
  if ( v16 < 0 )
    goto LABEL_14;
  *a8 = v15;
  return v17;
}

```

## disassembly

```asm
0x1800053c0  push    rbx
0x1800053c2  push    rbp
0x1800053c3  push    rsi
0x1800053c4  push    rdi
0x1800053c5  push    r12
0x1800053c7  push    r14
0x1800053c9  push    r15
0x1800053cb  sub     rsp, 30h
0x1800053cf  mov     r15d, r9d
0x1800053d2  mov     r12d, r8d
0x1800053d5  mov     rbp, rdx
0x1800053d8  mov     r14, rcx
0x1800053db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800053e2  lea     rax, WPP_GLOBAL_Control
0x1800053e9  mov     esi, 8
0x1800053ee  cmp     rcx, rax
0x1800053f1  jz      short loc_1800053FD
0x1800053f3  test    [rcx+1Ch], sil
0x1800053f7  jnz     loc_18000551D
0x1800053fd  mov     rbx, [rsp+68h+arg_38]
0x180005405  mov     qword ptr [rbx], 0
0x18000540c  call    cs:__imp_GetProcessHeap
0x180005412  mov     r8d, 48h ; 'H'; dwBytes
0x180005418  mov     edx, esi; dwFlags
0x18000541a  mov     rcx, rax; hHeap
0x18000541d  call    cs:__imp_HeapAlloc
0x180005423  mov     rdi, rax
0x180005426  test    rax, rax
0x180005429  jz      loc_18000553A
0x18000542f  lea     rdx, [rax+8]
0x180005433  mov     [rax], r14
0x180005436  mov     rcx, rbp; Src
0x180005439  call    FwStringCopy
0x18000543e  mov     esi, eax
0x180005440  test    eax, eax
0x180005442  js      loc_180005505
0x180005448  mov     eax, [rsp+68h+arg_20]
0x18000544f  xor     r9d, r9d; lpName
0x180005452  mov     [rdi+1Ch], eax
0x180005455  xor     r8d, r8d; bInitialState
0x180005458  mov     rax, [rsp+68h+arg_28]
0x180005460  xor     edx, edx; bManualReset
0x180005462  mov     [rdi+20h], rax
0x180005466  xor     ecx, ecx; lpEventAttributes
0x180005468  mov     rax, [rsp+68h+arg_30]
0x180005470  mov     [rdi+28h], rax
0x180005474  mov     [rdi+10h], r12d
0x180005478  mov     [rdi+14h], r15d
0x18000547c  call    cs:__imp_CreateEventW
0x180005482  mov     [rdi+38h], rax
0x180005486  test    rax, rax
0x180005489  jz      loc_18000554A
0x18000548f  or      r9d, 0FFFFFFFFh
0x180005493  mov     [rsp+68h+var_48], 80h
0x18000549b  mov     r8, rdi
0x18000549e  lea     rdx, FwRegNotifyOnChange
0x1800054a5  mov     rcx, rax
0x1800054a8  call    cs:__imp_RegisterWaitForSingleObjectEx
0x1800054ae  mov     [rdi+40h], rax
0x1800054b2  test    rax, rax
0x1800054b5  jz      short loc_1800054CA
0x1800054b7  mov     rdx, rdi
0x1800054ba  call    FwExecuteInPersistentThread
0x1800054bf  mov     esi, eax
0x1800054c1  test    eax, eax
0x1800054c3  js      short loc_180005505
0x1800054c5  mov     [rbx], rdi
0x1800054c8  jmp     short loc_1800054F4
0x1800054ca  lea     rbp, aRegisterwaitfo; "RegisterWaitForSingleObjectEx"
0x1800054d1  lea     rbx, aFwregnotifycre_0; "FwRegNotifyCreate"
0x1800054d8  call    cs:__imp_GetLastError
0x1800054de  mov     esi, eax
0x1800054e0  mov     r8d, esi
0x1800054e3  mov     rdx, rbp
0x1800054e6  mov     rcx, rbx
0x1800054e9  call    FwReportErrorAsWinError
0x1800054ee  mov     esi, eax
0x1800054f0  test    eax, eax
0x1800054f2  js      short loc_180005513
0x1800054f4  mov     eax, esi
0x1800054f6  add     rsp, 30h
0x1800054fa  pop     r15
0x1800054fc  pop     r14
0x1800054fe  pop     r12
0x180005500  pop     rdi
0x180005501  pop     rsi
0x180005502  pop     rbp
0x180005503  pop     rbx
0x180005504  retn
0x180005505  mov     edx, eax
0x180005507  lea     rcx, aFwregnotifycre_0; "FwRegNotifyCreate"
0x18000550e  call    FwReportReturnError
0x180005513  mov     rcx, rdi
0x180005516  call    FwRegNotifyDestroy
0x18000551b  jmp     short loc_1800054F4
0x18000551d  mov     rcx, [rcx+10h]
0x180005521  lea     r8, WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids
0x180005528  mov     edx, 18h
0x18000552d  mov     r9, rbp
0x180005530  call    WPP_SF_S
0x180005535  jmp     loc_1800053FD
0x18000553a  lea     rbx, aFwregnotifycre_0; "FwRegNotifyCreate"
0x180005541  lea     rbp, aFwalloc_0; "FwAlloc"
0x180005548  jmp     short loc_1800054E0
0x18000554a  lea     rbp, aCreateeventw; "CreateEventW"
0x180005551  jmp     loc_1800054D1
```
