# CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)

- ea: `0x18000eca8`
- end: `0x18000ecf0`
- name: `??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z`
- size: `72`
- prototype: `CAutoHKey *(CAutoHKey *__hidden this, HKEY, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000eef0`

## callees

- `0x18000eca8`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18000ecc7`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18000ecc7`

## pseudocode

```c
CAutoHKey *__fastcall CAutoHKey::CAutoHKey(CAutoHKey *this, HKEY a2, const unsigned __int16 *a3, HKEY *a4)
{
  HKEY v6; // rax

  if ( RegCreateKeyW(a2, a3, a4) )
  {
    *a4 = 0;
    v6 = 0;
  }
  else
  {
    v6 = *a4;
  }
  *(_QWORD *)this = v6;
  return this;
}

```

## disassembly

```asm
0x18000eca8  mov     [rsp+arg_0], rbx
0x18000ecad  push    rdi
0x18000ecae  sub     rsp, 20h
0x18000ecb2  mov     rax, r8
0x18000ecb5  mov     r10, rdx
0x18000ecb8  mov     rdi, rcx
0x18000ecbb  mov     rdx, rax; lpSubKey
0x18000ecbe  mov     rcx, r10; hKey
0x18000ecc1  mov     r8, r9; phkResult
0x18000ecc4  mov     rbx, r9
0x18000ecc7  call    cs:__imp_RegCreateKeyW
0x18000eccd  test    eax, eax
0x18000eccf  jz      short loc_18000ECDC
0x18000ecd1  mov     qword ptr [rbx], 0
0x18000ecd8  xor     eax, eax
0x18000ecda  jmp     short loc_18000ECDF
0x18000ecdc  mov     rax, [rbx]
0x18000ecdf  mov     [rdi], rax
0x18000ece2  mov     rax, rdi
0x18000ece5  mov     rbx, [rsp+28h+arg_0]
0x18000ecea  add     rsp, 20h
0x18000ecee  pop     rdi
0x18000ecef  retn
```
