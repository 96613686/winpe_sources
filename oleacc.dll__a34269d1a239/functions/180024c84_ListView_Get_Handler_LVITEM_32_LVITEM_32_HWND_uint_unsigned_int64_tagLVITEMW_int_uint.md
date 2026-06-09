# ListView_Get_Handler<LVITEM_32>(LVITEM_32 &,HWND__ *,uint,unsigned __int64,tagLVITEMW *,int,uint)

- ea: `0x180024c84`
- end: `0x180024ded`
- name: `??$ListView_Get_Handler@ULVITEM_32@@@@YAJAEAULVITEM_32@@PEAUHWND__@@I_KPEAUtagLVITEMW@@HI@Z`
- size: `361`
- prototype: `__int64 __usercall@<rax>(LPVOID lpBuffer@<rcx>, HWND@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d1cc`

## callees

- `0x180024c84`
- `0x180025fd0`
- `0x18002604c`
- `0x180026090`
- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180024d81`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180024d81`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180024d43`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180024d43`
- `USER32!SendMessageW` at `0x180024d5c`
- `USER32!SendMessageW` at `0x180024d5c`

## pseudocode

```c
__int64 __fastcall ListView_Get_Handler<LVITEM_32>(int *lpBuffer, HWND a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v5; // rdi
  unsigned int v6; // r9d
  __int64 result; // rax
  unsigned int v10; // ebx
  bool v11; // zf
  int v12; // eax
  void *v13; // rdx
  HANDLE v14; // rcx
  char *v15; // rdx
  void **v16; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpBaseAddress; // [rsp+38h] [rbp-18h]
  HANDLE hProcess; // [rsp+40h] [rbp-10h]
  int v19; // [rsp+48h] [rbp-8h]
  int v20; // [rsp+4Ch] [rbp-4h]
  unsigned int v21; // [rsp+80h] [rbp+30h] BYREF

  v5 = a5;
  v6 = 0;
  v21 = 0;
  if ( (*(_BYTE *)a5 & 1) != 0 )
  {
    result = PlusOneTimesTchar(*(_DWORD *)(a5 + 32), &v21);
    if ( (int)result < 0 )
      return result;
    v6 = v21;
  }
  lpBaseAddress = 0;
  v16 = &CXSendHelper::`vftable';
  if ( CXSendHelper::Alloc((CXSendHelper *)&v16, a2, 40, v6) )
  {
    v11 = v20 == 0;
    *lpBuffer = *(_DWORD *)v5;
    lpBuffer[1] = *(_DWORD *)(v5 + 4);
    lpBuffer[2] = *(_DWORD *)(v5 + 8);
    if ( v11 )
      v12 = 0;
    else
      v12 = (_DWORD)lpBaseAddress + v19;
    v13 = lpBaseAddress;
    v14 = hProcess;
    lpBuffer[5] = v12;
    lpBuffer[6] = *(_DWORD *)(v5 + 32);
    if ( WriteProcessMemory(v14, v13, lpBuffer, 0x28u, 0)
      && SendMessageW(a2, 0x104Bu, 0, (LPARAM)lpBaseAddress)
      && ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x28u, 0)
      && (v15 = *(char **)(v5 + 24),
          *(_DWORD *)(v5 + 12) = lpBuffer[3],
          *(_DWORD *)(v5 + 16) = lpBuffer[4],
          *(_DWORD *)(v5 + 36) = lpBuffer[7],
          *(_QWORD *)(v5 + 40) = lpBuffer[8],
          *(_DWORD *)(v5 + 48) = lpBuffer[9],
          (unsigned int)CXSendHelper::ReadExtra((CXSendHelper *)&v16, v15, (void *)(unsigned int)lpBuffer[5], 1)) )
    {
      v10 = 0;
    }
    else
    {
      v10 = -2147467259;
    }
  }
  else
  {
    v10 = -2147024882;
  }
  CXSendHelper::~CXSendHelper((CXSendHelper *)&v16);
  return v10;
}

