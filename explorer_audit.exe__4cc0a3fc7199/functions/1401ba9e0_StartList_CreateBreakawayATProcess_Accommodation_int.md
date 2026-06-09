# StartList::CreateBreakawayATProcess(Accommodation *,int)

- ea: `0x1401ba9e0`
- end: `0x1401bad8c`
- name: `?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z`
- size: `940`
- prototype: `int(StartList *__hidden this, struct Accommodation *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1401bbfcc`

## callees

- `0x1400158a4`
- `0x1400847f8`
- `0x140104ce0`
- `0x1401b96ac`
- `0x1401b9edc`
- `0x1401ba6b4`
- `0x1401ba9e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401baae8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401babb4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401babc3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bad5f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401baae8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401babb4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401babc3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401bad5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1401bac6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1401bad47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1401bac6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1401bad47`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1401bac78`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1401bac78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1401bad55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1401bad55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401baa84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401baa84`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1401bacc2`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1401bacc2`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1401bad3c`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1401bad3c`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1401bac60`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1401bac93`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1401bac60`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1401bac93`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1401bad0c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1401bad0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bad1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bad27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bad1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401bad27`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1401bac3d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1401bac3d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1401baa7a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1401baa7a`
- `api-ms-win-rtcore-ntuser-shell-l1-1-0!GetShellWindow` at `0x1401bac0a`
- `api-ms-win-rtcore-ntuser-shell-l1-1-0!GetShellWindow` at `0x1401bac0a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1401bac24`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1401bac24`

## string_xrefs

- `0x1401bab23`: `/launchnarratorupdates`
- `0x1401baa2c`: `%SystemRoot%\System32\ATBroker.exe`
- `0x1401baa73`: `%SystemRoot%\System32\ATBroker.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartList::CreateBreakawayATProcess(StartList *this, struct Accommodation *a2, int a3)
{
  char *v6; // rbx
  DWORD v7; // eax
  signed int LastError; // eax
  unsigned int v9; // esi
  unsigned __int64 v10; // rax
  char *v11; // rbx
  char IsEnabled; // al
  char v13; // dl
  const wchar_t *v14; // rcx
  const wchar_t *v15; // rax
  const wchar_t *v16; // rdx
  unsigned __int64 v17; // rdx
  WCHAR *v18; // rbx
  int v19; // eax
  const wchar_t *v20; // rdx
  unsigned __int64 v21; // rdx
  int v22; // r15d
  struct _PROC_THREAD_ATTRIBUTE_LIST *v23; // r14
  HWND ShellWindow; // rax
  SIZE_T v25; // rsi
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v27; // rax
  BOOL updated; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v29; // rcx
  HANDLE v30; // rax
  const wchar_t *lpPreviousValue; // [rsp+30h] [rbp-91h]
  const wchar_t *lpPreviousValuea; // [rsp+30h] [rbp-91h]
  ULONG_PTR Size; // [rsp+58h] [rbp-69h] BYREF
  HANDLE Value; // [rsp+60h] [rbp-61h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-59h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+88h] [rbp-39h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v37; // [rsp+F0h] [rbp+2Fh]
  void *Block; // [rsp+128h] [rbp+67h] BYREF
  LPWSTR lpDst; // [rsp+140h] [rbp+7Fh] BYREF

  Block = this;
  if ( (unsigned int)Accommodation::IsRunning(a2) )
    return 0;
  Block = 0;
  if ( (int)StringCchLengthW(StartList::_atBrokerExe, 0x7FFFFFFFu, (unsigned __int64 *)&Block) >= 0 )
  {
    v6 = (char *)Block + 260;
    if ( (char *)Block + 260 >= Block )
    {
      lpDst = 0;
      if ( (unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&lpDst, (char *)Block + 260) )
      {
        v7 = ExpandEnvironmentStringsW(StartList::_atBrokerExe, lpDst, (DWORD)v6);
        if ( !v7 )
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_32;
        }
        if ( v7 > (unsigned __int64)v6 )
        {
          v9 = -2147024774;
LABEL_32:
          free(lpDst);
          return v9;
        }
        v10 = (unsigned __int64)(v6 + 22);
        if ( v6 + 22 >= v6 )
        {
          v11 = v6 + 282;
          if ( v10 + 260 >= v10 )
          {
            Block = 0;
            if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v10 + 260) )
            {
              free(Block);
              goto LABEL_15;
            }
            IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl'::`2'::impl);
            v13 = *((_BYTE *)a2 + 85);
            v14 = L"/launchnarratorhome";
            if ( IsEnabled )
            {
              if ( !v13 )
                v14 = (const wchar_t *)&Class;
              v15 = L"/launchnarratorupdates";
              if ( !*((_BYTE *)a2 + 86) )
                v15 = (const wchar_t *)&Class;
              v16 = L"/hardwarebuttonlaunch";
              if ( !*((_BYTE *)a2 + 84) )
                v16 = (const wchar_t *)&Class;
              lpPreviousValue = v16;
              v17 = (unsigned __int64)v11;
              v18 = (WCHAR *)Block;
              v19 = StringCchPrintfW(
                      (unsigned __int16 *)Block,
                      v17,
                      L"%s /start %s %s %s %s",
                      lpDst,
                      *(_QWORD *)a2,
                      lpPreviousValue,
                      v15,
                      v14);
            }
            else
            {
              if ( !v13 )
                v14 = (const wchar_t *)&Class;
              v20 = L"/hardwarebuttonlaunch";
              if ( !*((_BYTE *)a2 + 84) )
                v20 = (const wchar_t *)&Class;
              lpPreviousValuea = v20;
              v21 = (unsigned __int64)v11;
              v18 = (WCHAR *)Block;
              v19 = StringCchPrintfW(
                      (unsigned __int16 *)Block,
                      v21,
                      L"%s /start %s %s %s",
                      lpDst,
                      *(_QWORD *)a2,
                      lpPreviousValuea,
                      v14);
            }
            if ( v19 >= 0 )
            {
              memset(&ProcessInformation, 0, sizeof(ProcessInformation));
              memset_0(&StartupInfo.cb + 1, 0, 0x6Cu);
              StartupInfo.cb = 112;
              Value = 0;
              v22 = 0;
              v23 = 0;
              Size = 0;
              if ( a3 )
              {
                ShellWindow = GetShellWindow();
                if ( ShellWindow )
                {
                  LODWORD(Block) = 0;
                  if ( GetWindowThreadProcessId(ShellWindow, (LPDWORD)&Block) )
                  {
                    Value = OpenProcess(0x80u, 0, (DWORD)Block);
                    if ( Value )
                    {
                      InitializeProcThreadAttributeList(0, 1u, 0, &Size);
                      v25 = Size;
                      ProcessHeap = GetProcessHeap();
                      v27 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)HeapAlloc(ProcessHeap, 0, v25);
                      v23 = v27;
                      if ( v27 )
                      {
                        if ( InitializeProcThreadAttributeList(v27, 1u, 0, &Size) )
                        {
                          v22 = 1;
                          updated = UpdateProcThreadAttribute(v23, 0, 0x20000u, &Value, 8u, 0, 0);
                          v29 = v37;
                          if ( updated )
                            v29 = v23;
                          v37 = v29;
                        }
                      }
                    }
                  }
                }
              }
              if ( CreateProcessW(lpDst, v18, 0, 0, 0, 0x1080000u, 0, 0, &StartupInfo, &ProcessInformation) )
              {
                v9 = 0;
                CloseHandle(ProcessInformation.hProcess);
                CloseHandle(ProcessInformation.hThread);
              }
              else
              {
                v9 = -2147467259;
              }
              if ( v22 )
                DeleteProcThreadAttributeList(v23);
              if ( v23 )
              {
                v30 = GetProcessHeap();
                HeapFree(v30, 0, v23);
              }
              free(v18);
              goto LABEL_32;
            }
            free(v18);
          }
        }
        v9 = -2147467259;
        goto LABEL_32;
      }
