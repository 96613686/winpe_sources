# FreeRepairInfos(tagRepairInfo *,ulong,int)

- ea: `0x18000a6cc`
- end: `0x18000a7c5`
- name: `?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z`
- size: `249`
- prototype: `void __fastcall(struct tagRepairInfo *pv, unsigned int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000a208`

## callees

- `0x18000a6cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a6ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a734`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a746`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a758`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a76a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a788`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a7b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a6ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a734`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a746`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a758`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a76a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a788`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a7b2`

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
0x18000a6cc  test    rcx, rcx
0x18000a6cf  jz      locret_18000A7C4
0x18000a6d5  push    rbx
0x18000a6d6  push    rbp
0x18000a6d7  push    rsi
0x18000a6d8  push    rdi
0x18000a6d9  push    r14
0x18000a6db  push    r15
0x18000a6dd  sub     rsp, 28h
0x18000a6e1  mov     r15d, r8d
0x18000a6e4  mov     r14d, edx
0x18000a6e7  mov     rdi, rcx
0x18000a6ea  test    edx, edx
0x18000a6ec  jz      loc_18000A7B8
0x18000a6f2  xor     esi, esi
0x18000a6f4  xor     ebp, ebp
0x18000a6f6  imul    rbx, rbp, 70h ; 'p'
0x18000a6fa  mov     rcx, [rbx+rdi+10h]; pv
0x18000a6ff  call    cs:__imp_CoTaskMemFree
0x18000a705  mov     rcx, [rbx+rdi+18h]; pv
0x18000a70a  mov     qword ptr [rbx+rdi+10h], 0
0x18000a713  call    cs:__imp_CoTaskMemFree
0x18000a719  mov     qword ptr [rbx+rdi+18h], 0
0x18000a722  add     rbx, 38h ; '8'
0x18000a726  add     rbx, rdi
0x18000a729  jz      short loc_18000A79C
0x18000a72b  cmp     dword ptr [rbx], 2
0x18000a72e  jnz     short loc_18000A77A
0x18000a730  mov     rcx, [rbx+20h]; pv
0x18000a734  call    cs:__imp_CoTaskMemFree
0x18000a73a  mov     rcx, [rbx+10h]; pv
0x18000a73e  mov     qword ptr [rbx+20h], 0
0x18000a746  call    cs:__imp_CoTaskMemFree
0x18000a74c  mov     rcx, [rbx+8]; pv
0x18000a750  mov     qword ptr [rbx+10h], 0
0x18000a758  call    cs:__imp_CoTaskMemFree
0x18000a75e  mov     rcx, [rbx+18h]; pv
0x18000a762  mov     qword ptr [rbx+8], 0
0x18000a76a  call    cs:__imp_CoTaskMemFree
0x18000a770  mov     qword ptr [rbx+18h], 0
0x18000a778  jmp     short loc_18000A796
0x18000a77a  cmp     dword ptr [rbx], 3
0x18000a77d  jz      short loc_18000A784
0x18000a77f  cmp     dword ptr [rbx], 4
0x18000a782  jnz     short loc_18000A796
0x18000a784  mov     rcx, [rbx+8]; pv
0x18000a788  call    cs:__imp_CoTaskMemFree
0x18000a78e  mov     qword ptr [rbx+8], 0
0x18000a796  mov     dword ptr [rbx], 1
0x18000a79c  inc     esi
0x18000a79e  inc     rbp
0x18000a7a1  cmp     esi, r14d
0x18000a7a4  jb      loc_18000A6F6
0x18000a7aa  test    r15d, r15d
0x18000a7ad  jz      short loc_18000A7B8
0x18000a7af  mov     rcx, rdi; pv
0x18000a7b2  call    cs:__imp_CoTaskMemFree
0x18000a7b8  add     rsp, 28h
0x18000a7bc  pop     r15
0x18000a7be  pop     r14
0x18000a7c0  pop     rdi
0x18000a7c1  pop     rsi
0x18000a7c2  pop     rbp
0x18000a7c3  pop     rbx
0x18000a7c4  retn
```
