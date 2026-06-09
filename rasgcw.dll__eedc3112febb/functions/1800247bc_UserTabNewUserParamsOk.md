# UserTabNewUserParamsOk

- ea: `0x1800247bc`
- end: `0x180024a31`
- name: `UserTabNewUserParamsOk`
- size: `629`
- prototype: `__int64 __fastcall(HWND hDlg)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800237b0`

## callees

- `0x1800247bc`
- `0x18002bf2c`
- `0x18002c0e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024979`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024979`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800249c5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800249c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249b3`
- `USER32!GetDlgItem` at `0x180024810`
- `USER32!GetDlgItem` at `0x180024836`
- `USER32!GetDlgItem` at `0x18002485c`
- `USER32!GetDlgItem` at `0x1800248a2`
- `USER32!GetDlgItem` at `0x180024810`
- `USER32!GetDlgItem` at `0x180024836`
- `USER32!GetDlgItem` at `0x18002485c`
- `USER32!GetDlgItem` at `0x1800248a2`
- `USER32!GetWindowTextW` at `0x180024828`
- `USER32!GetWindowTextW` at `0x18002484e`
- `USER32!GetWindowTextW` at `0x180024894`
- `USER32!GetWindowTextW` at `0x1800248b9`
- `USER32!GetWindowTextW` at `0x180024828`
- `USER32!GetWindowTextW` at `0x18002484e`
- `USER32!GetWindowTextW` at `0x180024894`
- `USER32!GetWindowTextW` at `0x1800248b9`
- `USER32!DialogBoxParamW` at `0x1800249a8`
- `USER32!DialogBoxParamW` at `0x1800249a8`
- `samcli!NetUserModalsGet` at `0x1800247eb`
- `samcli!NetUserModalsGet` at `0x1800247eb`
- `netutils!NetApiBufferFree` at `0x180024802`
- `netutils!NetApiBufferFree` at `0x180024802`

## string_xrefs

