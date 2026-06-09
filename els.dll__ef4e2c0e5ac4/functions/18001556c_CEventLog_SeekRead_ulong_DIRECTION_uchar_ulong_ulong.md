# CEventLog::SeekRead(ulong,DIRECTION,uchar * *,ulong *,ulong *)

- ea: `0x18001556c`
- end: `0x18001567c`
- name: `?SeekRead@CEventLog@@QEAAJKW4DIRECTION@@PEAPEAEPEAK2@Z`
- size: `272`
- prototype: `__int64 __fastcall(__int64, DWORD, int, void **, DWORD *, DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800153ec`
- `0x180015afc`

## callees

- `0x180002bb8`
- `0x18001556c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001560c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015662`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015671`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001560c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015662`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015671`
- `ADVAPI32!ReadEventLogW` at `0x1800155f4`
- `ADVAPI32!ReadEventLogW` at `0x1800155f4`
- `KERNEL32!GetLastError` at `0x1800155fe`
- `KERNEL32!GetLastError` at `0x1800155fe`

## pseudocode

```c
__int64 __fastcall CEventLog::SeekRead(__int64 a1, DWORD a2, int a3, void **a4, DWORD *a5, DWORD *a6)
{
  DWORD *pnBytesRead; // r12
  signed int v7; // ebx
  DWORD *v8; // rsi
  void *v9; // rdi
  void *v14; // rax
  signed int LastError; // eax
  DWORD pnMinNumberOfBytesNeeded; // [rsp+A8h] [rbp+20h] BYREF

  pnBytesRead = a6;
  v7 = 0;
  v8 = a5;
  v9 = 0;
  for ( pnMinNumberOfBytesNeeded = 0; ; *v8 = pnMinNumberOfBytesNeeded )
  {
    if ( *a4 )
    {
      v14 = operator new[](*v8);
    }
    else
    {
      if ( v9 )
        goto LABEL_7;
      v14 = operator new[](0x200u);
      *v8 = 512;
    }
    v9 = v14;
    if ( !v14 )
      return (unsigned int)-2147024882;
LABEL_7:
    if ( ReadEventLogW(*(HANDLE *)(a1 + 8), a3 | 2, a2, v9, *v8, pnBytesRead, &pnMinNumberOfBytesNeeded) )
      goto LABEL_18;
    LastError = GetLastError();
    if ( LastError != 122 )
      break;
    operator delete[](v9);
    v9 = operator new[](pnMinNumberOfBytesNeeded);
    if ( !v9 )
    {
      *v8 = 0;
      return (unsigned int)-2147024882;
    }
  }
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  else
    v7 = LastError;
  operator delete[](v9);
  v9 = 0;
  if ( v7 >= 0 )
  {
LABEL_18:
    operator delete[](*a4);
    *a4 = v9;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001556c  mov     rax, rsp
0x18001556f  push    rbx
0x180015570  push    rbp
0x180015571  push    rsi
0x180015572  push    rdi
0x180015573  push    r12
0x180015575  push    r13
0x180015577  push    r14
0x180015579  push    r15
0x18001557b  sub     rsp, 48h
0x18001557f  mov     r12, [rsp+88h+arg_28]
0x180015587  xor     ebx, ebx
0x180015589  mov     rsi, [rsp+88h+arg_20]
0x180015591  xor     edi, edi
0x180015593  mov     [rax+20h], ebx
0x180015596  mov     r14, r9
0x180015599  mov     ebp, r8d
0x18001559c  mov     r15d, edx
0x18001559f  mov     r13, rcx
0x1800155a2  cmp     [r14], rbx
0x1800155a5  jnz     short loc_1800155BE
0x1800155a7  test    rdi, rdi
0x1800155aa  jnz     short loc_1800155CD
0x1800155ac  mov     ecx, 200h; unsigned __int64
0x1800155b1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800155b6  mov     dword ptr [rsi], 200h
0x1800155bc  jmp     short loc_1800155C5
0x1800155be  mov     ecx, [rsi]; unsigned __int64
0x1800155c0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800155c5  mov     rdi, rax
0x1800155c8  test    rax, rax
0x1800155cb  jz      short loc_180015636
0x1800155cd  mov     rcx, [r13+8]; hEventLog
0x1800155d1  lea     rax, [rsp+88h+arg_18]
0x1800155d9  mov     [rsp+88h+pnMinNumberOfBytesNeeded], rax; pnMinNumberOfBytesNeeded
0x1800155de  mov     edx, ebp
0x1800155e0  mov     eax, [rsi]
0x1800155e2  or      edx, 2; dwReadFlags
0x1800155e5  mov     [rsp+88h+pnBytesRead], r12; pnBytesRead
0x1800155ea  mov     r9, rdi; lpBuffer
0x1800155ed  mov     r8d, r15d; dwRecordOffset
0x1800155f0  mov     [rsp+88h+nNumberOfBytesToRead], eax; nNumberOfBytesToRead
0x1800155f4  call    cs:__imp_ReadEventLogW
0x1800155fa  test    eax, eax
0x1800155fc  jnz     short loc_18001566E
0x1800155fe  call    cs:__imp_GetLastError
0x180015604  cmp     eax, 7Ah ; 'z'
0x180015607  jnz     short loc_18001564E
0x180015609  mov     rcx, rdi
0x18001560c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015612  mov     ecx, [rsp+88h+arg_18]; unsigned __int64
0x180015619  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001561e  mov     rdi, rax
0x180015621  test    rax, rax
0x180015624  jz      short loc_180015634
0x180015626  mov     eax, [rsp+88h+arg_18]
0x18001562d  mov     [rsi], eax
0x18001562f  jmp     loc_1800155A2
0x180015634  mov     [rsi], ebx
0x180015636  mov     ebx, 8007000Eh
0x18001563b  mov     eax, ebx
0x18001563d  add     rsp, 48h
0x180015641  pop     r15
0x180015643  pop     r14
0x180015645  pop     r13
0x180015647  pop     r12
0x180015649  pop     rdi
0x18001564a  pop     rsi
0x18001564b  pop     rbp
0x18001564c  pop     rbx
0x18001564d  retn
0x18001564e  test    eax, eax
0x180015650  jg      short loc_180015656
0x180015652  mov     ebx, eax
0x180015654  jmp     short loc_18001565F
0x180015656  movzx   ebx, ax
0x180015659  or      ebx, 80070000h
0x18001565f  mov     rcx, rdi
0x180015662  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015668  xor     edi, edi
0x18001566a  test    ebx, ebx
0x18001566c  js      short loc_18001563B
0x18001566e  mov     rcx, [r14]
0x180015671  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015677  mov     [r14], rdi
0x18001567a  jmp     short loc_18001563B
```
