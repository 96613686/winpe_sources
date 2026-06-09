# InitializDeviceTable(void)

- ea: `0x18001533c`
- end: `0x180015616`
- name: `?InitializDeviceTable@@YAKXZ`
- size: `730`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b570`

## callees

- `0x180007b7c`
- `0x180011450`
- `0x18001533c`
- `0x18002e268`
- `0x18003b8f4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180015458`
- `KERNEL32!HeapAlloc` at `0x180015458`
- `KERNEL32!GetLastError` at `0x1800155b2`
- `KERNEL32!GetLastError` at `0x1800155b2`
- `KERNEL32!HeapFree` at `0x1800155f2`
- `KERNEL32!HeapFree` at `0x1800155f2`
- `rtutils!RouterLogEventW` at `0x1800155e0`
- `rtutils!RouterLogEventW` at `0x1800155e0`

## string_xrefs

- `0x1800153d4`: `DDMServiceInitialize: DdmGetDeviceConfigInfo failed: Error %d`
- `0x18001552c`: `DDMServiceInitialize: DdmGetDeviceConfigInfo failed: Error %d`
- `0x18001547d`: `DDMServiceInitialize: Malloc failed: Error %d`

## pseudocode

```c
__int64 InitializDeviceTable(void)
{
  DWORD DeviceConfigInfo; // eax
  DWORD v1; // ebx
  __int64 v2; // r8
  __int64 v3; // rax
  void *v4; // rax
  void *v5; // rsi
  __int64 v6; // r8
  __int64 v7; // rax
  DWORD v8; // eax
  __int64 v9; // r8
  __int64 v10; // rax
  DWORD dwErrorCode; // eax
  SIZE_T dwBytes; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+40h] [rbp-C0h] BYREF
  int *v16; // [rsp+50h] [rbp-B0h]
  int v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+5Ch] [rbp-A4h]
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  char v20[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v14 = 6;
  dwBytes = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  DeviceConfigInfo = DdmGetDeviceConfigInfo(0, (int)&v14, (int)&dwBytes + 4, (int)&dwBytes, 0);
  v1 = DeviceConfigInfo;
  if ( !DeviceConfigInfo || DeviceConfigInfo == 603 )
  {
    v4 = HeapAlloc(hHeap, 8u, (unsigned int)dwBytes);
    v5 = v4;
    if ( v4 )
    {
      v8 = DdmGetDeviceConfigInfo(0, (int)&v14, (int)&dwBytes + 4, (int)&dwBytes, v4);
      v1 = v8;
      if ( v8 )
      {
        if ( (byte_1800C8404 & 8) != 0 )
        {
          LOWORD(v19) = 0;
          FormatRRASErrorString(&v19, L"DDMServiceInitialize: DdmGetDeviceConfigInfo failed: Error %d", v8);
          if ( (byte_1800C8404 & 8) != 0 )
          {
            v10 = -1;
            do
              ++v10;
            while ( *(_WORD *)&v20[2 * v10 - 4] );
            v18 = 0;
            v17 = 2 * v10 + 2;
            v16 = &v19;
            McGenEventWrite_EventWriteTransfer(
              (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (const EVENT_DESCRIPTOR *)RasDdmTraceError,
              v9,
              2u,
              &v15);
          }
        }
      }
      else if ( !DdmDeviceTable::GetInstance(0) || !DdmConnectionTable::GetInstance() )
      {
        dwErrorCode = GetLastError();
        v1 = dwErrorCode;
        if ( dword_1800C84E4 )
          RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, dwErrorCode);
      }
      HeapFree(hHeap, 0, v5);
    }
    else
    {
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v19, L"DDMServiceInitialize: Malloc failed: Error %d", 8);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v7 = -1;
          do
            ++v7;
          while ( *(_WORD *)&v20[2 * v7 - 4] );
          v18 = 0;
          v17 = 2 * v7 + 2;
          v16 = &v19;
          McGenEventWrite_EventWriteTransfer(
            (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasDdmTraceError,
            v6,
            2u,
            &v15);
        }
      }
      return 8;
    }
  }
  else if ( (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v19) = 0;
    FormatRRASErrorString(&v19, L"DDMServiceInitialize: DdmGetDeviceConfigInfo failed: Error %d", DeviceConfigInfo);
    if ( (byte_1800C8404 & 8) != 0 )
    {
      v3 = -1;
      do
        ++v3;
      while ( *(_WORD *)&v20[2 * v3 - 4] );
      v18 = 0;
      v17 = 2 * v3 + 2;
      v16 = &v19;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasDdmTraceError,
        v2,
        2u,
        &v15);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18001533c  push    rbp
0x18001533e  push    rbx
0x18001533f  push    rsi
0x180015340  push    r14
0x180015342  lea     rbp, [rsp-778h]
0x18001534a  sub     rsp, 878h
0x180015351  mov     rax, cs:__security_cookie
0x180015358  xor     rax, rsp
0x18001535b  mov     [rbp+790h+var_30], rax
0x180015362  xor     r14d, r14d
0x180015365  mov     [rsp+890h+var_858], 6
0x18001536d  xor     edx, edx; Val
0x18001536f  mov     dword ptr [rsp+890h+dwBytes+4], r14d
0x180015374  mov     r8d, 7FCh; Size
0x18001537a  mov     dword ptr [rsp+890h+dwBytes], r14d
0x18001537f  lea     rcx, [rsp+890h+var_82C]; void *
0x180015384  mov     [rsp+890h+var_830], r14d
0x180015389  call    memset_0
0x18001538e  lea     r9, [rsp+890h+dwBytes]; int
0x180015393  mov     [rsp+890h+plpszSubStringArray], r14; void *
0x180015398  lea     r8, [rsp+890h+dwBytes+4]; int
0x18001539d  xor     ecx, ecx; int
0x18001539f  lea     rdx, [rsp+890h+var_858]; int
0x1800153a4  call    DdmGetDeviceConfigInfo
0x1800153a9  mov     ebx, eax
0x1800153ab  test    eax, eax
0x1800153ad  jz      loc_180015447
0x1800153b3  cmp     eax, 25Bh
0x1800153b8  jz      loc_180015447
0x1800153be  test    cs:byte_1800C8404, 8
0x1800153c5  jz      loc_1800155F8
0x1800153cb  mov     r8d, eax
0x1800153ce  mov     word ptr [rsp+890h+var_830], r14w
0x1800153d4  lea     rdx, aDdmserviceinit_32; "DDMServiceInitialize: DdmGetDeviceConfi"...
0x1800153db  lea     rcx, [rsp+890h+var_830]
0x1800153e0  call    FormatRRASErrorString
0x1800153e5  test    cs:byte_1800C8404, 8
0x1800153ec  jz      loc_1800155F8
0x1800153f2  lea     rcx, [rsp+890h+var_830]
0x1800153f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800153fb  inc     rax
0x1800153fe  cmp     [rcx+rax*2], r14w
0x180015403  jnz     short loc_1800153FB
0x180015405  lea     eax, ds:2[rax*2]
0x18001540c  mov     [rsp+890h+var_834], r14d
0x180015411  lea     rcx, [rsp+890h+var_830]
0x180015416  mov     [rsp+890h+var_838], eax
0x18001541a  lea     rax, [rsp+890h+var_850]
0x18001541f  mov     [rsp+890h+var_840], rcx
0x180015424  mov     r9d, 2
0x18001542a  mov     [rsp+890h+plpszSubStringArray], rax
0x18001542f  lea     rdx, RasDdmTraceError
0x180015436  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001543d  call    McGenEventWrite_EventWriteTransfer
0x180015442  jmp     loc_1800155F8
0x180015447  mov     r8d, dword ptr [rsp+890h+dwBytes]; dwBytes
0x18001544c  mov     edx, 8; dwFlags
0x180015451  mov     rcx, cs:hHeap; hHeap
0x180015458  call    cs:__imp_HeapAlloc
0x18001545e  mov     rsi, rax
0x180015461  test    rax, rax
0x180015464  jnz     loc_1800154F1
0x18001546a  test    cs:byte_1800C8404, 8
0x180015471  jz      short loc_1800154E7
0x180015473  lea     r8d, [rax+8]
0x180015477  mov     word ptr [rsp+890h+var_830], r14w
0x18001547d  lea     rdx, aDdmserviceinit_8; "DDMServiceInitialize: Malloc failed: Er"...
0x180015484  lea     rcx, [rsp+890h+var_830]
0x180015489  call    FormatRRASErrorString
0x18001548e  test    cs:byte_1800C8404, 8
0x180015495  jz      short loc_1800154E7
0x180015497  lea     rcx, [rsp+890h+var_830]
0x18001549c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800154a0  inc     rax
0x1800154a3  cmp     [rcx+rax*2], r14w
0x1800154a8  jnz     short loc_1800154A0
0x1800154aa  lea     eax, ds:2[rax*2]
0x1800154b1  mov     [rsp+890h+var_834], r14d
0x1800154b6  lea     rcx, [rsp+890h+var_830]
0x1800154bb  mov     [rsp+890h+var_838], eax
0x1800154bf  lea     rax, [rsp+890h+var_850]
0x1800154c4  mov     [rsp+890h+var_840], rcx
0x1800154c9  mov     r9d, 2
0x1800154cf  mov     [rsp+890h+plpszSubStringArray], rax
0x1800154d4  lea     rdx, RasDdmTraceError
0x1800154db  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800154e2  call    McGenEventWrite_EventWriteTransfer
0x1800154e7  mov     ebx, 8
0x1800154ec  jmp     loc_1800155F8
0x1800154f1  lea     r9, [rsp+890h+dwBytes]; int
0x1800154f6  mov     [rsp+890h+plpszSubStringArray], rsi; void *
0x1800154fb  lea     r8, [rsp+890h+dwBytes+4]; int
0x180015500  xor     ecx, ecx; int
0x180015502  lea     rdx, [rsp+890h+var_858]; int
0x180015507  call    DdmGetDeviceConfigInfo
0x18001550c  mov     ebx, eax
0x18001550e  test    eax, eax
0x180015510  jz      loc_18001559C
0x180015516  test    cs:byte_1800C8404, 8
0x18001551d  jz      loc_1800155E6
0x180015523  mov     r8d, eax
0x180015526  mov     word ptr [rsp+890h+var_830], r14w
0x18001552c  lea     rdx, aDdmserviceinit_32; "DDMServiceInitialize: DdmGetDeviceConfi"...
0x180015533  lea     rcx, [rsp+890h+var_830]
0x180015538  call    FormatRRASErrorString
0x18001553d  test    cs:byte_1800C8404, 8
0x180015544  jz      loc_1800155E6
0x18001554a  lea     rcx, [rsp+890h+var_830]
0x18001554f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015553  inc     rax
0x180015556  cmp     [rcx+rax*2], r14w
0x18001555b  jnz     short loc_180015553
0x18001555d  lea     eax, ds:2[rax*2]
0x180015564  mov     [rsp+890h+var_834], r14d
0x180015569  lea     rcx, [rsp+890h+var_830]
0x18001556e  mov     [rsp+890h+var_838], eax
0x180015572  lea     rax, [rsp+890h+var_850]
0x180015577  mov     [rsp+890h+var_840], rcx
0x18001557c  mov     r9d, 2
0x180015582  mov     [rsp+890h+plpszSubStringArray], rax
0x180015587  lea     rdx, RasDdmTraceError
0x18001558e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015595  call    McGenEventWrite_EventWriteTransfer
0x18001559a  jmp     short loc_1800155E6
0x18001559c  xor     ecx, ecx; unsigned int
0x18001559e  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x1800155a3  test    rax, rax
0x1800155a6  jz      short loc_1800155B2
0x1800155a8  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x1800155ad  test    rax, rax
0x1800155b0  jnz     short loc_1800155E6
0x1800155b2  call    cs:__imp_GetLastError
0x1800155b8  cmp     cs:dword_1800C84E4, r14d
0x1800155bf  mov     ebx, eax
0x1800155c1  jbe     short loc_1800155E6
0x1800155c3  mov     rcx, cs:hLogHandle; hLogHandle
0x1800155ca  xor     r9d, r9d; dwSubStringCount
0x1800155cd  mov     [rsp+890h+dwErrorCode], eax; dwErrorCode
0x1800155d1  mov     r8d, 4E88h; dwMessageId
0x1800155d7  mov     [rsp+890h+plpszSubStringArray], r14; plpszSubStringArray
0x1800155dc  lea     edx, [r9+1]; dwEventType
0x1800155e0  call    cs:__imp_RouterLogEventW
0x1800155e6  mov     rcx, cs:hHeap; hHeap
0x1800155ed  mov     r8, rsi; lpMem
0x1800155f0  xor     edx, edx; dwFlags
0x1800155f2  call    cs:__imp_HeapFree
0x1800155f8  mov     eax, ebx
0x1800155fa  mov     rcx, [rbp+790h+var_30]
0x180015601  xor     rcx, rsp; StackCookie
0x180015604  call    __security_check_cookie
0x180015609  add     rsp, 878h
0x180015610  pop     r14
0x180015612  pop     rsi
0x180015613  pop     rbx
0x180015614  pop     rbp
0x180015615  retn
```
