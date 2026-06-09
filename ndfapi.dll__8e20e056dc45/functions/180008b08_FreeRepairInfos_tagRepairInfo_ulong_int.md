# FreeRepairInfos(tagRepairInfo *,ulong,int)

- ea: `0x180008b08`
- end: `0x180008c01`
- name: `?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z`
- size: `249`
- prototype: `void __fastcall(struct tagRepairInfo *pv, unsigned int, int)`
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800083d0`
- `0x180008c08`
- `0x18000e2d4`
- `0x18001922c`
- `0x180019590`
- `0x18001977c`
- `0x180019af8`
- `0x18001a610`

## callees

- `0x180008b08`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180008b3b`
- `ole32!CoTaskMemFree` at `0x180008b4f`
- `ole32!CoTaskMemFree` at `0x180008b70`
- `ole32!CoTaskMemFree` at `0x180008b82`
- `ole32!CoTaskMemFree` at `0x180008b94`
- `ole32!CoTaskMemFree` at `0x180008ba6`
- `ole32!CoTaskMemFree` at `0x180008bc4`
- `ole32!CoTaskMemFree` at `0x180008bee`
- `ole32!CoTaskMemFree` at `0x180008b3b`
- `ole32!CoTaskMemFree` at `0x180008b4f`
- `ole32!CoTaskMemFree` at `0x180008b70`
- `ole32!CoTaskMemFree` at `0x180008b82`
- `ole32!CoTaskMemFree` at `0x180008b94`
- `ole32!CoTaskMemFree` at `0x180008ba6`
- `ole32!CoTaskMemFree` at `0x180008bc4`
- `ole32!CoTaskMemFree` at `0x180008bee`

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
0x180008b08  test    rcx, rcx
0x180008b0b  jz      locret_180008C00
0x180008b11  push    rbx
0x180008b12  push    rbp
0x180008b13  push    rsi
0x180008b14  push    rdi
0x180008b15  push    r14
0x180008b17  push    r15
0x180008b19  sub     rsp, 28h
0x180008b1d  mov     r15d, r8d
0x180008b20  mov     r14d, edx
0x180008b23  mov     rdi, rcx
0x180008b26  test    edx, edx
0x180008b28  jz      loc_180008BF4
0x180008b2e  xor     esi, esi
0x180008b30  xor     ebp, ebp
0x180008b32  imul    rbx, rbp, 70h ; 'p'
0x180008b36  mov     rcx, [rbx+rdi+10h]; pv
0x180008b3b  call    cs:__imp_CoTaskMemFree
0x180008b41  mov     rcx, [rbx+rdi+18h]; pv
0x180008b46  mov     qword ptr [rbx+rdi+10h], 0
0x180008b4f  call    cs:__imp_CoTaskMemFree
0x180008b55  mov     qword ptr [rbx+rdi+18h], 0
0x180008b5e  add     rbx, 38h ; '8'
0x180008b62  add     rbx, rdi
0x180008b65  jz      short loc_180008BD8
0x180008b67  cmp     dword ptr [rbx], 2
0x180008b6a  jnz     short loc_180008BB6
0x180008b6c  mov     rcx, [rbx+20h]; pv
0x180008b70  call    cs:__imp_CoTaskMemFree
0x180008b76  mov     rcx, [rbx+10h]; pv
0x180008b7a  mov     qword ptr [rbx+20h], 0
0x180008b82  call    cs:__imp_CoTaskMemFree
0x180008b88  mov     rcx, [rbx+8]; pv
0x180008b8c  mov     qword ptr [rbx+10h], 0
0x180008b94  call    cs:__imp_CoTaskMemFree
0x180008b9a  mov     rcx, [rbx+18h]; pv
0x180008b9e  mov     qword ptr [rbx+8], 0
0x180008ba6  call    cs:__imp_CoTaskMemFree
0x180008bac  mov     qword ptr [rbx+18h], 0
0x180008bb4  jmp     short loc_180008BD2
0x180008bb6  cmp     dword ptr [rbx], 3
0x180008bb9  jz      short loc_180008BC0
0x180008bbb  cmp     dword ptr [rbx], 4
0x180008bbe  jnz     short loc_180008BD2
0x180008bc0  mov     rcx, [rbx+8]; pv
0x180008bc4  call    cs:__imp_CoTaskMemFree
0x180008bca  mov     qword ptr [rbx+8], 0
0x180008bd2  mov     dword ptr [rbx], 1
0x180008bd8  inc     esi
0x180008bda  inc     rbp
0x180008bdd  cmp     esi, r14d
0x180008be0  jb      loc_180008B32
0x180008be6  test    r15d, r15d
0x180008be9  jz      short loc_180008BF4
0x180008beb  mov     rcx, rdi; pv
0x180008bee  call    cs:__imp_CoTaskMemFree
0x180008bf4  add     rsp, 28h
0x180008bf8  pop     r15
0x180008bfa  pop     r14
0x180008bfc  pop     rdi
0x180008bfd  pop     rsi
0x180008bfe  pop     rbp
0x180008bff  pop     rbx
0x180008c00  retn
```
