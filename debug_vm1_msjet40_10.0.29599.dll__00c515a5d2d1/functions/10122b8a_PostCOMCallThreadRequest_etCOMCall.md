# PostCOMCallThreadRequest(etCOMCall,...)

- ea: `0x10122b8a`
- end: `0x10122cfa`
- name: `?PostCOMCallThreadRequest@@YAJW4etCOMCall@@ZZ`
- size: `368`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x10017b70`
- `0x1003ee40`
- `0x100410c0`
- `0x101219d5`

## callees

- `0x101229c5`
- `0x10122b8a`
- `0x10123110`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x10122bde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x10122bde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10122ba2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10122ba2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x10122be5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x10122be5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x10122c2d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x10122c2d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10122c1f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10122c1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10122c8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10122c8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10122bc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10122bc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10122c79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10122c79`

## pseudocode

```c
int __cdecl PostCOMCallThreadRequest(int a1, char a2)
{
  HANDLE CurrentThread; // eax
  int *v3; // ecx
  int j; // edx
  int v5; // esi
  int *v6; // ebx
  int v7; // esi
  int *v8; // edi
  int *v10; // ecx
  int i; // edx
  int v12; // esi
  int *v13; // ebx
  int *v14; // edi
  _OWORD v15[18]; // [esp+Ch] [ebp-130h] BYREF

  if ( GetCurrentThreadId() == dword_10131128 || !dword_10131188 )
  {
    v10 = (int *)&a2;
    for ( i = 0; ; ++i )
    {
      v12 = *v10++;
      v13 = v10;
      if ( v12 )
      {
        if ( v12 == 1 )
        {
          ++v10;
          *((_DWORD *)&v15[15] + i) = *v13;
        }
        else if ( v12 == 99 )
        {
          return COMCallProcess(v15);
        }
      }
      else
      {
        v10 += 4;
        v14 = (int *)&v15[i];
        *v14++ = *v13;
        *v14++ = v13[1];
        *v14 = v13[2];
        v14[1] = v13[3];
      }
    }
  }
  EnterCriticalSection(&CriticalSection);
  if ( dword_1013119C )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
      TokenHandle = 0;
  }
  v3 = (int *)&a2;
  dword_10130FF4 = a1;
  for ( j = 0; ; ++j )
  {
    v5 = *v3++;
    v6 = v3;
    if ( v5 )
      break;
    v3 += 4;
    v8 = &dword_10131038[4 * j];
    *v8++ = *v6;
    *v8++ = v6[1];
    *v8 = v6[2];
    v8[1] = v6[3];
LABEL_14:
    ;
  }
  if ( v5 == 1 )
  {
    ++v3;
    dword_10130FF8[j] = *v6;
    goto LABEL_14;
  }
  if ( v5 != 99 )
    goto LABEL_14;
  SetEvent(pHandles);
  if ( WaitForSingleObject(hHandle, 0xFFFFFFFF) )
  {
    v7 = -2147467259;
    dword_10130FD8 = -2147467259;
  }
  else
  {
    v7 = dword_10130FD8;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  return v7;
}

```

## disassembly

