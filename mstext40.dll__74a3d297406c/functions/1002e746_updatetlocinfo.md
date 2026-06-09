# ___updatetlocinfo

- ea: `0x1002e746`
- end: `0x1002e7c6`
- name: `___updatetlocinfo`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1002b67a`

## callees

- `0x1002e746`
- `0x1002e7c6`
- `0x1002f09b`
- `0x10033b92`
- `0x10034c80`
- `0x10034cc5`
- `0x10034e74`
- `0x10034fde`

## pseudocode

```c
int __updatetlocinfo()
{
  int v0; // eax
  int v1; // esi
  int v2; // esi

  v0 = _getptd();
  v1 = v0;
  if ( (__globallocalestatus & *(_DWORD *)(v0 + 112)) != 0 && *(_DWORD *)(v0 + 108) )
  {
    v2 = *(_DWORD *)(_getptd() + 108);
  }
  else
  {
    _lock(12);
    v2 = _updatetlocinfoEx_nolock(v1 + 108, (int *)__ptlocinfo);
    _unlock(12);
  }
  if ( !v2 )
    _amsg_exit(32);
  return v2;
}

```

## disassembly

```asm
0x1002e746  push    0Ch
0x1002e748  push    offset stru_1003CF50
0x1002e74d  call    __SEH_prolog4
0x1002e752  and     [ebp+var_1C], 0
0x1002e756  call    __getptd
0x1002e75b  mov     esi, eax
0x1002e75d  mov     ecx, ___globallocalestatus
0x1002e763  test    [esi+70h], ecx
0x1002e766  jz      short loc_1002E78A
0x1002e768  cmp     dword ptr [esi+6Ch], 0
0x1002e76c  jz      short loc_1002E78A
0x1002e76e  call    __getptd
0x1002e773  mov     esi, [eax+6Ch]
0x1002e776  test    esi, esi
0x1002e778  jnz     short loc_1002E782
0x1002e77a  push    20h ; ' '
0x1002e77c  call    __amsg_exit
0x1002e781  pop     ecx
0x1002e782  mov     eax, esi
0x1002e784  call    __SEH_epilog4
0x1002e789  retn
0x1002e78a  push    0Ch
0x1002e78c  call    __lock
0x1002e791  pop     ecx
0x1002e792  and     [ebp+ms_exc.registration.TryLevel], 0
0x1002e796  push    ___ptlocinfo
0x1002e79c  lea     eax, [esi+6Ch]
0x1002e79f  push    eax
0x1002e7a0  call    __updatetlocinfoEx_nolock
0x1002e7a5  pop     ecx
0x1002e7a6  pop     ecx
0x1002e7a7  mov     esi, eax
0x1002e7a9  mov     [ebp+var_1C], esi
0x1002e7ac  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1002e7b3  call    loc_1002E7BD
0x1002e7b8  jmp     short loc_1002E776
0x1002e7ba  mov     esi, [ebp+var_1C]
0x1002e7bd  push    0Ch
0x1002e7bf  call    __unlock
0x1002e7c4  pop     ecx
0x1002e7c5  retn
```
