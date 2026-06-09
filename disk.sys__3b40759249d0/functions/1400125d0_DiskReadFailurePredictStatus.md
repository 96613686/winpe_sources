# DiskReadFailurePredictStatus

- ea: `0x1400125d0`
- end: `0x1400126b3`
- name: `DiskReadFailurePredictStatus`
- size: `227`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140011ee0`
- `0x140012210`

## callees

- `0x140005bf0`
- `0x1400125d0`
- `0x140012810`

## pseudocode

```c
NTSTATUS __fastcall DiskReadFailurePredictStatus(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  int v4; // edx
  NTSTATUS result; // eax
  bool v6; // zf
  bool v7; // cl
  __int64 v8; // [rsp+40h] [rbp-58h] BYREF
  _OWORD Buffer[4]; // [rsp+48h] [rbp-50h] BYREF

  v2 = *(_QWORD *)(a1 + 96);
  *(_BYTE *)(a2 + 4) = 0;
  v4 = *(_DWORD *)(v2 + 16);
  if ( v4 == 2 )
  {
    LODWORD(v8) = 61;
    memset(Buffer, 0, 61);
    result = DiskPerformSmartCommand(a1, 1770758, 176, 218, 0, 0, (char *)Buffer, (int *)&v8);
    if ( result >= 0 )
    {
      v6 = HIBYTE(Buffer[2]) == 0xF4;
      *(_DWORD *)a2 = 0;
      v7 = v6 && LOBYTE(Buffer[3]) == 44;
      *(_BYTE *)(a2 + 4) = v7;
    }
  }
  else if ( v4 == 3 )
  {
    *(_DWORD *)a2 = *(_DWORD *)(a1 + 820);
    *(_BYTE *)(a2 + 4) = *(_BYTE *)(a1 + 819);
    return 0;
  }
  else
  {
    return -1073741808;
  }
  return result;
}

```

## disassembly

```asm
0x1400125d0  push    rbx
0x1400125d2  sub     rsp, 90h
0x1400125d9  mov     rax, cs:__security_cookie
0x1400125e0  xor     rax, rsp
0x1400125e3  mov     [rsp+98h+var_10], rax
0x1400125eb  mov     rax, [rcx+60h]
0x1400125ef  mov     rbx, rdx
0x1400125f2  mov     byte ptr [rdx+4], 0
0x1400125f6  mov     edx, [rax+10h]
0x1400125f9  cmp     edx, 2
0x1400125fc  jnz     short loc_14001267D
0x1400125fe  xorps   xmm0, xmm0
0x140012601  mov     dword ptr [rsp+98h+var_58], 3Dh ; '='
0x140012609  lea     rax, [rsp+98h+var_58]
0x14001260e  mov     r9b, 0DAh; int
0x140012611  mov     [rsp+98h+var_60], rax; __int64
0x140012616  mov     r8b, 0B0h; int
0x140012619  lea     rax, [rsp+98h+var_50]
0x14001261e  mov     edx, 1B0506h; int
0x140012623  mov     [rsp+98h+Buffer], rax; Buffer
0x140012628  movups  [rsp+98h+var_30], xmm0
0x14001262d  mov     [rsp+98h+var_70], 0; char
0x140012632  mov     [rsp+98h+var_78], 0; char
0x140012637  movups  [rsp+98h+var_50], xmm0
0x14001263c  movups  [rsp+98h+var_40], xmm0
0x140012641  movups  [rsp+98h+var_30+0Dh], xmm0
0x140012646  call    DiskPerformSmartCommand
0x14001264b  mov     edx, eax
0x14001264d  test    eax, eax
0x14001264f  js      short loc_140012663
0x140012651  xor     eax, eax
0x140012653  cmp     byte ptr [rsp+98h+var_30+0Fh], 0F4h
0x140012658  mov     [rbx], eax
0x14001265a  jz      short loc_1400126A8
0x14001265c  xor     cl, cl
0x14001265e  mov     [rbx+4], cl
0x140012661  mov     eax, edx
0x140012663  mov     rcx, [rsp+98h+var_10]
0x14001266b  xor     rcx, rsp; StackCookie
0x14001266e  call    __security_check_cookie
0x140012673  add     rsp, 90h
0x14001267a  pop     rbx
0x14001267b  retn
0x14001267d  test    edx, edx
0x14001267f  jz      short loc_1400126A1
0x140012681  sub     edx, 1
0x140012684  jz      short loc_1400126A1
0x140012686  cmp     edx, 2
0x140012689  jnz     short loc_1400126A1
0x14001268b  mov     eax, [rcx+334h]
0x140012691  mov     [rbx], eax
0x140012693  movzx   eax, byte ptr [rcx+333h]
0x14001269a  mov     [rbx+4], al
0x14001269d  xor     eax, eax
0x14001269f  jmp     short loc_140012663
0x1400126a1  mov     eax, 0C0000010h
0x1400126a6  jmp     short loc_140012663
0x1400126a8  cmp     [rsp+98h+var_20], 2Ch ; ','
0x1400126ad  jnz     short loc_14001265C
0x1400126af  mov     cl, 1
0x1400126b1  jmp     short loc_14001265E
```
