# ListView_Set_Handler<LVITEM_32>(LVITEM_32 &,HWND__ *,uint,unsigned __int64,tagLVITEMW *,int,uint)

- ea: `0x180024f64`
- end: `0x180025094`
- name: `??$ListView_Set_Handler@ULVITEM_32@@@@YAJAEAULVITEM_32@@PEAUHWND__@@I_KPEAUtagLVITEMW@@HI@Z`
- size: `304`
- prototype: `__int64 __usercall@<rax>(LPCVOID lpBuffer@<rcx>, HWND@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180026308`

## callees

- `0x180024f64`
- `0x180025fd0`
- `0x18002604c`
- `0x180026090`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180025052`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180025052`
- `USER32!SendMessageW` at `0x18002506c`
- `USER32!SendMessageW` at `0x18002506c`

## pseudocode

```c
__int64 __fastcall ListView_Set_Handler<LVITEM_32>(_DWORD *lpBuffer, HWND a2, __int64 a3, WPARAM a4, _DWORD *a5)
{
  _DWORD *v5; // rbx
  unsigned int v7; // r9d
  __int64 result; // rax
  unsigned int v11; // ebx
  bool v12; // zf
  int v13; // eax
  void *v14; // rdx
  HANDLE v15; // rcx
  void **v16; // [rsp+30h] [rbp-38h] BYREF
  LPVOID lpBaseAddress; // [rsp+38h] [rbp-30h]
  HANDLE hProcess; // [rsp+40h] [rbp-28h]
  int v19; // [rsp+48h] [rbp-20h]
  int v20; // [rsp+4Ch] [rbp-1Ch]
  unsigned int v21; // [rsp+80h] [rbp+18h] BYREF

  v5 = a5;
  v7 = 0;
  v21 = 0;
  if ( (*(_BYTE *)a5 & 1) != 0 )
  {
    result = PlusOneTimesTchar(a5[8], &v21);
    if ( (int)result < 0 )
      return result;
    v7 = v21;
  }
  lpBaseAddress = 0;
  v16 = &CXSendHelper::`vftable';
  if ( CXSendHelper::Alloc((CXSendHelper *)&v16, a2, 40, v7) )
  {
    v12 = v20 == 0;
    *lpBuffer = *v5;
    lpBuffer[1] = v5[1];
    lpBuffer[2] = v5[2];
    if ( v12 )
      v13 = 0;
    else
      v13 = (_DWORD)lpBaseAddress + v19;
    v14 = lpBaseAddress;
    v15 = hProcess;
    lpBuffer[5] = v13;
    lpBuffer[6] = v5[8];
    lpBuffer[3] = v5[3];
    lpBuffer[4] = v5[4];
    lpBuffer[7] = v5[9];
    lpBuffer[8] = v5[10];
    lpBuffer[9] = v5[12];
    if ( WriteProcessMemory(v15, v14, lpBuffer, 0x28u, 0) )
      SendMessageW(a2, 0x102Bu, a4, (LPARAM)lpBaseAddress);
    v11 = 0;
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
0x180024f64  mov     rax, rsp
0x180024f67  mov     [rax+8], rbx
0x180024f6b  mov     [rax+10h], rsi
0x180024f6f  mov     [rax+18h], r8d
0x180024f73  push    rdi
0x180024f74  push    r14
0x180024f76  push    r15
0x180024f78  sub     rsp, 50h
0x180024f7c  mov     rbx, [rsp+68h+arg_20]
0x180024f84  mov     r15, r9
0x180024f87  xor     r9d, r9d
0x180024f8a  mov     r14, rdx
0x180024f8d  mov     rdi, rcx
0x180024f90  mov     [rax+18h], r9d
0x180024f94  test    byte ptr [rbx], 1
0x180024f97  jz      short loc_180024FB5
0x180024f99  mov     ecx, [rbx+20h]; unsigned int
0x180024f9c  lea     rdx, [rax+18h]; unsigned int *
0x180024fa0  call    ?PlusOneTimesTchar@@YAJKPEAK@Z; PlusOneTimesTchar(ulong,ulong *)
0x180024fa5  test    eax, eax
0x180024fa7  js      loc_180025080
0x180024fad  mov     r9d, [rsp+68h+arg_10]; unsigned int
0x180024fb5  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x180024fbc  mov     [rsp+68h+lpBaseAddress], 0
0x180024fc5  mov     r8d, 28h ; '('; unsigned int
0x180024fcb  mov     [rsp+68h+var_38], rax
0x180024fd0  mov     rdx, r14; HWND
0x180024fd3  lea     rcx, [rsp+68h+var_38]; this
0x180024fd8  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x180024fdd  test    eax, eax
0x180024fdf  jnz     short loc_180024FEB
0x180024fe1  mov     ebx, 8007000Eh
0x180024fe6  jmp     loc_180025074
0x180024feb  cmp     [rsp+68h+var_1C], 0
0x180024ff0  mov     eax, [rbx]
0x180024ff2  mov     [rdi], eax
0x180024ff4  mov     eax, [rbx+4]
0x180024ff7  mov     [rdi+4], eax
0x180024ffa  mov     eax, [rbx+8]
0x180024ffd  mov     [rdi+8], eax
0x180025000  jnz     short loc_180025006
0x180025002  xor     eax, eax
0x180025004  jmp     short loc_18002500F
0x180025006  mov     eax, [rsp+68h+var_20]
0x18002500a  add     rax, [rsp+68h+lpBaseAddress]
0x18002500f  mov     rdx, [rsp+68h+lpBaseAddress]; lpBaseAddress
0x180025014  mov     r9d, 28h ; '('; nSize
0x18002501a  mov     rcx, [rsp+68h+hProcess]; hProcess
0x18002501f  mov     r8, rdi; lpBuffer
0x180025022  mov     [rdi+14h], eax
0x180025025  mov     eax, [rbx+20h]
0x180025028  mov     [rdi+18h], eax
0x18002502b  mov     eax, [rbx+0Ch]
0x18002502e  mov     [rdi+0Ch], eax
0x180025031  mov     eax, [rbx+10h]
0x180025034  mov     [rdi+10h], eax
0x180025037  mov     eax, [rbx+24h]
0x18002503a  mov     [rdi+1Ch], eax
0x18002503d  mov     eax, [rbx+28h]
0x180025040  mov     [rdi+20h], eax
0x180025043  mov     eax, [rbx+30h]
0x180025046  mov     [rdi+24h], eax
0x180025049  mov     [rsp+68h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180025052  call    cs:__imp_WriteProcessMemory
0x180025058  test    eax, eax
0x18002505a  jz      short loc_180025072
0x18002505c  mov     r9, [rsp+68h+lpBaseAddress]; lParam
0x180025061  mov     r8, r15; wParam
0x180025064  mov     edx, 102Bh; Msg
0x180025069  mov     rcx, r14; hWnd
0x18002506c  call    cs:__imp_SendMessageW
0x180025072  xor     ebx, ebx
0x180025074  lea     rcx, [rsp+68h+var_38]; this
0x180025079  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x18002507e  mov     eax, ebx
0x180025080  mov     rbx, [rsp+68h+arg_0]
0x180025085  mov     rsi, [rsp+68h+arg_8]
0x18002508a  add     rsp, 50h
0x18002508e  pop     r15
0x180025090  pop     r14
0x180025092  pop     rdi
0x180025093  retn
```
