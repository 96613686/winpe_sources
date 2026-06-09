# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::operator&(void)

- ea: `0x180007c10`
- end: `0x180007c43`
- name: `??I?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAPEAPEAGXZ`
- size: `51`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ac1c`

## callees

- `0x180007c10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c21`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::operator&(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = -1;
  *(_QWORD *)(a1 + 16) = -1;
  return a1;
}

```

## disassembly

```asm
0x180007c10  push    rbx
0x180007c12  sub     rsp, 20h
0x180007c16  mov     rbx, rcx
0x180007c19  mov     rcx, [rcx]; pv
0x180007c1c  test    rcx, rcx
0x180007c1f  jz      short loc_180007C2E
0x180007c21  call    cs:__imp_CoTaskMemFree
0x180007c27  mov     qword ptr [rbx], 0
0x180007c2e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007c32  mov     [rbx+8], rax
0x180007c36  mov     [rbx+10h], rax
0x180007c3a  mov     rax, rbx
0x180007c3d  add     rsp, 20h
0x180007c41  pop     rbx
0x180007c42  retn
```
