# HsmpBitmapCreateSnapshot

- ea: `0x140044ed4`
- end: `0x1400451a6`
- name: `HsmpBitmapCreateSnapshot`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400845b0`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14000d95c`
- `0x14003659c`
- `0x140044ed4`
- `0x1400704ac`

## import_xrefs

- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x14004510f`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x14004510f`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140045014`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140045014`
- `ntoskrnl!ExAllocatePool2` at `0x140044f1c`
- `ntoskrnl!ExAllocatePool2` at `0x140044f1c`

## pseudocode

```c
__int64 __fastcall HsmpBitmapCreateSnapshot(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 *v5; // r12
  __int64 Pool2; // rax
  __int64 v8; // rbx
  int Range; // esi
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // edi
  __int64 v13; // rax
  unsigned int v14; // r13d
  __int64 v15; // rax
  __int64 v17; // [rsp+30h] [rbp-10h] BYREF
  __int64 v18; // [rsp+80h] [rbp+40h] BYREF
  __int64 v19; // [rsp+88h] [rbp+48h] BYREF
  char v20; // [rsp+90h] [rbp+50h] BYREF

  v19 = a2;
  v18 = a1;
  v5 = a5;
  v17 = 0;
  v20 = 0;
  *a5 = 0;
  Pool2 = ExAllocatePool2(64, 72, 1833071432);
  v8 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)(Pool2 + 16) = *(_DWORD *)(Pool2 + 16) & 0xFFFFFFF8 | 1;
    *(_DWORD *)(Pool2 + 20) = 1;
    Range = *(_DWORD *)(a4 + 24);
    if ( Range >= 0 )
    {
      if ( v19 >= *(_QWORD *)(a4 + 8) )
        v19 = *(_QWORD *)(a4 + 8);
      v12 = *(_DWORD *)(Pool2 + 16) ^ (*(_DWORD *)(a4 + 16) ^ *(_DWORD *)(Pool2 + 16)) & 0xFC0;
      *(_DWORD *)(Pool2 + 16) = v12;
      if ( FsRtlInitializeBaseMcbEx((PBASE_MCB)(Pool2 + 48), PagedPool, 0) )
      {
        Range = 0;
        *(_QWORD *)(v8 + 32) = v18;
        v13 = v19;
        *(_DWORD *)(v8 + 16) |= 0x20u;
        *(_QWORD *)(v8 + 8) = v13;
        v15 = v18;
        while ( 1 )
        {
          if ( v15 >= v19 )
          {
            *(_DWORD *)(v8 + 16) |= 8u;
            *v5 = v8;
            return (unsigned int)Range;
          }
          Range = HsmpBitmapQueryRange(a4, (unsigned int)&v18, (unsigned int)&v19, (unsigned int)&v20, (__int64)&v17);
          HsmDbgBreakOnStatus(Range);
          if ( Range < 0 )
            break;
          if ( v20 )
          {
            v14 = 1 << ((v12 >> 6) & 0x3F);
            if ( !FsRtlAddBaseMcbEntry(
                    (PBASE_MCB)(v8 + 48),
                    v18 / v14,
                    v18 / v14 + 1,
                    (v14 + v17 - 1) / v14 - v18 / v14) )
            {
              Range = -1073741670;
              HsmDbgBreakOnStatus(-1073741670);
              goto LABEL_30;
            }
          }
          v15 = v17;
          v18 = v17;
        }
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v11 = 171;
          goto LABEL_29;
        }
      }
      else
      {
        Range = -1073741670;
        HsmDbgBreakOnStatus(-1073741670);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            170,
            WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids,
            3221225626LL);
        }
      }
    }
    else
    {
      HsmDbgBreakOnStatus(Range);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v11 = 169;
LABEL_29:
        WPP_SF_qd(v10->AttachedDevice, v11, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids, a4, Range);
      }
    }
LABEL_30:
    HsmpBitmapRelease(v8);
  }
  else
  {
    Range = -1073741670;
    HsmDbgBreakOnStatus(-1073741670);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 168, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids, 3221225626LL);
    }
  }
  return (unsigned int)Range;
}

```

## disassembly

