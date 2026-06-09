# FreeRepairInfos(tagRepairInfo *,ulong,int)

- ea: `0x180017d20`
- end: `0x180017e19`
- name: `?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z`
- size: `249`
- prototype: `void __fastcall(struct tagRepairInfo *pv, unsigned int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000da10`
- `0x180017ac4`

## callees

- `0x180017d20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017d53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017d67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017d88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017d9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017dac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017dbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017ddc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017e06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017d53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017d67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017d88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017d9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017dac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017dbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017ddc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017e06`

## pseudocode

```c
void __fastcall FreeRepairInfos(struct tagRepairInfo *pv, unsigned int a2, int a3)
{
  unsigned int v6; // esi
  __int64 v7; // rbp
  __int64 v8; // rbx
  LPWSTR pwszDescription; // rcx
  UiInfo *p_UiInfo; // rbx
  LPWSTR pwszFile; // rcx
  LPWSTR pwzNull; // rcx
  LPWSTR pwszParameters; // rcx

  if ( pv && a2 )
  {
    v6 = 0;
    v7 = 0;
    do
    {
      v8 = v7;
      CoTaskMemFree(pv[v7].pwszClassName);
      pwszDescription = pv[v7].pwszDescription;
      pv[v8].pwszClassName = 0;
      CoTaskMemFree(pwszDescription);
      pv[v8].pwszDescription = 0;
      p_UiInfo = &pv[v7].UiInfo;
      if ( p_UiInfo )
      {
        if ( p_UiInfo->type == UIT_SHELL_COMMAND )
        {
          CoTaskMemFree(p_UiInfo->ShellInfo.pwszDirectory);
          pwszFile = p_UiInfo->ShellInfo.pwszFile;
          p_UiInfo->ShellInfo.pwszDirectory = 0;
          CoTaskMemFree(pwszFile);
          pwzNull = p_UiInfo->pwzNull;
          p_UiInfo->ShellInfo.pwszFile = 0;
          CoTaskMemFree(pwzNull);
          pwszParameters = p_UiInfo->ShellInfo.pwszParameters;
          p_UiInfo->pwzNull = 0;
          CoTaskMemFree(pwszParameters);
          p_UiInfo->ShellInfo.pwszParameters = 0;
        }
        else if ( p_UiInfo->type == UIT_HELP_PANE || p_UiInfo->type == UIT_DUI )
        {
          CoTaskMemFree(p_UiInfo->pwzNull);
          p_UiInfo->pwzNull = 0;
        }
        p_UiInfo->type = UIT_NONE;
      }
      ++v6;
      ++v7;
    }
    while ( v6 < a2 );
    if ( a3 )
      CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x180017d20  test    rcx, rcx
0x180017d23  jz      locret_180017E18
0x180017d29  push    rbx
0x180017d2a  push    rbp
0x180017d2b  push    rsi
0x180017d2c  push    rdi
0x180017d2d  push    r14
0x180017d2f  push    r15
0x180017d31  sub     rsp, 28h
0x180017d35  mov     r15d, r8d
0x180017d38  mov     r14d, edx
0x180017d3b  mov     rdi, rcx
0x180017d3e  test    edx, edx
0x180017d40  jz      loc_180017E0C
0x180017d46  xor     esi, esi
0x180017d48  xor     ebp, ebp
0x180017d4a  imul    rbx, rbp, 70h ; 'p'
0x180017d4e  mov     rcx, [rbx+rdi+10h]; pv
0x180017d53  call    cs:__imp_CoTaskMemFree
0x180017d59  mov     rcx, [rbx+rdi+18h]; pv
0x180017d5e  mov     qword ptr [rbx+rdi+10h], 0
0x180017d67  call    cs:__imp_CoTaskMemFree
0x180017d6d  mov     qword ptr [rbx+rdi+18h], 0
0x180017d76  add     rbx, 38h ; '8'
0x180017d7a  add     rbx, rdi
0x180017d7d  jz      short loc_180017DF0
0x180017d7f  cmp     dword ptr [rbx], 2
0x180017d82  jnz     short loc_180017DCE
0x180017d84  mov     rcx, [rbx+20h]; pv
0x180017d88  call    cs:__imp_CoTaskMemFree
0x180017d8e  mov     rcx, [rbx+10h]; pv
0x180017d92  mov     qword ptr [rbx+20h], 0
0x180017d9a  call    cs:__imp_CoTaskMemFree
0x180017da0  mov     rcx, [rbx+8]; pv
0x180017da4  mov     qword ptr [rbx+10h], 0
0x180017dac  call    cs:__imp_CoTaskMemFree
0x180017db2  mov     rcx, [rbx+18h]; pv
0x180017db6  mov     qword ptr [rbx+8], 0
0x180017dbe  call    cs:__imp_CoTaskMemFree
0x180017dc4  mov     qword ptr [rbx+18h], 0
0x180017dcc  jmp     short loc_180017DEA
0x180017dce  cmp     dword ptr [rbx], 3
0x180017dd1  jz      short loc_180017DD8
0x180017dd3  cmp     dword ptr [rbx], 4
0x180017dd6  jnz     short loc_180017DEA
0x180017dd8  mov     rcx, [rbx+8]; pv
0x180017ddc  call    cs:__imp_CoTaskMemFree
0x180017de2  mov     qword ptr [rbx+8], 0
0x180017dea  mov     dword ptr [rbx], 1
0x180017df0  inc     esi
0x180017df2  inc     rbp
0x180017df5  cmp     esi, r14d
0x180017df8  jb      loc_180017D4A
0x180017dfe  test    r15d, r15d
0x180017e01  jz      short loc_180017E0C
0x180017e03  mov     rcx, rdi; pv
0x180017e06  call    cs:__imp_CoTaskMemFree
0x180017e0c  add     rsp, 28h
0x180017e10  pop     r15
0x180017e12  pop     r14
0x180017e14  pop     rdi
0x180017e15  pop     rsi
0x180017e16  pop     rbp
0x180017e17  pop     rbx
0x180017e18  retn
```
