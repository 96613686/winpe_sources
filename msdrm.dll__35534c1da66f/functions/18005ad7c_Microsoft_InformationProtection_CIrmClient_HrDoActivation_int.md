# Microsoft::InformationProtection::CIrmClient::HrDoActivation(int)

- ea: `0x18005ad7c`
- end: `0x18005af20`
- name: `?HrDoActivation@CIrmClient@InformationProtection@Microsoft@@AEAAJH@Z`
- size: `420`
- prototype: `__int64 __fastcall(Microsoft::InformationProtection::CIrmClient *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005b0a0`

## callees

- `0x18001ad10`
- `0x18005a9cc`
- `0x18005aadc`
- `0x18005ad7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ae98`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ae98`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005ae0d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005ae0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ae1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ae1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005aec0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005aec0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005adcd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005adcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005adbb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005aece`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005aee9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005adbb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005aece`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005aee9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005aedc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005aef7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005aedc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005aef7`

## pseudocode

```c
__int64 __fastcall Microsoft::InformationProtection::CIrmClient::HrDoActivation(
        Microsoft::InformationProtection::CIrmClient *this)
{
  HANDLE ProcessHeap; // rax
  DRM_ACTSERV_INFO *v4; // rax
  unsigned __int16 **v5; // r9
  DRM_ACTSERV_INFO *v6; // rsi
  signed int ServiceLocation; // ebx
  void **p_wszURL; // r14
  char *EventW; // rax
  char *v10; // rdi
  signed int LastError; // eax
  HRESULT v12; // eax
  void *v13; // rdi
  HANDLE v14; // rax
  HANDLE v15; // rax
  __int128 pvContext; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+40h] [rbp-38h]

  Microsoft::InformationProtection::DebugLog(
    (Microsoft::InformationProtection *)L"%S Entered",
    "Microsoft::InformationProtection::CIrmClient::HrDoActivation");
  pvContext = 0;
  v17 = 0;
  if ( !*((_DWORD *)this + 4) )
    return 2147549183LL;
  ProcessHeap = GetProcessHeap();
  v4 = (DRM_ACTSERV_INFO *)HeapAlloc(ProcessHeap, 8u, 0x18u);
  v6 = v4;
  if ( v4 )
  {
    p_wszURL = (void **)&v4->wszURL;
    ServiceLocation = Microsoft::InformationProtection::HrFindServiceLocation(
                        *((_DWORD *)this + 4),
                        2u,
                        (int)v4 + 16,
                        v5);
    if ( ServiceLocation >= 0 )
    {
      EventW = (char *)CreateEventW(0, 0, 0, 0);
      v10 = EventW;
      if ( EventW )
      {
        *(_QWORD *)&pvContext = 0;
        *((_QWORD *)&pvContext + 1) = EventW;
      }
      else
      {
        LastError = GetLastError();
        ServiceLocation = LastError;
        if ( LastError > 0 )
          ServiceLocation = (unsigned __int16)LastError | 0x80070000;
        if ( ServiceLocation < 0 )
          goto LABEL_20;
      }
      v12 = DRMActivate(*((_DWORD *)this + 4), 0x12u, 0, v6, &pvContext, 0);
      ServiceLocation = v12;
      if ( v12 >= 0 )
      {
        if ( WaitForSingleObject(v10, 0xEA60u) )
        {
          ServiceLocation = -2147467259;
        }
        else if ( (int)v17 < 0 )
        {
          ServiceLocation = v17;
        }
      }
      else
      {
        Microsoft::InformationProtection::DebugLog(
          (Microsoft::InformationProtection *)L"%S FAILED at Line %d with hr = 0x%x",
          "Microsoft::InformationProtection::CIrmClient::HrDoActivation",
          352,
          (unsigned int)v12);
      }
      if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v10);
    }
LABEL_20:
    v13 = *p_wszURL;
    if ( *p_wszURL )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v13);
      *p_wszURL = 0;
    }
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v6);
    goto LABEL_23;
  }
  ServiceLocation = -2147024882;
LABEL_23:
  Microsoft::InformationProtection::DebugLog(
    (Microsoft::InformationProtection *)L"%S Exited with hr = 0x%x",
    "Microsoft::InformationProtection::CIrmClient::HrDoActivation",
    (unsigned int)ServiceLocation);
  return (unsigned int)ServiceLocation;
}

```

## disassembly

