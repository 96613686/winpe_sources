# ClfsRemoveContainersInternal

- ea: `0x1400550cc`
- end: `0x140055283`
- name: `ClfsRemoveContainersInternal`
- size: `439`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140034a38`
- `0x1400548c4`

## callees

- `0x14000c2f0`
- `0x14000ed64`
- `0x140017f20`
- `0x1400550cc`
- `0x140059e80`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400550f8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400550f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140055215`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400796f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140055215`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400796f5`

## string_xrefs

- `0x1400551b6`: `ClfsRemoveContainersInternal`
- `0x140055265`: `ClfsRemoveContainersInternal`

## pseudocode

```c
__int64 __fastcall ClfsRemoveContainersInternal(__int64 a1)
{
  __int64 v2; // rdi
  CClfsLogCcb *v3; // rsi
  int v4; // ebx
  __int64 v6; // [rsp+30h] [rbp-28h]

  if ( a1 )
  {
    KeEnterCriticalRegion();
    v2 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 120LL);
    v3 = *(CClfsLogCcb **)(a1 + 32);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 64LL))(v2);
    CClfsLogCcb::AddRef(v3);
    v4 = 0;
    if ( !*(_BYTE *)(*((_QWORD *)v3 + 9) + 75LL) )
      v4 = -1073741790;
    HIDWORD(v6) = v4;
    LODWORD(v6) = v4;
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          224,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsRemoveContainersInternal",
          95,
          v4,
          v6);
      }
    }
    else
    {
      v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 232LL))(v2);
      LODWORD(v6) = v4;
      if ( v4 < 0
        && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          225,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsRemoveContainersInternal",
          115,
          v4,
          v6);
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 72LL))(v2);
    CClfsLogCcb::Release((volatile signed __int32 *)v3);
    KeLeaveCriticalRegion();
    return (unsigned int)v4;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        223,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsRemoveContainersInternal",
        57,
        -1073741811);
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1400550cc  mov     rax, rsp
0x1400550cf  mov     [rax+10h], rbx
0x1400550d3  mov     [rax+18h], rsi
0x1400550d7  push    rdi
0x1400550d8  sub     rsp, 50h
0x1400550dc  mov     rbx, rcx
0x1400550df  mov     qword ptr [rax-18h], 0
0x1400550e7  mov     qword ptr [rax-20h], 0
0x1400550ef  test    rcx, rcx
0x1400550f2  jz      loc_140055234
0x1400550f8  call    cs:__imp_KeEnterCriticalRegion
0x1400550ff  nop     dword ptr [rax+rax+00h]
0x140055104  mov     rax, [rbx+18h]
0x140055108  mov     rdi, [rax+78h]
0x14005510c  mov     [rsp+58h+arg_0], rdi
0x140055111  mov     [rsp+58h+var_18], rdi
0x140055116  mov     rsi, [rbx+20h]
0x14005511a  mov     [rsp+58h+var_20], rsi
0x14005511f  mov     rax, [rdi]
0x140055122  mov     rax, [rax+40h]
0x140055126  mov     rcx, rdi
0x140055129  call    _guard_dispatch_icall
0x14005512e  mov     rcx, rsi; this
0x140055131  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x140055136  mov     [rsp+58h+var_24], 0
0x14005513e  mov     rax, [rsi+48h]
0x140055142  xor     ebx, ebx
0x140055144  mov     ecx, 0C0000022h
0x140055149  cmp     [rax+4Bh], bl
0x14005514c  cmovz   ebx, ecx
0x14005514f  mov     [rsp+58h+var_24], ebx
0x140055153  mov     [rsp+58h+var_28], ebx
0x140055157  test    ebx, ebx
0x140055159  js      short loc_1400551CF
0x14005515b  mov     rax, [rdi]
0x14005515e  mov     rax, [rax+0E8h]
0x140055165  mov     rcx, rdi
0x140055168  call    _guard_dispatch_icall
0x14005516d  mov     ebx, eax
0x14005516f  mov     [rsp+58h+var_28], eax
0x140055173  jmp     short loc_140055185
0x140055175  mov     ebx, eax
0x140055177  mov     [rsp+58h+var_28], eax
0x14005517b  mov     rsi, [rsp+58h+var_20]
0x140055180  mov     rdi, [rsp+58h+arg_0]
0x140055185  test    ebx, ebx
0x140055187  jns     short loc_1400551FE
0x140055189  lea     rax, WPP_GLOBAL_Control
0x140055190  mov     rcx, cs:WPP_GLOBAL_Control
0x140055197  cmp     rcx, rax
0x14005519a  jz      short loc_1400551FE
0x14005519c  mov     eax, [rcx+2Ch]
0x14005519f  bt      eax, 1Ah
0x1400551a3  jnb     short loc_1400551FE
0x1400551a5  mov     edx, 0E1h
0x1400551aa  mov     [rsp+58h+var_30], ebx
0x1400551ae  mov     [rsp+58h+var_38], 1B73h
0x1400551b6  lea     r9, aClfsremovecont; "ClfsRemoveContainersInternal"
0x1400551bd  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x1400551c4  mov     rcx, [rcx+18h]
0x1400551c8  call    WPP_SF_slD
0x1400551cd  jmp     short loc_1400551FE
0x1400551cf  lea     rax, WPP_GLOBAL_Control
0x1400551d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400551dd  cmp     rcx, rax
0x1400551e0  jz      short loc_1400551FE
0x1400551e2  mov     eax, [rcx+2Ch]
0x1400551e5  bt      eax, 1Ah
0x1400551e9  jnb     short loc_1400551FE
0x1400551eb  mov     edx, 0E0h
0x1400551f0  mov     [rsp+58h+var_30], ebx
0x1400551f4  mov     [rsp+58h+var_38], 1B5Fh
0x1400551fc  jmp     short loc_1400551B6
0x1400551fe  mov     rax, [rdi]
0x140055201  mov     rax, [rax+48h]
0x140055205  mov     rcx, rdi
0x140055208  call    _guard_dispatch_icall
0x14005520d  mov     rcx, rsi; Entry
0x140055210  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x140055215  call    cs:__imp_KeLeaveCriticalRegion
0x14005521c  nop     dword ptr [rax+rax+00h]
0x140055221  mov     eax, ebx
0x140055223  mov     rbx, [rsp+58h+arg_8]
0x140055228  mov     rsi, [rsp+58h+arg_10]
0x14005522d  add     rsp, 50h
0x140055231  pop     rdi
0x140055232  retn
0x140055234  lea     rax, WPP_GLOBAL_Control
0x14005523b  mov     rcx, cs:WPP_GLOBAL_Control
0x140055242  cmp     rcx, rax
0x140055245  jz      short loc_14005527C
0x140055247  test    dword ptr [rcx+2Ch], 4000000h
0x14005524e  jz      short loc_14005527C
0x140055250  mov     edx, 0DFh
0x140055255  mov     [rsp+58h+var_30], 0C000000Dh
0x14005525d  mov     [rsp+58h+var_38], 1B39h
0x140055265  lea     r9, aClfsremovecont; "ClfsRemoveContainersInternal"
0x14005526c  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140055273  mov     rcx, [rcx+18h]
0x140055277  call    WPP_SF_slD
0x14005527c  mov     eax, 0C000000Dh
0x140055281  jmp     short loc_140055223
0x1400796b9  push    rbp
0x1400796bb  sub     rsp, 30h
0x1400796bf  mov     rbp, rdx
0x1400796c2  mov     rcx, [rbp+40h]
0x1400796c6  test    rcx, rcx
0x1400796c9  jz      short loc_1400796DF
0x1400796cb  mov     rax, [rcx]
0x1400796ce  mov     rax, [rax+48h]
0x1400796d2  call    _guard_dispatch_icall
0x1400796d7  mov     qword ptr [rbp+40h], 0
0x1400796df  mov     rcx, [rbp+38h]; Entry
0x1400796e3  test    rcx, rcx
0x1400796e6  jz      short loc_1400796F5
0x1400796e8  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x1400796ed  mov     qword ptr [rbp+38h], 0
0x1400796f5  call    cs:__imp_KeLeaveCriticalRegion
0x1400796fc  nop     dword ptr [rax+rax+00h]
0x140079701  nop
0x140079702  add     rsp, 30h
0x140079706  pop     rbp
0x140079707  retn
```
