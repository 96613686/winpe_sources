# CMSMQMessage::GetStorageOfBody(ulong,void *,IStorage * *)

- ea: `0x1800154cc`
- end: `0x1800155c6`
- name: `?GetStorageOfBody@CMSMQMessage@@IEAAJKPEAXPEAPEAUIStorage@@@Z`
- size: `250`
- prototype: `int(CMSMQMessage *__hidden this, unsigned int, void *, struct IStorage **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800155cc`

## callees

- `0x1800154cc`
- `0x180029010`

## import_xrefs

- `KERNEL32!GlobalHandle` at `0x1800154fb`
- `KERNEL32!GlobalHandle` at `0x1800154fb`
- `ole32!StgOpenStorageOnILockBytes` at `0x180015561`
- `ole32!StgOpenStorageOnILockBytes` at `0x180015561`
- `ole32!CreateILockBytesOnHGlobal` at `0x18001550b`
- `ole32!CreateILockBytesOnHGlobal` at `0x18001550b`

## pseudocode

```c
HRESULT __fastcall CMSMQMessage::GetStorageOfBody(CMSMQMessage *this, unsigned int a2, void *a3, struct IStorage **a4)
{
  HGLOBAL v6; // rax
  HRESULT result; // eax
  HRESULT v8; // ebx
  void *v9; // rcx
  LPLOCKBYTES pplkbyt; // [rsp+50h] [rbp+8h] BYREF
  IStorage *ppstgOpen; // [rsp+68h] [rbp+20h] BYREF

  pplkbyt = 0;
  ppstgOpen = 0;
  *a4 = 0;
  v6 = GlobalHandle(a3);
  result = CreateILockBytesOnHGlobal(v6, 0, &pplkbyt);
  if ( result < 0 )
    return result;
  v8 = ((__int64 (__fastcall *)(LPLOCKBYTES, _QWORD))pplkbyt->lpVtbl->SetSize)(pplkbyt, a2);
  if ( v8 < 0 )
    goto LABEL_5;
  v8 = StgOpenStorageOnILockBytes(pplkbyt, 0, 0x12u, 0, 0, &ppstgOpen);
  if ( v8 == -2147286960 )
  {
    v8 = -2147024809;
LABEL_5:
    if ( pplkbyt )
    {
      ((void (__fastcall *)(LPLOCKBYTES))pplkbyt->lpVtbl->Release)(pplkbyt);
      pplkbyt = 0;
    }
    v9 = ppstgOpen;
    goto LABEL_8;
  }
  v9 = pplkbyt;
  *a4 = ppstgOpen;
LABEL_8:
  if ( v9 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
  return v8;
}

```

## disassembly

```asm
0x1800154cc  mov     rax, rsp
0x1800154cf  mov     [rax+10h], rbx
0x1800154d3  mov     [rax+8], rcx
0x1800154d7  push    rdi
0x1800154d8  sub     rsp, 40h
0x1800154dc  mov     rcx, r8; pMem
0x1800154df  mov     qword ptr [rax+8], 0
0x1800154e7  mov     rdi, r9
0x1800154ea  mov     qword ptr [rax+20h], 0
0x1800154f2  mov     ebx, edx
0x1800154f4  mov     qword ptr [r9], 0
0x1800154fb  call    cs:__imp_GlobalHandle
0x180015501  lea     r8, [rsp+48h+pplkbyt]; pplkbyt
0x180015506  xor     edx, edx; fDeleteOnRelease
0x180015508  mov     rcx, rax; hGlobal
0x18001550b  call    cs:__imp_CreateILockBytesOnHGlobal
0x180015511  test    eax, eax
0x180015513  js      loc_1800155AC
0x180015519  mov     rcx, [rsp+48h+pplkbyt]
0x18001551e  mov     dword ptr [rsp+48h+var_18+4], 0
0x180015526  mov     dword ptr [rsp+48h+var_18], ebx
0x18001552a  mov     rdx, [rsp+48h+var_18]
0x18001552f  mov     rax, [rcx]
0x180015532  mov     rax, [rax+30h]
0x180015536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001553b  mov     ebx, eax
0x18001553d  test    eax, eax
0x18001553f  js      short loc_180015575
0x180015541  mov     rcx, [rsp+48h+pplkbyt]; plkbyt
0x180015546  lea     rax, [rsp+48h+arg_18]
0x18001554b  xor     r9d, r9d; snbExclude
0x18001554e  mov     [rsp+48h+ppstgOpen], rax; ppstgOpen
0x180015553  xor     edx, edx; pstgPriority
0x180015555  mov     [rsp+48h+reserved], 0; reserved
0x18001555d  lea     r8d, [r9+12h]; grfMode
0x180015561  call    cs:__imp_StgOpenStorageOnILockBytes
0x180015567  mov     ebx, eax
0x180015569  cmp     eax, 80030050h
0x18001556e  jnz     short loc_1800155B7
0x180015570  mov     ebx, 80070057h
0x180015575  mov     rcx, [rsp+48h+pplkbyt]
0x18001557a  test    rcx, rcx
0x18001557d  jz      short loc_180015594
0x18001557f  mov     rax, [rcx]
0x180015582  mov     rax, [rax+10h]
0x180015586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001558b  mov     [rsp+48h+pplkbyt], 0
0x180015594  mov     rcx, [rsp+48h+arg_18]
0x180015599  test    rcx, rcx
0x18001559c  jz      short loc_1800155AA
0x18001559e  mov     rax, [rcx]
0x1800155a1  mov     rax, [rax+10h]
0x1800155a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155aa  mov     eax, ebx
0x1800155ac  mov     rbx, [rsp+48h+arg_8]
0x1800155b1  add     rsp, 40h
0x1800155b5  pop     rdi
0x1800155b6  retn
0x1800155b7  mov     rax, [rsp+48h+arg_18]
0x1800155bc  mov     rcx, [rsp+48h+pplkbyt]
0x1800155c1  mov     [rdi], rax
0x1800155c4  jmp     short loc_180015599
```
