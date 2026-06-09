# TabCtrl_Get_Handler<TCITEM_64>(TCITEM_64 &,HWND__ *,uint,unsigned __int64,tagTCITEMW *,int,uint)

- ea: `0x1800258b0`
- end: `0x180025a16`
- name: `??$TabCtrl_Get_Handler@UTCITEM_64@@@@YAJAEAUTCITEM_64@@PEAUHWND__@@I_KPEAUtagTCITEMW@@HI@Z`
- size: `358`
- prototype: `__int64 __usercall@<rax>(LPVOID lpBuffer@<rcx>, HWND@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800265ec`

## callees

- `0x1800258b0`
- `0x180025fd0`
- `0x18002604c`
- `0x180026090`
- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800259b8`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800259b8`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002597d`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002597d`
- `USER32!SendMessageW` at `0x180025996`
- `USER32!SendMessageW` at `0x180025996`

## pseudocode

```c
__int64 __fastcall TabCtrl_Get_Handler<TCITEM_64>(LPVOID lpBuffer, HWND a2, __int64 a3, WPARAM a4, __int64 a5)
{
  __int64 v5; // rbx
  unsigned int v7; // r9d
  __int64 result; // rax
  unsigned int v11; // ebx
  bool v12; // zf
  char *v13; // rax
  void *v14; // rdx
  HANDLE v15; // rcx
  char *v16; // rdx
  void **v17; // [rsp+30h] [rbp-28h] BYREF
  LPVOID lpBaseAddress; // [rsp+38h] [rbp-20h]
  HANDLE hProcess; // [rsp+40h] [rbp-18h]
  unsigned int v20; // [rsp+48h] [rbp-10h]
  int v21; // [rsp+4Ch] [rbp-Ch]
  unsigned int v22; // [rsp+A0h] [rbp+48h] BYREF

  v5 = a5;
  v7 = 0;
  v22 = 0;
  if ( (*(_BYTE *)a5 & 1) != 0 )
  {
    result = PlusOneTimesTchar(*(_DWORD *)(a5 + 24), &v22);
    if ( (int)result < 0 )
      return result;
    v7 = v22;
  }
  lpBaseAddress = 0;
  v17 = &CXSendHelper::`vftable';
  if ( CXSendHelper::Alloc((CXSendHelper *)&v17, a2, 56, v7) )
  {
    v12 = v21 == 0;
    *(_DWORD *)lpBuffer = *(_DWORD *)v5;
    *((_DWORD *)lpBuffer + 1) = *(_DWORD *)(v5 + 4);
    *((_DWORD *)lpBuffer + 2) = *(_DWORD *)(v5 + 8);
    if ( v12 )
      v13 = 0;
    else
      v13 = (char *)lpBaseAddress + v20;
    v14 = lpBaseAddress;
    v15 = hProcess;
    *((_QWORD *)lpBuffer + 2) = v13;
    *((_DWORD *)lpBuffer + 6) = *(_DWORD *)(v5 + 24);
    *((_DWORD *)lpBuffer + 7) = *(_DWORD *)(v5 + 28);
    *((_QWORD *)lpBuffer + 4) = *(_QWORD *)(v5 + 32);
    if ( WriteProcessMemory(v15, v14, lpBuffer, 0x28u, 0)
      && SendMessageW(a2, 0x133Cu, a4, (LPARAM)lpBaseAddress)
      && ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x28u, 0)
      && (v16 = *(char **)(v5 + 16),
          *(_DWORD *)(v5 + 4) = *((_DWORD *)lpBuffer + 1),
          *(_DWORD *)(v5 + 8) = *((_DWORD *)lpBuffer + 2),
          *(_DWORD *)(v5 + 28) = *((_DWORD *)lpBuffer + 7),
          *(_QWORD *)(v5 + 32) = *((_QWORD *)lpBuffer + 4),
          (unsigned int)CXSendHelper::ReadExtra((CXSendHelper *)&v17, v16, *((void **)lpBuffer + 2), 1)) )
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
  CXSendHelper::~CXSendHelper((CXSendHelper *)&v17);
  return v11;
}

