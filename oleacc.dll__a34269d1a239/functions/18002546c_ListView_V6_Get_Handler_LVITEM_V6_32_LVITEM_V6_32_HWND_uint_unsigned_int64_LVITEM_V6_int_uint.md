# ListView_V6_Get_Handler<LVITEM_V6_32>(LVITEM_V6_32 &,HWND__ *,uint,unsigned __int64,LVITEM_V6 *,int,uint)

- ea: `0x18002546c`
- end: `0x1800255cf`
- name: `??$ListView_V6_Get_Handler@ULVITEM_V6_32@@@@YAJAEAULVITEM_V6_32@@PEAUHWND__@@I_KPEAULVITEM_V6@@HI@Z`
- size: `355`
- prototype: `__int64 __usercall@<rax>(LPVOID lpBuffer@<rcx>, HWND hWnd@<rdx>, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800264cc`

## callees

- `0x18002546c`
- `0x180025fd0`
- `0x18002604c`
- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180025577`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180025577`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002552d`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002552d`
- `USER32!SendMessageW` at `0x180025547`
- `USER32!SendMessageW` at `0x180025547`

## pseudocode

```c
__int64 __fastcall ListView_V6_Get_Handler<LVITEM_V6_32>(
        unsigned int *lpBuffer,
        HWND hWnd,
        __int64 a3,
        __int64 a4,
        unsigned int *a5,
        int a6)
{
  unsigned __int64 v6; // r9
  unsigned int v9; // esi
  unsigned int v11; // ebx
  unsigned int v12; // eax
  void *v13; // rdx
  HANDLE v14; // rcx
  char *v15; // rdx
  void **v16; // [rsp+30h] [rbp-48h] BYREF
  LPVOID lpBaseAddress; // [rsp+38h] [rbp-40h]
  HANDLE hProcess; // [rsp+40h] [rbp-38h]
  int v19; // [rsp+48h] [rbp-30h]
  int v20; // [rsp+4Ch] [rbp-2Ch]

  LODWORD(v6) = 0;
  v9 = a5[14];
  if ( (*a5 & 0x200) != 0 )
  {
    v6 = 4LL * v9;
    if ( v6 > 0xFFFFFFFF )
      return 2147500037LL;
  }
  lpBaseAddress = 0;
  v16 = &CXSendHelper::`vftable';
  if ( CXSendHelper::Alloc((CXSendHelper *)&v16, hWnd, 52, v6) )
  {
    *lpBuffer = *a5;
    lpBuffer[1] = a5[1];
    lpBuffer[2] = a5[2];
    lpBuffer[11] = v9;
    if ( *((_QWORD *)a5 + 8) && v20 )
      v12 = (_DWORD)lpBaseAddress + v19;
    else
      v12 = 0;
    v13 = lpBaseAddress;
    v14 = hProcess;
    lpBuffer[12] = v12;
    if ( WriteProcessMemory(v14, v13, lpBuffer, 0x34u, 0)
      && (SendMessageW(hWnd, 0x104Bu, 0, (LPARAM)lpBaseAddress) || !a6)
      && ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x34u, 0)
      && ((v15 = (char *)*((_QWORD *)a5 + 8), a5[14] = lpBuffer[11], a5[13] = lpBuffer[10], !v15)
       || v9 >= lpBuffer[11]
       && (unsigned int)CXSendHelper::ReadExtra((CXSendHelper *)&v16, v15, (void *)lpBuffer[12], 0)) )
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
0x18002546c  push    rbx
0x18002546e  push    rsi
0x18002546f  push    rdi
0x180025470  push    r14
0x180025472  sub     rsp, 58h
0x180025476  mov     rdi, [rsp+78h+arg_20]
0x18002547e  xor     r9d, r9d; unsigned int
0x180025481  mov     r14, rdx
0x180025484  mov     rbx, rcx
0x180025487  test    dword ptr [rdi], 200h
0x18002548d  mov     esi, [rdi+38h]
0x180025490  jz      short loc_1800254AD
0x180025492  mov     r9d, esi
0x180025495  mov     eax, 0FFFFFFFFh
0x18002549a  shl     r9, 2
0x18002549e  cmp     r9, rax
0x1800254a1  jbe     short loc_1800254AD
0x1800254a3  mov     eax, 80004005h
0x1800254a8  jmp     loc_1800255C5
0x1800254ad  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x1800254b4  mov     [rsp+78h+lpBaseAddress], 0
0x1800254bd  mov     r8d, 34h ; '4'; unsigned int
0x1800254c3  mov     [rsp+78h+var_48], rax
0x1800254c8  lea     rcx, [rsp+78h+var_48]; this
0x1800254cd  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x1800254d2  test    eax, eax
0x1800254d4  jnz     short loc_1800254E0
0x1800254d6  mov     ebx, 8007000Eh
0x1800254db  jmp     loc_1800255B9
0x1800254e0  mov     eax, [rdi]
0x1800254e2  mov     [rbx], eax
0x1800254e4  mov     eax, [rdi+4]
0x1800254e7  mov     [rbx+4], eax
0x1800254ea  mov     eax, [rdi+8]
0x1800254ed  mov     [rbx+8], eax
0x1800254f0  mov     [rbx+2Ch], esi
0x1800254f3  cmp     qword ptr [rdi+40h], 0
0x1800254f8  jz      short loc_18002550C
0x1800254fa  cmp     [rsp+78h+var_2C], 0
0x1800254ff  jz      short loc_18002550C
0x180025501  mov     eax, [rsp+78h+var_30]
0x180025505  add     rax, [rsp+78h+lpBaseAddress]
0x18002550a  jmp     short loc_18002550E
0x18002550c  xor     eax, eax
0x18002550e  mov     rdx, [rsp+78h+lpBaseAddress]; lpBaseAddress
0x180025513  mov     r9d, 34h ; '4'; nSize
0x180025519  mov     rcx, [rsp+78h+hProcess]; hProcess
0x18002551e  mov     r8, rbx; lpBuffer
0x180025521  mov     [rbx+30h], eax
0x180025524  mov     [rsp+78h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x18002552d  call    cs:__imp_WriteProcessMemory
0x180025533  test    eax, eax
0x180025535  jz      short loc_1800255B4
0x180025537  mov     r9, [rsp+78h+lpBaseAddress]; lParam
0x18002553c  xor     r8d, r8d; wParam
0x18002553f  mov     edx, 104Bh; Msg
0x180025544  mov     rcx, r14; hWnd
0x180025547  call    cs:__imp_SendMessageW
0x18002554d  test    rax, rax
0x180025550  jnz     short loc_18002555B
0x180025552  cmp     [rsp+78h+arg_28], eax
0x180025559  jnz     short loc_1800255B4
0x18002555b  mov     rdx, [rsp+78h+lpBaseAddress]; lpBaseAddress
0x180025560  mov     r9d, 34h ; '4'; nSize
0x180025566  mov     rcx, [rsp+78h+hProcess]; hProcess
0x18002556b  mov     r8, rbx; lpBuffer
0x18002556e  mov     [rsp+78h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180025577  call    cs:__imp_ReadProcessMemory
0x18002557d  test    eax, eax
0x18002557f  jz      short loc_1800255B4
0x180025581  mov     eax, [rbx+2Ch]
0x180025584  mov     rdx, [rdi+40h]; void *
0x180025588  mov     [rdi+38h], eax
0x18002558b  mov     eax, [rbx+28h]
0x18002558e  mov     [rdi+34h], eax
0x180025591  test    rdx, rdx
0x180025594  jz      short loc_1800255B0
0x180025596  cmp     esi, [rbx+2Ch]
0x180025599  jb      short loc_1800255B4
0x18002559b  mov     r8d, [rbx+30h]; void *
0x18002559f  lea     rcx, [rsp+78h+var_48]; this
0x1800255a4  xor     r9d, r9d; int
0x1800255a7  call    ?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z; CXSendHelper::ReadExtra(void *,void *,int)
0x1800255ac  test    eax, eax
0x1800255ae  jz      short loc_1800255B4
0x1800255b0  xor     ebx, ebx
0x1800255b2  jmp     short loc_1800255B9
0x1800255b4  mov     ebx, 80004005h
0x1800255b9  lea     rcx, [rsp+78h+var_48]; this
0x1800255be  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x1800255c3  mov     eax, ebx
0x1800255c5  add     rsp, 58h
0x1800255c9  pop     r14
0x1800255cb  pop     rdi
0x1800255cc  pop     rsi
0x1800255cd  pop     rbx
0x1800255ce  retn
```
