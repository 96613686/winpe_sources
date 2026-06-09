# CDSLObject::FinalRelease(void)

- ea: `0x18004b428`
- end: `0x18004b53f`
- name: `?FinalRelease@CDSLObject@@QEAAXXZ`
- size: `279`
- prototype: `void __fastcall(CDSLObject *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180030474`
- `0x180030828`

## callees

- `0x18004af94`
- `0x18004b428`
- `0x180087010`

## import_xrefs

- `MSDART!mpFree` at `0x18004b4ea`
- `MSDART!mpFree` at `0x18004b4ea`
- `KERNEL32!CloseHandle` at `0x18004b488`
- `KERNEL32!CloseHandle` at `0x18004b488`
- `ole32!CoUninitialize` at `0x18004b533`
- `ole32!CoUninitialize` at `0x18004b533`
- `ole32!CoTaskMemFree` at `0x18004b4a0`
- `ole32!CoTaskMemFree` at `0x18004b519`
- `ole32!CoTaskMemFree` at `0x18004b4a0`
- `ole32!CoTaskMemFree` at `0x18004b519`

## pseudocode

```c
void __fastcall CDSLObject::FinalRelease(LPVOID *this)
{
  LPVOID v2; // rcx
  LPVOID v3; // rcx
  void *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  LPVOID v8; // rcx
  int v9; // ecx
  void *v10; // rcx

  CDSLObject::CleanUpProviderInformations((CDSLObject *)this);
  v2 = this[131];
  if ( v2 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
    this[131] = 0;
  }
  v3 = this[128];
  if ( v3 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v3 + 16LL))(v3);
    this[128] = 0;
  }
  v4 = this[129];
  if ( v4 )
  {
    CloseHandle(v4);
    this[129] = 0;
  }
  CoTaskMemFree(this[130]);
  v8 = this[134];
  this[130] = 0;
  if ( v8 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
    this[134] = 0;
  }
  while ( 1 )
  {
    v9 = *((_DWORD *)this + 62);
    if ( !v9 )
      break;
    *((_DWORD *)this + 62) = v9 - 1;
    mpFree(this[v9 + 29], v5, v6, v7);
    this[*((int *)this + 62) + 30] = 0;
  }
  v10 = this[32];
  if ( v10 )
  {
    CoTaskMemFree(v10);
    this[32] = 0;
  }
  if ( *((_BYTE *)this + 1056) )
    CoUninitialize();
}

```

## disassembly

```asm
0x18004b428  push    rbx
0x18004b42a  sub     rsp, 20h
0x18004b42e  mov     rbx, rcx
0x18004b431  call    ?CleanUpProviderInformations@CDSLObject@@AEAAXXZ; CDSLObject::CleanUpProviderInformations(void)
0x18004b436  mov     rcx, [rbx+418h]
0x18004b43d  test    rcx, rcx
0x18004b440  jz      short loc_18004B459
0x18004b442  mov     rax, [rcx]
0x18004b445  mov     rax, [rax+10h]
0x18004b449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b44e  mov     qword ptr [rbx+418h], 0
0x18004b459  mov     rcx, [rbx+400h]
0x18004b460  test    rcx, rcx
0x18004b463  jz      short loc_18004B47C
0x18004b465  mov     rax, [rcx]
0x18004b468  mov     rax, [rax+10h]
0x18004b46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b471  mov     qword ptr [rbx+400h], 0
0x18004b47c  mov     rcx, [rbx+408h]; hObject
0x18004b483  test    rcx, rcx
0x18004b486  jz      short loc_18004B499
0x18004b488  call    cs:__imp_CloseHandle
0x18004b48e  mov     qword ptr [rbx+408h], 0
0x18004b499  mov     rcx, [rbx+410h]; pv
0x18004b4a0  call    cs:__imp_CoTaskMemFree
0x18004b4a6  mov     rcx, [rbx+430h]
0x18004b4ad  mov     qword ptr [rbx+410h], 0
0x18004b4b8  test    rcx, rcx
0x18004b4bb  jz      short loc_18004B503
0x18004b4bd  mov     rax, [rcx]
0x18004b4c0  mov     rax, [rax+10h]
0x18004b4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b4c9  mov     qword ptr [rbx+430h], 0
0x18004b4d4  jmp     short loc_18004B503
0x18004b4d6  lea     eax, [rcx-1]
0x18004b4d9  movsxd  rcx, ecx
0x18004b4dc  mov     [rbx+0F8h], eax
0x18004b4e2  mov     rcx, [rbx+rcx*8+0E8h]
0x18004b4ea  call    cs:__imp_mpFree
0x18004b4f0  movsxd  rax, dword ptr [rbx+0F8h]
0x18004b4f7  mov     qword ptr [rbx+rax*8+0F0h], 0
0x18004b503  mov     ecx, [rbx+0F8h]
0x18004b509  test    ecx, ecx
0x18004b50b  jnz     short loc_18004B4D6
0x18004b50d  mov     rcx, [rbx+100h]; pv
0x18004b514  test    rcx, rcx
0x18004b517  jz      short loc_18004B52A
0x18004b519  call    cs:__imp_CoTaskMemFree
0x18004b51f  mov     qword ptr [rbx+100h], 0
0x18004b52a  cmp     byte ptr [rbx+420h], 0
0x18004b531  jz      short loc_18004B539
0x18004b533  call    cs:__imp_CoUninitialize
0x18004b539  add     rsp, 20h
0x18004b53d  pop     rbx
0x18004b53e  retn
```
