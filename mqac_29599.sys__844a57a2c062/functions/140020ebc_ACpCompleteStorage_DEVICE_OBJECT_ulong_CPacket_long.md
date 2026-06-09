# ACpCompleteStorage(_DEVICE_OBJECT *,ulong,CPacket * *,long)

- ea: `0x140020ebc`
- end: `0x140020f96`
- name: `?ACpCompleteStorage@@YAXPEAU_DEVICE_OBJECT@@KPEAPEAVCPacket@@J@Z`
- size: `218`
- prototype: `void __fastcall(struct _DEVICE_OBJECT *, unsigned int, struct CPacket **, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14001adac`
- `0x140021144`

## callees

- `0x140003d84`
- `0x140009adc`
- `0x14000a1d4`
- `0x140010470`
- `0x140012754`
- `0x1400177c4`
- `0x140020ebc`
- `0x140021080`

## pseudocode

```c
void __fastcall ACpCompleteStorage(struct _DEVICE_OBJECT *a1, unsigned int a2, struct CPacket **a3, int a4)
{
  int v4; // ebp
  __int64 i; // rbx
  struct CPacket *v9; // rax
  CPacket *v10; // rdi
  __int64 v11; // rcx
  bool v12; // zf

  v4 = a4;
  if ( a4 >= 0 )
    v4 = ACpStorageCompletedSuccess(a1, a2, a3);
  for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
  {
    v9 = CPacketHandleToCPacket(a1, a3[i]);
    v10 = v9;
    if ( v9 )
    {
      v11 = *((_QWORD *)v9 + 3);
      v12 = (*(_DWORD *)(v11 + 144))-- == 1;
      if ( v12 && *(_QWORD *)(v11 + 88) && !*(_QWORD *)(v11 + 104) )
        CMMFAllocator::MarkCoherent((CMMFAllocator *)v11);
      CPacket::HandleStorageCompleted(v10, v4);
      CQEntry::ReleaseBuffer(v10);
      CBaseObject::Release(v10);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 15, &WPP_154e3a669a6d37aaa7a9816475bffab0_Traceguids, a3[i]);
    }
  }
}

```

## disassembly

```asm
0x140020ebc  mov     [rsp+arg_0], rbx
0x140020ec1  mov     [rsp+arg_10], rbp
0x140020ec6  push    rsi
0x140020ec7  push    rdi
0x140020ec8  push    r12
0x140020eca  push    r14
0x140020ecc  push    r15
0x140020ece  sub     rsp, 20h
0x140020ed2  mov     ebp, r9d
0x140020ed5  mov     r14, r8
0x140020ed8  mov     esi, edx
0x140020eda  mov     r12, rcx
0x140020edd  test    r9d, r9d
0x140020ee0  js      short loc_140020EE9
0x140020ee2  call    ?ACpStorageCompletedSuccess@@YAJPEAU_DEVICE_OBJECT@@KPEAPEAVCPacket@@@Z; ACpStorageCompletedSuccess(_DEVICE_OBJECT *,ulong,CPacket * *)
0x140020ee7  mov     ebp, eax
0x140020ee9  xor     ebx, ebx
0x140020eeb  test    esi, esi
0x140020eed  jz      loc_140020F7E
0x140020ef3  mov     rdx, [r14+rbx*8]; struct CPacket *
0x140020ef7  mov     rcx, r12; struct _DEVICE_OBJECT *
0x140020efa  call    ?CPacketHandleToCPacket@@YAPEAVCPacket@@PEAU_DEVICE_OBJECT@@PEAV1@@Z; CPacketHandleToCPacket(_DEVICE_OBJECT *,CPacket *)
0x140020eff  mov     rdi, rax
0x140020f02  test    rax, rax
0x140020f05  jnz     short loc_140020F3A
0x140020f07  mov     rcx, cs:WPP_GLOBAL_Control
0x140020f0e  lea     rax, WPP_GLOBAL_Control
0x140020f15  cmp     rcx, rax
0x140020f18  jz      short loc_140020F74
0x140020f1a  mov     eax, [rcx+6Ch]
0x140020f1d  test    al, 1
0x140020f1f  jz      short loc_140020F74
0x140020f21  mov     r9, [r14+rbx*8]
0x140020f25  lea     edx, [rdi+0Fh]
0x140020f28  mov     rcx, [rcx+58h]
0x140020f2c  lea     r8, WPP_154e3a669a6d37aaa7a9816475bffab0_Traceguids
0x140020f33  call    WPP_SF_q
0x140020f38  jmp     short loc_140020F74
0x140020f3a  mov     rcx, [rax+18h]; this
0x140020f3e  add     dword ptr [rcx+90h], 0FFFFFFFFh
0x140020f45  jnz     short loc_140020F5A
0x140020f47  cmp     qword ptr [rcx+58h], 0
0x140020f4c  jz      short loc_140020F5A
0x140020f4e  cmp     qword ptr [rcx+68h], 0
0x140020f53  jnz     short loc_140020F5A
0x140020f55  call    ?MarkCoherent@CMMFAllocator@@AEAAXXZ; CMMFAllocator::MarkCoherent(void)
0x140020f5a  mov     edx, ebp; int
0x140020f5c  mov     rcx, rdi; this
0x140020f5f  call    ?HandleStorageCompleted@CPacket@@QEAAXJ@Z; CPacket::HandleStorageCompleted(long)
0x140020f64  mov     rcx, rdi; this
0x140020f67  call    ?ReleaseBuffer@CQEntry@@QEBAXXZ; CQEntry::ReleaseBuffer(void)
0x140020f6c  mov     rcx, rdi; this
0x140020f6f  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140020f74  inc     ebx
0x140020f76  cmp     ebx, esi
0x140020f78  jb      loc_140020EF3
0x140020f7e  mov     rbx, [rsp+48h+arg_0]
0x140020f83  mov     rbp, [rsp+48h+arg_10]
0x140020f88  add     rsp, 20h
0x140020f8c  pop     r15
0x140020f8e  pop     r14
0x140020f90  pop     r12
0x140020f92  pop     rdi
0x140020f93  pop     rsi
0x140020f94  retn
```
