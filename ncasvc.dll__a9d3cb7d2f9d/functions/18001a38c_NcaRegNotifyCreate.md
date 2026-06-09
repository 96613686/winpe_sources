# NcaRegNotifyCreate

- ea: `0x18001a38c`
- end: `0x18001a55e`
- name: `NcaRegNotifyCreate`
- size: `466`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x180014b80`

## callees

- `0x1800033bc`
- `0x180018fd4`
- `0x1800199b4`
- `0x180019c70`
- `0x180019dac`
- `0x18001a38c`
- `0x18001a564`
- `0x18001abd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a513`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a513`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001a501`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001a501`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a45e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a4b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a45e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a4b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4d9`
- `KERNEL32!RegisterWaitForSingleObject` at `0x18001a493`
- `KERNEL32!RegisterWaitForSingleObject` at `0x18001a493`

## string_xrefs

- `0x18001a4cb`: `CreateEventW`
- `0x18001a3ba`: `SYSTEM\CurrentControlSet\Services\iphlpsvc\Parameters\IPHTTPS\IPHTTPSInterface`
- `0x18001a40c`: `SYSTEM\CurrentControlSet\Services\iphlpsvc\Parameters\IPHTTPS\IPHTTPSInterface`
- `0x18001a3ee`: `NcaRegNotifyCreate`
- `0x18001a4d2`: `NcaRegNotifyCreate`
- `0x18001a539`: `NcaRegNotifyCreate`

## pseudocode

```c
__int64 __fastcall NcaRegNotifyCreate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8)
{
  DWORD LastError; // ebp
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  const char *v11; // rsi
  int v12; // eax
  int v13; // esi
  __int64 v14; // rdx
  HANDLE EventW; // rax
  HANDLE v16; // rax

  LastError = 8;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      WPP_149084e4aca63d179354f111bb13106e_Traceguids,
      L"SYSTEM\\CurrentControlSet\\Services\\iphlpsvc\\Parameters\\IPHTTPS\\IPHTTPSInterface");
  *a8 = 0;
  v9 = NcaAlloc(0x60u);
  v10 = v9;
  if ( !v9 )
  {
    v11 = "NcaAlloc";
    goto LABEL_14;
  }
  *v9 = -2147483646;
  v12 = NcaStringCopy((void *)L"SYSTEM\\CurrentControlSet\\Services\\iphlpsvc\\Parameters\\IPHTTPS\\IPHTTPSInterface");
  v13 = v12;
  if ( v12 < 0 )
  {
    v14 = (unsigned int)v12;
LABEL_18:
    NcaReportReturnError("NcaRegNotifyCreate", v14);
LABEL_19:
    NcaRegNotifyDestroy(v10);
    return (unsigned int)v13;
  }
  *((_DWORD *)v10 + 4) = 1;
  v10[4] = NcaEvCollIphttpsCertChanged;
  *((_DWORD *)v10 + 5) = 4;
  *((_DWORD *)v10 + 7) = 0;
  v10[5] = 0;
  *((_DWORD *)v10 + 18) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v10[7] = EventW;
  if ( !EventW )
    goto LABEL_12;
  if ( RegisterWaitForSingleObject((PHANDLE)v10 + 8, EventW, NcaRegNotifyOnChange, v10, 0xFFFFFFFF, 0x80u) )
  {
    v16 = CreateEventW(0, 0, 0, 0);
    v10[10] = v16;
    if ( v16 )
    {
      SetEvent((HANDLE)v10[7]);
      WaitForSingleObject((HANDLE)v10[10], 0xFFFFFFFF);
      NcaCloseHandle((char *)v10[10]);
      v13 = *((_DWORD *)v10 + 22);
      v10[10] = 0;
      if ( v13 >= 0 )
      {
        *a8 = v10;
        return (unsigned int)v13;
      }
      v14 = (unsigned int)v13;
      goto LABEL_18;
    }
LABEL_12:
    v11 = "CreateEventW";
    goto LABEL_13;
  }
  v11 = "RegisterWaitForSingleObject";
LABEL_13:
  LastError = GetLastError();
LABEL_14:
  v13 = NcaReportErrorAsWinError("NcaRegNotifyCreate", v11, LastError);
  if ( v13 < 0 )
    goto LABEL_19;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001a38c  push    rbx
