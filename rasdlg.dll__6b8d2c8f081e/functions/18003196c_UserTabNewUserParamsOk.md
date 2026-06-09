# UserTabNewUserParamsOk

- ea: `0x18003196c`
- end: `0x180031be1`
- name: `UserTabNewUserParamsOk`
- size: `629`
- prototype: `__int64 __fastcall(HWND hDlg)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180030960`

## callees

- `0x18003196c`
- `0x18003d248`
- `0x18003d3fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b63`
- `samcli!NetUserModalsGet` at `0x18003199b`
- `samcli!NetUserModalsGet` at `0x18003199b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180031b29`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180031b29`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031b75`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031b75`
- `netutils!NetApiBufferFree` at `0x1800319b2`
- `netutils!NetApiBufferFree` at `0x1800319b2`
- `USER32!DialogBoxParamW` at `0x180031b58`
- `USER32!DialogBoxParamW` at `0x180031b58`
- `USER32!GetWindowTextW` at `0x1800319d8`
- `USER32!GetWindowTextW` at `0x1800319fe`
- `USER32!GetWindowTextW` at `0x180031a44`
- `USER32!GetWindowTextW` at `0x180031a69`
- `USER32!GetWindowTextW` at `0x1800319d8`
- `USER32!GetWindowTextW` at `0x1800319fe`
- `USER32!GetWindowTextW` at `0x180031a44`
- `USER32!GetWindowTextW` at `0x180031a69`
- `USER32!GetDlgItem` at `0x1800319c0`
- `USER32!GetDlgItem` at `0x1800319e6`
- `USER32!GetDlgItem` at `0x180031a0c`
- `USER32!GetDlgItem` at `0x180031a52`
- `USER32!GetDlgItem` at `0x1800319c0`
- `USER32!GetDlgItem` at `0x1800319e6`
- `USER32!GetDlgItem` at `0x180031a0c`
- `USER32!GetDlgItem` at `0x180031a52`

## string_xrefs

- `0x180031b19`: `LocalSec.dll`

## pseudocode

```c
__int64 __fastcall UserTabNewUserParamsOk(HWND hDlg, __int64 a2)
{
  unsigned int v4; // r15d
  HWND DlgItem; // rax
  HWND v6; // rax
  unsigned __int16 *v7; // rsi
  HWND v8; // r14
  HWND v9; // rax
  __int64 v10; // rax
  unsigned int v11; // edi
  __int64 v12; // rax
  int v13; // ecx
  int v14; // eax
  const wchar_t *v15; // rax
  int v16; // r8d
  int v17; // ecx
  unsigned int v18; // ebp
  HMODULE Library; // rax
  HMODULE v20; // r14
  DWORD LastError; // esi
  unsigned int v22; // eax
  LPVOID Buffer; // [rsp+68h] [rbp+10h] BYREF

  Buffer = 0;
  v4 = 0;
  if ( !NetUserModalsGet(0, 0, (LPBYTE *)&Buffer) && Buffer )
  {
    v4 = *(_DWORD *)Buffer;
    NetApiBufferFree(Buffer);
  }
  DlgItem = GetDlgItem(hDlg, 7001);
  if ( DlgItem )
    GetWindowTextW(DlgItem, (LPWSTR)(a2 + 8), 21);
  v6 = GetDlgItem(hDlg, 7002);
  if ( v6 )
    GetWindowTextW(v6, (LPWSTR)(a2 + 52), 257);
  v7 = (unsigned __int16 *)(a2 + 568);
  v8 = GetDlgItem(hDlg, 7003);
  WipeMemoryInPlace(a2 + 568);
  WipeMemoryInPlace(a2 + 1082);
  if ( v8 )
    GetWindowTextW(v8, (LPWSTR)(a2 + 568), 256);
  v9 = GetDlgItem(hDlg, 7004);
  if ( v9 )
    GetWindowTextW(v9, (LPWSTR)(a2 + 1082), 256);
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(a2 + 2 * v10 + 8) );
  v11 = 1;
  if ( !(_DWORD)v10 )
  {
    *(_DWORD *)(a2 + 1596) = 7321;
LABEL_16:
    v11 = 0;
LABEL_39:
    WipeMemoryInPlace(a2 + 568);
    WipeMemoryInPlace(a2 + 1082);
    goto LABEL_40;
  }
  v12 = -1;
  do
    ++v12;
  while ( v7[v12] );
  if ( (unsigned int)v12 < v4 )
  {
    *(_DWORD *)(a2 + 1596) = 7322;
    goto LABEL_16;
  }
  do
  {
    v13 = v7[257];
    v14 = *v7 - v13;
    if ( v14 )
      break;
    ++v7;
  }
  while ( v13 );
  if ( v14 )
  {
    *(_DWORD *)(a2 + 1596) = 7323;
    goto LABEL_16;
  }
  if ( !*(_DWORD *)(a2 + 4) )
  {
    v15 = L"XXXXXXXXXXXXXXX";
    do
    {
      v16 = *(const wchar_t *)((char *)v15 + a2 + 568 - (_QWORD)L"XXXXXXXXXXXXXXX");
      v17 = *v15 - v16;
      if ( v17 )
        break;
      ++v15;
    }
    while ( v16 );
    if ( v17 )
    {
      v18 = 0;
      Library = LoadLibraryExW(L"LocalSec.dll", 0, 0x800u);
      v20 = Library;
      if ( Library )
      {
        v22 = DialogBoxParamW(Library, (LPCWSTR)0x1436, 0, PwDlgProc, 0);
        if ( v22 == -1 )
        {
          LastError = GetLastError();
        }
        else
        {
          LastError = 0;
          v18 = v22;
        }
        FreeLibrary(v20);
      }
      else
      {
        LastError = GetLastError();
      }
      if ( !LastError )
      {
        v11 = v18;
        if ( !v18 )
        {
          *(_DWORD *)(a2 + 1596) = 1003;
          goto LABEL_39;
        }
      }
    }
  }
