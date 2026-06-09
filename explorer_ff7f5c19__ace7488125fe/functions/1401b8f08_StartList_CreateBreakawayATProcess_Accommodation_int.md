# StartList::CreateBreakawayATProcess(Accommodation *,int)

- ea: `0x1401b8f08`
- end: `0x1401b92e6`
- name: `?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z`
- size: `990`
- prototype: `int(StartList *__hidden this, struct Accommodation *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1401ba634`

## callees

- `0x140020580`
- `0x14008a0b8`
- `0x14010ed90`
- `0x1401b7b20`
- `0x1401b83a8`
- `0x1401b8bcc`
- `0x1401b8f08`
- `0x1401b9520`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401b901c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401b90ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401b9103`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401b92b2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401b901c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401b90ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401b9103`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1401b92b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1401b9195`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1401b9195`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1401b9181`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1401b928e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1401b9181`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1401b928e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1401b92a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1401b92a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b8fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401b8fb2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1401b923b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1401b923b`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1401b927d`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1401b927d`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1401b91eb`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1401b91eb`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1401b9171`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1401b91b6`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1401b9171`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1401b91b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b9252`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b9262`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b9252`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b9262`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1401b8fa2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1401b8fa2`

## string_xrefs

- `0x1401b905d`: `/launchnarratorupdates`
- `0x1401b8f54`: `%SystemRoot%\System32\ATBroker.exe`
- `0x1401b8f9b`: `%SystemRoot%\System32\ATBroker.exe`

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
0x1401b8f08  mov     rax, rsp
0x1401b8f0b  mov     [rax+10h], rbx
0x1401b8f0f  mov     [rax+18h], rsi
0x1401b8f13  mov     [rax+8], rcx
0x1401b8f17  push    rbp
0x1401b8f18  push    r12
0x1401b8f1a  push    r13
0x1401b8f1c  push    r14
0x1401b8f1e  push    r15
0x1401b8f20  lea     rbp, [rax-5Fh]
0x1401b8f24  sub     rsp, 0F0h
0x1401b8f2b  mov     r12d, r8d
0x1401b8f2e  mov     rsi, rdx
0x1401b8f31  mov     rcx, rdx; this
0x1401b8f34  call    ?IsRunning@Accommodation@@QEAAHXZ; Accommodation::IsRunning(void)
0x1401b8f39  xor     r13d, r13d
0x1401b8f3c  test    eax, eax
0x1401b8f3e  jz      short loc_1401B8F47
0x1401b8f40  xor     eax, eax
0x1401b8f42  jmp     loc_1401B92C8
0x1401b8f47  mov     [rbp+57h+lpDst], r13
0x1401b8f4b  lea     r8, [rbp+57h+lpDst]; unsigned __int64 *
0x1401b8f4f  mov     edx, 7FFFFFFFh; unsigned __int64
0x1401b8f54  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x1401b8f5b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1401b8f60  test    eax, eax
0x1401b8f62  js      loc_1401B92C3
0x1401b8f68  mov     rax, [rbp+57h+lpDst]
0x1401b8f6c  lea     rbx, [rax+104h]
0x1401b8f73  cmp     rbx, rax
0x1401b8f76  jb      loc_1401B92C3
0x1401b8f7c  mov     [rbp+57h+lpDst], r13
0x1401b8f80  mov     rdx, rbx
0x1401b8f83  lea     rcx, [rbp+57h+lpDst]
0x1401b8f87  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x1401b8f8c  test    al, al
0x1401b8f8e  jz      loc_1401B9028
0x1401b8f94  mov     r8d, ebx; nSize
0x1401b8f97  mov     rdx, [rbp+57h+lpDst]; lpDst
0x1401b8f9b  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x1401b8fa2  call    cs:__imp_ExpandEnvironmentStringsW
0x1401b8fa9  nop     dword ptr [rax+rax+00h]
0x1401b8fae  test    eax, eax
0x1401b8fb0  jnz     short loc_1401B8FD6
0x1401b8fb2  call    cs:__imp_GetLastError
0x1401b8fb9  nop     dword ptr [rax+rax+00h]
0x1401b8fbe  mov     esi, eax
0x1401b8fc0  test    eax, eax
0x1401b8fc2  jle     loc_1401B90FF
0x1401b8fc8  movzx   esi, ax
0x1401b8fcb  or      esi, 80070000h
0x1401b8fd1  jmp     loc_1401B90FF
0x1401b8fd6  mov     eax, eax
0x1401b8fd8  cmp     rax, rbx
0x1401b8fdb  jbe     short loc_1401B8FE7
0x1401b8fdd  mov     esi, 8007007Ah
0x1401b8fe2  jmp     loc_1401B90FF
0x1401b8fe7  lea     rax, [rbx+16h]
0x1401b8feb  cmp     rax, rbx
0x1401b8fee  jb      loc_1401B90FA
0x1401b8ff4  lea     rbx, [rax+104h]
0x1401b8ffb  cmp     rbx, rax
0x1401b8ffe  jb      loc_1401B90FA
0x1401b9004  mov     [rbp+57h+Block], r13
0x1401b9008  mov     rdx, rbx
0x1401b900b  lea     rcx, [rbp+57h+Block]
0x1401b900f  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x1401b9014  test    al, al
0x1401b9016  jnz     short loc_1401B9032
0x1401b9018  mov     rcx, [rbp+57h+Block]; Block
0x1401b901c  call    cs:__imp_free
0x1401b9023  nop     dword ptr [rax+rax+00h]
0x1401b9028  mov     esi, 8007000Eh
0x1401b902d  jmp     loc_1401B90FF
0x1401b9032  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates> `wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl(void)'::`2'::impl
0x1401b9039  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(void)
0x1401b903e  mov     dl, [rsi+55h]
0x1401b9041  lea     r8, Class
0x1401b9048  lea     rcx, aLaunchnarrator; "/launchnarratorhome"
0x1401b904f  mov     r9, [rbp+57h+lpDst]
0x1401b9053  test    al, al
0x1401b9055  jz      short loc_1401B90AA
0x1401b9057  test    dl, dl
0x1401b9059  cmovz   rcx, r8
0x1401b905d  lea     rax, aLaunchnarrator_0; "/launchnarratorupdates"
0x1401b9064  cmp     [rsi+56h], r13b
0x1401b9068  cmovz   rax, r8
0x1401b906c  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x1401b9073  cmp     [rsi+54h], r13b
0x1401b9077  cmovz   rdx, r8
0x1401b907b  mov     [rsp+110h+lpCurrentDirectory], rcx
0x1401b9080  mov     [rsp+110h+lpReturnSize], rax
0x1401b9085  mov     [rsp+110h+lpPreviousValue], rdx
0x1401b908a  mov     rax, [rsi]
0x1401b908d  mov     [rsp+110h+cbSize], rax
0x1401b9092  lea     r8, aSStartSSSS; "%s /start %s %s %s %s"
0x1401b9099  mov     rdx, rbx; unsigned __int64
0x1401b909c  mov     rbx, [rbp+57h+Block]
0x1401b90a0  mov     rcx, rbx; unsigned __int16 *
0x1401b90a3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401b90a8  jmp     short loc_1401B90E7
0x1401b90aa  test    dl, dl
0x1401b90ac  cmovz   rcx, r8
0x1401b90b0  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x1401b90b7  cmp     [rsi+54h], r13b
0x1401b90bb  cmovz   rdx, r8
0x1401b90bf  mov     [rsp+110h+lpReturnSize], rcx
0x1401b90c4  mov     [rsp+110h+lpPreviousValue], rdx
0x1401b90c9  mov     rax, [rsi]
0x1401b90cc  mov     [rsp+110h+cbSize], rax
0x1401b90d1  lea     r8, aSStartSSS; "%s /start %s %s %s"
0x1401b90d8  mov     rdx, rbx; unsigned __int64
0x1401b90db  mov     rbx, [rbp+57h+Block]
0x1401b90df  mov     rcx, rbx; unsigned __int16 *
0x1401b90e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401b90e7  test    eax, eax
0x1401b90e9  jns     short loc_1401B9116
0x1401b90eb  mov     rcx, rbx; Block
0x1401b90ee  call    cs:__imp_free
0x1401b90f5  nop     dword ptr [rax+rax+00h]
0x1401b90fa  mov     esi, 80004005h
0x1401b90ff  mov     rcx, [rbp+57h+lpDst]; Block
0x1401b9103  call    cs:__imp_free
0x1401b910a  nop     dword ptr [rax+rax+00h]
0x1401b910f  mov     eax, esi
0x1401b9111  jmp     loc_1401B92C8
0x1401b9116  xorps   xmm0, xmm0
0x1401b9119  xor     eax, eax
0x1401b911b  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x1401b911f  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x1401b9123  xor     edx, edx; Val
0x1401b9125  lea     r8d, [rax+6Ch]; Size
0x1401b9129  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x1401b912d  call    memset_0
0x1401b9132  mov     [rbp+57h+StartupInfo.cb], 70h ; 'p'
0x1401b9139  mov     [rbp+57h+Value], r13
0x1401b913d  mov     r15d, r13d
0x1401b9140  mov     r14, r13
0x1401b9143  mov     [rbp+57h+Size], r13
0x1401b9147  test    r12d, r12d
0x1401b914a  jz      loc_1401B9205
0x1401b9150  lea     rdx, [rbp+57h+Value]; void **
0x1401b9154  call    ?GetShellProcessHandle@@YAJKPEAPEAX@Z; GetShellProcessHandle(ulong,void * *)
0x1401b9159  test    eax, eax
0x1401b915b  js      loc_1401B9205
0x1401b9161  lea     r9, [rbp+57h+Size]; lpSize
0x1401b9165  xor     r8d, r8d; dwFlags
0x1401b9168  lea     r12d, [r8+1]
0x1401b916c  mov     edx, r12d; dwAttributeCount
0x1401b916f  xor     ecx, ecx; lpAttributeList
0x1401b9171  call    cs:__imp_InitializeProcThreadAttributeList
0x1401b9178  nop     dword ptr [rax+rax+00h]
0x1401b917d  mov     rsi, [rbp+57h+Size]
0x1401b9181  call    cs:__imp_GetProcessHeap
0x1401b9188  nop     dword ptr [rax+rax+00h]
0x1401b918d  mov     r8, rsi; dwBytes
0x1401b9190  xor     edx, edx; dwFlags
0x1401b9192  mov     rcx, rax; hHeap
0x1401b9195  call    cs:__imp_HeapAlloc
0x1401b919c  nop     dword ptr [rax+rax+00h]
0x1401b91a1  mov     r14, rax
0x1401b91a4  test    rax, rax
0x1401b91a7  jz      short loc_1401B9205
0x1401b91a9  lea     r9, [rbp+57h+Size]; lpSize
0x1401b91ad  xor     r8d, r8d; dwFlags
0x1401b91b0  mov     edx, r12d; dwAttributeCount
0x1401b91b3  mov     rcx, rax; lpAttributeList
0x1401b91b6  call    cs:__imp_InitializeProcThreadAttributeList
0x1401b91bd  nop     dword ptr [rax+rax+00h]
0x1401b91c2  test    eax, eax
0x1401b91c4  jz      short loc_1401B9205
0x1401b91c6  mov     r15d, r12d
0x1401b91c9  mov     [rsp+110h+lpReturnSize], r13; lpReturnSize
0x1401b91ce  mov     [rsp+110h+lpPreviousValue], r13; lpPreviousValue
0x1401b91d3  mov     [rsp+110h+cbSize], 8; cbSize
0x1401b91dc  lea     r9, [rbp+57h+Value]; lpValue
0x1401b91e0  xor     edx, edx; dwFlags
0x1401b91e2  mov     r8d, 20000h; Attribute
0x1401b91e8  mov     rcx, r14; lpAttributeList
0x1401b91eb  call    cs:__imp_UpdateProcThreadAttribute
0x1401b91f2  nop     dword ptr [rax+rax+00h]
0x1401b91f7  mov     rcx, [rbp+57h+var_28]
0x1401b91fb  test    eax, eax
0x1401b91fd  cmovnz  rcx, r14
0x1401b9201  mov     [rbp+57h+var_28], rcx
0x1401b9205  lea     rax, [rbp+57h+ProcessInformation]
0x1401b9209  mov     [rsp+110h+lpProcessInformation], rax; lpProcessInformation
0x1401b920e  lea     rax, [rbp+57h+StartupInfo]
0x1401b9212  mov     [rsp+110h+lpStartupInfo], rax; lpStartupInfo
0x1401b9217  mov     [rsp+110h+lpCurrentDirectory], r13; lpCurrentDirectory
0x1401b921c  mov     [rsp+110h+lpReturnSize], r13; lpEnvironment
0x1401b9221  mov     dword ptr [rsp+110h+lpPreviousValue], 1080000h; dwCreationFlags
0x1401b9229  mov     dword ptr [rsp+110h+cbSize], r13d; bInheritHandles
0x1401b922e  xor     r9d, r9d; lpThreadAttributes
0x1401b9231  xor     r8d, r8d; lpProcessAttributes
0x1401b9234  mov     rdx, rbx; lpCommandLine
0x1401b9237  mov     rcx, [rbp+57h+lpDst]; lpApplicationName
0x1401b923b  call    cs:__imp_CreateProcessW
0x1401b9242  nop     dword ptr [rax+rax+00h]
0x1401b9247  test    eax, eax
0x1401b9249  jz      short loc_1401B9270
0x1401b924b  mov     esi, r13d
0x1401b924e  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x1401b9252  call    cs:__imp_CloseHandle
0x1401b9259  nop     dword ptr [rax+rax+00h]
0x1401b925e  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x1401b9262  call    cs:__imp_CloseHandle
0x1401b9269  nop     dword ptr [rax+rax+00h]
0x1401b926e  jmp     short loc_1401B9275
0x1401b9270  mov     esi, 80004005h
0x1401b9275  test    r15d, r15d
0x1401b9278  jz      short loc_1401B9289
0x1401b927a  mov     rcx, r14; lpAttributeList
0x1401b927d  call    cs:__imp_DeleteProcThreadAttributeList
0x1401b9284  nop     dword ptr [rax+rax+00h]
0x1401b9289  test    r14, r14
0x1401b928c  jz      short loc_1401B92AF
0x1401b928e  call    cs:__imp_GetProcessHeap
0x1401b9295  nop     dword ptr [rax+rax+00h]
0x1401b929a  mov     rcx, rax; hHeap
0x1401b929d  mov     r8, r14; lpMem
0x1401b92a0  xor     edx, edx; dwFlags
0x1401b92a2  call    cs:__imp_HeapFree
0x1401b92a9  nop     dword ptr [rax+rax+00h]
0x1401b92ae  nop
0x1401b92af  mov     rcx, rbx; Block
0x1401b92b2  call    cs:__imp_free
0x1401b92b9  nop     dword ptr [rax+rax+00h]
0x1401b92be  jmp     loc_1401B90FF
0x1401b92c3  mov     eax, 80004005h
0x1401b92c8  lea     r11, [rsp+110h+var_20]
0x1401b92d0  mov     rbx, [r11+38h]
0x1401b92d4  mov     rsi, [r11+40h]
0x1401b92d8  mov     rsp, r11
0x1401b92db  pop     r15
0x1401b92dd  pop     r14
0x1401b92df  pop     r13
0x1401b92e1  pop     r12
0x1401b92e3  pop     rbp
0x1401b92e4  retn
```
