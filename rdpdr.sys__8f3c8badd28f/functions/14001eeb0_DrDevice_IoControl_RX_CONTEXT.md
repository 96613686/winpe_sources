# DrDevice::IoControl(_RX_CONTEXT *)

- ea: `0x14001eeb0`
- end: `0x14001f292`
- name: `?IoControl@DrDevice@@UEAAJPEAU_RX_CONTEXT@@@Z`
- size: `994`
- prototype: `__int64 __fastcall(DrDevice *__hidden this, struct _RX_CONTEXT *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x140012180`
- `0x14001e000`

## callees

- `0x1400016a0`
- `0x140001890`
- `0x140001e30`
- `0x140003188`
- `0x14000324c`
- `0x14000327c`
- `0x140006560`
- `0x1400065c0`
- `0x1400068c0`
- `0x14001eeb0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14001eff8`
- `ntoskrnl!ProbeForRead` at `0x14001eff8`
- `ntoskrnl!ProbeForWrite` at `0x14001f020`
- `ntoskrnl!ProbeForWrite` at `0x14001f020`

## pseudocode

```c
__int64 __fastcall DrDevice::IoControl(DrDevice *this, struct _RX_CONTEXT *a2)
{
  __int64 v4; // rax
  RefCount *v5; // rbx
  unsigned int v6; // ebx
  int v7; // edi
  SIZE_T v8; // r14
  wchar_t *Buffer; // r15
  __int64 v10; // r9
  unsigned int v11; // eax
  unsigned int v12; // r14d
  size_t v13; // r15
  _DWORD *v14; // rdi
  __int64 v15; // r9
  unsigned int v16; // eax
  unsigned int v17; // esi
  RefCount *v19; // [rsp+80h] [rbp+8h] BYREF
  __int64 v20; // [rsp+88h] [rbp+10h] BYREF

  v4 = *((_QWORD *)this + 4);
  v20 = v4;
  if ( v4 )
    RefCount::AddRef((RefCount *)v4);
  v5 = *(RefCount **)&a2->pFobx->OffsetOfNextEaToReturn;
  v19 = v5;
  if ( v5 )
    RefCount::AddRef(v5);
  if ( (*(unsigned __int16 *)(v4 + 1134) | (*(unsigned __int16 *)(v4 + 1132) << 16)) - 65540 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
    v6 = -1073741822;
    goto LABEL_48;
  }
  if ( *(_DWORD *)(v4 + 596) != 3 || !v5 )
  {
LABEL_47:
    v6 = -1073741667;
LABEL_48:
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v19);
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v20);
    return v6;
  }
  v7 = *((_DWORD *)&a2->9 + 35);
  v8 = *((unsigned int *)&a2->9 + 43);
  Buffer = a2->Create.TransportName.Buffer;
  v10 = *((unsigned int *)this + 14);
  if ( (_DWORD)v10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids, v10);
    goto LABEL_47;
  }
  if ( a2->CurrentIrp->RequestorMode )
  {
    if ( (v7 & 1) != 0 && *((_QWORD *)&a2->9 + 19) && *((_DWORD *)&a2->9 + 42) )
      ProbeForRead(*((volatile void **)&a2->9 + 19), *((unsigned int *)&a2->9 + 42), 1u);
    if ( (v7 & 2) != 0 && Buffer && (_DWORD)v8 )
      ProbeForWrite(Buffer, v8, 1u);
  }
  v11 = *((_DWORD *)&a2->9 + 42);
  v12 = v11 + 56;
  if ( v11 + 56 < v11 || v12 < 0x38 )
  {
    v14 = 0;
    v13 = v12;
  }
  else
  {
    v13 = v12;
    v14 = operator new(v12, 0x100u);
  }
  if ( v14 )
  {
    memset(v14, 0, v13);
    *v14 = 1230128242;
    v14[1] = *((_DWORD *)this + 10);
    v14[2] = *((_DWORD *)v5 + 6);
    v14[4] = 14;
    v14[5] = *((unsigned __int8 *)&a2->9 + 176);
    v14[6] = *((_DWORD *)&a2->9 + 43);
    v14[7] = *((_DWORD *)&a2->9 + 42);
    v14[8] = *((_DWORD *)&a2->9 + 35);
    v15 = *((unsigned int *)&a2->9 + 42);
    if ( (_DWORD)v15 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids, v15);
      memmove(v14 + 14, *((const void **)&a2->9 + 19), *((unsigned int *)&a2->9 + 42));
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
    }
    v16 = (*(__int64 (__fastcall **)(DrDevice *, struct _RX_CONTEXT *, _DWORD *, _QWORD, bool, union _LARGE_INTEGER *, _DWORD))(*(_QWORD *)this + 24LL))(
            this,
            a2,
            v14,
            v12,
            ((__int64)a2->RdbssDbgExtension & 0x1000) == 0,
            &g_IOTimeOut,
            0);
    v17 = v16;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids, v16);
    operator delete(v14);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids, 0);
    v17 = -1073741670;
  }
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v19);
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v20);
  return v17;
}

```

