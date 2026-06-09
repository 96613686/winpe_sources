# SetCallResult

- ea: `0x1400031f0`
- end: `0x140003251`
- name: `SetCallResult`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400010b0`
- `0x140001ae0`

## callees

- `0x1400031f0`

## pseudocode

```c
void __fastcall SetCallResult(__int64 a1, char a2, _DWORD *a3, _QWORD *a4)
{
  __int64 v4; // rdx
  char v5; // al
  __int64 v6; // rcx
  int v7; // eax

  if ( (a2 & 0x10) != 0 && *(int *)(a1 + 24) >= 0 )
  {
    v4 = *(_QWORD *)(a1 + 16);
    v5 = *(_BYTE *)(v4 + 4);
    switch ( v5 )
    {
      case 3:
        *a3 = *(_DWORD *)(a1 + 32);
        v6 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 48LL);
        goto LABEL_14;
      case 5:
        goto LABEL_12;
      case 7:
LABEL_9:
        *a3 = *(_DWORD *)(v4 + 24);
        v6 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 56LL);
LABEL_14:
        *a4 = v6;
        return;
      case 10:
LABEL_12:
        v7 = *(_DWORD *)(v4 + 24);
        break;
      case 20:
        v7 = *(_DWORD *)(v4 + 32);
        break;
      case 25:
        goto LABEL_9;
      default:
        return;
    }
    *a3 = v7;
    v6 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 40LL);
    goto LABEL_14;
  }
}

```

## disassembly

```asm
0x1400031f0  test    dl, 10h
0x1400031f3  jz      short locret_140003250
0x1400031f5  cmp     dword ptr [rcx+18h], 0
0x1400031f9  jl      short locret_140003250
0x1400031fb  mov     rdx, [rcx+10h]
0x1400031ff  mov     al, [rdx+4]
0x140003202  cmp     al, 3
0x140003204  jz      short loc_14000323F
0x140003206  cmp     al, 5
0x140003208  jz      short loc_14000323A
0x14000320a  cmp     al, 7
0x14000320c  jz      short loc_14000321A
0x14000320e  cmp     al, 0Ah
0x140003210  jz      short loc_14000323A
0x140003212  cmp     al, 14h
0x140003214  jz      short loc_14000322A
0x140003216  cmp     al, 19h
0x140003218  jnz     short locret_140003250
0x14000321a  mov     eax, [rdx+18h]
0x14000321d  mov     [r8], eax
0x140003220  mov     rax, [rcx+10h]
0x140003224  mov     rcx, [rax+38h]
0x140003228  jmp     short loc_14000324D
0x14000322a  mov     eax, [rdx+20h]
0x14000322d  mov     [r8], eax
0x140003230  mov     rax, [rcx+10h]
0x140003234  mov     rcx, [rax+28h]
0x140003238  jmp     short loc_14000324D
0x14000323a  mov     eax, [rdx+18h]
0x14000323d  jmp     short loc_14000322D
0x14000323f  mov     eax, [rcx+20h]
0x140003242  mov     [r8], eax
0x140003245  mov     rax, [rcx+10h]
0x140003249  mov     rcx, [rax+30h]
0x14000324d  mov     [r9], rcx
0x140003250  retn
```
