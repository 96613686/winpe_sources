# CClass::ClearCache(bool)

- ea: `0x18000a1e4`
- end: `0x18000a29e`
- name: `?ClearCache@CClass@@QEAAJ_N@Z`
- size: `186`
- prototype: `__int64 __fastcall(CClass *__hidden this, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000828c`
- `0x180008450`

## callees

- `0x180008918`
- `0x18000a1e4`
- `0x18000a2a4`
- `0x18000a958`
- `0x18000b9b0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CClass::ClearCache(CClass *this)
{
  __int64 *v1; // rbx
  __int64 v3; // rcx
  __int64 *v4; // rdi
  _DWORD *v5; // rax

  v1 = (__int64 *)*((_QWORD *)this + 25);
  if ( v1 )
  {
    do
    {
      CDescriptor::ClearIStream((CDescriptor *)(v1 + 1));
      v3 = v1[23];
      v4 = (__int64 *)*v1;
      if ( v3 )
      {
        if ( (v1[24] & 0x1000) != 0 )
        {
          if ( (int)CObject::GC_RemoveAndDuplicateInParentList((CObject *)v1) >= 0 )
            CLoader::GC_UpdateForReleasedObject(*((CLoader **)this + 23), (struct CObject *)v1);
          v5 = v1 + 2;
        }
        else
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
          v5 = v1 + 2;
          v1[23] = 0;
          *((_DWORD *)v1 + 4) &= ~0x200u;
        }
        if ( (*v5 & 0xC14) == 0 )
          CClass::RemoveObject((CClass *)v1[26], 0);
      }
      v1 = v4;
    }
    while ( v4 );
  }
  return 0;
}

```

## disassembly

```asm
0x18000a1e4  mov     [rsp+arg_0], rbx
0x18000a1e9  mov     [rsp+arg_8], rsi
0x18000a1ee  push    rdi
0x18000a1ef  sub     rsp, 20h
0x18000a1f3  mov     rbx, [rcx+0C8h]
0x18000a1fa  mov     rsi, rcx
0x18000a1fd  test    rbx, rbx
0x18000a200  jz      loc_18000A28C
0x18000a206  lea     rcx, [rbx+8]; this
0x18000a20a  call    ?ClearIStream@CDescriptor@@QEAAXXZ; CDescriptor::ClearIStream(void)
0x18000a20f  mov     rcx, [rbx+0B8h]
0x18000a216  mov     rdi, [rbx]
0x18000a219  test    rcx, rcx
0x18000a21c  jz      short loc_18000A280
0x18000a21e  test    dword ptr [rbx+0C0h], 1000h
0x18000a228  jz      short loc_18000A24B
0x18000a22a  mov     rcx, rbx; this
0x18000a22d  call    ?GC_RemoveAndDuplicateInParentList@CObject@@QEAAJXZ; CObject::GC_RemoveAndDuplicateInParentList(void)
0x18000a232  test    eax, eax
0x18000a234  js      short loc_18000A245
0x18000a236  mov     rcx, [rsi+0B8h]; this
0x18000a23d  mov     rdx, rbx; struct CObject *
0x18000a240  call    ?GC_UpdateForReleasedObject@CLoader@@QEAAXPEAVCObject@@@Z; CLoader::GC_UpdateForReleasedObject(CObject *)
0x18000a245  lea     rax, [rbx+10h]
0x18000a249  jmp     short loc_18000A26A
0x18000a24b  mov     rax, [rcx]
0x18000a24e  mov     rax, [rax+10h]
0x18000a252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a257  lea     rax, [rbx+10h]
0x18000a25b  mov     qword ptr [rbx+0B8h], 0
0x18000a266  btr     dword ptr [rax], 9
0x18000a26a  test    dword ptr [rax], 0C14h
0x18000a270  jnz     short loc_18000A280
0x18000a272  mov     rcx, [rbx+0D0h]; this
0x18000a279  xor     edx, edx; struct CObject *
0x18000a27b  call    ?RemoveObject@CClass@@QEAAXPEAVCObject@@@Z; CClass::RemoveObject(CObject *)
0x18000a280  mov     rbx, rdi
0x18000a283  test    rdi, rdi
0x18000a286  jnz     loc_18000A206
0x18000a28c  mov     rbx, [rsp+28h+arg_0]
0x18000a291  xor     eax, eax
0x18000a293  mov     rsi, [rsp+28h+arg_8]
0x18000a298  add     rsp, 20h
0x18000a29c  pop     rdi
0x18000a29d  retn
```
