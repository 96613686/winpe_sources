# ExtSTASetDesiredBSSID(EXTSTA_VELAN *,void *,ulong)

- ea: `0x14006da60`
- end: `0x14006dcb2`
- name: `?ExtSTASetDesiredBSSID@@YAJPEAUEXTSTA_VELAN@@PEAXK@Z`
- size: `594`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x14000a53c`
- `0x140019bbc`
- `0x140020dc0`
- `0x14003b04c`
- `0x140054aa8`
- `0x14006da60`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006db09`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006db09`
- `ntoskrnl!ExAllocatePool2` at `0x14006db1e`
- `ntoskrnl!ExAllocatePool2` at `0x14006db1e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006dc73`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006dc73`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc84`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc84`

## pseudocode

```c
__int64 __fastcall ExtSTASetDesiredBSSID(struct EXTSTA_VELAN *a1, void *a2, unsigned int a3)
{
  size_t v3; // r14
  unsigned __int64 v6; // rsi
  unsigned int v7; // ebp
  unsigned int v8; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  _DWORD *v11; // rdi
  __int64 v12; // r15
  int v13; // edx
  int v14; // ebx
  __int64 v15; // r9
  int v16; // ecx
  __int64 v17; // rax
  unsigned int v18; // ebp

  v3 = a3;
  v6 = a3 / 6uLL;
  if ( a3 != 6 * v6 )
    return (unsigned int)-1073741811;
  if ( a3 < 6 )
    return (unsigned int)-1073741811;
  v7 = a3 + 12;
  if ( a3 + 12 < a3 )
    return (unsigned int)-1073741811;
  v8 = a3 + 28;
  if ( v7 >= 0xFFFFFFF0 )
    return (unsigned int)-1073741670;
  if ( v8 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_13:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_15;
  }
  if ( v8 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_13;
  }
  if ( v8 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_13;
  }
  if ( v8 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_13;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v8, 808464432);
LABEL_15:
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  Pool2[2] = 808464432;
  v11 = Pool2 + 4;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  Pool2[4] = 1311104;
  v12 = (__int64)(Pool2 + 7);
  Pool2[5] = v6;
  Pool2[6] = v6;
  memmove(Pool2 + 7, a2, v3);
  v14 = PtRequestAdapterSync(a1->pGenVElan->pAdapt, 1u, 0xE01017Eu, v11, v7);
  if ( v14 >= 0 )
  {
    v15 = (unsigned int)v11[2];
    if ( (_DWORD)v15 == 1 )
    {
      v16 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, v12);
    }
    else
    {
      v16 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, v15);
        v17 = 0;
        if ( v11[2] )
        {
          do
          {
            v16 = (int)WPP_GLOBAL_Control;
            v18 = v17 + 1;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF_d_MAC_(
                WPP_GLOBAL_Control->AttachedDevice,
                47,
                (unsigned int)WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids,
                v18,
                (__int64)v11 + 6 * v17 + 12);
            v17 = v18;
          }
          while ( v18 < v11[2] );
        }
      }
    }
    if ( (byte_1400B2801 & 1) != 0 )
      McTemplateK0pjqB6r2_EtwWriteTransfer(
        v16,
        v13,
        &a1->pGenVElan->gDeviceId,
        a1->pGenVElan,
        (__int64)&a1->pGenVElan->gDeviceId,
        v11[1],
        v12);
  }
  if ( v11 )
  {
    if ( *((_QWORD *)v11 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v11 - 2), v11 - 4);
    else
      ExFreePoolWithTag(v11 - 4, *(v11 - 2));
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14006da60  push    rbx
0x14006da62  push    rbp
0x14006da63  push    rsi
0x14006da64  push    rdi
0x14006da65  push    r12
0x14006da67  push    r13
0x14006da69  push    r14
0x14006da6b  push    r15
0x14006da6d  sub     rsp, 48h
0x14006da71  mov     r14d, r8d
0x14006da74  mov     rax, 0AAAAAAAAAAAAAAABh
0x14006da7e  mov     r12, rdx
0x14006da81  mov     r13, rcx
0x14006da84  mul     r14
0x14006da87  mov     rsi, rdx
0x14006da8a  shr     rsi, 2
0x14006da8e  lea     r9, [rsi+rsi*2]
0x14006da92  add     r9, r9
0x14006da95  cmp     r14, r9
0x14006da98  jnz     loc_14006DC99
0x14006da9e  cmp     r8d, 6
0x14006daa2  jb      loc_14006DC99
0x14006daa8  lea     ebp, [r8+0Ch]
0x14006daac  cmp     ebp, r8d
0x14006daaf  jb      loc_14006DC99
0x14006dab5  lea     eax, [rbp+10h]
0x14006dab8  cmp     eax, 10h
0x14006dabb  jb      loc_14006DC92
0x14006dac1  mov     ecx, 40h ; '@'
0x14006dac6  mov     edi, 30303030h
0x14006dacb  cmp     eax, ecx
0x14006dacd  ja      short loc_14006DAD8
0x14006dacf  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14006dad6  jmp     short loc_14006DB06
0x14006dad8  cmp     eax, 100h
0x14006dadd  ja      short loc_14006DAE8
0x14006dadf  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006dae6  jmp     short loc_14006DB06
0x14006dae8  cmp     eax, 400h
0x14006daed  ja      short loc_14006DAF8
0x14006daef  lea     rbx, Lookaside
0x14006daf6  jmp     short loc_14006DB06
0x14006daf8  cmp     eax, 800h
0x14006dafd  ja      short loc_14006DB17
0x14006daff  lea     rbx, stru_1400B31C0
0x14006db06  mov     rcx, rbx; Lookaside
0x14006db09  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006db10  nop     dword ptr [rax+rax+00h]
0x14006db15  jmp     short loc_14006DB2A
0x14006db17  xor     ebx, ebx
0x14006db19  mov     edx, eax
0x14006db1b  mov     r8d, edi
0x14006db1e  call    cs:__imp_ExAllocatePool2
0x14006db25  nop     dword ptr [rax+rax+00h]
0x14006db2a  test    rax, rax
0x14006db2d  jz      loc_14006DC92
0x14006db33  mov     [rax+8], edi
0x14006db36  mov     r8, r14; Size
0x14006db39  lea     rdi, [rax+10h]
0x14006db3d  mov     [rax], rbx
0x14006db40  mov     dword ptr [rdi], 140180h
0x14006db46  lea     r15, [rdi+0Ch]
0x14006db4a  mov     [rdi+4], esi
0x14006db4d  mov     rcx, r15; void *
0x14006db50  mov     rdx, r12; Src
0x14006db53  mov     [rdi+8], esi
0x14006db56  call    memmove
0x14006db5b  mov     rcx, [r13+0A38h]
0x14006db62  mov     r9, rdi; void *
0x14006db65  mov     edx, 1; unsigned int
0x14006db6a  mov     [rsp+88h+var_68], ebp; unsigned int
0x14006db6e  mov     r8d, 0E01017Eh; unsigned int
0x14006db74  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006db78  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006db7d  mov     ebx, eax
0x14006db7f  test    eax, eax
0x14006db81  js      loc_14006DC5C
0x14006db87  mov     r9d, [rdi+8]
0x14006db8b  cmp     r9d, 1
0x14006db8f  jnz     short loc_14006DBC1
0x14006db91  mov     rcx, cs:WPP_GLOBAL_Control
0x14006db98  lea     rsi, WPP_GLOBAL_Control
0x14006db9f  cmp     rcx, rsi
0x14006dba2  jz      loc_14006DC2F
0x14006dba8  mov     rcx, [rcx+18h]
0x14006dbac  lea     edx, [r9+2Ch]
0x14006dbb0  mov     r9, r15
0x14006dbb3  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006dbba  call    WPP_SF__MAC_
0x14006dbbf  jmp     short loc_14006DC2F
0x14006dbc1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dbc8  lea     rsi, WPP_GLOBAL_Control
0x14006dbcf  cmp     rcx, rsi
0x14006dbd2  jz      short loc_14006DC2F
0x14006dbd4  mov     rcx, [rcx+18h]
0x14006dbd8  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006dbdf  mov     edx, 2Eh ; '.'
0x14006dbe4  call    WPP_SF_d
0x14006dbe9  xor     eax, eax
0x14006dbeb  cmp     [rdi+8], eax
0x14006dbee  jbe     short loc_14006DC2F
0x14006dbf0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dbf7  lea     ebp, [rax+1]
0x14006dbfa  cmp     rcx, rsi
0x14006dbfd  jz      short loc_14006DC28
0x14006dbff  mov     rcx, [rcx+18h]
0x14006dc03  add     rax, 2
0x14006dc07  mov     edx, 2Fh ; '/'
0x14006dc0c  mov     r9d, ebp
0x14006dc0f  lea     rax, [rax+rax*2]
0x14006dc13  lea     r8, [rdi+rax*2]
0x14006dc17  mov     qword ptr [rsp+88h+var_68], r8
0x14006dc1c  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006dc23  call    WPP_SF_d_MAC_
0x14006dc28  mov     eax, ebp
0x14006dc2a  cmp     eax, [rdi+8]
0x14006dc2d  jb      short loc_14006DBF0
0x14006dc2f  test    cs:byte_1400B2801, 1
0x14006dc36  jz      short loc_14006DC5C
0x14006dc38  mov     r9, [r13+0A38h]
0x14006dc3f  mov     eax, [rdi+4]
0x14006dc42  mov     [rsp+88h+var_58], r15
0x14006dc47  mov     [rsp+88h+var_60], eax
0x14006dc4b  lea     r8, [r9+1338h]
0x14006dc52  mov     qword ptr [rsp+88h+var_68], r8
0x14006dc57  call    McTemplateK0pjqB6r2_EtwWriteTransfer
0x14006dc5c  test    rdi, rdi
0x14006dc5f  jz      short loc_14006DC9E
0x14006dc61  lea     rcx, [rdi-10h]; P
0x14006dc65  mov     rax, [rcx]
0x14006dc68  test    rax, rax
0x14006dc6b  jz      short loc_14006DC81
0x14006dc6d  mov     rdx, rcx; Entry
0x14006dc70  mov     rcx, rax; Lookaside
0x14006dc73  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006dc7a  nop     dword ptr [rax+rax+00h]
0x14006dc7f  jmp     short loc_14006DC9E
0x14006dc81  mov     edx, [rcx+8]; Tag
0x14006dc84  call    cs:__imp_ExFreePoolWithTag
0x14006dc8b  nop     dword ptr [rax+rax+00h]
0x14006dc90  jmp     short loc_14006DC9E
0x14006dc92  mov     ebx, 0C000009Ah
0x14006dc97  jmp     short loc_14006DC9E
0x14006dc99  mov     ebx, 0C000000Dh
0x14006dc9e  mov     eax, ebx
0x14006dca0  add     rsp, 48h
0x14006dca4  pop     r15
0x14006dca6  pop     r14
0x14006dca8  pop     r13
0x14006dcaa  pop     r12
0x14006dcac  pop     rdi
0x14006dcad  pop     rsi
0x14006dcae  pop     rbp
0x14006dcaf  pop     rbx
0x14006dcb0  retn
```
