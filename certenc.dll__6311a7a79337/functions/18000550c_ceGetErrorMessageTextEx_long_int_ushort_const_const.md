# ceGetErrorMessageTextEx(long,int,ushort const * const *)

- ea: `0x18000550c`
- end: `0x180005837`
- name: `?ceGetErrorMessageTextEx@@YAPEBGJHPEBQEBG@Z`
- size: `811`
- prototype: `const unsigned __int16 *__fastcall(DWORD dwMessageId, int, const unsigned __int16 *const *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180005f70`

## callees

- `0x1800053bc`
- `0x18000550c`
- `0x180005840`
- `0x180005938`
- `0x1800064e0`
- `0x180006518`
- `0x180008546`
- `0x180008580`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000576c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000576c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057e9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800057ff`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000580d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800057ff`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000580d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005656`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005656`

## string_xrefs

- `0x1800055be`: `ntdsbmsg.dll`
- `0x18000564f`: `wininet.dll`
- `0x1800056c4`: `cdosys.dll`

## pseudocode

```c
const unsigned __int16 *__fastcall ceGetErrorMessageTextEx(
        DWORD dwMessageId,
        __int64 a2,
        const unsigned __int16 *const *a3,
        const unsigned __int16 *const *a4)
{
  HMODULE v5; // r13
  const unsigned __int16 *v6; // r12
  __int64 v7; // r15
  __int64 v8; // rax
  unsigned int v9; // eax
  int v10; // r8d
  const unsigned __int16 *const *v11; // r9
  __int64 v12; // rsi
  unsigned int v13; // eax
  HMODULE System32Library; // rax
  const unsigned __int16 *const *v15; // r9
  int v16; // r14d
  signed int v17; // ebx
  unsigned int v18; // eax
  const unsigned __int16 *const *v19; // r9
  unsigned int v20; // eax
  HMODULE ModuleHandleW; // rax
  const unsigned __int16 *const *v22; // r9
  HINSTANCE v23; // r14
  DWORD v24; // ebx
  unsigned int v25; // eax
  const unsigned __int16 *const *v26; // r9
  unsigned int v27; // eax
  HINSTANCE v28; // rax
  const unsigned __int16 *const *v29; // r9
  const wchar_t *v30; // r14
  const wchar_t *v31; // rax
  unsigned __int64 v32; // rbx
  unsigned __int64 v33; // rsi
  unsigned __int16 *v34; // rax
  unsigned __int16 *v35; // rdi
  size_t v36; // rbx
  void *Src; // [rsp+20h] [rbp-69h] BYREF
  __int16 v39; // [rsp+28h] [rbp-61h] BYREF
  int v40; // [rsp+2Ch] [rbp-5Dh]
  HMODULE hLibModule; // [rsp+30h] [rbp-59h]
  __int64 v42; // [rsp+38h] [rbp-51h]
  unsigned __int16 v43[40]; // [rsp+40h] [rbp-49h] BYREF

  Src = 0;
  v5 = 0;
  v39 = 0;
  hLibModule = 0;
  if ( dwMessageId == -2147418113 )
  {
    v6 = L"Unexpected method call sequence.";
  }
  else
  {
    v6 = L"Possible data alignment fault.";
    if ( dwMessageId != -2147483646 )
      v6 = (const unsigned __int16 *)&v39;
  }
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( v6[v8] );
  v42 = v8;
  v9 = errFormatMessage(0, dwMessageId, (LPWSTR)&Src, a4);
  v12 = v9;
  if ( !v9 )
  {
    if ( (dwMessageId & 0xFFFF0000) != 0xC06D0000
      || (v13 = errFormatMessage(0, (unsigned __int16)dwMessageId, (LPWSTR)&Src, v11), (v12 = v13) == 0) )
    {
      System32Library = ceLoadSystem32Library(L"ntdsbmsg.dll");
      hLibModule = System32Library;
      v40 = 1;
      if ( System32Library )
      {
        v16 = 1;
        v17 = dwMessageId;
        v18 = errFormatMessage(System32Library, dwMessageId, (LPWSTR)&Src, v15);
        v12 = v18;
        if ( v18 )
          goto LABEL_30;
        while ( v17 < 0 )
        {
          if ( v16 && (unsigned int)ceHLastError() == -2147024579 )
          {
            if ( (v17 & 0xFFFF0000) == 0xFFFF0000 )
              v17 = -v17 | 0xC8000000;
            if ( v17 != dwMessageId )
            {
              v16 = 0;
              v20 = errFormatMessage(hLibModule, v17, (LPWSTR)&Src, v19);
              v12 = v20;
              if ( !v20 )
                continue;
            }
          }
          if ( v12 )
            goto LABEL_30;
          break;
        }
      }
      ModuleHandleW = GetModuleHandleW(L"wininet.dll");
      v23 = ModuleHandleW;
      if ( ModuleHandleW )
      {
        v24 = dwMessageId;
        v25 = errFormatMessage(ModuleHandleW, dwMessageId, (LPWSTR)&Src, v22);
        v12 = v25;
        if ( v25 )
          goto LABEL_30;
        while ( (v24 & 0xFFFF0000) == 0x80070000 )
        {
          if ( v40 )
          {
            if ( (unsigned int)ceHLastError() == -2147024579 )
            {
              v24 = (unsigned __int16)dwMessageId;
              if ( (unsigned __int16)dwMessageId != dwMessageId )
              {
                v40 = 0;
                v27 = errFormatMessage(v23, (unsigned __int16)dwMessageId, (LPWSTR)&Src, v26);
                v12 = v27;
                if ( !v27 )
                  continue;
              }
            }
          }
          if ( v12 )
            goto LABEL_30;
          break;
        }
      }
      v28 = ceLoadSystem32Library(L"cdosys.dll");
      v5 = v28;
      if ( v28 )
        v12 = errFormatMessage(v28, dwMessageId, (LPWSTR)&Src, v29);
    }
  }
LABEL_30:
  v43[0] = 0;
  v30 = 0;
  ceHResultToStringEx(v43, dwMessageId, v10);
  if ( v12 )
  {
    v31 = (const wchar_t *)Src;
  }
  else
  {
    v30 = L"Error";
    v31 = L"Error";
    Src = L"Error";
  }
  v32 = -1;
  do
    ++v32;
  while ( v31[v32] );
  if ( v32 >= 2 && v31[v32 - 2] == 13 && v31[v32 - 1] == 10 )
    v32 -= 2LL;
  do
    ++v7;
  while ( v43[v7] );
  v33 = v32 + v7 + v42 + 3;
  v34 = (unsigned __int16 *)LocalAlloc(0, 2 * v33);
  v35 = v34;
  if ( v34 )
  {
    v36 = v32;
    memcpy_0(v34, Src, v36 * 2);
    v35[v36] = 0;
    if ( v42 )
    {
      StringCchCatW(v35, v33, L" ");
      StringCchCatW(v35, v33, v6);
    }
    StringCchCatW(v35, v33, L" ");
    StringCchCatW(v35, v33, v43);
    if ( Src && v30 != Src )
      LocalFree(Src);
    Src = v35;
  }
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( v5 )
    FreeLibrary(v5);
  return (const unsigned __int16 *)Src;
}

```

