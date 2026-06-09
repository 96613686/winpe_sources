# ListView_GetCol_Handler<LVCOLUMN_32>(LVCOLUMN_32 &,HWND__ *,uint,unsigned __int64,tagLVCOLUMNW *,int,uint)

- ea: `0x180024a04`
- end: `0x180024b3b`
- name: `??$ListView_GetCol_Handler@ULVCOLUMN_32@@@@YAJAEAULVCOLUMN_32@@PEAUHWND__@@I_KPEAUtagLVCOLUMNW@@HI@Z`
- size: `311`
- prototype: `__int64 __usercall@<rax>(LPVOID lpBuffer@<rcx>, HWND@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180026230`

## callees

- `0x180024a04`
- `0x180025fd0`
- `0x18002604c`
- `0x180026090`
- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180024af7`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180024af7`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180024abc`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180024abc`
- `USER32!SendMessageW` at `0x180024ad5`
- `USER32!SendMessageW` at `0x180024ad5`

## pseudocode

```c
__int64 __fastcall ListView_GetCol_Handler<LVCOLUMN_32>(
        unsigned int *lpBuffer,
        HWND a2,
        __int64 a3,
        WPARAM a4,
        __int64 a5)
{
  __int64 v5; // rdi
  unsigned int v7; // r9d
  __int64 result; // rax
  unsigned int v11; // ebx
  bool v12; // zf
  unsigned int v13; // eax
  void *v14; // rdx
  HANDLE v15; // rcx
  void **v16; // [rsp+30h] [rbp-28h] BYREF
  LPVOID lpBaseAddress; // [rsp+38h] [rbp-20h]
  HANDLE hProcess; // [rsp+40h] [rbp-18h]
  int v19; // [rsp+48h] [rbp-10h]
  int v20; // [rsp+4Ch] [rbp-Ch]
  unsigned int v21; // [rsp+A0h] [rbp+48h] BYREF

  v5 = a5;
  v7 = 0;
  v21 = 0;
  if ( (*(_BYTE *)a5 & 4) != 0 )
  {
    result = PlusOneTimesTchar(*(_DWORD *)(a5 + 24), &v21);
    if ( (int)result < 0 )
      return result;
    v7 = v21;
  }
  lpBaseAddress = 0;
  v16 = &CXSendHelper::`vftable';
  if ( CXSendHelper::Alloc((CXSendHelper *)&v16, a2, 24, v7) )
  {
    v12 = v20 == 0;
    *lpBuffer = *(_DWORD *)v5;
    lpBuffer[5] = *(_DWORD *)(v5 + 28);
    if ( v12 )
      v13 = 0;
    else
      v13 = (_DWORD)lpBaseAddress + v19;
    v14 = lpBaseAddress;
    v15 = hProcess;
    lpBuffer[3] = v13;
    lpBuffer[4] = *(_DWORD *)(v5 + 24);
    if ( WriteProcessMemory(v15, v14, lpBuffer, 0x18u, 0)
      && SendMessageW(a2, 0x105Fu, a4, (LPARAM)lpBaseAddress)
      && ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x18u, 0)
      && (unsigned int)CXSendHelper::ReadExtra((CXSendHelper *)&v16, *(char **)(v5 + 16), (void *)lpBuffer[3], 1) )
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
0x180024a04  mov     [rsp-30h+arg_10], r8d
0x180024a09  push    rbp
0x180024a0a  push    rbx
0x180024a0b  push    rsi
0x180024a0c  push    rdi
0x180024a0d  push    r12
0x180024a0f  push    r15
0x180024a11  mov     rbp, rsp
0x180024a14  sub     rsp, 58h
0x180024a18  mov     rdi, [rbp+arg_20]
0x180024a1c  mov     r12, r9
0x180024a1f  xor     r9d, r9d
0x180024a22  mov     r15, rdx
0x180024a25  mov     rbx, rcx
0x180024a28  mov     [rbp+arg_10], r9d
0x180024a2c  test    byte ptr [rdi], 4
0x180024a2f  jz      short loc_180024A49
0x180024a31  mov     ecx, [rdi+18h]; unsigned int
0x180024a34  lea     rdx, [rbp+arg_10]; unsigned int *
0x180024a38  call    ?PlusOneTimesTchar@@YAJKPEAK@Z; PlusOneTimesTchar(ulong,ulong *)
0x180024a3d  test    eax, eax
0x180024a3f  js      loc_180024B2E
0x180024a45  mov     r9d, [rbp+arg_10]; unsigned int
0x180024a49  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x180024a50  mov     [rbp+lpBaseAddress], 0
0x180024a58  mov     r8d, 18h; unsigned int
0x180024a5e  mov     [rbp+var_28], rax
0x180024a62  mov     rdx, r15; HWND
0x180024a65  lea     rcx, [rbp+var_28]; this
0x180024a69  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x180024a6e  test    eax, eax
0x180024a70  jnz     short loc_180024A7C
0x180024a72  mov     ebx, 8007000Eh
0x180024a77  jmp     loc_180024B23
0x180024a7c  cmp     [rbp+var_C], 0
0x180024a80  mov     eax, [rdi]
0x180024a82  mov     [rbx], eax
0x180024a84  mov     eax, [rdi+1Ch]
0x180024a87  mov     [rbx+14h], eax
0x180024a8a  jnz     short loc_180024A90
0x180024a8c  xor     eax, eax
0x180024a8e  jmp     short loc_180024A97
0x180024a90  mov     eax, [rbp+var_10]
0x180024a93  add     rax, [rbp+lpBaseAddress]
0x180024a97  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180024a9b  mov     esi, 18h
0x180024aa0  mov     rcx, [rbp+hProcess]; hProcess
0x180024aa4  mov     r9d, esi; nSize
0x180024aa7  mov     [rbx+0Ch], eax
0x180024aaa  mov     r8, rbx; lpBuffer
0x180024aad  mov     eax, [rdi+18h]
0x180024ab0  mov     [rbx+10h], eax
0x180024ab3  mov     [rsp+58h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180024abc  call    cs:__imp_WriteProcessMemory
0x180024ac2  test    eax, eax
0x180024ac4  jz      short loc_180024B1E
0x180024ac6  mov     r9, [rbp+lpBaseAddress]; lParam
0x180024aca  mov     r8, r12; wParam
0x180024acd  mov     edx, 105Fh; Msg
0x180024ad2  mov     rcx, r15; hWnd
0x180024ad5  call    cs:__imp_SendMessageW
0x180024adb  test    rax, rax
0x180024ade  jz      short loc_180024B1E
0x180024ae0  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180024ae4  mov     r9d, esi; nSize
0x180024ae7  mov     rcx, [rbp+hProcess]; hProcess
0x180024aeb  mov     r8, rbx; lpBuffer
0x180024aee  mov     [rsp+58h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180024af7  call    cs:__imp_ReadProcessMemory
0x180024afd  test    eax, eax
0x180024aff  jz      short loc_180024B1E
0x180024b01  mov     r8d, [rbx+0Ch]; void *
0x180024b05  lea     r9d, [rsi-17h]; int
0x180024b09  mov     rdx, [rdi+10h]; void *
0x180024b0d  lea     rcx, [rbp+var_28]; this
0x180024b11  call    ?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z; CXSendHelper::ReadExtra(void *,void *,int)
0x180024b16  test    eax, eax
0x180024b18  jz      short loc_180024B1E
0x180024b1a  xor     ebx, ebx
0x180024b1c  jmp     short loc_180024B23
0x180024b1e  mov     ebx, 80004005h
0x180024b23  lea     rcx, [rbp+var_28]; this
0x180024b27  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x180024b2c  mov     eax, ebx
0x180024b2e  add     rsp, 58h
0x180024b32  pop     r15
0x180024b34  pop     r12
0x180024b36  pop     rdi
0x180024b37  pop     rsi
0x180024b38  pop     rbx
0x180024b39  pop     rbp
0x180024b3a  retn
```
