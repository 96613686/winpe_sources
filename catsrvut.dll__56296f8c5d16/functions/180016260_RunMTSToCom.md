# RunMTSToCom

- ea: `0x180016260`
- end: `0x1800163ac`
- name: `RunMTSToCom`
- size: `332`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180014734`
- `0x180014924`
- `0x180014ec8`
- `0x180016260`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800162d8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180016381`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800162d8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180016381`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001639c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001639c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800162ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800162ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800162a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180016296`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180016322`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180016296`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180016322`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1800163a5`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1800163a5`

## string_xrefs

- `0x18001634d`: `mtstocom.exe" `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn RunMTSToCom(unsigned int a1, __int64 a2, const CHAR *a3)
{
  unsigned __int16 *v4; // rdi
  signed int v5; // ebx
  UINT SystemDirectoryW; // ebx
  signed int LastError; // eax
  int v8; // eax
  __int64 cchWideChar; // r14
  unsigned __int16 *v10; // rax
  UINT v11; // esi
  __int64 v12; // rax
  __int64 v13; // rsi

  v4 = 0;
  if ( !a3 )
  {
    v5 = -2147467261;
    goto LABEL_16;
  }
  v5 = SetLocalComputerTransactionTimeout(a1);
  if ( v5 >= 0 )
  {
    SystemDirectoryW = GetSystemDirectoryW(0, 0);
    if ( !SystemDirectoryW )
      goto LABEL_5;
    v8 = MultiByteToWideChar(3u, 0, a3, -1, 0, 0);
    cchWideChar = v8;
    if ( !v8 )
      goto LABEL_5;
    v10 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v8 + SystemDirectoryW + 2 + 15LL, 2u));
    v4 = v10;
    if ( !v10 )
    {
      v5 = -2147024882;
      goto LABEL_16;
    }
    *v10 = 34;
    v11 = GetSystemDirectoryW(v10 + 1, SystemDirectoryW);
    if ( !v11 )
    {
LABEL_5:
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_16;
    }
    v12 = v11;
    v13 = v11 + 1;
    if ( v4[v12] != 92 )
    {
      v4[v13] = 92;
      v13 = (unsigned int)(v13 + 1);
      v4[v13] = 0;
    }
    v5 = StringCchCatW(v4, cchWideChar + SystemDirectoryW + 2 + 15LL, L"mtstocom.exe\" ");
    if ( v5 >= 0 )
    {
      if ( MultiByteToWideChar(3u, 0, a3, -1, &v4[(unsigned int)(v13 + 14)], cchWideChar) )
      {
        v5 = RunCmd(v4);
        goto LABEL_16;
      }
      goto LABEL_5;
    }
  }
LABEL_16:
  CoTaskMemFree(v4);
  ExitProcess(v5);
}

