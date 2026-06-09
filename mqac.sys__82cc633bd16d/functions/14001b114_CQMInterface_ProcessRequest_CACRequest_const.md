# CQMInterface::ProcessRequest(CACRequest const &)

- ea: `0x14001b114`
- end: `0x14001b268`
- name: `?ProcessRequest@CQMInterface@@QEAAJAEBVCACRequest@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CQMInterface *__hidden this, const struct CACRequest *)`
- caller_count: `17`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140004a38`
- `0x14000ebd4`
- `0x1400140f4`
- `0x14001569c`
- `0x140017884`
- `0x140017b04`
- `0x140017b90`
- `0x140017ca4`
- `0x140018dc8`
- `0x14001b870`
- `0x14001b900`
- `0x14001bc6c`
- `0x14001bcb0`
- `0x14001c000`
- `0x14001c1f0`
- `0x14001c2d0`
- `0x14001e0c0`

## callees

- `0x140001c04`
- `0x14001aaf8`
- `0x14001b114`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001b143`
- `ntoskrnl!ExAllocatePool2` at `0x14001b143`

## pseudocode

```c
__int64 __fastcall CQMInterface::ProcessRequest(CQMInterface *this, const struct CACRequest *a2)
{
  __int64 Pool2; // rax
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  CQMInterface **v19; // rdx

  if ( !*((_QWORD *)this + 1) )
    return 3222142987LL;
  Pool2 = ExAllocatePool2(256, 232, 1297174861);
  if ( Pool2 )
  {
    v6 = *((_OWORD *)a2 + 1);
    *(_OWORD *)Pool2 = *(_OWORD *)a2;
    v7 = *((_OWORD *)a2 + 2);
    *(_OWORD *)(Pool2 + 16) = v6;
    v8 = *((_OWORD *)a2 + 3);
    *(_OWORD *)(Pool2 + 32) = v7;
    v9 = *((_OWORD *)a2 + 4);
    *(_OWORD *)(Pool2 + 48) = v8;
    v10 = *((_OWORD *)a2 + 5);
    *(_OWORD *)(Pool2 + 64) = v9;
    v11 = *((_OWORD *)a2 + 6);
    *(_OWORD *)(Pool2 + 80) = v10;
    v12 = *((_OWORD *)a2 + 7);
    *(_OWORD *)(Pool2 + 96) = v11;
    v13 = *((_OWORD *)a2 + 8);
    *(_OWORD *)(Pool2 + 112) = v12;
    v14 = *((_OWORD *)a2 + 9);
    *(_OWORD *)(Pool2 + 128) = v13;
    v15 = *((_OWORD *)a2 + 10);
    *(_OWORD *)(Pool2 + 144) = v14;
    v16 = *((_OWORD *)a2 + 11);
    *(_OWORD *)(Pool2 + 160) = v15;
    v17 = *((_OWORD *)a2 + 12);
    *(_OWORD *)(Pool2 + 176) = v16;
    v18 = *((_OWORD *)a2 + 13);
    *(_OWORD *)(Pool2 + 192) = v17;
    *(_OWORD *)(Pool2 + 208) = v18;
    *(_QWORD *)(Pool2 + 224) = *((_QWORD *)a2 + 28);
    v19 = (CQMInterface **)*((_QWORD *)this + 8);
    if ( *v19 != (CQMInterface *)((char *)this + 56) )
      __fastfail(3u);
    *(_QWORD *)Pool2 = (char *)this + 56;
    *(_QWORD *)(Pool2 + 8) = v19;
    *v19 = (CQMInterface *)Pool2;
    *((_QWORD *)this + 8) = Pool2;
    CQMInterface::Dispatch(this);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        0x14u,
        (__int64)WPP_bbff1b0e8ef6334436de7c5c17c85fe3_Traceguids);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14001b114  mov     [rsp+arg_0], rbx
0x14001b119  push    rdi
0x14001b11a  sub     rsp, 20h
0x14001b11e  cmp     qword ptr [rcx+8], 0
0x14001b123  mov     rbx, rdx
0x14001b126  mov     rdi, rcx
0x14001b129  jnz     short loc_14001B135
0x14001b12b  mov     eax, 0C00E000Bh
0x14001b130  jmp     loc_14001B25C
0x14001b135  mov     edx, 0E8h
0x14001b13a  mov     r8d, 4D51514Dh
0x14001b140  lea     ecx, [rdx+18h]
0x14001b143  call    cs:__imp_ExAllocatePool2
0x14001b14a  nop     dword ptr [rax+rax+00h]
0x14001b14f  mov     rcx, rax
0x14001b152  test    rax, rax
0x14001b155  jnz     short loc_14001B190
0x14001b157  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b15e  lea     rax, WPP_GLOBAL_Control
0x14001b165  cmp     rcx, rax
0x14001b168  jz      short loc_14001B186
0x14001b16a  mov     eax, [rcx+6Ch]
0x14001b16d  test    al, 1
0x14001b16f  jz      short loc_14001B186
0x14001b171  mov     rcx, [rcx+58h]
0x14001b175  lea     r8, WPP_bbff1b0e8ef6334436de7c5c17c85fe3_Traceguids
0x14001b17c  mov     edx, 14h
0x14001b181  call    WPP_SF_
0x14001b186  mov     eax, 0C000009Ah
0x14001b18b  jmp     loc_14001B25C
0x14001b190  movups  xmm0, xmmword ptr [rbx]
0x14001b193  movups  xmm1, xmmword ptr [rbx+10h]
0x14001b197  movups  xmmword ptr [rax], xmm0
0x14001b19a  movups  xmm0, xmmword ptr [rbx+20h]
0x14001b19e  movups  xmmword ptr [rax+10h], xmm1
0x14001b1a2  movups  xmm1, xmmword ptr [rbx+30h]
0x14001b1a6  movups  xmmword ptr [rax+20h], xmm0
0x14001b1aa  movups  xmm0, xmmword ptr [rbx+40h]
0x14001b1ae  movups  xmmword ptr [rax+30h], xmm1
0x14001b1b2  movups  xmm1, xmmword ptr [rbx+50h]
0x14001b1b6  movups  xmmword ptr [rax+40h], xmm0
0x14001b1ba  movups  xmm0, xmmword ptr [rbx+60h]
0x14001b1be  movups  xmmword ptr [rax+50h], xmm1
0x14001b1c2  movups  xmm1, xmmword ptr [rbx+70h]
0x14001b1c6  movups  xmmword ptr [rax+60h], xmm0
0x14001b1ca  movups  xmm0, xmmword ptr [rbx+80h]
0x14001b1d1  movups  xmmword ptr [rax+70h], xmm1
0x14001b1d5  movups  xmm1, xmmword ptr [rbx+90h]
0x14001b1dc  movups  xmmword ptr [rax+80h], xmm0
0x14001b1e3  movups  xmm0, xmmword ptr [rbx+0A0h]
0x14001b1ea  movups  xmmword ptr [rax+90h], xmm1
0x14001b1f1  movups  xmm1, xmmword ptr [rbx+0B0h]
0x14001b1f8  movups  xmmword ptr [rax+0A0h], xmm0
0x14001b1ff  movups  xmm0, xmmword ptr [rbx+0C0h]
0x14001b206  movups  xmmword ptr [rax+0B0h], xmm1
0x14001b20d  movups  xmm1, xmmword ptr [rbx+0D0h]
0x14001b214  movups  xmmword ptr [rax+0C0h], xmm0
0x14001b21b  movups  xmmword ptr [rax+0D0h], xmm1
0x14001b222  mov     rax, [rbx+0E0h]
0x14001b229  mov     [rcx+0E0h], rax
0x14001b230  lea     rax, [rdi+38h]
0x14001b234  mov     rdx, [rax+8]
0x14001b238  cmp     [rdx], rax
0x14001b23b  jz      short loc_14001B244
0x14001b23d  mov     ecx, 3
0x14001b242  int     29h; Win8: RtlFailFast(ecx)
0x14001b244  mov     [rcx], rax
0x14001b247  mov     [rcx+8], rdx
0x14001b24b  mov     [rdx], rcx
0x14001b24e  mov     [rax+8], rcx
0x14001b252  mov     rcx, rdi; this
0x14001b255  call    ?Dispatch@CQMInterface@@AEAAXXZ; CQMInterface::Dispatch(void)
0x14001b25a  xor     eax, eax
0x14001b25c  mov     rbx, [rsp+28h+arg_0]
0x14001b261  add     rsp, 20h
0x14001b265  pop     rdi
0x14001b266  retn
```
