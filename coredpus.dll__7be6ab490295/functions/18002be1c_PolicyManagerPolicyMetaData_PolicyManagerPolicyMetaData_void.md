# PolicyManagerPolicyMetaData::~PolicyManagerPolicyMetaData(void)

- ea: `0x18002be1c`
- end: `0x18002bee0`
- name: `??1PolicyManagerPolicyMetaData@@QEAA@XZ`
- size: `196`
- prototype: `void __fastcall(PolicyManagerPolicyMetaData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002bee8`

## callees

- `0x18002be1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002beac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002becd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002beac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002becd`

## pseudocode

```c
void __fastcall PolicyManagerPolicyMetaData::~PolicyManagerPolicyMetaData(PolicyManagerPolicyMetaData *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx

  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 5);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)this + 6);
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)this + 7);
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = (void *)*((_QWORD *)this + 9);
  if ( v6 )
    CoTaskMemFree(v6);
  v7 = (void *)*((_QWORD *)this + 11);
  if ( v7 )
    CoTaskMemFree(v7);
  v8 = (void *)*((_QWORD *)this + 13);
  if ( v8 )
    CoTaskMemFree(v8);
  if ( *(_DWORD *)this == 1 || *(_DWORD *)this == 3 )
  {
    v9 = (void *)*((_QWORD *)this + 1);
    if ( v9 )
      CoTaskMemFree(v9);
  }
}

```

## disassembly

```asm
0x18002be1c  push    rbx
0x18002be1e  sub     rsp, 20h
0x18002be22  mov     rbx, rcx
0x18002be25  mov     rcx, [rcx+20h]; pv
0x18002be29  test    rcx, rcx
0x18002be2c  jz      short loc_18002BE3A
0x18002be2e  call    cs:__imp_CoTaskMemFree
0x18002be35  nop     dword ptr [rax+rax+00h]
0x18002be3a  mov     rcx, [rbx+28h]; pv
0x18002be3e  test    rcx, rcx
0x18002be41  jz      short loc_18002BE4F
0x18002be43  call    cs:__imp_CoTaskMemFree
0x18002be4a  nop     dword ptr [rax+rax+00h]
0x18002be4f  mov     rcx, [rbx+30h]; pv
0x18002be53  test    rcx, rcx
0x18002be56  jz      short loc_18002BE64
0x18002be58  call    cs:__imp_CoTaskMemFree
0x18002be5f  nop     dword ptr [rax+rax+00h]
0x18002be64  mov     rcx, [rbx+38h]; pv
0x18002be68  test    rcx, rcx
0x18002be6b  jz      short loc_18002BE79
0x18002be6d  call    cs:__imp_CoTaskMemFree
0x18002be74  nop     dword ptr [rax+rax+00h]
0x18002be79  mov     rcx, [rbx+48h]; pv
0x18002be7d  test    rcx, rcx
0x18002be80  jz      short loc_18002BE8E
0x18002be82  call    cs:__imp_CoTaskMemFree
0x18002be89  nop     dword ptr [rax+rax+00h]
0x18002be8e  mov     rcx, [rbx+58h]; pv
0x18002be92  test    rcx, rcx
0x18002be95  jz      short loc_18002BEA3
0x18002be97  call    cs:__imp_CoTaskMemFree
0x18002be9e  nop     dword ptr [rax+rax+00h]
0x18002bea3  mov     rcx, [rbx+68h]; pv
0x18002bea7  test    rcx, rcx
0x18002beaa  jz      short loc_18002BEB8
0x18002beac  call    cs:__imp_CoTaskMemFree
0x18002beb3  nop     dword ptr [rax+rax+00h]
0x18002beb8  mov     ecx, [rbx]
0x18002beba  sub     ecx, 1
0x18002bebd  jz      short loc_18002BEC4
0x18002bebf  cmp     ecx, 2
0x18002bec2  jnz     short loc_18002BED9
0x18002bec4  mov     rcx, [rbx+8]; pv
0x18002bec8  test    rcx, rcx
0x18002becb  jz      short loc_18002BED9
0x18002becd  call    cs:__imp_CoTaskMemFree
0x18002bed4  nop     dword ptr [rax+rax+00h]
0x18002bed9  add     rsp, 20h
0x18002bedd  pop     rbx
0x18002bede  retn
```
