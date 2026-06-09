# IERunsAsDifferentUser(void)

- ea: `0x1800624f0`
- end: `0x18006259e`
- name: `?IERunsAsDifferentUser@@YAHXZ`
- size: `174`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180018410`
- `0x1800329b0`
- `0x1800624f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180062536`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180062536`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062580`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006258b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062580`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006258b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180062559`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180062559`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18006251e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18006251e`
- `ext-ms-win-ntuser-window-l1-1-0!GetShellWindow` at `0x18006250b`
- `ext-ms-win-ntuser-window-l1-1-0!GetShellWindow` at `0x18006250b`

## pseudocode

```c
_BOOL8 IERunsAsDifferentUser(void)
{
  PSID v0; // rbx
  BOOL v1; // edi
  HWND ShellWindow; // rax
  unsigned int ProcessSid; // eax
  DWORD CurrentProcessId; // eax
  unsigned int v5; // eax
  DWORD dwProcessId; // [rsp+30h] [rbp+8h] BYREF
  PSID pSid1; // [rsp+38h] [rbp+10h] BYREF
  PSID pSid2; // [rsp+40h] [rbp+18h] BYREF

  v0 = 0;
  v1 = 0;
  pSid1 = 0;
  pSid2 = 0;
  dwProcessId = 0;
  ShellWindow = GetShellWindow();
  if ( ShellWindow )
  {
    GetWindowThreadProcessId(ShellWindow, &dwProcessId);
    ProcessSid = GetProcessSid(dwProcessId, &pSid2);
    if ( ProcessSid )
    {
      if ( ProcessSid == 5 )
        LOBYTE(v1) = (unsigned __int8)IEConfiguration_GetBool(536870915) == 0;
    }
    else
    {
      CurrentProcessId = GetCurrentProcessId();
      v5 = GetProcessSid(CurrentProcessId, &pSid1);
      v0 = pSid1;
      if ( !v5 )
        v1 = !EqualSid(pSid1, pSid2);
    }
    LocalFree(v0);
    LocalFree(pSid2);
  }
  return v1;
}

```

## disassembly

```asm
0x1800624f0  mov     rax, rsp
0x1800624f3  mov     [rax+20h], rbx
0x1800624f7  push    rdi
0x1800624f8  sub     rsp, 20h
0x1800624fc  xor     ebx, ebx
0x1800624fe  xor     edi, edi
0x180062500  mov     [rax+10h], rbx
0x180062504  mov     [rax+18h], rbx
0x180062508  mov     [rax+8], ebx
0x18006250b  call    cs:__imp_GetShellWindow
0x180062511  test    rax, rax
0x180062514  jz      short loc_180062591
0x180062516  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x18006251b  mov     rcx, rax; hWnd
0x18006251e  call    cs:__imp_GetWindowThreadProcessId
0x180062524  mov     ecx, [rsp+28h+dwProcessId]; dwProcessId
0x180062528  lea     rdx, [rsp+28h+pSid2]; void **
0x18006252d  call    ?GetProcessSid@@YAKKPEAPEAX@Z; GetProcessSid(ulong,void * *)
0x180062532  test    eax, eax
0x180062534  jnz     short loc_180062568
0x180062536  call    cs:__imp_GetCurrentProcessId
0x18006253c  mov     ecx, eax; dwProcessId
0x18006253e  lea     rdx, [rsp+28h+pSid1]; void **
0x180062543  call    ?GetProcessSid@@YAKKPEAPEAX@Z; GetProcessSid(ulong,void * *)
0x180062548  mov     rbx, [rsp+28h+pSid1]
0x18006254d  test    eax, eax
0x18006254f  jnz     short loc_18006257D
0x180062551  mov     rdx, [rsp+28h+pSid2]; pSid2
0x180062556  mov     rcx, rbx; pSid1
0x180062559  call    cs:__imp_EqualSid
0x18006255f  test    eax, eax
0x180062561  jnz     short loc_18006257D
0x180062563  lea     edi, [rax+1]
0x180062566  jmp     short loc_18006257D
0x180062568  cmp     eax, 5
0x18006256b  jnz     short loc_18006257D
0x18006256d  mov     ecx, 20000003h
0x180062572  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180062577  test    al, al
0x180062579  setz    dil
0x18006257d  mov     rcx, rbx; hMem
0x180062580  call    cs:__imp_LocalFree
0x180062586  mov     rcx, [rsp+28h+pSid2]; hMem
0x18006258b  call    cs:__imp_LocalFree
0x180062591  mov     rbx, [rsp+28h+arg_18]
0x180062596  mov     eax, edi
0x180062598  add     rsp, 20h
0x18006259c  pop     rdi
0x18006259d  retn
```