```asm
0x18005ad7c  push    rbx
0x18005ad7e  push    rbp
0x18005ad7f  push    rsi
0x18005ad80  push    rdi
0x18005ad81  push    r14
0x18005ad83  sub     rsp, 50h
0x18005ad87  mov     rbp, rcx
0x18005ad8a  lea     rdx, aMicrosoftInfor_31; "Microsoft::InformationProtection::CIrmC"...
0x18005ad91  lea     rcx, aSEntered; "%S Entered"
0x18005ad98  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005ad9d  xor     eax, eax
0x18005ad9f  xorps   xmm0, xmm0
0x18005ada2  movups  [rsp+78h+var_48], xmm0
0x18005ada7  mov     [rsp+78h+var_38], rax
0x18005adac  cmp     [rbp+10h], eax
0x18005adaf  jnz     short loc_18005ADBB
0x18005adb1  mov     eax, 8000FFFFh
0x18005adb6  jmp     loc_18005AF15
0x18005adbb  call    cs:__imp_GetProcessHeap
0x18005adc1  mov     edx, 8; dwFlags
0x18005adc6  mov     rcx, rax; hHeap
0x18005adc9  lea     r8d, [rdx+10h]; dwBytes
0x18005adcd  call    cs:__imp_HeapAlloc
0x18005add3  mov     rsi, rax
0x18005add6  test    rax, rax
0x18005add9  jnz     short loc_18005ADE5
0x18005addb  mov     ebx, 8007000Eh
0x18005ade0  jmp     loc_18005AEFD
0x18005ade5  mov     ecx, [rbp+10h]; hClient
0x18005ade8  lea     r14, [rax+10h]
0x18005adec  mov     r8, r14; unsigned int
0x18005adef  mov     edx, 2; uServiceType
0x18005adf4  call    ?HrFindServiceLocation@InformationProtection@Microsoft@@YAJKIPEAPEAG@Z; Microsoft::InformationProtection::HrFindServiceLocation(ulong,uint,ushort * *)
0x18005adf9  mov     ebx, eax
0x18005adfb  test    eax, eax
0x18005adfd  js      loc_18005AEC6
0x18005ae03  xor     r9d, r9d; lpName
0x18005ae06  xor     r8d, r8d; bInitialState
0x18005ae09  xor     edx, edx; bManualReset
0x18005ae0b  xor     ecx, ecx; lpEventAttributes
0x18005ae0d  call    cs:__imp_CreateEventW
0x18005ae13  mov     rdi, rax
0x18005ae16  test    rax, rax
0x18005ae19  jnz     short loc_18005AE39
0x18005ae1b  call    cs:__imp_GetLastError
0x18005ae21  mov     ebx, eax
0x18005ae23  test    eax, eax
0x18005ae25  jle     short loc_18005AE30
0x18005ae27  movzx   ebx, ax
0x18005ae2a  or      ebx, 80070000h
0x18005ae30  test    ebx, ebx
0x18005ae32  jns     short loc_18005AE47
0x18005ae34  jmp     loc_18005AEC6
0x18005ae39  mov     qword ptr [rsp+78h+var_48], 0
0x18005ae42  mov     qword ptr [rsp+78h+var_48+8], rdi
0x18005ae47  mov     ecx, [rbp+10h]; hClient
0x18005ae4a  lea     rax, [rsp+78h+var_48]
0x18005ae4f  xor     r8d, r8d; uLangID
0x18005ae52  mov     [rsp+78h+hParentWnd], 0; hParentWnd
0x18005ae5b  mov     r9, rsi; pActServInfo
0x18005ae5e  mov     [rsp+78h+pvContext], rax; pvContext
0x18005ae63  lea     edx, [r8+12h]; uFlags
0x18005ae67  call    DRMActivate
0x18005ae6c  mov     ebx, eax
0x18005ae6e  test    eax, eax
0x18005ae70  jns     short loc_18005AE90
0x18005ae72  mov     r9d, eax
0x18005ae75  lea     rdx, aMicrosoftInfor_31; "Microsoft::InformationProtection::CIrmC"...
0x18005ae7c  mov     r8d, 160h
0x18005ae82  lea     rcx, aSFailedAtLineD; "%S FAILED at Line %d with hr = 0x%x"
0x18005ae89  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005ae8e  jmp     short loc_18005AEB3
0x18005ae90  mov     edx, 0EA60h; dwMilliseconds
0x18005ae95  mov     rcx, rdi; hHandle
0x18005ae98  call    cs:__imp_WaitForSingleObject
0x18005ae9e  test    eax, eax
0x18005aea0  jz      short loc_18005AEA9
0x18005aea2  mov     ebx, 80004005h
0x18005aea7  jmp     short loc_18005AEB3
0x18005aea9  mov     rax, [rsp+78h+var_38]
0x18005aeae  test    eax, eax
0x18005aeb0  cmovs   ebx, eax
0x18005aeb3  lea     rax, [rdi-1]
0x18005aeb7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005aebb  ja      short loc_18005AEC6
0x18005aebd  mov     rcx, rdi; hObject
0x18005aec0  call    cs:__imp_CloseHandle
0x18005aec6  mov     rdi, [r14]
0x18005aec9  test    rdi, rdi
0x18005aecc  jz      short loc_18005AEE9
0x18005aece  call    cs:__imp_GetProcessHeap
0x18005aed4  mov     r8, rdi; lpMem
0x18005aed7  xor     edx, edx; dwFlags
0x18005aed9  mov     rcx, rax; hHeap
0x18005aedc  call    cs:__imp_HeapFree
0x18005aee2  mov     qword ptr [r14], 0
0x18005aee9  call    cs:__imp_GetProcessHeap
0x18005aeef  mov     r8, rsi; lpMem
0x18005aef2  xor     edx, edx; dwFlags
0x18005aef4  mov     rcx, rax; hHeap
0x18005aef7  call    cs:__imp_HeapFree
0x18005aefd  mov     r8d, ebx
0x18005af00  lea     rdx, aMicrosoftInfor_31; "Microsoft::InformationProtection::CIrmC"...
0x18005af07  lea     rcx, aSExitedWithHr0; "%S Exited with hr = 0x%x"
0x18005af0e  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005af13  mov     eax, ebx
0x18005af15  add     rsp, 50h
0x18005af19  pop     r14
0x18005af1b  pop     rdi
0x18005af1c  pop     rsi
0x18005af1d  pop     rbp
0x18005af1e  pop     rbx
0x18005af1f  retn
```
