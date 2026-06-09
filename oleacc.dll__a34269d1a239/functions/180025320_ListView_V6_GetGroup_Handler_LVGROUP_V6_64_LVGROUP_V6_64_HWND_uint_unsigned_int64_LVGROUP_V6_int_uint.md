# ListView_V6_GetGroup_Handler<LVGROUP_V6_64>(LVGROUP_V6_64 &,HWND__ *,uint,unsigned __int64,LVGROUP_V6 *,int,uint)

- ea: `0x180025320`
- end: `0x180025463`
- name: `??$ListView_V6_GetGroup_Handler@ULVGROUP_V6_64@@@@YAJAEAULVGROUP_V6_64@@PEAUHWND__@@I_KPEAULVGROUP_V6@@HI@Z`
- size: `323`
- prototype: `__int64 __fastcall(LPVOID lpBuffer, HWND, UINT Msg, WPARAM wParam, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800263e8`

## callees

- `0x180025320`
- `0x180025fd0`
- `0x18002604c`
- `0x180026090`
- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002541c`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002541c`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800253e3`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800253e3`
- `USER32!SendMessageW` at `0x1800253fa`
- `USER32!SendMessageW` at `0x1800253fa`

## pseudocode

```c
__int64 __fastcall ListView_V6_GetGroup_Handler<LVGROUP_V6_64>(
        LPVOID lpBuffer,
        HWND a2,
        UINT Msg,
        WPARAM wParam,
        __int64 a5,
        unsigned int a6)
{
  unsigned int v7; // r9d
  __int64 result; // rax
  unsigned int v12; // ebx
  bool v13; // zf
  char *v14; // rax
  void *v15; // rdx
  HANDLE v16; // rcx
  void **v17; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpBaseAddress; // [rsp+38h] [rbp-18h]
  HANDLE hProcess; // [rsp+40h] [rbp-10h]
  unsigned int v20; // [rsp+48h] [rbp-8h]
  int v21; // [rsp+4Ch] [rbp-4h]

  v7 = 0;
  a6 = 0;
  if ( (*(_BYTE *)(a5 + 4) & 1) != 0 )
  {
    result = PlusOneTimesTchar(*(_DWORD *)(a5 + 16), &a6);
    if ( (int)result < 0 )
      return result;
    v7 = a6;
  }
  lpBaseAddress = 0;
  v17 = &CXSendHelper::`vftable';
  if ( CXSendHelper::Alloc((CXSendHelper *)&v17, a2, 56, v7) )
  {
    v13 = v21 == 0;
    *(_DWORD *)lpBuffer = *(_DWORD *)a5;
    *((_DWORD *)lpBuffer + 1) = *(_DWORD *)(a5 + 4);
    if ( v13 )
      v14 = 0;
    else
      v14 = (char *)lpBaseAddress + v20;
    v15 = lpBaseAddress;
    v16 = hProcess;
    *((_QWORD *)lpBuffer + 1) = v14;
    *((_DWORD *)lpBuffer + 4) = *(_DWORD *)(a5 + 16);
    *((_DWORD *)lpBuffer + 9) = *(_DWORD *)(a5 + 36);
    if ( WriteProcessMemory(v16, v15, lpBuffer, 0x38u, 0)
      && SendMessageW(a2, Msg, wParam, (LPARAM)lpBaseAddress)
      && ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x38u, 0)
      && (unsigned int)CXSendHelper::ReadExtra((CXSendHelper *)&v17, *(char **)(a5 + 8), *((void **)lpBuffer + 1), 1) )
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
0x180025320  push    rbp
0x180025322  push    rbx
0x180025323  push    rdi
0x180025324  push    r12
0x180025326  push    r13
0x180025328  push    r14
0x18002532a  push    r15
0x18002532c  mov     rbp, rsp
0x18002532f  sub     rsp, 50h
0x180025333  mov     rdi, [rbp+arg_20]
0x180025337  mov     r12, r9
0x18002533a  xor     r9d, r9d
0x18002533d  mov     r13d, r8d
0x180025340  mov     r15, rdx
0x180025343  mov     [rbp+arg_28], r9d
0x180025347  mov     rbx, rcx
0x18002534a  test    byte ptr [rdi+4], 1
0x18002534e  jz      short loc_180025368
0x180025350  mov     ecx, [rdi+10h]; unsigned int
0x180025353  lea     rdx, [rbp+arg_28]; unsigned int *
0x180025357  call    ?PlusOneTimesTchar@@YAJKPEAK@Z; PlusOneTimesTchar(ulong,ulong *)
0x18002535c  test    eax, eax
0x18002535e  js      loc_180025453
0x180025364  mov     r9d, [rbp+arg_28]; unsigned int
0x180025368  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x18002536f  mov     [rbp+lpBaseAddress], 0
0x180025377  mov     r8d, 38h ; '8'; unsigned int
0x18002537d  mov     [rbp+var_20], rax
0x180025381  mov     rdx, r15; HWND
0x180025384  lea     rcx, [rbp+var_20]; this
0x180025388  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x18002538d  test    eax, eax
0x18002538f  jnz     short loc_18002539B
0x180025391  mov     ebx, 8007000Eh
0x180025396  jmp     loc_180025448
0x18002539b  cmp     [rbp+var_4], 0
0x18002539f  mov     eax, [rdi]
0x1800253a1  mov     [rbx], eax
0x1800253a3  mov     eax, [rdi+4]
0x1800253a6  mov     [rbx+4], eax
0x1800253a9  jnz     short loc_1800253AF
0x1800253ab  xor     eax, eax
0x1800253ad  jmp     short loc_1800253B6
0x1800253af  mov     eax, [rbp+var_8]
0x1800253b2  add     rax, [rbp+lpBaseAddress]
0x1800253b6  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x1800253ba  mov     r14d, 38h ; '8'
0x1800253c0  mov     rcx, [rbp+hProcess]; hProcess
0x1800253c4  mov     r9d, r14d; nSize
0x1800253c7  mov     [rbx+8], rax
0x1800253cb  mov     r8, rbx; lpBuffer
0x1800253ce  mov     eax, [rdi+10h]
0x1800253d1  mov     [rbx+10h], eax
0x1800253d4  mov     eax, [rdi+24h]
0x1800253d7  mov     [rbx+24h], eax
0x1800253da  mov     [rsp+50h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x1800253e3  call    cs:__imp_WriteProcessMemory
0x1800253e9  test    eax, eax
0x1800253eb  jz      short loc_180025443
0x1800253ed  mov     r9, [rbp+lpBaseAddress]; lParam
0x1800253f1  mov     r8, r12; wParam
0x1800253f4  mov     edx, r13d; Msg
0x1800253f7  mov     rcx, r15; hWnd
0x1800253fa  call    cs:__imp_SendMessageW
0x180025400  test    rax, rax
0x180025403  jz      short loc_180025443
0x180025405  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180025409  mov     r9d, r14d; nSize
0x18002540c  mov     rcx, [rbp+hProcess]; hProcess
0x180025410  mov     r8, rbx; lpBuffer
0x180025413  mov     [rsp+50h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x18002541c  call    cs:__imp_ReadProcessMemory
0x180025422  test    eax, eax
0x180025424  jz      short loc_180025443
0x180025426  mov     r8, [rbx+8]; void *
0x18002542a  lea     r9d, [r14-37h]; int
0x18002542e  mov     rdx, [rdi+8]; void *
0x180025432  lea     rcx, [rbp+var_20]; this
0x180025436  call    ?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z; CXSendHelper::ReadExtra(void *,void *,int)
0x18002543b  test    eax, eax
0x18002543d  jz      short loc_180025443
0x18002543f  xor     ebx, ebx
0x180025441  jmp     short loc_180025448
0x180025443  mov     ebx, 80004005h
0x180025448  lea     rcx, [rbp+var_20]; this
0x18002544c  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x180025451  mov     eax, ebx
0x180025453  add     rsp, 50h
0x180025457  pop     r15
0x180025459  pop     r14
0x18002545b  pop     r13
0x18002545d  pop     r12
0x18002545f  pop     rdi
0x180025460  pop     rbx
0x180025461  pop     rbp
0x180025462  retn
```
