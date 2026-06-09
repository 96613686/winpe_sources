# ToolInfo_GetTitle_Handler<TTGETTITLE_64>(TTGETTITLE_64 &,HWND__ *,uint,unsigned __int64,_TTGETTITLE *,int,uint)

- ea: `0x180025b50`
- end: `0x180025c7d`
- name: `??$ToolInfo_GetTitle_Handler@UTTGETTITLE_64@@@@YAJAEAUTTGETTITLE_64@@PEAUHWND__@@I_KPEAU_TTGETTITLE@@HI@Z`
- size: `301`
- prototype: `__int64 __usercall@<rax>(LPVOID lpBuffer@<rcx>, HWND hWnd@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800267c0`

## callees

- `0x180025b50`
- `0x180025fd0`
- `0x18002604c`
- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180025c2b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180025c2b`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180025bed`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180025bed`
- `USER32!SendMessageW` at `0x180025c07`
- `USER32!SendMessageW` at `0x180025c07`

## pseudocode

```c
__int64 __fastcall ToolInfo_GetTitle_Handler<TTGETTITLE_64>(
        LPVOID lpBuffer,
        HWND hWnd,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  unsigned __int64 v7; // r9
  unsigned int v8; // ebx
  bool v9; // zf
  char *v10; // rax
  void *v11; // rdx
  HANDLE v12; // rcx
  char *v13; // rdx
  void **v15; // [rsp+30h] [rbp-48h] BYREF
  LPVOID lpBaseAddress; // [rsp+38h] [rbp-40h]
  HANDLE hProcess; // [rsp+40h] [rbp-38h]
  unsigned int v18; // [rsp+48h] [rbp-30h]
  int v19; // [rsp+4Ch] [rbp-2Ch]

  v7 = 2LL * *(unsigned int *)(a5 + 8);
  if ( v7 > 0xFFFFFFFF )
    return 2147942934LL;
  lpBaseAddress = 0;
  v15 = &CXSendHelper::`vftable';
  if ( CXSendHelper::Alloc((CXSendHelper *)&v15, hWnd, 24, v7) )
  {
    v9 = v19 == 0;
    *(_DWORD *)lpBuffer = 24;
    *((_DWORD *)lpBuffer + 2) = *(_DWORD *)(a5 + 8);
    if ( v9 )
      v10 = 0;
    else
      v10 = (char *)lpBaseAddress + v18;
    v11 = lpBaseAddress;
    v12 = hProcess;
    *((_QWORD *)lpBuffer + 2) = v10;
    if ( WriteProcessMemory(v12, v11, lpBuffer, 0x18u, 0)
      && SendMessageW(hWnd, 0x423u, 0, (LPARAM)lpBaseAddress)
      && ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x18u, 0)
      && (v13 = *(char **)(a5 + 16),
          *(_DWORD *)(a5 + 4) = *((_DWORD *)lpBuffer + 1),
          (unsigned int)CXSendHelper::ReadExtra((CXSendHelper *)&v15, v13, *((void **)lpBuffer + 2), 1)) )
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
0x180025b50  push    rbx
0x180025b52  push    rbp
0x180025b53  push    rsi
0x180025b54  push    r15
0x180025b56  sub     rsp, 58h
0x180025b5a  mov     rsi, [rsp+78h+arg_20]
0x180025b62  mov     eax, 0FFFFFFFFh
0x180025b67  mov     rbp, rdx
0x180025b6a  mov     rbx, rcx
0x180025b6d  mov     r9d, [rsi+8]
0x180025b71  add     r9, r9; unsigned int
0x180025b74  cmp     r9, rax
0x180025b77  ja      loc_180025C6E
0x180025b7d  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x180025b84  mov     [rsp+78h+lpBaseAddress], 0
0x180025b8d  mov     r15d, 18h
0x180025b93  mov     [rsp+78h+var_48], rax
0x180025b98  mov     r8d, r15d; unsigned int
0x180025b9b  lea     rcx, [rsp+78h+var_48]; this
0x180025ba0  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x180025ba5  test    eax, eax
0x180025ba7  jnz     short loc_180025BB3
0x180025ba9  mov     ebx, 8007000Eh
0x180025bae  jmp     loc_180025C60
0x180025bb3  cmp     [rsp+78h+var_2C], 0
0x180025bb8  mov     [rbx], r15d
0x180025bbb  mov     eax, [rsi+8]
0x180025bbe  mov     [rbx+8], eax
0x180025bc1  jnz     short loc_180025BC7
0x180025bc3  xor     eax, eax
0x180025bc5  jmp     short loc_180025BD0
0x180025bc7  mov     eax, [rsp+78h+var_30]
0x180025bcb  add     rax, [rsp+78h+lpBaseAddress]
0x180025bd0  mov     rdx, [rsp+78h+lpBaseAddress]; lpBaseAddress
0x180025bd5  mov     r9, r15; nSize
0x180025bd8  mov     rcx, [rsp+78h+hProcess]; hProcess
0x180025bdd  mov     r8, rbx; lpBuffer
0x180025be0  mov     [rbx+10h], rax
0x180025be4  mov     [rsp+78h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180025bed  call    cs:__imp_WriteProcessMemory
0x180025bf3  test    eax, eax
0x180025bf5  jz      short loc_180025C5B
0x180025bf7  mov     r9, [rsp+78h+lpBaseAddress]; lParam
0x180025bfc  xor     r8d, r8d; wParam
0x180025bff  mov     edx, 423h; Msg
0x180025c04  mov     rcx, rbp; hWnd
0x180025c07  call    cs:__imp_SendMessageW
0x180025c0d  test    rax, rax
0x180025c10  jz      short loc_180025C5B
0x180025c12  mov     rdx, [rsp+78h+lpBaseAddress]; lpBaseAddress
0x180025c17  mov     r9, r15; nSize
0x180025c1a  mov     rcx, [rsp+78h+hProcess]; hProcess
0x180025c1f  mov     r8, rbx; lpBuffer
0x180025c22  mov     [rsp+78h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180025c2b  call    cs:__imp_ReadProcessMemory
0x180025c31  test    eax, eax
0x180025c33  jz      short loc_180025C5B
0x180025c35  mov     eax, [rbx+4]
0x180025c38  lea     rcx, [rsp+78h+var_48]; this
0x180025c3d  mov     rdx, [rsi+10h]; void *
0x180025c41  mov     r9d, 1; int
0x180025c47  mov     [rsi+4], eax
0x180025c4a  mov     r8, [rbx+10h]; void *
0x180025c4e  call    ?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z; CXSendHelper::ReadExtra(void *,void *,int)
0x180025c53  test    eax, eax
0x180025c55  jz      short loc_180025C5B
0x180025c57  xor     ebx, ebx
0x180025c59  jmp     short loc_180025C60
0x180025c5b  mov     ebx, 80004005h
0x180025c60  lea     rcx, [rsp+78h+var_48]; this
0x180025c65  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x180025c6a  mov     eax, ebx
0x180025c6c  jmp     short loc_180025C73
0x180025c6e  mov     eax, 80070216h
0x180025c73  add     rsp, 58h
0x180025c77  pop     r15
0x180025c79  pop     rsi
0x180025c7a  pop     rbp
0x180025c7b  pop     rbx
0x180025c7c  retn
```