```asm
0x140044ed4  mov     rax, rsp
0x140044ed7  mov     [rax+20h], rbx
0x140044edb  mov     [rax+18h], r8b
0x140044edf  mov     [rax+10h], rdx
0x140044ee3  mov     [rax+8], rcx
0x140044ee7  push    rbp
0x140044ee8  push    rsi
0x140044ee9  push    rdi
0x140044eea  push    r12
0x140044eec  push    r13
0x140044eee  push    r14
0x140044ef0  push    r15
0x140044ef2  mov     rbp, rsp
0x140044ef5  sub     rsp, 40h
0x140044ef9  mov     r12, [rbp+arg_20]
0x140044efd  xor     r13d, r13d
0x140044f00  mov     r8d, 6D427348h
0x140044f06  mov     [rbp+var_10], r13
0x140044f0a  mov     r15, r9
0x140044f0d  mov     [rbp+arg_10], r13b
0x140044f11  lea     edx, [r13+48h]
0x140044f15  mov     [r12], r13
0x140044f19  lea     ecx, [rdx-8]
0x140044f1c  call    cs:__imp_ExAllocatePool2
0x140044f23  nop     dword ptr [rax+rax+00h]
0x140044f28  mov     rbx, rax
0x140044f2b  test    rax, rax
0x140044f2e  jnz     short loc_140044F8C
0x140044f30  mov     edi, 0C000009Ah
0x140044f35  mov     ecx, edi
0x140044f37  mov     esi, edi
0x140044f39  call    HsmDbgBreakOnStatus
0x140044f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140044f45  lea     rax, WPP_GLOBAL_Control
0x140044f4c  cmp     rcx, rax
0x140044f4f  jz      loc_14004518B
0x140044f55  mov     eax, [rcx+2Ch]
0x140044f58  lea     r14d, [r13+1]
0x140044f5c  test    r14b, al
0x140044f5f  jz      loc_14004518B
0x140044f65  cmp     byte ptr [rcx+29h], 2
0x140044f69  jb      loc_14004518B
0x140044f6f  mov     rcx, [rcx+18h]
0x140044f73  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x140044f7a  mov     edx, 0A8h
0x140044f7f  mov     r9d, edi
0x140044f82  call    WPP_SF_d
0x140044f87  jmp     loc_14004518B
0x140044f8c  mov     eax, [rax+10h]
0x140044f8f  mov     r14d, 1
0x140044f95  and     eax, 0FFFFFFF9h
0x140044f98  or      eax, r14d
0x140044f9b  mov     [rbx+10h], eax
0x140044f9e  mov     [rbx+14h], r14d
0x140044fa2  mov     esi, [r15+18h]
0x140044fa6  test    esi, esi
0x140044fa8  jns     short loc_140044FE8
0x140044faa  mov     ecx, esi
0x140044fac  call    HsmDbgBreakOnStatus
0x140044fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140044fb8  lea     rax, WPP_GLOBAL_Control
0x140044fbf  cmp     rcx, rax
0x140044fc2  jz      loc_140045179
0x140044fc8  mov     eax, [rcx+2Ch]
0x140044fcb  test    r14b, al
0x140044fce  jz      loc_140045179
0x140044fd4  cmp     byte ptr [rcx+29h], 2
0x140044fd8  jb      loc_140045179
0x140044fde  mov     edx, 0A9h
0x140044fe3  jmp     loc_140045162
0x140044fe8  mov     rax, [r15+8]
0x140044fec  cmp     [rbp+arg_8], rax
0x140044ff0  jl      short loc_140044FF6
0x140044ff2  mov     [rbp+arg_8], rax
0x140044ff6  mov     eax, [rbx+10h]
0x140044ff9  lea     rcx, [rbx+30h]; Mcb
0x140044ffd  mov     edi, eax
0x140044fff  xor     r8d, r8d; Flags
0x140045002  xor     edi, [r15+10h]
0x140045006  mov     edx, r14d; PoolType
0x140045009  and     edi, 0FC0h
0x14004500f  xor     edi, eax
0x140045011  mov     [rbx+10h], edi
0x140045014  call    cs:__imp_FsRtlInitializeBaseMcbEx
0x14004501b  nop     dword ptr [rax+rax+00h]
0x140045020  test    al, al
0x140045022  jnz     short loc_14004507C
0x140045024  mov     edi, 0C000009Ah
0x140045029  mov     ecx, edi
0x14004502b  mov     esi, edi
0x14004502d  call    HsmDbgBreakOnStatus
0x140045032  mov     rcx, cs:WPP_GLOBAL_Control
0x140045039  lea     rax, WPP_GLOBAL_Control
0x140045040  cmp     rcx, rax
0x140045043  jz      loc_140045179
0x140045049  mov     eax, [rcx+2Ch]
0x14004504c  test    r14b, al
0x14004504f  jz      loc_140045179
0x140045055  cmp     byte ptr [rcx+29h], 2
0x140045059  jb      loc_140045179
0x14004505f  mov     rcx, [rcx+18h]
0x140045063  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x14004506a  mov     edx, 0AAh
0x14004506f  mov     r9d, edi
0x140045072  call    WPP_SF_d
0x140045077  jmp     loc_140045179
0x14004507c  mov     rax, [rbp+arg_0]
0x140045080  mov     esi, r13d
0x140045083  shr     edi, 6
0x140045086  mov     r13d, r14d
0x140045089  and     edi, 3Fh
0x14004508c  mov     [rbx+20h], rax
0x140045090  mov     rax, [rbp+arg_8]
0x140045094  mov     cl, dil
0x140045097  shl     r13d, cl
0x14004509a  or      dword ptr [rbx+10h], 20h
0x14004509e  mov     [rbx+8], rax
0x1400450a2  mov     rax, [rbp+arg_0]
0x1400450a6  cmp     rax, [rbp+arg_8]
0x1400450aa  jge     loc_140045183
0x1400450b0  lea     rax, [rbp+var_10]
0x1400450b4  mov     rcx, r15
0x1400450b7  lea     r9, [rbp+arg_10]
0x1400450bb  mov     [rsp+40h+var_20], rax
0x1400450c0  lea     r8, [rbp+arg_8]
0x1400450c4  lea     rdx, [rbp+arg_0]
0x1400450c8  call    HsmpBitmapQueryRange
0x1400450cd  mov     ecx, eax
0x1400450cf  mov     esi, eax
0x1400450d1  call    HsmDbgBreakOnStatus
0x1400450d6  test    esi, esi
0x1400450d8  js      short loc_14004513C
0x1400450da  cmp     [rbp+arg_10], 0
0x1400450de  jz      short loc_14004511F
0x1400450e0  mov     rax, [rbp+arg_0]
0x1400450e4  lea     rcx, [rbx+30h]; Mcb
0x1400450e8  cqo
0x1400450ea  mov     r8d, r13d
0x1400450ed  idiv    r8
0x1400450f0  mov     r10, rax
0x1400450f3  mov     rax, [rbp+var_10]
0x1400450f7  dec     rax
0x1400450fa  add     rax, r8
0x1400450fd  cqo
0x1400450ff  idiv    r8
0x140045102  lea     r8, [r10+1]; Lbn
0x140045106  mov     rdx, r10; Vbn
0x140045109  sub     rax, r10
0x14004510c  mov     r9, rax; SectorCount
0x14004510f  call    cs:__imp_FsRtlAddBaseMcbEntry
0x140045116  nop     dword ptr [rax+rax+00h]
0x14004511b  test    al, al
0x14004511d  jz      short loc_14004512C
0x14004511f  mov     rax, [rbp+var_10]
0x140045123  mov     [rbp+arg_0], rax
0x140045127  jmp     loc_1400450A6
0x14004512c  mov     edi, 0C000009Ah
0x140045131  mov     ecx, edi
0x140045133  mov     esi, edi
0x140045135  call    HsmDbgBreakOnStatus
0x14004513a  jmp     short loc_140045179
0x14004513c  mov     rcx, cs:WPP_GLOBAL_Control
0x140045143  lea     rax, WPP_GLOBAL_Control
0x14004514a  cmp     rcx, rax
0x14004514d  jz      short loc_140045179
0x14004514f  mov     eax, [rcx+2Ch]
0x140045152  test    r14b, al
0x140045155  jz      short loc_140045179
0x140045157  cmp     byte ptr [rcx+29h], 2
0x14004515b  jb      short loc_140045179
0x14004515d  mov     edx, 0ABh
0x140045162  mov     rcx, [rcx+18h]
0x140045166  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x14004516d  mov     r9, r15
0x140045170  mov     dword ptr [rsp+40h+var_20], esi
0x140045174  call    WPP_SF_qd
0x140045179  mov     rcx, rbx
0x14004517c  call    HsmpBitmapRelease
0x140045181  jmp     short loc_14004518B
0x140045183  or      dword ptr [rbx+10h], 8
0x140045187  mov     [r12], rbx
0x14004518b  mov     rbx, [rsp+40h+arg_18]
0x140045193  mov     eax, esi
0x140045195  add     rsp, 40h
0x140045199  pop     r15
0x14004519b  pop     r14
0x14004519d  pop     r13
0x14004519f  pop     r12
0x1400451a1  pop     rdi
0x1400451a2  pop     rsi
0x1400451a3  pop     rbp
0x1400451a4  retn
```