LABEL_40:
  EncryptMemoryInPlace((LPVOID)(a2 + 568), 0x200u);
  EncryptMemoryInPlace((LPVOID)(a2 + 1082), 0x200u);
  return v11;
}

```

## disassembly

```asm
0x18003196c  mov     rax, rsp
0x18003196f  mov     [rax+8], rbx
0x180031973  mov     [rax+18h], rbp
0x180031977  push    rsi
0x180031978  push    rdi
0x180031979  push    r12
0x18003197b  push    r14
0x18003197d  push    r15
0x18003197f  sub     rsp, 30h
0x180031983  mov     rbx, rdx
0x180031986  lea     r8, [rax+10h]; bufptr
0x18003198a  mov     rdi, rcx
0x18003198d  xor     r12d, r12d
0x180031990  xor     edx, edx; level
0x180031992  mov     [rax+10h], r12
0x180031996  xor     ecx, ecx; servername
0x180031998  mov     r15d, r12d
0x18003199b  call    cs:__imp_NetUserModalsGet
0x1800319a1  test    eax, eax
0x1800319a3  jnz     short loc_1800319B8
0x1800319a5  mov     rcx, [rsp+58h+Buffer]; Buffer
0x1800319aa  test    rcx, rcx
0x1800319ad  jz      short loc_1800319B8
0x1800319af  mov     r15d, [rcx]
0x1800319b2  call    cs:__imp_NetApiBufferFree
0x1800319b8  mov     edx, 1B59h; nIDDlgItem
0x1800319bd  mov     rcx, rdi; hDlg
0x1800319c0  call    cs:__imp_GetDlgItem
0x1800319c6  test    rax, rax
0x1800319c9  jz      short loc_1800319DE
0x1800319cb  lea     rdx, [rbx+8]; lpString
0x1800319cf  mov     r8d, 15h; nMaxCount
0x1800319d5  mov     rcx, rax; hWnd
0x1800319d8  call    cs:__imp_GetWindowTextW
0x1800319de  mov     edx, 1B5Ah; nIDDlgItem
0x1800319e3  mov     rcx, rdi; hDlg
0x1800319e6  call    cs:__imp_GetDlgItem
0x1800319ec  test    rax, rax
0x1800319ef  jz      short loc_180031A04
0x1800319f1  lea     rdx, [rbx+34h]; lpString
0x1800319f5  mov     r8d, 101h; nMaxCount
0x1800319fb  mov     rcx, rax; hWnd
0x1800319fe  call    cs:__imp_GetWindowTextW
0x180031a04  mov     edx, 1B5Bh; nIDDlgItem
0x180031a09  mov     rcx, rdi; hDlg
0x180031a0c  call    cs:__imp_GetDlgItem
0x180031a12  lea     rsi, [rbx+238h]
0x180031a19  mov     r14, rax
0x180031a1c  mov     rcx, rsi
0x180031a1f  call    WipeMemoryInPlace
0x180031a24  lea     rbp, [rbx+43Ah]
0x180031a2b  mov     rcx, rbp
0x180031a2e  call    WipeMemoryInPlace
0x180031a33  test    r14, r14
0x180031a36  jz      short loc_180031A4A
0x180031a38  mov     r8d, 100h; nMaxCount
0x180031a3e  mov     rdx, rsi; lpString
0x180031a41  mov     rcx, r14; hWnd
0x180031a44  call    cs:__imp_GetWindowTextW
0x180031a4a  mov     edx, 1B5Ch; nIDDlgItem
0x180031a4f  mov     rcx, rdi; hDlg
0x180031a52  call    cs:__imp_GetDlgItem
0x180031a58  test    rax, rax
0x180031a5b  jz      short loc_180031A6F
0x180031a5d  mov     r8d, 100h; nMaxCount
0x180031a63  mov     rdx, rbp; lpString
0x180031a66  mov     rcx, rax; hWnd
0x180031a69  call    cs:__imp_GetWindowTextW
0x180031a6f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031a73  inc     rax
0x180031a76  cmp     [rbx+rax*2+8], r12w
0x180031a7c  jnz     short loc_180031A73
0x180031a7e  mov     edi, 1
0x180031a83  cmp     eax, edi
0x180031a85  jnb     short loc_180031A99
0x180031a87  mov     dword ptr [rbx+63Ch], 1C99h
0x180031a91  mov     edi, r12d
0x180031a94  jmp     loc_180031B8F
0x180031a99  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031a9d  inc     rax
0x180031aa0  cmp     [rsi+rax*2], r12w
0x180031aa5  jnz     short loc_180031A9D
0x180031aa7  cmp     eax, r15d
0x180031aaa  jnb     short loc_180031AB8
0x180031aac  mov     dword ptr [rbx+63Ch], 1C9Ah
0x180031ab6  jmp     short loc_180031A91
0x180031ab8  sub     rbp, rsi
0x180031abb  movzx   eax, word ptr [rsi]
0x180031abe  movzx   ecx, word ptr [rsi+rbp]
0x180031ac2  sub     eax, ecx
0x180031ac4  jnz     short loc_180031ACE
0x180031ac6  add     rsi, 2
0x180031aca  test    ecx, ecx
0x180031acc  jnz     short loc_180031ABB
0x180031ace  test    eax, eax
0x180031ad0  jz      short loc_180031ADE
0x180031ad2  mov     dword ptr [rbx+63Ch], 1C9Bh
0x180031adc  jmp     short loc_180031A91
0x180031ade  cmp     [rbx+4], r12d
0x180031ae2  jnz     loc_180031BA7
0x180031ae8  lea     rdx, [rbx+238h]
0x180031aef  lea     rax, aXxxxxxxxxxxxxx; "XXXXXXXXXXXXXXX"
0x180031af6  sub     rdx, rax
0x180031af9  movzx   ecx, word ptr [rax]
0x180031afc  movzx   r8d, word ptr [rax+rdx]
0x180031b01  sub     ecx, r8d
0x180031b04  jnz     short loc_180031B0F
0x180031b06  add     rax, 2
0x180031b0a  test    r8d, r8d
0x180031b0d  jnz     short loc_180031AF9
0x180031b0f  test    ecx, ecx
0x180031b11  jz      loc_180031BA7
0x180031b17  xor     edx, edx; hFile
0x180031b19  lea     rcx, aLocalsecDll; "LocalSec.dll"
0x180031b20  mov     r8d, 800h; dwFlags
0x180031b26  mov     ebp, r12d
0x180031b29  call    cs:__imp_LoadLibraryExW
0x180031b2f  mov     r14, rax
0x180031b32  test    rax, rax
0x180031b35  jnz     short loc_180031B41
0x180031b37  call    cs:__imp_GetLastError
0x180031b3d  mov     esi, eax
0x180031b3f  jmp     short loc_180031B7B
0x180031b41  lea     r9, PwDlgProc; lpDialogFunc
0x180031b48  mov     [rsp+58h+dwInitParam], r12; dwInitParam
0x180031b4d  xor     r8d, r8d; hWndParent
0x180031b50  mov     edx, 1436h; lpTemplateName
0x180031b55  mov     rcx, r14; hInstance
0x180031b58  call    cs:__imp_DialogBoxParamW
0x180031b5e  cmp     eax, 0FFFFFFFFh
0x180031b61  jnz     short loc_180031B6D
0x180031b63  call    cs:__imp_GetLastError
0x180031b69  mov     esi, eax
0x180031b6b  jmp     short loc_180031B72
0x180031b6d  mov     esi, r12d
0x180031b70  mov     ebp, eax
0x180031b72  mov     rcx, r14; hLibModule
0x180031b75  call    cs:__imp_FreeLibrary
0x180031b7b  test    esi, esi
0x180031b7d  jnz     short loc_180031BA7
0x180031b7f  mov     edi, ebp
0x180031b81  test    ebp, ebp
0x180031b83  jnz     short loc_180031BA7
0x180031b85  mov     dword ptr [rbx+63Ch], 3EBh
0x180031b8f  lea     rcx, [rbx+238h]
0x180031b96  call    WipeMemoryInPlace
0x180031b9b  lea     rcx, [rbx+43Ah]
0x180031ba2  call    WipeMemoryInPlace
0x180031ba7  mov     esi, 200h
0x180031bac  lea     rcx, [rbx+238h]; pDataIn
0x180031bb3  mov     edx, esi; cbDataIn
0x180031bb5  call    EncryptMemoryInPlace
0x180031bba  lea     rcx, [rbx+43Ah]; pDataIn
0x180031bc1  mov     edx, esi; cbDataIn
0x180031bc3  call    EncryptMemoryInPlace
0x180031bc8  mov     rbx, [rsp+58h+arg_0]
0x180031bcd  mov     eax, edi
0x180031bcf  mov     rbp, [rsp+58h+arg_10]
0x180031bd4  add     rsp, 30h
0x180031bd8  pop     r15
0x180031bda  pop     r14
0x180031bdc  pop     r12
0x180031bde  pop     rdi
0x180031bdf  pop     rsi
0x180031be0  retn
```
