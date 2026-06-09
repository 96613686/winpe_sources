# CDumpCollection::Init(ulong,ulong)

- ea: `0x18003f818`
- end: `0x18003f98b`
- name: `?Init@CDumpCollection@@QEAAJKK@Z`
- size: `371`
- prototype: `__int64 __fastcall(CDumpCollection *__hidden this, DWORD dwProcessId, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180008970`
- `0x180009190`

## callees

- `0x180009ed8`
- `0x180009f00`
- `0x18003e964`
- `0x18003f818`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f89e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f8e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f89e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f8e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f84d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f84d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f943`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f887`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f887`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18003f8df`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18003f8df`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003f869`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003f869`

## pseudocode

```c
__int64 __fastcall CDumpCollection::Init(CDumpCollection *this, DWORD dwProcessId, int a3)
{
  HANDLE v6; // rax
  void *v7; // rcx
  void *v8; // rcx
  signed int v9; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  signed int LastError; // eax

  if ( (unsigned __int64)(*((_QWORD *)this + 137) + 1LL) <= 1 && !*((_WORD *)this + 20) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this);
    *((_DWORD *)this + 278) = dwProcessId;
    *((_DWORD *)this + 279) = a3;
    v6 = OpenProcess(0x100450u, 0, dwProcessId);
    v7 = (void *)*((_QWORD *)this + 137);
    *((_QWORD *)this + 137) = v6;
    if ( (unsigned __int64)v7 + 1 > 1 )
      CloseHandle(v7);
    v8 = (void *)*((_QWORD *)this + 137);
    if ( (unsigned __int64)v8 + 1 > 1 )
    {
      if ( K32GetModuleFileNameExW(v8, 0, (LPWSTR)this + 20, 0x104u) )
      {
        v10 = 0;
LABEL_21:
        LeaveCriticalSection((LPCRITICAL_SECTION)this);
        return v10;
      }
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_18:
        if ( (v10 & 0x80000000) != 0 )
          CDumpCollection::Cleanup(this);
        goto LABEL_21;
      }
      v12 = 37;
    }
    else
    {
      v9 = GetLastError();
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_18;
      v12 = 36;
    }
    WPP_SF_d(v11[2], v12, &WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v10);
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18003f818  push    rbx
0x18003f81a  push    rbp
0x18003f81b  push    rsi
0x18003f81c  push    rdi
0x18003f81d  push    r14
0x18003f81f  sub     rsp, 20h
0x18003f823  mov     rax, [rcx+448h]
0x18003f82a  mov     ebp, r8d
0x18003f82d  inc     rax
0x18003f830  mov     esi, edx
0x18003f832  mov     rdi, rcx
0x18003f835  cmp     rax, 1
0x18003f839  ja      loc_18003F94D
0x18003f83f  xor     r14d, r14d
0x18003f842  cmp     [rcx+28h], r14w
0x18003f847  jnz     loc_18003F94D
0x18003f84d  call    cs:__imp_EnterCriticalSection
0x18003f853  mov     r8d, esi; dwProcessId
0x18003f856  mov     [rdi+458h], esi
0x18003f85c  xor     edx, edx; bInheritHandle
0x18003f85e  mov     [rdi+45Ch], ebp
0x18003f864  mov     ecx, 100450h; dwDesiredAccess
0x18003f869  call    cs:__imp_OpenProcess
0x18003f86f  mov     rcx, [rdi+448h]; hObject
0x18003f876  mov     [rdi+448h], rax
0x18003f87d  lea     rax, [rcx+1]
0x18003f881  cmp     rax, 1
0x18003f885  jbe     short loc_18003F88D
0x18003f887  call    cs:__imp_CloseHandle
0x18003f88d  mov     rcx, [rdi+448h]; hProcess
0x18003f894  lea     rax, [rcx+1]
0x18003f898  cmp     rax, 1
0x18003f89c  ja      short loc_18003F8D3
0x18003f89e  call    cs:__imp_GetLastError
0x18003f8a4  mov     ebx, eax
0x18003f8a6  test    eax, eax
0x18003f8a8  jle     short loc_18003F8B3
0x18003f8aa  movzx   ebx, ax
0x18003f8ad  or      ebx, 80070000h
0x18003f8b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f8ba  lea     rax, WPP_GLOBAL_Control
0x18003f8c1  cmp     rcx, rax
0x18003f8c4  jz      short loc_18003F92F
0x18003f8c6  test    byte ptr [rcx+1Ch], 1
0x18003f8ca  jz      short loc_18003F92F
0x18003f8cc  mov     edx, 24h ; '$'
0x18003f8d1  jmp     short loc_18003F91C
0x18003f8d3  mov     r9d, 104h; nSize
0x18003f8d9  lea     r8, [rdi+28h]; lpFilename
0x18003f8dd  xor     edx, edx; hModule
0x18003f8df  call    cs:__imp_K32GetModuleFileNameExW
0x18003f8e5  test    eax, eax
0x18003f8e7  jnz     short loc_18003F93D
0x18003f8e9  call    cs:__imp_GetLastError
0x18003f8ef  mov     ebx, eax
0x18003f8f1  test    eax, eax
0x18003f8f3  jle     short loc_18003F8FE
0x18003f8f5  movzx   ebx, ax
0x18003f8f8  or      ebx, 80070000h
0x18003f8fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f905  lea     rax, WPP_GLOBAL_Control
0x18003f90c  cmp     rcx, rax
0x18003f90f  jz      short loc_18003F92F
0x18003f911  test    byte ptr [rcx+1Ch], 1
0x18003f915  jz      short loc_18003F92F
0x18003f917  mov     edx, 25h ; '%'
0x18003f91c  mov     rcx, [rcx+10h]
0x18003f920  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003f927  mov     r9d, ebx
0x18003f92a  call    WPP_SF_d
0x18003f92f  test    ebx, ebx
0x18003f931  jns     short loc_18003F940
0x18003f933  mov     rcx, rdi; this
0x18003f936  call    ?Cleanup@CDumpCollection@@QEAAXXZ; CDumpCollection::Cleanup(void)
0x18003f93b  jmp     short loc_18003F940
0x18003f93d  mov     ebx, r14d
0x18003f940  mov     rcx, rdi; lpCriticalSection
0x18003f943  call    cs:__imp_LeaveCriticalSection
0x18003f949  mov     eax, ebx
0x18003f94b  jmp     short loc_18003F980
0x18003f94d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f954  lea     rax, WPP_GLOBAL_Control
0x18003f95b  cmp     rcx, rax
0x18003f95e  jz      short loc_18003F97B
0x18003f960  test    byte ptr [rcx+1Ch], 1
0x18003f964  jz      short loc_18003F97B
0x18003f966  mov     rcx, [rcx+10h]
0x18003f96a  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003f971  mov     edx, 23h ; '#'
0x18003f976  call    WPP_SF_
0x18003f97b  mov     eax, 80070057h
0x18003f980  add     rsp, 20h
0x18003f984  pop     r14
0x18003f986  pop     rdi
0x18003f987  pop     rsi
0x18003f988  pop     rbp
0x18003f989  pop     rbx
0x18003f98a  retn
```
