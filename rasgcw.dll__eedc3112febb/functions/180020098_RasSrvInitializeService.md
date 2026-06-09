# RasSrvInitializeService

- ea: `0x180020098`
- end: `0x180020239`
- name: `RasSrvInitializeService`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x1800209f8`

## callees

- `0x180020098`
- `0x180020b80`
- `0x180021274`
- `0x1800213fc`
- `0x1800263f8`
- `0x1800264b4`
- `0x180026558`
- `0x18002663c`
- `0x180026710`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002015c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002015c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800201d0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800201d0`
- `MPRAPI!MprAdminIsServiceInitialized` at `0x1800201b5`
- `MPRAPI!MprAdminIsServiceInitialized` at `0x1800201b5`
- `USER32!GetActiveWindow` at `0x1800200da`
- `USER32!GetActiveWindow` at `0x1800200da`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180020152`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180020152`

## string_xrefs

- `0x180020191`: `RasSrvInitializeService: Timeout from SvcStart.`
- `0x18002017b`: `RasSrvInitializeService: SvcStart: returned: %d`
- `0x180020200`: `RasSrvInitializeService: SvcStop: returned: %d`
- `0x1800201df`: `RasSrvInitializeService: Timeout. MprAdminIsServiceRunning returned false`
- `0x180020223`: `RasSrvInitializeService: returned: %d`
- `0x1800200c6`: `remoteaccess`

## pseudocode