```

## disassembly

```asm
0x180024c84  mov     [rsp-18h+arg_0], rbx
0x180024c89  mov     [rsp-18h+arg_8], rsi
0x180024c8e  mov     [rsp-18h+arg_10], r8d
0x180024c93  push    rbp
0x180024c94  push    rdi
0x180024c95  push    r15
0x180024c97  mov     rbp, rsp
0x180024c9a  sub     rsp, 50h
0x180024c9e  mov     rdi, [rbp+arg_20]
0x180024ca2  xor     r9d, r9d
0x180024ca5  mov     r15, rdx
0x180024ca8  mov     [rbp+arg_10], r9d
0x180024cac  mov     rbx, rcx
0x180024caf  test    byte ptr [rdi], 1
0x180024cb2  jz      short loc_180024CCC
0x180024cb4  mov     ecx, [rdi+20h]; unsigned int
0x180024cb7  lea     rdx, [rbp+arg_10]; unsigned int *
0x180024cbb  call    ?PlusOneTimesTchar@@YAJKPEAK@Z; PlusOneTimesTchar(ulong,ulong *)
0x180024cc0  test    eax, eax
0x180024cc2  js      loc_180024DDA
0x180024cc8  mov     r9d, [rbp+arg_10]; unsigned int
0x180024ccc  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x180024cd3  mov     [rbp+lpBaseAddress], 0
0x180024cdb  mov     r8d, 28h ; '('; unsigned int
0x180024ce1  mov     [rbp+var_20], rax
0x180024ce5  mov     rdx, r15; HWND
0x180024ce8  lea     rcx, [rbp+var_20]; this
0x180024cec  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x180024cf1  test    eax, eax
0x180024cf3  jnz     short loc_180024CFF
0x180024cf5  mov     ebx, 8007000Eh
0x180024cfa  jmp     loc_180024DCF
0x180024cff  cmp     [rbp+var_4], 0
0x180024d03  mov     eax, [rdi]
0x180024d05  mov     [rbx], eax
0x180024d07  mov     eax, [rdi+4]
0x180024d0a  mov     [rbx+4], eax
0x180024d0d  mov     eax, [rdi+8]
0x180024d10  mov     [rbx+8], eax
0x180024d13  jnz     short loc_180024D19
0x180024d15  xor     eax, eax
0x180024d17  jmp     short loc_180024D20
0x180024d19  mov     eax, [rbp+var_8]
0x180024d1c  add     rax, [rbp+lpBaseAddress]
0x180024d20  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180024d24  mov     r9d, 28h ; '('; nSize
0x180024d2a  mov     rcx, [rbp+hProcess]; hProcess
0x180024d2e  mov     r8, rbx; lpBuffer
0x180024d31  mov     [rbx+14h], eax
0x180024d34  mov     eax, [rdi+20h]
0x180024d37  mov     [rbx+18h], eax
0x180024d3a  mov     [rsp+50h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180024d43  call    cs:__imp_WriteProcessMemory
0x180024d49  test    eax, eax
0x180024d4b  jz      short loc_180024DCA
0x180024d4d  mov     r9, [rbp+lpBaseAddress]; lParam
0x180024d51  xor     r8d, r8d; wParam
0x180024d54  mov     edx, 104Bh; Msg
0x180024d59  mov     rcx, r15; hWnd
0x180024d5c  call    cs:__imp_SendMessageW
0x180024d62  test    rax, rax
0x180024d65  jz      short loc_180024DCA
0x180024d67  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180024d6b  mov     r9d, 28h ; '('; nSize
0x180024d71  mov     rcx, [rbp+hProcess]; hProcess
0x180024d75  mov     r8, rbx; lpBuffer
0x180024d78  mov     [rsp+50h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180024d81  call    cs:__imp_ReadProcessMemory
0x180024d87  test    eax, eax
0x180024d89  jz      short loc_180024DCA
0x180024d8b  mov     eax, [rbx+0Ch]
0x180024d8e  lea     rcx, [rbp+var_20]; this
0x180024d92  mov     rdx, [rdi+18h]; void *
0x180024d96  mov     r9d, 1; int
0x180024d9c  mov     [rdi+0Ch], eax
0x180024d9f  mov     eax, [rbx+10h]
0x180024da2  mov     [rdi+10h], eax
0x180024da5  mov     eax, [rbx+1Ch]
0x180024da8  mov     [rdi+24h], eax
0x180024dab  movsxd  rax, dword ptr [rbx+20h]
0x180024daf  mov     [rdi+28h], rax
0x180024db3  mov     eax, [rbx+24h]
0x180024db6  mov     [rdi+30h], eax
0x180024db9  mov     r8d, [rbx+14h]; void *
0x180024dbd  call    ?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z; CXSendHelper::ReadExtra(void *,void *,int)
0x180024dc2  test    eax, eax
0x180024dc4  jz      short loc_180024DCA
0x180024dc6  xor     ebx, ebx
0x180024dc8  jmp     short loc_180024DCF
0x180024dca  mov     ebx, 80004005h
0x180024dcf  lea     rcx, [rbp+var_20]; this
0x180024dd3  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x180024dd8  mov     eax, ebx
0x180024dda  mov     rbx, [rsp+50h+arg_0]
0x180024ddf  mov     rsi, [rsp+50h+arg_8]
0x180024de4  add     rsp, 50h
0x180024de8  pop     r15
0x180024dea  pop     rdi
0x180024deb  pop     rbp
0x180024dec  retn
```
