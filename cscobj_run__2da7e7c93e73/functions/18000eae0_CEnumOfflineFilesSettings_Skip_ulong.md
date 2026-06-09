# CEnumOfflineFilesSettings::Skip(ulong)

- ea: `0x18000eae0`
- end: `0x18000eb5f`
- name: `?Skip@CEnumOfflineFilesSettings@@UEAAJK@Z`
- size: `127`
- prototype: `__int64 __fastcall(CEnumOfflineFilesSettings *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000eae0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eb28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eb28`

## pseudocode

```c
__int64 __fastcall CEnumOfflineFilesSettings::Skip(CEnumOfflineFilesSettings *this, int a2)
{
  int v2; // edi
  int v4; // ebx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  v2 = a2;
  if ( !*((_QWORD *)this + 2) )
    return v2 != 0;
  pv = 0;
  if ( !a2 )
    return 0;
  do
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2), &pv);
    if ( v4 )
      break;
    CoTaskMemFree(pv);
    pv = 0;
    --v2;
  }
  while ( v2 );
  if ( v4 >= 0 )
    return v2 != 0;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000eae0  mov     [rsp+arg_8], rbx
0x18000eae5  mov     [rsp+arg_10], rsi
0x18000eaea  push    rdi
0x18000eaeb  sub     rsp, 20h
0x18000eaef  cmp     qword ptr [rcx+10h], 0
0x18000eaf4  mov     edi, edx
0x18000eaf6  mov     rsi, rcx
0x18000eaf9  jz      short loc_18000EB40
0x18000eafb  mov     [rsp+28h+pv], 0
0x18000eb04  test    edx, edx
0x18000eb06  jz      short loc_18000EB44
0x18000eb08  mov     rcx, [rsi+10h]
0x18000eb0c  lea     rdx, [rsp+28h+pv]
0x18000eb11  mov     rax, [rcx]
0x18000eb14  mov     rax, [rax+18h]
0x18000eb18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb1d  mov     ebx, eax
0x18000eb1f  test    eax, eax
0x18000eb21  jnz     short loc_18000EB3C
0x18000eb23  mov     rcx, [rsp+28h+pv]; pv
0x18000eb28  call    cs:__imp_CoTaskMemFree
0x18000eb2e  mov     [rsp+28h+pv], 0
0x18000eb37  add     edi, 0FFFFFFFFh
0x18000eb3a  jnz     short loc_18000EB08
0x18000eb3c  test    ebx, ebx
0x18000eb3e  js      short loc_18000EB4D
0x18000eb40  test    edi, edi
0x18000eb42  jnz     short loc_18000EB48
0x18000eb44  xor     ebx, ebx
0x18000eb46  jmp     short loc_18000EB4D
0x18000eb48  mov     ebx, 1
0x18000eb4d  mov     rsi, [rsp+28h+arg_10]
0x18000eb52  mov     eax, ebx
0x18000eb54  mov     rbx, [rsp+28h+arg_8]
0x18000eb59  add     rsp, 20h
0x18000eb5d  pop     rdi
0x18000eb5e  retn
```
