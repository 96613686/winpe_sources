# ScopeWarden__lambda_db437c453d3c1e1d138b56d16ce75663___::_ScopeWarden__lambda_db437c453d3c1e1d138b56d16ce75663___

- ea: `0x18012b3fc`
- end: `0x18012b47a`
- name: `ScopeWarden__lambda_db437c453d3c1e1d138b56d16ce75663___::_ScopeWarden__lambda_db437c453d3c1e1d138b56d16ce75663___`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18012d28c`
- `0x180327eb8`

## callees

- `0x180104d30`
- `0x18012b3fc`
- `0x1802cea88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012b426`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012b438`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012b461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012b46b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012b426`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012b438`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012b461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012b46b`

## pseudocode

```c
void __fastcall ScopeWarden__lambda_db437c453d3c1e1d138b56d16ce75663___::_ScopeWarden__lambda_db437c453d3c1e1d138b56d16ce75663___(
        __int64 *a1)
{
  __int64 v1; // rcx
  LPVOID *v2; // rbx
  _DWORD *v3; // rcx

  v1 = *a1;
  if ( v1 )
  {
    v2 = *(LPVOID **)(v1 + 8);
    v3 = *(_DWORD **)v1;
    if ( *v3 == 1 )
    {
      CoTaskMemFree(v2[1]);
      CoTaskMemFree(v2[6]);
    }
    else if ( *v3 == 3 || *v3 == 5 )
    {
      CoTaskMemFree(v2[9]);
      v2[9] = 0;
      CoTaskMemFree(v2[10]);
      v2[10] = 0;
      FreeCDPComDeviceInfo((__int64)(v2 + 20));
      FreeCDPComEndpoint((__int64)(v2 + 11));
    }
  }
}

```

## disassembly

```asm
0x18012b3fc  push    rbx
0x18012b3fe  sub     rsp, 20h
0x18012b402  mov     rcx, [rcx]
0x18012b405  test    rcx, rcx
0x18012b408  jz      short loc_18012B474
0x18012b40a  mov     rbx, [rcx+8]
0x18012b40e  mov     rcx, [rcx]
0x18012b411  mov     edx, [rcx]
0x18012b413  sub     edx, 1
0x18012b416  jz      short loc_18012B45D
0x18012b418  sub     edx, 2
0x18012b41b  jz      short loc_18012B422
0x18012b41d  cmp     edx, 2
0x18012b420  jnz     short loc_18012B472
0x18012b422  mov     rcx, [rbx+48h]; pv
0x18012b426  call    cs:__imp_CoTaskMemFree
0x18012b42c  mov     qword ptr [rbx+48h], 0
0x18012b434  mov     rcx, [rbx+50h]; pv
0x18012b438  call    cs:__imp_CoTaskMemFree
0x18012b43e  mov     qword ptr [rbx+50h], 0
0x18012b446  lea     rcx, [rbx+0A0h]
0x18012b44d  call    FreeCDPComDeviceInfo
0x18012b452  lea     rcx, [rbx+58h]
0x18012b456  call    FreeCDPComEndpoint
0x18012b45b  jmp     short loc_18012B472
0x18012b45d  mov     rcx, [rbx+8]; pv
0x18012b461  call    cs:__imp_CoTaskMemFree
0x18012b467  mov     rcx, [rbx+30h]; pv
0x18012b46b  call    cs:__imp_CoTaskMemFree
0x18012b471  nop
0x18012b472  jmp     short $+2
0x18012b474  add     rsp, 20h
0x18012b478  pop     rbx
0x18012b479  retn
```
