# ClasspCompleteOffloadRead

- ea: `0x140023d08`
- end: `0x140023e36`
- name: `ClasspCompleteOffloadRead`
- size: `302`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400206f8`
- `0x1400252a0`
- `0x140025340`

## callees

- `0x140023c50`
- `0x140023d08`
- `0x140023e3c`
- `0x14002734c`

## pseudocode

```c
__int64 __fastcall ClasspCompleteOffloadRead(struct _DEVICE_OBJECT **P, NTSTATUS a2)
{
  IRP *v2; // r14
  struct _DEVICE_OBJECT *v4; // r15
  struct _DEVICE_OBJECT *v6; // rax
  _IRP *MasterIrp; // rbx
  unsigned int *DeviceExtension; // rcx
  struct _DEVICE_OBJECT *v9; // r12
  struct _DEVICE_OBJECT *v10; // rbp
  _MDL *v11; // rsi
  __int64 v12; // rax
  _OWORD *v13; // rbx
  __int128 v14; // xmm1

  v2 = (IRP *)P[1];
  v4 = *P;
  v6 = P[34];
  MasterIrp = v2->AssociatedIrp.MasterIrp;
  DeviceExtension = (unsigned int *)(*P)->DeviceExtension;
  v9 = P[35];
  v10 = P[47];
  *(_QWORD *)&MasterIrp->Type = 0;
  if ( a2 < 0 )
  {
    MasterIrp->MdlAddress = 0;
    MasterIrp->Flags = 0;
  }
  else
  {
    v11 = (_MDL *)((_QWORD)v6 * DeviceExtension[143]);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_qIID(WPP_GLOBAL_Control->AttachedDevice, 241);
    if ( v11 < (_MDL *)v9 )
      *(_DWORD *)&MasterIrp->Type |= 1u;
    v12 = 4;
    MasterIrp->MdlAddress = v11;
    MasterIrp->Flags = 512;
    v13 = &MasterIrp->Flags + 1;
    do
    {
      *v13 = *(_OWORD *)&v10->Type;
      v13[1] = *(_OWORD *)&v10->NextDevice;
      v13[2] = *(_OWORD *)&v10->CurrentIrp;
      v13[3] = *(_OWORD *)&v10->Flags;
      v13[4] = *(_OWORD *)&v10->DeviceExtension;
      v13[5] = v10->Queue.ListEntry;
      v13[6] = *(_OWORD *)&v10->Queue.Wcb.NumberOfChannels;
      v14 = *(_OWORD *)&v10->Queue.Wcb.DeviceContext;
      v10 = (struct _DEVICE_OBJECT *)((char *)v10 + 128);
      v13[7] = v14;
      v13 += 8;
      --v12;
    }
    while ( v12 );
  }
  v2->IoStatus.Information = 536;
  ClasspCompleteOffloadRequest(v4, v2, a2);
  return ClasspCleanupOffloadReadContext(P);
}

```

## disassembly

```asm
0x140023d08  push    rbx
0x140023d0a  push    rbp
0x140023d0b  push    rsi
0x140023d0c  push    rdi
0x140023d0d  push    r12
0x140023d0f  push    r13
0x140023d11  push    r14
0x140023d13  push    r15
0x140023d15  sub     rsp, 48h
0x140023d19  mov     r14, [rcx+8]
0x140023d1d  mov     rdi, rcx
0x140023d20  mov     r15, [rcx]
0x140023d23  mov     r13d, edx
0x140023d26  mov     rax, [rcx+110h]
0x140023d2d  xor     edx, edx
0x140023d2f  mov     rbx, [r14+18h]
0x140023d33  mov     rcx, [r15+40h]
0x140023d37  mov     r12, [rdi+118h]
0x140023d3e  mov     rbp, [rdi+178h]
0x140023d45  mov     [rbx], rdx
0x140023d48  test    r13d, r13d
0x140023d4b  js      loc_140023DFF
0x140023d51  mov     esi, [rcx+23Ch]
0x140023d57  imul    rsi, rax
0x140023d5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140023d62  lea     rax, WPP_GLOBAL_Control
0x140023d69  cmp     rcx, rax
0x140023d6c  jz      short loc_140023D93
0x140023d6e  mov     eax, [rdi+0FCh]
0x140023d74  mov     edx, 0F1h
0x140023d79  mov     rcx, [rcx+18h]
0x140023d7d  mov     r9, r15
0x140023d80  mov     [rsp+88h+var_58], eax
0x140023d84  mov     [rsp+88h+var_60], r12
0x140023d89  mov     [rsp+88h+var_68], rsi
0x140023d8e  call    WPP_SF_qIID
0x140023d93  cmp     rsi, r12
0x140023d96  jnb     short loc_140023D9B
0x140023d98  or      dword ptr [rbx], 1
0x140023d9b  mov     eax, 4
0x140023da0  mov     [rbx+8], rsi
0x140023da4  mov     dword ptr [rbx+10h], 200h
0x140023dab  add     rbx, 14h
0x140023daf  lea     ecx, [rax+7Ch]
0x140023db2  movups  xmm0, xmmword ptr [rbp+0]
0x140023db6  movups  xmmword ptr [rbx], xmm0
0x140023db9  movups  xmm1, xmmword ptr [rbp+10h]
0x140023dbd  movups  xmmword ptr [rbx+10h], xmm1
0x140023dc1  movups  xmm0, xmmword ptr [rbp+20h]
0x140023dc5  movups  xmmword ptr [rbx+20h], xmm0
0x140023dc9  movups  xmm1, xmmword ptr [rbp+30h]
0x140023dcd  movups  xmmword ptr [rbx+30h], xmm1
0x140023dd1  movups  xmm0, xmmword ptr [rbp+40h]
0x140023dd5  movups  xmmword ptr [rbx+40h], xmm0
0x140023dd9  movups  xmm1, xmmword ptr [rbp+50h]
0x140023ddd  movups  xmmword ptr [rbx+50h], xmm1
0x140023de1  movups  xmm0, xmmword ptr [rbp+60h]
0x140023de5  movups  xmmword ptr [rbx+60h], xmm0
0x140023de9  movups  xmm1, xmmword ptr [rbp+70h]
0x140023ded  add     rbp, rcx
0x140023df0  movups  xmmword ptr [rbx+70h], xmm1
0x140023df4  add     rbx, rcx
0x140023df7  sub     rax, 1
0x140023dfb  jnz     short loc_140023DB2
0x140023dfd  jmp     short loc_140023E06
0x140023dff  mov     [rbx+8], rdx
0x140023e03  mov     [rbx+10h], edx
0x140023e06  mov     r8d, r13d
0x140023e09  mov     qword ptr [r14+38h], 218h
0x140023e11  mov     rdx, r14; Irp
0x140023e14  mov     rcx, r15; DeviceObject
0x140023e17  call    ClasspCompleteOffloadRequest
0x140023e1c  mov     rcx, rdi; P
0x140023e1f  call    ClasspCleanupOffloadReadContext
0x140023e24  add     rsp, 48h
0x140023e28  pop     r15
0x140023e2a  pop     r14
0x140023e2c  pop     r13
0x140023e2e  pop     r12
0x140023e30  pop     rdi
0x140023e31  pop     rsi
0x140023e32  pop     rbp
0x140023e33  pop     rbx
0x140023e34  retn
```
