# CdUpdateDirentFromRawDirent

- ea: `0x14001292c`
- end: `0x140012a0b`
- name: `CdUpdateDirentFromRawDirent`
- size: `223`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `11`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000b1a4`
- `0x14000b684`
- `0x14000dc38`
- `0x140011138`
- `0x1400120cc`
- `0x140012198`
- `0x14001233c`
- `0x140012508`
- `0x140012884`
- `0x1400135d0`
- `0x140018bec`

## callees

- `0x140001114`
- `0x14001292c`

## pseudocode

```c
__int64 __fastcall CdUpdateDirentFromRawDirent(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int8 *v4; // r10
  unsigned int v5; // r8d
  int v6; // edx
  unsigned __int8 v7; // dl
  int v8; // eax
  int v9; // eax
  int v10; // ecx
  __int64 result; // rax

  v4 = (unsigned __int8 *)(*(_QWORD *)a3 + *(unsigned int *)(a3 + 24));
  *(_DWORD *)a4 = *(_DWORD *)(a3 + 24) + *(_DWORD *)(a3 + 8);
  v5 = *v4;
  *(_DWORD *)(a4 + 4) = v5;
  v6 = *(_DWORD *)(v4 + 2);
  *(_DWORD *)(a4 + 8) = v6;
  *(_DWORD *)(a4 + 8) = v6 + v4[1];
  *(_DWORD *)(a4 + 12) = *(_DWORD *)(v4 + 10);
  *(_QWORD *)(a4 + 16) = v4 + 18;
  v7 = v4[((*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) & 1) == 0) + 24];
  *(_BYTE *)(a4 + 24) = v7;
  *(_QWORD *)(a4 + 28) = 0;
  v8 = v4[26];
  if ( (_BYTE)v8 )
  {
    *(_DWORD *)(a4 + 28) = v8;
    *(_DWORD *)(a4 + 32) = v4[27];
  }
  v9 = v4[32];
  if ( !(_BYTE)v9 )
    CdRaiseStatusEx(a1, 3221225730LL, 0, 786432, 512);
  v10 = v4[32];
  *(_DWORD *)(a4 + 44) = v9;
  *(_QWORD *)(a4 + 48) = v4 + 33;
  result = 0;
  *(_WORD *)(a4 + 40) = 0;
  *(_BYTE *)(a4 + 42) = 0;
  *(_DWORD *)(a4 + 120) = 0;
  *(_DWORD *)(a4 + 36) = 0;
  if ( (v7 & 2) == 0 )
  {
    result = (unsigned int)(v10 + 34);
    if ( v5 > (unsigned int)result )
    {
      result = (unsigned int)result & 0xFFFFFFFE;
      *(_DWORD *)(a4 + 36) = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001292c  mov     [rsp+arg_8], rdx
0x140012931  sub     rsp, 38h
0x140012935  mov     eax, [r8+8]
0x140012939  mov     r11, rcx
0x14001293c  add     eax, [r8+18h]
0x140012940  mov     r10d, [r8+18h]
0x140012944  add     r10, [r8]
0x140012947  mov     [r9], eax
0x14001294a  movzx   r8d, byte ptr [r10]
0x14001294e  mov     [r9+4], r8d
0x140012952  mov     edx, [r10+2]
0x140012956  mov     [r9+8], edx
0x14001295a  movzx   eax, byte ptr [r10+1]
0x14001295f  add     eax, edx
0x140012961  mov     [r9+8], eax
0x140012965  mov     eax, [r10+0Ah]
0x140012969  mov     [r9+0Ch], eax
0x14001296d  lea     rax, [r10+12h]
0x140012971  mov     [r9+10h], rax
0x140012975  mov     rax, [rcx+10h]
0x140012979  mov     ecx, [rax+30h]
0x14001297c  not     ecx
0x14001297e  and     ecx, 1
0x140012981  mov     dl, [rcx+r10+18h]
0x140012986  mov     [r9+18h], dl
0x14001298a  mov     qword ptr [r9+1Ch], 0
0x140012992  movzx   eax, byte ptr [r10+1Ah]
0x140012997  test    al, al
0x140012999  jz      short loc_1400129A8
0x14001299b  mov     [r9+1Ch], eax
0x14001299f  movzx   eax, byte ptr [r10+1Bh]
0x1400129a4  mov     [r9+20h], eax
0x1400129a8  movzx   eax, byte ptr [r10+20h]
0x1400129ad  test    al, al
0x1400129af  jz      short loc_1400129EC
0x1400129b1  mov     ecx, eax
0x1400129b3  mov     [r9+2Ch], eax
0x1400129b7  lea     rax, [r10+21h]
0x1400129bb  mov     [r9+30h], rax
0x1400129bf  xor     eax, eax
0x1400129c1  mov     [r9+28h], ax
0x1400129c6  mov     [r9+2Ah], al
0x1400129ca  mov     [r9+78h], eax
0x1400129ce  mov     [r9+24h], eax
0x1400129d2  test    dl, 2
0x1400129d5  jnz     short loc_1400129E6
0x1400129d7  lea     eax, [rcx+22h]
0x1400129da  cmp     r8d, eax
0x1400129dd  jbe     short loc_1400129E6
0x1400129df  and     eax, 0FFFFFFFEh
0x1400129e2  mov     [r9+24h], eax
0x1400129e6  add     rsp, 38h
0x1400129ea  retn
0x1400129ec  mov     r9d, 0C0000h
0x1400129f2  mov     [rsp+38h+var_18], 200h
0x1400129fa  xor     r8d, r8d
0x1400129fd  mov     edx, 0C0000102h
0x140012a02  mov     rcx, r11
0x140012a05  call    CdRaiseStatusEx
```
