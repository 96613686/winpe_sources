# FreeRepairInfos(tagRepairInfo *,ulong,int)

- ea: `0x180005ff8`
- end: `0x1800060f1`
- name: `?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z`
- size: `249`
- prototype: `void __fastcall(struct tagRepairInfo *pv, unsigned int, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800057d4`
- `0x18000b098`
- `0x180011e30`
- `0x18001a4e4`

## callees

- `0x180005ff8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000602b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000603f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006060`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006072`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006084`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000602b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000603f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006060`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006072`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006084`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060de`

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
0x180005ff8  test    rcx, rcx
0x180005ffb  jz      locret_1800060F0
0x180006001  push    rbx
0x180006002  push    rbp
0x180006003  push    rsi
0x180006004  push    rdi
0x180006005  push    r14
0x180006007  push    r15
0x180006009  sub     rsp, 28h
0x18000600d  mov     r15d, r8d
0x180006010  mov     r14d, edx
0x180006013  mov     rdi, rcx
0x180006016  test    edx, edx
0x180006018  jz      loc_1800060E4
0x18000601e  xor     esi, esi
0x180006020  xor     ebp, ebp
0x180006022  imul    rbx, rbp, 70h ; 'p'
0x180006026  mov     rcx, [rbx+rdi+10h]; pv
0x18000602b  call    cs:__imp_CoTaskMemFree
0x180006031  mov     rcx, [rbx+rdi+18h]; pv
0x180006036  mov     qword ptr [rbx+rdi+10h], 0
0x18000603f  call    cs:__imp_CoTaskMemFree
0x180006045  mov     qword ptr [rbx+rdi+18h], 0
0x18000604e  add     rbx, 38h ; '8'
0x180006052  add     rbx, rdi
0x180006055  jz      short loc_1800060C8
0x180006057  cmp     dword ptr [rbx], 2
0x18000605a  jnz     short loc_1800060A6
0x18000605c  mov     rcx, [rbx+20h]; pv
0x180006060  call    cs:__imp_CoTaskMemFree
0x180006066  mov     rcx, [rbx+10h]; pv
0x18000606a  mov     qword ptr [rbx+20h], 0
0x180006072  call    cs:__imp_CoTaskMemFree
0x180006078  mov     rcx, [rbx+8]; pv
0x18000607c  mov     qword ptr [rbx+10h], 0
0x180006084  call    cs:__imp_CoTaskMemFree
0x18000608a  mov     rcx, [rbx+18h]; pv
0x18000608e  mov     qword ptr [rbx+8], 0
0x180006096  call    cs:__imp_CoTaskMemFree
0x18000609c  mov     qword ptr [rbx+18h], 0
0x1800060a4  jmp     short loc_1800060C2
0x1800060a6  cmp     dword ptr [rbx], 3
0x1800060a9  jz      short loc_1800060B0
0x1800060ab  cmp     dword ptr [rbx], 4
0x1800060ae  jnz     short loc_1800060C2
0x1800060b0  mov     rcx, [rbx+8]; pv
0x1800060b4  call    cs:__imp_CoTaskMemFree
0x1800060ba  mov     qword ptr [rbx+8], 0
0x1800060c2  mov     dword ptr [rbx], 1
0x1800060c8  inc     esi
0x1800060ca  inc     rbp
0x1800060cd  cmp     esi, r14d
0x1800060d0  jb      loc_180006022
0x1800060d6  test    r15d, r15d
0x1800060d9  jz      short loc_1800060E4
0x1800060db  mov     rcx, rdi; pv
0x1800060de  call    cs:__imp_CoTaskMemFree
0x1800060e4  add     rsp, 28h
0x1800060e8  pop     r15
0x1800060ea  pop     r14
0x1800060ec  pop     rdi
0x1800060ed  pop     rsi
0x1800060ee  pop     rbp
0x1800060ef  pop     rbx
0x1800060f0  retn
```
