# pSpUtilsSetLogPath

- ea: `0x1800076d4`
- end: `0x1800077c8`
- name: `pSpUtilsSetLogPath`
- size: `244`
- prototype: `_BOOL8()`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000729c`
- `0x180007458`

## callees

- `0x180006100`
- `0x180006e28`
- `0x1800076d4`
- `0x1800084ac`
- `0x18000a1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000779a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000779a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007790`

## pseudocode

```c
_BOOL8 pSpUtilsSetLogPath()
{
  wchar_t *v0; // rax
  DWORD LastError; // ebx
  wchar_t *v2; // r8
  __int64 v3; // rdx
  __int64 v4; // rcx
  wchar_t *v5; // rcx
  wchar_t pszSrc[264]; // [rsp+20h] [rbp-228h] BYREF

  v0 = (wchar_t *)g_sputils_WindowsDirectory;
  if ( !g_sputils_WindowsDirectory )
    goto LABEL_2;
  v2 = pszSrc;
  v3 = 260;
  v4 = 2147483646;
  do
  {
    if ( !v4 )
      break;
    if ( !*v0 )
      break;
    *v2++ = *v0++;
    --v4;
    --v3;
  }
  while ( v3 );
  v5 = v2 - 1;
  if ( v3 )
    v5 = v2;
  *v5 = 0;
  if ( v3 )
  {
    if ( !(unsigned int)pSetupConcatenatePaths(pszSrc, L"INF", 260)
      || !(unsigned int)pSpUtilsSetTextLogPath(pszSrc)
      || (LastError = 0, !(unsigned int)pSpUtilsLogSetPath(pszSrc)) )
    {
      LastError = GetLastError();
    }
  }
  else
  {
LABEL_2:
    LastError = 87;
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x1800076d4  mov     [rsp+arg_0], rbx
0x1800076d9  push    rdi
0x1800076da  sub     rsp, 240h
0x1800076e1  mov     rax, cs:__security_cookie
0x1800076e8  xor     rax, rsp
0x1800076eb  mov     [rsp+248h+var_18], rax
0x1800076f3  mov     rax, cs:g_sputils_WindowsDirectory
0x1800076fa  xor     edi, edi
0x1800076fc  test    rax, rax
0x1800076ff  jnz     short loc_18000770B
0x180007701  mov     ebx, 57h ; 'W'
0x180007706  jmp     loc_180007798
0x18000770b  mov     r10d, 104h
0x180007711  lea     r8, [rsp+248h+pszSrc]
0x180007716  mov     edx, r10d
0x180007719  mov     ecx, 7FFFFFFEh
0x18000771e  test    rcx, rcx
0x180007721  jz      short loc_180007742
0x180007723  movzx   r9d, word ptr [rax]
0x180007727  test    r9w, r9w
0x18000772b  jz      short loc_180007742
0x18000772d  mov     [r8], r9w
0x180007731  add     rax, 2
0x180007735  add     r8, 2
0x180007739  dec     rcx
0x18000773c  sub     rdx, 1
0x180007740  jnz     short loc_18000771E
0x180007742  test    rdx, rdx
0x180007745  lea     rcx, [r8-2]
0x180007749  cmovnz  rcx, r8
0x18000774d  mov     [rcx], di
0x180007750  jz      short loc_180007701
0x180007752  mov     ebx, cs:g_sputils_IsOnlineWindowsDirectory
0x180007758  lea     rdx, aInf; "INF"
0x18000775f  mov     r8d, r10d
0x180007762  lea     rcx, [rsp+248h+pszSrc]
0x180007767  call    pSetupConcatenatePaths
0x18000776c  test    eax, eax
0x18000776e  jz      short loc_180007790
0x180007770  mov     edx, ebx
0x180007772  lea     rcx, [rsp+248h+pszSrc]; pszSrc
0x180007777  call    _pSpUtilsSetTextLogPath
0x18000777c  test    eax, eax
0x18000777e  jz      short loc_180007790
0x180007780  lea     rcx, [rsp+248h+pszSrc]; pszSrc
0x180007785  mov     ebx, edi
0x180007787  call    _pSpUtilsLogSetPath
0x18000778c  test    eax, eax
0x18000778e  jnz     short loc_180007798
0x180007790  call    cs:__imp_GetLastError
0x180007796  mov     ebx, eax
0x180007798  mov     ecx, ebx; dwErrCode
0x18000779a  call    cs:__imp_SetLastError
0x1800077a0  test    ebx, ebx
0x1800077a2  mov     eax, edi
0x1800077a4  setz    al
0x1800077a7  mov     rcx, [rsp+248h+var_18]
0x1800077af  xor     rcx, rsp; StackCookie
0x1800077b2  call    __security_check_cookie
0x1800077b7  mov     rbx, [rsp+248h+arg_0]
0x1800077bf  add     rsp, 240h
0x1800077c6  pop     rdi
0x1800077c7  retn
```
