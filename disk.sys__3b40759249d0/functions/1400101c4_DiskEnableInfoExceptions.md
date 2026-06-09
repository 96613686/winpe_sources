# DiskEnableInfoExceptions

- ea: `0x1400101c4`
- end: `0x14001047c`
- name: `DiskEnableInfoExceptions`
- size: `696`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000e5f8`

## callees

- `0x1400034a0`
- `0x140004078`
- `0x1400101c4`
- `0x140010cb8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010404`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010452`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010404`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010452`
- `ntoskrnl!ExAllocatePool2` at `0x1400101ff`
- `ntoskrnl!ExAllocatePool2` at `0x1400101ff`
- `CLASSPNP!ClassModeSelect` at `0x1400103d0`
- `CLASSPNP!ClassModeSelect` at `0x1400103d0`

## pseudocode

```c
__int64 __fastcall DiskEnableInfoExceptions(__int64 a1, char a2)
{
  __int64 v2; // rbp
  __int64 Pool2; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  void *v8; // r14
  __int64 v10; // rdx
  _BYTE *v11; // r15
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  char v14; // r13
  char v15; // r15
  _BYTE *v16; // r9
  __int64 v17; // r8
  int v18; // ebx
  unsigned int v19; // [rsp+60h] [rbp+8h] BYREF
  _BYTE *v20; // [rsp+70h] [rbp+18h] BYREF

  v2 = *(_QWORD *)(a1 + 96);
  v20 = 0;
  v19 = 192;
  Pool2 = ExAllocatePool2(72, 192, 1095000915);
  v8 = (void *)Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_a9711c54c416383df697b4e008bb3725_Traceguids);
    }
    return 3221225626LL;
  }
  LOBYTE(v7) = 1;
  if ( (int)DiskGetModePage(*(_QWORD *)(a1 + 8), v6, v7, Pool2, &v19, &v20) < 0 || (v11 = v20) == 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      goto LABEL_40;
    }
    v13 = 13;
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      WPP_a9711c54c416383df697b4e008bb3725_Traceguids,
      *(_QWORD *)(a1 + 8));
  }
  if ( (v11[2] & 8) == 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      goto LABEL_40;
    }
    v13 = 15;
LABEL_39:
    WPP_SF_q(v12->AttachedDevice, v13, WPP_a9711c54c416383df697b4e008bb3725_Traceguids, *(_QWORD *)(a1 + 8));
LABEL_40:
    ExFreePoolWithTag(v8, 0);
    return 3221225659LL;
  }
  v14 = v11[2];
  v15 = v11[3];
  if ( (int)DiskGetModePage(*(_QWORD *)(a1 + 8), v10, 0, v8, &v19, &v20) < 0 )
    goto LABEL_40;
  v16 = v20;
  if ( !v20 )
    goto LABEL_40;
  if ( (v20[3] & 0xF) == 0 && (v15 & 0xF) == 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      goto LABEL_40;
    }
    v13 = 16;
    goto LABEL_39;
  }
  if ( v14 < 0 )
    v20[2] = v20[2] & 0x7F | (*(_BYTE *)(v2 + 20) == 0 ? 0x80 : 0);
  if ( (v15 & 0xF) != 0 )
    v16[3] = v16[3] & 0xF0 | 4;
  v17 = v19;
  v16[2] = v16[2] & 0xF7 | (a2 == 0 ? 8 : 0);
  LOBYTE(v16) = *v16 >> 7;
  v18 = ClassModeSelect(*(_QWORD *)(a1 + 8), v8, v17, v16);
  if ( v18 >= 0 )
  {
    if ( a2 )
    {
      *(_DWORD *)(v2 + 16) = 3;
      *(_BYTE *)(v2 + 22) = 1;
    }
    else
    {
      *(_DWORD *)(v2 + 16) = 0;
      *(_BYTE *)(v2 + 22) = 0;
    }
  }
  ExFreePoolWithTag(v8, 0);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1400101c4  mov     rax, rsp
0x1400101c7  mov     [rax+10h], rbx
0x1400101cb  mov     [rax+20h], rbp
0x1400101cf  push    rsi
0x1400101d0  push    r12
0x1400101d2  push    r13
0x1400101d4  push    r14
0x1400101d6  push    r15
0x1400101d8  sub     rsp, 30h
0x1400101dc  mov     rbp, [rcx+60h]
0x1400101e0  mov     r12b, dl
0x1400101e3  mov     edx, 0C0h
0x1400101e8  mov     qword ptr [rax+18h], 0
0x1400101f0  mov     rsi, rcx
0x1400101f3  mov     [rax+8], edx
0x1400101f6  mov     r8d, 41446353h
0x1400101fc  lea     ecx, [rdx-78h]
0x1400101ff  call    cs:__imp_ExAllocatePool2
0x140010206  nop     dword ptr [rax+rax+00h]
0x14001020b  mov     r14, rax
0x14001020e  test    rax, rax
0x140010211  jnz     short loc_140010251
0x140010213  mov     rcx, cs:WPP_GLOBAL_Control
0x14001021a  lea     rbx, WPP_GLOBAL_Control
0x140010221  cmp     rcx, rbx
0x140010224  jz      short loc_140010247
0x140010226  mov     eax, [rcx+2Ch]
0x140010229  test    al, 40h
0x14001022b  jz      short loc_140010247
0x14001022d  cmp     byte ptr [rcx+29h], 2
0x140010231  jb      short loc_140010247
0x140010233  mov     rcx, [rcx+18h]
0x140010237  lea     edx, [r14+0Ch]
0x14001023b  lea     r8, WPP_a9711c54c416383df697b4e008bb3725_Traceguids
0x140010242  call    WPP_SF_
0x140010247  mov     eax, 0C000009Ah
0x14001024c  jmp     loc_140010463
0x140010251  mov     rcx, [rsi+8]
0x140010255  lea     rax, [rsp+58h+arg_10]
0x14001025a  mov     [rsp+58h+var_30], rax
0x14001025f  mov     r9, r14
0x140010262  lea     rax, [rsp+58h+arg_0]
0x140010267  mov     r8b, 1
0x14001026a  mov     [rsp+58h+var_38], rax
0x14001026f  call    DiskGetModePage
0x140010274  test    eax, eax
0x140010276  js      loc_140010414
0x14001027c  mov     r15, [rsp+58h+arg_10]
0x140010281  test    r15, r15
0x140010284  jz      loc_140010414
0x14001028a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010291  lea     rbx, WPP_GLOBAL_Control
0x140010298  cmp     rcx, rbx
0x14001029b  jz      short loc_1400102C3
0x14001029d  mov     eax, [rcx+2Ch]
0x1400102a0  test    al, 40h
0x1400102a2  jz      short loc_1400102C3
0x1400102a4  cmp     byte ptr [rcx+29h], 4
0x1400102a8  jb      short loc_1400102C3
0x1400102aa  mov     r9, [rsi+8]
0x1400102ae  lea     r8, WPP_a9711c54c416383df697b4e008bb3725_Traceguids
0x1400102b5  mov     rcx, [rcx+18h]
0x1400102b9  mov     edx, 0Eh
0x1400102be  call    WPP_SF_q
0x1400102c3  mov     al, [r15+2]
0x1400102c7  test    al, 8
0x1400102c9  jnz     short loc_1400102FA
0x1400102cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400102d2  cmp     rcx, rbx
0x1400102d5  jz      loc_14001044D
0x1400102db  mov     eax, [rcx+2Ch]
0x1400102de  test    al, 40h
0x1400102e0  jz      loc_14001044D
0x1400102e6  cmp     byte ptr [rcx+29h], 4
0x1400102ea  jb      loc_14001044D
0x1400102f0  mov     edx, 0Fh
0x1400102f5  jmp     loc_140010439
0x1400102fa  mov     rcx, [rsi+8]
0x1400102fe  mov     r13b, al
0x140010301  mov     r15b, [r15+3]
0x140010305  lea     rax, [rsp+58h+arg_10]
0x14001030a  mov     [rsp+58h+var_30], rax
0x14001030f  mov     r9, r14
0x140010312  lea     rax, [rsp+58h+arg_0]
0x140010317  xor     r8d, r8d
0x14001031a  mov     [rsp+58h+var_38], rax
0x14001031f  call    DiskGetModePage
0x140010324  test    eax, eax
0x140010326  js      loc_14001044D
0x14001032c  mov     r9, [rsp+58h+arg_10]
0x140010331  test    r9, r9
0x140010334  jz      loc_14001044D
0x14001033a  test    byte ptr [r9+3], 0Fh
0x14001033f  jnz     short loc_140010376
0x140010341  test    r15b, 0Fh
0x140010345  jnz     short loc_140010376
0x140010347  mov     rcx, cs:WPP_GLOBAL_Control
0x14001034e  cmp     rcx, rbx
0x140010351  jz      loc_14001044D
0x140010357  mov     eax, [rcx+2Ch]
0x14001035a  test    al, 40h
0x14001035c  jz      loc_14001044D
0x140010362  cmp     byte ptr [rcx+29h], 4
0x140010366  jb      loc_14001044D
0x14001036c  mov     edx, 10h
0x140010371  jmp     loc_140010439
0x140010376  test    r13b, r13b
0x140010379  jns     short loc_140010393
0x14001037b  mov     al, [rbp+14h]
0x14001037e  neg     al
0x140010380  mov     al, [r9+2]
0x140010384  sbb     cl, cl
0x140010386  and     al, 7Fh
0x140010388  not     cl
0x14001038a  and     cl, 80h
0x14001038d  or      cl, al
0x14001038f  mov     [r9+2], cl
0x140010393  test    r15b, 0Fh
0x140010397  jz      short loc_1400103A5
0x140010399  mov     al, [r9+3]
0x14001039d  and     al, 0F4h
0x14001039f  or      al, 4
0x1400103a1  mov     [r9+3], al
0x1400103a5  mov     r8d, [rsp+58h+arg_0]
0x1400103aa  mov     al, r12b
0x1400103ad  neg     al
0x1400103af  mov     rdx, r14
0x1400103b2  mov     al, [r9+2]
0x1400103b6  sbb     cl, cl
0x1400103b8  and     al, 0F7h
0x1400103ba  not     cl
0x1400103bc  and     cl, 8
0x1400103bf  or      cl, al
0x1400103c1  mov     [r9+2], cl
0x1400103c5  mov     r9b, [r9]
0x1400103c8  mov     rcx, [rsi+8]
0x1400103cc  shr     r9b, 7
0x1400103d0  call    cs:__imp_ClassModeSelect
0x1400103d7  nop     dword ptr [rax+rax+00h]
0x1400103dc  mov     ebx, eax
0x1400103de  test    eax, eax
0x1400103e0  js      short loc_1400103FF
0x1400103e2  test    r12b, r12b
0x1400103e5  jz      short loc_1400103F4
0x1400103e7  mov     dword ptr [rbp+10h], 3
0x1400103ee  mov     byte ptr [rbp+16h], 1
0x1400103f2  jmp     short loc_1400103FF
0x1400103f4  mov     dword ptr [rbp+10h], 0
0x1400103fb  mov     byte ptr [rbp+16h], 0
0x1400103ff  xor     edx, edx; Tag
0x140010401  mov     rcx, r14; P
0x140010404  call    cs:__imp_ExFreePoolWithTag
0x14001040b  nop     dword ptr [rax+rax+00h]
0x140010410  mov     eax, ebx
0x140010412  jmp     short loc_140010463
0x140010414  mov     rcx, cs:WPP_GLOBAL_Control
0x14001041b  lea     rbx, WPP_GLOBAL_Control
0x140010422  cmp     rcx, rbx
0x140010425  jz      short loc_14001044D
0x140010427  mov     eax, [rcx+2Ch]
0x14001042a  test    al, 40h
0x14001042c  jz      short loc_14001044D
0x14001042e  cmp     byte ptr [rcx+29h], 4
0x140010432  jb      short loc_14001044D
0x140010434  mov     edx, 0Dh
0x140010439  mov     r9, [rsi+8]
0x14001043d  lea     r8, WPP_a9711c54c416383df697b4e008bb3725_Traceguids
0x140010444  mov     rcx, [rcx+18h]
0x140010448  call    WPP_SF_q
0x14001044d  xor     edx, edx; Tag
0x14001044f  mov     rcx, r14; P
0x140010452  call    cs:__imp_ExFreePoolWithTag
0x140010459  nop     dword ptr [rax+rax+00h]
0x14001045e  mov     eax, 0C00000BBh
0x140010463  mov     rbx, [rsp+58h+arg_8]
0x140010468  mov     rbp, [rsp+58h+arg_18]
0x14001046d  add     rsp, 30h
0x140010471  pop     r15
0x140010473  pop     r14
0x140010475  pop     r13
0x140010477  pop     r12
0x140010479  pop     rsi
0x14001047a  retn
```
