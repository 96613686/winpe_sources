# LoadPeerDistDll

- ea: `0x180083acc`
- end: `0x180083c83`
- name: `LoadPeerDistDll`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180035cbc`

## callees

- `0x180039fb4`
- `0x180083acc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083b0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083b0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083b20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083b34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083b48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083b5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083b70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083b84`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083b98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083bac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083bc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083bd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083be8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083bfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083c10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083b20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083b34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083b48`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083b5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083b70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083b84`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083b98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083bac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083bc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083bd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083be8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083bfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083c10`
- `KERNEL32!LoadLibraryExW` at `0x180083af8`
- `KERNEL32!LoadLibraryExW` at `0x180083af8`

## string_xrefs

- `0x180083aeb`: `PeerDist.dll`
- `0x180083b9e`: `PeerDistClientOpenContent`
- `0x180083bda`: `PeerDistClientCompleteContentInformation`
- `0x180083c02`: `PeerDistClientBlockRead`

## pseudocode

```c
DWORD __fastcall LoadPeerDistDll(HMODULE *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rax

  memset_0(a1, 0, 0x70u);
  Library = LoadLibraryExW(L"PeerDist.dll", 0, 0x800u);
  *a1 = Library;
  v3 = Library;
  if ( !Library )
    return GetLastError();
  a1[1] = (HMODULE)GetProcAddress(Library, "PeerDistStartup");
  a1[2] = (HMODULE)GetProcAddress(v3, "PeerDistShutdown");
  a1[3] = (HMODULE)GetProcAddress(v3, "PeerDistGetStatusEx");
  a1[4] = (HMODULE)GetProcAddress(v3, "PeerDistRegisterForStatusChangeNotificationEx");
  a1[5] = (HMODULE)GetProcAddress(v3, "PeerDistUnregisterForStatusChangeNotification");
  a1[6] = (HMODULE)GetProcAddress(v3, "PeerDistServerRetrieveContentInformation");
  a1[7] = (HMODULE)GetProcAddress(v3, "PeerDistServerCloseContentInformation");
  a1[8] = (HMODULE)GetProcAddress(v3, "PeerDistClientOpenContent");
  a1[9] = (HMODULE)GetProcAddress(v3, "PeerDistClientCloseContent");
  a1[10] = (HMODULE)GetProcAddress(v3, "PeerDistClientAddContentInformation");
  a1[11] = (HMODULE)GetProcAddress(v3, "PeerDistClientCompleteContentInformation");
  a1[12] = (HMODULE)GetProcAddress(v3, "PeerDistClientAddData");
  ProcAddress = GetProcAddress(v3, "PeerDistClientBlockRead");
  a1[13] = (HMODULE)ProcAddress;
  if ( a1[1] && a1[2] && a1[3] && a1[4] && a1[5] && a1[6] && a1[7] && a1[8] && a1[9] && a1[10] && a1[11] && a1[12] )
    return ProcAddress == 0 ? 0x7F : 0;
  else
    return 127;
}

```

## disassembly

