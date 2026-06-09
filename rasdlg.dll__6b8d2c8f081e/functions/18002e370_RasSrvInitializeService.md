# RasSrvInitializeService

- ea: `0x18002e370`
- end: `0x18002e511`
- name: `RasSrvInitializeService`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18002ee94`

## callees

- `0x18002e370`
- `0x18002f01c`
- `0x180033888`
- `0x180033a10`
- `0x1800345d8`
- `0x180034694`
- `0x180034738`
- `0x18003481c`
- `0x1800348f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e434`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002e4a8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002e4a8`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18002e42a`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18002e42a`
- `MPRAPI!MprAdminIsServiceInitialized` at `0x18002e48d`
- `MPRAPI!MprAdminIsServiceInitialized` at `0x18002e48d`
- `USER32!GetActiveWindow` at `0x18002e3b2`
- `USER32!GetActiveWindow` at `0x18002e3b2`

## string_xrefs

- `0x18002e453`: `RasSrvInitializeService: SvcStart: returned: %d`
- `0x18002e469`: `RasSrvInitializeService: Timeout from SvcStart.`
- `0x18002e4b7`: `RasSrvInitializeService: Timeout. MprAdminIsServiceRunning returned false`
- `0x18002e4d8`: `RasSrvInitializeService: SvcStop: returned: %d`
- `0x18002e4fb`: `RasSrvInitializeService: returned: %d`
- `0x18002e39e`: `remoteaccess`

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
  result = DialupOpenNamedService(aRemoteaccess_0, (__int64 *)&lpMem);
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
0x18002e370  mov     rax, rsp
0x18002e373  push    rbx
0x18002e374  push    rsi
0x18002e375  push    rdi
0x18002e376  sub     rsp, 60h
0x18002e37a  mov     qword ptr [rax+10h], 0
0x18002e382  mov     qword ptr [rax+18h], 0
0x18002e38a  mov     dword ptr [rax+8], 0
0x18002e391  call    RasSrvUiInit
0x18002e396  lea     rdx, [rsp+78h+lpMem]
0x18002e39e  lea     rcx, aRemoteaccess_0; "remoteaccess"
0x18002e3a5  call    DialupOpenNamedService
0x18002e3aa  test    eax, eax
0x18002e3ac  jnz     loc_18002E509
0x18002e3b2  call    cs:__imp_GetActiveWindow
0x18002e3b8  lea     r8, [rsp+78h+hCursor]
0x18002e3c0  call    RasSrvShowServiceWait
0x18002e3c5  mov     rdi, [rsp+78h+lpMem]
0x18002e3cd  test    rdi, rdi
0x18002e3d0  jnz     short loc_18002E3DA
0x18002e3d2  lea     ebx, [rdi+57h]
0x18002e3d5  jmp     loc_18002E4E4
0x18002e3da  mov     rcx, [rdi+8]; hService
0x18002e3de  or      r9d, 0FFFFFFFFh; dwErrorControl
0x18002e3e2  mov     [rsp+78h+lpDisplayName], 0; lpDisplayName
0x18002e3eb  mov     r8d, 2; dwStartType
0x18002e3f1  mov     [rsp+78h+lpPassword], 0; lpPassword
0x18002e3fa  or      edx, r9d; dwServiceType
0x18002e3fd  mov     [rsp+78h+lpServiceStartName], 0; lpServiceStartName
0x18002e406  mov     [rsp+78h+lpDependencies], 0; lpDependencies
0x18002e40f  mov     [rsp+78h+lpdwTagId], 0; lpdwTagId
0x18002e418  mov     [rsp+78h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x18002e421  mov     [rsp+78h+lpBinaryPathName], 0; lpBinaryPathName
0x18002e42a  call    cs:__imp_ChangeServiceConfigW
0x18002e430  test    eax, eax
0x18002e432  jnz     short loc_18002E444
0x18002e434  call    cs:__imp_GetLastError
0x18002e43a  mov     ebx, eax
0x18002e43c  test    eax, eax
0x18002e43e  jnz     loc_18002E4E4
0x18002e444  mov     edx, 12Ch
0x18002e449  mov     rcx, rdi
0x18002e44c  call    SvcStart
0x18002e451  mov     edx, eax
0x18002e453  lea     rcx, aRassrvinitiali_3; "RasSrvInitializeService: SvcStart: retu"...
0x18002e45a  mov     ebx, eax
0x18002e45c  call    DbgOutputTrace
0x18002e461  cmp     ebx, 5B4h
0x18002e467  jnz     short loc_18002E47C
0x18002e469  lea     rcx, aRassrvinitiali_4; "RasSrvInitializeService: Timeout from S"...
0x18002e470  call    DbgOutputTrace
0x18002e475  mov     ebx, 3EBh
0x18002e47a  jmp     short loc_18002E4E4
0x18002e47c  test    ebx, ebx
0x18002e47e  jnz     short loc_18002E4E4
0x18002e480  lea     esi, [rbx+78h]
0x18002e483  lea     rdx, [rsp+78h+fIsServiceInitialized]; fIsServiceInitialized
0x18002e48b  xor     ecx, ecx; lpwsServerName
0x18002e48d  call    cs:__imp_MprAdminIsServiceInitialized
0x18002e493  cmp     [rsp+78h+fIsServiceInitialized], 0
0x18002e49b  mov     ebx, eax
0x18002e49d  jnz     short loc_18002E4CA
0x18002e49f  test    eax, eax
0x18002e4a1  jnz     short loc_18002E4B3
0x18002e4a3  mov     ecx, 3E8h; dwMilliseconds
0x18002e4a8  call    cs:__imp_Sleep
0x18002e4ae  add     esi, 0FFFFFFFFh
0x18002e4b1  jnz     short loc_18002E483
0x18002e4b3  test    esi, esi
0x18002e4b5  jnz     short loc_18002E4CA
0x18002e4b7  lea     rcx, aRassrvinitiali_1; "RasSrvInitializeService: Timeout. MprAd"...
0x18002e4be  call    DbgOutputTrace
0x18002e4c3  mov     ebx, 3EBh
0x18002e4c8  jmp     short loc_18002E4CE
0x18002e4ca  test    ebx, ebx
0x18002e4cc  jz      short loc_18002E4E4
0x18002e4ce  mov     rcx, rdi
0x18002e4d1  call    SvcStop
0x18002e4d6  mov     edx, eax
0x18002e4d8  lea     rcx, aRassrvinitiali_0; "RasSrvInitializeService: SvcStop: retur"...
0x18002e4df  call    DbgOutputTrace
0x18002e4e4  mov     rcx, [rsp+78h+hCursor]; hCursor
0x18002e4ec  call    RasSrvFinishServiceWait
0x18002e4f1  mov     rcx, rdi; lpMem
0x18002e4f4  call    SvcClose
0x18002e4f9  mov     edx, ebx
0x18002e4fb  lea     rcx, aRassrvinitiali_2; "RasSrvInitializeService: returned: %d"
0x18002e502  call    DbgOutputTrace
0x18002e507  mov     eax, ebx
0x18002e509  add     rsp, 60h
0x18002e50d  pop     rdi
0x18002e50e  pop     rsi
0x18002e50f  pop     rbx
0x18002e510  retn
```
