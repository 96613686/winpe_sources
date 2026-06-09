# COleObject::CleanupState(void)

- ea: `0x1800531d0`
- end: `0x18005327b`
- name: `?CleanupState@COleObject@@AEAAXXZ`
- size: `171`
- prototype: `void __fastcall(COleObject *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180052b3c`
- `0x180054b50`

## callees

- `0x180023010`
- `0x180040054`
- `0x1800417c8`
- `0x18004a8fc`
- `0x1800531d0`
- `0x180053d4c`

## import_xrefs

- `GDI32!DeleteObject` at `0x180053237`
- `GDI32!DeleteObject` at `0x180053237`

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
0x1800531d0  push    rbx
0x1800531d2  sub     rsp, 20h
0x1800531d6  mov     rax, [rcx+40h]
0x1800531da  mov     rbx, rcx
0x1800531dd  test    rax, rax
0x1800531e0  jz      short loc_180053214
0x1800531e2  test    byte ptr [rcx+0A0h], 2
0x1800531e9  jnz     short loc_180053214
0x1800531eb  lea     rcx, [rax+80h]; this
0x1800531f2  test    rcx, rcx
0x1800531f5  jz      short loc_18005320C
0x1800531f7  lea     r8, [rbx+30h]
0x1800531fb  mov     rax, rbx
0x1800531fe  neg     rax
0x180053201  sbb     rdx, rdx
0x180053204  and     rdx, r8; struct ITxNotify *
0x180053207  call    ?Remove@CNotifyMgr@@QEAAXPEAVITxNotify@@@Z; CNotifyMgr::Remove(ITxNotify *)
0x18005320c  mov     qword ptr [rbx+40h], 0
0x180053214  mov     rcx, rbx; this
0x180053217  call    ?DisconnectObject@COleObject@@AEAAXXZ; COleObject::DisconnectObject(void)
0x18005321c  lea     rcx, [rbx+50h]; struct IUnknown **
0x180053220  cmp     qword ptr [rcx], 0
0x180053224  jz      short loc_18005322B
0x180053226  call    ?SafeReleaseAndNULL@@YAXPEAPEAUIUnknown@@@Z; SafeReleaseAndNULL(IUnknown * *)
0x18005322b  mov     rcx, [rbx+80h]; ho
0x180053232  test    rcx, rcx
0x180053235  jz      short loc_180053248
0x180053237  call    cs:__imp_DeleteObject
0x18005323d  mov     qword ptr [rbx+80h], 0
0x180053248  mov     rcx, [rbx+78h]; void *
0x18005324c  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x180053251  mov     rcx, [rbx+88h]; lpMem
0x180053258  mov     qword ptr [rbx+78h], 0
0x180053260  test    rcx, rcx
0x180053263  jz      short loc_180053275
0x180053265  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x18005326a  mov     qword ptr [rbx+88h], 0
0x180053275  add     rsp, 20h
0x180053279  pop     rbx
0x18005327a  retn
```
