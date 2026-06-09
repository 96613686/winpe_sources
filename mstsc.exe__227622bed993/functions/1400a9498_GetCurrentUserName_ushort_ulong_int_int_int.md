# GetCurrentUserName(ushort *,ulong,int,int *,int *)

- ea: `0x1400a9498`
- end: `0x1400a984a`
- name: `?GetCurrentUserName@@YAHPEAGKHPEAH1@Z`
- size: `946`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned int@<edx>, int@<r8d>, int *@<r9>, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004e59c`
- `0x1400b6994`

## callees

- `0x140008a34`
- `0x140008a78`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x1400947cc`
- `0x1400a9498`
- `0x1400aa650`
- `0x140112010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1400a9666`
- `KERNEL32!LoadLibraryExW` at `0x1400a9666`
- `KERNEL32!FreeLibrary` at `0x1400a9831`
- `KERNEL32!FreeLibrary` at `0x1400a9831`
- `KERNEL32!GetProcAddress` at `0x1400a96d0`
- `KERNEL32!GetProcAddress` at `0x1400a96d0`
- `KERNEL32!GetLastError` at `0x1400a9502`
- `KERNEL32!GetLastError` at `0x1400a9527`
- `KERNEL32!GetLastError` at `0x1400a95a5`
- `KERNEL32!GetLastError` at `0x1400a9693`
- `KERNEL32!GetLastError` at `0x1400a9706`
- `KERNEL32!GetLastError` at `0x1400a9502`
- `KERNEL32!GetLastError` at `0x1400a9527`
- `KERNEL32!GetLastError` at `0x1400a95a5`
- `KERNEL32!GetLastError` at `0x1400a9693`
- `KERNEL32!GetLastError` at `0x1400a9706`
- `KERNEL32!SetLastError` at `0x1400a9632`
- `KERNEL32!SetLastError` at `0x1400a9632`
- `Secur32!GetUserNameExW` at `0x1400a94f8`
- `Secur32!GetUserNameExW` at `0x1400a9574`
- `Secur32!GetUserNameExW` at `0x1400a94f8`
- `Secur32!GetUserNameExW` at `0x1400a9574`
- `NETAPI32!NetApiBufferFree` at `0x1400a9823`
- `NETAPI32!NetApiBufferFree` at `0x1400a9823`

## string_xrefs

- `0x1400a965d`: `samcli.dll`

## pseudocode

```c
__int64 __fastcall GetCurrentUserName(unsigned __int16 *a1, unsigned int a2, __int64 a3, int *a4, unsigned __int16 *a5)
{
  unsigned __int64 v5; // r14
  HMODULE v7; // rsi
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int *v10; // rdx
  const unsigned __int16 *v11; // rcx
  unsigned int v12; // edi
  DWORD v13; // ebx
  unsigned int v14; // eax
  signed int v15; // ebx
  unsigned int v16; // eax
  __int64 v17; // rdx
  HMODULE Library; // rax
  DWORD v19; // ebx
  unsigned int v20; // eax
  __int64 v21; // rdx
  FARPROC ProcAddress; // rax
  __int64 v23; // r9
  const unsigned __int16 *v24; // r8
  __int64 v26; // [rsp+20h] [rbp-10h]
  ULONG nSize; // [rsp+70h] [rbp+40h] BYREF
  LPVOID Buffer; // [rsp+78h] [rbp+48h] BYREF

  v5 = a2;
  nSize = 0;
  a5 = 0;
  v7 = 0;
  Buffer = 0;
  if ( Str )
    goto LABEL_41;
  nSize = 512;
  if ( !GetUserNameExW(NameUserPrincipal, &NameBuffer, &nSize)
    && GetLastError() != 1332
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      105,
      WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
  }
  nSize = 512;
  if ( GetUserNameExW(NameSamCompatible, &Str, &nSize) )
  {
    v15 = IsLocalUser(v11, v10, &a5);
    if ( v15 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_19;
      }
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 107;
LABEL_18:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids, v16, v15);
LABEL_19:
      SetLastError(v15);
LABEL_20:
      v12 = 0;
      goto LABEL_49;
    }
    if ( dword_140151D34 && (unsigned int)CTscCredentialsQueryUi::IsOSVersionWin8OrLater() )
    {
      Library = LoadLibraryExW(L"samcli.dll", 0, 0);
      v7 = Library;
      if ( !Library )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_20;
        }
        v19 = GetLastError();
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        v21 = 108;
        goto LABEL_28;
      }
      ProcAddress = GetProcAddress(Library, "NetUserGetInfo");
      if ( !ProcAddress )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_20;
        }
        v19 = GetLastError();
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        v21 = 109;
LABEL_28:
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids, v20, v19);
        goto LABEL_20;
      }
      if ( !((unsigned int (__fastcall *)(_QWORD, unsigned __int16 *, __int64, LPVOID *))ProcAddress)(
              0,
              a5,
              24,
              &Buffer) )
      {
        if ( *(_DWORD *)Buffer )
        {
          dword_140151D34 = 0;
          v23 = *((_QWORD *)Buffer + 1);
          v26 = *((_QWORD *)Buffer + 2);
          dword_140151D30 = 1;
          v15 = StringCchPrintfW(&Str, 0x200u, L"%s\\%s", v23, v26);
          if ( v15 < 0 )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_19;
            }
            v16 = RdpWppGetCurrentThreadActivityIdPrefix();
            v17 = 110;
            goto LABEL_18;
          }
        }
      }
    }
LABEL_41:
    v24 = &NameBuffer;
    if ( !NameBuffer )
      v24 = &Str;
    v15 = StringCchCopyW(a1, v5, v24);
    if ( v15 >= 0 )
    {
      v12 = 1;
      goto LABEL_49;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 111;
    goto LABEL_18;
  }
  v12 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = GetLastError();
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids, v14, v13);
  }
LABEL_49:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( v7 )
    FreeLibrary(v7);
  return v12;
}

```

