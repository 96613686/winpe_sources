# ListView_V6_Get_Handler<LVITEM_V6_64>(LVITEM_V6_64 &,HWND__ *,uint,unsigned __int64,LVITEM_V6 *,int,uint)

- ea: `0x1800255d8`
- end: `0x18002573c`
- name: `??$ListView_V6_Get_Handler@ULVITEM_V6_64@@@@YAJAEAULVITEM_V6_64@@PEAUHWND__@@I_KPEAULVITEM_V6@@HI@Z`
- size: `356`
- prototype: `__int64 __usercall@<rax>(LPVOID lpBuffer@<rcx>, HWND hWnd@<rdx>, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800264cc`

## callees

- `0x1800255d8`
- `0x180025fd0`
- `0x18002604c`
- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800256e4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800256e4`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002569a`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002569a`
- `USER32!SendMessageW` at `0x1800256b4`
- `USER32!SendMessageW` at `0x1800256b4`

## pseudocode

```c
__int64 __fastcall ListView_V6_Get_Handler<LVITEM_V6_64>(
        LPVOID lpBuffer,
        HWND hWnd,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  unsigned __int64 v6; // r9
  unsigned int v9; // esi
  unsigned int v11; // ebx
  char *v12; // rax
  void *v13; // rdx
  HANDLE v14; // rcx
  char *v15; // rdx
  void **v16; // [rsp+30h] [rbp-48h] BYREF
  LPVOID lpBaseAddress; // [rsp+38h] [rbp-40h]
  HANDLE hProcess; // [rsp+40h] [rbp-38h]
  unsigned int v19; // [rsp+48h] [rbp-30h]
  int v20; // [rsp+4Ch] [rbp-2Ch]

  LODWORD(v6) = 0;
  v9 = *(_DWORD *)(a5 + 56);
  if ( (*(_DWORD *)a5 & 0x200) != 0 )
  {
    v6 = 4LL * v9;
    if ( v6 > 0xFFFFFFFF )
      return 2147500037LL;
  }
  lpBaseAddress = 0;
  v16 = &CXSendHelper::`vftable';
  if ( CXSendHelper::Alloc((CXSendHelper *)&v16, hWnd, 72, v6) )
  {
    *(_DWORD *)lpBuffer = *(_DWORD *)a5;
    *((_DWORD *)lpBuffer + 1) = *(_DWORD *)(a5 + 4);
    *((_DWORD *)lpBuffer + 2) = *(_DWORD *)(a5 + 8);
    *((_DWORD *)lpBuffer + 14) = v9;
    if ( *(_QWORD *)(a5 + 64) && v20 )
      v12 = (char *)lpBaseAddress + v19;
    else
      v12 = 0;
    v13 = lpBaseAddress;
    v14 = hProcess;
    *((_QWORD *)lpBuffer + 8) = v12;
    if ( WriteProcessMemory(v14, v13, lpBuffer, 0x48u, 0)
      && (SendMessageW(hWnd, 0x104Bu, 0, (LPARAM)lpBaseAddress) || !a6)
      && ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x48u, 0)
      && ((v15 = *(char **)(a5 + 64),
           *(_DWORD *)(a5 + 56) = *((_DWORD *)lpBuffer + 14),
           *(_DWORD *)(a5 + 52) = *((_DWORD *)lpBuffer + 13),
           !v15)
       || v9 >= *((_DWORD *)lpBuffer + 14)
       && (unsigned int)CXSendHelper::ReadExtra((CXSendHelper *)&v16, v15, *((void **)lpBuffer + 8), 0)) )
    {
      v11 = 0;
    }
    else
    {
      v11 = -2147467259;
    }
  }
  else
  {
    v11 = -2147024882;
  }
  CXSendHelper::~CXSendHelper((CXSendHelper *)&v16);
  return v11;
}

```

## disassembly

```asm
0x1800255d8  push    rbx
0x1800255da  push    rsi
0x1800255db  push    rdi
0x1800255dc  push    r14
0x1800255de  sub     rsp, 58h
0x1800255e2  mov     rdi, [rsp+78h+arg_20]
0x1800255ea  xor     r9d, r9d; unsigned int
0x1800255ed  mov     r14, rdx
0x1800255f0  mov     rbx, rcx
0x1800255f3  test    dword ptr [rdi], 200h
0x1800255f9  mov     esi, [rdi+38h]
0x1800255fc  jz      short loc_180025619
0x1800255fe  mov     r9d, esi
0x180025601  mov     eax, 0FFFFFFFFh
0x180025606  shl     r9, 2
0x18002560a  cmp     r9, rax
0x18002560d  jbe     short loc_180025619
0x18002560f  mov     eax, 80004005h
0x180025614  jmp     loc_180025732
0x180025619  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x180025620  mov     [rsp+78h+lpBaseAddress], 0
0x180025629  mov     r8d, 48h ; 'H'; unsigned int
0x18002562f  mov     [rsp+78h+var_48], rax
0x180025634  lea     rcx, [rsp+78h+var_48]; this
0x180025639  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x18002563e  test    eax, eax
0x180025640  jnz     short loc_18002564C
0x180025642  mov     ebx, 8007000Eh
0x180025647  jmp     loc_180025726
0x18002564c  mov     eax, [rdi]
0x18002564e  mov     [rbx], eax
0x180025650  mov     eax, [rdi+4]
0x180025653  mov     [rbx+4], eax
0x180025656  mov     eax, [rdi+8]
0x180025659  mov     [rbx+8], eax
0x18002565c  mov     [rbx+38h], esi
0x18002565f  cmp     qword ptr [rdi+40h], 0
0x180025664  jz      short loc_180025678
0x180025666  cmp     [rsp+78h+var_2C], 0
0x18002566b  jz      short loc_180025678
0x18002566d  mov     eax, [rsp+78h+var_30]
0x180025671  add     rax, [rsp+78h+lpBaseAddress]
0x180025676  jmp     short loc_18002567A
0x180025678  xor     eax, eax
0x18002567a  mov     rdx, [rsp+78h+lpBaseAddress]; lpBaseAddress
0x18002567f  mov     r9d, 48h ; 'H'; nSize
0x180025685  mov     rcx, [rsp+78h+hProcess]; hProcess
0x18002568a  mov     r8, rbx; lpBuffer
0x18002568d  mov     [rbx+40h], rax
0x180025691  mov     [rsp+78h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x18002569a  call    cs:__imp_WriteProcessMemory
0x1800256a0  test    eax, eax
0x1800256a2  jz      short loc_180025721
0x1800256a4  mov     r9, [rsp+78h+lpBaseAddress]; lParam
0x1800256a9  xor     r8d, r8d; wParam
0x1800256ac  mov     edx, 104Bh; Msg
0x1800256b1  mov     rcx, r14; hWnd
0x1800256b4  call    cs:__imp_SendMessageW
0x1800256ba  test    rax, rax
0x1800256bd  jnz     short loc_1800256C8
0x1800256bf  cmp     [rsp+78h+arg_28], eax
0x1800256c6  jnz     short loc_180025721
0x1800256c8  mov     rdx, [rsp+78h+lpBaseAddress]; lpBaseAddress
0x1800256cd  mov     r9d, 48h ; 'H'; nSize
0x1800256d3  mov     rcx, [rsp+78h+hProcess]; hProcess
0x1800256d8  mov     r8, rbx; lpBuffer
0x1800256db  mov     [rsp+78h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x1800256e4  call    cs:__imp_ReadProcessMemory
0x1800256ea  test    eax, eax
0x1800256ec  jz      short loc_180025721
0x1800256ee  mov     eax, [rbx+38h]
0x1800256f1  mov     rdx, [rdi+40h]; void *
0x1800256f5  mov     [rdi+38h], eax
0x1800256f8  mov     eax, [rbx+34h]
0x1800256fb  mov     [rdi+34h], eax
0x1800256fe  test    rdx, rdx
0x180025701  jz      short loc_18002571D
0x180025703  cmp     esi, [rbx+38h]
0x180025706  jb      short loc_180025721
0x180025708  mov     r8, [rbx+40h]; void *
0x18002570c  lea     rcx, [rsp+78h+var_48]; this
0x180025711  xor     r9d, r9d; int
0x180025714  call    ?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z; CXSendHelper::ReadExtra(void *,void *,int)
0x180025719  test    eax, eax
0x18002571b  jz      short loc_180025721
0x18002571d  xor     ebx, ebx
0x18002571f  jmp     short loc_180025726
0x180025721  mov     ebx, 80004005h
0x180025726  lea     rcx, [rsp+78h+var_48]; this
0x18002572b  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x180025730  mov     eax, ebx
0x180025732  add     rsp, 58h
0x180025736  pop     r14
0x180025738  pop     rdi
0x180025739  pop     rsi
0x18002573a  pop     rbx
0x18002573b  retn
```
