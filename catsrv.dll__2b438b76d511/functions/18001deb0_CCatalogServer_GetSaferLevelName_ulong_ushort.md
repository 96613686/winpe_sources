# CCatalogServer::GetSaferLevelName(ulong,ushort * *)

- ea: `0x18001deb0`
- end: `0x18001dfad`
- name: `?GetSaferLevelName@CCatalogServer@@AEAAJKPEAPEAG@Z`
- size: `253`
- prototype: `__int64 __fastcall(CCatalogServer *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001db50`

## callees

- `0x18001deb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001def7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001def7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001df88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001df88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001df35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001df35`
- `ADVAPI32!SaferCreateLevel` at `0x18001deed`
- `ADVAPI32!SaferCreateLevel` at `0x18001deed`
- `ADVAPI32!SaferGetLevelInformation` at `0x18001df2b`
- `ADVAPI32!SaferGetLevelInformation` at `0x18001df5f`
- `ADVAPI32!SaferGetLevelInformation` at `0x18001df2b`
- `ADVAPI32!SaferGetLevelInformation` at `0x18001df5f`
- `ADVAPI32!SaferCloseLevel` at `0x18001df9a`
- `ADVAPI32!SaferCloseLevel` at `0x18001df9a`

## pseudocode

```c
signed int __fastcall CCatalogServer::GetSaferLevelName(CCatalogServer *this, DWORD a2, unsigned __int16 **a3)
{
  signed int result; // eax
  unsigned __int16 *v5; // rdi
  unsigned int v6; // ebx
  signed int LastError; // eax
  DWORD dwOutBufferSize; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+44h] [rbp+Ch]
  SAFER_LEVEL_HANDLE LevelHandle; // [rsp+50h] [rbp+18h] BYREF

  v9 = HIDWORD(this);
  *a3 = 0;
  LevelHandle = 0;
  dwOutBufferSize = 0;
  if ( SaferCreateLevel(1u, a2, 1u, &LevelHandle, 0) )
  {
    SaferGetLevelInformation(LevelHandle, SaferObjectFriendlyName, 0, 0, &dwOutBufferSize);
    v5 = (unsigned __int16 *)CoTaskMemAlloc(dwOutBufferSize);
    if ( v5 )
    {
      if ( SaferGetLevelInformation(LevelHandle, SaferObjectFriendlyName, v5, dwOutBufferSize, &dwOutBufferSize) )
      {
        *a3 = v5;
        v6 = 0;
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        CoTaskMemFree(v5);
      }
    }
    else
    {
      v6 = -2147024882;
    }
    SaferCloseLevel(LevelHandle);
    return v6;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18001deb0  mov     rax, rsp
0x18001deb3  mov     [rax+10h], rbx
0x18001deb7  mov     [rax+8], rcx
0x18001debb  push    rdi
0x18001debc  sub     rsp, 30h
0x18001dec0  mov     ecx, 1; dwScopeId
0x18001dec5  mov     qword ptr [r8], 0
0x18001decc  mov     rbx, r8
0x18001decf  mov     qword ptr [rax+18h], 0
0x18001ded7  mov     r8d, ecx; OpenFlags
0x18001deda  mov     dword ptr [rax+8], 0
0x18001dee1  lea     r9, [rax+18h]; pLevelHandle
0x18001dee5  mov     qword ptr [rax-18h], 0
0x18001deed  call    cs:__imp_SaferCreateLevel
0x18001def3  test    eax, eax
0x18001def5  jnz     short loc_18001DF12
0x18001def7  call    cs:__imp_GetLastError
0x18001defd  test    eax, eax
0x18001deff  jle     loc_18001DFA2
0x18001df05  movzx   eax, ax
0x18001df08  or      eax, 80070000h
0x18001df0d  jmp     loc_18001DFA2
0x18001df12  mov     rcx, [rsp+38h+LevelHandle]; LevelHandle
0x18001df17  lea     rax, [rsp+38h+dwOutBufferSize]
0x18001df1c  xor     r9d, r9d; dwInBufferSize
0x18001df1f  mov     [rsp+38h+lpdwOutBufferSize], rax; lpdwOutBufferSize
0x18001df24  xor     r8d, r8d; lpQueryBuffer
0x18001df27  lea     edx, [r9+3]; dwInfoType
0x18001df2b  call    cs:__imp_SaferGetLevelInformation
0x18001df31  mov     ecx, [rsp+38h+dwOutBufferSize]; cb
0x18001df35  call    cs:__imp_CoTaskMemAlloc
0x18001df3b  mov     rdi, rax
0x18001df3e  test    rax, rax
0x18001df41  jz      short loc_18001DF90
0x18001df43  mov     r9d, [rsp+38h+dwOutBufferSize]; dwInBufferSize
0x18001df48  lea     rax, [rsp+38h+dwOutBufferSize]
0x18001df4d  mov     rcx, [rsp+38h+LevelHandle]; LevelHandle
0x18001df52  mov     r8, rdi; lpQueryBuffer
0x18001df55  mov     edx, 3; dwInfoType
0x18001df5a  mov     [rsp+38h+lpdwOutBufferSize], rax; lpdwOutBufferSize
0x18001df5f  call    cs:__imp_SaferGetLevelInformation
0x18001df65  test    eax, eax
0x18001df67  jz      short loc_18001DF70
0x18001df69  mov     [rbx], rdi
0x18001df6c  xor     ebx, ebx
0x18001df6e  jmp     short loc_18001DF95
0x18001df70  call    cs:__imp_GetLastError
0x18001df76  mov     ebx, eax
0x18001df78  test    eax, eax
0x18001df7a  jle     short loc_18001DF85
0x18001df7c  movzx   ebx, ax
0x18001df7f  or      ebx, 80070000h
0x18001df85  mov     rcx, rdi; pv
0x18001df88  call    cs:__imp_CoTaskMemFree
0x18001df8e  jmp     short loc_18001DF95
0x18001df90  mov     ebx, 8007000Eh
0x18001df95  mov     rcx, [rsp+38h+LevelHandle]; hLevelHandle
0x18001df9a  call    cs:__imp_SaferCloseLevel
0x18001dfa0  mov     eax, ebx
0x18001dfa2  mov     rbx, [rsp+38h+arg_8]
0x18001dfa7  add     rsp, 30h
0x18001dfab  pop     rdi
0x18001dfac  retn
```
