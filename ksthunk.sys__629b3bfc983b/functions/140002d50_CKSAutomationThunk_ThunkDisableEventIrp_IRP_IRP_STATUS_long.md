# CKSAutomationThunk::ThunkDisableEventIrp(_IRP *,_IRP_STATUS,long *)

- ea: `0x140002d50`
- end: `0x140002dc1`
- name: `?ThunkDisableEventIrp@CKSAutomationThunk@@IEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002160`
- `0x140002380`

## callees

- `0x140002d50`

## pseudocode

```c
__int64 __fastcall CKSAutomationThunk::ThunkDisableEventIrp(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 v4; // rcx
  int v5; // r8d
  __int64 result; // rax
  __int64 v7; // rcx
  unsigned int v8; // eax

  v4 = *(_QWORD *)(a2 + 184);
  v5 = *(_DWORD *)(v4 + 16);
  if ( (unsigned int)(v5 - 1) <= 0xE )
  {
    *a4 = -1073741306;
    return 0;
  }
  result = 1;
  if ( v5 )
  {
    *(_OWORD *)(v4 - 72) = *(_OWORD *)v4;
    *(_OWORD *)(v4 - 56) = *(_OWORD *)(v4 + 16);
    *(_OWORD *)(v4 - 40) = *(_OWORD *)(v4 + 32);
    *(_QWORD *)(v4 - 24) = *(_QWORD *)(v4 + 48);
    *(_BYTE *)(v4 - 69) = 0;
    v7 = *(_QWORD *)(a2 + 184);
    v8 = *(_DWORD *)(v7 - 56);
    if ( v8 + 16 < v8 )
    {
      *a4 = -1073741811;
      return 0;
    }
    *(_DWORD *)(v7 - 56) = v8 + 16;
    return 5;
  }
  return result;
}

```

## disassembly

```asm
0x140002d50  mov     rcx, [rdx+0B8h]
0x140002d57  mov     r8d, [rcx+10h]
0x140002d5b  lea     eax, [r8-1]
0x140002d5f  cmp     eax, 0Eh
0x140002d62  ja      short loc_140002D6F
0x140002d64  mov     dword ptr [r9], 0C0000206h
0x140002d6b  xor     eax, eax
0x140002d6d  retn
0x140002d6f  mov     eax, 1
0x140002d74  test    r8d, r8d
0x140002d77  jz      short locret_140002DC0
0x140002d79  movups  xmm0, xmmword ptr [rcx]
0x140002d7c  movups  xmmword ptr [rcx-48h], xmm0
0x140002d80  movups  xmm1, xmmword ptr [rcx+10h]
0x140002d84  movups  xmmword ptr [rcx-38h], xmm1
0x140002d88  movups  xmm0, xmmword ptr [rcx+20h]
0x140002d8c  movups  xmmword ptr [rcx-28h], xmm0
0x140002d90  movsd   xmm1, qword ptr [rcx+30h]
0x140002d95  movsd   qword ptr [rcx-18h], xmm1
0x140002d9a  mov     byte ptr [rcx-45h], 0
0x140002d9e  mov     rcx, [rdx+0B8h]
0x140002da5  mov     eax, [rcx-38h]
0x140002da8  lea     edx, [rax+10h]
0x140002dab  cmp     edx, eax
0x140002dad  jnb     short loc_140002DB8
0x140002daf  mov     dword ptr [r9], 0C000000Dh
0x140002db6  jmp     short loc_140002D6B
0x140002db8  mov     [rcx-38h], edx
0x140002dbb  mov     eax, 5
0x140002dc0  retn
```
