# ListView_GetCol_Handler<LVCOLUMN_64>(LVCOLUMN_64 &,HWND__ *,uint,unsigned __int64,tagLVCOLUMNW *,int,uint)

- ea: `0x180024b44`
- end: `0x180024c7c`
- name: `??$ListView_GetCol_Handler@ULVCOLUMN_64@@@@YAJAEAULVCOLUMN_64@@PEAUHWND__@@I_KPEAUtagLVCOLUMNW@@HI@Z`
- size: `312`
- prototype: `__int64 __usercall@<rax>(LPVOID lpBuffer@<rcx>, HWND@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180026230`

## callees

- `0x180024b44`
- `0x180025fd0`
- `0x18002604c`
- `0x180026090`
- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180024c38`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180024c38`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180024bfd`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180024bfd`
- `USER32!SendMessageW` at `0x180024c16`
- `USER32!SendMessageW` at `0x180024c16`

## pseudocode

```c
__int64 __fastcall ListView_GetCol_Handler<LVCOLUMN_64>(LPVOID lpBuffer, HWND a2, __int64 a3, WPARAM a4, __int64 a5)
{
  __int64 v5; // rdi
  unsigned int v7; // r9d
  __int64 result; // rax
  unsigned int v11; // ebx
  bool v12; // zf
  char *v13; // rax
  void *v14; // rdx
  HANDLE v15; // rcx
  void **v16; // [rsp+30h] [rbp-28h] BYREF
  LPVOID lpBaseAddress; // [rsp+38h] [rbp-20h]
  HANDLE hProcess; // [rsp+40h] [rbp-18h]
  unsigned int v19; // [rsp+48h] [rbp-10h]
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
  if ( CXSendHelper::Alloc((CXSendHelper *)&v16, a2, 32, v7) )
  {
    v12 = v20 == 0;
    *(_DWORD *)lpBuffer = *(_DWORD *)v5;
    *((_DWORD *)lpBuffer + 7) = *(_DWORD *)(v5 + 28);
    if ( v12 )
      v13 = 0;
    else
      v13 = (char *)lpBaseAddress + v19;
    v14 = lpBaseAddress;
    v15 = hProcess;
    *((_QWORD *)lpBuffer + 2) = v13;
    *((_DWORD *)lpBuffer + 6) = *(_DWORD *)(v5 + 24);
    if ( WriteProcessMemory(v15, v14, lpBuffer, 0x20u, 0)
      && SendMessageW(a2, 0x105Fu, a4, (LPARAM)lpBaseAddress)
      && ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x20u, 0)
      && (unsigned int)CXSendHelper::ReadExtra((CXSendHelper *)&v16, *(char **)(v5 + 16), *((void **)lpBuffer + 2), 1) )
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
0x180024b44  mov     [rsp-30h+arg_10], r8d
0x180024b49  push    rbp
0x180024b4a  push    rbx
0x180024b4b  push    rsi
0x180024b4c  push    rdi
0x180024b4d  push    r12
0x180024b4f  push    r15
0x180024b51  mov     rbp, rsp
0x180024b54  sub     rsp, 58h
0x180024b58  mov     rdi, [rbp+arg_20]
0x180024b5c  mov     r12, r9
0x180024b5f  xor     r9d, r9d
0x180024b62  mov     r15, rdx
0x180024b65  mov     rbx, rcx
0x180024b68  mov     [rbp+arg_10], r9d
0x180024b6c  test    byte ptr [rdi], 4
0x180024b6f  jz      short loc_180024B89
0x180024b71  mov     ecx, [rdi+18h]; unsigned int
0x180024b74  lea     rdx, [rbp+arg_10]; unsigned int *
0x180024b78  call    ?PlusOneTimesTchar@@YAJKPEAK@Z; PlusOneTimesTchar(ulong,ulong *)
0x180024b7d  test    eax, eax
0x180024b7f  js      loc_180024C6F
0x180024b85  mov     r9d, [rbp+arg_10]; unsigned int
0x180024b89  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x180024b90  mov     [rbp+lpBaseAddress], 0
0x180024b98  mov     r8d, 20h ; ' '; unsigned int
0x180024b9e  mov     [rbp+var_28], rax
0x180024ba2  mov     rdx, r15; HWND
0x180024ba5  lea     rcx, [rbp+var_28]; this
0x180024ba9  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x180024bae  test    eax, eax
0x180024bb0  jnz     short loc_180024BBC
0x180024bb2  mov     ebx, 8007000Eh
0x180024bb7  jmp     loc_180024C64
0x180024bbc  cmp     [rbp+var_C], 0
0x180024bc0  mov     eax, [rdi]
0x180024bc2  mov     [rbx], eax
0x180024bc4  mov     eax, [rdi+1Ch]
0x180024bc7  mov     [rbx+1Ch], eax
0x180024bca  jnz     short loc_180024BD0
0x180024bcc  xor     eax, eax
0x180024bce  jmp     short loc_180024BD7
0x180024bd0  mov     eax, [rbp+var_10]
0x180024bd3  add     rax, [rbp+lpBaseAddress]
0x180024bd7  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180024bdb  mov     esi, 20h ; ' '
0x180024be0  mov     rcx, [rbp+hProcess]; hProcess
0x180024be4  mov     r9d, esi; nSize
0x180024be7  mov     [rbx+10h], rax
0x180024beb  mov     r8, rbx; lpBuffer
0x180024bee  mov     eax, [rdi+18h]
0x180024bf1  mov     [rbx+18h], eax
0x180024bf4  mov     [rsp+58h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180024bfd  call    cs:__imp_WriteProcessMemory
0x180024c03  test    eax, eax
0x180024c05  jz      short loc_180024C5F
0x180024c07  mov     r9, [rbp+lpBaseAddress]; lParam
0x180024c0b  mov     r8, r12; wParam
0x180024c0e  mov     edx, 105Fh; Msg
0x180024c13  mov     rcx, r15; hWnd
0x180024c16  call    cs:__imp_SendMessageW
0x180024c1c  test    rax, rax
0x180024c1f  jz      short loc_180024C5F
0x180024c21  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180024c25  mov     r9d, esi; nSize
0x180024c28  mov     rcx, [rbp+hProcess]; hProcess
0x180024c2c  mov     r8, rbx; lpBuffer
0x180024c2f  mov     [rsp+58h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180024c38  call    cs:__imp_ReadProcessMemory
0x180024c3e  test    eax, eax
0x180024c40  jz      short loc_180024C5F
0x180024c42  mov     r8, [rbx+10h]; void *
0x180024c46  lea     r9d, [rsi-1Fh]; int
0x180024c4a  mov     rdx, [rdi+10h]; void *
0x180024c4e  lea     rcx, [rbp+var_28]; this
0x180024c52  call    ?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z; CXSendHelper::ReadExtra(void *,void *,int)
0x180024c57  test    eax, eax
0x180024c59  jz      short loc_180024C5F
0x180024c5b  xor     ebx, ebx
0x180024c5d  jmp     short loc_180024C64
0x180024c5f  mov     ebx, 80004005h
0x180024c64  lea     rcx, [rbp+var_28]; this
0x180024c68  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x180024c6d  mov     eax, ebx
0x180024c6f  add     rsp, 58h
0x180024c73  pop     r15
0x180024c75  pop     r12
0x180024c77  pop     rdi
0x180024c78  pop     rsi
0x180024c79  pop     rbx
0x180024c7a  pop     rbp
0x180024c7b  retn
```
