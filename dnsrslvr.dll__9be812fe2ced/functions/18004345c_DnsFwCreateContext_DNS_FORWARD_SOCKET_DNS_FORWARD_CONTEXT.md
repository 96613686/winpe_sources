# DnsFwCreateContext(_DNS_FORWARD_SOCKET *,_DNS_FORWARD_CONTEXT * *)

- ea: `0x18004345c`
- end: `0x180043686`
- name: `?DnsFwCreateContext@@YAKPEAU_DNS_FORWARD_SOCKET@@PEAPEAU_DNS_FORWARD_CONTEXT@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(struct _DNS_FORWARD_SOCKET *, struct _DNS_FORWARD_CONTEXT **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800445c8`
- `0x1800447bc`

## callees

- `0x180008b00`
- `0x1800432fc`
- `0x18004345c`
- `0x180044174`
- `0x180086b1c`
- `0x180086f78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004358e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800435d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004358e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800435d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800434da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004353b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800434da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004353b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800434ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004354c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800434ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004354c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18004357c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800435c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18004357c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800435c6`

## pseudocode

```c
__int64 __fastcall DnsFwCreateContext(struct _DNS_FORWARD_SOCKET *a1, struct _DNS_FORWARD_CONTEXT **a2)
{
  signed int v4; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  _QWORD *v8; // rax
  HANDLE v9; // rax
  LPVOID v10; // rax
  HANDLE EventA; // rax
  signed int LastError; // eax
  HANDLE v13; // rax
  signed int v14; // eax
  __int64 v15; // rcx
  int Socket; // eax
  unsigned int v17; // eax

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qq(1035, 20, (unsigned int)WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, (_DWORD)a1, (__int64)a2);
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    v4 = -2147024809;
    goto LABEL_31;
  }
  if ( !a2 )
  {
    v4 = -2147024809;
    goto LABEL_31;
  }
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 8u, 0x200u);
  v7 = v6;
  if ( !v6 )
  {
    v4 = -2147024882;
    goto LABEL_31;
  }
  v6[1] = v6;
  *v6 = v6;
  v8 = v6 + 2;
  v8[1] = v8;
  *v8 = v8;
  v7[4] = 1;
  v7[7] = a1;
  _InterlockedIncrement((volatile signed __int32 *)a1 + 10);
  *((_DWORD *)v7 + 95) = 65537;
  v9 = GetProcessHeap();
  v10 = HeapAlloc(v9, 8u, 0x10001u);
  v7[46] = v10;
  if ( !v10 )
  {
    v4 = -2147024882;
LABEL_29:
    DnsFwDerefContext((struct _DNS_FORWARD_CONTEXT *)v7);
    goto LABEL_31;
  }
  EventA = CreateEventA(0, 1, 0, 0);
  v7[58] = EventA;
  if ( !EventA )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147418113;
    goto LABEL_29;
  }
  v13 = CreateEventA(0, 1, 0, 0);
  v7[59] = v13;
  if ( !v13 )
  {
    v14 = GetLastError();
    v4 = v14;
    if ( v14 > 0 )
      v4 = (unsigned __int16)v14 | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147418113;
    goto LABEL_29;
  }
  v15 = v7[7];
  v4 = 0;
  if ( *(_DWORD *)(v15 + 64) == 6 )
  {
    Socket = DnsFwCreateSocket(*(_WORD *)(v15 + 56), 6u, 0, (struct _DNS_FORWARD_SOCKET **)v7 + 8);
    v4 = Socket;
    if ( Socket > 0 )
      v4 = (unsigned __int16)Socket | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_29;
  }
  *a2 = (struct _DNS_FORWARD_CONTEXT *)v7;
LABEL_31:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v17 = WX_WIN32_FROM_HR((unsigned int)v4);
    WPP_SF_d(1035, 21, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, v17);
  }
  return WX_WIN32_FROM_HR((unsigned int)v4);
}

```

## disassembly