0x18001a38e  push    rbp
0x18001a38f  push    rsi
0x18001a390  push    rdi
0x18001a391  sub     rsp, 38h
0x18001a395  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a39c  lea     rax, WPP_GLOBAL_Control
0x18001a3a3  mov     ebp, 8
0x18001a3a8  cmp     rcx, rax
0x18001a3ab  jz      short loc_18001A3CD
0x18001a3ad  test    [rcx+1Ch], bpl
0x18001a3b1  jz      short loc_18001A3CD
0x18001a3b3  mov     rcx, [rcx+10h]
0x18001a3b7  lea     edx, [rbp+11h]
0x18001a3ba  lea     r9, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\ip"...
0x18001a3c1  lea     r8, WPP_149084e4aca63d179354f111bb13106e_Traceguids
0x18001a3c8  call    WPP_SF_S
0x18001a3cd  mov     rbx, [rsp+58h+arg_38]
0x18001a3d5  mov     ecx, 60h ; '`'
0x18001a3da  mov     qword ptr [rbx], 0
0x18001a3e1  call    NcaAlloc
0x18001a3e6  mov     rdi, rax
0x18001a3e9  test    rax, rax
0x18001a3ec  jnz     short loc_18001A401
0x18001a3ee  lea     rbx, aNcaregnotifycr; "NcaRegNotifyCreate"
0x18001a3f5  lea     rsi, aNcaalloc; "NcaAlloc"
0x18001a3fc  jmp     loc_18001A4E7
0x18001a401  lea     rdx, [rax+8]
0x18001a405  mov     qword ptr [rax], 0FFFFFFFF80000002h
0x18001a40c  lea     rcx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\ip"...
0x18001a413  call    NcaStringCopy
0x18001a418  mov     esi, eax
0x18001a41a  test    eax, eax
0x18001a41c  jns     short loc_18001A425
0x18001a41e  mov     edx, eax
0x18001a420  jmp     loc_18001A539
0x18001a425  lea     rax, ?NcaEvCollIphttpsCertChanged@@YAXPEAXJ@Z; NcaEvCollIphttpsCertChanged(void *,long)
0x18001a42c  mov     dword ptr [rdi+10h], 1
0x18001a433  xor     r9d, r9d; lpName
0x18001a436  mov     [rdi+20h], rax
0x18001a43a  xor     r8d, r8d; bInitialState
0x18001a43d  mov     dword ptr [rdi+14h], 4
0x18001a444  xor     edx, edx; bManualReset
0x18001a446  mov     dword ptr [rdi+1Ch], 0
0x18001a44d  xor     ecx, ecx; lpEventAttributes
0x18001a44f  mov     qword ptr [rdi+28h], 0
0x18001a457  mov     dword ptr [rdi+48h], 0
0x18001a45e  call    cs:__imp_CreateEventW
0x18001a465  nop     dword ptr [rax+rax+00h]
0x18001a46a  mov     [rdi+38h], rax
0x18001a46e  test    rax, rax
0x18001a471  jz      short loc_18001A4CB
0x18001a473  or      esi, 0FFFFFFFFh
0x18001a476  mov     [rsp+58h+dwFlags], 80h; dwFlags
0x18001a47e  lea     rcx, [rdi+40h]; phNewWaitObject
0x18001a482  mov     [rsp+58h+dwMilliseconds], esi; dwMilliseconds
0x18001a486  mov     r9, rdi; Context
0x18001a489  lea     r8, NcaRegNotifyOnChange; Callback
0x18001a490  mov     rdx, rax; hObject
0x18001a493  call    cs:__imp_RegisterWaitForSingleObject
0x18001a49a  nop     dword ptr [rax+rax+00h]
0x18001a49f  test    eax, eax
0x18001a4a1  jnz     short loc_18001A4AC
0x18001a4a3  lea     rsi, aRegisterwaitfo; "RegisterWaitForSingleObject"
0x18001a4aa  jmp     short loc_18001A4D2
0x18001a4ac  xor     r9d, r9d; lpName
0x18001a4af  xor     r8d, r8d; bInitialState
0x18001a4b2  xor     edx, edx; bManualReset
0x18001a4b4  xor     ecx, ecx; lpEventAttributes
0x18001a4b6  call    cs:__imp_CreateEventW
0x18001a4bd  nop     dword ptr [rax+rax+00h]
0x18001a4c2  mov     [rdi+50h], rax
0x18001a4c6  test    rax, rax
0x18001a4c9  jnz     short loc_18001A4FD
0x18001a4cb  lea     rsi, aCreateeventw; "CreateEventW"
0x18001a4d2  lea     rbx, aNcaregnotifycr; "NcaRegNotifyCreate"
0x18001a4d9  call    cs:__imp_GetLastError
0x18001a4e0  nop     dword ptr [rax+rax+00h]
0x18001a4e5  mov     ebp, eax
0x18001a4e7  mov     r8d, ebp
0x18001a4ea  mov     rdx, rsi
0x18001a4ed  mov     rcx, rbx
0x18001a4f0  call    NcaReportErrorAsWinError
0x18001a4f5  mov     esi, eax
0x18001a4f7  test    eax, eax
0x18001a4f9  jns     short loc_18001A552
0x18001a4fb  jmp     short loc_18001A545
0x18001a4fd  mov     rcx, [rdi+38h]; hEvent
0x18001a501  call    cs:__imp_SetEvent
0x18001a508  nop     dword ptr [rax+rax+00h]
0x18001a50d  mov     rcx, [rdi+50h]; hHandle
0x18001a511  mov     edx, esi; dwMilliseconds
0x18001a513  call    cs:__imp_WaitForSingleObject
0x18001a51a  nop     dword ptr [rax+rax+00h]
0x18001a51f  mov     rcx, [rdi+50h]
0x18001a523  call    NcaCloseHandle
0x18001a528  mov     esi, [rdi+58h]
0x18001a52b  mov     qword ptr [rdi+50h], 0
0x18001a533  test    esi, esi
0x18001a535  jns     short loc_18001A54F
0x18001a537  mov     edx, esi
0x18001a539  lea     rcx, aNcaregnotifycr; "NcaRegNotifyCreate"
0x18001a540  call    NcaReportReturnError
0x18001a545  mov     rcx, rdi; lpMem
0x18001a548  call    NcaRegNotifyDestroy
0x18001a54d  jmp     short loc_18001A552
0x18001a54f  mov     [rbx], rdi
0x18001a552  mov     eax, esi
0x18001a554  add     rsp, 38h
0x18001a558  pop     rdi
0x18001a559  pop     rsi
0x18001a55a  pop     rbp
0x18001a55b  pop     rbx
0x18001a55c  retn
```
