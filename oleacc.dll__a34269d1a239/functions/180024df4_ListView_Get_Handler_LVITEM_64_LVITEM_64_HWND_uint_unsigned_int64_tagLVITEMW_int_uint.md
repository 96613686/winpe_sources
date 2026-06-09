# ListView_Get_Handler<LVITEM_64>(LVITEM_64 &,HWND__ *,uint,unsigned __int64,tagLVITEMW *,int,uint)

- ea: `0x180024df4`
- end: `0x180024f5e`
- name: `??$ListView_Get_Handler@ULVITEM_64@@@@YAJAEAULVITEM_64@@PEAUHWND__@@I_KPEAUtagLVITEMW@@HI@Z`
- size: `362`
- prototype: `__int64 __fastcall(LPVOID lpBuffer, HWND, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d1cc`

## callees

- `0x180024df4`
- `0x180025fd0`
- `0x18002604c`
- `0x180026090`
- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180024ef2`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180024ef2`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180024eb4`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180024eb4`
- `USER32!SendMessageW` at `0x180024ecd`
- `USER32!SendMessageW` at `0x180024ecd`

## pseudocode

```c
__int64 __fastcall ListView_Get_Handler<LVITEM_64>(LPVOID lpBuffer, HWND a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v5; // rdi
  unsigned int v6; // r9d
  __int64 result; // rax
  unsigned int v10; // ebx
  bool v11; // zf
  char *v12; // rax
  void *v13; // rdx
  HANDLE v14; // rcx
  void *v15; // rdx
  void **v16; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpBaseAddress; // [rsp+38h] [rbp-18h]
  HANDLE hProcess; // [rsp+40h] [rbp-10h]
  unsigned int v19; // [rsp+48h] [rbp-8h]
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
  if ( (unsigned int)CXSendHelper::Alloc((CXSendHelper *)&v16, a2, 0x38u, v6) )
  {
    v11 = v20 == 0;
    *(_DWORD *)lpBuffer = *(_DWORD *)v5;
    *((_DWORD *)lpBuffer + 1) = *(_DWORD *)(v5 + 4);
    *((_DWORD *)lpBuffer + 2) = *(_DWORD *)(v5 + 8);
    if ( v11 )
      v12 = 0;
    else
      v12 = (char *)lpBaseAddress + v19;
    v13 = lpBaseAddress;
    v14 = hProcess;
    *((_QWORD *)lpBuffer + 3) = v12;
    *((_DWORD *)lpBuffer + 8) = *(_DWORD *)(v5 + 32);
    if ( WriteProcessMemory(v14, v13, lpBuffer, 0x38u, 0)
      && SendMessageW(a2, 0x104Bu, 0, (LPARAM)lpBaseAddress)
      && ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x38u, 0)
      && (v15 = *(void **)(v5 + 24),
          *(_DWORD *)(v5 + 12) = *((_DWORD *)lpBuffer + 3),
          *(_DWORD *)(v5 + 16) = *((_DWORD *)lpBuffer + 4),
          *(_DWORD *)(v5 + 36) = *((_DWORD *)lpBuffer + 9),
          *(_QWORD *)(v5 + 40) = *((_QWORD *)lpBuffer + 5),
          *(_DWORD *)(v5 + 48) = *((_DWORD *)lpBuffer + 12),
          CXSendHelper::ReadExtra((CXSendHelper *)&v16, v15, *((void **)lpBuffer + 3), 1)) )
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
0x180024df4  mov     [rsp-18h+arg_0], rbx
0x180024df9  mov     [rsp-18h+arg_8], rsi
0x180024dfe  mov     [rsp-18h+arg_10], r8d
0x180024e03  push    rbp
0x180024e04  push    rdi
0x180024e05  push    r15
0x180024e07  mov     rbp, rsp
0x180024e0a  sub     rsp, 50h
0x180024e0e  mov     rdi, [rbp+arg_20]
0x180024e12  xor     r9d, r9d
0x180024e15  mov     r15, rdx
0x180024e18  mov     [rbp+arg_10], r9d
0x180024e1c  mov     rbx, rcx
0x180024e1f  test    byte ptr [rdi], 1
0x180024e22  jz      short loc_180024E3C
0x180024e24  mov     ecx, [rdi+20h]; unsigned int
0x180024e27  lea     rdx, [rbp+arg_10]; unsigned int *
0x180024e2b  call    ?PlusOneTimesTchar@@YAJKPEAK@Z; PlusOneTimesTchar(ulong,ulong *)
0x180024e30  test    eax, eax
0x180024e32  js      loc_180024F4B
0x180024e38  mov     r9d, [rbp+arg_10]; unsigned int
0x180024e3c  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x180024e43  mov     [rbp+lpBaseAddress], 0
0x180024e4b  mov     r8d, 38h ; '8'; unsigned int
0x180024e51  mov     [rbp+var_20], rax
0x180024e55  mov     rdx, r15; HWND
0x180024e58  lea     rcx, [rbp+var_20]; this
0x180024e5c  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x180024e61  test    eax, eax
0x180024e63  jnz     short loc_180024E6F
0x180024e65  mov     ebx, 8007000Eh
0x180024e6a  jmp     loc_180024F40
0x180024e6f  cmp     [rbp+var_4], 0
0x180024e73  mov     eax, [rdi]
0x180024e75  mov     [rbx], eax
0x180024e77  mov     eax, [rdi+4]
0x180024e7a  mov     [rbx+4], eax
0x180024e7d  mov     eax, [rdi+8]
0x180024e80  mov     [rbx+8], eax
0x180024e83  jnz     short loc_180024E89
0x180024e85  xor     eax, eax
0x180024e87  jmp     short loc_180024E90
0x180024e89  mov     eax, [rbp+var_8]
0x180024e8c  add     rax, [rbp+lpBaseAddress]
0x180024e90  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180024e94  mov     r9d, 38h ; '8'; nSize
0x180024e9a  mov     rcx, [rbp+hProcess]; hProcess
0x180024e9e  mov     r8, rbx; lpBuffer
0x180024ea1  mov     [rbx+18h], rax
0x180024ea5  mov     eax, [rdi+20h]
0x180024ea8  mov     [rbx+20h], eax
0x180024eab  mov     [rsp+50h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180024eb4  call    cs:__imp_WriteProcessMemory
0x180024eba  test    eax, eax
0x180024ebc  jz      short loc_180024F3B
0x180024ebe  mov     r9, [rbp+lpBaseAddress]; lParam
0x180024ec2  xor     r8d, r8d; wParam
0x180024ec5  mov     edx, 104Bh; Msg
0x180024eca  mov     rcx, r15; hWnd
0x180024ecd  call    cs:__imp_SendMessageW
0x180024ed3  test    rax, rax
0x180024ed6  jz      short loc_180024F3B
0x180024ed8  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180024edc  mov     r9d, 38h ; '8'; nSize
0x180024ee2  mov     rcx, [rbp+hProcess]; hProcess
0x180024ee6  mov     r8, rbx; lpBuffer
0x180024ee9  mov     [rsp+50h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180024ef2  call    cs:__imp_ReadProcessMemory
0x180024ef8  test    eax, eax
0x180024efa  jz      short loc_180024F3B
0x180024efc  mov     eax, [rbx+0Ch]
0x180024eff  lea     rcx, [rbp+var_20]; this
0x180024f03  mov     rdx, [rdi+18h]; void *
0x180024f07  mov     r9d, 1; int
0x180024f0d  mov     [rdi+0Ch], eax
0x180024f10  mov     eax, [rbx+10h]
0x180024f13  mov     [rdi+10h], eax
0x180024f16  mov     eax, [rbx+24h]
0x180024f19  mov     [rdi+24h], eax
0x180024f1c  mov     rax, [rbx+28h]
0x180024f20  mov     [rdi+28h], rax
0x180024f24  mov     eax, [rbx+30h]
0x180024f27  mov     [rdi+30h], eax
0x180024f2a  mov     r8, [rbx+18h]; void *
0x180024f2e  call    ?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z; CXSendHelper::ReadExtra(void *,void *,int)
0x180024f33  test    eax, eax
0x180024f35  jz      short loc_180024F3B
0x180024f37  xor     ebx, ebx
0x180024f39  jmp     short loc_180024F40
0x180024f3b  mov     ebx, 80004005h
0x180024f40  lea     rcx, [rbp+var_20]; this
0x180024f44  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x180024f49  mov     eax, ebx
0x180024f4b  mov     rbx, [rsp+50h+arg_0]
0x180024f50  mov     rsi, [rsp+50h+arg_8]
0x180024f55  add     rsp, 50h
0x180024f59  pop     r15
0x180024f5b  pop     rdi
0x180024f5c  pop     rbp
0x180024f5d  retn
```
