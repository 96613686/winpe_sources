# CObject::GC_RemoveAndDuplicateInParentList(void)

- ea: `0x18000a958`
- end: `0x18000a9ef`
- name: `?GC_RemoveAndDuplicateInParentList@CObject@@QEAAJXZ`
- size: `151`
- prototype: `__int64 __fastcall(CObject *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180009550`
- `0x18000a1e4`

## callees

- `0x18000a060`
- `0x18000a584`
- `0x18000a958`
- `0x18000a9f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a9a6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a9a6`

## pseudocode

```c
__int64 __fastcall CObject::GC_RemoveAndDuplicateInParentList(CObject *this)
{
  struct CObject *v2; // rax
  CObject *v3; // rax
  struct IDirectMusicObject *v5; // [rsp+20h] [rbp-18h]
  struct IDirectMusicObject **v6; // [rsp+40h] [rbp+8h] BYREF

  v5 = (struct IDirectMusicObject *)*((_QWORD *)this + 23);
  v6 = 0;
  if ( (int)CClass::FindObject(
              *((CClass **)this + 26),
              (CObject *)((char *)this + 8),
              &v6,
              (struct IDirectMusicObject **)this,
              v5) >= 0
    && v6 )
  {
    v2 = 0;
LABEL_6:
    CClass::GC_Replace(*((CClass **)this + 26), this, v2);
    return 0;
  }
  v3 = (CObject *)malloc(0xD8u);
  if ( v3 )
  {
    v2 = CObject::CObject(v3, *((struct CClass **)this + 26), (CObject *)((char *)this + 8));
    if ( v2 )
      goto LABEL_6;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000a958  mov     r11, rsp
0x18000a95b  mov     [r11+10h], rbx
0x18000a95f  push    rdi
0x18000a960  sub     rsp, 30h
0x18000a964  mov     rax, [rcx+0B8h]
0x18000a96b  lea     rdx, [rcx+8]; struct CDescriptor *
0x18000a96f  mov     rbx, rcx
0x18000a972  mov     [r11-18h], rax
0x18000a976  mov     r9, rcx; struct CObject *
0x18000a979  mov     qword ptr [r11+8], 0
0x18000a981  mov     rcx, [rcx+0D0h]; this
0x18000a988  lea     r8, [r11+8]; struct CObject **
0x18000a98c  call    ?FindObject@CClass@@QEAAJPEAVCDescriptor@@PEAPEAVCObject@@PEAV3@PEAUIDirectMusicObject@@@Z; CClass::FindObject(CDescriptor *,CObject * *,CObject *,IDirectMusicObject *)
0x18000a991  test    eax, eax
0x18000a993  js      short loc_18000A9A1
0x18000a995  cmp     [rsp+38h+arg_0], 0
0x18000a99b  jz      short loc_18000A9A1
0x18000a99d  xor     eax, eax
0x18000a99f  jmp     short loc_18000A9C9
0x18000a9a1  mov     ecx, 0D8h; Size
0x18000a9a6  call    cs:__imp_malloc
0x18000a9ac  test    rax, rax
0x18000a9af  jz      short loc_18000A9DF
0x18000a9b1  mov     rdx, [rbx+0D0h]; struct CClass *
0x18000a9b8  lea     r8, [rbx+8]; struct CDescriptor *
0x18000a9bc  mov     rcx, rax; this
0x18000a9bf  call    ??0CObject@@QEAA@PEAVCClass@@PEAVCDescriptor@@@Z; CObject::CObject(CClass *,CDescriptor *)
0x18000a9c4  test    rax, rax
0x18000a9c7  jz      short loc_18000A9DF
0x18000a9c9  mov     rcx, [rbx+0D0h]; this
0x18000a9d0  mov     r8, rax; struct CObject *
0x18000a9d3  mov     rdx, rbx; struct CObject *
0x18000a9d6  call    ?GC_Replace@CClass@@QEAAXPEAVCObject@@0@Z; CClass::GC_Replace(CObject *,CObject *)
0x18000a9db  xor     eax, eax
0x18000a9dd  jmp     short loc_18000A9E4
0x18000a9df  mov     eax, 8007000Eh
0x18000a9e4  mov     rbx, [rsp+38h+arg_8]
0x18000a9e9  add     rsp, 30h
0x18000a9ed  pop     rdi
0x18000a9ee  retn
```
