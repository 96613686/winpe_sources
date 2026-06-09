# CKSAutomationThunk::ThunkDisableEventIrp(_IRP *,_IRP_STATUS,long *)

- ea: `0x1400036b0`
- end: `0x140003721`
- name: `?ThunkDisableEventIrp@CKSAutomationThunk@@IEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400021e0`
- `0x140002c80`

## callees

- `0x1400036b0`

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
0x1400036b0  mov     rcx, [rdx+0B8h]
0x1400036b7  mov     r8d, [rcx+10h]
0x1400036bb  lea     eax, [r8-1]
0x1400036bf  cmp     eax, 0Eh
0x1400036c2  ja      short loc_1400036CF
0x1400036c4  mov     dword ptr [r9], 0C0000206h
0x1400036cb  xor     eax, eax
0x1400036cd  retn
0x1400036cf  mov     eax, 1
0x1400036d4  test    r8d, r8d
0x1400036d7  jz      short locret_140003720
0x1400036d9  movups  xmm0, xmmword ptr [rcx]
0x1400036dc  movups  xmmword ptr [rcx-48h], xmm0
0x1400036e0  movups  xmm1, xmmword ptr [rcx+10h]
0x1400036e4  movups  xmmword ptr [rcx-38h], xmm1
0x1400036e8  movups  xmm0, xmmword ptr [rcx+20h]
0x1400036ec  movups  xmmword ptr [rcx-28h], xmm0
0x1400036f0  movsd   xmm1, qword ptr [rcx+30h]
0x1400036f5  movsd   qword ptr [rcx-18h], xmm1
0x1400036fa  mov     byte ptr [rcx-45h], 0
0x1400036fe  mov     rcx, [rdx+0B8h]
0x140003705  mov     eax, [rcx-38h]
0x140003708  lea     edx, [rax+10h]
0x14000370b  cmp     edx, eax
0x14000370d  jnb     short loc_140003718
0x14000370f  mov     dword ptr [r9], 0C000000Dh
0x140003716  jmp     short loc_1400036CB
0x140003718  mov     [rcx-38h], edx
0x14000371b  mov     eax, 5
0x140003720  retn
```
