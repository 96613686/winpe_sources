# WaitForMUP(ulong,int)

- ea: `0x1800b49e0`
- end: `0x1800b4cbf`
- name: `?WaitForMUP@@YAHKH@Z`
- size: `735`
- prototype: `__int64 __fastcall(DWORD dwMilliseconds, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b4cc8`

## callees

- `0x1800526e0`
- `0x180075ec0`
- `0x1800b49e0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800b4b40`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800b4b40`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4c09`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4c09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4b4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4b4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b4c61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b4c61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b4a6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b4a6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b4a2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b4a2d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b4a63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b4a63`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b4b5e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b4b5e`

## string_xrefs

- `0x1800b4c2c`: `WaitForMUP: Completed WaitForSingleObject.`
- `0x1800b4c4f`: `WaitForMUP: Completed WaitForSingleObject.`

## pseudocode

```c
_BOOL8 __fastcall WaitForMUP(DWORD dwMilliseconds, int a2)
{
  int v4; // esi
  int v5; // ebx
  HANDLE v6; // rdi
  void (*v8)(unsigned int, const unsigned __int16 *, ...); // rax
  BOOL v9; // ebx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+48h] BYREF
  int Data; // [rsp+90h] [rbp+50h] BYREF
  DWORD Type; // [rsp+98h] [rbp+58h] BYREF

  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 0;
  v4 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    RegQueryValueExW(hKey, L"WaitForNetwork", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
  }
  v5 = 20;
  if ( !a2 && Data )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"Waiting for wksta to start for MUP event");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"Waiting for wksta to start for MUP event");
      }
    }
    if ( (unsigned int)WaitForServiceToStart(L"lanmanworkstation", 0x1D4C0u) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"Setting up for long wait for MUP event");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"Setting up for long wait for MUP event");
        }
      }
      v5 = 600;
    }
  }
  while ( 1 )
  {
    v6 = OpenEventW(0x100000u, 0, L"wkssvc:  MUP finished initializing event");
    if ( v6 )
      break;
    if ( GetLastError() == 2 )
    {
      Sleep(0x1F4u);
      if ( ++v4 < v5 )
        continue;
    }
    return 0;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    v8 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"Waiting for wkssvc to signal MUP event");
    }
    else
    {
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
      {
LABEL_30:
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( v8 )
          {
            v8(4u, L"WaitForMUP: Beginning WaitForSingleObject.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"WaitForMUP: Beginning WaitForSingleObject.");
          }
        }
        goto LABEL_36;
      }
      RedirectDebugMsg(4u, L"Waiting for wkssvc to signal MUP event");
    }
    v8 = g_lpDebugMsg;
    goto LABEL_30;
  }
LABEL_36:
  v9 = WaitForSingleObject(v6, dwMilliseconds) == 0;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"WaitForMUP: Completed WaitForSingleObject.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"WaitForMUP: Completed WaitForSingleObject.");
    }
  }
  CloseHandle(v6);
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"Done waiting for MUP");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"Done waiting for MUP");
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800b49e0  push    rbp
0x1800b49e2  push    rbx
0x1800b49e3  push    rsi
0x1800b49e4  push    rdi
0x1800b49e5  push    r12
0x1800b49e7  push    r14
0x1800b49e9  push    r15
0x1800b49eb  mov     rbp, rsp
0x1800b49ee  sub     rsp, 40h
0x1800b49f2  xor     r15d, r15d
0x1800b49f5  lea     rax, [rbp+hKey]
0x1800b49f9  mov     edi, edx
0x1800b49fb  mov     [rbp+hKey], r15
0x1800b49ff  mov     r14d, ecx
0x1800b4a02  mov     [rbp+Data], r15d
0x1800b4a06  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800b4a0d  mov     [rbp+Type], r15d
0x1800b4a11  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b4a18  mov     [rbp+cbData], r15d
0x1800b4a1c  mov     r9d, 20019h; samDesired
0x1800b4a22  mov     [rsp+40h+phkResult], rax; phkResult
0x1800b4a27  xor     r8d, r8d; ulOptions
0x1800b4a2a  mov     esi, r15d
0x1800b4a2d  call    cs:__imp_RegOpenKeyExW
0x1800b4a33  lea     r12d, [r15+4]
0x1800b4a37  test    eax, eax
0x1800b4a39  jnz     short loc_1800B4A73
0x1800b4a3b  mov     rcx, [rbp+hKey]; hKey
0x1800b4a3f  lea     rax, [rbp+cbData]
0x1800b4a43  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800b4a48  lea     r9, [rbp+Type]; lpType
0x1800b4a4c  lea     rax, [rbp+Data]
0x1800b4a50  mov     [rbp+cbData], r12d
0x1800b4a54  xor     r8d, r8d; lpReserved
0x1800b4a57  mov     [rsp+40h+phkResult], rax; lpData
0x1800b4a5c  lea     rdx, aWaitfornetwork_0; "WaitForNetwork"
0x1800b4a63  call    cs:__imp_RegQueryValueExW
0x1800b4a69  mov     rcx, [rbp+hKey]; hKey
0x1800b4a6d  call    cs:__imp_RegCloseKey
0x1800b4a73  mov     ebx, 14h
0x1800b4a78  test    edi, edi
0x1800b4a7a  jnz     loc_1800B4B32
0x1800b4a80  cmp     [rbp+Data], r15d
0x1800b4a84  jz      loc_1800B4B32
0x1800b4a8a  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4a91  jz      short loc_1800B4AD1
0x1800b4a93  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4a9a  test    rax, rax
0x1800b4a9d  jz      short loc_1800B4AB0
0x1800b4a9f  lea     rdx, aWaitingForWkst; "Waiting for wksta to start for MUP even"...
0x1800b4aa6  mov     ecx, r12d
0x1800b4aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4aae  jmp     short loc_1800B4AD1
0x1800b4ab0  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4ab7  jz      short loc_1800B4AD1
0x1800b4ab9  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4ac0  jz      short loc_1800B4AD1
0x1800b4ac2  lea     rdx, aWaitingForWkst; "Waiting for wksta to start for MUP even"...
0x1800b4ac9  mov     ecx, r12d; unsigned int
0x1800b4acc  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4ad1  mov     edx, 1D4C0h; unsigned int
0x1800b4ad6  lea     rcx, aLanmanworkstat; "lanmanworkstation"
0x1800b4add  call    ?WaitForServiceToStart@@YAHPEBGK@Z; WaitForServiceToStart(ushort const *,ulong)
0x1800b4ae2  test    eax, eax
0x1800b4ae4  jz      short loc_1800B4B32
0x1800b4ae6  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4aed  jz      short loc_1800B4B2D
0x1800b4aef  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4af6  test    rax, rax
0x1800b4af9  jz      short loc_1800B4B0C
0x1800b4afb  lea     rdx, aSettingUpForLo; "Setting up for long wait for MUP event"
0x1800b4b02  mov     ecx, r12d
0x1800b4b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4b0a  jmp     short loc_1800B4B2D
0x1800b4b0c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4b13  jz      short loc_1800B4B2D
0x1800b4b15  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4b1c  jz      short loc_1800B4B2D
0x1800b4b1e  lea     rdx, aSettingUpForLo; "Setting up for long wait for MUP event"
0x1800b4b25  mov     ecx, r12d; unsigned int
0x1800b4b28  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4b2d  mov     ebx, 258h
0x1800b4b32  lea     r8, aWkssvcMupFinis; "wkssvc:  MUP finished initializing even"...
0x1800b4b39  xor     edx, edx; bInheritHandle
0x1800b4b3b  mov     ecx, 100000h; dwDesiredAccess
0x1800b4b40  call    cs:__imp_OpenEventW
0x1800b4b46  mov     rdi, rax
0x1800b4b49  test    rax, rax
0x1800b4b4c  jnz     short loc_1800B4B71
0x1800b4b4e  call    cs:__imp_GetLastError
0x1800b4b54  cmp     eax, 2
0x1800b4b57  jnz     short loc_1800B4B6A
0x1800b4b59  mov     ecx, 1F4h; dwMilliseconds
0x1800b4b5e  call    cs:__imp_Sleep
0x1800b4b64  inc     esi
0x1800b4b66  cmp     esi, ebx
0x1800b4b68  jl      short loc_1800B4B32
0x1800b4b6a  xor     eax, eax
0x1800b4b6c  jmp     loc_1800B4CB0
0x1800b4b71  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4b78  jz      loc_1800B4C03
0x1800b4b7e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4b85  test    rax, rax
0x1800b4b88  jz      short loc_1800B4B9B
0x1800b4b8a  lea     rdx, aWaitingForWkss; "Waiting for wkssvc to signal MUP event"
0x1800b4b91  mov     ecx, r12d
0x1800b4b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4b99  jmp     short loc_1800B4BBC
0x1800b4b9b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4ba2  jz      short loc_1800B4BC3
0x1800b4ba4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4bab  jz      short loc_1800B4BC3
0x1800b4bad  lea     rdx, aWaitingForWkss; "Waiting for wkssvc to signal MUP event"
0x1800b4bb4  mov     ecx, r12d; unsigned int
0x1800b4bb7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4bbc  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4bc3  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4bca  jz      short loc_1800B4C03
0x1800b4bcc  test    rax, rax
0x1800b4bcf  jz      short loc_1800B4BE2
0x1800b4bd1  lea     rdx, aWaitformupBegi; "WaitForMUP: Beginning WaitForSingleObje"...
0x1800b4bd8  mov     ecx, r12d
0x1800b4bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4be0  jmp     short loc_1800B4C03
0x1800b4be2  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4be9  jz      short loc_1800B4C03
0x1800b4beb  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4bf2  jz      short loc_1800B4C03
0x1800b4bf4  lea     rdx, aWaitformupBegi; "WaitForMUP: Beginning WaitForSingleObje"...
0x1800b4bfb  mov     ecx, r12d; unsigned int
0x1800b4bfe  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4c03  mov     edx, r14d; dwMilliseconds
0x1800b4c06  mov     rcx, rdi; hHandle
0x1800b4c09  call    cs:__imp_WaitForSingleObject
0x1800b4c0f  test    eax, eax
0x1800b4c11  mov     ebx, r15d
0x1800b4c14  setz    bl
0x1800b4c17  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4c1e  jz      short loc_1800B4C5E
0x1800b4c20  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4c27  test    rax, rax
0x1800b4c2a  jz      short loc_1800B4C3D
0x1800b4c2c  lea     rdx, aWaitformupComp; "WaitForMUP: Completed WaitForSingleObje"...
0x1800b4c33  mov     ecx, r12d
0x1800b4c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4c3b  jmp     short loc_1800B4C5E
0x1800b4c3d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4c44  jz      short loc_1800B4C5E
0x1800b4c46  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4c4d  jz      short loc_1800B4C5E
0x1800b4c4f  lea     rdx, aWaitformupComp; "WaitForMUP: Completed WaitForSingleObje"...
0x1800b4c56  mov     ecx, r12d; unsigned int
0x1800b4c59  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4c5e  mov     rcx, rdi; hObject
0x1800b4c61  call    cs:__imp_CloseHandle
0x1800b4c67  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b4c6e  jz      short loc_1800B4CAE
0x1800b4c70  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b4c77  test    rax, rax
0x1800b4c7a  jz      short loc_1800B4C8D
0x1800b4c7c  lea     rdx, aDoneWaitingFor; "Done waiting for MUP"
0x1800b4c83  mov     ecx, r12d
0x1800b4c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4c8b  jmp     short loc_1800B4CAE
0x1800b4c8d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b4c94  jz      short loc_1800B4CAE
0x1800b4c96  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b4c9d  jz      short loc_1800B4CAE
0x1800b4c9f  lea     rdx, aDoneWaitingFor; "Done waiting for MUP"
0x1800b4ca6  mov     ecx, r12d; unsigned int
0x1800b4ca9  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b4cae  mov     eax, ebx
0x1800b4cb0  add     rsp, 40h
0x1800b4cb4  pop     r15
0x1800b4cb6  pop     r14
0x1800b4cb8  pop     r12
0x1800b4cba  pop     rdi
0x1800b4cbb  pop     rsi
0x1800b4cbc  pop     rbx
0x1800b4cbd  pop     rbp
0x1800b4cbe  retn
```