```c
__int64 RasSrvInitializeService()
{
  __int64 result; // rax
  __int64 v1; // rdx
  __int64 v2; // rcx
  void *v3; // rdi
  DWORD LastError; // ebx
  int v5; // esi
  DWORD IsServiceInitialized; // eax
  int v7; // eax
  BOOL fIsServiceInitialized; // [rsp+80h] [rbp+8h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp+10h] BYREF
  HCURSOR hCursor; // [rsp+90h] [rbp+18h] BYREF

  lpMem = 0;
  hCursor = 0;
  fIsServiceInitialized = 0;
  RasSrvUiInit();
  result = DialupOpenNamedService(aRemoteaccess, (__int64 *)&lpMem);
  if ( !(_DWORD)result )
  {
    GetActiveWindow();
    RasSrvShowServiceWait(v2, v1, &hCursor);
    v3 = lpMem;
    if ( lpMem )
    {
      if ( ChangeServiceConfigW(*((SC_HANDLE *)lpMem + 1), 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0)
        || (LastError = GetLastError()) == 0 )
      {
        LastError = SvcStart(v3, 300);
        DbgOutputTrace("RasSrvInitializeService: SvcStart: returned: %d", LastError);
        if ( LastError == 1460 )
        {
          DbgOutputTrace("RasSrvInitializeService: Timeout from SvcStart.");
          LastError = 1003;
        }
        else if ( !LastError )
        {
          v5 = 120;
          while ( 1 )
          {
            IsServiceInitialized = MprAdminIsServiceInitialized(0, &fIsServiceInitialized);
            LastError = IsServiceInitialized;
            if ( fIsServiceInitialized )
              break;
            if ( !IsServiceInitialized )
            {
              Sleep(0x3E8u);
              if ( --v5 )
                continue;
            }
            if ( !v5 )
            {
              DbgOutputTrace("RasSrvInitializeService: Timeout. MprAdminIsServiceRunning returned false");
              LastError = 1003;
              goto LABEL_16;
            }
            break;
          }
          if ( !LastError )
            goto LABEL_17;
LABEL_16:
          v7 = SvcStop(v3);
          DbgOutputTrace("RasSrvInitializeService: SvcStop: returned: %d", v7);
        }
      }
    }
    else
    {
      LastError = 87;
    }
LABEL_17:
    RasSrvFinishServiceWait(hCursor);
    SvcClose(v3);
    DbgOutputTrace("RasSrvInitializeService: returned: %d", LastError);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180020098  mov     rax, rsp
0x18002009b  push    rbx
0x18002009c  push    rsi
0x18002009d  push    rdi
0x18002009e  sub     rsp, 60h
0x1800200a2  mov     qword ptr [rax+10h], 0
0x1800200aa  mov     qword ptr [rax+18h], 0
0x1800200b2  mov     dword ptr [rax+8], 0
0x1800200b9  call    RasSrvUiInit
0x1800200be  lea     rdx, [rsp+78h+lpMem]
0x1800200c6  lea     rcx, aRemoteaccess; "remoteaccess"
0x1800200cd  call    DialupOpenNamedService
0x1800200d2  test    eax, eax
0x1800200d4  jnz     loc_180020231
0x1800200da  call    cs:__imp_GetActiveWindow
0x1800200e0  lea     r8, [rsp+78h+hCursor]
0x1800200e8  call    RasSrvShowServiceWait
0x1800200ed  mov     rdi, [rsp+78h+lpMem]
0x1800200f5  test    rdi, rdi
0x1800200f8  jnz     short loc_180020102
0x1800200fa  lea     ebx, [rdi+57h]
0x1800200fd  jmp     loc_18002020C
0x180020102  mov     rcx, [rdi+8]; hService
0x180020106  or      r9d, 0FFFFFFFFh; dwErrorControl
0x18002010a  mov     [rsp+78h+lpDisplayName], 0; lpDisplayName
0x180020113  mov     r8d, 2; dwStartType
0x180020119  mov     [rsp+78h+lpPassword], 0; lpPassword
0x180020122  or      edx, r9d; dwServiceType
0x180020125  mov     [rsp+78h+lpServiceStartName], 0; lpServiceStartName
0x18002012e  mov     [rsp+78h+lpDependencies], 0; lpDependencies
0x180020137  mov     [rsp+78h+lpdwTagId], 0; lpdwTagId
0x180020140  mov     [rsp+78h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180020149  mov     [rsp+78h+lpBinaryPathName], 0; lpBinaryPathName
0x180020152  call    cs:__imp_ChangeServiceConfigW
0x180020158  test    eax, eax
0x18002015a  jnz     short loc_18002016C
0x18002015c  call    cs:__imp_GetLastError
0x180020162  mov     ebx, eax
0x180020164  test    eax, eax
0x180020166  jnz     loc_18002020C
0x18002016c  mov     edx, 12Ch
0x180020171  mov     rcx, rdi
0x180020174  call    SvcStart
0x180020179  mov     edx, eax
0x18002017b  lea     rcx, aRassrvinitiali_2; "RasSrvInitializeService: SvcStart: retu"...
0x180020182  mov     ebx, eax
0x180020184  call    DbgOutputTrace
0x180020189  cmp     ebx, 5B4h
0x18002018f  jnz     short loc_1800201A4
0x180020191  lea     rcx, aRassrvinitiali_3; "RasSrvInitializeService: Timeout from S"...
0x180020198  call    DbgOutputTrace
0x18002019d  mov     ebx, 3EBh
0x1800201a2  jmp     short loc_18002020C
0x1800201a4  test    ebx, ebx
0x1800201a6  jnz     short loc_18002020C
0x1800201a8  lea     esi, [rbx+78h]
0x1800201ab  lea     rdx, [rsp+78h+fIsServiceInitialized]; fIsServiceInitialized
0x1800201b3  xor     ecx, ecx; lpwsServerName
0x1800201b5  call    cs:__imp_MprAdminIsServiceInitialized
0x1800201bb  cmp     [rsp+78h+fIsServiceInitialized], 0
0x1800201c3  mov     ebx, eax
0x1800201c5  jnz     short loc_1800201F2
0x1800201c7  test    eax, eax
0x1800201c9  jnz     short loc_1800201DB
0x1800201cb  mov     ecx, 3E8h; dwMilliseconds
0x1800201d0  call    cs:__imp_Sleep
0x1800201d6  add     esi, 0FFFFFFFFh
0x1800201d9  jnz     short loc_1800201AB
0x1800201db  test    esi, esi
0x1800201dd  jnz     short loc_1800201F2
0x1800201df  lea     rcx, aRassrvinitiali_0; "RasSrvInitializeService: Timeout. MprAd"...
0x1800201e6  call    DbgOutputTrace
0x1800201eb  mov     ebx, 3EBh
0x1800201f0  jmp     short loc_1800201F6
0x1800201f2  test    ebx, ebx
0x1800201f4  jz      short loc_18002020C
0x1800201f6  mov     rcx, rdi
0x1800201f9  call    SvcStop
0x1800201fe  mov     edx, eax
0x180020200  lea     rcx, aRassrvinitiali; "RasSrvInitializeService: SvcStop: retur"...
0x180020207  call    DbgOutputTrace
0x18002020c  mov     rcx, [rsp+78h+hCursor]; hCursor
0x180020214  call    RasSrvFinishServiceWait
0x180020219  mov     rcx, rdi; lpMem
0x18002021c  call    SvcClose
0x180020221  mov     edx, ebx
0x180020223  lea     rcx, aRassrvinitiali_1; "RasSrvInitializeService: returned: %d"
0x18002022a  call    DbgOutputTrace
0x18002022f  mov     eax, ebx
0x180020231  add     rsp, 60h
0x180020235  pop     rdi
0x180020236  pop     rsi
0x180020237  pop     rbx
0x180020238  retn
```
