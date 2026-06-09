# LocalDB::loadUserInstanceDll(void)

- ea: `0x18017e590`
- end: `0x18017ec0f`
- name: `?loadUserInstanceDll@LocalDB@@QEAAKXZ`
- size: `1663`
- prototype: `unsigned int __fastcall(LocalDB *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18017e1d0`

## callees

- `0x180001f70`
- `0x1800030c0`
- `0x180003d80`
- `0x180159ed0`
- `0x18015a6f0`
- `0x18015a880`
- `0x18017d980`
- `0x18017e590`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18017eb8c`
- `KERNEL32!FreeLibrary` at `0x18017eb8c`
- `KERNEL32!GetLastError` at `0x18017e966`
- `KERNEL32!GetLastError` at `0x18017eade`
- `KERNEL32!GetLastError` at `0x18017e966`
- `KERNEL32!GetLastError` at `0x18017eade`
- `KERNEL32!GetProcAddress` at `0x18017ea20`
- `KERNEL32!GetProcAddress` at `0x18017ea34`
- `KERNEL32!GetProcAddress` at `0x18017ea20`
- `KERNEL32!GetProcAddress` at `0x18017ea34`
- `KERNEL32!LoadLibraryA` at `0x18017e954`
- `KERNEL32!LoadLibraryA` at `0x18017e954`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall LocalDB::loadUserInstanceDll(LocalDB *this)
{
  __int64 v2; // rdi
  unsigned int v3; // ebp
  unsigned int UserInstanceDllPath; // ebx
  unsigned int v5; // edi
  unsigned int v6; // ecx
  __int64 v7; // rdx
  HMODULE LibraryA; // rax
  HMODULE v9; // rdi
  FARPROC ProcAddress; // rax
  int v12; // [rsp+40h] [rbp-148h] BYREF
  __int64 v13; // [rsp+48h] [rbp-140h]
  int v14; // [rsp+50h] [rbp-138h]
  __int64 v15; // [rsp+58h] [rbp-130h] BYREF
  CHAR LibFileName[272]; // [rsp+60h] [rbp-128h] BYREF

  v2 = -1;
  v15 = -1;
  v3 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266E48[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_180248060[0])(
      bidID,
      0,
      0,
      &v15,
      off_180266E48[0],
      0);
  UserInstanceDllPath = 0;
  v12 = 0;
  if ( *(_QWORD *)this )
    goto LABEL_73;
  v13 = *((_QWORD *)this + 3);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v13 + 16) + 32LL) + 8LL))(*(_QWORD *)(v13 + 16) + 32LL);
  v14 = 1;
  if ( *(_QWORD *)this )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v13 + 16) + 32LL) + 24LL))(*(_QWORD *)(v13 + 16) + 32LL);
    goto LABEL_73;
  }
  UserInstanceDllPath = LocalDB::GetUserInstanceDllPath(this, LibFileName, 0x104u, (enum LocalDBErrorState *)&v12);
  if ( UserInstanceDllPath )
  {
    v5 = 50153;
    if ( (bidGblFlags & 2) == 0 || !off_180265530[0] )
      goto LABEL_20;
    switch ( v12 )
    {
      case 0:
        v6 = 50152;
        break;
      case 1:
        goto LABEL_15;
      case 2:
        v6 = 50154;
        break;
      case 3:
        v6 = 50155;
        break;
      default:
LABEL_15:
        v6 = 50153;
        break;
    }
    SniErrorIdFromStringId(v6);
    bidTraceW(off_1802621E8[0], 250880, off_180265530[0], 8);
LABEL_20:
    if ( v12 )
    {
      if ( v12 != 1 )
      {
        if ( v12 == 2 )
        {
          v5 = 50154;
        }
        else if ( v12 == 3 )
        {
          v5 = 50155;
        }
      }
    }
    else
    {
      v5 = 50152;
    }
    SNISetLastError(8, UserInstanceDllPath, v5);
    if ( (bidGblFlags & 2) != 0 && off_180265538[0] )
      bidTraceW(off_1802621F0[0], 252928, off_180265538[0], UserInstanceDllPath);
LABEL_49:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v13 + 16) + 32LL) + 24LL))(*(_QWORD *)(v13 + 16) + 32LL);
LABEL_72:
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 1) = 0;
LABEL_73:
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265588[0] )
      bidTraceW(off_180262240[0], 340992, off_180265588[0], UserInstanceDllPath);
    v3 = UserInstanceDllPath;
    goto LABEL_77;
  }
  v7 = -1;
  do
    ++v7;
  while ( LibFileName[v7] );
  UserInstanceDllPath = StrTrimBoth_Sys(LibFileName, 3);
  if ( UserInstanceDllPath )
  {
    if ( (bidGblFlags & 2) != 0 && off_180265540[0] )
    {
      SniErrorIdFromStringId(0xC3EBu);
      bidTraceW(off_1802621F8[0], 0x40000, off_180265540[0], 8);
    }
    SNISetLastError(8, UserInstanceDllPath, 50155);
    if ( (bidGblFlags & 2) != 0 && off_180265548[0] )
      bidTraceW(off_180262200[0], 264192, off_180265548[0], UserInstanceDllPath);
    goto LABEL_49;
  }
  do
    ++v2;
  while ( LibFileName[v2] );
  if ( !v2 )
  {
    UserInstanceDllPath = 13;
    if ( (bidGblFlags & 2) != 0 && off_180265550[0] )
    {
      SniErrorIdFromStringId(0xC3EBu);
      bidTraceW(off_180262208[0], 273408, off_180265550[0], 8);
    }
    SNISetLastError(8, 13, 50155);
    if ( (bidGblFlags & 2) != 0 && off_180265558[0] )
      bidTraceW(off_180262210[0], 275456, off_180265558[0], 13);
    goto LABEL_49;
  }
  LibraryA = LoadLibraryA(LibFileName);
  v9 = LibraryA;
  if ( !LibraryA )
  {
    UserInstanceDllPath = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_180265560[0] )
    {
      SniErrorIdFromStringId(0xC3ECu);
      bidTraceW(off_180262218[0], 285696, off_180265560[0], 8);
    }
    SNISetLastError(8, UserInstanceDllPath, 50156);
    if ( (bidGblFlags & 2) != 0 && off_180265568[0] )
      bidTraceW(off_180262220[0], 287744, off_180265568[0], UserInstanceDllPath);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v13 + 16) + 32LL) + 24LL))(*(_QWORD *)(v13 + 16) + 32LL);
LABEL_71:
    if ( !UserInstanceDllPath )
      goto LABEL_73;
    goto LABEL_72;
  }
  *((_QWORD *)this + 2) = GetProcAddress(LibraryA, "LocalDBStartInstance");
  ProcAddress = GetProcAddress(v9, "LocalDBFormatMessage");
  *((_QWORD *)this + 1) = ProcAddress;
  if ( !*((_QWORD *)this + 2) || !ProcAddress )
  {
    UserInstanceDllPath = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_180265570[0] )
    {
      SniErrorIdFromStringId(0xC3EDu);
      bidTraceW(off_180262228[0], 305152, off_180265570[0], 8);
    }
    SNISetLastError(8, UserInstanceDllPath, 50157);
    if ( (bidGblFlags & 2) != 0 && off_180265578[0] )
      bidTraceW(off_180262230[0], 307200, off_180265578[0], UserInstanceDllPath);
    goto LABEL_70;
  }
  if ( _InterlockedExchange64((volatile __int64 *)this, (__int64)v9) )
  {
LABEL_70:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v13 + 16) + 32LL) + 24LL))(*(_QWORD *)(v13 + 16) + 32LL);
    FreeLibrary(v9);
    goto LABEL_71;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v13 + 16) + 32LL) + 24LL))(*(_QWORD *)(v13 + 16) + 32LL);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265580[0] )
    bidTraceW(off_180262238[0], 323584, off_180265580[0], 0);
LABEL_77:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v15);
  return v3;
}

```

