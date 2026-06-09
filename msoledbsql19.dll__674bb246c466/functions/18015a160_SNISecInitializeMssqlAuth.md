# SNISecInitializeMssqlAuth

- ea: `0x18015a160`
- end: `0x18015a5a6`
- name: `SNISecInitializeMssqlAuth`
- size: `1094`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1801a0300`

## callees

- `0x1800030c0`
- `0x18015a160`
- `0x18015a6f0`
- `0x18015a880`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18015a4da`
- `KERNEL32!FreeLibrary` at `0x18015a4da`
- `KERNEL32!GetLastError` at `0x18015a18d`
- `KERNEL32!GetLastError` at `0x18015a245`
- `KERNEL32!GetLastError` at `0x18015a2e0`
- `KERNEL32!GetLastError` at `0x18015a37b`
- `KERNEL32!GetLastError` at `0x18015a41a`
- `KERNEL32!GetLastError` at `0x18015a4f9`
- `KERNEL32!GetLastError` at `0x18015a18d`
- `KERNEL32!GetLastError` at `0x18015a245`
- `KERNEL32!GetLastError` at `0x18015a2e0`
- `KERNEL32!GetLastError` at `0x18015a37b`
- `KERNEL32!GetLastError` at `0x18015a41a`
- `KERNEL32!GetLastError` at `0x18015a4f9`
- `KERNEL32!GetProcAddress` at `0x18015a233`
- `KERNEL32!GetProcAddress` at `0x18015a2ce`
- `KERNEL32!GetProcAddress` at `0x18015a369`
- `KERNEL32!GetProcAddress` at `0x18015a404`
- `KERNEL32!GetProcAddress` at `0x18015a233`
- `KERNEL32!GetProcAddress` at `0x18015a2ce`
- `KERNEL32!GetProcAddress` at `0x18015a369`
- `KERNEL32!GetProcAddress` at `0x18015a404`
- `KERNEL32!LoadLibraryExA` at `0x18015a177`
- `KERNEL32!LoadLibraryExA` at `0x18015a177`

## string_xrefs

- `0x18015a168`: `mssql-auth.dll`
- `0x18015a229`: `GetAccessToken`

## pseudocode

