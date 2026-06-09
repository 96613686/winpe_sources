# ConnectHECI(void * *)

- ea: `0x1801451c0`
- end: `0x180145467`
- name: `?ConnectHECI@@YAJPEAPEAX@Z`
- size: `679`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180145470`
- `0x180145948`
- `0x180145dcc`
- `0x1801460c8`
- `0x180146ba8`

## callees

- `0x180019080`
- `0x180019fe8`
- `0x180019ff4`
- `0x1800e439c`
- `0x1800ed44c`
- `0x1800ed46c`
- `0x1800f9d84`
- `0x180145168`
- `0x180145194`
- `0x1801451c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18014540c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18014540c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014532a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014532a`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180145230`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180145230`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1801452e7`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1801452e7`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18014531a`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18014536b`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18014531a`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18014536b`
- `DEVOBJ!DevObjGetClassDevs` at `0x18014526d`
- `DEVOBJ!DevObjGetClassDevs` at `0x18014526d`

## pseudocode

```c
__int64 __fastcall ConnectHECI(void **a1)
{
  __int64 v2; // rdx
  unsigned int LastError; // ebx
  __int64 DeviceInfoList; // rax
  const char *v5; // r9
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rax
  unsigned int i; // esi
  const char *v10; // r9
  _DWORD *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  HANDLE FileW; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-39h]
  size_t *dwCreationDispositiona; // [rsp+20h] [rbp-39h]
  size_t Size; // [rsp+40h] [rbp-19h] BYREF
  void *Block; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v20[16]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v21; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v22[8]; // [rsp+68h] [rbp+Fh] BYREF
  _OWORD v23[2]; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( a1 )
  {
    if ( *a1 )
    {
      v2 = 607;
      goto LABEL_3;
    }
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    v21 = DeviceInfoList;
    v6 = DeviceInfoList;
    if ( DeviceInfoList == -1 )
    {
      v7 = 610;
    }
    else
    {
      if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_HECI, 0, 18, 0, 0) )
      {
        Block = 0;
        memset(v23, 0, sizeof(v23));
        LODWORD(v23[0]) = 32;
        v8 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v22, &Block);
        wil::scope_exit__lambda_9905a906a714268c8f3e490c8e11bc55___(v20, v8);
        for ( i = 0; ; ++i )
        {
          LODWORD(Size) = 0;
          dwCreationDispositiona = (size_t *)v23;
          if ( !(unsigned int)DevObjEnumDeviceInterfaces(v6, 0, &GUID_DEVINTERFACE_HECI, i) )
            break;
          dwCreationDispositiona = &Size;
          LODWORD(Size) = 0;
          if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v6, v23, 0, 0) && GetLastError() != 122 )
          {
            v12 = 654;
            goto LABEL_19;
          }
          v11 = o_malloc_0((unsigned int)Size);
          Block = v11;
          if ( !v11 )
          {
            LastError = -2147024888;
            v13 = 659;
            goto LABEL_22;
          }
          *v11 = 8;
          LODWORD(dwCreationDispositiona) = 0;
          if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v6, v23, Block, (unsigned int)Size) )
            break;
          free(Block);
          Block = 0;
        }
        if ( Block )
        {
          FileW = CreateFileW((LPCWSTR)Block + 2, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
          if ( FileW != (HANDLE)-1LL )
          {
            *a1 = FileW;
            wil::details::lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55___::_lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55___(v20);
            LastError = 0;
            goto LABEL_28;
          }
          v12 = 695;
LABEL_19:
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)v12,
                        (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                        v10);
        }
        else
        {
          LastError = -2147023728;
          v13 = 680;
LABEL_22:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v13,
            (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
            (const char *)LastError,
            (int)dwCreationDispositiona);
        }
        wil::details::lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55___::_lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55___(v20);
        goto LABEL_28;
      }
      v7 = 619;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v7,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v5);
LABEL_28:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&v21);
    return LastError;
  }
  v2 = 606;
LABEL_3:
  LastError = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v2,
    (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
    (const char *)0x80070057LL,
    dwCreationDisposition);
  return LastError;
}