## disassembly

```asm
0x14001eeb0  mov     r11, rsp
0x14001eeb3  mov     [r11+18h], rbx
0x14001eeb7  push    rsi
0x14001eeb8  push    rdi
0x14001eeb9  push    r12
0x14001eebb  push    r14
0x14001eebd  push    r15
0x14001eebf  sub     rsp, 50h
0x14001eec3  mov     rsi, rdx
0x14001eec6  mov     r12, rcx
0x14001eec9  mov     rax, [rcx+20h]
0x14001eecd  mov     [r11+10h], rax
0x14001eed1  test    rax, rax
0x14001eed4  jz      short loc_14001EEDE
0x14001eed6  mov     rcx, rax; this
0x14001eed9  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14001eede  mov     rbx, [rdx+40h]
0x14001eee2  mov     rbx, [rbx+40h]
0x14001eee6  mov     [rsp+78h+arg_0], rbx
0x14001eeee  test    rbx, rbx
0x14001eef1  jz      short loc_14001EEFB
0x14001eef3  mov     rcx, rbx; this
0x14001eef6  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14001eefb  movzx   edx, word ptr [rax+46Ch]
0x14001ef02  shl     edx, 10h
0x14001ef05  movzx   ecx, word ptr [rax+46Eh]
0x14001ef0c  or      edx, ecx
0x14001ef0e  cmp     edx, 10004h
0x14001ef14  jns     short loc_14001EF4E
0x14001ef16  lea     rbx, WPP_GLOBAL_Control
0x14001ef1d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ef24  cmp     rcx, rbx
0x14001ef27  jz      short loc_14001EF44
0x14001ef29  cmp     byte ptr [rcx+29h], 5
0x14001ef2d  jb      short loc_14001EF44
0x14001ef2f  mov     edx, 28h ; '('
0x14001ef34  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001ef3b  mov     rcx, [rcx+18h]
0x14001ef3f  call    WPP_SF_
0x14001ef44  mov     ebx, 0C0000002h
0x14001ef49  jmp     loc_14001F260
0x14001ef4e  cmp     dword ptr [rax+254h], 3
0x14001ef55  jnz     loc_14001F25B
0x14001ef5b  test    rbx, rbx
0x14001ef5e  jz      loc_14001F25B
0x14001ef64  mov     [rsp+78h+var_38], 0
0x14001ef6d  mov     edi, [rsi+21Ch]
0x14001ef73  mov     ecx, [rsi+238h]
0x14001ef79  mov     r14d, [rsi+23Ch]
0x14001ef80  mov     r10, [rsi+228h]
0x14001ef87  mov     r15, [rsi+230h]
0x14001ef8e  mov     r9d, [r12+38h]
0x14001ef93  test    r9d, r9d
0x14001ef96  jz      short loc_14001EFD3
0x14001ef98  lea     rbx, WPP_GLOBAL_Control
0x14001ef9f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001efa6  cmp     rcx, rbx
0x14001efa9  jz      loc_14001F25B
0x14001efaf  cmp     byte ptr [rcx+29h], 5
0x14001efb3  jb      loc_14001F25B
0x14001efb9  mov     edx, 29h ; ')'
0x14001efbe  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001efc5  mov     rcx, [rcx+18h]
0x14001efc9  call    WPP_SF_d
0x14001efce  jmp     loc_14001F25B
0x14001efd3  mov     rax, [rsi+28h]
0x14001efd7  cmp     byte ptr [rax+40h], 0
0x14001efdb  jz      short loc_14001F02C
0x14001efdd  test    dil, 1
0x14001efe1  jz      short loc_14001F004
0x14001efe3  test    r10, r10
0x14001efe6  jz      short loc_14001F004
0x14001efe8  test    ecx, ecx
0x14001efea  jz      short loc_14001F004
0x14001efec  mov     rdx, rcx; Length
0x14001efef  mov     r8d, 1; Alignment
0x14001eff5  mov     rcx, r10; Address
0x14001eff8  call    cs:__imp_ProbeForRead
0x14001efff  nop     dword ptr [rax+rax+00h]
0x14001f004  test    dil, 2
0x14001f008  jz      short loc_14001F02C
0x14001f00a  test    r15, r15
0x14001f00d  jz      short loc_14001F02C
0x14001f00f  test    r14d, r14d
0x14001f012  jz      short loc_14001F02C
0x14001f014  mov     rdx, r14; Length
0x14001f017  mov     r8d, 1; Alignment
0x14001f01d  mov     rcx, r15; Address
0x14001f020  call    cs:__imp_ProbeForWrite
0x14001f027  nop     dword ptr [rax+rax+00h]
0x14001f02c  mov     eax, [rsi+238h]
0x14001f032  lea     r14d, [rax+38h]
0x14001f036  cmp     r14d, eax
0x14001f039  jb      short loc_14001F05B
0x14001f03b  cmp     r14d, 38h ; '8'
0x14001f03f  jb      short loc_14001F05B
0x14001f041  mov     r15d, r14d
0x14001f044  mov     edx, 100h; unsigned __int64
0x14001f049  mov     ecx, r14d; unsigned __int64
0x14001f04c  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x14001f051  mov     rdi, rax
0x14001f054  mov     [rsp+78h+var_38], rax
0x14001f059  jmp     short loc_14001F065
0x14001f05b  xor     edi, edi
0x14001f05d  mov     [rsp+78h+var_38], rdi
0x14001f062  mov     r15d, r14d
0x14001f065  test    rdi, rdi
0x14001f068  jz      loc_14001F1AE
0x14001f06e  mov     r8, r15; Size
0x14001f071  xor     edx, edx; Val
0x14001f073  mov     rcx, rdi; void *
0x14001f076  call    memset
0x14001f07b  mov     dword ptr [rdi], 49524472h
0x14001f081  mov     eax, [r12+28h]
0x14001f086  mov     [rdi+4], eax
0x14001f089  mov     eax, [rbx+18h]
0x14001f08c  mov     [rdi+8], eax
0x14001f08f  mov     dword ptr [rdi+10h], 0Eh
0x14001f096  movzx   eax, byte ptr [rsi+240h]
0x14001f09d  mov     [rdi+14h], eax
0x14001f0a0  mov     eax, [rsi+23Ch]
0x14001f0a6  mov     [rdi+18h], eax
0x14001f0a9  mov     eax, [rsi+238h]
0x14001f0af  mov     [rdi+1Ch], eax
0x14001f0b2  mov     eax, [rsi+21Ch]
0x14001f0b8  mov     [rdi+20h], eax
0x14001f0bb  mov     r9d, [rsi+238h]
0x14001f0c2  test    r9d, r9d
0x14001f0c5  jz      short loc_14001F10E
0x14001f0c7  lea     rbx, WPP_GLOBAL_Control
0x14001f0ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f0d5  cmp     rcx, rbx
0x14001f0d8  jz      short loc_14001F0F5
0x14001f0da  cmp     byte ptr [rcx+29h], 4
0x14001f0de  jb      short loc_14001F0F5
0x14001f0e0  mov     edx, 2Ah ; '*'
0x14001f0e5  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001f0ec  mov     rcx, [rcx+18h]
0x14001f0f0  call    WPP_SF_d
0x14001f0f5  mov     r8d, [rsi+238h]; Size
0x14001f0fc  lea     rcx, [rdi+38h]; void *
0x14001f100  mov     rdx, [rsi+228h]; Src
0x14001f107  call    memmove
0x14001f10c  jmp     short loc_14001F13C
0x14001f10e  lea     rbx, WPP_GLOBAL_Control
0x14001f115  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f11c  cmp     rcx, rbx
0x14001f11f  jz      short loc_14001F13C
0x14001f121  cmp     byte ptr [rcx+29h], 4
0x14001f125  jb      short loc_14001F13C
0x14001f127  mov     edx, 2Bh ; '+'
0x14001f12c  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001f133  mov     rcx, [rcx+18h]
0x14001f137  call    WPP_SF_
0x14001f13c  mov     rax, [r12]
0x14001f140  mov     ecx, [rsi+78h]
0x14001f143  shr     ecx, 0Ch
0x14001f146  not     cl
0x14001f148  and     cl, 1
0x14001f14b  mov     rax, [rax+18h]
0x14001f14f  mov     [rsp+78h+var_48], 0
0x14001f157  lea     rdx, ?g_IOTimeOut@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_IOTimeOut
0x14001f15e  mov     [rsp+78h+var_50], rdx
0x14001f163  mov     [rsp+78h+var_58], cl
0x14001f167  mov     r9d, r14d
0x14001f16a  mov     r8, rdi
0x14001f16d  mov     rdx, rsi
0x14001f170  mov     rcx, r12
0x14001f173  call    _guard_dispatch_icall
0x14001f178  mov     esi, eax
0x14001f17a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f181  cmp     rcx, rbx
0x14001f184  jz      short loc_14001F1A4
0x14001f186  cmp     byte ptr [rcx+29h], 4
0x14001f18a  jb      short loc_14001F1A4
0x14001f18c  mov     edx, 2Ch ; ','
0x14001f191  mov     r9d, eax
0x14001f194  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001f19b  mov     rcx, [rcx+18h]
0x14001f19f  call    WPP_SF_d
0x14001f1a4  mov     rcx, rdi; void *
0x14001f1a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001f1ac  jmp     short loc_14001F1E4
0x14001f1ae  lea     rbx, WPP_GLOBAL_Control
0x14001f1b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f1bc  cmp     rcx, rbx
0x14001f1bf  jz      short loc_14001F1DF
0x14001f1c1  cmp     byte ptr [rcx+29h], 2
0x14001f1c5  jb      short loc_14001F1DF
0x14001f1c7  mov     edx, 2Dh ; '-'
0x14001f1cc  xor     r9d, r9d
0x14001f1cf  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001f1d6  mov     rcx, [rcx+18h]
0x14001f1da  call    WPP_SF_d
0x14001f1df  mov     esi, 0C000009Ah
0x14001f1e4  lea     rcx, [rsp+78h+arg_0]
0x14001f1ec  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001f1f1  lea     rcx, [rsp+78h+arg_8]
0x14001f1f9  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001f1fe  mov     eax, esi
0x14001f200  jmp     short loc_14001F27C
0x14001f202  lea     rax, WPP_GLOBAL_Control
0x14001f209  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f210  cmp     rcx, rax
0x14001f213  jz      short loc_14001F230
0x14001f215  cmp     byte ptr [rcx+29h], 2
0x14001f219  jb      short loc_14001F230
0x14001f21b  mov     edx, 2Eh ; '.'
0x14001f220  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001f227  mov     rcx, [rcx+18h]
0x14001f22b  call    WPP_SF_
0x14001f230  mov     rcx, [rsp+78h+var_38]; void *
0x14001f235  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001f23a  lea     rcx, [rsp+78h+arg_0]
0x14001f242  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001f247  lea     rcx, [rsp+78h+arg_8]
0x14001f24f  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001f254  mov     eax, 0C000000Dh
0x14001f259  jmp     short loc_14001F27C
0x14001f25b  mov     ebx, 0C000009Dh
0x14001f260  lea     rcx, [rsp+78h+arg_0]
0x14001f268  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001f26d  lea     rcx, [rsp+78h+arg_8]
0x14001f275  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001f27a  mov     eax, ebx
0x14001f27c  mov     rbx, [rsp+78h+arg_10]
0x14001f284  add     rsp, 50h
0x14001f288  pop     r15
0x14001f28a  pop     r14
0x14001f28c  pop     r12
0x14001f28e  pop     rdi
0x14001f28f  pop     rsi
0x14001f290  retn
```
