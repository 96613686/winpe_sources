# CCatalogServer::CCatalogServer(void)

- ea: `0x180006b40`
- end: `0x180006cc6`
- name: `??0CCatalogServer@@QEAA@XZ`
- size: `390`
- prototype: `CCatalogServer *__fastcall(CCatalogServer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800068f8`

## callees

- `0x180006b40`
- `0x180009098`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x180006c07`
- `msvcrt!_beginthreadex` at `0x180006c07`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006c25`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006c25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006cab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006cab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006bd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006bd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006c9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006c9e`

## string_xrefs

- `0x180006c4d`: `com\complus\src\comcat\catsrv\catalogsrv.cpp`

## pseudocode

```c
CCatalogServer *__fastcall CCatalogServer::CCatalogServer(CCatalogServer *this)
{
  bool v1; // zf
  void *v3; // rdi
  int v5; // [rsp+30h] [rbp-38h] BYREF
  __int16 v6; // [rsp+34h] [rbp-34h]
  int v7; // [rsp+38h] [rbp-30h]
  const unsigned __int16 *v8; // [rsp+40h] [rbp-28h]
  __int64 v9; // [rsp+48h] [rbp-20h]
  __int64 v10; // [rsp+50h] [rbp-18h]
  int v11; // [rsp+58h] [rbp-10h]
  int v12; // [rsp+5Ch] [rbp-Ch]
  unsigned int ThrdAddr; // [rsp+70h] [rbp+8h] BYREF

  *((_DWORD *)this + 42) = 0;
  v1 = CCatalogServer::ms_fRegdbStarted == 0;
  *((_OWORD *)this + 11) = 0;
  *((_OWORD *)this + 12) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_BYTE *)this + 216) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((GUID *)this + 18) = GUID_DefaultAppPartition;
  if ( v1 )
  {
    EnterCriticalSection(&stru_180072D50);
    if ( !CCatalogServer::ms_fRegdbStarted )
    {
      ThrdAddr = 0;
      v3 = (void *)_beginthreadex(0, 0, RunService, 0, 0, &ThrdAddr);
      if ( v3 )
      {
        if ( WaitForSingleObject(g_ThreadStartEvent, 0x15F90u) )
        {
          v5 = 0;
          v6 = 21;
          v8 = L"dwRetval == WAIT_OBJECT_0";
          v7 = -1073605930;
          v9 = 0;
          v10 = 0;
          v12 = 1;
          v11 = 1;
          CError::WriteToLog(
            (CError *)&v5,
            L"com\\complus\\src\\comcat\\catsrv\\catalogsrv.cpp",
            0x20Au,
            L"dwRetval == WAIT_OBJECT_0");
        }
        if ( g_bThreadRunning )
        {
          CCatalogServer::ms_hServiceThread = v3;
          CCatalogServer::ms_fRegdbStarted = 1;
        }
        else
        {
          CloseHandle(v3);
        }
      }
    }
    LeaveCriticalSection(&stru_180072D50);
  }
  return this;
}