```

## disassembly

```asm
0x1800258b0  mov     [rsp-30h+arg_10], r8d
0x1800258b5  push    rbp
0x1800258b6  push    rbx
0x1800258b7  push    rsi
0x1800258b8  push    rdi
0x1800258b9  push    r12
0x1800258bb  push    r15
0x1800258bd  mov     rbp, rsp
0x1800258c0  sub     rsp, 58h
0x1800258c4  mov     rbx, [rbp+arg_20]
0x1800258c8  mov     r12, r9
0x1800258cb  xor     r9d, r9d
0x1800258ce  mov     r15, rdx
0x1800258d1  mov     rdi, rcx
0x1800258d4  mov     [rbp+arg_10], r9d
0x1800258d8  test    byte ptr [rbx], 1
0x1800258db  jz      short loc_1800258F5
0x1800258dd  mov     ecx, [rbx+18h]; unsigned int
0x1800258e0  lea     rdx, [rbp+arg_10]; unsigned int *
0x1800258e4  call    ?PlusOneTimesTchar@@YAJKPEAK@Z; PlusOneTimesTchar(ulong,ulong *)
0x1800258e9  test    eax, eax
0x1800258eb  js      loc_180025A09
0x1800258f1  mov     r9d, [rbp+arg_10]; unsigned int
0x1800258f5  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x1800258fc  mov     [rbp+lpBaseAddress], 0
0x180025904  mov     r8d, 38h ; '8'; unsigned int
0x18002590a  mov     [rbp+var_28], rax
0x18002590e  mov     rdx, r15; HWND
0x180025911  lea     rcx, [rbp+var_28]; this
0x180025915  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x18002591a  test    eax, eax
0x18002591c  jnz     short loc_180025928
0x18002591e  mov     ebx, 8007000Eh
0x180025923  jmp     loc_1800259FE
0x180025928  cmp     [rbp+var_C], 0
0x18002592c  mov     eax, [rbx]
0x18002592e  mov     [rdi], eax
0x180025930  mov     eax, [rbx+4]
0x180025933  mov     [rdi+4], eax
0x180025936  mov     eax, [rbx+8]
0x180025939  mov     [rdi+8], eax
0x18002593c  jnz     short loc_180025942
0x18002593e  xor     eax, eax
0x180025940  jmp     short loc_180025949
0x180025942  mov     eax, [rbp+var_10]
0x180025945  add     rax, [rbp+lpBaseAddress]
0x180025949  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x18002594d  mov     esi, 28h ; '('
0x180025952  mov     rcx, [rbp+hProcess]; hProcess
0x180025956  mov     r9d, esi; nSize
0x180025959  mov     [rdi+10h], rax
0x18002595d  mov     r8, rdi; lpBuffer
0x180025960  mov     eax, [rbx+18h]
0x180025963  mov     [rdi+18h], eax
0x180025966  mov     eax, [rbx+1Ch]
0x180025969  mov     [rdi+1Ch], eax
0x18002596c  mov     rax, [rbx+20h]
0x180025970  mov     [rdi+20h], rax
0x180025974  mov     [rsp+58h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x18002597d  call    cs:__imp_WriteProcessMemory
0x180025983  test    eax, eax
0x180025985  jz      short loc_1800259F9
0x180025987  mov     r9, [rbp+lpBaseAddress]; lParam
0x18002598b  mov     r8, r12; wParam
0x18002598e  mov     edx, 133Ch; Msg
0x180025993  mov     rcx, r15; hWnd
0x180025996  call    cs:__imp_SendMessageW
0x18002599c  test    rax, rax
0x18002599f  jz      short loc_1800259F9
0x1800259a1  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x1800259a5  mov     r9d, esi; nSize
0x1800259a8  mov     rcx, [rbp+hProcess]; hProcess
0x1800259ac  mov     r8, rdi; lpBuffer
0x1800259af  mov     [rsp+58h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x1800259b8  call    cs:__imp_ReadProcessMemory
0x1800259be  test    eax, eax
0x1800259c0  jz      short loc_1800259F9
0x1800259c2  mov     eax, [rdi+4]
0x1800259c5  lea     r9d, [rsi-27h]; int
0x1800259c9  mov     rdx, [rbx+10h]; void *
0x1800259cd  lea     rcx, [rbp+var_28]; this
0x1800259d1  mov     [rbx+4], eax
0x1800259d4  mov     eax, [rdi+8]
0x1800259d7  mov     [rbx+8], eax
0x1800259da  mov     eax, [rdi+1Ch]
0x1800259dd  mov     [rbx+1Ch], eax
0x1800259e0  mov     rax, [rdi+20h]
0x1800259e4  mov     [rbx+20h], rax
0x1800259e8  mov     r8, [rdi+10h]; void *
0x1800259ec  call    ?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z; CXSendHelper::ReadExtra(void *,void *,int)
0x1800259f1  test    eax, eax
0x1800259f3  jz      short loc_1800259F9
0x1800259f5  xor     ebx, ebx
0x1800259f7  jmp     short loc_1800259FE
0x1800259f9  mov     ebx, 80004005h
0x1800259fe  lea     rcx, [rbp+var_28]; this
0x180025a02  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x180025a07  mov     eax, ebx
0x180025a09  add     rsp, 58h
0x180025a0d  pop     r15
0x180025a0f  pop     r12
0x180025a11  pop     rdi
0x180025a12  pop     rsi
0x180025a13  pop     rbx
0x180025a14  pop     rbp
0x180025a15  retn
```
