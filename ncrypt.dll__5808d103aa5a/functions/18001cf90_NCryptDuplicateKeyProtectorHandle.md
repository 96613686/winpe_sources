# NCryptDuplicateKeyProtectorHandle

- ea: `0x18001cf90`
- end: `0x18001d032`
- name: `NCryptDuplicateKeyProtectorHandle`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800090e0`

## callees

- `0x18000e120`
- `0x1800109d0`
- `0x18001cf90`

## string_xrefs

- `0x18001d012`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\router.c`

## pseudocode

```c
__int64 __fastcall NCryptDuplicateKeyProtectorHandle(__int64 a1, _QWORD *a2, __int64 a3)
{
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rcx
  signed __int32 v8; // eax

  if ( !a1 || *(_DWORD *)a1 != 72 )
  {
    v5 = -2146893786;
    v6 = 246;
    v7 = 2148073510LL;
    goto LABEL_10;
  }
  if ( !a2 )
  {
    v5 = -2146893785;
    v6 = 253;
    v7 = 2148073511LL;
LABEL_10:
    DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\router.c", v6);
    return v5;
  }
  v8 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, a3, a1, v8);
  *a2 = a1;
  return 0;
}

```

## disassembly

```asm
0x18001cf90  mov     [rsp+arg_0], rbx
0x18001cf95  push    rdi
0x18001cf96  sub     rsp, 30h
0x18001cf9a  mov     rdi, rdx
0x18001cf9d  mov     rbx, rcx
0x18001cfa0  test    rcx, rcx
0x18001cfa3  jz      short loc_18001D002
0x18001cfa5  cmp     dword ptr [rcx], 48h ; 'H'
0x18001cfa8  jnz     short loc_18001D002
0x18001cfaa  test    rdx, rdx
0x18001cfad  jnz     short loc_18001CFC1
0x18001cfaf  mov     ebx, 80090027h
0x18001cfb4  mov     r9d, 0FDh
0x18001cfba  mov     ecx, 80090027h
0x18001cfbf  jmp     short loc_18001D012
0x18001cfc1  mov     eax, 1
0x18001cfc6  lock xadd [rcx+4], eax
0x18001cfcb  inc     eax
0x18001cfcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfd4  lea     rdx, WPP_GLOBAL_Control
0x18001cfdb  cmp     rcx, rdx
0x18001cfde  jz      short loc_18001CFFB
0x18001cfe0  test    byte ptr [rcx+1Ch], 20h
0x18001cfe4  jz      short loc_18001CFFB
0x18001cfe6  mov     rcx, [rcx+10h]
0x18001cfea  mov     edx, 0Bh
0x18001cfef  mov     r9, rbx
0x18001cff2  mov     [rsp+38h+var_18], eax
0x18001cff6  call    WPP_SF_qD
0x18001cffb  mov     [rdi], rbx
0x18001cffe  xor     ebx, ebx
0x18001d000  jmp     short loc_18001D025
0x18001d002  mov     ebx, 80090026h
0x18001d007  mov     r9d, 0F6h
0x18001d00d  mov     ecx, 80090026h
0x18001d012  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001d019  lea     rdx, aStatus; "Status"
0x18001d020  call    DebugTraceError
0x18001d025  mov     eax, ebx
0x18001d027  mov     rbx, [rsp+38h+arg_0]
0x18001d02c  add     rsp, 30h
0x18001d030  pop     rdi
0x18001d031  retn
```
