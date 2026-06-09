# FindDeviceOnInterface

- ea: `0x180011698`
- end: `0x1800118e3`
- name: `FindDeviceOnInterface`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012f64`

## callees

- `0x18000d92c`
- `0x180011698`
- `0x1800292b0`

## import_xrefs

- `msvcrt!malloc` at `0x180011756`
- `msvcrt!malloc` at `0x180011756`
- `msvcrt!free` at `0x1800118bb`
- `msvcrt!free` at `0x1800118bb`
- `msvcrt!wcsstr` at `0x1800117bd`
- `msvcrt!wcsstr` at `0x1800117d2`
- `msvcrt!wcsstr` at `0x1800117bd`
- `msvcrt!wcsstr` at `0x1800117d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001173f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001180f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001186d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001173f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001180f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001186d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011887`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011853`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011853`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800116db`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800116db`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1800116e6`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1800117af`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1800116e6`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1800117af`
- `DEVOBJ!DevObjGetClassDevs` at `0x180011733`
- `DEVOBJ!DevObjGetClassDevs` at `0x180011733`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800118ad`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800118ad`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180011801`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180011801`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001179e`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001179e`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800116ff`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800116ff`

## string_xrefs

- `0x18001188f`: `FindDeviceOnInterface: DevObjCreateDeviceInfoList failed with: %d`
- `0x180011876`: `Createfile %ws failed with %d`

## pseudocode

```c
__int64 __fastcall FindDeviceOnInterface(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  __int64 DeviceInfoList; // rax
  __int64 v6; // rdi
  unsigned int v7; // esi
  WCHAR *v8; // rbx
  const CHAR *v9; // rcx
  unsigned int v10; // r14d
  __int64 i; // r9
  char *FileW; // rax
  _OWORD v14[2]; // [rsp+40h] [rbp-B8h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-98h] BYREF

  *a5 = -1;
  StringFromGUID2(&rguid, sz, 39);
  CharLowerW(sz);
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v6 = DeviceInfoList;
  if ( (unsigned __int64)(DeviceInfoList - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    GetLastError();
    RasTapiTrace("FindDeviceOnInterface: DevObjCreateDeviceInfoList failed with: %d");
    v7 = 0;
    if ( !v6 || v6 == -1 )
      return v7;
    v8 = 0;
  }
  else
  {
    v7 = 0;
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, qword_18002E758, 0, 18, 0, 0) )
    {
      v8 = (WCHAR *)malloc(0x210u);
      if ( !v8 )
        goto LABEL_20;
      v10 = 0;
      memset(v14, 0, sizeof(v14));
      for ( i = 0; ; i = v10 )
      {
        LODWORD(v14[0]) = 32;
        if ( !(unsigned int)DevObjEnumDeviceInterfaces(v6, 0, qword_18002E758, i, v14) )
          break;
        *(_DWORD *)v8 = 8;
        if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v6, v14, v8, 528, 0, 0) )
        {
          CharLowerW(v8 + 2);
          if ( wcsstr(v8 + 2, sz) )
          {
            if ( wcsstr(v8 + 2, L"asyncmac") )
            {
              FileW = (char *)CreateFileW(v8 + 2, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
              if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
              {
                GetLastError();
                RasTapiTrace("Createfile %ws failed with %d");
              }
              else
              {
                *a5 = FileW;
                v7 = 1;
              }
              goto LABEL_20;
            }
          }
        }
        ++v10;
      }
      if ( GetLastError() == 259 )
        goto LABEL_20;
      v9 = "FindDeviceOnInterface: DevObjEnumDeviceInterfaces failed, Error= %d";
    }
    else
    {
      v8 = 0;
      GetLastError();
      v9 = "FindDeviceOnInterface: DevObjGetClassDevs failed with: %d";
    }
    RasTapiTrace(v9);
  }
