# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x1800092cc`
- end: `0x1800094cb`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000911c`

## callees

- `0x1800092cc`
- `0x180022292`
- `0x1800222d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000941d`
- `KERNEL32!GetLastError` at `0x18000941d`
- `KERNEL32!SetLastError` at `0x1800093c6`
- `KERNEL32!SetLastError` at `0x1800093c6`
- `KERNEL32!DeactivateActCtx` at `0x1800094a5`
- `KERNEL32!DeactivateActCtx` at `0x180022a8e`
- `KERNEL32!DeactivateActCtx` at `0x1800094a5`
- `KERNEL32!DeactivateActCtx` at `0x180022a8e`
- `KERNEL32!LoadLibraryW` at `0x180009497`
- `KERNEL32!LoadLibraryW` at `0x180009497`
- `KERNEL32!ActivateActCtx` at `0x18000944b`
- `KERNEL32!ActivateActCtx` at `0x18000944b`
- `KERNEL32!FindActCtxSectionStringW` at `0x180009486`
- `KERNEL32!FindActCtxSectionStringW` at `0x180009486`
- `KERNEL32!CreateActCtxW` at `0x18000940c`
- `KERNEL32!CreateActCtxW` at `0x18000940c`
- `KERNEL32!GetModuleFileNameW` at `0x1800093ae`
- `KERNEL32!GetModuleFileNameW` at `0x1800093ae`
- `KERNEL32!GetModuleHandleExW` at `0x18000938d`
- `KERNEL32!GetModuleHandleExW` at `0x18000938d`
- `KERNEL32!QueryActCtxW` at `0x180009340`
- `KERNEL32!QueryActCtxW` at `0x180009340`

## string_xrefs

- `0x180009477`: `Comctl32.dll`
- `0x180009490`: `Comctl32.dll`

## pseudocode

```c
__int64 WinbaseIsolationAwarePrivatetRgzlnPgpgk()
{
  unsigned int v0; // ebx
  HANDLE ActCtxW; // rax
  DWORD ModuleFileNameW; // eax
  DWORD LastError; // eax
  HMODULE phModule; // [rsp+40h] [rbp-2B8h] BYREF
  ULONG_PTR Cookie; // [rsp+48h] [rbp-2B0h] BYREF
  HANDLE hActCtx[2]; // [rsp+50h] [rbp-2A8h] BYREF
  struct tagACTCTX_SECTION_KEYED_DATA pActCtx; // [rsp+60h] [rbp-298h] BYREF
  WCHAR Filename[264]; // [rsp+D0h] [rbp-228h] BYREF

  *(_OWORD *)hActCtx = 0;
  Cookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || WinbaseIsolationAwarePrivateT_UnPgpgk != (HANDLE)-1LL )
    return 1;
  v0 = 0;
  if ( QueryActCtxW(0x80000010, &WinbaseIsolationAwarePrivateT_UnPgpgk, 0, 1u, hActCtx, 0x10u, 0) )
  {
    ActCtxW = hActCtx[0];
    if ( hActCtx[0] )
      goto LABEL_13;
    memset(&pActCtx, 0, 56);
    phModule = 0;
    if ( GetModuleHandleExW(6u, (LPCWSTR)&WinbaseIsolationAwarePrivateT_UnPgpgk, &phModule) )
    {
      ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x105u);
      if ( ModuleFileNameW )
      {
        if ( ModuleFileNameW >= 0x105 )
        {
          SetLastError(0x6Fu);
          return v0;
        }
        pActCtx.cbSize = 56;
        pActCtx.ulDataFormatVersion = 136;
        pActCtx.lpData = Filename;
        *(_QWORD *)&pActCtx.ulSectionGlobalDataLength = 3;
        *(_QWORD *)&pActCtx.ulSectionTotalLength = phModule;
        ActCtxW = CreateActCtxW((PCACTCTXW)&pActCtx);
        hActCtx[0] = ActCtxW;
        if ( ActCtxW != (HANDLE)-1LL )
          goto LABEL_13;
        LastError = GetLastError();
        if ( LastError - 2 <= 1 || LastError - 1812 <= 3 )
        {
          ActCtxW = 0;
          hActCtx[0] = 0;
LABEL_13:
          WinbaseIsolationAwarePrivateT_UnPgpgk = ActCtxW;
          if ( ActivateActCtx(ActCtxW, &Cookie) )
          {
            memset_0(&pActCtx, 0, sizeof(pActCtx));
            pActCtx.cbSize = 112;
            if ( FindActCtxSectionStringW(0, 0, 2u, L"Comctl32.dll", &pActCtx) )
              LoadLibraryW(L"Comctl32.dll");
            DeactivateActCtx(0, Cookie);
          }
          return 1;
        }
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800092cc  push    rbx
0x1800092ce  sub     rsp, 2F0h
0x1800092d5  mov     rax, cs:__security_cookie
0x1800092dc  xor     rax, rsp
0x1800092df  mov     [rsp+2F8h+var_18], rax
0x1800092e7  xorps   xmm0, xmm0
0x1800092ea  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x1800092ef  mov     [rsp+2F8h+Cookie], 0
0x1800092f8  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800092ff  jnz     loc_1800094AB
0x180009305  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18000930d  jnz     loc_1800094AB
0x180009313  xor     ebx, ebx
0x180009315  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18000931a  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180009323  lea     rax, [rsp+2F8h+hActCtx]
0x180009328  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18000932d  lea     r9d, [rbx+1]; ulInfoClass
0x180009331  xor     r8d, r8d; pvSubInstance
0x180009334  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18000933b  mov     ecx, 80000010h; dwFlags
0x180009340  call    cs:__imp_QueryActCtxW
0x180009346  test    eax, eax
0x180009348  jz      loc_1800094B0
0x18000934e  mov     rax, [rsp+2F8h+hActCtx]
0x180009353  test    rax, rax
0x180009356  jnz     loc_18000943C
0x18000935c  xorps   xmm0, xmm0
0x18000935f  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x180009364  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x180009369  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x180009371  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180009379  mov     [rsp+2F8h+phModule], rax
0x18000937e  lea     r8, [rsp+2F8h+phModule]; phModule
0x180009383  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18000938a  lea     ecx, [rbx+6]; dwFlags
0x18000938d  call    cs:__imp_GetModuleHandleExW
0x180009393  test    eax, eax
0x180009395  jz      loc_1800094B0
0x18000939b  mov     r8d, 105h; nSize
0x1800093a1  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x1800093a9  mov     rcx, [rsp+2F8h+phModule]; hModule
0x1800093ae  call    cs:__imp_GetModuleFileNameW
0x1800093b4  test    eax, eax
0x1800093b6  jz      loc_1800094B0
0x1800093bc  cmp     eax, 105h
0x1800093c1  jb      short loc_1800093D1
0x1800093c3  lea     ecx, [rbx+6Fh]; dwErrCode
0x1800093c6  call    cs:__imp_SetLastError
0x1800093cc  jmp     loc_1800094B0
0x1800093d1  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x1800093d9  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x1800093e1  lea     rax, [rsp+2F8h+Filename]
0x1800093e9  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x1800093ee  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x1800093fa  mov     rax, [rsp+2F8h+phModule]
0x1800093ff  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180009407  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x18000940c  call    cs:__imp_CreateActCtxW
0x180009412  mov     [rsp+2F8h+hActCtx], rax
0x180009417  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000941b  jnz     short loc_18000943C
0x18000941d  call    cs:__imp_GetLastError
0x180009423  lea     ecx, [rax-2]
0x180009426  cmp     ecx, 1
0x180009429  jbe     short loc_180009435
0x18000942b  add     eax, 0FFFFF8ECh
0x180009430  cmp     eax, 3
0x180009433  ja      short loc_1800094B0
0x180009435  xor     eax, eax
0x180009437  mov     [rsp+2F8h+hActCtx], rax
0x18000943c  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180009443  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x180009448  mov     rcx, rax; hActCtx
0x18000944b  call    cs:__imp_ActivateActCtx
0x180009451  test    eax, eax
0x180009453  jz      short loc_1800094AB
0x180009455  mov     ebx, 70h ; 'p'
0x18000945a  mov     r8d, ebx; Size
0x18000945d  xor     edx, edx; Val
0x18000945f  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x180009464  call    memset_0
0x180009469  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18000946d  lea     rax, [rsp+2F8h+pActCtx]
0x180009472  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180009477  lea     r9, LibFileName; "Comctl32.dll"
0x18000947e  xor     edx, edx; lpExtensionGuid
0x180009480  lea     r8d, [rbx-6Eh]; ulSectionId
0x180009484  xor     ecx, ecx; dwFlags
0x180009486  call    cs:__imp_FindActCtxSectionStringW
0x18000948c  test    eax, eax
0x18000948e  jz      short loc_18000949E
0x180009490  lea     rcx, LibFileName; "Comctl32.dll"
0x180009497  call    cs:__imp_LoadLibraryW
0x18000949d  nop
0x18000949e  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x1800094a3  xor     ecx, ecx; dwFlags
0x1800094a5  call    cs:__imp_DeactivateActCtx
0x1800094ab  mov     ebx, 1
0x1800094b0  mov     eax, ebx
0x1800094b2  mov     rcx, [rsp+2F8h+var_18]
0x1800094ba  xor     rcx, rsp; StackCookie
0x1800094bd  call    __security_check_cookie
0x1800094c2  add     rsp, 2F0h
0x1800094c9  pop     rbx
0x1800094ca  retn
0x180022a7f  push    rbp
0x180022a81  sub     rsp, 40h
0x180022a85  mov     rbp, rdx
0x180022a88  mov     rdx, [rbp+48h]; ulCookie
0x180022a8c  xor     ecx, ecx; dwFlags
0x180022a8e  call    cs:__imp_DeactivateActCtx
0x180022a94  nop
0x180022a95  add     rsp, 40h
0x180022a99  pop     rbp
0x180022a9a  retn
```