```asm
0x10122b8a  mov     edi, edi
0x10122b8c  push    ebp
0x10122b8d  mov     ebp, esp
0x10122b8f  sub     esp, 130h
0x10122b95  mov     eax, ___security_cookie
0x10122b9a  xor     eax, ebp
0x10122b9c  mov     [ebp+var_4], eax
0x10122b9f  push    ebx
0x10122ba0  push    esi
0x10122ba1  push    edi
0x10122ba2  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10122ba8  cmp     eax, dword_10131128
0x10122bae  jz      loc_10122C98
0x10122bb4  cmp     dword_10131188, 0
0x10122bbb  jz      loc_10122C98
0x10122bc1  push    offset CriticalSection; lpCriticalSection
0x10122bc6  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10122bcc  cmp     dword_1013119C, 0
0x10122bd3  jz      short loc_10122BF4
0x10122bd5  push    offset TokenHandle; TokenHandle
0x10122bda  push    1; OpenAsSelf
0x10122bdc  push    4; DesiredAccess
0x10122bde  call    ds:__imp__GetCurrentThread@0; GetCurrentThread()
0x10122be4  push    eax; ThreadHandle
0x10122be5  call    ds:__imp__OpenThreadToken@16; OpenThreadToken(x,x,x,x)
0x10122beb  test    eax, eax
0x10122bed  jnz     short loc_10122BF4
0x10122bef  mov     TokenHandle, eax
0x10122bf4  mov     eax, [ebp+arg_0]
0x10122bf7  lea     ecx, [ebp+arg_4]
0x10122bfa  mov     dword_10130FF4, eax
0x10122bff  xor     edx, edx
0x10122c01  mov     esi, [ecx]
0x10122c03  add     ecx, 4
0x10122c06  mov     eax, esi
0x10122c08  mov     ebx, ecx
0x10122c0a  sub     eax, 0
0x10122c0d  jz      short loc_10122C52
0x10122c0f  sub     eax, 1
0x10122c12  jz      short loc_10122C44
0x10122c14  cmp     esi, 63h ; 'c'
0x10122c17  jnz     short loc_10122C66
0x10122c19  push    pHandles; hEvent
0x10122c1f  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10122c25  push    0FFFFFFFFh; dwMilliseconds
0x10122c27  push    hHandle; hHandle
0x10122c2d  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x10122c33  test    eax, eax
0x10122c35  jz      short loc_10122C69
0x10122c37  mov     esi, 80004005h
0x10122c3c  mov     dword_10130FD8, esi
0x10122c42  jmp     short loc_10122C6F
0x10122c44  mov     eax, [ebx]
0x10122c46  add     ecx, 4
0x10122c49  mov     dword_10130FF8[edx*4], eax
0x10122c50  jmp     short loc_10122C66
0x10122c52  mov     edi, edx
0x10122c54  add     ecx, 10h
0x10122c57  shl     edi, 4
0x10122c5a  mov     esi, ebx
0x10122c5c  add     edi, offset dword_10131038
0x10122c62  movsd
0x10122c63  movsd
0x10122c64  movsd
0x10122c65  movsd
0x10122c66  inc     edx
0x10122c67  jmp     short loc_10122C01
0x10122c69  mov     esi, dword_10130FD8
0x10122c6f  mov     eax, TokenHandle
0x10122c74  test    eax, eax
0x10122c76  jz      short loc_10122C89
0x10122c78  push    eax; hObject
0x10122c79  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10122c7f  mov     TokenHandle, 0
0x10122c89  push    offset CriticalSection; lpCriticalSection
0x10122c8e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10122c94  mov     eax, esi
0x10122c96  jmp     short loc_10122CC7
0x10122c98  lea     ecx, [ebp+arg_4]
0x10122c9b  xor     edx, edx
0x10122c9d  mov     esi, [ecx]
0x10122c9f  add     ecx, 4
0x10122ca2  mov     eax, esi
0x10122ca4  mov     ebx, ecx
0x10122ca6  sub     eax, 0
0x10122ca9  jz      short loc_10122CE1
0x10122cab  sub     eax, 1
0x10122cae  jz      short loc_10122CD6
0x10122cb0  cmp     esi, 63h ; 'c'
0x10122cb3  jnz     short loc_10122CF7
0x10122cb5  mov     ecx, [ebp+arg_0]
0x10122cb8  lea     eax, [ebp+var_130]
0x10122cbe  push    eax
0x10122cbf  lea     edx, [ebp+var_40]
0x10122cc2  call    ?COMCallProcess@@YGJW4etCOMCall@@QAKQAU_GUID@@@Z; COMCallProcess(etCOMCall,ulong * const,_GUID * const)
0x10122cc7  mov     ecx, [ebp+var_4]
0x10122cca  pop     edi
0x10122ccb  pop     esi
0x10122ccc  xor     ecx, ebp; StackCookie
0x10122cce  pop     ebx
0x10122ccf  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10122cd4  leave
0x10122cd5  retn
0x10122cd6  mov     eax, [ebx]
0x10122cd8  add     ecx, 4
0x10122cdb  mov     [ebp+edx*4+var_40], eax
0x10122cdf  jmp     short loc_10122CF7
0x10122ce1  mov     eax, edx
0x10122ce3  lea     edi, [ebp+var_130]
0x10122ce9  shl     eax, 4
0x10122cec  add     ecx, 10h
0x10122cef  add     edi, eax
0x10122cf1  mov     esi, ebx
0x10122cf3  movsd
0x10122cf4  movsd
0x10122cf5  movsd
0x10122cf6  movsd
0x10122cf7  inc     edx
0x10122cf8  jmp     short loc_10122C9D
```
