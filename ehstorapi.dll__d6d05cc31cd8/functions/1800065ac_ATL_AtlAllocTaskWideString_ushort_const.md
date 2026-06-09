# ATL::AtlAllocTaskWideString(ushort const *)

- ea: `0x1800065ac`
- end: `0x180006645`
- name: `?AtlAllocTaskWideString@ATL@@YAPEAGPEBG@Z`
- size: `153`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007090`

## callees

- `0x1800062d4`
- `0x1800065ac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000661b`
- `msvcrt!memcpy_s` at `0x18000661b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800065ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800065ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006628`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006628`

## pseudocode

```c
unsigned __int16 *__fastcall ATL::AtlAllocTaskWideString(const unsigned __int16 *Source)
{
  __int64 v2; // rdx
  void *v3; // rax
  void *v4; // rbx
  SIZE_T cb; // [rsp+30h] [rbp+8h] BYREF

  if ( !Source )
    return 0;
  v2 = -1;
  do
    ++v2;
  while ( Source[v2] );
  if ( v2 == -1 )
    return 0;
  cb = v2 + 1;
  if ( (int)ATL::AtlMultiply<unsigned __int64>(&cb, v2 + 1, 2) < 0 )
    return 0;
  v3 = CoTaskMemAlloc(cb);
  v4 = v3;
  if ( !v3 )
    return 0;
  if ( memcpy_s(v3, cb, Source, cb) )
  {
    CoTaskMemFree(v4);
    return 0;
  }
  return (unsigned __int16 *)v4;
}

```

## disassembly

```asm
0x1800065ac  mov     [rsp+arg_8], rbx
0x1800065b1  mov     [rsp+arg_10], rbp
0x1800065b6  push    rdi
0x1800065b7  sub     rsp, 20h
0x1800065bb  xor     ebp, ebp
0x1800065bd  mov     rdi, rcx
0x1800065c0  test    rcx, rcx
0x1800065c3  jz      short loc_18000662E
0x1800065c5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800065c9  inc     rdx
0x1800065cc  cmp     [rcx+rdx*2], bp
0x1800065d0  jnz     short loc_1800065C9
0x1800065d2  mov     rax, rdx
0x1800065d5  not     rax
0x1800065d8  cmp     rax, 1
0x1800065dc  jb      short loc_18000662E
0x1800065de  inc     rdx
0x1800065e1  lea     rcx, [rsp+28h+cb]
0x1800065e6  mov     r8d, 2
0x1800065ec  mov     [rsp+28h+cb], rdx
0x1800065f1  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x1800065f6  test    eax, eax
0x1800065f8  js      short loc_18000662E
0x1800065fa  mov     rcx, [rsp+28h+cb]; cb
0x1800065ff  call    cs:__imp_CoTaskMemAlloc
0x180006605  mov     rbx, rax
0x180006608  test    rax, rax
0x18000660b  jz      short loc_18000662E
0x18000660d  mov     r9, [rsp+28h+cb]; SourceSize
0x180006612  mov     r8, rdi; Source
0x180006615  mov     rdx, r9; DestinationSize
0x180006618  mov     rcx, rax; Destination
0x18000661b  call    cs:__imp_memcpy_s
0x180006621  test    eax, eax
0x180006623  jz      short loc_180006640
0x180006625  mov     rcx, rbx; pv
0x180006628  call    cs:__imp_CoTaskMemFree
0x18000662e  xor     eax, eax
0x180006630  mov     rbx, [rsp+28h+arg_8]
0x180006635  mov     rbp, [rsp+28h+arg_10]
0x18000663a  add     rsp, 20h
0x18000663e  pop     rdi
0x18000663f  retn
0x180006640  mov     rax, rbx
0x180006643  jmp     short loc_180006630
```
