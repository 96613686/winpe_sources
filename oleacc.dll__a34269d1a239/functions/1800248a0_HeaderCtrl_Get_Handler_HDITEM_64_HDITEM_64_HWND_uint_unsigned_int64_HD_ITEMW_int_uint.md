# HeaderCtrl_Get_Handler<HDITEM_64>(HDITEM_64 &,HWND__ *,uint,unsigned __int64,_HD_ITEMW *,int,uint)

- ea: `0x1800248a0`
- end: `0x1800249fe`
- name: `??$HeaderCtrl_Get_Handler@UHDITEM_64@@@@YAJAEAUHDITEM_64@@PEAUHWND__@@I_KPEAU_HD_ITEMW@@HI@Z`
- size: `350`
- prototype: `__int64 __usercall@<rax>(LPVOID lpBuffer@<rcx>, HWND@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180026150`

## callees

- `0x1800248a0`
- `0x180025fd0`
- `0x18002604c`
- `0x180026090`
- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180024992`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180024992`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180024953`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180024953`
- `USER32!SendMessageW` at `0x180024970`
- `USER32!SendMessageW` at `0x180024970`

## pseudocode

```c
__int64 __fastcall HeaderCtrl_Get_Handler<HDITEM_64>(LPVOID lpBuffer, HWND a2, __int64 a3, WPARAM a4, __int64 a5)
{
  __int64 v5; // rdi
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
  if ( (*(_BYTE *)a5 & 2) != 0 )
  {
    result = PlusOneTimesTchar(*(_DWORD *)(a5 + 24), &v22);
    if ( (int)result < 0 )
      return result;
    v7 = v22;
  }
  lpBaseAddress = 0;
  v17 = &CXSendHelper::`vftable';
  if ( CXSendHelper::Alloc((CXSendHelper *)&v17, a2, 48, v7) )
  {
    v12 = v21 == 0;
    *(_DWORD *)lpBuffer = *(_DWORD *)v5;
    if ( v12 )
      v13 = 0;
    else
      v13 = (char *)lpBaseAddress + v20;
    v14 = lpBaseAddress;
    v15 = hProcess;
    *((_QWORD *)lpBuffer + 1) = v13;
    *((_DWORD *)lpBuffer + 6) = *(_DWORD *)(v5 + 24);
    if ( WriteProcessMemory(v15, v14, lpBuffer, 0x30u, 0)
      && SendMessageW(a2, 0x120Bu, a4, (LPARAM)lpBaseAddress)
      && ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x30u, 0)
      && (v16 = *(char **)(v5 + 8),
          *(_DWORD *)(v5 + 4) = *((_DWORD *)lpBuffer + 1),
          *(_QWORD *)(v5 + 16) = *((_QWORD *)lpBuffer + 2),
          *(_DWORD *)(v5 + 28) = *((_DWORD *)lpBuffer + 7),
          *(_QWORD *)(v5 + 32) = *((_QWORD *)lpBuffer + 4),
          *(_DWORD *)(v5 + 40) = *((_DWORD *)lpBuffer + 10),
          *(_DWORD *)(v5 + 44) = *((_DWORD *)lpBuffer + 11),
          (unsigned int)CXSendHelper::ReadExtra((CXSendHelper *)&v17, v16, *((void **)lpBuffer + 1), 1)) )
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
0x1800248a0  mov     [rsp-30h+arg_10], r8d
0x1800248a5  push    rbp
0x1800248a6  push    rbx
0x1800248a7  push    rsi
0x1800248a8  push    rdi
0x1800248a9  push    r12
0x1800248ab  push    r15
0x1800248ad  mov     rbp, rsp
0x1800248b0  sub     rsp, 58h
0x1800248b4  mov     rdi, [rbp+arg_20]
0x1800248b8  mov     r12, r9
0x1800248bb  xor     r9d, r9d
0x1800248be  mov     r15, rdx
0x1800248c1  mov     rbx, rcx
0x1800248c4  mov     [rbp+arg_10], r9d
0x1800248c8  test    byte ptr [rdi], 2
0x1800248cb  jz      short loc_1800248E5
0x1800248cd  mov     ecx, [rdi+18h]; unsigned int
0x1800248d0  lea     rdx, [rbp+arg_10]; unsigned int *
0x1800248d4  call    ?PlusOneTimesTchar@@YAJKPEAK@Z; PlusOneTimesTchar(ulong,ulong *)
0x1800248d9  test    eax, eax
0x1800248db  js      loc_1800249F1
0x1800248e1  mov     r9d, [rbp+arg_10]; unsigned int
0x1800248e5  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x1800248ec  mov     [rbp+lpBaseAddress], 0
0x1800248f4  mov     r8d, 30h ; '0'; unsigned int
0x1800248fa  mov     [rbp+var_28], rax
0x1800248fe  mov     rdx, r15; HWND
0x180024901  lea     rcx, [rbp+var_28]; this
0x180024905  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x18002490a  test    eax, eax
0x18002490c  jnz     short loc_180024918
0x18002490e  mov     ebx, 8007000Eh
0x180024913  jmp     loc_1800249E6
0x180024918  cmp     [rbp+var_C], 0
0x18002491c  mov     eax, [rdi]
0x18002491e  mov     [rbx], eax
0x180024920  jnz     short loc_180024926
0x180024922  xor     eax, eax
0x180024924  jmp     short loc_18002492D
0x180024926  mov     eax, [rbp+var_10]
0x180024929  add     rax, [rbp+lpBaseAddress]
0x18002492d  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180024931  mov     esi, 30h ; '0'
0x180024936  mov     rcx, [rbp+hProcess]; hProcess
0x18002493a  mov     r9d, esi; nSize
0x18002493d  mov     [rbx+8], rax
0x180024941  mov     r8, rbx; lpBuffer
0x180024944  mov     eax, [rdi+18h]
0x180024947  mov     [rbx+18h], eax
0x18002494a  mov     [rsp+58h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180024953  call    cs:__imp_WriteProcessMemory
0x180024959  test    eax, eax
0x18002495b  jz      loc_1800249E1
0x180024961  mov     r9, [rbp+lpBaseAddress]; lParam
0x180024965  mov     r8, r12; wParam
0x180024968  mov     edx, 120Bh; Msg
0x18002496d  mov     rcx, r15; hWnd
0x180024970  call    cs:__imp_SendMessageW
0x180024976  test    rax, rax
0x180024979  jz      short loc_1800249E1
0x18002497b  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x18002497f  mov     r9d, esi; nSize
0x180024982  mov     rcx, [rbp+hProcess]; hProcess
0x180024986  mov     r8, rbx; lpBuffer
0x180024989  mov     [rsp+58h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180024992  call    cs:__imp_ReadProcessMemory
0x180024998  test    eax, eax
0x18002499a  jz      short loc_1800249E1
0x18002499c  mov     eax, [rbx+4]
0x18002499f  lea     r9d, [rsi-2Fh]; int
0x1800249a3  mov     rdx, [rdi+8]; void *
0x1800249a7  lea     rcx, [rbp+var_28]; this
0x1800249ab  mov     [rdi+4], eax
0x1800249ae  mov     rax, [rbx+10h]
0x1800249b2  mov     [rdi+10h], rax
0x1800249b6  mov     eax, [rbx+1Ch]
0x1800249b9  mov     [rdi+1Ch], eax
0x1800249bc  mov     rax, [rbx+20h]
0x1800249c0  mov     [rdi+20h], rax
0x1800249c4  mov     eax, [rbx+28h]
0x1800249c7  mov     [rdi+28h], eax
0x1800249ca  mov     eax, [rbx+2Ch]
0x1800249cd  mov     [rdi+2Ch], eax
0x1800249d0  mov     r8, [rbx+8]; void *
0x1800249d4  call    ?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z; CXSendHelper::ReadExtra(void *,void *,int)
0x1800249d9  test    eax, eax
0x1800249db  jz      short loc_1800249E1
0x1800249dd  xor     ebx, ebx
0x1800249df  jmp     short loc_1800249E6
0x1800249e1  mov     ebx, 80004005h
0x1800249e6  lea     rcx, [rbp+var_28]; this
0x1800249ea  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x1800249ef  mov     eax, ebx
0x1800249f1  add     rsp, 58h
0x1800249f5  pop     r15
0x1800249f7  pop     r12
0x1800249f9  pop     rdi
0x1800249fa  pop     rsi
0x1800249fb  pop     rbx
0x1800249fc  pop     rbp
0x1800249fd  retn
```
