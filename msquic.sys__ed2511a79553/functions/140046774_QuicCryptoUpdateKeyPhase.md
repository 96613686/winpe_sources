# QuicCryptoUpdateKeyPhase

- ea: `0x140046774`
- end: `0x1400468ab`
- name: `QuicCryptoUpdateKeyPhase`
- size: `311`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140001d6c`
- `0x140012630`
- `0x140017580`

## callees

- `0x140008ef0`
- `0x1400426e8`
- `0x140046774`

## pseudocode

```c
char __fastcall QuicCryptoUpdateKeyPhase(__int64 a1, char a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rdi
  __int64 v9; // rax
  char v10; // cl
  char result; // al

  QuicPacketKeyFree(*(PVOID *)(a1 + 2904));
  *(_QWORD *)(*(_QWORD *)(a1 + 2912) + 16LL) = *(_QWORD *)(*(_QWORD *)(a1 + 2896) + 16LL);
  *(_QWORD *)(*(_QWORD *)(a1 + 2896) + 16LL) = 0;
  *(_QWORD *)(a1 + 2904) = *(_QWORD *)(a1 + 2896);
  v4 = *(_QWORD *)(a1 + 2912);
  *(_QWORD *)(a1 + 2912) = 0;
  *(_QWORD *)(a1 + 2896) = v4;
  QuicPacketKeyFree(*(PVOID *)(a1 + 2952));
  v5 = *(_QWORD *)(a1 + 2960);
  *(_QWORD *)(v5 + 16) = *(_QWORD *)(*(_QWORD *)(a1 + 2944) + 16LL);
  *(_QWORD *)(*(_QWORD *)(a1 + 2944) + 16LL) = 0;
  *(_QWORD *)(a1 + 2952) = *(_QWORD *)(a1 + 2944);
  v6 = *(_QWORD *)(a1 + 2960);
  *(_QWORD *)(a1 + 2960) = 0;
  *(_QWORD *)(a1 + 2944) = v6;
  v7 = *(_DWORD *)(a1 + 3848);
  if ( v7 != -1 )
    *(_DWORD *)(a1 + 3848) = v7 + 1;
  v8 = *(_QWORD *)(a1 + 2776);
  if ( (byte_14005C489 & 0x40) != 0 )
    McTemplateU0pu_EtwWriteTransfer(v5, (const EVENT_DESCRIPTOR *)QuicConnKeyPhaseChange, a1, a2);
  v9 = *(_QWORD *)(a1 + 3424);
  *(_QWORD *)(v8 + 408) = -1;
  *(_QWORD *)(v8 + 400) = v9;
  v10 = *(_BYTE *)(v8 + 424);
  result = v10 & 0xFE;
  *(_QWORD *)(v8 + 416) = 0;
  *(_BYTE *)(v8 + 424) = v10 & 0xFE | ((v10 & 1) == 0) | 2;
  return result;
}

```

## disassembly

```asm
0x140046774  mov     [rsp+arg_0], rbx
0x140046779  mov     [rsp+arg_8], rsi
0x14004677e  push    rdi
0x14004677f  sub     rsp, 20h
0x140046783  mov     rbx, rcx
0x140046786  mov     sil, dl
0x140046789  mov     rcx, [rcx+0B58h]; P
0x140046790  call    QuicPacketKeyFree
0x140046795  mov     rax, [rbx+0B50h]
0x14004679c  mov     r8, [rbx+0B60h]
0x1400467a3  mov     rax, [rax+10h]
0x1400467a7  mov     [r8+10h], rax
0x1400467ab  mov     rax, [rbx+0B50h]
0x1400467b2  and     qword ptr [rax+10h], 0
0x1400467b7  mov     rax, [rbx+0B50h]
0x1400467be  mov     [rbx+0B58h], rax
0x1400467c5  mov     rax, [rbx+0B60h]
0x1400467cc  and     qword ptr [rbx+0B60h], 0
0x1400467d4  mov     [rbx+0B50h], rax
0x1400467db  mov     rcx, [rbx+0B88h]; P
0x1400467e2  call    QuicPacketKeyFree
0x1400467e7  mov     rax, [rbx+0B80h]
0x1400467ee  mov     rcx, [rbx+0B90h]
0x1400467f5  mov     rax, [rax+10h]
0x1400467f9  mov     [rcx+10h], rax
0x1400467fd  mov     rax, [rbx+0B80h]
0x140046804  and     qword ptr [rax+10h], 0
0x140046809  mov     rax, [rbx+0B80h]
0x140046810  mov     [rbx+0B88h], rax
0x140046817  mov     rax, [rbx+0B90h]
0x14004681e  and     qword ptr [rbx+0B90h], 0
0x140046826  mov     [rbx+0B80h], rax
0x14004682d  mov     eax, [rbx+0F08h]
0x140046833  cmp     eax, 0FFFFFFFFh
0x140046836  jnb     short loc_140046840
0x140046838  inc     eax
0x14004683a  mov     [rbx+0F08h], eax
0x140046840  test    cs:byte_14005C489, 40h
0x140046847  mov     rdi, [rbx+0AD8h]
0x14004684e  jz      short loc_140046862
0x140046850  mov     r9b, sil
0x140046853  lea     rdx, QuicConnKeyPhaseChange
0x14004685a  mov     r8, rbx
0x14004685d  call    McTemplateU0pu_EtwWriteTransfer
0x140046862  mov     rax, [rbx+0D60h]
0x140046869  or      qword ptr [rdi+198h], 0FFFFFFFFFFFFFFFFh
0x140046871  mov     rbx, [rsp+28h+arg_0]
0x140046876  mov     rsi, [rsp+28h+arg_8]
0x14004687b  mov     [rdi+190h], rax
0x140046882  mov     al, [rdi+1A8h]
0x140046888  mov     cl, al
0x14004688a  and     al, 0FEh
0x14004688c  not     cl
0x14004688e  and     cl, 1
0x140046891  or      cl, al
0x140046893  or      cl, 2
0x140046896  and     qword ptr [rdi+1A0h], 0
0x14004689e  mov     [rdi+1A8h], cl
0x1400468a4  add     rsp, 20h
0x1400468a8  pop     rdi
0x1400468a9  retn
```
