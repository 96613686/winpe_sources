# CContainer::QueryInterface(_GUID const &,void * *)

- ea: `0x18000f240`
- end: `0x18000f2f7`
- name: `?QueryInterface@CContainer@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(CContainer *__hidden this, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ac0`
- `0x18000f300`
- `0x18000f310`
- `0x18000f320`

## callees

- `0x18000f240`

## pseudocode

```c
__int64 __fastcall CContainer::QueryInterface(CContainer *this, const struct _GUID *a2, void **a3)
{
  unsigned __int64 v3; // rdx

  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDirectMusicContainer.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDirectMusicContainer.Data4 )
  {
    *a3 = this;
    _InterlockedIncrement((volatile signed __int32 *)this + 12);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDirectMusicObject.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDirectMusicObject.Data4 )
  {
    v3 = (unsigned __int64)this + 8;
LABEL_9:
    *a3 = (void *)(v3 & -(__int64)(this != 0));
    _InterlockedIncrement((volatile signed __int32 *)this + 12);
    return 0;
  }
  if ( (*(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_IDirectMusicObjectP.Data1
     || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_IDirectMusicObjectP.Data4)
    && *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IPersistStream.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IPersistStream.Data4 )
  {
    v3 = (unsigned __int64)this + 16;
    goto LABEL_9;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000f240  mov     rax, [rdx]
0x18000f243  mov     r9, rcx
0x18000f246  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000f24d  jnz     short loc_18000F25C
0x18000f24f  mov     rax, [rdx+8]
0x18000f253  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000f25a  jz      short loc_18000F275
0x18000f25c  mov     rax, [rdx]
0x18000f25f  cmp     rax, qword ptr cs:IID_IDirectMusicContainer.Data1
0x18000f266  jnz     short loc_18000F27E
0x18000f268  mov     rax, [rdx+8]
0x18000f26c  cmp     rax, qword ptr cs:IID_IDirectMusicContainer.Data4
0x18000f273  jnz     short loc_18000F27E
0x18000f275  mov     [r8], r9
0x18000f278  lock inc dword ptr [rcx+30h]
0x18000f27c  jmp     short loc_18000F2AF
0x18000f27e  mov     rax, [rdx]
0x18000f281  cmp     rax, qword ptr cs:IID_IDirectMusicObject.Data1
0x18000f288  jnz     short loc_18000F2B2
0x18000f28a  mov     rax, [rdx+8]
0x18000f28e  cmp     rax, qword ptr cs:IID_IDirectMusicObject.Data4
0x18000f295  jnz     short loc_18000F2B2
0x18000f297  lea     rdx, [rcx+8]
0x18000f29b  mov     rax, r9
0x18000f29e  neg     rax
0x18000f2a1  sbb     rcx, rcx
0x18000f2a4  and     rcx, rdx
0x18000f2a7  mov     [r8], rcx
0x18000f2aa  lock inc dword ptr [r9+30h]
0x18000f2af  xor     eax, eax
0x18000f2b1  retn
0x18000f2b2  mov     rax, [rdx]
0x18000f2b5  cmp     rax, qword ptr cs:IID_IDirectMusicObjectP.Data1
0x18000f2bc  jnz     short loc_18000F2CB
0x18000f2be  mov     rax, [rdx+8]
0x18000f2c2  cmp     rax, qword ptr cs:IID_IDirectMusicObjectP.Data4
0x18000f2c9  jz      short loc_18000F2EA
0x18000f2cb  mov     rax, [rdx]
0x18000f2ce  cmp     rax, qword ptr cs:IID_IPersistStream.Data1
0x18000f2d5  jnz     short loc_18000F2EA
0x18000f2d7  mov     rax, [rdx+8]
0x18000f2db  cmp     rax, qword ptr cs:IID_IPersistStream.Data4
0x18000f2e2  jnz     short loc_18000F2EA
0x18000f2e4  lea     rdx, [rcx+10h]
0x18000f2e8  jmp     short loc_18000F29B
0x18000f2ea  mov     qword ptr [r8], 0
0x18000f2f1  mov     eax, 80004002h
0x18000f2f6  retn
```