LABEL_20:
  DevObjDestroyDeviceInfoList(v6);
  if ( v8 )
    free(v8);
  return v7;
}

```

## disassembly

```asm
0x180011698  push    rbx
0x18001169a  push    rbp
0x18001169b  push    rsi
0x18001169c  push    rdi
0x18001169d  push    r14
0x18001169f  push    r15
0x1800116a1  sub     rsp, 0C8h
0x1800116a8  mov     rax, cs:__security_cookie
0x1800116af  xor     rax, rsp
0x1800116b2  mov     [rsp+0F8h+var_48], rax
0x1800116ba  mov     r15, [rsp+0F8h+arg_20]
0x1800116c2  lea     rdx, [rsp+0F8h+sz]; lpsz
0x1800116c7  mov     r8d, 27h ; '''; cchMax
0x1800116cd  lea     rcx, rguid; rguid
0x1800116d4  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x1800116db  call    cs:__imp_StringFromGUID2
0x1800116e1  lea     rcx, [rsp+0F8h+sz]; lpsz
0x1800116e6  call    cs:__imp_CharLowerW
0x1800116ec  xor     r9d, r9d
0x1800116ef  mov     qword ptr [rsp+0F8h+dwCreationDisposition], 0
0x1800116f8  xor     r8d, r8d
0x1800116fb  xor     edx, edx
0x1800116fd  xor     ecx, ecx
0x1800116ff  call    cs:__imp_DevObjCreateDeviceInfoList
0x180011705  mov     rdi, rax
0x180011708  lea     rcx, [rax-1]
0x18001170c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180011710  ja      loc_180011887
0x180011716  xor     esi, esi
0x180011718  lea     rdx, qword_18002E758
0x18001171f  mov     qword ptr [rsp+0F8h+dwFlagsAndAttributes], rsi
0x180011724  xor     r8d, r8d
0x180011727  mov     rcx, rax
0x18001172a  mov     qword ptr [rsp+0F8h+dwCreationDisposition], rsi
0x18001172f  lea     r9d, [rsi+12h]
0x180011733  call    cs:__imp_DevObjGetClassDevs
0x180011739  test    eax, eax
0x18001173b  jnz     short loc_180011751
0x18001173d  xor     ebx, ebx
0x18001173f  call    cs:__imp_GetLastError
0x180011745  lea     rcx, aFinddeviceonin; "FindDeviceOnInterface: DevObjGetClassDe"...
0x18001174c  jmp     loc_180011827
0x180011751  mov     ecx, 210h; Size
0x180011756  call    cs:__imp_malloc
0x18001175c  mov     rbx, rax
0x18001175f  test    rax, rax
0x180011762  jz      loc_1800118AA
0x180011768  xorps   xmm0, xmm0
0x18001176b  xor     r14d, r14d
0x18001176e  movups  [rsp+0F8h+var_B8], xmm0
0x180011773  xor     r9d, r9d
0x180011776  movups  [rsp+0F8h+var_A8], xmm0
0x18001177b  jmp     short loc_1800117E3
0x18001177d  mov     qword ptr [rsp+0F8h+dwFlagsAndAttributes], rsi
0x180011782  lea     rdx, [rsp+0F8h+var_B8]
0x180011787  mov     r9d, 210h
0x18001178d  mov     qword ptr [rsp+0F8h+dwCreationDisposition], rsi
0x180011792  mov     r8, rbx
0x180011795  mov     dword ptr [rbx], 8
0x18001179b  mov     rcx, rdi
0x18001179e  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800117a4  test    eax, eax
0x1800117a6  jz      short loc_1800117DD
0x1800117a8  lea     rbp, [rbx+4]
0x1800117ac  mov     rcx, rbp; lpsz
0x1800117af  call    cs:__imp_CharLowerW
0x1800117b5  lea     rdx, [rsp+0F8h+sz]; SubStr
0x1800117ba  mov     rcx, rbp; Str
0x1800117bd  call    cs:__imp_wcsstr
0x1800117c3  test    rax, rax
0x1800117c6  jz      short loc_1800117DD
0x1800117c8  lea     rdx, aAsyncmac; "asyncmac"
0x1800117cf  mov     rcx, rbp; Str
0x1800117d2  call    cs:__imp_wcsstr
0x1800117d8  test    rax, rax
0x1800117db  jnz     short loc_180011830
0x1800117dd  inc     r14d
0x1800117e0  mov     r9d, r14d
0x1800117e3  lea     rax, [rsp+0F8h+var_B8]
0x1800117e8  mov     dword ptr [rsp+0F8h+var_B8], 20h ; ' '
0x1800117f0  lea     r8, qword_18002E758
0x1800117f7  mov     qword ptr [rsp+0F8h+dwCreationDisposition], rax
0x1800117fc  xor     edx, edx
0x1800117fe  mov     rcx, rdi
0x180011801  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180011807  test    eax, eax
0x180011809  jnz     loc_18001177D
0x18001180f  call    cs:__imp_GetLastError
0x180011815  cmp     eax, 103h
0x18001181a  jz      loc_1800118AA
0x180011820  lea     rcx, aFinddeviceonin_1; "FindDeviceOnInterface: DevObjEnumDevice"...
0x180011827  mov     edx, eax
0x180011829  call    RasTapiTrace
0x18001182e  jmp     short loc_1800118AA
0x180011830  mov     [rsp+0F8h+hTemplateFile], rsi; hTemplateFile
0x180011835  xor     r9d, r9d; lpSecurityAttributes
0x180011838  mov     [rsp+0F8h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x180011840  xor     r8d, r8d; dwShareMode
0x180011843  mov     edx, 0C0000000h; dwDesiredAccess
0x180011848  mov     [rsp+0F8h+dwCreationDisposition], 3; dwCreationDisposition
0x180011850  mov     rcx, rbp; lpFileName
0x180011853  call    cs:__imp_CreateFileW
0x180011859  lea     rcx, [rax-1]
0x18001185d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180011861  ja      short loc_18001186D
0x180011863  mov     [r15], rax
0x180011866  mov     esi, 1
0x18001186b  jmp     short loc_1800118AA
0x18001186d  call    cs:__imp_GetLastError
0x180011873  mov     rdx, rbp
0x180011876  lea     rcx, aCreatefileWsFa; "Createfile %ws failed with %d"
0x18001187d  mov     r8d, eax
0x180011880  call    RasTapiTrace
0x180011885  jmp     short loc_1800118AA
0x180011887  call    cs:__imp_GetLastError
0x18001188d  mov     edx, eax
0x18001188f  lea     rcx, aFinddeviceonin_2; "FindDeviceOnInterface: DevObjCreateDevi"...
0x180011896  call    RasTapiTrace
0x18001189b  xor     esi, esi
0x18001189d  test    rdi, rdi
0x1800118a0  jz      short loc_1800118C1
0x1800118a2  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800118a6  jz      short loc_1800118C1
0x1800118a8  xor     ebx, ebx
0x1800118aa  mov     rcx, rdi
0x1800118ad  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800118b3  test    rbx, rbx
0x1800118b6  jz      short loc_1800118C1
0x1800118b8  mov     rcx, rbx; Block
0x1800118bb  call    cs:__imp_free
0x1800118c1  mov     eax, esi
0x1800118c3  mov     rcx, [rsp+0F8h+var_48]
0x1800118cb  xor     rcx, rsp; StackCookie
0x1800118ce  call    __security_check_cookie
0x1800118d3  add     rsp, 0C8h
0x1800118da  pop     r15
0x1800118dc  pop     r14
0x1800118de  pop     rdi
0x1800118df  pop     rsi
0x1800118e0  pop     rbp
0x1800118e1  pop     rbx
0x1800118e2  retn
```
