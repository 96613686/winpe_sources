# SelfRegOrUnreg(ushort const *,char const *)

- ea: `0x140007568`
- end: `0x140007753`
- name: `?SelfRegOrUnreg@@YAHPEBGPEBD@Z`
- size: `491`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140007550`
- `0x140007760`

## callees

- `0x140003c8c`
- `0x140007568`
- `0x14000817c`
- `0x1400087bc`
- `0x140009820`
- `0x14000a010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x1400076ab`
- `ADVAPI32!SetThreadToken` at `0x1400076ab`
- `KERNEL32!lstrlenW` at `0x1400075af`
- `KERNEL32!lstrlenW` at `0x1400075af`
- `KERNEL32!GetLastError` at `0x140007692`
- `KERNEL32!GetLastError` at `0x1400076b5`
- `KERNEL32!GetLastError` at `0x1400076df`
- `KERNEL32!GetLastError` at `0x140007692`
- `KERNEL32!GetLastError` at `0x1400076b5`
- `KERNEL32!GetLastError` at `0x1400076df`
- `KERNEL32!GlobalFree` at `0x1400075f0`
- `KERNEL32!GlobalFree` at `0x14000765f`
- `KERNEL32!GlobalFree` at `0x140007722`
- `KERNEL32!GlobalFree` at `0x1400075f0`
- `KERNEL32!GlobalFree` at `0x14000765f`
- `KERNEL32!GlobalFree` at `0x140007722`
- `KERNEL32!SetCurrentDirectoryW` at `0x140007688`
- `KERNEL32!SetCurrentDirectoryW` at `0x140007688`
- `KERNEL32!GetProcAddress` at `0x1400076d4`
- `KERNEL32!GetProcAddress` at `0x1400076d4`
- `KERNEL32!FreeLibrary` at `0x140007705`
- `KERNEL32!FreeLibrary` at `0x140007705`
- `KERNEL32!LoadLibraryExW` at `0x140007675`
- `KERNEL32!LoadLibraryExW` at `0x140007675`
- `ole32!CoUninitialize` at `0x14000770b`
- `ole32!CoUninitialize` at `0x14000770b`
- `ole32!CoInitialize` at `0x140007647`
- `ole32!CoInitialize` at `0x140007647`

## pseudocode

```c
__int64 __fastcall SelfRegOrUnreg(const unsigned __int16 *a1, LPCSTR lpProcName)
{
  __int64 v4; // rdx
  WCHAR v6; // ax
  const unsigned __int16 *v7; // rcx
  const unsigned __int16 *v8; // r8
  unsigned int v9; // ebx
  HMODULE Library; // rdi
  signed int LastError; // eax
  signed int v12; // eax
  __int64 (*ProcAddress)(void); // rax
  signed int v14; // eax
  HGLOBAL hMem; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+28h] [rbp-D8h]
  char v17; // [rsp+30h] [rbp-D0h] BYREF

  v16 = 260;
  hMem = &v17;
  v4 = (unsigned int)(lstrlenW(a1) + 1);
  if ( ((int)v4 <= 260 || (unsigned __int8)CAPITempBuffer<unsigned short,260>::SetSize(&hMem, v4))
    && StringCchCopyW((unsigned __int16 *)hMem, v16, a1) >= 0 )
  {
    if ( !a1 )
      goto LABEL_33;
    v6 = *a1;
    v7 = a1;
    v8 = 0;
    while ( v6 )
    {
      v7 = APICharNext(v7);
      v6 = *v7;
      if ( *v7 == 92 )
        v8 = v7;
    }
    if ( v8 )
    {
      *((_WORD *)hMem + v8 - a1) = 0;
      v9 = CoInitialize(0);
      if ( !v9 )
      {
        Library = LoadLibraryExW(a1, 0, 8u);
        if ( !Library || !SetCurrentDirectoryW((LPCWSTR)hMem) )
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
        }
        if ( !SetThreadToken(0, 0) )
        {
          v12 = GetLastError();
          v9 = v12;
          if ( v12 > 0 )
            v9 = (unsigned __int16)v12 | 0x80070000;
        }
        if ( !v9 )
        {
          ProcAddress = GetProcAddress(Library, lpProcName);
          if ( ProcAddress )
          {
            v9 = ProcAddress();
          }
          else
          {
            v14 = GetLastError();
            v9 = v14;
            if ( v14 > 0 )
              v9 = (unsigned __int16)v14 | 0x80070000;
          }
        }
        if ( Library )
          FreeLibrary(Library);
        CoUninitialize();
      }
      if ( v16 > 260 )
        GlobalFree(hMem);
      return v9;
    }
    else
    {
LABEL_33:
      if ( v16 > 260 )
        GlobalFree(hMem);
      return 1;
    }
  }
  else
  {
    if ( v16 > 260 )
      GlobalFree(hMem);
    return 14;
  }
}