```c
__int64 SNISecInitializeMssqlAuth()
{
  DWORD LastError; // ebx
  HMODULE Library; // rax
  __int64 v2; // rdx
  wchar_t *v3; // r8
  __int64 v4; // rdx
  char *v5; // rcx
  HMODULE v6; // rcx
  DWORD v7; // eax
  void (*v8)(void *); // rax

  LastError = 0;
  Library = LoadLibraryExA("mssql-auth.dll", 0, 0x800u);
  g_mssqlAuth = Library;
  if ( Library )
  {
    *(&g_mssqlAuth + 1) = (HMODULE)GetProcAddress(Library, "GetAccessToken");
    if ( *(&g_mssqlAuth + 1) )
    {
      *(_QWORD *)&xmmword_1802538C0 = GetProcAddress(g_mssqlAuth, "Allocate");
      if ( (_QWORD)xmmword_1802538C0 )
      {
        *((_QWORD *)&xmmword_1802538C0 + 1) = GetProcAddress(g_mssqlAuth, "Free");
        if ( *((_QWORD *)&xmmword_1802538C0 + 1) )
        {
          qword_1802538D0 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(g_mssqlAuth, "Shutdown");
          if ( qword_1802538D0 )
          {
            v8 = (void (*)(void *))*((_QWORD *)&xmmword_1802538C0 + 1);
            mssql::auth::pfAllocate = (void *(*)(unsigned __int64))xmmword_1802538C0;
LABEL_48:
            mssql::auth::pfFree = v8;
            goto LABEL_49;
          }
          LastError = GetLastError();
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_37;
          if ( off_180263F40[0] )
            bidTraceW(off_180260BF8[0], 49152, off_180263F40[0], LastError);
          if ( (bidGblFlags & 2) == 0 || !off_180263F48[0] )
            goto LABEL_37;
          SniErrorIdFromStringId(0xC3B4u);
          v3 = off_180263F48[0];
          v4 = 49152;
          v5 = off_180260C00[0];
        }
        else
        {
          LastError = GetLastError();
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_37;
          if ( off_180263F30[0] )
            bidTraceW(off_180260BE8[0], 48128, off_180263F30[0], LastError);
          if ( (bidGblFlags & 2) == 0 || !off_180263F38[0] )
            goto LABEL_37;
          SniErrorIdFromStringId(0xC3B4u);
          v3 = off_180263F38[0];
          v4 = 48128;
          v5 = off_180260BF0[0];
        }
      }
      else
      {
        LastError = GetLastError();
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_37;
        if ( off_180263F20[0] )
          bidTraceW(off_180260BD8[0], 47104, off_180263F20[0], LastError);
        if ( (bidGblFlags & 2) == 0 || !off_180263F28[0] )
          goto LABEL_37;
        SniErrorIdFromStringId(0xC3B4u);
        v3 = off_180263F28[0];
        v4 = 47104;
        v5 = off_180260BE0[0];
      }
    }
    else
    {
      LastError = GetLastError();
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_37;
      if ( off_180263F10[0] )
        bidTraceW(off_180260BC8[0], 46080, off_180263F10[0], LastError);
      if ( (bidGblFlags & 2) == 0 || !off_180263F18[0] )
        goto LABEL_37;
      SniErrorIdFromStringId(0xC3B4u);
      v3 = off_180263F18[0];
      v4 = 46080;
      v5 = off_180260BD0[0];
    }
    bidTraceW(v5, v4, v3, 8);
LABEL_37:
    SNISetLastError(8, LastError, 50100);
    goto LABEL_38;
  }
  LastError = GetLastError();
  if ( (bidGblFlags & 2) != 0 && off_180263F00[0] )
  {
    SniErrorIdFromStringId(0xC3CAu);
    bidTraceW(off_180260BB8[0], 40960, off_180263F00[0], 8);
  }
  SNISetLastError(8, LastError, 50122);
  if ( (bidGblFlags & 2) != 0 && off_180263F08[0] )
    bidTraceW(off_180260BC0[0], 41984, off_180263F08[0], LastError);
LABEL_38:
  if ( LastError )
  {
    v6 = g_mssqlAuth;
    if ( g_mssqlAuth )
    {
      if ( qword_1802538D0 )
      {
        qword_1802538D0(g_mssqlAuth, v2);
        v6 = g_mssqlAuth;
      }
      if ( !FreeLibrary(v6) && (bidGblFlags & 2) != 0 && off_180263F58[0] )
      {
        v7 = GetLastError();
        bidTraceW(off_180260C10[0], 75776, off_180263F58[0], v7);
      }
      v8 = 0;
      *(_OWORD *)&g_mssqlAuth = 0;
      mssql::auth::pfAllocate = 0;
      xmmword_1802538C0 = 0;
      qword_1802538D0 = 0;
      goto LABEL_48;
    }
  }
LABEL_49:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180263F50[0] )
    bidTraceW(off_180260C08[0], 61440, off_180263F50[0], LastError);
  return LastError;
}

```

## disassembly

