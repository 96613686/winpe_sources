# DfscAgeOutExpiredCacheEntries

- ea: `0x140026d10`
- end: `0x140026ebb`
- name: `DfscAgeOutExpiredCacheEntries`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400010d0`

## callees

- `0x1400026a4`
- `0x1400199e4`
- `0x14001d090`
- `0x140026d10`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x140026e31`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140026e31`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026dea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026e05`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026dea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026e05`
- `ntoskrnl!ExReleaseResourceLite` at `0x140026dde`
- `ntoskrnl!ExReleaseResourceLite` at `0x140026df9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140026dde`
- `ntoskrnl!ExReleaseResourceLite` at `0x140026df9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140026d4c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140026d76`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140026d4c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140026d76`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026d31`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026d58`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026d31`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026d58`

## pseudocode

```c
__int64 __fastcall DfscAgeOutExpiredCacheEntries(__int64 a1)
{
  unsigned int v2; // r15d
  __int64 v3; // rbx
  struct _ERESOURCE *v4; // r13
  struct _ERESOURCE *v5; // rsi
  __int64 v6; // rdi
  __int64 v7; // r12
  bool v8; // zf
  __int64 v9; // r14
  int v11; // esi
  __int64 v12; // rbp
  __int64 v13; // rcx
  struct _ERESOURCE *v14; // [rsp+70h] [rbp+8h]
  struct _ERESOURCE *v15; // [rsp+78h] [rbp+10h]

  v2 = 0;
  v3 = MEMORY[0xFFFFF78000000320];
  KeEnterCriticalRegion();
  v4 = (struct _ERESOURCE *)(a1 + 56);
  v14 = (struct _ERESOURCE *)(a1 + 56);
  ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 56), 1u);
  KeEnterCriticalRegion();
  v5 = (struct _ERESOURCE *)(a1 + 160);
  v15 = (struct _ERESOURCE *)(a1 + 160);
  ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 160), 1u);
  v6 = *(_QWORD *)(a1 + 32);
  if ( DWORD2(xmmword_14000C750) )
  {
    v7 = a1 + 24;
    do
    {
      if ( v6 == v7 )
        break;
      v8 = (*(_BYTE *)(v6 - 36) & 1) == 0;
      v9 = v6 - 48;
      v6 = *(_QWORD *)(v6 + 8);
      if ( !v8 && *(int *)(v9 + 4) <= 1 )
      {
        v11 = *(_DWORD *)(v9 + 40);
        v12 = *(_QWORD *)(v9 + 32);
        v13 = 10000000 * (unsigned __int64)(unsigned int)(HIDWORD(xmmword_14000C750) * v11) / KeQueryTimeIncrement()
            + v12;
        if ( v13 )
        {
          if ( v3 >= v13 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
            {
              WPP_SF_qZ(
                WPP_GLOBAL_Control->AttachedDevice,
                32,
                (unsigned int)WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids,
                v9,
                v9 + 144);
            }
            ++v2;
            DfscRmUnlinkReferral(v9);
            DfscRmDereferenceReferral((volatile signed __int32 *)v9);
          }
        }
      }
    }
    while ( v2 < DWORD2(xmmword_14000C750) );
    v4 = v14;
    v5 = v15;
  }
  ExReleaseResourceLite(v5);
  KeLeaveCriticalRegion();
  ExReleaseResourceLite(v4);
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x140026d10  push    rbx
0x140026d12  push    rsi
0x140026d13  push    rdi
0x140026d14  push    r12
0x140026d16  push    r13
0x140026d18  push    r15
0x140026d1a  sub     rsp, 38h
0x140026d1e  mov     rbx, 0FFFFF78000000320h
0x140026d28  mov     r12, rcx
0x140026d2b  xor     r15d, r15d
0x140026d2e  mov     rbx, [rbx]
0x140026d31  call    cs:__imp_KeEnterCriticalRegion
0x140026d38  nop     dword ptr [rax+rax+00h]
0x140026d3d  lea     r13, [r12+38h]
0x140026d42  mov     dl, 1; Wait
0x140026d44  mov     rcx, r13; Resource
0x140026d47  mov     [rsp+68h+arg_0], r13
0x140026d4c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140026d53  nop     dword ptr [rax+rax+00h]
0x140026d58  call    cs:__imp_KeEnterCriticalRegion
0x140026d5f  nop     dword ptr [rax+rax+00h]
0x140026d64  lea     rsi, [r12+0A0h]
0x140026d6c  mov     dl, 1; Wait
0x140026d6e  mov     rcx, rsi; Resource
0x140026d71  mov     [rsp+68h+arg_8], rsi
0x140026d76  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140026d7d  nop     dword ptr [rax+rax+00h]
0x140026d82  cmp     dword ptr cs:xmmword_14000C750+8, r15d
0x140026d89  mov     rdi, [r12+20h]
0x140026d8e  jz      short loc_140026DDB
0x140026d90  mov     [rsp+68h+arg_10], rbp
0x140026d98  lea     r13, WPP_GLOBAL_Control
0x140026d9f  mov     [rsp+68h+var_38], r14
0x140026da4  add     r12, 18h
0x140026da8  cmp     rdi, r12
0x140026dab  jz      short loc_140026DC4
0x140026dad  test    byte ptr [rdi-24h], 1
0x140026db1  lea     r14, [rdi-30h]
0x140026db5  mov     rdi, [rdi+8]
0x140026db9  jnz     short loc_140026E22
0x140026dbb  cmp     r15d, dword ptr cs:xmmword_14000C750+8
0x140026dc2  jb      short loc_140026DA8
0x140026dc4  mov     r13, [rsp+68h+arg_0]
0x140026dc9  mov     rsi, [rsp+68h+arg_8]
0x140026dce  mov     r14, [rsp+68h+var_38]
0x140026dd3  mov     rbp, [rsp+68h+arg_10]
0x140026ddb  mov     rcx, rsi; Resource
0x140026dde  call    cs:__imp_ExReleaseResourceLite
0x140026de5  nop     dword ptr [rax+rax+00h]
0x140026dea  call    cs:__imp_KeLeaveCriticalRegion
0x140026df1  nop     dword ptr [rax+rax+00h]
0x140026df6  mov     rcx, r13; Resource
0x140026df9  call    cs:__imp_ExReleaseResourceLite
0x140026e00  nop     dword ptr [rax+rax+00h]
0x140026e05  call    cs:__imp_KeLeaveCriticalRegion
0x140026e0c  nop     dword ptr [rax+rax+00h]
0x140026e11  xor     eax, eax
0x140026e13  add     rsp, 38h
0x140026e17  pop     r15
0x140026e19  pop     r13
0x140026e1b  pop     r12
0x140026e1d  pop     rdi
0x140026e1e  pop     rsi
0x140026e1f  pop     rbx
0x140026e20  retn
0x140026e22  cmp     dword ptr [r14+4], 1
0x140026e27  jg      short loc_140026DBB
0x140026e29  mov     esi, [r14+28h]
0x140026e2d  mov     rbp, [r14+20h]
0x140026e31  call    cs:__imp_KeQueryTimeIncrement
0x140026e38  nop     dword ptr [rax+rax+00h]
0x140026e3d  imul    esi, dword ptr cs:xmmword_14000C750+0Ch
0x140026e44  xor     edx, edx
0x140026e46  mov     ecx, eax
0x140026e48  mov     eax, esi
0x140026e4a  imul    rax, 989680h
0x140026e51  div     rcx
0x140026e54  lea     rcx, [rax+rbp]
0x140026e58  test    rcx, rcx
0x140026e5b  jz      loc_140026DBB
0x140026e61  cmp     rbx, rcx
0x140026e64  jl      loc_140026DBB
0x140026e6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140026e71  cmp     rcx, r13
0x140026e74  jz      short loc_140026EA3
0x140026e76  test    dword ptr [rcx+2Ch], 400000h
0x140026e7d  jz      short loc_140026EA3
0x140026e7f  mov     rcx, [rcx+18h]
0x140026e83  lea     rax, [r14+90h]
0x140026e8a  mov     edx, 20h ; ' '
0x140026e8f  mov     [rsp+68h+var_48], rax
0x140026e94  mov     r9, r14
0x140026e97  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x140026e9e  call    WPP_SF_qZ
0x140026ea3  mov     rcx, r14
0x140026ea6  inc     r15d
0x140026ea9  call    DfscRmUnlinkReferral
0x140026eae  mov     rcx, r14; P
0x140026eb1  call    DfscRmDereferenceReferral
0x140026eb6  jmp     loc_140026DBB
```
