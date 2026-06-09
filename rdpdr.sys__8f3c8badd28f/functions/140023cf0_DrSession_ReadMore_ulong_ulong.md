# DrSession::ReadMore(ulong,ulong)

- ea: `0x140023cf0`
- end: `0x140024017`
- name: `?ReadMore@DrSession@@QEAAHKK@Z`
- size: `807`
- prototype: `__int64 __fastcall(DrSession *__hidden this, unsigned int, unsigned int)`
- caller_count: `10`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140012ff0`
- `0x1400131e0`
- `0x1400137c0`
- `0x140013e70`
- `0x140014360`
- `0x140020100`
- `0x1400205a8`
- `0x1400227a0`
- `0x140023030`
- `0x140023500`

## callees

- `0x140001660`
- `0x140001890`
- `0x1400018a0`
- `0x140003188`
- `0x14000324c`
- `0x14000327c`
- `0x140006560`
- `0x1400111d0`
- `0x14001d2e0`
- `0x140023cf0`
- `0x140025480`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140023ddb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140023ddb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140023df0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140023df0`

## pseudocode

```c
__int64 __fastcall DrSession::ReadMore(DrSession *this, unsigned int a2, unsigned int a3)
{
  unsigned int v3; // r10d
  unsigned int v4; // r9d
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // r15d
  unsigned int v10; // esi
  RefCount *v11; // rbx
  int v12; // r15d
  RefCount **v13; // rax
  RefCount **v14; // r14
  int v15; // r15d
  RefCount *v16; // rdx
  __int64 v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // edx
  int v20; // r14d

  v3 = *((_DWORD *)this + 154);
  v4 = v3;
  if ( a3 && v3 < a3 )
    v4 = 1600 * (a3 / 0x640 + 1);
  v7 = v4 + 1600;
  if ( v4 - a2 >= 0x640 )
    v7 = v4;
  if ( v7 > v3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
    v8 = DrSession::ReallocateChannelBuffer(this, v7, a2);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 0;
      v11 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          63,
          WPP_5c887063686c325024567ba4647d07cf_Traceguids,
          (unsigned int)v8);
      DrSession::ChannelIoFailed(this);
LABEL_37:
      if ( v9 != -2147483643 )
        goto LABEL_43;
      goto LABEL_38;
    }
  }
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)((char *)this + 480), 1u);
  v11 = (RefCount *)*((_QWORD *)this + 5);
  if ( v11 )
  {
    RefCount::AddRef(*((RefCount **)this + 5));
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 58) + 32LL))((char *)this + 464);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
    RefCount::AddRef(this);
    v12 = *((_DWORD *)this + 154);
    *((_DWORD *)this + 186) = a2;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids);
    v13 = (RefCount **)operator new(0x30u, 0x40u);
    v14 = v13;
    if ( v13 )
    {
      *v13 = v11;
      v15 = v12 - a2;
      RefCount::AddRef(v11);
      v14[3] = v16;
      v10 = 0;
      v14[1] = (RefCount *)DrSession::ReadCompletionRoutine;
      *((_DWORD *)v14 + 11) = 0;
      v14[2] = this;
      *((_DWORD *)v14 + 8) = v15;
      *(RefCount **)((char *)v14 + 36) = (RefCount *)3;
      v18 = TSAddWorkItemToQueue(v17, v14, VirtualChannel::IoWorker);
      v9 = v18;
      if ( !v18 )
      {
        v9 = 259;
        v20 = 259;
        goto LABEL_36;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids, v18);
      tagCHANNELCLOSECONTEXT::`scalar deleting destructor'(v14, v19);
      if ( v9 >= 0 )
        goto LABEL_38;
      v20 = v9;
      if ( v9 == -2147483643 )
      {
LABEL_36:
        if ( v20 < 0 )
          goto LABEL_37;
LABEL_38:
        v10 = 1;
        goto LABEL_43;
      }
    }
    else
    {
      v9 = -1073741670;
      v10 = 0;
      v20 = -1073741670;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        65,
        WPP_5c887063686c325024567ba4647d07cf_Traceguids,
        (unsigned int)v20);
    RefCount::Release(this);
    DrSession::ChannelIoFailed(this);
    goto LABEL_36;
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 58) + 32LL))((char *)this + 464);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
  v10 = 0;
LABEL_43:
  if ( v11 )
    RefCount::Release(v11);
  return v10;
}

