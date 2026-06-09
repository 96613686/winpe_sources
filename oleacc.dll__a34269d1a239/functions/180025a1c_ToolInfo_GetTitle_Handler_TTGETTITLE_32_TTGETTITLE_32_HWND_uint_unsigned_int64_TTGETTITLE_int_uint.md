# ToolInfo_GetTitle_Handler<TTGETTITLE_32>(TTGETTITLE_32 &,HWND__ *,uint,unsigned __int64,_TTGETTITLE *,int,uint)

- ea: `0x180025a1c`
- end: `0x180025b48`
- name: `??$ToolInfo_GetTitle_Handler@UTTGETTITLE_32@@@@YAJAEAUTTGETTITLE_32@@PEAUHWND__@@I_KPEAU_TTGETTITLE@@HI@Z`
- size: `300`
- prototype: `__int64 __usercall@<rax>(LPVOID lpBuffer@<rcx>, HWND hWnd@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800267c0`

## callees

- `0x180025a1c`
- `0x180025fd0`
- `0x18002604c`
- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180025af6`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180025af6`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180025ab8`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180025ab8`
- `USER32!SendMessageW` at `0x180025ad2`
- `USER32!SendMessageW` at `0x180025ad2`

## pseudocode

```c
__int64 __fastcall ToolInfo_GetTitle_Handler<TTGETTITLE_32>(
        unsigned int *lpBuffer,
        HWND hWnd,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  unsigned __int64 v7; // r9
  unsigned int v8; // ebx
  bool v9; // zf
  unsigned int v10; // eax
  void *v11; // rdx
  HANDLE v12; // rcx
  char *v13; // rdx
  void **v15; // [rsp+30h] [rbp-48h] BYREF
  LPVOID lpBaseAddress; // [rsp+38h] [rbp-40h]
  HANDLE hProcess; // [rsp+40h] [rbp-38h]
  int v18; // [rsp+48h] [rbp-30h]
  int v19; // [rsp+4Ch] [rbp-2Ch]

  v7 = 2LL * *(unsigned int *)(a5 + 8);
  if ( v7 > 0xFFFFFFFF )
    return 2147942934LL;
  lpBaseAddress = 0;
  v15 = &CXSendHelper::`vftable';
  if ( CXSendHelper::Alloc((CXSendHelper *)&v15, hWnd, 16, v7) )
  {
    v9 = v19 == 0;
    *lpBuffer = 16;
    lpBuffer[2] = *(_DWORD *)(a5 + 8);
    if ( v9 )
      v10 = 0;
    else
      v10 = (_DWORD)lpBaseAddress + v18;
    v11 = lpBaseAddress;
    v12 = hProcess;
    lpBuffer[3] = v10;
    if ( WriteProcessMemory(v12, v11, lpBuffer, 0x10u, 0)
      && SendMessageW(hWnd, 0x423u, 0, (LPARAM)lpBaseAddress)
      && ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x10u, 0)
      && (v13 = *(char **)(a5 + 16),
          *(_DWORD *)(a5 + 4) = lpBuffer[1],
          (unsigned int)CXSendHelper::ReadExtra((CXSendHelper *)&v15, v13, (void *)lpBuffer[3], 1)) )
    {
      v8 = 0;
    }
    else
    {
      v8 = -2147467259;
    }
  }
  else
  {
    v8 = -2147024882;
  }
  CXSendHelper::~CXSendHelper((CXSendHelper *)&v15);
  return v8;
}

