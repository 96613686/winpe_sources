# GetCurrentUserName(ushort *,ulong,int,int *,int *)

- ea: `0x1400ab608`
- end: `0x1400ab9ba`
- name: `?GetCurrentUserName@@YAHPEAGKHPEAH1@Z`
- size: `946`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned int@<edx>, int@<r8d>, int *@<r9>, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14005070c`
- `0x1400b8b04`

## callees

- `0x140008a34`
- `0x140008a78`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14009693c`
- `0x1400ab608`
- `0x1400ac7c0`
- `0x140114010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1400ab7d6`
- `KERNEL32!LoadLibraryExW` at `0x1400ab7d6`
- `KERNEL32!FreeLibrary` at `0x1400ab9a1`
- `KERNEL32!FreeLibrary` at `0x1400ab9a1`
- `KERNEL32!GetProcAddress` at `0x1400ab840`
- `KERNEL32!GetProcAddress` at `0x1400ab840`
- `KERNEL32!GetLastError` at `0x1400ab672`
- `KERNEL32!GetLastError` at `0x1400ab697`
- `KERNEL32!GetLastError` at `0x1400ab715`
- `KERNEL32!GetLastError` at `0x1400ab803`
- `KERNEL32!GetLastError` at `0x1400ab876`
- `KERNEL32!GetLastError` at `0x1400ab672`
- `KERNEL32!GetLastError` at `0x1400ab697`
- `KERNEL32!GetLastError` at `0x1400ab715`
- `KERNEL32!GetLastError` at `0x1400ab803`
- `KERNEL32!GetLastError` at `0x1400ab876`
- `KERNEL32!SetLastError` at `0x1400ab7a2`
- `KERNEL32!SetLastError` at `0x1400ab7a2`
- `Secur32!GetUserNameExW` at `0x1400ab668`
- `Secur32!GetUserNameExW` at `0x1400ab6e4`
- `Secur32!GetUserNameExW` at `0x1400ab668`
- `Secur32!GetUserNameExW` at `0x1400ab6e4`
- `NETAPI32!NetApiBufferFree` at `0x1400ab993`
- `NETAPI32!NetApiBufferFree` at `0x1400ab993`

## string_xrefs

