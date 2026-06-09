# PolicyManagerPolicyMetaData::~PolicyManagerPolicyMetaData(void)

- ea: `0x1800456fc`
- end: `0x1800457c0`
- name: `??1PolicyManagerPolicyMetaData@@QEAA@XZ`
- size: `196`
- prototype: `void __fastcall(PolicyManagerPolicyMetaData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800457c8`

## callees

- `0x1800456fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004570e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004574d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045777`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004578c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800457ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004570e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004574d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045777`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004578c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800457ad`

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
0x1800456fc  push    rbx
0x1800456fe  sub     rsp, 20h
0x180045702  mov     rbx, rcx
0x180045705  mov     rcx, [rcx+20h]; pv
0x180045709  test    rcx, rcx
0x18004570c  jz      short loc_18004571A
0x18004570e  call    cs:__imp_CoTaskMemFree
0x180045715  nop     dword ptr [rax+rax+00h]
0x18004571a  mov     rcx, [rbx+28h]; pv
0x18004571e  test    rcx, rcx
0x180045721  jz      short loc_18004572F
0x180045723  call    cs:__imp_CoTaskMemFree
0x18004572a  nop     dword ptr [rax+rax+00h]
0x18004572f  mov     rcx, [rbx+30h]; pv
0x180045733  test    rcx, rcx
0x180045736  jz      short loc_180045744
0x180045738  call    cs:__imp_CoTaskMemFree
0x18004573f  nop     dword ptr [rax+rax+00h]
0x180045744  mov     rcx, [rbx+38h]; pv
0x180045748  test    rcx, rcx
0x18004574b  jz      short loc_180045759
0x18004574d  call    cs:__imp_CoTaskMemFree
0x180045754  nop     dword ptr [rax+rax+00h]
0x180045759  mov     rcx, [rbx+48h]; pv
0x18004575d  test    rcx, rcx
0x180045760  jz      short loc_18004576E
0x180045762  call    cs:__imp_CoTaskMemFree
0x180045769  nop     dword ptr [rax+rax+00h]
0x18004576e  mov     rcx, [rbx+58h]; pv
0x180045772  test    rcx, rcx
0x180045775  jz      short loc_180045783
0x180045777  call    cs:__imp_CoTaskMemFree
0x18004577e  nop     dword ptr [rax+rax+00h]
0x180045783  mov     rcx, [rbx+68h]; pv
0x180045787  test    rcx, rcx
0x18004578a  jz      short loc_180045798
0x18004578c  call    cs:__imp_CoTaskMemFree
0x180045793  nop     dword ptr [rax+rax+00h]
0x180045798  mov     ecx, [rbx]
0x18004579a  sub     ecx, 1
0x18004579d  jz      short loc_1800457A4
0x18004579f  cmp     ecx, 2
0x1800457a2  jnz     short loc_1800457B9
0x1800457a4  mov     rcx, [rbx+8]; pv
0x1800457a8  test    rcx, rcx
0x1800457ab  jz      short loc_1800457B9
0x1800457ad  call    cs:__imp_CoTaskMemFree
0x1800457b4  nop     dword ptr [rax+rax+00h]
0x1800457b9  add     rsp, 20h
0x1800457bd  pop     rbx
0x1800457be  retn
```