```

## disassembly

```asm
0x140007568  mov     [rsp-8+arg_10], rbx
0x14000756d  push    rbp
0x14000756e  push    rsi
0x14000756f  push    rdi
0x140007570  push    r14
0x140007572  push    r15
0x140007574  lea     rbp, [rsp-150h]
0x14000757c  sub     rsp, 250h
0x140007583  mov     rax, cs:__security_cookie
0x14000758a  xor     rax, rsp
0x14000758d  mov     [rbp+170h+var_30], rax
0x140007594  lea     rax, [rsp+270h+var_240]
0x140007599  mov     r15d, 104h
0x14000759f  mov     [rsp+270h+var_248], r15d
0x1400075a4  mov     rsi, rdx
0x1400075a7  mov     [rsp+270h+hMem], rax
0x1400075ac  mov     rdi, rcx
0x1400075af  call    cs:__imp_lstrlenW
0x1400075b5  xor     r14d, r14d
0x1400075b8  lea     edx, [rax+1]
0x1400075bb  cmp     edx, r15d
0x1400075be  jle     short loc_1400075CE
0x1400075c0  lea     rcx, [rsp+270h+hMem]
0x1400075c5  call    ?SetSize@?$CAPITempBuffer@G$0BAE@@@QEAA_NH_N@Z; CAPITempBuffer<ushort,260>::SetSize(int,bool)
0x1400075ca  test    al, al
0x1400075cc  jz      short loc_1400075E4
0x1400075ce  movsxd  rdx, [rsp+270h+var_248]; unsigned __int64
0x1400075d3  mov     r8, rdi; unsigned __int16 *
0x1400075d6  mov     rcx, [rsp+270h+hMem]; unsigned __int16 *
0x1400075db  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400075e0  test    eax, eax
0x1400075e2  jns     short loc_140007600
0x1400075e4  cmp     [rsp+270h+var_248], r15d
0x1400075e9  jle     short loc_1400075F6
0x1400075eb  mov     rcx, [rsp+270h+hMem]; hMem
0x1400075f0  call    cs:__imp_GlobalFree
0x1400075f6  mov     eax, 0Eh
0x1400075fb  jmp     loc_14000772D
0x140007600  test    rdi, rdi
0x140007603  jz      loc_140007716
0x140007609  movzx   eax, word ptr [rdi]
0x14000760c  mov     rcx, rdi; unsigned __int16 *
0x14000760f  mov     r8, r14
0x140007612  test    ax, ax
0x140007615  jz      short loc_14000762C
0x140007617  call    ?APICharNext@@YAPEBGPEBG@Z; APICharNext(ushort const *)
0x14000761c  mov     rcx, rax
0x14000761f  movzx   eax, word ptr [rax]
0x140007622  cmp     ax, 5Ch ; '\'
0x140007626  cmovz   r8, rcx
0x14000762a  jmp     short loc_140007612
0x14000762c  test    r8, r8
0x14000762f  jz      loc_140007716
0x140007635  mov     rax, [rsp+270h+hMem]
0x14000763a  sub     r8, rdi
0x14000763d  sar     r8, 1
0x140007640  xor     ecx, ecx; pvReserved
0x140007642  mov     [rax+r8*2], r14w
0x140007647  call    cs:__imp_CoInitialize
0x14000764d  mov     ebx, eax
0x14000764f  test    eax, eax
0x140007651  jz      short loc_14000766C
0x140007653  cmp     [rsp+270h+var_248], r15d
0x140007658  jle     short loc_140007665
0x14000765a  mov     rcx, [rsp+270h+hMem]; hMem
0x14000765f  call    cs:__imp_GlobalFree
0x140007665  mov     eax, ebx
0x140007667  jmp     loc_14000772D
0x14000766c  xor     edx, edx; hFile
0x14000766e  mov     rcx, rdi; lpLibFileName
0x140007671  lea     r8d, [rdx+8]; dwFlags
0x140007675  call    cs:__imp_LoadLibraryExW
0x14000767b  mov     rdi, rax
0x14000767e  test    rax, rax
0x140007681  jz      short loc_140007692
0x140007683  mov     rcx, [rsp+270h+hMem]; lpPathName
0x140007688  call    cs:__imp_SetCurrentDirectoryW
0x14000768e  test    eax, eax
0x140007690  jnz     short loc_1400076A7
0x140007692  call    cs:__imp_GetLastError
0x140007698  mov     ebx, eax
0x14000769a  test    eax, eax
0x14000769c  jle     short loc_1400076A7
0x14000769e  movzx   ebx, ax
0x1400076a1  or      ebx, 80070000h
0x1400076a7  xor     edx, edx; Token
0x1400076a9  xor     ecx, ecx; Thread
0x1400076ab  call    cs:__imp_SetThreadToken
0x1400076b1  test    eax, eax
0x1400076b3  jnz     short loc_1400076CA
0x1400076b5  call    cs:__imp_GetLastError
0x1400076bb  mov     ebx, eax
0x1400076bd  test    eax, eax
0x1400076bf  jle     short loc_1400076CA
0x1400076c1  movzx   ebx, ax
0x1400076c4  or      ebx, 80070000h
0x1400076ca  test    ebx, ebx
0x1400076cc  jnz     short loc_1400076FD
0x1400076ce  mov     rdx, rsi; lpProcName
0x1400076d1  mov     rcx, rdi; hModule
0x1400076d4  call    cs:__imp_GetProcAddress
0x1400076da  test    rax, rax
0x1400076dd  jnz     short loc_1400076F6
0x1400076df  call    cs:__imp_GetLastError
0x1400076e5  mov     ebx, eax
0x1400076e7  test    eax, eax
0x1400076e9  jle     short loc_1400076FD
0x1400076eb  movzx   ebx, ax
0x1400076ee  or      ebx, 80070000h
0x1400076f4  jmp     short loc_1400076FD
0x1400076f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400076fb  mov     ebx, eax
0x1400076fd  test    rdi, rdi
0x140007700  jz      short loc_14000770B
0x140007702  mov     rcx, rdi; hLibModule
0x140007705  call    cs:__imp_FreeLibrary
0x14000770b  call    cs:__imp_CoUninitialize
0x140007711  jmp     loc_140007653
0x140007716  cmp     [rsp+270h+var_248], r15d
0x14000771b  jle     short loc_140007728
0x14000771d  mov     rcx, [rsp+270h+hMem]; hMem
0x140007722  call    cs:__imp_GlobalFree
0x140007728  mov     eax, 1
0x14000772d  mov     rcx, [rbp+170h+var_30]
0x140007734  xor     rcx, rsp; StackCookie
0x140007737  call    __security_check_cookie
0x14000773c  mov     rbx, [rsp+270h+arg_10]
0x140007744  add     rsp, 250h
0x14000774b  pop     r15
0x14000774d  pop     r14
0x14000774f  pop     rdi
0x140007750  pop     rsi
0x140007751  pop     rbp
0x140007752  retn
```
