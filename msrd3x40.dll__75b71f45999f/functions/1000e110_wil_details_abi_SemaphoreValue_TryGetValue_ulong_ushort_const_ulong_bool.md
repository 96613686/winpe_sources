# wil::details_abi::SemaphoreValue::TryGetValue<ulong>(ushort const *,ulong *,bool *)

- ea: `0x1000e110`
- end: `0x1000e394`
- name: `??$TryGetValue@K@SemaphoreValue@details_abi@wil@@SGJPBGPAKPA_N@Z`
- size: `644`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1000ebe0`
- `0x1000eef0`

## callees

- `0x100084f0`
- `0x10009ce0`
- `0x10009d30`
- `0x10009d80`
- `0x1000e110`
- `0x1005e3b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1000e27b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1000e298`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1000e2c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1000e2e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1000e27b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1000e298`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1000e2c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1000e2e8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1000e1c7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1000e1c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1000e241`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1000e302`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1000e241`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1000e302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000e1d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000e2a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000e2f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000e1d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000e2a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000e2f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000e333`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000e36a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000e333`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000e36a`

## pseudocode

```c
int __fastcall wil::details_abi::SemaphoreValue::TryGetValue<unsigned long>(WCHAR *a1, int *a2, int a3)
{
  WCHAR *v4; // edx
  int v5; // esi
  int v6; // edi
  WCHAR *v7; // eax
  int v8; // ecx
  WCHAR *v9; // eax
  HANDLE v10; // eax
  void *v11; // esi
  wil::details::in1diag3 *v12; // ecx
  int v13; // ebx
  wil::details::in1diag3 *v15; // ecx
  int LastError; // edi
  DWORD v17; // eax
  wil::details::in1diag3 *v18; // ecx
  DWORD v19; // eax
  wil::details::in1diag3 *v20; // ecx
  wil::details::in1diag3 *v21; // ecx
  wchar_t *v22; // [esp+0h] [ebp-228h]
  void *v23; // [esp+0h] [ebp-228h]
  const char *v24; // [esp+4h] [ebp-224h]
  const char *v25; // [esp+4h] [ebp-224h]
  const char *v26; // [esp+8h] [ebp-220h]
  const char *v27; // [esp+8h] [ebp-220h]
  int PreviousCount; // [esp+Ch] [ebp-21Ch] BYREF
  int v29; // [esp+10h] [ebp-218h] BYREF
  int *v30; // [esp+14h] [ebp-214h]
  WCHAR Name[262]; // [esp+18h] [ebp-210h] BYREF

  v4 = Name;
  v30 = a2;
  v5 = 2147483646;
  *a2 = 0;
  v6 = 260;
  do
  {
    if ( !v5 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v5;
    --v6;
  }
  while ( v6 );
  v7 = v4 - 1;
  if ( v6 )
    v7 = v4;
  *v7 = 0;
  v8 = 260;
  v9 = Name;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  if ( v8 )
    StringCopyWorkerW((STRSAFE_LPWSTR)v8, (size_t)L"_p0", (size_t *)v8, v22, (size_t)v24);
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  if ( v10 )
  {
    v13 = 0;
    v17 = WaitForSingleObject(v10, 0);
    if ( v17 != -1 )
    {
      if ( v17 && v17 != 258 )
        goto LABEL_37;
      PreviousCount = 0;
      if ( v17 )
      {
        v29 = 0;
        if ( ReleaseSemaphore(v11, 1, &v29) )
        {
          if ( v29 || ReleaseSemaphore(v11, 1, 0) || GetLastError() != 298 )
            goto LABEL_37;
          v19 = WaitForSingleObject(v11, 0);
          if ( v19 != -1 )
          {
            if ( v19 )
            {
LABEL_37:
              wil::details::in1diag3::Return_Hr(v18, (void *)0x8000FFFF, (unsigned int)v22, v24, (int)v26);
              LastError = -2147418113;
              goto LABEL_38;
            }
            goto LABEL_34;
          }
        }
      }
      else if ( ReleaseSemaphore(v11, 1, &PreviousCount) )
      {
        ++PreviousCount;
        if ( ReleaseSemaphore(v11, 1, 0) || GetLastError() != 298 )
          goto LABEL_37;
LABEL_34:
        v13 = PreviousCount;
        goto LABEL_35;
      }
    }
    LastError = wil::details::in1diag3::Return_GetLastError(v18, v22, (unsigned int)v24, v26);
    if ( LastError < 0 )
    {
LABEL_38:
      wil::details::in1diag3::Return_Hr(v20, (void *)LastError, (unsigned int)v22, v24, (int)v26);
      if ( !CloseHandle(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(v15, v23, (unsigned int)v25, v27);
      goto LABEL_17;
    }
LABEL_35:
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(v21, v22, (unsigned int)v24, v26);
    goto LABEL_15;
  }
  if ( GetLastError() == 2 )
  {
    v13 = 0;
LABEL_15:
    *v30 = v13;
    return 0;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(v12, v22, (unsigned int)v24, v26);
  v13 = 0;
  if ( LastError >= 0 )
    goto LABEL_15;
LABEL_17:
  wil::details::in1diag3::Return_Hr(v15, (void *)LastError, (unsigned int)v23, v25, (int)v27);
  return LastError;
}

```

