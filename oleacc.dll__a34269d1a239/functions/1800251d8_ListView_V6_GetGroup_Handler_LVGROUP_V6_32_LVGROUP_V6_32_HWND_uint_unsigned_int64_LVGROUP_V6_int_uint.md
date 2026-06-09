# ListView_V6_GetGroup_Handler<LVGROUP_V6_32>(LVGROUP_V6_32 &,HWND__ *,uint,unsigned __int64,LVGROUP_V6 *,int,uint)

- ea: `0x1800251d8`
- end: `0x18002531a`
- name: `??$ListView_V6_GetGroup_Handler@ULVGROUP_V6_32@@@@YAJAEAULVGROUP_V6_32@@PEAUHWND__@@I_KPEAULVGROUP_V6@@HI@Z`
- size: `322`
- prototype: `__int64 __fastcall(LPVOID lpBuffer, HWND, UINT Msg, WPARAM wParam, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800263e8`

## callees

- `0x1800251d8`
- `0x180025fd0`
- `0x18002604c`
- `0x180026090`
- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800252d3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800252d3`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002529a`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002529a`
- `USER32!SendMessageW` at `0x1800252b1`
- `USER32!SendMessageW` at `0x1800252b1`

## pseudocode

```c
__int64 __fastcall ListView_V6_GetGroup_Handler<LVGROUP_V6_32>(
        unsigned int *lpBuffer,
        HWND a2,
        UINT Msg,
        WPARAM wParam,
        char **a5,
        unsigned int a6)
{
  unsigned int v7; // r9d
  __int64 result; // rax
  unsigned int v12; // ebx
  bool v13; // zf
  unsigned int v14; // eax
  void *v15; // rdx
  HANDLE v16; // rcx
  void **v17; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpBaseAddress; // [rsp+38h] [rbp-18h]
  HANDLE hProcess; // [rsp+40h] [rbp-10h]
  int v20; // [rsp+48h] [rbp-8h]
  int v21; // [rsp+4Ch] [rbp-4h]

  v7 = 0;
  a6 = 0;
  if ( (*((_BYTE *)a5 + 4) & 1) != 0 )
  {
    result = PlusOneTimesTchar(*((_DWORD *)a5 + 4), &a6);
    if ( (int)result < 0 )
      return result;
    v7 = a6;
  }
  lpBaseAddress = 0;
  v17 = &CXSendHelper::`vftable';
  if ( CXSendHelper::Alloc((CXSendHelper *)&v17, a2, 40, v7) )
  {
    v13 = v21 == 0;
    *lpBuffer = *(_DWORD *)a5;
    lpBuffer[1] = *((_DWORD *)a5 + 1);
    if ( v13 )
      v14 = 0;
    else
      v14 = (_DWORD)lpBaseAddress + v20;
    v15 = lpBaseAddress;
    v16 = hProcess;
    lpBuffer[2] = v14;
    lpBuffer[3] = *((_DWORD *)a5 + 4);
    lpBuffer[6] = *((_DWORD *)a5 + 9);
    if ( WriteProcessMemory(v16, v15, lpBuffer, 0x28u, 0)
      && SendMessageW(a2, Msg, wParam, (LPARAM)lpBaseAddress)
      && ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x28u, 0)
      && (unsigned int)CXSendHelper::ReadExtra((CXSendHelper *)&v17, a5[1], (void *)lpBuffer[2], 1) )
    {
      v12 = 0;
    }
    else
    {
      v12 = -2147467259;
    }
  }
  else
  {
    v12 = -2147024882;
  }
  CXSendHelper::~CXSendHelper((CXSendHelper *)&v17);
  return v12;
}

```

## disassembly

```asm
0x1800251d8  push    rbp
0x1800251da  push    rbx
0x1800251db  push    rdi
0x1800251dc  push    r12
0x1800251de  push    r13
0x1800251e0  push    r14
0x1800251e2  push    r15
0x1800251e4  mov     rbp, rsp
0x1800251e7  sub     rsp, 50h
0x1800251eb  mov     rdi, [rbp+arg_20]
0x1800251ef  mov     r12, r9
0x1800251f2  xor     r9d, r9d
0x1800251f5  mov     r13d, r8d
0x1800251f8  mov     r15, rdx
0x1800251fb  mov     [rbp+arg_28], r9d
0x1800251ff  mov     rbx, rcx
0x180025202  test    byte ptr [rdi+4], 1
0x180025206  jz      short loc_180025220
0x180025208  mov     ecx, [rdi+10h]; unsigned int
0x18002520b  lea     rdx, [rbp+arg_28]; unsigned int *
0x18002520f  call    ?PlusOneTimesTchar@@YAJKPEAK@Z; PlusOneTimesTchar(ulong,ulong *)
0x180025214  test    eax, eax
0x180025216  js      loc_18002530A
0x18002521c  mov     r9d, [rbp+arg_28]; unsigned int
0x180025220  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x180025227  mov     [rbp+lpBaseAddress], 0
0x18002522f  mov     r8d, 28h ; '('; unsigned int
0x180025235  mov     [rbp+var_20], rax
0x180025239  mov     rdx, r15; HWND
0x18002523c  lea     rcx, [rbp+var_20]; this
0x180025240  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x180025245  test    eax, eax
0x180025247  jnz     short loc_180025253
0x180025249  mov     ebx, 8007000Eh
0x18002524e  jmp     loc_1800252FF
0x180025253  cmp     [rbp+var_4], 0
0x180025257  mov     eax, [rdi]
0x180025259  mov     [rbx], eax
0x18002525b  mov     eax, [rdi+4]
0x18002525e  mov     [rbx+4], eax
0x180025261  jnz     short loc_180025267
0x180025263  xor     eax, eax
0x180025265  jmp     short loc_18002526E
0x180025267  mov     eax, [rbp+var_8]
0x18002526a  add     rax, [rbp+lpBaseAddress]
0x18002526e  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180025272  mov     r14d, 28h ; '('
0x180025278  mov     rcx, [rbp+hProcess]; hProcess
0x18002527c  mov     r9d, r14d; nSize
0x18002527f  mov     [rbx+8], eax
0x180025282  mov     r8, rbx; lpBuffer
0x180025285  mov     eax, [rdi+10h]
0x180025288  mov     [rbx+0Ch], eax
0x18002528b  mov     eax, [rdi+24h]
0x18002528e  mov     [rbx+18h], eax
0x180025291  mov     [rsp+50h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x18002529a  call    cs:__imp_WriteProcessMemory
0x1800252a0  test    eax, eax
0x1800252a2  jz      short loc_1800252FA
0x1800252a4  mov     r9, [rbp+lpBaseAddress]; lParam
0x1800252a8  mov     r8, r12; wParam
0x1800252ab  mov     edx, r13d; Msg
0x1800252ae  mov     rcx, r15; hWnd
0x1800252b1  call    cs:__imp_SendMessageW
0x1800252b7  test    rax, rax
0x1800252ba  jz      short loc_1800252FA
0x1800252bc  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x1800252c0  mov     r9d, r14d; nSize
0x1800252c3  mov     rcx, [rbp+hProcess]; hProcess
0x1800252c7  mov     r8, rbx; lpBuffer
0x1800252ca  mov     [rsp+50h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x1800252d3  call    cs:__imp_ReadProcessMemory
0x1800252d9  test    eax, eax
0x1800252db  jz      short loc_1800252FA
0x1800252dd  mov     r8d, [rbx+8]; void *
0x1800252e1  lea     r9d, [r14-27h]; int
0x1800252e5  mov     rdx, [rdi+8]; void *
0x1800252e9  lea     rcx, [rbp+var_20]; this
0x1800252ed  call    ?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z; CXSendHelper::ReadExtra(void *,void *,int)
0x1800252f2  test    eax, eax
0x1800252f4  jz      short loc_1800252FA
0x1800252f6  xor     ebx, ebx
0x1800252f8  jmp     short loc_1800252FF
0x1800252fa  mov     ebx, 80004005h
0x1800252ff  lea     rcx, [rbp+var_20]; this
0x180025303  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x180025308  mov     eax, ebx
0x18002530a  add     rsp, 50h
0x18002530e  pop     r15
0x180025310  pop     r14
0x180025312  pop     r13
0x180025314  pop     r12
0x180025316  pop     rdi
0x180025317  pop     rbx
0x180025318  pop     rbp
0x180025319  retn
```