```

## disassembly

```asm
0x180006b40  mov     [rsp+arg_8], rbx
0x180006b45  mov     [rsp+arg_10], rsi
0x180006b4a  push    rdi
0x180006b4b  sub     rsp, 60h
0x180006b4f  xor     esi, esi
0x180006b51  xorps   xmm0, xmm0
0x180006b54  mov     [rcx+0A8h], esi
0x180006b5a  xor     eax, eax
0x180006b5c  cmp     cs:?ms_fRegdbStarted@CCatalogServer@@0HA, esi; int CCatalogServer::ms_fRegdbStarted
0x180006b62  mov     rbx, rcx
0x180006b65  movups  xmmword ptr [rcx+0B0h], xmm0
0x180006b6c  movups  xmmword ptr [rcx+0C0h], xmm0
0x180006b73  mov     [rcx+0D0h], rax
0x180006b7a  mov     [rcx+0D8h], sil
0x180006b81  mov     [rcx+0E0h], rsi
0x180006b88  mov     [rcx+0E8h], rsi
0x180006b8f  mov     [rcx+0F0h], rsi
0x180006b96  mov     [rcx+0F8h], rsi
0x180006b9d  mov     [rcx+100h], rsi
0x180006ba4  mov     [rcx+108h], rsi
0x180006bab  mov     [rcx+110h], rsi
0x180006bb2  mov     [rcx+118h], rsi
0x180006bb9  movups  xmm0, xmmword ptr cs:GUID_DefaultAppPartition.Data1
0x180006bc0  movdqu  xmmword ptr [rcx+120h], xmm0
0x180006bc8  jnz     loc_180006CB1
0x180006bce  lea     rcx, stru_180072D50; lpCriticalSection
0x180006bd5  call    cs:__imp_EnterCriticalSection
0x180006bdb  cmp     cs:?ms_fRegdbStarted@CCatalogServer@@0HA, esi; int CCatalogServer::ms_fRegdbStarted
0x180006be1  jnz     loc_180006CA4
0x180006be7  lea     rax, [rsp+68h+arg_0]
0x180006bec  mov     [rsp+68h+arg_0], esi
0x180006bf0  mov     [rsp+68h+ThrdAddr], rax; ThrdAddr
0x180006bf5  lea     r8, ?RunService@@YAIPEAX@Z; StartAddress
0x180006bfc  xor     r9d, r9d; ArgList
0x180006bff  mov     [rsp+68h+InitFlag], esi; InitFlag
0x180006c03  xor     edx, edx; StackSize
0x180006c05  xor     ecx, ecx; Security
0x180006c07  call    cs:__imp__beginthreadex
0x180006c0d  mov     rdi, rax
0x180006c10  test    rax, rax
0x180006c13  jz      loc_180006CA4
0x180006c19  mov     rcx, cs:?g_ThreadStartEvent@@3PEAXEA; hHandle
0x180006c20  mov     edx, 15F90h; dwMilliseconds
0x180006c25  call    cs:__imp_WaitForSingleObject
0x180006c2b  test    eax, eax
0x180006c2d  jz      short loc_180006C80
0x180006c2f  lea     eax, [rsi+15h]
0x180006c32  mov     [rsp+68h+var_38], esi
0x180006c36  lea     r9, aDwretvalWaitOb; "dwRetval == WAIT_OBJECT_0"
0x180006c3d  mov     [rsp+68h+var_34], ax
0x180006c42  mov     r8d, 20Ah; unsigned int
0x180006c48  mov     [rsp+68h+var_28], r9
0x180006c4d  lea     rdx, aComComplusSrcC_1; "com\\complus\\src\\comcat\\catsrv\\cata"...
0x180006c54  mov     [rsp+68h+var_30], 0C00212D6h
0x180006c5c  lea     rcx, [rsp+68h+var_38]; this
0x180006c61  mov     [rsp+68h+var_20], rsi
0x180006c66  mov     [rsp+68h+var_18], rsi
0x180006c6b  mov     [rsp+68h+var_C], 1
0x180006c73  mov     [rsp+68h+var_10], 1
0x180006c7b  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180006c80  cmp     cs:?g_bThreadRunning@@3HA, esi; int g_bThreadRunning
0x180006c86  jz      short loc_180006C9B
0x180006c88  mov     cs:?ms_hServiceThread@CCatalogServer@@0REAXEA, rdi; void * CCatalogServer::ms_hServiceThread
0x180006c8f  mov     cs:?ms_fRegdbStarted@CCatalogServer@@0HA, 1; int CCatalogServer::ms_fRegdbStarted
0x180006c99  jmp     short loc_180006CA4
0x180006c9b  mov     rcx, rdi; hObject
0x180006c9e  call    cs:__imp_CloseHandle
0x180006ca4  lea     rcx, stru_180072D50; lpCriticalSection
0x180006cab  call    cs:__imp_LeaveCriticalSection
0x180006cb1  lea     r11, [rsp+68h+var_8]
0x180006cb6  mov     rax, rbx
0x180006cb9  mov     rbx, [r11+18h]
0x180006cbd  mov     rsi, [r11+20h]
0x180006cc1  mov     rsp, r11
0x180006cc4  pop     rdi
0x180006cc5  retn
```