```

## disassembly

```asm
0x180025a1c  push    rbx
0x180025a1e  push    rbp
0x180025a1f  push    rsi
0x180025a20  push    r15
0x180025a22  sub     rsp, 58h
0x180025a26  mov     rsi, [rsp+78h+arg_20]
0x180025a2e  mov     eax, 0FFFFFFFFh
0x180025a33  mov     rbp, rdx
0x180025a36  mov     rbx, rcx
0x180025a39  mov     r9d, [rsi+8]
0x180025a3d  add     r9, r9; unsigned int
0x180025a40  cmp     r9, rax
0x180025a43  ja      loc_180025B39
0x180025a49  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x180025a50  mov     [rsp+78h+lpBaseAddress], 0
0x180025a59  mov     r15d, 10h
0x180025a5f  mov     [rsp+78h+var_48], rax
0x180025a64  mov     r8d, r15d; unsigned int
0x180025a67  lea     rcx, [rsp+78h+var_48]; this
0x180025a6c  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x180025a71  test    eax, eax
0x180025a73  jnz     short loc_180025A7F
0x180025a75  mov     ebx, 8007000Eh
0x180025a7a  jmp     loc_180025B2B
0x180025a7f  cmp     [rsp+78h+var_2C], 0
0x180025a84  mov     [rbx], r15d
0x180025a87  mov     eax, [rsi+8]
0x180025a8a  mov     [rbx+8], eax
0x180025a8d  jnz     short loc_180025A93
0x180025a8f  xor     eax, eax
0x180025a91  jmp     short loc_180025A9C
0x180025a93  mov     eax, [rsp+78h+var_30]
0x180025a97  add     rax, [rsp+78h+lpBaseAddress]
0x180025a9c  mov     rdx, [rsp+78h+lpBaseAddress]; lpBaseAddress
0x180025aa1  mov     r9, r15; nSize
0x180025aa4  mov     rcx, [rsp+78h+hProcess]; hProcess
0x180025aa9  mov     r8, rbx; lpBuffer
0x180025aac  mov     [rbx+0Ch], eax
0x180025aaf  mov     [rsp+78h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180025ab8  call    cs:__imp_WriteProcessMemory
0x180025abe  test    eax, eax
0x180025ac0  jz      short loc_180025B26
0x180025ac2  mov     r9, [rsp+78h+lpBaseAddress]; lParam
0x180025ac7  xor     r8d, r8d; wParam
0x180025aca  mov     edx, 423h; Msg
0x180025acf  mov     rcx, rbp; hWnd
0x180025ad2  call    cs:__imp_SendMessageW
0x180025ad8  test    rax, rax
0x180025adb  jz      short loc_180025B26
0x180025add  mov     rdx, [rsp+78h+lpBaseAddress]; lpBaseAddress
0x180025ae2  mov     r9, r15; nSize
0x180025ae5  mov     rcx, [rsp+78h+hProcess]; hProcess
0x180025aea  mov     r8, rbx; lpBuffer
0x180025aed  mov     [rsp+78h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180025af6  call    cs:__imp_ReadProcessMemory
0x180025afc  test    eax, eax
0x180025afe  jz      short loc_180025B26
0x180025b00  mov     eax, [rbx+4]
0x180025b03  lea     rcx, [rsp+78h+var_48]; this
0x180025b08  mov     rdx, [rsi+10h]; void *
0x180025b0c  mov     r9d, 1; int
0x180025b12  mov     [rsi+4], eax
0x180025b15  mov     r8d, [rbx+0Ch]; void *
0x180025b19  call    ?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z; CXSendHelper::ReadExtra(void *,void *,int)
0x180025b1e  test    eax, eax
0x180025b20  jz      short loc_180025B26
0x180025b22  xor     ebx, ebx
0x180025b24  jmp     short loc_180025B2B
0x180025b26  mov     ebx, 80004005h
0x180025b2b  lea     rcx, [rsp+78h+var_48]; this
0x180025b30  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x180025b35  mov     eax, ebx
0x180025b37  jmp     short loc_180025B3E
0x180025b39  mov     eax, 80070216h
0x180025b3e  add     rsp, 58h
0x180025b42  pop     r15
0x180025b44  pop     rsi
0x180025b45  pop     rbp
0x180025b46  pop     rbx
0x180025b47  retn
```