## disassembly

```asm
0x18000550c  push    rbp
0x18000550e  push    rbx
0x18000550f  push    rsi
0x180005510  push    rdi
0x180005511  push    r12
0x180005513  push    r13
0x180005515  push    r14
0x180005517  push    r15
0x180005519  lea     rbp, [rsp-1Fh]
0x18000551e  sub     rsp, 0A8h
0x180005525  mov     rax, cs:__security_cookie
0x18000552c  xor     rax, rsp
0x18000552f  mov     [rbp+57h+var_50], rax
0x180005533  xor     ebx, ebx
0x180005535  mov     edi, ecx
0x180005537  mov     [rbp+57h+Src], rbx
0x18000553b  mov     r13d, ebx
0x18000553e  mov     [rbp+57h+var_B8], bx
0x180005542  mov     [rbp+57h+hLibModule], rbx
0x180005546  cmp     ecx, 8000FFFFh
0x18000554c  jnz     short loc_180005557
0x18000554e  lea     r12, aUnexpectedMeth; "Unexpected method call sequence."
0x180005555  jmp     short loc_18000556C
0x180005557  cmp     edi, 80000002h
0x18000555d  lea     r12, aPossibleDataAl; "Possible data alignment fault."
0x180005564  lea     rax, [rbp+57h+var_B8]
0x180005568  cmovnz  r12, rax
0x18000556c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180005570  mov     rax, r15
0x180005573  inc     rax
0x180005576  cmp     [r12+rax*2], bx
0x18000557b  jnz     short loc_180005573
0x18000557d  lea     r8, [rbp+57h+Src]; lpBuffer
0x180005581  mov     [rbp+57h+var_A8], rax
0x180005585  mov     edx, edi; dwMessageId
0x180005587  xor     ecx, ecx; lpSource
0x180005589  call    ?errFormatMessage@@YAKPEAUHINSTANCE__@@JPEAPEBGPEBQEBG@Z; errFormatMessage(HINSTANCE__ *,long,ushort const * *,ushort const * const *)
0x18000558e  mov     esi, eax
0x180005590  test    eax, eax
0x180005592  jnz     loc_1800056EC
0x180005598  mov     eax, edi
0x18000559a  and     eax, 0FFFF0000h
0x18000559f  cmp     eax, 0C06D0000h
0x1800055a4  jnz     short loc_1800055BE
0x1800055a6  movzx   edx, di; dwMessageId
0x1800055a9  lea     r8, [rbp+57h+Src]; lpBuffer
0x1800055ad  xor     ecx, ecx; lpSource
0x1800055af  call    ?errFormatMessage@@YAKPEAUHINSTANCE__@@JPEAPEBGPEBQEBG@Z; errFormatMessage(HINSTANCE__ *,long,ushort const * *,ushort const * const *)
0x1800055b4  mov     esi, eax
0x1800055b6  test    eax, eax
0x1800055b8  jnz     loc_1800056EC
0x1800055be  lea     rcx, aNtdsbmsgDll; "ntdsbmsg.dll"
0x1800055c5  call    ?ceLoadSystem32Library@@YAPEAUHINSTANCE__@@PEBG@Z; ceLoadSystem32Library(ushort const *)
0x1800055ca  mov     [rbp+57h+hLibModule], rax
0x1800055ce  mov     ecx, 1
0x1800055d3  mov     [rbp+57h+var_B4], ecx
0x1800055d6  test    rax, rax
0x1800055d9  jz      short loc_18000564F
0x1800055db  mov     r14d, ecx
0x1800055de  lea     r8, [rbp+57h+Src]; lpBuffer
0x1800055e2  mov     rcx, rax; lpSource
0x1800055e5  mov     edx, edi; dwMessageId
0x1800055e7  mov     ebx, edi
0x1800055e9  call    ?errFormatMessage@@YAKPEAUHINSTANCE__@@JPEAPEBGPEBQEBG@Z; errFormatMessage(HINSTANCE__ *,long,ushort const * *,ushort const * const *)
0x1800055ee  mov     esi, eax
0x1800055f0  test    rsi, rsi
0x1800055f3  jnz     loc_1800056EA
0x1800055f9  test    ebx, ebx
0x1800055fb  jns     short loc_18000564D
0x1800055fd  test    r14d, r14d
0x180005600  jz      short loc_180005640
0x180005602  call    ?ceHLastError@@YAJXZ; ceHLastError(void)
0x180005607  cmp     eax, 8007013Dh
0x18000560c  jnz     short loc_180005640
0x18000560e  mov     ecx, 0FFFF0000h
0x180005613  mov     eax, ebx
0x180005615  and     eax, ecx
0x180005617  cmp     eax, ecx
0x180005619  jnz     short loc_180005623
0x18000561b  neg     ebx
0x18000561d  or      ebx, 0C8000000h
0x180005623  cmp     ebx, edi
0x180005625  jz      short loc_180005640
0x180005627  mov     rcx, [rbp+57h+hLibModule]; lpSource
0x18000562b  lea     r8, [rbp+57h+Src]; lpBuffer
0x18000562f  mov     edx, ebx; dwMessageId
0x180005631  xor     r14d, r14d
0x180005634  call    ?errFormatMessage@@YAKPEAUHINSTANCE__@@JPEAPEBGPEBQEBG@Z; errFormatMessage(HINSTANCE__ *,long,ushort const * *,ushort const * const *)
0x180005639  mov     esi, eax
0x18000563b  test    rsi, rsi
0x18000563e  jz      short loc_1800055F9
0x180005640  xor     ebx, ebx
0x180005642  test    rsi, rsi
0x180005645  jnz     loc_1800056EC
0x18000564b  jmp     short loc_18000564F
0x18000564d  xor     ebx, ebx
0x18000564f  lea     rcx, aWininetDll; "wininet.dll"
0x180005656  call    cs:__imp_GetModuleHandleW
0x18000565c  mov     r14, rax
0x18000565f  test    rax, rax
0x180005662  jz      short loc_1800056C4
0x180005664  lea     r8, [rbp+57h+Src]; lpBuffer
0x180005668  mov     edx, edi; dwMessageId
0x18000566a  mov     rcx, rax; lpSource
0x18000566d  mov     ebx, edi
0x18000566f  call    ?errFormatMessage@@YAKPEAUHINSTANCE__@@JPEAPEBGPEBQEBG@Z; errFormatMessage(HINSTANCE__ *,long,ushort const * *,ushort const * const *)
0x180005674  mov     esi, eax
0x180005676  test    eax, eax
0x180005678  jnz     short loc_1800056EA
0x18000567a  mov     eax, ebx
0x18000567c  and     eax, 0FFFF0000h
0x180005681  cmp     eax, 80070000h
0x180005686  jnz     short loc_1800056C2
0x180005688  cmp     [rbp+57h+var_B4], r13d
0x18000568c  jz      short loc_1800056B9
0x18000568e  call    ?ceHLastError@@YAJXZ; ceHLastError(void)
0x180005693  cmp     eax, 8007013Dh
0x180005698  jnz     short loc_1800056B9
0x18000569a  movzx   ebx, bx
0x18000569d  cmp     ebx, edi
0x18000569f  jz      short loc_1800056B9
0x1800056a1  lea     r8, [rbp+57h+Src]; lpBuffer
0x1800056a5  mov     [rbp+57h+var_B4], r13d
0x1800056a9  mov     edx, ebx; dwMessageId
0x1800056ab  mov     rcx, r14; lpSource
0x1800056ae  call    ?errFormatMessage@@YAKPEAUHINSTANCE__@@JPEAPEBGPEBQEBG@Z; errFormatMessage(HINSTANCE__ *,long,ushort const * *,ushort const * const *)
0x1800056b3  mov     esi, eax
0x1800056b5  test    eax, eax
0x1800056b7  jz      short loc_18000567A
0x1800056b9  xor     ebx, ebx
0x1800056bb  test    rsi, rsi
0x1800056be  jnz     short loc_1800056EC
0x1800056c0  jmp     short loc_1800056C4
0x1800056c2  xor     ebx, ebx
0x1800056c4  lea     rcx, aCdosysDll; "cdosys.dll"
0x1800056cb  call    ?ceLoadSystem32Library@@YAPEAUHINSTANCE__@@PEBG@Z; ceLoadSystem32Library(ushort const *)
0x1800056d0  mov     r13, rax
0x1800056d3  test    rax, rax
0x1800056d6  jz      short loc_1800056EC
0x1800056d8  lea     r8, [rbp+57h+Src]; lpBuffer
0x1800056dc  mov     edx, edi; dwMessageId
0x1800056de  mov     rcx, rax; lpSource
0x1800056e1  call    ?errFormatMessage@@YAKPEAUHINSTANCE__@@JPEAPEBGPEBQEBG@Z; errFormatMessage(HINSTANCE__ *,long,ushort const * *,ushort const * const *)
0x1800056e6  mov     esi, eax
0x1800056e8  jmp     short loc_1800056EC
0x1800056ea  xor     ebx, ebx
0x1800056ec  mov     edx, edi; int
0x1800056ee  mov     [rbp+57h+var_A0], bx
0x1800056f2  lea     rcx, [rbp+57h+var_A0]; unsigned __int16 *
0x1800056f6  mov     r14, rbx
0x1800056f9  call    ?ceHResultToStringEx@@YAPEBGPEAGJH@Z; ceHResultToStringEx(ushort *,long,int)
0x1800056fe  test    rsi, rsi
0x180005701  jnz     short loc_180005713
0x180005703  lea     r14, aError; "Error"
0x18000570a  mov     rax, r14
0x18000570d  mov     [rbp+57h+Src], rax
0x180005711  jmp     short loc_180005717
0x180005713  mov     rax, [rbp+57h+Src]
0x180005717  mov     rbx, r15
0x18000571a  xor     ecx, ecx
0x18000571c  inc     rbx
0x18000571f  cmp     [rax+rbx*2], cx
0x180005723  jnz     short loc_18000571C
0x180005725  cmp     rbx, 2
0x180005729  jb      short loc_18000574A
0x18000572b  lea     rcx, [rbx-2]
0x18000572f  mov     edx, 0Dh
0x180005734  cmp     dx, [rax+rcx*2]
0x180005738  jnz     short loc_180005748
0x18000573a  mov     edx, 0Ah
0x18000573f  cmp     dx, [rax+rbx*2-2]
0x180005744  cmovz   rbx, rcx
0x180005748  xor     ecx, ecx
0x18000574a  lea     rax, [rbp+57h+var_A0]
0x18000574e  inc     r15
0x180005751  cmp     [rax+r15*2], cx
0x180005756  jnz     short loc_18000574E
0x180005758  mov     rsi, [rbp+57h+var_A8]
0x18000575c  xor     ecx, ecx; uFlags
0x18000575e  add     rsi, 3
0x180005762  add     rsi, r15
0x180005765  add     rsi, rbx
0x180005768  lea     rdx, [rsi+rsi]; uBytes
0x18000576c  call    cs:__imp_LocalAlloc
0x180005772  xor     r15d, r15d
0x180005775  mov     rdi, rax
0x180005778  test    rax, rax
0x18000577b  jz      short loc_1800057F3
0x18000577d  mov     rdx, [rbp+57h+Src]; Src
0x180005781  add     rbx, rbx
0x180005784  mov     r8, rbx; Size
0x180005787  mov     rcx, rax; void *
0x18000578a  call    memcpy_0
0x18000578f  mov     [rbx+rdi], r15w
0x180005794  cmp     [rbp+57h+var_A8], r15
0x180005798  jz      short loc_1800057BA
0x18000579a  lea     r8, asc_18000C3F4; " "
0x1800057a1  mov     rdx, rsi; unsigned __int64
0x1800057a4  mov     rcx, rdi; unsigned __int16 *
0x1800057a7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800057ac  mov     r8, r12; unsigned __int16 *
0x1800057af  mov     rdx, rsi; unsigned __int64
0x1800057b2  mov     rcx, rdi; unsigned __int16 *
0x1800057b5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800057ba  lea     r8, asc_18000C3F4; " "
0x1800057c1  mov     rdx, rsi; unsigned __int64
0x1800057c4  mov     rcx, rdi; unsigned __int16 *
0x1800057c7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800057cc  lea     r8, [rbp+57h+var_A0]; unsigned __int16 *
0x1800057d0  mov     rdx, rsi; unsigned __int64
0x1800057d3  mov     rcx, rdi; unsigned __int16 *
0x1800057d6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800057db  mov     rcx, [rbp+57h+Src]; hMem
0x1800057df  test    rcx, rcx
0x1800057e2  jz      short loc_1800057EF
0x1800057e4  cmp     r14, rcx
0x1800057e7  jz      short loc_1800057EF
0x1800057e9  call    cs:__imp_LocalFree
0x1800057ef  mov     [rbp+57h+Src], rdi
0x1800057f3  mov     rax, [rbp+57h+hLibModule]
0x1800057f7  test    rax, rax
0x1800057fa  jz      short loc_180005805
0x1800057fc  mov     rcx, rax; hLibModule
0x1800057ff  call    cs:__imp_FreeLibrary
0x180005805  test    r13, r13
0x180005808  jz      short loc_180005813
0x18000580a  mov     rcx, r13; hLibModule
0x18000580d  call    cs:__imp_FreeLibrary
0x180005813  mov     rax, [rbp+57h+Src]
0x180005817  mov     rcx, [rbp+57h+var_50]
0x18000581b  xor     rcx, rsp; StackCookie
0x18000581e  call    __security_check_cookie
0x180005823  add     rsp, 0A8h
0x18000582a  pop     r15
0x18000582c  pop     r14
0x18000582e  pop     r13
0x180005830  pop     r12
0x180005832  pop     rdi
0x180005833  pop     rsi
0x180005834  pop     rbx
0x180005835  pop     rbp
0x180005836  retn
```