LABEL_15:
      v9 = -2147024882;
      goto LABEL_32;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x1401ba9e0  mov     rax, rsp
0x1401ba9e3  mov     [rax+10h], rbx
0x1401ba9e7  mov     [rax+18h], rsi
0x1401ba9eb  mov     [rax+8], rcx
0x1401ba9ef  push    rbp
0x1401ba9f0  push    r12
0x1401ba9f2  push    r13
0x1401ba9f4  push    r14
0x1401ba9f6  push    r15
0x1401ba9f8  lea     rbp, [rax-5Fh]
0x1401ba9fc  sub     rsp, 0F0h
0x1401baa03  mov     r12d, r8d
0x1401baa06  mov     rsi, rdx
0x1401baa09  mov     rcx, rdx; this
0x1401baa0c  call    ?IsRunning@Accommodation@@QEAAHXZ; Accommodation::IsRunning(void)
0x1401baa11  xor     r13d, r13d
0x1401baa14  test    eax, eax
0x1401baa16  jz      short loc_1401BAA1F
0x1401baa18  xor     eax, eax
0x1401baa1a  jmp     loc_1401BAD6F
0x1401baa1f  mov     [rbp+57h+Block], r13
0x1401baa23  lea     r8, [rbp+57h+Block]; unsigned __int64 *
0x1401baa27  mov     edx, 7FFFFFFFh; unsigned __int64
0x1401baa2c  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x1401baa33  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1401baa38  test    eax, eax
0x1401baa3a  js      loc_1401BAD6A
0x1401baa40  mov     rax, [rbp+57h+Block]
0x1401baa44  lea     rbx, [rax+104h]
0x1401baa4b  cmp     rbx, rax
0x1401baa4e  jb      loc_1401BAD6A
0x1401baa54  mov     [rbp+57h+lpDst], r13
0x1401baa58  mov     rdx, rbx
0x1401baa5b  lea     rcx, [rbp+57h+lpDst]
0x1401baa5f  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x1401baa64  test    al, al
0x1401baa66  jz      loc_1401BAAEE
0x1401baa6c  mov     r8d, ebx; nSize
0x1401baa6f  mov     rdx, [rbp+57h+lpDst]; lpDst
0x1401baa73  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x1401baa7a  call    cs:__imp_ExpandEnvironmentStringsW
0x1401baa80  test    eax, eax
0x1401baa82  jnz     short loc_1401BAAA2
0x1401baa84  call    cs:__imp_GetLastError
0x1401baa8a  mov     esi, eax
0x1401baa8c  test    eax, eax
0x1401baa8e  jle     loc_1401BABBF
0x1401baa94  movzx   esi, ax
0x1401baa97  or      esi, 80070000h
0x1401baa9d  jmp     loc_1401BABBF
0x1401baaa2  mov     eax, eax
0x1401baaa4  cmp     rax, rbx
0x1401baaa7  jbe     short loc_1401BAAB3
0x1401baaa9  mov     esi, 8007007Ah
0x1401baaae  jmp     loc_1401BABBF
0x1401baab3  lea     rax, [rbx+16h]
0x1401baab7  cmp     rax, rbx
0x1401baaba  jb      loc_1401BABBA
0x1401baac0  lea     rbx, [rax+104h]
0x1401baac7  cmp     rbx, rax
0x1401baaca  jb      loc_1401BABBA
0x1401baad0  mov     [rbp+57h+Block], r13
0x1401baad4  mov     rdx, rbx
0x1401baad7  lea     rcx, [rbp+57h+Block]
0x1401baadb  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x1401baae0  test    al, al
0x1401baae2  jnz     short loc_1401BAAF8
0x1401baae4  mov     rcx, [rbp+57h+Block]; Block
0x1401baae8  call    cs:__imp_free
0x1401baaee  mov     esi, 8007000Eh
0x1401baaf3  jmp     loc_1401BABBF
0x1401baaf8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates> `wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl(void)'::`2'::impl
0x1401baaff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(void)
0x1401bab04  mov     dl, [rsi+55h]
0x1401bab07  lea     r8, Class
0x1401bab0e  lea     rcx, aLaunchnarrator; "/launchnarratorhome"
0x1401bab15  mov     r9, [rbp+57h+lpDst]
0x1401bab19  test    al, al
0x1401bab1b  jz      short loc_1401BAB70
0x1401bab1d  test    dl, dl
0x1401bab1f  cmovz   rcx, r8
0x1401bab23  lea     rax, aLaunchnarrator_0; "/launchnarratorupdates"
0x1401bab2a  cmp     [rsi+56h], r13b
0x1401bab2e  cmovz   rax, r8
0x1401bab32  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x1401bab39  cmp     [rsi+54h], r13b
0x1401bab3d  cmovz   rdx, r8
0x1401bab41  mov     [rsp+110h+lpCurrentDirectory], rcx
0x1401bab46  mov     [rsp+110h+lpReturnSize], rax
0x1401bab4b  mov     [rsp+110h+lpPreviousValue], rdx
0x1401bab50  mov     rax, [rsi]
0x1401bab53  mov     [rsp+110h+cbSize], rax
0x1401bab58  lea     r8, aSStartSSSS; "%s /start %s %s %s %s"
0x1401bab5f  mov     rdx, rbx; unsigned __int64
0x1401bab62  mov     rbx, [rbp+57h+Block]
0x1401bab66  mov     rcx, rbx; unsigned __int16 *
0x1401bab69  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401bab6e  jmp     short loc_1401BABAD
0x1401bab70  test    dl, dl
0x1401bab72  cmovz   rcx, r8
0x1401bab76  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x1401bab7d  cmp     [rsi+54h], r13b
0x1401bab81  cmovz   rdx, r8
0x1401bab85  mov     [rsp+110h+lpReturnSize], rcx
0x1401bab8a  mov     [rsp+110h+lpPreviousValue], rdx
0x1401bab8f  mov     rax, [rsi]
0x1401bab92  mov     [rsp+110h+cbSize], rax
0x1401bab97  lea     r8, aSStartSSS; "%s /start %s %s %s"
0x1401bab9e  mov     rdx, rbx; unsigned __int64
0x1401baba1  mov     rbx, [rbp+57h+Block]
0x1401baba5  mov     rcx, rbx; unsigned __int16 *
0x1401baba8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401babad  test    eax, eax
0x1401babaf  jns     short loc_1401BABD0
0x1401babb1  mov     rcx, rbx; Block
0x1401babb4  call    cs:__imp_free
0x1401babba  mov     esi, 80004005h
0x1401babbf  mov     rcx, [rbp+57h+lpDst]; Block
0x1401babc3  call    cs:__imp_free
0x1401babc9  mov     eax, esi
0x1401babcb  jmp     loc_1401BAD6F
0x1401babd0  xorps   xmm0, xmm0
0x1401babd3  xor     eax, eax
0x1401babd5  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x1401babd9  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x1401babdd  xor     edx, edx; Val
0x1401babdf  lea     r8d, [rax+6Ch]; Size
0x1401babe3  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x1401babe7  call    memset_0
0x1401babec  mov     [rbp+57h+StartupInfo.cb], 70h ; 'p'
0x1401babf3  mov     [rbp+57h+Value], r13
0x1401babf7  mov     r15d, r13d
0x1401babfa  mov     r14, r13
0x1401babfd  mov     [rbp+57h+Size], r13
0x1401bac01  test    r12d, r12d
0x1401bac04  jz      loc_1401BACD6
0x1401bac0a  call    cs:__imp_GetShellWindow
0x1401bac10  test    rax, rax
0x1401bac13  jz      loc_1401BACD6
0x1401bac19  mov     dword ptr [rbp+57h+Block], r13d
0x1401bac1d  lea     rdx, [rbp+57h+Block]; lpdwProcessId
0x1401bac21  mov     rcx, rax; hWnd
0x1401bac24  call    cs:__imp_GetWindowThreadProcessId
0x1401bac2a  test    eax, eax
0x1401bac2c  jz      loc_1401BACD6
0x1401bac32  mov     r8d, dword ptr [rbp+57h+Block]; dwProcessId
0x1401bac36  xor     edx, edx; bInheritHandle
0x1401bac38  mov     ecx, 80h; dwDesiredAccess
0x1401bac3d  call    cs:__imp_OpenProcess
0x1401bac43  mov     [rbp+57h+Value], rax
0x1401bac47  test    rax, rax
0x1401bac4a  jz      loc_1401BACD6
0x1401bac50  lea     r9, [rbp+57h+Size]; lpSize
0x1401bac54  xor     r8d, r8d; dwFlags
0x1401bac57  lea     r12d, [r8+1]
0x1401bac5b  mov     edx, r12d; dwAttributeCount
0x1401bac5e  xor     ecx, ecx; lpAttributeList
0x1401bac60  call    cs:__imp_InitializeProcThreadAttributeList
0x1401bac66  mov     rsi, [rbp+57h+Size]
0x1401bac6a  call    cs:__imp_GetProcessHeap
0x1401bac70  mov     r8, rsi; dwBytes
0x1401bac73  xor     edx, edx; dwFlags
0x1401bac75  mov     rcx, rax; hHeap
0x1401bac78  call    cs:__imp_HeapAlloc
0x1401bac7e  mov     r14, rax
0x1401bac81  test    rax, rax
0x1401bac84  jz      short loc_1401BACD6
0x1401bac86  lea     r9, [rbp+57h+Size]; lpSize
0x1401bac8a  xor     r8d, r8d; dwFlags
0x1401bac8d  mov     edx, r12d; dwAttributeCount
0x1401bac90  mov     rcx, rax; lpAttributeList
0x1401bac93  call    cs:__imp_InitializeProcThreadAttributeList
0x1401bac99  test    eax, eax
0x1401bac9b  jz      short loc_1401BACD6
0x1401bac9d  mov     r15d, r12d
0x1401baca0  mov     [rsp+110h+lpReturnSize], r13; lpReturnSize
0x1401baca5  mov     [rsp+110h+lpPreviousValue], r13; lpPreviousValue
0x1401bacaa  mov     [rsp+110h+cbSize], 8; cbSize
0x1401bacb3  lea     r9, [rbp+57h+Value]; lpValue
0x1401bacb7  xor     edx, edx; dwFlags
0x1401bacb9  mov     r8d, 20000h; Attribute
0x1401bacbf  mov     rcx, r14; lpAttributeList
0x1401bacc2  call    cs:__imp_UpdateProcThreadAttribute
0x1401bacc8  mov     rcx, [rbp+57h+var_28]
0x1401baccc  test    eax, eax
0x1401bacce  cmovnz  rcx, r14
0x1401bacd2  mov     [rbp+57h+var_28], rcx
0x1401bacd6  lea     rax, [rbp+57h+ProcessInformation]
0x1401bacda  mov     [rsp+110h+lpProcessInformation], rax; lpProcessInformation
0x1401bacdf  lea     rax, [rbp+57h+StartupInfo]
0x1401bace3  mov     [rsp+110h+lpStartupInfo], rax; lpStartupInfo
0x1401bace8  mov     [rsp+110h+lpCurrentDirectory], r13; lpCurrentDirectory
0x1401baced  mov     [rsp+110h+lpReturnSize], r13; lpEnvironment
0x1401bacf2  mov     dword ptr [rsp+110h+lpPreviousValue], 1080000h; dwCreationFlags
0x1401bacfa  mov     dword ptr [rsp+110h+cbSize], r13d; bInheritHandles
0x1401bacff  xor     r9d, r9d; lpThreadAttributes
0x1401bad02  xor     r8d, r8d; lpProcessAttributes
0x1401bad05  mov     rdx, rbx; lpCommandLine
0x1401bad08  mov     rcx, [rbp+57h+lpDst]; lpApplicationName
0x1401bad0c  call    cs:__imp_CreateProcessW
0x1401bad12  test    eax, eax
0x1401bad14  jz      short loc_1401BAD2F
0x1401bad16  mov     esi, r13d
0x1401bad19  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x1401bad1d  call    cs:__imp_CloseHandle
0x1401bad23  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x1401bad27  call    cs:__imp_CloseHandle
0x1401bad2d  jmp     short loc_1401BAD34
0x1401bad2f  mov     esi, 80004005h
0x1401bad34  test    r15d, r15d
0x1401bad37  jz      short loc_1401BAD42
0x1401bad39  mov     rcx, r14; lpAttributeList
0x1401bad3c  call    cs:__imp_DeleteProcThreadAttributeList
0x1401bad42  test    r14, r14
0x1401bad45  jz      short loc_1401BAD5C
0x1401bad47  call    cs:__imp_GetProcessHeap
0x1401bad4d  mov     rcx, rax; hHeap
0x1401bad50  mov     r8, r14; lpMem
0x1401bad53  xor     edx, edx; dwFlags
0x1401bad55  call    cs:__imp_HeapFree
0x1401bad5b  nop
0x1401bad5c  mov     rcx, rbx; Block
0x1401bad5f  call    cs:__imp_free
0x1401bad65  jmp     loc_1401BABBF
0x1401bad6a  mov     eax, 80004005h
0x1401bad6f  lea     r11, [rsp+110h+var_20]
0x1401bad77  mov     rbx, [r11+38h]
0x1401bad7b  mov     rsi, [r11+40h]
0x1401bad7f  mov     rsp, r11
0x1401bad82  pop     r15
0x1401bad84  pop     r14
0x1401bad86  pop     r13
0x1401bad88  pop     r12
0x1401bad8a  pop     rbp
0x1401bad8b  retn
```
