# HsmpBitmapCreateSnapshot

- ea: `0x140044de4`
- end: `0x1400450b6`
- name: `HsmpBitmapCreateSnapshot`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400843f8`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14000d95c`
- `0x14003659c`
- `0x140044de4`
- `0x14007038c`

## import_xrefs

- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x14004501f`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x14004501f`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140044f24`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140044f24`
- `ntoskrnl!ExAllocatePool2` at `0x140044e2c`
- `ntoskrnl!ExAllocatePool2` at `0x140044e2c`

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
          HsmDbgBreakOnStatus((unsigned int)Range);
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
              HsmDbgBreakOnStatus(3221225626LL);
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
        HsmDbgBreakOnStatus(3221225626LL);
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
      HsmDbgBreakOnStatus((unsigned int)Range);
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
    HsmDbgBreakOnStatus(3221225626LL);
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
0x140044de4  mov     rax, rsp
0x140044de7  mov     [rax+20h], rbx
0x140044deb  mov     [rax+18h], r8b
0x140044def  mov     [rax+10h], rdx
0x140044df3  mov     [rax+8], rcx
0x140044df7  push    rbp
0x140044df8  push    rsi
0x140044df9  push    rdi
0x140044dfa  push    r12
0x140044dfc  push    r13
0x140044dfe  push    r14
0x140044e00  push    r15
0x140044e02  mov     rbp, rsp
0x140044e05  sub     rsp, 40h
0x140044e09  mov     r12, [rbp+arg_20]
0x140044e0d  xor     r13d, r13d
0x140044e10  mov     r8d, 6D427348h
0x140044e16  mov     [rbp+var_10], r13
0x140044e1a  mov     r15, r9
0x140044e1d  mov     [rbp+arg_10], r13b
0x140044e21  lea     edx, [r13+48h]
0x140044e25  mov     [r12], r13
0x140044e29  lea     ecx, [rdx-8]
0x140044e2c  call    cs:__imp_ExAllocatePool2
0x140044e33  nop     dword ptr [rax+rax+00h]
0x140044e38  mov     rbx, rax
0x140044e3b  test    rax, rax
0x140044e3e  jnz     short loc_140044E9C
0x140044e40  mov     edi, 0C000009Ah
0x140044e45  mov     ecx, edi
0x140044e47  mov     esi, edi
0x140044e49  call    HsmDbgBreakOnStatus
0x140044e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140044e55  lea     rax, WPP_GLOBAL_Control
0x140044e5c  cmp     rcx, rax
0x140044e5f  jz      loc_14004509B
0x140044e65  mov     eax, [rcx+2Ch]
0x140044e68  lea     r14d, [r13+1]
0x140044e6c  test    r14b, al
0x140044e6f  jz      loc_14004509B
0x140044e75  cmp     byte ptr [rcx+29h], 2
0x140044e79  jb      loc_14004509B
0x140044e7f  mov     rcx, [rcx+18h]
0x140044e83  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x140044e8a  mov     edx, 0A8h
0x140044e8f  mov     r9d, edi
0x140044e92  call    WPP_SF_d
0x140044e97  jmp     loc_14004509B
0x140044e9c  mov     eax, [rax+10h]
0x140044e9f  mov     r14d, 1
0x140044ea5  and     eax, 0FFFFFFF9h
0x140044ea8  or      eax, r14d
0x140044eab  mov     [rbx+10h], eax
0x140044eae  mov     [rbx+14h], r14d
0x140044eb2  mov     esi, [r15+18h]
0x140044eb6  test    esi, esi
0x140044eb8  jns     short loc_140044EF8
0x140044eba  mov     ecx, esi
0x140044ebc  call    HsmDbgBreakOnStatus
0x140044ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x140044ec8  lea     rax, WPP_GLOBAL_Control
0x140044ecf  cmp     rcx, rax
0x140044ed2  jz      loc_140045089
0x140044ed8  mov     eax, [rcx+2Ch]
0x140044edb  test    r14b, al
0x140044ede  jz      loc_140045089
0x140044ee4  cmp     byte ptr [rcx+29h], 2
0x140044ee8  jb      loc_140045089
0x140044eee  mov     edx, 0A9h
0x140044ef3  jmp     loc_140045072
0x140044ef8  mov     rax, [r15+8]
0x140044efc  cmp     [rbp+arg_8], rax
0x140044f00  jl      short loc_140044F06
0x140044f02  mov     [rbp+arg_8], rax
0x140044f06  mov     eax, [rbx+10h]
0x140044f09  lea     rcx, [rbx+30h]; Mcb
0x140044f0d  mov     edi, eax
0x140044f0f  xor     r8d, r8d; Flags
0x140044f12  xor     edi, [r15+10h]
0x140044f16  mov     edx, r14d; PoolType
0x140044f19  and     edi, 0FC0h
0x140044f1f  xor     edi, eax
0x140044f21  mov     [rbx+10h], edi
0x140044f24  call    cs:__imp_FsRtlInitializeBaseMcbEx
0x140044f2b  nop     dword ptr [rax+rax+00h]
0x140044f30  test    al, al
0x140044f32  jnz     short loc_140044F8C
0x140044f34  mov     edi, 0C000009Ah
0x140044f39  mov     ecx, edi
0x140044f3b  mov     esi, edi
0x140044f3d  call    HsmDbgBreakOnStatus
0x140044f42  mov     rcx, cs:WPP_GLOBAL_Control
0x140044f49  lea     rax, WPP_GLOBAL_Control
0x140044f50  cmp     rcx, rax
0x140044f53  jz      loc_140045089
0x140044f59  mov     eax, [rcx+2Ch]
0x140044f5c  test    r14b, al
0x140044f5f  jz      loc_140045089
0x140044f65  cmp     byte ptr [rcx+29h], 2
0x140044f69  jb      loc_140045089
0x140044f6f  mov     rcx, [rcx+18h]
0x140044f73  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x140044f7a  mov     edx, 0AAh
0x140044f7f  mov     r9d, edi
0x140044f82  call    WPP_SF_d
0x140044f87  jmp     loc_140045089
0x140044f8c  mov     rax, [rbp+arg_0]
0x140044f90  mov     esi, r13d
0x140044f93  shr     edi, 6
0x140044f96  mov     r13d, r14d
0x140044f99  and     edi, 3Fh
0x140044f9c  mov     [rbx+20h], rax
0x140044fa0  mov     rax, [rbp+arg_8]
0x140044fa4  mov     cl, dil
0x140044fa7  shl     r13d, cl
0x140044faa  or      dword ptr [rbx+10h], 20h
0x140044fae  mov     [rbx+8], rax
0x140044fb2  mov     rax, [rbp+arg_0]
0x140044fb6  cmp     rax, [rbp+arg_8]
0x140044fba  jge     loc_140045093
0x140044fc0  lea     rax, [rbp+var_10]
0x140044fc4  mov     rcx, r15
0x140044fc7  lea     r9, [rbp+arg_10]
0x140044fcb  mov     [rsp+40h+var_20], rax
0x140044fd0  lea     r8, [rbp+arg_8]
0x140044fd4  lea     rdx, [rbp+arg_0]
0x140044fd8  call    HsmpBitmapQueryRange
0x140044fdd  mov     ecx, eax
0x140044fdf  mov     esi, eax
0x140044fe1  call    HsmDbgBreakOnStatus
0x140044fe6  test    esi, esi
0x140044fe8  js      short loc_14004504C
0x140044fea  cmp     [rbp+arg_10], 0
0x140044fee  jz      short loc_14004502F
0x140044ff0  mov     rax, [rbp+arg_0]
0x140044ff4  lea     rcx, [rbx+30h]; Mcb
0x140044ff8  cqo
0x140044ffa  mov     r8d, r13d
0x140044ffd  idiv    r8
0x140045000  mov     r10, rax
0x140045003  mov     rax, [rbp+var_10]
0x140045007  dec     rax
0x14004500a  add     rax, r8
0x14004500d  cqo
0x14004500f  idiv    r8
0x140045012  lea     r8, [r10+1]; Lbn
0x140045016  mov     rdx, r10; Vbn
0x140045019  sub     rax, r10
0x14004501c  mov     r9, rax; SectorCount
0x14004501f  call    cs:__imp_FsRtlAddBaseMcbEntry
0x140045026  nop     dword ptr [rax+rax+00h]
0x14004502b  test    al, al
0x14004502d  jz      short loc_14004503C
0x14004502f  mov     rax, [rbp+var_10]
0x140045033  mov     [rbp+arg_0], rax
0x140045037  jmp     loc_140044FB6
0x14004503c  mov     edi, 0C000009Ah
0x140045041  mov     ecx, edi
0x140045043  mov     esi, edi
0x140045045  call    HsmDbgBreakOnStatus
0x14004504a  jmp     short loc_140045089
0x14004504c  mov     rcx, cs:WPP_GLOBAL_Control
0x140045053  lea     rax, WPP_GLOBAL_Control
0x14004505a  cmp     rcx, rax
0x14004505d  jz      short loc_140045089
0x14004505f  mov     eax, [rcx+2Ch]
0x140045062  test    r14b, al
0x140045065  jz      short loc_140045089
0x140045067  cmp     byte ptr [rcx+29h], 2
0x14004506b  jb      short loc_140045089
0x14004506d  mov     edx, 0ABh
0x140045072  mov     rcx, [rcx+18h]
0x140045076  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x14004507d  mov     r9, r15
0x140045080  mov     dword ptr [rsp+40h+var_20], esi
0x140045084  call    WPP_SF_qd
0x140045089  mov     rcx, rbx
0x14004508c  call    HsmpBitmapRelease
0x140045091  jmp     short loc_14004509B
0x140045093  or      dword ptr [rbx+10h], 8
0x140045097  mov     [r12], rbx
0x14004509b  mov     rbx, [rsp+40h+arg_18]
0x1400450a3  mov     eax, esi
0x1400450a5  add     rsp, 40h
0x1400450a9  pop     r15
0x1400450ab  pop     r14
0x1400450ad  pop     r13
0x1400450af  pop     r12
0x1400450b1  pop     rdi
0x1400450b2  pop     rsi
0x1400450b3  pop     rbp
0x1400450b4  retn
```
