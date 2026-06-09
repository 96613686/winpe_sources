# ACBeginGetPacket2Remote

- ea: `0x1400047fc`
- end: `0x140004988`
- name: `ACBeginGetPacket2Remote`
- size: `396`
- prototype: `__int64 __usercall@<rax>(struct _DEVICE_OBJECT *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140001c34`
- `0x140003ecc`
- `0x1400047fc`
- `0x1400096b0`
- `0x14000b5d8`
- `0x14000ba08`
- `0x14001a564`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14000487d`
- `ntoskrnl!ProbeForWrite` at `0x14000487d`

## pseudocode

```c
__int64 __fastcall ACBeginGetPacket2Remote(
        struct _DEVICE_OBJECT *a1,
        __int64 a2,
        __int64 a3,
        const struct CQueueBase *a4,
        __int64 a5)
{
  __int64 v7; // r14
  int v8; // ebx
  int v10; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_qqdDdi(WPP_GLOBAL_Control->Queue.ListEntry.Blink);
  }
  v7 = *(_QWORD *)(a5 + 32);
  if ( v7 )
    ProbeForWrite(*(volatile void **)(a5 + 32), 4u, 1u);
  v8 = CQueueBase::Validate(a4);
  if ( v8 >= 0 )
  {
    v10 = operator!=<BOID>(a5 + 56, &unk_140027BC0);
    return (unsigned int)ACpReceiveMessage(
                           a1,
                           *(_DWORD *)(a5 + 4),
                           *(_DWORD *)a5,
                           *(_DWORD *)(a5 + 8),
                           (a5 + 56) & -(__int64)(v10 != 0),
                           *(_BYTE *)(a5 + 40),
                           *(_QWORD *)(a5 + 48),
                           v7);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_Dq(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        84,
        &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
        (unsigned int)v8,
        a4);
    }
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x1400047fc  push    rbx
0x1400047fe  push    rsi
0x1400047ff  push    rdi
0x140004800  push    r12
0x140004802  push    r13
0x140004804  push    r14
0x140004806  push    r15
0x140004808  sub     rsp, 70h
0x14000480c  mov     rsi, r9
0x14000480f  mov     r12, r8
0x140004812  mov     r15, rdx
0x140004815  mov     r13, rcx
0x140004818  lea     rax, WPP_GLOBAL_Control
0x14000481f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004826  mov     rdi, [rsp+0A8h+arg_20]
0x14000482e  cmp     rcx, rax
0x140004831  jz      short loc_140004868
0x140004833  mov     eax, [rcx+6Ch]
0x140004836  test    al, 4
0x140004838  jz      short loc_140004868
0x14000483a  movzx   edx, byte ptr [rdi+28h]
0x14000483e  mov     rax, [rdi+30h]
0x140004842  mov     qword ptr [rsp+0A8h+var_68], rax
0x140004847  mov     dword ptr [rsp+0A8h+var_70], edx
0x14000484b  mov     eax, [rdi+4]
0x14000484e  mov     [rsp+0A8h+var_78], eax
0x140004852  mov     eax, [rdi+8]
0x140004855  mov     [rsp+0A8h+var_80], eax
0x140004859  mov     qword ptr [rsp+0A8h+var_88], r15
0x14000485e  mov     rcx, [rcx+58h]
0x140004862  call    WPP_SF_qqdDdi
0x140004867  nop
0x140004868  mov     r14, [rdi+20h]
0x14000486c  test    r14, r14
0x14000486f  jz      short loc_140004889
0x140004871  mov     edx, 4; Length
0x140004876  lea     r8d, [rdx-3]; Alignment
0x14000487a  mov     rcx, r14; Address
0x14000487d  call    cs:__imp_ProbeForWrite
0x140004884  nop     dword ptr [rax+rax+00h]
0x140004889  mov     rcx, rsi; struct CQueueBase *
0x14000488c  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x140004891  mov     ebx, eax
0x140004893  mov     [rsp+0A8h+var_48], eax
0x140004897  test    eax, eax
0x140004899  jns     short loc_1400048DA
0x14000489b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400048a2  lea     rax, WPP_GLOBAL_Control
0x1400048a9  cmp     rcx, rax
0x1400048ac  jz      short loc_1400048D3
0x1400048ae  mov     edx, [rcx+6Ch]
0x1400048b1  test    dl, 1
0x1400048b4  jz      short loc_1400048D3
0x1400048b6  mov     edx, 54h ; 'T'
0x1400048bb  mov     qword ptr [rsp+0A8h+var_88], rsi
0x1400048c0  mov     r9d, ebx
0x1400048c3  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400048ca  mov     rcx, [rcx+58h]
0x1400048ce  call    WPP_SF_Dq
0x1400048d3  mov     eax, ebx
0x1400048d5  jmp     loc_140004977
0x1400048da  lea     rbx, [rdi+38h]
0x1400048de  lea     rdx, unk_140027BC0
0x1400048e5  mov     rcx, rbx
0x1400048e8  call    ??$?9UBOID@@@@YAHAEBUBOID@@0@Z; operator!=<BOID>(BOID const &,BOID const &)
0x1400048ed  neg     eax
0x1400048ef  sbb     rcx, rcx
0x1400048f2  and     rcx, rbx
0x1400048f5  mov     [rsp+0A8h+var_58], r14; __int64
0x1400048fa  mov     rax, [rdi+30h]
0x1400048fe  mov     [rsp+0A8h+var_60], rax; __int64
0x140004903  mov     al, [rdi+28h]
0x140004906  mov     [rsp+0A8h+var_68], al; char
0x14000490a  mov     [rsp+0A8h+var_70], rcx; __int64
0x14000490f  mov     eax, [rdi+8]
0x140004912  mov     [rsp+0A8h+var_78], eax; unsigned int
0x140004916  mov     eax, [rdi]
0x140004918  mov     [rsp+0A8h+var_80], eax; int
0x14000491c  mov     eax, [rdi+4]
0x14000491f  mov     [rsp+0A8h+var_88], eax; int
0x140004923  mov     r9, rsi
0x140004926  mov     r8, r12
0x140004929  mov     rdx, r15
0x14000492c  mov     rcx, r13; struct _DEVICE_OBJECT *
0x14000492f  call    ACpReceiveMessage
0x140004934  mov     ebx, eax
0x140004936  mov     [rsp+0A8h+var_48], eax
0x14000493a  jmp     short loc_140004975
0x14000493c  mov     ebx, eax
0x14000493e  mov     [rsp+0A8h+var_48], eax
0x140004942  lea     rax, WPP_GLOBAL_Control
0x140004949  mov     rcx, cs:WPP_GLOBAL_Control
0x140004950  cmp     rcx, rax
0x140004953  jz      short loc_140004975
0x140004955  mov     eax, [rcx+6Ch]
0x140004958  test    al, 1
0x14000495a  jz      short loc_140004975
0x14000495c  mov     edx, 55h ; 'U'
0x140004961  mov     r9d, ebx
0x140004964  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000496b  mov     rcx, [rcx+58h]
0x14000496f  call    WPP_SF_d
0x140004974  nop
0x140004975  mov     eax, ebx
0x140004977  add     rsp, 70h
0x14000497b  pop     r15
0x14000497d  pop     r14
0x14000497f  pop     r13
0x140004981  pop     r12
0x140004983  pop     rdi
0x140004984  pop     rsi
0x140004985  pop     rbx
0x140004986  retn
```
