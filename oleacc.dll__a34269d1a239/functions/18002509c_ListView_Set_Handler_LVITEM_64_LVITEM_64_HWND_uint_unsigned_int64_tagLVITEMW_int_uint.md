# ListView_Set_Handler<LVITEM_64>(LVITEM_64 &,HWND__ *,uint,unsigned __int64,tagLVITEMW *,int,uint)

- ea: `0x18002509c`
- end: `0x1800251cf`
- name: `??$ListView_Set_Handler@ULVITEM_64@@@@YAJAEAULVITEM_64@@PEAUHWND__@@I_KPEAUtagLVITEMW@@HI@Z`
- size: `307`
- prototype: `__int64 __usercall@<rax>(LPCVOID lpBuffer@<rcx>, HWND@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180026308`

## callees

- `0x18002509c`
- `0x180025fd0`
- `0x18002604c`
- `0x180026090`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002518d`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002518d`
- `USER32!SendMessageW` at `0x1800251a7`
- `USER32!SendMessageW` at `0x1800251a7`

## pseudocode

```c
__int64 __fastcall ListView_Set_Handler<LVITEM_64>(_DWORD *lpBuffer, HWND a2, __int64 a3, WPARAM a4, __int64 a5)
{
  __int64 v5; // rbx
  unsigned int v7; // r9d
  __int64 result; // rax
  unsigned int v11; // ebx
  bool v12; // zf
  char *v13; // rax
  void *v14; // rdx
  HANDLE v15; // rcx
  void **v16; // [rsp+30h] [rbp-38h] BYREF
  LPVOID lpBaseAddress; // [rsp+38h] [rbp-30h]
  HANDLE hProcess; // [rsp+40h] [rbp-28h]
  unsigned int v19; // [rsp+48h] [rbp-20h]
  int v20; // [rsp+4Ch] [rbp-1Ch]
  unsigned int v21; // [rsp+80h] [rbp+18h] BYREF

  v5 = a5;
  v7 = 0;
  v21 = 0;
  if ( (*(_BYTE *)a5 & 1) != 0 )
  {
    result = PlusOneTimesTchar(*(_DWORD *)(a5 + 32), &v21);
    if ( (int)result < 0 )
      return result;
    v7 = v21;
  }
  lpBaseAddress = 0;
  v16 = &CXSendHelper::`vftable';
  if ( CXSendHelper::Alloc((CXSendHelper *)&v16, a2, 56, v7) )
  {
    v12 = v20 == 0;
    *lpBuffer = *(_DWORD *)v5;
    lpBuffer[1] = *(_DWORD *)(v5 + 4);
    lpBuffer[2] = *(_DWORD *)(v5 + 8);
    if ( v12 )
      v13 = 0;
    else
      v13 = (char *)lpBaseAddress + v19;
    v14 = lpBaseAddress;
    v15 = hProcess;
    *((_QWORD *)lpBuffer + 3) = v13;
    lpBuffer[8] = *(_DWORD *)(v5 + 32);
    lpBuffer[3] = *(_DWORD *)(v5 + 12);
    lpBuffer[4] = *(_DWORD *)(v5 + 16);
    lpBuffer[9] = *(_DWORD *)(v5 + 36);
    *((_QWORD *)lpBuffer + 5) = *(_QWORD *)(v5 + 40);
    lpBuffer[12] = *(_DWORD *)(v5 + 48);
    if ( WriteProcessMemory(v15, v14, lpBuffer, 0x38u, 0) )
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
0x18002509c  mov     rax, rsp
0x18002509f  mov     [rax+8], rbx
0x1800250a3  mov     [rax+10h], rsi
0x1800250a7  mov     [rax+18h], r8d
0x1800250ab  push    rdi
0x1800250ac  push    r14
0x1800250ae  push    r15
0x1800250b0  sub     rsp, 50h
0x1800250b4  mov     rbx, [rsp+68h+arg_20]
0x1800250bc  mov     r15, r9
0x1800250bf  xor     r9d, r9d
0x1800250c2  mov     r14, rdx
0x1800250c5  mov     rdi, rcx
0x1800250c8  mov     [rax+18h], r9d
0x1800250cc  test    byte ptr [rbx], 1
0x1800250cf  jz      short loc_1800250ED
0x1800250d1  mov     ecx, [rbx+20h]; unsigned int
0x1800250d4  lea     rdx, [rax+18h]; unsigned int *
0x1800250d8  call    ?PlusOneTimesTchar@@YAJKPEAK@Z; PlusOneTimesTchar(ulong,ulong *)
0x1800250dd  test    eax, eax
0x1800250df  js      loc_1800251BB
0x1800250e5  mov     r9d, [rsp+68h+arg_10]; unsigned int
0x1800250ed  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x1800250f4  mov     [rsp+68h+lpBaseAddress], 0
0x1800250fd  mov     r8d, 38h ; '8'; unsigned int
0x180025103  mov     [rsp+68h+var_38], rax
0x180025108  mov     rdx, r14; HWND
0x18002510b  lea     rcx, [rsp+68h+var_38]; this
0x180025110  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x180025115  test    eax, eax
0x180025117  jnz     short loc_180025123
0x180025119  mov     ebx, 8007000Eh
0x18002511e  jmp     loc_1800251AF
0x180025123  cmp     [rsp+68h+var_1C], 0
0x180025128  mov     eax, [rbx]
0x18002512a  mov     [rdi], eax
0x18002512c  mov     eax, [rbx+4]
0x18002512f  mov     [rdi+4], eax
0x180025132  mov     eax, [rbx+8]
0x180025135  mov     [rdi+8], eax
0x180025138  jnz     short loc_18002513E
0x18002513a  xor     eax, eax
0x18002513c  jmp     short loc_180025147
0x18002513e  mov     eax, [rsp+68h+var_20]
0x180025142  add     rax, [rsp+68h+lpBaseAddress]
0x180025147  mov     rdx, [rsp+68h+lpBaseAddress]; lpBaseAddress
0x18002514c  mov     r9d, 38h ; '8'; nSize
0x180025152  mov     rcx, [rsp+68h+hProcess]; hProcess
0x180025157  mov     r8, rdi; lpBuffer
0x18002515a  mov     [rdi+18h], rax
0x18002515e  mov     eax, [rbx+20h]
0x180025161  mov     [rdi+20h], eax
0x180025164  mov     eax, [rbx+0Ch]
0x180025167  mov     [rdi+0Ch], eax
0x18002516a  mov     eax, [rbx+10h]
0x18002516d  mov     [rdi+10h], eax
0x180025170  mov     eax, [rbx+24h]
0x180025173  mov     [rdi+24h], eax
0x180025176  mov     rax, [rbx+28h]
0x18002517a  mov     [rdi+28h], rax
0x18002517e  mov     eax, [rbx+30h]
0x180025181  mov     [rdi+30h], eax
0x180025184  mov     [rsp+68h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x18002518d  call    cs:__imp_WriteProcessMemory
0x180025193  test    eax, eax
0x180025195  jz      short loc_1800251AD
0x180025197  mov     r9, [rsp+68h+lpBaseAddress]; lParam
0x18002519c  mov     r8, r15; wParam
0x18002519f  mov     edx, 102Bh; Msg
0x1800251a4  mov     rcx, r14; hWnd
0x1800251a7  call    cs:__imp_SendMessageW
0x1800251ad  xor     ebx, ebx
0x1800251af  lea     rcx, [rsp+68h+var_38]; this
0x1800251b4  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x1800251b9  mov     eax, ebx
0x1800251bb  mov     rbx, [rsp+68h+arg_0]
0x1800251c0  mov     rsi, [rsp+68h+arg_8]
0x1800251c5  add     rsp, 50h
0x1800251c9  pop     r15
0x1800251cb  pop     r14
0x1800251cd  pop     rdi
0x1800251ce  retn
```
