# ___updatetmbcinfo

- ea: `0x1002eac8`
- end: `0x1002eb6e`
- name: `___updatetmbcinfo`
- size: `166`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1002b67a`
- `0x1002eb6e`

## callees

- `0x1002df32`
- `0x1002eac8`
- `0x1002f09b`
- `0x10033b92`
- `0x10034c80`
- `0x10034cc5`
- `0x10034e74`
- `0x10034fde`

## pseudocode

```c
int *__updatetmbcinfo()
{
  _DWORD *v0; // eax
  _DWORD *v1; // edi
  int *v2; // esi

  v0 = (_DWORD *)_getptd();
  v1 = v0;
  if ( (__globallocalestatus & v0[28]) != 0 && v0[27] )
  {
    v2 = (int *)v0[26];
  }
  else
  {
    _lock(13);
    v2 = (int *)v1[26];
    if ( v2 != __ptmbcinfo )
    {
      if ( v2 && !_InterlockedExchangeAdd(v2, 0xFFFFFFFF) && v2 != __initialmbcinfo )
        free(v2);
      v1[26] = __ptmbcinfo;
      v2 = (int *)__ptmbcinfo;
      _InterlockedExchangeAdd((volatile signed __int32 *)__ptmbcinfo, 1u);
    }
    _unlock(13);
  }
  if ( !v2 )
    _amsg_exit(32);
  return v2;
}

```

## disassembly

```asm
0x1002eac8  push    0Ch
0x1002eaca  push    offset stru_1003CF70
0x1002eacf  call    __SEH_prolog4
0x1002ead4  xor     esi, esi
0x1002ead6  mov     [ebp+var_1C], esi
0x1002ead9  call    __getptd
0x1002eade  mov     edi, eax
0x1002eae0  mov     ecx, ___globallocalestatus
0x1002eae6  test    [edi+70h], ecx
0x1002eae9  jz      short loc_1002EB07
0x1002eaeb  cmp     [edi+6Ch], esi
0x1002eaee  jz      short loc_1002EB07
0x1002eaf0  mov     esi, [edi+68h]
0x1002eaf3  test    esi, esi
0x1002eaf5  jnz     short loc_1002EAFF
0x1002eaf7  push    20h ; ' '
0x1002eaf9  call    __amsg_exit
0x1002eafe  pop     ecx
0x1002eaff  mov     eax, esi
0x1002eb01  call    __SEH_epilog4
0x1002eb06  retn
0x1002eb07  push    0Dh
0x1002eb09  call    __lock
0x1002eb0e  pop     ecx
0x1002eb0f  mov     [ebp+ms_exc.registration.TryLevel], esi
0x1002eb12  mov     esi, [edi+68h]
0x1002eb15  mov     [ebp+var_1C], esi
0x1002eb18  cmp     esi, ___ptmbcinfo
0x1002eb1e  jz      short loc_1002EB54
0x1002eb20  test    esi, esi
0x1002eb22  jz      short loc_1002EB3C
0x1002eb24  or      eax, 0FFFFFFFFh
0x1002eb27  lock xadd [esi], eax
0x1002eb2b  jnz     short loc_1002EB3C
0x1002eb2d  cmp     esi, offset ___initialmbcinfo
0x1002eb33  jz      short loc_1002EB3C
0x1002eb35  push    esi; Block
0x1002eb36  call    _free
0x1002eb3b  pop     ecx
0x1002eb3c  mov     eax, ___ptmbcinfo
0x1002eb41  mov     [edi+68h], eax
0x1002eb44  mov     esi, ___ptmbcinfo
0x1002eb4a  mov     [ebp+var_1C], esi
0x1002eb4d  xor     eax, eax
0x1002eb4f  inc     eax
0x1002eb50  lock xadd [esi], eax
0x1002eb54  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1002eb5b  call    loc_1002EB65
0x1002eb60  jmp     short loc_1002EAF3
0x1002eb62  mov     esi, [ebp+var_1C]
0x1002eb65  push    0Dh
0x1002eb67  call    __unlock
0x1002eb6c  pop     ecx
0x1002eb6d  retn
```
