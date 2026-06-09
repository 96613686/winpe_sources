# LocalDB::loadUserInstanceDll(void)

- ea: `0x100443818`
- end: `0x100443df7`
- name: `?loadUserInstanceDll@LocalDB@@QEAAKXZ`
- size: `1503`
- prototype: `unsigned int __fastcall(LocalDB *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1004434a4`

## callees

- `0x100419e64`
- `0x10043a7c4`
- `0x10043a930`
- `0x100442db8`
- `0x100443818`
- `0x100545d84`
- `0x100546aa8`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!LoadLibraryA` at `0x100443b7e`
- `KERNEL32!LoadLibraryA` at `0x100443b7e`
- `KERNEL32!GetLastError` at `0x100443b90`
- `KERNEL32!GetLastError` at `0x100443cd4`
- `KERNEL32!GetLastError` at `0x100443b90`
- `KERNEL32!GetLastError` at `0x100443cd4`
- `KERNEL32!GetProcAddress` at `0x100443c3e`
- `KERNEL32!GetProcAddress` at `0x100443c53`
- `KERNEL32!GetProcAddress` at `0x100443c3e`
- `KERNEL32!GetProcAddress` at `0x100443c53`
- `KERNEL32!FreeLibrary` at `0x100443d76`
- `KERNEL32!FreeLibrary` at `0x100443d76`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LocalDB::loadUserInstanceDll(LocalDB *this)
{
  __int64 v2; // rsi
  unsigned int v3; // ebx
  unsigned int UserInstanceDllPath; // edi
  unsigned int v5; // r14d
  unsigned int v6; // ecx
  wchar_t *v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rdx
  HMODULE LibraryA; // rax
  HMODULE v11; // r14
  FARPROC ProcAddress; // rax
  bool v13; // zf
  __int64 v14; // rcx
  __int64 v16; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B8h]
  __int64 v18; // [rsp+58h] [rbp-B0h]
  _QWORD v19[3]; // [rsp+60h] [rbp-A8h] BYREF
  CHAR LibFileName[272]; // [rsp+78h] [rbp-90h] BYREF

  v19[1] = -2;
  v2 = -1;
  v19[0] = -1;
  v3 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E8018[0] && bidID != -1 )
    off_1005D39F0();
  UserInstanceDllPath = 0;
  if ( *(_QWORD *)this )
    goto LABEL_73;
  v17 = *((_QWORD *)this + 3);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v17 + 16) + 32LL) + 8LL))(*(_QWORD *)(v17 + 16) + 32LL);
  LODWORD(v18) = 1;
  if ( *(_QWORD *)this )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v17 + 16) + 32LL) + 24LL))(*(_QWORD *)(v17 + 16) + 32LL);
    goto LABEL_73;
  }
  UserInstanceDllPath = LocalDB::GetUserInstanceDllPath(this, LibFileName, 0x104u, (enum LocalDBErrorState *)&v16);
  if ( UserInstanceDllPath )
  {
    v5 = 50153;
    if ( (bidGblFlags & 2) == 0 || !off_1005E6260[0] )
      goto LABEL_20;
    if ( !(_DWORD)v16 )
    {
      v6 = 50152;
      goto LABEL_19;
    }
    if ( (_DWORD)v16 != 1 )
    {
      if ( (_DWORD)v16 == 2 )
      {
        v6 = 50154;
        goto LABEL_19;
      }
      if ( (_DWORD)v16 == 3 )
      {
        v6 = 50155;
LABEL_19:
        SniErrorIdFromStringId(v6);
        bidTraceW(0, 250880, off_1005E6260[0], 9);
LABEL_20:
        if ( (_DWORD)v16 )
        {
          if ( (_DWORD)v16 != 1 )
          {
            if ( (_DWORD)v16 == 2 )
            {
              v5 = 50154;
            }
            else if ( (_DWORD)v16 == 3 )
            {
              v5 = 50155;
            }
          }
        }
        else
        {
          v5 = 50152;
        }
        SNISetLastError(9, UserInstanceDllPath, v5);
        if ( (bidGblFlags & 2) == 0 || !off_1005E6268[0] )
          goto LABEL_48;
        v7 = off_1005E6268[0];
        v8 = 252928;
LABEL_47:
        bidTraceW(0, v8, v7, UserInstanceDllPath);
LABEL_48:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v17 + 16) + 32LL) + 24LL))(*(_QWORD *)(v17 + 16) + 32LL);
LABEL_72:
        *((_QWORD *)this + 2) = 0;
        *((_QWORD *)this + 1) = 0;
LABEL_73:
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E62B8[0] )
          bidTraceW(0, 340992, off_1005E62B8[0], UserInstanceDllPath);
        v3 = UserInstanceDllPath;
        goto LABEL_77;
      }
    }
    v6 = 50153;
    goto LABEL_19;
  }
  v9 = -1;
  do
    ++v9;
  while ( LibFileName[v9] );
  UserInstanceDllPath = StrTrimBoth_Sys(LibFileName, 3);
  if ( UserInstanceDllPath )
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E6270[0] )
    {
      SniErrorIdFromStringId(0xC3EBu);
      bidTraceW(0, 0x40000, off_1005E6270[0], 9);
    }
    SNISetLastError(9, UserInstanceDllPath, 50155);
    if ( (bidGblFlags & 2) == 0 || !off_1005E6278[0] )
      goto LABEL_48;
    v7 = off_1005E6278[0];
    v8 = 264192;
    goto LABEL_47;
  }
  do
    ++v2;
  while ( LibFileName[v2] );
  if ( !v2 )
  {
    UserInstanceDllPath = 13;
    if ( (bidGblFlags & 2) != 0 && off_1005E6280[0] )
    {
      SniErrorIdFromStringId(0xC3EBu);
      bidTraceW(0, 273408, off_1005E6280[0], 9);
    }
    SNISetLastError(9, 13, 50155);
    if ( (bidGblFlags & 2) == 0 || !off_1005E6288[0] )
      goto LABEL_48;
    v7 = off_1005E6288[0];
    v8 = 275456;
    goto LABEL_47;
  }
  LibraryA = LoadLibraryA(LibFileName);
  v11 = LibraryA;
  if ( !LibraryA )
  {
    UserInstanceDllPath = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1005E6290[0] )
    {
      SniErrorIdFromStringId(0xC3ECu);
      bidTraceW(0, 285696, off_1005E6290[0], 9);
    }
    SNISetLastError(9, UserInstanceDllPath, 50156);
    if ( (bidGblFlags & 2) != 0 && off_1005E6298[0] )
      bidTraceW(0, 287744, off_1005E6298[0], UserInstanceDllPath);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v17 + 16) + 32LL) + 24LL))(*(_QWORD *)(v17 + 16) + 32LL);
LABEL_71:
    if ( !UserInstanceDllPath )
      goto LABEL_73;
    goto LABEL_72;
  }
  *((_QWORD *)this + 2) = GetProcAddress(LibraryA, "LocalDBStartInstance");
  ProcAddress = GetProcAddress(v11, "LocalDBFormatMessage");
  *((_QWORD *)this + 1) = ProcAddress;
  if ( !*((_QWORD *)this + 2) || !ProcAddress )
  {
    UserInstanceDllPath = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1005E62A0[0] )
    {
      SniErrorIdFromStringId(0xC3EDu);
      bidTraceW(0, 305152, off_1005E62A0[0], 9);
    }
    SNISetLastError(9, UserInstanceDllPath, 50157);
    if ( (bidGblFlags & 2) != 0 && off_1005E62A8[0] )
      bidTraceW(0, 307200, off_1005E62A8[0], UserInstanceDllPath);
    v14 = *(_QWORD *)(v17 + 16);
    goto LABEL_70;
  }
  v13 = _InterlockedExchange64((volatile __int64 *)this, (__int64)v11) == 0;
  v14 = *(_QWORD *)(v17 + 16);
  if ( !v13 )
  {
LABEL_70:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v14 + 32) + 24LL))(v14 + 32);
    FreeLibrary(v11);
    goto LABEL_71;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(v14 + 32) + 24LL))(v14 + 32);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E62B0[0] )
    bidTraceW(0, 323584, off_1005E62B0[0], 0);
LABEL_77:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v19);
  return v3;
}

```

