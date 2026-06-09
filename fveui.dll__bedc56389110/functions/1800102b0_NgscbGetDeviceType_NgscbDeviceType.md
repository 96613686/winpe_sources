# NgscbGetDeviceType(NgscbDeviceType *)

- ea: `0x1800102b0`
- end: `0x1800103b0`
- name: `?NgscbGetDeviceType@@YAJPEAW4NgscbDeviceType@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(enum NgscbDeviceType *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180014aac`

## callees

- `0x1800037a0`
- `0x1800102b0`
- `0x1800103b8`
- `0x180010dbc`
- `0x18002d010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180010398`
- `KERNEL32!FreeLibrary` at `0x180010398`
- `KERNEL32!LoadLibraryExW` at `0x1800102e0`
- `KERNEL32!LoadLibraryExW` at `0x1800102e0`
- `KERNEL32!GetProcAddress` at `0x180010338`
- `KERNEL32!GetProcAddress` at `0x180010338`

## string_xrefs

- `0x1800102d3`: `powrprof.dll`

## pseudocode

```c
__int64 __fastcall NgscbGetDeviceType(enum NgscbDeviceType *a1)
{
  unsigned int KnownLastErrorHR; // ebx
  HMODULE Library; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  int v6; // eax
  int v7; // ecx

  KnownLastErrorHR = 0;
  if ( !(unsigned __int8)NgscbpGetDeviceType_TEST_Override() )
  {
    Library = LoadLibraryExW(L"powrprof.dll", 0, 0x800u);
    v4 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "PowerDeterminePlatformRoleEx");
      if ( ProcAddress )
      {
        v6 = ((__int64 (__fastcall *)(__int64))ProcAddress)(2);
        v7 = -1;
        if ( v6 == 8 )
          v7 = 1;
        *(_DWORD *)a1 = v7;
      }
      else
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
            KnownLastErrorHR);
      }
      FreeLibrary(v4);
    }
    else
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
          KnownLastErrorHR);
    }
  }
  return KnownLastErrorHR;
}

```

## disassembly

```asm
0x1800102b0  mov     [rsp+arg_0], rbx
0x1800102b5  mov     [rsp+arg_8], rsi
0x1800102ba  push    rdi
0x1800102bb  sub     rsp, 20h
0x1800102bf  mov     rsi, rcx
0x1800102c2  xor     ebx, ebx
0x1800102c4  call    NgscbpGetDeviceType_TEST_Override
0x1800102c9  test    al, al
0x1800102cb  jnz     loc_18001039E
0x1800102d1  xor     edx, edx; hFile
0x1800102d3  lea     rcx, aPowrprofDll; "powrprof.dll"
0x1800102da  mov     r8d, 800h; dwFlags
0x1800102e0  call    cs:__imp_LoadLibraryExW
0x1800102e6  mov     rdi, rax
0x1800102e9  test    rax, rax
0x1800102ec  jnz     short loc_18001032E
0x1800102ee  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1800102f3  mov     ebx, eax
0x1800102f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102fc  lea     rax, WPP_GLOBAL_Control
0x180010303  cmp     rcx, rax
0x180010306  jz      loc_18001039E
0x18001030c  test    byte ptr [rcx+1Ch], 40h
0x180010310  jz      loc_18001039E
0x180010316  mov     rcx, [rcx+10h]
0x18001031a  lea     edx, [rdi+15h]
0x18001031d  mov     r9d, ebx
0x180010320  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180010327  call    WPP_SF_d
0x18001032c  jmp     short loc_18001039E
0x18001032e  lea     rdx, aPowerdetermine; "PowerDeterminePlatformRoleEx"
0x180010335  mov     rcx, rdi; hModule
0x180010338  call    cs:__imp_GetProcAddress
0x18001033e  test    rax, rax
0x180010341  jnz     short loc_18001037D
0x180010343  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x180010348  mov     ebx, eax
0x18001034a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010351  lea     rax, WPP_GLOBAL_Control
0x180010358  cmp     rcx, rax
0x18001035b  jz      short loc_180010395
0x18001035d  test    byte ptr [rcx+1Ch], 40h
0x180010361  jz      short loc_180010395
0x180010363  mov     rcx, [rcx+10h]
0x180010367  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18001036e  mov     edx, 16h
0x180010373  mov     r9d, ebx
0x180010376  call    WPP_SF_d
0x18001037b  jmp     short loc_180010395
0x18001037d  mov     ecx, 2
0x180010382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010387  or      ecx, 0FFFFFFFFh
0x18001038a  cmp     eax, 8
0x18001038d  lea     edx, [rcx+2]
0x180010390  cmovz   ecx, edx
0x180010393  mov     [rsi], ecx
0x180010395  mov     rcx, rdi; hLibModule
0x180010398  call    cs:__imp_FreeLibrary
0x18001039e  mov     rsi, [rsp+28h+arg_8]
0x1800103a3  mov     eax, ebx
0x1800103a5  mov     rbx, [rsp+28h+arg_0]
0x1800103aa  add     rsp, 20h
0x1800103ae  pop     rdi
0x1800103af  retn
```
