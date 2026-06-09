# MdaCheckDirectoryAccess

- ea: `0x140014300`
- end: `0x14001455c`
- name: `MdaCheckDirectoryAccess`
- size: `604`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140005de0`

## callees

- `0x140008140`
- `0x140014300`
- `0x1400159cc`
- `0x1400159fc`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14001438b`
- `ntoskrnl!KeReleaseMutex` at `0x1400143df`
- `ntoskrnl!KeReleaseMutex` at `0x140014515`
- `ntoskrnl!KeReleaseMutex` at `0x14001438b`
- `ntoskrnl!KeReleaseMutex` at `0x1400143df`
- `ntoskrnl!KeReleaseMutex` at `0x140014515`

## pseudocode

```c
__int64 __fastcall MdaCheckDirectoryAccess(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rdi
  __int64 v5; // r9
  int v7; // eax
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  int v10; // ecx
  int v11; // edx
  int v12; // eax
  unsigned int v13; // r8d
  __int64 i; // rcx
  int v15; // r9d

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
  v4 = *(_DWORD **)(a1 + 40);
  HacAcquireLock(a2);
  v5 = *(unsigned int *)(a2 + 128);
  if ( (_DWORD)v5 != 2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_cca3db0522623f5e31396e1525c29988_Traceguids, v5);
    KeReleaseMutex(*(PRKMUTEX *)(a2 + 40), 0);
    return 0;
  }
  v7 = v4[9];
  if ( !v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
      goto LABEL_14;
    v9 = 15;
LABEL_13:
    WPP_SF_(v8->AttachedDevice, v9, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
LABEL_14:
    KeReleaseMutex(*(PRKMUTEX *)(a2 + 40), 0);
    return 1;
  }
  v10 = *(_DWORD *)(a2 + 140);
  if ( v7 == v10 || (_WORD)v7 == (_WORD)v10 )
  {
    if ( (*(_DWORD *)(a2 + 132) & 0x40) != 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
        goto LABEL_14;
      v9 = 16;
      goto LABEL_13;
    }
  }
  else
  {
    v11 = *(_DWORD *)(a2 + 144);
    v12 = v4[10];
    if ( v12 != v11 && (_WORD)v12 != (_WORD)v11 )
    {
      v13 = v4[11];
      for ( i = 0; (unsigned int)i < v13; i = (unsigned int)(i + 1) )
      {
        v15 = v4[i + 12];
        if ( v15 == v11 || (_WORD)v15 == (_WORD)v11 )
        {
          if ( (*(_DWORD *)(a2 + 132) & 8) == 0 )
            goto LABEL_41;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
          {
            v9 = 18;
            goto LABEL_13;
          }
          goto LABEL_14;
        }
      }
      if ( (_DWORD)i != v13 || (*(_DWORD *)(a2 + 132) & 1) == 0 )
        goto LABEL_41;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      {
        v9 = 19;
        goto LABEL_13;
      }
      goto LABEL_14;
    }
    if ( (*(_DWORD *)(a2 + 132) & 8) != 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
        goto LABEL_14;
      v9 = 17;
      goto LABEL_13;
    }
  }
LABEL_41:
  KeReleaseMutex(*(PRKMUTEX *)(a2 + 40), 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140014300  mov     [rsp+arg_0], rbx
0x140014305  mov     [rsp+arg_8], rsi
0x14001430a  push    rdi
0x14001430b  sub     rsp, 20h
0x14001430f  mov     rbx, rdx
0x140014312  mov     rdi, rcx
0x140014315  mov     rcx, cs:WPP_GLOBAL_Control
0x14001431c  lea     rsi, WPP_GLOBAL_Control
0x140014323  cmp     rcx, rsi
0x140014326  jz      short loc_140014344
0x140014328  mov     eax, [rcx+2Ch]
0x14001432b  test    al, 8
0x14001432d  jz      short loc_140014344
0x14001432f  mov     rcx, [rcx+18h]
0x140014333  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x14001433a  mov     edx, 0Dh
0x14001433f  call    WPP_SF_
0x140014344  mov     rdi, [rdi+28h]
0x140014348  mov     rcx, rbx
0x14001434b  call    HacAcquireLock
0x140014350  mov     r9d, [rbx+80h]
0x140014357  cmp     r9d, 2
0x14001435b  jz      short loc_1400143AA
0x14001435d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014364  cmp     rcx, rsi
0x140014367  jz      short loc_140014385
0x140014369  mov     eax, [rcx+2Ch]
0x14001436c  test    al, 1
0x14001436e  jz      short loc_140014385
0x140014370  mov     rcx, [rcx+18h]
0x140014374  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x14001437b  mov     edx, 0Eh
0x140014380  call    WPP_SF_d
0x140014385  mov     rcx, [rbx+28h]; Mutex
0x140014389  xor     edx, edx; Wait
0x14001438b  call    cs:__imp_KeReleaseMutex
0x140014392  nop     dword ptr [rax+rax+00h]
0x140014397  xor     eax, eax
0x140014399  mov     rbx, [rsp+28h+arg_0]
0x14001439e  mov     rsi, [rsp+28h+arg_8]
0x1400143a3  add     rsp, 20h
0x1400143a7  pop     rdi
0x1400143a8  retn
0x1400143aa  mov     eax, [rdi+24h]
0x1400143ad  test    eax, eax
0x1400143af  jnz     short loc_1400143F5
0x1400143b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400143b8  cmp     rcx, rsi
0x1400143bb  jz      short loc_1400143D9
0x1400143bd  mov     eax, [rcx+2Ch]
0x1400143c0  test    al, 8
0x1400143c2  jz      short loc_1400143D9
0x1400143c4  mov     edx, 0Fh
0x1400143c9  mov     rcx, [rcx+18h]
0x1400143cd  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x1400143d4  call    WPP_SF_
0x1400143d9  mov     rcx, [rbx+28h]; Mutex
0x1400143dd  xor     edx, edx; Wait
0x1400143df  call    cs:__imp_KeReleaseMutex
0x1400143e6  nop     dword ptr [rax+rax+00h]
0x1400143eb  mov     eax, 1
0x1400143f0  jmp     loc_14001454B
0x1400143f5  mov     ecx, [rbx+8Ch]
0x1400143fb  cmp     eax, ecx
0x1400143fd  jz      loc_1400144E0
0x140014403  cmp     ax, cx
0x140014406  jz      loc_1400144E0
0x14001440c  mov     edx, [rbx+90h]
0x140014412  mov     eax, [rdi+28h]
0x140014415  cmp     eax, edx
0x140014417  jz      loc_1400144B1
0x14001441d  cmp     ax, dx
0x140014420  jz      loc_1400144B1
0x140014426  mov     r8d, [rdi+2Ch]
0x14001442a  xor     ecx, ecx
0x14001442c  cmp     ecx, r8d
0x14001442f  jnb     short loc_140014478
0x140014431  mov     r9d, [rdi+rcx*4+30h]
0x140014436  cmp     r9d, edx
0x140014439  jz      short loc_140014445
0x14001443b  cmp     r9w, dx
0x14001443f  jz      short loc_140014445
0x140014441  inc     ecx
0x140014443  jmp     short loc_14001442C
0x140014445  mov     eax, [rbx+84h]
0x14001444b  test    al, 8
0x14001444d  jz      loc_14001450F
0x140014453  mov     rcx, cs:WPP_GLOBAL_Control
0x14001445a  cmp     rcx, rsi
0x14001445d  jz      loc_1400143D9
0x140014463  mov     eax, [rcx+2Ch]
0x140014466  test    al, 8
0x140014468  jz      loc_1400143D9
0x14001446e  mov     edx, 12h
0x140014473  jmp     loc_1400143C9
0x140014478  jnz     loc_14001450F
0x14001447e  mov     eax, [rbx+84h]
0x140014484  test    al, 1
0x140014486  jz      loc_14001450F
0x14001448c  mov     rcx, cs:WPP_GLOBAL_Control
0x140014493  cmp     rcx, rsi
0x140014496  jz      loc_1400143D9
0x14001449c  mov     eax, [rcx+2Ch]
0x14001449f  test    al, 8
0x1400144a1  jz      loc_1400143D9
0x1400144a7  mov     edx, 13h
0x1400144ac  jmp     loc_1400143C9
0x1400144b1  mov     eax, [rbx+84h]
0x1400144b7  test    al, 8
0x1400144b9  jz      short loc_14001450F
0x1400144bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400144c2  cmp     rcx, rsi
0x1400144c5  jz      loc_1400143D9
0x1400144cb  mov     eax, [rcx+2Ch]
0x1400144ce  test    al, 8
0x1400144d0  jz      loc_1400143D9
0x1400144d6  mov     edx, 11h
0x1400144db  jmp     loc_1400143C9
0x1400144e0  mov     eax, [rbx+84h]
0x1400144e6  test    al, 40h
0x1400144e8  jz      short loc_14001450F
0x1400144ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400144f1  cmp     rcx, rsi
0x1400144f4  jz      loc_1400143D9
0x1400144fa  mov     eax, [rcx+2Ch]
0x1400144fd  test    al, 8
0x1400144ff  jz      loc_1400143D9
0x140014505  mov     edx, 10h
0x14001450a  jmp     loc_1400143C9
0x14001450f  mov     rcx, [rbx+28h]; Mutex
0x140014513  xor     edx, edx; Wait
0x140014515  call    cs:__imp_KeReleaseMutex
0x14001451c  nop     dword ptr [rax+rax+00h]
0x140014521  mov     rcx, cs:WPP_GLOBAL_Control
0x140014528  cmp     rcx, rsi
0x14001452b  jz      short loc_140014549
0x14001452d  mov     eax, [rcx+2Ch]
0x140014530  test    al, 8
0x140014532  jz      short loc_140014549
0x140014534  mov     rcx, [rcx+18h]
0x140014538  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x14001453f  mov     edx, 14h
0x140014544  call    WPP_SF_
0x140014549  xor     eax, eax
0x14001454b  mov     rbx, [rsp+28h+arg_0]
0x140014550  mov     rsi, [rsp+28h+arg_8]
0x140014555  add     rsp, 20h
0x140014559  pop     rdi
0x14001455a  retn
```