## disassembly

```asm
0x100443818  mov     rax, rsp
0x10044381b  push    rbp
0x10044381c  push    r12
0x10044381e  push    r14
0x100443820  lea     rbp, [rax-0A8h]
0x100443827  sub     rsp, 190h
0x10044382e  mov     [rsp+1A0h+var_140], 0FFFFFFFFFFFFFFFEh
0x100443837  mov     [rax+10h], rbx
0x10044383b  mov     [rax+18h], rsi
0x10044383f  mov     [rax+20h], rdi
0x100443843  mov     rax, cs:__security_cookie
0x10044384a  xor     rax, rsp
0x10044384d  mov     [rbp+0A0h+var_20], rax
0x100443854  mov     r12, rcx
0x100443857  or      rsi, 0FFFFFFFFFFFFFFFFh
0x10044385b  mov     [rsp+1A0h+var_148], rsi
0x100443860  mov     eax, cs:_bidGblFlags
0x100443866  mov     ecx, 20004h
0x10044386b  and     eax, ecx
0x10044386d  xor     ebx, ebx
0x10044386f  cmp     eax, ecx
0x100443871  jnz     short loc_1004438BA
0x100443873  mov     rax, cs:off_1005E8018; "<LocalDB::loadUserInstanceDll|API|SNI> "...
0x10044387a  test    rax, rax
0x10044387d  jz      short loc_1004438BA
0x10044387f  cmp     cs:_bidID, rsi
0x100443886  jz      short loc_1004438BA
0x100443888  mov     r10, cs:off_1005D39F0
0x10044388f  mov     [rsp+1A0h+var_178], rbx
0x100443894  mov     rax, cs:off_1005E8018; "<LocalDB::loadUserInstanceDll|API|SNI> "...
0x10044389b  mov     qword ptr [rsp+1A0h+var_180], rax
0x1004438a0  lea     r9, [rsp+1A0h+var_148]
0x1004438a5  xor     r8d, r8d
0x1004438a8  xor     edx, edx
0x1004438aa  mov     rcx, cs:_bidID
0x1004438b1  mov     rax, r10
0x1004438b4  call    cs:__guard_dispatch_icall_fptr
0x1004438ba  mov     edi, ebx
0x1004438bc  mov     rax, [r12]
0x1004438c0  test    rax, rax
0x1004438c3  jnz     loc_100443D8A
0x1004438c9  mov     rax, [r12+18h]
0x1004438ce  mov     [rsp+1A0h+var_158], rax
0x1004438d3  mov     rcx, [rax+10h]
0x1004438d7  add     rcx, 20h ; ' '
0x1004438db  mov     rax, [rcx]
0x1004438de  mov     rax, [rax+8]
0x1004438e2  call    cs:__guard_dispatch_icall_fptr
0x1004438e8  mov     dword ptr [rsp+1A0h+var_150], 1
0x1004438f0  mov     rax, [r12]
0x1004438f4  test    rax, rax
0x1004438f7  jz      short loc_100443918
0x1004438f9  mov     rax, [rsp+1A0h+var_158]
0x1004438fe  mov     rcx, [rax+10h]
0x100443902  add     rcx, 20h ; ' '
0x100443906  mov     rax, [rcx]
0x100443909  mov     rax, [rax+18h]
0x10044390d  call    cs:__guard_dispatch_icall_fptr
0x100443913  jmp     loc_100443D8A
0x100443918  lea     r9, [rsp+1A0h+var_160]; enum LocalDBErrorState *
0x10044391d  mov     r8d, 104h; unsigned int
0x100443923  lea     rdx, [rsp+1A0h+LibFileName]; char *
0x100443928  mov     rcx, r12; this
0x10044392b  call    ?GetUserInstanceDllPath@LocalDB@@AEAAJPEADKPEAW4LocalDBErrorState@@@Z; LocalDB::GetUserInstanceDllPath(char *,ulong,LocalDBErrorState *)
0x100443930  mov     edi, eax
0x100443932  test    eax, eax
0x100443934  jz      loc_100443A12
0x10044393a  mov     esi, 9
0x10044393f  mov     r14d, 0C3E9h
0x100443945  test    byte ptr cs:_bidGblFlags, 2
0x10044394c  jz      short loc_1004439AB
0x10044394e  mov     rax, cs:off_1005E6260; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443955  test    rax, rax
0x100443958  jz      short loc_1004439AB
0x10044395a  mov     ecx, dword ptr [rsp+1A0h+var_160]
0x10044395e  test    ecx, ecx
0x100443960  jz      short loc_100443983
0x100443962  sub     ecx, 1
0x100443965  jz      short loc_10044397E
0x100443967  sub     ecx, 1
0x10044396a  jz      short loc_100443977
0x10044396c  cmp     ecx, 1
0x10044396f  jnz     short loc_10044397E
0x100443971  lea     ecx, [r14+2]
0x100443975  jmp     short loc_100443988
0x100443977  mov     ecx, 0C3EAh
0x10044397c  jmp     short loc_100443988
0x10044397e  mov     ecx, r14d
0x100443981  jmp     short loc_100443988
0x100443983  mov     ecx, 0C3E8h; unsigned int
0x100443988  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10044398d  mov     dword ptr [rsp+1A0h+var_178], edi
0x100443991  mov     [rsp+1A0h+var_180], eax
0x100443995  mov     r9d, esi
0x100443998  mov     r8, cs:off_1005E6260; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x10044399f  mov     edx, 3D400h
0x1004439a4  xor     ecx, ecx
0x1004439a6  call    _bidTraceW
0x1004439ab  mov     ecx, dword ptr [rsp+1A0h+var_160]
0x1004439af  test    ecx, ecx
0x1004439b1  jz      short loc_1004439D2
0x1004439b3  sub     ecx, 1
0x1004439b6  jz      short loc_1004439D8
0x1004439b8  sub     ecx, 1
0x1004439bb  jz      short loc_1004439CA
0x1004439bd  cmp     ecx, 1
0x1004439c0  jnz     short loc_1004439D8
0x1004439c2  mov     r14d, 0C3EBh
0x1004439c8  jmp     short loc_1004439D8
0x1004439ca  mov     r14d, 0C3EAh
0x1004439d0  jmp     short loc_1004439D8
0x1004439d2  mov     r14d, 0C3E8h
0x1004439d8  mov     r8d, r14d
0x1004439db  mov     edx, edi
0x1004439dd  mov     ecx, esi
0x1004439df  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004439e4  test    byte ptr cs:_bidGblFlags, 2
0x1004439eb  jz      loc_100443B5A
0x1004439f1  mov     rax, cs:off_1005E6268; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x1004439f8  test    rax, rax
0x1004439fb  jz      loc_100443B5A
0x100443a01  mov     r8, cs:off_1005E6268; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443a08  mov     edx, 3DC00h
0x100443a0d  jmp     loc_100443B4F
0x100443a12  lea     rax, [rsp+1A0h+LibFileName]
0x100443a17  mov     rdx, rsi
0x100443a1a  inc     rdx
0x100443a1d  cmp     [rax+rdx], bl
0x100443a20  jnz     short loc_100443A1A
0x100443a22  inc     rdx
0x100443a25  mov     [rsp+1A0h+var_180], 3; int
0x100443a2d  lea     r9, asc_100585218; " \t"
0x100443a34  xor     r8d, r8d
0x100443a37  lea     rcx, [rsp+1A0h+LibFileName]; Source
0x100443a3c  call    StrTrimBoth_Sys
0x100443a41  mov     edi, eax
0x100443a43  test    eax, eax
0x100443a45  jz      short loc_100443AC6
0x100443a47  mov     esi, 9
0x100443a4c  test    byte ptr cs:_bidGblFlags, 2
0x100443a53  jz      short loc_100443A89
0x100443a55  mov     rax, cs:off_1005E6270; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443a5c  test    rax, rax
0x100443a5f  jz      short loc_100443A89
0x100443a61  mov     ecx, 0C3EBh; unsigned int
0x100443a66  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100443a6b  mov     dword ptr [rsp+1A0h+var_178], edi
0x100443a6f  mov     [rsp+1A0h+var_180], eax
0x100443a73  mov     r9d, esi
0x100443a76  mov     r8, cs:off_1005E6270; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443a7d  mov     edx, 40000h
0x100443a82  xor     ecx, ecx
0x100443a84  call    _bidTraceW
0x100443a89  mov     r8d, 0C3EBh
0x100443a8f  mov     edx, edi
0x100443a91  mov     ecx, esi
0x100443a93  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100443a98  test    byte ptr cs:_bidGblFlags, 2
0x100443a9f  jz      loc_100443B5A
0x100443aa5  mov     rax, cs:off_1005E6278; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443aac  test    rax, rax
0x100443aaf  jz      loc_100443B5A
0x100443ab5  mov     r8, cs:off_1005E6278; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443abc  mov     edx, 40800h
0x100443ac1  jmp     loc_100443B4F
0x100443ac6  lea     rax, [rsp+1A0h+LibFileName]
0x100443acb  inc     rsi
0x100443ace  cmp     [rax+rsi], bl
0x100443ad1  jnz     short loc_100443ACB
0x100443ad3  test    rsi, rsi
0x100443ad6  jnz     loc_100443B79
0x100443adc  lea     edi, [rsi+0Dh]
0x100443adf  lea     esi, [rdi-4]
0x100443ae2  test    byte ptr cs:_bidGblFlags, 2
0x100443ae9  jz      short loc_100443B1F
0x100443aeb  mov     rax, cs:off_1005E6280; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443af2  test    rax, rax
0x100443af5  jz      short loc_100443B1F
0x100443af7  mov     ecx, 0C3EBh; unsigned int
0x100443afc  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100443b01  mov     dword ptr [rsp+1A0h+var_178], edi
0x100443b05  mov     [rsp+1A0h+var_180], eax
0x100443b09  mov     r9d, esi
0x100443b0c  mov     r8, cs:off_1005E6280; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443b13  mov     edx, 42C00h
0x100443b18  xor     ecx, ecx
0x100443b1a  call    _bidTraceW
0x100443b1f  mov     r8d, 0C3EBh
0x100443b25  mov     edx, edi
0x100443b27  mov     ecx, esi
0x100443b29  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100443b2e  test    byte ptr cs:_bidGblFlags, 2
0x100443b35  jz      short loc_100443B5A
0x100443b37  mov     rax, cs:off_1005E6288; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443b3e  test    rax, rax
0x100443b41  jz      short loc_100443B5A
0x100443b43  mov     r8, cs:off_1005E6288; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443b4a  mov     edx, 43400h
0x100443b4f  mov     r9d, edi
0x100443b52  xor     ecx, ecx
0x100443b54  call    _bidTraceW
0x100443b59  nop
0x100443b5a  mov     rax, [rsp+1A0h+var_158]
0x100443b5f  mov     rcx, [rax+10h]
0x100443b63  add     rcx, 20h ; ' '
0x100443b67  mov     rax, [rcx]
0x100443b6a  mov     rax, [rax+18h]
0x100443b6e  call    cs:__guard_dispatch_icall_fptr
0x100443b74  jmp     loc_100443D80
0x100443b79  lea     rcx, [rsp+1A0h+LibFileName]; lpLibFileName
0x100443b7e  call    cs:__imp_LoadLibraryA
0x100443b84  mov     r14, rax
0x100443b87  test    rax, rax
0x100443b8a  jnz     loc_100443C34
0x100443b90  call    cs:__imp_GetLastError
0x100443b96  mov     edi, eax
0x100443b98  lea     esi, [r14+9]
0x100443b9c  mov     r14d, 0C3ECh
0x100443ba2  test    byte ptr cs:_bidGblFlags, 2
0x100443ba9  jz      short loc_100443BDD
0x100443bab  mov     rax, cs:off_1005E6290; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443bb2  test    rax, rax
0x100443bb5  jz      short loc_100443BDD
0x100443bb7  mov     ecx, r14d; unsigned int
0x100443bba  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100443bbf  mov     dword ptr [rsp+1A0h+var_178], edi
0x100443bc3  mov     [rsp+1A0h+var_180], eax
0x100443bc7  mov     r9d, esi
0x100443bca  mov     r8, cs:off_1005E6290; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443bd1  mov     edx, 45C00h
0x100443bd6  xor     ecx, ecx
0x100443bd8  call    _bidTraceW
0x100443bdd  mov     r8d, r14d
0x100443be0  mov     edx, edi
0x100443be2  mov     ecx, esi
0x100443be4  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100443be9  test    byte ptr cs:_bidGblFlags, 2
0x100443bf0  jz      short loc_100443C15
0x100443bf2  mov     rax, cs:off_1005E6298; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443bf9  test    rax, rax
0x100443bfc  jz      short loc_100443C15
0x100443bfe  mov     r9d, edi
0x100443c01  mov     r8, cs:off_1005E6298; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443c08  mov     edx, 46400h
0x100443c0d  xor     ecx, ecx
0x100443c0f  call    _bidTraceW
0x100443c14  nop
0x100443c15  mov     rax, [rsp+1A0h+var_158]
0x100443c1a  mov     rcx, [rax+10h]
0x100443c1e  add     rcx, 20h ; ' '
0x100443c22  mov     rax, [rcx]
0x100443c25  mov     rax, [rax+18h]
0x100443c29  call    cs:__guard_dispatch_icall_fptr
0x100443c2f  jmp     loc_100443D7C
0x100443c34  lea     rdx, aLocaldbstartin; "LocalDBStartInstance"
0x100443c3b  mov     rcx, r14; hModule
0x100443c3e  call    cs:__imp_GetProcAddress
0x100443c44  mov     [r12+10h], rax
0x100443c49  lea     rdx, aLocaldbformatm; "LocalDBFormatMessage"
0x100443c50  mov     rcx, r14; hModule
0x100443c53  call    cs:__imp_GetProcAddress
0x100443c59  mov     [r12+8], rax
0x100443c5e  cmp     [r12+10h], rbx
0x100443c63  jz      short loc_100443CD4
0x100443c65  test    rax, rax
0x100443c68  jz      short loc_100443CD4
0x100443c6a  mov     rax, r14
0x100443c6d  xchg    rax, [r12]
0x100443c71  test    rax, rax
0x100443c74  mov     rax, [rsp+1A0h+var_158]
0x100443c79  mov     rcx, [rax+10h]
0x100443c7d  jnz     loc_100443D62
0x100443c83  add     rcx, 20h ; ' '
0x100443c87  mov     rax, [rcx]
0x100443c8a  mov     rax, [rax+18h]
0x100443c8e  call    cs:__guard_dispatch_icall_fptr
0x100443c94  mov     eax, cs:_bidGblFlags
0x100443c9a  mov     ecx, 20002h
0x100443c9f  and     eax, ecx
0x100443ca1  cmp     eax, ecx
0x100443ca3  jnz     loc_100443DBF
0x100443ca9  mov     rax, cs:off_1005E62B0; "<LocalDB::loadUserInstanceDll|RET|SNI> "...
0x100443cb0  test    rax, rax
0x100443cb3  jz      loc_100443DBF
0x100443cb9  xor     r9d, r9d
0x100443cbc  mov     r8, cs:off_1005E62B0; "<LocalDB::loadUserInstanceDll|RET|SNI> "...
0x100443cc3  mov     edx, 4F000h
0x100443cc8  xor     ecx, ecx
0x100443cca  call    _bidTraceW
0x100443ccf  jmp     loc_100443DBF
0x100443cd4  call    cs:__imp_GetLastError
0x100443cda  mov     edi, eax
0x100443cdc  mov     esi, 9
0x100443ce1  test    byte ptr cs:_bidGblFlags, 2
0x100443ce8  jz      short loc_100443D1E
0x100443cea  mov     rax, cs:off_1005E62A0; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x100443cf1  test    rax, rax
0x100443cf4  jz      short loc_100443D1E
0x100443cf6  mov     ecx, 0C3EDh; unsigned int
0x100443cfb  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
  ... truncated ...
```