```

## disassembly

```asm
0x1801451c0  mov     [rsp-8+arg_8], rbx
0x1801451c5  mov     [rsp-8+arg_10], rsi
0x1801451ca  push    rbp
0x1801451cb  push    rdi
0x1801451cc  push    r14
0x1801451ce  lea     rbp, [rsp-47h]
0x1801451d3  sub     rsp, 0A0h
0x1801451da  mov     rax, cs:__security_cookie
0x1801451e1  xor     rax, rsp
0x1801451e4  mov     [rbp+57h+var_20], rax
0x1801451e8  xor     r14d, r14d
0x1801451eb  mov     rdi, rcx
0x1801451ee  test    rcx, rcx
0x1801451f1  jnz     short loc_180145215
0x1801451f3  mov     edx, 25Eh; void *
0x1801451f8  mov     rcx, [rbp+5Fh]; this
0x1801451fc  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180145203  mov     ebx, 80070057h
0x180145208  mov     r9d, ebx; char *
0x18014520b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180145210  jmp     loc_180145440
0x180145215  cmp     [rcx], r14
0x180145218  jz      short loc_180145221
0x18014521a  mov     edx, 25Fh
0x18014521f  jmp     short loc_1801451F8
0x180145221  xor     r9d, r9d
0x180145224  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x180145229  xor     r8d, r8d
0x18014522c  xor     edx, edx
0x18014522e  xor     ecx, ecx
0x180145230  call    cs:__imp_DevObjCreateDeviceInfoList
0x180145237  nop     dword ptr [rax+rax+00h]
0x18014523c  mov     [rbp+57h+var_50], rax
0x180145240  mov     rbx, rax
0x180145243  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180145247  jnz     short loc_180145250
0x180145249  mov     edx, 262h
0x18014524e  jmp     short loc_180145282
0x180145250  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r14
0x180145255  lea     rdx, GUID_DEVINTERFACE_HECI
0x18014525c  mov     r9d, 12h
0x180145262  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x180145267  xor     r8d, r8d
0x18014526a  mov     rcx, rbx
0x18014526d  call    cs:__imp_DevObjGetClassDevs
0x180145274  nop     dword ptr [rax+rax+00h]
0x180145279  test    eax, eax
0x18014527b  jnz     short loc_180145299
0x18014527d  mov     edx, 26Bh; void *
0x180145282  mov     rcx, [rbp+5Fh]; this
0x180145286  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18014528d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180145292  mov     ebx, eax
0x180145294  jmp     loc_180145437
0x180145299  xorps   xmm0, xmm0
0x18014529c  mov     [rbp+57h+Block], r14
0x1801452a0  movups  [rbp+57h+var_40], xmm0
0x1801452a4  lea     rdx, [rbp+57h+Block]
0x1801452a8  mov     dword ptr [rbp+57h+var_40], 20h ; ' '
0x1801452af  lea     rcx, [rbp+57h+var_48]
0x1801452b3  movups  [rbp+57h+var_30], xmm0
0x1801452b7  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1801452bc  mov     rdx, rax
0x1801452bf  lea     rcx, [rbp+57h+var_60]
0x1801452c3  call    wil__scope_exit__lambda_9905a906a714268c8f3e490c8e11bc55___
0x1801452c8  mov     esi, r14d
0x1801452cb  lea     rax, [rbp+57h+var_40]
0x1801452cf  mov     dword ptr [rbp+57h+Size], r14d
0x1801452d3  mov     r9d, esi
0x1801452d6  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x1801452db  lea     r8, GUID_DEVINTERFACE_HECI
0x1801452e2  xor     edx, edx
0x1801452e4  mov     rcx, rbx
0x1801452e7  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1801452ee  nop     dword ptr [rax+rax+00h]
0x1801452f3  test    eax, eax
0x1801452f5  jz      loc_1801453D3
0x1801452fb  lea     rax, [rbp+57h+Size]
0x1801452ff  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r14
0x180145304  xor     r9d, r9d
0x180145307  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; int
0x18014530c  xor     r8d, r8d
0x18014530f  mov     dword ptr [rbp+57h+Size], r14d
0x180145313  lea     rdx, [rbp+57h+var_40]
0x180145317  mov     rcx, rbx
0x18014531a  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180145321  nop     dword ptr [rax+rax+00h]
0x180145326  test    eax, eax
0x180145328  jnz     short loc_18014533B
0x18014532a  call    cs:__imp_GetLastError
0x180145331  nop     dword ptr [rax+rax+00h]
0x180145336  cmp     eax, 7Ah ; 'z'
0x180145339  jnz     short loc_18014538F
0x18014533b  mov     ecx, dword ptr [rbp+57h+Size]; Size
0x18014533e  call    _o_malloc_0
0x180145343  mov     [rbp+57h+Block], rax
0x180145347  test    rax, rax
0x18014534a  jz      short loc_1801453B4
0x18014534c  mov     dword ptr [rax], 8
0x180145352  lea     rdx, [rbp+57h+var_40]
0x180145356  mov     r9d, dword ptr [rbp+57h+Size]
0x18014535a  mov     rcx, rbx
0x18014535d  mov     r8, [rbp+57h+Block]
0x180145361  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r14
0x180145366  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x18014536b  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180145372  nop     dword ptr [rax+rax+00h]
0x180145377  test    eax, eax
0x180145379  jnz     short loc_1801453D3
0x18014537b  mov     rcx, [rbp+57h+Block]; Block
0x18014537f  call    free
0x180145384  inc     esi
0x180145386  mov     [rbp+57h+Block], r14
0x18014538a  jmp     loc_1801452CB
0x18014538f  mov     edx, 28Eh; void *
0x180145394  mov     rcx, [rbp+5Fh]; this
0x180145398  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18014539f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801453a4  mov     ebx, eax
0x1801453a6  lea     rcx, [rbp+57h+var_60]
0x1801453aa  call    wil__details__lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55______lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55___
0x1801453af  jmp     loc_180145437
0x1801453b4  mov     ebx, 80070008h
0x1801453b9  mov     edx, 293h; void *
0x1801453be  mov     rcx, [rbp+5Fh]; this
0x1801453c2  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801453c9  mov     r9d, ebx; char *
0x1801453cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801453d1  jmp     short loc_1801453A6
0x1801453d3  mov     rcx, [rbp+57h+Block]
0x1801453d7  test    rcx, rcx
0x1801453da  jnz     short loc_1801453E8
0x1801453dc  mov     ebx, 80070490h
0x1801453e1  mov     edx, 2A8h
0x1801453e6  jmp     short loc_1801453BE
0x1801453e8  mov     [rsp+0B0h+hTemplateFile], r14; hTemplateFile
0x1801453ed  mov     r8d, 3; dwShareMode
0x1801453f3  mov     [rsp+0B0h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1801453fb  add     rcx, 4; lpFileName
0x1801453ff  xor     r9d, r9d; lpSecurityAttributes
0x180145402  mov     [rsp+0B0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180145407  mov     edx, 0C0000000h; dwDesiredAccess
0x18014540c  call    cs:__imp_CreateFileW
0x180145413  nop     dword ptr [rax+rax+00h]
0x180145418  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18014541c  jnz     short loc_180145428
0x18014541e  mov     edx, 2B7h
0x180145423  jmp     loc_180145394
0x180145428  lea     rcx, [rbp+57h+var_60]
0x18014542c  mov     [rdi], rax
0x18014542f  call    wil__details__lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55______lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55___
0x180145434  mov     ebx, r14d
0x180145437  lea     rcx, [rbp+57h+var_50]
0x18014543b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x180145440  mov     eax, ebx
0x180145442  mov     rcx, [rbp+57h+var_20]
0x180145446  xor     rcx, rsp; StackCookie
0x180145449  call    __security_check_cookie
0x18014544e  lea     r11, [rsp+0B0h+var_10]
0x180145456  mov     rbx, [r11+28h]
0x18014545a  mov     rsi, [r11+30h]
0x18014545e  mov     rsp, r11
0x180145461  pop     r14
0x180145463  pop     rdi
0x180145464  pop     rbp
0x180145465  retn
```