```

## disassembly

```asm
0x140023cf0  push    rbx
0x140023cf2  push    rsi
0x140023cf3  sub     rsp, 28h
0x140023cf7  mov     r10d, [rcx+268h]
0x140023cfe  mov     r9d, r10d
0x140023d01  mov     [rsp+38h+arg_0], rbp
0x140023d06  mov     rbp, rcx
0x140023d09  mov     esi, edx
0x140023d0b  test    r8d, r8d
0x140023d0e  jz      short loc_140023D29
0x140023d10  cmp     r10d, r8d
0x140023d13  jnb     short loc_140023D29
0x140023d15  mov     eax, 51EB851Fh
0x140023d1a  mul     r8d
0x140023d1d  shr     edx, 9
0x140023d20  inc     edx
0x140023d22  imul    r9d, edx, 640h
0x140023d29  mov     [rsp+38h+arg_8], rdi
0x140023d2e  lea     ebx, [r9+640h]
0x140023d35  mov     [rsp+38h+arg_10], r12
0x140023d3a  mov     eax, r9d
0x140023d3d  sub     eax, esi
0x140023d3f  mov     [rsp+38h+arg_18], r14
0x140023d44  cmp     eax, 640h
0x140023d49  mov     [rsp+38h+var_18], r15
0x140023d4e  cmovnb  ebx, r9d
0x140023d52  cmp     ebx, r10d
0x140023d55  jbe     short loc_140023DD4
0x140023d57  mov     rcx, cs:WPP_GLOBAL_Control
0x140023d5e  lea     rdi, WPP_GLOBAL_Control
0x140023d65  cmp     rcx, rdi
0x140023d68  jz      short loc_140023D85
0x140023d6a  cmp     byte ptr [rcx+29h], 4
0x140023d6e  jb      short loc_140023D85
0x140023d70  mov     rcx, [rcx+18h]
0x140023d74  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140023d7b  mov     edx, 3Eh ; '>'
0x140023d80  call    WPP_SF_
0x140023d85  mov     r8d, esi; unsigned int
0x140023d88  mov     edx, ebx; unsigned int
0x140023d8a  mov     rcx, rbp; this
0x140023d8d  call    ?ReallocateChannelBuffer@DrSession@@AEAAJKK@Z; DrSession::ReallocateChannelBuffer(ulong,ulong)
0x140023d92  mov     r15d, eax
0x140023d95  test    eax, eax
0x140023d97  jns     short loc_140023DDB
0x140023d99  xor     esi, esi
0x140023d9b  mov     ebx, esi
0x140023d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140023da4  cmp     rcx, rdi
0x140023da7  jz      short loc_140023DC7
0x140023da9  cmp     byte ptr [rcx+29h], 2
0x140023dad  jb      short loc_140023DC7
0x140023daf  mov     rcx, [rcx+18h]
0x140023db3  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140023dba  mov     edx, 3Fh ; '?'
0x140023dbf  mov     r9d, eax
0x140023dc2  call    WPP_SF_d
0x140023dc7  mov     rcx, rbp; this
0x140023dca  call    ?ChannelIoFailed@DrSession@@AEAAXXZ; DrSession::ChannelIoFailed(void)
0x140023dcf  jmp     loc_140023F97
0x140023dd4  lea     rdi, WPP_GLOBAL_Control
0x140023ddb  call    cs:__imp_KeEnterCriticalRegion
0x140023de2  nop     dword ptr [rax+rax+00h]
0x140023de7  lea     rcx, [rbp+1E0h]; Resource
0x140023dee  mov     dl, 1; Wait
0x140023df0  call    cs:__imp_ExAcquireResourceSharedLite
0x140023df7  nop     dword ptr [rax+rax+00h]
0x140023dfc  mov     rbx, [rbp+28h]
0x140023e00  test    rbx, rbx
0x140023e03  jz      loc_140023FA7
0x140023e09  mov     rcx, rbx; this
0x140023e0c  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140023e11  mov     rax, [rbp+1D0h]
0x140023e18  lea     rcx, [rbp+1D0h]
0x140023e1f  mov     rax, [rax+20h]
0x140023e23  call    _guard_dispatch_icall
0x140023e28  mov     rcx, cs:WPP_GLOBAL_Control
0x140023e2f  cmp     rcx, rdi
0x140023e32  jz      short loc_140023E4F
0x140023e34  cmp     byte ptr [rcx+29h], 5
0x140023e38  jb      short loc_140023E4F
0x140023e3a  mov     rcx, [rcx+18h]
0x140023e3e  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140023e45  mov     edx, 40h ; '@'
0x140023e4a  call    WPP_SF_
0x140023e4f  mov     rcx, rbp; this
0x140023e52  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140023e57  mov     r15d, [rbp+268h]
0x140023e5e  mov     r12, [rbp+260h]
0x140023e65  mov     [rbp+2E8h], esi
0x140023e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140023e72  cmp     rcx, rdi
0x140023e75  jz      short loc_140023E92
0x140023e77  cmp     byte ptr [rcx+29h], 4
0x140023e7b  jb      short loc_140023E92
0x140023e7d  mov     rcx, [rcx+18h]
0x140023e81  lea     r8, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids
0x140023e88  mov     edx, 0Ah
0x140023e8d  call    WPP_SF_
0x140023e92  mov     edx, 40h ; '@'; unsigned __int64
0x140023e97  mov     ecx, 30h ; '0'; unsigned __int64
0x140023e9c  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x140023ea1  mov     r14, rax
0x140023ea4  test    rax, rax
0x140023ea7  jz      loc_140023F4D
0x140023ead  mov     rcx, rbx; this
0x140023eb0  mov     [rax], rbx
0x140023eb3  sub     r15d, esi
0x140023eb6  lea     rdx, [r12+rsi]
0x140023eba  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140023ebf  lea     rax, ?ReadCompletionRoutine@DrSession@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; DrSession::ReadCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x140023ec6  mov     [r14+18h], rdx
0x140023eca  xor     esi, esi
0x140023ecc  mov     [r14+8], rax
0x140023ed0  mov     rdx, r14
0x140023ed3  mov     [r14+2Ch], esi
0x140023ed7  lea     r8, ?IoWorker@VirtualChannel@@CAXPEAU_DEVICE_OBJECT@@PEAX@Z; VirtualChannel::IoWorker(_DEVICE_OBJECT *,void *)
0x140023ede  mov     [r14+10h], rbp
0x140023ee2  mov     [r14+20h], r15d
0x140023ee6  mov     qword ptr [r14+24h], 3
0x140023eee  call    TSAddWorkItemToQueue
0x140023ef3  mov     r15d, eax
0x140023ef6  test    eax, eax
0x140023ef8  jnz     short loc_140023F08
0x140023efa  mov     r15d, 103h
0x140023f00  mov     r14d, r15d
0x140023f03  jmp     loc_140023F92
0x140023f08  mov     rcx, cs:WPP_GLOBAL_Control
0x140023f0f  cmp     rcx, rdi
0x140023f12  jz      short loc_140023F32
0x140023f14  cmp     byte ptr [rcx+29h], 2
0x140023f18  jb      short loc_140023F32
0x140023f1a  mov     rcx, [rcx+18h]
0x140023f1e  lea     r8, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids
0x140023f25  mov     edx, 0Bh
0x140023f2a  mov     r9d, r15d
0x140023f2d  call    WPP_SF_d
0x140023f32  mov     rcx, r14; P
0x140023f35  call    ??_GtagCHANNELCLOSECONTEXT@@QEAAPEAXI@Z; tagCHANNELCLOSECONTEXT::`scalar deleting destructor'(uint)
0x140023f3a  test    r15d, r15d
0x140023f3d  jns     short loc_140023FA0
0x140023f3f  mov     r14d, r15d
0x140023f42  cmp     r15d, 80000005h
0x140023f49  jnz     short loc_140023F58
0x140023f4b  jmp     short loc_140023F92
0x140023f4d  mov     r15d, 0C000009Ah
0x140023f53  xor     esi, esi
0x140023f55  mov     r14d, r15d
0x140023f58  mov     rcx, cs:WPP_GLOBAL_Control
0x140023f5f  cmp     rcx, rdi
0x140023f62  jz      short loc_140023F82
0x140023f64  cmp     byte ptr [rcx+29h], 2
0x140023f68  jb      short loc_140023F82
0x140023f6a  mov     rcx, [rcx+18h]
0x140023f6e  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140023f75  mov     edx, 41h ; 'A'
0x140023f7a  mov     r9d, r14d
0x140023f7d  call    WPP_SF_d
0x140023f82  mov     rcx, rbp; this
0x140023f85  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140023f8a  mov     rcx, rbp; this
0x140023f8d  call    ?ChannelIoFailed@DrSession@@AEAAXXZ; DrSession::ChannelIoFailed(void)
0x140023f92  test    r14d, r14d
0x140023f95  jns     short loc_140023FA0
0x140023f97  cmp     r15d, 80000005h
0x140023f9e  jnz     short loc_140023FE7
0x140023fa0  mov     esi, 1
0x140023fa5  jmp     short loc_140023FE7
0x140023fa7  mov     rax, [rbp+1D0h]
0x140023fae  lea     rcx, [rbp+1D0h]
0x140023fb5  mov     rax, [rax+20h]
0x140023fb9  call    _guard_dispatch_icall
0x140023fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140023fc5  cmp     rcx, rdi
0x140023fc8  jz      short loc_140023FE5
0x140023fca  cmp     byte ptr [rcx+29h], 4
0x140023fce  jb      short loc_140023FE5
0x140023fd0  mov     rcx, [rcx+18h]
0x140023fd4  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140023fdb  mov     edx, 42h ; 'B'
0x140023fe0  call    WPP_SF_
0x140023fe5  xor     esi, esi
0x140023fe7  mov     r15, [rsp+38h+var_18]
0x140023fec  mov     r14, [rsp+38h+arg_18]
0x140023ff1  mov     r12, [rsp+38h+arg_10]
0x140023ff6  mov     rdi, [rsp+38h+arg_8]
0x140023ffb  mov     rbp, [rsp+38h+arg_0]
0x140024000  test    rbx, rbx
0x140024003  jz      short loc_14002400D
0x140024005  mov     rcx, rbx; this
0x140024008  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14002400d  mov     eax, esi
0x14002400f  add     rsp, 28h
0x140024013  pop     rsi
0x140024014  pop     rbx
0x140024015  retn
```
