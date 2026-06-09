# SaveCachedString(_GPOINFO *,ushort const *,ushort const *)

- ea: `0x1800221d4`
- end: `0x180022436`
- name: `?SaveCachedString@@YAHPEAU_GPOINFO@@PEBG1@Z`
- size: `610`
- prototype: `__int64 __fastcall(struct _GPOINFO *, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18005ce5c`

## callees

- `0x18000a504`
- `0x1800221d4`
- `0x18002243c`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022304`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022344`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022362`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002236d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022304`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022344`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022362`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002236d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800221fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800221fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022313`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022353`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022313`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022353`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800222f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800222f3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800222df`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800222df`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002229a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002229a`

## string_xrefs

- `0x1800223ec`: `SaveCachedString: failed with error: %d`
- `0x18002241f`: `SaveCachedString: failed with error: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SaveCachedString(struct _GPOINFO *a1, LPCWSTR lpValueName, BYTE *lpData)
{
  int v6; // edx
  DWORD LastError; // edi
  __int64 v8; // rsi
  BYTE *v9; // rax
  WCHAR *v10; // rbx
  unsigned int v11; // r15d
  unsigned __int64 v12; // rcx
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-8h] BYREF
  DWORD dwDisposition; // [rsp+A0h] [rbp+40h] BYREF
  DWORD v17; // [rsp+B8h] [rbp+58h]

  lpSubKey = 0;
  LastError = GetLastError();
  v17 = LastError;
  hKey = 0;
  dwDisposition = 0;
  if ( !a1 || !lpValueName || !lpData )
  {
    SetLastError(0x57u);
    return 0;
  }
  if ( !(unsigned int)GetRegistryActivePath(a1, v6, (unsigned __int16 **)&lpSubKey) )
    goto LABEL_23;
  v8 = 0x7FFFFFFF;
  v9 = lpData;
  do
  {
    if ( !*(_WORD *)v9 )
      break;
    v9 += 2;
    --v8;
  }
  while ( v8 );
  if ( !v8 )
  {
LABEL_23:
    SetLastError(LastError);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&lpSubKey);
    return 0;
  }
  v10 = (WCHAR *)lpSubKey;
  v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
  if ( !v11 )
  {
    v12 = ((2 * (0x7FFFFFFF - v8)) & -(__int64)(v8 != 0)) + 2;
    if ( v12 > 0xFFFFFFFF )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"SizeTToDWord() Failed to convert to DWORD");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"SizeTToDWord() Failed to convert to DWORD");
        }
      }
    }
    else
    {
      v11 = RegSetValueExW(hKey, lpValueName, 0, v11 + 1, lpData, v12);
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v11 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"SaveCachedString: failed with error: %d", v11);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"SaveCachedString: failed with error: %d", v11);
      }
    }
    SetLastError(LastError);
    if ( v10 )
      LocalFree(v10);
    return 0;
  }
  SetLastError(LastError);
  if ( v10 )
    LocalFree(v10);
  return 1;
}

