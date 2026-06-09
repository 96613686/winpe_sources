# DrSetFileInfo(_RX_CONTEXT *)

- ea: `0x1400172d0`
- end: `0x140017373`
- name: `?DrSetFileInfo@@YAJPEAU_RX_CONTEXT@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(struct _RX_CONTEXT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callees

- `0x140001050`
- `0x1400016a0`
- `0x14000324c`
- `0x140006560`
- `0x1400172d0`

## pseudocode

```c
__int64 __fastcall DrSetFileInfo(struct _RX_CONTEXT *a1)
{
  int RdbssDbgExtension; // eax
  unsigned int v3; // ebx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  v5 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
  RdbssDbgExtension = (int)a1->RdbssDbgExtension;
  if ( (RdbssDbgExtension & 0x1000) != 0 )
  {
    if ( (RdbssDbgExtension & 2) == 0 )
    {
      BYTE3(a1->RealDevice) = 1;
      v3 = -1069481981;
      goto LABEL_11;
    }
    LODWORD(a1->RdbssDbgExtension) = RdbssDbgExtension & 0xFFFFEFFF;
  }
  if ( (unsigned int)GetDeviceFromRxContext(a1, &v5) )
    v3 = (*(__int64 (__fastcall **)(__int64, struct _RX_CONTEXT *))(*(_QWORD *)v5 + 192LL))(v5, a1);
  else
    v3 = -1073741823;
LABEL_11:
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v5);
  return v3;
}

```

## disassembly

```asm
0x1400172d0  push    rbx
0x1400172d2  sub     rsp, 20h
0x1400172d6  mov     rbx, rcx
0x1400172d9  mov     [rsp+28h+arg_0], 0
0x1400172e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400172e9  lea     rax, WPP_GLOBAL_Control
0x1400172f0  cmp     rcx, rax
0x1400172f3  jz      short loc_140017310
0x1400172f5  cmp     byte ptr [rcx+29h], 4
0x1400172f9  jb      short loc_140017310
0x1400172fb  mov     rcx, [rcx+18h]
0x1400172ff  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x140017306  mov     edx, 3Bh ; ';'
0x14001730b  call    WPP_SF_
0x140017310  mov     eax, [rbx+78h]
0x140017313  bt      eax, 0Ch
0x140017317  jnb     short loc_140017324
0x140017319  test    al, 2
0x14001731b  jz      short loc_140017350
0x14001731d  btr     eax, 0Ch
0x140017321  mov     [rbx+78h], eax
0x140017324  lea     rdx, [rsp+28h+arg_0]
0x140017329  mov     rcx, rbx
0x14001732c  call    ?GetDeviceFromRxContext@@YAHPEAU_RX_CONTEXT@@AEAV?$SmartPtr@VDrDevice@@@@@Z; GetDeviceFromRxContext(_RX_CONTEXT *,SmartPtr<DrDevice> &)
0x140017331  test    eax, eax
0x140017333  jz      short loc_14001735B
0x140017335  mov     rcx, [rsp+28h+arg_0]
0x14001733a  mov     rdx, rbx
0x14001733d  mov     rax, [rcx]
0x140017340  mov     rax, [rax+0C0h]
0x140017347  call    _guard_dispatch_icall
0x14001734c  mov     ebx, eax
0x14001734e  jmp     short loc_140017360
0x140017350  mov     byte ptr [rbx+23h], 1
0x140017354  mov     ebx, 0C0410003h
0x140017359  jmp     short loc_140017360
0x14001735b  mov     ebx, 0C0000001h
0x140017360  lea     rcx, [rsp+28h+arg_0]
0x140017365  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001736a  mov     eax, ebx
0x14001736c  add     rsp, 20h
0x140017370  pop     rbx
0x140017371  retn
```
