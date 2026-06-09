# FreeRepairInfos(tagRepairInfo *,ulong,int)

- ea: `0x18000d2f8`
- end: `0x18000d426`
- name: `?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z`
- size: `302`
- prototype: `void __fastcall(struct tagRepairInfo *pv, unsigned int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180009250`
- `0x18000cf64`

## callees

- `0x18000d2f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d32b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d345`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d370`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d388`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d3a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d3b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d3dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d40c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d32b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d345`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d370`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d388`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d3a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d3b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d3dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d40c`

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
0x18000d2f8  test    rcx, rcx
0x18000d2fb  jz      locret_18000D424
0x18000d301  push    rbx
0x18000d302  push    rbp
0x18000d303  push    rsi
0x18000d304  push    rdi
0x18000d305  push    r14
0x18000d307  push    r15
0x18000d309  sub     rsp, 28h
0x18000d30d  mov     r15d, r8d
0x18000d310  mov     r14d, edx
0x18000d313  mov     rdi, rcx
0x18000d316  test    edx, edx
0x18000d318  jz      loc_18000D418
0x18000d31e  xor     esi, esi
0x18000d320  xor     ebp, ebp
0x18000d322  imul    rbx, rbp, 70h ; 'p'
0x18000d326  mov     rcx, [rbx+rdi+10h]; pv
0x18000d32b  call    cs:__imp_CoTaskMemFree
0x18000d332  nop     dword ptr [rax+rax+00h]
0x18000d337  mov     rcx, [rbx+rdi+18h]; pv
0x18000d33c  mov     qword ptr [rbx+rdi+10h], 0
0x18000d345  call    cs:__imp_CoTaskMemFree
0x18000d34c  nop     dword ptr [rax+rax+00h]
0x18000d351  mov     qword ptr [rbx+rdi+18h], 0
0x18000d35a  add     rbx, 38h ; '8'
0x18000d35e  add     rbx, rdi
0x18000d361  jz      loc_18000D3F6
0x18000d367  cmp     dword ptr [rbx], 2
0x18000d36a  jnz     short loc_18000D3CE
0x18000d36c  mov     rcx, [rbx+20h]; pv
0x18000d370  call    cs:__imp_CoTaskMemFree
0x18000d377  nop     dword ptr [rax+rax+00h]
0x18000d37c  mov     rcx, [rbx+10h]; pv
0x18000d380  mov     qword ptr [rbx+20h], 0
0x18000d388  call    cs:__imp_CoTaskMemFree
0x18000d38f  nop     dword ptr [rax+rax+00h]
0x18000d394  mov     rcx, [rbx+8]; pv
0x18000d398  mov     qword ptr [rbx+10h], 0
0x18000d3a0  call    cs:__imp_CoTaskMemFree
0x18000d3a7  nop     dword ptr [rax+rax+00h]
0x18000d3ac  mov     rcx, [rbx+18h]; pv
0x18000d3b0  mov     qword ptr [rbx+8], 0
0x18000d3b8  call    cs:__imp_CoTaskMemFree
0x18000d3bf  nop     dword ptr [rax+rax+00h]
0x18000d3c4  mov     qword ptr [rbx+18h], 0
0x18000d3cc  jmp     short loc_18000D3F0
0x18000d3ce  cmp     dword ptr [rbx], 3
0x18000d3d1  jz      short loc_18000D3D8
0x18000d3d3  cmp     dword ptr [rbx], 4
0x18000d3d6  jnz     short loc_18000D3F0
0x18000d3d8  mov     rcx, [rbx+8]; pv
0x18000d3dc  call    cs:__imp_CoTaskMemFree
0x18000d3e3  nop     dword ptr [rax+rax+00h]
0x18000d3e8  mov     qword ptr [rbx+8], 0
0x18000d3f0  mov     dword ptr [rbx], 1
0x18000d3f6  inc     esi
0x18000d3f8  inc     rbp
0x18000d3fb  cmp     esi, r14d
0x18000d3fe  jb      loc_18000D322
0x18000d404  test    r15d, r15d
0x18000d407  jz      short loc_18000D418
0x18000d409  mov     rcx, rdi; pv
0x18000d40c  call    cs:__imp_CoTaskMemFree
0x18000d413  nop     dword ptr [rax+rax+00h]
0x18000d418  add     rsp, 28h
0x18000d41c  pop     r15
0x18000d41e  pop     r14
0x18000d420  pop     rdi
0x18000d421  pop     rsi
0x18000d422  pop     rbp
0x18000d423  pop     rbx
0x18000d424  retn
```
