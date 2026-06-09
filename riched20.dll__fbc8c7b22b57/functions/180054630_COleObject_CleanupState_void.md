# COleObject::CleanupState(void)

- ea: `0x180054630`
- end: `0x1800546e2`
- name: `?CleanupState@COleObject@@AEAAXXZ`
- size: `178`
- prototype: `void __fastcall(COleObject *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180053f80`
- `0x1800560a8`

## callees

- `0x18002720c`
- `0x180040b40`
- `0x18004277c`
- `0x18004bac8`
- `0x180054630`
- `0x1800551d0`

## import_xrefs

- `GDI32!DeleteObject` at `0x180054697`
- `GDI32!DeleteObject` at `0x180054697`

## pseudocode

```c
void __fastcall COleObject::CleanupState(COleObject *this)
{
  __int64 v1; // rax
  void *v3; // rcx
  void *v4; // rcx

  v1 = *((_QWORD *)this + 8);
  if ( v1 && (*((_BYTE *)this + 160) & 2) == 0 )
  {
    if ( v1 != -128 )
      CNotifyMgr::Remove(
        (CNotifyMgr *)(v1 + 128),
        (struct ITxNotify *)(((unsigned __int64)this + 48) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
    *((_QWORD *)this + 8) = 0;
  }
  COleObject::DisconnectObject(this);
  if ( *((_QWORD *)this + 10) )
    SafeReleaseAndNULL((struct IUnknown **)this + 10);
  v3 = (void *)*((_QWORD *)this + 16);
  if ( v3 )
  {
    DeleteObject(v3);
    *((_QWORD *)this + 16) = 0;
  }
  CW32System::GlobalFree(*((void **)this + 15));
  v4 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 15) = 0;
  if ( v4 )
  {
    CW32System::FreePv(v4);
    *((_QWORD *)this + 17) = 0;
  }
}

```

## disassembly

```asm
0x180054630  push    rbx
0x180054632  sub     rsp, 20h
0x180054636  mov     rax, [rcx+40h]
0x18005463a  mov     rbx, rcx
0x18005463d  test    rax, rax
0x180054640  jz      short loc_180054674
0x180054642  test    byte ptr [rcx+0A0h], 2
0x180054649  jnz     short loc_180054674
0x18005464b  lea     rcx, [rax+80h]; this
0x180054652  test    rcx, rcx
0x180054655  jz      short loc_18005466C
0x180054657  lea     r8, [rbx+30h]
0x18005465b  mov     rax, rbx
0x18005465e  neg     rax
0x180054661  sbb     rdx, rdx
0x180054664  and     rdx, r8; struct ITxNotify *
0x180054667  call    ?Remove@CNotifyMgr@@QEAAXPEAVITxNotify@@@Z; CNotifyMgr::Remove(ITxNotify *)
0x18005466c  mov     qword ptr [rbx+40h], 0
0x180054674  mov     rcx, rbx; this
0x180054677  call    ?DisconnectObject@COleObject@@AEAAXXZ; COleObject::DisconnectObject(void)
0x18005467c  lea     rcx, [rbx+50h]; struct IUnknown **
0x180054680  cmp     qword ptr [rcx], 0
0x180054684  jz      short loc_18005468B
0x180054686  call    ?SafeReleaseAndNULL@@YAXPEAPEAUIUnknown@@@Z; SafeReleaseAndNULL(IUnknown * *)
0x18005468b  mov     rcx, [rbx+80h]; ho
0x180054692  test    rcx, rcx
0x180054695  jz      short loc_1800546AE
0x180054697  call    cs:__imp_DeleteObject
0x18005469e  nop     dword ptr [rax+rax+00h]
0x1800546a3  mov     qword ptr [rbx+80h], 0
0x1800546ae  mov     rcx, [rbx+78h]; void *
0x1800546b2  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x1800546b7  mov     rcx, [rbx+88h]; lpMem
0x1800546be  mov     qword ptr [rbx+78h], 0
0x1800546c6  test    rcx, rcx
0x1800546c9  jz      short loc_1800546DB
0x1800546cb  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x1800546d0  mov     qword ptr [rbx+88h], 0
0x1800546db  add     rsp, 20h
0x1800546df  pop     rbx
0x1800546e0  retn
```
