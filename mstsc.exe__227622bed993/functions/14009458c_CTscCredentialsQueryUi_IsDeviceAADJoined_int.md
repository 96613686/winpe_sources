# CTscCredentialsQueryUi::IsDeviceAADJoined(int *)

- ea: `0x14009458c`
- end: `0x1400947c6`
- name: `?IsDeviceAADJoined@CTscCredentialsQueryUi@@CAJPEAH@Z`
- size: `570`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140094f40`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14009458c`
- `0x140112010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x14009460c`
- `KERNEL32!LoadLibraryW` at `0x14009460c`
- `KERNEL32!FreeLibrary` at `0x1400947b5`
- `KERNEL32!FreeLibrary` at `0x1400947b5`
- `KERNEL32!GetProcAddress` at `0x14009468d`
- `KERNEL32!GetProcAddress` at `0x1400946a0`
- `KERNEL32!GetProcAddress` at `0x14009468d`
- `KERNEL32!GetProcAddress` at `0x1400946a0`
- `KERNEL32!GetLastError` at `0x14009461a`
- `KERNEL32!GetLastError` at `0x14009461a`

## string_xrefs

- `0x140094605`: `netapi32.dll`

## pseudocode

```c
__int64 __fastcall CTscCredentialsQueryUi::IsDeviceAADJoined(int *a1)
{
  void (*v1)(void); // rbp
  HMODULE v3; // rdi
  unsigned int v4; // eax
  signed int LastError; // ebx
  HMODULE LibraryW; // rax
  unsigned int v7; // eax
  FARPROC ProcAddress; // rbx
  FARPROC v9; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v11; // eax
  unsigned int v12; // eax
  _DWORD *v14; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  v14 = 0;
  if ( a1 )
  {
    LibraryW = LoadLibraryW(L"netapi32.dll");
    v3 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "NetGetAadJoinInformation");
      v9 = GetProcAddress(v3, "NetFreeAadJoinInformation");
      v1 = (void (*)(void))v9;
      if ( ProcAddress && v9 )
      {
        LastError = ((__int64 (__fastcall *)(_QWORD, _DWORD **))ProcAddress)(0, &v14);
        if ( LastError >= 0 )
        {
          if ( !v14 || (v11 = 1, *v14 != 1) )
            v11 = 0;
          *a1 = v11;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            62,
            (unsigned int)WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"NetGetAadJoinInformation failed",
            LastError);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v12 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids, v12);
        }
        LastError = -2147467263;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids,
          v7,
          LastError);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
    }
  }
  else
  {
    v3 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids,
        v4,
        (__int64)"pfAADJoined",
        -2147024809);
    }
    LastError = -2147024809;
  }
  if ( v14 && v1 )
    v1();
  if ( v3 )
    FreeLibrary(v3);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14009458c  push    rbx
0x14009458e  push    rbp
0x14009458f  push    rsi
0x140094590  push    rdi
0x140094591  sub     rsp, 38h
0x140094595  xor     ebp, ebp
0x140094597  mov     rsi, rcx
0x14009459a  mov     [rsp+58h+arg_0], rbp
0x14009459f  test    rcx, rcx
0x1400945a2  jnz     short loc_140094605
0x1400945a4  xor     edi, edi
0x1400945a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400945ad  lea     rax, WPP_GLOBAL_Control
0x1400945b4  cmp     rcx, rax
0x1400945b7  jz      short loc_1400945FB
0x1400945b9  test    byte ptr [rcx+1Ch], 8
0x1400945bd  jz      short loc_1400945FB
0x1400945bf  cmp     byte ptr [rcx+19h], 2
0x1400945c3  jb      short loc_1400945FB
0x1400945c5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400945ca  lea     rcx, aPfaadjoined; "pfAADJoined"
0x1400945d1  mov     [rsp+58h+var_30], 80070057h
0x1400945d9  mov     [rsp+58h+var_38], rcx
0x1400945de  lea     edx, [rsi+3Bh]
0x1400945e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400945e8  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x1400945ef  mov     r9d, eax
0x1400945f2  mov     rcx, [rcx+10h]
0x1400945f6  call    WPP_SF_DsD
0x1400945fb  mov     ebx, 80070057h
0x140094600  jmp     loc_140094796
0x140094605  lea     rcx, aNetapi32Dll_0; "netapi32.dll"
0x14009460c  call    cs:__imp_LoadLibraryW
0x140094612  mov     rdi, rax
0x140094615  test    rax, rax
0x140094618  jnz     short loc_140094683
0x14009461a  call    cs:__imp_GetLastError
0x140094620  mov     ebx, eax
0x140094622  mov     rcx, cs:WPP_GLOBAL_Control
0x140094629  lea     rax, WPP_GLOBAL_Control
0x140094630  cmp     rcx, rax
0x140094633  jz      short loc_140094667
0x140094635  test    byte ptr [rcx+1Ch], 8
0x140094639  jz      short loc_140094667
0x14009463b  cmp     byte ptr [rcx+19h], 2
0x14009463f  jb      short loc_140094667
0x140094641  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140094646  mov     rcx, cs:WPP_GLOBAL_Control
0x14009464d  lea     edx, [rdi+3Ch]
0x140094650  mov     r9d, eax
0x140094653  mov     dword ptr [rsp+58h+var_38], ebx
0x140094657  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x14009465e  mov     rcx, [rcx+10h]
0x140094662  call    WPP_SF_Dd
0x140094667  test    ebx, ebx
0x140094669  jle     short loc_140094674
0x14009466b  movzx   ebx, bx
0x14009466e  or      ebx, 80070000h
0x140094674  test    ebx, ebx
0x140094676  mov     eax, 80004005h
0x14009467b  cmovns  ebx, eax
0x14009467e  jmp     loc_140094796
0x140094683  lea     rdx, aNetgetaadjoini; "NetGetAadJoinInformation"
0x14009468a  mov     rcx, rdi; hModule
0x14009468d  call    cs:__imp_GetProcAddress
0x140094693  lea     rdx, aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x14009469a  mov     rcx, rdi; hModule
0x14009469d  mov     rbx, rax
0x1400946a0  call    cs:__imp_GetProcAddress
0x1400946a6  mov     rbp, rax
0x1400946a9  test    rbx, rbx
0x1400946ac  jz      loc_14009474A
0x1400946b2  test    rax, rax
0x1400946b5  jz      loc_14009474A
0x1400946bb  lea     rdx, [rsp+58h+arg_0]
0x1400946c0  xor     ecx, ecx
0x1400946c2  mov     rax, rbx
0x1400946c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400946ca  mov     ebx, eax
0x1400946cc  test    eax, eax
0x1400946ce  jns     short loc_140094731
0x1400946d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400946d7  lea     rax, WPP_GLOBAL_Control
0x1400946de  cmp     rcx, rax
0x1400946e1  jz      loc_140094796
0x1400946e7  test    byte ptr [rcx+1Ch], 8
0x1400946eb  jz      loc_140094796
0x1400946f1  cmp     byte ptr [rcx+19h], 2
0x1400946f5  jb      loc_140094796
0x1400946fb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140094700  lea     rcx, aNetgetaadjoini_0; "NetGetAadJoinInformation failed"
0x140094707  mov     [rsp+58h+var_30], ebx
0x14009470b  mov     [rsp+58h+var_38], rcx
0x140094710  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x140094717  mov     rcx, cs:WPP_GLOBAL_Control
0x14009471e  mov     edx, 3Eh ; '>'
0x140094723  mov     r9d, eax
0x140094726  mov     rcx, [rcx+10h]
0x14009472a  call    WPP_SF_DsD
0x14009472f  jmp     short loc_140094796
0x140094731  mov     rcx, [rsp+58h+arg_0]
0x140094736  test    rcx, rcx
0x140094739  jz      short loc_140094744
0x14009473b  mov     eax, 1
0x140094740  cmp     [rcx], eax
0x140094742  jz      short loc_140094746
0x140094744  xor     eax, eax
0x140094746  mov     [rsi], eax
0x140094748  jmp     short loc_140094796
0x14009474a  mov     rcx, cs:WPP_GLOBAL_Control
0x140094751  lea     rax, WPP_GLOBAL_Control
0x140094758  cmp     rcx, rax
0x14009475b  jz      short loc_140094791
0x14009475d  mov     eax, 1
0x140094762  test    [rcx+1Ch], al
0x140094765  jz      short loc_140094791
0x140094767  cmp     byte ptr [rcx+19h], 3
0x14009476b  jb      short loc_140094791
0x14009476d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140094772  mov     rcx, cs:WPP_GLOBAL_Control
0x140094779  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x140094780  mov     edx, 3Dh ; '='
0x140094785  mov     r9d, eax
0x140094788  mov     rcx, [rcx+10h]
0x14009478c  call    WPP_SF_d
0x140094791  mov     ebx, 80004001h
0x140094796  mov     rcx, [rsp+58h+arg_0]
0x14009479b  test    rcx, rcx
0x14009479e  jz      short loc_1400947AD
0x1400947a0  test    rbp, rbp
0x1400947a3  jz      short loc_1400947AD
0x1400947a5  mov     rax, rbp
0x1400947a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400947ad  test    rdi, rdi
0x1400947b0  jz      short loc_1400947BB
0x1400947b2  mov     rcx, rdi; hLibModule
0x1400947b5  call    cs:__imp_FreeLibrary
0x1400947bb  mov     eax, ebx
0x1400947bd  add     rsp, 38h
0x1400947c1  pop     rdi
0x1400947c2  pop     rsi
0x1400947c3  pop     rbp
0x1400947c4  pop     rbx
0x1400947c5  retn
```