```

## disassembly

```asm
0x180016260  push    rbx
0x180016262  push    rbp
0x180016263  push    rsi
0x180016264  push    rdi
0x180016265  push    r12
0x180016267  push    r14
0x180016269  push    r15
0x18001626b  sub     rsp, 30h
0x18001626f  mov     rbp, r8
0x180016272  xor     edi, edi
0x180016274  test    r8, r8
0x180016277  jnz     short loc_180016283
0x180016279  mov     ebx, 80004003h
0x18001627e  jmp     loc_180016399
0x180016283  call    ?SetLocalComputerTransactionTimeout@@YAJK@Z; SetLocalComputerTransactionTimeout(ulong)
0x180016288  mov     ebx, eax
0x18001628a  test    eax, eax
0x18001628c  js      loc_180016399
0x180016292  xor     edx, edx; uSize
0x180016294  xor     ecx, ecx; lpBuffer
0x180016296  call    cs:__imp_GetSystemDirectoryW
0x18001629c  mov     ebx, eax
0x18001629e  test    eax, eax
0x1800162a0  jnz     short loc_1800162C0
0x1800162a2  call    cs:__imp_GetLastError
0x1800162a8  mov     ebx, eax
0x1800162aa  test    eax, eax
0x1800162ac  jle     loc_180016399
0x1800162b2  movzx   ebx, ax
0x1800162b5  or      ebx, 80070000h
0x1800162bb  jmp     loc_180016399
0x1800162c0  mov     [rsp+68h+cchWideChar], edi; cchWideChar
0x1800162c4  mov     [rsp+68h+lpWideCharStr], rdi; lpWideCharStr
0x1800162c9  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800162cd  mov     r9d, r12d; cbMultiByte
0x1800162d0  mov     r8, rbp; lpMultiByteStr
0x1800162d3  xor     edx, edx; dwFlags
0x1800162d5  lea     ecx, [rdx+3]; CodePage
0x1800162d8  call    cs:__imp_MultiByteToWideChar
0x1800162de  movsxd  r14, eax
0x1800162e1  test    eax, eax
0x1800162e3  jz      short loc_1800162A2
0x1800162e5  lea     r15d, [rbx+2]
0x1800162e9  add     r15, 0Fh
0x1800162ed  add     r15, r14
0x1800162f0  lea     eax, [r12+3]
0x1800162f5  mul     r15
0x1800162f8  cmovb   rax, r12
0x1800162fc  mov     rcx, rax; cb
0x1800162ff  call    cs:__imp_CoTaskMemAlloc
0x180016305  mov     rdi, rax
0x180016308  test    rax, rax
0x18001630b  jnz     short loc_180016317
0x18001630d  mov     ebx, 8007000Eh
0x180016312  jmp     loc_180016399
0x180016317  mov     word ptr [rax], 22h ; '"'
0x18001631c  lea     rcx, [rax+2]; lpBuffer
0x180016320  mov     edx, ebx; uSize
0x180016322  call    cs:__imp_GetSystemDirectoryW
0x180016328  mov     esi, eax
0x18001632a  test    eax, eax
0x18001632c  jz      loc_1800162A2
0x180016332  mov     eax, esi
0x180016334  inc     esi
0x180016336  mov     ecx, 5Ch ; '\'
0x18001633b  cmp     [rdi+rax*2], cx
0x18001633f  jz      short loc_18001634D
0x180016341  mov     [rdi+rsi*2], cx
0x180016345  inc     esi
0x180016347  xor     eax, eax
0x180016349  mov     [rdi+rsi*2], ax
0x18001634d  lea     r8, aMtstocomExe; "mtstocom.exe\" "
0x180016354  mov     rdx, r15; unsigned __int64
0x180016357  mov     rcx, rdi; unsigned __int16 *
0x18001635a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001635f  mov     ebx, eax
0x180016361  test    eax, eax
0x180016363  js      short loc_180016399
0x180016365  lea     eax, [rsi+0Eh]
0x180016368  lea     rax, [rdi+rax*2]
0x18001636c  mov     [rsp+68h+cchWideChar], r14d; cchWideChar
0x180016371  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x180016376  mov     r9d, r12d; cbMultiByte
0x180016379  mov     r8, rbp; lpMultiByteStr
0x18001637c  xor     edx, edx; dwFlags
0x18001637e  lea     ecx, [rdx+3]; CodePage
0x180016381  call    cs:__imp_MultiByteToWideChar
0x180016387  test    eax, eax
0x180016389  jz      loc_1800162A2
0x18001638f  mov     rcx, rdi; unsigned __int16 *
0x180016392  call    ?RunCmd@@YAJPEAGH@Z; RunCmd(ushort *,int)
0x180016397  mov     ebx, eax
0x180016399  mov     rcx, rdi; pv
0x18001639c  call    cs:__imp_CoTaskMemFree
0x1800163a2  nop
0x1800163a3  mov     ecx, ebx; uExitCode
0x1800163a5  call    cs:__imp_ExitProcess
```