```asm
0x18015a160  push    rbx
0x18015a162  sub     rsp, 60h
0x18015a166  xor     edx, edx; hFile
0x18015a168  lea     rcx, aMssqlAuthDll; "mssql-auth.dll"
0x18015a16f  mov     r8d, 800h; dwFlags
0x18015a175  xor     ebx, ebx
0x18015a177  call    cs:__imp_LoadLibraryExA
0x18015a17d  mov     qword ptr cs:?g_mssqlAuth@@3UMssqlAuthFunctionTable@@A, rax; MssqlAuthFunctionTable g_mssqlAuth
0x18015a184  test    rax, rax
0x18015a187  jnz     loc_18015A229
0x18015a18d  call    cs:__imp_GetLastError
0x18015a193  test    byte ptr cs:_bidGblFlags, 2
0x18015a19a  mov     ebx, eax
0x18015a19c  jz      short loc_18015A1DA
0x18015a19e  mov     rcx, cs:off_180263F00; "<SNISecInitializeMssqlAuth|ERR|SNI> Pro"...
0x18015a1a5  test    rcx, rcx
0x18015a1a8  jz      short loc_18015A1DA
0x18015a1aa  mov     ecx, 0C3CAh; unsigned int
0x18015a1af  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015a1b4  mov     r8, cs:off_180263F00; "<SNISecInitializeMssqlAuth|ERR|SNI> Pro"...
0x18015a1bb  mov     r9d, 8
0x18015a1c1  mov     rcx, cs:off_180260BB8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015a1c8  mov     edx, 0A000h
0x18015a1cd  mov     [rsp+68h+var_40], ebx
0x18015a1d1  mov     [rsp+68h+var_48], eax
0x18015a1d5  call    _bidTraceW
0x18015a1da  mov     r8d, 0C3CAh
0x18015a1e0  mov     edx, ebx
0x18015a1e2  mov     ecx, 8
0x18015a1e7  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18015a1ec  test    byte ptr cs:_bidGblFlags, 2
0x18015a1f3  jz      loc_18015A4A9
0x18015a1f9  mov     rax, cs:off_180263F08; "<SNISecInitializeMssqlAuth|ERR|SNI> Loa"...
0x18015a200  test    rax, rax
0x18015a203  jz      loc_18015A4A9
0x18015a209  mov     r8, cs:off_180263F08; "<SNISecInitializeMssqlAuth|ERR|SNI> Loa"...
0x18015a210  mov     r9d, ebx
0x18015a213  mov     rcx, cs:off_180260BC0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015a21a  mov     edx, 0A400h
0x18015a21f  call    _bidTraceW
0x18015a224  jmp     loc_18015A4A9
0x18015a229  lea     rdx, aGetaccesstoken; "GetAccessToken"
0x18015a230  mov     rcx, rax; hModule
0x18015a233  call    cs:__imp_GetProcAddress
0x18015a239  mov     qword ptr cs:?g_mssqlAuth@@3UMssqlAuthFunctionTable@@A+8, rax; MssqlAuthFunctionTable g_mssqlAuth
0x18015a240  test    rax, rax
0x18015a243  jnz     short loc_18015A2C0
0x18015a245  call    cs:__imp_GetLastError
0x18015a24b  test    byte ptr cs:_bidGblFlags, 2
0x18015a252  mov     ebx, eax
0x18015a254  jz      loc_18015A497
0x18015a25a  mov     rax, cs:off_180263F10; "<SNISecInitializeMssqlAuth|ERR|SNI> Get"...
0x18015a261  test    rax, rax
0x18015a264  jz      short loc_18015A281
0x18015a266  mov     r8, cs:off_180263F10; "<SNISecInitializeMssqlAuth|ERR|SNI> Get"...
0x18015a26d  mov     r9d, ebx
0x18015a270  mov     rcx, cs:off_180260BC8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015a277  mov     edx, 0B400h
0x18015a27c  call    _bidTraceW
0x18015a281  test    byte ptr cs:_bidGblFlags, 2
0x18015a288  jz      loc_18015A497
0x18015a28e  mov     rax, cs:off_180263F18; "<SNISecInitializeMssqlAuth|ERR|SNI> Pro"...
0x18015a295  test    rax, rax
0x18015a298  jz      loc_18015A497
0x18015a29e  mov     ecx, 0C3B4h; unsigned int
0x18015a2a3  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015a2a8  mov     r8, cs:off_180263F18; "<SNISecInitializeMssqlAuth|ERR|SNI> Pro"...
0x18015a2af  mov     edx, 0B400h
0x18015a2b4  mov     rcx, cs:off_180260BD0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015a2bb  jmp     loc_18015A484
0x18015a2c0  mov     rcx, qword ptr cs:?g_mssqlAuth@@3UMssqlAuthFunctionTable@@A; hModule
0x18015a2c7  lea     rdx, aAllocate; "Allocate"
0x18015a2ce  call    cs:__imp_GetProcAddress
0x18015a2d4  mov     qword ptr cs:xmmword_1802538C0, rax
0x18015a2db  test    rax, rax
0x18015a2de  jnz     short loc_18015A35B
0x18015a2e0  call    cs:__imp_GetLastError
0x18015a2e6  test    byte ptr cs:_bidGblFlags, 2
0x18015a2ed  mov     ebx, eax
0x18015a2ef  jz      loc_18015A497
0x18015a2f5  mov     rax, cs:off_180263F20; "<SNISecInitializeMssqlAuth|ERR|SNI> Get"...
0x18015a2fc  test    rax, rax
0x18015a2ff  jz      short loc_18015A31C
0x18015a301  mov     r8, cs:off_180263F20; "<SNISecInitializeMssqlAuth|ERR|SNI> Get"...
0x18015a308  mov     r9d, ebx
0x18015a30b  mov     rcx, cs:off_180260BD8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015a312  mov     edx, 0B800h
0x18015a317  call    _bidTraceW
0x18015a31c  test    byte ptr cs:_bidGblFlags, 2
0x18015a323  jz      loc_18015A497
0x18015a329  mov     rax, cs:off_180263F28; "<SNISecInitializeMssqlAuth|ERR|SNI> Pro"...
0x18015a330  test    rax, rax
0x18015a333  jz      loc_18015A497
0x18015a339  mov     ecx, 0C3B4h; unsigned int
0x18015a33e  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015a343  mov     r8, cs:off_180263F28; "<SNISecInitializeMssqlAuth|ERR|SNI> Pro"...
0x18015a34a  mov     edx, 0B800h
0x18015a34f  mov     rcx, cs:off_180260BE0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015a356  jmp     loc_18015A484
0x18015a35b  mov     rcx, qword ptr cs:?g_mssqlAuth@@3UMssqlAuthFunctionTable@@A; hModule
0x18015a362  lea     rdx, aFree; "Free"
0x18015a369  call    cs:__imp_GetProcAddress
0x18015a36f  mov     qword ptr cs:xmmword_1802538C0+8, rax
0x18015a376  test    rax, rax
0x18015a379  jnz     short loc_18015A3F6
0x18015a37b  call    cs:__imp_GetLastError
0x18015a381  test    byte ptr cs:_bidGblFlags, 2
0x18015a388  mov     ebx, eax
0x18015a38a  jz      loc_18015A497
0x18015a390  mov     rax, cs:off_180263F30; "<SNISecInitializeMssqlAuth|ERR|SNI> Get"...
0x18015a397  test    rax, rax
0x18015a39a  jz      short loc_18015A3B7
0x18015a39c  mov     r8, cs:off_180263F30; "<SNISecInitializeMssqlAuth|ERR|SNI> Get"...
0x18015a3a3  mov     r9d, ebx
0x18015a3a6  mov     rcx, cs:off_180260BE8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015a3ad  mov     edx, 0BC00h
0x18015a3b2  call    _bidTraceW
0x18015a3b7  test    byte ptr cs:_bidGblFlags, 2
0x18015a3be  jz      loc_18015A497
0x18015a3c4  mov     rax, cs:off_180263F38; "<SNISecInitializeMssqlAuth|ERR|SNI> Pro"...
0x18015a3cb  test    rax, rax
0x18015a3ce  jz      loc_18015A497
0x18015a3d4  mov     ecx, 0C3B4h; unsigned int
0x18015a3d9  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015a3de  mov     r8, cs:off_180263F38; "<SNISecInitializeMssqlAuth|ERR|SNI> Pro"...
0x18015a3e5  mov     edx, 0BC00h
0x18015a3ea  mov     rcx, cs:off_180260BF0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015a3f1  jmp     loc_18015A484
0x18015a3f6  mov     rcx, qword ptr cs:?g_mssqlAuth@@3UMssqlAuthFunctionTable@@A; hModule
0x18015a3fd  lea     rdx, aShutdown_0; "Shutdown"
0x18015a404  call    cs:__imp_GetProcAddress
0x18015a40a  mov     cs:qword_1802538D0, rax
0x18015a411  test    rax, rax
0x18015a414  jnz     loc_18015A549
0x18015a41a  call    cs:__imp_GetLastError
0x18015a420  test    byte ptr cs:_bidGblFlags, 2
0x18015a427  mov     ebx, eax
0x18015a429  jz      short loc_18015A497
0x18015a42b  mov     rax, cs:off_180263F40; "<SNISecInitializeMssqlAuth|ERR|SNI> Get"...
0x18015a432  test    rax, rax
0x18015a435  jz      short loc_18015A452
0x18015a437  mov     r8, cs:off_180263F40; "<SNISecInitializeMssqlAuth|ERR|SNI> Get"...
0x18015a43e  mov     r9d, ebx
0x18015a441  mov     rcx, cs:off_180260BF8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015a448  mov     edx, 0C000h
0x18015a44d  call    _bidTraceW
0x18015a452  test    byte ptr cs:_bidGblFlags, 2
0x18015a459  jz      short loc_18015A497
0x18015a45b  mov     rax, cs:off_180263F48; "<SNISecInitializeMssqlAuth|ERR|SNI> Pro"...
0x18015a462  test    rax, rax
0x18015a465  jz      short loc_18015A497
0x18015a467  mov     ecx, 0C3B4h; unsigned int
0x18015a46c  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015a471  mov     r8, cs:off_180263F48; "<SNISecInitializeMssqlAuth|ERR|SNI> Pro"...
0x18015a478  mov     edx, 0C000h
0x18015a47d  mov     rcx, cs:off_180260C00; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015a484  mov     [rsp+68h+var_40], ebx
0x18015a488  mov     r9d, 8
0x18015a48e  mov     [rsp+68h+var_48], eax
0x18015a492  call    _bidTraceW
0x18015a497  mov     r8d, 0C3B4h
0x18015a49d  mov     edx, ebx
0x18015a49f  mov     ecx, 8
0x18015a4a4  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18015a4a9  test    ebx, ebx
0x18015a4ab  jz      loc_18015A565
0x18015a4b1  mov     rcx, qword ptr cs:?g_mssqlAuth@@3UMssqlAuthFunctionTable@@A; MssqlAuthFunctionTable g_mssqlAuth
0x18015a4b8  test    rcx, rcx
0x18015a4bb  jz      loc_18015A565
0x18015a4c1  mov     rax, cs:qword_1802538D0
0x18015a4c8  test    rax, rax
0x18015a4cb  jz      short loc_18015A4DA
0x18015a4cd  call    cs:__guard_dispatch_icall_fptr
0x18015a4d3  mov     rcx, qword ptr cs:?g_mssqlAuth@@3UMssqlAuthFunctionTable@@A; hLibModule
0x18015a4da  call    cs:__imp_FreeLibrary
0x18015a4e0  test    eax, eax
0x18015a4e2  jnz     short loc_18015A51A
0x18015a4e4  test    byte ptr cs:_bidGblFlags, 2
0x18015a4eb  jz      short loc_18015A51A
0x18015a4ed  mov     rax, cs:off_180263F58; "<SNISecTerminateMssqlAuth|ERR|SNI> Free"...
0x18015a4f4  test    rax, rax
0x18015a4f7  jz      short loc_18015A51A
0x18015a4f9  call    cs:__imp_GetLastError
0x18015a4ff  mov     r8, cs:off_180263F58; "<SNISecTerminateMssqlAuth|ERR|SNI> Free"...
0x18015a506  mov     edx, 12800h
0x18015a50b  mov     rcx, cs:off_180260C10; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015a512  mov     r9d, eax
0x18015a515  call    _bidTraceW
0x18015a51a  xorps   xmm0, xmm0
0x18015a51d  xor     eax, eax
0x18015a51f  mov     [rsp+68h+var_18], rax
0x18015a524  movups  cs:?g_mssqlAuth@@3UMssqlAuthFunctionTable@@A, xmm0; MssqlAuthFunctionTable g_mssqlAuth
0x18015a52b  mov     cs:?pfAllocate@auth@mssql@@3P6APEAX_K@ZEA, rax; void * (*mssql::auth::pfAllocate)(unsigned __int64)
0x18015a532  movups  cs:xmmword_1802538C0, xmm0
0x18015a539  movsd   xmm0, [rsp+68h+var_18]
0x18015a53f  movsd   cs:qword_1802538D0, xmm0
0x18015a547  jmp     short loc_18015A55E
0x18015a549  mov     rax, qword ptr cs:xmmword_1802538C0
0x18015a550  mov     cs:?pfAllocate@auth@mssql@@3P6APEAX_K@ZEA, rax; void * (*mssql::auth::pfAllocate)(unsigned __int64)
0x18015a557  mov     rax, qword ptr cs:xmmword_1802538C0+8
0x18015a55e  mov     cs:?pfFree@auth@mssql@@3P6AXPEAX@ZEA, rax; void (*mssql::auth::pfFree)(void *)
0x18015a565  mov     eax, cs:_bidGblFlags
0x18015a56b  and     eax, 20002h
0x18015a570  cmp     eax, 20002h
0x18015a575  jnz     short loc_18015A59E
0x18015a577  mov     rax, cs:off_180263F50; "<SNISecInitializeMssqlAuth|RET|SNI> %x"...
0x18015a57e  test    rax, rax
0x18015a581  jz      short loc_18015A59E
0x18015a583  mov     r8, cs:off_180263F50; "<SNISecInitializeMssqlAuth|RET|SNI> %x"...
0x18015a58a  mov     r9d, ebx
0x18015a58d  mov     rcx, cs:off_180260C08; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015a594  mov     edx, 0F000h
0x18015a599  call    _bidTraceW
0x18015a59e  mov     eax, ebx
0x18015a5a0  add     rsp, 60h
0x18015a5a4  pop     rbx
0x18015a5a5  retn
```
