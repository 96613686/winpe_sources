# PortMgrUpdatePortCharacterstics

- ea: `0x180013560`
- end: `0x1800137de`
- name: `PortMgrUpdatePortCharacterstics`
- size: `638`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18001a350`
- `0x18001fb58`
- `0x180022960`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x180013560`
- `0x1800137f0`
- `0x180019cd0`
- `0x1800214f0`
- `0x18002f705`

## pseudocode

```c
__int64 __fastcall PortMgrUpdatePortCharacterstics(_DWORD *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // r14d
  _QWORD *v9; // r10
  int v10; // ecx
  unsigned int v11; // edi
  __int64 result; // rax

  v4 = a1[5];
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a4 )
    goto LABEL_30;
  v10 = *(_DWORD *)(a4 + 8);
  if ( v10 == a1[50] )
  {
    memcpy_0(a1 + 48, (const void *)a4, 0x880u);
    if ( !*(_QWORD *)(a4 + 2144) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v4);
      a1[6] |= 0x80u;
    }
    if ( !*(_QWORD *)(a4 + 2112) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v4);
      a1[6] |= 0x200u;
    }
    if ( !*(_QWORD *)(a4 + 2120) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v4);
      a1[6] |= 0x100u;
      a1[6] |= 0x400u;
    }
    if ( !*(_QWORD *)(a4 + 2168) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v4);
      a1[6] |= 0x800u;
    }
    v9 = WPP_GLOBAL_Control;
LABEL_30:
    v11 = 0;
    if ( (*(_BYTE *)(a3 + 12) & 2) != 0 )
    {
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 4) != 0 )
        WPP_SF_d(v9[7], 18, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v4);
      a1[6] |= 0x400u;
      v9 = WPP_GLOBAL_Control;
    }
    if ( a1[594] != 1 )
      goto LABEL_41;
    result = UpdateSupplicantCharacterstics(a1 + 596, a2, a3);
    v11 = result;
    if ( (_DWORD)result )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return result;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_41;
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v4, result);
    }
    goto LABEL_40;
  }
  v11 = 87;
  if ( v9 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v9 + 68) & 1) == 0 )
      goto LABEL_41;
    WPP_SF_ddd(v9[7], 13, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v4, v10, a1[50]);
LABEL_40:
    v9 = WPP_GLOBAL_Control;
LABEL_41:
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
      WPP_SF_D(v9[7], 20, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x180013560  push    rbx
0x180013562  push    rbp
0x180013563  push    rsi
0x180013564  push    rdi
0x180013565  push    r14
0x180013567  push    r15
0x180013569  sub     rsp, 38h
0x18001356d  mov     r14d, [rcx+14h]
0x180013571  mov     rdi, r9
0x180013574  mov     rsi, r8
0x180013577  mov     ebp, edx
0x180013579  mov     rbx, rcx
0x18001357c  mov     r10, cs:WPP_GLOBAL_Control
0x180013583  lea     r15, WPP_GLOBAL_Control
0x18001358a  cmp     r10, r15
0x18001358d  jz      short loc_1800135B5
0x18001358f  test    dword ptr [r10+44h], 800h
0x180013597  jz      short loc_1800135B5
0x180013599  mov     rcx, [r10+38h]
0x18001359d  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x1800135a4  mov     edx, 0Ch
0x1800135a9  call    WPP_SF_
0x1800135ae  mov     r10, cs:WPP_GLOBAL_Control
0x1800135b5  test    rdi, rdi
0x1800135b8  jz      loc_180013718
0x1800135be  mov     eax, [rbx+0C8h]
0x1800135c4  mov     ecx, [rdi+8]
0x1800135c7  cmp     ecx, eax
0x1800135c9  jz      short loc_180013609
0x1800135cb  mov     edi, 57h ; 'W'
0x1800135d0  cmp     r10, r15
0x1800135d3  jz      loc_1800137CF
0x1800135d9  test    byte ptr [r10+44h], 1
0x1800135de  jz      loc_1800137A8
0x1800135e4  mov     [rsp+68h+var_40], eax
0x1800135e8  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x1800135ef  mov     [rsp+68h+var_48], ecx
0x1800135f3  mov     edx, 0Dh
0x1800135f8  mov     rcx, [r10+38h]
0x1800135fc  mov     r9d, r14d
0x1800135ff  call    WPP_SF_ddd
0x180013604  jmp     loc_1800137A1
0x180013609  lea     rcx, [rbx+0C0h]; void *
0x180013610  mov     rdx, rdi; Src
0x180013613  mov     r8d, 880h; Size
0x180013619  call    memcpy_0
0x18001361e  cmp     qword ptr [rdi+860h], 0
0x180013626  jnz     short loc_180013659
0x180013628  mov     rcx, cs:WPP_GLOBAL_Control
0x18001362f  cmp     rcx, r15
0x180013632  jz      short loc_180013652
0x180013634  test    byte ptr [rcx+44h], 4
0x180013638  jz      short loc_180013652
0x18001363a  mov     rcx, [rcx+38h]
0x18001363e  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180013645  mov     edx, 0Eh
0x18001364a  mov     r9d, r14d
0x18001364d  call    WPP_SF_d
0x180013652  or      dword ptr [rbx+18h], 80h
0x180013659  cmp     qword ptr [rdi+840h], 0
0x180013661  jnz     short loc_180013694
0x180013663  mov     rcx, cs:WPP_GLOBAL_Control
0x18001366a  cmp     rcx, r15
0x18001366d  jz      short loc_18001368D
0x18001366f  test    byte ptr [rcx+44h], 4
0x180013673  jz      short loc_18001368D
0x180013675  mov     rcx, [rcx+38h]
0x180013679  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180013680  mov     edx, 0Fh
0x180013685  mov     r9d, r14d
0x180013688  call    WPP_SF_d
0x18001368d  or      dword ptr [rbx+18h], 200h
0x180013694  cmp     qword ptr [rdi+848h], 0
0x18001369c  jnz     short loc_1800136D6
0x18001369e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136a5  cmp     rcx, r15
0x1800136a8  jz      short loc_1800136C8
0x1800136aa  test    byte ptr [rcx+44h], 4
0x1800136ae  jz      short loc_1800136C8
0x1800136b0  mov     rcx, [rcx+38h]
0x1800136b4  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x1800136bb  mov     edx, 10h
0x1800136c0  mov     r9d, r14d
0x1800136c3  call    WPP_SF_d
0x1800136c8  or      dword ptr [rbx+18h], 100h
0x1800136cf  or      dword ptr [rbx+18h], 400h
0x1800136d6  cmp     qword ptr [rdi+878h], 0
0x1800136de  jnz     short loc_180013711
0x1800136e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136e7  cmp     rcx, r15
0x1800136ea  jz      short loc_18001370A
0x1800136ec  test    byte ptr [rcx+44h], 4
0x1800136f0  jz      short loc_18001370A
0x1800136f2  mov     rcx, [rcx+38h]
0x1800136f6  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x1800136fd  mov     edx, 11h
0x180013702  mov     r9d, r14d
0x180013705  call    WPP_SF_d
0x18001370a  or      dword ptr [rbx+18h], 800h
0x180013711  mov     r10, cs:WPP_GLOBAL_Control
0x180013718  xor     edi, edi
0x18001371a  test    byte ptr [rsi+0Ch], 2
0x18001371e  jz      short loc_180013752
0x180013720  cmp     r10, r15
0x180013723  jz      short loc_180013744
0x180013725  test    byte ptr [r10+44h], 4
0x18001372a  jz      short loc_180013744
0x18001372c  mov     rcx, [r10+38h]
0x180013730  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180013737  mov     edx, 12h
0x18001373c  mov     r9d, r14d
0x18001373f  call    WPP_SF_d
0x180013744  or      dword ptr [rbx+18h], 400h
0x18001374b  mov     r10, cs:WPP_GLOBAL_Control
0x180013752  cmp     dword ptr [rbx+948h], 1
0x180013759  jnz     short loc_1800137A8
0x18001375b  lea     rcx, [rbx+950h]
0x180013762  mov     r8, rsi
0x180013765  mov     edx, ebp
0x180013767  call    UpdateSupplicantCharacterstics
0x18001376c  mov     edi, eax
0x18001376e  test    eax, eax
0x180013770  jz      short loc_1800137A1
0x180013772  mov     r10, cs:WPP_GLOBAL_Control
0x180013779  cmp     r10, r15
0x18001377c  jz      short loc_1800137D1
0x18001377e  test    byte ptr [r10+44h], 1
0x180013783  jz      short loc_1800137A8
0x180013785  mov     rcx, [r10+38h]
0x180013789  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180013790  mov     edx, 13h
0x180013795  mov     [rsp+68h+var_48], eax
0x180013799  mov     r9d, r14d
0x18001379c  call    WPP_SF_dd
0x1800137a1  mov     r10, cs:WPP_GLOBAL_Control
0x1800137a8  cmp     r10, r15
0x1800137ab  jz      short loc_1800137CF
0x1800137ad  test    dword ptr [r10+44h], 800h
0x1800137b5  jz      short loc_1800137CF
0x1800137b7  mov     rcx, [r10+38h]
0x1800137bb  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x1800137c2  mov     edx, 14h
0x1800137c7  mov     r9d, edi
0x1800137ca  call    WPP_SF_D
0x1800137cf  mov     eax, edi
0x1800137d1  add     rsp, 38h
0x1800137d5  pop     r15
0x1800137d7  pop     r14
0x1800137d9  pop     rdi
0x1800137da  pop     rsi
0x1800137db  pop     rbp
0x1800137dc  pop     rbx
0x1800137dd  retn
```