- `0x180024969`: `LocalSec.dll`

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
0x1800247bc  mov     rax, rsp
0x1800247bf  mov     [rax+8], rbx
0x1800247c3  mov     [rax+18h], rbp
0x1800247c7  push    rsi
0x1800247c8  push    rdi
0x1800247c9  push    r12
0x1800247cb  push    r14
0x1800247cd  push    r15
0x1800247cf  sub     rsp, 30h
0x1800247d3  mov     rbx, rdx
0x1800247d6  lea     r8, [rax+10h]; bufptr
0x1800247da  mov     rdi, rcx
0x1800247dd  xor     r12d, r12d
0x1800247e0  xor     edx, edx; level
0x1800247e2  mov     [rax+10h], r12
0x1800247e6  xor     ecx, ecx; servername
0x1800247e8  mov     r15d, r12d
0x1800247eb  call    cs:__imp_NetUserModalsGet
0x1800247f1  test    eax, eax
0x1800247f3  jnz     short loc_180024808
0x1800247f5  mov     rcx, [rsp+58h+Buffer]; Buffer
0x1800247fa  test    rcx, rcx
0x1800247fd  jz      short loc_180024808
0x1800247ff  mov     r15d, [rcx]
0x180024802  call    cs:__imp_NetApiBufferFree
0x180024808  mov     edx, 1B59h; nIDDlgItem
0x18002480d  mov     rcx, rdi; hDlg
0x180024810  call    cs:__imp_GetDlgItem
0x180024816  test    rax, rax
0x180024819  jz      short loc_18002482E
0x18002481b  lea     rdx, [rbx+8]; lpString
0x18002481f  mov     r8d, 15h; nMaxCount
0x180024825  mov     rcx, rax; hWnd
0x180024828  call    cs:__imp_GetWindowTextW
0x18002482e  mov     edx, 1B5Ah; nIDDlgItem
0x180024833  mov     rcx, rdi; hDlg
0x180024836  call    cs:__imp_GetDlgItem
0x18002483c  test    rax, rax
0x18002483f  jz      short loc_180024854
0x180024841  lea     rdx, [rbx+34h]; lpString
0x180024845  mov     r8d, 101h; nMaxCount
0x18002484b  mov     rcx, rax; hWnd
0x18002484e  call    cs:__imp_GetWindowTextW
0x180024854  mov     edx, 1B5Bh; nIDDlgItem
0x180024859  mov     rcx, rdi; hDlg
0x18002485c  call    cs:__imp_GetDlgItem
0x180024862  lea     rsi, [rbx+238h]
0x180024869  mov     r14, rax
0x18002486c  mov     rcx, rsi
0x18002486f  call    WipeMemoryInPlace
0x180024874  lea     rbp, [rbx+43Ah]
0x18002487b  mov     rcx, rbp
0x18002487e  call    WipeMemoryInPlace
0x180024883  test    r14, r14
0x180024886  jz      short loc_18002489A
0x180024888  mov     r8d, 100h; nMaxCount
0x18002488e  mov     rdx, rsi; lpString
0x180024891  mov     rcx, r14; hWnd
0x180024894  call    cs:__imp_GetWindowTextW
0x18002489a  mov     edx, 1B5Ch; nIDDlgItem
0x18002489f  mov     rcx, rdi; hDlg
0x1800248a2  call    cs:__imp_GetDlgItem
0x1800248a8  test    rax, rax
0x1800248ab  jz      short loc_1800248BF
0x1800248ad  mov     r8d, 100h; nMaxCount
0x1800248b3  mov     rdx, rbp; lpString
0x1800248b6  mov     rcx, rax; hWnd
0x1800248b9  call    cs:__imp_GetWindowTextW
0x1800248bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800248c3  inc     rax
0x1800248c6  cmp     [rbx+rax*2+8], r12w
0x1800248cc  jnz     short loc_1800248C3
0x1800248ce  mov     edi, 1
0x1800248d3  cmp     eax, edi
0x1800248d5  jnb     short loc_1800248E9
0x1800248d7  mov     dword ptr [rbx+63Ch], 1C99h
0x1800248e1  mov     edi, r12d
0x1800248e4  jmp     loc_1800249DF
0x1800248e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800248ed  inc     rax
0x1800248f0  cmp     [rsi+rax*2], r12w
0x1800248f5  jnz     short loc_1800248ED
0x1800248f7  cmp     eax, r15d
0x1800248fa  jnb     short loc_180024908
0x1800248fc  mov     dword ptr [rbx+63Ch], 1C9Ah
0x180024906  jmp     short loc_1800248E1
0x180024908  sub     rbp, rsi
0x18002490b  movzx   eax, word ptr [rsi]
0x18002490e  movzx   ecx, word ptr [rsi+rbp]
0x180024912  sub     eax, ecx
0x180024914  jnz     short loc_18002491E
0x180024916  add     rsi, 2
0x18002491a  test    ecx, ecx
0x18002491c  jnz     short loc_18002490B
0x18002491e  test    eax, eax
0x180024920  jz      short loc_18002492E
0x180024922  mov     dword ptr [rbx+63Ch], 1C9Bh
0x18002492c  jmp     short loc_1800248E1
0x18002492e  cmp     [rbx+4], r12d
0x180024932  jnz     loc_1800249F7
0x180024938  lea     rdx, [rbx+238h]
0x18002493f  lea     rax, aXxxxxxxxxxxxxx; "XXXXXXXXXXXXXXX"
0x180024946  sub     rdx, rax
0x180024949  movzx   ecx, word ptr [rax]
0x18002494c  movzx   r8d, word ptr [rax+rdx]
0x180024951  sub     ecx, r8d
0x180024954  jnz     short loc_18002495F
0x180024956  add     rax, 2
0x18002495a  test    r8d, r8d
0x18002495d  jnz     short loc_180024949
0x18002495f  test    ecx, ecx
0x180024961  jz      loc_1800249F7
0x180024967  xor     edx, edx; hFile
0x180024969  lea     rcx, aLocalsecDll; "LocalSec.dll"
0x180024970  mov     r8d, 800h; dwFlags
0x180024976  mov     ebp, r12d
0x180024979  call    cs:__imp_LoadLibraryExW
0x18002497f  mov     r14, rax
0x180024982  test    rax, rax
0x180024985  jnz     short loc_180024991
0x180024987  call    cs:__imp_GetLastError
0x18002498d  mov     esi, eax
0x18002498f  jmp     short loc_1800249CB
0x180024991  lea     r9, PwDlgProc; lpDialogFunc
0x180024998  mov     [rsp+58h+dwInitParam], r12; dwInitParam
0x18002499d  xor     r8d, r8d; hWndParent
0x1800249a0  mov     edx, 1436h; lpTemplateName
0x1800249a5  mov     rcx, r14; hInstance
0x1800249a8  call    cs:__imp_DialogBoxParamW
0x1800249ae  cmp     eax, 0FFFFFFFFh
0x1800249b1  jnz     short loc_1800249BD
0x1800249b3  call    cs:__imp_GetLastError
0x1800249b9  mov     esi, eax
0x1800249bb  jmp     short loc_1800249C2
0x1800249bd  mov     esi, r12d
0x1800249c0  mov     ebp, eax
0x1800249c2  mov     rcx, r14; hLibModule
0x1800249c5  call    cs:__imp_FreeLibrary
0x1800249cb  test    esi, esi
0x1800249cd  jnz     short loc_1800249F7
0x1800249cf  mov     edi, ebp
0x1800249d1  test    ebp, ebp
0x1800249d3  jnz     short loc_1800249F7
0x1800249d5  mov     dword ptr [rbx+63Ch], 3EBh
0x1800249df  lea     rcx, [rbx+238h]
0x1800249e6  call    WipeMemoryInPlace
0x1800249eb  lea     rcx, [rbx+43Ah]
0x1800249f2  call    WipeMemoryInPlace
0x1800249f7  mov     esi, 200h
0x1800249fc  lea     rcx, [rbx+238h]; pDataIn
0x180024a03  mov     edx, esi; cbDataIn
0x180024a05  call    EncryptMemoryInPlace
0x180024a0a  lea     rcx, [rbx+43Ah]; pDataIn
0x180024a11  mov     edx, esi; cbDataIn
0x180024a13  call    EncryptMemoryInPlace
0x180024a18  mov     rbx, [rsp+58h+arg_0]
0x180024a1d  mov     eax, edi
0x180024a1f  mov     rbp, [rsp+58h+arg_10]
0x180024a24  add     rsp, 30h
0x180024a28  pop     r15
0x180024a2a  pop     r14
0x180024a2c  pop     r12
0x180024a2e  pop     rdi
0x180024a2f  pop     rsi
0x180024a30  retn
```
