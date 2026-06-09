# scl_AdjustOldSideBearingPoints(fnt_ElementType *,fnt_GlobalGraphicStateType const *)

- ea: `0x140043510`
- end: `0x140043575`
- name: `?scl_AdjustOldSideBearingPoints@@YAXPEAUfnt_ElementType@@PEBUfnt_GlobalGraphicStateType@@@Z`
- size: `101`
- prototype: `void __fastcall(struct fnt_ElementType *, const struct fnt_GlobalGraphicStateType *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140042d40`

## callees

- `0x140043510`

## pseudocode

```c
void __fastcall scl_AdjustOldSideBearingPoints(struct fnt_ElementType *a1, const struct fnt_GlobalGraphicStateType *a2)
{
  __int64 v3; // r11
  __int64 v4; // rcx
  int v5; // r9d
  unsigned int v6; // r8d
  __int64 v7; // rcx

  v3 = *((_QWORD *)a1 + 2);
  v4 = (unsigned __int16)(*(_WORD *)(*((_QWORD *)a1 + 8) + 2LL * *((__int16 *)a1 + 40) - 2) + 1);
  v5 = *(_DWORD *)(v3 + 4 * v4);
  if ( (*((_BYTE *)a2 + 448) & 5) == 1 )
    v6 = (v5 + 2) & 0xFFFFFFFC;
  else
    v6 = (v5 + 32) & 0xFFFFFFC0;
  *(_DWORD *)(v3 + 4 * v4) = v6;
  v7 = (unsigned __int16)(*(_WORD *)(*((_QWORD *)a1 + 8) + 2LL * *((__int16 *)a1 + 40) - 2) + 2);
  *(_DWORD *)(*((_QWORD *)a1 + 2) + 4 * v7) += v6 - v5;
}

```

## disassembly

```asm
0x140043510  mov     rax, [rcx+40h]
0x140043514  mov     r10, rcx
0x140043517  movsx   r8, word ptr [rcx+50h]
0x14004351c  mov     r11, [r10+10h]
0x140043520  movzx   r9d, word ptr [rax+r8*2-2]
0x140043526  mov     al, [rdx+1C0h]
0x14004352c  inc     r9w
0x140043530  movzx   ecx, r9w
0x140043534  and     al, 5
0x140043536  mov     r9d, [r11+rcx*4]
0x14004353a  cmp     al, 1
0x14004353c  jnz     short loc_14004356B
0x14004353e  lea     r8d, [r9+2]
0x140043542  and     r8d, 0FFFFFFFCh
0x140043546  mov     [r11+rcx*4], r8d
0x14004354a  sub     r8d, r9d
0x14004354d  movsx   rcx, word ptr [r10+50h]
0x140043552  mov     rax, [r10+40h]
0x140043556  movzx   edx, word ptr [rax+rcx*2-2]
0x14004355b  mov     rax, [r10+10h]
0x14004355f  add     dx, 2
0x140043563  movzx   ecx, dx
0x140043566  add     [rax+rcx*4], r8d
0x14004356a  retn
0x14004356b  lea     r8d, [r9+20h]
0x14004356f  and     r8d, 0FFFFFFC0h
0x140043573  jmp     short loc_140043546
```
