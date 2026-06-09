# StartList::CreateBreakawayATProcess(Accommodation *,int)

- ea: `0x14001e0e0`
- end: `0x14001e457`
- name: `?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z`
- size: `887`
- prototype: `int(StartList *__hidden this, struct Accommodation *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140020938`

## callees

- `0x140002de3`
- `0x140009f28`
- `0x140013a34`
- `0x14001c494`
- `0x14001e0e0`
- `0x14001ed1c`
- `0x1400211d0`
- `0x140021724`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001e184`
- `KERNEL32!GetLastError` at `0x14001e184`
- `KERNEL32!CloseHandle` at `0x14001e3e8`
- `KERNEL32!CloseHandle` at `0x14001e3f2`
- `KERNEL32!CloseHandle` at `0x14001e3e8`
- `KERNEL32!CloseHandle` at `0x14001e3f2`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x14001e407`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x14001e407`
- `KERNEL32!CreateProcessW` at `0x14001e3d7`
- `KERNEL32!CreateProcessW` at `0x14001e3d7`
- `KERNEL32!UpdateProcThreadAttribute` at `0x14001e38d`
- `KERNEL32!UpdateProcThreadAttribute` at `0x14001e38d`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x14001e32b`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x14001e35e`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x14001e32b`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x14001e35e`
- `KERNEL32!HeapAlloc` at `0x14001e343`
- `KERNEL32!HeapAlloc` at `0x14001e343`
- `KERNEL32!GetProcessHeap` at `0x14001e335`
- `KERNEL32!GetProcessHeap` at `0x14001e412`
- `KERNEL32!GetProcessHeap` at `0x14001e335`
- `KERNEL32!GetProcessHeap` at `0x14001e412`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14001e17a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14001e17a`
- `KERNEL32!HeapFree` at `0x14001e420`
- `KERNEL32!HeapFree` at `0x14001e420`
- `msvcrt!free` at `0x14001e1e8`
- `msvcrt!free` at `0x14001e2b4`
- `msvcrt!free` at `0x14001e2c3`
- `msvcrt!free` at `0x14001e42a`
- `msvcrt!free` at `0x14001e1e8`
- `msvcrt!free` at `0x14001e2b4`
- `msvcrt!free` at `0x14001e2c3`
- `msvcrt!free` at `0x14001e42a`

## string_xrefs