## disassembly

```asm
0x1400a9498  mov     [rsp-28h+arg_0], rbx
0x1400a949d  mov     [rsp-28h+Buffer], r9
0x1400a94a2  mov     [rsp-28h+nSize], r8d
0x1400a94a7  push    rbp
0x1400a94a8  push    rsi
0x1400a94a9  push    rdi
0x1400a94aa  push    r14
0x1400a94ac  push    r15
0x1400a94ae  mov     rbp, rsp
0x1400a94b1  sub     rsp, 30h
0x1400a94b5  xor     r15d, r15d
0x1400a94b8  mov     r14d, edx
0x1400a94bb  cmp     cs:Str, r15w
0x1400a94c3  lea     rbx, WPP_GLOBAL_Control
0x1400a94ca  mov     rdi, rcx
0x1400a94cd  mov     [rbp+nSize], r15d
0x1400a94d1  mov     [rbp+arg_20], r15
0x1400a94d5  mov     esi, r15d
0x1400a94d8  mov     [rbp+Buffer], r15
0x1400a94dc  jnz     loc_1400A97B2
0x1400a94e2  lea     r8, [rbp+nSize]; nSize
0x1400a94e6  mov     [rbp+nSize], 200h
0x1400a94ed  lea     rdx, NameBuffer; lpNameBuffer
0x1400a94f4  lea     ecx, [r15+8]; NameFormat
0x1400a94f8  call    cs:__imp_GetUserNameExW
0x1400a94fe  test    al, al
0x1400a9500  jnz     short loc_1400A955D
0x1400a9502  call    cs:__imp_GetLastError
0x1400a9508  cmp     eax, 534h
0x1400a950d  jz      short loc_1400A955D
0x1400a950f  mov     rax, cs:WPP_GLOBAL_Control
0x1400a9516  cmp     rax, rbx
0x1400a9519  jz      short loc_1400A955D
0x1400a951b  test    byte ptr [rax+1Ch], 1
0x1400a951f  jz      short loc_1400A955D
0x1400a9521  cmp     byte ptr [rax+19h], 2
0x1400a9525  jb      short loc_1400A955D
0x1400a9527  call    cs:__imp_GetLastError
0x1400a952d  mov     ebx, eax
0x1400a952f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9534  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a953b  lea     edx, [r15+69h]
0x1400a953f  mov     r9d, eax
0x1400a9542  mov     dword ptr [rsp+30h+var_10], ebx
0x1400a9546  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400a954d  mov     rcx, [rcx+10h]
0x1400a9551  call    WPP_SF_Dd
0x1400a9556  lea     rbx, WPP_GLOBAL_Control
0x1400a955d  lea     r8, [rbp+nSize]; nSize
0x1400a9561  mov     [rbp+nSize], 200h
0x1400a9568  lea     rdx, Str; lpNameBuffer
0x1400a956f  mov     ecx, 2; NameFormat
0x1400a9574  call    cs:__imp_GetUserNameExW
0x1400a957a  test    al, al
0x1400a957c  jnz     short loc_1400A95DA
0x1400a957e  mov     edi, r15d
0x1400a9581  mov     rax, cs:WPP_GLOBAL_Control
0x1400a9588  cmp     rax, rbx
0x1400a958b  jz      loc_1400A981A
0x1400a9591  test    byte ptr [rax+1Ch], 1
0x1400a9595  jz      loc_1400A981A
0x1400a959b  cmp     byte ptr [rax+19h], 2
0x1400a959f  jb      loc_1400A981A
0x1400a95a5  call    cs:__imp_GetLastError
0x1400a95ab  mov     ebx, eax
0x1400a95ad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a95b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a95b9  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400a95c0  mov     edx, 6Ah ; 'j'
0x1400a95c5  mov     dword ptr [rsp+30h+var_10], ebx
0x1400a95c9  mov     r9d, eax
0x1400a95cc  mov     rcx, [rcx+10h]
0x1400a95d0  call    WPP_SF_Dd
0x1400a95d5  jmp     loc_1400A981A
0x1400a95da  lea     r8, [rbp+arg_20]; unsigned __int16 **
0x1400a95de  call    ?IsLocalUser@@YAJPEBGPEAHPEAPEAG@Z; IsLocalUser(ushort const *,int *,ushort * *)
0x1400a95e3  mov     ebx, eax
0x1400a95e5  test    eax, eax
0x1400a95e7  jns     short loc_1400A9640
0x1400a95e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a95f0  lea     rdx, WPP_GLOBAL_Control
0x1400a95f7  cmp     rcx, rdx
0x1400a95fa  jz      short loc_1400A9630
0x1400a95fc  test    byte ptr [rcx+1Ch], 1
0x1400a9600  jz      short loc_1400A9630
0x1400a9602  cmp     byte ptr [rcx+19h], 2
0x1400a9606  jb      short loc_1400A9630
0x1400a9608  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a960d  mov     edx, 6Bh ; 'k'
0x1400a9612  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9619  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400a9620  mov     r9d, eax
0x1400a9623  mov     dword ptr [rsp+30h+var_10], ebx
0x1400a9627  mov     rcx, [rcx+10h]
0x1400a962b  call    WPP_SF_Dd
0x1400a9630  mov     ecx, ebx; dwErrCode
0x1400a9632  call    cs:__imp_SetLastError
0x1400a9638  mov     edi, r15d
0x1400a963b  jmp     loc_1400A981A
0x1400a9640  cmp     cs:dword_140151D34, r15d
0x1400a9647  jz      loc_1400A97B2
0x1400a964d  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x1400a9652  test    eax, eax
0x1400a9654  jz      loc_1400A97B2
0x1400a965a  xor     r8d, r8d; dwFlags
0x1400a965d  lea     rcx, aSamcliDll; "samcli.dll"
0x1400a9664  xor     edx, edx; hFile
0x1400a9666  call    cs:__imp_LoadLibraryExW
0x1400a966c  mov     rsi, rax
0x1400a966f  test    rax, rax
0x1400a9672  jnz     short loc_1400A96C6
0x1400a9674  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a967b  lea     rdx, WPP_GLOBAL_Control
0x1400a9682  cmp     rcx, rdx
0x1400a9685  jz      short loc_1400A9638
0x1400a9687  test    byte ptr [rcx+1Ch], 1
0x1400a968b  jz      short loc_1400A9638
0x1400a968d  cmp     byte ptr [rcx+19h], 2
0x1400a9691  jb      short loc_1400A9638
0x1400a9693  call    cs:__imp_GetLastError
0x1400a9699  mov     ebx, eax
0x1400a969b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a96a0  lea     edx, [rsi+6Ch]
0x1400a96a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a96aa  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400a96b1  mov     r9d, eax
0x1400a96b4  mov     dword ptr [rsp+30h+var_10], ebx
0x1400a96b8  mov     rcx, [rcx+10h]
0x1400a96bc  call    WPP_SF_Dd
0x1400a96c1  jmp     loc_1400A9638
0x1400a96c6  lea     rdx, aNetusergetinfo; "NetUserGetInfo"
0x1400a96cd  mov     rcx, rax; hModule
0x1400a96d0  call    cs:__imp_GetProcAddress
0x1400a96d6  test    rax, rax
0x1400a96d9  jnz     short loc_1400A971A
0x1400a96db  mov     rax, cs:WPP_GLOBAL_Control
0x1400a96e2  lea     rdx, WPP_GLOBAL_Control
0x1400a96e9  cmp     rax, rdx
0x1400a96ec  jz      loc_1400A9638
0x1400a96f2  test    byte ptr [rax+1Ch], 1
0x1400a96f6  jz      loc_1400A9638
0x1400a96fc  cmp     byte ptr [rax+19h], 2
0x1400a9700  jb      loc_1400A9638
0x1400a9706  call    cs:__imp_GetLastError
0x1400a970c  mov     ebx, eax
0x1400a970e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9713  mov     edx, 6Dh ; 'm'
0x1400a9718  jmp     short loc_1400A96A3
0x1400a971a  mov     rdx, [rbp+arg_20]
0x1400a971e  lea     r9, [rbp+Buffer]
0x1400a9722  mov     r8d, 18h
0x1400a9728  xor     ecx, ecx
0x1400a972a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a972f  test    eax, eax
0x1400a9731  jnz     short loc_1400A97B2
0x1400a9733  mov     r9, [rbp+Buffer]
0x1400a9737  cmp     [r9], r15d
0x1400a973a  jz      short loc_1400A97B2
0x1400a973c  mov     cs:dword_140151D34, r15d
0x1400a9743  lea     r8, aSS_0; "%s\\%s"
0x1400a974a  mov     rax, [r9+10h]
0x1400a974e  lea     rcx, Str; unsigned __int16 *
0x1400a9755  mov     r9, [r9+8]
0x1400a9759  mov     edx, 200h; unsigned __int64
0x1400a975e  mov     [rsp+30h+var_10], rax
0x1400a9763  mov     cs:dword_140151D30, 1
0x1400a976d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400a9772  mov     ebx, eax
0x1400a9774  test    eax, eax
0x1400a9776  jns     short loc_1400A97B2
0x1400a9778  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a977f  lea     rdx, WPP_GLOBAL_Control
0x1400a9786  cmp     rcx, rdx
0x1400a9789  jz      loc_1400A9630
0x1400a978f  test    byte ptr [rcx+1Ch], 1
0x1400a9793  jz      loc_1400A9630
0x1400a9799  cmp     byte ptr [rcx+19h], 2
0x1400a979d  jb      loc_1400A9630
0x1400a97a3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a97a8  mov     edx, 6Eh ; 'n'
0x1400a97ad  jmp     loc_1400A9612
0x1400a97b2  cmp     cs:NameBuffer, r15w
0x1400a97ba  lea     r8, NameBuffer
0x1400a97c1  mov     rdx, r14; unsigned __int64
0x1400a97c4  mov     rcx, rdi; unsigned __int16 *
0x1400a97c7  jnz     short loc_1400A97D0
0x1400a97c9  lea     r8, Str; unsigned __int16 *
0x1400a97d0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400a97d5  mov     ebx, eax
0x1400a97d7  test    eax, eax
0x1400a97d9  jns     short loc_1400A9815
0x1400a97db  mov     rax, cs:WPP_GLOBAL_Control
0x1400a97e2  lea     rdx, WPP_GLOBAL_Control
0x1400a97e9  cmp     rax, rdx
0x1400a97ec  jz      loc_1400A9630
0x1400a97f2  test    byte ptr [rax+1Ch], 1
0x1400a97f6  jz      loc_1400A9630
0x1400a97fc  cmp     byte ptr [rax+19h], 2
0x1400a9800  jb      loc_1400A9630
0x1400a9806  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a980b  mov     edx, 6Fh ; 'o'
0x1400a9810  jmp     loc_1400A9612
0x1400a9815  mov     edi, 1
0x1400a981a  mov     rcx, [rbp+Buffer]; Buffer
0x1400a981e  test    rcx, rcx
0x1400a9821  jz      short loc_1400A9829
0x1400a9823  call    cs:__imp_NetApiBufferFree
0x1400a9829  test    rsi, rsi
0x1400a982c  jz      short loc_1400A9837
0x1400a982e  mov     rcx, rsi; hLibModule
0x1400a9831  call    cs:__imp_FreeLibrary
0x1400a9837  mov     rbx, [rsp+30h+arg_0]
0x1400a983c  mov     eax, edi
0x1400a983e  add     rsp, 30h
0x1400a9842  pop     r15
0x1400a9844  pop     r14
0x1400a9846  pop     rdi
0x1400a9847  pop     rsi
0x1400a9848  pop     rbp
0x1400a9849  retn
```