- `0x1400ab7cd`: `samcli.dll`

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
    if ( dword_140153E64 && (unsigned int)CTscCredentialsQueryUi::IsOSVersionWin8OrLater() )
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
          dword_140153E64 = 0;
          v23 = *((_QWORD *)Buffer + 1);
          v26 = *((_QWORD *)Buffer + 2);
          dword_140153E60 = 1;
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
0x1400ab608  mov     [rsp-28h+arg_0], rbx
0x1400ab60d  mov     [rsp-28h+Buffer], r9
0x1400ab612  mov     [rsp-28h+nSize], r8d
0x1400ab617  push    rbp
0x1400ab618  push    rsi
0x1400ab619  push    rdi
0x1400ab61a  push    r14
0x1400ab61c  push    r15
0x1400ab61e  mov     rbp, rsp
0x1400ab621  sub     rsp, 30h
0x1400ab625  xor     r15d, r15d
0x1400ab628  mov     r14d, edx
0x1400ab62b  cmp     cs:Str, r15w
0x1400ab633  lea     rbx, WPP_GLOBAL_Control
0x1400ab63a  mov     rdi, rcx
0x1400ab63d  mov     [rbp+nSize], r15d
0x1400ab641  mov     [rbp+arg_20], r15
0x1400ab645  mov     esi, r15d
0x1400ab648  mov     [rbp+Buffer], r15
0x1400ab64c  jnz     loc_1400AB922
0x1400ab652  lea     r8, [rbp+nSize]; nSize
0x1400ab656  mov     [rbp+nSize], 200h
0x1400ab65d  lea     rdx, NameBuffer; lpNameBuffer
0x1400ab664  lea     ecx, [r15+8]; NameFormat
0x1400ab668  call    cs:__imp_GetUserNameExW
0x1400ab66e  test    al, al
0x1400ab670  jnz     short loc_1400AB6CD
0x1400ab672  call    cs:__imp_GetLastError
0x1400ab678  cmp     eax, 534h
0x1400ab67d  jz      short loc_1400AB6CD
0x1400ab67f  mov     rax, cs:WPP_GLOBAL_Control
0x1400ab686  cmp     rax, rbx
0x1400ab689  jz      short loc_1400AB6CD
0x1400ab68b  test    byte ptr [rax+1Ch], 1
0x1400ab68f  jz      short loc_1400AB6CD
0x1400ab691  cmp     byte ptr [rax+19h], 2
0x1400ab695  jb      short loc_1400AB6CD
0x1400ab697  call    cs:__imp_GetLastError
0x1400ab69d  mov     ebx, eax
0x1400ab69f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab6a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab6ab  lea     edx, [r15+69h]
0x1400ab6af  mov     r9d, eax
0x1400ab6b2  mov     dword ptr [rsp+30h+var_10], ebx
0x1400ab6b6  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ab6bd  mov     rcx, [rcx+10h]
0x1400ab6c1  call    WPP_SF_Dd
0x1400ab6c6  lea     rbx, WPP_GLOBAL_Control
0x1400ab6cd  lea     r8, [rbp+nSize]; nSize
0x1400ab6d1  mov     [rbp+nSize], 200h
0x1400ab6d8  lea     rdx, Str; lpNameBuffer
0x1400ab6df  mov     ecx, 2; NameFormat
0x1400ab6e4  call    cs:__imp_GetUserNameExW
0x1400ab6ea  test    al, al
0x1400ab6ec  jnz     short loc_1400AB74A
0x1400ab6ee  mov     edi, r15d
0x1400ab6f1  mov     rax, cs:WPP_GLOBAL_Control
0x1400ab6f8  cmp     rax, rbx
0x1400ab6fb  jz      loc_1400AB98A
0x1400ab701  test    byte ptr [rax+1Ch], 1
0x1400ab705  jz      loc_1400AB98A
0x1400ab70b  cmp     byte ptr [rax+19h], 2
0x1400ab70f  jb      loc_1400AB98A
0x1400ab715  call    cs:__imp_GetLastError
0x1400ab71b  mov     ebx, eax
0x1400ab71d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab722  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab729  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ab730  mov     edx, 6Ah ; 'j'
0x1400ab735  mov     dword ptr [rsp+30h+var_10], ebx
0x1400ab739  mov     r9d, eax
0x1400ab73c  mov     rcx, [rcx+10h]
0x1400ab740  call    WPP_SF_Dd
0x1400ab745  jmp     loc_1400AB98A
0x1400ab74a  lea     r8, [rbp+arg_20]; unsigned __int16 **
0x1400ab74e  call    ?IsLocalUser@@YAJPEBGPEAHPEAPEAG@Z; IsLocalUser(ushort const *,int *,ushort * *)
0x1400ab753  mov     ebx, eax
0x1400ab755  test    eax, eax
0x1400ab757  jns     short loc_1400AB7B0
0x1400ab759  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab760  lea     rdx, WPP_GLOBAL_Control
0x1400ab767  cmp     rcx, rdx
0x1400ab76a  jz      short loc_1400AB7A0
0x1400ab76c  test    byte ptr [rcx+1Ch], 1
0x1400ab770  jz      short loc_1400AB7A0
0x1400ab772  cmp     byte ptr [rcx+19h], 2
0x1400ab776  jb      short loc_1400AB7A0
0x1400ab778  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab77d  mov     edx, 6Bh ; 'k'
0x1400ab782  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab789  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ab790  mov     r9d, eax
0x1400ab793  mov     dword ptr [rsp+30h+var_10], ebx
0x1400ab797  mov     rcx, [rcx+10h]
0x1400ab79b  call    WPP_SF_Dd
0x1400ab7a0  mov     ecx, ebx; dwErrCode
0x1400ab7a2  call    cs:__imp_SetLastError
0x1400ab7a8  mov     edi, r15d
0x1400ab7ab  jmp     loc_1400AB98A
0x1400ab7b0  cmp     cs:dword_140153E64, r15d
0x1400ab7b7  jz      loc_1400AB922
0x1400ab7bd  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x1400ab7c2  test    eax, eax
0x1400ab7c4  jz      loc_1400AB922
0x1400ab7ca  xor     r8d, r8d; dwFlags
0x1400ab7cd  lea     rcx, aSamcliDll; "samcli.dll"
0x1400ab7d4  xor     edx, edx; hFile
0x1400ab7d6  call    cs:__imp_LoadLibraryExW
0x1400ab7dc  mov     rsi, rax
0x1400ab7df  test    rax, rax
0x1400ab7e2  jnz     short loc_1400AB836
0x1400ab7e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab7eb  lea     rdx, WPP_GLOBAL_Control
0x1400ab7f2  cmp     rcx, rdx
0x1400ab7f5  jz      short loc_1400AB7A8
0x1400ab7f7  test    byte ptr [rcx+1Ch], 1
0x1400ab7fb  jz      short loc_1400AB7A8
0x1400ab7fd  cmp     byte ptr [rcx+19h], 2
0x1400ab801  jb      short loc_1400AB7A8
0x1400ab803  call    cs:__imp_GetLastError
0x1400ab809  mov     ebx, eax
0x1400ab80b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab810  lea     edx, [rsi+6Ch]
0x1400ab813  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab81a  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ab821  mov     r9d, eax
0x1400ab824  mov     dword ptr [rsp+30h+var_10], ebx
0x1400ab828  mov     rcx, [rcx+10h]
0x1400ab82c  call    WPP_SF_Dd
0x1400ab831  jmp     loc_1400AB7A8
0x1400ab836  lea     rdx, aNetusergetinfo; "NetUserGetInfo"
0x1400ab83d  mov     rcx, rax; hModule
0x1400ab840  call    cs:__imp_GetProcAddress
0x1400ab846  test    rax, rax
0x1400ab849  jnz     short loc_1400AB88A
0x1400ab84b  mov     rax, cs:WPP_GLOBAL_Control
0x1400ab852  lea     rdx, WPP_GLOBAL_Control
0x1400ab859  cmp     rax, rdx
0x1400ab85c  jz      loc_1400AB7A8
0x1400ab862  test    byte ptr [rax+1Ch], 1
0x1400ab866  jz      loc_1400AB7A8
0x1400ab86c  cmp     byte ptr [rax+19h], 2
0x1400ab870  jb      loc_1400AB7A8
0x1400ab876  call    cs:__imp_GetLastError
0x1400ab87c  mov     ebx, eax
0x1400ab87e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab883  mov     edx, 6Dh ; 'm'
0x1400ab888  jmp     short loc_1400AB813
0x1400ab88a  mov     rdx, [rbp+arg_20]
0x1400ab88e  lea     r9, [rbp+Buffer]
0x1400ab892  mov     r8d, 18h
0x1400ab898  xor     ecx, ecx
0x1400ab89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ab89f  test    eax, eax
0x1400ab8a1  jnz     short loc_1400AB922
0x1400ab8a3  mov     r9, [rbp+Buffer]
0x1400ab8a7  cmp     [r9], r15d
0x1400ab8aa  jz      short loc_1400AB922
0x1400ab8ac  mov     cs:dword_140153E64, r15d
0x1400ab8b3  lea     r8, aSS_0; "%s\\%s"
0x1400ab8ba  mov     rax, [r9+10h]
0x1400ab8be  lea     rcx, Str; unsigned __int16 *
0x1400ab8c5  mov     r9, [r9+8]
0x1400ab8c9  mov     edx, 200h; unsigned __int64
0x1400ab8ce  mov     [rsp+30h+var_10], rax
0x1400ab8d3  mov     cs:dword_140153E60, 1
0x1400ab8dd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400ab8e2  mov     ebx, eax
0x1400ab8e4  test    eax, eax
0x1400ab8e6  jns     short loc_1400AB922
0x1400ab8e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab8ef  lea     rdx, WPP_GLOBAL_Control
0x1400ab8f6  cmp     rcx, rdx
0x1400ab8f9  jz      loc_1400AB7A0
0x1400ab8ff  test    byte ptr [rcx+1Ch], 1
0x1400ab903  jz      loc_1400AB7A0
0x1400ab909  cmp     byte ptr [rcx+19h], 2
0x1400ab90d  jb      loc_1400AB7A0
0x1400ab913  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab918  mov     edx, 6Eh ; 'n'
0x1400ab91d  jmp     loc_1400AB782
0x1400ab922  cmp     cs:NameBuffer, r15w
0x1400ab92a  lea     r8, NameBuffer
0x1400ab931  mov     rdx, r14; unsigned __int64
0x1400ab934  mov     rcx, rdi; unsigned __int16 *
0x1400ab937  jnz     short loc_1400AB940
0x1400ab939  lea     r8, Str; unsigned __int16 *
0x1400ab940  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400ab945  mov     ebx, eax
0x1400ab947  test    eax, eax
0x1400ab949  jns     short loc_1400AB985
0x1400ab94b  mov     rax, cs:WPP_GLOBAL_Control
0x1400ab952  lea     rdx, WPP_GLOBAL_Control
0x1400ab959  cmp     rax, rdx
0x1400ab95c  jz      loc_1400AB7A0
0x1400ab962  test    byte ptr [rax+1Ch], 1
0x1400ab966  jz      loc_1400AB7A0
0x1400ab96c  cmp     byte ptr [rax+19h], 2
0x1400ab970  jb      loc_1400AB7A0
0x1400ab976  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab97b  mov     edx, 6Fh ; 'o'
0x1400ab980  jmp     loc_1400AB782
0x1400ab985  mov     edi, 1
0x1400ab98a  mov     rcx, [rbp+Buffer]; Buffer
0x1400ab98e  test    rcx, rcx
0x1400ab991  jz      short loc_1400AB999
0x1400ab993  call    cs:__imp_NetApiBufferFree
0x1400ab999  test    rsi, rsi
0x1400ab99c  jz      short loc_1400AB9A7
0x1400ab99e  mov     rcx, rsi; hLibModule
0x1400ab9a1  call    cs:__imp_FreeLibrary
0x1400ab9a7  mov     rbx, [rsp+30h+arg_0]
0x1400ab9ac  mov     eax, edi
0x1400ab9ae  add     rsp, 30h
0x1400ab9b2  pop     r15
0x1400ab9b4  pop     r14
0x1400ab9b6  pop     rdi
0x1400ab9b7  pop     rsi
0x1400ab9b8  pop     rbp
0x1400ab9b9  retn
```