## disassembly

```asm
0x1000e110  mov     edi, edi
0x1000e112  push    ebp
0x1000e113  mov     ebp, esp
0x1000e115  and     esp, 0FFFFFFF8h
0x1000e118  sub     esp, 21Ch
0x1000e11e  mov     eax, ___security_cookie
0x1000e123  xor     eax, esp
0x1000e125  mov     [esp+21Ch+var_4], eax
0x1000e12c  mov     eax, edx
0x1000e12e  lea     edx, [esp+21Ch+Name]
0x1000e132  push    ebx; char *
0x1000e133  push    esi; unsigned int
0x1000e134  push    edi; void *
0x1000e135  mov     [esp+228h+var_214], eax
0x1000e139  mov     esi, 7FFFFFFEh
0x1000e13e  mov     dword ptr [eax], 0
0x1000e144  mov     edi, 104h
0x1000e149  nop     dword ptr [eax+00000000h]
0x1000e150  test    esi, esi
0x1000e152  jz      short loc_1000E16D
0x1000e154  movzx   eax, word ptr [ecx]
0x1000e157  mov     ebx, eax
0x1000e159  test    ax, ax
0x1000e15c  jz      short loc_1000E16D
0x1000e15e  mov     [edx], bx
0x1000e161  add     ecx, 2
0x1000e164  add     edx, 2
0x1000e167  dec     esi
0x1000e168  sub     edi, 1
0x1000e16b  jnz     short loc_1000E150
0x1000e16d  test    edi, edi
0x1000e16f  lea     eax, [edx-2]
0x1000e172  cmovnz  eax, edx
0x1000e175  xor     ecx, ecx
0x1000e177  mov     [eax], cx
0x1000e17a  mov     ecx, 104h
0x1000e17f  lea     eax, [esp+228h+Name]
0x1000e183  cmp     word ptr [eax], 0
0x1000e187  jz      short loc_1000E191
0x1000e189  add     eax, 2
0x1000e18c  sub     ecx, 1
0x1000e18f  jnz     short loc_1000E183
0x1000e191  mov     edx, 104h
0x1000e196  mov     esi, ecx
0x1000e198  mov     eax, edx
0x1000e19a  sub     eax, ecx
0x1000e19c  neg     esi
0x1000e19e  sbb     esi, esi
0x1000e1a0  and     esi, eax
0x1000e1a2  test    ecx, ecx
0x1000e1a4  jz      short loc_1000E1BB
0x1000e1a6  push    ecx; pcchNewDestLength
0x1000e1a7  push    offset aP0; "_p0"
0x1000e1ac  push    ecx; pszDest
0x1000e1ad  lea     ecx, [esp+234h+Name]
0x1000e1b1  sub     edx, esi
0x1000e1b3  lea     ecx, [ecx+esi*2]
0x1000e1b6  call    StringCopyWorkerW
0x1000e1bb  lea     eax, [esp+228h+Name]
0x1000e1bf  push    eax; lpName
0x1000e1c0  push    0; bInheritHandle
0x1000e1c2  push    1F0003h; dwDesiredAccess
0x1000e1c7  call    ds:__imp__OpenSemaphoreW@12; OpenSemaphoreW(x,x,x)
0x1000e1cd  mov     esi, eax
0x1000e1cf  test    esi, esi
0x1000e1d1  jnz     short loc_1000E23D
0x1000e1d3  call    ds:__imp__GetLastError@0; GetLastError()
0x1000e1d9  cmp     eax, 2
0x1000e1dc  jnz     short loc_1000E1FF
0x1000e1de  xor     ebx, ebx
0x1000e1e0  mov     eax, [esp+228h+var_214]
0x1000e1e4  mov     [eax], ebx
0x1000e1e6  xor     eax, eax
0x1000e1e8  pop     edi
0x1000e1e9  pop     esi
0x1000e1ea  pop     ebx
0x1000e1eb  mov     ecx, [esp+21Ch+var_4]
0x1000e1f2  xor     ecx, esp; StackCookie
0x1000e1f4  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000e1f9  mov     esp, ebp
0x1000e1fb  pop     ebp
0x1000e1fc  retn    4
0x1000e1ff  push    ecx; this
0x1000e200  mov     ecx, [ebp+4]
0x1000e203  mov     edx, 0D0h
0x1000e208  call    ?Return_GetLastError@in1diag3@details@wil@@YGJPAXIPBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1000e20d  mov     edi, eax
0x1000e20f  xor     ebx, ebx
0x1000e211  test    edi, edi
0x1000e213  jns     short loc_1000E1E0
0x1000e215  push    edi; void *
0x1000e216  push    ecx; this
0x1000e217  mov     ecx, [ebp+4]
0x1000e21a  mov     edx, 66h ; 'f'
0x1000e21f  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000e224  mov     ecx, [esp+228h+var_4]
0x1000e22b  mov     eax, edi
0x1000e22d  pop     edi
0x1000e22e  pop     esi
0x1000e22f  pop     ebx
0x1000e230  xor     ecx, esp; StackCookie
0x1000e232  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000e237  mov     esp, ebp
0x1000e239  pop     ebp
0x1000e23a  retn    4
0x1000e23d  xor     ebx, ebx
0x1000e23f  push    ebx; dwMilliseconds
0x1000e240  push    esi; hHandle
0x1000e241  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x1000e247  cmp     eax, 0FFFFFFFFh
0x1000e24a  jnz     short loc_1000E256
0x1000e24c  mov     edx, 9Ch
0x1000e251  jmp     loc_1000E312
0x1000e256  test    eax, eax
0x1000e258  jz      short loc_1000E26B
0x1000e25a  cmp     eax, 102h
0x1000e25f  jz      short loc_1000E26B
0x1000e261  mov     edx, 9Dh
0x1000e266  jmp     loc_1000E347
0x1000e26b  mov     [esp+228h+PreviousCount], ebx
0x1000e26f  test    eax, eax
0x1000e271  jnz     short loc_1000E2B9
0x1000e273  lea     eax, [esp+228h+PreviousCount]
0x1000e277  push    eax; lpPreviousCount
0x1000e278  push    1; lReleaseCount
0x1000e27a  push    esi; hSemaphore
0x1000e27b  call    ds:__imp__ReleaseSemaphore@12; ReleaseSemaphore(x,x,x)
0x1000e281  test    eax, eax
0x1000e283  jnz     short loc_1000E28F
0x1000e285  mov     edx, 0A5h
0x1000e28a  jmp     loc_1000E312
0x1000e28f  inc     [esp+228h+PreviousCount]
0x1000e293  push    0; lpPreviousCount
0x1000e295  push    1; lReleaseCount
0x1000e297  push    esi; hSemaphore
0x1000e298  call    ds:__imp__ReleaseSemaphore@12; ReleaseSemaphore(x,x,x)
0x1000e29e  test    eax, eax
0x1000e2a0  jnz     short loc_1000E2AF
0x1000e2a2  call    ds:__imp__GetLastError@0; GetLastError()
0x1000e2a8  cmp     eax, 12Ah
0x1000e2ad  jz      short loc_1000E32E
0x1000e2af  mov     edx, 0AAh
0x1000e2b4  jmp     loc_1000E347
0x1000e2b9  lea     eax, [esp+228h+var_218]
0x1000e2bd  mov     [esp+228h+var_218], ebx
0x1000e2c1  push    eax; lpPreviousCount
0x1000e2c2  push    1; lReleaseCount
0x1000e2c4  push    esi; hSemaphore
0x1000e2c5  call    ds:__imp__ReleaseSemaphore@12; ReleaseSemaphore(x,x,x)
0x1000e2cb  test    eax, eax
0x1000e2cd  jnz     short loc_1000E2D6
0x1000e2cf  mov     edx, 0B4h
0x1000e2d4  jmp     short loc_1000E312
0x1000e2d6  cmp     [esp+228h+var_218], ebx
0x1000e2da  jz      short loc_1000E2E3
0x1000e2dc  mov     edx, 0B5h
0x1000e2e1  jmp     short loc_1000E347
0x1000e2e3  push    0; lpPreviousCount
0x1000e2e5  push    1; lReleaseCount
0x1000e2e7  push    esi; hSemaphore
0x1000e2e8  call    ds:__imp__ReleaseSemaphore@12; ReleaseSemaphore(x,x,x)
0x1000e2ee  test    eax, eax
0x1000e2f0  jnz     short loc_1000E342
0x1000e2f2  call    ds:__imp__GetLastError@0; GetLastError()
0x1000e2f8  cmp     eax, 12Ah
0x1000e2fd  jnz     short loc_1000E342
0x1000e2ff  push    0; dwMilliseconds
0x1000e301  push    esi; hHandle
0x1000e302  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x1000e308  cmp     eax, 0FFFFFFFFh
0x1000e30b  jnz     short loc_1000E323
0x1000e30d  mov     edx, 0BBh
0x1000e312  push    ecx; this
0x1000e313  mov     ecx, [ebp+4]
0x1000e316  call    ?Return_GetLastError@in1diag3@details@wil@@YGJPAXIPBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1000e31b  mov     edi, eax
0x1000e31d  test    edi, edi
0x1000e31f  jns     short loc_1000E332
0x1000e321  jmp     short loc_1000E35A
0x1000e323  test    eax, eax
0x1000e325  jz      short loc_1000E32E
0x1000e327  mov     edx, 0BCh
0x1000e32c  jmp     short loc_1000E347
0x1000e32e  mov     ebx, [esp+228h+PreviousCount]
0x1000e332  push    esi; hObject
0x1000e333  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1000e339  test    eax, eax
0x1000e33b  jz      short loc_1000E386
0x1000e33d  jmp     loc_1000E1E0
0x1000e342  mov     edx, 0B8h
0x1000e347  push    8000FFFFh; void *
0x1000e34c  push    ecx; this
0x1000e34d  mov     ecx, [ebp+4]
0x1000e350  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000e355  mov     edi, 8000FFFFh
0x1000e35a  push    edi; void *
0x1000e35b  push    ecx; this
0x1000e35c  mov     ecx, [ebp+4]
0x1000e35f  mov     edx, 0D6h
0x1000e364  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1000e369  push    esi; hObject
0x1000e36a  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1000e370  test    eax, eax
0x1000e372  jnz     loc_1000E215
0x1000e378  push    ecx; this
0x1000e379  mov     ecx, [ebp+4]
0x1000e37c  mov     edx, 0A0Bh
0x1000e381  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1000e386  push    ecx; this
0x1000e387  mov     ecx, [ebp+4]
0x1000e38a  mov     edx, 0A0Bh
0x1000e38f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