```

## disassembly

```asm
0x1800221d4  mov     [rsp-38h+arg_8], rbx
0x1800221d9  push    rbp
0x1800221da  push    rsi
0x1800221db  push    rdi
0x1800221dc  push    r12
0x1800221de  push    r13
0x1800221e0  push    r14
0x1800221e2  push    r15
0x1800221e4  mov     rbp, rsp
0x1800221e7  sub     rsp, 60h
0x1800221eb  mov     r12, r8
0x1800221ee  mov     r13, rdx
0x1800221f1  mov     rbx, rcx
0x1800221f4  xor     r15d, r15d
0x1800221f7  mov     [rbp+lpSubKey], r15
0x1800221fb  call    cs:__imp_GetLastError
0x180022201  mov     edi, eax
0x180022203  mov     [rbp+arg_18], eax
0x180022206  mov     [rbp+hKey], r15
0x18002220a  mov     [rbp+dwDisposition], r15d
0x18002220e  test    rbx, rbx
0x180022211  jz      loc_18002235D
0x180022217  test    r13, r13
0x18002221a  jz      loc_18002235D
0x180022220  test    r12, r12
0x180022223  jz      loc_18002235D
0x180022229  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x18002222d  mov     rcx, rbx; struct _GPOINFO *
0x180022230  call    ?GetRegistryActivePath@@YAHPEAU_GPOINFO@@HPEAPEAG@Z; GetRegistryActivePath(_GPOINFO *,int,ushort * *)
0x180022235  test    eax, eax
0x180022237  jz      loc_18002236B
0x18002223d  mov     r14d, 7FFFFFFFh
0x180022243  mov     esi, r14d
0x180022246  mov     rax, r12
0x180022249  cmp     [rax], r15w
0x18002224d  jz      short loc_180022259
0x18002224f  add     rax, 2
0x180022253  sub     rsi, 1
0x180022257  jnz     short loc_180022249
0x180022259  test    rsi, rsi
0x18002225c  jz      loc_18002236B
0x180022262  lea     rax, [rbp+dwDisposition]
0x180022266  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18002226b  lea     rax, [rbp+hKey]
0x18002226f  mov     [rsp+60h+phkResult], rax; phkResult
0x180022274  mov     [rsp+60h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180022279  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x180022281  mov     [rsp+60h+dwOptions], r15d; dwOptions
0x180022286  xor     r9d, r9d; lpClass
0x180022289  xor     r8d, r8d; Reserved
0x18002228c  mov     rbx, [rbp+lpSubKey]
0x180022290  mov     rdx, rbx; lpSubKey
0x180022293  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002229a  call    cs:__imp_RegCreateKeyExW
0x1800222a0  mov     r15d, eax
0x1800222a3  test    eax, eax
0x1800222a5  jnz     short loc_1800222E8
0x1800222a7  sub     r14, rsi
0x1800222aa  add     r14, r14
0x1800222ad  neg     rsi
0x1800222b0  sbb     rcx, rcx
0x1800222b3  and     rcx, r14
0x1800222b6  add     rcx, 2
0x1800222ba  mov     eax, 0FFFFFFFFh
0x1800222bf  cmp     rcx, rax
0x1800222c2  ja      loc_18002237F
0x1800222c8  mov     [rsp+60h+samDesired], ecx; cbData
0x1800222cc  mov     qword ptr [rsp+60h+dwOptions], r12; lpData
0x1800222d1  lea     r9d, [r15+1]; dwType
0x1800222d5  xor     r8d, r8d; Reserved
0x1800222d8  mov     rdx, r13; lpValueName
0x1800222db  mov     rcx, [rbp+hKey]; hKey
0x1800222df  call    cs:__imp_RegSetValueExW
0x1800222e5  mov     r15d, eax
0x1800222e8  xor     esi, esi
0x1800222ea  mov     rcx, [rbp+hKey]; hKey
0x1800222ee  test    rcx, rcx
0x1800222f1  jz      short loc_1800222FD
0x1800222f3  call    cs:__imp_RegCloseKey
0x1800222f9  mov     [rbp+hKey], rsi
0x1800222fd  test    r15d, r15d
0x180022300  jnz     short loc_180022336
0x180022302  mov     ecx, edi; dwErrCode
0x180022304  call    cs:__imp_SetLastError
0x18002230a  nop
0x18002230b  test    rbx, rbx
0x18002230e  jz      short loc_180022319
0x180022310  mov     rcx, rbx; hMem
0x180022313  call    cs:__imp_LocalFree
0x180022319  mov     eax, 1
0x18002231e  mov     rbx, [rsp+60h+arg_8]
0x180022326  add     rsp, 60h
0x18002232a  pop     r15
0x18002232c  pop     r14
0x18002232e  pop     r13
0x180022330  pop     r12
0x180022332  pop     rdi
0x180022333  pop     rsi
0x180022334  pop     rbp
0x180022335  retn
0x180022336  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18002233c  jnz     loc_1800223DD
0x180022342  mov     ecx, edi; dwErrCode
0x180022344  call    cs:__imp_SetLastError
0x18002234a  nop
0x18002234b  test    rbx, rbx
0x18002234e  jz      short loc_180022359
0x180022350  mov     rcx, rbx; hMem
0x180022353  call    cs:__imp_LocalFree
0x180022359  xor     eax, eax
0x18002235b  jmp     short loc_18002231E
0x18002235d  mov     ecx, 57h ; 'W'; dwErrCode
0x180022362  call    cs:__imp_SetLastError
0x180022368  nop
0x180022369  jmp     short loc_180022359
0x18002236b  mov     ecx, edi; dwErrCode
0x18002236d  call    cs:__imp_SetLastError
0x180022373  nop
0x180022374  lea     rcx, [rbp+lpSubKey]
0x180022378  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18002237d  jmp     short loc_180022359
0x18002237f  xor     esi, esi
0x180022381  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180022387  jz      loc_1800222EA
0x18002238d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180022394  test    rax, rax
0x180022397  jz      short loc_1800223AD
0x180022399  lea     rdx, aSizettodwordFa_1; "SizeTToDWord() Failed to convert to DWO"...
0x1800223a0  lea     ecx, [rsi+2]
0x1800223a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223a8  jmp     loc_1800222EA
0x1800223ad  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800223b4  jz      loc_1800222EA
0x1800223ba  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800223c1  jz      loc_1800222EA
0x1800223c7  lea     rdx, aSizettodwordFa_1; "SizeTToDWord() Failed to convert to DWO"...
0x1800223ce  mov     ecx, 2; unsigned int
0x1800223d3  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800223d8  jmp     loc_1800222EA
0x1800223dd  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800223e4  test    rax, rax
0x1800223e7  jz      short loc_180022402
0x1800223e9  mov     r8d, r15d
0x1800223ec  lea     rdx, aSavecachedstri; "SaveCachedString: failed with error: %d"
0x1800223f3  mov     ecx, 2
0x1800223f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223fd  jmp     loc_180022342
0x180022402  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180022409  jz      loc_180022342
0x18002240f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180022416  jz      loc_180022342
0x18002241c  mov     r8d, r15d
0x18002241f  lea     rdx, aSavecachedstri; "SaveCachedString: failed with error: %d"
0x180022426  mov     ecx, 2; unsigned int
0x18002242b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180022430  jmp     loc_180022342
```
