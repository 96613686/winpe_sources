# CService::InternalInit(ushort *,CServiceControlManager *,ulong,ushort *)

- ea: `0x180014b94`
- end: `0x180014c62`
- name: `?InternalInit@CService@@IEAAJPEAGPEAVCServiceControlManager@@K0@Z`
- size: `206`
- prototype: `__int64 __fastcall(CService *__hidden this, unsigned __int16 *, struct CServiceControlManager *, unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007d90`
- `0x180008ad8`

## callees

- `0x180014b94`
- `0x18001509c`
- `0x180015230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c11`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180014c02`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180014c02`

## string_xrefs

- `0x180014bc2`: `com\complus\dtc\shared\util\scm.cpp`
- `0x180014c33`: `com\complus\dtc\shared\util\scm.cpp`
- `0x180014c3a`: `OpenServiceW call failed`
- `0x180014bbb`: `CServiceControlManager::Create call failed`
- `0x180014be7`: `CServiceControlManager::GetHandle call failed`

## pseudocode

```c
__int64 __fastcall CService::InternalInit(
        struct CServiceControlManager **this,
        unsigned __int16 *a2,
        struct CServiceControlManager *a3,
        unsigned __int16 *a4)
{
  int v5; // ebx
  unsigned int v6; // r9d
  char *v7; // rdx
  SC_HANDLE v9; // rcx
  SC_HANDLE v10; // rax
  signed int LastError; // eax
  int v12; // edi
  unsigned int v13; // ecx

  v5 = CServiceControlManager::Create(this + 1, (unsigned int)a2, (unsigned __int16 *)a3, a4);
  if ( v5 < 0 )
  {
    v6 = 241;
    v7 = "CServiceControlManager::Create call failed";
LABEL_3:
    TraceFile(v5, v7, "com\\complus\\dtc\\shared\\util\\scm.cpp", v6);
    return (unsigned int)v5;
  }
  v9 = (SC_HANDLE)*((_QWORD *)this[1] + 1);
  if ( !v9 )
  {
    v6 = 258;
    v7 = "CServiceControlManager::GetHandle call failed";
    v5 = -2147467259;
    goto LABEL_3;
  }
  v10 = OpenServiceW(v9, L"MSDTC", 1u);
  this[2] = (struct CServiceControlManager *)v10;
  if ( !v10 )
  {
    LastError = GetLastError();
    v12 = (unsigned __int16)LastError;
    v5 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    else
      v13 = LastError;
    TraceFile(v13, "OpenServiceW call failed", "com\\complus\\dtc\\shared\\util\\scm.cpp", 0x10Du);
    if ( v5 > 0 )
      return v12 | 0x80070000;
    return (unsigned int)v5;
  }
  return 0;
}

```

## disassembly

```asm
0x180014b94  mov     [rsp+arg_0], rbx
0x180014b99  mov     [rsp+arg_8], rsi
0x180014b9e  push    rdi
0x180014b9f  sub     rsp, 20h
0x180014ba3  mov     rsi, rcx
0x180014ba6  add     rcx, 8; struct CServiceControlManager **
0x180014baa  call    ?Create@CServiceControlManager@@SAJPEAPEAV1@KPEAG1@Z; CServiceControlManager::Create(CServiceControlManager * *,ulong,ushort *,ushort *)
0x180014baf  mov     ebx, eax
0x180014bb1  test    eax, eax
0x180014bb3  jns     short loc_180014BD4
0x180014bb5  mov     r9d, 0F1h; unsigned int
0x180014bbb  lea     rdx, aCservicecontro_0; "CServiceControlManager::Create call fai"...
0x180014bc2  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\scm.cp"...
0x180014bc9  mov     ecx, ebx; int
0x180014bcb  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180014bd0  mov     eax, ebx
0x180014bd2  jmp     short loc_180014C52
0x180014bd4  mov     rax, [rsi+8]
0x180014bd8  mov     rcx, [rax+8]; hSCManager
0x180014bdc  test    rcx, rcx
0x180014bdf  jnz     short loc_180014BF5
0x180014be1  mov     r9d, 102h
0x180014be7  lea     rdx, aCservicecontro; "CServiceControlManager::GetHandle call "...
0x180014bee  mov     ebx, 80004005h
0x180014bf3  jmp     short loc_180014BC2
0x180014bf5  mov     r8d, 1; dwDesiredAccess
0x180014bfb  lea     rdx, aMsdtc; "MSDTC"
0x180014c02  call    cs:__imp_OpenServiceW
0x180014c08  mov     [rsi+10h], rax
0x180014c0c  test    rax, rax
0x180014c0f  jnz     short loc_180014C50
0x180014c11  call    cs:__imp_GetLastError
0x180014c17  movzx   edi, ax
0x180014c1a  mov     ebx, eax
0x180014c1c  mov     esi, 80070000h
0x180014c21  test    eax, eax
0x180014c23  jg      short loc_180014C29
0x180014c25  mov     ecx, eax
0x180014c27  jmp     short loc_180014C2D
0x180014c29  mov     ecx, edi
0x180014c2b  or      ecx, esi; int
0x180014c2d  mov     r9d, 10Dh; unsigned int
0x180014c33  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\scm.cp"...
0x180014c3a  lea     rdx, aOpenservicewCa; "OpenServiceW call failed"
0x180014c41  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180014c46  test    ebx, ebx
0x180014c48  jle     short loc_180014BD0
0x180014c4a  mov     ebx, edi
0x180014c4c  or      ebx, esi
0x180014c4e  jmp     short loc_180014BD0
0x180014c50  xor     eax, eax
0x180014c52  mov     rbx, [rsp+28h+arg_0]
0x180014c57  mov     rsi, [rsp+28h+arg_8]
0x180014c5c  add     rsp, 20h
0x180014c60  pop     rdi
0x180014c61  retn
```
