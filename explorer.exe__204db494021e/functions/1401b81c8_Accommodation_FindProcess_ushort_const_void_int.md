# Accommodation::FindProcess(ushort const *,void * *,int)

- ea: `0x1401b81c8`
- end: `0x1401b83a0`
- name: `?FindProcess@Accommodation@@SAKPEBGPEAPEAXH@Z`
- size: `472`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, void **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401b83a8`

## callees

- `0x14010e160`
- `0x1401b81c8`
- `0x1401d1de0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401b8341`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401b8341`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1401b826c`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1401b829b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1401b826c`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1401b829b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1401b824e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1401b824e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b8354`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b8354`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1401b82d2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1401b82d2`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x1401b8302`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x1401b8302`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x1401b8327`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x1401b8327`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x1401b8222`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x1401b8222`

## pseudocode

```c
__int64 __fastcall Accommodation::FindProcess(const unsigned __int16 *a1, void **a2)
{
  DWORD CurrentProcessId; // eax
  DWORD v5; // r15d
  DWORD v6; // esi
  __int64 i; // rbx
  DWORD v8; // ecx
  DWORD v9; // r8d
  HANDLE v10; // rax
  void *v11; // rdi
  DWORD cbNeeded; // [rsp+20h] [rbp-E0h] BYREF
  DWORD pSessionId; // [rsp+24h] [rbp-DCh] BYREF
  DWORD v15; // [rsp+28h] [rbp-D8h] BYREF
  DWORD v16; // [rsp+2Ch] [rbp-D4h] BYREF
  HMODULE hModule; // [rsp+30h] [rbp-D0h] BYREF
  DWORD idProcess[2048]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR BaseName[264]; // [rsp+2040h] [rbp+1F40h] BYREF

  *a2 = 0;
  cbNeeded = 0;
  if ( !K32EnumProcesses(idProcess, 0x2000u, &cbNeeded) )
    return 0;
  cbNeeded >>= 2;
  if ( cbNeeded > 0x800 )
    cbNeeded = 2048;
  CurrentProcessId = GetCurrentProcessId();
  pSessionId = 0;
  v5 = CurrentProcessId;
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    return 0;
  v6 = 0;
  for ( i = 0; (unsigned int)i < cbNeeded; i = (unsigned int)(i + 1) )
  {
    v8 = idProcess[i];
    v15 = 0;
    if ( ProcessIdToSessionId(v8, &v15) )
    {
      if ( v15 == pSessionId )
      {
        v9 = idProcess[i];
        if ( v5 != v9 )
        {
          v10 = OpenProcess(0x410u, 0, v9);
          v11 = v10;
          if ( v10 )
          {
            hModule = 0;
            v16 = 0;
            if ( K32EnumProcessModules(v10, &hModule, 8u, &v16)
              && K32GetModuleBaseNameW(v11, hModule, BaseName, 0x104u)
              && !(unsigned int)_o__wcsicmp(BaseName, a1) )
            {
              v6 = idProcess[i];
              *a2 = v11;
              return v6;
            }
            CloseHandle(v11);
          }
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1401b81c8  mov     [rsp-8+arg_10], rbx
0x1401b81cd  push    rbp
0x1401b81ce  push    rsi
0x1401b81cf  push    rdi
0x1401b81d0  push    r12
0x1401b81d2  push    r13
0x1401b81d4  push    r14
0x1401b81d6  push    r15
0x1401b81d8  lea     rbp, [rsp-2160h]
0x1401b81e0  mov     eax, 2260h
0x1401b81e5  call    _alloca_probe
0x1401b81ea  sub     rsp, rax
0x1401b81ed  mov     rax, cs:__security_cookie
0x1401b81f4  xor     rax, rsp
0x1401b81f7  mov     [rbp+2190h+var_40], rax
0x1401b81fe  mov     r12, rdx
0x1401b8201  mov     qword ptr [rdx], 0
0x1401b8208  mov     r13, rcx
0x1401b820b  mov     [rsp+2290h+cbNeeded], 0
0x1401b8213  mov     edx, 2000h; cb
0x1401b8218  lea     rcx, [rsp+2290h+idProcess]; lpidProcess
0x1401b821d  lea     r8, [rsp+2290h+cbNeeded]; lpcbNeeded
0x1401b8222  call    cs:__imp_K32EnumProcesses
0x1401b8229  nop     dword ptr [rax+rax+00h]
0x1401b822e  test    eax, eax
0x1401b8230  jz      loc_1401B8373
0x1401b8236  mov     eax, [rsp+2290h+cbNeeded]
0x1401b823a  mov     ecx, 800h
0x1401b823f  shr     eax, 2
0x1401b8242  mov     [rsp+2290h+cbNeeded], eax
0x1401b8246  cmp     eax, ecx
0x1401b8248  jbe     short loc_1401B824E
0x1401b824a  mov     [rsp+2290h+cbNeeded], ecx
0x1401b824e  call    cs:__imp_GetCurrentProcessId
0x1401b8255  nop     dword ptr [rax+rax+00h]
0x1401b825a  lea     rdx, [rsp+2290h+pSessionId]; pSessionId
0x1401b825f  mov     [rsp+2290h+pSessionId], 0
0x1401b8267  mov     ecx, eax; dwProcessId
0x1401b8269  mov     r15d, eax
0x1401b826c  call    cs:__imp_ProcessIdToSessionId
0x1401b8273  nop     dword ptr [rax+rax+00h]
0x1401b8278  test    eax, eax
0x1401b827a  jz      loc_1401B8373
0x1401b8280  xor     esi, esi
0x1401b8282  xor     ebx, ebx
0x1401b8284  cmp     ebx, [rsp+2290h+cbNeeded]
0x1401b8288  jnb     loc_1401B836F
0x1401b828e  mov     ecx, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x1401b8292  lea     rdx, [rsp+2290h+var_2268]; pSessionId
0x1401b8297  mov     [rsp+2290h+var_2268], esi
0x1401b829b  call    cs:__imp_ProcessIdToSessionId
0x1401b82a2  nop     dword ptr [rax+rax+00h]
0x1401b82a7  test    eax, eax
0x1401b82a9  jz      loc_1401B8360
0x1401b82af  mov     eax, [rsp+2290h+pSessionId]
0x1401b82b3  cmp     [rsp+2290h+var_2268], eax
0x1401b82b7  jnz     loc_1401B8360
0x1401b82bd  mov     r8d, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x1401b82c2  cmp     r15d, r8d
0x1401b82c5  jz      loc_1401B8360
0x1401b82cb  xor     edx, edx; bInheritHandle
0x1401b82cd  mov     ecx, 410h; dwDesiredAccess
0x1401b82d2  call    cs:__imp_OpenProcess
0x1401b82d9  nop     dword ptr [rax+rax+00h]
0x1401b82de  mov     rdi, rax
0x1401b82e1  test    rax, rax
0x1401b82e4  jz      short loc_1401B8360
0x1401b82e6  lea     r9, [rsp+2290h+var_2264]; lpcbNeeded
0x1401b82eb  mov     [rsp+2290h+hModule], rsi
0x1401b82f0  mov     r8d, 8; cb
0x1401b82f6  mov     [rsp+2290h+var_2264], esi
0x1401b82fa  lea     rdx, [rsp+2290h+hModule]; lphModule
0x1401b82ff  mov     rcx, rax; hProcess
0x1401b8302  call    cs:__imp_K32EnumProcessModules
0x1401b8309  nop     dword ptr [rax+rax+00h]
0x1401b830e  test    eax, eax
0x1401b8310  jz      short loc_1401B8351
0x1401b8312  mov     rdx, [rsp+2290h+hModule]; hModule
0x1401b8317  lea     r8, [rbp+2190h+BaseName]; lpBaseName
0x1401b831e  mov     r9d, 104h; nSize
0x1401b8324  mov     rcx, rdi; hProcess
0x1401b8327  call    cs:__imp_K32GetModuleBaseNameW
0x1401b832e  nop     dword ptr [rax+rax+00h]
0x1401b8333  test    eax, eax
0x1401b8335  jz      short loc_1401B8351
0x1401b8337  mov     rdx, r13
0x1401b833a  lea     rcx, [rbp+2190h+BaseName]
0x1401b8341  call    cs:__imp__o__wcsicmp
0x1401b8348  nop     dword ptr [rax+rax+00h]
0x1401b834d  test    eax, eax
0x1401b834f  jz      short loc_1401B8367
0x1401b8351  mov     rcx, rdi; hObject
0x1401b8354  call    cs:__imp_CloseHandle
0x1401b835b  nop     dword ptr [rax+rax+00h]
0x1401b8360  inc     ebx
0x1401b8362  jmp     loc_1401B8284
0x1401b8367  mov     esi, [rsp+rbx*4+2290h+idProcess]
0x1401b836b  mov     [r12], rdi
0x1401b836f  mov     eax, esi
0x1401b8371  jmp     short loc_1401B8375
0x1401b8373  xor     eax, eax
0x1401b8375  mov     rcx, [rbp+2190h+var_40]
0x1401b837c  xor     rcx, rsp; StackCookie
0x1401b837f  call    __security_check_cookie
0x1401b8384  mov     rbx, [rsp+2290h+arg_10]
0x1401b838c  add     rsp, 2260h
0x1401b8393  pop     r15
0x1401b8395  pop     r14
0x1401b8397  pop     r13
0x1401b8399  pop     r12
0x1401b839b  pop     rdi
0x1401b839c  pop     rsi
0x1401b839d  pop     rbp
0x1401b839e  retn
```