```asm
0x180083acc  mov     [rsp+arg_0], rbx
0x180083ad1  mov     [rsp+arg_8], rsi
0x180083ad6  push    rdi
0x180083ad7  sub     rsp, 20h
0x180083adb  xor     edx, edx; Val
0x180083add  mov     rbx, rcx
0x180083ae0  lea     r8d, [rdx+70h]; Size
0x180083ae4  call    memset_0
0x180083ae9  xor     edx, edx; hFile
0x180083aeb  lea     rcx, LibFileName; "PeerDist.dll"
0x180083af2  mov     r8d, 800h; dwFlags
0x180083af8  call    cs:__imp_LoadLibraryExW
0x180083afe  xor     esi, esi
0x180083b00  mov     [rbx], rax
0x180083b03  mov     rdi, rax
0x180083b06  test    rax, rax
0x180083b09  jnz     short loc_180083B16
0x180083b0b  call    cs:__imp_GetLastError
0x180083b11  jmp     loc_180083C73
0x180083b16  lea     rdx, ProcName; "PeerDistStartup"
0x180083b1d  mov     rcx, rdi; hModule
0x180083b20  call    cs:__imp_GetProcAddress
0x180083b26  lea     rdx, aPeerdistshutdo; "PeerDistShutdown"
0x180083b2d  mov     rcx, rdi; hModule
0x180083b30  mov     [rbx+8], rax
0x180083b34  call    cs:__imp_GetProcAddress
0x180083b3a  lea     rdx, aPeerdistgetsta; "PeerDistGetStatusEx"
0x180083b41  mov     rcx, rdi; hModule
0x180083b44  mov     [rbx+10h], rax
0x180083b48  call    cs:__imp_GetProcAddress
0x180083b4e  lea     rdx, aPeerdistregist; "PeerDistRegisterForStatusChangeNotifica"...
0x180083b55  mov     rcx, rdi; hModule
0x180083b58  mov     [rbx+18h], rax
0x180083b5c  call    cs:__imp_GetProcAddress
0x180083b62  lea     rdx, aPeerdistunregi; "PeerDistUnregisterForStatusChangeNotifi"...
0x180083b69  mov     rcx, rdi; hModule
0x180083b6c  mov     [rbx+20h], rax
0x180083b70  call    cs:__imp_GetProcAddress
0x180083b76  lea     rdx, aPeerdistserver_0; "PeerDistServerRetrieveContentInformatio"...
0x180083b7d  mov     rcx, rdi; hModule
0x180083b80  mov     [rbx+28h], rax
0x180083b84  call    cs:__imp_GetProcAddress
0x180083b8a  lea     rdx, aPeerdistserver; "PeerDistServerCloseContentInformation"
0x180083b91  mov     rcx, rdi; hModule
0x180083b94  mov     [rbx+30h], rax
0x180083b98  call    cs:__imp_GetProcAddress
0x180083b9e  lea     rdx, aPeerdistclient_1; "PeerDistClientOpenContent"
0x180083ba5  mov     rcx, rdi; hModule
0x180083ba8  mov     [rbx+38h], rax
0x180083bac  call    cs:__imp_GetProcAddress
0x180083bb2  lea     rdx, aPeerdistclient_2; "PeerDistClientCloseContent"
0x180083bb9  mov     rcx, rdi; hModule
0x180083bbc  mov     [rbx+40h], rax
0x180083bc0  call    cs:__imp_GetProcAddress
0x180083bc6  lea     rdx, aPeerdistclient_0; "PeerDistClientAddContentInformation"
0x180083bcd  mov     rcx, rdi; hModule
0x180083bd0  mov     [rbx+48h], rax
0x180083bd4  call    cs:__imp_GetProcAddress
0x180083bda  lea     rdx, aPeerdistclient_3; "PeerDistClientCompleteContentInformatio"...
0x180083be1  mov     rcx, rdi; hModule
0x180083be4  mov     [rbx+50h], rax
0x180083be8  call    cs:__imp_GetProcAddress
0x180083bee  lea     rdx, aPeerdistclient_4; "PeerDistClientAddData"
0x180083bf5  mov     rcx, rdi; hModule
0x180083bf8  mov     [rbx+58h], rax
0x180083bfc  call    cs:__imp_GetProcAddress
0x180083c02  lea     rdx, aPeerdistclient; "PeerDistClientBlockRead"
0x180083c09  mov     rcx, rdi; hModule
0x180083c0c  mov     [rbx+60h], rax
0x180083c10  call    cs:__imp_GetProcAddress
0x180083c16  mov     [rbx+68h], rax
0x180083c1a  cmp     [rbx+8], rsi
0x180083c1e  jz      short loc_180083C6E
0x180083c20  cmp     [rbx+10h], rsi
0x180083c24  jz      short loc_180083C6E
0x180083c26  cmp     [rbx+18h], rsi
0x180083c2a  jz      short loc_180083C6E
0x180083c2c  cmp     [rbx+20h], rsi
0x180083c30  jz      short loc_180083C6E
0x180083c32  cmp     [rbx+28h], rsi
0x180083c36  jz      short loc_180083C6E
0x180083c38  cmp     [rbx+30h], rsi
0x180083c3c  jz      short loc_180083C6E
0x180083c3e  cmp     [rbx+38h], rsi
0x180083c42  jz      short loc_180083C6E
0x180083c44  cmp     [rbx+40h], rsi
0x180083c48  jz      short loc_180083C6E
0x180083c4a  cmp     [rbx+48h], rsi
0x180083c4e  jz      short loc_180083C6E
0x180083c50  cmp     [rbx+50h], rsi
0x180083c54  jz      short loc_180083C6E
0x180083c56  cmp     [rbx+58h], rsi
0x180083c5a  jz      short loc_180083C6E
0x180083c5c  cmp     [rbx+60h], rsi
0x180083c60  jz      short loc_180083C6E
0x180083c62  neg     rax
0x180083c65  sbb     eax, eax
0x180083c67  not     eax
0x180083c69  and     eax, 7Fh
0x180083c6c  jmp     short loc_180083C73
0x180083c6e  mov     eax, 7Fh
0x180083c73  mov     rbx, [rsp+28h+arg_0]
0x180083c78  mov     rsi, [rsp+28h+arg_8]
0x180083c7d  add     rsp, 20h
0x180083c81  pop     rdi
0x180083c82  retn
```