```asm
0x18004345c  mov     [rsp+arg_8], rbx
0x180043461  mov     [rsp+arg_10], rsi
0x180043466  push    rdi
0x180043467  sub     rsp, 30h
0x18004346b  mov     rsi, rdx
0x18004346e  mov     [rsp+38h+arg_4], 0
0x180043476  mov     rbx, rcx
0x180043479  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180043480  jz      short loc_1800434A0
0x180043482  mov     edx, 14h
0x180043487  mov     [rsp+38h+var_18], rsi
0x18004348c  mov     ecx, 40Bh
0x180043491  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x180043498  mov     r9, rbx
0x18004349b  call    WPP_SF_qq
0x1800434a0  test    rsi, rsi
0x1800434a3  jz      short loc_1800434AC
0x1800434a5  mov     qword ptr [rsi], 0
0x1800434ac  test    rbx, rbx
0x1800434af  jnz     short loc_1800434C3
0x1800434b1  mov     ebx, 80070057h
0x1800434b6  mov     [rsp+38h+arg_4], 1C7h
0x1800434be  jmp     loc_180043647
0x1800434c3  test    rsi, rsi
0x1800434c6  jnz     short loc_1800434DA
0x1800434c8  mov     ebx, 80070057h
0x1800434cd  mov     [rsp+38h+arg_4], 1C8h
0x1800434d5  jmp     loc_180043647
0x1800434da  call    cs:__imp_GetProcessHeap
0x1800434e0  mov     edx, 8; dwFlags
0x1800434e5  mov     r8d, 200h; dwBytes
0x1800434eb  mov     rcx, rax; hHeap
0x1800434ee  call    cs:__imp_HeapAlloc
0x1800434f4  mov     rdi, rax
0x1800434f7  test    rax, rax
0x1800434fa  jnz     short loc_18004350E
0x1800434fc  mov     ebx, 8007000Eh
0x180043501  mov     [rsp+38h+arg_4], 1CDh
0x180043509  jmp     loc_180043647
0x18004350e  mov     [rax+8], rdi
0x180043512  mov     [rax], rdi
0x180043515  add     rax, 10h
0x180043519  mov     [rax+8], rax
0x18004351d  mov     [rax], rax
0x180043520  mov     qword ptr [rdi+20h], 1
0x180043528  mov     [rdi+38h], rbx
0x18004352c  lock inc dword ptr [rbx+28h]
0x180043530  mov     ebx, 10001h
0x180043535  mov     [rdi+17Ch], ebx
0x18004353b  call    cs:__imp_GetProcessHeap
0x180043541  mov     r8d, ebx; dwBytes
0x180043544  mov     edx, 8; dwFlags
0x180043549  mov     rcx, rax; hHeap
0x18004354c  call    cs:__imp_HeapAlloc
0x180043552  mov     [rdi+170h], rax
0x180043559  test    rax, rax
0x18004355c  jnz     short loc_180043570
0x18004355e  mov     ebx, 8007000Eh
0x180043563  mov     [rsp+38h+arg_4], 1DBh
0x18004356b  jmp     loc_18004363A
0x180043570  xor     r9d, r9d; lpName
0x180043573  xor     r8d, r8d; bInitialState
0x180043576  xor     ecx, ecx; lpEventAttributes
0x180043578  lea     edx, [r9+1]; bManualReset
0x18004357c  call    cs:__imp_CreateEventA
0x180043582  mov     [rdi+1D0h], rax
0x180043589  test    rax, rax
0x18004358c  jnz     short loc_1800435BA
0x18004358e  call    cs:__imp_GetLastError
0x180043594  mov     ebx, eax
0x180043596  test    eax, eax
0x180043598  jle     short loc_1800435A3
0x18004359a  movzx   ebx, ax
0x18004359d  or      ebx, 80070000h
0x1800435a3  test    ebx, ebx
0x1800435a5  mov     [rsp+38h+arg_4], 1DEh
0x1800435ad  mov     eax, 8000FFFFh
0x1800435b2  cmovns  ebx, eax
0x1800435b5  jmp     loc_18004363A
0x1800435ba  xor     r9d, r9d; lpName
0x1800435bd  xor     r8d, r8d; bInitialState
0x1800435c0  xor     ecx, ecx; lpEventAttributes
0x1800435c2  lea     edx, [r9+1]; bManualReset
0x1800435c6  call    cs:__imp_CreateEventA
0x1800435cc  mov     [rdi+1D8h], rax
0x1800435d3  test    rax, rax
0x1800435d6  jnz     short loc_180043601
0x1800435d8  call    cs:__imp_GetLastError
0x1800435de  mov     ebx, eax
0x1800435e0  test    eax, eax
0x1800435e2  jle     short loc_1800435ED
0x1800435e4  movzx   ebx, ax
0x1800435e7  or      ebx, 80070000h
0x1800435ed  test    ebx, ebx
0x1800435ef  mov     [rsp+38h+arg_4], 1E1h
0x1800435f7  mov     eax, 8000FFFFh
0x1800435fc  cmovns  ebx, eax
0x1800435ff  jmp     short loc_18004363A
0x180043601  mov     rcx, [rdi+38h]
0x180043605  xor     ebx, ebx
0x180043607  lea     edx, [rbx+6]; unsigned int
0x18004360a  cmp     [rcx+40h], edx
0x18004360d  jnz     short loc_180043644
0x18004360f  movzx   ecx, word ptr [rcx+38h]; unsigned __int16
0x180043613  lea     r9, [rdi+40h]; struct _DNS_FORWARD_SOCKET **
0x180043617  xor     r8d, r8d; int
0x18004361a  call    ?DnsFwCreateSocket@@YAKGKHPEAPEAU_DNS_FORWARD_SOCKET@@@Z; DnsFwCreateSocket(ushort,ulong,int,_DNS_FORWARD_SOCKET * *)
0x18004361f  mov     ebx, eax
0x180043621  test    eax, eax
0x180043623  jle     short loc_18004362E
0x180043625  movzx   ebx, ax
0x180043628  or      ebx, 80070000h
0x18004362e  test    ebx, ebx
0x180043630  jns     short loc_180043644
0x180043632  mov     [rsp+38h+arg_4], 1E8h
0x18004363a  mov     rcx, rdi; lpMem
0x18004363d  call    ?DnsFwDerefContext@@YAXPEAU_DNS_FORWARD_CONTEXT@@@Z; DnsFwDerefContext(_DNS_FORWARD_CONTEXT *)
0x180043642  jmp     short loc_180043647
0x180043644  mov     [rsi], rdi
0x180043647  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004364e  jz      short loc_180043670
0x180043650  mov     ecx, ebx
0x180043652  call    WX_WIN32_FROM_HR
0x180043657  mov     r9d, eax
0x18004365a  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x180043661  mov     edx, 15h
0x180043666  mov     ecx, 40Bh
0x18004366b  call    WPP_SF_d
0x180043670  mov     ecx, ebx
0x180043672  mov     rbx, [rsp+38h+arg_8]
0x180043677  mov     rsi, [rsp+38h+arg_10]
0x18004367c  add     rsp, 30h
0x180043680  pop     rdi
0x180043681  jmp     WX_WIN32_FROM_HR
```
