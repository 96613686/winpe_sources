# HeaderCtrl_Get_Handler<HDITEM_32>(HDITEM_32 &,HWND__ *,uint,unsigned __int64,_HD_ITEMW *,int,uint)

- ea: `0x18002473c`
- end: `0x180024899`
- name: `??$HeaderCtrl_Get_Handler@UHDITEM_32@@@@YAJAEAUHDITEM_32@@PEAUHWND__@@I_KPEAU_HD_ITEMW@@HI@Z`
- size: `349`
- prototype: `__int64 __usercall@<rax>(LPVOID lpBuffer@<rcx>, HWND@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180026150`

## callees

- `0x18002473c`
- `0x180025fd0`
- `0x18002604c`
- `0x180026090`
- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002482d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002482d`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800247ee`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800247ee`
- `USER32!SendMessageW` at `0x18002480b`
- `USER32!SendMessageW` at `0x18002480b`

## pseudocode

```c
__int64 __fastcall HeaderCtrl_Get_Handler<HDITEM_32>(int *lpBuffer, HWND a2, __int64 a3, WPARAM a4, __int64 a5)
{
  __int64 v5; // rdi
  unsigned int v7; // r9d
  __int64 result; // rax
  unsigned int v11; // ebx
  bool v12; // zf
  int v13; // eax
  void *v14; // rdx
  HANDLE v15; // rcx
  char *v16; // rdx
  void **v17; // [rsp+30h] [rbp-28h] BYREF
  LPVOID lpBaseAddress; // [rsp+38h] [rbp-20h]
  HANDLE hProcess; // [rsp+40h] [rbp-18h]
  int v20; // [rsp+48h] [rbp-10h]
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
  if ( CXSendHelper::Alloc((CXSendHelper *)&v17, a2, 36, v7) )
  {
    v12 = v21 == 0;
    *lpBuffer = *(_DWORD *)v5;
    if ( v12 )
      v13 = 0;
    else
      v13 = (_DWORD)lpBaseAddress + v20;
    v14 = lpBaseAddress;
    v15 = hProcess;
    lpBuffer[2] = v13;
    lpBuffer[4] = *(_DWORD *)(v5 + 24);
    if ( WriteProcessMemory(v15, v14, lpBuffer, 0x24u, 0)
      && SendMessageW(a2, 0x120Bu, a4, (LPARAM)lpBaseAddress)
      && ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x24u, 0)
      && (v16 = *(char **)(v5 + 8),
          *(_DWORD *)(v5 + 4) = lpBuffer[1],
          *(_QWORD *)(v5 + 16) = lpBuffer[3],
          *(_DWORD *)(v5 + 28) = lpBuffer[5],
          *(_QWORD *)(v5 + 32) = lpBuffer[6],
          *(_DWORD *)(v5 + 40) = lpBuffer[7],
          *(_DWORD *)(v5 + 44) = lpBuffer[8],
          (unsigned int)CXSendHelper::ReadExtra((CXSendHelper *)&v17, v16, (void *)(unsigned int)lpBuffer[2], 1)) )
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
0x18002473c  mov     [rsp-30h+arg_10], r8d
0x180024741  push    rbp
0x180024742  push    rbx
0x180024743  push    rsi
0x180024744  push    rdi
0x180024745  push    r12
0x180024747  push    r15
0x180024749  mov     rbp, rsp
0x18002474c  sub     rsp, 58h
0x180024750  mov     rdi, [rbp+arg_20]
0x180024754  mov     r12, r9
0x180024757  xor     r9d, r9d
0x18002475a  mov     r15, rdx
0x18002475d  mov     rbx, rcx
0x180024760  mov     [rbp+arg_10], r9d
0x180024764  test    byte ptr [rdi], 2
0x180024767  jz      short loc_180024781
0x180024769  mov     ecx, [rdi+18h]; unsigned int
0x18002476c  lea     rdx, [rbp+arg_10]; unsigned int *
0x180024770  call    ?PlusOneTimesTchar@@YAJKPEAK@Z; PlusOneTimesTchar(ulong,ulong *)
0x180024775  test    eax, eax
0x180024777  js      loc_18002488C
0x18002477d  mov     r9d, [rbp+arg_10]; unsigned int
0x180024781  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x180024788  mov     [rbp+lpBaseAddress], 0
0x180024790  mov     r8d, 24h ; '$'; unsigned int
0x180024796  mov     [rbp+var_28], rax
0x18002479a  mov     rdx, r15; HWND
0x18002479d  lea     rcx, [rbp+var_28]; this
0x1800247a1  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x1800247a6  test    eax, eax
0x1800247a8  jnz     short loc_1800247B4
0x1800247aa  mov     ebx, 8007000Eh
0x1800247af  jmp     loc_180024881
0x1800247b4  cmp     [rbp+var_C], 0
0x1800247b8  mov     eax, [rdi]
0x1800247ba  mov     [rbx], eax
0x1800247bc  jnz     short loc_1800247C2
0x1800247be  xor     eax, eax
0x1800247c0  jmp     short loc_1800247C9
0x1800247c2  mov     eax, [rbp+var_10]
0x1800247c5  add     rax, [rbp+lpBaseAddress]
0x1800247c9  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x1800247cd  mov     esi, 24h ; '$'
0x1800247d2  mov     rcx, [rbp+hProcess]; hProcess
0x1800247d6  mov     r9d, esi; nSize
0x1800247d9  mov     [rbx+8], eax
0x1800247dc  mov     r8, rbx; lpBuffer
0x1800247df  mov     eax, [rdi+18h]
0x1800247e2  mov     [rbx+10h], eax
0x1800247e5  mov     [rsp+58h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x1800247ee  call    cs:__imp_WriteProcessMemory
0x1800247f4  test    eax, eax
0x1800247f6  jz      loc_18002487C
0x1800247fc  mov     r9, [rbp+lpBaseAddress]; lParam
0x180024800  mov     r8, r12; wParam
0x180024803  mov     edx, 120Bh; Msg
0x180024808  mov     rcx, r15; hWnd
0x18002480b  call    cs:__imp_SendMessageW
0x180024811  test    rax, rax
0x180024814  jz      short loc_18002487C
0x180024816  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x18002481a  mov     r9d, esi; nSize
0x18002481d  mov     rcx, [rbp+hProcess]; hProcess
0x180024821  mov     r8, rbx; lpBuffer
0x180024824  mov     [rsp+58h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x18002482d  call    cs:__imp_ReadProcessMemory
0x180024833  test    eax, eax
0x180024835  jz      short loc_18002487C
0x180024837  mov     eax, [rbx+4]
0x18002483a  lea     r9d, [rsi-23h]; int
0x18002483e  mov     rdx, [rdi+8]; void *
0x180024842  lea     rcx, [rbp+var_28]; this
0x180024846  mov     [rdi+4], eax
0x180024849  movsxd  rax, dword ptr [rbx+0Ch]
0x18002484d  mov     [rdi+10h], rax
0x180024851  mov     eax, [rbx+14h]
0x180024854  mov     [rdi+1Ch], eax
0x180024857  movsxd  rax, dword ptr [rbx+18h]
0x18002485b  mov     [rdi+20h], rax
0x18002485f  mov     eax, [rbx+1Ch]
0x180024862  mov     [rdi+28h], eax
0x180024865  mov     eax, [rbx+20h]
0x180024868  mov     [rdi+2Ch], eax
0x18002486b  mov     r8d, [rbx+8]; void *
0x18002486f  call    ?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z; CXSendHelper::ReadExtra(void *,void *,int)
0x180024874  test    eax, eax
0x180024876  jz      short loc_18002487C
0x180024878  xor     ebx, ebx
0x18002487a  jmp     short loc_180024881
0x18002487c  mov     ebx, 80004005h
0x180024881  lea     rcx, [rbp+var_28]; this
0x180024885  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x18002488a  mov     eax, ebx
0x18002488c  add     rsp, 58h
0x180024890  pop     r15
0x180024892  pop     r12
0x180024894  pop     rdi
0x180024895  pop     rsi
0x180024896  pop     rbx
0x180024897  pop     rbp
0x180024898  retn
```