## disassembly

```asm
0x18017e590  mov     [rsp+arg_8], rbx
0x18017e595  mov     [rsp+arg_10], rbp
0x18017e59a  mov     [rsp+arg_18], rsi
0x18017e59f  push    rdi
0x18017e5a0  sub     rsp, 180h
0x18017e5a7  mov     rax, cs:__security_cookie
0x18017e5ae  xor     rax, rsp
0x18017e5b1  mov     [rsp+188h+var_18], rax
0x18017e5b9  mov     rsi, rcx
0x18017e5bc  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18017e5c3  mov     [rsp+188h+var_130], rdi
0x18017e5c8  mov     eax, cs:_bidGblFlags
0x18017e5ce  and     eax, 20004h
0x18017e5d3  xor     ebp, ebp
0x18017e5d5  cmp     eax, 20004h
0x18017e5da  jnz     short loc_18017E623
0x18017e5dc  mov     rax, cs:off_180266E48; "<LocalDB::loadUserInstanceDll|API|SNI> "...
0x18017e5e3  test    rax, rax
0x18017e5e6  jz      short loc_18017E623
0x18017e5e8  cmp     cs:_bidID, rdi
0x18017e5ef  jz      short loc_18017E623
0x18017e5f1  mov     r10, cs:off_180248060
0x18017e5f8  mov     [rsp+188h+var_160], rbp
0x18017e5fd  mov     rax, cs:off_180266E48; "<LocalDB::loadUserInstanceDll|API|SNI> "...
0x18017e604  mov     qword ptr [rsp+188h+var_168], rax
0x18017e609  lea     r9, [rsp+188h+var_130]
0x18017e60e  xor     r8d, r8d
0x18017e611  xor     edx, edx
0x18017e613  mov     rcx, cs:_bidID
0x18017e61a  mov     rax, r10
0x18017e61d  call    cs:__guard_dispatch_icall_fptr
0x18017e623  mov     ebx, ebp
0x18017e625  mov     [rsp+188h+var_148], ebp
0x18017e629  mov     rax, [rsi]
0x18017e62c  test    rax, rax
0x18017e62f  jnz     loc_18017EB9E
0x18017e635  mov     rax, [rsi+18h]
0x18017e639  mov     [rsp+188h+var_140], rax
0x18017e63e  mov     rcx, [rax+10h]
0x18017e642  add     rcx, 20h ; ' '
0x18017e646  mov     rax, [rcx]
0x18017e649  mov     rax, [rax+8]
0x18017e64d  call    cs:__guard_dispatch_icall_fptr
0x18017e653  mov     [rsp+188h+var_138], 1
0x18017e65b  mov     rax, [rsi]
0x18017e65e  test    rax, rax
0x18017e661  jz      short loc_18017E683
0x18017e663  mov     rax, [rsp+188h+var_140]
0x18017e668  mov     rcx, [rax+10h]
0x18017e66c  add     rcx, 20h ; ' '
0x18017e670  mov     rax, [rcx]
0x18017e673  mov     rax, [rax+18h]
0x18017e677  call    cs:__guard_dispatch_icall_fptr
0x18017e67d  nop
0x18017e67e  jmp     loc_18017EB9E
0x18017e683  lea     r9, [rsp+188h+var_148]; enum LocalDBErrorState *
0x18017e688  mov     r8d, 104h; unsigned int
0x18017e68e  lea     rdx, [rsp+188h+LibFileName]; char *
0x18017e693  mov     rcx, rsi; this
0x18017e696  call    ?GetUserInstanceDllPath@LocalDB@@AEAAJPEADKPEAW4LocalDBErrorState@@@Z; LocalDB::GetUserInstanceDllPath(char *,ulong,LocalDBErrorState *)
0x18017e69b  mov     ebx, eax
0x18017e69d  test    eax, eax
0x18017e69f  jz      loc_18017E7A2
0x18017e6a5  mov     edi, 0C3E9h
0x18017e6aa  test    byte ptr cs:_bidGblFlags, 2
0x18017e6b1  jz      short loc_18017E718
0x18017e6b3  mov     rax, cs:off_180265530; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e6ba  test    rax, rax
0x18017e6bd  jz      short loc_18017E718
0x18017e6bf  mov     ecx, [rsp+188h+var_148]
0x18017e6c3  test    ecx, ecx
0x18017e6c5  jz      short loc_18017E6E8
0x18017e6c7  sub     ecx, 1
0x18017e6ca  jz      short loc_18017E6D6
0x18017e6cc  sub     ecx, 1
0x18017e6cf  jz      short loc_18017E6E1
0x18017e6d1  cmp     ecx, 1
0x18017e6d4  jz      short loc_18017E6DA
0x18017e6d6  mov     ecx, edi
0x18017e6d8  jmp     short loc_18017E6ED
0x18017e6da  mov     ecx, 0C3EBh
0x18017e6df  jmp     short loc_18017E6ED
0x18017e6e1  mov     ecx, 0C3EAh
0x18017e6e6  jmp     short loc_18017E6ED
0x18017e6e8  mov     ecx, 0C3E8h; unsigned int
0x18017e6ed  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18017e6f2  mov     dword ptr [rsp+188h+var_160], ebx
0x18017e6f6  mov     [rsp+188h+var_168], eax
0x18017e6fa  mov     r9d, 8
0x18017e700  mov     r8, cs:off_180265530; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e707  mov     edx, 3D400h
0x18017e70c  mov     rcx, cs:off_1802621E8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017e713  call    _bidTraceW
0x18017e718  mov     ecx, [rsp+188h+var_148]
0x18017e71c  test    ecx, ecx
0x18017e71e  jz      short loc_18017E73D
0x18017e720  sub     ecx, 1
0x18017e723  jz      short loc_18017E742
0x18017e725  sub     ecx, 1
0x18017e728  jz      short loc_18017E736
0x18017e72a  cmp     ecx, 1
0x18017e72d  jnz     short loc_18017E742
0x18017e72f  mov     edi, 0C3EBh
0x18017e734  jmp     short loc_18017E742
0x18017e736  mov     edi, 0C3EAh
0x18017e73b  jmp     short loc_18017E742
0x18017e73d  mov     edi, 0C3E8h
0x18017e742  mov     r8d, edi
0x18017e745  mov     edx, ebx
0x18017e747  mov     ecx, 8
0x18017e74c  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18017e751  test    byte ptr cs:_bidGblFlags, 2
0x18017e758  jz      short loc_18017E782
0x18017e75a  mov     rax, cs:off_180265538; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e761  test    rax, rax
0x18017e764  jz      short loc_18017E782
0x18017e766  mov     r9d, ebx
0x18017e769  mov     r8, cs:off_180265538; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e770  mov     edx, 3DC00h
0x18017e775  mov     rcx, cs:off_1802621F0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017e77c  call    _bidTraceW
0x18017e781  nop
0x18017e782  mov     rax, [rsp+188h+var_140]
0x18017e787  mov     rcx, [rax+10h]
0x18017e78b  add     rcx, 20h ; ' '
0x18017e78f  mov     rax, [rcx]
0x18017e792  mov     rax, [rax+18h]
0x18017e796  call    cs:__guard_dispatch_icall_fptr
0x18017e79c  nop
0x18017e79d  jmp     loc_18017EB96
0x18017e7a2  lea     rax, [rsp+188h+LibFileName]
0x18017e7a7  mov     rdx, rdi
0x18017e7aa  nop     word ptr [rax+rax+00h]
0x18017e7b0  inc     rdx
0x18017e7b3  cmp     byte ptr [rax+rdx], 0
0x18017e7b7  jnz     short loc_18017E7B0
0x18017e7b9  inc     rdx
0x18017e7bc  mov     [rsp+188h+var_168], 3; int
0x18017e7c4  lea     r9, asc_18020FA88; " \t"
0x18017e7cb  xor     r8d, r8d
0x18017e7ce  lea     rcx, [rsp+188h+LibFileName]; Src
0x18017e7d3  call    StrTrimBoth_Sys
0x18017e7d8  mov     ebx, eax
0x18017e7da  test    eax, eax
0x18017e7dc  jz      loc_18017E88A
0x18017e7e2  test    byte ptr cs:_bidGblFlags, 2
0x18017e7e9  jz      short loc_18017E827
0x18017e7eb  mov     rax, cs:off_180265540; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e7f2  test    rax, rax
0x18017e7f5  jz      short loc_18017E827
0x18017e7f7  mov     ecx, 0C3EBh; unsigned int
0x18017e7fc  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18017e801  mov     dword ptr [rsp+188h+var_160], ebx
0x18017e805  mov     [rsp+188h+var_168], eax
0x18017e809  mov     r9d, 8
0x18017e80f  mov     r8, cs:off_180265540; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e816  mov     edx, 40000h
0x18017e81b  mov     rcx, cs:off_1802621F8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017e822  call    _bidTraceW
0x18017e827  mov     r8d, 0C3EBh
0x18017e82d  mov     edx, ebx
0x18017e82f  mov     ecx, 8
0x18017e834  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18017e839  test    byte ptr cs:_bidGblFlags, 2
0x18017e840  jz      short loc_18017E86A
0x18017e842  mov     rax, cs:off_180265548; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e849  test    rax, rax
0x18017e84c  jz      short loc_18017E86A
0x18017e84e  mov     r9d, ebx
0x18017e851  mov     r8, cs:off_180265548; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e858  mov     edx, 40800h
0x18017e85d  mov     rcx, cs:off_180262200; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017e864  call    _bidTraceW
0x18017e869  nop
0x18017e86a  mov     rax, [rsp+188h+var_140]
0x18017e86f  mov     rcx, [rax+10h]
0x18017e873  add     rcx, 20h ; ' '
0x18017e877  mov     rax, [rcx]
0x18017e87a  mov     rax, [rax+18h]
0x18017e87e  call    cs:__guard_dispatch_icall_fptr
0x18017e884  nop
0x18017e885  jmp     loc_18017EB96
0x18017e88a  lea     rax, [rsp+188h+LibFileName]
0x18017e88f  nop
0x18017e890  inc     rdi
0x18017e893  cmp     byte ptr [rax+rdi], 0
0x18017e897  jnz     short loc_18017E890
0x18017e899  test    rdi, rdi
0x18017e89c  jnz     loc_18017E94F
0x18017e8a2  mov     ebx, 0Dh
0x18017e8a7  test    byte ptr cs:_bidGblFlags, 2
0x18017e8ae  jz      short loc_18017E8EC
0x18017e8b0  mov     rax, cs:off_180265550; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e8b7  test    rax, rax
0x18017e8ba  jz      short loc_18017E8EC
0x18017e8bc  mov     ecx, 0C3EBh; unsigned int
0x18017e8c1  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18017e8c6  mov     dword ptr [rsp+188h+var_160], ebx
0x18017e8ca  mov     [rsp+188h+var_168], eax
0x18017e8ce  mov     r9d, 8
0x18017e8d4  mov     r8, cs:off_180265550; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e8db  mov     edx, 42C00h
0x18017e8e0  mov     rcx, cs:off_180262208; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017e8e7  call    _bidTraceW
0x18017e8ec  mov     r8d, 0C3EBh
0x18017e8f2  mov     edx, ebx
0x18017e8f4  mov     ecx, 8
0x18017e8f9  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18017e8fe  test    byte ptr cs:_bidGblFlags, 2
0x18017e905  jz      short loc_18017E92F
0x18017e907  mov     rax, cs:off_180265558; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e90e  test    rax, rax
0x18017e911  jz      short loc_18017E92F
0x18017e913  mov     r9d, ebx
0x18017e916  mov     r8, cs:off_180265558; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e91d  mov     edx, 43400h
0x18017e922  mov     rcx, cs:off_180262210; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017e929  call    _bidTraceW
0x18017e92e  nop
0x18017e92f  mov     rax, [rsp+188h+var_140]
0x18017e934  mov     rcx, [rax+10h]
0x18017e938  add     rcx, 20h ; ' '
0x18017e93c  mov     rax, [rcx]
0x18017e93f  mov     rax, [rax+18h]
0x18017e943  call    cs:__guard_dispatch_icall_fptr
0x18017e949  nop
0x18017e94a  jmp     loc_18017EB96
0x18017e94f  lea     rcx, [rsp+188h+LibFileName]; lpLibFileName
0x18017e954  call    cs:__imp_LoadLibraryA
0x18017e95a  mov     rdi, rax
0x18017e95d  test    rax, rax
0x18017e960  jnz     loc_18017EA16
0x18017e966  call    cs:__imp_GetLastError
0x18017e96c  mov     ebx, eax
0x18017e96e  test    byte ptr cs:_bidGblFlags, 2
0x18017e975  jz      short loc_18017E9B3
0x18017e977  mov     rax, cs:off_180265560; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e97e  test    rax, rax
0x18017e981  jz      short loc_18017E9B3
0x18017e983  mov     ecx, 0C3ECh; unsigned int
0x18017e988  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18017e98d  mov     dword ptr [rsp+188h+var_160], ebx
0x18017e991  mov     [rsp+188h+var_168], eax
0x18017e995  mov     r9d, 8
0x18017e99b  mov     r8, cs:off_180265560; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e9a2  mov     edx, 45C00h
0x18017e9a7  mov     rcx, cs:off_180262218; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017e9ae  call    _bidTraceW
0x18017e9b3  mov     r8d, 0C3ECh
0x18017e9b9  mov     edx, ebx
0x18017e9bb  mov     ecx, 8
0x18017e9c0  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18017e9c5  test    byte ptr cs:_bidGblFlags, 2
0x18017e9cc  jz      short loc_18017E9F6
0x18017e9ce  mov     rax, cs:off_180265568; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e9d5  test    rax, rax
0x18017e9d8  jz      short loc_18017E9F6
0x18017e9da  mov     r9d, ebx
0x18017e9dd  mov     r8, cs:off_180265568; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x18017e9e4  mov     edx, 46400h
0x18017e9e9  mov     rcx, cs:off_180262220; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18017e9f0  call    _bidTraceW
0x18017e9f5  nop
0x18017e9f6  mov     rax, [rsp+188h+var_140]
0x18017e9fb  mov     rcx, [rax+10h]
0x18017e9ff  add     rcx, 20h ; ' '
0x18017ea03  mov     rax, [rcx]
0x18017ea06  mov     rax, [rax+18h]
0x18017ea0a  call    cs:__guard_dispatch_icall_fptr
0x18017ea10  nop
0x18017ea11  jmp     loc_18017EB92
0x18017ea16  lea     rdx, aLocaldbstartin; "LocalDBStartInstance"
0x18017ea1d  mov     rcx, rdi; hModule
0x18017ea20  call    cs:__imp_GetProcAddress
0x18017ea26  mov     [rsi+10h], rax
0x18017ea2a  lea     rdx, aLocaldbformatm; "LocalDBFormatMessage"
0x18017ea31  mov     rcx, rdi; hModule
0x18017ea34  call    cs:__imp_GetProcAddress
0x18017ea3a  mov     [rsi+8], rax
0x18017ea3e  cmp     qword ptr [rsi+10h], 0
0x18017ea43  jz      loc_18017EADE
0x18017ea49  test    rax, rax
0x18017ea4c  jz      loc_18017EADE
0x18017ea52  mov     rax, rdi
0x18017ea55  xchg    rax, [rsi]
0x18017ea58  test    rax, rax
0x18017ea5b  jz      short loc_18017EA7D
0x18017ea5d  mov     rax, [rsp+188h+var_140]
0x18017ea62  mov     rcx, [rax+10h]
0x18017ea66  add     rcx, 20h ; ' '
0x18017ea6a  mov     rax, [rcx]
0x18017ea6d  mov     rax, [rax+18h]
0x18017ea71  call    cs:__guard_dispatch_icall_fptr
0x18017ea77  nop
0x18017ea78  jmp     loc_18017EB89
0x18017ea7d  mov     rax, [rsp+188h+var_140]
0x18017ea82  mov     rcx, [rax+10h]
0x18017ea86  add     rcx, 20h ; ' '
0x18017ea8a  mov     rax, [rcx]
0x18017ea8d  mov     rax, [rax+18h]
  ... truncated ...
```
