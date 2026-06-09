# PortMgrInitPort

- ea: `0x1800238b8`
- end: `0x180023b0d`
- name: `PortMgrInitPort`
- size: `597`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001fb58`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18001a880`
- `0x18001ad40`
- `0x18001be88`
- `0x1800214f0`
- `0x1800238b8`
- `0x18002f705`

## import_xrefs

- `MobileNetworking!CreateTimer` at `0x180023a90`
- `MobileNetworking!CreateTimer` at `0x180023a90`
- `MobileNetworking!CreateReadWriteLock` at `0x18002398f`
- `MobileNetworking!CreateReadWriteLock` at `0x18002398f`

## pseudocode

```c
__int64 __fastcall PortMgrInitPort(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v3; // r14d
  int v6; // r13d
  _QWORD *v7; // rcx
  unsigned int v8; // ebx
  int v9; // r12d
  unsigned int inited; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx

  v3 = *(_DWORD *)(a1 + 20);
  v6 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    v8 = 87;
    v9 = 0;
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 68) & 1) != 0 )
      WPP_SF_(v7[7], 30, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
    goto LABEL_8;
  }
  *(_DWORD *)(a1 + 2376) = 1;
  *(_DWORD *)(a1 + 24) = 0x40000000;
  *(_QWORD *)(a1 + 8) = a1;
  *(_QWORD *)a1 = a1;
  v9 = 1;
  *(_QWORD *)(a1 + 184) = a1 + 176;
  *(_QWORD *)(a1 + 176) = a1 + 176;
  inited = CreateReadWriteLock(a1 + 2896);
  v8 = inited;
  if ( inited )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_8;
    v12 = 31;
    goto LABEL_13;
  }
  v6 = 1;
  memcpy_0((void *)(a1 + 192), a3, 0x880u);
  inited = PortMgrSetPortDefaults(a1);
  v8 = inited;
  if ( inited )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_8;
    v12 = 32;
    goto LABEL_13;
  }
  if ( *(_DWORD *)(a1 + 2376) == 1 )
  {
    inited = InitSupplicantContext(a1, a1 + 2384, a3[2]);
    v8 = inited;
    if ( inited )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_8;
      v12 = 33;
      goto LABEL_13;
    }
  }
  inited = CreateTimer(a1 + 2888, qword_18003DE00, a1 + 2896, a1, OneXTimerCallback);
  v8 = inited;
  if ( !inited )
    goto LABEL_27;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v12 = 34;
LABEL_13:
    WPP_SF_dd(v11[7], v12, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v3, inited);
  }
LABEL_8:
  PortMgrDeInitPortHelper(a1, v9, 0, v6);
LABEL_27:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x1800238b8  push    rbx
0x1800238ba  push    rbp
0x1800238bb  push    rdi
0x1800238bc  push    r12
0x1800238be  push    r13
0x1800238c0  push    r14
0x1800238c2  push    r15
0x1800238c4  sub     rsp, 30h
0x1800238c8  mov     r14d, [rcx+14h]
0x1800238cc  mov     rbp, r8
0x1800238cf  mov     rdi, rcx
0x1800238d2  xor     r13d, r13d
0x1800238d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238dc  lea     rax, WPP_GLOBAL_Control
0x1800238e3  cmp     rcx, rax
0x1800238e6  jz      short loc_180023913
0x1800238e8  test    dword ptr [rcx+44h], 800h
0x1800238ef  jz      short loc_180023913
0x1800238f1  mov     rcx, [rcx+38h]
0x1800238f5  lea     edx, [r13+1Dh]
0x1800238f9  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180023900  call    WPP_SF_
0x180023905  mov     rcx, cs:WPP_GLOBAL_Control
0x18002390c  lea     rax, WPP_GLOBAL_Control
0x180023913  test    rbp, rbp
0x180023916  jnz     short loc_180023959
0x180023918  lea     ebx, [rbp+57h]
0x18002391b  xor     r12d, r12d
0x18002391e  cmp     rcx, rax
0x180023921  jz      short loc_18002393C
0x180023923  test    byte ptr [rcx+44h], 1
0x180023927  jz      short loc_18002393C
0x180023929  mov     rcx, [rcx+38h]
0x18002392d  lea     edx, [rbp+1Eh]
0x180023930  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180023937  call    WPP_SF_
0x18002393c  lea     rbp, WPP_GLOBAL_Control
0x180023943  mov     r9d, r13d
0x180023946  xor     r8d, r8d
0x180023949  mov     edx, r12d
0x18002394c  mov     rcx, rdi
0x18002394f  call    PortMgrDeInitPortHelper
0x180023954  jmp     loc_180023ACE
0x180023959  mov     dword ptr [rdi+948h], 1
0x180023963  lea     rax, [rdi+0B0h]
0x18002396a  mov     dword ptr [rdi+18h], 40000000h
0x180023971  lea     r15, [rdi+0B50h]
0x180023978  mov     [rdi+8], rdi
0x18002397c  mov     rcx, r15
0x18002397f  mov     [rdi], rdi
0x180023982  mov     r12d, 1
0x180023988  mov     [rax+8], rax
0x18002398c  mov     [rax], rax
0x18002398f  call    cs:__imp_CreateReadWriteLock
0x180023995  mov     ebx, eax
0x180023997  test    eax, eax
0x180023999  jz      short loc_1800239D5
0x18002399b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239a2  lea     rbp, WPP_GLOBAL_Control
0x1800239a9  cmp     rcx, rbp
0x1800239ac  jz      short loc_180023943
0x1800239ae  test    [rcx+44h], r12b
0x1800239b2  jz      short loc_180023943
0x1800239b4  lea     edx, [r12+1Eh]
0x1800239b9  mov     rcx, [rcx+38h]
0x1800239bd  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x1800239c4  mov     r9d, r14d
0x1800239c7  mov     dword ptr [rsp+68h+var_48], eax
0x1800239cb  call    WPP_SF_dd
0x1800239d0  jmp     loc_180023943
0x1800239d5  lea     rcx, [rdi+0C0h]; void *
0x1800239dc  mov     rdx, rbp; Src
0x1800239df  mov     r8d, 880h; Size
0x1800239e5  mov     r13d, r12d
0x1800239e8  call    memcpy_0
0x1800239ed  mov     rcx, rdi
0x1800239f0  call    PortMgrSetPortDefaults
0x1800239f5  mov     ebx, eax
0x1800239f7  test    eax, eax
0x1800239f9  jz      short loc_180023A23
0x1800239fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a02  lea     rbp, WPP_GLOBAL_Control
0x180023a09  cmp     rcx, rbp
0x180023a0c  jz      loc_180023943
0x180023a12  test    [rcx+44h], r12b
0x180023a16  jz      loc_180023943
0x180023a1c  mov     edx, 20h ; ' '
0x180023a21  jmp     short loc_1800239B9
0x180023a23  cmp     [rdi+948h], r12d
0x180023a2a  jnz     short loc_180023A70
0x180023a2c  mov     r8d, [rbp+8]
0x180023a30  lea     rdx, [rdi+950h]
0x180023a37  mov     rcx, rdi
0x180023a3a  call    InitSupplicantContext
0x180023a3f  mov     ebx, eax
0x180023a41  test    eax, eax
0x180023a43  jz      short loc_180023A70
0x180023a45  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a4c  lea     rbp, WPP_GLOBAL_Control
0x180023a53  cmp     rcx, rbp
0x180023a56  jz      loc_180023943
0x180023a5c  test    [rcx+44h], r12b
0x180023a60  jz      loc_180023943
0x180023a66  mov     edx, 21h ; '!'
0x180023a6b  jmp     loc_1800239B9
0x180023a70  mov     rdx, cs:qword_18003DE00
0x180023a77  lea     rax, OneXTimerCallback
0x180023a7e  lea     rcx, [rdi+0B48h]
0x180023a85  mov     [rsp+68h+var_48], rax
0x180023a8a  mov     r9, rdi
0x180023a8d  mov     r8, r15
0x180023a90  call    cs:__imp_CreateTimer
0x180023a96  mov     ebx, eax
0x180023a98  test    eax, eax
0x180023a9a  jz      short loc_180023AC7
0x180023a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023aa3  lea     rbp, WPP_GLOBAL_Control
0x180023aaa  cmp     rcx, rbp
0x180023aad  jz      loc_180023943
0x180023ab3  test    [rcx+44h], r12b
0x180023ab7  jz      loc_180023943
0x180023abd  mov     edx, 22h ; '"'
0x180023ac2  jmp     loc_1800239B9
0x180023ac7  lea     rbp, WPP_GLOBAL_Control
0x180023ace  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ad5  cmp     rcx, rbp
0x180023ad8  jz      short loc_180023AFB
0x180023ada  test    dword ptr [rcx+44h], 800h
0x180023ae1  jz      short loc_180023AFB
0x180023ae3  mov     rcx, [rcx+38h]
0x180023ae7  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180023aee  mov     edx, 23h ; '#'
0x180023af3  mov     r9d, ebx
0x180023af6  call    WPP_SF_D
0x180023afb  mov     eax, ebx
0x180023afd  add     rsp, 30h
0x180023b01  pop     r15
0x180023b03  pop     r14
0x180023b05  pop     r13
0x180023b07  pop     r12
0x180023b09  pop     rdi
0x180023b0a  pop     rbp
0x180023b0b  pop     rbx
0x180023b0c  retn
```
