# CPacket::Create(CPacket * *,_DEVICE_OBJECT *,ulong,ACPoolType,int)

- ea: `0x1400152d0`
- end: `0x14001548a`
- name: `?Create@CPacket@@SAJPEAPEAV1@PEAU_DEVICE_OBJECT@@KW4ACPoolType@@H@Z`
- size: `442`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int, int, int)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x140003f74`
- `0x140014980`
- `0x140015084`

## callees

- `0x140001128`
- `0x140001c04`
- `0x14000fe84`
- `0x140010d20`
- `0x140010ebc`
- `0x1400126fc`
- `0x1400152d0`
- `0x140019124`
- `0x140019148`

## pseudocode

```c
__int64 __fastcall CPacket::Create(_QWORD *a1, __int64 a2, unsigned int a3, int a4, int a5)
{
  CBaseObject *v6; // rdi
  __int64 v7; // r8
  __int64 result; // rax
  __int64 v11; // rcx
  int v12; // r9d
  __int64 v13; // rcx
  unsigned int v14; // ebx
  __int64 AccessibleBuffer; // r14
  _DWORD *v16; // rax
  _DWORD *v17; // rsi
  struct CPacket *v18; // rdx
  struct CDeviceExt *v19; // rcx
  CBaseObject *v20; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v21; // [rsp+A0h] [rbp+58h] BYREF

  v6 = 0;
  v7 = a3 + 32;
  v20 = 0;
  if ( (unsigned int)v7 < a3 )
    return 3221225713LL;
  v11 = *(_QWORD *)(*(_QWORD *)(a2 + 64) + 320LL);
  if ( a4 )
  {
    v12 = a4 - 1;
    if ( v12 )
    {
      if ( v12 != 1 )
      {
        v21 = -1;
        goto LABEL_11;
      }
      v13 = v11 + 136;
    }
    else
    {
      v13 = v11 + 72;
    }
  }
  else
  {
    v13 = v11 + 8;
  }
  CPoolAllocator::malloc(v13, &v21, v7, &v20, a5);
  v6 = v20;
LABEL_11:
  v14 = v21;
  if ( v21 != -1 )
  {
    AccessibleBuffer = CMMFAllocator::GetAccessibleBuffer(v6, v21);
    if ( AccessibleBuffer )
    {
      v16 = operator new(0x70u, 0x100u, 0x5041514Du, LowPoolPriority);
      v17 = v16;
      if ( v16 )
      {
        v16[2] = 1;
        v16[4] = v14;
        *(_QWORD *)v16 = &CQEntry::`vftable';
        *((_QWORD *)v16 + 3) = v6;
        *((_QWORD *)v16 + 4) = 0;
        *((_QWORD *)v16 + 5) = 0;
        v16[13] = 0;
        *((_QWORD *)v16 + 7) = 0;
        *((_QWORD *)v16 + 8) = 0;
        CBaseObject::AddRef(v6);
        v17[24] = 0;
        *((_QWORD *)v17 + 9) = 0;
        *((_QWORD *)v17 + 10) = 0;
        *((_QWORD *)v17 + 11) = 0;
        *(_QWORD *)v17 = &CPacket::`vftable';
        *((_QWORD *)v17 + 13) = a2;
        *(_QWORD *)(AccessibleBuffer + 12) = 0;
        *(_QWORD *)(AccessibleBuffer + 4) = 0;
        *(_OWORD *)(AccessibleBuffer + 20) = 0;
        *(_DWORD *)(AccessibleBuffer + 16) |= 0x200000u;
        *(_BYTE *)(AccessibleBuffer + 36) = 16;
        *(_DWORD *)(AccessibleBuffer + 40) = 1380927820;
        *(_DWORD *)(AccessibleBuffer + 44) = a3;
        *(_DWORD *)(AccessibleBuffer + 48) = -1;
        *(_WORD *)(AccessibleBuffer + 38) = 3;
        SetLowestPacketAllocated(*(struct CDeviceExt **)(a2 + 64), (struct CPacket *)v17);
        SetHighestPacketAllocated(v19, v18);
        result = 0;
        *a1 = v17;
        return result;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 10, WPP_521cf5ef77973c292796e113f00b944d_Traceguids);
      }
    }
    CMMFAllocator::free(v6, v14);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x1400152d0  push    rbp
0x1400152d2  push    rbx
0x1400152d3  push    rsi
0x1400152d4  push    rdi
0x1400152d5  push    r12
0x1400152d7  push    r13
0x1400152d9  push    r14
0x1400152db  push    r15
0x1400152dd  mov     rbp, rsp
0x1400152e0  sub     rsp, 48h
0x1400152e4  mov     r15d, r8d
0x1400152e7  xor     edi, edi
0x1400152e9  add     r8d, 20h ; ' '
0x1400152ed  mov     [rbp+var_18], rdi
0x1400152f1  mov     r13, rdx
0x1400152f4  mov     r12, rcx
0x1400152f7  cmp     r8d, r15d
0x1400152fa  jnb     short loc_140015306
0x1400152fc  mov     eax, 0C00000F1h
0x140015301  jmp     loc_140015478
0x140015306  mov     rax, [rdx+40h]
0x14001530a  or      esi, 0FFFFFFFFh
0x14001530d  mov     rcx, [rax+140h]
0x140015314  test    r9d, r9d
0x140015317  jz      short loc_140015339
0x140015319  sub     r9d, 1
0x14001531d  jz      short loc_140015333
0x14001531f  cmp     r9d, 1
0x140015323  jz      short loc_14001532A
0x140015325  mov     [rbp+arg_10], esi
0x140015328  jmp     short loc_140015355
0x14001532a  add     rcx, 88h
0x140015331  jmp     short loc_14001533D
0x140015333  add     rcx, 48h ; 'H'
0x140015337  jmp     short loc_14001533D
0x140015339  add     rcx, 8
0x14001533d  mov     eax, [rbp+arg_20]
0x140015340  lea     r9, [rbp+var_18]
0x140015344  lea     rdx, [rbp+arg_10]
0x140015348  mov     [rsp+48h+var_28], eax
0x14001534c  call    ?malloc@CPoolAllocator@@QEAA?AVCAllocatorBlockOffset@@KPEAPEAVCMMFAllocator@@H@Z; CPoolAllocator::malloc(ulong,CMMFAllocator * *,int)
0x140015351  mov     rdi, [rbp+var_18]
0x140015355  mov     ebx, [rbp+arg_10]
0x140015358  cmp     ebx, esi
0x14001535a  jz      loc_140015473
0x140015360  mov     edx, ebx
0x140015362  mov     rcx, rdi
0x140015365  call    ?GetAccessibleBuffer@CMMFAllocator@@QEAAPEAVCAccessibleBlock@@VCAllocatorBlockOffset@@@Z; CMMFAllocator::GetAccessibleBuffer(CAllocatorBlockOffset)
0x14001536a  mov     r14, rax
0x14001536d  test    rax, rax
0x140015370  jz      loc_140015469
0x140015376  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x140015379  mov     edx, 100h; unsigned __int64
0x14001537e  mov     r8d, 5041514Dh; unsigned int
0x140015384  lea     ecx, [r9+70h]; unsigned __int64
0x140015388  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14001538d  mov     rsi, rax
0x140015390  test    rax, rax
0x140015393  jz      loc_14001543A
0x140015399  mov     dword ptr [rax+8], 1
0x1400153a0  mov     rcx, rdi; this
0x1400153a3  mov     [rsi+10h], ebx
0x1400153a6  lea     rax, ??_7CQEntry@@6B@; const CQEntry::`vftable'
0x1400153ad  xor     ebx, ebx
0x1400153af  mov     [rsi], rax
0x1400153b2  mov     [rsi+18h], rdi
0x1400153b6  mov     [rsi+20h], rbx
0x1400153ba  mov     [rsi+28h], rbx
0x1400153be  mov     [rsi+34h], ebx
0x1400153c1  mov     [rsi+38h], rbx
0x1400153c5  mov     [rsi+40h], rbx
0x1400153c9  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x1400153ce  mov     [rsi+60h], ebx
0x1400153d1  lea     rax, ??_7CPacket@@6B@; const CPacket::`vftable'
0x1400153d8  mov     [rsi+48h], rbx
0x1400153dc  xorps   xmm0, xmm0
0x1400153df  mov     [rsi+50h], rbx
0x1400153e3  mov     rdx, rsi; struct CPacket *
0x1400153e6  mov     [rsi+58h], rbx
0x1400153ea  mov     [rsi], rax
0x1400153ed  mov     [rsi+68h], r13
0x1400153f1  mov     [r14+0Ch], rbx
0x1400153f5  mov     [r14+4], rbx
0x1400153f9  movups  xmmword ptr [r14+14h], xmm0
0x1400153fe  bts     dword ptr [r14+10h], 15h
0x140015404  mov     byte ptr [r14+24h], 10h
0x140015409  mov     dword ptr [r14+28h], 524F494Ch
0x140015411  mov     [r14+2Ch], r15d
0x140015415  mov     dword ptr [r14+30h], 0FFFFFFFFh
0x14001541d  mov     word ptr [r14+26h], 3
0x140015424  mov     rcx, [r13+40h]; struct CDeviceExt *
0x140015428  call    ?SetLowestPacketAllocated@@YAXPEAUCDeviceExt@@PEAVCPacket@@@Z; SetLowestPacketAllocated(CDeviceExt *,CPacket *)
0x14001542d  call    ?SetHighestPacketAllocated@@YAXPEAUCDeviceExt@@PEAVCPacket@@@Z; SetHighestPacketAllocated(CDeviceExt *,CPacket *)
0x140015432  xor     eax, eax
0x140015434  mov     [r12], rsi
0x140015438  jmp     short loc_140015478
0x14001543a  mov     rcx, cs:WPP_GLOBAL_Control
0x140015441  lea     rax, WPP_GLOBAL_Control
0x140015448  cmp     rcx, rax
0x14001544b  jz      short loc_140015469
0x14001544d  mov     eax, [rcx+6Ch]
0x140015450  test    al, 1
0x140015452  jz      short loc_140015469
0x140015454  mov     rcx, [rcx+58h]
0x140015458  lea     r8, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x14001545f  mov     edx, 0Ah
0x140015464  call    WPP_SF_
0x140015469  mov     edx, ebx
0x14001546b  mov     rcx, rdi
0x14001546e  call    ?free@CMMFAllocator@@QEAAXVCAllocatorBlockOffset@@@Z; CMMFAllocator::free(CAllocatorBlockOffset)
0x140015473  mov     eax, 0C000009Ah
0x140015478  add     rsp, 48h
0x14001547c  pop     r15
0x14001547e  pop     r14
0x140015480  pop     r13
0x140015482  pop     r12
0x140015484  pop     rdi
0x140015485  pop     rsi
0x140015486  pop     rbx
0x140015487  pop     rbp
0x140015488  retn
```