- `0x14001e223`: `/launchnarratorupdates`
- `0x14001e12c`: `%SystemRoot%\System32\ATBroker.exe`
- `0x14001e173`: `%SystemRoot%\System32\ATBroker.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartList::CreateBreakawayATProcess(WCHAR *this, struct Accommodation *a2, int a3)
{
  LPWSTR v6; // rbx
  DWORD v7; // eax
  signed int LastError; // eax
  unsigned int v9; // esi
  unsigned __int64 v10; // rax
  LPWSTR v11; // rbx
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
  unsigned int v22; // ecx
  int v23; // r15d
  struct _PROC_THREAD_ATTRIBUTE_LIST *v24; // r14
  SIZE_T v25; // rsi
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v27; // rax
  BOOL updated; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v29; // rcx
  HANDLE v30; // rax
  const wchar_t *lpPreviousValue; // [rsp+30h] [rbp-91h]
  const wchar_t *lpPreviousValuea; // [rsp+30h] [rbp-91h]
  ULONG_PTR Size; // [rsp+58h] [rbp-69h] BYREF
  void *Value; // [rsp+60h] [rbp-61h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-59h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+88h] [rbp-39h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v37; // [rsp+F0h] [rbp+2Fh]
  LPWSTR lpDst; // [rsp+128h] [rbp+67h] BYREF
  void *Block; // [rsp+140h] [rbp+7Fh] BYREF

  lpDst = this;
  if ( (unsigned int)Accommodation::IsRunning(a2) )
    return 0;
  lpDst = 0;
  if ( (int)StringCchLengthW(StartList::_atBrokerExe, 0x7FFFFFFFu, (unsigned __int64 *)&lpDst) >= 0 )
  {
    v6 = lpDst + 130;
    if ( lpDst + 130 >= lpDst )
    {
      lpDst = 0;
      if ( (unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&lpDst, v6) )
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
        v10 = (unsigned __int64)(v6 + 11);
        if ( v6 + 11 >= v6 )
        {
          v11 = v6 + 141;
          if ( v10 + 260 >= v10 )
          {
            Block = 0;
            if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v10 + 260) )
            {
              free(Block);
              goto LABEL_15;
            }
            IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl'::`2'::impl);
            v13 = *((_BYTE *)a2 + 85);
            v14 = L"/launchnarratorhome";
            if ( IsEnabled )
            {
              if ( !v13 )
                v14 = &qword_14002AAD0;
              v15 = L"/launchnarratorupdates";
              if ( !*((_BYTE *)a2 + 86) )
                v15 = &qword_14002AAD0;
              v16 = L"/hardwarebuttonlaunch";
              if ( !*((_BYTE *)a2 + 84) )
                v16 = &qword_14002AAD0;
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
                v14 = &qword_14002AAD0;
              v20 = L"/hardwarebuttonlaunch";
              if ( !*((_BYTE *)a2 + 84) )
                v20 = &qword_14002AAD0;
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
              v23 = 0;
              v24 = 0;
              Size = 0;
              if ( a3 )
              {
                if ( (int)GetShellProcessHandle(v22, &Value) >= 0 )
                {
                  InitializeProcThreadAttributeList(0, 1u, 0, &Size);
                  v25 = Size;
                  ProcessHeap = GetProcessHeap();
                  v27 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)HeapAlloc(ProcessHeap, 0, v25);
                  v24 = v27;
                  if ( v27 )
                  {
                    if ( InitializeProcThreadAttributeList(v27, 1u, 0, &Size) )
                    {
                      v23 = 1;
                      updated = UpdateProcThreadAttribute(v24, 0, 0x20000u, &Value, 8u, 0, 0);
                      v29 = v37;
                      if ( updated )
                        v29 = v24;
                      v37 = v29;
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
              if ( v23 )
                DeleteProcThreadAttributeList(v24);
              if ( v24 )
              {
                v30 = GetProcessHeap();
                HeapFree(v30, 0, v24);
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
0x14001e0e0  mov     rax, rsp
0x14001e0e3  mov     [rax+10h], rbx
0x14001e0e7  mov     [rax+18h], rsi
0x14001e0eb  mov     [rax+8], rcx
0x14001e0ef  push    rbp
0x14001e0f0  push    r12
0x14001e0f2  push    r13
0x14001e0f4  push    r14
0x14001e0f6  push    r15
0x14001e0f8  lea     rbp, [rax-5Fh]
0x14001e0fc  sub     rsp, 0F0h
0x14001e103  mov     r12d, r8d
0x14001e106  mov     rsi, rdx
0x14001e109  mov     rcx, rdx; this
0x14001e10c  call    ?IsRunning@Accommodation@@QEAAHXZ; Accommodation::IsRunning(void)
0x14001e111  xor     r13d, r13d
0x14001e114  test    eax, eax
0x14001e116  jz      short loc_14001E11F
0x14001e118  xor     eax, eax
0x14001e11a  jmp     loc_14001E43A
0x14001e11f  mov     [rbp+57h+lpDst], r13
0x14001e123  lea     r8, [rbp+57h+lpDst]; unsigned __int64 *
0x14001e127  mov     edx, 7FFFFFFFh; unsigned __int64
0x14001e12c  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x14001e133  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001e138  test    eax, eax
0x14001e13a  js      loc_14001E435
0x14001e140  mov     rax, [rbp+57h+lpDst]
0x14001e144  lea     rbx, [rax+104h]
0x14001e14b  cmp     rbx, rax
0x14001e14e  jb      loc_14001E435
0x14001e154  mov     [rbp+57h+lpDst], r13
0x14001e158  mov     rdx, rbx
0x14001e15b  lea     rcx, [rbp+57h+lpDst]
0x14001e15f  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x14001e164  test    al, al
0x14001e166  jz      loc_14001E1EE
0x14001e16c  mov     r8d, ebx; nSize
0x14001e16f  mov     rdx, [rbp+57h+lpDst]; lpDst
0x14001e173  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x14001e17a  call    cs:__imp_ExpandEnvironmentStringsW
0x14001e180  test    eax, eax
0x14001e182  jnz     short loc_14001E1A2
0x14001e184  call    cs:__imp_GetLastError
0x14001e18a  mov     esi, eax
0x14001e18c  test    eax, eax
0x14001e18e  jle     loc_14001E2BF
0x14001e194  movzx   esi, ax
0x14001e197  or      esi, 80070000h
0x14001e19d  jmp     loc_14001E2BF
0x14001e1a2  mov     eax, eax
0x14001e1a4  cmp     rax, rbx
0x14001e1a7  jbe     short loc_14001E1B3
0x14001e1a9  mov     esi, 8007007Ah
0x14001e1ae  jmp     loc_14001E2BF
0x14001e1b3  lea     rax, [rbx+16h]
0x14001e1b7  cmp     rax, rbx
0x14001e1ba  jb      loc_14001E2BA
0x14001e1c0  lea     rbx, [rax+104h]
0x14001e1c7  cmp     rbx, rax
0x14001e1ca  jb      loc_14001E2BA
0x14001e1d0  mov     [rbp+57h+Block], r13
0x14001e1d4  mov     rdx, rbx
0x14001e1d7  lea     rcx, [rbp+57h+Block]
0x14001e1db  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x14001e1e0  test    al, al
0x14001e1e2  jnz     short loc_14001E1F8
0x14001e1e4  mov     rcx, [rbp+57h+Block]; Block
0x14001e1e8  call    cs:__imp_free
0x14001e1ee  mov     esi, 8007000Eh
0x14001e1f3  jmp     loc_14001E2BF
0x14001e1f8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates> `wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl(void)'::`2'::impl
0x14001e1ff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(void)
0x14001e204  mov     dl, [rsi+55h]
0x14001e207  lea     r8, qword_14002AAD0
0x14001e20e  lea     rcx, aLaunchnarrator; "/launchnarratorhome"
0x14001e215  mov     r9, [rbp+57h+lpDst]
0x14001e219  test    al, al
0x14001e21b  jz      short loc_14001E270
0x14001e21d  test    dl, dl
0x14001e21f  cmovz   rcx, r8
0x14001e223  lea     rax, aLaunchnarrator_0; "/launchnarratorupdates"
0x14001e22a  cmp     [rsi+56h], r13b
0x14001e22e  cmovz   rax, r8
0x14001e232  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x14001e239  cmp     [rsi+54h], r13b
0x14001e23d  cmovz   rdx, r8
0x14001e241  mov     [rsp+110h+lpCurrentDirectory], rcx
0x14001e246  mov     [rsp+110h+lpReturnSize], rax
0x14001e24b  mov     [rsp+110h+lpPreviousValue], rdx
0x14001e250  mov     rax, [rsi]
0x14001e253  mov     [rsp+110h+cbSize], rax
0x14001e258  lea     r8, aSStartSSSS; "%s /start %s %s %s %s"
0x14001e25f  mov     rdx, rbx; unsigned __int64
0x14001e262  mov     rbx, [rbp+57h+Block]
0x14001e266  mov     rcx, rbx; unsigned __int16 *
0x14001e269  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001e26e  jmp     short loc_14001E2AD
0x14001e270  test    dl, dl
0x14001e272  cmovz   rcx, r8
0x14001e276  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x14001e27d  cmp     [rsi+54h], r13b
0x14001e281  cmovz   rdx, r8
0x14001e285  mov     [rsp+110h+lpReturnSize], rcx
0x14001e28a  mov     [rsp+110h+lpPreviousValue], rdx
0x14001e28f  mov     rax, [rsi]
0x14001e292  mov     [rsp+110h+cbSize], rax
0x14001e297  lea     r8, aSStartSSS; "%s /start %s %s %s"
0x14001e29e  mov     rdx, rbx; unsigned __int64
0x14001e2a1  mov     rbx, [rbp+57h+Block]
0x14001e2a5  mov     rcx, rbx; unsigned __int16 *
0x14001e2a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001e2ad  test    eax, eax
0x14001e2af  jns     short loc_14001E2D0
0x14001e2b1  mov     rcx, rbx; Block
0x14001e2b4  call    cs:__imp_free
0x14001e2ba  mov     esi, 80004005h
0x14001e2bf  mov     rcx, [rbp+57h+lpDst]; Block
0x14001e2c3  call    cs:__imp_free
0x14001e2c9  mov     eax, esi
0x14001e2cb  jmp     loc_14001E43A
0x14001e2d0  xorps   xmm0, xmm0
0x14001e2d3  xor     eax, eax
0x14001e2d5  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x14001e2d9  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x14001e2dd  xor     edx, edx; Val
0x14001e2df  lea     r8d, [rax+6Ch]; Size
0x14001e2e3  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x14001e2e7  call    memset_0
0x14001e2ec  mov     [rbp+57h+StartupInfo.cb], 70h ; 'p'
0x14001e2f3  mov     [rbp+57h+Value], r13
0x14001e2f7  mov     r15d, r13d
0x14001e2fa  mov     r14, r13
0x14001e2fd  mov     [rbp+57h+Size], r13
0x14001e301  test    r12d, r12d
0x14001e304  jz      loc_14001E3A1
0x14001e30a  lea     rdx, [rbp+57h+Value]; void **
0x14001e30e  call    ?GetShellProcessHandle@@YAJKPEAPEAX@Z; GetShellProcessHandle(ulong,void * *)
0x14001e313  test    eax, eax
0x14001e315  js      loc_14001E3A1
0x14001e31b  lea     r9, [rbp+57h+Size]; lpSize
0x14001e31f  xor     r8d, r8d; dwFlags
0x14001e322  lea     r12d, [r8+1]
0x14001e326  mov     edx, r12d; dwAttributeCount
0x14001e329  xor     ecx, ecx; lpAttributeList
0x14001e32b  call    cs:__imp_InitializeProcThreadAttributeList
0x14001e331  mov     rsi, [rbp+57h+Size]
0x14001e335  call    cs:__imp_GetProcessHeap
0x14001e33b  mov     r8, rsi; dwBytes
0x14001e33e  xor     edx, edx; dwFlags
0x14001e340  mov     rcx, rax; hHeap
0x14001e343  call    cs:__imp_HeapAlloc
0x14001e349  mov     r14, rax
0x14001e34c  test    rax, rax
0x14001e34f  jz      short loc_14001E3A1
0x14001e351  lea     r9, [rbp+57h+Size]; lpSize
0x14001e355  xor     r8d, r8d; dwFlags
0x14001e358  mov     edx, r12d; dwAttributeCount
0x14001e35b  mov     rcx, rax; lpAttributeList
0x14001e35e  call    cs:__imp_InitializeProcThreadAttributeList
0x14001e364  test    eax, eax
0x14001e366  jz      short loc_14001E3A1
0x14001e368  mov     r15d, r12d
0x14001e36b  mov     [rsp+110h+lpReturnSize], r13; lpReturnSize
0x14001e370  mov     [rsp+110h+lpPreviousValue], r13; lpPreviousValue
0x14001e375  mov     [rsp+110h+cbSize], 8; cbSize
0x14001e37e  lea     r9, [rbp+57h+Value]; lpValue
0x14001e382  xor     edx, edx; dwFlags
0x14001e384  mov     r8d, 20000h; Attribute
0x14001e38a  mov     rcx, r14; lpAttributeList
0x14001e38d  call    cs:__imp_UpdateProcThreadAttribute
0x14001e393  mov     rcx, [rbp+57h+var_28]
0x14001e397  test    eax, eax
0x14001e399  cmovnz  rcx, r14
0x14001e39d  mov     [rbp+57h+var_28], rcx
0x14001e3a1  lea     rax, [rbp+57h+ProcessInformation]
0x14001e3a5  mov     [rsp+110h+lpProcessInformation], rax; lpProcessInformation
0x14001e3aa  lea     rax, [rbp+57h+StartupInfo]
0x14001e3ae  mov     [rsp+110h+lpStartupInfo], rax; lpStartupInfo
0x14001e3b3  mov     [rsp+110h+lpCurrentDirectory], r13; lpCurrentDirectory
0x14001e3b8  mov     [rsp+110h+lpReturnSize], r13; lpEnvironment
0x14001e3bd  mov     dword ptr [rsp+110h+lpPreviousValue], 1080000h; dwCreationFlags
0x14001e3c5  mov     dword ptr [rsp+110h+cbSize], r13d; bInheritHandles
0x14001e3ca  xor     r9d, r9d; lpThreadAttributes
0x14001e3cd  xor     r8d, r8d; lpProcessAttributes
0x14001e3d0  mov     rdx, rbx; lpCommandLine
0x14001e3d3  mov     rcx, [rbp+57h+lpDst]; lpApplicationName
0x14001e3d7  call    cs:__imp_CreateProcessW
0x14001e3dd  test    eax, eax
0x14001e3df  jz      short loc_14001E3FA
0x14001e3e1  mov     esi, r13d
0x14001e3e4  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x14001e3e8  call    cs:__imp_CloseHandle
0x14001e3ee  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x14001e3f2  call    cs:__imp_CloseHandle
0x14001e3f8  jmp     short loc_14001E3FF
0x14001e3fa  mov     esi, 80004005h
0x14001e3ff  test    r15d, r15d
0x14001e402  jz      short loc_14001E40D
0x14001e404  mov     rcx, r14; lpAttributeList
0x14001e407  call    cs:__imp_DeleteProcThreadAttributeList
0x14001e40d  test    r14, r14
0x14001e410  jz      short loc_14001E427
0x14001e412  call    cs:__imp_GetProcessHeap
0x14001e418  mov     rcx, rax; hHeap
0x14001e41b  mov     r8, r14; lpMem
0x14001e41e  xor     edx, edx; dwFlags
0x14001e420  call    cs:__imp_HeapFree
0x14001e426  nop
0x14001e427  mov     rcx, rbx; Block
0x14001e42a  call    cs:__imp_free
0x14001e430  jmp     loc_14001E2BF
0x14001e435  mov     eax, 80004005h
0x14001e43a  lea     r11, [rsp+110h+var_20]
0x14001e442  mov     rbx, [r11+38h]
0x14001e446  mov     rsi, [r11+40h]
0x14001e44a  mov     rsp, r11
0x14001e44d  pop     r15
0x14001e44f  pop     r14
0x14001e451  pop     r13
0x14001e453  pop     r12
0x14001e455  pop     rbp
0x14001e456  retn
```
