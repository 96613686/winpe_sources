# CCommand::CheckForZombieCommandAndFix(void)

- ea: `0x100147f0`
- end: `0x1001488f`
- name: `?CheckForZombieCommandAndFix@CCommand@@QAGJXZ`
- size: `159`
- prototype: `int(CCommand *__hidden this)`
- caller_count: `11`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1000fc70`
- `0x1000fcf0`
- `0x100107b0`
- `0x100108b0`
- `0x100109e0`
- `0x10010b50`
- `0x10010f80`
- `0x10011130`
- `0x100132e0`
- `0x1002e200`
- `0x1002e3e0`

## callees

- `0x100147f0`
- `0x1001c6d0`
- `0x10049580`
- `0x100495b0`
- `0x1004cea1`

## pseudocode

```c
int __thiscall CCommand::CheckForZombieCommandAndFix(int ecx0)
{
  int v2; // ebx
  int v3; // esi
  CTransactionState *v4; // ecx
  int isZombie; // eax
  int v6; // eax
  CTransactionState *v7; // ecx
  int v8; // ecx
  volatile signed __int32 *v9; // eax

  v2 = 0;
  v3 = *(_DWORD *)(ecx0 + 56);
  if ( v3 )
  {
    if ( *(_DWORD *)(v3 + 16) == 1 && (v4 = *(CTransactionState **)(v3 + 8)) != 0 )
      isZombie = CTransactionState::isZombie(v4);
    else
      isZombie = *(_DWORD *)(v3 + 12);
    if ( isZombie == 1 )
    {
      if ( (*(_BYTE *)(ecx0 + 60) & 0x10) != 0 )
      {
        *(_DWORD *)(ecx0 + 96) = 1;
        v6 = (*(int (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)(ecx0 + 24) + 16))(
               *(_DWORD *)(**(_DWORD **)(ecx0 + 24) + 16),
               *(_DWORD *)(ecx0 + 24));
        v3 = *(_DWORD *)(ecx0 + 56);
        v2 = v6;
        *(_DWORD *)(ecx0 + 96) = 0;
      }
      if ( *(_DWORD *)(ecx0 + 72) == 1 )
        *(_DWORD *)(ecx0 + 100) = -1;
      if ( v3 )
      {
        _InterlockedDecrement((volatile signed __int32 *)v3);
        if ( !*(_DWORD *)v3 )
        {
          v7 = *(CTransactionState **)(v3 + 8);
          if ( v7 )
            CTransactionState::Release(v7);
          operator delete((void *)v3);
        }
      }
      v8 = *(_DWORD *)(ecx0 + 52);
      *(_DWORD *)(ecx0 + 56) = *(_DWORD *)(v8 + 88);
      v9 = *(volatile signed __int32 **)(v8 + 88);
      if ( v9 )
        _InterlockedIncrement(v9);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x100147f0  mov     edi, edi
0x100147f2  push    ebx
0x100147f3  push    esi
0x100147f4  push    edi
0x100147f5  mov     edi, ecx
0x100147f7  xor     ebx, ebx
0x100147f9  mov     esi, [edi+38h]
0x100147fc  test    esi, esi
0x100147fe  jz      loc_10014889
0x10014804  cmp     dword ptr [esi+10h], 1
0x10014808  jnz     short loc_10014818
0x1001480a  mov     ecx, [esi+8]; this
0x1001480d  test    ecx, ecx
0x1001480f  jz      short loc_10014818
0x10014811  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x10014816  jmp     short loc_1001481B
0x10014818  mov     eax, [esi+0Ch]
0x1001481b  cmp     eax, 1
0x1001481e  jnz     short loc_10014889
0x10014820  test    byte ptr [edi+3Ch], 10h
0x10014824  jz      short loc_10014848
0x10014826  mov     [edi+60h], eax
0x10014829  mov     eax, [edi+18h]
0x1001482c  push    eax
0x1001482d  mov     ecx, [eax]
0x1001482f  mov     esi, [ecx+10h]
0x10014832  mov     ecx, esi
0x10014834  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001483a  call    esi
0x1001483c  mov     esi, [edi+38h]
0x1001483f  mov     ebx, eax
0x10014841  mov     dword ptr [edi+60h], 0
0x10014848  cmp     dword ptr [edi+48h], 1
0x1001484c  jnz     short loc_10014855
0x1001484e  mov     dword ptr [edi+64h], 0FFFFFFFFh
0x10014855  test    esi, esi
0x10014857  jz      short loc_10014876
0x10014859  lock dec dword ptr [esi]
0x1001485c  cmp     dword ptr [esi], 0
0x1001485f  ja      short loc_10014876
0x10014861  mov     ecx, [esi+8]; this
0x10014864  test    ecx, ecx
0x10014866  jz      short loc_1001486D
0x10014868  call    ?Release@CTransactionState@@QAEKXZ; CTransactionState::Release(void)
0x1001486d  push    esi; Block
0x1001486e  call    ??3@YAXPAX@Z; operator delete(void *)
0x10014873  add     esp, 4
0x10014876  mov     ecx, [edi+34h]
0x10014879  mov     eax, [ecx+58h]
0x1001487c  mov     [edi+38h], eax
0x1001487f  mov     eax, [ecx+58h]
0x10014882  test    eax, eax
0x10014884  jz      short loc_10014889
0x10014886  lock inc dword ptr [eax]
0x10014889  pop     edi
0x1001488a  pop     esi
0x1001488b  mov     eax, ebx
0x1001488d  pop     ebx
0x1001488e  retn
```
