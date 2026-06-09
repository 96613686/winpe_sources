# Smb2RequestResiliency

- ea: `0x14002b968`
- end: `0x14002ba18`
- name: `Smb2RequestResiliency`
- size: `176`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001cc00`

## callees

- `0x140028500`
- `0x14002b968`

## import_xrefs

- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002b9ab`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002b9ab`

## pseudocode

```c
__int64 __fastcall Smb2RequestResiliency(__int64 a1)
{
  _DWORD *v2; // rdi
  __int64 v3; // rax
  __int64 v4; // rsi
  __int64 v5; // rbp

  if ( *(_DWORD *)(a1 + 568) < 8u )
    return 3221225485LL;
  v2 = *(_DWORD **)(a1 + 552);
  if ( *v2 > 0x36EE80u )
    return 3221225485LL;
  v3 = *(_QWORD *)(a1 + 72);
  v4 = *(_QWORD *)(v3 + 48);
  v5 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 40) + 40LL) + 424LL) + 88LL);
  if ( *(_BYTE *)(MRxSmbGetConfigurationBlock(a1) + 233) || (*(_BYTE *)(v5 + 736) & 4) == 0 )
    return 3221225659LL;
  if ( (*(_DWORD *)(v4 + 8) & 0x40) != 0 )
  {
    *(_QWORD *)(a1 + 184) = 0;
    return 0;
  }
  else
  {
    *(_QWORD *)(v4 + 256) = 10000LL * (unsigned int)*v2;
    return Smb2GenericFsControl(a1, *(_DWORD *)(a1 + 540), 0);
  }
}

```

## disassembly

```asm
0x14002b968  push    rbx
0x14002b96a  push    rbp
0x14002b96b  push    rsi
0x14002b96c  push    rdi
0x14002b96d  sub     rsp, 28h
0x14002b971  cmp     dword ptr [rcx+238h], 8
0x14002b978  mov     rbx, rcx
0x14002b97b  jb      loc_14002BA09
0x14002b981  mov     rdi, [rcx+228h]
0x14002b988  cmp     dword ptr [rdi], 36EE80h
0x14002b98e  ja      short loc_14002BA09
0x14002b990  mov     rax, [rcx+48h]
0x14002b994  mov     rsi, [rax+30h]
0x14002b998  mov     rax, [rax+28h]
0x14002b99c  mov     rdx, [rax+28h]
0x14002b9a0  mov     rax, [rdx+1A8h]
0x14002b9a7  mov     rbp, [rax+58h]
0x14002b9ab  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14002b9b2  nop     dword ptr [rax+rax+00h]
0x14002b9b7  cmp     byte ptr [rax+0E9h], 0
0x14002b9be  jnz     short loc_14002BA02
0x14002b9c0  test    byte ptr [rbp+2E0h], 4
0x14002b9c7  jz      short loc_14002BA02
0x14002b9c9  mov     eax, [rsi+8]
0x14002b9cc  test    al, 40h
0x14002b9ce  jz      short loc_14002B9DF
0x14002b9d0  mov     qword ptr [rbx+0B8h], 0
0x14002b9db  xor     eax, eax
0x14002b9dd  jmp     short loc_14002BA0E
0x14002b9df  mov     eax, [rdi]
0x14002b9e1  xor     r8d, r8d
0x14002b9e4  imul    rcx, rax, 2710h
0x14002b9eb  mov     [rsi+100h], rcx
0x14002b9f2  mov     rcx, rbx
0x14002b9f5  mov     edx, [rbx+21Ch]
0x14002b9fb  call    Smb2GenericFsControl
0x14002ba00  jmp     short loc_14002BA0E
0x14002ba02  mov     eax, 0C00000BBh
0x14002ba07  jmp     short loc_14002BA0E
0x14002ba09  mov     eax, 0C000000Dh
0x14002ba0e  add     rsp, 28h
0x14002ba12  pop     rdi
0x14002ba13  pop     rsi
0x14002ba14  pop     rbp
0x14002ba15  pop     rbx
0x14002ba16  retn
```
