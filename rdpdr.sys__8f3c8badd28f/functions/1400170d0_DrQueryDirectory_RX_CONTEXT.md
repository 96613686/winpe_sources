# DrQueryDirectory(_RX_CONTEXT *)

- ea: `0x1400170d0`
- end: `0x140017183`
- name: `?DrQueryDirectory@@YAJPEAU_RX_CONTEXT@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(struct _RX_CONTEXT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x140001050`
- `0x1400016a0`
- `0x14000324c`
- `0x140006560`
- `0x1400170d0`

## pseudocode

```c
__int64 __fastcall DrQueryDirectory(struct _RX_CONTEXT *a1)
{
  unsigned int v2; // ebx
  int RdbssDbgExtension; // eax
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  v5 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
  if ( *((_BYTE *)&a1->9 + 118) )
  {
    v2 = -1073741822;
  }
  else
  {
    RdbssDbgExtension = (int)a1->RdbssDbgExtension;
    if ( (RdbssDbgExtension & 0x1000) != 0 )
    {
      if ( (RdbssDbgExtension & 2) == 0 )
      {
        BYTE3(a1->RealDevice) = 1;
        v2 = -1069481981;
        goto LABEL_13;
      }
      LODWORD(a1->RdbssDbgExtension) = RdbssDbgExtension & 0xFFFFEFFF;
    }
    if ( (unsigned int)GetDeviceFromRxContext(a1, &v5) )
      v2 = (*(__int64 (__fastcall **)(__int64, struct _RX_CONTEXT *))(*(_QWORD *)v5 + 152LL))(v5, a1);
    else
      v2 = -1073741823;
  }
LABEL_13:
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v5);
  return v2;
}

```

## disassembly

```asm
0x1400170d0  push    rbx
0x1400170d2  sub     rsp, 20h
0x1400170d6  mov     rbx, rcx
0x1400170d9  mov     [rsp+28h+arg_0], 0
0x1400170e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400170e9  lea     rax, WPP_GLOBAL_Control
0x1400170f0  cmp     rcx, rax
0x1400170f3  jz      short loc_140017110
0x1400170f5  cmp     byte ptr [rcx+29h], 4
0x1400170f9  jb      short loc_140017110
0x1400170fb  mov     rcx, [rcx+18h]
0x1400170ff  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x140017106  mov     edx, 35h ; '5'
0x14001710b  call    WPP_SF_
0x140017110  cmp     byte ptr [rbx+206h], 0
0x140017117  jz      short loc_140017120
0x140017119  mov     ebx, 0C0000002h
0x14001711e  jmp     short loc_140017170
0x140017120  mov     eax, [rbx+78h]
0x140017123  bt      eax, 0Ch
0x140017127  jnb     short loc_140017134
0x140017129  test    al, 2
0x14001712b  jz      short loc_140017160
0x14001712d  btr     eax, 0Ch
0x140017131  mov     [rbx+78h], eax
0x140017134  lea     rdx, [rsp+28h+arg_0]
0x140017139  mov     rcx, rbx
0x14001713c  call    ?GetDeviceFromRxContext@@YAHPEAU_RX_CONTEXT@@AEAV?$SmartPtr@VDrDevice@@@@@Z; GetDeviceFromRxContext(_RX_CONTEXT *,SmartPtr<DrDevice> &)
0x140017141  test    eax, eax
0x140017143  jz      short loc_14001716B
0x140017145  mov     rcx, [rsp+28h+arg_0]
0x14001714a  mov     rdx, rbx
0x14001714d  mov     rax, [rcx]
0x140017150  mov     rax, [rax+98h]
0x140017157  call    _guard_dispatch_icall
0x14001715c  mov     ebx, eax
0x14001715e  jmp     short loc_140017170
0x140017160  mov     byte ptr [rbx+23h], 1
0x140017164  mov     ebx, 0C0410003h
0x140017169  jmp     short loc_140017170
0x14001716b  mov     ebx, 0C0000001h
0x140017170  lea     rcx, [rsp+28h+arg_0]
0x140017175  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001717a  mov     eax, ebx
0x14001717c  add     rsp, 20h
0x140017180  pop     rbx
0x140017181  retn
```
