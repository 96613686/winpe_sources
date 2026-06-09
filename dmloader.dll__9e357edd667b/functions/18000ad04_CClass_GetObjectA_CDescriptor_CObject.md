# CClass::GetObjectA(CDescriptor *,CObject * *)

- ea: `0x18000ad04`
- end: `0x18000ad94`
- name: `?GetObjectA@CClass@@QEAAJPEAVCDescriptor@@PEAPEAVCObject@@@Z`
- size: `144`
- prototype: `__int64 __fastcall(CClass *__hidden this, struct CDescriptor *, struct CObject **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008bc0`
- `0x180008e90`
- `0x180009b20`

## callees

- `0x18000a060`
- `0x18000a584`
- `0x18000ad04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ad42`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ad42`

## pseudocode

```c
__int64 __fastcall CClass::GetObjectA(CClass *this, struct CDescriptor *a2, struct IDirectMusicObject ***a3)
{
  __int64 result; // rax
  CObject *v7; // rax
  struct CObject *v8; // rax

  if ( !a2 )
    return 2147500035LL;
  result = CClass::FindObject(this, a2, a3, 0, 0);
  if ( (int)result < 0 )
  {
    v7 = (CObject *)malloc(0xD8u);
    if ( v7 )
    {
      v8 = CObject::CObject(v7, this, a2);
      *a3 = (struct IDirectMusicObject **)v8;
      if ( v8 )
      {
        *(_QWORD *)v8 = *((_QWORD *)this + 25);
        *((_QWORD *)this + 25) = v8;
        return 0;
      }
    }
    else
    {
      *a3 = 0;
    }
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000ad04  mov     [rsp+arg_0], rbx
0x18000ad09  mov     [rsp+arg_8], rsi
0x18000ad0e  push    rdi
0x18000ad0f  sub     rsp, 30h
0x18000ad13  mov     rdi, r8
0x18000ad16  mov     rsi, rdx
0x18000ad19  mov     rbx, rcx
0x18000ad1c  test    rdx, rdx
0x18000ad1f  jnz     short loc_18000AD28
0x18000ad21  mov     eax, 80004003h
0x18000ad26  jmp     short loc_18000AD84
0x18000ad28  xor     r9d, r9d; struct CObject *
0x18000ad2b  mov     [rsp+38h+var_18], 0; struct IDirectMusicObject *
0x18000ad34  call    ?FindObject@CClass@@QEAAJPEAVCDescriptor@@PEAPEAVCObject@@PEAV3@PEAUIDirectMusicObject@@@Z; CClass::FindObject(CDescriptor *,CObject * *,CObject *,IDirectMusicObject *)
0x18000ad39  test    eax, eax
0x18000ad3b  jns     short loc_18000AD84
0x18000ad3d  mov     ecx, 0D8h; Size
0x18000ad42  call    cs:__imp_malloc
0x18000ad48  test    rax, rax
0x18000ad4b  jz      short loc_18000AD78
0x18000ad4d  mov     r8, rsi; struct CDescriptor *
0x18000ad50  mov     rdx, rbx; struct CClass *
0x18000ad53  mov     rcx, rax; this
0x18000ad56  call    ??0CObject@@QEAA@PEAVCClass@@PEAVCDescriptor@@@Z; CObject::CObject(CClass *,CDescriptor *)
0x18000ad5b  mov     [rdi], rax
0x18000ad5e  test    rax, rax
0x18000ad61  jz      short loc_18000AD7F
0x18000ad63  mov     rcx, [rbx+0C8h]
0x18000ad6a  mov     [rax], rcx
0x18000ad6d  mov     [rbx+0C8h], rax
0x18000ad74  xor     eax, eax
0x18000ad76  jmp     short loc_18000AD84
0x18000ad78  mov     qword ptr [rdi], 0
0x18000ad7f  mov     eax, 8007000Eh
0x18000ad84  mov     rbx, [rsp+38h+arg_0]
0x18000ad89  mov     rsi, [rsp+38h+arg_8]
0x18000ad8e  add     rsp, 30h
0x18000ad92  pop     rdi
0x18000ad93  retn
```
