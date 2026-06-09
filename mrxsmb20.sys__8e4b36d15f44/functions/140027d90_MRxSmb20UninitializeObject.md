# MRxSmb20UninitializeObject

- ea: `0x140027d90`
- end: `0x140027e8a`
- name: `MRxSmb20UninitializeObject`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140027d90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140027de0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027de0`
- `rdbss!RxNameCacheFinalize` at `0x140027e05`
- `rdbss!RxNameCacheFinalize` at `0x140027e18`
- `rdbss!RxNameCacheFinalize` at `0x140027e2b`
- `rdbss!RxNameCacheFinalize` at `0x140027e3e`
- `rdbss!RxNameCacheFinalize` at `0x140027e51`
- `rdbss!RxNameCacheFinalize` at `0x140027e64`
- `rdbss!RxNameCacheFinalize` at `0x140027e77`
- `rdbss!RxNameCacheFinalize` at `0x140027e05`
- `rdbss!RxNameCacheFinalize` at `0x140027e18`
- `rdbss!RxNameCacheFinalize` at `0x140027e2b`
- `rdbss!RxNameCacheFinalize` at `0x140027e3e`
- `rdbss!RxNameCacheFinalize` at `0x140027e51`
- `rdbss!RxNameCacheFinalize` at `0x140027e64`
- `rdbss!RxNameCacheFinalize` at `0x140027e77`
- `ksecdd!BCryptDestroyHash` at `0x140027dbd`
- `ksecdd!BCryptDestroyHash` at `0x140027dbd`

## pseudocode

```c
void __fastcall MRxSmb20UninitializeObject(unsigned __int16 *a1)
{
  int v2; // ecx
  void *v3; // rcx
  void *v4; // rcx

  v2 = *a1 - 57857;
  if ( v2 )
  {
    if ( v2 == 5 )
    {
      v3 = (void *)*((_QWORD *)a1 + 62);
      if ( v3 )
      {
        BCryptDestroyHash(v3);
        v4 = (void *)*((_QWORD *)a1 + 63);
        *((_QWORD *)a1 + 62) = 0;
        ExFreePoolWithTag(v4, 0x6D536F48u);
        *((_QWORD *)a1 + 63) = 0;
      }
    }
  }
  else
  {
    RxNameCacheFinalize((PNAME_CACHE_CONTROL)(a1 + 648));
    RxNameCacheFinalize((PNAME_CACHE_CONTROL)(a1 + 96));
    RxNameCacheFinalize((PNAME_CACHE_CONTROL)(a1 + 188));
    RxNameCacheFinalize((PNAME_CACHE_CONTROL)(a1 + 280));
    RxNameCacheFinalize((PNAME_CACHE_CONTROL)(a1 + 372));
    RxNameCacheFinalize((PNAME_CACHE_CONTROL)(a1 + 464));
    RxNameCacheFinalize((PNAME_CACHE_CONTROL)(a1 + 556));
  }
}

```

## disassembly

```asm
0x140027d90  push    rbx
0x140027d92  sub     rsp, 20h
0x140027d96  mov     rbx, rcx
0x140027d99  movzx   ecx, word ptr [rcx]
0x140027d9c  sub     ecx, 0E201h
0x140027da2  jz      short loc_140027DFE
0x140027da4  cmp     ecx, 5
0x140027da7  jnz     loc_140027E83
0x140027dad  mov     rcx, [rbx+1F0h]; hHash
0x140027db4  test    rcx, rcx
0x140027db7  jz      loc_140027E83
0x140027dbd  call    cs:__imp_BCryptDestroyHash
0x140027dc4  nop     dword ptr [rax+rax+00h]
0x140027dc9  mov     rcx, [rbx+1F8h]; P
0x140027dd0  mov     edx, 6D536F48h; Tag
0x140027dd5  mov     qword ptr [rbx+1F0h], 0
0x140027de0  call    cs:__imp_ExFreePoolWithTag
0x140027de7  nop     dword ptr [rax+rax+00h]
0x140027dec  mov     qword ptr [rbx+1F8h], 0
0x140027df7  add     rsp, 20h
0x140027dfb  pop     rbx
0x140027dfc  retn
0x140027dfe  lea     rcx, [rbx+510h]; NameCacheCtl
0x140027e05  call    cs:__imp_RxNameCacheFinalize
0x140027e0c  nop     dword ptr [rax+rax+00h]
0x140027e11  lea     rcx, [rbx+0C0h]; NameCacheCtl
0x140027e18  call    cs:__imp_RxNameCacheFinalize
0x140027e1f  nop     dword ptr [rax+rax+00h]
0x140027e24  lea     rcx, [rbx+178h]; NameCacheCtl
0x140027e2b  call    cs:__imp_RxNameCacheFinalize
0x140027e32  nop     dword ptr [rax+rax+00h]
0x140027e37  lea     rcx, [rbx+230h]; NameCacheCtl
0x140027e3e  call    cs:__imp_RxNameCacheFinalize
0x140027e45  nop     dword ptr [rax+rax+00h]
0x140027e4a  lea     rcx, [rbx+2E8h]; NameCacheCtl
0x140027e51  call    cs:__imp_RxNameCacheFinalize
0x140027e58  nop     dword ptr [rax+rax+00h]
0x140027e5d  lea     rcx, [rbx+3A0h]; NameCacheCtl
0x140027e64  call    cs:__imp_RxNameCacheFinalize
0x140027e6b  nop     dword ptr [rax+rax+00h]
0x140027e70  lea     rcx, [rbx+458h]; NameCacheCtl
0x140027e77  call    cs:__imp_RxNameCacheFinalize
0x140027e7e  nop     dword ptr [rax+rax+00h]
0x140027e83  add     rsp, 20h
0x140027e87  pop     rbx
0x140027e88  retn
```
