# TabCtrl_Get_Handler<TCITEM_32>(TCITEM_32 &,HWND__ *,uint,unsigned __int64,tagTCITEMW *,int,uint)

- ea: `0x180025744`
- end: `0x1800258a7`
- name: `??$TabCtrl_Get_Handler@UTCITEM_32@@@@YAJAEAUTCITEM_32@@PEAUHWND__@@I_KPEAUtagTCITEMW@@HI@Z`
- size: `355`
- prototype: `__int64 __usercall@<rax>(LPVOID lpBuffer@<rcx>, HWND@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800265ec`

## callees

- `0x180025744`
- `0x180025fd0`
- `0x18002604c`
- `0x180026090`
- `0x1800260d0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180025849`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180025849`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002580e`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002580e`
- `USER32!SendMessageW` at `0x180025827`
- `USER32!SendMessageW` at `0x180025827`

## pseudocode

```c
__int64 __fastcall TabCtrl_Get_Handler<TCITEM_32>(int *lpBuffer, HWND a2, __int64 a3, WPARAM a4, __int64 a5)
{
  __int64 v5; // rbx
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
  if ( (*(_BYTE *)a5 & 1) != 0 )
  {
    result = PlusOneTimesTchar(*(_DWORD *)(a5 + 24), &v22);
    if ( (int)result < 0 )
      return result;
    v7 = v22;
  }
  lpBaseAddress = 0;
  v17 = &CXSendHelper::`vftable';
  if ( CXSendHelper::Alloc((CXSendHelper *)&v17, a2, 44, v7) )
  {
    v12 = v21 == 0;
    *lpBuffer = *(_DWORD *)v5;
    lpBuffer[1] = *(_DWORD *)(v5 + 4);
    lpBuffer[2] = *(_DWORD *)(v5 + 8);
    if ( v12 )
      v13 = 0;
    else
      v13 = (_DWORD)lpBaseAddress + v20;
    v14 = lpBaseAddress;
    v15 = hProcess;
    lpBuffer[3] = v13;
    lpBuffer[4] = *(_DWORD *)(v5 + 24);
    lpBuffer[5] = *(_DWORD *)(v5 + 28);
    lpBuffer[6] = *(_DWORD *)(v5 + 32);
    if ( WriteProcessMemory(v15, v14, lpBuffer, 0x1Cu, 0)
      && SendMessageW(a2, 0x133Cu, a4, (LPARAM)lpBaseAddress)
      && ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x1Cu, 0)
      && (v16 = *(char **)(v5 + 16),
          *(_DWORD *)(v5 + 4) = lpBuffer[1],
          *(_DWORD *)(v5 + 8) = lpBuffer[2],
          *(_DWORD *)(v5 + 28) = lpBuffer[5],
          *(_QWORD *)(v5 + 32) = lpBuffer[6],
          (unsigned int)CXSendHelper::ReadExtra((CXSendHelper *)&v17, v16, (void *)(unsigned int)lpBuffer[3], 1)) )
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
0x180025744  mov     [rsp-30h+arg_10], r8d
0x180025749  push    rbp
0x18002574a  push    rbx
0x18002574b  push    rsi
0x18002574c  push    rdi
0x18002574d  push    r12
0x18002574f  push    r15
0x180025751  mov     rbp, rsp
0x180025754  sub     rsp, 58h
0x180025758  mov     rbx, [rbp+arg_20]
0x18002575c  mov     r12, r9
0x18002575f  xor     r9d, r9d
0x180025762  mov     r15, rdx
0x180025765  mov     rdi, rcx
0x180025768  mov     [rbp+arg_10], r9d
0x18002576c  test    byte ptr [rbx], 1
0x18002576f  jz      short loc_180025789
0x180025771  mov     ecx, [rbx+18h]; unsigned int
0x180025774  lea     rdx, [rbp+arg_10]; unsigned int *
0x180025778  call    ?PlusOneTimesTchar@@YAJKPEAK@Z; PlusOneTimesTchar(ulong,ulong *)
0x18002577d  test    eax, eax
0x18002577f  js      loc_18002589A
0x180025785  mov     r9d, [rbp+arg_10]; unsigned int
0x180025789  lea     rax, ??_7CXSendHelper@@6B@; const CXSendHelper::`vftable'
0x180025790  mov     [rbp+lpBaseAddress], 0
0x180025798  mov     r8d, 2Ch ; ','; unsigned int
0x18002579e  mov     [rbp+var_28], rax
0x1800257a2  mov     rdx, r15; HWND
0x1800257a5  lea     rcx, [rbp+var_28]; this
0x1800257a9  call    ?Alloc@CXSendHelper@@QEAAHPEAUHWND__@@II@Z; CXSendHelper::Alloc(HWND__ *,uint,uint)
0x1800257ae  test    eax, eax
0x1800257b0  jnz     short loc_1800257BC
0x1800257b2  mov     ebx, 8007000Eh
0x1800257b7  jmp     loc_18002588F
0x1800257bc  cmp     [rbp+var_C], 0
0x1800257c0  mov     eax, [rbx]
0x1800257c2  mov     [rdi], eax
0x1800257c4  mov     eax, [rbx+4]
0x1800257c7  mov     [rdi+4], eax
0x1800257ca  mov     eax, [rbx+8]
0x1800257cd  mov     [rdi+8], eax
0x1800257d0  jnz     short loc_1800257D6
0x1800257d2  xor     eax, eax
0x1800257d4  jmp     short loc_1800257DD
0x1800257d6  mov     eax, [rbp+var_10]
0x1800257d9  add     rax, [rbp+lpBaseAddress]
0x1800257dd  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x1800257e1  mov     esi, 1Ch
0x1800257e6  mov     rcx, [rbp+hProcess]; hProcess
0x1800257ea  mov     r9d, esi; nSize
0x1800257ed  mov     [rdi+0Ch], eax
0x1800257f0  mov     r8, rdi; lpBuffer
0x1800257f3  mov     eax, [rbx+18h]
0x1800257f6  mov     [rdi+10h], eax
0x1800257f9  mov     eax, [rbx+1Ch]
0x1800257fc  mov     [rdi+14h], eax
0x1800257ff  mov     eax, [rbx+20h]
0x180025802  mov     [rdi+18h], eax
0x180025805  mov     [rsp+58h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x18002580e  call    cs:__imp_WriteProcessMemory
0x180025814  test    eax, eax
0x180025816  jz      short loc_18002588A
0x180025818  mov     r9, [rbp+lpBaseAddress]; lParam
0x18002581c  mov     r8, r12; wParam
0x18002581f  mov     edx, 133Ch; Msg
0x180025824  mov     rcx, r15; hWnd
0x180025827  call    cs:__imp_SendMessageW
0x18002582d  test    rax, rax
0x180025830  jz      short loc_18002588A
0x180025832  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x180025836  mov     r9d, esi; nSize
0x180025839  mov     rcx, [rbp+hProcess]; hProcess
0x18002583d  mov     r8, rdi; lpBuffer
0x180025840  mov     [rsp+58h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180025849  call    cs:__imp_ReadProcessMemory
0x18002584f  test    eax, eax
0x180025851  jz      short loc_18002588A
0x180025853  mov     eax, [rdi+4]
0x180025856  lea     r9d, [rsi-1Bh]; int
0x18002585a  mov     rdx, [rbx+10h]; void *
0x18002585e  lea     rcx, [rbp+var_28]; this
0x180025862  mov     [rbx+4], eax
0x180025865  mov     eax, [rdi+8]
0x180025868  mov     [rbx+8], eax
0x18002586b  mov     eax, [rdi+14h]
0x18002586e  mov     [rbx+1Ch], eax
0x180025871  movsxd  rax, dword ptr [rdi+18h]
0x180025875  mov     [rbx+20h], rax
0x180025879  mov     r8d, [rdi+0Ch]; void *
0x18002587d  call    ?ReadExtra@CXSendHelper@@QEAAHPEAX0H@Z; CXSendHelper::ReadExtra(void *,void *,int)
0x180025882  test    eax, eax
0x180025884  jz      short loc_18002588A
0x180025886  xor     ebx, ebx
0x180025888  jmp     short loc_18002588F
0x18002588a  mov     ebx, 80004005h
0x18002588f  lea     rcx, [rbp+var_28]; this
0x180025893  call    ??1CXSendHelper@@UEAA@XZ; CXSendHelper::~CXSendHelper(void)
0x180025898  mov     eax, ebx
0x18002589a  add     rsp, 58h
0x18002589e  pop     r15
0x1800258a0  pop     r12
0x1800258a2  pop     rdi
0x1800258a3  pop     rsi
0x1800258a4  pop     rbx
0x1800258a5  pop     rbp
0x1800258a6  retn
```
